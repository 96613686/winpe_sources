# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180008384`
- end: `0x180008488`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008740`
- `0x180008780`
- `0x180009db0`

## callees

- `0x180008384`
- `0x180012010`

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
0x180008384  push    rbx
0x180008386  push    rbp
0x180008387  push    rsi
0x180008388  push    rdi
0x180008389  push    r14
0x18000838b  sub     rsp, 30h
0x18000838f  mov     rsi, r9
0x180008392  mov     rdi, r8
0x180008395  mov     rbx, rdx
0x180008398  mov     r14, rcx
0x18000839b  test    rcx, rcx
0x18000839e  jz      loc_180008478
0x1800083a4  test    rdx, rdx
0x1800083a7  jz      loc_180008478
0x1800083ad  test    r9, r9
0x1800083b0  jnz     short loc_1800083BC
0x1800083b2  mov     eax, 80004003h
0x1800083b7  jmp     loc_18000847D
0x1800083bc  mov     qword ptr [r9], 0
0x1800083c3  cmp     dword ptr [r8], 0
0x1800083c7  jnz     short loc_180008401
0x1800083c9  cmp     dword ptr [r8+4], 0
0x1800083ce  jnz     short loc_180008401
0x1800083d0  cmp     dword ptr [r8+8], 0C0h
0x1800083d8  jnz     short loc_180008401
0x1800083da  cmp     dword ptr [r8+0Ch], 46000000h
0x1800083e2  jnz     short loc_180008401
0x1800083e4  mov     rbx, [rdx+8]
0x1800083e8  add     rbx, r14
0x1800083eb  mov     rcx, rbx
0x1800083ee  mov     rax, [rbx]
0x1800083f1  mov     rax, [rax+8]
0x1800083f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083fa  xor     eax, eax
0x1800083fc  mov     [rsi], rbx
0x1800083ff  jmp     short loc_18000847D
0x180008401  cmp     qword ptr [rdx+10h], 0
0x180008406  jz      short loc_180008468
0x180008408  mov     rcx, [rbx]
0x18000840b  test    rcx, rcx
0x18000840e  jnz     short loc_180008415
0x180008410  lea     ebp, [rcx+1]
0x180008413  jmp     short loc_180008435
0x180008415  mov     eax, [rdi]
0x180008417  cmp     [rcx], eax
0x180008419  jnz     short loc_18000845D
0x18000841b  mov     eax, [rdi+4]
0x18000841e  cmp     [rcx+4], eax
0x180008421  jnz     short loc_18000845D
0x180008423  mov     eax, [rdi+8]
0x180008426  cmp     [rcx+8], eax
0x180008429  jnz     short loc_18000845D
0x18000842b  mov     eax, [rdi+0Ch]
0x18000842e  cmp     [rcx+0Ch], eax
0x180008431  jnz     short loc_18000845D
0x180008433  xor     ebp, ebp
0x180008435  mov     rax, [rbx+10h]
0x180008439  cmp     rax, 1
0x18000843d  jz      short loc_18000846F
0x18000843f  mov     r9, [rbx+8]
0x180008443  mov     r8, rsi
0x180008446  mov     rdx, rdi
0x180008449  mov     rcx, r14
0x18000844c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008451  test    eax, eax
0x180008453  jz      short loc_18000847D
0x180008455  test    ebp, ebp
0x180008457  jnz     short loc_18000845D
0x180008459  test    eax, eax
0x18000845b  js      short loc_18000847D
0x18000845d  add     rbx, 18h
0x180008461  cmp     qword ptr [rbx+10h], 0
0x180008466  jnz     short loc_180008408
0x180008468  mov     eax, 80004002h
0x18000846d  jmp     short loc_18000847D
0x18000846f  mov     rbx, [rbx+8]
0x180008473  jmp     loc_1800083E8
0x180008478  mov     eax, 80070057h
0x18000847d  add     rsp, 30h
0x180008481  pop     r14
0x180008483  pop     rdi
0x180008484  pop     rsi
0x180008485  pop     rbp
0x180008486  pop     rbx
0x180008487  retn
```
