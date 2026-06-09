# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180004684`
- end: `0x180004788`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004c70`
- `0x180004d00`
- `0x180004d20`

## callees

- `0x180004684`
- `0x180013010`

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
0x180004684  push    rbx
0x180004686  push    rbp
0x180004687  push    rsi
0x180004688  push    rdi
0x180004689  push    r14
0x18000468b  sub     rsp, 30h
0x18000468f  mov     rsi, r9
0x180004692  mov     rdi, r8
0x180004695  mov     rbx, rdx
0x180004698  mov     r14, rcx
0x18000469b  test    rcx, rcx
0x18000469e  jz      loc_180004778
0x1800046a4  test    rdx, rdx
0x1800046a7  jz      loc_180004778
0x1800046ad  test    r9, r9
0x1800046b0  jnz     short loc_1800046BC
0x1800046b2  mov     eax, 80004003h
0x1800046b7  jmp     loc_18000477D
0x1800046bc  mov     qword ptr [r9], 0
0x1800046c3  cmp     dword ptr [r8], 0
0x1800046c7  jnz     short loc_180004701
0x1800046c9  cmp     dword ptr [r8+4], 0
0x1800046ce  jnz     short loc_180004701
0x1800046d0  cmp     dword ptr [r8+8], 0C0h
0x1800046d8  jnz     short loc_180004701
0x1800046da  cmp     dword ptr [r8+0Ch], 46000000h
0x1800046e2  jnz     short loc_180004701
0x1800046e4  mov     rbx, [rdx+8]
0x1800046e8  add     rbx, r14
0x1800046eb  mov     rcx, rbx
0x1800046ee  mov     rax, [rbx]
0x1800046f1  mov     rax, [rax+8]
0x1800046f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fa  xor     eax, eax
0x1800046fc  mov     [rsi], rbx
0x1800046ff  jmp     short loc_18000477D
0x180004701  cmp     qword ptr [rdx+10h], 0
0x180004706  jz      short loc_180004768
0x180004708  mov     rcx, [rbx]
0x18000470b  test    rcx, rcx
0x18000470e  jnz     short loc_180004715
0x180004710  lea     ebp, [rcx+1]
0x180004713  jmp     short loc_180004735
0x180004715  mov     eax, [rdi]
0x180004717  cmp     [rcx], eax
0x180004719  jnz     short loc_18000475D
0x18000471b  mov     eax, [rdi+4]
0x18000471e  cmp     [rcx+4], eax
0x180004721  jnz     short loc_18000475D
0x180004723  mov     eax, [rdi+8]
0x180004726  cmp     [rcx+8], eax
0x180004729  jnz     short loc_18000475D
0x18000472b  mov     eax, [rdi+0Ch]
0x18000472e  cmp     [rcx+0Ch], eax
0x180004731  jnz     short loc_18000475D
0x180004733  xor     ebp, ebp
0x180004735  mov     rax, [rbx+10h]
0x180004739  cmp     rax, 1
0x18000473d  jz      short loc_18000476F
0x18000473f  mov     r9, [rbx+8]
0x180004743  mov     r8, rsi
0x180004746  mov     rdx, rdi
0x180004749  mov     rcx, r14
0x18000474c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004751  test    eax, eax
0x180004753  jz      short loc_18000477D
0x180004755  test    ebp, ebp
0x180004757  jnz     short loc_18000475D
0x180004759  test    eax, eax
0x18000475b  js      short loc_18000477D
0x18000475d  add     rbx, 18h
0x180004761  cmp     qword ptr [rbx+10h], 0
0x180004766  jnz     short loc_180004708
0x180004768  mov     eax, 80004002h
0x18000476d  jmp     short loc_18000477D
0x18000476f  mov     rbx, [rbx+8]
0x180004773  jmp     loc_1800046E8
0x180004778  mov     eax, 80070057h
0x18000477d  add     rsp, 30h
0x180004781  pop     r14
0x180004783  pop     rdi
0x180004784  pop     rsi
0x180004785  pop     rbp
0x180004786  pop     rbx
0x180004787  retn
```
