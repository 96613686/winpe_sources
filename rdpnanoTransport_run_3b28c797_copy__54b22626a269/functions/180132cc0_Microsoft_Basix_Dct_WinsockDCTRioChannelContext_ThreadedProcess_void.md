# Microsoft::Basix::Dct::WinsockDCTRioChannelContext::ThreadedProcess(void)

- ea: `0x180132cc0`
- end: `0x180132ebb`
- name: `?ThreadedProcess@WinsockDCTRioChannelContext@Dct@Basix@Microsoft@@EEAA_NXZ`
- size: `507`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x1800109a0`
- `0x180010a60`
- `0x180017344`
- `0x18001902c`
- `0x180024700`
- `0x180027b84`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18012b8f0`
- `0x180132cc0`
- `0x1801338a0`
- `0x1801ad754`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180132d40`
- `KERNEL32!GetLastError` at `0x180132d40`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180132d24`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180132d24`

## string_xrefs

- `0x180132dec`: `Failed to dequeue a completion with error code %d (%s)`
- `0x180132e54`: `Could not dequeue a completion request. Exiting IO Thread.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall Microsoft::Basix::Dct::WinsockDCTRioChannelContext::ThreadedProcess(HANDLE *this)
{
  Microsoft::Basix::Dct::detail::BasicStateManagement *v1; // rbx
  BOOL QueuedCompletionStatus; // edi
  DWORD LastError; // eax
  unsigned int v5; // edi
  Microsoft::Basix::Instrumentation::EventBase *v6; // rax
  Microsoft::Basix *v7; // rcx
  const struct std::error_category *v8; // rax
  __int64 v9; // rbx
  int v10; // r8d
  const char *v11; // r9
  Microsoft::Basix *v12; // rcx
  const struct std::error_category *v13; // rax
  _BYTE v14[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+A0h] [rbp-60h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+130h] [rbp+30h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+138h] [rbp+38h] BYREF
  __int128 v21; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 CompletionKey; // [rsp+150h] [rbp+50h] BYREF

  CompletionKey = 0;
  Overlapped = 0;
  NumberOfBytesTransferred = 0;
  v1 = (Microsoft::Basix::Dct::detail::BasicStateManagement *)(this - 136);
  QueuedCompletionStatus = GetQueuedCompletionStatus(
                             this[360],
                             &NumberOfBytesTransferred,
                             &CompletionKey,
                             &Overlapped,
                             0xFAu);
  if ( Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed(v1) )
    return 0;
  if ( QueuedCompletionStatus )
  {
    Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue(v1, 1);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 258 && LastError != 1784 )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v21, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v21);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v21) )
      {
        v6 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v21);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v6) )
        {
          v15 = v16;
          v8 = Microsoft::Basix::WindowsCategory(v7);
          v9 = (*(__int64 (__fastcall **)(const struct std::error_category *, _BYTE *, _QWORD))(*(_QWORD *)v8 + 16LL))(
                 v8,
                 v16,
                 v5);
          std::string::string(v14, "Failed to dequeue a completion with error code %d (%s)", v10, v11);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,std::string>(
            (unsigned int)&v21,
            (unsigned int)"NANO_DCT",
            (unsigned int)v14,
            v5,
            v9);
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v14);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v21);
      std::string::string(v16, (const char *)&Str1);
      std::string::string(v14, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
      std::string::string(v17, "Could not dequeue a completion request. Exiting IO Thread.");
      v13 = Microsoft::Basix::WindowsCategory(v12);
      v21 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v15, v5, v13);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v21,
        (unsigned int)v17,
        (unsigned int)v14,
        621,
        (__int64)v16);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180132cc0  mov     [rsp-8+arg_8], rbx
0x180132cc5  mov     [rsp-8+arg_10], rdi
0x180132cca  push    rbp
0x180132ccb  lea     rbp, [rsp-60h]
0x180132cd0  mov     eax, 160h
0x180132cd5  call    _alloca_probe
0x180132cda  sub     rsp, rax
0x180132cdd  mov     rax, cs:__security_cookie
0x180132ce4  xor     rax, rsp
0x180132ce7  mov     [rbp+60h+var_8], rax
0x180132ceb  mov     [rbp+60h+CompletionKey], 0
0x180132cf3  mov     [rbp+60h+Overlapped], 0
0x180132cfb  mov     [rbp+60h+NumberOfBytesTransferred], 0
0x180132d02  lea     rbx, [rcx-440h]
0x180132d09  mov     [rsp+160h+dwMilliseconds], 0FAh; dwMilliseconds
0x180132d11  lea     r9, [rbp+60h+Overlapped]; lpOverlapped
0x180132d15  lea     r8, [rbp+60h+CompletionKey]; lpCompletionKey
0x180132d19  lea     rdx, [rbp+60h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180132d1d  mov     rcx, [rbx+0F80h]; CompletionPort
0x180132d24  call    cs:__imp_GetQueuedCompletionStatus
0x180132d2a  mov     edi, eax
0x180132d2c  mov     rcx, rbx; this
0x180132d2f  call    ?IsClosed@BasicStateManagement@detail@Dct@Basix@Microsoft@@QEBA_NXZ; Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed(void)
0x180132d34  test    al, al
0x180132d36  jz      short loc_180132D3C
0x180132d38  xor     al, al
0x180132d3a  jmp     short loc_180132D64
0x180132d3c  test    edi, edi
0x180132d3e  jnz     short loc_180132D58
0x180132d40  call    cs:__imp_GetLastError
0x180132d46  mov     edi, eax
0x180132d48  cmp     eax, 102h
0x180132d4d  jz      short loc_180132D62
0x180132d4f  cmp     eax, 6F8h
0x180132d54  jnz     short loc_180132D85
0x180132d56  jmp     short loc_180132D62
0x180132d58  mov     dl, 1; bool
0x180132d5a  mov     rcx, rbx; this
0x180132d5d  call    ?_DrainCompletionQueue@WinsockDCTRioChannelContext@Dct@Basix@Microsoft@@AEAAX_N@Z; Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue(bool)
0x180132d62  mov     al, 1
0x180132d64  mov     rcx, [rbp+60h+var_8]
0x180132d68  xor     rcx, rsp; StackCookie
0x180132d6b  call    __security_check_cookie
0x180132d70  lea     r11, [rsp+160h+var_s0]
0x180132d78  mov     rbx, [r11+18h]
0x180132d7c  mov     rdi, [r11+20h]
0x180132d80  mov     rsp, r11
0x180132d83  pop     rbp
0x180132d84  retn
0x180132d85  mov     edx, 10h; unsigned __int64
0x180132d8a  lea     rcx, [rbp+60h+var_20]; this
0x180132d8e  call    ?__autoclassinit2@exception_ptr@std@@QEAAX_K@Z; std::exception_ptr::__autoclassinit2(unsigned __int64)
0x180132d93  lea     rcx, [rbp+60h+var_20]
0x180132d97  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180132d9c  nop
0x180132d9d  lea     rcx, [rbp+60h+var_20]
0x180132da1  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x180132da6  test    al, al
0x180132da8  jz      short loc_180132E27
0x180132daa  lea     rcx, [rbp+60h+var_20]
0x180132dae  call    ??$iterator_to_raw_pointer@PEAV?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@@movelib@boost@@YAPEAV?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@AEBQEAV23@@Z; boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> * const &)
0x180132db3  mov     rcx, rax; this
0x180132db6  call    ?IsEnabled@EventBase@Instrumentation@Basix@Microsoft@@QEBA_NXZ; Microsoft::Basix::Instrumentation::EventBase::IsEnabled(void)
0x180132dbb  test    al, al
0x180132dbd  jz      short loc_180132E27
0x180132dbf  lea     rax, [rsp+160h+var_100]
0x180132dc4  mov     [rsp+160h+var_110], rax
0x180132dc9  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180132dce  mov     r9, rax
0x180132dd1  mov     rcx, [rax]
0x180132dd4  mov     rax, [rcx+10h]
0x180132dd8  mov     r8d, edi
0x180132ddb  lea     rdx, [rsp+160h+var_100]
0x180132de0  mov     rcx, r9
0x180132de3  call    cs:__guard_dispatch_icall_fptr
0x180132de9  mov     rbx, rax
0x180132dec  lea     rdx, aFailedToDequeu; "Failed to dequeue a completion with err"...
0x180132df3  lea     rcx, [rsp+160h+var_130]
0x180132df8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180132dfd  nop
0x180132dfe  mov     qword ptr [rsp+160h+dwMilliseconds], rbx
0x180132e03  mov     r9d, edi
0x180132e06  lea     r8, [rsp+160h+var_130]
0x180132e0b  lea     rdx, aNanoDct; "NANO_DCT"
0x180132e12  lea     rcx, [rbp+60h+var_20]
0x180132e16  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IV65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,std::string)
0x180132e1b  nop
0x180132e1c  lea     rcx, [rsp+160h+var_130]; void *
0x180132e21  call    ??1?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@property_tree@boost@@QEAA@XZ; boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(void)
0x180132e26  nop
0x180132e27  lea     rcx, [rbp+60h+var_20]; void *
0x180132e2b  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x180132e30  lea     rdx, Str1
0x180132e37  lea     rcx, [rsp+160h+var_100]
0x180132e3c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180132e41  nop
0x180132e42  lea     rdx, aCW1SSrcLibbasi_82; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180132e49  lea     rcx, [rsp+160h+var_130]
0x180132e4e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180132e53  nop
0x180132e54  lea     rdx, aCouldNotDequeu; "Could not dequeue a completion request."...
0x180132e5b  lea     rcx, [rbp+60h+var_E0]
0x180132e5f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180132e64  nop
0x180132e65  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180132e6a  mov     r8, rax; struct std::error_category *
0x180132e6d  mov     edx, edi; int
0x180132e6f  lea     rcx, [rsp+160h+var_110]; this
0x180132e74  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180132e79  movups  xmm0, xmmword ptr [rax]
0x180132e7c  movdqu  [rbp+60h+var_20], xmm0
0x180132e81  lea     rax, [rsp+160h+var_100]
0x180132e86  mov     [rsp+160h+var_138], rax
0x180132e8b  mov     qword ptr [rsp+160h+dwMilliseconds], 26Dh
0x180132e94  lea     r9, [rsp+160h+var_130]
0x180132e99  lea     r8, [rbp+60h+var_E0]
0x180132e9d  lea     rdx, [rbp+60h+var_20]
0x180132ea1  lea     rcx, [rbp+60h+pExceptionObject]
0x180132ea5  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180132eaa  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180132eb1  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180132eb5  call    _CxxThrowException
```
