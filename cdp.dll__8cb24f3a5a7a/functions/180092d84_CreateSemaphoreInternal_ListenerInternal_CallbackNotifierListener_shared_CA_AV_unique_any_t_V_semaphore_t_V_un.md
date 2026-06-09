# ?CreateSemaphoreInternal@ListenerInternal@CallbackNotifierListener@shared@@CA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z

- ea: `0x180092d84`
- end: `0x1800931ab`
- name: `?CreateSemaphoreInternal@ListenerInternal@CallbackNotifierListener@shared@@CA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1063`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009240c`
- `0x180093b20`

## callees

- `0x180009770`
- `0x180009b94`
- `0x18000acdc`
- `0x18000d02c`
- `0x180092d84`
- `0x1800935cc`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801782cc`
- `0x1801f6fb0`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092fa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800930d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092fa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800930d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092e26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009317f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009317f`
- `ntdll!RtlNtStatusToDosError` at `0x180092f7c`
- `ntdll!RtlNtStatusToDosError` at `0x1800930a2`
- `ntdll!RtlNtStatusToDosError` at `0x180092f7c`
- `ntdll!RtlNtStatusToDosError` at `0x1800930a2`
- `ntdll!NtCreateSemaphore` at `0x180093054`
- `ntdll!NtCreateSemaphore` at `0x18009309a`
- `ntdll!NtCreateSemaphore` at `0x180093054`
- `ntdll!NtCreateSemaphore` at `0x18009309a`
- `ntdll!RtlInitUnicodeString` at `0x180092f24`
- `ntdll!RtlInitUnicodeString` at `0x180092f24`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x180092f54`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x180092f74`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x180092f54`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x180092f74`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180092e00`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180092e00`

## string_xrefs

- `0x180092e7e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180092fd4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180093104`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HLOCAL *__fastcall shared::CallbackNotifierListener::ListenerInternal::CreateSemaphoreInternal(HLOCAL *a1, _QWORD *a2)
{
  BOOL v4; // esi
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  _QWORD *v12; // r8
  const WCHAR *v13; // rdx
  NTSTATUS v14; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  NTSTATUS v22; // ebx
  NTSTATUS v23; // eax
  signed int v24; // eax
  unsigned int v25; // ebx
  int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  unsigned int v32; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL *p_hMem; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  char v35; // [rsp+48h] [rbp-B8h]
  int v36; // [rsp+50h] [rbp-B0h]
  __int64 CurrentThreadId; // [rsp+58h] [rbp-A8h] BYREF
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v42; // [rsp+88h] [rbp-78h]
  int v43; // [rsp+90h] [rbp-70h]
  HLOCAL *v44; // [rsp+98h] [rbp-68h]
  _BYTE v45[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v47[3]; // [rsp+F0h] [rbp-10h] BYREF
  PCWSTR SourceString[2]; // [rsp+120h] [rbp+20h] BYREF
  __m128i si128; // [rsp+130h] [rbp+30h]
  _BYTE v50[128]; // [rsp+140h] [rbp+40h] BYREF

  v44 = a1;
  v36 = 0;
  v41 = 24;
  v43 = 0;
  hMem = 0;
  p_hMem = &hMem;
  SecurityDescriptor = 0;
  v35 = 1;
  v4 = ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;WD)", 1u, &SecurityDescriptor, 0);
  if ( v35 )
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      p_hMem,
      SecurityDescriptor);
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    p_hMem = (HLOCAL *)".\\callbacknotifierlistener.cpp";
    LODWORD(SecurityDescriptor) = 264;
    v32 = v6;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v7,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v32,
      (unsigned int)&p_hMem,
      (__int64)&SecurityDescriptor,
      (__int64)&CurrentThreadId);
    v8 = cdp::ExceptionStackFromSourceLocationInfo(v45, &p_hMem);
    v11 = cdp::ErrorCodeToString(v6, v9, v10, v8);
    ConnectedDevices::Exception::Exception(pExceptionObject, v6, v11);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v42 = hMem;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v50);
  if ( a2[3] <= 0xFu )
    v12 = a2;
  else
    v12 = (_QWORD *)*a2;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v50,
    SourceString,
    v12,
    (char *)v12 + a2[2]);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v50);
  v36 = 14;
  DestinationString = 0;
  v13 = (const WCHAR *)SourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v13 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v13);
  memset(v47, 0, sizeof(v47));
  ObjectAttributes = 0;
  if ( (int)BaseFormatObjectAttributes(v47, &v41, &DestinationString, &ObjectAttributes) < 0 )
  {
    v14 = BaseFormatObjectAttributes(v47, &v41, &DestinationString, &ObjectAttributes);
    v15 = RtlNtStatusToDosError(v14);
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    p_hMem = (HLOCAL *)".\\callbacknotifierlistener.cpp";
    LODWORD(SecurityDescriptor) = 273;
    v32 = v16;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v17,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v32,
      (unsigned int)&p_hMem,
      (__int64)&SecurityDescriptor,
      (__int64)&CurrentThreadId);
    v18 = cdp::ExceptionStackFromSourceLocationInfo(v45, &p_hMem);
    v21 = cdp::ErrorCodeToString(v16, v19, v20, v18);
    ConnectedDevices::Exception::Exception(pExceptionObject, v16, v21);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  *a1 = 0;
  v36 = 15;
  p_hMem = a1;
  SecurityDescriptor = 0;
  v35 = 1;
  v22 = NtCreateSemaphore(&SecurityDescriptor, 0x100003u, ObjectAttributes, 0, 0xFFFF);
  __1__out_param_t_V__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&p_hMem);
  if ( v22 < 0 )
  {
    p_hMem = a1;
    SecurityDescriptor = 0;
    v35 = 1;
    v23 = NtCreateSemaphore(&SecurityDescriptor, 0x100003u, ObjectAttributes, 0, 0xFFFF);
    v24 = RtlNtStatusToDosError(v23);
    v25 = v24;
    if ( v24 > 0 )
      v25 = (unsigned __int16)v24 | 0x80070000;
    __1__out_param_t_V__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&p_hMem);
    p_hMem = (HLOCAL *)".\\callbacknotifierlistener.cpp";
    LODWORD(SecurityDescriptor) = 277;
    v32 = v25;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v26,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v32,
      (unsigned int)&p_hMem,
      (__int64)&SecurityDescriptor,
      (__int64)&CurrentThreadId);
    v27 = cdp::ExceptionStackFromSourceLocationInfo(v45, &p_hMem);
    v30 = cdp::ErrorCodeToString(v25, v28, v29, v27);
    ConnectedDevices::Exception::Exception(pExceptionObject, v25, v30);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(SourceString[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(SourceString[0]) = 0;
  if ( hMem )
    LocalFree(hMem);
  return a1;
}

```

## disassembly

```asm
0x180092d84  mov     [rsp-8+arg_10], rbx
0x180092d89  push    rbp
0x180092d8a  push    rsi
0x180092d8b  push    rdi
0x180092d8c  lea     rbp, [rsp-0D0h]
0x180092d94  sub     rsp, 1D0h
0x180092d9b  mov     rax, cs:__security_cookie
0x180092da2  xor     rax, rsp
0x180092da5  mov     [rbp+0E0h+var_20], rax
0x180092dac  mov     rbx, rdx
0x180092daf  mov     rdi, rcx
0x180092db2  mov     [rbp+0E0h+var_148], rcx
0x180092db6  mov     [rsp+1E0h+var_190], 0
0x180092dbe  mov     [rbp+0E0h+var_160], 18h
0x180092dc5  mov     [rbp+0E0h+var_150], 0
0x180092dcc  mov     [rsp+1E0h+hMem], 0
0x180092dd5  lea     rax, [rsp+1E0h+hMem]
0x180092dda  mov     [rsp+1E0h+var_1A8], rax
0x180092ddf  mov     [rsp+1E0h+SecurityDescriptor], 0
0x180092de8  mov     [rsp+1E0h+var_198], 1
0x180092ded  xor     r9d, r9d; SecurityDescriptorSize
0x180092df0  lea     r8, [rsp+1E0h+SecurityDescriptor]; SecurityDescriptor
0x180092df5  lea     edx, [r9+1]; StringSDRevision
0x180092df9  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)"
0x180092e00  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180092e06  mov     esi, eax
0x180092e08  cmp     [rsp+1E0h+var_198], 0
0x180092e0d  jz      short loc_180092E1E
0x180092e0f  mov     rdx, [rsp+1E0h+SecurityDescriptor]
0x180092e14  mov     rcx, [rsp+1E0h+var_1A8]
0x180092e19  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180092e1e  test    esi, esi
0x180092e20  jnz     loc_180092EC1
0x180092e26  call    cs:__imp_GetLastError
0x180092e2c  mov     ebx, eax
0x180092e2e  test    eax, eax
0x180092e30  jle     short loc_180092E3B
0x180092e32  movzx   ebx, ax
0x180092e35  or      ebx, 80070000h
0x180092e3b  lea     rax, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x180092e42  mov     [rsp+1E0h+var_1A8], rax
0x180092e47  mov     dword ptr [rsp+1E0h+SecurityDescriptor], 108h
0x180092e4f  mov     [rsp+1E0h+var_1B0], ebx
0x180092e53  call    cs:__imp_GetCurrentThreadId
0x180092e59  mov     eax, eax
0x180092e5b  mov     [rsp+1E0h+var_188], rax
0x180092e60  lea     rax, [rsp+1E0h+var_188]
0x180092e65  mov     [rsp+1E0h+var_1B8], rax
0x180092e6a  lea     rax, [rsp+1E0h+SecurityDescriptor]
0x180092e6f  mov     qword ptr [rsp+1E0h+MaximumCount], rax
0x180092e74  lea     r9, [rsp+1E0h+var_1A8]
0x180092e79  lea     r8, [rsp+1E0h+var_1B0]
0x180092e7e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180092e85  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180092e8a  lea     rdx, [rsp+1E0h+var_1A8]
0x180092e8f  lea     rcx, [rbp+0E0h+var_140]
0x180092e93  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180092e98  mov     r9, rax
0x180092e9b  mov     ecx, ebx
0x180092e9d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180092ea2  mov     r8, rax
0x180092ea5  mov     edx, ebx
0x180092ea7  lea     rcx, [rbp+0E0h+pExceptionObject]
0x180092eab  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180092eb0  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180092eb7  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x180092ebb  call    _CxxThrowException_0
0x180092ec1  mov     rax, [rsp+1E0h+hMem]
0x180092ec6  mov     [rbp+0E0h+var_158], rax
0x180092eca  lea     rcx, [rbp+0E0h+var_A0]
0x180092ece  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180092ed3  nop
0x180092ed4  cmp     qword ptr [rbx+18h], 0Fh
0x180092ed9  jbe     short loc_180092EE0
0x180092edb  mov     r8, [rbx]
0x180092ede  jmp     short loc_180092EE3
0x180092ee0  mov     r8, rbx
0x180092ee3  mov     r9, [rbx+10h]
0x180092ee7  add     r9, r8
0x180092eea  lea     rdx, [rbp+0E0h+SourceString]
0x180092eee  lea     rcx, [rbp+0E0h+var_A0]
0x180092ef2  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180092ef7  nop
0x180092ef8  lea     rcx, [rbp+0E0h+var_A0]
0x180092efc  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180092f01  mov     [rsp+1E0h+var_190], 0Eh
0x180092f09  xorps   xmm0, xmm0
0x180092f0c  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x180092f11  lea     rdx, [rbp+0E0h+SourceString]
0x180092f15  cmp     [rbp+0E0h+var_A8], 7
0x180092f1a  cmova   rdx, [rbp+0E0h+SourceString]; SourceString
0x180092f1f  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x180092f24  call    cs:__imp_RtlInitUnicodeString
0x180092f2a  xorps   xmm0, xmm0
0x180092f2d  movups  [rbp+0E0h+var_F0], xmm0
0x180092f31  movups  [rbp+0E0h+var_E0], xmm0
0x180092f35  movups  [rbp+0E0h+var_D0], xmm0
0x180092f39  mov     [rsp+1E0h+ObjectAttributes], 0
0x180092f42  lea     r9, [rsp+1E0h+ObjectAttributes]
0x180092f47  lea     r8, [rsp+1E0h+DestinationString]
0x180092f4c  lea     rdx, [rbp+0E0h+var_160]
0x180092f50  lea     rcx, [rbp+0E0h+var_F0]
0x180092f54  call    cs:__imp_BaseFormatObjectAttributes
0x180092f5a  test    eax, eax
0x180092f5c  jns     loc_180093017
0x180092f62  lea     r9, [rsp+1E0h+ObjectAttributes]
0x180092f67  lea     r8, [rsp+1E0h+DestinationString]
0x180092f6c  lea     rdx, [rbp+0E0h+var_160]
0x180092f70  lea     rcx, [rbp+0E0h+var_F0]
0x180092f74  call    cs:__imp_BaseFormatObjectAttributes
0x180092f7a  mov     ecx, eax; Status
0x180092f7c  call    cs:__imp_RtlNtStatusToDosError
0x180092f82  mov     ebx, eax
0x180092f84  test    eax, eax
0x180092f86  jle     short loc_180092F91
0x180092f88  movzx   ebx, ax
0x180092f8b  or      ebx, 80070000h
0x180092f91  lea     rax, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x180092f98  mov     [rsp+1E0h+var_1A8], rax
0x180092f9d  mov     dword ptr [rsp+1E0h+SecurityDescriptor], 111h
0x180092fa5  mov     [rsp+1E0h+var_1B0], ebx
0x180092fa9  call    cs:__imp_GetCurrentThreadId
0x180092faf  mov     eax, eax
0x180092fb1  mov     [rsp+1E0h+var_188], rax
0x180092fb6  lea     rax, [rsp+1E0h+var_188]
0x180092fbb  mov     [rsp+1E0h+var_1B8], rax
0x180092fc0  lea     rax, [rsp+1E0h+SecurityDescriptor]
0x180092fc5  mov     qword ptr [rsp+1E0h+MaximumCount], rax
0x180092fca  lea     r9, [rsp+1E0h+var_1A8]
0x180092fcf  lea     r8, [rsp+1E0h+var_1B0]
0x180092fd4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180092fdb  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180092fe0  lea     rdx, [rsp+1E0h+var_1A8]
0x180092fe5  lea     rcx, [rbp+0E0h+var_140]
0x180092fe9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180092fee  mov     r9, rax
0x180092ff1  mov     ecx, ebx
0x180092ff3  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180092ff8  mov     r8, rax
0x180092ffb  mov     edx, ebx
0x180092ffd  lea     rcx, [rbp+0E0h+pExceptionObject]
0x180093001  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180093006  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18009300d  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x180093011  call    _CxxThrowException_0
0x180093017  mov     qword ptr [rdi], 0
0x18009301e  mov     [rsp+1E0h+var_190], 0Fh
0x180093026  mov     [rsp+1E0h+var_1A8], rdi
0x18009302b  mov     [rsp+1E0h+SecurityDescriptor], 0
0x180093034  mov     [rsp+1E0h+var_198], 1
0x180093039  mov     esi, 0FFFFh
0x18009303e  mov     [rsp+1E0h+MaximumCount], esi; MaximumCount
0x180093042  xor     r9d, r9d; InitialCount
0x180093045  mov     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x18009304a  mov     edx, 100003h; DesiredAccess
0x18009304f  lea     rcx, [rsp+1E0h+SecurityDescriptor]; SemaphoreHandle
0x180093054  call    cs:__imp_NtCreateSemaphore
0x18009305a  mov     ebx, eax
0x18009305c  lea     rcx, [rsp+1E0h+var_1A8]
0x180093061  call    ??1?$out_param_t@V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x180093066  shr     ebx, 1Fh
0x180093069  test    bl, bl
0x18009306b  jz      loc_180093147
0x180093071  mov     [rsp+1E0h+var_1A8], rdi
0x180093076  mov     [rsp+1E0h+SecurityDescriptor], 0
0x18009307f  mov     [rsp+1E0h+var_198], 1
0x180093084  mov     [rsp+1E0h+MaximumCount], esi; MaximumCount
0x180093088  xor     r9d, r9d; InitialCount
0x18009308b  mov     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x180093090  mov     edx, 100003h; DesiredAccess
0x180093095  lea     rcx, [rsp+1E0h+SecurityDescriptor]; SemaphoreHandle
0x18009309a  call    cs:__imp_NtCreateSemaphore
0x1800930a0  mov     ecx, eax; Status
0x1800930a2  call    cs:__imp_RtlNtStatusToDosError
0x1800930a8  mov     ebx, eax
0x1800930aa  test    eax, eax
0x1800930ac  jle     short loc_1800930B7
0x1800930ae  movzx   ebx, ax
0x1800930b1  or      ebx, 80070000h
0x1800930b7  lea     rcx, [rsp+1E0h+var_1A8]
0x1800930bc  call    ??1?$out_param_t@V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x1800930c1  lea     rax, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x1800930c8  mov     [rsp+1E0h+var_1A8], rax
0x1800930cd  mov     dword ptr [rsp+1E0h+SecurityDescriptor], 115h
0x1800930d5  mov     [rsp+1E0h+var_1B0], ebx
0x1800930d9  call    cs:__imp_GetCurrentThreadId
0x1800930df  mov     eax, eax
0x1800930e1  mov     [rsp+1E0h+var_188], rax
0x1800930e6  lea     rax, [rsp+1E0h+var_188]
0x1800930eb  mov     [rsp+1E0h+var_1B8], rax
0x1800930f0  lea     rax, [rsp+1E0h+SecurityDescriptor]
0x1800930f5  mov     qword ptr [rsp+1E0h+MaximumCount], rax
0x1800930fa  lea     r9, [rsp+1E0h+var_1A8]
0x1800930ff  lea     r8, [rsp+1E0h+var_1B0]
0x180093104  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18009310b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180093110  lea     rdx, [rsp+1E0h+var_1A8]
0x180093115  lea     rcx, [rbp+0E0h+var_140]
0x180093119  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18009311e  mov     r9, rax
0x180093121  mov     ecx, ebx
0x180093123  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180093128  mov     r8, rax
0x18009312b  mov     edx, ebx
0x18009312d  lea     rcx, [rbp+0E0h+pExceptionObject]
0x180093131  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180093136  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18009313d  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x180093141  call    _CxxThrowException_0
0x180093147  mov     rdx, [rbp+0E0h+var_A8]
0x18009314b  cmp     rdx, 7
0x18009314f  jbe     short loc_180093162
0x180093151  lea     rdx, ds:2[rdx*2]
0x180093159  mov     rcx, [rbp+0E0h+SourceString]
0x18009315d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180093162  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18009316a  movdqu  xmmword ptr [rbp+30h], xmm0
0x18009316f  xor     ecx, ecx
0x180093171  mov     word ptr [rbp+0E0h+SourceString], cx
0x180093175  mov     rcx, [rsp+1E0h+hMem]; hMem
0x18009317a  test    rcx, rcx
0x18009317d  jz      short loc_180093185
0x18009317f  call    cs:__imp_LocalFree
0x180093185  mov     rax, rdi
0x180093188  mov     rcx, [rbp+0E0h+var_20]
0x18009318f  xor     rcx, rsp; StackCookie
0x180093192  call    __security_check_cookie
0x180093197  mov     rbx, [rsp+1E0h+arg_10]
0x18009319f  add     rsp, 1D0h
0x1800931a6  pop     rdi
0x1800931a7  pop     rsi
0x1800931a8  pop     rbp
0x1800931a9  retn
```
