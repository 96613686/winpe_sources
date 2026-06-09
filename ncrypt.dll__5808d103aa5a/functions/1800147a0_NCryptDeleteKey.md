# NCryptDeleteKey

- ea: `0x1800147a0`
- end: `0x180014938`
- name: `NCryptDeleteKey`
- size: `408`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x18000e120`
- `0x180010684`
- `0x1800147a0`
- `0x180014940`
- `0x180020010`

## string_xrefs

- `0x180014813`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800148a7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800148e1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180014877`: `NCryptDeleteKey`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptDeleteKey(NCRYPT_KEY_HANDLE hKey, DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE *v4; // rdx
  _QWORD *v5; // rdi
  __int64 v6; // r8
  PVOID *v7; // r9
  unsigned int v8; // ebx
  int v9; // r9d
  __int64 v10; // rcx
  _BYTE *v11; // rax
  DWORD v13; // [rsp+90h] [rbp+28h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_GLOBAL_Control, hKey, dwFlags);
  v5 = (_QWORD *)ValidateClientKeyHandle(hKey);
  if ( v5 )
  {
    do
    {
      CertInUseMetadataCleanup(v5 + 5);
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v5[1] + 88LL))(
             *(_QWORD *)(v5[1] + 272LL),
             v5[2],
             dwFlags);
      if ( v8 != -2146893778 )
        break;
      if ( (dwFlags & 0x40) != 0 )
      {
        v8 = -2146893790;
        DebugTraceError(
          2148073506LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
          2179);
        return NormalizeNteStatus(v8, v4, (NCryptKeyName **)v6, v7, v13);
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(v5[1] + 192LL))(
             *(_QWORD *)(v5[1] + 272LL),
             hKey,
             L"NCryptDeleteKey",
             0);
    }
    while ( !v8 );
    if ( v8 )
    {
      DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 2197);
      EtwLogNCryptOperationFailed(3, *(_QWORD *)(v5[1] + 280LL), v5[3], v9, v8);
    }
    else
    {
      DereferenceProvider(v5[1]);
      v10 = 48;
      v11 = v5;
      do
      {
        *v11++ = 0;
        --v10;
      }
      while ( v10 );
      MSCryptFree(v5);
      v8 = 0;
    }
  }
  else
  {
    v8 = -2146893786;
    if ( (PVOID *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v6 + 16),
        (_DWORD)v4,
        v6,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        106);
  }
  return NormalizeNteStatus(v8, v4, (NCryptKeyName **)v6, v7, v13);
}

```

## disassembly

```asm
0x1800147a0  push    rbx
0x1800147a2  push    rbp
0x1800147a3  push    rsi
0x1800147a4  push    rdi
0x1800147a5  push    r14
0x1800147a7  sub     rsp, 40h
0x1800147ab  mov     ebp, edx
0x1800147ad  mov     rsi, rcx
0x1800147b0  mov     r8, cs:WPP_GLOBAL_Control
0x1800147b7  lea     r14, WPP_GLOBAL_Control
0x1800147be  cmp     r8, r14
0x1800147c1  jz      short loc_1800147E6
0x1800147c3  test    byte ptr [r8+1Ch], 4
0x1800147c8  jz      short loc_1800147E6
0x1800147ca  mov     r9, rcx
0x1800147cd  mov     [rsp+68h+var_48], ebp
0x1800147d1  mov     rcx, [r8+10h]
0x1800147d5  mov     edx, 13h
0x1800147da  call    WPP_SF_PD
0x1800147df  mov     r8, cs:WPP_GLOBAL_Control
0x1800147e6  mov     rcx, rsi
0x1800147e9  call    ValidateClientKeyHandle
0x1800147ee  mov     rdi, rax
0x1800147f1  test    rax, rax
0x1800147f4  jnz     short loc_180014840
0x1800147f6  mov     ebx, 80090026h
0x1800147fb  cmp     r8, r14
0x1800147fe  jz      loc_180014927
0x180014804  test    byte ptr [r8+1Ch], 1
0x180014809  jz      loc_180014927
0x18001480f  mov     rcx, [r8+10h]
0x180014813  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001481a  mov     [rsp+68h+var_38], 86Ah
0x180014822  lea     r9, aStatus; "Status"
0x180014829  mov     [rsp+68h+var_40], rax
0x18001482e  mov     [rsp+68h+var_48], 80090026h
0x180014836  call    WPP_SF_sDsd
0x18001483b  jmp     loc_180014927
0x180014840  lea     rcx, [rdi+28h]
0x180014844  call    CertInUseMetadataCleanup
0x180014849  mov     rcx, [rdi+8]
0x18001484d  mov     r8d, ebp
0x180014850  mov     rdx, [rdi+10h]
0x180014854  mov     rax, [rcx+58h]
0x180014858  mov     rcx, [rcx+110h]
0x18001485f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014864  mov     ebx, eax
0x180014866  cmp     eax, 8009002Eh
0x18001486b  jnz     short loc_18001489D
0x18001486d  test    bpl, 40h
0x180014871  jnz     short loc_1800148DB
0x180014873  mov     rcx, [rdi+8]
0x180014877  lea     r8, aNcryptdeleteke_0; "NCryptDeleteKey"
0x18001487e  xor     r9d, r9d
0x180014881  mov     rdx, rsi
0x180014884  mov     rax, [rcx+0C0h]
0x18001488b  mov     rcx, [rcx+110h]
0x180014892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014897  mov     ebx, eax
0x180014899  test    eax, eax
0x18001489b  jz      short loc_180014840
0x18001489d  test    ebx, ebx
0x18001489f  jz      short loc_180014900
0x1800148a1  mov     r9d, 895h
0x1800148a7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800148ae  lea     rdx, aStatus; "Status"
0x1800148b5  mov     ecx, ebx
0x1800148b7  call    DebugTraceError
0x1800148bc  mov     rdx, [rdi+8]
0x1800148c0  mov     ecx, 3
0x1800148c5  mov     r8, [rdi+18h]
0x1800148c9  mov     [rsp+68h+var_48], ebx
0x1800148cd  mov     rdx, [rdx+118h]
0x1800148d4  call    EtwLogNCryptOperationFailed
0x1800148d9  jmp     short loc_180014927
0x1800148db  mov     r9d, 883h
0x1800148e1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800148e8  lea     rdx, aStatus; "Status"
0x1800148ef  mov     ecx, 80090022h
0x1800148f4  mov     ebx, 80090022h
0x1800148f9  call    DebugTraceError
0x1800148fe  jmp     short loc_180014927
0x180014900  mov     rcx, [rdi+8]
0x180014904  call    DereferenceProvider
0x180014909  mov     ecx, 30h ; '0'
0x18001490e  mov     rax, rdi
0x180014911  mov     byte ptr [rax], 0
0x180014914  inc     rax
0x180014917  sub     rcx, 1
0x18001491b  jnz     short loc_180014911
0x18001491d  mov     rcx, rdi
0x180014920  call    MSCryptFree
0x180014925  xor     ebx, ebx
0x180014927  mov     ecx, ebx
0x180014929  add     rsp, 40h
0x18001492d  pop     r14
0x18001492f  pop     rdi
0x180014930  pop     rsi
0x180014931  pop     rbp
0x180014932  pop     rbx
0x180014933  jmp     NormalizeNteStatus
```
