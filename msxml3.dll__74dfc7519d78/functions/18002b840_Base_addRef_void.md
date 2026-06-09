# Base::_addRef(void)

- ea: `0x18002b840`
- end: `0x18002ba0e`
- name: `?_addRef@Base@@QEAAKXZ`
- size: `462`
- prototype: `unsigned int __fastcall(Base *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002b320`
- `0x18002b3b0`
- `0x18002b650`
- `0x18002b660`
- `0x180036000`

## callees

- `0x18002b840`
- `0x18002ba14`
- `0x18004b488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b86b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b93a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b86b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b93a`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18002b9f9`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18002b9f9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b9ac`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b9ac`

## pseudocode

```c
unsigned __int64 __fastcall Base::_addRef(Base *this)
{
  unsigned __int64 v1; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rdx
  Base *v5; // r8
  unsigned __int64 result; // rax
  unsigned __int64 v7; // rax
  int v8; // ebx
  struct TLSDATA *Value; // rax
  unsigned __int64 v10; // rax
  __int64 i; // rcx
  unsigned __int64 v12; // [rsp+30h] [rbp+8h]

  v1 = *((_QWORD *)this + 1);
  if ( v1 == -1 || (v1 & 4) == 0 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v8 = g_fMultiProcessor ? 0xFA0 : 0;
        while ( 1 )
        {
          v12 = *((_QWORD *)this + 1);
          if ( v12 != -1 && v12 == _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, -1, v12) )
            break;
          if ( v8 )
            --v8;
          else
            SwitchToThread();
        }
        if ( (v12 & 1) == 0 )
          break;
        if ( (unsigned int)v12 < 8 )
          failure_tracing::record();
        v7 = v12 + 8;
        *((_QWORD *)this + 1) = v12 + 8;
        if ( v12 != -9 )
          return v7 >> 3;
      }
      Value = (struct TLSDATA *)TlsGetValue(g_dwTlsIndex);
      if ( v12 >> 3 < 0x100 )
        break;
      v10 = Base::removeFromZeroList(this, v12, Value);
      *((_QWORD *)this + 1) = v10;
      if ( (v10 & 1) != 0 )
        goto LABEL_19;
      Sleep(0);
    }
    --*((_DWORD *)Value + 48);
    *((_QWORD *)Value + (v12 >> 3) + 25) = 0;
    *((_QWORD *)this + 1) = v12 & 2 | 9;
LABEL_19:
    v7 = 8;
    return v7 >> 3;
  }
  else if ( (v1 & 1) != 0 )
  {
    if ( v1 < 8 )
      failure_tracing::record();
    *((_QWORD *)this + 1) = v1 + 8;
    return (v1 + 8) >> 3;
  }
  else
  {
    v3 = TlsGetValue(g_dwTlsIndex);
    v4 = v3;
    v5 = (Base *)v3[8];
    if ( v5 == this )
    {
      v3[8] = v1 & 0xFFFFFFFFFFFFFFF9uLL;
    }
    else
    {
      for ( i = *((_QWORD *)v5 + 1);
            (Base *)(i & 0xFFFFFFFFFFFFFFF9uLL) != this;
            i = *(_QWORD *)((i & 0xFFFFFFFFFFFFFFF9uLL) + 8) )
      {
        v5 = (Base *)(i & 0xFFFFFFFFFFFFFFF9uLL);
      }
      *((_QWORD *)v5 + 1) ^= (v1 ^ *((_QWORD *)v5 + 1)) & 0xFFFFFFFFFFFFFFF9uLL;
    }
    result = 1;
    *((_QWORD *)this + 1) = v1 & 2 | 0xD;
    --*((_DWORD *)v4 + 18);
  }
  return result;
}

```

## disassembly

```asm
0x18002b840  mov     [rsp+arg_10], rbx
0x18002b845  push    rdi
0x18002b846  sub     rsp, 20h
0x18002b84a  mov     rbx, [rcx+8]
0x18002b84e  mov     rdi, rcx
0x18002b851  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002b855  jz      short loc_18002B8D5
0x18002b857  test    bl, 4
0x18002b85a  jz      short loc_18002B8D5
0x18002b85c  test    bl, 1
0x18002b85f  jnz     loc_18002B977
0x18002b865  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002b86b  call    cs:__imp_TlsGetValue
0x18002b871  mov     rdx, rax
0x18002b874  mov     r8, [rax+40h]
0x18002b878  cmp     r8, rdi
0x18002b87b  jnz     loc_18002B9B7
0x18002b881  mov     rcx, rbx
0x18002b884  and     rcx, 0FFFFFFFFFFFFFFF9h
0x18002b888  mov     [rax+40h], rcx
0x18002b88c  and     ebx, 2
0x18002b88f  mov     eax, 1
0x18002b894  or      rbx, 0Dh
0x18002b898  mov     [rdi+8], rbx
0x18002b89c  dec     dword ptr [rdx+48h]
0x18002b89f  mov     rbx, [rsp+28h+arg_10]
0x18002b8a4  add     rsp, 20h
0x18002b8a8  pop     rdi
0x18002b8a9  retn
0x18002b8aa  cmp     ebx, 8
0x18002b8ad  jb      loc_18002BA04
0x18002b8b3  lea     rax, [rbx+8]
0x18002b8b7  mov     [rdi+8], rax
0x18002b8bb  cmp     rbx, 0FFFFFFFFFFFFFFF7h
0x18002b8bf  jz      short loc_18002B8E1
0x18002b8c1  mov     rsi, [rsp+28h+arg_8]
0x18002b8c6  shr     rax, 3
0x18002b8ca  mov     rbx, [rsp+28h+arg_10]
0x18002b8cf  add     rsp, 20h
0x18002b8d3  pop     rdi
0x18002b8d4  retn
0x18002b8d5  mov     [rsp+28h+arg_8], rsi
0x18002b8da  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002b8e1  movzx   eax, cs:?g_fMultiProcessor@@3_NA; bool g_fMultiProcessor
0x18002b8e8  neg     al
0x18002b8ea  sbb     ebx, ebx
0x18002b8ec  and     ebx, 0FA0h
0x18002b8f2  mov     rax, [rdi+8]
0x18002b8f6  mov     [rsp+28h+arg_0], rax
0x18002b8fb  mov     rax, [rsp+28h+arg_0]
0x18002b900  cmp     rax, rsi
0x18002b903  jz      short loc_18002B91A
0x18002b905  mov     rax, [rsp+28h+arg_0]
0x18002b90a  lock cmpxchg [rdi+8], rsi
0x18002b910  mov     rcx, [rsp+28h+arg_0]
0x18002b915  cmp     rcx, rax
0x18002b918  jz      short loc_18002B926
0x18002b91a  test    ebx, ebx
0x18002b91c  jz      loc_18002B9F9
0x18002b922  dec     ebx
0x18002b924  jmp     short loc_18002B8F2
0x18002b926  mov     rbx, [rsp+28h+arg_0]
0x18002b92b  test    bl, 1
0x18002b92e  jnz     loc_18002B8AA
0x18002b934  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002b93a  call    cs:__imp_TlsGetValue
0x18002b940  mov     rcx, rbx
0x18002b943  shr     rcx, 3
0x18002b947  cmp     rcx, 100h
0x18002b94e  jnb     short loc_18002B994
0x18002b950  dec     dword ptr [rax+0C0h]
0x18002b956  and     ebx, 2
0x18002b959  or      rbx, 9
0x18002b95d  mov     qword ptr [rax+rcx*8+0C8h], 0
0x18002b969  mov     [rdi+8], rbx
0x18002b96d  mov     eax, 8
0x18002b972  jmp     loc_18002B8C1
0x18002b977  cmp     rbx, 8
0x18002b97b  jb      short loc_18002B9F2
0x18002b97d  lea     rax, [rbx+8]
0x18002b981  mov     rbx, [rsp+28h+arg_10]
0x18002b986  mov     [rdi+8], rax
0x18002b98a  shr     rax, 3
0x18002b98e  add     rsp, 20h
0x18002b992  pop     rdi
0x18002b993  retn
0x18002b994  mov     r8, rax; struct TLSDATA *
0x18002b997  mov     rdx, rbx; unsigned __int64
0x18002b99a  mov     rcx, rdi; this
0x18002b99d  call    ?removeFromZeroList@Base@@AEAA_K_KPEAUTLSDATA@@@Z; Base::removeFromZeroList(unsigned __int64,TLSDATA *)
0x18002b9a2  mov     [rdi+8], rax
0x18002b9a6  test    al, 1
0x18002b9a8  jnz     short loc_18002B96D
0x18002b9aa  xor     ecx, ecx; dwMilliseconds
0x18002b9ac  call    cs:__imp_Sleep
0x18002b9b2  jmp     loc_18002B8E1
0x18002b9b7  mov     rcx, [r8+8]
0x18002b9bb  mov     rax, rcx
0x18002b9be  and     rax, 0FFFFFFFFFFFFFFF9h
0x18002b9c2  cmp     rax, rdi
0x18002b9c5  jz      short loc_18002B9DE
0x18002b9c7  mov     r8, rcx
0x18002b9ca  and     r8, 0FFFFFFFFFFFFFFF9h
0x18002b9ce  mov     rcx, [r8+8]
0x18002b9d2  mov     rax, rcx
0x18002b9d5  and     rax, 0FFFFFFFFFFFFFFF9h
0x18002b9d9  cmp     rax, rdi
0x18002b9dc  jnz     short loc_18002B9C7
0x18002b9de  mov     rcx, [r8+8]
0x18002b9e2  xor     rcx, rbx
0x18002b9e5  and     rcx, 0FFFFFFFFFFFFFFF9h
0x18002b9e9  xor     [r8+8], rcx
0x18002b9ed  jmp     loc_18002B88C
0x18002b9f2  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002b9f7  jmp     short loc_18002B97D
0x18002b9f9  call    cs:__imp_SwitchToThread
0x18002b9ff  jmp     loc_18002B8F2
0x18002ba04  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002ba09  jmp     loc_18002B8B3
```
