# Microsoft::Basix::Dct::WinsockDCTChannelContext::CancelIO(bool)

- ea: `0x18014fc40`
- end: `0x18014fe3f`
- name: `?CancelIO@WinsockDCTChannelContext@Dct@Basix@Microsoft@@MEAAX_N@Z`
- size: `511`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinsockDCTChannelContext *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1801379f0`

## callees

- `0x1801353c4`
- `0x18014fc40`
- `0x18014fe40`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18014fd50`
- `KERNEL32!GetLastError` at `0x18014fd50`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18014fd38`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18014fd38`
- `KERNEL32!CancelIoEx` at `0x18014fdbb`
- `KERNEL32!CancelIoEx` at `0x18014fdbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Basix::Dct::WinsockDCTChannelContext::CancelIO(
        Microsoft::Basix::Dct::WinsockDCTChannelContext *this,
        char a2)
{
  char *v4; // rbx
  __int64 v5; // rax
  HANDLE *v6; // rsi
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rax
  BOOL QueuedCompletionStatus; // eax
  LPOVERLAPPED v10; // rbx
  char v11; // bl
  LPOVERLAPPED Overlapped; // [rsp+30h] [rbp-48h] BYREF
  char v13[8]; // [rsp+38h] [rbp-40h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 CompletionKey[2]; // [rsp+48h] [rbp-30h] BYREF

  *(_OWORD *)CompletionKey = 0;
  v4 = (char *)this + 3992;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 3992)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v5 = *((_QWORD *)this + 498);
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v6 = (HANDLE *)*((_QWORD *)this + 497);
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 498);
  if ( a2 )
    std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer>::reset();
  Mtx_unlock((_Mtx_t)v4);
  if ( v6 )
  {
    if ( a2 )
    {
      Microsoft::Basix::WinUtils::WinSockObj::CancelIo((Microsoft::Basix::WinUtils::WinSockObj *)v6, 1);
      v8 = *((_QWORD *)this + 496);
      if ( v8 && v8 != -1 )
      {
        while ( 1 )
        {
          CompletionKey[0] = 0;
          Overlapped = 0;
          NumberOfBytesTransferred = 0;
          QueuedCompletionStatus = GetQueuedCompletionStatus(
                                     *((HANDLE *)this + 496),
                                     &NumberOfBytesTransferred,
                                     CompletionKey,
                                     &Overlapped,
                                     0);
          v10 = Overlapped;
          if ( Overlapped )
            v10 = (LPOVERLAPPED)((char *)Overlapped - 8);
          if ( !QueuedCompletionStatus && GetLastError() == 258 )
            break;
          if ( v10 )
            (*(void (__fastcall **)(LPOVERLAPPED, __int64))v10->Internal)(v10, 1);
        }
        if ( v10 )
          (*(void (__fastcall **)(LPOVERLAPPED, __int64))v10->Internal)(v10, 1);
      }
    }
    else
    {
      v13[0] = 1;
      v11 = ((__int64 (__fastcall *)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data2)(v13);
      *(_BYTE *)(*(__int64 (__fastcall **)(HANDLE *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v6 + 52) = v11;
      CancelIoEx(v6[51], 0);
    }
  }
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
}

```

## disassembly

```asm
0x18014fc40  mov     [rsp+arg_8], rbx
0x18014fc45  mov     [rsp+arg_10], rbp
0x18014fc4a  push    rsi
0x18014fc4b  push    rdi
0x18014fc4c  push    r14
0x18014fc4e  mov     eax, 60h
0x18014fc53  call    _alloca_probe
0x18014fc58  sub     rsp, rax
0x18014fc5b  mov     rax, cs:__security_cookie
0x18014fc62  xor     rax, rsp
0x18014fc65  mov     [rsp+78h+var_20], rax
0x18014fc6a  mov     bpl, dl
0x18014fc6d  mov     r14, rcx
0x18014fc70  xorps   xmm1, xmm1
0x18014fc73  movdqu  xmmword ptr [rsp+78h+CompletionKey], xmm1
0x18014fc79  lea     rbx, [rcx+0F98h]
0x18014fc80  mov     rcx, rbx; _Mtx_t
0x18014fc83  call    _Mtx_lock
0x18014fc88  test    eax, eax
0x18014fc8a  jnz     loc_18014FE34
0x18014fc90  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18014fc97  jz      loc_18014FE22
0x18014fc9d  lea     rcx, [r14+0F88h]
0x18014fca4  mov     rax, [rcx+8]
0x18014fca8  test    rax, rax
0x18014fcab  jz      short loc_18014FCB1
0x18014fcad  lock inc dword ptr [rax+8]
0x18014fcb1  mov     rsi, [rcx]
0x18014fcb4  mov     rdi, [rcx+8]
0x18014fcb8  test    bpl, bpl
0x18014fcbb  jz      short loc_18014FCC2
0x18014fcbd  call    ?reset@?$shared_ptr@VOutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@QEAAXXZ; std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer>::reset(void)
0x18014fcc2  mov     rcx, rbx; _Mtx_t
0x18014fcc5  call    _Mtx_unlock
0x18014fcca  test    rsi, rsi
0x18014fccd  jz      loc_18014FDC2
0x18014fcd3  test    bpl, bpl
0x18014fcd6  jz      loc_18014FD93
0x18014fcdc  mov     dl, 1; bool
0x18014fcde  mov     rcx, rsi; this
0x18014fce1  call    ?CancelIo@WinSockObj@WinUtils@Basix@Microsoft@@QEAAX_N@Z; Microsoft::Basix::WinUtils::WinSockObj::CancelIo(bool)
0x18014fce6  mov     rax, [r14+0F80h]
0x18014fced  test    rax, rax
0x18014fcf0  jz      loc_18014FDC2
0x18014fcf6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18014fcfa  jz      loc_18014FDC2
0x18014fd00  mov     [rsp+78h+CompletionKey], 0
0x18014fd09  mov     [rsp+78h+Overlapped], 0
0x18014fd12  mov     [rsp+78h+NumberOfBytesTransferred], 0
0x18014fd1a  mov     [rsp+78h+dwMilliseconds], 0; dwMilliseconds
0x18014fd22  lea     r9, [rsp+78h+Overlapped]; lpOverlapped
0x18014fd27  lea     r8, [rsp+78h+CompletionKey]; lpCompletionKey
0x18014fd2c  lea     rdx, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18014fd31  mov     rcx, [r14+0F80h]; CompletionPort
0x18014fd38  call    cs:__imp_GetQueuedCompletionStatus
0x18014fd3e  mov     rbx, [rsp+78h+Overlapped]
0x18014fd43  test    rbx, rbx
0x18014fd46  jz      short loc_18014FD4C
0x18014fd48  add     rbx, 0FFFFFFFFFFFFFFF8h
0x18014fd4c  test    eax, eax
0x18014fd4e  jnz     short loc_18014FD5D
0x18014fd50  call    cs:__imp_GetLastError
0x18014fd56  cmp     eax, 102h
0x18014fd5b  jz      short loc_18014FD78
0x18014fd5d  test    rbx, rbx
0x18014fd60  jz      short loc_18014FD00
0x18014fd62  mov     rax, [rbx]
0x18014fd65  mov     edx, 1
0x18014fd6a  mov     rcx, rbx
0x18014fd6d  mov     rax, [rax]
0x18014fd70  call    cs:__guard_dispatch_icall_fptr
0x18014fd76  jmp     short loc_18014FD00
0x18014fd78  test    rbx, rbx
0x18014fd7b  jz      short loc_18014FDC2
0x18014fd7d  mov     rax, [rbx]
0x18014fd80  mov     edx, 1
0x18014fd85  mov     rcx, rbx
0x18014fd88  mov     rax, [rax]
0x18014fd8b  call    cs:__guard_dispatch_icall_fptr
0x18014fd91  jmp     short loc_18014FDC2
0x18014fd93  mov     [rsp+78h+var_40], 1
0x18014fd98  lea     rcx, [rsp+78h+var_40]
0x18014fd9d  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data2; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18014fda2  mov     bl, al
0x18014fda4  lea     rcx, [rsi+1A0h]
0x18014fdab  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18014fdb0  xchg    bl, [rax]
0x18014fdb2  xor     edx, edx; lpOverlapped
0x18014fdb4  mov     rcx, [rsi+198h]; hFile
0x18014fdbb  call    cs:__imp_CancelIoEx
0x18014fdc1  nop
0x18014fdc2  test    rdi, rdi
0x18014fdc5  jz      short loc_18014FE00
0x18014fdc7  or      eax, 0FFFFFFFFh
0x18014fdca  lock xadd [rdi+8], eax
0x18014fdcf  cmp     eax, 1
0x18014fdd2  jnz     short loc_18014FE00
0x18014fdd4  mov     rax, [rdi]
0x18014fdd7  mov     rcx, rdi
0x18014fdda  mov     rax, [rax]
0x18014fddd  call    cs:__guard_dispatch_icall_fptr
0x18014fde3  or      eax, 0FFFFFFFFh
0x18014fde6  lock xadd [rdi+0Ch], eax
0x18014fdeb  cmp     eax, 1
0x18014fdee  jnz     short loc_18014FE00
0x18014fdf0  mov     rax, [rdi]
0x18014fdf3  mov     rcx, rdi
0x18014fdf6  mov     rax, [rax+8]
0x18014fdfa  call    cs:__guard_dispatch_icall_fptr
0x18014fe00  mov     rcx, [rsp+78h+var_20]
0x18014fe05  xor     rcx, rsp; StackCookie
0x18014fe08  call    __security_check_cookie
0x18014fe0d  lea     r11, [rsp+78h+var_18]
0x18014fe12  mov     rbx, [r11+28h]
0x18014fe16  mov     rbp, [r11+30h]
0x18014fe1a  mov     rsp, r11
0x18014fe1d  pop     r14
0x18014fe1f  pop     rdi
0x18014fe20  pop     rsi
0x18014fe21  retn
0x18014fe22  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18014fe29  mov     ecx, 6; int
0x18014fe2e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18014fe34  mov     ecx, 5; int
0x18014fe39  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
