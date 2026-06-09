# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180004a5c`
- end: `0x180004b60`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005030`
- `0x1800050a0`
- `0x180005130`
- `0x180005150`
- `0x180005170`
- `0x1800070d0`

## callees

- `0x180004a5c`
- `0x18000c010`

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
0x180004a5c  push    rbx
0x180004a5e  push    rbp
0x180004a5f  push    rsi
0x180004a60  push    rdi
0x180004a61  push    r14
0x180004a63  sub     rsp, 30h
0x180004a67  mov     rsi, r9
0x180004a6a  mov     rdi, r8
0x180004a6d  mov     rbx, rdx
0x180004a70  mov     r14, rcx
0x180004a73  test    rcx, rcx
0x180004a76  jz      loc_180004B50
0x180004a7c  test    rdx, rdx
0x180004a7f  jz      loc_180004B50
0x180004a85  test    r9, r9
0x180004a88  jnz     short loc_180004A94
0x180004a8a  mov     eax, 80004003h
0x180004a8f  jmp     loc_180004B55
0x180004a94  mov     qword ptr [r9], 0
0x180004a9b  cmp     dword ptr [r8], 0
0x180004a9f  jnz     short loc_180004AD9
0x180004aa1  cmp     dword ptr [r8+4], 0
0x180004aa6  jnz     short loc_180004AD9
0x180004aa8  cmp     dword ptr [r8+8], 0C0h
0x180004ab0  jnz     short loc_180004AD9
0x180004ab2  cmp     dword ptr [r8+0Ch], 46000000h
0x180004aba  jnz     short loc_180004AD9
0x180004abc  mov     rbx, [rdx+8]
0x180004ac0  add     rbx, r14
0x180004ac3  mov     rcx, rbx
0x180004ac6  mov     rax, [rbx]
0x180004ac9  mov     rax, [rax+8]
0x180004acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad2  xor     eax, eax
0x180004ad4  mov     [rsi], rbx
0x180004ad7  jmp     short loc_180004B55
0x180004ad9  cmp     qword ptr [rdx+10h], 0
0x180004ade  jz      short loc_180004B40
0x180004ae0  mov     rcx, [rbx]
0x180004ae3  test    rcx, rcx
0x180004ae6  jnz     short loc_180004AED
0x180004ae8  lea     ebp, [rcx+1]
0x180004aeb  jmp     short loc_180004B0D
0x180004aed  mov     eax, [rdi]
0x180004aef  cmp     [rcx], eax
0x180004af1  jnz     short loc_180004B35
0x180004af3  mov     eax, [rdi+4]
0x180004af6  cmp     [rcx+4], eax
0x180004af9  jnz     short loc_180004B35
0x180004afb  mov     eax, [rdi+8]
0x180004afe  cmp     [rcx+8], eax
0x180004b01  jnz     short loc_180004B35
0x180004b03  mov     eax, [rdi+0Ch]
0x180004b06  cmp     [rcx+0Ch], eax
0x180004b09  jnz     short loc_180004B35
0x180004b0b  xor     ebp, ebp
0x180004b0d  mov     rax, [rbx+10h]
0x180004b11  cmp     rax, 1
0x180004b15  jz      short loc_180004B47
0x180004b17  mov     r9, [rbx+8]
0x180004b1b  mov     r8, rsi
0x180004b1e  mov     rdx, rdi
0x180004b21  mov     rcx, r14
0x180004b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b29  test    eax, eax
0x180004b2b  jz      short loc_180004B55
0x180004b2d  test    ebp, ebp
0x180004b2f  jnz     short loc_180004B35
0x180004b31  test    eax, eax
0x180004b33  js      short loc_180004B55
0x180004b35  add     rbx, 18h
0x180004b39  cmp     qword ptr [rbx+10h], 0
0x180004b3e  jnz     short loc_180004AE0
0x180004b40  mov     eax, 80004002h
0x180004b45  jmp     short loc_180004B55
0x180004b47  mov     rbx, [rbx+8]
0x180004b4b  jmp     loc_180004AC0
0x180004b50  mov     eax, 80070057h
0x180004b55  add     rsp, 30h
0x180004b59  pop     r14
0x180004b5b  pop     rdi
0x180004b5c  pop     rsi
0x180004b5d  pop     rbp
0x180004b5e  pop     rbx
0x180004b5f  retn
```
