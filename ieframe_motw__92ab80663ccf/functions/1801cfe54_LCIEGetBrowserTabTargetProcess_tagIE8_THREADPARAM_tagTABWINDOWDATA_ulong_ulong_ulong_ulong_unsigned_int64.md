# LCIEGetBrowserTabTargetProcess(tagIE8_THREADPARAM *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *,ulong *,unsigned __int64 *)

- ea: `0x1801cfe54`
- end: `0x1801d05c0`
- name: `?LCIEGetBrowserTabTargetProcess@@YAJPEAUtagIE8_THREADPARAM@@PEAUtagTABWINDOWDATA@@PEAK222PEA_K@Z`
- size: `1900`
- prototype: `int(struct tagIE8_THREADPARAM *, struct tagTABWINDOWDATA *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180204a50`
- `0x18027f19c`
- `0x1802ac88c`

## callees

- `0x180086b60`
- `0x180095bec`
- `0x18009c58c`
- `0x1801cc014`
- `0x1801ceb00`
- `0x1801cfe54`
- `0x1801d0e14`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1801d0180`
- `KERNEL32!GetCurrentProcessId` at `0x1801d0180`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801cfefa`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801cfefa`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801d00b2`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801d0235`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801d00b2`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801d0235`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801cffa7`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801d00e4`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801d01b5`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801d0267`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801cffa7`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801d00e4`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801d01b5`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801d0267`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801d02f6`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801d03a4`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801d02f6`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801d03a4`
- `msIso!__imp_?IsoGetProcessAndManagerFromPid@@YAJKPEAK0@Z` at `0x1801d02ad`
- `msIso!__imp_?IsoGetProcessAndManagerFromPid@@YAJKPEAK0@Z` at `0x1801d02ad`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801cfecd`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801cfecd`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801cfedb`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801cfedb`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801d0328`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801d0495`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801d0328`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801d0495`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801d054b`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801d054b`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801cff0f`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801cff0f`

## pseudocode

```c
__int64 __fastcall LCIEGetBrowserTabTargetProcess(
        struct tagIE8_THREADPARAM *a1,
        struct tagTABWINDOWDATA *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int64 *a7)
{
  unsigned int v7; // r13d
  unsigned int *v8; // r15
  unsigned int *v9; // r12
  unsigned int *v10; // rsi
  struct tagIE8_THREADPARAM *v12; // r14
  unsigned int AuthorityManager; // ebx
  struct tagTABWINDOWDATA *v15; // rbx
  struct _ITEMIDLIST_ABSOLUTE *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  int NextArtifact; // eax
  unsigned int v20; // ebx
  unsigned int v21; // esi
  unsigned int v22; // r15d
  int v23; // r12d
  __int64 v24; // rcx
  unsigned int v25; // r8d
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // ecx
  unsigned int v31; // r10d
  DWORD CurrentProcessId; // r15d
  __int64 v33; // rdx
  unsigned int v34; // r12d
  __int64 v35; // rsi
  __int64 v36; // rdx
  unsigned int v37; // ecx
  __int64 i; // rsi
  unsigned int v39; // r14d
  unsigned __int64 *v40; // rax
  unsigned int v41; // r15d
  unsigned int v42; // ecx
  unsigned int v43; // r14d
  unsigned int v44; // esi
  unsigned int v45; // r12d
  unsigned int v46; // eax
  __int64 v47; // r13
  char v48; // bl
  bool v49; // cl
  unsigned int *v50; // rax
  unsigned int v51; // eax
  unsigned int v52; // r15d
  unsigned __int64 *v53; // rax
  struct tagTABWINDOWDATA *v54; // rax
  unsigned __int64 *v55; // rdi
  unsigned int *v56; // rax
  unsigned int v57; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v58; // [rsp+34h] [rbp-CCh]
  unsigned int v59; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v60; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v61; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v62; // [rsp+48h] [rbp-B8h]
  unsigned int v63; // [rsp+4Ch] [rbp-B4h]
  __int64 v64; // [rsp+50h] [rbp-B0h] BYREF
  int v65; // [rsp+58h] [rbp-A8h]
  unsigned int *v66; // [rsp+60h] [rbp-A0h]
  unsigned int *v67; // [rsp+68h] [rbp-98h]
  unsigned int *v68; // [rsp+70h] [rbp-90h]
  struct tagTABWINDOWDATA *v69; // [rsp+78h] [rbp-88h]
  unsigned int v70; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v71; // [rsp+88h] [rbp-78h]
  struct tagIE8_THREADPARAM *v72; // [rsp+90h] [rbp-70h]
  _BYTE v73[24]; // [rsp+A0h] [rbp-60h] BYREF
  int v74; // [rsp+B8h] [rbp-48h]
  _QWORD v75[72]; // [rsp+110h] [rbp+10h]
  _BYTE v76[32]; // [rsp+350h] [rbp+250h] BYREF

  v7 = 0;
  v8 = a5;
  v9 = a4;
  v10 = a6;
  v68 = a5;
  v12 = a1;
  v66 = a6;
  v71 = a7;
  v57 = 0;
  v61 = 0;
  v64 = 0;
  v67 = a4;
  v69 = a2;
  v72 = a1;
  AuthorityManager = IsoGetAuthorityManager();
  if ( IsoGetCurrentProcessManager() != AuthorityManager )
    return 2147549183LL;
  if ( !(unsigned __int8)IEConfiguration_GetBool(268435483) )
  {
    *v9 = IsoGetIntegrity(1) | 0x2000;
    *a5 = 0;
    *a6 = 0;
    return 0;
  }
  v15 = v69;
  v16 = (struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)v12 + 44);
  v62 = 0;
  v65 = 0;
  v60 = 0;
  v63 = 0;
  v58 = 0;
  LCIEGetURLPolicy(v16, v69, a3, &v57, &v60);
  if ( !*((_DWORD *)v12 + 80) )
  {
    v18 = v60;
    *((_DWORD *)v12 + 80) = v60;
    *((_DWORD *)v15 + 13) = v18;
  }
  LOBYTE(v17) = 20;
  NextArtifact = IsoGetNextArtifact(5, v17, v76, &v61, &v64, 0);
  v20 = v57;
  v70 = v57;
  if ( !NextArtifact )
  {
    v21 = 0;
    v22 = 0;
    v23 = 0;
    do
    {
      if ( *(_WORD *)(v64 + 2) != 3
        || (*(_DWORD *)(v64 + 20) & 0x6050000) != 0x4000000
        || (++v22, *((_DWORD *)v12 + 28) != *(_DWORD *)(v64 + 80))
        && ((*((_BYTE *)v12 + 116) & 8) != 0 || (*(_BYTE *)(v64 + 76) & 8) != 0)
        || ((v20 ^ *(_DWORD *)(v64 + 20)) & 0x8000000) != 0
        || *(_DWORD *)(v64 + 72) != *((_DWORD *)v12 + 80)
        || *(_DWORD *)(v64 + 84)
        || !LCIEIsProcessAlive(*(_DWORD *)(v64 + 16))
        || (*(_DWORD *)(v64 + 64) & 1) != 0
        || v7 >= 0x18 )
      {
        v25 = v61;
      }
      else
      {
        v24 = v64;
        v25 = v61;
        v26 = 3LL * v7;
        LODWORD(v75[v26 + 2]) = *(_DWORD *)(v64 + 12);
        v27 = *(_DWORD *)(v24 + 20);
        HIDWORD(v75[v26 + 1]) = v25;
        v28 = v27 & 0xFFF;
        v75[v26] = 0;
        BYTE4(v75[v26 + 2]) = 0;
        if ( v28 == (v20 & 0xFFF) )
          ++v21;
        else
          ++v23;
        ++v7;
        LOBYTE(v75[v26 + 1]) = v28 == (v20 & 0xFFF);
      }
      IsoUnlockArtifact(v25);
      LOBYTE(v29) = 20;
    }
    while ( !(unsigned int)IsoGetNextArtifact(6, v29, v76, &v61, &v64, 0) );
    v65 = v23;
    v9 = v67;
    v63 = v22;
    v8 = v68;
    v62 = v21;
    v10 = v66;
    v58 = v7;
  }
  if ( *((_BYTE *)v69 + 15) )
  {
    v60 = 0;
    LCIELogonFrameProcesses_GetLogonSessionCounts(&v60, 0);
    if ( v60 < LCIEMaxTabProcessesInLogonSession() && v63 < 0x18 )
    {
      *v9 = v20 | 0x5000;
      *v8 = 0;
      *v10 = 0;
      return 0;
    }
  }
  v30 = v62;
  v31 = 0;
  v60 = 0;
  if ( !v62 )
  {
    v44 = 0;
    v43 = 0;
    goto LABEL_84;
  }
  CurrentProcessId = GetCurrentProcessId();
  LOBYTE(v33) = 20;
  if ( !(unsigned int)IsoGetNextArtifact(5, v33, v76, &v61, &v64, 0) )
  {
    v34 = v60;
    do
    {
      if ( *(_WORD *)(v64 + 2) == 515 && *(_DWORD *)(v64 + 16) != CurrentProcessId )
      {
        v35 = 0;
        if ( v7 )
        {
          do
          {
            if ( (unsigned int)v35 >= 0x18 )
              break;
            if ( *(_DWORD *)(v64 + 12) == LODWORD(v75[3 * v35 + 2]) )
            {
              if ( (*(_DWORD *)GetSharedMemoryPointer(v61) & 0x8000000) != 0 )
              {
                ++HIDWORD(v75[3 * v35]);
              }
              else
              {
                ++LODWORD(v75[3 * v35]);
                ++v34;
              }
            }
            v35 = (unsigned int)(v35 + 1);
          }
          while ( (unsigned int)v35 < v7 );
          v60 = v34;
        }
      }
      IsoUnlockArtifact(v61);
      LOBYTE(v36) = 20;
    }
    while ( !(unsigned int)IsoGetNextArtifact(6, v36, v76, &v61, &v64, 0) );
    v9 = v67;
    v12 = v72;
  }
  v37 = *((_DWORD *)v12 + 54);
  if ( v37 )
  {
    v59 = 0;
    v57 = 0;
    if ( (int)IsoGetProcessAndManagerFromPid(v37, &v57, &v59) >= 0 )
    {
      for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      {
        if ( LOBYTE(v75[3 * i + 1]) )
        {
          v39 = v75[3 * i + 2];
          if ( v39 == v57 )
          {
            memset_0(v73, 0, 0x70u);
            if ( (int)IsoGetProcessData(v39, (struct _IsoProcess *)v73) >= 0 )
            {
              v40 = v71;
              BYTE4(v75[3 * i + 2]) = 1;
              v41 = HIDWORD(v75[3 * i + 1]);
              if ( (int)IsoAddDependency(v41, v41, 1, 50, v40) >= 0 )
              {
                v50 = v68;
                *v9 = v20 | 0x4000;
                *v50 = v41;
                *v66 = v39;
                return 0;
              }
            }
          }
        }
      }
    }
  }
  while ( 1 )
  {
    do
    {
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v57 = 0;
      v45 = 0;
      v59 = 99999;
    }
    while ( !v7 );
    v46 = v58;
    v47 = 0;
    v48 = 1;
    do
    {
      if ( !LOBYTE(v75[3 * v47 + 1]) || BYTE4(v75[3 * v47 + 2]) )
        goto LABEL_71;
      memset_0(v73, 0, 0x70u);
      if ( (int)IsoGetProcessData(v75[3 * v47 + 2], (struct _IsoProcess *)v73) < 0 )
        goto LABEL_74;
      v49 = !v74 || v74 == 3;
      v51 = v75[3 * v47];
      if ( v51 >= v59 )
      {
        if ( v51 == v59 )
        {
          v46 = v58;
          if ( v48 )
          {
            v42 = v57;
          }
          else
          {
            if ( !v49 )
            {
              v52 = v59;
              v42 = v57;
              goto LABEL_76;
            }
            v43 = HIDWORD(v75[3 * v47 + 1]);
            v42 = v45;
            v44 = v75[3 * v47 + 2];
            v48 = 1;
            v57 = v45;
          }
LABEL_71:
          v52 = v59;
          goto LABEL_76;
        }
LABEL_74:
        v42 = v57;
        v52 = v59;
        goto LABEL_75;
      }
      v43 = HIDWORD(v75[3 * v47 + 1]);
      v48 = v49;
      v44 = v75[3 * v47 + 2];
      v42 = v45;
      v57 = v45;
      v52 = v51;
      v59 = v51;
LABEL_75:
      v46 = v58;
LABEL_76:
      ++v45;
      ++v47;
    }
    while ( v45 < v46 );
    v7 = v58;
    if ( v44 )
    {
      v53 = v71;
      BYTE4(v75[3 * v42 + 2]) = 1;
      if ( (int)IsoAddDependency(v43, v43, 1, 50, v53) >= 0 )
        break;
    }
  }
  v20 = v70;
  if ( !v52 )
  {
    *v67 = v70 | 0x4000;
    *v68 = v43;
    goto LABEL_81;
  }
  v9 = v67;
  v8 = v68;
  v30 = v62;
  v31 = v60;
LABEL_84:
  v54 = v69;
  if ( (*((_BYTE *)v72 + 4) & 2) != 0 )
    *((_BYTE *)v69 + 16) = 1;
  if ( !v30 || !v44 )
  {
LABEL_91:
    if ( v63 >= 0x18 )
    {
      if ( !v30 )
        return 2147942414LL;
    }
    else if ( v63 != 23 || v65 || !v30 )
    {
      v55 = v71;
      if ( *v71 )
      {
        IsoRemoveDependency(*v71);
        *v55 = 0;
      }
      v56 = v66;
      *v9 = v20 | 0x5000;
      *v8 = 0;
      *v56 = 0;
      return 0;
    }
    if ( v44 )
      goto LABEL_100;
    return 2147942414LL;
  }
  if ( !*((_BYTE *)v54 + 16) && (unsigned int)LCIEShouldCreateNewTabProcess(v31, v7, v30, v63) )
  {
    v30 = v62;
    goto LABEL_91;
  }
LABEL_100:
  *v9 = v20 | 0x4000;
  *v8 = v43;
LABEL_81:
  *v66 = v44;
  return 0;
}

```

## disassembly

```asm
0x1801cfe54  push    rbp
0x1801cfe56  push    rbx
0x1801cfe57  push    rsi
0x1801cfe58  push    rdi
0x1801cfe59  push    r12
0x1801cfe5b  push    r13
0x1801cfe5d  push    r14
0x1801cfe5f  push    r15
0x1801cfe61  lea     rbp, [rsp-288h]
0x1801cfe69  sub     rsp, 388h
0x1801cfe70  mov     rax, cs:__security_cookie
0x1801cfe77  xor     rax, rsp
0x1801cfe7a  mov     [rbp+2C0h+var_50], rax
0x1801cfe81  mov     rax, [rbp+2C0h+arg_30]
0x1801cfe88  xor     r13d, r13d
0x1801cfe8b  mov     r15, [rbp+2C0h+arg_20]
0x1801cfe92  mov     r12, r9
0x1801cfe95  mov     rsi, [rbp+2C0h+arg_28]
0x1801cfe9c  mov     rdi, r8
0x1801cfe9f  mov     [rsp+3C0h+var_350], r15
0x1801cfea4  mov     r14, rcx
0x1801cfea7  mov     [rsp+3C0h+var_360], rsi
0x1801cfeac  mov     [rbp+2C0h+var_338], rax
0x1801cfeb0  mov     [rsp+3C0h+var_390], r13d
0x1801cfeb5  mov     [rsp+3C0h+var_380], r13d
0x1801cfeba  mov     [rsp+3C0h+var_370], r13
0x1801cfebf  mov     [rsp+3C0h+var_358], r9
0x1801cfec4  mov     [rsp+3C0h+var_348], rdx
0x1801cfec9  mov     [rbp+2C0h+var_330], rcx
0x1801cfecd  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1801cfed4  nop     dword ptr [rax+rax+00h]
0x1801cfed9  mov     ebx, eax
0x1801cfedb  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801cfee2  nop     dword ptr [rax+rax+00h]
0x1801cfee7  cmp     eax, ebx
0x1801cfee9  jz      short loc_1801CFEF5
0x1801cfeeb  mov     eax, 8000FFFFh
0x1801cfef0  jmp     loc_1801D059C
0x1801cfef5  mov     ecx, 1000001Bh
0x1801cfefa  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801cff01  nop     dword ptr [rax+rax+00h]
0x1801cff06  test    al, al
0x1801cff08  jnz     short loc_1801CFF30
0x1801cff0a  mov     ecx, 1
0x1801cff0f  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1801cff16  nop     dword ptr [rax+rax+00h]
0x1801cff1b  bts     eax, 0Dh
0x1801cff1f  mov     [r12], eax
0x1801cff23  mov     [r15], r13d
0x1801cff26  mov     [rsi], r13d
0x1801cff29  xor     eax, eax
0x1801cff2b  jmp     loc_1801D059C
0x1801cff30  mov     rbx, [rsp+3C0h+var_348]
0x1801cff35  lea     r9, [rsp+3C0h+var_390]; unsigned int *
0x1801cff3a  mov     rcx, [r14+160h]; struct _ITEMIDLIST_ABSOLUTE *
0x1801cff41  xor     eax, eax
0x1801cff43  mov     [rsp+3C0h+var_378], eax
0x1801cff47  mov     r8, rdi; unsigned int *
0x1801cff4a  mov     [rsp+3C0h+var_368], eax
0x1801cff4e  mov     rdx, rbx; struct tagTABWINDOWDATA *
0x1801cff51  mov     [rsp+3C0h+var_384], eax
0x1801cff55  lea     rax, [rsp+3C0h+var_384]
0x1801cff5a  mov     [rsp+3C0h+var_3A0], rax; unsigned int *
0x1801cff5f  mov     [rsp+3C0h+var_374], r13d
0x1801cff64  mov     [rsp+3C0h+var_38C], r13d
0x1801cff69  call    ?LCIEGetURLPolicy@@YAJPEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagTABWINDOWDATA@@PEAK22@Z; LCIEGetURLPolicy(_ITEMIDLIST_ABSOLUTE *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *)
0x1801cff6e  cmp     [r14+140h], r13d
0x1801cff75  jnz     short loc_1801CFF85
0x1801cff77  mov     eax, [rsp+3C0h+var_384]
0x1801cff7b  mov     [r14+140h], eax
0x1801cff82  mov     [rbx+34h], eax
0x1801cff85  lea     rax, [rsp+3C0h+var_370]
0x1801cff8a  mov     [rsp+3C0h+var_398], r13
0x1801cff8f  lea     r9, [rsp+3C0h+var_380]
0x1801cff94  mov     [rsp+3C0h+var_3A0], rax
0x1801cff99  lea     r8, [rbp+2C0h+var_70]
0x1801cffa0  mov     dl, 14h
0x1801cffa2  mov     ecx, 5
0x1801cffa7  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801cffae  nop     dword ptr [rax+rax+00h]
0x1801cffb3  mov     ebx, [rsp+3C0h+var_390]
0x1801cffb7  mov     edi, 1
0x1801cffbc  mov     [rbp+2C0h+var_340], ebx
0x1801cffbf  lea     edx, [rdi+2]
0x1801cffc2  test    eax, eax
0x1801cffc4  jnz     loc_1801D011F
0x1801cffca  mov     esi, r13d
0x1801cffcd  mov     r15d, r13d
0x1801cffd0  mov     r12d, r13d
0x1801cffd3  mov     rcx, [rsp+3C0h+var_370]
0x1801cffd8  cmp     [rcx+2], dx
0x1801cffdc  jnz     loc_1801D00AA
0x1801cffe2  mov     edx, [rcx+14h]
0x1801cffe5  mov     eax, edx
0x1801cffe7  and     eax, 6050000h
0x1801cffec  cmp     eax, 4000000h
0x1801cfff1  jnz     loc_1801D00AA
0x1801cfff7  mov     eax, [rcx+50h]
0x1801cfffa  add     r15d, edi
0x1801cfffd  cmp     [r14+70h], eax
0x1801d0001  jz      short loc_1801D0018
0x1801d0003  test    byte ptr [r14+74h], 8
0x1801d0008  jnz     loc_1801D00AA
0x1801d000e  test    byte ptr [rcx+4Ch], 8
0x1801d0012  jnz     loc_1801D00AA
0x1801d0018  xor     edx, ebx
0x1801d001a  bt      edx, 1Bh
0x1801d001e  jb      loc_1801D00AA
0x1801d0024  mov     eax, [r14+140h]
0x1801d002b  cmp     [rcx+48h], eax
0x1801d002e  jnz     short loc_1801D00AA
0x1801d0030  cmp     dword ptr [rcx+54h], 0
0x1801d0034  jnz     short loc_1801D00AA
0x1801d0036  mov     ecx, [rcx+10h]; unsigned int
0x1801d0039  call    ?LCIEIsProcessAlive@@YA_NK@Z; LCIEIsProcessAlive(ulong)
0x1801d003e  test    al, al
0x1801d0040  jz      short loc_1801D00AA
0x1801d0042  mov     rax, [rsp+3C0h+var_370]
0x1801d0047  mov     ecx, [rax+40h]
0x1801d004a  test    dil, cl
0x1801d004d  jnz     short loc_1801D00AA
0x1801d004f  cmp     r13d, 18h
0x1801d0053  jnb     short loc_1801D00AA
0x1801d0055  mov     rcx, [rsp+3C0h+var_370]
0x1801d005a  mov     r9d, 0FFFh
0x1801d0060  mov     r8d, [rsp+3C0h+var_380]
0x1801d0065  mov     eax, r13d
0x1801d0068  lea     rdx, [rax+rax*2]
0x1801d006c  mov     eax, [rcx+0Ch]
0x1801d006f  mov     [rbp+rdx*8+2C0h+var_2A0], eax
0x1801d0073  mov     eax, [rcx+14h]
0x1801d0076  mov     ecx, ebx
0x1801d0078  and     ecx, r9d
0x1801d007b  mov     [rbp+rdx*8+2C0h+var_2A4], r8d
0x1801d0080  and     eax, r9d
0x1801d0083  mov     [rbp+rdx*8+2C0h+var_2B0], 0
0x1801d008c  mov     [rbp+rdx*8+2C0h+var_29C], 0
0x1801d0091  cmp     eax, ecx
0x1801d0093  jnz     short loc_1801D0099
0x1801d0095  add     esi, edi
0x1801d0097  jmp     short loc_1801D009C
0x1801d0099  add     r12d, edi
0x1801d009c  cmp     eax, ecx
0x1801d009e  setz    al
0x1801d00a1  add     r13d, edi
0x1801d00a4  mov     [rbp+rdx*8+2C0h+var_2A8], al
0x1801d00a8  jmp     short loc_1801D00AF
0x1801d00aa  mov     r8d, [rsp+3C0h+var_380]
0x1801d00af  mov     ecx, r8d
0x1801d00b2  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801d00b9  nop     dword ptr [rax+rax+00h]
0x1801d00be  lea     rax, [rsp+3C0h+var_370]
0x1801d00c3  mov     [rsp+3C0h+var_398], 0
0x1801d00cc  lea     r9, [rsp+3C0h+var_380]
0x1801d00d1  mov     [rsp+3C0h+var_3A0], rax
0x1801d00d6  lea     r8, [rbp+2C0h+var_70]
0x1801d00dd  mov     dl, 14h
0x1801d00df  mov     ecx, 6
0x1801d00e4  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801d00eb  nop     dword ptr [rax+rax+00h]
0x1801d00f0  mov     edx, 3
0x1801d00f5  test    eax, eax
0x1801d00f7  jz      loc_1801CFFD3
0x1801d00fd  mov     [rsp+3C0h+var_368], r12d
0x1801d0102  mov     r12, [rsp+3C0h+var_358]
0x1801d0107  mov     [rsp+3C0h+var_374], r15d
0x1801d010c  mov     r15, [rsp+3C0h+var_350]
0x1801d0111  mov     [rsp+3C0h+var_378], esi
0x1801d0115  mov     rsi, [rsp+3C0h+var_360]
0x1801d011a  mov     [rsp+3C0h+var_38C], r13d
0x1801d011f  mov     rax, [rsp+3C0h+var_348]
0x1801d0124  cmp     byte ptr [rax+0Fh], 0
0x1801d0128  jz      short loc_1801D016C
0x1801d012a  xor     edx, edx; unsigned int *
0x1801d012c  mov     [rsp+3C0h+var_384], 0
0x1801d0134  lea     rcx, [rsp+3C0h+var_384]; unsigned int *
0x1801d0139  call    ?LCIELogonFrameProcesses_GetLogonSessionCounts@@YAXPEAK0@Z; LCIELogonFrameProcesses_GetLogonSessionCounts(ulong *,ulong *)
0x1801d013e  call    ?LCIEMaxTabProcessesInLogonSession@@YAKXZ; LCIEMaxTabProcessesInLogonSession(void)
0x1801d0143  cmp     [rsp+3C0h+var_384], eax
0x1801d0147  jnb     short loc_1801D016C
0x1801d0149  cmp     [rsp+3C0h+var_374], 18h
0x1801d014e  jnb     short loc_1801D016C
0x1801d0150  or      ebx, 5000h
0x1801d0156  mov     [r12], ebx
0x1801d015a  mov     dword ptr [r15], 0
0x1801d0161  mov     dword ptr [rsi], 0
0x1801d0167  jmp     loc_1801CFF29
0x1801d016c  mov     ecx, [rsp+3C0h+var_378]
0x1801d0170  xor     r10d, r10d
0x1801d0173  mov     [rsp+3C0h+var_384], r10d
0x1801d0178  test    ecx, ecx
0x1801d017a  jz      loc_1801D04D0
0x1801d0180  call    cs:__imp_GetCurrentProcessId
0x1801d0187  nop     dword ptr [rax+rax+00h]
0x1801d018c  mov     [rsp+3C0h+var_398], 0
0x1801d0195  lea     r9, [rsp+3C0h+var_380]
0x1801d019a  mov     r15d, eax
0x1801d019d  lea     r8, [rbp+2C0h+var_70]
0x1801d01a4  lea     rax, [rsp+3C0h+var_370]
0x1801d01a9  mov     dl, 14h
0x1801d01ab  mov     ecx, 5
0x1801d01b0  mov     [rsp+3C0h+var_3A0], rax
0x1801d01b5  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801d01bc  nop     dword ptr [rax+rax+00h]
0x1801d01c1  test    eax, eax
0x1801d01c3  jnz     loc_1801D0284
0x1801d01c9  mov     r12d, [rsp+3C0h+var_384]
0x1801d01ce  mov     rax, [rsp+3C0h+var_370]
0x1801d01d3  mov     ecx, 203h
0x1801d01d8  cmp     [rax+2], cx
0x1801d01dc  jnz     short loc_1801D0231
0x1801d01de  mov     eax, [rax+10h]
0x1801d01e1  cmp     eax, r15d
0x1801d01e4  jz      short loc_1801D0231
0x1801d01e6  xor     esi, esi
0x1801d01e8  test    r13d, r13d
0x1801d01eb  jz      short loc_1801D0231
0x1801d01ed  cmp     esi, 18h
0x1801d01f0  jnb     short loc_1801D022C
0x1801d01f2  mov     rax, [rsp+3C0h+var_370]
0x1801d01f7  lea     r14, [rsi+rsi*2]
0x1801d01fb  mov     ecx, [rbp+r14*8+2C0h+var_2A0]
0x1801d0200  cmp     [rax+0Ch], ecx
0x1801d0203  jnz     short loc_1801D0225
0x1801d0205  mov     ecx, [rsp+3C0h+var_380]; unsigned int
0x1801d0209  call    ?GetSharedMemoryPointer@@YAPEAUBROWSERTAB_SHAREDMEMORY@@K@Z; GetSharedMemoryPointer(ulong)
0x1801d020e  mov     ecx, [rax]
0x1801d0210  bt      ecx, 1Bh
0x1801d0214  jnb     short loc_1801D021D
0x1801d0216  add     dword ptr [rbp+r14*8+2C0h+var_2B0+4], edi
0x1801d021b  jmp     short loc_1801D0225
0x1801d021d  add     dword ptr [rbp+r14*8+2C0h+var_2B0], edi
0x1801d0222  add     r12d, edi
0x1801d0225  add     esi, edi
0x1801d0227  cmp     esi, r13d
0x1801d022a  jb      short loc_1801D01ED
0x1801d022c  mov     [rsp+3C0h+var_384], r12d
0x1801d0231  mov     ecx, [rsp+3C0h+var_380]
0x1801d0235  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801d023c  nop     dword ptr [rax+rax+00h]
0x1801d0241  lea     rax, [rsp+3C0h+var_370]
0x1801d0246  mov     [rsp+3C0h+var_398], 0
0x1801d024f  lea     r9, [rsp+3C0h+var_380]
0x1801d0254  mov     [rsp+3C0h+var_3A0], rax
0x1801d0259  lea     r8, [rbp+2C0h+var_70]
0x1801d0260  mov     dl, 14h
0x1801d0262  mov     ecx, 6
0x1801d0267  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801d026e  nop     dword ptr [rax+rax+00h]
0x1801d0273  test    eax, eax
0x1801d0275  jz      loc_1801D01CE
0x1801d027b  mov     r12, [rsp+3C0h+var_358]
0x1801d0280  mov     r14, [rbp+2C0h+var_330]
0x1801d0284  mov     ecx, [r14+0D8h]
0x1801d028b  test    ecx, ecx
0x1801d028d  jz      loc_1801D0343
0x1801d0293  lea     r8, [rsp+3C0h+var_388]
0x1801d0298  mov     [rsp+3C0h+var_388], 0
0x1801d02a0  lea     rdx, [rsp+3C0h+var_390]
0x1801d02a5  mov     [rsp+3C0h+var_390], 0
0x1801d02ad  call    cs:__imp_?IsoGetProcessAndManagerFromPid@@YAJKPEAK0@Z; IsoGetProcessAndManagerFromPid(ulong,ulong *,ulong *)
0x1801d02b4  nop     dword ptr [rax+rax+00h]
0x1801d02b9  test    eax, eax
0x1801d02bb  js      loc_1801D0343
0x1801d02c1  xor     esi, esi
0x1801d02c3  test    r13d, r13d
0x1801d02c6  jz      short loc_1801D0343
0x1801d02c8  lea     r15, [rsi+rsi*2]
0x1801d02cc  cmp     [rbp+r15*8+2C0h+var_2A8], 0
0x1801d02d2  jz      short loc_1801D033C
0x1801d02d4  mov     r14d, [rbp+r15*8+2C0h+var_2A0]
0x1801d02d9  cmp     r14d, [rsp+3C0h+var_390]
0x1801d02de  jnz     short loc_1801D033C
0x1801d02e0  xor     edx, edx; Val
0x1801d02e2  lea     rcx, [rbp+2C0h+var_320]; void *
0x1801d02e6  lea     r8d, [rdx+70h]; Size
0x1801d02ea  call    memset_0
0x1801d02ef  lea     rdx, [rbp+2C0h+var_320]
0x1801d02f3  mov     ecx, r14d
0x1801d02f6  call    cs:__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z; IsoGetProcessData(ulong,_IsoProcess *)
0x1801d02fd  nop     dword ptr [rax+rax+00h]
0x1801d0302  test    eax, eax
0x1801d0304  js      short loc_1801D033C
0x1801d0306  mov     rax, [rbp+2C0h+var_338]
0x1801d030a  mov     r9d, 32h ; '2'
0x1801d0310  mov     [rbp+r15*8+2C0h+var_29C], dil
0x1801d0315  mov     r8d, edi
0x1801d0318  mov     r15d, [rbp+r15*8+2C0h+var_2A4]
0x1801d031d  mov     edx, r15d
0x1801d0320  mov     ecx, r15d
0x1801d0323  mov     [rsp+3C0h+var_3A0], rax
0x1801d0328  call    cs:__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z; IsoAddDependency(ulong,ulong,_IsoComponentDependencyFlags,_BlockSuspendReason,unsigned __int64 *)
0x1801d032f  nop     dword ptr [rax+rax+00h]
0x1801d0334  test    eax, eax
0x1801d0336  jns     loc_1801D03C8
0x1801d033c  add     esi, edi
0x1801d033e  cmp     esi, r13d
0x1801d0341  jb      short loc_1801D02C8
0x1801d0343  xor     ecx, ecx
0x1801d0345  xor     r14d, r14d
  ... truncated ...
```
