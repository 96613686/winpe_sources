# CShellBrowser2::_BrowserTab_MsgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1801f8350`
- end: `0x1801f95da`
- name: `?_BrowserTab_MsgProc@CShellBrowser2@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4746`
- prototype: `__int64 __usercall@<rax>(CShellBrowser2 *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180207c30`

## callees

- `0x180005030`
- `0x18001546c`
- `0x18001d1a0`
- `0x180024b74`
- `0x1800310c0`
- `0x1800384d4`
- `0x18004d308`
- `0x1800757e8`
- `0x18007587c`
- `0x180078534`
- `0x18008f1bc`
- `0x180099a08`
- `0x18009d350`
- `0x1800a17f8`
- `0x1800dd040`
- `0x1801bd820`
- `0x1801cdc88`
- `0x1801f3138`
- `0x1801f3d88`
- `0x1801f40b0`
- `0x1801f74d4`
- `0x1801f7564`
- `0x1801f8350`
- `0x1801f9c2c`
- `0x1801fa2c0`
- `0x1801fbce4`
- `0x1801fbf68`
- `0x1801fc0e0`
- `0x1801fea8c`
- `0x1801ff03c`
- `0x1801ff860`
- `0x1801ffd3c`
- `0x1801fffa4`
- `0x18020515c`
- `0x1802631f4`
- `0x180263460`
- `0x180263530`
- `0x18026af94`
- `0x18026b874`
- `0x18042cf7c`
- `0x180476180`
- `0x1804762a4`
- `0x180522b98`
- `0x18052559c`
- `0x18057a5ac`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `msvcrt!free` at `0x1801f8a0e`
- `msvcrt!free` at `0x1801f8a0e`
- `KERNEL32!SetEvent` at `0x1801f8ffc`
- `KERNEL32!SetEvent` at `0x1801f8ffc`
- `KERNEL32!CloseHandle` at `0x1801f9010`
- `KERNEL32!CloseHandle` at `0x1801f9010`
- `KERNEL32!GetCurrentThreadId` at `0x1801f88eb`
- `KERNEL32!GetCurrentThreadId` at `0x1801f88eb`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801f89cf`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801f89fe`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801f89cf`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801f89fe`
- `USER32!PostMessageW` at `0x1801f8926`
- `USER32!PostMessageW` at `0x1801f8926`
- `OLEAUT32!__imp_SysAllocString` at `0x1801f8b43`
- `OLEAUT32!__imp_SysAllocString` at `0x1801f8b43`
- `OLEAUT32!__imp_SysFreeString` at `0x1801f8b65`
- `OLEAUT32!__imp_SysFreeString` at `0x1801f8b65`
- `SHELL32!__imp_ILFree` at `0x1801f8796`
- `SHELL32!__imp_ILFree` at `0x1801f8796`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f85b7`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f9167`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f91fb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f92f2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f9372`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f940a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f9494`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f85b7`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f9167`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f91fb`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f92f2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f9372`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f940a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f9494`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1801f8e8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1801f8e8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801f8b75`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801f8d79`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801f8b75`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801f8d79`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801f8d8e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801f8d8e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1801f8ea8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1801f8ea8`
- `WININET!InternetShowSecurityInfoByURLW` at `0x1801f89ef`
- `WININET!InternetShowSecurityInfoByURLW` at `0x1801f89ef`
- `msIso!__imp_?LCIESerializable_UnpackWStr@@YAKPEAPEAGW4LCIESerializable_UnpackWStr_Enum@@_KPEBE@Z` at `0x1801f89a1`
- `msIso!__imp_?LCIESerializable_UnpackWStr@@YAKPEAPEAGW4LCIESerializable_UnpackWStr_Enum@@_KPEBE@Z` at `0x1801f89a1`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801f8a83`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801f8fb0`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801f905f`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801f8a83`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801f8fb0`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801f905f`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8874`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8ac9`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8bc4`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8c42`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f91a6`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f923c`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f9331`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f9449`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f94d3`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8874`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8ac9`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8bc4`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f8c42`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f91a6`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f923c`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f9331`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f9449`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801f94d3`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801f8954`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801f8954`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801f958c`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801f958c`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801f8388`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801f8388`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f83d3`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f885e`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f8ab1`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f8bac`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f8c2c`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f9190`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f9224`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f931b`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f9433`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f94bd`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f83d3`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f885e`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f8ab1`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f8bac`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f8c2c`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f9190`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f9224`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f931b`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f9433`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801f94bd`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801f959b`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801f959b`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801f8485`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801f8670`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801f8485`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801f8670`

## pseudocode

```c
__int64 __fastcall CShellBrowser2::_BrowserTab_MsgProc(
        CShellBrowser2 *this,
        HWND a2,
        int a3,
        unsigned int a4,
        __int64 a5)
{
  int WindowsMessageNumber; // r12d
  char v9; // di
  unsigned int v10; // esi
  unsigned int v11; // esi
  void (*v12)(void); // rax
  struct LCIEPackedBuffer *v13; // r15
  int v14; // eax
  unsigned int v15; // edx
  char *v16; // rsi
  char v17; // r12
  int v18; // r15d
  __int64 v19; // rax
  unsigned __int16 *v20; // r13
  int v21; // ecx
  unsigned __int16 *v22; // r12
  struct tagVARIANT *v23; // rax
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  unsigned __int16 *v28; // rbx
  unsigned int v29; // r9d
  char *v30; // rdx
  char *v31; // rdx
  ULONG_PTR v32; // rax
  unsigned __int64 v33; // rdx
  unsigned int v34; // ebx
  DWORD CurrentThreadId; // eax
  unsigned __int64 v36; // rcx
  _lambda_ce15d259f53648a8c53bb735717135d9_ *v37; // rbx
  __int64 v38; // rdi
  unsigned int v39; // r8d
  unsigned int v40; // ecx
  unsigned int v41; // edx
  char *v42; // rax
  unsigned __int16 *v43; // rax
  OLECHAR *v44; // rdi
  char *v45; // rcx
  __int128 v46; // xmm0
  __int64 v47; // xmm1_8
  WPARAM v48; // rcx
  char *v49; // rcx
  char *v50; // rcx
  ULONG_PTR v51; // rax
  WPARAM v52; // rcx
  int MaySaveChanges; // eax
  const WCHAR *v54; // rsi
  void *v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // r8
  DWORD v59; // eax
  unsigned int v60; // r12d
  ULONG v61; // esi
  char *v62; // r15
  struct tagIE8_THREADPARAM *v63; // rsi
  __int64 v64; // r8
  __int64 v65; // r8
  int v66; // r15d
  HANDLE *v67; // rdi
  void *v68; // rcx
  int v69; // eax
  unsigned int v70; // r8d
  bool v71; // zf
  LCIEMessagePortChannelHost *v72; // rcx
  unsigned int v73; // edx
  LCIEMessagePortChannelHost *v74; // rcx
  _DWORD *v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdi
  _DWORD *v78; // rax
  int v79; // edx
  int v80; // ecx
  char *v81; // rax
  void *v82; // rax
  __int64 v83; // rcx
  unsigned int v84; // edi
  unsigned int v86; // [rsp+20h] [rbp-91h]
  void *Block; // [rsp+40h] [rbp-71h] BYREF
  char v88[8]; // [rsp+48h] [rbp-69h] BYREF
  struct LCIEPackedBuffer *v89; // [rsp+50h] [rbp-61h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-59h] BYREF
  LPSTREAM ppstm[2]; // [rsp+60h] [rbp-51h] BYREF
  struct tagMSLLHOOKSTRUCT v92; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v93; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v94[20]; // [rsp+98h] [rbp-19h] BYREF
  int v95; // [rsp+ACh] [rbp-5h]
  struct _GUID v96; // [rsp+B0h] [rbp-1h] BYREF

  WindowsMessageNumber = IsoGetWindowsMessageNumber(3);
  if ( a5 )
  {
    v89 = 0;
    v93 = 0;
    v9 = 1;
    if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, &v89, &v93) >= 0 )
    {
      v94[16] = 0;
      v95 = 0;
      v96 = (struct _GUID)*((_OWORD *)v89 + 1);
      ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)v94, &v96);
      if ( a4 <= 0xD23 )
      {
        if ( a4 == 3363 )
        {
          MaySaveChanges = CBaseBrowser2::_MaySaveChanges(this, 0);
          v41 = *((_DWORD *)this + 1586);
          v40 = *((_DWORD *)this + 1587);
          if ( MaySaveChanges == 1 )
            v39 = 3365;
          else
            v39 = 3364;
          goto LABEL_97;
        }
        if ( a4 <= 0xC3F )
        {
          switch ( a4 )
          {
            case 0xC3Fu:
              if ( a3 != WindowsMessageNumber )
              {
                *(_QWORD *)&v96.Data1 = 0;
                if ( (int)IsoGetArtifactAddress(a5, 0xDu, (struct _IsoArtifact **)&v96, 0) >= 0 )
                {
                  v36 = *(_QWORD *)(*(_QWORD *)&v96.Data1 + 16LL);
                  if ( v36 >= 0x2A && v36 >= (unsigned __int64)*((unsigned int *)v89 + 9) + 32 )
                  {
                    Block = 0;
                    if ( (unsigned int)LCIESerializable_UnpackWStr(&Block, 1) )
                    {
                      v37 = _lambda_ce15d259f53648a8c53bb735717135d9_::_lambda_ce15d259f53648a8c53bb735717135d9_(
                              (_lambda_ce15d259f53648a8c53bb735717135d9_ *)ppstm,
                              (const struct DesktopEuppFirstRunUI *)&Block,
                              (const struct EuppFirstRunSettings **)this);
                      v38 = SetThreadDpiAwarenessContext(-2);
                      InternetShowSecurityInfoByURLW(**(LPCWSTR **)v37, *(HWND *)(*((_QWORD *)v37 + 1) + 344LL));
                      SetThreadDpiAwarenessContext(v38);
                      free(Block);
                    }
                  }
                }
              }
              goto LABEL_249;
            case 0x101u:
              if ( a3 != WindowsMessageNumber )
                PostMessageW(*((HWND *)this + 43), 0x10u, 0, 0);
              goto LABEL_249;
            case 0xC03u:
            case 0xC04u:
              if ( a3 != WindowsMessageNumber )
              {
                v34 = (unsigned int)v89;
                CurrentThreadId = GetCurrentThreadId();
                LayerAsyncBoundaryManager::ApplyMessageToBoundary(
                  (LayerAsyncBoundaryManager *)CurrentThreadId,
                  v34,
                  0,
                  0,
                  v86);
              }
              goto LABEL_249;
            case 0xC1Fu:
              Block = 0;
              if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
                || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x48u) )
              {
                v30 = (char *)Block;
              }
              else
              {
                v30 = 0;
                Block = 0;
              }
              if ( v30 )
                v31 = v30 + 32;
              else
                v31 = 0;
              if ( v31 )
              {
                v92.pt = (POINT)*((_QWORD *)v31 + 1);
                *(_QWORD *)&v92.mouseData = *((_QWORD *)v31 + 3);
                *(_QWORD *)&v92.time = *((unsigned int *)v31 + 4);
                v32 = *((_QWORD *)v31 + 4);
                v33 = *(_QWORD *)v31;
                v92.dwExtraInfo = v32;
                CallDetourHookHandler(7, v33, (__int64)&v92);
              }
              goto LABEL_249;
          }
          if ( a4 != 3128 )
          {
            if ( a4 == 3129 || a4 - 3130 <= 1 )
            {
              if ( a3 == WindowsMessageNumber )
                goto LABEL_249;
              LCIE2ChangeComponentSharedFlagBit_FromComponentThread(1, 8u);
              ppstm[0] = 0;
              if ( (*(int (__fastcall **)(char *, GUID *, GUID *, LPSTREAM *))(*((_QWORD *)this + 4) + 24LL))(
                     (char *)this + 32,
                     &IID_IWebBrowserApp,
                     &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
                     ppstm) < 0 )
                goto LABEL_249;
              v10 = a4 - 3129;
              if ( v10 )
              {
                v11 = v10 - 1;
                if ( v11 )
                {
                  if ( v11 != 1 )
                  {
LABEL_23:
                    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm[0] + 16LL))(ppstm[0]);
                    goto LABEL_249;
                  }
                  v12 = *(void (**)(void))(*(_QWORD *)ppstm[0] + 112LL);
                }
                else
                {
                  v12 = *(void (**)(void))(*(_QWORD *)ppstm[0] + 56LL);
                }
              }
              else
              {
                v12 = *(void (**)(void))(*(_QWORD *)ppstm[0] + 64LL);
              }
              v12();
              goto LABEL_23;
            }
LABEL_189:
            v72 = (LCIEMessagePortChannelHost *)*((_QWORD *)this + 838);
            if ( v72 && LCIEMessagePortChannelHost::CanHandleMessage(v72, a4) )
            {
              LCIEMessagePortChannelHost::HandleMessage(v74, v73, a5, v89, v93);
LABEL_250:
              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)v94);
              return 0;
            }
LABEL_249:
            IsoFreeMessageBuffer(a5);
            goto LABEL_250;
          }
          if ( a3 == WindowsMessageNumber )
            goto LABEL_249;
          v13 = v89;
          Block = 0;
          memset(&v92, 0, 24);
          if ( (int)LCIE_IEFRAME_VariantArrayUnpack(0, a5, 0, (struct ATL::CComVariant **)&Block, 0) >= 0 )
          {
            ppstm[0] = 0;
            v14 = (*(__int64 (__fastcall **)(char *, GUID *, GUID *, LPSTREAM *))(*((_QWORD *)this + 4) + 24LL))(
                    (char *)this + 32,
                    &IID_IWebBrowserApp,
                    &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
                    ppstm);
            v16 = (char *)Block;
            if ( v14 < 0 )
              goto LABEL_64;
            v17 = 0;
            if ( *((_DWORD *)v13 + 10) != 1 )
            {
              switch ( *((_DWORD *)v13 + 10) )
              {
                case 2:
                  if ( *((_DWORD *)v13 + 9) != 1 )
                    goto LABEL_63;
                  (*(void (__fastcall **)(LPSTREAM, char *))(*(_QWORD *)ppstm[0] + 104LL))(ppstm[0], (char *)Block + 48);
                  v24 = *((_DWORD *)this + 1586);
                  v25 = *((_DWORD *)this + 1588);
                  LODWORD(pidl) = *((_DWORD *)this + 1616);
                  TFlatIsoMessage<LCIE_USERREFRESH>::Post(v25, v24, v26, v27, (__int64)&pidl);
                  break;
                case 3:
                  break;
                case 4:
                  v17 = 1;
                  goto LABEL_44;
                default:
                  if ( *((_DWORD *)v13 + 10) == 5 && IsDualEngineProcess() )
                  {
                    v18 = *((_DWORD *)v13 + 9);
                    if ( v18 >= 2 )
                    {
                      v19 = *((_QWORD *)v16 + 7);
                      v20 = 0;
                      v21 = *((_DWORD *)v16 + 20);
                      *(_QWORD *)&v96.Data1 = v19;
                      LODWORD(pidl) = v21;
                      if ( v18 >= 3 )
                        v20 = (unsigned __int16 *)*((_QWORD *)v16 + 13);
                      v22 = 0;
                      if ( v18 >= 4 )
                        v22 = (unsigned __int16 *)*((_QWORD *)v16 + 16);
                      if ( (unsigned int)GetUrlSchemeW(v19) - 15 <= 1 )
                      {
                        (*(void (__fastcall **)(LPSTREAM, char *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *))(*(_QWORD *)ppstm[0] + 416LL))(
                          ppstm[0],
                          v16 + 48,
                          &v92,
                          &v92,
                          &v92,
                          &v92);
                      }
                      else
                      {
                        v23 = (struct tagVARIANT *)(v16 + 120);
                        if ( v18 < 5 )
                          v23 = (struct tagVARIANT *)&v92;
                        CShellBrowser2::_DualEngineNavigateWithPostData(
                          this,
                          (struct IWebBrowser2 *)ppstm[0],
                          *(unsigned __int16 **)&v96.Data1,
                          v20,
                          v22,
                          (unsigned int)pidl,
                          v23);
                      }
                    }
                  }
                  goto LABEL_63;
              }
              if ( *((_DWORD *)v13 + 9) == 1 )
                (*(void (__fastcall **)(LPSTREAM, char *))(*(_QWORD *)ppstm[0] + 104LL))(ppstm[0], v16 + 48);
              goto LABEL_63;
            }
LABEL_44:
            LCIE2ChangeComponentSharedFlagBit_FromComponentThread(1, 8u);
            if ( *((_DWORD *)v13 + 9) == 4 )
            {
              v28 = (unsigned __int16 *)*((_QWORD *)v16 + 16);
              goto LABEL_56;
            }
            if ( !v17 && (v16[104] & 1) == 0 )
            {
              if ( *((_DWORD *)v13 + 9) == 3 )
                (*(void (__fastcall **)(LPSTREAM, char *, char *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *))(*(_QWORD *)ppstm[0] + 416LL))(
                  ppstm[0],
                  v16 + 48,
                  v16 + 72,
                  &v92,
                  &v92,
                  &v92);
              goto LABEL_63;
            }
            v28 = 0;
            if ( *((int *)v13 + 9) >= 3 )
            {
LABEL_56:
              pidl = 0;
              Block = 0;
              if ( (int)VariantToIDList(v16 + 48, &pidl) < 0
                || (int)IUriFromPidl(pidl, 50342788, &Block) < 0
                || (ILFree(pidl),
                    *(_QWORD *)&v96.Data1 = 0,
                    (*(int (__fastcall **)(void *, __int64, struct _GUID *))(*(_QWORD *)Block + 24LL))(Block, 11, &v96) < 0)
                || !*(_QWORD *)&v96.Data1
                || (int)_NavigateWithReferrer(
                          (struct IWebBrowser2 *)ppstm[0],
                          *(unsigned __int16 **)&v96.Data1,
                          v28,
                          v29) < 0 )
              {
                (*(void (__fastcall **)(LPSTREAM, char *, char *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *))(*(_QWORD *)ppstm[0] + 416LL))(
                  ppstm[0],
                  v16 + 48,
                  v16 + 72,
                  &v92,
                  &v92,
                  &v92);
              }
              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&Block);
            }
LABEL_63:
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm[0] + 16LL))(ppstm[0]);
LABEL_64:
            if ( v16 )
              ATL::CComVariant::`vector deleting destructor'((ATL::CComVariant *)v16, v15);
          }
LABEL_66:
          ATL::CComVariant::Clear((ATL::CComVariant *)&v92);
          goto LABEL_249;
        }
        switch ( a4 )
        {
          case 0xC45u:
            CShellBrowser2::_OnConfirmedClose(this, 0);
            goto LABEL_249;
          case 0xC53u:
            Block = 0;
            if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
              || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x48u) )
            {
              v49 = (char *)Block;
            }
            else
            {
              v49 = 0;
              Block = 0;
            }
            if ( v49 )
              v50 = v49 + 32;
            else
              v50 = 0;
            if ( v50 )
            {
              v92.pt = (POINT)*((_QWORD *)v50 + 1);
              v92.mouseData = *((_DWORD *)v50 + 4);
              v92.flags = *((_DWORD *)v50 + 5);
              *(_QWORD *)&v92.time = *((unsigned int *)v50 + 6);
              v51 = *((_QWORD *)v50 + 4);
              v52 = *(_QWORD *)v50;
              v92.dwExtraInfo = v51;
              ForwardLowlevelMouseHookEvents(v52, &v92);
            }
            goto LABEL_249;
          case 0xC54u:
            Block = 0;
            if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
              || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x40u) )
            {
              v45 = (char *)Block;
            }
            else
            {
              v45 = 0;
              Block = 0;
            }
            if ( v45 )
              v45 += 32;
            if ( v45 )
            {
              v46 = *(_OWORD *)(v45 + 8);
              v47 = *((_QWORD *)v45 + 3);
              v48 = *(_QWORD *)v45;
              *(_OWORD *)&v92.pt.x = v46;
              *(_QWORD *)&v92.time = v47;
              ForwardLowlevelKeyboardHookEvents(v48, (const struct tagKBDLLHOOKSTRUCT *)&v92);
            }
            goto LABEL_249;
        }
        if ( a4 != 3169 )
        {
          if ( a4 == 3278 )
          {
            Block = 0;
            if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
              || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x240u) )
            {
              v42 = (char *)Block;
            }
            else
            {
              v42 = 0;
              Block = 0;
            }
            if ( v42 && v42 != (char *)-32LL )
              CShellBrowser2::_OnBrowserFrameChanged(this, (struct LCIE_FRAME_DATA *)(v42 + 32), a5);
            goto LABEL_250;
          }
          if ( a4 != 3327 )
          {
            if ( a4 == 3359 )
            {
              CShellBrowser2::_SuspendForDeferredUnload(this);
              goto LABEL_249;
            }
            goto LABEL_189;
          }
          CBaseBrowser2::_UpdateTravelLogForRecovery(this);
          v39 = 3328;
          goto LABEL_95;
        }
        ppstm[0] = 0;
        if ( (int)LCIEGetStreamFromMessage(a5, a3 == WindowsMessageNumber, ppstm) >= 0 )
        {
          Block = 0;
          if ( (int)IStream_ReadStrIE(ppstm[0], &Block) >= 0 )
          {
            v43 = SysAllocString((const OLECHAR *)Block);
            v44 = v43;
            if ( v43 )
            {
              CShellBrowser2::OnMSSiteModeJumpListItemRemoved(this, v43);
              SysFreeString(v44);
            }
          }
          CoTaskMemFree(Block);
        }
LABEL_110:
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(ppstm);
        goto LABEL_249;
      }
      if ( a4 > 0xD3F )
      {
        if ( a4 == 3393 )
        {
          if ( v89 )
          {
            v83 = *((_QWORD *)this + 50);
            v84 = *((_DWORD *)v89 + 8);
            if ( !v83
              || (memset(&v92, 0, 24),
                  v92.mouseData = v84,
                  LOWORD(v92.pt.x) = 3,
                  (*(int (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v83 + 32LL))(
                    v83,
                    &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                    95) < 0) )
            {
              IsoUnlockArtifact(v84);
            }
          }
          goto LABEL_249;
        }
        if ( a4 != 5125 )
        {
          switch ( a4 )
          {
            case 0x1406u:
              if ( v89 && IsDualEngineProcess() )
              {
                Block = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
                  || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x2Cu) )
                {
                  v81 = (char *)Block;
                }
                else
                {
                  v81 = 0;
                  Block = 0;
                }
                if ( v81 && v81 != (char *)-32LL )
                  CShellBrowser2::_DualEngineSimulateMouseInput(this, (struct LCIE_SIMULATEMOUSE_DATA *)(v81 + 32));
              }
              goto LABEL_249;
            case 0x1408u:
              if ( IsDualEngineProcess() )
              {
                if ( !(unsigned int)CBaseBrowser2::_CanNavigate(this)
                  || (unsigned int)CBaseBrowser2::_MaySaveChanges(this, 1) == 1 )
                {
                  v9 = 0;
                }
                else
                {
                  (*(void (__fastcall **)(char *, _QWORD, __int64, __int64, _QWORD, _QWORD))(*((_QWORD *)this + 5) + 32LL))(
                    (char *)this + 40,
                    0,
                    23,
                    2,
                    0,
                    0);
                }
                v79 = *((_DWORD *)this + 1586);
                v80 = *((_DWORD *)this + 1587);
                v88[0] = v9;
                TFlatIsoMessage<bool>::Post(v80, v79, 5129, 0, (__int64)v88);
              }
              goto LABEL_249;
            case 0x140Au:
              if ( v89 && IsDualEngineProcess() )
              {
                Block = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
                  || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x24u) )
                {
                  v78 = Block;
                }
                else
                {
                  v78 = 0;
                  Block = 0;
                }
                if ( v78 && v78 != (_DWORD *)-32LL )
                  CShellBrowser2::_DualEngineTravelToEntry(this, v78[8]);
              }
              goto LABEL_249;
            case 0x1414u:
              if ( v89 && IsDualEngineProcess() )
              {
                *(_QWORD *)&v96.Data1 = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&v96, 0) < 0
                  || (v71 = !VerifyUntrusted_IsoMessage_ExactSize(a5, 0x106Cu), v76 = 0, !v71) )
                {
                  v76 = *(_QWORD *)&v96.Data1;
                }
                if ( v76 )
                {
                  v77 = v76 + 32;
                  if ( v76 != -32 )
                  {
                    Block = 0;
                    if ( (*(int (__fastcall **)(char *, SID *, GUID *, void **))(*((_QWORD *)this + 4) + 24LL))(
                           (char *)this + 32,
                           &SID_SDocObjectHost,
                           &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
                           &Block) >= 0 )
                    {
                      *(_QWORD *)&v92.time = 0;
                      v92.pt = (POINT)0x4000LL;
                      *(_QWORD *)&v92.mouseData = v77;
                      (*(void (__fastcall **)(void *, const struct _GUID *, __int64))(*(_QWORD *)Block + 32LL))(
                        Block,
                        &CGID_DocHostCmdPriv,
                        25);
                    }
                    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&Block);
                  }
                }
              }
              goto LABEL_249;
            case 0x1417u:
              if ( v89 && IsDualEngineProcess() )
              {
                Block = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
                  || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x2Cu) )
                {
                  v75 = Block;
                }
                else
                {
                  v75 = 0;
                  Block = 0;
                }
                if ( v75 && v75 != (_DWORD *)-32LL )
                  CBaseBrowser2::_DualEngineNavigationEntriesDeleted(this, v75[8], v75[9], v75[10]);
              }
              goto LABEL_249;
          }
          goto LABEL_189;
        }
        if ( !v89 || !IsDualEngineProcess() )
          goto LABEL_249;
        Block = 0;
        if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
          || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x28u) )
        {
          v82 = Block;
        }
        else
        {
          v82 = 0;
          Block = 0;
        }
        if ( !v82 || v82 == (void *)-32LL )
          goto LABEL_249;
        *((_BYTE *)this + 6221) = 1;
        CShellBrowser2::_DualEngineSimulateKeyEvent(this, *((_DWORD *)v82 + 8), *((_BYTE *)v82 + 36));
        v40 = *((_DWORD *)this + 1588);
        v39 = 5127;
        goto LABEL_96;
      }
      switch ( a4 )
      {
        case 0xD3Fu:
          if ( v89 )
          {
            v71 = *((_BYTE *)this + 6700) == 0;
            *((_DWORD *)this + 1674) = *((_DWORD *)v89 + 17);
            if ( !v71 )
              CShellBrowser2::_CreateAndSendPreviewImageForFlipAhead(this);
          }
          goto LABEL_249;
        case 0xD27u:
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 833) + 128LL))(*((_QWORD *)this + 833));
          ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 6656);
          v39 = 3368;
          break;
        case 0xD29u:
          v69 = CShellBrowser2::_CleanupBrowserTabForEmptyTabConversion(this);
          v70 = 3370;
          if ( v69 < 0 )
            v70 = 3371;
          LCIEPostMessageWithoutBuffer(*((_DWORD *)this + 1587), *((_DWORD *)this + 1586), v70, 0);
          CShellBrowser2::_KeepProcessAlive(this, 0);
          goto LABEL_249;
        case 0xD2Cu:
          if ( v93 >= 0x3A8 )
          {
            CShellBrowser2::_KeepProcessAlive(this, 1);
            v63 = LCIEUnpackIETHREADPARAM((struct LCIEPackedBuffer *)((char *)v89 + 432), v93 - 936);
            if ( v63 )
            {
              if ( (Microsoft_IEFRAMEEnableBits & 0x20000) != 0 )
                McGenEventWrite_EventWriteTransfer(
                  BERP_IEFRAME2_Context,
                  EmptyTab_Reuse_ReinitializeBrowserTab_Begin,
                  v64,
                  1,
                  &v96);
              v66 = CShellBrowser2::_InitializeWindow(this, v63, 1);
              if ( v66 < 0 )
              {
                if ( (Microsoft_IEFRAMEEnableBits & 0x20000) != 0 )
                  McGenEventWrite_EventWriteTransfer(
                    BERP_IEFRAME2_Context,
                    EmptyTab_Reuse_ReinitializeBrowserTab_Failed,
                    v65,
                    1,
                    &v96);
                v67 = (HANDLE *)((char *)v63 + 456);
                v68 = (void *)*((_QWORD *)v63 + 57);
                if ( v68 )
                  SetEvent(v68);
              }
              else
              {
                LCIEPostMessageWithoutBuffer(*((_DWORD *)this + 1587), *((_DWORD *)this + 1586), 0xD2Eu, 0);
                v67 = (HANDLE *)((char *)v63 + 456);
              }
              if ( *v67 )
                CloseHandle(*v67);
              SHDestroyIETHREADPARAM(v63);
              if ( v66 >= 0 )
                goto LABEL_249;
            }
          }
          v39 = 3375;
          break;
        case 0xD30u:
          if ( !v89 )
            goto LABEL_249;
          v60 = *((_DWORD *)v89 + 8);
          v61 = *((_DWORD *)v89 + 9);
          v62 = (char *)v89 + 40;
          ppstm[0] = 0;
          if ( CreateStreamOnHGlobal(0, 1, ppstm) >= 0 && IStream_Write(ppstm[0], v62, v61) >= 0 )
          {
            pidl = 0;
            if ( CBaseBrowser2::GetTravelLog((CShellBrowser2 *)((char *)this + 8), (struct ITravelLog **)&pidl) >= 0 )
            {
              Block = 0;
              if ( (**(int (__fastcall ***)(LPITEMIDLIST, GUID *, void **))&pidl->mkid.cb)(
                     pidl,
                     &GUID_19bb515b_da44_4bcc_8625_6ad1be065692,
                     &Block) >= 0 )
                (*(void (__fastcall **)(void *, _QWORD, LPSTREAM))(*(_QWORD *)Block + 112LL))(Block, v60, ppstm[0]);
              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&Block);
            }
            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pidl);
          }
          goto LABEL_110;
        default:
          switch ( a4 )
          {
            case 0xD32u:
              v56 = TFlatIsoMessage<LCIE_CORRELATEDVTABCONTEXT>::VerifyExactSize((unsigned int)a5);
              if ( !v56 )
                goto LABEL_249;
              v57 = *((_QWORD *)this + 50);
              if ( !v57 )
                goto LABEL_249;
              v58 = 84;
              break;
            case 0xD33u:
              v56 = TFlatIsoMessage<LCIE_CORRELATEDVTABCONTEXT>::VerifyExactSize((unsigned int)a5);
              if ( !v56 )
                goto LABEL_249;
              v57 = *((_QWORD *)this + 50);
              if ( !v57 )
                goto LABEL_249;
              v58 = 85;
              break;
            case 0xD3Eu:
              LODWORD(pidl) = 0;
              v54 = (const WCHAR *)TArrayIsoMessage<unsigned short>::VerifyArraySize((unsigned int)a5, &pidl);
              if ( v54 && (unsigned int)pidl > 1 )
              {
                v55 = (void *)*((_QWORD *)this + 865);
                if ( v55 )
                {
                  CoTaskMemFree(v55);
                  *((_QWORD *)this + 865) = 0;
                }
                SHStrDupW(v54, (LPWSTR *)this + 865);
                (*(void (__fastcall **)(_QWORD, GUID *, __int64))(**((_QWORD **)this + 50) + 32LL))(
                  *((_QWORD *)this + 50),
                  &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                  91);
              }
              goto LABEL_249;
            default:
              goto LABEL_189;
          }
          v59 = *(_DWORD *)(v56 + 32);
          memset(&v92, 0, 24);
          v92.mouseData = v59;
          LOWORD(v92.pt.x) = 19;
          (*(void (__fastcall **)(__int64, GUID *, __int64, _QWORD, struct tagMSLLHOOKSTRUCT *, _QWORD))(*(_QWORD *)v57 + 32LL))(
            v57,
            &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
            v58,
            0,
            &v92,
            0);
          goto LABEL_66;
      }
LABEL_95:
      v40 = *((_DWORD *)this + 1587);
LABEL_96:
      v41 = *((_DWORD *)this + 1586);
LABEL_97:
      LCIEPostMessageWithoutBuffer(v40, v41, v39, 0);
      goto LABEL_249;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801f8350  mov     [rsp-8+arg_8], rbx
0x1801f8355  push    rbp
0x1801f8356  push    rsi
0x1801f8357  push    rdi
0x1801f8358  push    r12
0x1801f835a  push    r13
0x1801f835c  push    r14
0x1801f835e  push    r15
0x1801f8360  lea     rbp, [rsp-1Fh]
0x1801f8365  sub     rsp, 0D0h
0x1801f836c  mov     rax, cs:__security_cookie
0x1801f8373  xor     rax, rsp
0x1801f8376  mov     [rbp+4Fh+var_40], rax
0x1801f837a  mov     rbx, rcx
0x1801f837d  mov     rsi, r9
0x1801f8380  mov     ecx, 3
0x1801f8385  mov     r15d, r8d
0x1801f8388  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x1801f838f  nop     dword ptr [rax+rax+00h]
0x1801f8394  mov     r14, qword ptr [rbp+4Fh+arg_20]
0x1801f8398  cmp     r15d, eax
0x1801f839b  mov     r12d, eax
0x1801f839e  setz    r13b
0x1801f83a2  test    r14, r14
0x1801f83a5  jz      loc_1801F95B0
0x1801f83ab  xor     r8d, r8d
0x1801f83ae  mov     [rbp+4Fh+var_B0], 0
0x1801f83b6  lea     rax, [rbp+4Fh+var_70]
0x1801f83ba  mov     [rbp+4Fh+var_70], 0
0x1801f83c1  lea     r9, [rbp+4Fh+var_B0]
0x1801f83c5  mov     [rsp+100h+var_E0], rax; unsigned int
0x1801f83ca  mov     ecx, r14d
0x1801f83cd  lea     edi, [r8+1]
0x1801f83d1  mov     edx, edi
0x1801f83d3  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x1801f83da  nop     dword ptr [rax+rax+00h]
0x1801f83df  test    eax, eax
0x1801f83e1  js      loc_1801F95B0
0x1801f83e7  mov     rax, [rbp+4Fh+var_B0]
0x1801f83eb  lea     rdx, [rbp+4Fh+var_50]; struct _GUID
0x1801f83ef  lea     rcx, [rbp+4Fh+var_68]; this
0x1801f83f3  mov     [rbp+4Fh+var_58], 0
0x1801f83f7  mov     [rbp+4Fh+var_54], 0
0x1801f83fe  movups  xmm0, xmmword ptr [rax+10h]
0x1801f8402  movdqu  xmmword ptr [rbp+4Fh+var_50.Data1], xmm0
0x1801f8407  call    ?Set@ThreadUserInputIdSetter@@QEAAXU_GUID@@@Z; ThreadUserInputIdSetter::Set(_GUID)
0x1801f840c  mov     eax, 0D23h
0x1801f8411  cmp     esi, eax
0x1801f8413  ja      loc_1801F8CED
0x1801f8419  jz      loc_1801F8CBA
0x1801f841f  mov     eax, 0C3Fh
0x1801f8424  cmp     esi, eax
0x1801f8426  ja      loc_1801F8A1F
0x1801f842c  jz      loc_1801F8937
0x1801f8432  mov     eax, esi
0x1801f8434  sub     eax, 101h
0x1801f8439  jz      loc_1801F890C
0x1801f843f  sub     eax, 0B02h
0x1801f8444  jz      loc_1801F88DE
0x1801f844a  sub     eax, edi
0x1801f844c  jz      loc_1801F88DE
0x1801f8452  sub     eax, 1Bh
0x1801f8455  jz      loc_1801F8847
0x1801f845b  sub     eax, 19h
0x1801f845e  jz      loc_1801F8512
0x1801f8464  sub     eax, edi
0x1801f8466  jz      short loc_1801F8474
0x1801f8468  sub     eax, edi
0x1801f846a  jz      short loc_1801F8474
0x1801f846c  cmp     eax, edi
0x1801f846e  jnz     loc_1801F911B
0x1801f8474  cmp     r15d, r12d
0x1801f8477  jz      loc_1801F9598
0x1801f847d  mov     edx, 8
0x1801f8482  mov     cl, dil
0x1801f8485  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z; LCIE2ChangeComponentSharedFlagBit_FromComponentThread(bool,ulong)
0x1801f848c  nop     dword ptr [rax+rax+00h]
0x1801f8491  lea     rcx, [rbx+20h]
0x1801f8495  mov     [rbp+4Fh+ppstm], 0
0x1801f849d  mov     rax, [rcx]
0x1801f84a0  lea     r9, [rbp+4Fh+ppstm]
0x1801f84a4  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x1801f84ab  lea     rdx, IID_IWebBrowserApp
0x1801f84b2  mov     rax, [rax+18h]
0x1801f84b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84bb  test    eax, eax
0x1801f84bd  js      loc_1801F9598
0x1801f84c3  sub     esi, 0C39h
0x1801f84c9  jz      short loc_1801F84ED
0x1801f84cb  sub     esi, edi
0x1801f84cd  jz      short loc_1801F84E0
0x1801f84cf  cmp     esi, edi
0x1801f84d1  jnz     short loc_1801F84FD
0x1801f84d3  mov     rcx, [rbp+4Fh+ppstm]
0x1801f84d7  mov     rax, [rcx]
0x1801f84da  mov     rax, [rax+70h]
0x1801f84de  jmp     short loc_1801F84F8
0x1801f84e0  mov     rcx, [rbp+4Fh+ppstm]
0x1801f84e4  mov     rax, [rcx]
0x1801f84e7  mov     rax, [rax+38h]
0x1801f84eb  jmp     short loc_1801F84F8
0x1801f84ed  mov     rcx, [rbp+4Fh+ppstm]
0x1801f84f1  mov     rax, [rcx]
0x1801f84f4  mov     rax, [rax+40h]
0x1801f84f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84fd  mov     rcx, [rbp+4Fh+ppstm]
0x1801f8501  mov     rax, [rcx]
0x1801f8504  mov     rax, [rax+10h]
0x1801f8508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f850d  jmp     loc_1801F9598
0x1801f8512  cmp     r15d, r12d
0x1801f8515  jz      loc_1801F9598
0x1801f851b  mov     r15, [rbp+4Fh+var_B0]
0x1801f851f  lea     r9, [rbp+4Fh+Block]; struct ATL::CComVariant **
0x1801f8523  xor     eax, eax
0x1801f8525  mov     [rbp+4Fh+Block], 0
0x1801f852d  xorps   xmm0, xmm0
0x1801f8530  mov     [rbp+4Fh+var_90.dwExtraInfo], rax
0x1801f8534  xor     r8d, r8d; bool
0x1801f8537  mov     [rsp+100h+var_E0], rax; int *
0x1801f853c  mov     edx, r14d; unsigned int
0x1801f853f  xor     ecx, ecx; int
0x1801f8541  movups  xmmword ptr [rbp+4Fh+var_90.vkCode], xmm0
0x1801f8545  call    ?LCIE_IEFRAME_VariantArrayUnpack@@YAJHK_NPEAPEAVCComVariant@ATL@@PEAJ@Z; LCIE_IEFRAME_VariantArrayUnpack(int,ulong,bool,ATL::CComVariant * *,long *)
0x1801f854a  test    eax, eax
0x1801f854c  js      loc_1801F8839
0x1801f8552  lea     rcx, [rbx+20h]
0x1801f8556  mov     [rbp+4Fh+ppstm], 0
0x1801f855e  mov     rax, [rcx]
0x1801f8561  lea     r9, [rbp+4Fh+ppstm]
0x1801f8565  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x1801f856c  lea     rdx, IID_IWebBrowserApp
0x1801f8573  mov     rax, [rax+18h]
0x1801f8577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f857c  mov     rsi, [rbp+4Fh+Block]
0x1801f8580  test    eax, eax
0x1801f8582  js      loc_1801F882C
0x1801f8588  mov     ecx, [r15+28h]
0x1801f858c  xor     r12b, r12b
0x1801f858f  sub     ecx, edi
0x1801f8591  jz      loc_1801F8668
0x1801f8597  sub     ecx, edi
0x1801f8599  jz      loc_1801F86DF
0x1801f859f  sub     ecx, edi
0x1801f85a1  jz      loc_1801F8720
0x1801f85a7  sub     ecx, edi
0x1801f85a9  jz      loc_1801F8665
0x1801f85af  cmp     ecx, edi
0x1801f85b1  jnz     loc_1801F881C
0x1801f85b7  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801f85be  nop     dword ptr [rax+rax+00h]
0x1801f85c3  test    al, al
0x1801f85c5  jz      loc_1801F881C
0x1801f85cb  mov     r15d, [r15+24h]
0x1801f85cf  cmp     r15d, 2
0x1801f85d3  jl      loc_1801F881C
0x1801f85d9  mov     rax, [rsi+38h]
0x1801f85dd  xor     r13d, r13d
0x1801f85e0  mov     ecx, [rsi+50h]
0x1801f85e3  mov     qword ptr [rbp+4Fh+var_50.Data1], rax
0x1801f85e7  mov     dword ptr [rbp+4Fh+pidl], ecx
0x1801f85ea  lea     edx, [r13+3]
0x1801f85ee  cmp     r15d, edx
0x1801f85f1  jl      short loc_1801F85F7
0x1801f85f3  mov     r13, [rsi+68h]
0x1801f85f7  xor     r12d, r12d
0x1801f85fa  cmp     r15d, 4
0x1801f85fe  jl      short loc_1801F8607
0x1801f8600  mov     r12, [rsi+80h]
0x1801f8607  mov     rcx, rax
0x1801f860a  call    GetUrlSchemeW
0x1801f860f  add     eax, 0FFFFFFF1h
0x1801f8612  cmp     eax, edi
0x1801f8614  jbe     short loc_1801F864D
0x1801f8616  lea     rax, [rsi+78h]
0x1801f861a  cmp     r15d, 5
0x1801f861e  jge     short loc_1801F8624
0x1801f8620  lea     rax, [rbp+4Fh+var_90]
0x1801f8624  mov     r8, qword ptr [rbp+4Fh+var_50.Data1]; unsigned __int16 *
0x1801f8628  mov     r9, r13; unsigned __int16 *
0x1801f862b  mov     rdx, [rbp+4Fh+ppstm]; struct IWebBrowser2 *
0x1801f862f  mov     rcx, rbx; this
0x1801f8632  mov     [rsp+100h+var_D0], rax; struct tagVARIANT *
0x1801f8637  mov     eax, dword ptr [rbp+4Fh+pidl]
0x1801f863a  mov     [rsp+100h+var_D8], eax; unsigned int
0x1801f863e  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x1801f8643  call    ?_DualEngineNavigateWithPostData@CShellBrowser2@@AEAAXPEAUIWebBrowser2@@PEAG11KAEAUtagVARIANT@@@Z; CShellBrowser2::_DualEngineNavigateWithPostData(IWebBrowser2 *,ushort *,ushort *,ushort *,ulong,tagVARIANT &)
0x1801f8648  jmp     loc_1801F881C
0x1801f864d  lea     r8, [rbp+4Fh+var_90]
0x1801f8651  mov     qword ptr [rsp+100h+var_D8], r8
0x1801f8656  lea     r8, [rbp+4Fh+var_90]
0x1801f865a  mov     [rsp+100h+var_E0], r8
0x1801f865f  lea     r8, [rbp+4Fh+var_90]
0x1801f8663  jmp     short loc_1801F86BF
0x1801f8665  mov     r12b, dil
0x1801f8668  mov     edx, 8
0x1801f866d  mov     cl, dil
0x1801f8670  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z; LCIE2ChangeComponentSharedFlagBit_FromComponentThread(bool,ulong)
0x1801f8677  nop     dword ptr [rax+rax+00h]
0x1801f867c  cmp     dword ptr [r15+24h], 4
0x1801f8681  jz      loc_1801F8754
0x1801f8687  test    r12b, r12b
0x1801f868a  jnz     loc_1801F8743
0x1801f8690  test    [rsi+68h], dil
0x1801f8694  jnz     loc_1801F8743
0x1801f869a  mov     edx, 3
0x1801f869f  cmp     [r15+24h], edx
0x1801f86a3  jnz     loc_1801F881C
0x1801f86a9  lea     r9, [rbp+4Fh+var_90]
0x1801f86ad  mov     qword ptr [rsp+100h+var_D8], r9
0x1801f86b2  lea     r8, [rsi+48h]
0x1801f86b6  lea     r9, [rbp+4Fh+var_90]
0x1801f86ba  mov     [rsp+100h+var_E0], r9
0x1801f86bf  mov     rcx, [rbp+4Fh+ppstm]
0x1801f86c3  lea     r9, [rbp+4Fh+var_90]
0x1801f86c7  lea     rdx, [rsi+30h]
0x1801f86cb  mov     rax, [rcx]
0x1801f86ce  mov     rax, [rax+1A0h]
0x1801f86d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f86da  jmp     loc_1801F881C
0x1801f86df  cmp     [r15+24h], edi
0x1801f86e3  jnz     loc_1801F881C
0x1801f86e9  mov     rcx, [rbp+4Fh+ppstm]
0x1801f86ed  lea     rdx, [rsi+30h]
0x1801f86f1  mov     rax, [rcx]
0x1801f86f4  mov     rax, [rax+68h]
0x1801f86f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f86fd  mov     eax, [rbx+1940h]
0x1801f8703  mov     edx, [rbx+18C8h]
0x1801f8709  mov     ecx, [rbx+18D0h]
0x1801f870f  mov     dword ptr [rbp+4Fh+pidl], eax
0x1801f8712  lea     rax, [rbp+4Fh+pidl]
0x1801f8716  mov     [rsp+100h+var_E0], rax
0x1801f871b  call    ?Post@?$TFlatIsoMessage@ULCIE_USERREFRESH@@@@SAJKKKKPEBULCIE_USERREFRESH@@@Z; TFlatIsoMessage<LCIE_USERREFRESH>::Post(ulong,ulong,ulong,ulong,LCIE_USERREFRESH const *)
0x1801f8720  cmp     [r15+24h], edi
0x1801f8724  jnz     loc_1801F881C
0x1801f872a  mov     rcx, [rbp+4Fh+ppstm]
0x1801f872e  lea     rdx, [rsi+30h]
0x1801f8732  mov     rax, [rcx]
0x1801f8735  mov     rax, [rax+68h]
0x1801f8739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f873e  jmp     loc_1801F881C
0x1801f8743  xor     ebx, ebx
0x1801f8745  lea     edx, [rbx+3]
0x1801f8748  cmp     [r15+24h], edx
0x1801f874c  jl      loc_1801F881C
0x1801f8752  jmp     short loc_1801F875B
0x1801f8754  mov     rbx, [rsi+80h]
0x1801f875b  lea     rdx, [rbp+4Fh+pidl]
0x1801f875f  mov     [rbp+4Fh+pidl], 0
0x1801f8767  lea     rcx, [rsi+30h]
0x1801f876b  mov     [rbp+4Fh+Block], 0
0x1801f8773  call    VariantToIDList
0x1801f8778  test    eax, eax
0x1801f877a  js      short loc_1801F87E2
0x1801f877c  mov     rcx, [rbp+4Fh+pidl]
0x1801f8780  lea     r8, [rbp+4Fh+Block]
0x1801f8784  mov     edx, 3002B84h
0x1801f8789  call    IUriFromPidl
0x1801f878e  test    eax, eax
0x1801f8790  js      short loc_1801F87E2
0x1801f8792  mov     rcx, [rbp+4Fh+pidl]; pidl
0x1801f8796  call    cs:__imp_ILFree
0x1801f879d  nop     dword ptr [rax+rax+00h]
0x1801f87a2  mov     rcx, [rbp+4Fh+Block]
0x1801f87a6  lea     r8, [rbp+4Fh+var_50]
0x1801f87aa  mov     qword ptr [rbp+4Fh+var_50.Data1], 0
0x1801f87b2  xor     r9d, r9d
0x1801f87b5  mov     rax, [rcx]
0x1801f87b8  lea     edx, [r9+0Bh]
0x1801f87bc  mov     rax, [rax+18h]
0x1801f87c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f87c5  test    eax, eax
0x1801f87c7  js      short loc_1801F87E2
0x1801f87c9  mov     rdx, qword ptr [rbp+4Fh+var_50.Data1]; unsigned __int16 *
0x1801f87cd  test    rdx, rdx
0x1801f87d0  jz      short loc_1801F87E2
0x1801f87d2  mov     rcx, [rbp+4Fh+ppstm]; struct IWebBrowser2 *
0x1801f87d6  mov     r8, rbx; unsigned __int16 *
0x1801f87d9  call    ?_NavigateWithReferrer@@YAJPEAUIWebBrowser2@@PEAG1K@Z; _NavigateWithReferrer(IWebBrowser2 *,ushort *,ushort *,ulong)
0x1801f87de  test    eax, eax
0x1801f87e0  jns     short loc_1801F8813
0x1801f87e2  mov     rcx, [rbp+4Fh+ppstm]
0x1801f87e6  lea     rdx, [rbp+4Fh+var_90]
0x1801f87ea  mov     qword ptr [rsp+100h+var_D8], rdx
0x1801f87ef  lea     r8, [rsi+48h]
0x1801f87f3  lea     rdx, [rbp+4Fh+var_90]
0x1801f87f7  mov     [rsp+100h+var_E0], rdx
0x1801f87fc  lea     r9, [rbp+4Fh+var_90]
0x1801f8800  mov     rax, [rcx]
0x1801f8803  lea     rdx, [rsi+30h]
0x1801f8807  mov     rax, [rax+1A0h]
0x1801f880e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8813  lea     rcx, [rbp+4Fh+Block]; void *
0x1801f8817  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801f881c  mov     rcx, [rbp+4Fh+ppstm]
0x1801f8820  mov     rax, [rcx]
0x1801f8823  mov     rax, [rax+10h]
0x1801f8827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f882c  test    rsi, rsi
  ... truncated ...
```
