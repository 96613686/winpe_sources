# AccWrap_AddIAccProp::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x180014700`
- end: `0x18001479d`
- name: `?GetIdentityString@AccWrap_AddIAccProp@@UEAAJKPEAPEAEPEAK@Z`
- size: `157`
- prototype: `__int64 __fastcall(AccWrap_AddIAccProp *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014700`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014755`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014755`

## pseudocode

```c
__int64 __fastcall AccWrap_AddIAccProp::GetIdentityString(
        AccWrap_AddIAccProp *this,
        int a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  unsigned int v8; // ecx
  __int64 result; // rax
  unsigned __int8 *v10; // rcx
  int v11; // eax

  *a3 = 0;
  *a4 = 0;
  if ( *((_DWORD *)this + 26) )
  {
    if ( *((_QWORD *)this + 12) )
    {
      v10 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
      if ( v10 )
      {
        v11 = *((_DWORD *)this + 24);
        *(_DWORD *)v10 = -2147483647;
        *((_DWORD *)v10 + 1) = v11;
        result = 0;
        *((_DWORD *)v10 + 2) = -4;
        *((_DWORD *)v10 + 3) = a2;
        *a3 = v10;
        *a4 = 16;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      return 2147500033LL;
    }
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8));
    result = 0;
    if ( v8 )
      return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180014700  push    rbx
0x180014702  push    rbp
0x180014703  push    rsi
0x180014704  push    rdi
0x180014705  push    r14
0x180014707  sub     rsp, 30h
0x18001470b  xor     r14d, r14d
0x18001470e  mov     rdi, r9
0x180014711  mov     [r8], r14
0x180014714  mov     rsi, r8
0x180014717  mov     [r9], r14d
0x18001471a  mov     ebp, edx
0x18001471c  mov     rbx, rcx
0x18001471f  cmp     [rcx+68h], r14d
0x180014723  jnz     short loc_18001474A
0x180014725  mov     rcx, [rcx+40h]
0x180014729  mov     rax, [rcx]
0x18001472c  mov     rax, [rax+18h]
0x180014730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014735  mov     ecx, eax
0x180014737  mov     eax, r14d
0x18001473a  test    ecx, ecx
0x18001473c  cmovnz  eax, ecx
0x18001473f  add     rsp, 30h
0x180014743  pop     r14
0x180014745  pop     rdi
0x180014746  pop     rsi
0x180014747  pop     rbp
0x180014748  pop     rbx
0x180014749  retn
0x18001474a  cmp     [rcx+60h], r14
0x18001474e  jz      short loc_180014786
0x180014750  mov     ecx, 10h; cb
0x180014755  call    cs:__imp_CoTaskMemAlloc
0x18001475b  mov     rcx, rax
0x18001475e  test    rax, rax
0x180014761  jz      short loc_180014796
0x180014763  mov     eax, [rbx+60h]
0x180014766  mov     dword ptr [rcx], 80000001h
0x18001476c  mov     [rcx+4], eax
0x18001476f  xor     eax, eax
0x180014771  mov     dword ptr [rcx+8], 0FFFFFFFCh
0x180014778  mov     [rcx+0Ch], ebp
0x18001477b  mov     [rsi], rcx
0x18001477e  mov     dword ptr [rdi], 10h
0x180014784  jmp     short loc_18001473F
0x180014786  mov     eax, 80004001h
0x18001478b  add     rsp, 30h
0x18001478f  pop     r14
0x180014791  pop     rdi
0x180014792  pop     rsi
0x180014793  pop     rbp
0x180014794  pop     rbx
0x180014795  retn
0x180014796  mov     eax, 8007000Eh
0x18001479b  jmp     short loc_18001473F
```
