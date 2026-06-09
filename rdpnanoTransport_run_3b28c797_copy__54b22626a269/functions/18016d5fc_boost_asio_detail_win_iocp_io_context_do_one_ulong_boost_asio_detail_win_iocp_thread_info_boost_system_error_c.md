# boost::asio::detail::win_iocp_io_context::do_one(ulong,boost::asio::detail::win_iocp_thread_info &,boost::system::error_code &)

- ea: `0x18016d5fc`
- end: `0x18016d9ff`
- name: `?do_one@win_iocp_io_context@detail@asio@boost@@AEAA_KKAEAUwin_iocp_thread_info@234@AEAVerror_code@system@4@@Z`
- size: `1027`
- prototype: `unsigned __int64 __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this, unsigned int, struct boost::asio::detail::win_iocp_thread_info *, struct boost::system::error_code *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801714ac`
- `0x180181640`

## callees

- `0x180163f50`
- `0x18016d5fc`
- `0x18017105c`
- `0x180172d58`
- `0x180173d90`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18016d81d`
- `KERNEL32!GetLastError` at `0x18016d9d0`
- `KERNEL32!GetLastError` at `0x18016d81d`
- `KERNEL32!GetLastError` at `0x18016d9d0`
- `KERNEL32!SetLastError` at `0x18016d7f0`
- `KERNEL32!SetLastError` at `0x18016d7f0`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18016d814`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18016d814`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016d6fe`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016d9c6`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016d6fe`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016d9c6`
- `KERNEL32!EnterCriticalSection` at `0x18016d65d`
- `KERNEL32!EnterCriticalSection` at `0x18016d70b`
- `KERNEL32!EnterCriticalSection` at `0x18016d65d`
- `KERNEL32!EnterCriticalSection` at `0x18016d70b`
- `KERNEL32!LeaveCriticalSection` at `0x18016d761`
- `KERNEL32!LeaveCriticalSection` at `0x18016d7dd`
- `KERNEL32!LeaveCriticalSection` at `0x18016d761`
- `KERNEL32!LeaveCriticalSection` at `0x18016d7dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall boost::asio::detail::win_iocp_io_context::do_one(
        boost::asio::detail::win_iocp_io_context *this,
        DWORD a2,
        struct boost::asio::detail::win_iocp_thread_info *a3,
        struct boost::system::error_code *a4)
{
  HANDLE *v7; // r12
  _QWORD *i; // rsi
  LPOVERLAPPED v9; // rsi
  LPOVERLAPPED v10; // rcx
  LPOVERLAPPED v11; // rax
  __int64 v12; // rax
  LPOVERLAPPED v13; // r10
  LPOVERLAPPED v14; // rcx
  LPOVERLAPPED v15; // rax
  DWORD dwMilliseconds; // eax
  BOOL QueuedCompletionStatus; // r15d
  DWORD LastError; // eax
  LPOVERLAPPED v19; // rsi
  __int64 v20; // rax
  void ***v21; // rax
  DWORD v22; // eax
  __int64 v24; // rax
  HANDLE *v25; // [rsp+30h] [rbp-79h]
  _BYTE v27[24]; // [rsp+58h] [rbp-51h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp-39h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+78h] [rbp-31h] BYREF
  LPOVERLAPPED lpOverlapped[2]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v31; // [rsp+90h] [rbp-19h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-9h]
  unsigned __int64 CompletionKey; // [rsp+A8h] [rbp-1h] BYREF

  v7 = (HANDLE *)((char *)this + 48);
  v25 = (HANDLE *)((char *)this + 48);
  do
  {
    while ( 1 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 24, 0, 1) == 1 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
        *(_OWORD *)lpOverlapped = 0;
        if ( *((_QWORD *)this + 19) )
        {
          lpOverlapped[0] = *((LPOVERLAPPED *)this + 19);
          lpOverlapped[1] = *((LPOVERLAPPED *)this + 20);
          *((_QWORD *)this + 19) = 0;
          *((_QWORD *)this + 20) = 0;
        }
        for ( i = (_QWORD *)*((_QWORD *)this + 18); i; i = (_QWORD *)i[1] )
          (*(void (__fastcall **)(_QWORD *, LPOVERLAPPED *))(*i + 32LL))(i, lpOverlapped);
        v9 = lpOverlapped[0];
        if ( lpOverlapped[0] )
        {
          v10 = lpOverlapped[0];
          v11 = lpOverlapped[0];
          v7 = v25;
          do
          {
            lpOverlapped[0] = (LPOVERLAPPED)v11[1].Internal;
            lpOverlapped[1] = (LPOVERLAPPED)((unsigned __int64)lpOverlapped[1] & -(__int64)(lpOverlapped[0] != 0));
            v10[1].Internal = 0;
            v9[1].Offset = 1;
            if ( !PostQueuedCompletionStatus(*v25, 0, 0, v9) )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
              v9[1].Internal = 0;
              v12 = *((_QWORD *)this + 20);
              if ( v12 )
                *(_QWORD *)(v12 + 32) = v9;
              else
                *((_QWORD *)this + 19) = v9;
              *((_QWORD *)this + 20) = v9;
              if ( lpOverlapped[0] )
              {
                v9[1].Internal = (ULONG_PTR)lpOverlapped[0];
                *((LPOVERLAPPED *)this + 20) = lpOverlapped[1];
                *(_OWORD *)lpOverlapped = 0;
              }
              _InterlockedExchange((volatile __int32 *)this + 24, 1);
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
            }
            v9 = lpOverlapped[0];
            v11 = lpOverlapped[0];
            v10 = lpOverlapped[0];
          }
          while ( lpOverlapped[0] );
        }
        boost::asio::detail::win_iocp_io_context::update_timeout(this);
        v13 = lpOverlapped[0];
        if ( lpOverlapped[0] )
        {
          v14 = lpOverlapped[0];
          v15 = lpOverlapped[0];
          do
          {
            lpOverlapped[0] = (LPOVERLAPPED)v15[1].Internal;
            lpOverlapped[1] = (LPOVERLAPPED)((unsigned __int64)lpOverlapped[1] & -(__int64)(lpOverlapped[0] != 0));
            v14[1].Internal = 0;
            v31 = 0;
            v32 = 0;
            ((void (__fastcall *)(_QWORD, LPOVERLAPPED, __int128 *, _QWORD))v13[1].InternalHigh)(0, v13, &v31, 0);
            v13 = lpOverlapped[0];
            v15 = lpOverlapped[0];
            v14 = lpOverlapped[0];
          }
          while ( lpOverlapped[0] );
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      }
      NumberOfBytesTransferred = 0;
      CompletionKey = 0;
      Overlapped = 0;
      SetLastError(0);
      dwMilliseconds = *((_DWORD *)this + 18);
      if ( a2 < dwMilliseconds )
        dwMilliseconds = a2;
      QueuedCompletionStatus = GetQueuedCompletionStatus(
                                 *v7,
                                 &NumberOfBytesTransferred,
                                 &CompletionKey,
                                 &Overlapped,
                                 dwMilliseconds);
      LastError = GetLastError();
      v19 = Overlapped;
      if ( Overlapped )
        break;
      if ( QueuedCompletionStatus )
      {
        if ( CompletionKey != 1 )
        {
          _InterlockedExchange((volatile __int32 *)this + 16, (__int32)Overlapped);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 15, 0) )
          {
            if ( _InterlockedExchange((volatile __int32 *)this + 16, 1)
              || PostQueuedCompletionStatus(*((HANDLE *)this + 6), 0, 0, 0) )
            {
LABEL_42:
              *(_OWORD *)a4 = 0;
              v32 = 0;
              *((_QWORD *)a4 + 2) = 0;
            }
            else
            {
              LastError = GetLastError();
LABEL_49:
              v24 = boost::system::error_code::error_code(
                      (boost::system::error_code *)v27,
                      LastError,
                      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
              *(_OWORD *)a4 = *(_OWORD *)v24;
              *((_QWORD *)a4 + 2) = *(_QWORD *)(v24 + 16);
            }
            return 0;
          }
        }
      }
      else
      {
        if ( LastError != 258 )
          goto LABEL_49;
        if ( a2 != -1 )
          goto LABEL_42;
      }
    }
    boost::system::error_code::error_code(
      (boost::system::error_code *)&v31,
      LastError,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    if ( CompletionKey == 2 )
    {
      v20 = boost::system::error_code::error_code(
              (boost::system::error_code *)v27,
              v19->Offset,
              (const struct boost::system::error_category *)v19->Internal);
      v31 = *(_OWORD *)v20;
      v32 = *(_QWORD *)(v20 + 16);
      NumberOfBytesTransferred = v19->OffsetHigh;
    }
    else
    {
      if ( v32 )
      {
        v21 = &boost::system::detail::interop_cat_holder<void>::instance;
        if ( v32 != 1 )
          v21 = (void ***)*((_QWORD *)&v31 + 1);
      }
      else
      {
        v21 = &boost::system::detail::system_cat_holder<void>::instance;
      }
      v19->Internal = (ULONG_PTR)v21;
      if ( v32 == 1 )
        v22 = v31 + 1000 * (*((_QWORD *)&v31 + 1) % 0x1FFFF7uLL);
      else
        v22 = v31;
      v19->Offset = v22;
      v19->OffsetHigh = NumberOfBytesTransferred;
    }
  }
  while ( _InterlockedCompareExchange((volatile signed __int32 *)&v19[1].16, 1, 0) != 1 );
  ((void (__fastcall *)(boost::asio::detail::win_iocp_io_context *, LPOVERLAPPED, __int128 *, _QWORD))v19[1].InternalHigh)(
    this,
    v19,
    &v31,
    NumberOfBytesTransferred);
  boost::asio::detail::thread_info_base::rethrow_pending_exception(a3);
  *(_OWORD *)a4 = 0;
  *((_QWORD *)a4 + 2) = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0xFFFFFFFF) == 1 )
    boost::asio::detail::win_iocp_io_context::stop(this);
  return 1;
}

```

## disassembly

```asm
0x18016d5fc  push    rbp
0x18016d5fe  push    rbx
0x18016d5ff  push    rsi
0x18016d600  push    rdi
0x18016d601  push    r12
0x18016d603  push    r13
0x18016d605  push    r14
0x18016d607  push    r15
0x18016d609  lea     rbp, [rsp-1Fh]
0x18016d60e  mov     eax, 0C8h
0x18016d613  call    _alloca_probe
0x18016d618  sub     rsp, rax
0x18016d61b  mov     rax, cs:__security_cookie
0x18016d622  xor     rax, rsp
0x18016d625  mov     [rbp+57h+var_50], rax
0x18016d629  mov     r14, r9
0x18016d62c  mov     [rbp+57h+var_C8], r8
0x18016d630  mov     r13d, edx
0x18016d633  mov     rbx, rcx
0x18016d636  lea     r12, [rcx+30h]
0x18016d63a  mov     [rbp+57h+var_D0], r12
0x18016d63e  mov     edi, 1
0x18016d643  xor     esi, esi
0x18016d645  mov     eax, edi
0x18016d647  lock cmpxchg [rbx+60h], esi
0x18016d64c  jnz     loc_18016D7E3
0x18016d652  lea     r15, [rbx+68h]
0x18016d656  mov     [rbp+57h+var_C0], r15
0x18016d65a  mov     rcx, r15; lpCriticalSection
0x18016d65d  call    cs:__imp_EnterCriticalSection
0x18016d663  mov     [rbp+57h+var_B8], dil
0x18016d667  xorps   xmm1, xmm1
0x18016d66a  movdqu  xmmword ptr [rbp+57h+lpOverlapped], xmm1
0x18016d66f  mov     rax, [rbx+98h]
0x18016d676  test    rax, rax
0x18016d679  jz      short loc_18016D698
0x18016d67b  mov     [rbp+57h+lpOverlapped], rax
0x18016d67f  mov     rax, [rbx+0A0h]
0x18016d686  mov     [rbp+57h+lpOverlapped+8], rax
0x18016d68a  mov     [rbx+98h], rsi
0x18016d691  mov     [rbx+0A0h], rsi
0x18016d698  mov     rsi, [rbx+90h]
0x18016d69f  jmp     short loc_18016D6B9
0x18016d6a1  mov     rax, [rsi]
0x18016d6a4  lea     rdx, [rbp+57h+lpOverlapped]
0x18016d6a8  mov     rcx, rsi
0x18016d6ab  mov     rax, [rax+20h]
0x18016d6af  call    cs:__guard_dispatch_icall_fptr
0x18016d6b5  mov     rsi, [rsi+8]
0x18016d6b9  test    rsi, rsi
0x18016d6bc  jnz     short loc_18016D6A1
0x18016d6be  mov     rsi, [rbp+57h+lpOverlapped]
0x18016d6c2  test    rsi, rsi
0x18016d6c5  jz      loc_18016D77A
0x18016d6cb  mov     rcx, rsi
0x18016d6ce  mov     rax, rsi
0x18016d6d1  mov     r12, [rbp+57h+var_D0]
0x18016d6d5  mov     rax, [rax+20h]
0x18016d6d9  mov     [rbp+57h+lpOverlapped], rax
0x18016d6dd  neg     rax
0x18016d6e0  sbb     rax, rax
0x18016d6e3  and     [rbp+57h+lpOverlapped+8], rax
0x18016d6e7  mov     qword ptr [rcx+20h], 0
0x18016d6ef  mov     [rsi+30h], edi
0x18016d6f2  mov     r9, rsi; lpOverlapped
0x18016d6f5  xor     r8d, r8d; dwCompletionKey
0x18016d6f8  xor     edx, edx; dwNumberOfBytesTransferred
0x18016d6fa  mov     rcx, [r12]; CompletionPort
0x18016d6fe  call    cs:__imp_PostQueuedCompletionStatus
0x18016d704  test    eax, eax
0x18016d706  jnz     short loc_18016D767
0x18016d708  mov     rcx, r15; lpCriticalSection
0x18016d70b  call    cs:__imp_EnterCriticalSection
0x18016d711  mov     qword ptr [rsi+20h], 0
0x18016d719  mov     rax, [rbx+0A0h]
0x18016d720  test    rax, rax
0x18016d723  jz      short loc_18016D72B
0x18016d725  mov     [rax+20h], rsi
0x18016d729  jmp     short loc_18016D732
0x18016d72b  mov     [rbx+98h], rsi
0x18016d732  mov     [rbx+0A0h], rsi
0x18016d739  mov     rax, [rbp+57h+lpOverlapped]
0x18016d73d  test    rax, rax
0x18016d740  jz      short loc_18016D759
0x18016d742  mov     [rsi+20h], rax
0x18016d746  mov     rax, [rbp+57h+lpOverlapped+8]
0x18016d74a  mov     [rbx+0A0h], rax
0x18016d751  xorps   xmm0, xmm0
0x18016d754  movdqu  xmmword ptr [rbp+57h+lpOverlapped], xmm0
0x18016d759  mov     eax, edi
0x18016d75b  xchg    eax, [rbx+60h]
0x18016d75e  mov     rcx, r15; lpCriticalSection
0x18016d761  call    cs:__imp_LeaveCriticalSection
0x18016d767  mov     rsi, [rbp+57h+lpOverlapped]
0x18016d76b  mov     rax, rsi
0x18016d76e  mov     rcx, rsi
0x18016d771  test    rsi, rsi
0x18016d774  jnz     loc_18016D6D5
0x18016d77a  mov     rcx, rbx; this
0x18016d77d  call    ?update_timeout@win_iocp_io_context@detail@asio@boost@@AEAAXXZ; boost::asio::detail::win_iocp_io_context::update_timeout(void)
0x18016d782  nop
0x18016d783  mov     r10, [rbp+57h+lpOverlapped]
0x18016d787  xor     esi, esi
0x18016d789  test    r10, r10
0x18016d78c  jz      short loc_18016D7DA
0x18016d78e  mov     rcx, r10
0x18016d791  mov     rax, r10
0x18016d794  mov     rax, [rax+20h]
0x18016d798  mov     [rbp+57h+lpOverlapped], rax
0x18016d79c  neg     rax
0x18016d79f  sbb     rax, rax
0x18016d7a2  and     [rbp+57h+lpOverlapped+8], rax
0x18016d7a6  mov     [rcx+20h], rsi
0x18016d7aa  xorps   xmm0, xmm0
0x18016d7ad  movups  [rbp+57h+var_70], xmm0
0x18016d7b1  mov     [rbp+57h+var_60], rsi
0x18016d7b5  xor     r9d, r9d
0x18016d7b8  lea     r8, [rbp+57h+var_70]
0x18016d7bc  mov     rdx, r10
0x18016d7bf  xor     ecx, ecx
0x18016d7c1  mov     rax, [r10+28h]
0x18016d7c5  call    cs:__guard_dispatch_icall_fptr
0x18016d7cb  mov     r10, [rbp+57h+lpOverlapped]
0x18016d7cf  mov     rax, r10
0x18016d7d2  mov     rcx, r10
0x18016d7d5  test    r10, r10
0x18016d7d8  jnz     short loc_18016D794
0x18016d7da  mov     rcx, r15; lpCriticalSection
0x18016d7dd  call    cs:__imp_LeaveCriticalSection
0x18016d7e3  mov     [rbp+57h+NumberOfBytesTransferred], esi
0x18016d7e6  mov     [rbp+57h+CompletionKey], rsi
0x18016d7ea  mov     [rbp+57h+Overlapped], rsi
0x18016d7ee  xor     ecx, ecx; dwErrCode
0x18016d7f0  call    cs:__imp_SetLastError
0x18016d7f6  mov     eax, [rbx+48h]
0x18016d7f9  cmp     r13d, eax
0x18016d7fc  cmovb   eax, r13d
0x18016d800  mov     [rsp+100h+dwMilliseconds], eax; dwMilliseconds
0x18016d804  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x18016d808  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x18016d80c  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18016d810  mov     rcx, [r12]; CompletionPort
0x18016d814  call    cs:__imp_GetQueuedCompletionStatus
0x18016d81a  mov     r15d, eax
0x18016d81d  call    cs:__imp_GetLastError
0x18016d823  mov     rsi, [rbp+57h+Overlapped]
0x18016d827  test    rsi, rsi
0x18016d82a  jz      loc_18016D943
0x18016d830  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x18016d837  mov     edx, eax; int
0x18016d839  lea     rcx, [rbp+57h+var_70]; this
0x18016d83d  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x18016d842  cmp     [rbp+57h+CompletionKey], 2
0x18016d847  jnz     short loc_18016D871
0x18016d849  mov     r8, [rsi]; struct boost::system::error_category *
0x18016d84c  mov     edx, [rsi+10h]; int
0x18016d84f  lea     rcx, [rbp+57h+var_A8]; this
0x18016d853  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x18016d858  movups  xmm0, xmmword ptr [rax]
0x18016d85b  movups  [rbp+57h+var_70], xmm0
0x18016d85f  movsd   xmm1, qword ptr [rax+10h]
0x18016d864  movsd   [rbp+57h+var_60], xmm1
0x18016d869  mov     eax, [rsi+14h]
0x18016d86c  mov     [rbp+57h+NumberOfBytesTransferred], eax
0x18016d86f  jmp     short loc_18016D8DB
0x18016d871  mov     rcx, [rbp+57h+var_60]
0x18016d875  test    rcx, rcx
0x18016d878  jnz     short loc_18016D883
0x18016d87a  lea     rax, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; boost::system::detail::system_error_category const boost::system::detail::system_cat_holder<void>::instance
0x18016d881  jmp     short loc_18016D892
0x18016d883  lea     rax, ?instance@?$interop_cat_holder@X@detail@system@boost@@2Vinterop_error_category@234@B; boost::system::detail::interop_error_category const boost::system::detail::interop_cat_holder<void>::instance
0x18016d88a  cmp     rcx, rdi
0x18016d88d  cmovnz  rax, qword ptr [rbp+57h+var_70+8]
0x18016d892  mov     [rsi], rax
0x18016d895  cmp     [rbp+57h+var_60], rdi
0x18016d899  jz      short loc_18016D8A0
0x18016d89b  mov     eax, dword ptr [rbp+57h+var_70]
0x18016d89e  jmp     short loc_18016D8D2
0x18016d8a0  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x18016d8a4  mov     rax, 4800144005B3h
0x18016d8ae  mul     rcx
0x18016d8b1  mov     rax, rcx
0x18016d8b4  sub     rax, rdx
0x18016d8b7  shr     rax, 1
0x18016d8ba  add     rax, rdx
0x18016d8bd  shr     rax, 14h
0x18016d8c1  imul    eax, 1FFFF7h
0x18016d8c7  sub     ecx, eax
0x18016d8c9  imul    eax, ecx, 3E8h
0x18016d8cf  add     eax, dword ptr [rbp+57h+var_70]
0x18016d8d2  mov     [rsi+10h], eax
0x18016d8d5  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x18016d8d8  mov     [rsi+14h], eax
0x18016d8db  xor     eax, eax
0x18016d8dd  lock cmpxchg [rsi+30h], edi
0x18016d8e2  cmp     eax, edi
0x18016d8e4  jnz     loc_18016D643
0x18016d8ea  mov     [rbp+57h+var_D0], rbx
0x18016d8ee  mov     r9d, [rbp+57h+NumberOfBytesTransferred]
0x18016d8f2  lea     r8, [rbp+57h+var_70]
0x18016d8f6  mov     rdx, rsi
0x18016d8f9  mov     rcx, rbx
0x18016d8fc  mov     rax, [rsi+28h]
0x18016d900  call    cs:__guard_dispatch_icall_fptr
0x18016d906  mov     rcx, [rbp+57h+var_C8]; this
0x18016d90a  call    ?rethrow_pending_exception@thread_info_base@detail@asio@boost@@QEAAXXZ; boost::asio::detail::thread_info_base::rethrow_pending_exception(void)
0x18016d90f  xorps   xmm0, xmm0
0x18016d912  mov     [rbp+57h+var_B0], 0
0x18016d91a  movups  xmmword ptr [r14], xmm0
0x18016d91e  movsd   xmm0, [rbp+57h+var_B0]
0x18016d923  movsd   qword ptr [r14+10h], xmm0
0x18016d929  or      edx, 0FFFFFFFFh
0x18016d92c  lock xadd [rbx+38h], edx
0x18016d931  cmp     edx, 1
0x18016d934  jnz     short loc_18016D93E
0x18016d936  mov     rcx, rbx; this
0x18016d939  call    ?stop@win_iocp_io_context@detail@asio@boost@@QEAAXXZ; boost::asio::detail::win_iocp_io_context::stop(void)
0x18016d93e  mov     rax, rdi
0x18016d941  jmp     short loc_18016D975
0x18016d943  test    r15d, r15d
0x18016d946  jnz     short loc_18016D995
0x18016d948  cmp     eax, 102h
0x18016d94d  jnz     loc_18016D9D6
0x18016d953  cmp     r13d, 0FFFFFFFFh
0x18016d957  jz      loc_18016D645
0x18016d95d  xorps   xmm0, xmm0
0x18016d960  movups  xmmword ptr [r14], xmm0
0x18016d964  mov     [rbp+57h+var_60], rsi
0x18016d968  movsd   xmm0, [rbp+57h+var_60]
0x18016d96d  movsd   qword ptr [r14+10h], xmm0
0x18016d973  xor     eax, eax
0x18016d975  mov     rcx, [rbp+57h+var_50]
0x18016d979  xor     rcx, rsp; StackCookie
0x18016d97c  call    __security_check_cookie
0x18016d981  add     rsp, 0C8h
0x18016d988  pop     r15
0x18016d98a  pop     r14
0x18016d98c  pop     r13
0x18016d98e  pop     r12
0x18016d990  pop     rdi
0x18016d991  pop     rsi
0x18016d992  pop     rbx
0x18016d993  pop     rbp
0x18016d994  retn
0x18016d995  cmp     [rbp+57h+CompletionKey], rdi
0x18016d999  jz      loc_18016D645
0x18016d99f  mov     eax, esi
0x18016d9a1  xchg    eax, [rbx+40h]
0x18016d9a4  mov     eax, esi
0x18016d9a6  lock xadd [rbx+3Ch], eax
0x18016d9ab  test    eax, eax
0x18016d9ad  jz      loc_18016D645
0x18016d9b3  xchg    edi, [rbx+40h]
0x18016d9b6  test    edi, edi
0x18016d9b8  jnz     short loc_18016D95D
0x18016d9ba  xor     r9d, r9d; lpOverlapped
0x18016d9bd  xor     r8d, r8d; dwCompletionKey
0x18016d9c0  xor     edx, edx; dwNumberOfBytesTransferred
0x18016d9c2  mov     rcx, [rbx+30h]; CompletionPort
0x18016d9c6  call    cs:__imp_PostQueuedCompletionStatus
0x18016d9cc  test    eax, eax
0x18016d9ce  jnz     short loc_18016D95D
0x18016d9d0  call    cs:__imp_GetLastError
0x18016d9d6  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x18016d9dd  mov     edx, eax; int
0x18016d9df  lea     rcx, [rbp+57h+var_A8]; this
0x18016d9e3  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x18016d9e8  movups  xmm0, xmmword ptr [rax]
0x18016d9eb  movups  xmmword ptr [r14], xmm0
0x18016d9ef  movsd   xmm1, qword ptr [rax+10h]
0x18016d9f4  movsd   qword ptr [r14+10h], xmm1
0x18016d9fa  jmp     loc_18016D973
```
