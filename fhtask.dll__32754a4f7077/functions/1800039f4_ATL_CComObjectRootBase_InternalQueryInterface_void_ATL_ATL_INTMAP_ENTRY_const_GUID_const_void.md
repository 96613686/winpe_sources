# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800039f4`
- end: `0x180003af8`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003fd0`
- `0x180004040`
- `0x1800040d0`
- `0x1800040f0`
- `0x180004110`

## callees

- `0x1800039f4`
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
0x1800039f4  push    rbx
0x1800039f6  push    rbp
0x1800039f7  push    rsi
0x1800039f8  push    rdi
0x1800039f9  push    r14
0x1800039fb  sub     rsp, 30h
0x1800039ff  mov     rsi, r9
0x180003a02  mov     rdi, r8
0x180003a05  mov     rbx, rdx
0x180003a08  mov     r14, rcx
0x180003a0b  test    rcx, rcx
0x180003a0e  jz      loc_180003AE8
0x180003a14  test    rdx, rdx
0x180003a17  jz      loc_180003AE8
0x180003a1d  test    r9, r9
0x180003a20  jnz     short loc_180003A2C
0x180003a22  mov     eax, 80004003h
0x180003a27  jmp     loc_180003AED
0x180003a2c  mov     qword ptr [r9], 0
0x180003a33  cmp     dword ptr [r8], 0
0x180003a37  jnz     short loc_180003A71
0x180003a39  cmp     dword ptr [r8+4], 0
0x180003a3e  jnz     short loc_180003A71
0x180003a40  cmp     dword ptr [r8+8], 0C0h
0x180003a48  jnz     short loc_180003A71
0x180003a4a  cmp     dword ptr [r8+0Ch], 46000000h
0x180003a52  jnz     short loc_180003A71
0x180003a54  mov     rbx, [rdx+8]
0x180003a58  add     rbx, r14
0x180003a5b  mov     rcx, rbx
0x180003a5e  mov     rax, [rbx]
0x180003a61  mov     rax, [rax+8]
0x180003a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6a  xor     eax, eax
0x180003a6c  mov     [rsi], rbx
0x180003a6f  jmp     short loc_180003AED
0x180003a71  cmp     qword ptr [rdx+10h], 0
0x180003a76  jz      short loc_180003AD8
0x180003a78  mov     rcx, [rbx]
0x180003a7b  test    rcx, rcx
0x180003a7e  jnz     short loc_180003A85
0x180003a80  lea     ebp, [rcx+1]
0x180003a83  jmp     short loc_180003AA5
0x180003a85  mov     eax, [rdi]
0x180003a87  cmp     [rcx], eax
0x180003a89  jnz     short loc_180003ACD
0x180003a8b  mov     eax, [rdi+4]
0x180003a8e  cmp     [rcx+4], eax
0x180003a91  jnz     short loc_180003ACD
0x180003a93  mov     eax, [rdi+8]
0x180003a96  cmp     [rcx+8], eax
0x180003a99  jnz     short loc_180003ACD
0x180003a9b  mov     eax, [rdi+0Ch]
0x180003a9e  cmp     [rcx+0Ch], eax
0x180003aa1  jnz     short loc_180003ACD
0x180003aa3  xor     ebp, ebp
0x180003aa5  mov     rax, [rbx+10h]
0x180003aa9  cmp     rax, 1
0x180003aad  jz      short loc_180003ADF
0x180003aaf  mov     r9, [rbx+8]
0x180003ab3  mov     r8, rsi
0x180003ab6  mov     rdx, rdi
0x180003ab9  mov     rcx, r14
0x180003abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac1  test    eax, eax
0x180003ac3  jz      short loc_180003AED
0x180003ac5  test    ebp, ebp
0x180003ac7  jnz     short loc_180003ACD
0x180003ac9  test    eax, eax
0x180003acb  js      short loc_180003AED
0x180003acd  add     rbx, 18h
0x180003ad1  cmp     qword ptr [rbx+10h], 0
0x180003ad6  jnz     short loc_180003A78
0x180003ad8  mov     eax, 80004002h
0x180003add  jmp     short loc_180003AED
0x180003adf  mov     rbx, [rbx+8]
0x180003ae3  jmp     loc_180003A58
0x180003ae8  mov     eax, 80070057h
0x180003aed  add     rsp, 30h
0x180003af1  pop     r14
0x180003af3  pop     rdi
0x180003af4  pop     rsi
0x180003af5  pop     rbp
0x180003af6  pop     rbx
0x180003af7  retn
```
