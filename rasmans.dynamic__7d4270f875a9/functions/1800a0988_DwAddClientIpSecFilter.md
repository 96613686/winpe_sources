# DwAddClientIpSecFilter

- ea: `0x1800a0988`
- end: `0x1800a1174`
- name: `DwAddClientIpSecFilter`
- size: `2028`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fa8c`

## callees

- `0x18009fcf8`
- `0x18009fe5c`
- `0x18009ff60`
- `0x1800a0050`
- `0x1800a0410`
- `0x1800a08a0`
- `0x1800a0988`
- `0x1800a2930`
- `0x1800a29c0`
- `0x1800a2b38`
- `0x1800a2cb0`
- `0x1800a2df4`
- `0x1800a3928`
- `0x1800a3f98`
- `0x1800e7e28`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c3a`
- `RPCRT4!UuidCreate` at `0x1800a0e04`
- `RPCRT4!UuidCreate` at `0x1800a0e2a`
- `RPCRT4!UuidCreate` at `0x1800a0e04`
- `RPCRT4!UuidCreate` at `0x1800a0e2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0aa4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0aa4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0c26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a111e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a111e`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a10a3`
- `fwpuclnt!FwpmTransactionCommit0` at `0x1800a10a3`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800a0ee9`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800a0ee9`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800a10c7`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800a10c7`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x1800a0e70`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x1800a0e70`

## string_xrefs

- `0x1800a0b0e`: `DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.`
- `0x1800a0b24`: `DwAddClientIpSecFilter: Filter already exists.`
- `0x1800a0e16`: `UuidCreate failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DwAddClientIpSecFilter(__int64 a1, unsigned int a2, int a3, __int64 a4, DWORD cbData, __int64 a6)
{
  _DWORD *v8; // rsi
  HLOCAL v9; // r13
  unsigned int v10; // r14d
  __int64 v11; // rcx
  DWORD LastError; // eax
  __int64 ServerNode; // rax
  __int64 v14; // rbx
  DWORD v15; // ebx
  int v16; // ecx
  int v17; // eax
  __int64 v18; // rcx
  const CHAR *v19; // rcx
  HLOCAL v20; // rbx
  int v21; // r9d
  int v22; // r9d
  int v24; // [rsp+50h] [rbp-408h]
  HLOCAL v25; // [rsp+58h] [rbp-400h] BYREF
  int v26; // [rsp+64h] [rbp-3F4h] BYREF
  int v27[2]; // [rsp+68h] [rbp-3F0h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-3E8h] BYREF
  int v29; // [rsp+74h] [rbp-3E4h] BYREF
  int v30; // [rsp+7Ch] [rbp-3DCh]
  int v31; // [rsp+80h] [rbp-3D8h] BYREF
  int v32; // [rsp+84h] [rbp-3D4h] BYREF
  int v33[4]; // [rsp+90h] [rbp-3C8h] BYREF
  int v34; // [rsp+A0h] [rbp-3B8h]
  _DWORD *v35; // [rsp+B0h] [rbp-3A8h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-3A0h] BYREF
  unsigned int v37; // [rsp+D0h] [rbp-388h]
  __int64 v38; // [rsp+D8h] [rbp-380h]
  __int64 v39; // [rsp+E0h] [rbp-378h] BYREF
  HLOCAL hMem; // [rsp+E8h] [rbp-370h]
  __int128 v41; // [rsp+F0h] [rbp-368h] BYREF
  __int128 v42; // [rsp+100h] [rbp-358h] BYREF
  __int128 v43; // [rsp+110h] [rbp-348h]
  __int128 v44; // [rsp+120h] [rbp-338h]
  __int64 v45; // [rsp+130h] [rbp-328h]
  _OWORD v46[2]; // [rsp+140h] [rbp-318h] BYREF
  int v47; // [rsp+160h] [rbp-2F8h]
  UUID v48; // [rsp+170h] [rbp-2E8h] BYREF
  const wchar_t *v49; // [rsp+180h] [rbp-2D8h]
  int v50; // [rsp+1B0h] [rbp-2A8h]
  __int128 *v51; // [rsp+1B8h] [rbp-2A0h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+1D0h] [rbp-288h] BYREF
  _BYTE Src[480]; // [rsp+230h] [rbp-228h] BYREF

  v45 = a1;
  v37 = a2;
  v38 = a6;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  memset_0(&v48, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v25 = 0;
  v10 = 0;
  v28 = 0;
  v29 = 0;
  v32 = 0;
  v31 = 0;
  v27[1] = 0;
  v27[0] = 0;
  v24 = 0;
  v39 = 0;
  RasIpsecTrace("DwAddClientIpSecFilter.");
  v41 = 0;
  v36 = 0;
  hMem = LocalAlloc(0x40u, 0x118u);
  if ( !hMem )
  {
    RasIpsecTrace("DwAddclientipsecfilter: failed to alloc");
    LastError = GetLastError();
LABEL_49:
    v15 = LastError;
    goto LABEL_50;
  }
  *(_OWORD *)v33 = *(_OWORD *)a1;
  v34 = *(_DWORD *)(a1 + 16);
  ServerNode = FindServerNode(v11, v33);
  v14 = ServerNode;
  if ( ServerNode )
  {
    if ( a2 == *(_DWORD *)(ServerNode + 76) )
    {
      RasIpsecTrace("DwAddClientIpSecFilter: Filter already exists.");
      ++*(_DWORD *)(v14 + 52);
      v15 = 0;
    }
    else
    {
      RasIpsecTrace("DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.");
      v15 = 87;
    }
    goto LABEL_50;
  }
  v15 = 87;
  v30 = 87;
  if ( cbData > 0xA )
  {
    RasIpsecTrace("DwAddClientIpSecFilter: Invalid value of dwNumPolicy");
    v9 = v25;
LABEL_50:
    v17 = 0;
    goto LABEL_51;
  }
  v26 = 0;
  if ( a2 >= 2 )
  {
    v16 = a2 - 2;
    if ( a2 - 2 > 1 )
      goto LABEL_48;
  }
  if ( !a3 )
  {
    v15 = GenerateCertificatesList(0, &v35, &v28, &v26);
    v30 = v15;
    v10 = v28;
    if ( v15 || !v28 || v26 )
    {
      RasIpsecTrace("Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
      if ( !v10 || v26 )
        v15 = 766;
      v8 = v35;
      goto LABEL_25;
    }
    v8 = v35;
    if ( v35 )
      v35[14] |= 2u;
    if ( !a3 )
    {
LABEL_27:
      v15 = BuildIpsecOffers(a2, &v25, &v29);
      if ( v15 )
      {
        v19 = "BuildIpsecOffers for ipsec proposals failed with 0x%x";
LABEL_29:
        RasIpsecTrace(v19);
        goto LABEL_25;
      }
      BuildQMPolicy((unsigned int)&Uuid, (unsigned int)v46, a2, (_DWORD)v25, v29, g_dwIpsecUdpEncapsulation, cbData);
      v20 = hMem;
      BuildMMOffers((int)hMem, (int)&v32, (int)&v31, 0, v38, cbData, 0);
      LODWORD(v43) = 0;
      v44 = (unsigned int)v31;
      LODWORD(v42) = 28800;
      *((_QWORD *)&v43 + 1) = v20;
      DWORD1(v43) = v32;
      *((_QWORD *)&v42 + 1) = v8;
      DWORD1(v42) = v10;
      memset_0(&v48, 0, 0x58u);
      v50 = 5;
      v51 = &v42;
      v49 = L"L2TP Main Mode Policy";
      v15 = UuidCreate(&Uuid.providerContextKey);
      if ( v15 || (v15 = UuidCreate(&v48)) != 0 )
      {
        v19 = "UuidCreate failed with 0x%x";
        goto LABEL_29;
      }
      v15 = FwpmTransactionBegin0Wrapper();
      if ( v15 )
      {
        v19 = "FwpmTransactionBegin0 failed with 0x%x";
        goto LABEL_29;
      }
      v24 = 1;
      v15 = FwpmProviderContextAdd2(gFwpEngineHandle, &v48, 0, 0);
      if ( v15 )
      {
        v19 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
        goto LABEL_29;
      }
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      v15 = BuildCMMFilter(&v41, &v48, v33);
      if ( v15 )
      {
        v19 = "BuildCMMFilter for MM filter failed with 0x%x";
        goto LABEL_29;
      }
      v15 = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
      if ( v15 )
      {
        v19 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
        goto LABEL_29;
      }
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      v15 = BuildCTxFilter((unsigned int)&v36, (unsigned int)&Uuid, (unsigned int)v33, v21, 1);
      if ( v15 )
      {
        v19 = "BuildCTxFilter for QM filter failed with 0x%x";
        goto LABEL_29;
      }
      v15 = AddFilters(&v36, Src, v27, 0);
      if ( v15
        || (WfpFilterListDestroy(&v36, (char *)&v36 + 8),
            v36 = 0,
            *(_OWORD *)v33 = *(_OWORD *)a1,
            v34 = *(_DWORD *)(a1 + 16),
            BuildCTxFilter((unsigned int)&v36, (unsigned int)&Uuid, (unsigned int)v33, v22, 0),
            (v15 = AddFilters(&v36, Src, v27, &v39)) != 0) )
      {
        v19 = "AddFilters for QM filter failed with 0x%x";
        goto LABEL_29;
      }
      v15 = AddFilters(&v41, Src, v27, 0);
      if ( v15 )
      {
        v19 = "AddFilters for MM filter failed with 0x%x";
        goto LABEL_29;
      }
LABEL_48:
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      gpIpSecSrvList = AddNodeToServerList(v16, a2, (int)v33, (int)&v48, (__int64)&Uuid, Src, v27[0], v39);
      LastError = FwpmTransactionCommit0(gFwpEngineHandle);
      v9 = v25;
      goto LABEL_49;
    }
  }
  if ( v8 || (v8 = LocalAlloc(0x40u, 0x40u)) != 0 )
  {
    v18 = 10LL * v10;
    v8[2 * v18] = 0;
    *(_QWORD *)&v8[2 * v18 + 4] = a4;
    v8[2 * v18 + 2] = a3;
    ++v10;
    goto LABEL_27;
  }
  v15 = GetLastError();
LABEL_25:
  v9 = v25;
  v17 = v24;
LABEL_51:
  if ( v15 && v17 )
    FwpmTransactionAbort0(gFwpEngineHandle);
  WfpFilterListDestroy(&v36, (char *)&v36 + 8);
  WfpFilterListDestroy(&v41, (char *)&v41 + 8);
  if ( v9 )
    FreeIpsecOffers(v9);
  if ( hMem )
    LocalFree(hMem);
  if ( v8 )
    FreeAuthInfoList(v8);
  RasIpsecTrace("DwAddClientIpSecFilter: rc=0x%x");
  return v15;
}

```

## disassembly

```asm
0x1800a0988  mov     [rsp+arg_18], r9
0x1800a098d  mov     [rsp+arg_10], r8d
0x1800a0992  push    rbx
0x1800a0993  push    rsi
0x1800a0994  push    rdi
0x1800a0995  push    r12
0x1800a0997  push    r13
0x1800a0999  push    r14
0x1800a099b  push    r15
0x1800a099d  sub     rsp, 420h
0x1800a09a4  mov     rax, cs:__security_cookie
0x1800a09ab  xor     rax, rsp
0x1800a09ae  mov     [rsp+458h+var_48], rax
0x1800a09b6  mov     r12d, edx
0x1800a09b9  mov     r15, rcx
0x1800a09bc  mov     [rsp+458h+var_328], rcx
0x1800a09c4  mov     [rsp+458h+var_388], edx
0x1800a09cb  mov     rax, [rsp+458h+arg_28]
0x1800a09d3  mov     [rsp+458h+var_380], rax
0x1800a09db  xor     eax, eax
0x1800a09dd  xorps   xmm0, xmm0
0x1800a09e0  movups  [rsp+458h+var_318], xmm0
0x1800a09e8  movups  [rsp+458h+var_308], xmm0
0x1800a09f0  mov     [rsp+458h+var_2F8], eax
0x1800a09f7  xorps   xmm1, xmm1
0x1800a09fa  movups  [rsp+458h+var_358], xmm1
0x1800a0a02  movups  [rsp+458h+var_348], xmm1
0x1800a0a0a  movups  [rsp+458h+var_338], xmm1
0x1800a0a12  lea     ebx, [rax+58h]
0x1800a0a15  mov     r8d, ebx; Size
0x1800a0a18  xor     edx, edx; Val
0x1800a0a1a  lea     rcx, [rsp+458h+var_2E8]; void *
0x1800a0a22  call    memset_0
0x1800a0a27  mov     r8d, ebx; Size
0x1800a0a2a  xor     edx, edx; Val
0x1800a0a2c  lea     rcx, [rsp+458h+Uuid]; void *
0x1800a0a34  call    memset_0
0x1800a0a39  xor     edi, edi
0x1800a0a3b  mov     esi, edi
0x1800a0a3d  mov     [rsp+458h+var_3A8], rdi
0x1800a0a45  mov     r13d, edi
0x1800a0a48  mov     [rsp+458h+var_400], rdi
0x1800a0a4d  mov     r14d, edi
0x1800a0a50  mov     [rsp+458h+var_3E8], edi
0x1800a0a54  mov     [rsp+458h+var_3E4], edi
0x1800a0a58  mov     [rsp+458h+var_3D4], edi
0x1800a0a5f  mov     [rsp+458h+var_3D8], edi
0x1800a0a66  mov     [rsp+458h+var_3EC], edi
0x1800a0a6a  mov     [rsp+458h+var_3F0], edi
0x1800a0a6e  mov     [rsp+458h+var_408], edi
0x1800a0a72  mov     [rsp+458h+var_378], rdi
0x1800a0a7a  lea     rcx, aDwaddclientips_1; "DwAddClientIpSecFilter."
0x1800a0a81  call    RasIpsecTrace
0x1800a0a86  xorps   xmm0, xmm0
0x1800a0a89  movups  [rsp+458h+var_368], xmm0
0x1800a0a91  xorps   xmm1, xmm1
0x1800a0a94  movups  [rsp+458h+var_3A0], xmm1
0x1800a0a9c  mov     edx, 118h; uBytes
0x1800a0aa1  lea     ecx, [rbx-18h]; uFlags
0x1800a0aa4  call    cs:__imp_LocalAlloc
0x1800a0aab  nop     dword ptr [rax+rax+00h]
0x1800a0ab0  mov     [rsp+458h+hMem], rax
0x1800a0ab8  test    rax, rax
0x1800a0abb  jnz     short loc_1800A0ADA
0x1800a0abd  lea     rcx, aDwaddclientips; "DwAddclientipsecfilter: failed to alloc"
0x1800a0ac4  call    RasIpsecTrace
0x1800a0ac9  call    cs:__imp_GetLastError
0x1800a0ad0  nop     dword ptr [rax+rax+00h]
0x1800a0ad5  jmp     loc_1800A10B4
0x1800a0ada  movaps  xmm0, xmmword ptr [r15]
0x1800a0ade  movaps  xmmword ptr [rsp+458h+var_3C8], xmm0
0x1800a0ae6  mov     eax, [r15+10h]
0x1800a0aea  mov     [rsp+458h+var_3B8], eax
0x1800a0af1  lea     rdx, [rsp+458h+var_3C8]
0x1800a0af9  call    FindServerNode
0x1800a0afe  mov     rbx, rax
0x1800a0b01  test    rax, rax
0x1800a0b04  jz      short loc_1800A0B3A
0x1800a0b06  mov     edx, [rax+4Ch]
0x1800a0b09  cmp     r12d, edx
0x1800a0b0c  jz      short loc_1800A0B24
0x1800a0b0e  lea     rcx, aDwaddclientips_2; "DwAddClientIpSecFilter: Already a filte"...
0x1800a0b15  call    RasIpsecTrace
0x1800a0b1a  mov     ebx, 57h ; 'W'
0x1800a0b1f  jmp     loc_1800A10B6
0x1800a0b24  lea     rcx, aDwaddclientips_0; "DwAddClientIpSecFilter: Filter already "...
0x1800a0b2b  call    RasIpsecTrace
0x1800a0b30  inc     dword ptr [rbx+34h]
0x1800a0b33  mov     ebx, edi
0x1800a0b35  jmp     loc_1800A10B6
0x1800a0b3a  mov     ebx, 57h ; 'W'
0x1800a0b3f  mov     [rsp+458h+var_3DC], ebx
0x1800a0b43  mov     r13d, [rsp+458h+cbData]
0x1800a0b4b  cmp     r13d, 0Ah
0x1800a0b4f  jbe     short loc_1800A0B67
0x1800a0b51  lea     rcx, aDwaddclientips_3; "DwAddClientIpSecFilter: Invalid value o"...
0x1800a0b58  call    RasIpsecTrace
0x1800a0b5d  mov     r13, [rsp+458h+var_400]
0x1800a0b62  jmp     loc_1800A10B6
0x1800a0b67  mov     [rsp+458h+var_3F4], edi
0x1800a0b6b  mov     ecx, r12d
0x1800a0b6e  test    r12d, r12d
0x1800a0b71  jz      short loc_1800A0B86
0x1800a0b73  sub     ecx, 1
0x1800a0b76  jz      short loc_1800A0B86
0x1800a0b78  sub     ecx, 1; int
0x1800a0b7b  jz      short loc_1800A0B86
0x1800a0b7d  cmp     ecx, 1
0x1800a0b80  jnz     loc_1800A1037
0x1800a0b86  mov     eax, [rsp+458h+arg_10]
0x1800a0b8d  test    eax, eax
0x1800a0b8f  jnz     loc_1800A0C1C
0x1800a0b95  lea     r9, [rsp+458h+var_3F4]
0x1800a0b9a  lea     r8, [rsp+458h+var_3E8]
0x1800a0b9f  lea     rdx, [rsp+458h+var_3A8]
0x1800a0ba7  xor     ecx, ecx
0x1800a0ba9  call    GenerateCertificatesList
0x1800a0bae  mov     ebx, eax
0x1800a0bb0  mov     [rsp+458h+var_3DC], eax
0x1800a0bb4  jmp     short loc_1800A0BE8
0x1800a0bb6  mov     edx, [rsp+458h+var_3EC]
0x1800a0bba  lea     rcx, aGeneratecertif; "GenerateCertificatesList raised excepti"...
0x1800a0bc1  call    RasIpsecTrace
0x1800a0bc6  xor     edi, edi
0x1800a0bc8  mov     r13d, [rsp+458h+cbData]
0x1800a0bd0  mov     ebx, [rsp+458h+var_3DC]
0x1800a0bd4  mov     [rsp+458h+var_408], edi
0x1800a0bd8  mov     r15, [rsp+458h+var_328]
0x1800a0be0  mov     r12d, [rsp+458h+var_388]
0x1800a0be8  mov     r14d, [rsp+458h+var_3E8]
0x1800a0bed  test    ebx, ebx
0x1800a0bef  jnz     short loc_1800A0C4A
0x1800a0bf1  test    r14d, r14d
0x1800a0bf4  jz      short loc_1800A0C4A
0x1800a0bf6  cmp     [rsp+458h+var_3F4], edi
0x1800a0bfa  jnz     short loc_1800A0C4A
0x1800a0bfc  mov     rsi, [rsp+458h+var_3A8]
0x1800a0c04  mov     eax, [rsp+458h+arg_10]
0x1800a0c0b  test    rsi, rsi
0x1800a0c0e  jz      short loc_1800A0C14
0x1800a0c10  or      dword ptr [rsi+38h], 2
0x1800a0c14  test    eax, eax
0x1800a0c16  jz      loc_1800A0CAE
0x1800a0c1c  test    rsi, rsi
0x1800a0c1f  jnz     short loc_1800A0C86
0x1800a0c21  lea     edx, [rsi+40h]; uBytes
0x1800a0c24  mov     ecx, edx; uFlags
0x1800a0c26  call    cs:__imp_LocalAlloc
0x1800a0c2d  nop     dword ptr [rax+rax+00h]
0x1800a0c32  mov     rsi, rax
0x1800a0c35  test    rax, rax
0x1800a0c38  jnz     short loc_1800A0C86
0x1800a0c3a  call    cs:__imp_GetLastError
0x1800a0c41  nop     dword ptr [rax+rax+00h]
0x1800a0c46  mov     ebx, eax
0x1800a0c48  jmp     short loc_1800A0C78
0x1800a0c4a  mov     r9d, [rsp+458h+var_3F4]
0x1800a0c4f  mov     r8d, r14d
0x1800a0c52  mov     edx, ebx
0x1800a0c54  lea     rcx, aFailedToGenera; "Failed to generate certificate list. rc"...
0x1800a0c5b  call    RasIpsecTrace
0x1800a0c60  test    r14d, r14d
0x1800a0c63  jz      short loc_1800A0C6B
0x1800a0c65  cmp     [rsp+458h+var_3F4], edi
0x1800a0c69  jz      short loc_1800A0C70
0x1800a0c6b  mov     ebx, 2FEh
0x1800a0c70  mov     rsi, [rsp+458h+var_3A8]
0x1800a0c78  mov     r13, [rsp+458h+var_400]
0x1800a0c7d  mov     eax, [rsp+458h+var_408]
0x1800a0c81  jmp     loc_1800A10B8
0x1800a0c86  mov     eax, r14d
0x1800a0c89  lea     rcx, [rax+rax*4]
0x1800a0c8d  add     rcx, rcx
0x1800a0c90  mov     [rsi+rcx*8], edi
0x1800a0c93  mov     rax, [rsp+458h+arg_18]
0x1800a0c9b  mov     [rsi+rcx*8+10h], rax
0x1800a0ca0  mov     eax, [rsp+458h+arg_10]
0x1800a0ca7  mov     [rsi+rcx*8+8], eax
0x1800a0cab  inc     r14d
0x1800a0cae  mov     [rsp+458h+var_410], r13d
0x1800a0cb3  mov     rax, [rsp+458h+var_380]
0x1800a0cbb  mov     [rsp+458h+var_418], rax
0x1800a0cc0  mov     dword ptr [rsp+458h+Src], 0E10h
0x1800a0cc8  mov     dword ptr [rsp+458h+var_438], 3D090h
0x1800a0cd0  lea     r8, [rsp+458h+var_3E4]
0x1800a0cd5  lea     rdx, [rsp+458h+var_400]
0x1800a0cda  mov     ecx, r12d
0x1800a0cdd  call    BuildIpsecOffers
0x1800a0ce2  mov     ebx, eax
0x1800a0ce4  test    eax, eax
0x1800a0ce6  jz      short loc_1800A0CF8
0x1800a0ce8  lea     rcx, aBuildipsecoffe; "BuildIpsecOffers for ipsec proposals fa"...
0x1800a0cef  mov     edx, eax
0x1800a0cf1  call    RasIpsecTrace
0x1800a0cf6  jmp     short loc_1800A0C78
0x1800a0cf8  mov     dword ptr [rsp+458h+var_428], r13d
0x1800a0cfd  mov     eax, cs:g_dwIpsecUdpEncapsulation
0x1800a0d03  mov     dword ptr [rsp+458h+Src], eax
0x1800a0d07  mov     eax, [rsp+458h+var_3E4]
0x1800a0d0b  mov     dword ptr [rsp+458h+var_438], eax
0x1800a0d0f  mov     r9, [rsp+458h+var_400]
0x1800a0d14  mov     r8d, r12d
0x1800a0d17  lea     rdx, [rsp+458h+var_318]
0x1800a0d1f  lea     rcx, [rsp+458h+Uuid]
0x1800a0d27  call    BuildQMPolicy
0x1800a0d2c  mov     [rsp+458h+var_428], rdi; __int64
0x1800a0d31  mov     dword ptr [rsp+458h+Src], r13d; cbData
0x1800a0d36  mov     rax, [rsp+458h+var_380]
0x1800a0d3e  mov     [rsp+458h+var_438], rax; __int64
0x1800a0d43  xor     r9d, r9d; int
0x1800a0d46  lea     r8, [rsp+458h+var_3D8]; int
0x1800a0d4e  lea     rdx, [rsp+458h+var_3D4]; int
0x1800a0d56  mov     rbx, [rsp+458h+hMem]
0x1800a0d5e  mov     rcx, rbx; int
0x1800a0d61  call    BuildMMOffers
0x1800a0d66  mov     dword ptr [rsp+458h+var_348], edi
0x1800a0d6d  mov     dword ptr [rsp+458h+var_338+4], edi
0x1800a0d74  mov     qword ptr [rsp+458h+var_338+8], 708h
0x1800a0d80  mov     eax, [rsp+458h+var_3D8]
0x1800a0d87  mov     dword ptr [rsp+458h+var_338], eax
0x1800a0d8e  mov     dword ptr [rsp+458h+var_358], 7080h
0x1800a0d99  mov     qword ptr [rsp+458h+var_348+8], rbx
0x1800a0da1  mov     eax, [rsp+458h+var_3D4]
0x1800a0da8  mov     dword ptr [rsp+458h+var_348+4], eax
0x1800a0daf  mov     qword ptr [rsp+458h+var_358+8], rsi
0x1800a0db7  mov     dword ptr [rsp+458h+var_358+4], r14d
0x1800a0dbf  xor     edx, edx; Val
0x1800a0dc1  lea     r8d, [rdx+58h]; Size
0x1800a0dc5  lea     rcx, [rsp+458h+var_2E8]; void *
0x1800a0dcd  call    memset_0
0x1800a0dd2  mov     [rsp+458h+var_2A8], 5
0x1800a0ddd  lea     rax, [rsp+458h+var_358]
0x1800a0de5  mov     [rsp+458h+var_2A0], rax
0x1800a0ded  lea     rax, aL2tpMainModePo; "L2TP Main Mode Policy"
0x1800a0df4  mov     [rsp+458h+var_2D8], rax
0x1800a0dfc  lea     rcx, [rsp+458h+Uuid]; Uuid
0x1800a0e04  call    cs:__imp_UuidCreate
0x1800a0e0b  nop     dword ptr [rax+rax+00h]
0x1800a0e10  mov     ebx, eax
0x1800a0e12  test    eax, eax
0x1800a0e14  jz      short loc_1800A0E22
0x1800a0e16  lea     rcx, aUuidcreateFail; "UuidCreate failed with 0x%x"
0x1800a0e1d  jmp     loc_1800A0CEF
0x1800a0e22  lea     rcx, [rsp+458h+var_2E8]; Uuid
0x1800a0e2a  call    cs:__imp_UuidCreate
0x1800a0e31  nop     dword ptr [rax+rax+00h]
0x1800a0e36  mov     ebx, eax
0x1800a0e38  test    eax, eax
0x1800a0e3a  jnz     short loc_1800A0E16
0x1800a0e3c  call    FwpmTransactionBegin0Wrapper
0x1800a0e41  mov     ebx, eax
0x1800a0e43  test    eax, eax
0x1800a0e45  jz      short loc_1800A0E53
0x1800a0e47  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x1800a0e4e  jmp     loc_1800A0CEF
0x1800a0e53  mov     [rsp+458h+var_408], 1
0x1800a0e5b  xor     r9d, r9d
0x1800a0e5e  xor     r8d, r8d
0x1800a0e61  lea     rdx, [rsp+458h+var_2E8]
0x1800a0e69  mov     rcx, cs:gFwpEngineHandle
0x1800a0e70  call    cs:__imp_FwpmProviderContextAdd2
0x1800a0e77  nop     dword ptr [rax+rax+00h]
0x1800a0e7c  mov     ebx, eax
0x1800a0e7e  test    eax, eax
0x1800a0e80  jz      short loc_1800A0E8E
0x1800a0e82  lea     rcx, aFwpmproviderco; "FwpmProviderContextAdd0 for MM policy f"...
0x1800a0e89  jmp     loc_1800A0CEF
0x1800a0e8e  movaps  xmm0, xmmword ptr [r15]
0x1800a0e92  movaps  xmmword ptr [rsp+458h+var_3C8], xmm0
0x1800a0e9a  mov     eax, [r15+10h]
0x1800a0e9e  mov     [rsp+458h+var_3B8], eax
0x1800a0ea5  lea     r8, [rsp+458h+var_3C8]
0x1800a0ead  lea     rdx, [rsp+458h+var_2E8]
0x1800a0eb5  lea     rcx, [rsp+458h+var_368]
0x1800a0ebd  call    BuildCMMFilter
0x1800a0ec2  mov     ebx, eax
0x1800a0ec4  test    eax, eax
0x1800a0ec6  jz      short loc_1800A0ED4
0x1800a0ec8  lea     rcx, aBuildcmmfilter; "BuildCMMFilter for MM filter failed wit"...
0x1800a0ecf  jmp     loc_1800A0CEF
0x1800a0ed4  xor     r9d, r9d; id
0x1800a0ed7  xor     r8d, r8d; sd
0x1800a0eda  lea     rdx, [rsp+458h+Uuid]; providerContext
0x1800a0ee2  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800a0ee9  call    cs:__imp_FwpmProviderContextAdd0
0x1800a0ef0  nop     dword ptr [rax+rax+00h]
0x1800a0ef5  mov     ebx, eax
0x1800a0ef7  test    eax, eax
0x1800a0ef9  jz      short loc_1800A0F07
0x1800a0efb  lea     rcx, aFwpmproviderco_1; "FwpmProviderContextAdd0 for QM policy f"...
0x1800a0f02  jmp     loc_1800A0CEF
0x1800a0f07  movaps  xmm0, xmmword ptr [r15]
0x1800a0f0b  movaps  xmmword ptr [rsp+458h+var_3C8], xmm0
0x1800a0f13  mov     eax, [r15+10h]
0x1800a0f17  mov     [rsp+458h+var_3B8], eax
0x1800a0f1e  mov     dword ptr [rsp+458h+var_438], 1
0x1800a0f26  lea     r8, [rsp+458h+var_3C8]
0x1800a0f2e  lea     rdx, [rsp+458h+Uuid]
0x1800a0f36  lea     rcx, [rsp+458h+var_3A0]
0x1800a0f3e  call    BuildCTxFilter
  ... truncated ...
```
