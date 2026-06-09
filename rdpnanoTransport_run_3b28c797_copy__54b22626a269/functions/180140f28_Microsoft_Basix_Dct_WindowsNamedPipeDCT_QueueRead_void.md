# Microsoft::Basix::Dct::WindowsNamedPipeDCT::QueueRead(void)

- ea: `0x180140f28`
- end: `0x1801413a0`
- name: `?QueueRead@WindowsNamedPipeDCT@Dct@Basix@Microsoft@@IEAAXXZ`
- size: `1144`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WindowsNamedPipeDCT *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18013ec40`
- `0x1801403fc`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x18004e1dc`
- `0x1800bb210`
- `0x18011963c`
- `0x18013ea18`
- `0x180140f28`
- `0x180141730`
- `0x1801b3b70`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801410ad`
- `KERNEL32!GetLastError` at `0x18014114c`
- `KERNEL32!GetLastError` at `0x1801410ad`
- `KERNEL32!GetLastError` at `0x18014114c`
- `KERNEL32!ReadFile` at `0x18014109f`
- `KERNEL32!ReadFile` at `0x18014109f`
- `KERNEL32!StartThreadpoolIo` at `0x180141068`
- `KERNEL32!StartThreadpoolIo` at `0x180141068`
- `KERNEL32!CancelThreadpoolIo` at `0x1801410c5`
- `KERNEL32!CancelThreadpoolIo` at `0x1801410c5`

## string_xrefs

- `0x180141134`: `Queuing read for a named pipe failed.`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::WindowsNamedPipeDCT::QueueRead(Microsoft::Basix::Dct::WindowsNamedPipeDCT *this)
{
  char v2; // r12
  char *v3; // r14
  __int64 v4; // rax
  __int64 *v5; // rax
  char *v6; // r15
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  volatile signed __int32 *v11; // rcx
  volatile signed __int32 *v12; // rbx
  struct _OVERLAPPED *lpOverlapped; // rdi
  DWORD v14; // ebx
  __int64 v15; // rax
  void (__fastcall *v16)(Microsoft::Basix::Dct::WindowsNamedPipeDCT *, __int64); // rdi
  Microsoft::Basix *v17; // rcx
  const struct std::error_category *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  volatile signed __int32 *v21; // rbx
  void (__fastcall *v22)(Microsoft::Basix::Dct::WindowsNamedPipeDCT *, __int64); // rbx
  Microsoft::Basix *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int128 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B0h]
  __int128 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v32[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v34[144]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = 0;
  v3 = (char *)this + 1112;
  if ( Mtx_lock((Microsoft::Basix::Dct::WindowsNamedPipeDCT *)((char *)this + 1112)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v3 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v3 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_QWORD *)this + 149) && (v4 = *((_QWORD *)this + 138)) != 0 && v4 != -1 )
  {
    v5 = (__int64 *)Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::WindowsNamedPipeDCT>(
                      (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                      &v26);
    v6 = (char *)this + 1216;
    v7 = *((_QWORD *)this + 152);
    v8 = v5[1];
    v9 = 0;
    v10 = 0;
    if ( v8 )
    {
      v9 = *v5;
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 12));
      v10 = v8;
    }
    *(_QWORD *)(v7 + 40) = v9;
    v11 = *(volatile signed __int32 **)(v7 + 48);
    *(_QWORD *)(v7 + 48) = v10;
    if ( v11 && _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    v12 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
    if ( *((_QWORD *)&v26 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(
      *(_QWORD *)v6 + 88LL,
      (char *)this + 1216);
    StartThreadpoolIo(*((PTP_IO *)this + 149));
    lpOverlapped = *(struct _OVERLAPPED **)v6;
    v14 = *(_DWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*(_QWORD *)(*(_QWORD *)v6 + 56LL))
                    + 40);
    v15 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*(_QWORD *)(*(_QWORD *)v6 + 56LL));
    if ( !ReadFile(*((HANDLE *)this + 138), *(LPVOID *)(v15 + 16), v14, 0, lpOverlapped) && GetLastError() != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 149));
      v16 = *(void (__fastcall **)(Microsoft::Basix::Dct::WindowsNamedPipeDCT *, __int64))(*(_QWORD *)this + 120LL);
      v29 = 0;
      v30 = 0;
      std::string::_Construct<1,char const *>(&v29, (const char *)&Str1, 0);
      v27 = 0;
      v28 = 0;
      std::string::_Construct<1,char const *>(
        &v27,
        "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsnamedpipedct.cpp",
        59);
      memset(v32, 0, sizeof(v32));
      std::string::_Construct<1,char const *>(v32, "Queuing read for a named pipe failed.", 37);
      v18 = Microsoft::Basix::WindowsCategory(v17);
      LODWORD(v26) = GetLastError();
      *((_QWORD *)&v26 + 1) = v18;
      v19 = Microsoft::Basix::SystemException::SystemException(
              (unsigned int)v34,
              (unsigned int)&v26,
              (unsigned int)v32,
              (unsigned int)&v27,
              228,
              (__int64)&v29);
      v20 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v31, v19);
      v16(this, v20);
      __ExceptionPtrDestroy(&v31);
      std::string::_Tidy_deallocate(v32);
      std::string::_Tidy_deallocate(&v27);
      std::string::_Tidy_deallocate(&v29);
      v26 = 0;
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        *(_QWORD *)v6 + 88LL,
        &v26);
      v21 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
      if ( *((_QWORD *)&v26 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
      v2 = 1;
    }
    Mtx_unlock((_Mtx_t)v3);
    if ( v2 )
    {
      Microsoft::Basix::Dct::WindowsNamedPipeDCT::TerminatePipeInstance(this);
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(this, 0);
    }
  }
  else
  {
    v22 = *(void (__fastcall **)(Microsoft::Basix::Dct::WindowsNamedPipeDCT *, __int64))(*(_QWORD *)this + 120LL);
    memset(v33, 0, sizeof(v33));
    std::string::_Construct<1,char const *>(v33, (const char *)&Str1, 0);
    v27 = 0;
    v28 = 0;
    std::string::_Construct<1,char const *>(
      &v27,
      "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsnamedpipedct.cpp",
      59);
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "The pipe is closed.", 19);
    LODWORD(v26) = 2;
    *((_QWORD *)&v26 + 1) = Microsoft::Basix::WindowsCategory(v23);
    v31 = v26;
    v24 = Microsoft::Basix::SystemException::SystemException(
            (unsigned int)v34,
            (unsigned int)&v31,
            (unsigned int)&v29,
            (unsigned int)&v27,
            205,
            (__int64)v33);
    v25 = std::make_exception_ptr<Microsoft::Basix::SystemException>(v32, v24);
    v22(this, v25);
    __ExceptionPtrDestroy(v32);
    std::string::_Tidy_deallocate(&v29);
    std::string::_Tidy_deallocate(&v27);
    std::string::_Tidy_deallocate(v33);
    Mtx_unlock((_Mtx_t)v3);
  }
}

```

## disassembly

```asm
0x180140f28  mov     [rsp-8+arg_0], rbx
0x180140f2d  mov     [rsp-8+arg_8], rsi
0x180140f32  mov     [rsp-8+arg_10], rdi
0x180140f37  push    rbp
0x180140f38  push    r12
0x180140f3a  push    r13
0x180140f3c  push    r14
0x180140f3e  push    r15
0x180140f40  lea     rbp, [rsp-60h]
0x180140f45  mov     eax, 160h
0x180140f4a  call    _alloca_probe
0x180140f4f  sub     rsp, rax
0x180140f52  mov     rsi, rcx
0x180140f55  xor     r12b, r12b
0x180140f58  lea     r14, [rcx+458h]
0x180140f5f  mov     rcx, r14; _Mtx_t
0x180140f62  call    _Mtx_lock
0x180140f67  test    eax, eax
0x180140f69  jnz     loc_180141395
0x180140f6f  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x180140f77  jz      loc_180141382
0x180140f7d  cmp     qword ptr [rsi+4A8h], 0
0x180140f85  jz      loc_180141259
0x180140f8b  mov     rax, [rsi+450h]
0x180140f92  test    rax, rax
0x180140f95  jz      loc_180141259
0x180140f9b  or      r13, 0FFFFFFFFFFFFFFFFh
0x180140f9f  cmp     rax, r13
0x180140fa2  jz      loc_180141259
0x180140fa8  mov     rax, [rsi+8]
0x180140fac  movsxd  rcx, dword ptr [rax+4]
0x180140fb0  add     rcx, 8
0x180140fb4  add     rcx, rsi
0x180140fb7  lea     rdx, [rsp+180h+var_150]
0x180140fbc  call    ??$GetSharedPtr@VWindowsNamedPipeDCT@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VWindowsNamedPipeDCT@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::WindowsNamedPipeDCT>(void)
0x180140fc1  lea     r15, [rsi+4C0h]
0x180140fc8  mov     rdx, [r15]
0x180140fcb  mov     rcx, [rax+8]
0x180140fcf  xor     r8d, r8d
0x180140fd2  xor     r9d, r9d
0x180140fd5  test    rcx, rcx
0x180140fd8  jz      short loc_180140FE4
0x180140fda  mov     r8, [rax]
0x180140fdd  lock inc dword ptr [rcx+0Ch]
0x180140fe1  mov     r9, rcx
0x180140fe4  mov     [rdx+28h], r8
0x180140fe8  mov     rcx, [rdx+30h]
0x180140fec  mov     [rdx+30h], r9
0x180140ff0  test    rcx, rcx
0x180140ff3  jz      short loc_18014100F
0x180140ff5  mov     eax, r13d
0x180140ff8  lock xadd [rcx+0Ch], eax
0x180140ffd  add     eax, r13d
0x180141000  jnz     short loc_18014100F
0x180141002  mov     rax, [rcx]
0x180141005  mov     rax, [rax+8]
0x180141009  call    cs:__guard_dispatch_icall_fptr
0x18014100f  mov     rbx, qword ptr [rsp+180h+var_150+8]
0x180141014  test    rbx, rbx
0x180141017  jz      short loc_180141052
0x180141019  mov     eax, r13d
0x18014101c  lock xadd [rbx+8], eax
0x180141021  add     eax, r13d
0x180141024  jnz     short loc_180141052
0x180141026  mov     rax, [rbx]
0x180141029  mov     rcx, rbx
0x18014102c  mov     rax, [rax]
0x18014102f  call    cs:__guard_dispatch_icall_fptr
0x180141035  mov     eax, r13d
0x180141038  lock xadd [rbx+0Ch], eax
0x18014103d  add     eax, r13d
0x180141040  jnz     short loc_180141052
0x180141042  mov     rax, [rbx]
0x180141045  mov     rcx, rbx
0x180141048  mov     rax, [rax+8]
0x18014104c  call    cs:__guard_dispatch_icall_fptr
0x180141052  mov     rcx, [r15]
0x180141055  add     rcx, 58h ; 'X'
0x180141059  mov     rdx, r15
0x18014105c  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x180141061  mov     rcx, [rsi+4A8h]; pio
0x180141068  call    cs:__imp_StartThreadpoolIo
0x18014106e  mov     rdi, [r15]
0x180141071  mov     rcx, [rdi+38h]
0x180141075  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18014107a  mov     ebx, [rax+28h]
0x18014107d  mov     rcx, [r15]
0x180141080  mov     rcx, [rcx+38h]
0x180141084  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180141089  mov     [rsp+180h+lpOverlapped], rdi; lpOverlapped
0x18014108e  xor     r9d, r9d; lpNumberOfBytesRead
0x180141091  mov     r8d, ebx; nNumberOfBytesToRead
0x180141094  mov     rdx, [rax+10h]; lpBuffer
0x180141098  mov     rcx, [rsi+450h]; hFile
0x18014109f  call    cs:__imp_ReadFile
0x1801410a5  test    eax, eax
0x1801410a7  jnz     loc_180141231
0x1801410ad  call    cs:__imp_GetLastError
0x1801410b3  cmp     eax, 3E5h
0x1801410b8  jz      loc_180141231
0x1801410be  mov     rcx, [rsi+4A8h]; pio
0x1801410c5  call    cs:__imp_CancelThreadpoolIo
0x1801410cb  mov     rax, [rsi]
0x1801410ce  mov     rdi, [rax+78h]
0x1801410d2  xorps   xmm0, xmm0
0x1801410d5  movups  [rsp+180h+var_120], xmm0
0x1801410da  xorps   xmm1, xmm1
0x1801410dd  movdqu  [rsp+180h+var_110], xmm1
0x1801410e3  xor     r8d, r8d
0x1801410e6  lea     rdx, Str1
0x1801410ed  lea     rcx, [rsp+180h+var_120]
0x1801410f2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801410f7  xorps   xmm0, xmm0
0x1801410fa  movups  [rsp+180h+var_140], xmm0
0x1801410ff  xorps   xmm1, xmm1
0x180141102  movdqu  [rsp+180h+var_130], xmm1
0x180141108  mov     r8d, 3Bh ; ';'
0x18014110e  lea     rdx, aCW1SSrcLibbasi_54; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180141115  lea     rcx, [rsp+180h+var_140]
0x18014111a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014111f  xorps   xmm0, xmm0
0x180141122  movups  [rbp+80h+var_F0], xmm0
0x180141126  xorps   xmm1, xmm1
0x180141129  movdqu  [rbp+80h+var_E0], xmm1
0x18014112e  mov     r8d, 25h ; '%'
0x180141134  lea     rdx, aQueuingReadFor_0; "Queuing read for a named pipe failed."
0x18014113b  lea     rcx, [rbp+80h+var_F0]
0x18014113f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180141144  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180141149  mov     rbx, rax
0x18014114c  call    cs:__imp_GetLastError
0x180141152  mov     dword ptr [rsp+180h+var_150], eax
0x180141156  mov     qword ptr [rsp+180h+var_150+8], rbx
0x18014115b  movaps  xmm0, [rsp+180h+var_150]
0x180141160  movdqa  [rsp+180h+var_150], xmm0
0x180141166  lea     rax, [rsp+180h+var_120]
0x18014116b  mov     [rsp+180h+var_158], rax
0x180141170  mov     [rsp+180h+lpOverlapped], 0E4h
0x180141179  lea     r9, [rsp+180h+var_140]
0x18014117e  lea     r8, [rbp+80h+var_F0]
0x180141182  lea     rdx, [rsp+180h+var_150]
0x180141187  lea     rcx, [rbp+80h+var_B0]
0x18014118b  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180141190  mov     rdx, rax
0x180141193  lea     rcx, [rbp+80h+var_100]
0x180141197  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18014119c  mov     rdx, rax
0x18014119f  mov     rcx, rsi
0x1801411a2  mov     rax, rdi
0x1801411a5  call    cs:__guard_dispatch_icall_fptr
0x1801411ab  lea     rcx, [rbp+80h+var_100]; void *
0x1801411af  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801411b4  lea     rcx, [rbp+80h+var_F0]
0x1801411b8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801411bd  lea     rcx, [rsp+180h+var_140]
0x1801411c2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801411c7  lea     rcx, [rsp+180h+var_120]
0x1801411cc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801411d1  xorps   xmm0, xmm0
0x1801411d4  movdqu  [rsp+180h+var_150], xmm0
0x1801411da  mov     rcx, [r15]
0x1801411dd  add     rcx, 58h ; 'X'
0x1801411e1  lea     rdx, [rsp+180h+var_150]
0x1801411e6  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x1801411eb  mov     rbx, qword ptr [rsp+180h+var_150+8]
0x1801411f0  test    rbx, rbx
0x1801411f3  jz      short loc_18014122E
0x1801411f5  mov     eax, r13d
0x1801411f8  lock xadd [rbx+8], eax
0x1801411fd  add     eax, r13d
0x180141200  jnz     short loc_18014122E
0x180141202  mov     rax, [rbx]
0x180141205  mov     rcx, rbx
0x180141208  mov     rax, [rax]
0x18014120b  call    cs:__guard_dispatch_icall_fptr
0x180141211  mov     eax, r13d
0x180141214  lock xadd [rbx+0Ch], eax
0x180141219  add     eax, r13d
0x18014121c  jnz     short loc_18014122E
0x18014121e  mov     rax, [rbx]
0x180141221  mov     rcx, rbx
0x180141224  mov     rax, [rax+8]
0x180141228  call    cs:__guard_dispatch_icall_fptr
0x18014122e  mov     r12b, 1
0x180141231  mov     rcx, r14; _Mtx_t
0x180141234  call    _Mtx_unlock
0x180141239  test    r12b, r12b
0x18014123c  jz      loc_180141361
0x180141242  mov     rcx, rsi; this
0x180141245  call    ?TerminatePipeInstance@WindowsNamedPipeDCT@Dct@Basix@Microsoft@@IEAAXXZ; Microsoft::Basix::Dct::WindowsNamedPipeDCT::TerminatePipeInstance(void)
0x18014124a  xor     edx, edx; bool
0x18014124c  mov     rcx, rsi; this
0x18014124f  call    ?FireOnClosed@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@MEAAX_N@Z; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(bool)
0x180141254  jmp     loc_180141361
0x180141259  mov     rax, [rsi]
0x18014125c  mov     rbx, [rax+78h]
0x180141260  xorps   xmm0, xmm0
0x180141263  movups  [rbp+80h+var_D0], xmm0
0x180141267  xorps   xmm1, xmm1
0x18014126a  movdqu  [rbp+80h+var_C0], xmm1
0x18014126f  xor     r8d, r8d
0x180141272  lea     rdx, Str1
0x180141279  lea     rcx, [rbp+80h+var_D0]
0x18014127d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180141282  xorps   xmm0, xmm0
0x180141285  movups  [rsp+180h+var_140], xmm0
0x18014128a  xorps   xmm1, xmm1
0x18014128d  movdqu  [rsp+180h+var_130], xmm1
0x180141293  mov     r8d, 3Bh ; ';'
0x180141299  lea     rdx, aCW1SSrcLibbasi_54; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x1801412a0  lea     rcx, [rsp+180h+var_140]
0x1801412a5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801412aa  xorps   xmm0, xmm0
0x1801412ad  movups  [rsp+180h+var_120], xmm0
0x1801412b2  xorps   xmm1, xmm1
0x1801412b5  movdqu  [rsp+180h+var_110], xmm1
0x1801412bb  mov     r8d, 13h
0x1801412c1  lea     rdx, aThePipeIsClose; "The pipe is closed."
0x1801412c8  lea     rcx, [rsp+180h+var_120]
0x1801412cd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801412d2  mov     dword ptr [rsp+180h+var_150], 2
0x1801412da  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1801412df  mov     qword ptr [rsp+180h+var_150+8], rax
0x1801412e4  movaps  xmm0, [rsp+180h+var_150]
0x1801412e9  movdqa  [rbp+80h+var_100], xmm0
0x1801412ee  lea     rax, [rbp+80h+var_D0]
0x1801412f2  mov     [rsp+180h+var_158], rax
0x1801412f7  mov     [rsp+180h+lpOverlapped], 0CDh
0x180141300  lea     r9, [rsp+180h+var_140]
0x180141305  lea     r8, [rsp+180h+var_120]
0x18014130a  lea     rdx, [rbp+80h+var_100]
0x18014130e  lea     rcx, [rbp+80h+var_B0]
0x180141312  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180141317  mov     rdx, rax
0x18014131a  lea     rcx, [rbp+80h+var_F0]
0x18014131e  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x180141323  mov     rdx, rax
0x180141326  mov     rcx, rsi
0x180141329  mov     rax, rbx
0x18014132c  call    cs:__guard_dispatch_icall_fptr
0x180141332  lea     rcx, [rbp+80h+var_F0]; void *
0x180141336  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18014133b  lea     rcx, [rsp+180h+var_120]
0x180141340  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180141345  lea     rcx, [rsp+180h+var_140]
0x18014134a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014134f  lea     rcx, [rbp+80h+var_D0]
0x180141353  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180141358  mov     rcx, r14; _Mtx_t
0x18014135b  call    _Mtx_unlock
0x180141360  nop
0x180141361  lea     r11, [rsp+180h+var_20]
0x180141369  mov     rbx, [r11+30h]
0x18014136d  mov     rsi, [r11+38h]
0x180141371  mov     rdi, [r11+40h]
0x180141375  mov     rsp, r11
0x180141378  pop     r15
0x18014137a  pop     r14
0x18014137c  pop     r13
0x18014137e  pop     r12
0x180141380  pop     rbp
0x180141381  retn
0x180141382  mov     dword ptr [r14+4Ch], 7FFFFFFEh
0x18014138a  mov     ecx, 6; int
0x18014138f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180141395  mov     ecx, 5; int
0x18014139a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
