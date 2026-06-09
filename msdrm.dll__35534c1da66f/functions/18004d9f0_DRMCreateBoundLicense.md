# DRMCreateBoundLicense

- ea: `0x18004d9f0`
- end: `0x18004dcee`
- name: `DRMCreateBoundLicense`
- size: `766`
- prototype: `HRESULT __stdcall(DRMENVHANDLE hEnv, DRMBOUNDLICENSEPARAMS *pParams, PWSTR wszLicenseChain, DRMHANDLE *phBoundLicense, DRMHANDLE *phErrorLog)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180005fc0`
- `0x180059cec`

## callees

- `0x180001284`
- `0x1800046c8`
- `0x18001f1a8`
- `0x18001f3ac`
- `0x18001fe60`
- `0x180039a5c`
- `0x18004d588`
- `0x18004d9f0`
- `0x18005bdc0`
- `0x18005f010`

## string_xrefs

- `0x18004da1a`: `[msdrm]:+DRMCreateBoundLicense \n`
- `0x18004daa1`: `Created the enabling principal\n`
- `0x18004dcad`: `[msdrm]:-DRMCreateBoundLicense HR=0x%x\n`

## pseudocode

```c
HRESULT __stdcall DRMCreateBoundLicense(
        DRMENVHANDLE hEnv,
        DRMBOUNDLICENSEPARAMS *pParams,
        PWSTR wszLicenseChain,
        DRMHANDLE *phBoundLicense,
        DRMHANDLE *phErrorLog)
{
  CHandlesTable *v9; // rcx
  HRESULT SPHandle; // edi
  int v11; // eax
  CHandlesTable *v12; // rcx
  PWSTR wszIDType; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  PWSTR wszRightsGroup; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  CHandlesTable *v22; // rcx
  int v23; // eax
  void **v24; // rcx
  unsigned __int64 i; // r14
  __int64 v26; // rbx
  HRESULT result; // eax
  bool v28; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-7Dh] BYREF
  unsigned int v30; // [rsp+48h] [rbp-79h] BYREF
  unsigned int v31; // [rsp+4Ch] [rbp-75h] BYREF
  __int128 v32; // [rsp+50h] [rbp-71h] BYREF
  unsigned int v33; // [rsp+60h] [rbp-61h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-59h] BYREF
  __int128 v35; // [rsp+78h] [rbp-49h] BYREF
  __int128 v36; // [rsp+88h] [rbp-39h] BYREF
  __int128 v37; // [rsp+98h] [rbp-29h] BYREF
  char v38; // [rsp+A8h] [rbp-19h] BYREF

  _RTLTRACE("[msdrm]:+DRMCreateBoundLicense \n");
  v33 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  *(_OWORD *)Block = 0;
  if ( !pParams || !wszLicenseChain || !phBoundLicense )
    goto LABEL_25;
  *((_QWORD *)&v32 + 1) = &v38;
  SPHandle = CHandlesTable::GetSPHandle(v9, hEnv, &v33);
  if ( SPHandle < 0 )
    goto LABEL_26;
  if ( !pParams->hEnablingPrincipal )
  {
    _RTLTRACE("Created the enabling principal\n");
    if ( pParams->wszDefaultEnablingPrincipalCredentials )
    {
      *(_QWORD *)&v35 = pParams->wszDefaultEnablingPrincipalCredentials;
      *((_QWORD *)&v35 + 1) = 0x1000000000LL;
      v11 = ((__int64 (__fastcall *)(_QWORD, __int128 *, __int128 *, _QWORD, unsigned int *))g_pfnSPCreateEnablingPrincipal)(
              v33,
              &v35,
              &v32,
              0,
              &v30);
      goto LABEL_9;
    }
LABEL_25:
    SPHandle = -2147024809;
    goto LABEL_26;
  }
  _RTLTRACE("Using existing enabling principal");
  v11 = CHandlesTable::GetSPHandle(v12, pParams->hEnablingPrincipal, &v30);
LABEL_9:
  SPHandle = v11;
  if ( v11 >= 0 )
  {
    if ( pParams->idResource.wszID && (wszIDType = pParams->idResource.wszIDType) != 0 )
    {
      *((_QWORD *)&v37 + 1) = pParams->idResource.wszID;
      v14 = *((_QWORD *)&v32 + 1);
      *(_QWORD *)&v37 = wszIDType;
      v15 = 2LL * (unsigned int)v32;
      *(_QWORD *)(*((_QWORD *)&v32 + 1) + 8 * v15) = &v37;
      *(_DWORD *)(v14 + 8 * v15 + 8) = 16;
      *(_DWORD *)(v14 + 8 * v15 + 12) = 64;
      v16 = v32 + 1;
      LODWORD(v32) = v32 + 1;
    }
    else
    {
      v16 = v32;
    }
    wszRightsGroup = pParams->wszRightsGroup;
    if ( wszRightsGroup )
    {
      v18 = v16;
      v19 = *((_QWORD *)&v32 + 1);
      v18 *= 2;
      *(_QWORD *)(*((_QWORD *)&v32 + 1) + 8 * v18) = wszRightsGroup;
      *(_DWORD *)(v19 + 8 * v18 + 8) = 0;
      *(_DWORD *)(v19 + 8 * v18 + 12) = 66;
      v16 = v32 + 1;
      LODWORD(v32) = v32 + 1;
    }
    if ( pParams->dwFlags )
    {
      v20 = v16;
      v21 = *((_QWORD *)&v32 + 1);
      v20 *= 2;
      *(_QWORD *)(*((_QWORD *)&v32 + 1) + 8 * v20) = &pParams->dwFlags;
      *(_DWORD *)(v21 + 8 * v20 + 8) = 4;
      *(_DWORD *)(v21 + 8 * v20 + 12) = 65;
      LODWORD(v32) = v32 + 1;
    }
    SPHandle = _ParseRequestedRightsToGrants(pParams->wszRightsRequested, (struct _SPAPIBINDLICENSEPARAMS *)Block);
    if ( SPHandle >= 0 )
    {
      *((_QWORD *)&v36 + 1) = 0x1000000000LL;
      *(_QWORD *)&v36 = wszLicenseChain;
      SPHandle = ((__int64 (__fastcall *)(_QWORD, __int128 *, __int128 *, void **, _QWORD, unsigned int *))g_pfnSPBindLicense)(
                   v30,
                   &v36,
                   &v32,
                   Block,
                   0,
                   &v29);
      if ( SPHandle >= 0 )
      {
        SPHandle = IsCLC(wszLicenseChain, &v28);
        if ( SPHandle >= 0 )
        {
          if ( v28 )
            v23 = CHandlesTable::CreateCLCHandle(v22, &v31, v29, wszLicenseChain);
          else
            v23 = CHandlesTable::CreateHandle(v22, &v31, v29);
          SPHandle = v23;
        }
      }
    }
  }
LABEL_26:
  v24 = (void **)Block[1];
  if ( Block[1] )
  {
    for ( i = 0; i < LODWORD(Block[0]); v24 = (void **)Block[1] )
    {
      v26 = 6 * i;
      operator delete(v24[6 * i++ + 1]);
      *((_QWORD *)Block[1] + v26 + 1) = 0;
    }
    operator delete(v24);
    Block[1] = 0;
  }
  if ( SPHandle < 0 )
  {
    if ( v29 )
      ((void (*)(void))g_pfnSPCloseHandle)();
  }
  else
  {
    *phBoundLicense = v31;
  }
  if ( !pParams->hEnablingPrincipal && v30 )
    ((void (*)(void))g_pfnSPCloseHandle)();
  _RTLTRACE("[msdrm]:-DRMCreateBoundLicense HR=0x%x\n", SPHandle);
  result = -2147024774;
  if ( SPHandle != -2147024774 )
  {
    result = -2147168468;
    if ( SPHandle != -1073426388 )
      return SPHandle;
  }
  return result;
}

```

## disassembly

```asm
0x18004d9f0  push    rbp
0x18004d9f2  push    rbx
0x18004d9f3  push    rsi
0x18004d9f4  push    rdi
0x18004d9f5  push    r12
0x18004d9f7  push    r14
0x18004d9f9  push    r15
0x18004d9fb  lea     rbp, [rsp-1Fh]
0x18004da00  sub     rsp, 0E0h
0x18004da07  mov     rax, cs:__security_cookie
0x18004da0e  xor     rax, rsp
0x18004da11  mov     [rbp+4Fh+var_38], rax
0x18004da15  mov     edi, ecx
0x18004da17  mov     r15, r9
0x18004da1a  lea     rcx, aMsdrmDrmcreate_8; "[msdrm]:+DRMCreateBoundLicense \n"
0x18004da21  mov     rbx, r8
0x18004da24  mov     rsi, rdx
0x18004da27  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004da2c  xor     r12d, r12d
0x18004da2f  xorps   xmm0, xmm0
0x18004da32  mov     [rbp+4Fh+var_B0], r12d
0x18004da36  xorps   xmm1, xmm1
0x18004da39  mov     [rbp+4Fh+var_C8], r12d
0x18004da3d  mov     [rbp+4Fh+var_CC], r12d
0x18004da41  mov     [rbp+4Fh+var_C4], r12d
0x18004da45  mov     [rsp+110h+var_D0], r12b
0x18004da4a  movups  [rbp+4Fh+var_C0], xmm0
0x18004da4e  movups  [rbp+4Fh+var_98], xmm1
0x18004da52  movups  [rbp+4Fh+var_88], xmm0
0x18004da56  movups  [rbp+4Fh+var_78], xmm1
0x18004da5a  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x18004da5e  test    rsi, rsi
0x18004da61  jz      loc_18004DC2A
0x18004da67  test    rbx, rbx
0x18004da6a  jz      loc_18004DC2A
0x18004da70  test    r15, r15
0x18004da73  jz      loc_18004DC2A
0x18004da79  lea     rax, [rbp+4Fh+var_68]
0x18004da7d  mov     edx, edi; unsigned int
0x18004da7f  lea     r8, [rbp+4Fh+var_B0]; unsigned int *
0x18004da83  mov     qword ptr [rbp+4Fh+var_C0+8], rax
0x18004da87  call    ?GetSPHandle@CHandlesTable@@QEAAJKPEAK@Z; CHandlesTable::GetSPHandle(ulong,ulong *)
0x18004da8c  mov     edi, eax
0x18004da8e  test    eax, eax
0x18004da90  js      loc_18004DC2F
0x18004da96  lea     r14d, [r12+10h]
0x18004da9b  cmp     [rsi+4], r12d
0x18004da9f  jnz     short loc_18004DAEB
0x18004daa1  lea     rcx, aCreatedTheEnab; "Created the enabling principal\n"
0x18004daa8  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004daad  mov     rax, [rsi+48h]
0x18004dab1  test    rax, rax
0x18004dab4  jz      loc_18004DC2A
0x18004daba  mov     ecx, [rbp+4Fh+var_B0]
0x18004dabd  lea     r8, [rbp+4Fh+var_C0]
0x18004dac1  mov     qword ptr [rbp+4Fh+var_98], rax
0x18004dac5  lea     rdx, [rbp+4Fh+var_98]
0x18004dac9  lea     rax, [rbp+4Fh+var_C8]
0x18004dacd  mov     dword ptr [rbp+4Fh+var_98+8], r12d
0x18004dad1  mov     [rsp+110h+var_F0], rax
0x18004dad6  xor     r9d, r9d
0x18004dad9  mov     rax, cs:?g_pfnSPCreateEnablingPrincipal@@3P6AJKPEAU_SPAPI_TOKEN@@PEAU_SPAPI_SUPPORT_INFO@@PEAUSPAPI_HANDLEGROUP@@PEAK@ZEA; long (*g_pfnSPCreateEnablingPrincipal)(ulong,_SPAPI_TOKEN *,_SPAPI_SUPPORT_INFO *,SPAPI_HANDLEGROUP *,ulong *)
0x18004dae0  mov     dword ptr [rbp+4Fh+var_98+0Ch], r14d
0x18004dae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dae9  jmp     short loc_18004DB03
0x18004daeb  lea     rcx, aUsingExistingE; "Using existing enabling principal"
0x18004daf2  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004daf7  mov     edx, [rsi+4]; unsigned int
0x18004dafa  lea     r8, [rbp+4Fh+var_C8]; unsigned int *
0x18004dafe  call    ?GetSPHandle@CHandlesTable@@QEAAJKPEAK@Z; CHandlesTable::GetSPHandle(ulong,ulong *)
0x18004db03  mov     edi, eax
0x18004db05  test    eax, eax
0x18004db07  js      loc_18004DC2F
0x18004db0d  mov     rax, [rsi+30h]
0x18004db11  test    rax, rax
0x18004db14  jz      short loc_18004DB50
0x18004db16  mov     rcx, [rsi+28h]
0x18004db1a  test    rcx, rcx
0x18004db1d  jz      short loc_18004DB50
0x18004db1f  mov     qword ptr [rbp+4Fh+var_78+8], rax
0x18004db23  lea     rdx, [rbp+4Fh+var_78]
0x18004db27  mov     rax, qword ptr [rbp+4Fh+var_C0+8]
0x18004db2b  mov     qword ptr [rbp+4Fh+var_78], rcx
0x18004db2f  mov     ecx, dword ptr [rbp+4Fh+var_C0]
0x18004db32  add     rcx, rcx
0x18004db35  mov     [rax+rcx*8], rdx
0x18004db39  mov     [rax+rcx*8+8], r14d
0x18004db3e  mov     dword ptr [rax+rcx*8+0Ch], 40h ; '@'
0x18004db46  mov     eax, dword ptr [rbp+4Fh+var_C0]
0x18004db49  inc     eax
0x18004db4b  mov     dword ptr [rbp+4Fh+var_C0], eax
0x18004db4e  jmp     short loc_18004DB53
0x18004db50  mov     eax, dword ptr [rbp+4Fh+var_C0]
0x18004db53  mov     rdx, [rsi+18h]
0x18004db57  test    rdx, rdx
0x18004db5a  jz      short loc_18004DB7E
0x18004db5c  mov     ecx, eax
0x18004db5e  mov     rax, qword ptr [rbp+4Fh+var_C0+8]
0x18004db62  add     rcx, rcx
0x18004db65  mov     [rax+rcx*8], rdx
0x18004db69  mov     [rax+rcx*8+8], r12d
0x18004db6e  mov     dword ptr [rax+rcx*8+0Ch], 42h ; 'B'
0x18004db76  mov     eax, dword ptr [rbp+4Fh+var_C0]
0x18004db79  inc     eax
0x18004db7b  mov     dword ptr [rbp+4Fh+var_C0], eax
0x18004db7e  lea     rdx, [rsi+50h]
0x18004db82  cmp     [rdx], r12d
0x18004db85  jz      short loc_18004DBA7
0x18004db87  mov     ecx, eax
0x18004db89  mov     rax, qword ptr [rbp+4Fh+var_C0+8]
0x18004db8d  add     rcx, rcx
0x18004db90  mov     [rax+rcx*8], rdx
0x18004db94  mov     dword ptr [rax+rcx*8+8], 4
0x18004db9c  mov     dword ptr [rax+rcx*8+0Ch], 41h ; 'A'
0x18004dba4  inc     dword ptr [rbp+4Fh+var_C0]
0x18004dba7  mov     rcx, [rsi+10h]; unsigned __int16 *
0x18004dbab  lea     rdx, [rbp+4Fh+Block]; struct _SPAPIBINDLICENSEPARAMS *
0x18004dbaf  call    ?_ParseRequestedRightsToGrants@@YAJPEBGAEAU_SPAPIBINDLICENSEPARAMS@@@Z; _ParseRequestedRightsToGrants(ushort const *,_SPAPIBINDLICENSEPARAMS &)
0x18004dbb4  mov     edi, eax
0x18004dbb6  test    eax, eax
0x18004dbb8  js      short loc_18004DC2F
0x18004dbba  mov     ecx, [rbp+4Fh+var_C8]
0x18004dbbd  lea     rax, [rbp+4Fh+var_CC]
0x18004dbc1  mov     [rsp+110h+var_E8], rax
0x18004dbc6  lea     r9, [rbp+4Fh+Block]
0x18004dbca  mov     rax, cs:?g_pfnSPBindLicense@@3P6AJKPEAU_SPAPI_TOKEN@@PEAU_SPAPI_SUPPORT_INFO@@PEAU_SPAPIBINDLICENSEPARAMS@@PEAUSPAPI_HANDLEGROUP@@PEAK@ZEA; long (*g_pfnSPBindLicense)(ulong,_SPAPI_TOKEN *,_SPAPI_SUPPORT_INFO *,_SPAPIBINDLICENSEPARAMS *,SPAPI_HANDLEGROUP *,ulong *)
0x18004dbd1  lea     r8, [rbp+4Fh+var_C0]
0x18004dbd5  lea     rdx, [rbp+4Fh+var_88]
0x18004dbd9  mov     dword ptr [rbp+4Fh+var_88+8], r12d
0x18004dbdd  mov     qword ptr [rbp+4Fh+var_88], rbx
0x18004dbe1  mov     dword ptr [rbp+4Fh+var_88+0Ch], r14d
0x18004dbe5  mov     [rsp+110h+var_F0], r12
0x18004dbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbef  mov     edi, eax
0x18004dbf1  test    eax, eax
0x18004dbf3  js      short loc_18004DC2F
0x18004dbf5  lea     rdx, [rsp+110h+var_D0]; bool *
0x18004dbfa  mov     rcx, rbx; wszChain
0x18004dbfd  call    ?IsCLC@@YAJPEBGPEA_N@Z; IsCLC(ushort const *,bool *)
0x18004dc02  mov     edi, eax
0x18004dc04  test    eax, eax
0x18004dc06  js      short loc_18004DC2F
0x18004dc08  lea     rdx, [rbp+4Fh+var_C4]; unsigned int *
0x18004dc0c  mov     r8d, [rbp+4Fh+var_CC]; unsigned int
0x18004dc10  cmp     [rsp+110h+var_D0], r12b
0x18004dc15  jz      short loc_18004DC23
0x18004dc17  mov     r9, rbx; unsigned __int16 *
0x18004dc1a  call    ?CreateCLCHandle@CHandlesTable@@QEAAJPEAKKPEBG@Z; CHandlesTable::CreateCLCHandle(ulong *,ulong,ushort const *)
0x18004dc1f  mov     edi, eax
0x18004dc21  jmp     short loc_18004DC2F
0x18004dc23  call    ?CreateHandle@CHandlesTable@@QEAAJPEAKK@Z; CHandlesTable::CreateHandle(ulong *,ulong)
0x18004dc28  jmp     short loc_18004DC1F
0x18004dc2a  mov     edi, 80070057h
0x18004dc2f  mov     rcx, [rbp+4Fh+Block+8]
0x18004dc33  test    rcx, rcx
0x18004dc36  jz      short loc_18004DC73
0x18004dc38  mov     r14, r12
0x18004dc3b  cmp     dword ptr [rbp+4Fh+Block], r12d
0x18004dc3f  jbe     short loc_18004DC6A
0x18004dc41  lea     rbx, [r14+r14*2]
0x18004dc45  add     rbx, rbx
0x18004dc48  mov     rcx, [rcx+rbx*8+8]; Block
0x18004dc4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004dc52  mov     rax, [rbp+4Fh+Block+8]
0x18004dc56  inc     r14
0x18004dc59  mov     [rax+rbx*8+8], r12
0x18004dc5e  mov     eax, dword ptr [rbp+4Fh+Block]
0x18004dc61  mov     rcx, [rbp+4Fh+Block+8]; Block
0x18004dc65  cmp     r14, rax
0x18004dc68  jb      short loc_18004DC41
0x18004dc6a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004dc6f  mov     [rbp+4Fh+Block+8], r12
0x18004dc73  test    edi, edi
0x18004dc75  js      short loc_18004DC7F
0x18004dc77  mov     eax, [rbp+4Fh+var_C4]
0x18004dc7a  mov     [r15], eax
0x18004dc7d  jmp     short loc_18004DC92
0x18004dc7f  mov     ecx, [rbp+4Fh+var_CC]
0x18004dc82  test    ecx, ecx
0x18004dc84  jz      short loc_18004DC92
0x18004dc86  mov     rax, cs:?g_pfnSPCloseHandle@@3P6AJK@ZEA; long (*g_pfnSPCloseHandle)(ulong)
0x18004dc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc92  cmp     [rsi+4], r12d
0x18004dc96  jnz     short loc_18004DCAB
0x18004dc98  mov     ecx, [rbp+4Fh+var_C8]
0x18004dc9b  test    ecx, ecx
0x18004dc9d  jz      short loc_18004DCAB
0x18004dc9f  mov     rax, cs:?g_pfnSPCloseHandle@@3P6AJK@ZEA; long (*g_pfnSPCloseHandle)(ulong)
0x18004dca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcab  mov     edx, edi
0x18004dcad  lea     rcx, aMsdrmDrmcreate_2; "[msdrm]:-DRMCreateBoundLicense HR=0x%x"...
0x18004dcb4  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004dcb9  mov     eax, 8007007Ah
0x18004dcbe  cmp     edi, eax
0x18004dcc0  jz      short loc_18004DCD0
0x18004dcc2  cmp     edi, 0C004D02Ch
0x18004dcc8  mov     eax, 8004CF2Ch
0x18004dccd  cmovnz  eax, edi
0x18004dcd0  mov     rcx, [rbp+4Fh+var_38]
0x18004dcd4  xor     rcx, rsp; StackCookie
0x18004dcd7  call    __security_check_cookie
0x18004dcdc  add     rsp, 0E0h
0x18004dce3  pop     r15
0x18004dce5  pop     r14
0x18004dce7  pop     r12
0x18004dce9  pop     rdi
0x18004dcea  pop     rsi
0x18004dceb  pop     rbx
0x18004dcec  pop     rbp
0x18004dced  retn
```
