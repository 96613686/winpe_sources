# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000c048`
- end: `0x18000c14c`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c1a0`
- `0x18000c230`
- `0x18000c250`

## callees

- `0x18000c048`
- `0x180011010`

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
0x18000c048  push    rbx
0x18000c04a  push    rbp
0x18000c04b  push    rsi
0x18000c04c  push    rdi
0x18000c04d  push    r14
0x18000c04f  sub     rsp, 30h
0x18000c053  mov     rsi, r9
0x18000c056  mov     rdi, r8
0x18000c059  mov     rbx, rdx
0x18000c05c  mov     r14, rcx
0x18000c05f  test    rcx, rcx
0x18000c062  jz      loc_18000C13C
0x18000c068  test    rdx, rdx
0x18000c06b  jz      loc_18000C13C
0x18000c071  test    r9, r9
0x18000c074  jnz     short loc_18000C080
0x18000c076  mov     eax, 80004003h
0x18000c07b  jmp     loc_18000C141
0x18000c080  mov     qword ptr [r9], 0
0x18000c087  cmp     dword ptr [r8], 0
0x18000c08b  jnz     short loc_18000C0C5
0x18000c08d  cmp     dword ptr [r8+4], 0
0x18000c092  jnz     short loc_18000C0C5
0x18000c094  cmp     dword ptr [r8+8], 0C0h
0x18000c09c  jnz     short loc_18000C0C5
0x18000c09e  cmp     dword ptr [r8+0Ch], 46000000h
0x18000c0a6  jnz     short loc_18000C0C5
0x18000c0a8  mov     rbx, [rdx+8]
0x18000c0ac  add     rbx, r14
0x18000c0af  mov     rcx, rbx
0x18000c0b2  mov     rax, [rbx]
0x18000c0b5  mov     rax, [rax+8]
0x18000c0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0be  xor     eax, eax
0x18000c0c0  mov     [rsi], rbx
0x18000c0c3  jmp     short loc_18000C141
0x18000c0c5  cmp     qword ptr [rdx+10h], 0
0x18000c0ca  jz      short loc_18000C12C
0x18000c0cc  mov     rcx, [rbx]
0x18000c0cf  test    rcx, rcx
0x18000c0d2  jnz     short loc_18000C0D9
0x18000c0d4  lea     ebp, [rcx+1]
0x18000c0d7  jmp     short loc_18000C0F9
0x18000c0d9  mov     eax, [rdi]
0x18000c0db  cmp     [rcx], eax
0x18000c0dd  jnz     short loc_18000C121
0x18000c0df  mov     eax, [rdi+4]
0x18000c0e2  cmp     [rcx+4], eax
0x18000c0e5  jnz     short loc_18000C121
0x18000c0e7  mov     eax, [rdi+8]
0x18000c0ea  cmp     [rcx+8], eax
0x18000c0ed  jnz     short loc_18000C121
0x18000c0ef  mov     eax, [rdi+0Ch]
0x18000c0f2  cmp     [rcx+0Ch], eax
0x18000c0f5  jnz     short loc_18000C121
0x18000c0f7  xor     ebp, ebp
0x18000c0f9  mov     rax, [rbx+10h]
0x18000c0fd  cmp     rax, 1
0x18000c101  jz      short loc_18000C133
0x18000c103  mov     r9, [rbx+8]
0x18000c107  mov     r8, rsi
0x18000c10a  mov     rdx, rdi
0x18000c10d  mov     rcx, r14
0x18000c110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c115  test    eax, eax
0x18000c117  jz      short loc_18000C141
0x18000c119  test    ebp, ebp
0x18000c11b  jnz     short loc_18000C121
0x18000c11d  test    eax, eax
0x18000c11f  js      short loc_18000C141
0x18000c121  add     rbx, 18h
0x18000c125  cmp     qword ptr [rbx+10h], 0
0x18000c12a  jnz     short loc_18000C0CC
0x18000c12c  mov     eax, 80004002h
0x18000c131  jmp     short loc_18000C141
0x18000c133  mov     rbx, [rbx+8]
0x18000c137  jmp     loc_18000C0AC
0x18000c13c  mov     eax, 80070057h
0x18000c141  add     rsp, 30h
0x18000c145  pop     r14
0x18000c147  pop     rdi
0x18000c148  pop     rsi
0x18000c149  pop     rbp
0x18000c14a  pop     rbx
0x18000c14b  retn
```
