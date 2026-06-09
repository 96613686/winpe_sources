# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x140003564`
- end: `0x140003668`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003d60`
- `0x140003df0`
- `0x140003e10`

## callees

- `0x140003564`
- `0x140007010`

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
0x140003564  push    rbx
0x140003566  push    rbp
0x140003567  push    rsi
0x140003568  push    rdi
0x140003569  push    r14
0x14000356b  sub     rsp, 30h
0x14000356f  mov     rsi, r9
0x140003572  mov     rdi, r8
0x140003575  mov     rbx, rdx
0x140003578  mov     r14, rcx
0x14000357b  test    rcx, rcx
0x14000357e  jz      loc_140003658
0x140003584  test    rdx, rdx
0x140003587  jz      loc_140003658
0x14000358d  test    r9, r9
0x140003590  jnz     short loc_14000359C
0x140003592  mov     eax, 80004003h
0x140003597  jmp     loc_14000365D
0x14000359c  mov     qword ptr [r9], 0
0x1400035a3  cmp     dword ptr [r8], 0
0x1400035a7  jnz     short loc_1400035E1
0x1400035a9  cmp     dword ptr [r8+4], 0
0x1400035ae  jnz     short loc_1400035E1
0x1400035b0  cmp     dword ptr [r8+8], 0C0h
0x1400035b8  jnz     short loc_1400035E1
0x1400035ba  cmp     dword ptr [r8+0Ch], 46000000h
0x1400035c2  jnz     short loc_1400035E1
0x1400035c4  mov     rbx, [rdx+8]
0x1400035c8  add     rbx, r14
0x1400035cb  mov     rcx, rbx
0x1400035ce  mov     rax, [rbx]
0x1400035d1  mov     rax, [rax+8]
0x1400035d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035da  xor     eax, eax
0x1400035dc  mov     [rsi], rbx
0x1400035df  jmp     short loc_14000365D
0x1400035e1  cmp     qword ptr [rdx+10h], 0
0x1400035e6  jz      short loc_140003648
0x1400035e8  mov     rcx, [rbx]
0x1400035eb  test    rcx, rcx
0x1400035ee  jnz     short loc_1400035F5
0x1400035f0  lea     ebp, [rcx+1]
0x1400035f3  jmp     short loc_140003615
0x1400035f5  mov     eax, [rdi]
0x1400035f7  cmp     [rcx], eax
0x1400035f9  jnz     short loc_14000363D
0x1400035fb  mov     eax, [rdi+4]
0x1400035fe  cmp     [rcx+4], eax
0x140003601  jnz     short loc_14000363D
0x140003603  mov     eax, [rdi+8]
0x140003606  cmp     [rcx+8], eax
0x140003609  jnz     short loc_14000363D
0x14000360b  mov     eax, [rdi+0Ch]
0x14000360e  cmp     [rcx+0Ch], eax
0x140003611  jnz     short loc_14000363D
0x140003613  xor     ebp, ebp
0x140003615  mov     rax, [rbx+10h]
0x140003619  cmp     rax, 1
0x14000361d  jz      short loc_14000364F
0x14000361f  mov     r9, [rbx+8]
0x140003623  mov     r8, rsi
0x140003626  mov     rdx, rdi
0x140003629  mov     rcx, r14
0x14000362c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003631  test    eax, eax
0x140003633  jz      short loc_14000365D
0x140003635  test    ebp, ebp
0x140003637  jnz     short loc_14000363D
0x140003639  test    eax, eax
0x14000363b  js      short loc_14000365D
0x14000363d  add     rbx, 18h
0x140003641  cmp     qword ptr [rbx+10h], 0
0x140003646  jnz     short loc_1400035E8
0x140003648  mov     eax, 80004002h
0x14000364d  jmp     short loc_14000365D
0x14000364f  mov     rbx, [rbx+8]
0x140003653  jmp     loc_1400035C8
0x140003658  mov     eax, 80070057h
0x14000365d  add     rsp, 30h
0x140003661  pop     r14
0x140003663  pop     rdi
0x140003664  pop     rsi
0x140003665  pop     rbp
0x140003666  pop     rbx
0x140003667  retn
```
