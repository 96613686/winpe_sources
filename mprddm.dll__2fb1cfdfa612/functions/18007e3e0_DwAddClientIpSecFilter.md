# DwAddClientIpSecFilter

- ea: `0x18007e3e0`
- end: `0x18007eb49`
- name: `DwAddClientIpSecFilter`
- size: `1897`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fe00`

## callees

- `0x18007d7f0`
- `0x18007d94c`
- `0x18007da3c`
- `0x18007db24`
- `0x18007dedc`
- `0x18007e30c`
- `0x18007e3e0`
- `0x1800801e0`
- `0x180080264`
- `0x1800803a8`
- `0x1800804dc`
- `0x1800805f8`
- `0x180081078`
- `0x18008a780`
- `0x18008b464`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18007eae4`
- `KERNEL32!LocalFree` at `0x18007eafa`
- `KERNEL32!LocalFree` at `0x18007eae4`
- `KERNEL32!LocalFree` at `0x18007eafa`
- `KERNEL32!GetLastError` at `0x18007e508`
- `KERNEL32!GetLastError` at `0x18007e649`
- `KERNEL32!GetLastError` at `0x18007e508`
- `KERNEL32!GetLastError` at `0x18007e649`
- `KERNEL32!LocalAlloc` at `0x18007e4e9`
- `KERNEL32!LocalAlloc` at `0x18007e63b`
- `KERNEL32!LocalAlloc` at `0x18007e4e9`
- `KERNEL32!LocalAlloc` at `0x18007e63b`
- `RPCRT4!UuidCreate` at `0x18007e7e4`
- `RPCRT4!UuidCreate` at `0x18007e80b`
- `RPCRT4!UuidCreate` at `0x18007e7e4`
- `RPCRT4!UuidCreate` at `0x18007e80b`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007ea6c`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18007ea6c`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18007e8b8`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18007e8b8`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18007ea85`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18007ea85`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18007e848`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18007e848`

## string_xrefs

- `0x18007e547`: `DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.`
- `0x18007e55d`: `DwAddClientIpSecFilter: Filter already exists.`
- `0x18007e7f0`: `UuidCreate failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DwAddClientIpSecFilter(__int64 a1, unsigned int a2, int a3, __int64 a4)
{
  _DWORD *v6; // rsi
  char *v7; // r13
  unsigned int v8; // r14d
  __int64 v9; // rcx
  DWORD LastError; // eax
  __int64 ServerNode; // rax
  __int64 v12; // rbx
  DWORD v13; // ebx
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rcx
  HLOCAL v17; // rbx
  const CHAR *v18; // rcx
  int v19; // r9d
  int v20; // r9d
  unsigned int i; // r15d
  int v23; // [rsp+20h] [rbp-428h]
  DWORD Src; // [rsp+28h] [rbp-420h]
  int v25; // [rsp+50h] [rbp-3F8h]
  int v26; // [rsp+58h] [rbp-3F0h] BYREF
  int v27; // [rsp+5Ch] [rbp-3ECh] BYREF
  int v28[2]; // [rsp+60h] [rbp-3E8h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-3E0h] BYREF
  int v30; // [rsp+70h] [rbp-3D8h]
  int v31; // [rsp+74h] [rbp-3D4h] BYREF
  int v32; // [rsp+78h] [rbp-3D0h] BYREF
  int v33[4]; // [rsp+80h] [rbp-3C8h] BYREF
  int v34; // [rsp+90h] [rbp-3B8h]
  _DWORD *v35; // [rsp+A0h] [rbp-3A8h] BYREF
  char *v36; // [rsp+A8h] [rbp-3A0h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-398h] BYREF
  unsigned int v38; // [rsp+C8h] [rbp-380h]
  __int64 v39; // [rsp+D0h] [rbp-378h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp-370h]
  __int128 v41; // [rsp+E0h] [rbp-368h] BYREF
  __int128 v42; // [rsp+F0h] [rbp-358h] BYREF
  __int128 v43; // [rsp+100h] [rbp-348h]
  __int128 v44; // [rsp+110h] [rbp-338h]
  __int64 v45; // [rsp+120h] [rbp-328h]
  _OWORD v46[2]; // [rsp+130h] [rbp-318h] BYREF
  int v47; // [rsp+150h] [rbp-2F8h]
  UUID v48; // [rsp+160h] [rbp-2E8h] BYREF
  const wchar_t *v49; // [rsp+170h] [rbp-2D8h]
  int v50; // [rsp+1A0h] [rbp-2A8h]
  __int128 *v51; // [rsp+1A8h] [rbp-2A0h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+1C0h] [rbp-288h] BYREF
  _BYTE v53[480]; // [rsp+220h] [rbp-228h] BYREF

  v45 = a1;
  v38 = a2;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  memset_0(&v48, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v6 = 0;
  v35 = 0;
  v7 = 0;
  v36 = 0;
  v8 = 0;
  v29 = 0;
  v28[0] = 0;
  v32 = 0;
  v31 = 0;
  v28[1] = 0;
  v27 = 0;
  v25 = 0;
  v39 = 0;
  RasIpsecTrace("DwAddClientIpSecFilter.");
  v41 = 0;
  v37 = 0;
  hMem = LocalAlloc(0x40u, 0x118u);
  if ( !hMem )
  {
    RasIpsecTrace("DwAddclientipsecfilter: failed to alloc");
    LastError = GetLastError();
LABEL_47:
    v13 = LastError;
LABEL_48:
    v15 = 0;
    goto LABEL_49;
  }
  *(_OWORD *)v33 = *(_OWORD *)a1;
  v34 = *(_DWORD *)(a1 + 16);
  ServerNode = FindServerNode(v9, v33);
  v12 = ServerNode;
  if ( ServerNode )
  {
    if ( a2 == *(_DWORD *)(ServerNode + 76) )
    {
      RasIpsecTrace("DwAddClientIpSecFilter: Filter already exists.");
      ++*(_DWORD *)(v12 + 52);
      v13 = 0;
    }
    else
    {
      RasIpsecTrace("DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.");
      v13 = 87;
    }
    goto LABEL_48;
  }
  v26 = 0;
  if ( a2 >= 2 )
  {
    v14 = a2 - 2;
    if ( a2 - 2 > 1 )
      goto LABEL_46;
  }
  v30 = 87;
  if ( !a3 )
  {
    v13 = GenerateCertificatesList(0, &v35, &v29, &v26);
    v30 = v13;
    v8 = v29;
    if ( v13 || !v29 || v26 )
    {
      RasIpsecTrace("Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
      if ( !v8 || v26 )
        v13 = 766;
      v6 = v35;
      goto LABEL_23;
    }
    v6 = v35;
    if ( v35 )
      v35[14] |= 2u;
    if ( !a3 )
    {
LABEL_25:
      v13 = BuildIpsecOffers(a2, &v36, v28);
      if ( v13 )
      {
        RasIpsecTrace("BuildIpsecOffers for ipsec proposals failed with 0x%x");
        v7 = v36;
        goto LABEL_23;
      }
      v7 = v36;
      BuildQMPolicy((unsigned int)&Uuid, (unsigned int)v46, a2, (_DWORD)v36, v28[0], g_dwIpsecUdpEncapsulation);
      v17 = hMem;
      BuildMMOffers((int)hMem, (int)&v32, (int)&v31, 0, v23, Src, 0);
      LODWORD(v43) = 0;
      v44 = (unsigned int)v31;
      LODWORD(v42) = 28800;
      *((_QWORD *)&v43 + 1) = v17;
      DWORD1(v43) = v32;
      *((_QWORD *)&v42 + 1) = v6;
      DWORD1(v42) = v8;
      memset_0(&v48, 0, 0x58u);
      v50 = 5;
      v51 = &v42;
      v49 = L"L2TP Main Mode Policy";
      v13 = UuidCreate(&Uuid.providerContextKey);
      if ( v13 || (v13 = UuidCreate(&v48)) != 0 )
      {
        v18 = "UuidCreate failed with 0x%x";
LABEL_29:
        RasIpsecTrace(v18);
        goto LABEL_23;
      }
      v13 = FwpmTransactionBegin0Wrapper();
      if ( v13 )
      {
        v18 = "FwpmTransactionBegin0 failed with 0x%x";
        goto LABEL_29;
      }
      v25 = 1;
      v13 = FwpmProviderContextAdd2(gFwpEngineHandle, &v48, 0, 0);
      if ( v13 )
      {
        v18 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
        goto LABEL_29;
      }
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      v13 = BuildCMMFilter(&v41, &v48, v33);
      if ( v13 )
      {
        v18 = "BuildCMMFilter for MM filter failed with 0x%x";
        goto LABEL_29;
      }
      v13 = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
      if ( v13 )
      {
        v18 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
        goto LABEL_29;
      }
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      v13 = BuildCTxFilter((unsigned int)&v37, (unsigned int)&Uuid, (unsigned int)v33, v19, 1);
      if ( v13 )
      {
        v18 = "BuildCTxFilter for QM filter failed with 0x%x";
        goto LABEL_29;
      }
      v13 = AddFilters(&v37, v53, &v27, 0);
      if ( v13
        || (WfpFilterListDestroy(&v37, (char *)&v37 + 8),
            v37 = 0,
            *(_OWORD *)v33 = *(_OWORD *)a1,
            v34 = *(_DWORD *)(a1 + 16),
            BuildCTxFilter((unsigned int)&v37, (unsigned int)&Uuid, (unsigned int)v33, v20, 0),
            (v13 = AddFilters(&v37, v53, &v27, &v39)) != 0) )
      {
        v18 = "AddFilters for QM filter failed with 0x%x";
        goto LABEL_29;
      }
      v13 = AddFilters(&v41, v53, &v27, 0);
      if ( v13 )
      {
        v18 = "AddFilters for MM filter failed with 0x%x";
        goto LABEL_29;
      }
LABEL_46:
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      gpIpSecSrvList = AddNodeToServerList(v14, a2, (int)v33, (int)&v48, (__int64)&Uuid, v53, v27, v39);
      LastError = FwpmTransactionCommit0(gFwpEngineHandle);
      goto LABEL_47;
    }
  }
  if ( v6 || (v6 = LocalAlloc(0x40u, 0x40u)) != 0 )
  {
    v16 = 10LL * v8;
    v6[2 * v16] = 0;
    *(_QWORD *)&v6[2 * v16 + 4] = a4;
    v6[2 * v16 + 2] = a3;
    ++v8;
    goto LABEL_25;
  }
  v13 = GetLastError();
LABEL_23:
  v15 = v25;
LABEL_49:
  if ( v13 && v15 )
    FwpmTransactionAbort0(gFwpEngineHandle);
  WfpFilterListDestroy(&v37, (char *)&v37 + 8);
  WfpFilterListDestroy(&v41, (char *)&v41 + 8);
  if ( v7 )
  {
    for ( i = 0; i < v28[0]; ++i )
      WfpClearIpsecProposal(&v7[32 * i]);
    LocalFree(v7);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v6 )
    FreeAuthInfoList(v6);
  RasIpsecTrace("DwAddClientIpSecFilter: rc=0x%x");
  return v13;
}

```

## disassembly

```asm
0x18007e3e0  mov     [rsp+arg_18], r9
0x18007e3e5  mov     [rsp+arg_10], r8d
0x18007e3ea  push    rbx
0x18007e3eb  push    rsi
0x18007e3ec  push    rdi
0x18007e3ed  push    r12
0x18007e3ef  push    r13
0x18007e3f1  push    r14
0x18007e3f3  push    r15
0x18007e3f5  sub     rsp, 410h
0x18007e3fc  mov     rax, cs:__security_cookie
0x18007e403  xor     rax, rsp
0x18007e406  mov     [rsp+448h+var_48], rax
0x18007e40e  mov     r12d, edx
0x18007e411  mov     r15, rcx
0x18007e414  mov     [rsp+448h+var_328], rcx
0x18007e41c  mov     [rsp+448h+var_380], edx
0x18007e423  xor     eax, eax
0x18007e425  xorps   xmm0, xmm0
0x18007e428  movups  [rsp+448h+var_318], xmm0
0x18007e430  movups  [rsp+448h+var_308], xmm0
0x18007e438  mov     [rsp+448h+var_2F8], eax
0x18007e43f  xorps   xmm1, xmm1
0x18007e442  movups  [rsp+448h+var_358], xmm1
0x18007e44a  movups  [rsp+448h+var_348], xmm1
0x18007e452  movups  [rsp+448h+var_338], xmm1
0x18007e45a  lea     ebx, [rax+58h]
0x18007e45d  mov     r8d, ebx; Size
0x18007e460  xor     edx, edx; Val
0x18007e462  lea     rcx, [rsp+448h+var_2E8]; void *
0x18007e46a  call    memset_0
0x18007e46f  mov     r8d, ebx; Size
0x18007e472  xor     edx, edx; Val
0x18007e474  lea     rcx, [rsp+448h+Uuid]; void *
0x18007e47c  call    memset_0
0x18007e481  xor     edi, edi
0x18007e483  mov     esi, edi
0x18007e485  mov     [rsp+448h+var_3A8], rdi
0x18007e48d  mov     r13d, edi
0x18007e490  mov     [rsp+448h+var_3A0], rdi
0x18007e498  mov     r14d, edi
0x18007e49b  mov     [rsp+448h+var_3E0], edi
0x18007e49f  mov     [rsp+448h+var_3E8], edi
0x18007e4a3  mov     [rsp+448h+var_3D0], edi
0x18007e4a7  mov     [rsp+448h+var_3D4], edi
0x18007e4ab  mov     [rsp+448h+var_3E4], edi
0x18007e4af  mov     [rsp+448h+var_3EC], edi
0x18007e4b3  mov     [rsp+448h+var_3F8], edi
0x18007e4b7  mov     [rsp+448h+var_378], rdi
0x18007e4bf  lea     rcx, aDwaddclientips_1; "DwAddClientIpSecFilter."
0x18007e4c6  call    RasIpsecTrace
0x18007e4cb  xorps   xmm0, xmm0
0x18007e4ce  movups  [rsp+448h+var_368], xmm0
0x18007e4d6  xorps   xmm1, xmm1
0x18007e4d9  movups  [rsp+448h+var_398], xmm1
0x18007e4e1  mov     edx, 118h; uBytes
0x18007e4e6  lea     ecx, [rbx-18h]; uFlags
0x18007e4e9  call    cs:__imp_LocalAlloc
0x18007e4ef  mov     [rsp+448h+hMem], rax
0x18007e4f7  test    rax, rax
0x18007e4fa  jnz     short loc_18007E513
0x18007e4fc  lea     rcx, aDwaddclientips; "DwAddclientipsecfilter: failed to alloc"
0x18007e503  call    RasIpsecTrace
0x18007e508  call    cs:__imp_GetLastError
0x18007e50e  jmp     loc_18007EA72
0x18007e513  movaps  xmm0, xmmword ptr [r15]
0x18007e517  movaps  xmmword ptr [rsp+448h+var_3C8], xmm0
0x18007e51f  mov     eax, [r15+10h]
0x18007e523  mov     [rsp+448h+var_3B8], eax
0x18007e52a  lea     rdx, [rsp+448h+var_3C8]
0x18007e532  call    FindServerNode
0x18007e537  mov     rbx, rax
0x18007e53a  test    rax, rax
0x18007e53d  jz      short loc_18007E573
0x18007e53f  mov     edx, [rax+4Ch]
0x18007e542  cmp     r12d, edx
0x18007e545  jz      short loc_18007E55D
0x18007e547  lea     rcx, aDwaddclientips_2; "DwAddClientIpSecFilter: Already a filte"...
0x18007e54e  call    RasIpsecTrace
0x18007e553  mov     ebx, 57h ; 'W'
0x18007e558  jmp     loc_18007EA74
0x18007e55d  lea     rcx, aDwaddclientips_0; "DwAddClientIpSecFilter: Filter already "...
0x18007e564  call    RasIpsecTrace
0x18007e569  inc     dword ptr [rbx+34h]
0x18007e56c  mov     ebx, edi
0x18007e56e  jmp     loc_18007EA74
0x18007e573  mov     [rsp+448h+var_3F0], edi
0x18007e577  mov     ecx, r12d
0x18007e57a  test    r12d, r12d
0x18007e57d  jz      short loc_18007E592
0x18007e57f  sub     ecx, 1
0x18007e582  jz      short loc_18007E592
0x18007e584  sub     ecx, 1; int
0x18007e587  jz      short loc_18007E592
0x18007e589  cmp     ecx, 1
0x18007e58c  jnz     loc_18007EA00
0x18007e592  mov     ebx, 57h ; 'W'
0x18007e597  mov     [rsp+448h+var_3D8], ebx
0x18007e59b  mov     eax, [rsp+448h+arg_10]
0x18007e5a2  test    eax, eax
0x18007e5a4  jnz     loc_18007E631
0x18007e5aa  lea     r9, [rsp+448h+var_3F0]
0x18007e5af  lea     r8, [rsp+448h+var_3E0]
0x18007e5b4  lea     rdx, [rsp+448h+var_3A8]
0x18007e5bc  xor     ecx, ecx
0x18007e5be  call    GenerateCertificatesList
0x18007e5c3  mov     ebx, eax
0x18007e5c5  mov     [rsp+448h+var_3D8], eax
0x18007e5c9  jmp     short loc_18007E5FD
0x18007e5cb  mov     edx, [rsp+448h+var_3E4]
0x18007e5cf  lea     rcx, aGeneratecertif; "GenerateCertificatesList raised excepti"...
0x18007e5d6  call    RasIpsecTrace
0x18007e5db  xor     edi, edi
0x18007e5dd  mov     ebx, [rsp+448h+var_3D8]
0x18007e5e1  mov     r13, [rsp+448h+var_3A0]
0x18007e5e9  mov     [rsp+448h+var_3F8], edi
0x18007e5ed  mov     r15, [rsp+448h+var_328]
0x18007e5f5  mov     r12d, [rsp+448h+var_380]
0x18007e5fd  mov     r14d, [rsp+448h+var_3E0]
0x18007e602  test    ebx, ebx
0x18007e604  jnz     short loc_18007E653
0x18007e606  test    r14d, r14d
0x18007e609  jz      short loc_18007E653
0x18007e60b  cmp     [rsp+448h+var_3F0], edi
0x18007e60f  jnz     short loc_18007E653
0x18007e611  mov     rsi, [rsp+448h+var_3A8]
0x18007e619  mov     eax, [rsp+448h+arg_10]
0x18007e620  test    rsi, rsi
0x18007e623  jz      short loc_18007E629
0x18007e625  or      dword ptr [rsi+38h], 2
0x18007e629  test    eax, eax
0x18007e62b  jz      loc_18007E6B2
0x18007e631  test    rsi, rsi
0x18007e634  jnz     short loc_18007E68A
0x18007e636  lea     edx, [rsi+40h]; uBytes
0x18007e639  mov     ecx, edx; uFlags
0x18007e63b  call    cs:__imp_LocalAlloc
0x18007e641  mov     rsi, rax
0x18007e644  test    rax, rax
0x18007e647  jnz     short loc_18007E68A
0x18007e649  call    cs:__imp_GetLastError
0x18007e64f  mov     ebx, eax
0x18007e651  jmp     short loc_18007E681
0x18007e653  mov     r9d, [rsp+448h+var_3F0]
0x18007e658  mov     r8d, r14d
0x18007e65b  mov     edx, ebx
0x18007e65d  lea     rcx, aFailedToGenera; "Failed to generate certificate list. rc"...
0x18007e664  call    RasIpsecTrace
0x18007e669  test    r14d, r14d
0x18007e66c  jz      short loc_18007E674
0x18007e66e  cmp     [rsp+448h+var_3F0], edi
0x18007e672  jz      short loc_18007E679
0x18007e674  mov     ebx, 2FEh
0x18007e679  mov     rsi, [rsp+448h+var_3A8]
0x18007e681  mov     eax, [rsp+448h+var_3F8]
0x18007e685  jmp     loc_18007EA76
0x18007e68a  mov     eax, r14d
0x18007e68d  lea     rcx, [rax+rax*4]
0x18007e691  add     rcx, rcx
0x18007e694  mov     [rsi+rcx*8], edi
0x18007e697  mov     rax, [rsp+448h+arg_18]
0x18007e69f  mov     [rsi+rcx*8+10h], rax
0x18007e6a4  mov     eax, [rsp+448h+arg_10]
0x18007e6ab  mov     [rsi+rcx*8+8], eax
0x18007e6af  inc     r14d
0x18007e6b2  mov     dword ptr [rsp+448h+Src], 0E10h
0x18007e6ba  mov     dword ptr [rsp+448h+var_428], 3D090h
0x18007e6c2  lea     r8, [rsp+448h+var_3E8]
0x18007e6c7  lea     rdx, [rsp+448h+var_3A0]
0x18007e6cf  mov     ecx, r12d
0x18007e6d2  call    BuildIpsecOffers
0x18007e6d7  mov     ebx, eax
0x18007e6d9  test    eax, eax
0x18007e6db  jz      short loc_18007E6F5
0x18007e6dd  mov     edx, eax
0x18007e6df  lea     rcx, aBuildipsecoffe; "BuildIpsecOffers for ipsec proposals fa"...
0x18007e6e6  call    RasIpsecTrace
0x18007e6eb  mov     r13, [rsp+448h+var_3A0]
0x18007e6f3  jmp     short loc_18007E681
0x18007e6f5  mov     eax, cs:g_dwIpsecUdpEncapsulation
0x18007e6fb  mov     dword ptr [rsp+448h+Src], eax; cbData
0x18007e6ff  mov     eax, [rsp+448h+var_3E8]
0x18007e703  mov     dword ptr [rsp+448h+var_428], eax; int
0x18007e707  mov     r13, [rsp+448h+var_3A0]
0x18007e70f  mov     r9, r13
0x18007e712  mov     r8d, r12d
0x18007e715  lea     rdx, [rsp+448h+var_318]
0x18007e71d  lea     rcx, [rsp+448h+Uuid]
0x18007e725  call    BuildQMPolicy
0x18007e72a  mov     [rsp+448h+var_418], rdi; __int64
0x18007e72f  xor     r9d, r9d; int
0x18007e732  lea     r8, [rsp+448h+var_3D4]; int
0x18007e737  lea     rdx, [rsp+448h+var_3D0]; int
0x18007e73c  mov     rbx, [rsp+448h+hMem]
0x18007e744  mov     rcx, rbx; int
0x18007e747  call    BuildMMOffers
0x18007e74c  mov     dword ptr [rsp+448h+var_348], edi
0x18007e753  mov     dword ptr [rsp+448h+var_338+4], edi
0x18007e75a  mov     qword ptr [rsp+448h+var_338+8], 708h
0x18007e766  mov     eax, [rsp+448h+var_3D4]
0x18007e76a  mov     dword ptr [rsp+448h+var_338], eax
0x18007e771  mov     dword ptr [rsp+448h+var_358], 7080h
0x18007e77c  mov     qword ptr [rsp+448h+var_348+8], rbx
0x18007e784  mov     eax, [rsp+448h+var_3D0]
0x18007e788  mov     dword ptr [rsp+448h+var_348+4], eax
0x18007e78f  mov     qword ptr [rsp+448h+var_358+8], rsi
0x18007e797  mov     dword ptr [rsp+448h+var_358+4], r14d
0x18007e79f  xor     edx, edx; Val
0x18007e7a1  lea     r8d, [rdx+58h]; Size
0x18007e7a5  lea     rcx, [rsp+448h+var_2E8]; void *
0x18007e7ad  call    memset_0
0x18007e7b2  mov     [rsp+448h+var_2A8], 5
0x18007e7bd  lea     rax, [rsp+448h+var_358]
0x18007e7c5  mov     [rsp+448h+var_2A0], rax
0x18007e7cd  lea     rax, aL2tpMainModePo; "L2TP Main Mode Policy"
0x18007e7d4  mov     [rsp+448h+var_2D8], rax
0x18007e7dc  lea     rcx, [rsp+448h+Uuid]; Uuid
0x18007e7e4  call    cs:__imp_UuidCreate
0x18007e7ea  mov     ebx, eax
0x18007e7ec  test    eax, eax
0x18007e7ee  jz      short loc_18007E803
0x18007e7f0  lea     rcx, aUuidcreateFail; "UuidCreate failed with 0x%x"
0x18007e7f7  mov     edx, eax
0x18007e7f9  call    RasIpsecTrace
0x18007e7fe  jmp     loc_18007E681
0x18007e803  lea     rcx, [rsp+448h+var_2E8]; Uuid
0x18007e80b  call    cs:__imp_UuidCreate
0x18007e811  mov     ebx, eax
0x18007e813  test    eax, eax
0x18007e815  jnz     short loc_18007E7F0
0x18007e817  call    FwpmTransactionBegin0Wrapper
0x18007e81c  mov     ebx, eax
0x18007e81e  test    eax, eax
0x18007e820  jz      short loc_18007E82B
0x18007e822  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18007e829  jmp     short loc_18007E7F7
0x18007e82b  mov     [rsp+448h+var_3F8], 1
0x18007e833  xor     r9d, r9d
0x18007e836  xor     r8d, r8d
0x18007e839  lea     rdx, [rsp+448h+var_2E8]
0x18007e841  mov     rcx, cs:gFwpEngineHandle
0x18007e848  call    cs:__imp_FwpmProviderContextAdd2
0x18007e84e  mov     ebx, eax
0x18007e850  test    eax, eax
0x18007e852  jz      short loc_18007E85D
0x18007e854  lea     rcx, aFwpmproviderco; "FwpmProviderContextAdd0 for MM policy f"...
0x18007e85b  jmp     short loc_18007E7F7
0x18007e85d  movaps  xmm0, xmmword ptr [r15]
0x18007e861  movaps  xmmword ptr [rsp+448h+var_3C8], xmm0
0x18007e869  mov     eax, [r15+10h]
0x18007e86d  mov     [rsp+448h+var_3B8], eax
0x18007e874  lea     r8, [rsp+448h+var_3C8]
0x18007e87c  lea     rdx, [rsp+448h+var_2E8]
0x18007e884  lea     rcx, [rsp+448h+var_368]
0x18007e88c  call    BuildCMMFilter
0x18007e891  mov     ebx, eax
0x18007e893  test    eax, eax
0x18007e895  jz      short loc_18007E8A3
0x18007e897  lea     rcx, aBuildcmmfilter; "BuildCMMFilter for MM filter failed wit"...
0x18007e89e  jmp     loc_18007E7F7
0x18007e8a3  xor     r9d, r9d; id
0x18007e8a6  xor     r8d, r8d; sd
0x18007e8a9  lea     rdx, [rsp+448h+Uuid]; providerContext
0x18007e8b1  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18007e8b8  call    cs:__imp_FwpmProviderContextAdd0
0x18007e8be  mov     ebx, eax
0x18007e8c0  test    eax, eax
0x18007e8c2  jz      short loc_18007E8D0
0x18007e8c4  lea     rcx, aFwpmproviderco_1; "FwpmProviderContextAdd0 for QM policy f"...
0x18007e8cb  jmp     loc_18007E7F7
0x18007e8d0  movaps  xmm0, xmmword ptr [r15]
0x18007e8d4  movaps  xmmword ptr [rsp+448h+var_3C8], xmm0
0x18007e8dc  mov     eax, [r15+10h]
0x18007e8e0  mov     [rsp+448h+var_3B8], eax
0x18007e8e7  mov     dword ptr [rsp+448h+var_428], 1
0x18007e8ef  lea     r8, [rsp+448h+var_3C8]
0x18007e8f7  lea     rdx, [rsp+448h+Uuid]
0x18007e8ff  lea     rcx, [rsp+448h+var_398]
0x18007e907  call    BuildCTxFilter
0x18007e90c  mov     ebx, eax
0x18007e90e  test    eax, eax
0x18007e910  jz      short loc_18007E91E
0x18007e912  lea     rcx, aBuildctxfilter; "BuildCTxFilter for QM filter failed wit"...
0x18007e919  jmp     loc_18007E7F7
0x18007e91e  xor     r9d, r9d
0x18007e921  lea     r8, [rsp+448h+var_3EC]
0x18007e926  lea     rdx, [rsp+448h+var_228]
0x18007e92e  lea     rcx, [rsp+448h+var_398]
0x18007e936  call    AddFilters
0x18007e93b  mov     ebx, eax
0x18007e93d  test    eax, eax
0x18007e93f  jz      short loc_18007E94D
0x18007e941  lea     rcx, aAddfiltersForQ_1; "AddFilters for QM filter failed with 0x"...
0x18007e948  jmp     loc_18007E7F7
0x18007e94d  lea     rdx, [rsp+448h+var_398+8]
0x18007e955  lea     rcx, [rsp+448h+var_398]
0x18007e95d  call    WfpFilterListDestroy
0x18007e962  xorps   xmm0, xmm0
0x18007e965  movups  [rsp+448h+var_398], xmm0
0x18007e96d  movaps  xmm1, xmmword ptr [r15]
  ... truncated ...
```
