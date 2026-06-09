# boost::asio::detail::win_iocp_io_context::shutdown(void)

- ea: `0x180172050`
- end: `0x1801722a0`
- name: `?shutdown@win_iocp_io_context@detail@asio@boost@@UEAAXXZ`
- size: `592`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18016f00c`
- `0x180172050`
- `0x180172d58`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x1801721db`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1801721db`
- `KERNEL32!SetWaitableTimer` at `0x1801720ad`
- `KERNEL32!SetWaitableTimer` at `0x1801720ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall boost::asio::detail::win_iocp_io_context::shutdown(boost::asio::detail::win_iocp_io_context *this)
{
  _QWORD *i; // rdi
  __int64 v3; // r10
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r10
  __int64 v8; // rcx
  __int64 v9; // rax
  __int128 v10; // [rsp+30h] [rbp-50h] BYREF
  __int64 v11; // [rsp+40h] [rbp-40h]
  __int128 v12; // [rsp+48h] [rbp-38h] BYREF
  LARGE_INTEGER DueTime; // [rsp+58h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int64 CompletionKey; // [rsp+68h] [rbp-18h] BYREF

  _InterlockedExchange((volatile __int32 *)this + 17, 1);
  if ( *((_QWORD *)this + 10) )
  {
    DueTime.QuadPart = 1;
    SetWaitableTimer(*((HANDLE *)this + 11), &DueTime, 1, 0, 0, 0);
  }
  if ( *((_QWORD *)this + 22) )
  {
    boost::asio::detail::win_iocp_io_context::stop(this);
    boost::asio::detail::win_thread::join((boost::asio::detail::win_iocp_io_context *)((char *)this + 176));
    _InterlockedDecrement((volatile signed __int32 *)this + 14);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0) > 0 )
  {
    _mm_lfence();
    do
    {
      v12 = 0;
      for ( i = (_QWORD *)*((_QWORD *)this + 18); i; i = (_QWORD *)i[1] )
        (*(void (__fastcall **)(_QWORD *, __int128 *))(*i + 40LL))(i, &v12);
      v3 = *((_QWORD *)this + 19);
      if ( v3 )
      {
        if ( *((_QWORD *)&v12 + 1) )
        {
          *(_QWORD *)(*((_QWORD *)&v12 + 1) + 32LL) = v3;
          v3 = v12;
        }
        else
        {
          *(_QWORD *)&v12 = *((_QWORD *)this + 19);
        }
        *((_QWORD *)&v12 + 1) = *((_QWORD *)this + 20);
        *((_QWORD *)this + 19) = 0;
        *((_QWORD *)this + 20) = 0;
      }
      else
      {
        v3 = v12;
      }
      if ( v3 )
      {
        v4 = v3;
        v5 = v3;
        v6 = v3;
        do
        {
          if ( v5 )
          {
            *(_QWORD *)&v12 = *(_QWORD *)(v6 + 32);
            *((_QWORD *)&v12 + 1) &= -(__int64)((_QWORD)v12 != 0);
            *(_QWORD *)(v4 + 32) = 0;
          }
          _InterlockedDecrement((volatile signed __int32 *)this + 14);
          v10 = 0;
          v11 = 0;
          (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(v3 + 40))(0, v3, &v10, 0);
          v3 = v12;
          v5 = v12;
          v6 = v12;
          v4 = v12;
        }
        while ( (_QWORD)v12 );
      }
      else
      {
        NumberOfBytesTransferred = 0;
        CompletionKey = 0;
        DueTime.QuadPart = 0;
        GetQueuedCompletionStatus(
          *((HANDLE *)this + 6),
          &NumberOfBytesTransferred,
          &CompletionKey,
          (LPOVERLAPPED *)&DueTime,
          *((_DWORD *)this + 18));
        if ( DueTime.QuadPart )
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 14);
          v10 = 0;
          v11 = 0;
          (*(void (__fastcall **)(_QWORD, LARGE_INTEGER, __int128 *, _QWORD))(DueTime.QuadPart + 40))(
            0,
            DueTime,
            &v10,
            0);
        }
      }
      v7 = v12;
      if ( (_QWORD)v12 )
      {
        v8 = v12;
        v9 = v12;
        do
        {
          *(_QWORD *)&v12 = *(_QWORD *)(v9 + 32);
          *((_QWORD *)&v12 + 1) &= -(__int64)((_QWORD)v12 != 0);
          *(_QWORD *)(v8 + 32) = 0;
          v10 = 0;
          v11 = 0;
          (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(v7 + 40))(0, v7, &v10, 0);
          v7 = v12;
          v9 = v12;
          v8 = v12;
        }
        while ( (_QWORD)v12 );
      }
    }
    while ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0) > 0 );
  }
  boost::asio::detail::win_thread::join((boost::asio::detail::win_iocp_io_context *)((char *)this + 80));
}

```

## disassembly

```asm
0x180172050  mov     [rsp-18h+arg_8], rbx
0x180172055  mov     [rsp-18h+arg_10], rsi
0x18017205a  push    rbp
0x18017205b  push    rdi
0x18017205c  push    r14
0x18017205e  mov     rbp, rsp
0x180172061  mov     eax, 80h
0x180172066  call    _alloca_probe
0x18017206b  sub     rsp, rax
0x18017206e  mov     rax, cs:__security_cookie
0x180172075  xor     rax, rsp
0x180172078  mov     [rbp+var_10], rax
0x18017207c  mov     rbx, rcx
0x18017207f  mov     r8d, 1; lPeriod
0x180172085  mov     eax, r8d
0x180172088  xchg    eax, [rcx+44h]
0x18017208b  xor     r14d, r14d
0x18017208e  cmp     [rcx+50h], r14
0x180172092  jz      short loc_1801720B3
0x180172094  mov     qword ptr [rbp+DueTime], r8
0x180172098  mov     [rsp+80h+fResume], r14d; fResume
0x18017209d  mov     [rsp+80h+lpArgToCompletionRoutine], r14; lpArgToCompletionRoutine
0x1801720a2  xor     r9d, r9d; pfnCompletionRoutine
0x1801720a5  lea     rdx, [rbp+DueTime]; lpDueTime
0x1801720a9  mov     rcx, [rcx+58h]; hTimer
0x1801720ad  call    cs:__imp_SetWaitableTimer
0x1801720b3  lea     rdi, [rbx+0B0h]
0x1801720ba  cmp     [rdi], r14
0x1801720bd  jz      short loc_1801720D3
0x1801720bf  mov     rcx, rbx; this
0x1801720c2  call    ?stop@win_iocp_io_context@detail@asio@boost@@QEAAXXZ; boost::asio::detail::win_iocp_io_context::stop(void)
0x1801720c7  mov     rcx, rdi; this
0x1801720ca  call    ?join@win_thread@detail@asio@boost@@QEAAXXZ; boost::asio::detail::win_thread::join(void)
0x1801720cf  lock dec dword ptr [rbx+38h]
0x1801720d3  mov     eax, r14d
0x1801720d6  lock xadd [rbx+38h], eax
0x1801720db  test    eax, eax
0x1801720dd  jle     loc_180172273
0x1801720e3  lfence
0x1801720e6  xorps   xmm1, xmm1
0x1801720e9  movdqu  [rbp+var_38], xmm1
0x1801720ee  mov     rdi, [rbx+90h]
0x1801720f5  jmp     short loc_18017210F
0x1801720f7  mov     rax, [rdi]
0x1801720fa  lea     rdx, [rbp+var_38]
0x1801720fe  mov     rcx, rdi
0x180172101  mov     rax, [rax+28h]
0x180172105  call    cs:__guard_dispatch_icall_fptr
0x18017210b  mov     rdi, [rdi+8]
0x18017210f  test    rdi, rdi
0x180172112  jnz     short loc_1801720F7
0x180172114  mov     r10, [rbx+98h]
0x18017211b  test    r10, r10
0x18017211e  jz      short loc_180172152
0x180172120  mov     rax, qword ptr [rbp+var_38+8]
0x180172124  test    rax, rax
0x180172127  jz      short loc_180172133
0x180172129  mov     [rax+20h], r10
0x18017212d  mov     r10, qword ptr [rbp+var_38]
0x180172131  jmp     short loc_180172137
0x180172133  mov     qword ptr [rbp+var_38], r10
0x180172137  mov     rax, [rbx+0A0h]
0x18017213e  mov     qword ptr [rbp+var_38+8], rax
0x180172142  mov     [rbx+98h], r14
0x180172149  mov     [rbx+0A0h], r14
0x180172150  jmp     short loc_180172156
0x180172152  mov     r10, qword ptr [rbp+var_38]
0x180172156  test    r10, r10
0x180172159  jz      short loc_1801721B8
0x18017215b  mov     rcx, r10
0x18017215e  mov     rax, r10
0x180172161  mov     rdx, r10
0x180172164  test    rax, rax
0x180172167  jz      short loc_18017217F
0x180172169  mov     rax, [rdx+20h]
0x18017216d  mov     qword ptr [rbp+var_38], rax
0x180172171  neg     rax
0x180172174  sbb     rax, rax
0x180172177  and     qword ptr [rbp+var_38+8], rax
0x18017217b  mov     [rcx+20h], r14
0x18017217f  lock dec dword ptr [rbx+38h]
0x180172183  xorps   xmm0, xmm0
0x180172186  movups  [rbp+var_50], xmm0
0x18017218a  mov     [rbp+var_40], r14
0x18017218e  xor     r9d, r9d
0x180172191  lea     r8, [rbp+var_50]
0x180172195  mov     rdx, r10
0x180172198  xor     ecx, ecx
0x18017219a  mov     rax, [r10+28h]
0x18017219e  call    cs:__guard_dispatch_icall_fptr
0x1801721a4  mov     r10, qword ptr [rbp+var_38]
0x1801721a8  mov     rax, r10
0x1801721ab  mov     rdx, r10
0x1801721ae  mov     rcx, r10
0x1801721b1  test    r10, r10
0x1801721b4  jnz     short loc_180172164
0x1801721b6  jmp     short loc_18017220E
0x1801721b8  mov     [rbp+NumberOfBytesTransferred], r14d
0x1801721bc  mov     [rbp+CompletionKey], r14
0x1801721c0  mov     qword ptr [rbp+DueTime], r14
0x1801721c4  mov     eax, [rbx+48h]
0x1801721c7  mov     dword ptr [rsp+80h+lpArgToCompletionRoutine], eax; dwMilliseconds
0x1801721cb  lea     r9, [rbp+DueTime]; lpOverlapped
0x1801721cf  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x1801721d3  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1801721d7  mov     rcx, [rbx+30h]; CompletionPort
0x1801721db  call    cs:__imp_GetQueuedCompletionStatus
0x1801721e1  cmp     qword ptr [rbp+DueTime], r14
0x1801721e5  jz      short loc_18017220E
0x1801721e7  lock dec dword ptr [rbx+38h]
0x1801721eb  xorps   xmm0, xmm0
0x1801721ee  movups  [rbp+var_50], xmm0
0x1801721f2  mov     [rbp+var_40], r14
0x1801721f6  mov     rdx, qword ptr [rbp+DueTime]
0x1801721fa  mov     rax, [rdx+28h]
0x1801721fe  xor     r9d, r9d
0x180172201  lea     r8, [rbp+var_50]
0x180172205  xor     ecx, ecx
0x180172207  call    cs:__guard_dispatch_icall_fptr
0x18017220d  nop
0x18017220e  mov     r10, qword ptr [rbp+var_38]
0x180172212  test    r10, r10
0x180172215  jz      short loc_180172263
0x180172217  mov     rcx, r10
0x18017221a  mov     rax, r10
0x18017221d  mov     rax, [rax+20h]
0x180172221  mov     qword ptr [rbp+var_38], rax
0x180172225  neg     rax
0x180172228  sbb     rax, rax
0x18017222b  and     qword ptr [rbp+var_38+8], rax
0x18017222f  mov     [rcx+20h], r14
0x180172233  xorps   xmm0, xmm0
0x180172236  movups  [rbp+var_50], xmm0
0x18017223a  mov     [rbp+var_40], r14
0x18017223e  xor     r9d, r9d
0x180172241  lea     r8, [rbp+var_50]
0x180172245  mov     rdx, r10
0x180172248  xor     ecx, ecx
0x18017224a  mov     rax, [r10+28h]
0x18017224e  call    cs:__guard_dispatch_icall_fptr
0x180172254  mov     r10, qword ptr [rbp+var_38]
0x180172258  mov     rax, r10
0x18017225b  mov     rcx, r10
0x18017225e  test    r10, r10
0x180172261  jnz     short loc_18017221D
0x180172263  mov     eax, r14d
0x180172266  lock xadd [rbx+38h], eax
0x18017226b  test    eax, eax
0x18017226d  jg      loc_1801720E6
0x180172273  lea     rcx, [rbx+50h]; this
0x180172277  call    ?join@win_thread@detail@asio@boost@@QEAAXXZ; boost::asio::detail::win_thread::join(void)
0x18017227c  mov     rcx, [rbp+var_10]
0x180172280  xor     rcx, rsp; StackCookie
0x180172283  call    __security_check_cookie
0x180172288  lea     r11, [rsp+80h+var_s0]
0x180172290  mov     rbx, [r11+28h]
0x180172294  mov     rsi, [r11+30h]
0x180172298  mov     rsp, r11
0x18017229b  pop     r14
0x18017229d  pop     rdi
0x18017229e  pop     rbp
0x18017229f  retn
```
