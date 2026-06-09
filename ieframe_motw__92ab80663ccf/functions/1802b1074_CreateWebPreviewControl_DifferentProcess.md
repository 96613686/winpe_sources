# _CreateWebPreviewControl_DifferentProcess

- ea: `0x1802b1074`
- end: `0x1802b178a`
- name: `_CreateWebPreviewControl_DifferentProcess`
- size: `1814`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, __int64, __int64, struct IUnknown *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802b02b0`

## callees

- `0x180007010`
- `0x1800144d0`
- `0x180083c5c`
- `0x180084d74`
- `0x180094450`
- `0x18009ccb8`
- `0x1801caff4`
- `0x1802b0250`
- `0x1802b0f30`
- `0x1802b1074`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1802b1636`
- `KERNEL32!GetTickCount` at `0x1802b16d4`
- `KERNEL32!GetTickCount` at `0x1802b1636`
- `KERNEL32!GetTickCount` at `0x1802b16d4`
- `KERNEL32!CloseHandle` at `0x1802b173c`
- `KERNEL32!CloseHandle` at `0x1802b173c`
- `KERNEL32!GetCurrentThreadId` at `0x1802b10f7`
- `KERNEL32!GetCurrentThreadId` at `0x1802b10f7`
- `USER32!TranslateMessage` at `0x1802b1693`
- `USER32!TranslateMessage` at `0x1802b1693`
- `USER32!DispatchMessageW` at `0x1802b16a3`
- `USER32!DispatchMessageW` at `0x1802b16a3`
- `USER32!MsgWaitForMultipleObjects` at `0x1802b165f`
- `USER32!MsgWaitForMultipleObjects` at `0x1802b165f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b1211`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b1232`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b150e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b1211`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b1232`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b150e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1802b151e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1802b151e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802b172c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802b172c`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1802b1533`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1802b1533`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x1802b1468`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x1802b1468`
- `msIso!__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z` at `0x1802b13fd`
- `msIso!__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z` at `0x1802b13fd`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1802b126e`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1802b126e`
- `msIso!__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1802b11ce`
- `msIso!__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1802b11ce`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1802b11ef`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1802b11ef`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1802b1716`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1802b1716`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1802b1168`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1802b12a3`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1802b1168`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x1802b12a3`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x1802b1344`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x1802b1344`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x1802b1336`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x1802b1336`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1802b1758`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1802b1758`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1802b15ec`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1802b15ec`
- `msIso!__imp_?IsoGetAuthority@@YAKPEAK00@Z` at `0x1802b113d`
- `msIso!__imp_?IsoGetAuthority@@YAKPEAK00@Z` at `0x1802b113d`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1802b1120`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1802b1120`

## pseudocode

```c
__int64 __fastcall CreateWebPreviewControl_DifferentProcess(
        int a1,
        char *a2,
        struct IUnknown *a3,
        _OWORD *a4,
        int a5,
        int a6,
        int a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        struct IUnknown *a10,
        _QWORD *a11)
{
  char *v12; // rsi
  struct IUnknown *v13; // r15
  bool v14; // r13
  DWORD CurrentThreadId; // eax
  int Integrity; // eax
  int v17; // edi
  int v18; // r14d
  __int64 v19; // rdx
  __int64 v20; // rdx
  HRESULT NextArtifact; // ebx
  unsigned int v22; // ecx
  unsigned __int8 v23; // al
  char v24; // si
  int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  struct IUnknown *v28; // rcx
  int v29; // r14d
  _QWORD *v30; // rdi
  __int64 v31; // rcx
  int v32; // eax
  DWORD TickCount; // esi
  DWORD v34; // eax
  _QWORD *v35; // rax
  DWORD dwWakeMask[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+50h] [rbp-B0h] BYREF
  char *v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v41; // [rsp+64h] [rbp-9Ch] BYREF
  struct IUnknown *v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43[2]; // [rsp+70h] [rbp-90h] BYREF
  PWSTR AppID; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v47; // [rsp+90h] [rbp-70h]
  HANDLE pHandles; // [rsp+98h] [rbp-68h] BYREF
  _OWORD *v49; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v50; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v51; // [rsp+B0h] [rbp-50h]
  MSG Msg; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v53[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v54; // [rsp+F2h] [rbp-Eh]
  unsigned int v55; // [rsp+F8h] [rbp-8h]
  int v56; // [rsp+100h] [rbp+0h]
  int v57; // [rsp+108h] [rbp+8h]
  int v58; // [rsp+254h] [rbp+154h]
  int v59; // [rsp+258h] [rbp+158h]
  __int16 v60; // [rsp+25Eh] [rbp+15Eh]
  unsigned int v61; // [rsp+288h] [rbp+188h]
  int v62; // [rsp+28Ch] [rbp+18Ch]
  _BYTE v63[32]; // [rsp+370h] [rbp+270h] BYREF

  v12 = a2;
  v13 = a10;
  v50 = a8;
  v47 = a11;
  v49 = a4;
  v42 = a3;
  v39 = a2;
  v51 = a9;
  v14 = LCIEUnifiedFrame();
  v38 = 0;
  v46 = 0;
  v43[0] = 0;
  v40 = 0;
  CurrentThreadId = GetCurrentThreadId();
  GetIESessionFromFrameThread(CurrentThreadId, v43, &v40);
  Integrity = IsoGetIntegrity((unsigned int)(a1 != 0) + 2);
  v45 = 0;
  v17 = Integrity;
  LOWORD(v18) = 0;
  IsoGetAuthority(0, &v45, 0);
  LOBYTE(v19) = 6;
  NextArtifact = IsoGetNextArtifact(1, v19, v63, &v38, &v46, 0);
  if ( NextArtifact )
  {
    v22 = v38;
    goto LABEL_26;
  }
  while ( 1 )
  {
    v22 = v38;
    if ( v38 == v45 )
      goto LABEL_21;
    if ( !v14 )
    {
      v20 = v43[0];
      if ( v43[0] == *(_DWORD *)(v46 + 44) || (v40 & 8) == 0 && (*(_BYTE *)(v46 + 40) & 8) == 0 )
        goto LABEL_23;
      goto LABEL_21;
    }
    AppID = 0;
    if ( (int)IsoLockArtifact(v38, 6u, (struct _IsoArtifact **)&AppID, 0) < 0 )
      goto LABEL_21;
    v18 = *((_DWORD *)AppID + 5);
    IsoUnlockArtifact(v38);
    v23 = v18 & 0x7F;
    v24 = v18 & 0x7F;
    if ( !a1 )
      break;
    if ( v23 < 0x7Cu && (!(unsigned __int8)IEConfiguration_GetBool(268435519) || v24 != 122) )
      goto LABEL_17;
LABEL_21:
    LOBYTE(v20) = 6;
    NextArtifact = IsoGetNextArtifact(2, v20, v63, &v38, &v46, 0);
    if ( NextArtifact )
      goto LABEL_22;
  }
  if ( v23 < 0x7Cu && (!(unsigned __int8)IEConfiguration_GetBool(268435519) || v24 != 122) )
    goto LABEL_21;
LABEL_17:
  if ( v43[0] != *(_DWORD *)(v46 + 44) && ((v40 & 8) != 0 || (*(_BYTE *)(v46 + 40) & 8) != 0)
    || (int)IsoGetArtifactAddress(v38, 6u, 0, 0) < 0 )
  {
    goto LABEL_21;
  }
LABEL_22:
  v22 = v38;
LABEL_23:
  v12 = v39;
  if ( !NextArtifact )
  {
    v25 = v18 & 0xFFF | 0x4000;
    goto LABEL_29;
  }
LABEL_26:
  if ( NextArtifact == 1 )
  {
    v22 = 0;
    v38 = 0;
    v25 = v17 | 0x5000;
    goto LABEL_29;
  }
  v25 = 0;
  if ( NextArtifact >= 0 )
  {
LABEL_29:
    v26 = v25 | v17;
    v41 = 0;
    v39 = 0;
    if ( (v26 & 0xF000) == 0x5000 )
      v27 = IsoAllocSharedMemoryPerFlags(v26, &v41, 0x2140u, (void **)&v39);
    else
      v27 = IsoAllocSharedMemory(v22, &v41, 0x2140u, (void **)&v39);
    NextArtifact = v27;
    if ( v27 >= 0 )
    {
      pHandles = (HANDLE)CreateOpenNamedSyncEventForPreview(v12, 1);
      if ( !pHandles )
      {
        NextArtifact = -2147467259;
        goto LABEL_74;
      }
      v28 = v42;
      v29 = 1;
      *(_QWORD *)v39 = v12;
      *((_QWORD *)v39 + 1) = v28;
      *((_OWORD *)v39 + 1) = *v49;
      *((_DWORD *)v39 + 8) = a5;
      *((_DWORD *)v39 + 9) = a6;
      *((_DWORD *)v39 + 10) = a7;
      memset_0(v39 + 8384, 0, 0x80u);
      *((_DWORD *)v39 + 2095) = 0;
      if ( !a10 )
        goto LABEL_78;
      v42 = 0;
      if ( !LCIEForceSecurityProxiesFromFlags(v26)
        || (NextArtifact = CLCIE_IIDProxy_Master::MakeMaster(1u, &IID_IWebPreviewCallback, &v42, a10), NextArtifact >= 0) )
      {
        if ( v42 )
          v13 = v42;
        NextArtifact = LCIEMarshalInterfaceIntoBufferForHandle(
                         v26,
                         v38,
                         &IID_IWebPreviewCallback,
                         v13,
                         (unsigned __int8 *)v39 + 8384,
                         0x80u,
                         (unsigned int *)v39 + 2095);
      }
      if ( v42 )
        ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
      if ( NextArtifact >= 0 )
      {
LABEL_78:
        if ( !v50 )
        {
          *((_WORD *)v39 + 22) = 0;
          goto LABEL_47;
        }
        NextArtifact = StringCchCopyW((unsigned __int16 *)v39 + 22, 0x824u, v50);
        if ( NextArtifact >= 0 )
        {
LABEL_47:
          if ( v51 )
          {
            NextArtifact = StringCchCopyW((unsigned __int16 *)v39 + 2106, 0x824u, v51);
            if ( NextArtifact >= 0 )
              goto LABEL_51;
          }
          else
          {
            *((_WORD *)v39 + 2106) = 0;
LABEL_51:
            AppID = 0;
            if ( (unsigned __int8)IEConfiguration_GetBool(268435465) || IsDualEngineProcess() )
              NextArtifact = GetCurrentProcessExplicitAppUserModelID(&AppID);
            if ( NextArtifact >= 0 )
            {
              LODWORD(v42) = 0;
              memset_0(v53, 0, 0x278u);
              v61 = v41;
              v55 = v38;
              v53[0] = 20;
              v54 = 632;
              v62 = 112;
              v59 = 3;
              v56 = 105;
              v58 = 0;
              v60 = 1;
              v57 = 0;
              IESessionSetTabProcessCompCreDat(v43[0], v40, (struct _IsoCreationComponentData *)v53);
              *(_QWORD *)v43 = 0;
              NextArtifact = IsoCreateComponentByCreDat(v26, v53, AppID, &v42, 0, 0, 0, v43, 0);
              if ( NextArtifact >= 0 )
              {
                v30 = operator new(0x20u);
                if ( v30 )
                {
                  v31 = *(_QWORD *)v43;
                  v32 = (int)v42;
                  *v30 = &CWebPreviewControl_LCIEProxy::`vftable';
                  v30[2] = v31;
                  *((_DWORD *)v30 + 2) = v32;
                  v30[3] = 0;
                  TickCount = GetTickCount();
                  while ( 1 )
                  {
                    v34 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0x3E8u, 0x1CFFu);
                    if ( (v34 & 0xFFFFFF7F) == 0 )
                      break;
                    if ( ((v34 - 1) & 0xFFFFFF7F) == 0 )
                    {
                      memset(&Msg, 0, sizeof(Msg));
                      while ( 1 )
                      {
                        dwWakeMask[0] = 1;
                        if ( !(unsigned int)IEPeekMessage(&Msg, 0, 0, 0, *(_QWORD *)dwWakeMask, 1) )
                          break;
                        TranslateMessage(&Msg);
                        DispatchMessageW(&Msg);
                      }
                      if ( Msg.message != 18 && GetTickCount() - TickCount < 0x3E8 )
                        continue;
                    }
                    v35 = v47;
                    goto LABEL_66;
                  }
                  v35 = v47;
                  v29 = 0;
                  *v47 = v30;
LABEL_66:
                  if ( !*v35 )
                  {
                    NextArtifact = -2147467259;
                    CWebPreviewControl_LCIEProxy::`scalar deleting destructor'((CWebPreviewControl_LCIEProxy *)v30, 1u);
                  }
                }
                else
                {
                  IsoRemoveArtifact((unsigned int)v42);
                  NextArtifact = -2147024882;
                }
              }
            }
            CoTaskMemFree(AppID);
          }
        }
      }
      CloseHandle(pHandles);
      if ( v29 )
LABEL_74:
        IsoFreeSharedMemory(v41);
    }
  }
  return (unsigned int)NextArtifact;
}

```

## disassembly

```asm
0x1802b1074  push    rbp
0x1802b1076  push    rbx
0x1802b1077  push    rsi
0x1802b1078  push    rdi
0x1802b1079  push    r12
0x1802b107b  push    r13
0x1802b107d  push    r14
0x1802b107f  push    r15
0x1802b1081  lea     rbp, [rsp-2A8h]
0x1802b1089  sub     rsp, 3A8h
0x1802b1090  mov     rax, cs:__security_cookie
0x1802b1097  xor     rax, rsp
0x1802b109a  mov     [rbp+2E0h+var_50], rax
0x1802b10a1  mov     rax, [rbp+2E0h+arg_38]
0x1802b10a8  mov     r12d, ecx
0x1802b10ab  mov     rcx, [rbp+2E0h+arg_40]
0x1802b10b2  mov     rsi, rdx
0x1802b10b5  mov     r15, [rbp+2E0h+arg_48]
0x1802b10bc  mov     [rbp+2E0h+var_338], rax
0x1802b10c0  mov     rax, [rbp+2E0h+arg_50]
0x1802b10c7  mov     [rbp+2E0h+var_350], rax
0x1802b10cb  mov     [rbp+2E0h+var_340], r9
0x1802b10cf  mov     [rsp+3E0h+var_378], r8
0x1802b10d4  mov     [rsp+3E0h+var_388], rdx
0x1802b10d9  mov     [rbp+2E0h+var_330], rcx
0x1802b10dd  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x1802b10e2  xor     ebx, ebx
0x1802b10e4  mov     r13b, al
0x1802b10e7  mov     [rsp+3E0h+var_390], ebx
0x1802b10eb  mov     [rbp+2E0h+var_358], rbx
0x1802b10ef  mov     [rsp+3E0h+var_370], ebx
0x1802b10f3  mov     [rsp+3E0h+var_380], ebx
0x1802b10f7  call    cs:__imp_GetCurrentThreadId
0x1802b10fe  nop     dword ptr [rax+rax+00h]
0x1802b1103  mov     ecx, eax; unsigned int
0x1802b1105  lea     r8, [rsp+3E0h+var_380]; unsigned int *
0x1802b110a  lea     rdx, [rsp+3E0h+var_370]; unsigned int *
0x1802b110f  call    ?GetIESessionFromFrameThread@@YAJKPEAK0@Z; GetIESessionFromFrameThread(ulong,ulong *,ulong *)
0x1802b1114  mov     ecx, r12d
0x1802b1117  neg     ecx
0x1802b1119  sbb     ecx, ecx
0x1802b111b  neg     ecx
0x1802b111d  add     ecx, 2
0x1802b1120  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1802b1127  nop     dword ptr [rax+rax+00h]
0x1802b112c  xor     r8d, r8d
0x1802b112f  mov     [rbp+2E0h+var_360], ebx
0x1802b1132  lea     rdx, [rbp+2E0h+var_360]
0x1802b1136  xor     ecx, ecx
0x1802b1138  mov     edi, eax
0x1802b113a  mov     r14d, ebx
0x1802b113d  call    cs:__imp_?IsoGetAuthority@@YAKPEAK00@Z; IsoGetAuthority(ulong *,ulong *,ulong *)
0x1802b1144  nop     dword ptr [rax+rax+00h]
0x1802b1149  lea     rax, [rbp+2E0h+var_358]
0x1802b114d  mov     [rsp+3E0h+var_3B8], rbx
0x1802b1152  lea     r9, [rsp+3E0h+var_390]
0x1802b1157  mov     qword ptr [rsp+3E0h+dwWakeMask], rax
0x1802b115c  lea     r8, [rbp+2E0h+var_70]
0x1802b1163  mov     dl, 6
0x1802b1165  lea     ecx, [rbx+1]
0x1802b1168  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1802b116f  nop     dword ptr [rax+rax+00h]
0x1802b1174  mov     ebx, eax
0x1802b1176  test    eax, eax
0x1802b1178  jnz     loc_1802B12DD
0x1802b117e  mov     ecx, [rsp+3E0h+var_390]
0x1802b1182  cmp     ecx, [rbp+2E0h+var_360]
0x1802b1185  jz      loc_1802B127E
0x1802b118b  test    r13b, r13b
0x1802b118e  jnz     short loc_1802B11BB
0x1802b1190  mov     rax, [rbp+2E0h+var_358]
0x1802b1194  mov     edx, [rsp+3E0h+var_370]
0x1802b1198  cmp     edx, [rax+2Ch]
0x1802b119b  jz      loc_1802B12BD
0x1802b11a1  test    byte ptr [rsp+3E0h+var_380], 8
0x1802b11a6  jnz     loc_1802B127E
0x1802b11ac  test    byte ptr [rax+28h], 8
0x1802b11b0  jz      loc_1802B12BD
0x1802b11b6  jmp     loc_1802B127E
0x1802b11bb  xor     r9d, r9d
0x1802b11be  mov     [rsp+3E0h+AppID], 0
0x1802b11c7  lea     r8, [rsp+3E0h+AppID]
0x1802b11cc  mov     dl, 6
0x1802b11ce  call    cs:__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoLockArtifact(ulong,uchar,_IsoArtifact * *,ulong *)
0x1802b11d5  nop     dword ptr [rax+rax+00h]
0x1802b11da  test    eax, eax
0x1802b11dc  js      loc_1802B127E
0x1802b11e2  mov     rax, [rsp+3E0h+AppID]
0x1802b11e7  mov     ecx, [rsp+3E0h+var_390]
0x1802b11eb  mov     r14d, [rax+14h]
0x1802b11ef  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1802b11f6  nop     dword ptr [rax+rax+00h]
0x1802b11fb  mov     al, r14b
0x1802b11fe  and     al, 7Fh
0x1802b1200  mov     sil, al
0x1802b1203  test    r12d, r12d
0x1802b1206  jz      short loc_1802B1229
0x1802b1208  cmp     al, 7Ch ; '|'
0x1802b120a  jnb     short loc_1802B127E
0x1802b120c  mov     ecx, 1000003Fh
0x1802b1211  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1802b1218  nop     dword ptr [rax+rax+00h]
0x1802b121d  test    al, al
0x1802b121f  jz      short loc_1802B1248
0x1802b1221  cmp     sil, 7Ah ; 'z'
0x1802b1225  jnz     short loc_1802B1248
0x1802b1227  jmp     short loc_1802B127E
0x1802b1229  cmp     al, 7Ch ; '|'
0x1802b122b  jnb     short loc_1802B1248
0x1802b122d  mov     ecx, 1000003Fh
0x1802b1232  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1802b1239  nop     dword ptr [rax+rax+00h]
0x1802b123e  test    al, al
0x1802b1240  jz      short loc_1802B127E
0x1802b1242  cmp     sil, 7Ah ; 'z'
0x1802b1246  jnz     short loc_1802B127E
0x1802b1248  mov     rax, [rbp+2E0h+var_358]
0x1802b124c  mov     ecx, [rsp+3E0h+var_370]
0x1802b1250  cmp     ecx, [rax+2Ch]
0x1802b1253  jz      short loc_1802B1262
0x1802b1255  test    byte ptr [rsp+3E0h+var_380], 8
0x1802b125a  jnz     short loc_1802B127E
0x1802b125c  test    byte ptr [rax+28h], 8
0x1802b1260  jnz     short loc_1802B127E
0x1802b1262  mov     ecx, [rsp+3E0h+var_390]
0x1802b1266  xor     r9d, r9d
0x1802b1269  xor     r8d, r8d
0x1802b126c  mov     dl, 6
0x1802b126e  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x1802b1275  nop     dword ptr [rax+rax+00h]
0x1802b127a  test    eax, eax
0x1802b127c  jns     short loc_1802B12B9
0x1802b127e  lea     rax, [rbp+2E0h+var_358]
0x1802b1282  mov     [rsp+3E0h+var_3B8], 0
0x1802b128b  lea     r9, [rsp+3E0h+var_390]
0x1802b1290  mov     qword ptr [rsp+3E0h+dwWakeMask], rax
0x1802b1295  lea     r8, [rbp+2E0h+var_70]
0x1802b129c  mov     dl, 6
0x1802b129e  mov     ecx, 2
0x1802b12a3  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x1802b12aa  nop     dword ptr [rax+rax+00h]
0x1802b12af  mov     ebx, eax
0x1802b12b1  test    eax, eax
0x1802b12b3  jz      loc_1802B117E
0x1802b12b9  mov     ecx, [rsp+3E0h+var_390]
0x1802b12bd  mov     rsi, [rsp+3E0h+var_388]
0x1802b12c2  xor     r12d, r12d
0x1802b12c5  test    ebx, ebx
0x1802b12c7  jnz     short loc_1802B12E4
0x1802b12c9  movzx   eax, r14w
0x1802b12cd  lea     r13d, [r12+1]
0x1802b12d2  and     eax, 0FFFh
0x1802b12d7  bts     eax, 0Eh
0x1802b12db  jmp     short loc_1802B130A
0x1802b12dd  mov     ecx, [rsp+3E0h+var_390]
0x1802b12e1  xor     r12d, r12d
0x1802b12e4  mov     r13d, 1
0x1802b12ea  cmp     ebx, r13d
0x1802b12ed  jnz     short loc_1802B12FF
0x1802b12ef  mov     ecx, r12d
0x1802b12f2  mov     eax, edi
0x1802b12f4  mov     [rsp+3E0h+var_390], ecx
0x1802b12f8  or      eax, 5000h
0x1802b12fd  jmp     short loc_1802B130A
0x1802b12ff  mov     eax, r12d
0x1802b1302  test    ebx, ebx
0x1802b1304  js      loc_1802B1764
0x1802b130a  or      edi, eax
0x1802b130c  mov     [rsp+3E0h+var_37C], r12d
0x1802b1311  mov     eax, edi
0x1802b1313  mov     [rsp+3E0h+var_388], r12
0x1802b1318  and     eax, 0F000h
0x1802b131d  lea     r9, [rsp+3E0h+var_388]
0x1802b1322  lea     rdx, [rsp+3E0h+var_37C]
0x1802b1327  mov     r8d, 2140h
0x1802b132d  cmp     eax, 5000h
0x1802b1332  jnz     short loc_1802B1344
0x1802b1334  mov     ecx, edi
0x1802b1336  call    cs:__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z; IsoAllocSharedMemoryPerFlags(ulong,ulong *,ulong,void * *)
0x1802b133d  nop     dword ptr [rax+rax+00h]
0x1802b1342  jmp     short loc_1802B1350
0x1802b1344  call    cs:__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z; IsoAllocSharedMemory(ulong,ulong *,ulong,void * *)
0x1802b134b  nop     dword ptr [rax+rax+00h]
0x1802b1350  mov     ebx, eax
0x1802b1352  test    eax, eax
0x1802b1354  js      loc_1802B1764
0x1802b135a  mov     edx, r13d
0x1802b135d  mov     rcx, rsi
0x1802b1360  call    _CreateOpenNamedSyncEventForPreview
0x1802b1365  mov     [rbp+2E0h+pHandles], rax
0x1802b1369  test    rax, rax
0x1802b136c  jz      loc_1802B174F
0x1802b1372  mov     rax, [rsp+3E0h+var_388]
0x1802b1377  xor     edx, edx; Val
0x1802b1379  mov     rcx, [rsp+3E0h+var_378]
0x1802b137e  mov     r14d, r13d
0x1802b1381  mov     [rax], rsi
0x1802b1384  mov     esi, 80h
0x1802b1389  mov     rax, [rsp+3E0h+var_388]
0x1802b138e  mov     r8d, esi; Size
0x1802b1391  mov     [rax+8], rcx
0x1802b1395  mov     ecx, [rbp+2E0h+arg_20]
0x1802b139b  mov     rax, [rbp+2E0h+var_340]
0x1802b139f  movups  xmm0, xmmword ptr [rax]
0x1802b13a2  mov     rax, [rsp+3E0h+var_388]
0x1802b13a7  movdqu  xmmword ptr [rax+10h], xmm0
0x1802b13ac  mov     rax, [rsp+3E0h+var_388]
0x1802b13b1  mov     [rax+20h], ecx
0x1802b13b4  mov     rax, [rsp+3E0h+var_388]
0x1802b13b9  mov     ecx, [rbp+2E0h+arg_28]
0x1802b13bf  mov     [rax+24h], ecx
0x1802b13c2  mov     rax, [rsp+3E0h+var_388]
0x1802b13c7  mov     ecx, [rbp+2E0h+arg_30]
0x1802b13cd  mov     [rax+28h], ecx
0x1802b13d0  mov     rcx, [rsp+3E0h+var_388]
0x1802b13d5  add     rcx, 20C0h; void *
0x1802b13dc  call    memset_0
0x1802b13e1  mov     rax, [rsp+3E0h+var_388]
0x1802b13e6  mov     [rax+20BCh], r12d
0x1802b13ed  test    r15, r15
0x1802b13f0  jz      loc_1802B1494
0x1802b13f6  mov     ecx, edi
0x1802b13f8  mov     [rsp+3E0h+var_378], r12
0x1802b13fd  call    cs:__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z; LCIEForceSecurityProxiesFromFlags(ulong)
0x1802b1404  nop     dword ptr [rax+rax+00h]
0x1802b1409  test    eax, eax
0x1802b140b  jz      short loc_1802B142A
0x1802b140d  mov     r9, r15; struct IUnknown *
0x1802b1410  lea     r8, [rsp+3E0h+var_378]; struct IUnknown **
0x1802b1415  lea     rdx, IID_IWebPreviewCallback; struct _GUID *
0x1802b141c  mov     ecx, r13d; unsigned int
0x1802b141f  call    ?MakeMaster@CLCIE_IIDProxy_Master@@SAJKAEBU_GUID@@PEAPEAUIUnknown@@PEAU3@@Z; CLCIE_IIDProxy_Master::MakeMaster(ulong,_GUID const &,IUnknown * *,IUnknown *)
0x1802b1424  mov     ebx, eax
0x1802b1426  test    eax, eax
0x1802b1428  js      short loc_1802B1476
0x1802b142a  mov     rax, [rsp+3E0h+var_388]
0x1802b142f  lea     r8, IID_IWebPreviewCallback
0x1802b1436  lea     rcx, [rax+20BCh]
0x1802b143d  lea     rdx, [rax+20C0h]
0x1802b1444  mov     [rsp+3E0h+var_3B0], rcx
0x1802b1449  mov     rax, [rsp+3E0h+var_378]
0x1802b144e  mov     ecx, edi
0x1802b1450  test    rax, rax
0x1802b1453  mov     [rsp+3E0h+var_3B8], rsi
0x1802b1458  mov     qword ptr [rsp+3E0h+dwWakeMask], rdx
0x1802b145d  mov     edx, [rsp+3E0h+var_390]
0x1802b1461  cmovnz  r15, rax
0x1802b1465  mov     r9, r15
0x1802b1468  call    cs:__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z; LCIEMarshalInterfaceIntoBufferForHandle(ulong,ulong,_GUID const &,IUnknown *,uchar *,unsigned __int64,ulong *)
0x1802b146f  nop     dword ptr [rax+rax+00h]
0x1802b1474  mov     ebx, eax
0x1802b1476  mov     rcx, [rsp+3E0h+var_378]
0x1802b147b  test    rcx, rcx
0x1802b147e  jz      short loc_1802B148C
0x1802b1480  mov     rax, [rcx]
0x1802b1483  mov     rax, [rax+10h]
0x1802b1487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b148c  test    ebx, ebx
0x1802b148e  js      loc_1802B1738
0x1802b1494  mov     rax, [rbp+2E0h+var_338]
0x1802b1498  mov     esi, 824h
0x1802b149d  test    rax, rax
0x1802b14a0  jz      short loc_1802B14C1
0x1802b14a2  mov     rcx, [rsp+3E0h+var_388]
0x1802b14a7  mov     r8, rax; unsigned __int16 *
0x1802b14aa  add     rcx, 2Ch ; ','; unsigned __int16 *
0x1802b14ae  mov     edx, esi; unsigned __int64
0x1802b14b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802b14b5  mov     ebx, eax
0x1802b14b7  test    eax, eax
0x1802b14b9  js      loc_1802B1738
0x1802b14bf  jmp     short loc_1802B14CB
0x1802b14c1  mov     rax, [rsp+3E0h+var_388]
0x1802b14c6  mov     [rax+2Ch], r12w
0x1802b14cb  mov     rax, [rbp+2E0h+var_330]
0x1802b14cf  test    rax, rax
0x1802b14d2  jz      short loc_1802B14F7
0x1802b14d4  mov     rcx, [rsp+3E0h+var_388]
0x1802b14d9  mov     r8, rax; unsigned __int16 *
0x1802b14dc  add     rcx, 1074h; unsigned __int16 *
0x1802b14e3  mov     rdx, rsi; unsigned __int64
0x1802b14e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802b14eb  mov     ebx, eax
0x1802b14ed  test    eax, eax
0x1802b14ef  js      loc_1802B1738
0x1802b14f5  jmp     short loc_1802B1504
0x1802b14f7  mov     rax, [rsp+3E0h+var_388]
0x1802b14fc  mov     [rax+1074h], r12w
0x1802b1504  mov     ecx, 10000009h
0x1802b1509  mov     [rsp+3E0h+AppID], r12
0x1802b150e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1802b1515  nop     dword ptr [rax+rax+00h]
0x1802b151a  test    al, al
0x1802b151c  jnz     short loc_1802B152E
0x1802b151e  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1802b1525  nop     dword ptr [rax+rax+00h]
0x1802b152a  test    al, al
0x1802b152c  jz      short loc_1802B1541
0x1802b152e  lea     rcx, [rsp+3E0h+AppID]; AppID
0x1802b1533  call    cs:__imp_GetCurrentProcessExplicitAppUserModelID
  ... truncated ...
```
