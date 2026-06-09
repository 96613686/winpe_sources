# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180003280`
- end: `0x180003384`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800036d0`
- `0x1800036f0`
- `0x180003bc0`

## callees

- `0x180003280`
- `0x18000a010`

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
0x180003280  push    rbx
0x180003282  push    rbp
0x180003283  push    rsi
0x180003284  push    rdi
0x180003285  push    r14
0x180003287  sub     rsp, 30h
0x18000328b  mov     rsi, r9
0x18000328e  mov     rdi, r8
0x180003291  mov     rbx, rdx
0x180003294  mov     r14, rcx
0x180003297  test    rcx, rcx
0x18000329a  jz      loc_180003374
0x1800032a0  test    rdx, rdx
0x1800032a3  jz      loc_180003374
0x1800032a9  test    r9, r9
0x1800032ac  jnz     short loc_1800032B8
0x1800032ae  mov     eax, 80004003h
0x1800032b3  jmp     loc_180003379
0x1800032b8  mov     qword ptr [r9], 0
0x1800032bf  cmp     dword ptr [r8], 0
0x1800032c3  jnz     short loc_1800032FD
0x1800032c5  cmp     dword ptr [r8+4], 0
0x1800032ca  jnz     short loc_1800032FD
0x1800032cc  cmp     dword ptr [r8+8], 0C0h
0x1800032d4  jnz     short loc_1800032FD
0x1800032d6  cmp     dword ptr [r8+0Ch], 46000000h
0x1800032de  jnz     short loc_1800032FD
0x1800032e0  mov     rbx, [rdx+8]
0x1800032e4  add     rbx, r14
0x1800032e7  mov     rcx, rbx
0x1800032ea  mov     rax, [rbx]
0x1800032ed  mov     rax, [rax+8]
0x1800032f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f6  xor     eax, eax
0x1800032f8  mov     [rsi], rbx
0x1800032fb  jmp     short loc_180003379
0x1800032fd  cmp     qword ptr [rdx+10h], 0
0x180003302  jz      short loc_180003364
0x180003304  mov     rcx, [rbx]
0x180003307  test    rcx, rcx
0x18000330a  jnz     short loc_180003311
0x18000330c  lea     ebp, [rcx+1]
0x18000330f  jmp     short loc_180003331
0x180003311  mov     eax, [rdi]
0x180003313  cmp     [rcx], eax
0x180003315  jnz     short loc_180003359
0x180003317  mov     eax, [rdi+4]
0x18000331a  cmp     [rcx+4], eax
0x18000331d  jnz     short loc_180003359
0x18000331f  mov     eax, [rdi+8]
0x180003322  cmp     [rcx+8], eax
0x180003325  jnz     short loc_180003359
0x180003327  mov     eax, [rdi+0Ch]
0x18000332a  cmp     [rcx+0Ch], eax
0x18000332d  jnz     short loc_180003359
0x18000332f  xor     ebp, ebp
0x180003331  mov     rax, [rbx+10h]
0x180003335  cmp     rax, 1
0x180003339  jz      short loc_18000336B
0x18000333b  mov     r9, [rbx+8]
0x18000333f  mov     r8, rsi
0x180003342  mov     rdx, rdi
0x180003345  mov     rcx, r14
0x180003348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334d  test    eax, eax
0x18000334f  jz      short loc_180003379
0x180003351  test    ebp, ebp
0x180003353  jnz     short loc_180003359
0x180003355  test    eax, eax
0x180003357  js      short loc_180003379
0x180003359  add     rbx, 18h
0x18000335d  cmp     qword ptr [rbx+10h], 0
0x180003362  jnz     short loc_180003304
0x180003364  mov     eax, 80004002h
0x180003369  jmp     short loc_180003379
0x18000336b  mov     rbx, [rbx+8]
0x18000336f  jmp     loc_1800032E4
0x180003374  mov     eax, 80070057h
0x180003379  add     rsp, 30h
0x18000337d  pop     r14
0x18000337f  pop     rdi
0x180003380  pop     rsi
0x180003381  pop     rbp
0x180003382  pop     rbx
0x180003383  retn
```
