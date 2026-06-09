# Microsoft::Basix::Dct::WinHttpDCT::QueueRead(void)

- ea: `0x18036c55c`
- end: `0x18036c8d6`
- name: `?QueueRead@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXXZ`
- size: `890`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinHttpDCT *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18036ad88`
- `0x18036b240`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018d1c`
- `0x180018ea4`
- `0x1800bb210`
- `0x1800de3ec`
- `0x180117b2c`
- `0x18011963c`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180369978`
- `0x180369e40`
- `0x18036c55c`
- `0x180375c40`

## import_xrefs

- `WINHTTP!WinHttpWebSocketReceive` at `0x18036c6c4`
- `WINHTTP!WinHttpWebSocketReceive` at `0x18036c6c4`

## string_xrefs

- `0x18036c5ed`: `Read queued - : %d`
- `0x18036c72e`: `Queuing read for websocket failed.`
- `0x18036c81e`: `Microsoft::Basix::Dct::WinHttpDCT::QueueRead`
- `0x18036c80c`: `QueueRead (WinHttp) error: 0x%x\n    %s(%d): %s()`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::WinHttpDCT::QueueRead(Microsoft::Basix::Dct::WinHttpDCT *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  volatile signed __int32 *v4; // rbx
  __int64 v5; // rax
  DWORD v6; // edi
  Microsoft::Basix::Containers::FlexIBuffer *v7; // rbx
  __int64 v8; // rax
  unsigned __int8 *PointerRel; // rax
  signed int v10; // r14d
  void (__fastcall *v11)(Microsoft::Basix::Dct::WinHttpDCT *, __int64); // rdi
  __int64 v12; // rbx
  Microsoft::Basix *v13; // rcx
  const struct std::error_category *v14; // rax
  unsigned int v15; // r15d
  __int64 v16; // rax
  __int64 v17; // rax
  const char *v18; // r9
  volatile signed __int32 *v19; // rbx
  int peBufferType; // [rsp+20h] [rbp-E0h]
  const char *v21; // [rsp+28h] [rbp-D8h]
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h]
  _OWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v25[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v27; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v28; // [rsp+150h] [rbp+50h] BYREF

  if ( *((_QWORD *)this + 146) )
  {
    v28 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v28);
    if ( (_QWORD)v28 && *(_BYTE *)(v28 + 128) )
    {
      v2 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*((_QWORD *)this + 149));
      v3 = *(_QWORD *)(v2 + 32) - *(_QWORD *)(v2 + 24);
      memset(v24, 0, sizeof(v24));
      std::string::_Construct<1,char const *>(v24, "Read queued - : %d", 18);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64>(
        &v28,
        "NANO_DCT",
        v24,
        v3);
      std::string::_Tidy_deallocate(v24);
    }
    v4 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
    if ( *((_QWORD *)&v28 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    v5 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*((_QWORD *)this + 149));
    v6 = *(_DWORD *)(v5 + 32) - *(_DWORD *)(v5 + 24);
    v7 = (Microsoft::Basix::Containers::FlexIBuffer *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*((_QWORD *)this + 149));
    v8 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*((_QWORD *)this + 149));
    PointerRel = Microsoft::Basix::Containers::FlexIBuffer::GetPointerRel(
                   v7,
                   0,
                   *(_QWORD *)(v8 + 32) - *(_QWORD *)(v8 + 24));
    v10 = WinHttpWebSocketReceive(**((HINTERNET **)this + 146), PointerRel, v6, 0, 0);
    if ( v10 )
    {
      v11 = *(void (__fastcall **)(Microsoft::Basix::Dct::WinHttpDCT *, __int64))(*(_QWORD *)this + 120LL);
      v12 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinHttpDCT *, _BYTE *))(*(_QWORD *)this + 104LL))(
              this,
              v26);
      v22 = 0;
      v23 = 0;
      std::string::_Construct<1,char const *>(&v22, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp", 50);
      memset(v25, 0, sizeof(v25));
      std::string::_Construct<1,char const *>(v25, "Queuing read for websocket failed.", 34);
      v14 = Microsoft::Basix::WindowsCategory(v13);
      v15 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        v15 = v10;
      LODWORD(v28) = v15;
      *((_QWORD *)&v28 + 1) = v14;
      v16 = Microsoft::Basix::SystemException::SystemException(
              (unsigned int)&v27,
              (unsigned int)&v28,
              (unsigned int)v25,
              (unsigned int)&v22,
              162,
              v12);
      v17 = std::make_exception_ptr<Microsoft::Basix::SystemException>(v24, v16);
      v11(this, v17);
      __ExceptionPtrDestroy(v24);
      std::string::_Tidy_deallocate(v25);
      std::string::_Tidy_deallocate(&v22);
      std::string::_Tidy_deallocate(v26);
      v28 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v28);
      if ( (_QWORD)v28 && *(_BYTE *)(v28 + 128) )
      {
        v22 = 0;
        v23 = 0;
        std::string::_Construct<1,char const *>(
          &v22,
          "QueueRead (WinHttp) error: 0x%x\n    %s(%d): %s()",
          48,
          v18,
          peBufferType,
          v21);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(
          (unsigned int)&v28,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v22,
          v15,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp",
          163,
          (__int64)"Microsoft::Basix::Dct::WinHttpDCT::QueueRead");
        std::string::_Tidy_deallocate(&v22);
      }
      v19 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
      if ( *((_QWORD *)&v28 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
      Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(this, 0);
    }
  }
}

```

## disassembly

```asm
0x18036c55c  mov     [rsp-8+arg_8], rbx
0x18036c561  mov     [rsp-8+arg_10], rsi
0x18036c566  push    rbp
0x18036c567  push    rdi
0x18036c568  push    r12
0x18036c56a  push    r14
0x18036c56c  push    r15
0x18036c56e  lea     rbp, [rsp-70h]
0x18036c573  mov     eax, 170h
0x18036c578  call    _alloca_probe
0x18036c57d  sub     rsp, rax
0x18036c580  mov     rax, cs:__security_cookie
0x18036c587  xor     rax, rsp
0x18036c58a  mov     [rbp+90h+var_30], rax
0x18036c58e  mov     rsi, rcx
0x18036c591  cmp     qword ptr [rcx+490h], 0
0x18036c599  jz      loc_18036C8AE
0x18036c59f  xorps   xmm0, xmm0
0x18036c5a2  movups  [rbp+90h+var_40], xmm0
0x18036c5a6  lea     rcx, [rbp+90h+var_40]
0x18036c5aa  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18036c5af  nop
0x18036c5b0  mov     rax, qword ptr [rbp+90h+var_40]
0x18036c5b4  test    rax, rax
0x18036c5b7  jz      short loc_18036C623
0x18036c5b9  cmp     byte ptr [rax+80h], 0
0x18036c5c0  jz      short loc_18036C623
0x18036c5c2  mov     rcx, [rsi+4A8h]
0x18036c5c9  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18036c5ce  mov     rbx, [rax+20h]
0x18036c5d2  sub     rbx, [rax+18h]
0x18036c5d6  xorps   xmm0, xmm0
0x18036c5d9  movups  [rsp+190h+var_130], xmm0
0x18036c5de  xorps   xmm1, xmm1
0x18036c5e1  movdqu  [rsp+190h+var_120], xmm1
0x18036c5e7  mov     r8d, 12h
0x18036c5ed  lea     rdx, aReadQueuedD; "Read queued - : %d"
0x18036c5f4  lea     rcx, [rsp+190h+var_130]
0x18036c5f9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036c5fe  nop
0x18036c5ff  mov     r9, rbx
0x18036c602  lea     r8, [rsp+190h+var_130]
0x18036c607  lea     rdx, aNanoDct; "NANO_DCT"
0x18036c60e  lea     rcx, [rbp+90h+var_40]
0x18036c612  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@_K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,unsigned __int64)
0x18036c617  nop
0x18036c618  lea     rcx, [rsp+190h+var_130]
0x18036c61d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036c622  nop
0x18036c623  or      r12d, 0FFFFFFFFh
0x18036c627  mov     rbx, qword ptr [rbp+90h+var_40+8]
0x18036c62b  test    rbx, rbx
0x18036c62e  jz      short loc_18036C669
0x18036c630  mov     eax, r12d
0x18036c633  lock xadd [rbx+8], eax
0x18036c638  add     eax, r12d
0x18036c63b  jnz     short loc_18036C669
0x18036c63d  mov     rax, [rbx]
0x18036c640  mov     rcx, rbx
0x18036c643  mov     rax, [rax]
0x18036c646  call    cs:__guard_dispatch_icall_fptr
0x18036c64c  mov     eax, r12d
0x18036c64f  lock xadd [rbx+0Ch], eax
0x18036c654  add     eax, r12d
0x18036c657  jnz     short loc_18036C669
0x18036c659  mov     rax, [rbx]
0x18036c65c  mov     rcx, rbx
0x18036c65f  mov     rax, [rax+8]
0x18036c663  call    cs:__guard_dispatch_icall_fptr
0x18036c669  mov     rcx, [rsi+4A8h]
0x18036c670  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18036c675  mov     edi, [rax+20h]
0x18036c678  sub     edi, [rax+18h]
0x18036c67b  mov     rcx, [rsi+4A8h]
0x18036c682  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18036c687  mov     rbx, rax
0x18036c68a  mov     rcx, [rsi+4A8h]
0x18036c691  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18036c696  mov     r8, [rax+20h]
0x18036c69a  sub     r8, [rax+18h]; unsigned __int64
0x18036c69e  xor     edx, edx; __int64
0x18036c6a0  mov     rcx, rbx; this
0x18036c6a3  call    ?GetPointerRel@FlexIBuffer@Containers@Basix@Microsoft@@QEBAPEAE_J_K@Z; Microsoft::Basix::Containers::FlexIBuffer::GetPointerRel(__int64,unsigned __int64)
0x18036c6a8  mov     rcx, [rsi+490h]
0x18036c6af  mov     [rsp+190h+peBufferType], 0; peBufferType
0x18036c6b8  xor     r9d, r9d; pdwBytesRead
0x18036c6bb  mov     r8d, edi; dwBufferLength
0x18036c6be  mov     rdx, rax; pvBuffer
0x18036c6c1  mov     rcx, [rcx]; hWebSocket
0x18036c6c4  call    cs:__imp_WinHttpWebSocketReceive
0x18036c6ca  mov     r14d, eax
0x18036c6cd  test    eax, eax
0x18036c6cf  jz      loc_18036C8AE
0x18036c6d5  mov     rcx, [rsi]
0x18036c6d8  mov     rdi, [rcx+78h]
0x18036c6dc  mov     rax, [rcx+68h]
0x18036c6e0  lea     rdx, [rbp+90h+var_F0]
0x18036c6e4  mov     rcx, rsi
0x18036c6e7  call    cs:__guard_dispatch_icall_fptr
0x18036c6ed  mov     rbx, rax
0x18036c6f0  xorps   xmm0, xmm0
0x18036c6f3  movups  [rsp+190h+var_150], xmm0
0x18036c6f8  xorps   xmm1, xmm1
0x18036c6fb  movdqu  [rsp+190h+var_140], xmm1
0x18036c701  mov     r8d, 32h ; '2'
0x18036c707  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036c70e  lea     rcx, [rsp+190h+var_150]
0x18036c713  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036c718  nop
0x18036c719  xorps   xmm0, xmm0
0x18036c71c  movups  [rbp+90h+var_110], xmm0
0x18036c720  xorps   xmm1, xmm1
0x18036c723  movdqu  [rbp+90h+var_100], xmm1
0x18036c728  mov     r8d, 22h ; '"'
0x18036c72e  lea     rdx, aQueuingReadFor; "Queuing read for websocket failed."
0x18036c735  lea     rcx, [rbp+90h+var_110]
0x18036c739  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036c73e  nop
0x18036c73f  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036c744  movzx   r15d, r14w
0x18036c748  or      r15d, 80070000h
0x18036c74f  test    r14d, r14d
0x18036c752  cmovle  r15d, r14d
0x18036c756  mov     dword ptr [rbp+90h+var_40], r15d
0x18036c75a  mov     qword ptr [rbp+90h+var_40+8], rax
0x18036c75e  movaps  xmm0, [rbp+90h+var_40]
0x18036c762  movdqa  [rbp+90h+var_40], xmm0
0x18036c767  mov     [rsp+190h+var_168], rbx
0x18036c76c  mov     [rsp+190h+peBufferType], 0A2h
0x18036c775  lea     r9, [rsp+190h+var_150]
0x18036c77a  lea     r8, [rbp+90h+var_110]
0x18036c77e  lea     rdx, [rbp+90h+var_40]
0x18036c782  lea     rcx, [rbp+90h+var_D0]
0x18036c786  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036c78b  mov     rdx, rax
0x18036c78e  lea     rcx, [rsp+190h+var_130]
0x18036c793  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18036c798  nop
0x18036c799  mov     rdx, rax
0x18036c79c  mov     rcx, rsi
0x18036c79f  mov     rax, rdi
0x18036c7a2  call    cs:__guard_dispatch_icall_fptr
0x18036c7a8  nop
0x18036c7a9  lea     rcx, [rsp+190h+var_130]; void *
0x18036c7ae  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18036c7b3  nop
0x18036c7b4  lea     rcx, [rbp+90h+var_110]
0x18036c7b8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036c7bd  nop
0x18036c7be  lea     rcx, [rsp+190h+var_150]
0x18036c7c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036c7c8  nop
0x18036c7c9  lea     rcx, [rbp+90h+var_F0]
0x18036c7cd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036c7d2  xorps   xmm0, xmm0
0x18036c7d5  movups  [rbp+90h+var_40], xmm0
0x18036c7d9  lea     rcx, [rbp+90h+var_40]
0x18036c7dd  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18036c7e2  nop
0x18036c7e3  mov     rax, qword ptr [rbp+90h+var_40]
0x18036c7e7  test    rax, rax
0x18036c7ea  jz      short loc_18036C862
0x18036c7ec  cmp     byte ptr [rax+80h], 0
0x18036c7f3  jz      short loc_18036C862
0x18036c7f5  xorps   xmm0, xmm0
0x18036c7f8  movups  [rsp+190h+var_150], xmm0
0x18036c7fd  xorps   xmm1, xmm1
0x18036c800  movdqu  [rsp+190h+var_140], xmm1
0x18036c806  mov     r8d, 30h ; '0'
0x18036c80c  lea     rdx, aQueuereadWinht; "QueueRead (WinHttp) error: 0x%x\n    %s"...
0x18036c813  lea     rcx, [rsp+190h+var_150]
0x18036c818  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036c81d  nop
0x18036c81e  lea     rax, aMicrosoftBasix_313; "Microsoft::Basix::Dct::WinHttpDCT::Queu"...
0x18036c825  mov     [rsp+190h+var_160], rax
0x18036c82a  mov     dword ptr [rsp+190h+var_168], 0A3h
0x18036c832  lea     rax, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036c839  mov     [rsp+190h+peBufferType], rax
0x18036c83e  mov     r9d, r15d
0x18036c841  lea     r8, [rsp+190h+var_150]
0x18036c846  lea     rdx, aNanoDct; "NANO_DCT"
0x18036c84d  lea     rcx, [rbp+90h+var_40]
0x18036c851  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@JPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@J1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,long,char const *,int,char const *)
0x18036c856  nop
0x18036c857  lea     rcx, [rsp+190h+var_150]
0x18036c85c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036c861  nop
0x18036c862  mov     rbx, qword ptr [rbp+90h+var_40+8]
0x18036c866  test    rbx, rbx
0x18036c869  jz      short loc_18036C8A4
0x18036c86b  mov     eax, r12d
0x18036c86e  lock xadd [rbx+8], eax
0x18036c873  add     eax, r12d
0x18036c876  jnz     short loc_18036C8A4
0x18036c878  mov     rax, [rbx]
0x18036c87b  mov     rcx, rbx
0x18036c87e  mov     rax, [rax]
0x18036c881  call    cs:__guard_dispatch_icall_fptr
0x18036c887  mov     eax, r12d
0x18036c88a  lock xadd [rbx+0Ch], eax
0x18036c88f  add     eax, r12d
0x18036c892  jnz     short loc_18036C8A4
0x18036c894  mov     rax, [rbx]
0x18036c897  mov     rcx, rbx
0x18036c89a  mov     rax, [rax+8]
0x18036c89e  call    cs:__guard_dispatch_icall_fptr
0x18036c8a4  xor     edx, edx; bool
0x18036c8a6  mov     rcx, rsi; this
0x18036c8a9  call    ?FireOnClosedInternal@WinHttpDCT@Dct@Basix@Microsoft@@IEAAX_N@Z; Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(bool)
0x18036c8ae  mov     rcx, [rbp+90h+var_30]
0x18036c8b2  xor     rcx, rsp; StackCookie
0x18036c8b5  call    __security_check_cookie
0x18036c8ba  lea     r11, [rsp+190h+var_20]
0x18036c8c2  mov     rbx, [r11+38h]
0x18036c8c6  mov     rsi, [r11+40h]
0x18036c8ca  mov     rsp, r11
0x18036c8cd  pop     r15
0x18036c8cf  pop     r14
0x18036c8d1  pop     r12
0x18036c8d3  pop     rdi
0x18036c8d4  pop     rbp
0x18036c8d5  retn
```
