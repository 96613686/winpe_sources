# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180006f94`
- end: `0x180007098`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007570`
- `0x1800075e0`
- `0x1800076e0`
- `0x180007720`
- `0x180007770`
- `0x18000cb50`

## callees

- `0x180006f94`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x180006f94  push    rbx
0x180006f96  push    rbp
0x180006f97  push    rsi
0x180006f98  push    rdi
0x180006f99  push    r14
0x180006f9b  sub     rsp, 30h
0x180006f9f  mov     rsi, r9
0x180006fa2  mov     rdi, r8
0x180006fa5  mov     rbx, rdx
0x180006fa8  mov     r14, rcx
0x180006fab  test    rcx, rcx
0x180006fae  jz      loc_180007088
0x180006fb4  test    rdx, rdx
0x180006fb7  jz      loc_180007088
0x180006fbd  test    r9, r9
0x180006fc0  jnz     short loc_180006FCC
0x180006fc2  mov     eax, 80004003h
0x180006fc7  jmp     loc_18000708D
0x180006fcc  mov     qword ptr [r9], 0
0x180006fd3  cmp     dword ptr [r8], 0
0x180006fd7  jnz     short loc_180007011
0x180006fd9  cmp     dword ptr [r8+4], 0
0x180006fde  jnz     short loc_180007011
0x180006fe0  cmp     dword ptr [r8+8], 0C0h
0x180006fe8  jnz     short loc_180007011
0x180006fea  cmp     dword ptr [r8+0Ch], 46000000h
0x180006ff2  jnz     short loc_180007011
0x180006ff4  mov     rbx, [rdx+8]
0x180006ff8  add     rbx, r14
0x180006ffb  mov     rcx, rbx
0x180006ffe  mov     rax, [rbx]
0x180007001  mov     rax, [rax+8]
0x180007005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000700a  xor     eax, eax
0x18000700c  mov     [rsi], rbx
0x18000700f  jmp     short loc_18000708D
0x180007011  cmp     qword ptr [rdx+10h], 0
0x180007016  jz      short loc_180007078
0x180007018  mov     rcx, [rbx]
0x18000701b  test    rcx, rcx
0x18000701e  jnz     short loc_180007025
0x180007020  lea     ebp, [rcx+1]
0x180007023  jmp     short loc_180007045
0x180007025  mov     eax, [rdi]
0x180007027  cmp     [rcx], eax
0x180007029  jnz     short loc_18000706D
0x18000702b  mov     eax, [rdi+4]
0x18000702e  cmp     [rcx+4], eax
0x180007031  jnz     short loc_18000706D
0x180007033  mov     eax, [rdi+8]
0x180007036  cmp     [rcx+8], eax
0x180007039  jnz     short loc_18000706D
0x18000703b  mov     eax, [rdi+0Ch]
0x18000703e  cmp     [rcx+0Ch], eax
0x180007041  jnz     short loc_18000706D
0x180007043  xor     ebp, ebp
0x180007045  mov     rax, [rbx+10h]
0x180007049  cmp     rax, 1
0x18000704d  jz      short loc_18000707F
0x18000704f  mov     r9, [rbx+8]
0x180007053  mov     r8, rsi
0x180007056  mov     rdx, rdi
0x180007059  mov     rcx, r14
0x18000705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007061  test    eax, eax
0x180007063  jz      short loc_18000708D
0x180007065  test    ebp, ebp
0x180007067  jnz     short loc_18000706D
0x180007069  test    eax, eax
0x18000706b  js      short loc_18000708D
0x18000706d  add     rbx, 18h
0x180007071  cmp     qword ptr [rbx+10h], 0
0x180007076  jnz     short loc_180007018
0x180007078  mov     eax, 80004002h
0x18000707d  jmp     short loc_18000708D
0x18000707f  mov     rbx, [rbx+8]
0x180007083  jmp     loc_180006FF8
0x180007088  mov     eax, 80070057h
0x18000708d  add     rsp, 30h
0x180007091  pop     r14
0x180007093  pop     rdi
0x180007094  pop     rsi
0x180007095  pop     rbp
0x180007096  pop     rbx
0x180007097  retn
```
