# boost::asio::detail::win_thread::join(void)

- ea: `0x18016f00c`
- end: `0x18016f0e8`
- name: `?join@win_thread@detail@asio@boost@@QEAAXXZ`
- size: `220`
- prototype: `void __fastcall(boost::asio::detail::win_thread *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180165120`
- `0x18016583c`
- `0x1801659dc`
- `0x18016d500`
- `0x18016f980`
- `0x180171db0`
- `0x180171e50`
- `0x180172050`

## callees

- `0x18016f00c`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18016f068`
- `KERNEL32!CloseHandle` at `0x18016f0b8`
- `KERNEL32!CloseHandle` at `0x18016f068`
- `KERNEL32!CloseHandle` at `0x18016f0b8`
- `KERNEL32!WaitForSingleObject` at `0x18016f0ab`
- `KERNEL32!WaitForSingleObject` at `0x18016f0ab`
- `KERNEL32!WaitForMultipleObjects` at `0x18016f05b`
- `KERNEL32!WaitForMultipleObjects` at `0x18016f05b`
- `KERNEL32!QueueUserAPC` at `0x18016f09b`
- `KERNEL32!QueueUserAPC` at `0x18016f09b`
- `KERNEL32!TerminateThread` at `0x18016f085`
- `KERNEL32!TerminateThread` at `0x18016f085`

## pseudocode

```c
void __fastcall boost::asio::detail::win_thread::join(boost::asio::detail::win_thread *this)
{
  __int64 v2; // rcx
  signed __int32 v3; // eax
  __int64 v4; // rcx
  HANDLE Handles[2]; // [rsp+20h] [rbp-28h] BYREF

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    Handles[0] = *(HANDLE *)(v2 + 24);
    Handles[1] = *(HANDLE *)(v2 + 8);
    WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    CloseHandle(*(HANDLE *)(*(_QWORD *)this + 24LL));
    v3 = _InterlockedExchangeAdd(
           &boost::asio::detail::win_thread_base<boost::asio::detail::win_thread>::terminate_threads_,
           0);
    v4 = *(_QWORD *)this;
    if ( v3 )
    {
      TerminateThread(*(HANDLE *)(v4 + 8), 0);
    }
    else
    {
      QueueUserAPC(
        boost::io::detail::call_put_head<char,std::char_traits<char>,std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const>,
        *(HANDLE *)(v4 + 8),
        0);
      WaitForSingleObject(*(HANDLE *)(*(_QWORD *)this + 8LL), 0xFFFFFFFF);
    }
    CloseHandle(*(HANDLE *)(*(_QWORD *)this + 8LL));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18016f00c  push    rbx
0x18016f00e  mov     eax, 40h
0x18016f013  call    _alloca_probe
0x18016f018  sub     rsp, rax
0x18016f01b  mov     rax, cs:__security_cookie
0x18016f022  xor     rax, rsp
0x18016f025  mov     [rsp+48h+var_18], rax
0x18016f02a  mov     rbx, rcx
0x18016f02d  mov     rcx, [rcx]
0x18016f030  test    rcx, rcx
0x18016f033  jz      loc_18016F0D5
0x18016f039  mov     rax, [rcx+18h]
0x18016f03d  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18016f042  xor     r8d, r8d; bWaitAll
0x18016f045  mov     [rsp+48h+Handles], rax
0x18016f04a  mov     rax, [rcx+8]
0x18016f04e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18016f052  mov     [rsp+48h+var_20], rax
0x18016f057  lea     ecx, [r8+2]; nCount
0x18016f05b  call    cs:__imp_WaitForMultipleObjects
0x18016f061  mov     rcx, [rbx]
0x18016f064  mov     rcx, [rcx+18h]; hObject
0x18016f068  call    cs:__imp_CloseHandle
0x18016f06e  xor     eax, eax
0x18016f070  lock xadd cs:?terminate_threads_@?$win_thread_base@Vwin_thread@detail@asio@boost@@@detail@asio@boost@@0JA, eax; long boost::asio::detail::win_thread_base<boost::asio::detail::win_thread>::terminate_threads_
0x18016f078  mov     rcx, [rbx]
0x18016f07b  test    eax, eax
0x18016f07d  jz      short loc_18016F08D
0x18016f07f  mov     rcx, [rcx+8]; hThread
0x18016f083  xor     edx, edx; dwExitCode
0x18016f085  call    cs:__imp_TerminateThread
0x18016f08b  jmp     short loc_18016F0B1
0x18016f08d  mov     rdx, [rcx+8]; hThread
0x18016f091  xor     r8d, r8d; dwData
0x18016f094  lea     rcx, ??$call_put_head@DU?$char_traits@D@std@@$$CBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@2@@detail@io@boost@@YAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEBX@Z; pfnAPC
0x18016f09b  call    cs:__imp_QueueUserAPC
0x18016f0a1  mov     rcx, [rbx]
0x18016f0a4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18016f0a7  mov     rcx, [rcx+8]; hHandle
0x18016f0ab  call    cs:__imp_WaitForSingleObject
0x18016f0b1  mov     rcx, [rbx]
0x18016f0b4  mov     rcx, [rcx+8]; hObject
0x18016f0b8  call    cs:__imp_CloseHandle
0x18016f0be  mov     rcx, [rbx]
0x18016f0c1  mov     rax, [rcx]
0x18016f0c4  mov     rax, [rax+10h]
0x18016f0c8  call    cs:__guard_dispatch_icall_fptr
0x18016f0ce  mov     qword ptr [rbx], 0
0x18016f0d5  mov     rcx, [rsp+48h+var_18]
0x18016f0da  xor     rcx, rsp; StackCookie
0x18016f0dd  call    __security_check_cookie
0x18016f0e2  add     rsp, 40h
0x18016f0e6  pop     rbx
0x18016f0e7  retn
```
