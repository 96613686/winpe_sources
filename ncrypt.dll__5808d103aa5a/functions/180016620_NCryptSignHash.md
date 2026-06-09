# NCryptSignHash

- ea: `0x180016620`
- end: `0x18001686f`
- name: `NCryptSignHash`
- size: `591`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, void *pPaddingInfo, PBYTE pbHashValue, DWORD cbHashValue, PBYTE pbSignature, DWORD cbSignature, DWORD *pcbResult, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180010684`
- `0x180016620`
- `0x1800173c0`
- `0x18001993c`
- `0x180020010`

## string_xrefs

- `0x1800166bd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800167d3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800167fe`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptSignHash(
        NCRYPT_KEY_HANDLE hKey,
        void *pPaddingInfo,
        PBYTE pbHashValue,
        DWORD cbHashValue,
        PBYTE pbSignature,
        DWORD cbSignature,
        DWORD *pcbResult,
        DWORD dwFlags)
{
  PBYTE v9; // rbx
  DWORD v10; // edi
  NCRYPT_KEY_HANDLE *v11; // rdx
  _QWORD *v12; // rsi
  NCryptKeyName **v13; // r8
  NCryptAlgorithmName **v14; // r9
  __int64 v15; // r10
  unsigned int v16; // ebx
  unsigned int v17; // ebp
  DWORD *v18; // r12
  DWORD v19; // r14d
  PBYTE v20; // r15
  unsigned int v21; // eax
  int v22; // r9d
  NCRYPT_KEY_HANDLE v24; // [rsp+90h] [rbp+8h] BYREF
  void *v25; // [rsp+98h] [rbp+10h]
  PBYTE v26; // [rsp+A0h] [rbp+18h]

  v26 = pbHashValue;
  v25 = pPaddingInfo;
  v24 = hKey;
  v9 = pbHashValue;
  v10 = dwFlags;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, pbHashValue, hKey, dwFlags);
    hKey = v24;
  }
  v12 = (_QWORD *)ValidateClientKeyHandle(hKey);
  if ( v12 )
  {
    v17 = 0;
    if ( (unsigned int)Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH__private_IsEnabledDeviceUsageNoInline()
      && (v10 & 0x800000) != 0 )
    {
      v10 &= ~0x800000u;
      v17 = 3;
    }
    v18 = pcbResult;
    v19 = cbSignature;
    v20 = pbSignature;
    while ( 1 )
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, PBYTE, DWORD, PBYTE, DWORD, DWORD *, DWORD))(v12[1] + 176LL))(
              *(_QWORD *)(v12[1] + 272LL),
              v12[2],
              v25,
              v9,
              cbHashValue,
              v20,
              v19,
              v18,
              v10);
      v16 = v21;
      if ( v21 != -2146893778 )
        break;
      if ( (v10 & 0x40) != 0 )
      {
        v16 = -2146893790;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v11,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            (unsigned int)"Status",
            34,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            228);
        return NormalizeNteStatus(v16, v11, v13, v14, pbSignature, cbSignature, pcbResult, dwFlags);
      }
      v16 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(v12[1] + 192LL))(
              *(_QWORD *)(v12[1] + 272LL),
              v24,
              L"NCryptSignHash",
              0);
      if ( v16 )
        goto LABEL_21;
      v9 = v26;
    }
    if ( v21 )
    {
LABEL_21:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3574);
      EtwLogNCryptOperationFailed(6, *(_QWORD *)(v12[1] + 280LL), v12[3], v22, v16);
      return NormalizeNteStatus(v16, v11, v13, v14, pbSignature, cbSignature, pcbResult, dwFlags);
    }
    if ( v20 && v19 )
      CertInUseLog(v17, v12 + 5, &v24);
    v16 = 0;
  }
  else
  {
    v16 = -2146893786;
    if ( (NCRYPT_KEY_HANDLE *)v15 != v11 && (*(_BYTE *)(v15 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v15 + 16),
        (_DWORD)v11,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        190);
  }
  return NormalizeNteStatus(v16, v11, v13, v14, pbSignature, cbSignature, pcbResult, dwFlags);
}

```

## disassembly

```asm
0x180016620  mov     rax, rsp
0x180016623  mov     [rax+20h], rbx
0x180016627  mov     [rax+18h], r8
0x18001662b  mov     [rax+10h], rdx
0x18001662f  mov     [rax+8], rcx
0x180016633  push    rbp
0x180016634  push    rsi
0x180016635  push    rdi
0x180016636  push    r12
0x180016638  push    r13
0x18001663a  push    r14
0x18001663c  push    r15
0x18001663e  sub     rsp, 50h
0x180016642  mov     r13d, r9d
0x180016645  mov     rbx, r8
0x180016648  mov     r10, cs:WPP_GLOBAL_Control
0x18001664f  lea     rdx, WPP_GLOBAL_Control
0x180016656  mov     edi, [rsp+88h+dwFlags]
0x18001665d  cmp     r10, rdx
0x180016660  jz      short loc_180016693
0x180016662  test    byte ptr [r10+1Ch], 4
0x180016667  jz      short loc_180016693
0x180016669  mov     r9, rcx
0x18001666c  mov     [rax-68h], edi
0x18001666f  mov     rcx, [r10+10h]
0x180016673  mov     edx, 1Dh
0x180016678  call    WPP_SF_PD
0x18001667d  mov     rcx, [rsp+88h+arg_0]
0x180016685  lea     rdx, WPP_GLOBAL_Control
0x18001668c  mov     r10, cs:WPP_GLOBAL_Control
0x180016693  call    ValidateClientKeyHandle
0x180016698  mov     rsi, rax
0x18001669b  test    rax, rax
0x18001669e  jnz     short loc_1800166EA
0x1800166a0  mov     ebx, 80090026h
0x1800166a5  cmp     r10, rdx
0x1800166a8  jz      loc_180016851
0x1800166ae  test    byte ptr [r10+1Ch], 1
0x1800166b3  jz      loc_180016851
0x1800166b9  mov     rcx, [r10+10h]
0x1800166bd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800166c4  mov     [rsp+88h+var_58], 0DBEh
0x1800166cc  mov     [rsp+88h+var_60], r8
0x1800166d1  mov     [rsp+88h+var_68], 80090026h
0x1800166d9  lea     r9, aStatus; "Status"
0x1800166e0  call    WPP_SF_sDsd
0x1800166e5  jmp     loc_180016851
0x1800166ea  xor     ebp, ebp
0x1800166ec  call    Feature_CNG_NCRYPT_PRIVATE_TLS_CLIENT_AUTH__private_IsEnabledDeviceUsageNoInline
0x1800166f1  test    eax, eax
0x1800166f3  jz      short loc_180016704
0x1800166f5  bt      edi, 17h
0x1800166f9  jnb     short loc_180016704
0x1800166fb  btr     edi, 17h
0x1800166ff  mov     ebp, 3
0x180016704  mov     r12, [rsp+88h+pcbResult]
0x18001670c  mov     r14d, [rsp+88h+cbSignature]
0x180016714  mov     r15, [rsp+88h+pbSignature]
0x18001671c  mov     rcx, [rsi+8]
0x180016720  mov     r9, rbx
0x180016723  mov     r8, [rsp+88h+arg_8]
0x18001672b  mov     rdx, [rsi+10h]
0x18001672f  mov     [rsp+88h+var_48], edi
0x180016733  mov     rax, [rcx+0B0h]
0x18001673a  mov     rcx, [rcx+110h]
0x180016741  mov     [rsp+88h+var_50], r12
0x180016746  mov     [rsp+88h+var_58], r14d
0x18001674b  mov     [rsp+88h+var_60], r15
0x180016750  mov     [rsp+88h+var_68], r13d
0x180016755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001675a  mov     ebx, eax
0x18001675c  cmp     eax, 8009002Eh
0x180016761  jnz     loc_1800167F4
0x180016767  test    dil, 40h
0x18001676b  jnz     short loc_1800167A9
0x18001676d  mov     rcx, [rsi+8]
0x180016771  lea     r8, aNcryptsignhash_0; "NCryptSignHash"
0x180016778  mov     rdx, [rsp+88h+arg_0]
0x180016780  xor     r9d, r9d
0x180016783  mov     rax, [rcx+0C0h]
0x18001678a  mov     rcx, [rcx+110h]
0x180016791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016796  mov     ebx, eax
0x180016798  test    eax, eax
0x18001679a  jnz     short loc_1800167F8
0x18001679c  mov     rbx, [rsp+88h+arg_10]
0x1800167a4  jmp     loc_18001671C
0x1800167a9  mov     ebx, 80090022h
0x1800167ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167b5  lea     rax, WPP_GLOBAL_Control
0x1800167bc  cmp     rcx, rax
0x1800167bf  jz      loc_180016851
0x1800167c5  test    byte ptr [rcx+1Ch], 1
0x1800167c9  jz      loc_180016851
0x1800167cf  mov     rcx, [rcx+10h]
0x1800167d3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800167da  mov     [rsp+88h+var_58], 0DE4h
0x1800167e2  mov     [rsp+88h+var_60], r8
0x1800167e7  mov     [rsp+88h+var_68], 80090022h
0x1800167ef  jmp     loc_1800166D9
0x1800167f4  test    eax, eax
0x1800167f6  jz      short loc_180016832
0x1800167f8  mov     r9d, 0DF6h
0x1800167fe  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016805  lea     rdx, aStatus; "Status"
0x18001680c  mov     ecx, ebx
0x18001680e  call    DebugTraceError
0x180016813  mov     rdx, [rsi+8]
0x180016817  mov     ecx, 6
0x18001681c  mov     r8, [rsi+18h]
0x180016820  mov     [rsp+88h+var_68], ebx
0x180016824  mov     rdx, [rdx+118h]
0x18001682b  call    EtwLogNCryptOperationFailed
0x180016830  jmp     short loc_180016851
0x180016832  test    r15, r15
0x180016835  jz      short loc_18001684F
0x180016837  test    r14d, r14d
0x18001683a  jz      short loc_18001684F
0x18001683c  lea     rdx, [rsi+28h]
0x180016840  mov     ecx, ebp
0x180016842  lea     r8, [rsp+88h+arg_0]
0x18001684a  call    CertInUseLog
0x18001684f  xor     ebx, ebx
0x180016851  mov     ecx, ebx
0x180016853  mov     rbx, [rsp+88h+arg_18]
0x18001685b  add     rsp, 50h
0x18001685f  pop     r15
0x180016861  pop     r14
0x180016863  pop     r13
0x180016865  pop     r12
0x180016867  pop     rdi
0x180016868  pop     rsi
0x180016869  pop     rbp
0x18001686a  jmp     NormalizeNteStatus
```
