# _CreateWebPreviewControl_DifferentProcess

- ea: `0x18028eb00`
- end: `0x18028f16f`
- name: `_CreateWebPreviewControl_DifferentProcess`
- size: `1647`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, __int64, __int64, struct IUnknown *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18028dea0`

## callees

- `0x180011230`
- `0x18002acc0`
- `0x18007dc20`
- `0x18007f160`
- `0x18008d774`
- `0x1800959cc`
- `0x1801b5614`
- `0x18028de40`
- `0x18028e9f0`
- `0x18028eb00`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18028f056`
- `KERNEL32!GetTickCount` at `0x18028f0d8`
- `KERNEL32!GetTickCount` at `0x18028f056`
- `KERNEL32!GetTickCount` at `0x18028f0d8`
- `KERNEL32!CloseHandle` at `0x18028f12e`
- `KERNEL32!CloseHandle` at `0x18028f12e`
- `KERNEL32!GetCurrentThreadId` at `0x18028eb83`
- `KERNEL32!GetCurrentThreadId` at `0x18028eb83`
- `USER32!TranslateMessage` at `0x18028f0a3`
- `USER32!TranslateMessage` at `0x18028f0a3`
- `USER32!DispatchMessageW` at `0x18028f0ad`
- `USER32!DispatchMessageW` at `0x18028f0ad`
- `USER32!MsgWaitForMultipleObjects` at `0x18028f079`
- `USER32!MsgWaitForMultipleObjects` at `0x18028f079`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18028ec79`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18028ec94`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18028ef46`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18028ec79`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18028ec94`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18028ef46`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18028ef50`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18028ef50`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18028f124`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18028f124`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x18028ef5f`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x18028ef5f`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18028eea6`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18028eea6`
- `msIso!__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z` at `0x18028ee41`
- `msIso!__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z` at `0x18028ee41`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18028ecca`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18028ecca`
- `msIso!__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18028ec42`
- `msIso!__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18028ec42`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18028ec5d`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18028ec5d`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18028f114`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18028f114`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x18028ebe2`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x18028ecf9`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x18028ebe2`
- `msIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z` at `0x18028ecf9`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x18028ed8e`
- `msIso!__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z` at `0x18028ed8e`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x18028ed86`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x18028ed86`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x18028f144`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x18028f144`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18028f012`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18028f012`
- `msIso!__imp_?IsoGetAuthority@@YAKPEAK00@Z` at `0x18028ebbd`
- `msIso!__imp_?IsoGetAuthority@@YAKPEAK00@Z` at `0x18028ebbd`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18028eba6`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18028eba6`

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
0x18028eb00  push    rbp
0x18028eb02  push    rbx
0x18028eb03  push    rsi
0x18028eb04  push    rdi
0x18028eb05  push    r12
0x18028eb07  push    r13
0x18028eb09  push    r14
0x18028eb0b  push    r15
0x18028eb0d  lea     rbp, [rsp-2A8h]
0x18028eb15  sub     rsp, 3A8h
0x18028eb1c  mov     rax, cs:__security_cookie
0x18028eb23  xor     rax, rsp
0x18028eb26  mov     [rbp+2E0h+var_50], rax
0x18028eb2d  mov     rax, [rbp+2E0h+arg_38]
0x18028eb34  mov     r12d, ecx
0x18028eb37  mov     rcx, [rbp+2E0h+arg_40]
0x18028eb3e  mov     rsi, rdx
0x18028eb41  mov     r15, [rbp+2E0h+arg_48]
0x18028eb48  mov     [rbp+2E0h+var_338], rax
0x18028eb4c  mov     rax, [rbp+2E0h+arg_50]
0x18028eb53  mov     [rbp+2E0h+var_350], rax
0x18028eb57  mov     [rbp+2E0h+var_340], r9
0x18028eb5b  mov     [rsp+3E0h+var_378], r8
0x18028eb60  mov     [rsp+3E0h+var_388], rdx
0x18028eb65  mov     [rbp+2E0h+var_330], rcx
0x18028eb69  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18028eb6e  xor     ebx, ebx
0x18028eb70  mov     r13b, al
0x18028eb73  mov     [rsp+3E0h+var_390], ebx
0x18028eb77  mov     [rbp+2E0h+var_358], rbx
0x18028eb7b  mov     [rsp+3E0h+var_370], ebx
0x18028eb7f  mov     [rsp+3E0h+var_380], ebx
0x18028eb83  call    cs:__imp_GetCurrentThreadId
0x18028eb89  mov     ecx, eax; unsigned int
0x18028eb8b  lea     r8, [rsp+3E0h+var_380]; unsigned int *
0x18028eb90  lea     rdx, [rsp+3E0h+var_370]; unsigned int *
0x18028eb95  call    ?GetIESessionFromFrameThread@@YAJKPEAK0@Z; GetIESessionFromFrameThread(ulong,ulong *,ulong *)
0x18028eb9a  mov     ecx, r12d
0x18028eb9d  neg     ecx
0x18028eb9f  sbb     ecx, ecx
0x18028eba1  neg     ecx
0x18028eba3  add     ecx, 2
0x18028eba6  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18028ebac  xor     r8d, r8d
0x18028ebaf  mov     [rbp+2E0h+var_360], ebx
0x18028ebb2  lea     rdx, [rbp+2E0h+var_360]
0x18028ebb6  xor     ecx, ecx
0x18028ebb8  mov     edi, eax
0x18028ebba  mov     r14d, ebx
0x18028ebbd  call    cs:__imp_?IsoGetAuthority@@YAKPEAK00@Z; IsoGetAuthority(ulong *,ulong *,ulong *)
0x18028ebc3  lea     rax, [rbp+2E0h+var_358]
0x18028ebc7  mov     [rsp+3E0h+var_3B8], rbx
0x18028ebcc  lea     r9, [rsp+3E0h+var_390]
0x18028ebd1  mov     qword ptr [rsp+3E0h+dwWakeMask], rax
0x18028ebd6  lea     r8, [rbp+2E0h+var_70]
0x18028ebdd  mov     dl, 6
0x18028ebdf  lea     ecx, [rbx+1]
0x18028ebe2  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x18028ebe8  mov     ebx, eax
0x18028ebea  test    eax, eax
0x18028ebec  jnz     loc_18028ED2D
0x18028ebf2  mov     ecx, [rsp+3E0h+var_390]
0x18028ebf6  cmp     ecx, [rbp+2E0h+var_360]
0x18028ebf9  jz      loc_18028ECD4
0x18028ebff  test    r13b, r13b
0x18028ec02  jnz     short loc_18028EC2F
0x18028ec04  mov     rax, [rbp+2E0h+var_358]
0x18028ec08  mov     edx, [rsp+3E0h+var_370]
0x18028ec0c  cmp     edx, [rax+2Ch]
0x18028ec0f  jz      loc_18028ED0D
0x18028ec15  test    byte ptr [rsp+3E0h+var_380], 8
0x18028ec1a  jnz     loc_18028ECD4
0x18028ec20  test    byte ptr [rax+28h], 8
0x18028ec24  jz      loc_18028ED0D
0x18028ec2a  jmp     loc_18028ECD4
0x18028ec2f  xor     r9d, r9d
0x18028ec32  mov     [rsp+3E0h+AppID], 0
0x18028ec3b  lea     r8, [rsp+3E0h+AppID]
0x18028ec40  mov     dl, 6
0x18028ec42  call    cs:__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoLockArtifact(ulong,uchar,_IsoArtifact * *,ulong *)
0x18028ec48  test    eax, eax
0x18028ec4a  js      loc_18028ECD4
0x18028ec50  mov     rax, [rsp+3E0h+AppID]
0x18028ec55  mov     ecx, [rsp+3E0h+var_390]
0x18028ec59  mov     r14d, [rax+14h]
0x18028ec5d  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x18028ec63  mov     al, r14b
0x18028ec66  and     al, 7Fh
0x18028ec68  mov     sil, al
0x18028ec6b  test    r12d, r12d
0x18028ec6e  jz      short loc_18028EC8B
0x18028ec70  cmp     al, 7Ch ; '|'
0x18028ec72  jnb     short loc_18028ECD4
0x18028ec74  mov     ecx, 1000003Fh
0x18028ec79  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18028ec7f  test    al, al
0x18028ec81  jz      short loc_18028ECA4
0x18028ec83  cmp     sil, 7Ah ; 'z'
0x18028ec87  jnz     short loc_18028ECA4
0x18028ec89  jmp     short loc_18028ECD4
0x18028ec8b  cmp     al, 7Ch ; '|'
0x18028ec8d  jnb     short loc_18028ECA4
0x18028ec8f  mov     ecx, 1000003Fh
0x18028ec94  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18028ec9a  test    al, al
0x18028ec9c  jz      short loc_18028ECD4
0x18028ec9e  cmp     sil, 7Ah ; 'z'
0x18028eca2  jnz     short loc_18028ECD4
0x18028eca4  mov     rax, [rbp+2E0h+var_358]
0x18028eca8  mov     ecx, [rsp+3E0h+var_370]
0x18028ecac  cmp     ecx, [rax+2Ch]
0x18028ecaf  jz      short loc_18028ECBE
0x18028ecb1  test    byte ptr [rsp+3E0h+var_380], 8
0x18028ecb6  jnz     short loc_18028ECD4
0x18028ecb8  test    byte ptr [rax+28h], 8
0x18028ecbc  jnz     short loc_18028ECD4
0x18028ecbe  mov     ecx, [rsp+3E0h+var_390]
0x18028ecc2  xor     r9d, r9d
0x18028ecc5  xor     r8d, r8d
0x18028ecc8  mov     dl, 6
0x18028ecca  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x18028ecd0  test    eax, eax
0x18028ecd2  jns     short loc_18028ED09
0x18028ecd4  lea     rax, [rbp+2E0h+var_358]
0x18028ecd8  mov     [rsp+3E0h+var_3B8], 0
0x18028ece1  lea     r9, [rsp+3E0h+var_390]
0x18028ece6  mov     qword ptr [rsp+3E0h+dwWakeMask], rax
0x18028eceb  lea     r8, [rbp+2E0h+var_70]
0x18028ecf2  mov     dl, 6
0x18028ecf4  mov     ecx, 2
0x18028ecf9  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@EPEAXPEAKPEAPEAU_IsoArtifact@@2@Z; IsoGetNextArtifact(_IsoEnumeration,uchar,void *,ulong *,_IsoArtifact * *,ulong *)
0x18028ecff  mov     ebx, eax
0x18028ed01  test    eax, eax
0x18028ed03  jz      loc_18028EBF2
0x18028ed09  mov     ecx, [rsp+3E0h+var_390]
0x18028ed0d  mov     rsi, [rsp+3E0h+var_388]
0x18028ed12  xor     r12d, r12d
0x18028ed15  test    ebx, ebx
0x18028ed17  jnz     short loc_18028ED34
0x18028ed19  movzx   eax, r14w
0x18028ed1d  lea     r13d, [r12+1]
0x18028ed22  and     eax, 0FFFh
0x18028ed27  bts     eax, 0Eh
0x18028ed2b  jmp     short loc_18028ED5A
0x18028ed2d  mov     ecx, [rsp+3E0h+var_390]
0x18028ed31  xor     r12d, r12d
0x18028ed34  mov     r13d, 1
0x18028ed3a  cmp     ebx, r13d
0x18028ed3d  jnz     short loc_18028ED4F
0x18028ed3f  mov     ecx, r12d
0x18028ed42  mov     eax, edi
0x18028ed44  mov     [rsp+3E0h+var_390], ecx
0x18028ed48  or      eax, 5000h
0x18028ed4d  jmp     short loc_18028ED5A
0x18028ed4f  mov     eax, r12d
0x18028ed52  test    ebx, ebx
0x18028ed54  js      loc_18028F14A
0x18028ed5a  or      edi, eax
0x18028ed5c  mov     [rsp+3E0h+var_37C], r12d
0x18028ed61  mov     eax, edi
0x18028ed63  mov     [rsp+3E0h+var_388], r12
0x18028ed68  and     eax, 0F000h
0x18028ed6d  lea     r9, [rsp+3E0h+var_388]
0x18028ed72  lea     rdx, [rsp+3E0h+var_37C]
0x18028ed77  mov     r8d, 2140h
0x18028ed7d  cmp     eax, 5000h
0x18028ed82  jnz     short loc_18028ED8E
0x18028ed84  mov     ecx, edi
0x18028ed86  call    cs:__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z; IsoAllocSharedMemoryPerFlags(ulong,ulong *,ulong,void * *)
0x18028ed8c  jmp     short loc_18028ED94
0x18028ed8e  call    cs:__imp_?IsoAllocSharedMemory@@YAJKPEAKKPEAPEAX@Z; IsoAllocSharedMemory(ulong,ulong *,ulong,void * *)
0x18028ed94  mov     ebx, eax
0x18028ed96  test    eax, eax
0x18028ed98  js      loc_18028F14A
0x18028ed9e  mov     edx, r13d
0x18028eda1  mov     rcx, rsi
0x18028eda4  call    _CreateOpenNamedSyncEventForPreview
0x18028eda9  mov     [rbp+2E0h+pHandles], rax
0x18028edad  test    rax, rax
0x18028edb0  jz      loc_18028F13B
0x18028edb6  mov     rax, [rsp+3E0h+var_388]
0x18028edbb  xor     edx, edx; Val
0x18028edbd  mov     rcx, [rsp+3E0h+var_378]
0x18028edc2  mov     r14d, r13d
0x18028edc5  mov     [rax], rsi
0x18028edc8  mov     esi, 80h
0x18028edcd  mov     rax, [rsp+3E0h+var_388]
0x18028edd2  mov     r8d, esi; Size
0x18028edd5  mov     [rax+8], rcx
0x18028edd9  mov     ecx, [rbp+2E0h+arg_20]
0x18028eddf  mov     rax, [rbp+2E0h+var_340]
0x18028ede3  movups  xmm0, xmmword ptr [rax]
0x18028ede6  mov     rax, [rsp+3E0h+var_388]
0x18028edeb  movdqu  xmmword ptr [rax+10h], xmm0
0x18028edf0  mov     rax, [rsp+3E0h+var_388]
0x18028edf5  mov     [rax+20h], ecx
0x18028edf8  mov     rax, [rsp+3E0h+var_388]
0x18028edfd  mov     ecx, [rbp+2E0h+arg_28]
0x18028ee03  mov     [rax+24h], ecx
0x18028ee06  mov     rax, [rsp+3E0h+var_388]
0x18028ee0b  mov     ecx, [rbp+2E0h+arg_30]
0x18028ee11  mov     [rax+28h], ecx
0x18028ee14  mov     rcx, [rsp+3E0h+var_388]
0x18028ee19  add     rcx, 20C0h; void *
0x18028ee20  call    memset_0
0x18028ee25  mov     rax, [rsp+3E0h+var_388]
0x18028ee2a  mov     [rax+20BCh], r12d
0x18028ee31  test    r15, r15
0x18028ee34  jz      loc_18028EECC
0x18028ee3a  mov     ecx, edi
0x18028ee3c  mov     [rsp+3E0h+var_378], r12
0x18028ee41  call    cs:__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z; LCIEForceSecurityProxiesFromFlags(ulong)
0x18028ee47  test    eax, eax
0x18028ee49  jz      short loc_18028EE68
0x18028ee4b  mov     r9, r15; struct IUnknown *
0x18028ee4e  lea     r8, [rsp+3E0h+var_378]; struct IUnknown **
0x18028ee53  lea     rdx, IID_IWebPreviewCallback; struct _GUID *
0x18028ee5a  mov     ecx, r13d; unsigned int
0x18028ee5d  call    ?MakeMaster@CLCIE_IIDProxy_Master@@SAJKAEBU_GUID@@PEAPEAUIUnknown@@PEAU3@@Z; CLCIE_IIDProxy_Master::MakeMaster(ulong,_GUID const &,IUnknown * *,IUnknown *)
0x18028ee62  mov     ebx, eax
0x18028ee64  test    eax, eax
0x18028ee66  js      short loc_18028EEAE
0x18028ee68  mov     rax, [rsp+3E0h+var_388]
0x18028ee6d  lea     r8, IID_IWebPreviewCallback
0x18028ee74  lea     rcx, [rax+20BCh]
0x18028ee7b  lea     rdx, [rax+20C0h]
0x18028ee82  mov     [rsp+3E0h+var_3B0], rcx
0x18028ee87  mov     rax, [rsp+3E0h+var_378]
0x18028ee8c  mov     ecx, edi
0x18028ee8e  test    rax, rax
0x18028ee91  mov     [rsp+3E0h+var_3B8], rsi
0x18028ee96  mov     qword ptr [rsp+3E0h+dwWakeMask], rdx
0x18028ee9b  mov     edx, [rsp+3E0h+var_390]
0x18028ee9f  cmovnz  r15, rax
0x18028eea3  mov     r9, r15
0x18028eea6  call    cs:__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z; LCIEMarshalInterfaceIntoBufferForHandle(ulong,ulong,_GUID const &,IUnknown *,uchar *,unsigned __int64,ulong *)
0x18028eeac  mov     ebx, eax
0x18028eeae  mov     rcx, [rsp+3E0h+var_378]
0x18028eeb3  test    rcx, rcx
0x18028eeb6  jz      short loc_18028EEC4
0x18028eeb8  mov     rax, [rcx]
0x18028eebb  mov     rax, [rax+10h]
0x18028eebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028eec4  test    ebx, ebx
0x18028eec6  js      loc_18028F12A
0x18028eecc  mov     rax, [rbp+2E0h+var_338]
0x18028eed0  mov     esi, 824h
0x18028eed5  test    rax, rax
0x18028eed8  jz      short loc_18028EEF9
0x18028eeda  mov     rcx, [rsp+3E0h+var_388]
0x18028eedf  mov     r8, rax; unsigned __int16 *
0x18028eee2  add     rcx, 2Ch ; ','; unsigned __int16 *
0x18028eee6  mov     edx, esi; unsigned __int64
0x18028eee8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18028eeed  mov     ebx, eax
0x18028eeef  test    eax, eax
0x18028eef1  js      loc_18028F12A
0x18028eef7  jmp     short loc_18028EF03
0x18028eef9  mov     rax, [rsp+3E0h+var_388]
0x18028eefe  mov     [rax+2Ch], r12w
0x18028ef03  mov     rax, [rbp+2E0h+var_330]
0x18028ef07  test    rax, rax
0x18028ef0a  jz      short loc_18028EF2F
0x18028ef0c  mov     rcx, [rsp+3E0h+var_388]
0x18028ef11  mov     r8, rax; unsigned __int16 *
0x18028ef14  add     rcx, 1074h; unsigned __int16 *
0x18028ef1b  mov     rdx, rsi; unsigned __int64
0x18028ef1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18028ef23  mov     ebx, eax
0x18028ef25  test    eax, eax
0x18028ef27  js      loc_18028F12A
0x18028ef2d  jmp     short loc_18028EF3C
0x18028ef2f  mov     rax, [rsp+3E0h+var_388]
0x18028ef34  mov     [rax+1074h], r12w
0x18028ef3c  mov     ecx, 10000009h
0x18028ef41  mov     [rsp+3E0h+AppID], r12
0x18028ef46  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18028ef4c  test    al, al
0x18028ef4e  jnz     short loc_18028EF5A
0x18028ef50  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18028ef56  test    al, al
0x18028ef58  jz      short loc_18028EF67
0x18028ef5a  lea     rcx, [rsp+3E0h+AppID]; AppID
0x18028ef5f  call    cs:__imp_GetCurrentProcessExplicitAppUserModelID
0x18028ef65  mov     ebx, eax
0x18028ef67  test    ebx, ebx
0x18028ef69  js      loc_18028F11F
0x18028ef6f  mov     ebx, 278h
0x18028ef74  mov     dword ptr [rsp+3E0h+var_378], r12d
0x18028ef79  mov     r8d, ebx; Size
0x18028ef7c  lea     rcx, [rbp+2E0h+var_2F0]; void *
0x18028ef80  xor     edx, edx; Val
0x18028ef82  call    memset_0
0x18028ef87  mov     eax, [rsp+3E0h+var_37C]
0x18028ef8b  lea     r8, [rbp+2E0h+var_2F0]; struct _IsoCreationComponentData *
0x18028ef8f  mov     edx, [rsp+3E0h+var_380]; unsigned int
0x18028ef93  mov     ecx, [rsp+3E0h+var_370]; unsigned int
0x18028ef97  mov     [rbp+2E0h+var_158], eax
0x18028ef9d  mov     eax, [rsp+3E0h+var_390]
0x18028efa1  mov     [rbp+2E0h+var_2E8], eax
  ... truncated ...
```
