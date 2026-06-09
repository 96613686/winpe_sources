# Microsoft::Basix::Dct::WinsockDCTChannelContext::WaitForIOCPRequestCompletion(void)

- ea: `0x180153ac0`
- end: `0x1801541cb`
- name: `?WaitForIOCPRequestCompletion@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAA?AV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@XZ`
- size: `1803`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180152cc0`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180017380`
- `0x180017404`
- `0x180017494`
- `0x180018d1c`
- `0x18001902c`
- `0x180024700`
- `0x180024760`
- `0x180027b84`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18003f5c0`
- `0x1800448dc`
- `0x18011963c`
- `0x18012b8f0`
- `0x18014d140`
- `0x18014d714`
- `0x180153ac0`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311d5c`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180153b86`
- `KERNEL32!GetLastError` at `0x180153b86`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180153b36`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180153b36`

## string_xrefs

- `0x1801540fc`: `Failed to dequeue a completion with error code %d (%s)`
- `0x180154163`: `Could not dequeue a completion request. Exiting IO Thread.`
- `0x180153ffa`: `GetQueuedCompletionStatus() error %d: bytesTransfered(%d), lpOverlapped=%p`
- `0x180153dac`: `Failed in IO Read `
- `0x180153d2e`: `Failed in IO Write peer: `

## pseudocode

```c
// Hidden C++ exception states: #wind=23
char **__fastcall Microsoft::Basix::Dct::WinsockDCTChannelContext::WaitForIOCPRequestCompletion(HANDLE *a1, char **a2)
{
  BOOL QueuedCompletionStatus; // ebx
  char *p_hEvent; // rsi
  DWORD LastError; // eax
  unsigned int v7; // r14d
  Microsoft::Basix *v8; // rcx
  const struct std::error_category *v9; // rax
  __int64 v10; // rbx
  const char *v11; // r9
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rcx
  __int128 *v14; // rax
  int v15; // ebx
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rbx
  Microsoft::Basix *v23; // rcx
  const struct std::error_category *v24; // rax
  __int64 v25; // rax
  const void *v26; // rax
  int v28; // r9d
  LPOVERLAPPED v29; // rbx
  char v30; // di
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v33; // rax
  Microsoft::Basix *v34; // rcx
  const struct std::error_category *v35; // rax
  __int64 v36; // rbx
  int v37; // r8d
  const char *v38; // r9
  Microsoft::Basix *v39; // rcx
  const struct std::error_category *v40; // rax
  const void *dwMilliseconds; // [rsp+20h] [rbp-E0h]
  char v42; // [rsp+30h] [rbp-D0h]
  __int128 v43; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v44; // [rsp+48h] [rbp-B8h]
  int v45; // [rsp+58h] [rbp-A8h]
  char *v46; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v47[32]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v48[4]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v49[40]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+D0h] [rbp-30h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+160h] [rbp+60h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+168h] [rbp+68h] BYREF
  __int128 v53; // [rsp+170h] [rbp+70h] BYREF
  __m128i v54; // [rsp+180h] [rbp+80h]
  __int128 v55; // [rsp+190h] [rbp+90h] BYREF
  __m128i si128; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 CompletionKey; // [rsp+1B0h] [rbp+B0h] BYREF

  v46 = (char *)a2;
  v45 = 0;
  CompletionKey = 0;
  Overlapped = 0;
  NumberOfBytesTransferred = 0;
  QueuedCompletionStatus = GetQueuedCompletionStatus(
                             a1[496],
                             &NumberOfBytesTransferred,
                             &CompletionKey,
                             &Overlapped,
                             0xFAu);
  if ( Overlapped )
    p_hEvent = (char *)&Overlapped[-1].hEvent;
  else
    p_hEvent = 0;
  v46 = p_hEvent;
  if ( *(_DWORD *)(*(__int64 (__fastcall **)(HANDLE *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 2) == 34 )
  {
    *a2 = 0;
    if ( p_hEvent )
      (**(void (__fastcall ***)(char *, __int64))p_hEvent)(p_hEvent, 1);
    return a2;
  }
  if ( QueuedCompletionStatus )
    goto LABEL_32;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 258 && LastError != 1784 && LastError != 234 )
  {
    if ( !Overlapped )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v53, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v53);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              &v53,
                              v32) )
      {
        v33 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v53);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v33) )
        {
          v48[0] = v49;
          v35 = Microsoft::Basix::WindowsCategory(v34);
          v36 = (*(__int64 (__fastcall **)(const struct std::error_category *, _BYTE *, _QWORD))(*(_QWORD *)v35 + 16LL))(
                  v35,
                  v49,
                  v7);
          std::string::string(&v43, "Failed to dequeue a completion with error code %d (%s)", v37, v38);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,std::string>(
            (unsigned int)&v53,
            (unsigned int)"NANO_DCT",
            (unsigned int)&v43,
            v7,
            v36);
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v43);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v53);
      std::string::string(v49, (const char *)&Str1);
      std::string::string(&v43, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp");
      std::string::string(v47, "Could not dequeue a completion request. Exiting IO Thread.");
      v40 = Microsoft::Basix::WindowsCategory(v39);
      v53 = *(_OWORD *)std::error_code::error_code((std::error_code *)v48, v7, v40);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v53,
        (unsigned int)v47,
        (unsigned int)&v43,
        598,
        (__int64)v49);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    v53 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v53);
    if ( (_QWORD)v53 && *(_BYTE *)(v53 + 128) )
    {
      v48[0] = v47;
      v9 = Microsoft::Basix::WindowsCategory(v8);
      v10 = (*(__int64 (__fastcall **)(const struct std::error_category *, _BYTE *, _QWORD))(*(_QWORD *)v9 + 16LL))(
              v9,
              v47,
              v7);
      v43 = 0;
      v44 = 0;
      std::string::_Construct<1,char const *>(&v43, "IO request failed with error code %d (%s)", 41, v11);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,std::string>(
        (unsigned int)&v53,
        (unsigned int)"NANO_DCT",
        (unsigned int)&v43,
        v7,
        v10);
      std::string::_Tidy_deallocate(&v43);
    }
    v12 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
    if ( *((_QWORD *)&v53 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v53 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( !_InterlockedDecrement(v12 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v55 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v55) = 0;
    if ( *((_DWORD *)p_hEvent + 71) == 1 )
    {
      std::string::assign(&v55, "Failed in IO Read ");
    }
    else if ( *((_DWORD *)p_hEvent + 71) == 2 )
    {
      v13 = *((_QWORD *)p_hEvent + 16);
      if ( v13 )
      {
        v14 = (__int128 *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 8LL))(v13, v49);
        v15 = 2;
      }
      else
      {
        v43 = 0;
        v44 = 0;
        std::string::_Construct<1,char const *>(&v43, (const char *)&Str1, 0);
        v14 = &v43;
        v15 = 4;
      }
      v45 = v15;
      v16 = std::operator+<char>(v47, "Failed in IO Write peer: ", v14);
      if ( &v55 != (__int128 *)v16 )
      {
        std::string::_Tidy_deallocate(&v55);
        v55 = *(_OWORD *)v16;
        si128 = *(__m128i *)(v16 + 16);
        *(_QWORD *)(v16 + 16) = 0;
        *(_QWORD *)(v16 + 24) = 15;
        *(_BYTE *)v16 = 0;
      }
      std::string::_Tidy_deallocate(v47);
      if ( (v15 & 4) != 0 )
      {
        LOBYTE(v15) = v15 & 0xFB;
        std::string::_Tidy_deallocate(&v43);
      }
      if ( (v15 & 2) != 0 )
        std::string::_Tidy_deallocate(v49);
    }
    v17 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD *))*a1 + 13))(a1, v48);
    v18 = std::operator+<char>(&v43, &v55, ", local: ");
    v19 = std::operator+<char>(v49, v18, a1 + 13);
    v20 = std::operator+<char>(v47, v19, ", className");
    LOBYTE(v21) = v42;
    std::string::string(&v53, v21, v20, v17);
    std::string::_Tidy_deallocate(&v55);
    v55 = v53;
    si128 = v54;
    v54 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v53) = 0;
    std::string::_Tidy_deallocate(&v53);
    std::string::_Tidy_deallocate(v47);
    std::string::_Tidy_deallocate(v49);
    std::string::_Tidy_deallocate(&v43);
    std::string::_Tidy_deallocate(v48);
    v22 = (*((__int64 (__fastcall **)(HANDLE *, _BYTE *))*a1 + 13))(a1, v47);
    v43 = 0;
    v44 = 0;
    std::string::_Construct<1,char const *>(&v43, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp", 54);
    v24 = Microsoft::Basix::WindowsCategory(v23);
    LODWORD(v53) = v7;
    *((_QWORD *)&v53 + 1) = v24;
    v25 = Microsoft::Basix::SystemException::SystemException(
            (unsigned int)pExceptionObject,
            (unsigned int)&v53,
            (unsigned int)&v55,
            (unsigned int)&v43,
            616,
            v22);
    v26 = (const void *)std::make_exception_ptr<Microsoft::Basix::SystemException>(v48, v25);
    __ExceptionPtrAssign(p_hEvent + 104, v26);
    __ExceptionPtrDestroy(v48);
    std::string::_Tidy_deallocate(&v43);
    std::string::_Tidy_deallocate(v47);
    std::string::_Tidy_deallocate(&v55);
LABEL_32:
    *((_QWORD *)p_hEvent + 15) = NumberOfBytesTransferred;
    if ( *((_BYTE *)a1 + 2496) )
    {
      v46 = p_hEvent;
      Microsoft::Basix::Instrumentation::DequeueReadRequest::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        a1 + 328,
        a1 + 313,
        &v46);
    }
    *a2 = p_hEvent;
    return a2;
  }
  v53 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v53);
  if ( (_QWORD)v53 && *(_BYTE *)(v53 + 128) )
  {
    v29 = Overlapped;
    v30 = NumberOfBytesTransferred;
    v43 = 0;
    v44 = 0;
    std::string::_Construct<1,char const *>(
      &v43,
      "GetQueuedCompletionStatus() error %d: bytesTransfered(%d), lpOverlapped=%p",
      74,
      v28,
      dwMilliseconds);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned long,unsigned long,_OVERLAPPED *>(
      (unsigned int)&v53,
      (unsigned int)"NANO_DCT",
      (unsigned int)&v43,
      v7,
      v30,
      (__int64)v29);
    std::string::_Tidy_deallocate(&v43);
  }
  v31 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
  if ( *((_QWORD *)&v53 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v53 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  *a2 = 0;
  if ( p_hEvent )
    (**(void (__fastcall ***)(char *, __int64))p_hEvent)(p_hEvent, 1);
  return a2;
}

```

## disassembly

```asm
0x180153ac0  mov     [rsp-8+arg_10], rbx
0x180153ac5  push    rbp
0x180153ac6  push    rsi
0x180153ac7  push    rdi
0x180153ac8  push    r12
0x180153aca  push    r13
0x180153acc  push    r14
0x180153ace  push    r15
0x180153ad0  lea     rbp, [rsp-0C0h]
0x180153ad8  mov     eax, 1C0h
0x180153add  call    _alloca_probe
0x180153ae2  sub     rsp, rax
0x180153ae5  mov     rax, cs:__security_cookie
0x180153aec  xor     rax, rsp
0x180153aef  mov     [rbp+0F0h+var_38], rax
0x180153af6  mov     r15, rdx
0x180153af9  mov     r12, rcx
0x180153afc  mov     [rsp+1F0h+var_190], rdx
0x180153b01  xor     r13d, r13d
0x180153b04  mov     [rsp+1F0h+var_198], r13d
0x180153b09  mov     [rbp+0F0h+CompletionKey], r13
0x180153b10  mov     [rbp+0F0h+Overlapped], r13
0x180153b14  mov     [rbp+0F0h+NumberOfBytesTransferred], r13d
0x180153b18  mov     [rsp+1F0h+dwMilliseconds], 0FAh; dwMilliseconds
0x180153b20  lea     r9, [rbp+0F0h+Overlapped]; lpOverlapped
0x180153b24  lea     r8, [rbp+0F0h+CompletionKey]; lpCompletionKey
0x180153b2b  lea     rdx, [rbp+0F0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180153b2f  mov     rcx, [rcx+0F80h]; CompletionPort
0x180153b36  call    cs:__imp_GetQueuedCompletionStatus
0x180153b3c  mov     ebx, eax
0x180153b3e  mov     rsi, [rbp+0F0h+Overlapped]
0x180153b42  test    rsi, rsi
0x180153b45  jz      short loc_180153B4D
0x180153b47  add     rsi, 0FFFFFFFFFFFFFFF8h
0x180153b4b  jmp     short loc_180153B50
0x180153b4d  mov     rsi, r13
0x180153b50  mov     [rsp+1F0h+var_190], rsi
0x180153b55  lea     rcx, [r12+10h]
0x180153b5a  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180153b5f  mov     edx, [rax]
0x180153b61  nop
0x180153b62  cmp     edx, 22h ; '"'
0x180153b65  jnz     short loc_180153B7E
0x180153b67  mov     [r15], r13
0x180153b6a  test    rsi, rsi
0x180153b6d  jz      loc_180153F8C
0x180153b73  mov     rax, [rsi]
0x180153b76  mov     rax, [rax]
0x180153b79  jmp     loc_18015408C
0x180153b7e  test    ebx, ebx
0x180153b80  jnz     loc_180153F59
0x180153b86  call    cs:__imp_GetLastError
0x180153b8c  mov     r14d, eax
0x180153b8f  cmp     eax, 102h
0x180153b94  jz      loc_180153FB9
0x180153b9a  cmp     eax, 6F8h
0x180153b9f  jz      loc_180153FB9
0x180153ba5  cmp     eax, 0EAh
0x180153baa  jz      loc_180153FB9
0x180153bb0  lea     rcx, [rbp+0F0h+var_80]; this
0x180153bb4  cmp     [rbp+0F0h+Overlapped], r13
0x180153bb8  jz      loc_18015409F
0x180153bbe  xorps   xmm0, xmm0
0x180153bc1  movups  [rbp+0F0h+var_80], xmm0
0x180153bc5  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180153bca  nop
0x180153bcb  mov     rax, qword ptr [rbp+0F0h+var_80]
0x180153bcf  test    rax, rax
0x180153bd2  jz      loc_180153C5C
0x180153bd8  cmp     [rax+80h], r13b
0x180153bdf  jz      short loc_180153C5C
0x180153be1  lea     rax, [rsp+1F0h+var_188]
0x180153be6  mov     [rbp+0F0h+var_168], rax
0x180153bea  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180153bef  mov     rcx, rax
0x180153bf2  mov     rax, [rax]
0x180153bf5  mov     r8d, r14d
0x180153bf8  lea     rdx, [rsp+1F0h+var_188]
0x180153bfd  mov     rax, [rax+10h]
0x180153c01  call    cs:__guard_dispatch_icall_fptr
0x180153c07  mov     rbx, rax
0x180153c0a  xorps   xmm0, xmm0
0x180153c0d  movups  [rsp+1F0h+var_1B8], xmm0
0x180153c12  xorps   xmm1, xmm1
0x180153c15  movdqu  [rsp+1F0h+var_1A8], xmm1
0x180153c1b  mov     r8d, 29h ; ')'
0x180153c21  lea     rdx, aIoRequestFaile; "IO request failed with error code %d (%"...
0x180153c28  lea     rcx, [rsp+1F0h+var_1B8]
0x180153c2d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180153c32  nop
0x180153c33  mov     qword ptr [rsp+1F0h+dwMilliseconds], rbx
0x180153c38  mov     r9d, r14d
0x180153c3b  lea     r8, [rsp+1F0h+var_1B8]
0x180153c40  lea     rdx, aNanoDct; "NANO_DCT"
0x180153c47  lea     rcx, [rbp+0F0h+var_80]
0x180153c4b  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@IV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IV65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,std::string)
0x180153c50  nop
0x180153c51  lea     rcx, [rsp+1F0h+var_1B8]
0x180153c56  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153c5b  nop
0x180153c5c  mov     rbx, qword ptr [rbp+0F0h+var_80+8]
0x180153c60  test    rbx, rbx
0x180153c63  jz      short loc_180153C9D
0x180153c65  or      edi, 0FFFFFFFFh
0x180153c68  mov     eax, edi
0x180153c6a  lock xadd [rbx+8], eax
0x180153c6f  add     eax, edi
0x180153c71  jnz     short loc_180153C9D
0x180153c73  mov     rax, [rbx]
0x180153c76  mov     rcx, rbx
0x180153c79  mov     rax, [rax]
0x180153c7c  call    cs:__guard_dispatch_icall_fptr
0x180153c82  mov     eax, edi
0x180153c84  lock xadd [rbx+0Ch], eax
0x180153c89  add     eax, edi
0x180153c8b  jnz     short loc_180153C9D
0x180153c8d  mov     rax, [rbx]
0x180153c90  mov     rcx, rbx
0x180153c93  mov     rax, [rax+8]
0x180153c97  call    cs:__guard_dispatch_icall_fptr
0x180153c9d  xorps   xmm0, xmm0
0x180153ca0  movups  [rbp+0F0h+var_60], xmm0
0x180153ca7  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180153caf  movdqu  [rbp+0F0h+var_50], xmm1
0x180153cb7  mov     byte ptr [rbp+0F0h+var_60], r13b
0x180153cbe  mov     ecx, [rsi+11Ch]
0x180153cc4  sub     ecx, 1
0x180153cc7  jz      loc_180153DAC
0x180153ccd  cmp     ecx, 1
0x180153cd0  jnz     loc_180153DBF
0x180153cd6  mov     rcx, [rsi+80h]
0x180153cdd  test    rcx, rcx
0x180153ce0  jz      short loc_180153CFB
0x180153ce2  mov     rax, [rcx]
0x180153ce5  lea     rdx, [rbp+0F0h+var_148]
0x180153ce9  mov     rax, [rax+8]
0x180153ced  call    cs:__guard_dispatch_icall_fptr
0x180153cf3  nop
0x180153cf4  mov     ebx, 2
0x180153cf9  jmp     short loc_180153D27
0x180153cfb  movups  [rsp+1F0h+var_1B8], xmm0
0x180153d00  xorps   xmm1, xmm1
0x180153d03  movdqu  [rsp+1F0h+var_1A8], xmm1
0x180153d09  xor     r8d, r8d
0x180153d0c  lea     rdx, Str1
0x180153d13  lea     rcx, [rsp+1F0h+var_1B8]
0x180153d18  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180153d1d  lea     rax, [rsp+1F0h+var_1B8]
0x180153d22  mov     ebx, 4
0x180153d27  mov     [rsp+1F0h+var_198], ebx
0x180153d2b  mov     r8, rax
0x180153d2e  lea     rdx, aFailedInIoWrit_0; "Failed in IO Write peer: "
0x180153d35  lea     rcx, [rsp+1F0h+var_188]
0x180153d3a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180153d3f  mov     rdi, rax
0x180153d42  lea     rax, [rbp+0F0h+var_60]
0x180153d49  cmp     rax, rdi
0x180153d4c  jz      short loc_180153D7E
0x180153d4e  lea     rcx, [rbp+0F0h+var_60]
0x180153d55  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153d5a  movups  xmm0, xmmword ptr [rdi]
0x180153d5d  movups  [rbp+0F0h+var_60], xmm0
0x180153d64  movups  xmm1, xmmword ptr [rdi+10h]
0x180153d68  movups  [rbp+0F0h+var_50], xmm1
0x180153d6f  mov     [rdi+10h], r13
0x180153d73  mov     qword ptr [rdi+18h], 0Fh
0x180153d7b  mov     [rdi], r13b
0x180153d7e  lea     rcx, [rsp+1F0h+var_188]
0x180153d83  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153d88  nop
0x180153d89  test    bl, 4
0x180153d8c  jz      short loc_180153D9C
0x180153d8e  and     ebx, 0FFFFFFFBh
0x180153d91  lea     rcx, [rsp+1F0h+var_1B8]
0x180153d96  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153d9b  nop
0x180153d9c  test    bl, 2
0x180153d9f  jz      short loc_180153DBF
0x180153da1  lea     rcx, [rbp+0F0h+var_148]
0x180153da5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153daa  jmp     short loc_180153DBF
0x180153dac  lea     rdx, aFailedInIoRead; "Failed in IO Read "
0x180153db3  lea     rcx, [rbp+0F0h+var_60]
0x180153dba  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180153dbf  mov     rax, [r12]
0x180153dc3  lea     rdx, [rbp+0F0h+var_168]
0x180153dc7  mov     rcx, r12
0x180153dca  mov     rax, [rax+68h]
0x180153dce  call    cs:__guard_dispatch_icall_fptr
0x180153dd4  mov     rbx, rax
0x180153dd7  lea     r8, aLocal_0; ", local: "
0x180153dde  lea     rdx, [rbp+0F0h+var_60]
0x180153de5  lea     rcx, [rsp+1F0h+var_1B8]
0x180153dea  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@AEBV10@QEBD@Z; std::operator+<char>(std::string const &,char const * const)
0x180153def  nop
0x180153df0  lea     r8, [r12+68h]
0x180153df5  mov     rdx, rax
0x180153df8  lea     rcx, [rbp+0F0h+var_148]
0x180153dfc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x180153e01  nop
0x180153e02  lea     r8, aClassname; ", className"
0x180153e09  mov     rdx, rax
0x180153e0c  lea     rcx, [rsp+1F0h+var_188]
0x180153e11  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180153e16  nop
0x180153e17  mov     r9, rbx
0x180153e1a  mov     r8, rax
0x180153e1d  mov     dl, [rsp+1F0h+var_1C0]
0x180153e21  lea     rcx, [rbp+0F0h+var_80]
0x180153e25  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180153e2a  lea     rcx, [rbp+0F0h+var_60]
0x180153e31  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153e36  movups  xmm0, [rbp+0F0h+var_80]
0x180153e3a  movups  [rbp+0F0h+var_60], xmm0
0x180153e41  movups  xmm1, [rbp+0F0h+var_70]
0x180153e48  movups  [rbp+0F0h+var_50], xmm1
0x180153e4f  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180153e57  movdqu  [rbp+0F0h+var_70], xmm0
0x180153e5f  mov     byte ptr [rbp+0F0h+var_80], r13b
0x180153e63  lea     rcx, [rbp+0F0h+var_80]
0x180153e67  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153e6c  nop
0x180153e6d  lea     rcx, [rsp+1F0h+var_188]
0x180153e72  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153e77  nop
0x180153e78  lea     rcx, [rbp+0F0h+var_148]
0x180153e7c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153e81  nop
0x180153e82  lea     rcx, [rsp+1F0h+var_1B8]
0x180153e87  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153e8c  nop
0x180153e8d  lea     rcx, [rbp+0F0h+var_168]
0x180153e91  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153e96  mov     rax, [r12]
0x180153e9a  lea     rdx, [rsp+1F0h+var_188]
0x180153e9f  mov     rcx, r12
0x180153ea2  mov     rax, [rax+68h]
0x180153ea6  call    cs:__guard_dispatch_icall_fptr
0x180153eac  mov     rbx, rax
0x180153eaf  xorps   xmm0, xmm0
0x180153eb2  movups  [rsp+1F0h+var_1B8], xmm0
0x180153eb7  xorps   xmm1, xmm1
0x180153eba  movdqu  [rsp+1F0h+var_1A8], xmm1
0x180153ec0  mov     r8d, 36h ; '6'
0x180153ec6  lea     rdx, aCW1SSrcLibbasi_63; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180153ecd  lea     rcx, [rsp+1F0h+var_1B8]
0x180153ed2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180153ed7  nop
0x180153ed8  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180153edd  mov     dword ptr [rbp+0F0h+var_80], r14d
0x180153ee1  mov     qword ptr [rbp+0F0h+var_80+8], rax
0x180153ee5  movaps  xmm0, [rbp+0F0h+var_80]
0x180153ee9  movdqa  [rbp+0F0h+var_80], xmm0
0x180153eee  mov     [rsp+1F0h+var_1C8], rbx
0x180153ef3  mov     qword ptr [rsp+1F0h+dwMilliseconds], 268h
0x180153efc  lea     r9, [rsp+1F0h+var_1B8]
0x180153f01  lea     r8, [rbp+0F0h+var_60]
0x180153f08  lea     rdx, [rbp+0F0h+var_80]
0x180153f0c  lea     rcx, [rbp+0F0h+pExceptionObject]
0x180153f10  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180153f15  mov     rdx, rax
0x180153f18  lea     rcx, [rbp+0F0h+var_168]
0x180153f1c  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x180153f21  lea     rcx, [rsi+68h]; void *
0x180153f25  mov     rdx, rax; void *
0x180153f28  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180153f2d  lea     rcx, [rbp+0F0h+var_168]; void *
0x180153f31  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180153f36  nop
0x180153f37  lea     rcx, [rsp+1F0h+var_1B8]
0x180153f3c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153f41  nop
0x180153f42  lea     rcx, [rsp+1F0h+var_188]
0x180153f47  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153f4c  nop
0x180153f4d  lea     rcx, [rbp+0F0h+var_60]
0x180153f54  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153f59  mov     eax, [rbp+0F0h+NumberOfBytesTransferred]
0x180153f5c  mov     [rsi+78h], rax
0x180153f60  cmp     [r12+9C0h], r13b
0x180153f68  jz      short loc_180153F89
0x180153f6a  mov     [rsp+1F0h+var_190], rsi
0x180153f6f  lea     rdx, [r12+9C8h]
0x180153f77  lea     rcx, [r12+0A40h]
0x180153f7f  lea     r8, [rsp+1F0h+var_190]
0x180153f84  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@DequeueReadRequest@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K@Z; Microsoft::Basix::Instrumentation::DequeueReadRequest::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &)
0x180153f89  mov     [r15], rsi
0x180153f8c  mov     rax, r15
0x180153f8f  mov     rcx, [rbp+0F0h+var_38]
0x180153f96  xor     rcx, rsp; StackCookie
0x180153f99  call    __security_check_cookie
0x180153f9e  mov     rbx, [rsp+1F0h+arg_10]
0x180153fa6  add     rsp, 1C0h
0x180153fad  pop     r15
0x180153faf  pop     r14
0x180153fb1  pop     r13
0x180153fb3  pop     r12
0x180153fb5  pop     rdi
0x180153fb6  pop     rsi
0x180153fb7  pop     rbp
  ... truncated ...
```
