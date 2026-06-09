# Microsoft::Basix::Dct::WindowsFileDCT::QueueRead(void)

- ea: `0x180143e48`
- end: `0x18014429a`
- name: `?QueueRead@WindowsFileDCT@Dct@Basix@Microsoft@@IEAAXXZ`
- size: `1106`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WindowsFileDCT *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801422d0`
- `0x180142e10`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x18004e1dc`
- `0x1800bb210`
- `0x18011963c`
- `0x180142238`
- `0x180142ce4`
- `0x180143e48`
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

- `KERNEL32!GetLastError` at `0x180143fa7`
- `KERNEL32!GetLastError` at `0x180144046`
- `KERNEL32!GetLastError` at `0x180143fa7`
- `KERNEL32!GetLastError` at `0x180144046`
- `KERNEL32!ReadFile` at `0x180143f99`
- `KERNEL32!ReadFile` at `0x180143f99`
- `KERNEL32!StartThreadpoolIo` at `0x180143f62`
- `KERNEL32!StartThreadpoolIo` at `0x180143f62`
- `KERNEL32!CancelThreadpoolIo` at `0x180143fbf`
- `KERNEL32!CancelThreadpoolIo` at `0x180143fbf`

## string_xrefs

- `0x18014402e`: `Queuing read for a file failed.`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::WindowsFileDCT::QueueRead(Microsoft::Basix::Dct::WindowsFileDCT *this)
{
  char v2; // r12
  char *v3; // r14
  __int64 v4; // rax
  __int64 *v5; // rax
  char *v6; // r15
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rcx
  __int64 v11; // rcx
  struct _OVERLAPPED *lpOverlapped; // rdi
  DWORD v13; // ebx
  __int64 v14; // rax
  void (__fastcall *v15)(Microsoft::Basix::Dct::WindowsFileDCT *, __int64); // rdi
  Microsoft::Basix *v16; // rcx
  const struct std::error_category *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  volatile signed __int32 *v20; // rbx
  void (__fastcall *v21)(Microsoft::Basix::Dct::WindowsFileDCT *, __int64); // rbx
  Microsoft::Basix *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int128 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B0h]
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int128 v30; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v31[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v32[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[144]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = 0;
  v3 = (char *)this + 1096;
  if ( Mtx_lock((Microsoft::Basix::Dct::WindowsFileDCT *)((char *)this + 1096)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v3 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v3 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_QWORD *)this + 147) && (v4 = *((_QWORD *)this + 136)) != 0 && v4 != -1 )
  {
    v5 = (__int64 *)Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::WindowsFileDCT>(
                      (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                      &v25);
    v6 = (char *)this + 1200;
    v7 = *((_QWORD *)this + 150);
    v8 = *v5;
    v9 = v5[1];
    *v5 = 0;
    v5[1] = 0;
    *(_QWORD *)(v7 + 40) = v8;
    v10 = *(volatile signed __int32 **)(v7 + 48);
    *(_QWORD *)(v7 + 48) = v9;
    if ( v10 && _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = *((_QWORD *)&v25 + 1);
    if ( *((_QWORD *)&v25 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    }
    std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(
      *(_QWORD *)v6 + 88LL,
      (char *)this + 1200);
    StartThreadpoolIo(*((PTP_IO *)this + 147));
    lpOverlapped = *(struct _OVERLAPPED **)v6;
    v13 = *(_DWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*(_QWORD *)(*(_QWORD *)v6 + 56LL))
                    + 40);
    v14 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*(_QWORD *)(*(_QWORD *)v6 + 56LL));
    if ( !ReadFile(*((HANDLE *)this + 136), *(LPVOID *)(v14 + 16), v13, 0, lpOverlapped) && GetLastError() != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 147));
      v15 = *(void (__fastcall **)(Microsoft::Basix::Dct::WindowsFileDCT *, __int64))(*(_QWORD *)this + 120LL);
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(&v28, (const char *)&Str1, 0);
      v26 = 0;
      v27 = 0;
      std::string::_Construct<1,char const *>(&v26, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp", 54);
      memset(v31, 0, sizeof(v31));
      std::string::_Construct<1,char const *>(v31, "Queuing read for a file failed.", 31);
      v17 = Microsoft::Basix::WindowsCategory(v16);
      LODWORD(v25) = GetLastError();
      *((_QWORD *)&v25 + 1) = v17;
      v18 = Microsoft::Basix::SystemException::SystemException(
              (unsigned int)v33,
              (unsigned int)&v25,
              (unsigned int)v31,
              (unsigned int)&v26,
              284,
              (__int64)&v28);
      v19 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v30, v18);
      v15(this, v19);
      __ExceptionPtrDestroy(&v30);
      std::string::_Tidy_deallocate(v31);
      std::string::_Tidy_deallocate(&v26);
      std::string::_Tidy_deallocate(&v28);
      v25 = 0;
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        *(_QWORD *)v6 + 88LL,
        &v25);
      v20 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
      if ( *((_QWORD *)&v25 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
      v2 = 1;
    }
    Mtx_unlock((_Mtx_t)v3);
    if ( v2 )
    {
      Microsoft::Basix::Dct::WindowsFileDCT::CloseFiles(this);
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(this, 0);
    }
  }
  else
  {
    v21 = *(void (__fastcall **)(Microsoft::Basix::Dct::WindowsFileDCT *, __int64))(*(_QWORD *)this + 120LL);
    memset(v32, 0, sizeof(v32));
    std::string::_Construct<1,char const *>(v32, (const char *)&Str1, 0);
    v26 = 0;
    v27 = 0;
    std::string::_Construct<1,char const *>(&v26, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp", 54);
    v28 = 0;
    v29 = 0;
    std::string::_Construct<1,char const *>(&v28, "The file is closed.", 19);
    LODWORD(v25) = 2;
    *((_QWORD *)&v25 + 1) = Microsoft::Basix::WindowsCategory(v22);
    v30 = v25;
    v23 = Microsoft::Basix::SystemException::SystemException(
            (unsigned int)v33,
            (unsigned int)&v30,
            (unsigned int)&v28,
            (unsigned int)&v26,
            262,
            (__int64)v32);
    v24 = std::make_exception_ptr<Microsoft::Basix::SystemException>(v31, v23);
    v21(this, v24);
    __ExceptionPtrDestroy(v31);
    std::string::_Tidy_deallocate(&v28);
    std::string::_Tidy_deallocate(&v26);
    std::string::_Tidy_deallocate(v32);
    Mtx_unlock((_Mtx_t)v3);
  }
}

```

## disassembly

```asm
0x180143e48  mov     rax, rsp
0x180143e4b  mov     [rax+8], rbx
0x180143e4f  mov     [rax+10h], rsi
0x180143e53  mov     [rax+18h], rdi
0x180143e57  mov     [rax+20h], r12
0x180143e5b  push    rbp
0x180143e5c  push    r14
0x180143e5e  push    r15
0x180143e60  lea     rbp, [rax-78h]
0x180143e64  mov     eax, 160h
0x180143e69  call    _alloca_probe
0x180143e6e  sub     rsp, rax
0x180143e71  mov     rsi, rcx
0x180143e74  xor     r12b, r12b
0x180143e77  lea     r14, [rcx+448h]
0x180143e7e  mov     rcx, r14; _Mtx_t
0x180143e81  call    _Mtx_lock
0x180143e86  test    eax, eax
0x180143e88  jnz     loc_18014428F
0x180143e8e  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x180143e96  jz      loc_18014427C
0x180143e9c  cmp     qword ptr [rsi+498h], 0
0x180143ea4  jz      loc_180144153
0x180143eaa  mov     rax, [rsi+440h]
0x180143eb1  test    rax, rax
0x180143eb4  jz      loc_180144153
0x180143eba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180143ebe  jz      loc_180144153
0x180143ec4  mov     rax, [rsi+8]
0x180143ec8  movsxd  rcx, dword ptr [rax+4]
0x180143ecc  add     rcx, 8
0x180143ed0  add     rcx, rsi
0x180143ed3  lea     rdx, [rsp+170h+var_148+8]
0x180143ed8  call    ??$GetWeakPtr@VWindowsFileDCT@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VWindowsFileDCT@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::WindowsFileDCT>(void)
0x180143edd  lea     r15, [rsi+4B0h]
0x180143ee4  mov     r8, [r15]
0x180143ee7  mov     rcx, [rax]
0x180143eea  mov     rdx, [rax+8]
0x180143eee  mov     qword ptr [rax], 0
0x180143ef5  mov     qword ptr [rax+8], 0
0x180143efd  mov     [r8+28h], rcx
0x180143f01  mov     rcx, [r8+30h]
0x180143f05  mov     [r8+30h], rdx
0x180143f09  test    rcx, rcx
0x180143f0c  jz      short loc_180143F28
0x180143f0e  or      eax, 0FFFFFFFFh
0x180143f11  lock xadd [rcx+0Ch], eax
0x180143f16  cmp     eax, 1
0x180143f19  jnz     short loc_180143F28
0x180143f1b  mov     rax, [rcx]
0x180143f1e  mov     rax, [rax+8]
0x180143f22  call    cs:__guard_dispatch_icall_fptr
0x180143f28  mov     rcx, qword ptr [rsp+170h+var_138]
0x180143f2d  test    rcx, rcx
0x180143f30  jz      short loc_180143F4C
0x180143f32  or      eax, 0FFFFFFFFh
0x180143f35  lock xadd [rcx+0Ch], eax
0x180143f3a  cmp     eax, 1
0x180143f3d  jnz     short loc_180143F4C
0x180143f3f  mov     rax, [rcx]
0x180143f42  mov     rax, [rax+8]
0x180143f46  call    cs:__guard_dispatch_icall_fptr
0x180143f4c  mov     rcx, [r15]
0x180143f4f  add     rcx, 58h ; 'X'
0x180143f53  mov     rdx, r15
0x180143f56  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x180143f5b  mov     rcx, [rsi+498h]; pio
0x180143f62  call    cs:__imp_StartThreadpoolIo
0x180143f68  mov     rdi, [r15]
0x180143f6b  mov     rcx, [rdi+38h]
0x180143f6f  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180143f74  mov     ebx, [rax+28h]
0x180143f77  mov     rcx, [r15]
0x180143f7a  mov     rcx, [rcx+38h]
0x180143f7e  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180143f83  mov     [rsp+170h+lpOverlapped], rdi; lpOverlapped
0x180143f88  xor     r9d, r9d; lpNumberOfBytesRead
0x180143f8b  mov     r8d, ebx; nNumberOfBytesToRead
0x180143f8e  mov     rdx, [rax+10h]; lpBuffer
0x180143f92  mov     rcx, [rsi+440h]; hFile
0x180143f99  call    cs:__imp_ReadFile
0x180143f9f  test    eax, eax
0x180143fa1  jnz     loc_18014412B
0x180143fa7  call    cs:__imp_GetLastError
0x180143fad  cmp     eax, 3E5h
0x180143fb2  jz      loc_18014412B
0x180143fb8  mov     rcx, [rsi+498h]; pio
0x180143fbf  call    cs:__imp_CancelThreadpoolIo
0x180143fc5  mov     rax, [rsi]
0x180143fc8  mov     rdi, [rax+78h]
0x180143fcc  xorps   xmm0, xmm0
0x180143fcf  movups  [rsp+170h+var_118+8], xmm0
0x180143fd4  xorps   xmm1, xmm1
0x180143fd7  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x180143fdd  xor     r8d, r8d
0x180143fe0  lea     rdx, Str1
0x180143fe7  lea     rcx, [rsp+170h+var_118+8]
0x180143fec  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180143ff1  xorps   xmm0, xmm0
0x180143ff4  movups  [rsp+170h+var_138+8], xmm0
0x180143ff9  xorps   xmm1, xmm1
0x180143ffc  movdqu  [rsp+170h+var_128+8], xmm1
0x180144002  mov     r8d, 36h ; '6'
0x180144008  lea     rdx, aCW1SSrcLibbasi_69; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18014400f  lea     rcx, [rsp+170h+var_138+8]
0x180144014  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180144019  xorps   xmm0, xmm0
0x18014401c  movups  [rbp+70h+var_E0], xmm0
0x180144020  xorps   xmm1, xmm1
0x180144023  movdqu  [rbp+70h+var_D0], xmm1
0x180144028  mov     r8d, 1Fh
0x18014402e  lea     rdx, aQueuingReadFor_1; "Queuing read for a file failed."
0x180144035  lea     rcx, [rbp+70h+var_E0]
0x180144039  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014403e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180144043  mov     rbx, rax
0x180144046  call    cs:__imp_GetLastError
0x18014404c  mov     dword ptr [rsp+170h+var_148+8], eax
0x180144050  mov     qword ptr [rsp+170h+var_138], rbx
0x180144055  movaps  xmm0, [rsp+170h+var_148+8]
0x18014405a  movdqa  [rsp+170h+var_148+8], xmm0
0x180144060  lea     rax, [rsp+170h+var_118+8]
0x180144065  mov     qword ptr [rsp+170h+var_148], rax
0x18014406a  mov     [rsp+170h+lpOverlapped], 11Ch
0x180144073  lea     r9, [rsp+170h+var_138+8]
0x180144078  lea     r8, [rbp+70h+var_E0]
0x18014407c  lea     rdx, [rsp+170h+var_148+8]
0x180144081  lea     rcx, [rbp+70h+var_A0]
0x180144085  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18014408a  mov     rdx, rax
0x18014408d  lea     rcx, [rbp+70h+var_F0]
0x180144091  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x180144096  mov     rdx, rax
0x180144099  mov     rcx, rsi
0x18014409c  mov     rax, rdi
0x18014409f  call    cs:__guard_dispatch_icall_fptr
0x1801440a5  lea     rcx, [rbp+70h+var_F0]; void *
0x1801440a9  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1801440ae  lea     rcx, [rbp+70h+var_E0]
0x1801440b2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801440b7  lea     rcx, [rsp+170h+var_138+8]
0x1801440bc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801440c1  lea     rcx, [rsp+170h+var_118+8]
0x1801440c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801440cb  xorps   xmm0, xmm0
0x1801440ce  movdqu  [rsp+170h+var_148+8], xmm0
0x1801440d4  mov     rcx, [r15]
0x1801440d7  add     rcx, 58h ; 'X'
0x1801440db  lea     rdx, [rsp+170h+var_148+8]
0x1801440e0  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x1801440e5  mov     rbx, qword ptr [rsp+170h+var_138]
0x1801440ea  test    rbx, rbx
0x1801440ed  jz      short loc_180144128
0x1801440ef  or      eax, 0FFFFFFFFh
0x1801440f2  lock xadd [rbx+8], eax
0x1801440f7  cmp     eax, 1
0x1801440fa  jnz     short loc_180144128
0x1801440fc  mov     rax, [rbx]
0x1801440ff  mov     rcx, rbx
0x180144102  mov     rax, [rax]
0x180144105  call    cs:__guard_dispatch_icall_fptr
0x18014410b  or      eax, 0FFFFFFFFh
0x18014410e  lock xadd [rbx+0Ch], eax
0x180144113  cmp     eax, 1
0x180144116  jnz     short loc_180144128
0x180144118  mov     rax, [rbx]
0x18014411b  mov     rcx, rbx
0x18014411e  mov     rax, [rax+8]
0x180144122  call    cs:__guard_dispatch_icall_fptr
0x180144128  mov     r12b, 1
0x18014412b  mov     rcx, r14; _Mtx_t
0x18014412e  call    _Mtx_unlock
0x180144133  test    r12b, r12b
0x180144136  jz      loc_18014425B
0x18014413c  mov     rcx, rsi; this
0x18014413f  call    ?CloseFiles@WindowsFileDCT@Dct@Basix@Microsoft@@IEAAXXZ; Microsoft::Basix::Dct::WindowsFileDCT::CloseFiles(void)
0x180144144  xor     edx, edx; bool
0x180144146  mov     rcx, rsi; this
0x180144149  call    ?FireOnClosed@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@MEAAX_N@Z; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(bool)
0x18014414e  jmp     loc_18014425B
0x180144153  mov     rax, [rsi]
0x180144156  mov     rbx, [rax+78h]
0x18014415a  xorps   xmm0, xmm0
0x18014415d  movups  [rbp+70h+var_C0], xmm0
0x180144161  xorps   xmm1, xmm1
0x180144164  movdqu  [rbp+70h+var_B0], xmm1
0x180144169  xor     r8d, r8d
0x18014416c  lea     rdx, Str1
0x180144173  lea     rcx, [rbp+70h+var_C0]
0x180144177  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014417c  xorps   xmm0, xmm0
0x18014417f  movups  [rsp+170h+var_138+8], xmm0
0x180144184  xorps   xmm1, xmm1
0x180144187  movdqu  [rsp+170h+var_128+8], xmm1
0x18014418d  mov     r8d, 36h ; '6'
0x180144193  lea     rdx, aCW1SSrcLibbasi_69; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18014419a  lea     rcx, [rsp+170h+var_138+8]
0x18014419f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801441a4  xorps   xmm0, xmm0
0x1801441a7  movups  [rsp+170h+var_118+8], xmm0
0x1801441ac  xorps   xmm1, xmm1
0x1801441af  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x1801441b5  mov     r8d, 13h
0x1801441bb  lea     rdx, aTheFileIsClose; "The file is closed."
0x1801441c2  lea     rcx, [rsp+170h+var_118+8]
0x1801441c7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801441cc  mov     dword ptr [rsp+170h+var_148+8], 2
0x1801441d4  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1801441d9  mov     qword ptr [rsp+170h+var_138], rax
0x1801441de  movaps  xmm0, [rsp+170h+var_148+8]
0x1801441e3  movdqa  [rbp+70h+var_F0], xmm0
0x1801441e8  lea     rax, [rbp+70h+var_C0]
0x1801441ec  mov     qword ptr [rsp+170h+var_148], rax
0x1801441f1  mov     [rsp+170h+lpOverlapped], 106h
0x1801441fa  lea     r9, [rsp+170h+var_138+8]
0x1801441ff  lea     r8, [rsp+170h+var_118+8]
0x180144204  lea     rdx, [rbp+70h+var_F0]
0x180144208  lea     rcx, [rbp+70h+var_A0]
0x18014420c  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180144211  mov     rdx, rax
0x180144214  lea     rcx, [rbp+70h+var_E0]
0x180144218  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18014421d  mov     rdx, rax
0x180144220  mov     rcx, rsi
0x180144223  mov     rax, rbx
0x180144226  call    cs:__guard_dispatch_icall_fptr
0x18014422c  lea     rcx, [rbp+70h+var_E0]; void *
0x180144230  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180144235  lea     rcx, [rsp+170h+var_118+8]
0x18014423a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014423f  lea     rcx, [rsp+170h+var_138+8]
0x180144244  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180144249  lea     rcx, [rbp+70h+var_C0]
0x18014424d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180144252  mov     rcx, r14; _Mtx_t
0x180144255  call    _Mtx_unlock
0x18014425a  nop
0x18014425b  lea     r11, [rsp+170h+var_10]
0x180144263  mov     rbx, [r11+20h]
0x180144267  mov     rsi, [r11+28h]
0x18014426b  mov     rdi, [r11+30h]
0x18014426f  mov     r12, [r11+38h]
0x180144273  mov     rsp, r11
0x180144276  pop     r15
0x180144278  pop     r14
0x18014427a  pop     rbp
0x18014427b  retn
0x18014427c  mov     dword ptr [r14+4Ch], 7FFFFFFEh
0x180144284  mov     ecx, 6; int
0x180144289  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18014428f  mov     ecx, 5; int
0x180144294  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
