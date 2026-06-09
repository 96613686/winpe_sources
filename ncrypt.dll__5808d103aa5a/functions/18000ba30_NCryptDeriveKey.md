# NCryptDeriveKey

- ea: `0x18000ba30`
- end: `0x18000bb59`
- name: `NCryptDeriveKey`
- size: `297`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_SECRET_HANDLE hSharedSecret, LPCWSTR pwszKDF, NCryptBufferDesc *pParameterList, PBYTE pbDerivedKey, DWORD cbDerivedKey, DWORD *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a670`
- `0x18000ba30`
- `0x18000c8e0`
- `0x18000e120`
- `0x180010684`
- `0x180020010`

## string_xrefs

- `0x18000bafa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000bb37`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptDeriveKey(
        NCRYPT_SECRET_HANDLE hSharedSecret,
        LPCWSTR pwszKDF,
        NCryptBufferDesc *pParameterList,
        PBYTE pbDerivedKey,
        PBYTE cbDerivedKey,
        DWORD *pcbResult,
        ULONG dwFlags)
{
  unsigned int v11; // eax
  NCRYPT_KEY_HANDLE *v12; // rdx
  NCryptKeyName **v13; // r8
  NCryptAlgorithmName **v14; // r9
  unsigned int v15; // edi
  int v17; // r9d

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (_DWORD)pParameterList,
      hSharedSecret,
      (__int64)pwszKDF,
      dwFlags);
  if ( hSharedSecret && *(_DWORD *)hSharedSecret == 1145307139 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPCWSTR, NCryptBufferDesc *, PBYTE, DWORD, DWORD *, ULONG))(*(_QWORD *)(hSharedSecret + 8) + 216LL))(
            *(_QWORD *)(*(_QWORD *)(hSharedSecret + 8) + 272LL),
            *(_QWORD *)(hSharedSecret + 16),
            pwszKDF,
            pParameterList,
            pbDerivedKey,
            (DWORD)cbDerivedKey,
            pcbResult,
            dwFlags);
    v15 = v11;
    if ( v11 )
    {
      DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3863);
      EtwLogNCryptOperationFailed(
        9,
        *(_QWORD *)(*(_QWORD *)(hSharedSecret + 8) + 280LL),
        (unsigned int)L"DeriveKey",
        v17,
        v15);
    }
  }
  else
  {
    v15 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3847);
  }
  return NormalizeNteStatus(v15, v12, v13, v14, cbDerivedKey, pcbResult, *(DWORD **)&dwFlags);
}

```

## disassembly

```asm
0x18000ba30  push    rbx
0x18000ba32  push    rbp
0x18000ba33  push    rsi
0x18000ba34  push    rdi
0x18000ba35  push    r14
0x18000ba37  sub     rsp, 50h
0x18000ba3b  mov     rbp, r9
0x18000ba3e  mov     r14, r8
0x18000ba41  mov     rdi, rdx
0x18000ba44  mov     rbx, rcx
0x18000ba47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba4e  lea     rax, WPP_GLOBAL_Control
0x18000ba55  mov     esi, [rsp+78h+dwFlags]
0x18000ba5c  cmp     rcx, rax
0x18000ba5f  jz      short loc_18000BA67
0x18000ba61  test    byte ptr [rcx+1Ch], 4
0x18000ba65  jnz     short loc_18000BAD5
0x18000ba67  test    rbx, rbx
0x18000ba6a  jz      loc_18000BB31
0x18000ba70  cmp     dword ptr [rbx], 44440003h
0x18000ba76  jnz     loc_18000BB31
0x18000ba7c  mov     rcx, [rbx+8]
0x18000ba80  mov     r9, r14
0x18000ba83  mov     rdx, [rsp+78h+pcbResult]
0x18000ba8b  mov     r8, rdi
0x18000ba8e  mov     [rsp+78h+var_40], esi
0x18000ba92  mov     [rsp+78h+var_48], rdx
0x18000ba97  mov     edx, dword ptr [rsp+78h+cbDerivedKey]
0x18000ba9e  mov     rax, [rcx+0D8h]
0x18000baa5  mov     rcx, [rcx+110h]
0x18000baac  mov     [rsp+78h+var_50], edx
0x18000bab0  mov     rdx, [rbx+10h]
0x18000bab4  mov     [rsp+78h+var_58], rbp
0x18000bab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000babe  mov     edi, eax
0x18000bac0  test    eax, eax
0x18000bac2  jnz     short loc_18000BAF4
0x18000bac4  mov     ecx, edi
0x18000bac6  add     rsp, 50h
0x18000baca  pop     r14
0x18000bacc  pop     rdi
0x18000bacd  pop     rsi
0x18000bace  pop     rbp
0x18000bacf  pop     rbx
0x18000bad0  jmp     NormalizeNteStatus
0x18000bad5  mov     rcx, [rcx+10h]
0x18000bad9  mov     edx, 20h ; ' '
0x18000bade  mov     [rsp+78h+var_50], esi
0x18000bae2  mov     r9, rbx
0x18000bae5  mov     [rsp+78h+var_58], rdi
0x18000baea  call    WPP_SF_PSD
0x18000baef  jmp     loc_18000BA67
0x18000baf4  mov     r9d, 0F17h
0x18000bafa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb01  lea     rdx, aStatus; "Status"
0x18000bb08  mov     ecx, edi
0x18000bb0a  call    DebugTraceError
0x18000bb0f  mov     rdx, [rbx+8]
0x18000bb13  lea     r8, aDerivekey; "DeriveKey"
0x18000bb1a  mov     ecx, 9
0x18000bb1f  mov     dword ptr [rsp+78h+var_58], edi
0x18000bb23  mov     rdx, [rdx+118h]
0x18000bb2a  call    EtwLogNCryptOperationFailed
0x18000bb2f  jmp     short loc_18000BAC4
0x18000bb31  mov     r9d, 0F07h
0x18000bb37  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb3e  lea     rdx, aStatus; "Status"
0x18000bb45  mov     ecx, 80090026h
0x18000bb4a  mov     edi, 80090026h
0x18000bb4f  call    DebugTraceError
0x18000bb54  jmp     loc_18000BAC4
```
