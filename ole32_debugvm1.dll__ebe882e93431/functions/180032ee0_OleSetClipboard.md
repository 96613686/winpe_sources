# OleSetClipboard

- ea: `0x180032ee0`
- end: `0x1800332c3`
- name: `OleSetClipboard`
- size: `995`
- prototype: `HRESULT __stdcall(LPDATAOBJECT pDataObj)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000ad34`
- `0x18000f900`
- `0x180019230`
- `0x180019454`
- `0x180032ee0`
- `0x1800368dc`
- `0x18003c1ec`
- `0x1800405b8`
- `0x180040640`
- `0x180051168`
- `0x180052390`
- `0x180053014`
- `0x180059088`
- `0x18008bdd4`
- `0x18008be08`
- `0x18008bf20`
- `0x18008de68`
- `0x18008e1d0`
- `0x18008e468`
- `0x1800c39a8`
- `0x1800c3a8c`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x180032fcf`
- `KERNELBASE!GetPackageFullName` at `0x180032fcf`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003300f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003300f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032fbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032fbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033090`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033224`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032f62`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180032f62`
- `combase!__imp_?CoVrfShouldCallOleInit@@YAXPEBD@Z` at `0x180032f3e`
- `combase!__imp_?CoVrfShouldCallOleInit@@YAXPEBD@Z` at `0x180032f3e`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceAppIdForClipboard` at `0x1800330a8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceAppIdForClipboard` at `0x1800330a8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetEnterpriseIdForClipboard` at `0x180033070`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetEnterpriseIdForClipboard` at `0x180033070`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18003305d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18003305d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpClearClipboardMetaData` at `0x180033041`
- `ext-ms-win-edputil-policy-l1-1-0!EdpClearClipboardMetaData` at `0x180033041`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180033033`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180033033`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18003309d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18003309d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceIsEnlightenedForClipboard` at `0x180033085`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceIsEnlightenedForClipboard` at `0x180033085`

## string_xrefs

- `0x1800331b9`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180033209`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x180033147`: `Software\Microsoft\Ole\AppCompat`

## pseudocode

```c
HRESULT __stdcall OleSetClipboard(LPDATAOBJECT pDataObj)
{
  const _GUID *v1; // r8
  int v4; // r14d
  unsigned int v5; // edx
  Quirks::QuirkStatus *ReservedForOle; // rcx
  HRESULT v7; // ebx
  const _GUID *v8; // r8
  HANDLE CurrentProcess; // rax
  LONG PackageFullName; // eax
  wchar_t *v11; // rsi
  HANDLE v12; // rax
  DWORD ProcessId; // eax
  DWORD CurrentProcessId; // eax
  DWORD v15; // eax
  const wchar_t *v16; // rdx
  TraceLevel v17; // r9d
  int file; // edx
  TraceLevel v19; // r9d
  IAllowAstaToAstaDeadlockRisk *ptr; // rcx
  RegistryKey key; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int uSuppressASTAAutoFlush; // [rsp+38h] [rbp-C8h] BYREF
  Microsoft::WRL::ComPtr<IAllowAstaToAstaDeadlockRisk> spAllowAstaToAstaDeadlockRisk; // [rsp+40h] [rbp-C0h] BYREF
  Microsoft::WRL::ComPtr<IAgileDataObject> spAgileDataObject; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t awchPackageChars[128]; // [rsp+60h] [rbp-A0h] BYREF

  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (_MCGEN_TRACE_CONTEXT *)pDataObj,
      &OLE_Clipboard_SetClipboard_Start,
      v1,
      1u,
      (_EVENT_DATA_DESCRIPTOR *)&spAgileDataObject);
  if ( !IsOleInitialized() )
  {
    CoVrfShouldCallOleInit("OleSetClipboard");
    return -2147221008;
  }
  InitOnceExecuteOnce(&g_initAppContainerState, lambda_50fe48bf199844a7ed15a94e5b76e4d1_::_lambda_invoker_cdecl_, 0, 0);
  v4 = g_isAppContainer;
  if ( g_isAppContainer )
  {
    if ( ClipboardInitializeBroker() )
    {
      v7 = ExecuteClipboardBrokerFunctionAndTryToRecoverIfFailureLikelyToIndicateBrokerAbnormalTermination__lambda_9370c4e5c64663684a8eb35dd7926c23_((OleSetClipboard::__l14::<lambda_9370c4e5c64663684a8eb35dd7926c23>)pDataObj);
    }
    else
    {
      v7 = -2147467259;
      OleInternalOriginateError(-2147467259, 0x12Fu);
    }
  }
  else
  {
    memset_0(awchPackageChars, 0, sizeof(awchPackageChars));
    uSuppressASTAAutoFlush = 128;
    CurrentProcess = GetCurrentProcess();
    PackageFullName = GetPackageFullName(CurrentProcess, &uSuppressASTAAutoFlush, awchPackageChars);
    v7 = PackageFullName;
    if ( PackageFullName )
    {
      v11 = 0;
      if ( PackageFullName != 15700 && PackageFullName != 5 )
      {
        if ( PackageFullName > 0 )
          v7 = (unsigned __int16)PackageFullName | 0x80070000;
        if ( v7 < 0 )
          goto LABEL_23;
      }
    }
    else
    {
      v11 = awchPackageChars;
    }
    v12 = GetCurrentProcess();
    ProcessId = GetProcessId(v12);
    v7 = OleSetClipboardInternal(pDataObj, 0, 0, v11, ProcessId);
    if ( v7 >= 0 && (unsigned int)EdpGetIsManaged() && (int)EdpClearClipboardMetaData() >= 0 )
    {
      key._hkey = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( (int)EdpGetContextForProcess(CurrentProcessId, &key) >= 0 )
      {
        EdpSetEnterpriseIdForClipboard(*((_QWORD *)key._hkey + 1));
        if ( (*(_BYTE *)key._hkey & 3) != 0 )
          EdpSetSourceIsEnlightenedForClipboard(1);
      }
      spAllowAstaToAstaDeadlockRisk.ptr_ = 0;
      v15 = GetCurrentProcessId();
      EdpGetAppLockerUniqueAppIdentifier(v15, &spAllowAstaToAstaDeadlockRisk);
      EdpSetSourceAppIdForClipboard(spAllowAstaToAstaDeadlockRisk.ptr_);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&spAllowAstaToAstaDeadlockRisk);
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > *)&key);
    }
  }
LABEL_23:
  if ( pDataObj )
  {
    ReservedForOle = (Quirks::QuirkStatus *)NtCurrentTeb()->ReservedForOle;
    if ( (ReservedForOle[5] & 0x40400080) == 0x400080 && !Quirks::IsQuirkEnabled(ReservedForOle, v5) )
    {
      spAgileDataObject.ptr_ = 0;
      if ( CarefullyQueryNewInterface(
             pDataObj,
             &GUID_06495cd4_3e37_2721_6e15_e077975f3d3d,
             (void **)&spAgileDataObject.ptr_) < 0 )
      {
        spAllowAstaToAstaDeadlockRisk.ptr_ = 0;
        if ( CarefullyQueryNewInterface(
               pDataObj,
               &GUID_77dd1250_139c_2bc3_bd95_900aced61be5,
               (void **)&spAllowAstaToAstaDeadlockRisk.ptr_) < 0 )
        {
          key._hkey = 0;
          if ( RegistryKey::StaticOpen(
                 (HKEY__ *)0xFFFFFFFF80000002LL,
                 L"Software\\Microsoft\\Ole\\AppCompat",
                 (unsigned int)v8,
                 (HKEY__ **)&key._hkey) < 0
            || (uSuppressASTAAutoFlush = 0, RegistryKey::ReadDWORDValue(&key, v16, &uSuppressASTAAutoFlush) < 0)
            || !uSuppressASTAAutoFlush )
          {
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
              || gfEnableTracing
              && IsWppLevelEnabled((TraceLevel)(Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 + 1)) )
            {
              ComTraceMessageT<>(
                "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                "OleSetClipboard",
                3675,
                v17,
                L"Auto-flushing clipboard due to non-agile IDataObject on ASTA");
            }
            file = OleFlushClipboard();
            if ( file < 0
              && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
            {
              ComTraceMessageT<long>(
                "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                "OleSetClipboard",
                3686,
                v19,
                L"Auto-flush of the clipboard failed, hr=%!HRESULT!",
                file);
            }
          }
          if ( key._hkey )
          {
            RegCloseKey(key._hkey);
            key._hkey = 0;
          }
        }
        ptr = spAllowAstaToAstaDeadlockRisk.ptr_;
        if ( spAllowAstaToAstaDeadlockRisk.ptr_ )
        {
          spAllowAstaToAstaDeadlockRisk.ptr_ = 0;
          ((void (__fastcall *)(IAllowAstaToAstaDeadlockRisk *))ptr->lpVtbl->Release)(ptr);
        }
      }
      ReservedForOle = (Quirks::QuirkStatus *)spAgileDataObject.ptr_;
      if ( spAgileDataObject.ptr_ )
      {
        spAgileDataObject.ptr_ = 0;
        (*(void (__fastcall **)(Quirks::QuirkStatus *))(*(_QWORD *)ReservedForOle + 16LL))(ReservedForOle);
      }
    }
  }
  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (_MCGEN_TRACE_CONTEXT *)ReservedForOle,
      &OLE_Clipboard_SetClipboard_Stop,
      v8,
      1u,
      (_EVENT_DATA_DESCRIPTOR *)&spAgileDataObject);
  OleClipboardAggregateTelemetry::OleSetClipboardAggregate(v7, pDataObj);
  OleClipboardTracing::OleSetClipboardEtw(v7, pDataObj, v4 != 0);
  return v7;
}

```

## disassembly

```asm
0x180032ee0  push    rbp
0x180032ee2  push    rbx
0x180032ee3  push    rsi
0x180032ee4  push    rdi
0x180032ee5  push    r14
0x180032ee7  push    r15
0x180032ee9  lea     rbp, [rsp-78h]
0x180032eee  sub     rsp, 178h
0x180032ef5  mov     rax, cs:__security_cookie
0x180032efc  xor     rax, rsp
0x180032eff  mov     [rbp+0A0h+var_40], rax
0x180032f03  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x180032f0a  mov     rdi, pDataObject
0x180032f0d  jz      short loc_180032F2B
0x180032f0f  lea     rax, [rsp+1A0h+spAgileDataObject]
0x180032f14  mov     r9d, 1; Context
0x180032f1a  lea     rdx, OLE_Clipboard_SetClipboard_Start; EventDataCount
0x180032f21  mov     [rsp+1A0h+Descriptor], rax; Descriptor
0x180032f26  call    McGenEventWrite_EventWriteTransfer
0x180032f2b  call    ?IsOleInitialized@@YA_NXZ; IsOleInitialized(void)
0x180032f30  xor     r15d, r15d
0x180032f33  test    al, al
0x180032f35  jnz     short loc_180032F4E
0x180032f37  lea     pDataObject, aOlesetclipboar_1; "OleSetClipboard"
0x180032f3e  call    cs:__imp_?CoVrfShouldCallOleInit@@YAXPEBD@Z; CoVrfShouldCallOleInit(char const *)
0x180032f44  mov     eax, 800401F0h
0x180032f49  jmp     loc_1800332A7
0x180032f4e  xor     r9d, r9d; Context
0x180032f51  lea     rdx, _lambda_50fe48bf199844a7ed15a94e5b76e4d1____lambda_invoker_cdecl_; InitFn
0x180032f58  xor     r8d, r8d; Parameter
0x180032f5b  lea     pDataObject, ?g_initAppContainerState@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180032f62  call    cs:__imp_InitOnceExecuteOnce
0x180032f68  mov     r14d, cs:?g_isAppContainer@@3HA; int g_isAppContainer
0x180032f6f  test    r14d, r14d
0x180032f72  jz      short loc_180032FA2
0x180032f74  call    ?ClipboardInitializeBroker@@YAHXZ; ClipboardInitializeBroker(void)
0x180032f79  test    eax, eax
0x180032f7b  jz      short loc_180032F8C
0x180032f7d  mov     pDataObject, rdi; function
0x180032f80  call    ExecuteClipboardBrokerFunctionAndTryToRecoverIfFailureLikelyToIndicateBrokerAbnormalTermination__lambda_9370c4e5c64663684a8eb35dd7926c23___; ExecuteClipboardBrokerFunctionAndTryToRecoverIfFailureLikelyToIndicateBrokerAbnormalTermination__lambda_9370c4e5c64663684a8eb35dd7926c23_
0x180032f85  mov     ebx, eax
0x180032f87  jmp     loc_1800330C2
0x180032f8c  mov     ebx, 80004005h
0x180032f91  mov     edx, 12Fh; messageID
0x180032f96  mov     ecx, ebx; hr
0x180032f98  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x180032f9d  jmp     loc_1800330C2
0x180032fa2  xor     edx, edx; Val
0x180032fa4  lea     pDataObject, [rsp+1A0h+awchPackageChars]; void *
0x180032fa9  mov     r8d, 100h; Size
0x180032faf  call    memset_0
0x180032fb4  mov     [rsp+1A0h+uSuppressASTAAutoFlush], 80h
0x180032fbc  call    cs:__imp_GetCurrentProcess
0x180032fc2  mov     pDataObject, rax; hProcess
0x180032fc5  lea     r8, [rsp+1A0h+awchPackageChars]; packageFullName
0x180032fca  lea     rdx, [rsp+1A0h+uSuppressASTAAutoFlush]; packageFullNameLength
0x180032fcf  call    cs:__imp_GetPackageFullName
0x180032fd5  mov     ebx, eax
0x180032fd7  test    eax, eax
0x180032fd9  jnz     short loc_180032FE2
0x180032fdb  lea     rsi, [rsp+1A0h+awchPackageChars]
0x180032fe0  jmp     short loc_180033006
0x180032fe2  mov     rsi, r15
0x180032fe5  cmp     eax, 3D54h
0x180032fea  jz      short loc_180033006
0x180032fec  cmp     eax, 5
0x180032fef  jz      short loc_180033006
0x180032ff1  test    eax, eax
0x180032ff3  jle     short loc_180032FFE
0x180032ff5  movzx   ebx, ax
0x180032ff8  or      ebx, 80070000h
0x180032ffe  test    ebx, ebx
0x180033000  js      loc_1800330C2
0x180033006  call    cs:__imp_GetCurrentProcess
0x18003300c  mov     pDataObject, rax; Process
0x18003300f  call    cs:__imp_GetProcessId
0x180033015  mov     r9, rsi; pszCallerPackageFullName
0x180033018  xor     r8d, r8d; ppDataObjectMTAAddress
0x18003301b  xor     edx, edx; pSourceDataObject
0x18003301d  mov     dword ptr [rsp+1A0h+Descriptor], eax; pid
0x180033021  mov     pDataObject, rdi; pDataObject
0x180033024  call    ?OleSetClipboardInternal@@YAJPEAUIDataObject@@0PEAPEAXPEBGK@Z; OleSetClipboardInternal(IDataObject *,IDataObject *,void * *,ushort const *,ulong)
0x180033029  mov     ebx, eax
0x18003302b  test    eax, eax
0x18003302d  js      loc_1800330C2
0x180033033  call    cs:__imp_EdpGetIsManaged
0x180033039  test    eax, eax
0x18003303b  jz      loc_1800330C2
0x180033041  call    cs:__imp_EdpClearClipboardMetaData
0x180033047  test    eax, eax
0x180033049  js      short loc_1800330C2
0x18003304b  mov     [rsp+1A0h+key._hkey], r15
0x180033050  call    cs:__imp_GetCurrentProcessId
0x180033056  mov     ecx, eax
0x180033058  lea     rdx, [rsp+1A0h+key]
0x18003305d  call    cs:__imp_EdpGetContextForProcess
0x180033063  test    eax, eax
0x180033065  js      short loc_18003308B
0x180033067  mov     pDataObject, [rsp+1A0h+key._hkey]
0x18003306c  mov     pDataObject, [pDataObject+8]
0x180033070  call    cs:__imp_EdpSetEnterpriseIdForClipboard
0x180033076  mov     rax, [rsp+1A0h+key._hkey]
0x18003307b  test    byte ptr [rax], 3
0x18003307e  jz      short loc_18003308B
0x180033080  mov     ecx, 1
0x180033085  call    cs:__imp_EdpSetSourceIsEnlightenedForClipboard
0x18003308b  mov     [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_], r15
0x180033090  call    cs:__imp_GetCurrentProcessId
0x180033096  mov     ecx, eax
0x180033098  lea     rdx, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk]
0x18003309d  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x1800330a3  mov     pDataObject, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_]
0x1800330a8  call    cs:__imp_EdpSetSourceAppIdForClipboard
0x1800330ae  lea     pDataObject, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk]; this
0x1800330b3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800330b8  lea     pDataObject, [rsp+1A0h+key]; this
0x1800330bd  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x1800330c2  test    rdi, rdi
0x1800330c5  jz      loc_180033265
0x1800330cb  mov     rax, gs:30h
0x1800330d4  mov     pDataObject, [rax+1758h]; pStatus
0x1800330db  mov     eax, [pDataObject+14h]
0x1800330de  and     eax, 40400080h
0x1800330e3  cmp     eax, 400080h
0x1800330e8  jnz     loc_180033265
0x1800330ee  call    ?IsQuirkEnabled@Quirks@@CA_NPEAW4QuirkStatus@1@K@Z; Quirks::IsQuirkEnabled(Quirks::QuirkStatus *,ulong)
0x1800330f3  test    al, al
0x1800330f5  jnz     loc_180033265
0x1800330fb  lea     r8, [rsp+1A0h+spAgileDataObject]; ppv
0x180033100  mov     [rsp+1A0h+spAgileDataObject.ptr_], r15
0x180033105  lea     rdx, _GUID_06495cd4_3e37_2721_6e15_e077975f3d3d; iid
0x18003310c  mov     pDataObject, rdi; punk
0x18003310f  call    ?CarefullyQueryNewInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CarefullyQueryNewInterface(IUnknown *,_GUID const &,void * *)
0x180033114  test    eax, eax
0x180033116  jns     loc_18003324A
0x18003311c  lea     r8, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk]; ppv
0x180033121  mov     [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_], r15
0x180033126  lea     rdx, _GUID_77dd1250_139c_2bc3_bd95_900aced61be5; iid
0x18003312d  mov     pDataObject, rdi; punk
0x180033130  call    ?CarefullyQueryNewInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CarefullyQueryNewInterface(IUnknown *,_GUID const &,void * *)
0x180033135  test    eax, eax
0x180033137  jns     loc_18003322F
0x18003313d  lea     r9, [rsp+1A0h+key]; hkeyAncestor
0x180033142  mov     [rsp+1A0h+key._hkey], r15
0x180033147  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Ole\\AppCompat"
0x18003314e  mov     pDataObject, 0FFFFFFFF80000002h; hkeyAncestor
0x180033155  call    ?StaticOpen@RegistryKey@@CAJPEAUHKEY__@@PEBGKPEAPEAU2@@Z; RegistryKey::StaticOpen(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18003315a  test    eax, eax
0x18003315c  js      short loc_180033181
0x18003315e  lea     r8, [rsp+1A0h+uSuppressASTAAutoFlush]; unsigned int *
0x180033163  mov     [rsp+1A0h+uSuppressASTAAutoFlush], r15d
0x180033168  lea     pDataObject, [rsp+1A0h+key]; this
0x18003316d  call    ?ReadDWORDValue@RegistryKey@@QEBAJPEBGPEAK@Z; RegistryKey::ReadDWORDValue(ushort const *,ulong *)
0x180033172  test    eax, eax
0x180033174  js      short loc_180033181
0x180033176  cmp     [rsp+1A0h+uSuppressASTAAutoFlush], r15d
0x18003317b  jnz     loc_180033215
0x180033181  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180033187  test    eax, eax
0x180033189  jnz     short loc_1800331A0
0x18003318b  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180033192  jz      short loc_1800331C5
0x180033194  lea     ecx, [rax+1]; level
0x180033197  call    IsWppLevelEnabled
0x18003319c  test    al, al
0x18003319e  jz      short loc_1800331C5
0x1800331a0  lea     rax, aAutoFlushingCl; "Auto-flushing clipboard due to non-agil"...
0x1800331a7  mov     r8d, 0E5Bh; line
0x1800331ad  lea     rdx, aOlesetclipboar_1; "OleSetClipboard"
0x1800331b4  mov     [rsp+1A0h+Descriptor], rax; file
0x1800331b9  lea     pDataObject, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x1800331c0  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x1800331c5  call    OleFlushClipboard
0x1800331ca  mov     edx, eax
0x1800331cc  test    eax, eax
0x1800331ce  jns     short loc_180033215
0x1800331d0  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x1800331d6  test    ecx, ecx
0x1800331d8  jnz     short loc_1800331EC
0x1800331da  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800331e1  jz      short loc_180033215
0x1800331e3  call    IsWppLevelEnabled
0x1800331e8  test    al, al
0x1800331ea  jz      short loc_180033215
0x1800331ec  mov     [rsp+1A0h+file], edx; file
0x1800331f0  lea     rax, aAutoFlushOfThe; "Auto-flush of the clipboard failed, hr="...
0x1800331f7  lea     rdx, aOlesetclipboar_1; "OleSetClipboard"
0x1800331fe  mov     [rsp+1A0h+Descriptor], rax; <args_0>
0x180033203  mov     r8d, 0E66h; line
0x180033209  lea     pDataObject, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x180033210  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180033215  mov     rax, [rsp+1A0h+key._hkey]
0x18003321a  test    rax, rax
0x18003321d  jz      short loc_18003322F
0x18003321f  mov     pDataObject, [rsp+1A0h+key._hkey]; hKey
0x180033224  call    cs:__imp_RegCloseKey
0x18003322a  mov     [rsp+1A0h+key._hkey], r15
0x18003322f  mov     pDataObject, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_]
0x180033234  test    pDataObject, pDataObject
0x180033237  jz      short loc_18003324A
0x180033239  mov     [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_], r15
0x18003323e  mov     rax, [pDataObject]
0x180033241  mov     rax, [rax+10h]
0x180033245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003324a  mov     pDataObject, [rsp+1A0h+spAgileDataObject.ptr_]
0x18003324f  test    pDataObject, pDataObject
0x180033252  jz      short loc_180033265
0x180033254  mov     [rsp+1A0h+spAgileDataObject.ptr_], r15
0x180033259  mov     rax, [pDataObject]
0x18003325c  mov     rax, [rax+10h]
0x180033260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033265  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x18003326c  jz      short loc_18003328A
0x18003326e  lea     rax, [rsp+1A0h+spAgileDataObject]
0x180033273  mov     r9d, 1; Context
0x180033279  lea     rdx, OLE_Clipboard_SetClipboard_Stop; EventDataCount
0x180033280  mov     [rsp+1A0h+Descriptor], rax; Descriptor
0x180033285  call    McGenEventWrite_EventWriteTransfer
0x18003328a  mov     rdx, rdi; pDataObj
0x18003328d  mov     ecx, ebx; hr
0x18003328f  call    ?OleSetClipboardAggregate@OleClipboardAggregateTelemetry@@SAXJPEAUIDataObject@@@Z; OleClipboardAggregateTelemetry::OleSetClipboardAggregate(long,IDataObject *)
0x180033294  test    r14d, r14d
0x180033297  mov     rdx, rdi; pDataObj
0x18003329a  mov     ecx, ebx; hr
0x18003329c  setnz   r8b; isAppContainer
0x1800332a0  call    ?OleSetClipboardEtw@OleClipboardTracing@@SAXJPEAUIDataObject@@_N@Z; OleClipboardTracing::OleSetClipboardEtw(long,IDataObject *,bool)
0x1800332a5  mov     eax, ebx
0x1800332a7  mov     pDataObject, [rbp+0A0h+var_40]
0x1800332ab  xor     pDataObject, rsp; StackCookie
0x1800332ae  call    __security_check_cookie
0x1800332b3  add     rsp, 178h
0x1800332ba  pop     r15
0x1800332bc  pop     r14
0x1800332be  pop     rdi
0x1800332bf  pop     rsi
0x1800332c0  pop     rbx
0x1800332c1  pop     rbp
0x1800332c2  retn
```
