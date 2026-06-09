# CShellBrowser2::_BrowserTab_MsgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1801df42c`
- end: `0x1801e05d2`
- name: `?_BrowserTab_MsgProc@CShellBrowser2@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `4518`
- prototype: `__int64 __usercall@<rax>(CShellBrowser2 *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ee2b0`

## callees

- `0x18000b9e0`
- `0x180012140`
- `0x18001ba58`
- `0x1800231c4`
- `0x18002a710`
- `0x1800341a0`
- `0x180049a54`
- `0x18006fec8`
- `0x18006ff5c`
- `0x180073354`
- `0x180087978`
- `0x1800927d8`
- `0x180095e10`
- `0x18009bd88`
- `0x1800d4ac4`
- `0x1801a8808`
- `0x1801b7f70`
- `0x1801da658`
- `0x1801db1bc`
- `0x1801db480`
- `0x1801de644`
- `0x1801de6c8`
- `0x1801df42c`
- `0x1801e0bf0`
- `0x1801e11c8`
- `0x1801e2a80`
- `0x1801e2cd8`
- `0x1801e2e2c`
- `0x1801e5648`
- `0x1801e5bac`
- `0x1801e6368`
- `0x1801e683c`
- `0x1801e6a7c`
- `0x1801eb8c4`
- `0x180244fbc`
- `0x180245208`
- `0x1802452d0`
- `0x18024c4f4`
- `0x18024cd54`
- `0x1803f6978`
- `0x18043b970`
- `0x18043ba94`
- `0x1804e48c8`
- `0x1804e6f6c`
- `0x180537f38`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `msvcrt!free` at `0x1801dfa90`
- `msvcrt!free` at `0x1801dfa90`
- `KERNEL32!SetEvent` at `0x1801e001e`
- `KERNEL32!SetEvent` at `0x1801e001e`
- `KERNEL32!CloseHandle` at `0x1801e002c`
- `KERNEL32!CloseHandle` at `0x1801e002c`
- `KERNEL32!GetCurrentThreadId` at `0x1801df997`
- `KERNEL32!GetCurrentThreadId` at `0x1801df997`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801dfa63`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801dfa86`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801dfa63`
- `USER32!SetThreadDpiAwarenessContext` at `0x1801dfa86`
- `USER32!PostMessageW` at `0x1801df9cc`
- `USER32!PostMessageW` at `0x1801df9cc`
- `OLEAUT32!__imp_SysAllocString` at `0x1801dfbad`
- `OLEAUT32!__imp_SysAllocString` at `0x1801dfbad`
- `OLEAUT32!__imp_SysFreeString` at `0x1801dfbc9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801dfbc9`
- `SHELL32!__imp_ILFree` at `0x1801df854`
- `SHELL32!__imp_ILFree` at `0x1801df854`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801df681`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e0177`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e01f9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e02de`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e03a1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e0433`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e04ab`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801df681`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e0177`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e01f9`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e02de`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e03a1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e0433`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801e04ab`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1801dfebe`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1801dfebe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801dfbd3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801dfdb9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801dfbd3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801dfdb9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801dfdc8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801dfdc8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1801dfed6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1801dfed6`
- `WININET!InternetShowSecurityInfoByURLW` at `0x1801dfa7d`
- `WININET!InternetShowSecurityInfoByURLW` at `0x1801dfa7d`
- `msIso!__imp_?LCIESerializable_UnpackWStr@@YAKPEAPEAGW4LCIESerializable_UnpackWStr_Enum@@_KPEBE@Z` at `0x1801dfa3b`
- `msIso!__imp_?LCIESerializable_UnpackWStr@@YAKPEAPEAGW4LCIESerializable_UnpackWStr_Enum@@_KPEBE@Z` at `0x1801dfa3b`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801dfaff`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801dffd8`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801e0075`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801dfaff`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801dffd8`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x1801e0075`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801df926`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801dfb39`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801dfc16`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801dfc88`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e01aa`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e022e`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e0311`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e0466`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e04de`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801df926`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801dfb39`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801dfc16`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801dfc88`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e01aa`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e022e`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e0311`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e0466`
- `msIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x1801e04de`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801df9f4`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801df9f4`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801e0591`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801e0591`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801df464`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801df464`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801df4a9`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801df916`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801dfb27`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801dfc04`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801dfc78`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e019a`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e021c`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e0301`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e0456`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e04ce`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801df4a9`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801df916`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801dfb27`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801dfc04`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801dfc78`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e019a`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e021c`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e0301`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e0456`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801e04ce`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801e059a`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801e059a`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801df555`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801df734`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801df555`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x1801df734`

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
  char *v78; // rax
  unsigned int *v79; // rax
  unsigned int v80; // edi
  __int64 (__fastcall ***v81)(_QWORD, GUID *, void **); // rcx
  int v82; // eax
  int v83; // edx
  int v84; // ecx
  char *v85; // rax
  void *v86; // rax
  __int64 v87; // rcx
  unsigned int v88; // edi
  unsigned int v90; // [rsp+20h] [rbp-91h]
  int v91; // [rsp+20h] [rbp-91h]
  void *Block; // [rsp+40h] [rbp-71h] BYREF
  char v93[8]; // [rsp+48h] [rbp-69h] BYREF
  struct LCIEPackedBuffer *v94; // [rsp+50h] [rbp-61h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-59h] BYREF
  LPSTREAM ppstm[2]; // [rsp+60h] [rbp-51h] BYREF
  struct tagMSLLHOOKSTRUCT v97; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v98; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v99[20]; // [rsp+98h] [rbp-19h] BYREF
  int v100; // [rsp+ACh] [rbp-5h]
  struct _GUID v101; // [rsp+B0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  WindowsMessageNumber = IsoGetWindowsMessageNumber(3);
  if ( a5 )
  {
    v94 = 0;
    v98 = 0;
    v9 = 1;
    if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, &v94, &v98) >= 0 )
    {
      v99[16] = 0;
      v100 = 0;
      v101 = (struct _GUID)*((_OWORD *)v94 + 1);
      ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)v99, &v101);
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
                *(_QWORD *)&v101.Data1 = 0;
                if ( (int)IsoGetArtifactAddress(a5, 0xDu, (struct _IsoArtifact **)&v101, 0) >= 0 )
                {
                  v36 = *(_QWORD *)(*(_QWORD *)&v101.Data1 + 16LL);
                  if ( v36 >= 0x2A && v36 >= (unsigned __int64)*((unsigned int *)v94 + 9) + 32 )
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
              goto LABEL_251;
            case 0x101u:
              if ( a3 != WindowsMessageNumber )
                PostMessageW(*((HWND *)this + 43), 0x10u, 0, 0);
              goto LABEL_251;
            case 0xC03u:
            case 0xC04u:
              if ( a3 != WindowsMessageNumber )
              {
                v34 = (unsigned int)v94;
                CurrentThreadId = GetCurrentThreadId();
                LayerAsyncBoundaryManager::ApplyMessageToBoundary(
                  (LayerAsyncBoundaryManager *)CurrentThreadId,
                  v34,
                  0,
                  0,
                  v90);
              }
              goto LABEL_251;
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
                v97.pt = (POINT)*((_QWORD *)v31 + 1);
                *(_QWORD *)&v97.mouseData = *((_QWORD *)v31 + 3);
                *(_QWORD *)&v97.time = *((unsigned int *)v31 + 4);
                v32 = *((_QWORD *)v31 + 4);
                v33 = *(_QWORD *)v31;
                v97.dwExtraInfo = v32;
                CallDetourHookHandler(7, v33, (__int64)&v97);
              }
              goto LABEL_251;
          }
          if ( a4 != 3128 )
          {
            if ( a4 == 3129 || a4 - 3130 <= 1 )
            {
              if ( a3 == WindowsMessageNumber )
                goto LABEL_251;
              LCIE2ChangeComponentSharedFlagBit_FromComponentThread(1, 8u);
              ppstm[0] = 0;
              if ( (*(int (__fastcall **)(char *, GUID *, GUID *, LPSTREAM *))(*((_QWORD *)this + 4) + 24LL))(
                     (char *)this + 32,
                     &IID_IWebBrowserApp,
                     &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
                     ppstm) < 0 )
                goto LABEL_251;
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
                    goto LABEL_251;
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
              LCIEMessagePortChannelHost::HandleMessage(v74, v73, a5, v94, v98);
LABEL_252:
              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)v99);
              return 0;
            }
LABEL_251:
            IsoFreeMessageBuffer(a5);
            goto LABEL_252;
          }
          if ( a3 == WindowsMessageNumber )
            goto LABEL_251;
          v13 = v94;
          Block = 0;
          memset(&v97, 0, 24);
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
                      *(_QWORD *)&v101.Data1 = v19;
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
                          &v97,
                          &v97,
                          &v97,
                          &v97);
                      }
                      else
                      {
                        v23 = (struct tagVARIANT *)(v16 + 120);
                        if ( v18 < 5 )
                          v23 = (struct tagVARIANT *)&v97;
                        CShellBrowser2::_DualEngineNavigateWithPostData(
                          this,
                          (struct IWebBrowser2 *)ppstm[0],
                          *(unsigned __int16 **)&v101.Data1,
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
                  &v97,
                  &v97,
                  &v97);
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
                    *(_QWORD *)&v101.Data1 = 0,
                    (*(int (__fastcall **)(void *, __int64, struct _GUID *))(*(_QWORD *)Block + 24LL))(Block, 11, &v101) < 0)
                || !*(_QWORD *)&v101.Data1
                || (int)_NavigateWithReferrer(
                          (struct IWebBrowser2 *)ppstm[0],
                          *(unsigned __int16 **)&v101.Data1,
                          v28,
                          v29) < 0 )
              {
                (*(void (__fastcall **)(LPSTREAM, char *, char *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *, struct tagMSLLHOOKSTRUCT *))(*(_QWORD *)ppstm[0] + 416LL))(
                  ppstm[0],
                  v16 + 48,
                  v16 + 72,
                  &v97,
                  &v97,
                  &v97);
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
          ATL::CComVariant::Clear((ATL::CComVariant *)&v97);
          goto LABEL_251;
        }
        switch ( a4 )
        {
          case 0xC45u:
            CShellBrowser2::_OnConfirmedClose(this, 0);
            goto LABEL_251;
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
              v97.pt = (POINT)*((_QWORD *)v50 + 1);
              v97.mouseData = *((_DWORD *)v50 + 4);
              v97.flags = *((_DWORD *)v50 + 5);
              *(_QWORD *)&v97.time = *((unsigned int *)v50 + 6);
              v51 = *((_QWORD *)v50 + 4);
              v52 = *(_QWORD *)v50;
              v97.dwExtraInfo = v51;
              ForwardLowlevelMouseHookEvents(v52, &v97);
            }
            goto LABEL_251;
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
              *(_OWORD *)&v97.pt.x = v46;
              *(_QWORD *)&v97.time = v47;
              ForwardLowlevelKeyboardHookEvents(v48, (const struct tagKBDLLHOOKSTRUCT *)&v97);
            }
            goto LABEL_251;
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
            goto LABEL_252;
          }
          if ( a4 != 3327 )
          {
            if ( a4 == 3359 )
            {
              CShellBrowser2::_SuspendForDeferredUnload(this);
              goto LABEL_251;
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
        goto LABEL_251;
      }
      if ( a4 > 0xD3F )
      {
        if ( a4 == 3393 )
        {
          if ( v94 )
          {
            v87 = *((_QWORD *)this + 50);
            v88 = *((_DWORD *)v94 + 8);
            if ( !v87
              || (memset(&v97, 0, 24),
                  v97.mouseData = v88,
                  LOWORD(v97.pt.x) = 3,
                  (*(int (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v87 + 32LL))(
                    v87,
                    &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                    95) < 0) )
            {
              IsoUnlockArtifact(v88);
            }
          }
          goto LABEL_251;
        }
        if ( a4 != 5125 )
        {
          switch ( a4 )
          {
            case 0x1406u:
              if ( v94 && IsDualEngineProcess() )
              {
                Block = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
                  || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x2Cu) )
                {
                  v85 = (char *)Block;
                }
                else
                {
                  v85 = 0;
                  Block = 0;
                }
                if ( v85 && v85 != (char *)-32LL )
                  CShellBrowser2::_DualEngineSimulateMouseInput(this, (struct LCIE_SIMULATEMOUSE_DATA *)(v85 + 32));
              }
              goto LABEL_251;
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
                v83 = *((_DWORD *)this + 1586);
                v84 = *((_DWORD *)this + 1587);
                v93[0] = v9;
                TFlatIsoMessage<bool>::Post(v84, v83, 5129, 0, (__int64)v93);
              }
              goto LABEL_251;
            case 0x140Au:
              if ( v94 && IsDualEngineProcess() )
              {
                Block = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
                  || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x24u) )
                {
                  v78 = (char *)Block;
                }
                else
                {
                  v78 = 0;
                  Block = 0;
                }
                if ( v78 )
                {
                  v79 = (unsigned int *)(v78 + 32);
                  if ( v79 )
                  {
                    v80 = *v79;
                    v81 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 44);
                    Block = 0;
                    v82 = (**v81)(v81, &GUID_63416179_2ee8_4973_a86a_5897992097a9, &Block);
                    if ( v82 < 0 )
                      wil::details::in1diag3::FailFast_Hr(
                        retaddr,
                        (void *)0x4730,
                        (unsigned int)"inetcore\\ieframe\\browseui\\shbrows2.cpp",
                        (const char *)(unsigned int)v82,
                        v91);
                    (*(void (__fastcall **)(void *, CShellBrowser2 *, _QWORD, _QWORD))(*(_QWORD *)Block + 64LL))(
                      Block,
                      this,
                      v80,
                      0);
                    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&Block);
                  }
                }
              }
              goto LABEL_251;
            case 0x1414u:
              if ( v94 && IsDualEngineProcess() )
              {
                *(_QWORD *)&v101.Data1 = 0;
                if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&v101, 0) < 0
                  || (v71 = !VerifyUntrusted_IsoMessage_ExactSize(a5, 0x106Cu), v76 = 0, !v71) )
                {
                  v76 = *(_QWORD *)&v101.Data1;
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
                      *(_QWORD *)&v97.time = 0;
                      v97.pt = (POINT)0x4000LL;
                      *(_QWORD *)&v97.mouseData = v77;
                      (*(void (__fastcall **)(void *, const struct _GUID *, __int64))(*(_QWORD *)Block + 32LL))(
                        Block,
                        &CGID_DocHostCmdPriv,
                        25);
                    }
                    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&Block);
                  }
                }
              }
              goto LABEL_251;
            case 0x1417u:
              if ( v94 && IsDualEngineProcess() )
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
              goto LABEL_251;
          }
          goto LABEL_189;
        }
        if ( !v94 || !IsDualEngineProcess() )
          goto LABEL_251;
        Block = 0;
        if ( (int)IsoGetMessageBufferAddress(a5, 1, 0, (struct _IsoMessage **)&Block, 0) < 0
          || VerifyUntrusted_IsoMessage_ExactSize(a5, 0x28u) )
        {
          v86 = Block;
        }
        else
        {
          v86 = 0;
          Block = 0;
        }
        if ( !v86 || v86 == (void *)-32LL )
          goto LABEL_251;
        *((_BYTE *)this + 6221) = 1;
        CShellBrowser2::_DualEngineSimulateKeyEvent(this, *((_DWORD *)v86 + 8), *((_BYTE *)v86 + 36));
        v40 = *((_DWORD *)this + 1588);
        v39 = 5127;
        goto LABEL_96;
      }
      switch ( a4 )
      {
        case 0xD3Fu:
          if ( v94 )
          {
            v71 = *((_BYTE *)this + 6700) == 0;
            *((_DWORD *)this + 1674) = *((_DWORD *)v94 + 17);
            if ( !v71 )
              CShellBrowser2::_CreateAndSendPreviewImageForFlipAhead(this);
          }
          goto LABEL_251;
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
          goto LABEL_251;
        case 0xD2Cu:
          if ( v98 >= 0x3A8 )
          {
            CShellBrowser2::_KeepProcessAlive(this, 1);
            v63 = LCIEUnpackIETHREADPARAM((struct LCIEPackedBuffer *)((char *)v94 + 432), v98 - 936);
            if ( v63 )
            {
              if ( (Microsoft_IEFRAMEEnableBits & 0x20000) != 0 )
                McGenEventWrite_EventWriteTransfer(
                  BERP_IEFRAME2_Context,
                  EmptyTab_Reuse_ReinitializeBrowserTab_Begin,
                  v64,
                  1,
                  &v101);
              v66 = CShellBrowser2::_InitializeWindow(this, v63, 1);
              if ( v66 < 0 )
              {
                if ( (Microsoft_IEFRAMEEnableBits & 0x20000) != 0 )
                  McGenEventWrite_EventWriteTransfer(
                    BERP_IEFRAME2_Context,
                    EmptyTab_Reuse_ReinitializeBrowserTab_Failed,
                    v65,
                    1,
                    &v101);
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
                goto LABEL_251;
            }
          }
          v39 = 3375;
          break;
        case 0xD30u:
          if ( !v94 )
            goto LABEL_251;
          v60 = *((_DWORD *)v94 + 8);
          v61 = *((_DWORD *)v94 + 9);
          v62 = (char *)v94 + 40;
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
                goto LABEL_251;
              v57 = *((_QWORD *)this + 50);
              if ( !v57 )
                goto LABEL_251;
              v58 = 84;
              break;
            case 0xD33u:
              v56 = TFlatIsoMessage<LCIE_CORRELATEDVTABCONTEXT>::VerifyExactSize((unsigned int)a5);
              if ( !v56 )
                goto LABEL_251;
              v57 = *((_QWORD *)this + 50);
              if ( !v57 )
                goto LABEL_251;
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
              goto LABEL_251;
            default:
              goto LABEL_189;
          }
          v59 = *(_DWORD *)(v56 + 32);
          memset(&v97, 0, 24);
          v97.mouseData = v59;
          LOWORD(v97.pt.x) = 19;
          (*(void (__fastcall **)(__int64, GUID *, __int64, _QWORD, struct tagMSLLHOOKSTRUCT *, _QWORD))(*(_QWORD *)v57 + 32LL))(
            v57,
            &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
            v58,
            0,
            &v97,
            0);
          goto LABEL_66;
      }
LABEL_95:
      v40 = *((_DWORD *)this + 1587);
LABEL_96:
      v41 = *((_DWORD *)this + 1586);
LABEL_97:
      LCIEPostMessageWithoutBuffer(v40, v41, v39, 0);
      goto LABEL_251;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801df42c  mov     [rsp-8+arg_8], rbx
0x1801df431  push    rbp
0x1801df432  push    rsi
0x1801df433  push    rdi
0x1801df434  push    r12
0x1801df436  push    r13
0x1801df438  push    r14
0x1801df43a  push    r15
0x1801df43c  lea     rbp, [rsp-1Fh]
0x1801df441  sub     rsp, 0D0h
0x1801df448  mov     rax, cs:__security_cookie
0x1801df44f  xor     rax, rsp
0x1801df452  mov     [rbp+4Fh+var_40], rax
0x1801df456  mov     rbx, rcx
0x1801df459  mov     rsi, r9
0x1801df45c  mov     ecx, 3
0x1801df461  mov     r15d, r8d
0x1801df464  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x1801df46a  mov     r14, qword ptr [rbp+4Fh+arg_20]
0x1801df46e  cmp     r15d, eax
0x1801df471  mov     r12d, eax
0x1801df474  setz    r13b
0x1801df478  test    r14, r14
0x1801df47b  jz      loc_1801E05A9
0x1801df481  xor     r8d, r8d
0x1801df484  mov     [rbp+4Fh+var_B0], 0
0x1801df48c  lea     rax, [rbp+4Fh+var_70]
0x1801df490  mov     [rbp+4Fh+var_70], 0
0x1801df497  lea     r9, [rbp+4Fh+var_B0]
0x1801df49b  mov     [rsp+100h+var_E0], rax; unsigned int
0x1801df4a0  mov     ecx, r14d
0x1801df4a3  lea     edi, [r8+1]
0x1801df4a7  mov     edx, edi
0x1801df4a9  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x1801df4af  test    eax, eax
0x1801df4b1  js      loc_1801E05A9
0x1801df4b7  mov     rax, [rbp+4Fh+var_B0]
0x1801df4bb  lea     rdx, [rbp+4Fh+var_50]; struct _GUID
0x1801df4bf  lea     rcx, [rbp+4Fh+var_68]; this
0x1801df4c3  mov     [rbp+4Fh+var_58], 0
0x1801df4c7  mov     [rbp+4Fh+var_54], 0
0x1801df4ce  movups  xmm0, xmmword ptr [rax+10h]
0x1801df4d2  movdqu  xmmword ptr [rbp+4Fh+var_50.Data1], xmm0
0x1801df4d7  call    ?Set@ThreadUserInputIdSetter@@QEAAXU_GUID@@@Z; ThreadUserInputIdSetter::Set(_GUID)
0x1801df4dc  mov     eax, 0D23h
0x1801df4e1  cmp     esi, eax
0x1801df4e3  ja      loc_1801DFD2D
0x1801df4e9  jz      loc_1801DFCFA
0x1801df4ef  mov     eax, 0C3Fh
0x1801df4f4  cmp     esi, eax
0x1801df4f6  ja      loc_1801DFA9B
0x1801df4fc  jz      loc_1801DF9D7
0x1801df502  mov     eax, esi
0x1801df504  sub     eax, 101h
0x1801df509  jz      loc_1801DF9B2
0x1801df50f  sub     eax, 0B02h
0x1801df514  jz      loc_1801DF98A
0x1801df51a  sub     eax, edi
0x1801df51c  jz      loc_1801DF98A
0x1801df522  sub     eax, 1Bh
0x1801df525  jz      loc_1801DF8FF
0x1801df52b  sub     eax, 19h
0x1801df52e  jz      loc_1801DF5DC
0x1801df534  sub     eax, edi
0x1801df536  jz      short loc_1801DF544
0x1801df538  sub     eax, edi
0x1801df53a  jz      short loc_1801DF544
0x1801df53c  cmp     eax, edi
0x1801df53e  jnz     loc_1801E012B
0x1801df544  cmp     r15d, r12d
0x1801df547  jz      loc_1801E0597
0x1801df54d  mov     edx, 8
0x1801df552  mov     cl, dil
0x1801df555  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z; LCIE2ChangeComponentSharedFlagBit_FromComponentThread(bool,ulong)
0x1801df55b  lea     rcx, [rbx+20h]
0x1801df55f  mov     [rbp+4Fh+ppstm], 0
0x1801df567  mov     rax, [rcx]
0x1801df56a  lea     r9, [rbp+4Fh+ppstm]
0x1801df56e  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x1801df575  lea     rdx, IID_IWebBrowserApp
0x1801df57c  mov     rax, [rax+18h]
0x1801df580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df585  test    eax, eax
0x1801df587  js      loc_1801E0597
0x1801df58d  sub     esi, 0C39h
0x1801df593  jz      short loc_1801DF5B7
0x1801df595  sub     esi, edi
0x1801df597  jz      short loc_1801DF5AA
0x1801df599  cmp     esi, edi
0x1801df59b  jnz     short loc_1801DF5C7
0x1801df59d  mov     rcx, [rbp+4Fh+ppstm]
0x1801df5a1  mov     rax, [rcx]
0x1801df5a4  mov     rax, [rax+70h]
0x1801df5a8  jmp     short loc_1801DF5C2
0x1801df5aa  mov     rcx, [rbp+4Fh+ppstm]
0x1801df5ae  mov     rax, [rcx]
0x1801df5b1  mov     rax, [rax+38h]
0x1801df5b5  jmp     short loc_1801DF5C2
0x1801df5b7  mov     rcx, [rbp+4Fh+ppstm]
0x1801df5bb  mov     rax, [rcx]
0x1801df5be  mov     rax, [rax+40h]
0x1801df5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df5c7  mov     rcx, [rbp+4Fh+ppstm]
0x1801df5cb  mov     rax, [rcx]
0x1801df5ce  mov     rax, [rax+10h]
0x1801df5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df5d7  jmp     loc_1801E0597
0x1801df5dc  cmp     r15d, r12d
0x1801df5df  jz      loc_1801E0597
0x1801df5e5  mov     r15, [rbp+4Fh+var_B0]
0x1801df5e9  lea     r9, [rbp+4Fh+Block]; struct ATL::CComVariant **
0x1801df5ed  xor     eax, eax
0x1801df5ef  mov     [rbp+4Fh+Block], 0
0x1801df5f7  xorps   xmm0, xmm0
0x1801df5fa  mov     [rbp+4Fh+var_90.dwExtraInfo], rax
0x1801df5fe  xor     r8d, r8d; bool
0x1801df601  mov     [rsp+100h+var_E0], rax; int *
0x1801df606  mov     edx, r14d; unsigned int
0x1801df609  xor     ecx, ecx; int
0x1801df60b  movups  xmmword ptr [rbp+4Fh+var_90.vkCode], xmm0
0x1801df60f  call    ?LCIE_IEFRAME_VariantArrayUnpack@@YAJHK_NPEAPEAVCComVariant@ATL@@PEAJ@Z; LCIE_IEFRAME_VariantArrayUnpack(int,ulong,bool,ATL::CComVariant * *,long *)
0x1801df614  test    eax, eax
0x1801df616  js      loc_1801DF8F1
0x1801df61c  lea     rcx, [rbx+20h]
0x1801df620  mov     [rbp+4Fh+ppstm], 0
0x1801df628  mov     rax, [rcx]
0x1801df62b  lea     r9, [rbp+4Fh+ppstm]
0x1801df62f  lea     r8, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x1801df636  lea     rdx, IID_IWebBrowserApp
0x1801df63d  mov     rax, [rax+18h]
0x1801df641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df646  mov     rsi, [rbp+4Fh+Block]
0x1801df64a  test    eax, eax
0x1801df64c  js      loc_1801DF8E4
0x1801df652  mov     ecx, [r15+28h]
0x1801df656  xor     r12b, r12b
0x1801df659  sub     ecx, edi
0x1801df65b  jz      loc_1801DF72C
0x1801df661  sub     ecx, edi
0x1801df663  jz      loc_1801DF79D
0x1801df669  sub     ecx, edi
0x1801df66b  jz      loc_1801DF7DE
0x1801df671  sub     ecx, edi
0x1801df673  jz      loc_1801DF729
0x1801df679  cmp     ecx, edi
0x1801df67b  jnz     loc_1801DF8D4
0x1801df681  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801df687  test    al, al
0x1801df689  jz      loc_1801DF8D4
0x1801df68f  mov     r15d, [r15+24h]
0x1801df693  cmp     r15d, 2
0x1801df697  jl      loc_1801DF8D4
0x1801df69d  mov     rax, [rsi+38h]
0x1801df6a1  xor     r13d, r13d
0x1801df6a4  mov     ecx, [rsi+50h]
0x1801df6a7  mov     qword ptr [rbp+4Fh+var_50.Data1], rax
0x1801df6ab  mov     dword ptr [rbp+4Fh+pidl], ecx
0x1801df6ae  lea     edx, [r13+3]
0x1801df6b2  cmp     r15d, edx
0x1801df6b5  jl      short loc_1801DF6BB
0x1801df6b7  mov     r13, [rsi+68h]
0x1801df6bb  xor     r12d, r12d
0x1801df6be  cmp     r15d, 4
0x1801df6c2  jl      short loc_1801DF6CB
0x1801df6c4  mov     r12, [rsi+80h]
0x1801df6cb  mov     rcx, rax
0x1801df6ce  call    GetUrlSchemeW
0x1801df6d3  add     eax, 0FFFFFFF1h
0x1801df6d6  cmp     eax, edi
0x1801df6d8  jbe     short loc_1801DF711
0x1801df6da  lea     rax, [rsi+78h]
0x1801df6de  cmp     r15d, 5
0x1801df6e2  jge     short loc_1801DF6E8
0x1801df6e4  lea     rax, [rbp+4Fh+var_90]
0x1801df6e8  mov     r8, qword ptr [rbp+4Fh+var_50.Data1]; unsigned __int16 *
0x1801df6ec  mov     r9, r13; unsigned __int16 *
0x1801df6ef  mov     rdx, [rbp+4Fh+ppstm]; struct IWebBrowser2 *
0x1801df6f3  mov     rcx, rbx; this
0x1801df6f6  mov     [rsp+100h+var_D0], rax; struct tagVARIANT *
0x1801df6fb  mov     eax, dword ptr [rbp+4Fh+pidl]
0x1801df6fe  mov     [rsp+100h+var_D8], eax; unsigned int
0x1801df702  mov     [rsp+100h+var_E0], r12; unsigned __int16 *
0x1801df707  call    ?_DualEngineNavigateWithPostData@CShellBrowser2@@AEAAXPEAUIWebBrowser2@@PEAG11KAEAUtagVARIANT@@@Z; CShellBrowser2::_DualEngineNavigateWithPostData(IWebBrowser2 *,ushort *,ushort *,ushort *,ulong,tagVARIANT &)
0x1801df70c  jmp     loc_1801DF8D4
0x1801df711  lea     r8, [rbp+4Fh+var_90]
0x1801df715  mov     qword ptr [rsp+100h+var_D8], r8
0x1801df71a  lea     r8, [rbp+4Fh+var_90]
0x1801df71e  mov     [rsp+100h+var_E0], r8
0x1801df723  lea     r8, [rbp+4Fh+var_90]
0x1801df727  jmp     short loc_1801DF77D
0x1801df729  mov     r12b, dil
0x1801df72c  mov     edx, 8
0x1801df731  mov     cl, dil
0x1801df734  call    cs:__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z; LCIE2ChangeComponentSharedFlagBit_FromComponentThread(bool,ulong)
0x1801df73a  cmp     dword ptr [r15+24h], 4
0x1801df73f  jz      loc_1801DF812
0x1801df745  test    r12b, r12b
0x1801df748  jnz     loc_1801DF801
0x1801df74e  test    [rsi+68h], dil
0x1801df752  jnz     loc_1801DF801
0x1801df758  mov     edx, 3
0x1801df75d  cmp     [r15+24h], edx
0x1801df761  jnz     loc_1801DF8D4
0x1801df767  lea     r9, [rbp+4Fh+var_90]
0x1801df76b  mov     qword ptr [rsp+100h+var_D8], r9
0x1801df770  lea     r8, [rsi+48h]
0x1801df774  lea     r9, [rbp+4Fh+var_90]
0x1801df778  mov     [rsp+100h+var_E0], r9
0x1801df77d  mov     rcx, [rbp+4Fh+ppstm]
0x1801df781  lea     r9, [rbp+4Fh+var_90]
0x1801df785  lea     rdx, [rsi+30h]
0x1801df789  mov     rax, [rcx]
0x1801df78c  mov     rax, [rax+1A0h]
0x1801df793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df798  jmp     loc_1801DF8D4
0x1801df79d  cmp     [r15+24h], edi
0x1801df7a1  jnz     loc_1801DF8D4
0x1801df7a7  mov     rcx, [rbp+4Fh+ppstm]
0x1801df7ab  lea     rdx, [rsi+30h]
0x1801df7af  mov     rax, [rcx]
0x1801df7b2  mov     rax, [rax+68h]
0x1801df7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df7bb  mov     eax, [rbx+1940h]
0x1801df7c1  mov     edx, [rbx+18C8h]
0x1801df7c7  mov     ecx, [rbx+18D0h]
0x1801df7cd  mov     dword ptr [rbp+4Fh+pidl], eax
0x1801df7d0  lea     rax, [rbp+4Fh+pidl]
0x1801df7d4  mov     [rsp+100h+var_E0], rax
0x1801df7d9  call    ?Post@?$TFlatIsoMessage@ULCIE_USERREFRESH@@@@SAJKKKKPEBULCIE_USERREFRESH@@@Z; TFlatIsoMessage<LCIE_USERREFRESH>::Post(ulong,ulong,ulong,ulong,LCIE_USERREFRESH const *)
0x1801df7de  cmp     [r15+24h], edi
0x1801df7e2  jnz     loc_1801DF8D4
0x1801df7e8  mov     rcx, [rbp+4Fh+ppstm]
0x1801df7ec  lea     rdx, [rsi+30h]
0x1801df7f0  mov     rax, [rcx]
0x1801df7f3  mov     rax, [rax+68h]
0x1801df7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df7fc  jmp     loc_1801DF8D4
0x1801df801  xor     ebx, ebx
0x1801df803  lea     edx, [rbx+3]
0x1801df806  cmp     [r15+24h], edx
0x1801df80a  jl      loc_1801DF8D4
0x1801df810  jmp     short loc_1801DF819
0x1801df812  mov     rbx, [rsi+80h]
0x1801df819  lea     rdx, [rbp+4Fh+pidl]
0x1801df81d  mov     [rbp+4Fh+pidl], 0
0x1801df825  lea     rcx, [rsi+30h]
0x1801df829  mov     [rbp+4Fh+Block], 0
0x1801df831  call    VariantToIDList
0x1801df836  test    eax, eax
0x1801df838  js      short loc_1801DF89A
0x1801df83a  mov     rcx, [rbp+4Fh+pidl]
0x1801df83e  lea     r8, [rbp+4Fh+Block]
0x1801df842  mov     edx, 3002B84h
0x1801df847  call    IUriFromPidl
0x1801df84c  test    eax, eax
0x1801df84e  js      short loc_1801DF89A
0x1801df850  mov     rcx, [rbp+4Fh+pidl]; pidl
0x1801df854  call    cs:__imp_ILFree
0x1801df85a  mov     rcx, [rbp+4Fh+Block]
0x1801df85e  lea     r8, [rbp+4Fh+var_50]
0x1801df862  mov     qword ptr [rbp+4Fh+var_50.Data1], 0
0x1801df86a  xor     r9d, r9d
0x1801df86d  mov     rax, [rcx]
0x1801df870  lea     edx, [r9+0Bh]
0x1801df874  mov     rax, [rax+18h]
0x1801df878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df87d  test    eax, eax
0x1801df87f  js      short loc_1801DF89A
0x1801df881  mov     rdx, qword ptr [rbp+4Fh+var_50.Data1]; unsigned __int16 *
0x1801df885  test    rdx, rdx
0x1801df888  jz      short loc_1801DF89A
0x1801df88a  mov     rcx, [rbp+4Fh+ppstm]; struct IWebBrowser2 *
0x1801df88e  mov     r8, rbx; unsigned __int16 *
0x1801df891  call    ?_NavigateWithReferrer@@YAJPEAUIWebBrowser2@@PEAG1K@Z; _NavigateWithReferrer(IWebBrowser2 *,ushort *,ushort *,ulong)
0x1801df896  test    eax, eax
0x1801df898  jns     short loc_1801DF8CB
0x1801df89a  mov     rcx, [rbp+4Fh+ppstm]
0x1801df89e  lea     rdx, [rbp+4Fh+var_90]
0x1801df8a2  mov     qword ptr [rsp+100h+var_D8], rdx
0x1801df8a7  lea     r8, [rsi+48h]
0x1801df8ab  lea     rdx, [rbp+4Fh+var_90]
0x1801df8af  mov     [rsp+100h+var_E0], rdx
0x1801df8b4  lea     r9, [rbp+4Fh+var_90]
0x1801df8b8  mov     rax, [rcx]
0x1801df8bb  lea     rdx, [rsi+30h]
0x1801df8bf  mov     rax, [rax+1A0h]
0x1801df8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df8cb  lea     rcx, [rbp+4Fh+Block]; void *
0x1801df8cf  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801df8d4  mov     rcx, [rbp+4Fh+ppstm]
0x1801df8d8  mov     rax, [rcx]
0x1801df8db  mov     rax, [rax+10h]
0x1801df8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df8e4  test    rsi, rsi
0x1801df8e7  jz      short loc_1801DF8F1
0x1801df8e9  mov     rcx, rsi; this
0x1801df8ec  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x1801df8f1  lea     rcx, [rbp+4Fh+var_90]; this
0x1801df8f5  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1801df8fa  jmp     loc_1801E0597
  ... truncated ...
```
