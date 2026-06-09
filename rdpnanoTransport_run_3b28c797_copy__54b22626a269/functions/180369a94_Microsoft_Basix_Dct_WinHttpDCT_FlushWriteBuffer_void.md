# Microsoft::Basix::Dct::WinHttpDCT::FlushWriteBuffer(void)

- ea: `0x180369a94`
- end: `0x180369e3d`
- name: `?FlushWriteBuffer@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXXZ`
- size: `937`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinHttpDCT *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18036a740`
- `0x18036be0c`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18002b3c8`
- `0x18004e1dc`
- `0x1800de3ec`
- `0x18011963c`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180369978`
- `0x180369a94`
- `0x180375c40`

## import_xrefs

- `WINHTTP!WinHttpWebSocketSend` at `0x180369bcb`
- `WINHTTP!WinHttpWebSocketSend` at `0x180369bcb`

## string_xrefs

- `0x180369c36`: `Queuing write for websocket failed.`
- `0x180369d27`: `Microsoft::Basix::Dct::WinHttpDCT::FlushWriteBuffer`
- `0x180369d15`: `QueueWrite (WinHttp) error: 0x%x\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Microsoft::Basix::Dct::WinHttpDCT::FlushWriteBuffer(Microsoft::Basix::Dct::WinHttpDCT *this)
{
  char *v2; // rdi
  _QWORD *v3; // rcx
  volatile signed __int32 *v4; // r14
  __int64 v6; // rax
  __int64 v7; // rbx
  signed int v8; // r15d
  void (__fastcall *v9)(Microsoft::Basix::Dct::WinHttpDCT *, __int64); // rdi
  __int64 v10; // rbx
  Microsoft::Basix *v11; // rcx
  const struct std::error_category *v12; // rax
  unsigned int v13; // r12d
  __int64 v14; // rax
  __int64 v15; // rax
  const char *v16; // r9
  volatile signed __int32 *v17; // rbx
  int v18; // [rsp+20h] [rbp-E0h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+60h] [rbp-A0h]
  _OWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v25; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v26; // [rsp+150h] [rbp+50h] BYREF

  v2 = (char *)this + 1208;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinHttpDCT *)((char *)this + 1208)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v3 = (_QWORD *)*((_QWORD *)this + 161);
  if ( (!v3 || v3[1] == *v3) && *((_QWORD *)this + 167) )
  {
    std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(
      (char *)this + 1288,
      *(_QWORD *)(*((_QWORD *)this + 164) + 8 * (*((_QWORD *)this + 166) & (*((_QWORD *)this + 165) - 1LL))));
    std::shared_ptr<Microsoft::Basix::Instrumentation::DelayedTraceManager::SessionDelayTraceCircularBuffer>::`scalar deleting destructor'(
      *(_QWORD *)(*((_QWORD *)this + 164) + 8 * (*((_QWORD *)this + 166) & (*((_QWORD *)this + 165) - 1LL))),
      0);
    if ( (*((_QWORD *)this + 167))-- == 1 )
      *((_QWORD *)this + 166) = 0;
    else
      ++*((_QWORD *)this + 166);
    v6 = *((_QWORD *)this + 162);
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
    v7 = *((_QWORD *)this + 161);
    v4 = (volatile signed __int32 *)*((_QWORD *)this + 162);
    Mtx_unlock((_Mtx_t)v2);
    v8 = WinHttpWebSocketSend(
           **((HINTERNET **)this + 146),
           WINHTTP_WEB_SOCKET_BINARY_MESSAGE_BUFFER_TYPE,
           *(PVOID *)v7,
           *(_DWORD *)(v7 + 8) - *(_DWORD *)v7);
    if ( v8 )
    {
      v9 = *(void (__fastcall **)(Microsoft::Basix::Dct::WinHttpDCT *, __int64))(*(_QWORD *)this + 120LL);
      v10 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinHttpDCT *, _BYTE *))(*(_QWORD *)this + 104LL))(
              this,
              v24);
      v20 = 0;
      v21 = 0;
      std::string::_Construct<1,char const *>(&v20, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp", 50);
      memset(v22, 0, sizeof(v22));
      std::string::_Construct<1,char const *>(v22, "Queuing write for websocket failed.", 35);
      v12 = Microsoft::Basix::WindowsCategory(v11);
      v13 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v13 = v8;
      LODWORD(v26) = v13;
      *((_QWORD *)&v26 + 1) = v12;
      v14 = Microsoft::Basix::SystemException::SystemException(
              (unsigned int)&v25,
              (unsigned int)&v26,
              (unsigned int)v22,
              (unsigned int)&v20,
              114,
              v10);
      v15 = std::make_exception_ptr<Microsoft::Basix::SystemException>(v23, v14);
      v9(this, v15);
      __ExceptionPtrDestroy(v23);
      std::string::_Tidy_deallocate(v22);
      std::string::_Tidy_deallocate(&v20);
      std::string::_Tidy_deallocate(v24);
      v26 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v26);
      if ( (_QWORD)v26 && *(_BYTE *)(v26 + 128) )
      {
        v20 = 0;
        v21 = 0;
        std::string::_Construct<1,char const *>(
          &v20,
          "QueueWrite (WinHttp) error: 0x%x\n    %s(%d): %s()",
          49,
          v16,
          v18,
          v19);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(
          (unsigned int)&v26,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v20,
          v13,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp",
          115,
          (__int64)"Microsoft::Basix::Dct::WinHttpDCT::FlushWriteBuffer");
        std::string::_Tidy_deallocate(&v20);
      }
      v17 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
      if ( *((_QWORD *)&v26 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(this, 1);
    }
  }
  else
  {
    Mtx_unlock((_Mtx_t)v2);
    v4 = 0;
  }
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x180369a94  mov     [rsp-8+arg_8], rbx
0x180369a99  mov     [rsp-8+arg_10], rsi
0x180369a9e  push    rbp
0x180369a9f  push    rdi
0x180369aa0  push    r12
0x180369aa2  push    r14
0x180369aa4  push    r15
0x180369aa6  lea     rbp, [rsp-70h]
0x180369aab  mov     eax, 170h
0x180369ab0  call    _alloca_probe
0x180369ab5  sub     rsp, rax
0x180369ab8  mov     rax, cs:__security_cookie
0x180369abf  xor     rax, rsp
0x180369ac2  mov     [rbp+90h+var_30], rax
0x180369ac6  mov     rsi, rcx
0x180369ac9  xorps   xmm1, xmm1
0x180369acc  movdqu  [rsp+190h+var_150], xmm1
0x180369ad2  lea     rdi, [rcx+4B8h]
0x180369ad9  mov     rcx, rdi; _Mtx_t
0x180369adc  call    _Mtx_lock
0x180369ae1  test    eax, eax
0x180369ae3  jnz     loc_180369E32
0x180369ae9  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180369af0  jz      loc_180369E20
0x180369af6  lea     r14, [rsi+508h]
0x180369afd  mov     rcx, [r14]
0x180369b00  test    rcx, rcx
0x180369b03  jz      short loc_180369B0E
0x180369b05  mov     rax, [rcx+8]
0x180369b09  cmp     rax, [rcx]
0x180369b0c  jnz     short loc_180369B18
0x180369b0e  cmp     qword ptr [rsi+538h], 0
0x180369b16  jnz     short loc_180369B2A
0x180369b18  mov     rcx, rdi; _Mtx_t
0x180369b1b  call    _Mtx_unlock
0x180369b20  mov     r14, qword ptr [rsp+190h+var_150+8]
0x180369b25  jmp     loc_180369DB8
0x180369b2a  mov     rax, [rsi+528h]
0x180369b31  dec     rax
0x180369b34  and     rax, [rsi+530h]
0x180369b3b  mov     rdx, [rsi+520h]
0x180369b42  mov     rdx, [rdx+rax*8]
0x180369b46  mov     rcx, r14
0x180369b49  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x180369b4e  mov     rax, [rsi+528h]
0x180369b55  dec     rax
0x180369b58  and     rax, [rsi+530h]
0x180369b5f  mov     rcx, [rsi+520h]
0x180369b66  xor     edx, edx
0x180369b68  mov     rcx, [rcx+rax*8]
0x180369b6c  call    ??_G?$shared_ptr@VSessionDelayTraceCircularBuffer@DelayedTraceManager@Instrumentation@Basix@Microsoft@@@std@@QEAAPEAXI@Z; std::shared_ptr<Microsoft::Basix::Instrumentation::DelayedTraceManager::SessionDelayTraceCircularBuffer>::`scalar deleting destructor'(uint)
0x180369b71  sub     qword ptr [rsi+538h], 1
0x180369b79  jnz     short loc_180369B88
0x180369b7b  mov     qword ptr [rsi+530h], 0
0x180369b86  jmp     short loc_180369B8F
0x180369b88  inc     qword ptr [rsi+530h]
0x180369b8f  mov     rax, [r14+8]
0x180369b93  test    rax, rax
0x180369b96  jz      short loc_180369B9C
0x180369b98  lock inc dword ptr [rax+8]
0x180369b9c  mov     rbx, [r14]
0x180369b9f  mov     qword ptr [rsp+190h+var_150], rbx
0x180369ba4  mov     r14, [r14+8]
0x180369ba8  mov     qword ptr [rsp+190h+var_150+8], r14
0x180369bad  mov     rcx, rdi; _Mtx_t
0x180369bb0  call    _Mtx_unlock
0x180369bb5  mov     r9d, [rbx+8]
0x180369bb9  sub     r9d, [rbx]; dwBufferLength
0x180369bbc  mov     rcx, [rsi+490h]
0x180369bc3  mov     r8, [rbx]; pvBuffer
0x180369bc6  xor     edx, edx; eBufferType
0x180369bc8  mov     rcx, [rcx]; hWebSocket
0x180369bcb  call    cs:__imp_WinHttpWebSocketSend
0x180369bd1  mov     r15d, eax
0x180369bd4  test    eax, eax
0x180369bd6  jz      loc_180369DB8
0x180369bdc  mov     rcx, [rsi]
0x180369bdf  mov     rdi, [rcx+78h]
0x180369be3  mov     rax, [rcx+68h]
0x180369be7  lea     rdx, [rbp+90h+var_F0]
0x180369beb  mov     rcx, rsi
0x180369bee  call    cs:__guard_dispatch_icall_fptr
0x180369bf4  mov     rbx, rax
0x180369bf7  xorps   xmm0, xmm0
0x180369bfa  movups  [rsp+190h+var_140], xmm0
0x180369bff  xorps   xmm1, xmm1
0x180369c02  movdqu  [rsp+190h+var_130], xmm1
0x180369c08  mov     r8d, 32h ; '2'
0x180369c0e  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180369c15  lea     rcx, [rsp+190h+var_140]
0x180369c1a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180369c1f  nop
0x180369c20  xorps   xmm0, xmm0
0x180369c23  movups  [rsp+190h+var_120], xmm0
0x180369c28  xorps   xmm1, xmm1
0x180369c2b  movdqu  [rbp+90h+var_110], xmm1
0x180369c30  mov     r8d, 23h ; '#'
0x180369c36  lea     rdx, aQueuingWriteFo; "Queuing write for websocket failed."
0x180369c3d  lea     rcx, [rsp+190h+var_120]
0x180369c42  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180369c47  nop
0x180369c48  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180369c4d  movzx   r12d, r15w
0x180369c51  or      r12d, 80070000h
0x180369c58  test    r15d, r15d
0x180369c5b  cmovle  r12d, r15d
0x180369c5f  mov     dword ptr [rbp+90h+var_40], r12d
0x180369c63  mov     qword ptr [rbp+90h+var_40+8], rax
0x180369c67  movaps  xmm0, [rbp+90h+var_40]
0x180369c6b  movdqa  [rbp+90h+var_40], xmm0
0x180369c70  mov     [rsp+190h+var_168], rbx
0x180369c75  mov     [rsp+190h+var_170], 72h ; 'r'
0x180369c7e  lea     r9, [rsp+190h+var_140]
0x180369c83  lea     r8, [rsp+190h+var_120]
0x180369c88  lea     rdx, [rbp+90h+var_40]
0x180369c8c  lea     rcx, [rbp+90h+var_D0]
0x180369c90  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180369c95  mov     rdx, rax
0x180369c98  lea     rcx, [rbp+90h+var_100]
0x180369c9c  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x180369ca1  nop
0x180369ca2  mov     rdx, rax
0x180369ca5  mov     rcx, rsi
0x180369ca8  mov     rax, rdi
0x180369cab  call    cs:__guard_dispatch_icall_fptr
0x180369cb1  nop
0x180369cb2  lea     rcx, [rbp+90h+var_100]; void *
0x180369cb6  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180369cbb  nop
0x180369cbc  lea     rcx, [rsp+190h+var_120]
0x180369cc1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180369cc6  nop
0x180369cc7  lea     rcx, [rsp+190h+var_140]
0x180369ccc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180369cd1  nop
0x180369cd2  lea     rcx, [rbp+90h+var_F0]
0x180369cd6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180369cdb  xorps   xmm0, xmm0
0x180369cde  movups  [rbp+90h+var_40], xmm0
0x180369ce2  lea     rcx, [rbp+90h+var_40]
0x180369ce6  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180369ceb  nop
0x180369cec  mov     rax, qword ptr [rbp+90h+var_40]
0x180369cf0  test    rax, rax
0x180369cf3  jz      short loc_180369D6B
0x180369cf5  cmp     byte ptr [rax+80h], 0
0x180369cfc  jz      short loc_180369D6B
0x180369cfe  xorps   xmm0, xmm0
0x180369d01  movups  [rsp+190h+var_140], xmm0
0x180369d06  xorps   xmm1, xmm1
0x180369d09  movdqu  [rsp+190h+var_130], xmm1
0x180369d0f  mov     r8d, 31h ; '1'
0x180369d15  lea     rdx, aQueuewriteWinh; "QueueWrite (WinHttp) error: 0x%x\n    %"...
0x180369d1c  lea     rcx, [rsp+190h+var_140]
0x180369d21  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180369d26  nop
0x180369d27  lea     rax, aMicrosoftBasix_196; "Microsoft::Basix::Dct::WinHttpDCT::Flus"...
0x180369d2e  mov     [rsp+190h+var_160], rax
0x180369d33  mov     dword ptr [rsp+190h+var_168], 73h ; 's'
0x180369d3b  lea     rax, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180369d42  mov     [rsp+190h+var_170], rax
0x180369d47  mov     r9d, r12d
0x180369d4a  lea     r8, [rsp+190h+var_140]
0x180369d4f  lea     rdx, aNanoDct; "NANO_DCT"
0x180369d56  lea     rcx, [rbp+90h+var_40]
0x180369d5a  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@JPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@J1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,long,char const *,int,char const *)
0x180369d5f  nop
0x180369d60  lea     rcx, [rsp+190h+var_140]
0x180369d65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180369d6a  nop
0x180369d6b  mov     rbx, qword ptr [rbp+90h+var_40+8]
0x180369d6f  test    rbx, rbx
0x180369d72  jz      short loc_180369DAD
0x180369d74  or      eax, 0FFFFFFFFh
0x180369d77  lock xadd [rbx+8], eax
0x180369d7c  cmp     eax, 1
0x180369d7f  jnz     short loc_180369DAD
0x180369d81  mov     rax, [rbx]
0x180369d84  mov     rcx, rbx
0x180369d87  mov     rax, [rax]
0x180369d8a  call    cs:__guard_dispatch_icall_fptr
0x180369d90  or      eax, 0FFFFFFFFh
0x180369d93  lock xadd [rbx+0Ch], eax
0x180369d98  cmp     eax, 1
0x180369d9b  jnz     short loc_180369DAD
0x180369d9d  mov     rax, [rbx]
0x180369da0  mov     rcx, rbx
0x180369da3  mov     rax, [rax+8]
0x180369da7  call    cs:__guard_dispatch_icall_fptr
0x180369dad  mov     dl, 1; bool
0x180369daf  mov     rcx, rsi; this
0x180369db2  call    ?FireOnClosedInternal@WinHttpDCT@Dct@Basix@Microsoft@@IEAAX_N@Z; Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(bool)
0x180369db7  nop
0x180369db8  test    r14, r14
0x180369dbb  jz      short loc_180369DF8
0x180369dbd  or      eax, 0FFFFFFFFh
0x180369dc0  lock xadd [r14+8], eax
0x180369dc6  cmp     eax, 1
0x180369dc9  jnz     short loc_180369DF8
0x180369dcb  mov     rax, [r14]
0x180369dce  mov     rcx, r14
0x180369dd1  mov     rax, [rax]
0x180369dd4  call    cs:__guard_dispatch_icall_fptr
0x180369dda  or      eax, 0FFFFFFFFh
0x180369ddd  lock xadd [r14+0Ch], eax
0x180369de3  cmp     eax, 1
0x180369de6  jnz     short loc_180369DF8
0x180369de8  mov     rax, [r14]
0x180369deb  mov     rcx, r14
0x180369dee  mov     rax, [rax+8]
0x180369df2  call    cs:__guard_dispatch_icall_fptr
0x180369df8  mov     rcx, [rbp+90h+var_30]
0x180369dfc  xor     rcx, rsp; StackCookie
0x180369dff  call    __security_check_cookie
0x180369e04  lea     r11, [rsp+190h+var_20]
0x180369e0c  mov     rbx, [r11+38h]
0x180369e10  mov     rsi, [r11+40h]
0x180369e14  mov     rsp, r11
0x180369e17  pop     r15
0x180369e19  pop     r14
0x180369e1b  pop     r12
0x180369e1d  pop     rdi
0x180369e1e  pop     rbp
0x180369e1f  retn
0x180369e20  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180369e27  mov     ecx, 6; int
0x180369e2c  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180369e32  mov     ecx, 5; int
0x180369e37  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
