# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000771c`
- end: `0x180007821`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `261`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007c20`
- `0x180007c50`

## callees

- `0x18000771c`
- `0x18000f010`

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
0x18000771c  push    rbx
0x18000771e  push    rbp
0x18000771f  push    rsi
0x180007720  push    rdi
0x180007721  push    r14
0x180007723  sub     rsp, 30h
0x180007727  mov     rsi, r9
0x18000772a  mov     rdi, r8
0x18000772d  mov     rbx, rdx
0x180007730  mov     r14, rcx
0x180007733  test    rcx, rcx
0x180007736  jz      loc_180007810
0x18000773c  test    rdx, rdx
0x18000773f  jz      loc_180007810
0x180007745  test    r9, r9
0x180007748  jnz     short loc_180007754
0x18000774a  mov     eax, 80004003h
0x18000774f  jmp     loc_180007815
0x180007754  mov     qword ptr [r9], 0
0x18000775b  cmp     dword ptr [r8], 0
0x18000775f  jnz     short loc_180007799
0x180007761  cmp     dword ptr [r8+4], 0
0x180007766  jnz     short loc_180007799
0x180007768  cmp     dword ptr [r8+8], 0C0h
0x180007770  jnz     short loc_180007799
0x180007772  cmp     dword ptr [r8+0Ch], 46000000h
0x18000777a  jnz     short loc_180007799
0x18000777c  mov     rbx, [rdx+8]
0x180007780  add     rbx, r14
0x180007783  mov     rcx, rbx
0x180007786  mov     rax, [rbx]
0x180007789  mov     rax, [rax+8]
0x18000778d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007792  xor     eax, eax
0x180007794  mov     [rsi], rbx
0x180007797  jmp     short loc_180007815
0x180007799  cmp     qword ptr [rdx+10h], 0
0x18000779e  jz      short loc_180007800
0x1800077a0  mov     rcx, [rbx]
0x1800077a3  test    rcx, rcx
0x1800077a6  jnz     short loc_1800077AD
0x1800077a8  lea     ebp, [rcx+1]
0x1800077ab  jmp     short loc_1800077CD
0x1800077ad  mov     eax, [rdi]
0x1800077af  cmp     [rcx], eax
0x1800077b1  jnz     short loc_1800077F5
0x1800077b3  mov     eax, [rdi+4]
0x1800077b6  cmp     [rcx+4], eax
0x1800077b9  jnz     short loc_1800077F5
0x1800077bb  mov     eax, [rdi+8]
0x1800077be  cmp     [rcx+8], eax
0x1800077c1  jnz     short loc_1800077F5
0x1800077c3  mov     eax, [rdi+0Ch]
0x1800077c6  cmp     [rcx+0Ch], eax
0x1800077c9  jnz     short loc_1800077F5
0x1800077cb  xor     ebp, ebp
0x1800077cd  mov     rax, [rbx+10h]
0x1800077d1  cmp     rax, 1
0x1800077d5  jz      short loc_180007807
0x1800077d7  mov     r9, [rbx+8]
0x1800077db  mov     r8, rsi
0x1800077de  mov     rdx, rdi
0x1800077e1  mov     rcx, r14
0x1800077e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e9  test    eax, eax
0x1800077eb  jz      short loc_180007815
0x1800077ed  test    ebp, ebp
0x1800077ef  jnz     short loc_1800077F5
0x1800077f1  test    eax, eax
0x1800077f3  js      short loc_180007815
0x1800077f5  add     rbx, 18h
0x1800077f9  cmp     qword ptr [rbx+10h], 0
0x1800077fe  jnz     short loc_1800077A0
0x180007800  mov     eax, 80004002h
0x180007805  jmp     short loc_180007815
0x180007807  mov     rbx, [rbx+8]
0x18000780b  jmp     loc_180007780
0x180007810  mov     eax, 80070057h
0x180007815  add     rsp, 30h
0x180007819  pop     r14
0x18000781b  pop     rdi
0x18000781c  pop     rsi
0x18000781d  pop     rbp
0x18000781e  pop     rbx
0x18000781f  retn
```
