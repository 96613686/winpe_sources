# NCryptCreatePersistedKey

- ea: `0x1800175f0`
- end: `0x18001797c`
- name: `NCryptCreatePersistedKey`
- size: `908`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, NCRYPT_KEY_HANDLE *phKey, LPCWSTR pszAlgId, LPCWSTR pszKeyName, DWORD dwLegacyKeySpec, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180001044`
- `0x180009cd0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000e120`
- `0x180011cb0`
- `0x180013510`
- `0x1800175f0`
- `0x180018350`
- `0x180018e18`
- `0x18001b728`
- `0x18001f15d`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18001783d`
- `ntdll!RtlDllShutdownInProgress` at `0x18001783d`

## string_xrefs

- `0x18001768d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800176f1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001772b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800177bf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptCreatePersistedKey(
        NCRYPT_PROV_HANDLE hProvider,
        NCRYPT_KEY_HANDLE *phKey,
        LPCWSTR pszAlgId,
        LPCWSTR pszKeyName,
        DWORD dwLegacyKeySpec,
        DWORD dwFlags)
{
  LPCWSTR v7; // r12
  __int64 v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r14
  size_t v18; // r12
  void *v19; // rax
  NCRYPT_KEY_HANDLE v20; // rbx
  unsigned int v21; // eax
  _BYTE *v22; // rax
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // r8d
  LPCWSTR v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v29; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  char v32[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int64 *v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  unsigned int *v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  char v39[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v40[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v41[16]; // [rsp+D0h] [rbp-30h] BYREF
  DWORD *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  char v44[16]; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR *v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]

  v27 = pszAlgId;
  v7 = pszAlgId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PSSDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)pszAlgId, (__int64)pszKeyName, dwLegacyKeySpec, dwFlags);
  if ( !phKey )
  {
    v10 = 0;
    v11 = -2146893785;
    v12 = 1223;
    v13 = 2148073511LL;
LABEL_6:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v12);
    goto LABEL_26;
  }
  v10 = ValidateAndReferenceProvider(hProvider);
  if ( !v10 )
  {
    v11 = -2146893786;
    v12 = 1232;
    v13 = 2148073510LL;
    goto LABEL_6;
  }
  v14 = 0;
  if ( pszKeyName )
  {
    v15 = -1;
    do
      ++v15;
    while ( pszKeyName[v15] );
    v14 = 2 * v15 + 2;
  }
  v16 = v14 + 48;
  v17 = 48;
  if ( v14 < 0xFFFFFFD0 )
  {
    v18 = v16;
    v19 = (void *)SafeAllocaAllocateFromHeap(v16);
    v20 = (NCRYPT_KEY_HANDLE)v19;
    if ( v19 )
    {
      memset_0(v19, 0, v18);
      if ( v14 )
      {
        *(_QWORD *)(v20 + 24) = v20 + 48;
        memcpy_0((void *)(v20 + 48), pszKeyName, v14);
      }
      else
      {
        *(_QWORD *)(v20 + 24) = 0;
      }
      v7 = v27;
      v21 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, LPCWSTR, LPCWSTR, DWORD, DWORD))(v10 + 40))(
              *(_QWORD *)(v10 + 272),
              v20 + 16,
              v27,
              pszKeyName,
              dwLegacyKeySpec,
              dwFlags);
      v11 = v21;
      if ( !v21 )
      {
        *(_DWORD *)v20 = 1145307138;
        *(_QWORD *)(v20 + 8) = v10;
        v11 = 0;
        *(_DWORD *)(v20 + 32) = 1;
        *phKey = v20;
        goto LABEL_26;
      }
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 1283);
      EtwLogNCryptCreateKeyFailed(*(_QWORD *)(v10 + 280), (_DWORD)pszKeyName, (_DWORD)v27, dwFlags, v11);
      v22 = (_BYTE *)v20;
      do
      {
        *v22++ = 0;
        --v17;
      }
      while ( v17 );
      MSCryptFree(v20);
    }
    else
    {
      v11 = -2146893810;
      DebugTraceError(
        2148073486LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        1257);
      v7 = v27;
    }
  }
  else
  {
    v11 = -1073741675;
    DebugTraceError(3221225621LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 1248);
  }
  DereferenceProvider(v10);
LABEL_26:
  if ( (unsigned int)Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline()
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_18002A078 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18002A078, 0x400000000000LL) )
  {
    v30 = 1;
    v33 = &v30;
    v35 = &v31;
    v37 = &v28;
    v34 = 8;
    v31 = 0x1000000;
    v36 = 8;
    v28 = v11;
    v38 = 4;
    if ( v10 )
      v23 = *(_QWORD *)(v10 + 280);
    else
      v23 = 0;
    tlgCreate1Sz_wchar_t(v39, v23);
    tlgCreate1Sz_wchar_t(v40, g_processImageNameNcrypt);
    tlgCreate1Sz_wchar_t(v41, v7);
    v29 = dwFlags;
    v43 = 4;
    v42 = &v29;
    tlgCreate1Sz_wchar_t(v44, pszKeyName);
    LODWORD(v27) = dwLegacyKeySpec;
    v46 = 4;
    v45 = &v27;
    tlgWriteAgg(v24, (unsigned int)byte_1800244DD, v25, 11, (__int64)v32);
  }
  return NormalizeNteStatus(v11);
}

```

## disassembly

```asm
0x1800175f0  push    rbp
0x1800175f2  push    rbx
0x1800175f3  push    rsi
0x1800175f4  push    rdi
0x1800175f5  push    r12
0x1800175f7  push    r13
0x1800175f9  push    r14
0x1800175fb  push    r15
0x1800175fd  lea     rbp, [rsp-28h]
0x180017602  sub     rsp, 128h
0x180017609  mov     rax, cs:__security_cookie
0x180017610  xor     rax, rsp
0x180017613  mov     [rbp+60h+var_50], rax
0x180017617  mov     r15, r9
0x18001761a  mov     [rsp+160h+var_120], r8
0x18001761f  mov     r12, r8
0x180017622  mov     r13, rdx
0x180017625  mov     rbx, rcx
0x180017628  mov     rcx, cs:WPP_GLOBAL_Control
0x18001762f  lea     rax, WPP_GLOBAL_Control
0x180017636  cmp     rcx, rax
0x180017639  jz      short loc_18001766B
0x18001763b  test    byte ptr [rcx+1Ch], 4
0x18001763f  jz      short loc_18001766B
0x180017641  mov     eax, [rbp+60h+dwFlags]
0x180017647  mov     rcx, [rcx+10h]; LoggerHandle
0x18001764b  mov     dword ptr [rsp+160h+var_128], eax; char
0x18001764f  mov     eax, [rbp+60h+dwLegacyKeySpec]
0x180017655  mov     dword ptr [rsp+160h+var_130], eax; char
0x180017659  mov     [rsp+160h+var_138], r9; __int64
0x18001765e  mov     r9, rbx
0x180017661  mov     [rsp+160h+var_140], r8; __int64
0x180017666  call    WPP_SF_PSSDD
0x18001766b  xor     r14d, r14d
0x18001766e  test    r13, r13
0x180017671  jnz     short loc_18001769E
0x180017673  mov     esi, r14d
0x180017676  mov     edi, 80090027h
0x18001767b  mov     r9d, 4C7h
0x180017681  mov     ecx, 80090027h
0x180017686  lea     rdx, aStatus; "Status"
0x18001768d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017694  call    DebugTraceError
0x180017699  jmp     loc_180017830
0x18001769e  mov     rcx, rbx
0x1800176a1  call    ValidateAndReferenceProvider
0x1800176a6  mov     rsi, rax
0x1800176a9  test    rax, rax
0x1800176ac  jnz     short loc_1800176C0
0x1800176ae  mov     edi, 80090026h
0x1800176b3  mov     r9d, 4D0h
0x1800176b9  mov     ecx, 80090026h
0x1800176be  jmp     short loc_180017686
0x1800176c0  mov     edi, r14d
0x1800176c3  test    r15, r15
0x1800176c6  jz      short loc_1800176DD
0x1800176c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800176cc  inc     rax
0x1800176cf  cmp     [r15+rax*2], r14w
0x1800176d4  jnz     short loc_1800176CC
0x1800176d6  lea     edi, ds:2[rax*2]
0x1800176dd  lea     eax, [rdi+30h]
0x1800176e0  mov     r14d, 30h ; '0'
0x1800176e6  cmp     eax, r14d
0x1800176e9  jnb     short loc_180017713
0x1800176eb  mov     r9d, 4E0h
0x1800176f1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800176f8  lea     rdx, aStatus; "Status"
0x1800176ff  mov     ecx, 0C0000095h
0x180017704  mov     edi, 0C0000095h
0x180017709  call    DebugTraceError
0x18001770e  jmp     loc_180017808
0x180017713  mov     ecx, eax
0x180017715  mov     r12d, eax
0x180017718  call    SafeAllocaAllocateFromHeap
0x18001771d  mov     rbx, rax
0x180017720  test    rax, rax
0x180017723  jnz     short loc_180017752
0x180017725  mov     r9d, 4E9h
0x18001772b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017732  lea     rdx, aStatus; "Status"
0x180017739  mov     ecx, 8009000Eh
0x18001773e  mov     edi, 8009000Eh
0x180017743  call    DebugTraceError
0x180017748  mov     r12, [rsp+160h+var_120]
0x18001774d  jmp     loc_180017808
0x180017752  mov     r8, r12; Size
0x180017755  xor     edx, edx; Val
0x180017757  mov     rcx, rbx; void *
0x18001775a  call    memset_0
0x18001775f  test    edi, edi
0x180017761  jz      short loc_180017778
0x180017763  lea     rcx, [rbx+30h]; void *
0x180017767  mov     r8d, edi; Size
0x18001776a  mov     rdx, r15; Src
0x18001776d  mov     [rbx+18h], rcx
0x180017771  call    memcpy_0
0x180017776  jmp     short loc_180017780
0x180017778  mov     qword ptr [rbx+18h], 0
0x180017780  mov     eax, [rbp+60h+dwFlags]
0x180017786  lea     rdx, [rbx+10h]
0x18001778a  mov     r12, [rsp+160h+var_120]
0x18001778f  mov     r9, r15
0x180017792  mov     rcx, [rsi+110h]
0x180017799  mov     r8, r12
0x18001779c  mov     dword ptr [rsp+160h+var_138], eax
0x1800177a0  mov     eax, [rbp+60h+dwLegacyKeySpec]
0x1800177a6  mov     dword ptr [rsp+160h+var_140], eax
0x1800177aa  mov     rax, [rsi+28h]
0x1800177ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177b3  mov     edi, eax
0x1800177b5  test    eax, eax
0x1800177b7  jz      short loc_180017815
0x1800177b9  mov     r9d, 503h
0x1800177bf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800177c6  lea     rdx, aStatus; "Status"
0x1800177cd  mov     ecx, eax
0x1800177cf  call    DebugTraceError
0x1800177d4  mov     r9d, [rbp+60h+dwFlags]
0x1800177db  mov     r8, r12
0x1800177de  mov     rcx, [rsi+118h]
0x1800177e5  mov     rdx, r15
0x1800177e8  mov     dword ptr [rsp+160h+var_140], edi
0x1800177ec  call    EtwLogNCryptCreateKeyFailed
0x1800177f1  mov     rax, rbx
0x1800177f4  mov     byte ptr [rax], 0
0x1800177f7  inc     rax
0x1800177fa  sub     r14, 1
0x1800177fe  jnz     short loc_1800177F4
0x180017800  mov     rcx, rbx
0x180017803  call    MSCryptFree
0x180017808  mov     rcx, rsi
0x18001780b  call    DereferenceProvider
0x180017810  xor     r14d, r14d
0x180017813  jmp     short loc_180017830
0x180017815  xor     r14d, r14d
0x180017818  mov     dword ptr [rbx], 44440002h
0x18001781e  mov     [rbx+8], rsi
0x180017822  mov     edi, r14d
0x180017825  mov     dword ptr [rbx+20h], 1
0x18001782c  mov     [r13+0], rbx
0x180017830  call    Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline
0x180017835  test    eax, eax
0x180017837  jz      loc_180017955
0x18001783d  call    cs:__imp_RtlDllShutdownInProgress
0x180017843  test    al, al
0x180017845  jnz     loc_180017955
0x18001784b  mov     eax, cs:dword_18002A078
0x180017851  cmp     eax, 5
0x180017854  jbe     loc_180017955
0x18001785a  mov     rdx, 400000000000h
0x180017864  lea     rcx, dword_18002A078
0x18001786b  call    _tlgKeywordOn
0x180017870  test    al, al
0x180017872  jz      loc_180017955
0x180017878  mov     [rsp+160h+var_110], 1
0x180017881  lea     rax, [rsp+160h+var_110]
0x180017886  mov     [rbp+60h+var_E0], rax
0x18001788a  lea     rax, [rsp+160h+var_108]
0x18001788f  mov     [rbp+60h+var_D0], rax
0x180017893  lea     rax, [rsp+160h+var_118]
0x180017898  mov     [rbp+60h+var_C0], rax
0x18001789c  mov     [rbp+60h+var_D8], 8
0x1800178a4  mov     [rsp+160h+var_108], 1000000h
0x1800178ad  mov     [rbp+60h+var_C8], 8
0x1800178b5  mov     [rsp+160h+var_118], edi
0x1800178b9  mov     [rbp+60h+var_B8], 4
0x1800178c1  test    rsi, rsi
0x1800178c4  jz      short loc_1800178CF
0x1800178c6  mov     rdx, [rsi+118h]
0x1800178cd  jmp     short loc_1800178D2
0x1800178cf  mov     rdx, r14
0x1800178d2  lea     rcx, [rbp+60h+var_B0]
0x1800178d6  call    _tlgCreate1Sz_wchar_t
0x1800178db  lea     rdx, g_processImageNameNcrypt; "UNKNOWN"
0x1800178e2  lea     rcx, [rbp+60h+var_A0]
0x1800178e6  call    _tlgCreate1Sz_wchar_t
0x1800178eb  mov     rdx, r12
0x1800178ee  lea     rcx, [rbp+60h+var_90]
0x1800178f2  call    _tlgCreate1Sz_wchar_t
0x1800178f7  mov     eax, [rbp+60h+dwFlags]
0x1800178fd  lea     rcx, [rbp+60h+var_70]
0x180017901  mov     [rsp+160h+var_114], eax
0x180017905  mov     rdx, r15
0x180017908  lea     rax, [rsp+160h+var_114]
0x18001790d  mov     [rbp+60h+var_78], 4
0x180017915  mov     [rbp+60h+var_80], rax
0x180017919  call    _tlgCreate1Sz_wchar_t
0x18001791e  mov     eax, [rbp+60h+dwLegacyKeySpec]
0x180017924  lea     rdx, byte_1800244DD
0x18001792b  mov     dword ptr [rsp+160h+var_120], eax
0x18001792f  mov     r9d, 0Bh
0x180017935  lea     rax, [rsp+160h+var_120]
0x18001793a  mov     [rbp+60h+var_58], 4
0x180017942  mov     [rbp+60h+var_60], rax
0x180017946  lea     rax, [rsp+160h+var_100]
0x18001794b  mov     [rsp+160h+var_140], rax
0x180017950  call    _tlgWriteAgg
0x180017955  mov     ecx, edi
0x180017957  call    NormalizeNteStatus
0x18001795c  mov     rcx, [rbp+60h+var_50]
0x180017960  xor     rcx, rsp; StackCookie
0x180017963  call    __security_check_cookie
0x180017968  add     rsp, 128h
0x18001796f  pop     r15
0x180017971  pop     r14
0x180017973  pop     r13
0x180017975  pop     r12
0x180017977  pop     rdi
0x180017978  pop     rsi
0x180017979  pop     rbx
0x18001797a  pop     rbp
0x18001797b  retn
```
