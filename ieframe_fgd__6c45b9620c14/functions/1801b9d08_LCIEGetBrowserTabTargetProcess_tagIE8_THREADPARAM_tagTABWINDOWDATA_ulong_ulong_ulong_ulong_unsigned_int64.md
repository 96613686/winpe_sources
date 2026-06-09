# LCIEGetBrowserTabTargetProcess(tagIE8_THREADPARAM *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *,ulong *,unsigned __int64 *)

- ea: `0x1801b9d08`
- end: `0x1801ba43a`
- name: `?LCIEGetBrowserTabTargetProcess@@YAJPEAUtagIE8_THREADPARAM@@PEAUtagTABWINDOWDATA@@PEAK222PEA_K@Z`
- size: `1842`
- prototype: `int(struct tagIE8_THREADPARAM *, struct tagTABWINDOWDATA *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801eb1fc`
- `0x18025f57c`
- `0x18028a6d4`

## callees

- `0x1800805a8`
- `0x18008ee2c`
- `0x180095188`
- `0x1801b64a4`
- `0x1801b9d08`
- `0x1801babd0`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1801ba008`
- `KERNEL32!GetCurrentProcessId` at `0x1801ba008`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801b9da1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801b9da1`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801b9f47`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801ba0e2`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801b9f47`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801ba0e2`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801b9e41`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801b9f73`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801ba037`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801ba10e`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801b9e41`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801b9f73`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801ba037`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1801ba10e`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801ba190`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801ba22e`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801ba190`
- `msIso!__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z` at `0x1801ba22e`
- `msIso!__imp_?IsoGetProcessAndManagerFromPid@@YAJKPEAK0@Z` at `0x1801ba14d`
- `msIso!__imp_?IsoGetProcessAndManagerFromPid@@YAJKPEAK0@Z` at `0x1801ba14d`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801ba0a9`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801ba0a9`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801b9d80`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801b9d80`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801b9d88`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801b9d88`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801ba1b8`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801ba31c`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801ba1b8`
- `msIso!__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z` at `0x1801ba31c`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801ba3cc`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801ba3cc`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801b9db0`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1801b9db0`

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
  unsigned int *v8; // r12
  unsigned int *v9; // r15
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
  unsigned int v22; // r12d
  int v23; // r15d
  __int64 v24; // rcx
  unsigned int v25; // r8d
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // ecx
  unsigned int v31; // r10d
  DWORD CurrentProcessId; // r12d
  __int64 v33; // rdx
  unsigned int v34; // ebx
  __int64 v35; // rsi
  _DWORD *v36; // r15
  __int64 v37; // rdx
  unsigned int v38; // ecx
  __int64 v39; // rsi
  unsigned __int64 *v40; // r12
  unsigned int v41; // r14d
  unsigned int v42; // r15d
  unsigned int v43; // ecx
  unsigned int v44; // r14d
  unsigned int v45; // esi
  unsigned int v46; // r12d
  unsigned int v47; // eax
  __int64 v48; // r13
  char v49; // bl
  bool v50; // cl
  unsigned int v51; // eax
  unsigned int v52; // r15d
  unsigned __int64 *v53; // rax
  struct tagTABWINDOWDATA *v54; // rax
  unsigned __int64 *v55; // rdi
  unsigned int *v56; // rax
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  unsigned int v58; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v59; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v60[3]; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v61[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v62; // [rsp+50h] [rbp-B0h]
  unsigned int v63; // [rsp+54h] [rbp-ACh]
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  int v65; // [rsp+60h] [rbp-A0h]
  unsigned int v66; // [rsp+64h] [rbp-9Ch]
  unsigned int *v67; // [rsp+68h] [rbp-98h]
  unsigned int *v68; // [rsp+70h] [rbp-90h]
  unsigned int *v69; // [rsp+78h] [rbp-88h]
  struct tagTABWINDOWDATA *v70; // [rsp+80h] [rbp-80h]
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
  v69 = a5;
  v12 = a1;
  v67 = a6;
  v71 = a7;
  v61[0] = 0;
  v60[0] = 0;
  v64 = 0;
  v68 = a4;
  v70 = a2;
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
  v15 = v70;
  v16 = (struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)v12 + 44);
  v62 = 0;
  v65 = 0;
  v59 = 0;
  v63 = 0;
  v57 = 0;
  LCIEGetURLPolicy(v16, v70, a3, v61, &v59);
  if ( !*((_DWORD *)v12 + 80) )
  {
    v18 = v59;
    *((_DWORD *)v12 + 80) = v59;
    *((_DWORD *)v15 + 13) = v18;
  }
  LOBYTE(v17) = 20;
  NextArtifact = IsoGetNextArtifact(5, v17, v76, v60, &v64, 0);
  v20 = v61[0];
  v66 = v61[0];
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
        v25 = v60[0];
      }
      else
      {
        v24 = v64;
        v25 = v60[0];
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
    while ( !(unsigned int)IsoGetNextArtifact(6, v29, v76, v60, &v64, 0) );
    v65 = v23;
    v9 = v68;
    v63 = v22;
    v8 = v69;
    v62 = v21;
    v10 = v67;
    v57 = v7;
  }
  if ( *((_BYTE *)v70 + 15) )
  {
    v59 = 0;
    LCIELogonFrameProcesses_GetLogonSessionCounts(&v59, 0);
    if ( v59 < LCIEMaxTabProcessesInLogonSession() && v63 < 0x18 )
    {
      *v9 = v20 | 0x5000;
      *v8 = 0;
      *v10 = 0;
      return 0;
    }
  }
  v30 = v62;
  v31 = 0;
  v59 = 0;
  if ( !v62 )
  {
    v45 = 0;
    v44 = 0;
    goto LABEL_87;
  }
  CurrentProcessId = GetCurrentProcessId();
  LOBYTE(v33) = 20;
  if ( !(unsigned int)IsoGetNextArtifact(5, v33, v76, v60, &v64, 0) )
  {
    v34 = v59;
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
              v36 = 0;
              v59 = 0;
              *(_QWORD *)v61 = 0;
              if ( (int)IsoGetTrustSplitComponent(v60[0], 0, 0, &v59, (struct _IsoUntrustedComponent **)v61) >= 0 )
                v36 = (_DWORD *)(*(_QWORD *)v61 + 64LL);
              if ( (*v36 & 0x8000000) != 0 )
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
          v59 = v34;
        }
      }
      IsoUnlockArtifact(v60[0]);
      LOBYTE(v37) = 20;
    }
    while ( !(unsigned int)IsoGetNextArtifact(6, v37, v76, v60, &v64, 0) );
    v20 = v66;
    v12 = v72;
  }
  v38 = *((_DWORD *)v12 + 54);
  if ( v38 )
  {
    v58 = 0;
    v61[0] = 0;
    if ( (int)IsoGetProcessAndManagerFromPid(v38, v61, &v58) >= 0 )
    {
      v39 = 0;
      if ( v7 )
      {
        v40 = v71;
        do
        {
          if ( LOBYTE(v75[3 * v39 + 1]) )
          {
            v41 = v75[3 * v39 + 2];
            if ( v41 == v61[0] )
            {
              memset_0(v73, 0, 0x70u);
              if ( (int)IsoGetProcessData(v41, (struct _IsoProcess *)v73) >= 0 )
              {
                BYTE4(v75[3 * v39 + 2]) = 1;
                v42 = HIDWORD(v75[3 * v39 + 1]);
                if ( (int)IsoAddDependency(v42, v42, 1, 50, v40) >= 0 )
                {
                  *v68 = v20 | 0x4000;
                  *v69 = v42;
                  *v67 = v41;
                  return 0;
                }
              }
            }
          }
          v39 = (unsigned int)(v39 + 1);
        }
        while ( (unsigned int)v39 < v7 );
      }
    }
  }
  while ( 1 )
  {
    do
    {
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v61[0] = 0;
      v46 = 0;
      v58 = 99999;
    }
    while ( !v7 );
    v47 = v57;
    v48 = 0;
    v49 = 1;
    do
    {
      if ( !LOBYTE(v75[3 * v48 + 1]) || BYTE4(v75[3 * v48 + 2]) )
        goto LABEL_74;
      memset_0(v73, 0, 0x70u);
      if ( (int)IsoGetProcessData(v75[3 * v48 + 2], (struct _IsoProcess *)v73) < 0 )
        goto LABEL_77;
      v50 = !v74 || v74 == 3;
      v51 = v75[3 * v48];
      if ( v51 >= v58 )
      {
        if ( v51 == v58 )
        {
          v47 = v57;
          if ( v49 )
          {
            v43 = v61[0];
          }
          else
          {
            if ( !v50 )
            {
              v52 = v58;
              v43 = v61[0];
              goto LABEL_79;
            }
            v44 = HIDWORD(v75[3 * v48 + 1]);
            v43 = v46;
            v45 = v75[3 * v48 + 2];
            v49 = 1;
            v61[0] = v46;
          }
LABEL_74:
          v52 = v58;
          goto LABEL_79;
        }
LABEL_77:
        v43 = v61[0];
        v52 = v58;
        goto LABEL_78;
      }
      v44 = HIDWORD(v75[3 * v48 + 1]);
      v49 = v50;
      v45 = v75[3 * v48 + 2];
      v43 = v46;
      v61[0] = v46;
      v52 = v51;
      v58 = v51;
LABEL_78:
      v47 = v57;
LABEL_79:
      ++v46;
      ++v48;
    }
    while ( v46 < v47 );
    v7 = v57;
    if ( v45 )
    {
      v53 = v71;
      BYTE4(v75[3 * v43 + 2]) = 1;
      if ( (int)IsoAddDependency(v44, v44, 1, 50, v53) >= 0 )
        break;
    }
  }
  v20 = v66;
  if ( !v52 )
  {
    *v68 = v66 | 0x4000;
    *v69 = v44;
    goto LABEL_84;
  }
  v9 = v68;
  v8 = v69;
  v30 = v62;
  v31 = v59;
LABEL_87:
  v54 = v70;
  if ( (*((_BYTE *)v72 + 4) & 2) != 0 )
    *((_BYTE *)v70 + 16) = 1;
  if ( !v30 || !v45 )
  {
LABEL_94:
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
      v56 = v67;
      *v9 = v20 | 0x5000;
      *v8 = 0;
      *v56 = 0;
      return 0;
    }
    if ( v45 )
      goto LABEL_103;
    return 2147942414LL;
  }
  if ( !*((_BYTE *)v54 + 16) && (unsigned int)LCIEShouldCreateNewTabProcess(v31, v7, v30, v63) )
  {
    v30 = v62;
    goto LABEL_94;
  }
LABEL_103:
  *v9 = v20 | 0x4000;
  *v8 = v44;
LABEL_84:
  *v67 = v45;
  return 0;
}

```

## disassembly

```asm
0x1801b9d08  push    rbp
0x1801b9d0a  push    rbx
0x1801b9d0b  push    rsi
0x1801b9d0c  push    rdi
0x1801b9d0d  push    r12
0x1801b9d0f  push    r13
0x1801b9d11  push    r14
0x1801b9d13  push    r15
0x1801b9d15  lea     rbp, [rsp-288h]
0x1801b9d1d  sub     rsp, 388h
0x1801b9d24  mov     rax, cs:__security_cookie
0x1801b9d2b  xor     rax, rsp
0x1801b9d2e  mov     [rbp+2C0h+var_50], rax
0x1801b9d35  mov     rax, [rbp+2C0h+arg_30]
0x1801b9d3c  xor     r13d, r13d
0x1801b9d3f  mov     r12, [rbp+2C0h+arg_20]
0x1801b9d46  mov     r15, r9
0x1801b9d49  mov     rsi, [rbp+2C0h+arg_28]
0x1801b9d50  mov     rdi, r8
0x1801b9d53  mov     [rsp+3C0h+var_348], r12
0x1801b9d58  mov     r14, rcx
0x1801b9d5b  mov     [rsp+3C0h+var_358], rsi
0x1801b9d60  mov     [rbp+2C0h+var_338], rax
0x1801b9d64  mov     [rsp+3C0h+var_378], r13d
0x1801b9d69  mov     [rsp+3C0h+var_384], r13d
0x1801b9d6e  mov     [rsp+3C0h+var_368], r13
0x1801b9d73  mov     [rsp+3C0h+var_350], r9
0x1801b9d78  mov     [rbp+2C0h+var_340], rdx
0x1801b9d7c  mov     [rbp+2C0h+var_330], rcx
0x1801b9d80  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1801b9d86  mov     ebx, eax
0x1801b9d88  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801b9d8e  cmp     eax, ebx
0x1801b9d90  jz      short loc_1801B9D9C
0x1801b9d92  mov     eax, 8000FFFFh
0x1801b9d97  jmp     loc_1801BA417
0x1801b9d9c  mov     ecx, 1000001Bh
0x1801b9da1  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801b9da7  test    al, al
0x1801b9da9  jnz     short loc_1801B9DCB
0x1801b9dab  mov     ecx, 1
0x1801b9db0  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1801b9db6  bts     eax, 0Dh
0x1801b9dba  mov     [r15], eax
0x1801b9dbd  mov     [r12], r13d
0x1801b9dc1  mov     [rsi], r13d
0x1801b9dc4  xor     eax, eax
0x1801b9dc6  jmp     loc_1801BA417
0x1801b9dcb  mov     rbx, [rbp+2C0h+var_340]
0x1801b9dcf  lea     r9, [rsp+3C0h+var_378]; unsigned int *
0x1801b9dd4  mov     rcx, [r14+160h]; struct _ITEMIDLIST_ABSOLUTE *
0x1801b9ddb  xor     eax, eax
0x1801b9ddd  mov     [rsp+3C0h+var_370], eax
0x1801b9de1  mov     r8, rdi; unsigned int *
0x1801b9de4  mov     [rsp+3C0h+var_360], eax
0x1801b9de8  mov     rdx, rbx; struct tagTABWINDOWDATA *
0x1801b9deb  mov     [rsp+3C0h+var_388], eax
0x1801b9def  lea     rax, [rsp+3C0h+var_388]
0x1801b9df4  mov     [rsp+3C0h+var_3A0], rax; unsigned int *
0x1801b9df9  mov     [rsp+3C0h+var_36C], r13d
0x1801b9dfe  mov     [rsp+3C0h+var_390], r13d
0x1801b9e03  call    ?LCIEGetURLPolicy@@YAJPEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagTABWINDOWDATA@@PEAK22@Z; LCIEGetURLPolicy(_ITEMIDLIST_ABSOLUTE *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *)
0x1801b9e08  cmp     [r14+140h], r13d
0x1801b9e0f  jnz     short loc_1801B9E1F
0x1801b9e11  mov     eax, [rsp+3C0h+var_388]
0x1801b9e15  mov     [r14+140h], eax
0x1801b9e1c  mov     [rbx+34h], eax
0x1801b9e1f  lea     rax, [rsp+3C0h+var_368]
0x1801b9e24  mov     [rsp+3C0h+var_398], r13
0x1801b9e29  lea     r9, [rsp+3C0h+var_384]
0x1801b9e2e  mov     [rsp+3C0h+var_3A0], rax
0x1801b9e33  lea     r8, [rbp+2C0h+var_70]
0x1801b9e3a  mov     dl, 14h
0x1801b9e3c  mov     ecx, 5
0x1801b9e41  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801b9e47  mov     ebx, [rsp+3C0h+var_378]
0x1801b9e4b  mov     edi, 1
0x1801b9e50  mov     [rsp+3C0h+var_35C], ebx
0x1801b9e54  lea     edx, [rdi+2]
0x1801b9e57  test    eax, eax
0x1801b9e59  jnz     loc_1801B9FA8
0x1801b9e5f  mov     esi, r13d
0x1801b9e62  mov     r12d, r13d
0x1801b9e65  mov     r15d, r13d
0x1801b9e68  mov     rcx, [rsp+3C0h+var_368]
0x1801b9e6d  cmp     [rcx+2], dx
0x1801b9e71  jnz     loc_1801B9F3F
0x1801b9e77  mov     edx, [rcx+14h]
0x1801b9e7a  mov     eax, edx
0x1801b9e7c  and     eax, 6050000h
0x1801b9e81  cmp     eax, 4000000h
0x1801b9e86  jnz     loc_1801B9F3F
0x1801b9e8c  mov     eax, [rcx+50h]
0x1801b9e8f  add     r12d, edi
0x1801b9e92  cmp     [r14+70h], eax
0x1801b9e96  jz      short loc_1801B9EAD
0x1801b9e98  test    byte ptr [r14+74h], 8
0x1801b9e9d  jnz     loc_1801B9F3F
0x1801b9ea3  test    byte ptr [rcx+4Ch], 8
0x1801b9ea7  jnz     loc_1801B9F3F
0x1801b9ead  xor     edx, ebx
0x1801b9eaf  bt      edx, 1Bh
0x1801b9eb3  jb      loc_1801B9F3F
0x1801b9eb9  mov     eax, [r14+140h]
0x1801b9ec0  cmp     [rcx+48h], eax
0x1801b9ec3  jnz     short loc_1801B9F3F
0x1801b9ec5  cmp     dword ptr [rcx+54h], 0
0x1801b9ec9  jnz     short loc_1801B9F3F
0x1801b9ecb  mov     ecx, [rcx+10h]; unsigned int
0x1801b9ece  call    ?LCIEIsProcessAlive@@YA_NK@Z; LCIEIsProcessAlive(ulong)
0x1801b9ed3  test    al, al
0x1801b9ed5  jz      short loc_1801B9F3F
0x1801b9ed7  mov     rax, [rsp+3C0h+var_368]
0x1801b9edc  mov     ecx, [rax+40h]
0x1801b9edf  test    dil, cl
0x1801b9ee2  jnz     short loc_1801B9F3F
0x1801b9ee4  cmp     r13d, 18h
0x1801b9ee8  jnb     short loc_1801B9F3F
0x1801b9eea  mov     rcx, [rsp+3C0h+var_368]
0x1801b9eef  mov     r9d, 0FFFh
0x1801b9ef5  mov     r8d, [rsp+3C0h+var_384]
0x1801b9efa  mov     eax, r13d
0x1801b9efd  lea     rdx, [rax+rax*2]
0x1801b9f01  mov     eax, [rcx+0Ch]
0x1801b9f04  mov     [rbp+rdx*8+2C0h+var_2A0], eax
0x1801b9f08  mov     eax, [rcx+14h]
0x1801b9f0b  mov     ecx, ebx
0x1801b9f0d  and     ecx, r9d
0x1801b9f10  mov     [rbp+rdx*8+2C0h+var_2A4], r8d
0x1801b9f15  and     eax, r9d
0x1801b9f18  mov     [rbp+rdx*8+2C0h+var_2B0], 0
0x1801b9f21  mov     [rbp+rdx*8+2C0h+var_29C], 0
0x1801b9f26  cmp     eax, ecx
0x1801b9f28  jnz     short loc_1801B9F2E
0x1801b9f2a  add     esi, edi
0x1801b9f2c  jmp     short loc_1801B9F31
0x1801b9f2e  add     r15d, edi
0x1801b9f31  cmp     eax, ecx
0x1801b9f33  setz    al
0x1801b9f36  add     r13d, edi
0x1801b9f39  mov     [rbp+rdx*8+2C0h+var_2A8], al
0x1801b9f3d  jmp     short loc_1801B9F44
0x1801b9f3f  mov     r8d, [rsp+3C0h+var_384]
0x1801b9f44  mov     ecx, r8d
0x1801b9f47  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801b9f4d  lea     rax, [rsp+3C0h+var_368]
0x1801b9f52  mov     [rsp+3C0h+var_398], 0
0x1801b9f5b  lea     r9, [rsp+3C0h+var_384]
0x1801b9f60  mov     [rsp+3C0h+var_3A0], rax
0x1801b9f65  lea     r8, [rbp+2C0h+var_70]
0x1801b9f6c  mov     dl, 14h
0x1801b9f6e  mov     ecx, 6
0x1801b9f73  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801b9f79  mov     edx, 3
0x1801b9f7e  test    eax, eax
0x1801b9f80  jz      loc_1801B9E68
0x1801b9f86  mov     [rsp+3C0h+var_360], r15d
0x1801b9f8b  mov     r15, [rsp+3C0h+var_350]
0x1801b9f90  mov     [rsp+3C0h+var_36C], r12d
0x1801b9f95  mov     r12, [rsp+3C0h+var_348]
0x1801b9f9a  mov     [rsp+3C0h+var_370], esi
0x1801b9f9e  mov     rsi, [rsp+3C0h+var_358]
0x1801b9fa3  mov     [rsp+3C0h+var_390], r13d
0x1801b9fa8  mov     rax, [rbp+2C0h+var_340]
0x1801b9fac  cmp     byte ptr [rax+0Fh], 0
0x1801b9fb0  jz      short loc_1801B9FF4
0x1801b9fb2  xor     edx, edx; unsigned int *
0x1801b9fb4  mov     [rsp+3C0h+var_388], 0
0x1801b9fbc  lea     rcx, [rsp+3C0h+var_388]; unsigned int *
0x1801b9fc1  call    ?LCIELogonFrameProcesses_GetLogonSessionCounts@@YAXPEAK0@Z; LCIELogonFrameProcesses_GetLogonSessionCounts(ulong *,ulong *)
0x1801b9fc6  call    ?LCIEMaxTabProcessesInLogonSession@@YAKXZ; LCIEMaxTabProcessesInLogonSession(void)
0x1801b9fcb  cmp     [rsp+3C0h+var_388], eax
0x1801b9fcf  jnb     short loc_1801B9FF4
0x1801b9fd1  cmp     [rsp+3C0h+var_36C], 18h
0x1801b9fd6  jnb     short loc_1801B9FF4
0x1801b9fd8  or      ebx, 5000h
0x1801b9fde  mov     [r15], ebx
0x1801b9fe1  mov     dword ptr [r12], 0
0x1801b9fe9  mov     dword ptr [rsi], 0
0x1801b9fef  jmp     loc_1801B9DC4
0x1801b9ff4  mov     ecx, [rsp+3C0h+var_370]
0x1801b9ff8  xor     r10d, r10d
0x1801b9ffb  mov     [rsp+3C0h+var_388], r10d
0x1801ba000  test    ecx, ecx
0x1801ba002  jz      loc_1801BA352
0x1801ba008  call    cs:__imp_GetCurrentProcessId
0x1801ba00e  mov     [rsp+3C0h+var_398], 0
0x1801ba017  lea     r9, [rsp+3C0h+var_384]
0x1801ba01c  mov     r12d, eax
0x1801ba01f  lea     r8, [rbp+2C0h+var_70]
0x1801ba026  lea     rax, [rsp+3C0h+var_368]
0x1801ba02b  mov     dl, 14h
0x1801ba02d  mov     ecx, 5
0x1801ba032  mov     [rsp+3C0h+var_3A0], rax
0x1801ba037  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801ba03d  test    eax, eax
0x1801ba03f  jnz     loc_1801BA124
0x1801ba045  mov     ebx, [rsp+3C0h+var_388]
0x1801ba049  mov     rax, [rsp+3C0h+var_368]
0x1801ba04e  mov     ecx, 203h
0x1801ba053  cmp     [rax+2], cx
0x1801ba057  jnz     loc_1801BA0DE
0x1801ba05d  mov     eax, [rax+10h]
0x1801ba060  cmp     eax, r12d
0x1801ba063  jz      short loc_1801BA0DE
0x1801ba065  xor     esi, esi
0x1801ba067  test    r13d, r13d
0x1801ba06a  jz      short loc_1801BA0DE
0x1801ba06c  cmp     esi, 18h
0x1801ba06f  jnb     short loc_1801BA0DA
0x1801ba071  mov     rax, [rsp+3C0h+var_368]
0x1801ba076  lea     r14, [rsi+rsi*2]
0x1801ba07a  mov     ecx, [rbp+r14*8+2C0h+var_2A0]
0x1801ba07f  cmp     [rax+0Ch], ecx
0x1801ba082  jnz     short loc_1801BA0D3
0x1801ba084  mov     ecx, [rsp+3C0h+var_384]
0x1801ba088  lea     rax, [rsp+3C0h+var_378]
0x1801ba08d  xor     r15d, r15d
0x1801ba090  mov     [rsp+3C0h+var_3A0], rax
0x1801ba095  lea     r9, [rsp+3C0h+var_388]
0x1801ba09a  mov     [rsp+3C0h+var_388], r15d
0x1801ba09f  xor     r8d, r8d
0x1801ba0a2  mov     qword ptr [rsp+3C0h+var_378], r15
0x1801ba0a7  xor     edx, edx
0x1801ba0a9  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801ba0af  test    eax, eax
0x1801ba0b1  js      short loc_1801BA0BC
0x1801ba0b3  mov     r15, qword ptr [rsp+3C0h+var_378]
0x1801ba0b8  add     r15, 40h ; '@'
0x1801ba0bc  mov     eax, [r15]
0x1801ba0bf  bt      eax, 1Bh
0x1801ba0c3  jnb     short loc_1801BA0CC
0x1801ba0c5  add     dword ptr [rbp+r14*8+2C0h+var_2B0+4], edi
0x1801ba0ca  jmp     short loc_1801BA0D3
0x1801ba0cc  add     dword ptr [rbp+r14*8+2C0h+var_2B0], edi
0x1801ba0d1  add     ebx, edi
0x1801ba0d3  add     esi, edi
0x1801ba0d5  cmp     esi, r13d
0x1801ba0d8  jb      short loc_1801BA06C
0x1801ba0da  mov     [rsp+3C0h+var_388], ebx
0x1801ba0de  mov     ecx, [rsp+3C0h+var_384]
0x1801ba0e2  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801ba0e8  lea     rax, [rsp+3C0h+var_368]
0x1801ba0ed  mov     [rsp+3C0h+var_398], 0
0x1801ba0f6  lea     r9, [rsp+3C0h+var_384]
0x1801ba0fb  mov     [rsp+3C0h+var_3A0], rax
0x1801ba100  lea     r8, [rbp+2C0h+var_70]
0x1801ba107  mov     dl, 14h
0x1801ba109  mov     ecx, 6
0x1801ba10e  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1801ba114  test    eax, eax
0x1801ba116  jz      loc_1801BA049
0x1801ba11c  mov     ebx, [rsp+3C0h+var_35C]
0x1801ba120  mov     r14, [rbp+2C0h+var_330]
0x1801ba124  mov     ecx, [r14+0D8h]
0x1801ba12b  test    ecx, ecx
0x1801ba12d  jz      loc_1801BA1CD
0x1801ba133  lea     r8, [rsp+3C0h+var_38C]
0x1801ba138  mov     [rsp+3C0h+var_38C], 0
0x1801ba140  lea     rdx, [rsp+3C0h+var_378]
0x1801ba145  mov     [rsp+3C0h+var_378], 0
0x1801ba14d  call    cs:__imp_?IsoGetProcessAndManagerFromPid@@YAJKPEAK0@Z; IsoGetProcessAndManagerFromPid(ulong,ulong *,ulong *)
0x1801ba153  test    eax, eax
0x1801ba155  js      short loc_1801BA1CD
0x1801ba157  xor     esi, esi
0x1801ba159  test    r13d, r13d
0x1801ba15c  jz      short loc_1801BA1CD
0x1801ba15e  mov     r12, [rbp+2C0h+var_338]
0x1801ba162  lea     r15, [rsi+rsi*2]
0x1801ba166  cmp     [rbp+r15*8+2C0h+var_2A8], 0
0x1801ba16c  jz      short loc_1801BA1C6
0x1801ba16e  mov     r14d, [rbp+r15*8+2C0h+var_2A0]
0x1801ba173  cmp     r14d, [rsp+3C0h+var_378]
0x1801ba178  jnz     short loc_1801BA1C6
0x1801ba17a  xor     edx, edx; Val
0x1801ba17c  lea     rcx, [rbp+2C0h+var_320]; void *
0x1801ba180  lea     r8d, [rdx+70h]; Size
0x1801ba184  call    memset_0
0x1801ba189  lea     rdx, [rbp+2C0h+var_320]
0x1801ba18d  mov     ecx, r14d
0x1801ba190  call    cs:__imp_?IsoGetProcessData@@YAJKPEAU_IsoProcess@@@Z; IsoGetProcessData(ulong,_IsoProcess *)
0x1801ba196  test    eax, eax
0x1801ba198  js      short loc_1801BA1C6
0x1801ba19a  mov     [rbp+r15*8+2C0h+var_29C], dil
0x1801ba19f  mov     r9d, 32h ; '2'
0x1801ba1a5  mov     r15d, [rbp+r15*8+2C0h+var_2A4]
0x1801ba1aa  mov     r8d, edi
0x1801ba1ad  mov     edx, r15d
0x1801ba1b0  mov     [rsp+3C0h+var_3A0], r12
0x1801ba1b5  mov     ecx, r15d
0x1801ba1b8  call    cs:__imp_?IsoAddDependency@@YAJKKW4_IsoComponentDependencyFlags@@W4_BlockSuspendReason@@PEA_K@Z; IsoAddDependency(ulong,ulong,_IsoComponentDependencyFlags,_BlockSuspendReason,unsigned __int64 *)
0x1801ba1be  test    eax, eax
0x1801ba1c0  jns     loc_1801BA24C
0x1801ba1c6  add     esi, edi
0x1801ba1c8  cmp     esi, r13d
0x1801ba1cb  jb      short loc_1801BA162
0x1801ba1cd  xor     ecx, ecx
0x1801ba1cf  xor     r14d, r14d
0x1801ba1d2  xor     esi, esi
0x1801ba1d4  mov     [rsp+3C0h+var_378], ecx
  ... truncated ...
```
