# OleSetClipboard

- ea: `0x18001d410`
- end: `0x18001d877`
- name: `OleSetClipboard`
- size: `1127`
- prototype: `HRESULT __stdcall(LPDATAOBJECT pDataObj)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000962c`
- `0x18001c530`
- `0x18001c778`
- `0x18001d410`
- `0x18001d880`
- `0x18001d89c`
- `0x18001e5b4`
- `0x180041d48`
- `0x180046460`
- `0x180047484`
- `0x18004d474`
- `0x180087034`
- `0x180087068`
- `0x180087194`
- `0x18008798c`
- `0x1800879ac`
- `0x1800896b0`
- `0x1800898f8`
- `0x1800899e4`
- `0x1800cda28`
- `0x1800cdb24`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x18001d522`
- `KERNELBASE!GetPackageFullName` at `0x18001d522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d50a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d55b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d50a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d55b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d56a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d56a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d5c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d619`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d5c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d619`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d7c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d7c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001d4a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001d4a8`
- `combase!__imp_?CoVrfShouldCallOleInit@@YAXPEBD@Z` at `0x18001d47e`
- `combase!__imp_?CoVrfShouldCallOleInit@@YAXPEBD@Z` at `0x18001d47e`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceAppIdForClipboard` at `0x18001d63d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceAppIdForClipboard` at `0x18001d63d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceIsEnlightenedForClipboard` at `0x18001d608`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetSourceIsEnlightenedForClipboard` at `0x18001d608`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetEnterpriseIdForClipboard` at `0x18001d5ed`
- `ext-ms-win-edputil-policy-l1-1-0!EdpSetEnterpriseIdForClipboard` at `0x18001d5ed`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18001d5d4`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18001d5d4`
- `ext-ms-win-edputil-policy-l1-1-0!EdpClearClipboardMetaData` at `0x18001d5a8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpClearClipboardMetaData` at `0x18001d5a8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18001d594`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18001d594`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18001d62c`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetAppLockerUniqueAppIdentifier` at `0x18001d62c`

## string_xrefs

- `0x18001d755`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18001d7a6`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18001d6e2`: `Software\Microsoft\Ole\AppCompat`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __stdcall OleSetClipboard(LPDATAOBJECT pDataObj)
{
  const _GUID *v1; // r8
  int v4; // r14d
  unsigned int v5; // edx
  Quirks::QuirkStatus *ReservedForOle; // rcx
  HRESULT v7; // ebx
  const _GUID *v8; // r8
  const wchar_t *v9; // rsi
  HANDLE CurrentProcess; // rax
  LONG PackageFullName; // eax
  HANDLE v12; // rax
  DWORD ProcessId; // eax
  DWORD CurrentProcessId; // eax
  DWORD v15; // eax
  const wchar_t *v16; // rdx
  TraceLevel v17; // r9d
  int v18; // edx
  TraceLevel v19; // r9d
  IAgileDataObject *ptr; // rcx
  RegistryKey key; // [rsp+38h] [rbp-D0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > > edpContext; // [rsp+40h] [rbp-C8h] BYREF
  wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (__cdecl*)(EDP_CONTEXT *),&EdpFreeContext,wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t> > length; // [rsp+48h] [rbp-C0h] OVERLAPPED BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > uniqueAppId; // [rsp+50h] [rbp-B8h] BYREF
  Microsoft::WRL::ComPtr<IAllowAstaToAstaDeadlockRisk> spAllowAstaToAstaDeadlockRisk; // [rsp+58h] [rbp-B0h] BYREF
  Microsoft::WRL::ComPtr<IAgileDataObject> spAgileDataObject; // [rsp+60h] [rbp-A8h] BYREF
  void *ppv; // [rsp+68h] [rbp-A0h] BYREF
  _EVENT_DATA_DESCRIPTOR Descriptor; // [rsp+70h] [rbp-98h] BYREF
  wchar_t awchPackageChars[132]; // [rsp+80h] [rbp-88h] BYREF

  if ( (Microsoft_Windows_OLE_PerfEnableBits[0] & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (_MCGEN_TRACE_CONTEXT *)pDataObj,
      &OLE_Clipboard_SetClipboard_Start,
      v1,
      1u,
      &Descriptor);
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
    v9 = 0;
    memset_0(&awchPackageChars[4], 0, 0x100u);
    LODWORD(uniqueAppId.m_ptr) = 128;
    CurrentProcess = GetCurrentProcess();
    PackageFullName = GetPackageFullName(CurrentProcess, (UINT32 *)&uniqueAppId, &awchPackageChars[4]);
    v7 = PackageFullName;
    if ( PackageFullName )
    {
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
      v9 = &awchPackageChars[4];
    }
    v12 = GetCurrentProcess();
    ProcessId = GetProcessId(v12);
    v7 = OleSetClipboardInternal(pDataObj, 0, 0, v9, ProcessId);
    if ( v7 >= 0 && (unsigned int)EdpGetIsManaged() && (int)EdpClearClipboardMetaData() >= 0 )
    {
      length.m_ptr = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( (int)EdpGetContextForProcess(CurrentProcessId, &length) >= 0 )
      {
        EdpSetEnterpriseIdForClipboard(length.m_ptr->enterpriseIdForUIEnforcement);
        if ( (length.m_ptr->contextStates & 3) != 0 )
          EdpSetSourceIsEnlightenedForClipboard(1);
      }
      spAllowAstaToAstaDeadlockRisk.ptr_ = 0;
      v15 = GetCurrentProcessId();
      EdpGetAppLockerUniqueAppIdentifier(v15, &spAllowAstaToAstaDeadlockRisk);
      EdpSetSourceAppIdForClipboard(spAllowAstaToAstaDeadlockRisk.ptr_);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&spAllowAstaToAstaDeadlockRisk);
      wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&length);
    }
  }
LABEL_23:
  if ( pDataObj )
  {
    ReservedForOle = (Quirks::QuirkStatus *)NtCurrentTeb()->ReservedForOle;
    if ( (ReservedForOle[5] & 0x40400080) == 0x400080 && !Quirks::IsQuirkEnabled(ReservedForOle, v5) )
    {
      ppv = 0;
      if ( CarefullyQueryNewInterface(pDataObj, &GUID_06495cd4_3e37_2721_6e15_e077975f3d3d, &ppv) < 0 )
      {
        spAgileDataObject.ptr_ = 0;
        if ( CarefullyQueryNewInterface(
               pDataObj,
               &GUID_77dd1250_139c_2bc3_bd95_900aced61be5,
               (void **)&spAgileDataObject.ptr_) < 0 )
        {
          edpContext.m_ptr = 0;
          if ( RegistryKey::StaticOpen(
                 (HKEY__ *)0xFFFFFFFF80000002LL,
                 L"Software\\Microsoft\\Ole\\AppCompat",
                 (unsigned int)v8,
                 (HKEY__ **)&edpContext) < 0
            || (LODWORD(key._hkey) = 0,
                RegistryKey::ReadDWORDValue((RegistryKey *)&edpContext, v16, (unsigned int *)&key) < 0)
            || !LODWORD(key._hkey) )
          {
            if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING) )
              ComTraceMessageT<>(
                "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                "OleSetClipboard",
                3675,
                v17,
                L"Auto-flushing clipboard due to non-agile IDataObject on ASTA");
            v18 = OleFlushClipboard();
            if ( v18 < 0
              && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
            {
              ComTraceMessageT<long>(
                "com\\ole32\\ole232\\clipbrd\\clipapi.cpp",
                "OleSetClipboard",
                3686,
                v19,
                L"Auto-flush of the clipboard failed, hr=%!HRESULT!",
                v18);
            }
          }
          if ( edpContext.m_ptr )
          {
            RegCloseKey((HKEY)edpContext.m_ptr);
            edpContext.m_ptr = 0;
          }
        }
        ptr = spAgileDataObject.ptr_;
        if ( spAgileDataObject.ptr_ )
        {
          spAgileDataObject.ptr_ = 0;
          ((void (__fastcall *)(IAgileDataObject *))ptr->lpVtbl->Release)(ptr);
        }
      }
      ReservedForOle = (Quirks::QuirkStatus *)ppv;
      if ( ppv )
      {
        ppv = 0;
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
      &Descriptor);
  OleClipboardAggregateTelemetry::OleSetClipboardAggregate(v7, pDataObj);
  OleClipboardTracing::OleSetClipboardEtw(v7, pDataObj, v4 != 0);
  return v7;
}

```

## disassembly

```asm
0x18001d410  mov     rax, rsp
0x18001d413  mov     [rax+10h], rbx
0x18001d417  mov     [rax+18h], rsi
0x18001d41b  mov     [rax+20h], rdi
0x18001d41f  push    rbp
0x18001d420  push    r14
0x18001d422  push    r15
0x18001d424  lea     rbp, [rax-0A8h]
0x18001d42b  sub     rsp, 190h
0x18001d432  mov     rax, cs:__security_cookie
0x18001d439  xor     rax, rsp
0x18001d43c  mov     [rbp+0A0h+var_20], rax
0x18001d443  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x18001d44a  mov     rdi, pDataObject
0x18001d44d  jz      short loc_18001D46B
0x18001d44f  lea     rax, [rsp+1A0h+var_138]
0x18001d454  mov     r9d, 1; Context
0x18001d45a  lea     rdx, OLE_Clipboard_SetClipboard_Start; EventDataCount
0x18001d461  mov     [rsp+1A0h+Descriptor], rax; Descriptor
0x18001d466  call    McGenEventWrite_EventWriteTransfer
0x18001d46b  call    ?IsOleInitialized@@YA_NXZ; IsOleInitialized(void)
0x18001d470  xor     r15d, r15d
0x18001d473  test    al, al
0x18001d475  jnz     short loc_18001D494
0x18001d477  lea     pDataObject, aOlesetclipboar_1; "OleSetClipboard"
0x18001d47e  call    cs:__imp_?CoVrfShouldCallOleInit@@YAXPEBD@Z; CoVrfShouldCallOleInit(char const *)
0x18001d485  nop     dword ptr [rax+rax+00h]
0x18001d48a  mov     eax, 800401F0h
0x18001d48f  jmp     loc_18001D84A
0x18001d494  xor     r9d, r9d; Context
0x18001d497  lea     rdx, _lambda_50fe48bf199844a7ed15a94e5b76e4d1____lambda_invoker_cdecl_; InitFn
0x18001d49e  xor     r8d, r8d; Parameter
0x18001d4a1  lea     pDataObject, ?g_initAppContainerState@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18001d4a8  call    cs:__imp_InitOnceExecuteOnce
0x18001d4af  nop     dword ptr [rax+rax+00h]
0x18001d4b4  mov     r14d, cs:?g_isAppContainer@@3HA; int g_isAppContainer
0x18001d4bb  test    r14d, r14d
0x18001d4be  jz      short loc_18001D4EE
0x18001d4c0  call    ?ClipboardInitializeBroker@@YAHXZ; ClipboardInitializeBroker(void)
0x18001d4c5  test    eax, eax
0x18001d4c7  jz      short loc_18001D4D8
0x18001d4c9  mov     pDataObject, rdi; function
0x18001d4cc  call    ExecuteClipboardBrokerFunctionAndTryToRecoverIfFailureLikelyToIndicateBrokerAbnormalTermination__lambda_9370c4e5c64663684a8eb35dd7926c23___; ExecuteClipboardBrokerFunctionAndTryToRecoverIfFailureLikelyToIndicateBrokerAbnormalTermination__lambda_9370c4e5c64663684a8eb35dd7926c23_
0x18001d4d1  mov     ebx, eax
0x18001d4d3  jmp     loc_18001D65D
0x18001d4d8  mov     ebx, 80004005h
0x18001d4dd  mov     edx, 12Fh; messageID
0x18001d4e2  mov     ecx, ebx; hr
0x18001d4e4  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001d4e9  jmp     loc_18001D65D
0x18001d4ee  xor     edx, edx; Val
0x18001d4f0  lea     pDataObject, [rbp+0A0h+awchPackageChars+8]; void *
0x18001d4f4  mov     r8d, 100h; Size
0x18001d4fa  mov     rsi, r15
0x18001d4fd  call    memset_0
0x18001d502  mov     dword ptr [rsp+1A0h+uniqueAppId.m_ptr], 80h
0x18001d50a  call    cs:__imp_GetCurrentProcess
0x18001d511  nop     dword ptr [rax+rax+00h]
0x18001d516  mov     pDataObject, rax; hProcess
0x18001d519  lea     r8, [rbp+0A0h+awchPackageChars+8]; packageFullName
0x18001d51d  lea     rdx, [rsp+1A0h+uniqueAppId]; packageFullNameLength
0x18001d522  call    cs:__imp_GetPackageFullName
0x18001d529  nop     dword ptr [rax+rax+00h]
0x18001d52e  mov     ebx, eax
0x18001d530  test    eax, eax
0x18001d532  jnz     short loc_18001D53A
0x18001d534  lea     rsi, [rbp+0A0h+awchPackageChars+8]
0x18001d538  jmp     short loc_18001D55B
0x18001d53a  cmp     eax, 3D54h
0x18001d53f  jz      short loc_18001D55B
0x18001d541  cmp     eax, 5
0x18001d544  jz      short loc_18001D55B
0x18001d546  test    eax, eax
0x18001d548  jle     short loc_18001D553
0x18001d54a  movzx   ebx, ax
0x18001d54d  or      ebx, 80070000h
0x18001d553  test    ebx, ebx
0x18001d555  js      loc_18001D65D
0x18001d55b  call    cs:__imp_GetCurrentProcess
0x18001d562  nop     dword ptr [rax+rax+00h]
0x18001d567  mov     pDataObject, rax; Process
0x18001d56a  call    cs:__imp_GetProcessId
0x18001d571  nop     dword ptr [rax+rax+00h]
0x18001d576  mov     r9, rsi; pszCallerPackageFullName
0x18001d579  xor     r8d, r8d; ppDataObjectMTAAddress
0x18001d57c  xor     edx, edx; pSourceDataObject
0x18001d57e  mov     dword ptr [rsp+1A0h+Descriptor], eax; pid
0x18001d582  mov     pDataObject, rdi; pDataObject
0x18001d585  call    ?OleSetClipboardInternal@@YAJPEAUIDataObject@@0PEAPEAXPEBGK@Z; OleSetClipboardInternal(IDataObject *,IDataObject *,void * *,ushort const *,ulong)
0x18001d58a  mov     ebx, eax
0x18001d58c  test    eax, eax
0x18001d58e  js      loc_18001D65D
0x18001d594  call    cs:__imp_EdpGetIsManaged
0x18001d59b  nop     dword ptr [rax+rax+00h]
0x18001d5a0  test    eax, eax
0x18001d5a2  jz      loc_18001D65D
0x18001d5a8  call    cs:__imp_EdpClearClipboardMetaData
0x18001d5af  nop     dword ptr [rax+rax+00h]
0x18001d5b4  test    eax, eax
0x18001d5b6  js      loc_18001D65D
0x18001d5bc  mov     [rsp+1A0h+length.m_ptr], r15
0x18001d5c1  call    cs:__imp_GetCurrentProcessId
0x18001d5c8  nop     dword ptr [rax+rax+00h]
0x18001d5cd  mov     ecx, eax
0x18001d5cf  lea     rdx, [rsp+1A0h+length]
0x18001d5d4  call    cs:__imp_EdpGetContextForProcess
0x18001d5db  nop     dword ptr [rax+rax+00h]
0x18001d5e0  test    eax, eax
0x18001d5e2  js      short loc_18001D614
0x18001d5e4  mov     pDataObject, [rsp+1A0h+length.m_ptr]
0x18001d5e9  mov     pDataObject, [pDataObject+8]
0x18001d5ed  call    cs:__imp_EdpSetEnterpriseIdForClipboard
0x18001d5f4  nop     dword ptr [rax+rax+00h]
0x18001d5f9  mov     rax, [rsp+1A0h+length.m_ptr]
0x18001d5fe  test    byte ptr [rax], 3
0x18001d601  jz      short loc_18001D614
0x18001d603  mov     ecx, 1
0x18001d608  call    cs:__imp_EdpSetSourceIsEnlightenedForClipboard
0x18001d60f  nop     dword ptr [rax+rax+00h]
0x18001d614  mov     [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_], r15
0x18001d619  call    cs:__imp_GetCurrentProcessId
0x18001d620  nop     dword ptr [rax+rax+00h]
0x18001d625  mov     ecx, eax
0x18001d627  lea     rdx, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk]
0x18001d62c  call    cs:__imp_EdpGetAppLockerUniqueAppIdentifier
0x18001d633  nop     dword ptr [rax+rax+00h]
0x18001d638  mov     pDataObject, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk.ptr_]
0x18001d63d  call    cs:__imp_EdpSetSourceAppIdForClipboard
0x18001d644  nop     dword ptr [rax+rax+00h]
0x18001d649  lea     pDataObject, [rsp+1A0h+spAllowAstaToAstaDeadlockRisk]; this
0x18001d64e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d653  lea     pDataObject, [rsp+1A0h+length]; this
0x18001d658  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x18001d65d  test    rdi, rdi
0x18001d660  jz      loc_18001D808
0x18001d666  mov     rax, gs:30h
0x18001d66f  mov     pDataObject, [rax+1758h]; pStatus
0x18001d676  mov     eax, [pDataObject+14h]
0x18001d679  and     eax, 40400080h
0x18001d67e  cmp     eax, 400080h
0x18001d683  jnz     loc_18001D808
0x18001d689  call    ?IsQuirkEnabled@Quirks@@CA_NPEAW4QuirkStatus@1@K@Z; Quirks::IsQuirkEnabled(Quirks::QuirkStatus *,ulong)
0x18001d68e  test    al, al
0x18001d690  jnz     loc_18001D808
0x18001d696  lea     r8, [rsp+1A0h+ppv]; ppv
0x18001d69b  mov     [rsp+1A0h+ppv], r15
0x18001d6a0  lea     rdx, _GUID_06495cd4_3e37_2721_6e15_e077975f3d3d; iid
0x18001d6a7  mov     pDataObject, rdi; punk
0x18001d6aa  call    ?CarefullyQueryNewInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CarefullyQueryNewInterface(IUnknown *,_GUID const &,void * *)
0x18001d6af  test    eax, eax
0x18001d6b1  jns     loc_18001D7ED
0x18001d6b7  lea     r8, [rsp+1A0h+spAgileDataObject]; ppv
0x18001d6bc  mov     [rsp+1A0h+spAgileDataObject.ptr_], r15
0x18001d6c1  lea     rdx, _GUID_77dd1250_139c_2bc3_bd95_900aced61be5; iid
0x18001d6c8  mov     pDataObject, rdi; punk
0x18001d6cb  call    ?CarefullyQueryNewInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CarefullyQueryNewInterface(IUnknown *,_GUID const &,void * *)
0x18001d6d0  test    eax, eax
0x18001d6d2  jns     loc_18001D7D2
0x18001d6d8  lea     r9, [rsp+1A0h+edpContext]; hkeyAncestor
0x18001d6dd  mov     [rsp+1A0h+edpContext.m_ptr], r15
0x18001d6e2  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Ole\\AppCompat"
0x18001d6e9  mov     pDataObject, 0FFFFFFFF80000002h; hkeyAncestor
0x18001d6f0  call    ?StaticOpen@RegistryKey@@CAJPEAUHKEY__@@PEBGKPEAPEAU2@@Z; RegistryKey::StaticOpen(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18001d6f5  test    eax, eax
0x18001d6f7  js      short loc_18001D71C
0x18001d6f9  lea     r8, [rsp+1A0h+key]; unsigned int *
0x18001d6fe  mov     dword ptr [rsp+1A0h+key._hkey], r15d
0x18001d703  lea     pDataObject, [rsp+1A0h+edpContext]; this
0x18001d708  call    ?ReadDWORDValue@RegistryKey@@QEBAJPEBGPEAK@Z; RegistryKey::ReadDWORDValue(ushort const *,ulong *)
0x18001d70d  test    eax, eax
0x18001d70f  js      short loc_18001D71C
0x18001d711  cmp     dword ptr [rsp+1A0h+key._hkey], r15d
0x18001d716  jnz     loc_18001D7B2
0x18001d71c  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, r15d
0x18001d723  ja      short loc_18001D73C
0x18001d725  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18001d72c  jz      short loc_18001D761
0x18001d72e  mov     ecx, 1; level
0x18001d733  call    IsWppLevelEnabled
0x18001d738  test    al, al
0x18001d73a  jz      short loc_18001D761
0x18001d73c  lea     rax, aAutoFlushingCl; "Auto-flushing clipboard due to non-agil"...
0x18001d743  mov     r8d, 0E5Bh; line
0x18001d749  lea     rdx, aOlesetclipboar_1; "OleSetClipboard"
0x18001d750  mov     [rsp+1A0h+Descriptor], rax; file
0x18001d755  lea     pDataObject, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18001d75c  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18001d761  call    OleFlushClipboard
0x18001d766  mov     edx, eax
0x18001d768  test    eax, eax
0x18001d76a  jns     short loc_18001D7B2
0x18001d76c  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, r15d
0x18001d773  ja      short loc_18001D789
0x18001d775  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18001d77c  jz      short loc_18001D7B2
0x18001d77e  xor     ecx, ecx; level
0x18001d780  call    IsWppLevelEnabled
0x18001d785  test    al, al
0x18001d787  jz      short loc_18001D7B2
0x18001d789  mov     [rsp+1A0h+uSuppressASTAAutoFlush], edx; file
0x18001d78d  lea     rax, aAutoFlushOfThe; "Auto-flush of the clipboard failed, hr="...
0x18001d794  lea     rdx, aOlesetclipboar_1; "OleSetClipboard"
0x18001d79b  mov     [rsp+1A0h+Descriptor], rax; <args_0>
0x18001d7a0  mov     r8d, 0E66h; line
0x18001d7a6  lea     pDataObject, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18001d7ad  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18001d7b2  mov     rax, [rsp+1A0h+edpContext.m_ptr]
0x18001d7b7  test    rax, rax
0x18001d7ba  jz      short loc_18001D7D2
0x18001d7bc  mov     pDataObject, [rsp+1A0h+edpContext.m_ptr]; hKey
0x18001d7c1  call    cs:__imp_RegCloseKey
0x18001d7c8  nop     dword ptr [rax+rax+00h]
0x18001d7cd  mov     [rsp+1A0h+edpContext.m_ptr], r15
0x18001d7d2  mov     pDataObject, [rsp+1A0h+spAgileDataObject.ptr_]
0x18001d7d7  test    pDataObject, pDataObject
0x18001d7da  jz      short loc_18001D7ED
0x18001d7dc  mov     [rsp+1A0h+spAgileDataObject.ptr_], r15
0x18001d7e1  mov     rax, [pDataObject]
0x18001d7e4  mov     rax, [rax+10h]
0x18001d7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ed  mov     pDataObject, [rsp+1A0h+ppv]
0x18001d7f2  test    pDataObject, pDataObject
0x18001d7f5  jz      short loc_18001D808
0x18001d7f7  mov     [rsp+1A0h+ppv], r15
0x18001d7fc  mov     rax, [pDataObject]
0x18001d7ff  mov     rax, [rax+10h]
0x18001d803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d808  test    byte ptr cs:Microsoft_Windows_OLE_PerfEnableBits, 1
0x18001d80f  jz      short loc_18001D82D
0x18001d811  lea     rax, [rsp+1A0h+var_138]
0x18001d816  mov     r9d, 1; Context
0x18001d81c  lea     rdx, OLE_Clipboard_SetClipboard_Stop; EventDataCount
0x18001d823  mov     [rsp+1A0h+Descriptor], rax; Descriptor
0x18001d828  call    McGenEventWrite_EventWriteTransfer
0x18001d82d  mov     rdx, rdi; pDataObj
0x18001d830  mov     ecx, ebx; hr
0x18001d832  call    ?OleSetClipboardAggregate@OleClipboardAggregateTelemetry@@SAXJPEAUIDataObject@@@Z; OleClipboardAggregateTelemetry::OleSetClipboardAggregate(long,IDataObject *)
0x18001d837  test    r14d, r14d
0x18001d83a  mov     rdx, rdi; pDataObj
0x18001d83d  mov     ecx, ebx; hr
0x18001d83f  setnz   r8b; isAppContainer
0x18001d843  call    ?OleSetClipboardEtw@OleClipboardTracing@@SAXJPEAUIDataObject@@_N@Z; OleClipboardTracing::OleSetClipboardEtw(long,IDataObject *,bool)
0x18001d848  mov     eax, ebx
0x18001d84a  mov     pDataObject, [rbp+0A0h+var_20]
0x18001d851  xor     pDataObject, rsp; StackCookie
0x18001d854  call    __security_check_cookie
0x18001d859  lea     r11, [rsp+1A0h+var_10]
0x18001d861  mov     rbx, [r11+28h]
0x18001d865  mov     rsi, [r11+30h]
0x18001d869  mov     rdi, [r11+38h]
0x18001d86d  mov     rsp, r11
0x18001d870  pop     r15
0x18001d872  pop     r14
0x18001d874  pop     rbp
0x18001d875  retn
```
