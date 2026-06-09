# NCryptIsAlgSupported

- ea: `0x180011310`
- end: `0x180011461`
- name: `NCryptIsAlgSupported`
- size: `337`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszAlgId, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a670`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x18000e120`
- `0x180011310`
- `0x180011cb0`
- `0x180020010`

## string_xrefs

- `0x1800113ad`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001143e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptIsAlgSupported(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszAlgId, DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE *v6; // rdx
  __int64 v7; // rdi
  NCryptKeyName **v8; // r8
  NCryptAlgorithmName **v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  BYTE *v15; // [rsp+90h] [rbp+28h]
  DWORD v16; // [rsp+98h] [rbp+30h]
  DWORD *v17; // [rsp+A0h] [rbp+38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, dwFlags, hProvider, (__int64)pszAlgId, dwFlags);
  v7 = ValidateAndReferenceProvider(hProvider);
  if ( v7 )
  {
    while ( 1 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, _QWORD))(v7 + 136))(*(_QWORD *)(v7 + 272), pszAlgId, dwFlags);
      v11 = v10;
      if ( v10 != -2146893778 )
      {
        if ( !v10 )
          goto LABEL_5;
LABEL_14:
        v13 = 2618;
        v14 = v11;
        goto LABEL_15;
      }
      if ( (dwFlags & 0x40) != 0 )
        break;
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(v7 + 192))(
              *(_QWORD *)(v7 + 272),
              0,
              L"NCryptIsAlgSupported",
              0);
      if ( v11 )
        goto LABEL_14;
    }
    v11 = -2146893790;
    v13 = 2600;
    v14 = 2148073506LL;
LABEL_15:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v13);
LABEL_5:
    DereferenceProvider(v7);
  }
  else
  {
    v11 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v6,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        20);
  }
  return NormalizeNteStatus(v11, v6, v8, v9, v15, v16, v17);
}

```

## disassembly

```asm
0x180011310  push    rbx
0x180011312  push    rbp
0x180011313  push    rsi
0x180011314  push    rdi
0x180011315  push    r14
0x180011317  sub     rsp, 40h
0x18001131b  mov     esi, r8d
0x18001131e  mov     rbp, rdx
0x180011321  mov     rbx, rcx
0x180011324  mov     rcx, cs:WPP_GLOBAL_Control
0x18001132b  lea     r14, WPP_GLOBAL_Control
0x180011332  cmp     rcx, r14
0x180011335  jnz     loc_1800113D7
0x18001133b  mov     rcx, rbx
0x18001133e  call    ValidateAndReferenceProvider
0x180011343  mov     rdi, rax
0x180011346  test    rax, rax
0x180011349  jz      short loc_180011392
0x18001134b  mov     rcx, [rdi+110h]
0x180011352  mov     r8d, esi
0x180011355  mov     rax, [rdi+88h]
0x18001135c  mov     rdx, rbp
0x18001135f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011364  mov     ebx, eax
0x180011366  cmp     eax, 8009002Eh
0x18001136b  jz      loc_180011400
0x180011371  test    eax, eax
0x180011373  jnz     loc_18001142F
0x180011379  mov     rcx, rdi
0x18001137c  call    DereferenceProvider
0x180011381  mov     ecx, ebx
0x180011383  add     rsp, 40h
0x180011387  pop     r14
0x180011389  pop     rdi
0x18001138a  pop     rsi
0x18001138b  pop     rbp
0x18001138c  pop     rbx
0x18001138d  jmp     NormalizeNteStatus
0x180011392  mov     ebx, 80090026h
0x180011397  mov     rcx, cs:WPP_GLOBAL_Control
0x18001139e  cmp     rcx, r14
0x1800113a1  jz      short loc_180011381
0x1800113a3  test    byte ptr [rcx+1Ch], 1
0x1800113a7  jz      short loc_180011381
0x1800113a9  mov     rcx, [rcx+10h]
0x1800113ad  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800113b4  mov     [rsp+68h+var_38], 0A14h
0x1800113bc  lea     r9, aStatus; "Status"
0x1800113c3  mov     [rsp+68h+var_40], r8
0x1800113c8  mov     dword ptr [rsp+68h+var_48], 80090026h
0x1800113d0  call    WPP_SF_sDsd
0x1800113d5  jmp     short loc_180011381
0x1800113d7  test    byte ptr [rcx+1Ch], 4
0x1800113db  jz      loc_18001133B
0x1800113e1  mov     rcx, [rcx+10h]
0x1800113e5  mov     edx, 18h
0x1800113ea  mov     dword ptr [rsp+68h+var_40], esi
0x1800113ee  mov     r9, rbx
0x1800113f1  mov     [rsp+68h+var_48], rbp
0x1800113f6  call    WPP_SF_PSD
0x1800113fb  jmp     loc_18001133B
0x180011400  test    sil, 40h
0x180011404  jnz     short loc_18001144F
0x180011406  mov     rcx, [rdi+110h]
0x18001140d  lea     r8, aNcryptisalgsup_0; "NCryptIsAlgSupported"
0x180011414  mov     rax, [rdi+0C0h]
0x18001141b  xor     r9d, r9d
0x18001141e  xor     edx, edx
0x180011420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011425  mov     ebx, eax
0x180011427  test    eax, eax
0x180011429  jz      loc_18001134B
0x18001142f  mov     r9d, 0A3Ah
0x180011435  mov     ecx, ebx
0x180011437  lea     rdx, aStatus; "Status"
0x18001143e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011445  call    DebugTraceError
0x18001144a  jmp     loc_180011379
0x18001144f  mov     ebx, 80090022h
0x180011454  mov     r9d, 0A28h
0x18001145a  mov     ecx, 80090022h
0x18001145f  jmp     short loc_180011437
```
