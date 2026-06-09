# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000410c`
- end: `0x180004210`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800049d0`
- `0x180004a40`
- `0x180004ab0`
- `0x180004b20`
- `0x180004b80`
- `0x180004bb0`
- `0x180004bd0`

## callees

- `0x18000410c`
- `0x18000b010`

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
0x18000410c  push    rbx
0x18000410e  push    rbp
0x18000410f  push    rsi
0x180004110  push    rdi
0x180004111  push    r14
0x180004113  sub     rsp, 30h
0x180004117  mov     rsi, r9
0x18000411a  mov     rdi, r8
0x18000411d  mov     rbx, rdx
0x180004120  mov     r14, rcx
0x180004123  test    rcx, rcx
0x180004126  jz      loc_180004200
0x18000412c  test    rdx, rdx
0x18000412f  jz      loc_180004200
0x180004135  test    r9, r9
0x180004138  jnz     short loc_180004144
0x18000413a  mov     eax, 80004003h
0x18000413f  jmp     loc_180004205
0x180004144  mov     qword ptr [r9], 0
0x18000414b  cmp     dword ptr [r8], 0
0x18000414f  jnz     short loc_180004189
0x180004151  cmp     dword ptr [r8+4], 0
0x180004156  jnz     short loc_180004189
0x180004158  cmp     dword ptr [r8+8], 0C0h
0x180004160  jnz     short loc_180004189
0x180004162  cmp     dword ptr [r8+0Ch], 46000000h
0x18000416a  jnz     short loc_180004189
0x18000416c  mov     rbx, [rdx+8]
0x180004170  add     rbx, r14
0x180004173  mov     rcx, rbx
0x180004176  mov     rax, [rbx]
0x180004179  mov     rax, [rax+8]
0x18000417d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004182  xor     eax, eax
0x180004184  mov     [rsi], rbx
0x180004187  jmp     short loc_180004205
0x180004189  cmp     qword ptr [rdx+10h], 0
0x18000418e  jz      short loc_1800041F0
0x180004190  mov     rcx, [rbx]
0x180004193  test    rcx, rcx
0x180004196  jnz     short loc_18000419D
0x180004198  lea     ebp, [rcx+1]
0x18000419b  jmp     short loc_1800041BD
0x18000419d  mov     eax, [rdi]
0x18000419f  cmp     [rcx], eax
0x1800041a1  jnz     short loc_1800041E5
0x1800041a3  mov     eax, [rdi+4]
0x1800041a6  cmp     [rcx+4], eax
0x1800041a9  jnz     short loc_1800041E5
0x1800041ab  mov     eax, [rdi+8]
0x1800041ae  cmp     [rcx+8], eax
0x1800041b1  jnz     short loc_1800041E5
0x1800041b3  mov     eax, [rdi+0Ch]
0x1800041b6  cmp     [rcx+0Ch], eax
0x1800041b9  jnz     short loc_1800041E5
0x1800041bb  xor     ebp, ebp
0x1800041bd  mov     rax, [rbx+10h]
0x1800041c1  cmp     rax, 1
0x1800041c5  jz      short loc_1800041F7
0x1800041c7  mov     r9, [rbx+8]
0x1800041cb  mov     r8, rsi
0x1800041ce  mov     rdx, rdi
0x1800041d1  mov     rcx, r14
0x1800041d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d9  test    eax, eax
0x1800041db  jz      short loc_180004205
0x1800041dd  test    ebp, ebp
0x1800041df  jnz     short loc_1800041E5
0x1800041e1  test    eax, eax
0x1800041e3  js      short loc_180004205
0x1800041e5  add     rbx, 18h
0x1800041e9  cmp     qword ptr [rbx+10h], 0
0x1800041ee  jnz     short loc_180004190
0x1800041f0  mov     eax, 80004002h
0x1800041f5  jmp     short loc_180004205
0x1800041f7  mov     rbx, [rbx+8]
0x1800041fb  jmp     loc_180004170
0x180004200  mov     eax, 80070057h
0x180004205  add     rsp, 30h
0x180004209  pop     r14
0x18000420b  pop     rdi
0x18000420c  pop     rsi
0x18000420d  pop     rbp
0x18000420e  pop     rbx
0x18000420f  retn
```
