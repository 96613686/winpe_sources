# DragDropTelemetry::DragDropSession::DropCompleted(bool,HWND__ *)

- ea: `0x180029a6c`
- end: `0x180029e1a`
- name: `?DropCompleted@DragDropSession@DragDropTelemetry@@QEAAX_NPEAUHWND__@@@Z`
- size: `942`
- prototype: `void __fastcall(DragDropTelemetry::DragDropSession *this, bool dropTargetAccepted, HWND__ *dropWindow)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029908`

## callees

- `0x1800034d4`
- `0x1800039b4`
- `0x180029a6c`
- `0x18002a368`
- `0x18002a420`
- `0x18002d66c`
- `0x180042054`
- `0x180044574`
- `0x180046460`
- `0x180093128`
- `0x1800945e0`
- `0x1800c8cdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d73`
- `USER32!GetWindowThreadProcessId` at `0x180029aeb`
- `USER32!GetWindowThreadProcessId` at `0x180029aeb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180029b23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180029b23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180029b0f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180029b0f`

## pseudocode

```c
void __fastcall DragDropTelemetry::DragDropSession::DropCompleted(
        DragDropTelemetry::DragDropSession *this,
        unsigned __int64 dropTargetAccepted,
        HWND dropWindow)
{
  char v4; // r12
  const wchar_t *StringFromUIContext; // rax
  const wchar_t *v7; // r15
  unsigned int v8; // r8d
  wchar_t *FileNameW; // rsi
  wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *m_pActivityData; // rax
  int m_result; // ecx
  wil::StoredFailureInfo *p_m_failure; // rdi
  const _tlgProvider_t *v13; // rcx
  const _tlgProvider_t *v14; // rcx
  const _GUID *v15; // r9
  wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v16; // r8
  const wchar_t *v17; // rax
  const _tlgProvider_t *v18; // rax
  const _tlgProvider_t *v19; // rdi
  const wchar_t *v20; // rax
  unsigned int CurrentThreadId; // eax
  wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *v22; // r8
  const _GUID *v23; // r9
  unsigned int dropTargetPID; // [rsp+C0h] [rbp-80h] BYREF
  _tlgWrapperByVal<4> v25; // [rsp+C4h] [rbp-7Ch] BYREF
  _tlgWrapperByVal<4> v26; // [rsp+C8h] [rbp-78h] BYREF
  _tlgWrapperByVal<4> v27; // [rsp+CCh] [rbp-74h] BYREF
  _tlgWrapperByVal<4> v28; // [rsp+D0h] [rbp-70h] BYREF
  _tlgWrapperByVal<4> v29; // [rsp+D4h] [rbp-6Ch] BYREF
  _tlgWrapperByVal<4> v30; // [rsp+D8h] [rbp-68h] BYREF
  _tlgWrapSz<unsigned short> v31; // [rsp+E0h] [rbp-60h] BYREF
  _tlgWrapSz<char> v32; // [rsp+E8h] [rbp-58h] BYREF
  _tlgWrapSz<char> v33; // [rsp+F0h] [rbp-50h] BYREF
  _tlgWrapperByVal<8> v34; // [rsp+F8h] [rbp-48h] BYREF
  _tlgWrapperByVal<8> v35; // [rsp+100h] [rbp-40h] BYREF
  _tlgWrapperByVal<8> hProvider; // [rsp+108h] [rbp-38h] BYREF
  _tlgWrapSz<unsigned short> v37; // [rsp+110h] [rbp-30h] BYREF
  _tlgWrapSz<unsigned short> v38; // [rsp+118h] [rbp-28h] BYREF
  _tlgWrapSz<unsigned short> v39; // [rsp+120h] [rbp-20h] BYREF
  _tlgWrapSz<unsigned short> v40; // [rsp+128h] [rbp-18h] BYREF
  _tlgWrapSz<char> v41; // [rsp+130h] [rbp-10h] BYREF
  _tlgWrapSz<unsigned short> v42; // [rsp+138h] [rbp-8h] BYREF
  _tlgWrapSz<char> v43; // [rsp+140h] [rbp+0h] BYREF
  _tlgWrapSz<char> v44; // [rsp+148h] [rbp+8h] BYREF
  wchar_t dropTargetName[264]; // [rsp+150h] [rbp+10h] BYREF

  v4 = dropTargetAccepted;
  if ( DragDropTelemetry::IsEnabled((unsigned __int8)this, dropTargetAccepted) )
  {
    if ( dropWindow )
    {
      dropTargetPID = 0;
      if ( CallerIdentity::GetProcessTypeFromWindow(dropWindow, (PROCESS_UICONTEXT *)&dropTargetPID) >= 0 )
      {
        StringFromUIContext = DragDropTelemetryHelper::GetStringFromUIContext((PROCESS_UICONTEXT)dropTargetPID);
        dropTargetPID = 0;
        v7 = StringFromUIContext;
        GetWindowThreadProcessId(dropWindow, &dropTargetPID);
        if ( DragDropTelemetryHelper::GetProcessNameFromId(dropTargetPID, dropTargetName, v8) )
        {
          if ( PathIsFileSpecW(dropTargetName) )
            FileNameW = dropTargetName;
          else
            FileNameW = PathFindFileNameW(dropTargetName);
          m_pActivityData = this->m_pActivityData;
          m_result = m_pActivityData->m_result;
          if ( m_result >= 0
            || m_result != m_pActivityData->m_failure.m_failureInfo.hr
            || (p_m_failure = &m_pActivityData->m_failure,
                m_pActivityData == (wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DragDropLogging,_TlgReflectorTag_Param0IsProviderType> *)-80LL) )
          {
            wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop((wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType> *)this);
            v18 = DragDropLogging::Provider();
            v19 = v18;
            if ( v18->LevelPlus1 > 5 && tlgKeywordOn(v18, 0x400000000000uLL) )
            {
              v34.Value = (const unsigned __int64)v7;
              v33.Psz = (const char *const)FileNameW;
              v20 = L"Dropped";
              if ( !v4 )
                v20 = L"TargetRejected";
              v35.Value = 0x2000000;
              v32.Psz = (const char *const)v20;
              CurrentThreadId = GetCurrentThreadId();
              v22 = this->m_pActivityData;
              v26.Value = CurrentThreadId;
              v25.Value = v22->m_result;
              v31.Psz = (const wchar_t *const)0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                v19,
                &`DragDropTelemetry::DragDropSession::DropCompleted'::`42'::_tlgEvent._tlgChannel,
                &v22->m_Id,
                v23,
                (const _tlgWrapperByVal<8> *)&v31,
                &v25,
                &v26,
                (const _tlgWrapSz<unsigned short> *)&v32,
                (const _tlgWrapSz<unsigned short> *)&v33,
                (const _tlgWrapSz<unsigned short> *)&v34,
                &v35);
            }
          }
          else
          {
            wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop((wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType> *)this);
            v13 = DragDropLogging::Provider();
            if ( v13->LevelPlus1 > 5 && tlgKeywordOn(v13, 0x400000000000uLL) )
            {
              v16 = this->m_pActivityData;
              v37.Psz = v7;
              v17 = L"Dropped";
              v38.Psz = FileNameW;
              if ( !v4 )
                v17 = L"TargetRejected";
              v34.Value = 0x1000000;
              v39.Psz = v17;
              v40.Psz = p_m_failure->m_failureInfo.callContextCurrent.contextMessage;
              v41.Psz = p_m_failure->m_failureInfo.callContextCurrent.contextName;
              v27.Value = p_m_failure->m_failureInfo.callContextCurrent.contextId;
              v42.Psz = p_m_failure->m_failureInfo.callContextOriginating.contextMessage;
              v43.Psz = p_m_failure->m_failureInfo.callContextOriginating.contextName;
              v28.Value = p_m_failure->m_failureInfo.callContextOriginating.contextId;
              v44.Psz = p_m_failure->m_failureInfo.pszCallContext;
              v29.Value = p_m_failure->m_failureInfo.threadId;
              v31.Psz = p_m_failure->m_failureInfo.pszMessage;
              v30.Value = p_m_failure->m_failureInfo.type;
              v32.Psz = p_m_failure->m_failureInfo.pszModule;
              v25.Value = p_m_failure->m_failureInfo.uLineNumber;
              v33.Psz = p_m_failure->m_failureInfo.pszFile;
              v26.Value = p_m_failure->m_failureInfo.hr;
              hProvider.Value = 0x2000000;
              v35.Value = 0x2000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                v14,
                &`DragDropTelemetry::DragDropSession::DropCompleted'::`24'::_tlgEvent._tlgChannel,
                &v16->m_Id,
                v15,
                &v35,
                &v34,
                &v26,
                &v33,
                &v25,
                &v32,
                &v30,
                &v31,
                &v29,
                &v44,
                &v28,
                &v43,
                &v42,
                &v27,
                &v41,
                &v40,
                &v39,
                &v38,
                &v37,
                &hProvider);
            }
          }
          wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType> *)this);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180029a6c  mov     [rsp-8+arg_8], rbx
0x180029a71  mov     [rsp-8+arg_18], rsi
0x180029a76  push    rbp
0x180029a77  push    rdi
0x180029a78  push    r12
0x180029a7a  push    r14
0x180029a7c  push    r15
0x180029a7e  lea     rbp, [rsp-230h]
0x180029a86  sub     rsp, 370h
0x180029a8d  mov     rax, cs:__security_cookie
0x180029a94  xor     rax, rsp
0x180029a97  mov     [rbp+250h+var_30], rax
0x180029a9e  mov     rdi, dropWindow
0x180029aa1  mov     r12b, dropTargetAccepted
0x180029aa4  mov     rbx, this
0x180029aa7  call    ?IsEnabled@DragDropTelemetry@@SA_NE_K@Z; DragDropTelemetry::IsEnabled(uchar,unsigned __int64)
0x180029aac  test    al, al
0x180029aae  jz      loc_180029DEE
0x180029ab4  test    rdi, rdi
0x180029ab7  jz      loc_180029DEE
0x180029abd  and     [rbp+250h+dropTargetPID], 0
0x180029ac1  lea     rdx, [rbp+250h+dropTargetPID]; pProcessUIContext
0x180029ac5  mov     this, rdi; hwnd
0x180029ac8  call    ?GetProcessTypeFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAW4PROCESS_UICONTEXT@@@Z; CallerIdentity::GetProcessTypeFromWindow(HWND__ *,PROCESS_UICONTEXT *)
0x180029acd  test    eax, eax
0x180029acf  js      loc_180029DEE
0x180029ad5  mov     ecx, [rbp+250h+dropTargetPID]; uiContext
0x180029ad8  call    ?GetStringFromUIContext@DragDropTelemetryHelper@@SAPEBGW4PROCESS_UICONTEXT@@@Z; DragDropTelemetryHelper::GetStringFromUIContext(PROCESS_UICONTEXT)
0x180029add  and     [rbp+250h+dropTargetPID], 0
0x180029ae1  lea     rdx, [rbp+250h+dropTargetPID]; lpdwProcessId
0x180029ae5  mov     this, rdi; hWnd
0x180029ae8  mov     r15, rax
0x180029aeb  call    cs:__imp_GetWindowThreadProcessId
0x180029af2  nop     dword ptr [rax+rax+00h]
0x180029af7  mov     ecx, [rbp+250h+dropTargetPID]; processId
0x180029afa  lea     rdx, [rbp+250h+dropTargetName]; processName
0x180029afe  call    ?GetProcessNameFromId@DragDropTelemetryHelper@@SA_NKPEAGK@Z; DragDropTelemetryHelper::GetProcessNameFromId(ulong,ushort *,ulong)
0x180029b03  test    al, al
0x180029b05  jz      loc_180029DEE
0x180029b0b  lea     this, [rbp+250h+dropTargetName]; pszPath
0x180029b0f  call    cs:__imp_PathIsFileSpecW
0x180029b16  nop     dword ptr [rax+rax+00h]
0x180029b1b  test    eax, eax
0x180029b1d  jnz     short loc_180029B34
0x180029b1f  lea     this, [rbp+250h+dropTargetName]; pszPath
0x180029b23  call    cs:__imp_PathFindFileNameW
0x180029b2a  nop     dword ptr [rax+rax+00h]
0x180029b2f  mov     rsi, rax
0x180029b32  jmp     short loc_180029B38
0x180029b34  lea     rsi, [rbp+250h+dropTargetName]
0x180029b38  mov     rax, [rbx+110h]
0x180029b3f  mov     ecx, [rax+48h]
0x180029b42  test    ecx, ecx
0x180029b44  jns     loc_180029D15
0x180029b4a  cmp     ecx, [rax+58h]
0x180029b4d  jnz     loc_180029D15
0x180029b53  lea     rdi, [rax+50h]
0x180029b57  test    rdi, rdi
0x180029b5a  jz      loc_180029D15
0x180029b60  mov     this, rbx; this
0x180029b63  call    ?zInternalStop@?$ActivityBase@VDragDropLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180029b68  call    ?Provider@DragDropLogging@@SAPEBU_tlgProvider_t@@XZ; DragDropLogging::Provider(void)
0x180029b6d  mov     this, rax; hProvider
0x180029b70  cmp     dword ptr [rax], 5
0x180029b73  jbe     loc_180029DE6
0x180029b79  mov     rdx, 400000000000h; keyword
0x180029b83  call    _tlgKeywordOn
0x180029b88  test    al, al
0x180029b8a  jz      loc_180029DE6
0x180029b90  mov     dropWindow, [rbx+110h]; __annotation("_TlgWrite:|162|TraceLoggingType::Provider()|("DragDropSession")=~^*this^~|"PartA_PrivTags"=|"PartA_PrivTags"=|"wilActivity"=|"hresult"=Failure error code|"fileName"=Source code file name where the error occurred|"lineNumber"=Line number within the source code file where the error occurred|"module"=Name of the binary where the error occurred|"failureType"=Indicates what type of failure was observed (exception, returned error, logged error or fail fast|"message"=Custom message associated with the failure (if any)|"threadId"=Identifier of the thread the error occurred on|"callContext"=List of telemetry activities containing this error|"originatingContextId"=Identifier for the oldest telemetry activity containing this error|"originatingContextName"=Name of the oldest telemetry activity containing this error|"originatingContextMessage"=Custom message associated with the oldest telemetry activity containing this error (if any)|"currentContextId"=Identifier for the newest telemetry activity containing
0x180029b97  lea     rdx, aTargetrejected; "TargetRejected"
0x180029b9e  test    r12b, r12b
0x180029ba1  mov     [rbp+250h+var_280.Psz], r15
0x180029ba5  lea     rax, aDropped; "Dropped"
0x180029bac  mov     [rbp+250h+var_278.Psz], rsi
0x180029bb0  cmovz   rax, rdx
0x180029bb4  mov     [rbp+250h+var_298.Value], 1000000h
0x180029bbc  mov     [rbp+250h+var_270.Psz], rax
0x180029bc0  mov     r14d, 2000000h
0x180029bc6  mov     rax, [rdi+78h]
0x180029bca  add     dropWindow, 8; <writerArgs_0>
0x180029bce  mov     [rbp+250h+var_268.Psz], rax
0x180029bd2  mov     rax, [rdi+70h]
0x180029bd6  mov     [rbp+250h+var_260.Psz], rax
0x180029bda  mov     eax, [rdi+68h]
0x180029bdd  mov     [rbp+250h+var_2C4.Value], eax
0x180029be0  mov     rax, [rdi+60h]
0x180029be4  mov     [rbp+250h+var_258.Psz], rax
0x180029be8  mov     rax, [rdi+58h]
0x180029bec  mov     [rbp+250h+var_250.Psz], rax
0x180029bf0  mov     eax, [rdi+50h]
0x180029bf3  mov     [rbp+250h+var_2C0.Value], eax
0x180029bf6  mov     rax, [rdi+48h]
0x180029bfa  mov     [rbp+250h+var_248.Psz], rax
0x180029bfe  mov     eax, [rdi+20h]
0x180029c01  mov     [rbp+250h+var_2BC.Value], eax
0x180029c04  mov     rax, [rdi+18h]
0x180029c08  mov     [rbp+250h+var_2B0.Psz], rax
0x180029c0c  mov     eax, [rdi]
0x180029c0e  mov     [rbp+250h+var_2B8.Value], eax
0x180029c11  mov     rax, [rdi+80h]
0x180029c18  mov     [rbp+250h+var_2A8.Psz], rax
0x180029c1c  mov     eax, [rdi+40h]
0x180029c1f  mov     [rbp+250h+var_2CC.Value], eax
0x180029c22  mov     rax, [rdi+38h]
0x180029c26  mov     [rbp+250h+var_2A0.Psz], rax
0x180029c2a  mov     eax, [rdi+8]
0x180029c2d  mov     [rbp+250h+var_2C8.Value], eax
0x180029c30  lea     rax, [rbp+250h+var_288]
0x180029c34  mov     [rsp+390h+hProvider], rax; hProvider
0x180029c3c  lea     rax, [rbp+250h+var_280]
0x180029c40  mov     [rsp+390h+var_2E0], rax; <wrappedArgs_19>
0x180029c48  lea     rax, [rbp+250h+var_278]
0x180029c4c  mov     [rsp+390h+var_2E8], rax; <wrappedArgs_18>
0x180029c54  lea     rax, [rbp+250h+var_270]
0x180029c58  mov     [rsp+390h+var_2F0], rax; <wrappedArgs_17>
0x180029c60  lea     rax, [rbp+250h+var_268]
0x180029c64  mov     [rsp+390h+var_2F8], rax; <wrappedArgs_16>
0x180029c6c  lea     rax, [rbp+250h+var_260]
0x180029c70  mov     [rsp+390h+var_300], rax; <wrappedArgs_15>
0x180029c78  lea     rax, [rbp+250h+var_2C4]
0x180029c7c  mov     [rsp+390h+var_308], rax; <wrappedArgs_14>
0x180029c84  lea     rax, [rbp+250h+var_258]
0x180029c88  mov     [rsp+390h+var_310], rax; <wrappedArgs_13>
0x180029c90  lea     rax, [rbp+250h+var_250]
0x180029c94  mov     [rsp+390h+var_318], rax; <wrappedArgs_12>
0x180029c99  lea     rax, [rbp+250h+var_2C0]
0x180029c9d  mov     [rsp+390h+var_320], rax; <wrappedArgs_11>
0x180029ca2  lea     rax, [rbp+250h+var_248]
0x180029ca6  mov     [rsp+390h+var_328], rax; <wrappedArgs_10>
0x180029cab  lea     rax, [rbp+250h+var_2BC]
0x180029caf  mov     [rsp+390h+var_330], rax; <wrappedArgs_9>
0x180029cb4  lea     rax, [rbp+250h+var_2B0]
0x180029cb8  mov     [rsp+390h+var_338], rax; <wrappedArgs_8>
0x180029cbd  lea     rax, [rbp+250h+var_2B8]
0x180029cc1  mov     [rsp+390h+var_340], rax; <wrappedArgs_7>
0x180029cc6  lea     rax, [rbp+250h+var_2A8]
0x180029cca  mov     [rsp+390h+var_348], rax; <wrappedArgs_6>
0x180029ccf  lea     rax, [rbp+250h+var_2CC]
0x180029cd3  mov     [rsp+390h+var_350], rax; <wrappedArgs_5>
0x180029cd8  lea     rax, [rbp+250h+var_2A0]
0x180029cdc  mov     [rsp+390h+var_358], rax; <wrappedArgs_4>
0x180029ce1  lea     rax, [rbp+250h+var_2C8]
0x180029ce5  mov     [rsp+390h+var_360], rax; <wrappedArgs_3>
0x180029cea  lea     rax, [rbp+250h+var_298]
0x180029cee  mov     [rsp+390h+var_368], rax; <wrappedArgs_2>
0x180029cf3  lea     rax, [rbp+250h+var_290]
0x180029cf7  mov     [rsp+390h+var_370], rax; <wrappedArgs_1>
0x180029cfc  mov     [rbp+250h+var_288.Value], r14
0x180029d00  mov     [rbp+250h+var_290.Value], r14
0x180029d04  lea     rdx, ?_tlgEvent@?BI@??DropCompleted@DragDropSession@DragDropTelemetry@@QEAAX_NPEAUHWND__@@@Z@4U_unnamed_type__tlgEvent_@?BI@??123@QEAAX01@Z@B._tlgChannel; pEventMetadata
0x180029d0b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566663@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180029d10  jmp     loc_180029DE6
0x180029d15  mov     this, rbx; this
0x180029d18  call    ?zInternalStop@?$ActivityBase@VDragDropLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DragDropLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180029d1d  call    ?Provider@DragDropLogging@@SAPEBU_tlgProvider_t@@XZ; DragDropLogging::Provider(void)
0x180029d22  mov     rdi, rax
0x180029d25  cmp     dword ptr [rax], 5
0x180029d28  jbe     loc_180029DE6
0x180029d2e  mov     rdx, 400000000000h; keyword
0x180029d38  mov     this, rax; hProvider
0x180029d3b  call    _tlgKeywordOn
0x180029d40  test    al, al
0x180029d42  jz      loc_180029DE6
0x180029d48  lea     rdx, aTargetrejected; __annotation("_TlgWrite:|162|TraceLoggingType::Provider()|("DragDropSession")=~^*this^~|"PartA_PrivTags"=|"wilActivity"=|"hresult"=Failure error code|"threadId"=Identifier of the thread the activity was run on|"Result"=|"DropTargetName"=|"DropTargetUiContext"=|"PartA_PrivTags"=")
0x180029d4f  mov     [rbp+250h+var_298.Value], r15
0x180029d53  test    r12b, r12b
0x180029d56  mov     [rbp+250h+var_2A0.Psz], rsi
0x180029d5a  lea     rax, aDropped; "Dropped"
0x180029d61  mov     r14d, 2000000h
0x180029d67  cmovz   rax, rdx
0x180029d6b  mov     [rbp+250h+var_290.Value], r14
0x180029d6f  mov     [rbp+250h+var_2A8.Psz], rax
0x180029d73  call    cs:__imp_GetCurrentThreadId
0x180029d7a  nop     dword ptr [rax+rax+00h]
0x180029d7f  mov     dropWindow, [rbx+110h]
0x180029d86  lea     rdx, ?_tlgEvent@?CK@??DropCompleted@DragDropSession@DragDropTelemetry@@QEAAX_NPEAUHWND__@@@Z@4U_unnamed_type__tlgEvent_@?CK@??123@QEAAX01@Z@B._tlgChannel; pEventMetadata
0x180029d8d  mov     [rbp+250h+var_2C8.Value], eax
0x180029d90  mov     this, rdi; hProvider
0x180029d93  mov     eax, [dropWindow+48h]
0x180029d97  add     dropWindow, 8; <writerArgs_0>
0x180029d9b  mov     [rbp+250h+var_2CC.Value], eax
0x180029d9e  lea     rax, [rbp+250h+var_290]
0x180029da2  mov     [rsp+390h+var_340], rax; hProvider
0x180029da7  lea     rax, [rbp+250h+var_298]
0x180029dab  mov     [rsp+390h+var_348], rax; <wrappedArgs_6>
0x180029db0  lea     rax, [rbp+250h+var_2A0]
0x180029db4  mov     [rsp+390h+var_350], rax; <wrappedArgs_5>
0x180029db9  lea     rax, [rbp+250h+var_2A8]
0x180029dbd  mov     [rsp+390h+var_358], rax; <wrappedArgs_4>
0x180029dc2  lea     rax, [rbp+250h+var_2C8]
0x180029dc6  mov     [rsp+390h+var_360], rax; <wrappedArgs_3>
0x180029dcb  lea     rax, [rbp+250h+var_2CC]
0x180029dcf  mov     [rsp+390h+var_368], rax; <wrappedArgs_2>
0x180029dd4  lea     rax, [rbp+250h+var_2B0]
0x180029dd8  mov     [rsp+390h+var_370], rax; <wrappedArgs_1>
0x180029ddd  mov     [rbp+250h+var_2B0.Psz], r14
0x180029de1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@553@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180029de6  mov     this, rbx; this
0x180029de9  call    ?IgnoreCurrentThread@?$ActivityBase@VDragDropLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DragDropLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180029dee  mov     this, [rbp+250h+var_30]
0x180029df5  xor     this, rsp; StackCookie
0x180029df8  call    __security_check_cookie
0x180029dfd  lea     r11, [rsp+390h+var_20]
0x180029e05  mov     rbx, [r11+38h]
0x180029e09  mov     rsi, [r11+48h]
0x180029e0d  mov     rsp, r11
0x180029e10  pop     r15
0x180029e12  pop     r14
0x180029e14  pop     r12
0x180029e16  pop     rdi
0x180029e17  pop     rbp
0x180029e18  retn
```
