# DwAddClientIpSecFilter

- ea: `0x180083654`
- end: `0x180083de2`
- name: `DwAddClientIpSecFilter`
- size: `1934`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041670`

## callees

- `0x1800828f8`
- `0x180082a6c`
- `0x180082b7c`
- `0x180082cb4`
- `0x1800830ec`
- `0x180083584`
- `0x180083654`
- `0x180085a90`
- `0x180085b20`
- `0x180085cb4`
- `0x180085e24`
- `0x180085f44`
- `0x180086adc`
- `0x1800871ac`
- `0x180091790`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18008390c`
- `KERNEL32!LocalFree` at `0x18008390c`
- `KERNEL32!GetLastError` at `0x18008378b`
- `KERNEL32!GetLastError` at `0x180083a12`
- `KERNEL32!GetLastError` at `0x18008378b`
- `KERNEL32!GetLastError` at `0x180083a12`
- `KERNEL32!LocalAlloc` at `0x180083766`
- `KERNEL32!LocalAlloc` at `0x1800839fe`
- `KERNEL32!LocalAlloc` at `0x180083766`
- `KERNEL32!LocalAlloc` at `0x1800839fe`
- `RPCRT4!UuidCreate` at `0x180083baa`
- `RPCRT4!UuidCreate` at `0x180083bd7`
- `RPCRT4!UuidCreate` at `0x180083baa`
- `RPCRT4!UuidCreate` at `0x180083bd7`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180083896`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180083896`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x180083c90`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x180083c90`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800838b5`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800838b5`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x180083c1a`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x180083c1a`

## string_xrefs

- `0x1800837d0`: `DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.`
- `0x1800837e6`: `DwAddClientIpSecFilter: Filter already exists.`
- `0x180083bbc`: `UuidCreate failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DwAddClientIpSecFilter(__int128 *a1, unsigned int a2, int a3, __int64 a4)
{
  DWORD LastError; // ebx
  _QWORD *v7; // rsi
  HLOCAL v8; // r13
  __int64 v9; // rcx
  DWORD v10; // eax
  __int64 ServerNode; // rax
  __int64 v12; // r13
  int v13; // ecx
  int v14; // eax
  int v16; // r14d
  HLOCAL v17; // rbx
  const CHAR *v18; // rcx
  int v19; // r9d
  int v20; // r9d
  int v21; // [rsp+20h] [rbp-478h]
  BYTE Src; // [rsp+28h] [rbp-470h]
  int v23; // [rsp+50h] [rbp-448h]
  int v24; // [rsp+58h] [rbp-440h] BYREF
  int v25; // [rsp+5Ch] [rbp-43Ch] BYREF
  HLOCAL v26; // [rsp+60h] [rbp-438h] BYREF
  int v27; // [rsp+68h] [rbp-430h]
  int v28; // [rsp+6Ch] [rbp-42Ch] BYREF
  int v29; // [rsp+70h] [rbp-428h] BYREF
  int v30; // [rsp+78h] [rbp-420h]
  int v31; // [rsp+7Ch] [rbp-41Ch] BYREF
  int v32; // [rsp+80h] [rbp-418h] BYREF
  _DWORD *v33; // [rsp+88h] [rbp-410h] BYREF
  __int128 v34; // [rsp+90h] [rbp-408h] BYREF
  unsigned int v35; // [rsp+A8h] [rbp-3F0h]
  __int64 v36; // [rsp+B0h] [rbp-3E8h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-3E0h]
  __int128 v38; // [rsp+C0h] [rbp-3D8h] BYREF
  __int128 v39; // [rsp+D0h] [rbp-3C8h] BYREF
  int v40; // [rsp+E0h] [rbp-3B8h]
  int v41[4]; // [rsp+F0h] [rbp-3A8h] BYREF
  int v42; // [rsp+100h] [rbp-398h]
  __int128 v43; // [rsp+110h] [rbp-388h] BYREF
  __int128 v44; // [rsp+120h] [rbp-378h]
  __int128 v45; // [rsp+130h] [rbp-368h]
  __int128 *v46; // [rsp+150h] [rbp-348h]
  __int128 v47; // [rsp+160h] [rbp-338h] BYREF
  int v48; // [rsp+170h] [rbp-328h]
  _OWORD v49[2]; // [rsp+188h] [rbp-310h] BYREF
  int v50; // [rsp+1A8h] [rbp-2F0h]
  UUID v51; // [rsp+1B0h] [rbp-2E8h] BYREF
  const wchar_t *v52; // [rsp+1C0h] [rbp-2D8h]
  int v53; // [rsp+1F0h] [rbp-2A8h]
  __int128 *v54; // [rsp+1F8h] [rbp-2A0h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+210h] [rbp-288h] BYREF
  _BYTE v56[480]; // [rsp+270h] [rbp-228h] BYREF

  v46 = a1;
  v35 = a2;
  LastError = 87;
  v30 = 87;
  memset(v49, 0, sizeof(v49));
  v50 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  memset_0(&v51, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v7 = 0;
  v33 = 0;
  v8 = 0;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  v32 = 0;
  v31 = 0;
  v27 = 0;
  v25 = 0;
  v23 = 0;
  v36 = 0;
  RasIpsecTrace("DwAddClientIpSecFilter.");
  v38 = 0;
  v34 = 0;
  hMem = LocalAlloc(0x40u, 0x118u);
  if ( hMem )
  {
    v39 = *a1;
    v40 = *((_DWORD *)a1 + 4);
    ServerNode = FindServerNode(v9, &v39);
    v12 = ServerNode;
    if ( ServerNode )
    {
      if ( a2 == *(_DWORD *)(ServerNode + 76) )
      {
        RasIpsecTrace("DwAddClientIpSecFilter: Filter already exists.");
        ++*(_DWORD *)(v12 + 52);
        LastError = 0;
      }
      else
      {
        RasIpsecTrace("DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.");
      }
      v8 = v26;
      goto LABEL_13;
    }
    v24 = 0;
    if ( a2 >= 2 )
    {
      v13 = a2 - 2;
      if ( a2 - 2 >= 2 )
      {
        v8 = v26;
LABEL_11:
        *(_OWORD *)v41 = *a1;
        v42 = *((_DWORD *)a1 + 4);
        gpIpSecSrvList = AddNodeToServerList(v13, a2, (int)v41, (int)&v51, (__int64)&Uuid, v56, v25, v36);
        v10 = FwpmTransactionCommit0(gFwpEngineHandle);
        goto LABEL_12;
      }
    }
    if ( a3 )
    {
      v7 = LocalAlloc(0x40u, 0x40u);
      if ( !v7 )
      {
        LastError = GetLastError();
        goto LABEL_37;
      }
      *(_DWORD *)v7 = 0;
      v7[2] = a4;
      *((_DWORD *)v7 + 2) = a3;
      v16 = 1;
    }
    else
    {
      LastError = GenerateCertificatesList(0, &v33, &v28, &v24);
      v30 = LastError;
      v16 = v28;
      if ( LastError || !v28 || v24 )
      {
        RasIpsecTrace("Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
        if ( !v16 || v24 )
          LastError = 766;
        v7 = v33;
        goto LABEL_37;
      }
      v7 = v33;
      if ( v33 )
        v33[14] |= 2u;
    }
    LastError = BuildIpsecOffers(a2, &v26, &v29);
    if ( !LastError )
    {
      v8 = v26;
      BuildQMPolicy((unsigned int)&Uuid, (unsigned int)v49, a2, (_DWORD)v26, v29, *(_DWORD *)&g_dwIpsecUdpEncapsulation);
      v17 = hMem;
      BuildMMOffers((int)hMem, (int)&v32, (int)&v31, 0, v21, Src, 0);
      LODWORD(v44) = 0;
      v45 = (unsigned int)v31;
      LODWORD(v43) = 28800;
      *((_QWORD *)&v44 + 1) = v17;
      DWORD1(v44) = v32;
      *((_QWORD *)&v43 + 1) = v7;
      DWORD1(v43) = v16;
      memset_0(&v51, 0, 0x58u);
      v53 = 5;
      v54 = &v43;
      v52 = L"L2TP Main Mode Policy";
      LastError = UuidCreate(&Uuid.providerContextKey);
      if ( LastError || (LastError = UuidCreate(&v51)) != 0 )
      {
        v18 = "UuidCreate failed with 0x%x";
      }
      else
      {
        LastError = FwpmTransactionBegin0Wrapper();
        if ( LastError )
        {
          v18 = "FwpmTransactionBegin0 failed with 0x%x";
        }
        else
        {
          v23 = 1;
          LastError = FwpmProviderContextAdd2(gFwpEngineHandle, &v51, 0, 0);
          if ( LastError )
          {
            v18 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
          }
          else
          {
            v39 = *a1;
            v40 = *((_DWORD *)a1 + 4);
            LastError = BuildCMMFilter(&v38, &v51, &v39);
            if ( LastError )
            {
              v18 = "BuildCMMFilter for MM filter failed with 0x%x";
            }
            else
            {
              LastError = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
              if ( LastError )
              {
                v18 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
              }
              else
              {
                v47 = *a1;
                v48 = *((_DWORD *)a1 + 4);
                LastError = BuildCTxFilter((unsigned int)&v34, (unsigned int)&Uuid, (unsigned int)&v47, v19, 1);
                if ( LastError )
                {
                  v18 = "BuildCTxFilter for QM filter failed with 0x%x";
                }
                else
                {
                  LastError = AddFilters(&v34, v56, &v25, 0);
                  if ( LastError
                    || (WfpFilterListDestroy(&v34, (char *)&v34 + 8),
                        v34 = 0,
                        *(_OWORD *)v41 = *a1,
                        v42 = *((_DWORD *)a1 + 4),
                        BuildCTxFilter((unsigned int)&v34, (unsigned int)&Uuid, (unsigned int)v41, v20, 0),
                        (LastError = AddFilters(&v34, v56, &v25, &v36)) != 0) )
                  {
                    v18 = "AddFilters for QM filter failed with 0x%x";
                  }
                  else
                  {
                    LastError = AddFilters(&v38, v56, &v25, 0);
                    if ( !LastError )
                      goto LABEL_11;
                    v18 = "AddFilters for MM filter failed with 0x%x";
                  }
                }
              }
            }
          }
        }
      }
      RasIpsecTrace(v18);
LABEL_38:
      v14 = v23;
      goto LABEL_14;
    }
    RasIpsecTrace("BuildIpsecOffers for ipsec proposals failed with 0x%x");
LABEL_37:
    v8 = v26;
    goto LABEL_38;
  }
  RasIpsecTrace("DwAddclientipsecfilter: failed to alloc");
  v10 = GetLastError();
LABEL_12:
  LastError = v10;
LABEL_13:
  v14 = 0;
LABEL_14:
  if ( LastError && v14 )
    FwpmTransactionAbort0(gFwpEngineHandle);
  WfpFilterListDestroy(&v34, (char *)&v34 + 8);
  WfpFilterListDestroy(&v38, (char *)&v38 + 8);
  if ( v8 )
    FreeIpsecOffers(v8);
  if ( hMem )
    LocalFree(hMem);
  if ( v7 )
    FreeAuthInfoList(v7);
  RasIpsecTrace("DwAddClientIpSecFilter: rc=0x%x");
  return LastError;
}

```

## disassembly

```asm
0x180083654  mov     [rsp+arg_18], r9
0x180083659  mov     [rsp+arg_10], r8d
0x18008365e  push    rbx
0x18008365f  push    rsi
0x180083660  push    rdi
0x180083661  push    r12
0x180083663  push    r13
0x180083665  push    r14
0x180083667  push    r15
0x180083669  sub     rsp, 460h
0x180083670  mov     rax, cs:__security_cookie
0x180083677  xor     rax, rsp
0x18008367a  mov     [rsp+498h+var_48], rax
0x180083682  mov     r12d, edx
0x180083685  mov     r15, rcx
0x180083688  mov     [rsp+498h+var_348], rcx
0x180083690  mov     [rsp+498h+var_3F0], edx
0x180083697  mov     ebx, 57h ; 'W'
0x18008369c  mov     [rsp+498h+var_420], ebx
0x1800836a0  xor     eax, eax
0x1800836a2  xorps   xmm0, xmm0
0x1800836a5  movups  [rsp+498h+var_310], xmm0
0x1800836ad  movups  [rsp+498h+var_300], xmm0
0x1800836b5  mov     [rsp+498h+var_2F0], eax
0x1800836bc  xorps   xmm1, xmm1
0x1800836bf  movups  [rsp+498h+var_388], xmm1
0x1800836c7  movups  [rsp+498h+var_378], xmm1
0x1800836cf  movups  [rsp+498h+var_368], xmm1
0x1800836d7  lea     edi, [rbx+1]
0x1800836da  mov     r8d, edi; Size
0x1800836dd  xor     edx, edx; Val
0x1800836df  lea     rcx, [rsp+498h+var_2E8]; void *
0x1800836e7  call    memset_0
0x1800836ec  mov     r8d, edi; Size
0x1800836ef  xor     edx, edx; Val
0x1800836f1  lea     rcx, [rsp+498h+Uuid]; void *
0x1800836f9  call    memset_0
0x1800836fe  xor     edi, edi
0x180083700  mov     esi, edi
0x180083702  mov     [rsp+498h+var_410], rdi
0x18008370a  mov     r13d, edi
0x18008370d  mov     [rsp+498h+var_438], rdi
0x180083712  mov     r14d, edi
0x180083715  mov     [rsp+498h+var_42C], edi
0x180083719  mov     [rsp+498h+var_428], edi
0x18008371d  mov     [rsp+498h+var_418], edi
0x180083724  mov     [rsp+498h+var_41C], edi
0x180083728  mov     [rsp+498h+var_430], edi
0x18008372c  mov     [rsp+498h+var_43C], edi
0x180083730  mov     [rsp+498h+var_448], edi
0x180083734  mov     [rsp+498h+var_3E8], rdi
0x18008373c  lea     rcx, aDwaddclientips_1; "DwAddClientIpSecFilter."
0x180083743  call    RasIpsecTrace
0x180083748  xorps   xmm0, xmm0
0x18008374b  movups  [rsp+498h+var_3D8], xmm0
0x180083753  xorps   xmm1, xmm1
0x180083756  movups  [rsp+498h+var_408], xmm1
0x18008375e  mov     edx, 118h; uBytes
0x180083763  lea     ecx, [rbx-17h]; uFlags
0x180083766  call    cs:__imp_LocalAlloc
0x18008376d  nop     dword ptr [rax+rax+00h]
0x180083772  mov     [rsp+498h+hMem], rax
0x18008377a  test    rax, rax
0x18008377d  jnz     short loc_18008379C
0x18008377f  lea     rcx, aDwaddclientips; "DwAddclientipsecfilter: failed to alloc"
0x180083786  call    RasIpsecTrace
0x18008378b  call    cs:__imp_GetLastError
0x180083792  nop     dword ptr [rax+rax+00h]
0x180083797  jmp     loc_1800838A2
0x18008379c  movaps  xmm0, xmmword ptr [r15]
0x1800837a0  movaps  [rsp+498h+var_3C8], xmm0
0x1800837a8  mov     eax, [r15+10h]
0x1800837ac  mov     [rsp+498h+var_3B8], eax
0x1800837b3  lea     rdx, [rsp+498h+var_3C8]
0x1800837bb  call    FindServerNode
0x1800837c0  mov     r13, rax
0x1800837c3  test    rax, rax
0x1800837c6  jz      short loc_1800837FA
0x1800837c8  mov     edx, [rax+4Ch]
0x1800837cb  cmp     r12d, edx
0x1800837ce  jz      short loc_1800837E6
0x1800837d0  lea     rcx, aDwaddclientips_2; "DwAddClientIpSecFilter: Already a filte"...
0x1800837d7  call    RasIpsecTrace
0x1800837dc  mov     r13, [rsp+498h+var_438]
0x1800837e1  jmp     loc_1800838A4
0x1800837e6  lea     rcx, aDwaddclientips_0; "DwAddClientIpSecFilter: Filter already "...
0x1800837ed  call    RasIpsecTrace
0x1800837f2  inc     dword ptr [r13+34h]
0x1800837f6  mov     ebx, edi
0x1800837f8  jmp     short loc_1800837DC
0x1800837fa  mov     [rsp+498h+var_440], edi
0x1800837fe  mov     ecx, r12d
0x180083801  test    r12d, r12d
0x180083804  jz      loc_180083962
0x18008380a  sub     ecx, 1
0x18008380d  jz      loc_180083962
0x180083813  sub     ecx, 1; int
0x180083816  jz      loc_180083962
0x18008381c  cmp     ecx, 1
0x18008381f  jz      loc_180083962
0x180083825  mov     r13, [rsp+498h+var_438]
0x18008382a  movaps  xmm0, xmmword ptr [r15]
0x18008382e  movaps  xmmword ptr [rsp+498h+var_3A8], xmm0
0x180083836  mov     eax, [r15+10h]
0x18008383a  mov     [rsp+498h+var_398], eax
0x180083841  mov     rax, [rsp+498h+var_3E8]
0x180083849  mov     [rsp+498h+var_460], rax; __int64
0x18008384e  mov     eax, [rsp+498h+var_43C]
0x180083852  mov     dword ptr [rsp+498h+var_468], eax; int
0x180083856  lea     rax, [rsp+498h+var_228]
0x18008385e  mov     [rsp+498h+Src], rax; Src
0x180083863  lea     rax, [rsp+498h+Uuid]
0x18008386b  mov     [rsp+498h+var_478], rax; __int64
0x180083870  lea     r9, [rsp+498h+var_2E8]; int
0x180083878  lea     r8, [rsp+498h+var_3A8]; int
0x180083880  mov     edx, r12d; int
0x180083883  call    AddNodeToServerList
0x180083888  mov     cs:gpIpSecSrvList, rax
0x18008388f  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180083896  call    cs:__imp_FwpmTransactionCommit0
0x18008389d  nop     dword ptr [rax+rax+00h]
0x1800838a2  mov     ebx, eax
0x1800838a4  mov     eax, edi
0x1800838a6  test    ebx, ebx
0x1800838a8  jz      short loc_1800838C1
0x1800838aa  test    eax, eax
0x1800838ac  jz      short loc_1800838C1
0x1800838ae  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x1800838b5  call    cs:__imp_FwpmTransactionAbort0
0x1800838bc  nop     dword ptr [rax+rax+00h]
0x1800838c1  lea     rdx, [rsp+498h+var_408+8]
0x1800838c9  lea     rcx, [rsp+498h+var_408]
0x1800838d1  call    WfpFilterListDestroy
0x1800838d6  lea     rdx, [rsp+498h+var_3D8+8]
0x1800838de  lea     rcx, [rsp+498h+var_3D8]
0x1800838e6  call    WfpFilterListDestroy
0x1800838eb  test    r13, r13
0x1800838ee  jz      short loc_1800838FC
0x1800838f0  mov     edx, [rsp+498h+var_428]
0x1800838f4  mov     rcx, r13; hMem
0x1800838f7  call    FreeIpsecOffers
0x1800838fc  mov     rax, [rsp+498h+hMem]
0x180083904  test    rax, rax
0x180083907  jz      short loc_180083918
0x180083909  mov     rcx, rax; hMem
0x18008390c  call    cs:__imp_LocalFree
0x180083913  nop     dword ptr [rax+rax+00h]
0x180083918  test    rsi, rsi
0x18008391b  jz      short loc_18008392E
0x18008391d  mov     r8d, 1
0x180083923  mov     edx, r14d
0x180083926  mov     rcx, rsi; hMem
0x180083929  call    FreeAuthInfoList
0x18008392e  mov     edx, ebx
0x180083930  lea     rcx, aDwaddclientips_3; "DwAddClientIpSecFilter: rc=0x%x"
0x180083937  call    RasIpsecTrace
0x18008393c  mov     eax, ebx
0x18008393e  mov     rcx, [rsp+498h+var_48]
0x180083946  xor     rcx, rsp; StackCookie
0x180083949  call    __security_check_cookie
0x18008394e  add     rsp, 460h
0x180083955  pop     r15
0x180083957  pop     r14
0x180083959  pop     r13
0x18008395b  pop     r12
0x18008395d  pop     rdi
0x18008395e  pop     rsi
0x18008395f  pop     rbx
0x180083960  retn
0x180083962  mov     r13d, [rsp+498h+arg_10]
0x18008396a  test    r13d, r13d
0x18008396d  jnz     loc_1800839F4
0x180083973  lea     r9, [rsp+498h+var_440]
0x180083978  lea     r8, [rsp+498h+var_42C]
0x18008397d  lea     rdx, [rsp+498h+var_410]
0x180083985  xor     ecx, ecx
0x180083987  call    GenerateCertificatesList
0x18008398c  mov     ebx, eax
0x18008398e  mov     [rsp+498h+var_420], eax
0x180083992  jmp     short loc_1800839C6
0x180083994  mov     edx, [rsp+498h+var_430]
0x180083998  lea     rcx, aGeneratecertif; "GenerateCertificatesList raised excepti"...
0x18008399f  call    RasIpsecTrace
0x1800839a4  xor     edi, edi
0x1800839a6  mov     ebx, [rsp+498h+var_420]
0x1800839aa  mov     [rsp+498h+var_448], edi
0x1800839ae  mov     r15, [rsp+498h+var_348]
0x1800839b6  mov     r12d, [rsp+498h+var_3F0]
0x1800839be  mov     r13d, [rsp+498h+arg_10]
0x1800839c6  mov     r14d, [rsp+498h+var_42C]
0x1800839cb  test    ebx, ebx
0x1800839cd  jnz     short loc_180083A22
0x1800839cf  test    r14d, r14d
0x1800839d2  jz      short loc_180083A22
0x1800839d4  cmp     [rsp+498h+var_440], edi
0x1800839d8  jnz     short loc_180083A22
0x1800839da  mov     rsi, [rsp+498h+var_410]
0x1800839e2  test    rsi, rsi
0x1800839e5  jz      short loc_1800839EB
0x1800839e7  or      dword ptr [rsi+38h], 2
0x1800839eb  test    r13d, r13d
0x1800839ee  jz      loc_180083A80
0x1800839f4  test    rsi, rsi
0x1800839f7  jnz     short loc_180083A5E
0x1800839f9  lea     edx, [rsi+40h]; uBytes
0x1800839fc  mov     ecx, edx; uFlags
0x1800839fe  call    cs:__imp_LocalAlloc
0x180083a05  nop     dword ptr [rax+rax+00h]
0x180083a0a  mov     rsi, rax
0x180083a0d  test    rax, rax
0x180083a10  jnz     short loc_180083A5E
0x180083a12  call    cs:__imp_GetLastError
0x180083a19  nop     dword ptr [rax+rax+00h]
0x180083a1e  mov     ebx, eax
0x180083a20  jmp     short loc_180083A50
0x180083a22  mov     r9d, [rsp+498h+var_440]
0x180083a27  mov     r8d, r14d
0x180083a2a  mov     edx, ebx
0x180083a2c  lea     rcx, aFailedToGenera; "Failed to generate certificate list. rc"...
0x180083a33  call    RasIpsecTrace
0x180083a38  test    r14d, r14d
0x180083a3b  jz      short loc_180083A43
0x180083a3d  cmp     [rsp+498h+var_440], edi
0x180083a41  jz      short loc_180083A48
0x180083a43  mov     ebx, 2FEh
0x180083a48  mov     rsi, [rsp+498h+var_410]
0x180083a50  mov     r13, [rsp+498h+var_438]
0x180083a55  mov     eax, [rsp+498h+var_448]
0x180083a59  jmp     loc_1800838A6
0x180083a5e  mov     eax, r14d
0x180083a61  lea     rcx, [rax+rax*4]
0x180083a65  add     rcx, rcx
0x180083a68  mov     [rsi+rcx*8], edi
0x180083a6b  mov     rax, [rsp+498h+arg_18]
0x180083a73  mov     [rsi+rcx*8+10h], rax
0x180083a78  mov     [rsi+rcx*8+8], r13d
0x180083a7d  inc     r14d
0x180083a80  mov     dword ptr [rsp+498h+Src], 0E10h
0x180083a88  mov     dword ptr [rsp+498h+var_478], 3D090h
0x180083a90  lea     r8, [rsp+498h+var_428]
0x180083a95  lea     rdx, [rsp+498h+var_438]
0x180083a9a  mov     ecx, r12d
0x180083a9d  call    BuildIpsecOffers
0x180083aa2  mov     ebx, eax
0x180083aa4  test    eax, eax
0x180083aa6  jz      short loc_180083AB8
0x180083aa8  mov     edx, eax
0x180083aaa  lea     rcx, aBuildipsecoffe; "BuildIpsecOffers for ipsec proposals fa"...
0x180083ab1  call    RasIpsecTrace
0x180083ab6  jmp     short loc_180083A50
0x180083ab8  mov     eax, cs:g_dwIpsecUdpEncapsulation
0x180083abe  mov     dword ptr [rsp+498h+Src], eax; Data
0x180083ac2  mov     eax, [rsp+498h+var_428]
0x180083ac6  mov     dword ptr [rsp+498h+var_478], eax; int
0x180083aca  mov     r13, [rsp+498h+var_438]
0x180083acf  mov     r9, r13
0x180083ad2  mov     r8d, r12d
0x180083ad5  lea     rdx, [rsp+498h+var_310]
0x180083add  lea     rcx, [rsp+498h+Uuid]
0x180083ae5  call    BuildQMPolicy
0x180083aea  mov     [rsp+498h+var_468], rdi; __int64
0x180083aef  xor     r9d, r9d; int
0x180083af2  lea     r8, [rsp+498h+var_41C]; int
0x180083af7  lea     rdx, [rsp+498h+var_418]; int
0x180083aff  mov     rbx, [rsp+498h+hMem]
0x180083b07  mov     rcx, rbx; int
0x180083b0a  call    BuildMMOffers
0x180083b0f  mov     dword ptr [rsp+498h+var_378], edi
0x180083b16  mov     dword ptr [rsp+498h+var_368+4], edi
0x180083b1d  mov     qword ptr [rsp+498h+var_368+8], 708h
0x180083b29  mov     eax, [rsp+498h+var_41C]
0x180083b2d  mov     dword ptr [rsp+498h+var_368], eax
0x180083b34  mov     dword ptr [rsp+498h+var_388], 7080h
0x180083b3f  mov     qword ptr [rsp+498h+var_378+8], rbx
0x180083b47  mov     eax, [rsp+498h+var_418]
0x180083b4e  mov     dword ptr [rsp+498h+var_378+4], eax
0x180083b55  mov     qword ptr [rsp+498h+var_388+8], rsi
0x180083b5d  mov     dword ptr [rsp+498h+var_388+4], r14d
0x180083b65  xor     edx, edx; Val
0x180083b67  lea     r8d, [rdx+58h]; Size
0x180083b6b  lea     rcx, [rsp+498h+var_2E8]; void *
0x180083b73  call    memset_0
0x180083b78  mov     [rsp+498h+var_2A8], 5
0x180083b83  lea     rax, [rsp+498h+var_388]
0x180083b8b  mov     [rsp+498h+var_2A0], rax
0x180083b93  lea     rax, aL2tpMainModePo; "L2TP Main Mode Policy"
0x180083b9a  mov     [rsp+498h+var_2D8], rax
0x180083ba2  lea     rcx, [rsp+498h+Uuid]; Uuid
0x180083baa  call    cs:__imp_UuidCreate
0x180083bb1  nop     dword ptr [rax+rax+00h]
0x180083bb6  mov     ebx, eax
0x180083bb8  test    eax, eax
0x180083bba  jz      short loc_180083BCF
0x180083bbc  lea     rcx, aUuidcreateFail; "UuidCreate failed with 0x%x"
0x180083bc3  mov     edx, eax
0x180083bc5  call    RasIpsecTrace
0x180083bca  jmp     loc_180083A55
0x180083bcf  lea     rcx, [rsp+498h+var_2E8]; Uuid
0x180083bd7  call    cs:__imp_UuidCreate
0x180083bde  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
