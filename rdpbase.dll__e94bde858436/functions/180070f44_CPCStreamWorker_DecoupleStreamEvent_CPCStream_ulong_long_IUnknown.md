# CPCStreamWorker::DecoupleStreamEvent(CPCStream *,ulong,long,IUnknown *)

- ea: `0x180070f44`
- end: `0x1800711c0`
- name: `?DecoupleStreamEvent@CPCStreamWorker@@QEAAJPEAVCPCStream@@KJPEAUIUnknown@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(CPCStreamWorker *__hidden this, struct CPCStream *, unsigned int, int, struct IUnknown *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1801050e0`
- `0x180105208`
- `0x1801053fc`
- `0x1801058f0`

## callees

- `0x18001cc3c`
- `0x18004298c`
- `0x180046a84`
- `0x180070f44`
- `0x1800711c8`
- `0x1800787d4`
- `0x180108308`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800710b6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800710b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180071117`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180071117`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070ffa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007113f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007113f`

## string_xrefs

- `0x180071103`: `hThread`

## pseudocode

```c
__int64 __fastcall CPCStreamWorker::DecoupleStreamEvent(
        CPCStreamWorker *this,
        struct CPCStream *a2,
        int a3,
        __int64 a4,
        struct IUnknown *a5)
{
  struct CPCStream *v5; // rbx
  struct CPCStream *v6; // rbp
  struct CPCStream **v9; // rax
  struct CPCStream **v10; // rsi
  signed int v11; // edi
  struct IUnknown *v12; // rax
  struct CPCStream *EventW; // r14
  HANDLE v14; // r15
  signed int v15; // eax
  char v16; // bl
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v18; // edx
  const char *v19; // rcx
  signed int v20; // eax
  unsigned int v21; // edx
  signed int LastError; // eax
  unsigned int v23; // eax
  struct CPCStream *v25; // [rsp+60h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  v25 = 0;
  ThreadId = 0;
  if ( a2 )
  {
    TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v25);
    v5 = a2;
    v25 = a2;
    TCntPtr<CRdpUdpConnection>::SafeAddRef(&v25);
    v6 = a2;
  }
  v9 = (struct CPCStream **)operator new(0x20u);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v11 = v9 == 0 ? 0x8007000E : 0;
    if ( v6 != *v9 )
    {
      TCntPtr<SlidingStats<double,5,1>>::SafeRelease(v9);
      *v10 = v5;
      TCntPtr<CRdpUdpConnection>::SafeAddRef(v10);
    }
    v12 = a5;
    *((_DWORD *)v10 + 2) = a3;
    *((_DWORD *)v10 + 3) = 0;
    v10[2] = (struct CPCStream *)v12;
    EventW = (struct CPCStream *)CreateEventW(0, 1, 0, 0);
    if ( EventW )
    {
      v10[3] = EventW;
      v14 = CreateThread(0, 0, CPCStreamWorker::STATIC_Fire_Decouple_Notification, v10, 0, &ThreadId);
      if ( v14 )
      {
        WaitForSingleObject(EventW, 0x2710u);
LABEL_24:
        if ( v11 < 0 )
          PC_EVENT_INTERNAL::`scalar deleting destructor'((PC_EVENT_INTERNAL *)v10, v21);
        if ( EventW )
          CloseHandle(EventW);
        if ( v14 )
          CloseHandle(v14);
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v16 = LastError;
        if ( LastError > 0 )
          v16 = LastError;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 12;
        v19 = "hThread";
        goto LABEL_13;
      }
    }
    else
    {
      v14 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v16 = v15;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 11;
        v19 = "hEvent";
LABEL_13:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          (unsigned int)WPP_a22f260487b136bea20259a65a622838_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v19,
          v16);
      }
    }
    v20 = GetLastError();
    v11 = v20;
    if ( v20 > 0 )
      v11 = (unsigned __int16)v20 | 0x80070000;
    goto LABEL_24;
  }
  v11 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_a22f260487b136bea20259a65a622838_Traceguids,
      v23,
      (__int64)"OOM...",
      14);
  }
LABEL_34:
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180070f44  mov     rax, rsp
0x180070f47  mov     [rax+10h], rbx
0x180070f4b  mov     [rax+20h], r9d
0x180070f4f  mov     [rax+8], rcx
0x180070f53  push    rbp
0x180070f54  push    rsi
0x180070f55  push    rdi
0x180070f56  push    r14
0x180070f58  push    r15
0x180070f5a  sub     rsp, 30h
0x180070f5e  xor     ebx, ebx
0x180070f60  xor     ebp, ebp
0x180070f62  mov     [rax+8], rbx
0x180070f66  mov     r14d, r8d
0x180070f69  mov     [rax+20h], ebx
0x180070f6c  mov     rdi, rdx
0x180070f6f  test    rdx, rdx
0x180070f72  jz      short loc_180070F92
0x180070f74  lea     rcx, [rax+8]
0x180070f78  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x180070f7d  mov     rbx, rdi
0x180070f80  lea     rcx, [rsp+58h+arg_0]
0x180070f85  mov     [rsp+58h+arg_0], rbx
0x180070f8a  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x180070f8f  mov     rbp, rdi
0x180070f92  mov     ecx, 20h ; ' '; Size
0x180070f97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070f9c  mov     rsi, rax
0x180070f9f  test    rax, rax
0x180070fa2  jz      loc_180071147
0x180070fa8  mov     rcx, rax
0x180070fab  mov     qword ptr [rax], 0
0x180070fb2  neg     rcx
0x180070fb5  sbb     edi, edi
0x180070fb7  not     edi
0x180070fb9  and     edi, 8007000Eh
0x180070fbf  cmp     rbp, [rax]
0x180070fc2  jz      short loc_180070FD7
0x180070fc4  mov     rcx, rax
0x180070fc7  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x180070fcc  mov     rcx, rsi
0x180070fcf  mov     [rsi], rbx
0x180070fd2  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x180070fd7  mov     rax, [rsp+58h+arg_20]
0x180070fdf  xor     r9d, r9d; lpName
0x180070fe2  xor     r8d, r8d; bInitialState
0x180070fe5  mov     [rsi+8], r14d
0x180070fe9  xor     ecx, ecx; lpEventAttributes
0x180070feb  mov     dword ptr [rsi+0Ch], 0
0x180070ff2  mov     [rsi+10h], rax
0x180070ff6  lea     edx, [r9+1]; bManualReset
0x180070ffa  call    cs:__imp_CreateEventW
0x180071000  mov     r14, rax
0x180071003  test    rax, rax
0x180071006  jnz     loc_180071092
0x18007100c  xor     r15d, r15d
0x18007100f  mov     rdx, cs:WPP_GLOBAL_Control
0x180071016  lea     rcx, WPP_GLOBAL_Control
0x18007101d  mov     ebp, 80070000h
0x180071022  cmp     rdx, rcx
0x180071025  jz      short loc_180071078
0x180071027  test    byte ptr [rdx+1Ch], 8
0x18007102b  jz      short loc_180071078
0x18007102d  cmp     byte ptr [rdx+19h], 2
0x180071031  jb      short loc_180071078
0x180071033  call    cs:__imp_GetLastError
0x180071039  mov     ebx, eax
0x18007103b  test    eax, eax
0x18007103d  jle     short loc_180071044
0x18007103f  movzx   ebx, ax
0x180071042  or      ebx, ebp
0x180071044  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180071049  mov     edx, 0Bh
0x18007104e  lea     rcx, aHevent; "hEvent"
0x180071055  mov     dword ptr [rsp+58h+lpThreadId], ebx
0x180071059  lea     r8, WPP_a22f260487b136bea20259a65a622838_Traceguids
0x180071060  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x180071065  mov     r9d, eax
0x180071068  mov     rcx, cs:WPP_GLOBAL_Control
0x18007106f  mov     rcx, [rcx+10h]
0x180071073  call    WPP_SF_DsD
0x180071078  call    cs:__imp_GetLastError
0x18007107e  mov     edi, eax
0x180071080  test    eax, eax
0x180071082  jle     loc_18007111D
0x180071088  movzx   edi, ax
0x18007108b  or      edi, ebp
0x18007108d  jmp     loc_18007111D
0x180071092  lea     rax, [rsp+58h+ThreadId]
0x180071097  mov     [rsi+18h], r14
0x18007109b  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800710a0  lea     r8, ?STATIC_Fire_Decouple_Notification@CPCStreamWorker@@SAKPEAX@Z; lpStartAddress
0x1800710a7  mov     r9, rsi; lpParameter
0x1800710aa  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800710b2  xor     edx, edx; dwStackSize
0x1800710b4  xor     ecx, ecx; lpThreadAttributes
0x1800710b6  call    cs:__imp_CreateThread
0x1800710bc  mov     r15, rax
0x1800710bf  test    rax, rax
0x1800710c2  jnz     short loc_18007110F
0x1800710c4  mov     rdx, cs:WPP_GLOBAL_Control
0x1800710cb  lea     rcx, WPP_GLOBAL_Control
0x1800710d2  mov     ebp, 80070000h
0x1800710d7  cmp     rdx, rcx
0x1800710da  jz      short loc_180071078
0x1800710dc  test    byte ptr [rdx+1Ch], 8
0x1800710e0  jz      short loc_180071078
0x1800710e2  cmp     byte ptr [rdx+19h], 2
0x1800710e6  jb      short loc_180071078
0x1800710e8  call    cs:__imp_GetLastError
0x1800710ee  mov     ebx, eax
0x1800710f0  test    eax, eax
0x1800710f2  jle     short loc_1800710F9
0x1800710f4  movzx   ebx, ax
0x1800710f7  or      ebx, ebp
0x1800710f9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800710fe  mov     edx, 0Ch
0x180071103  lea     rcx, aHthread; "hThread"
0x18007110a  jmp     loc_180071055
0x18007110f  mov     edx, 2710h; dwMilliseconds
0x180071114  mov     rcx, r14; hHandle
0x180071117  call    cs:__imp_WaitForSingleObject
0x18007111d  test    edi, edi
0x18007111f  jns     short loc_180071129
0x180071121  mov     rcx, rsi; this
0x180071124  call    ??_GPC_EVENT_INTERNAL@@QEAAPEAXI@Z; PC_EVENT_INTERNAL::`scalar deleting destructor'(uint)
0x180071129  test    r14, r14
0x18007112c  jz      short loc_180071137
0x18007112e  mov     rcx, r14; hObject
0x180071131  call    cs:__imp_CloseHandle
0x180071137  test    r15, r15
0x18007113a  jz      short loc_1800711A3
0x18007113c  mov     rcx, r15; hObject
0x18007113f  call    cs:__imp_CloseHandle
0x180071145  jmp     short loc_1800711A3
0x180071147  mov     edi, 8007000Eh
0x18007114c  mov     rax, cs:WPP_GLOBAL_Control
0x180071153  lea     rcx, WPP_GLOBAL_Control
0x18007115a  cmp     rax, rcx
0x18007115d  jz      short loc_1800711A3
0x18007115f  test    byte ptr [rax+1Ch], 8
0x180071163  jz      short loc_1800711A3
0x180071165  cmp     byte ptr [rax+19h], 2
0x180071169  jb      short loc_1800711A3
0x18007116b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180071170  lea     rcx, aOom; "OOM..."
0x180071177  mov     dword ptr [rsp+58h+lpThreadId], 8007000Eh
0x18007117f  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x180071184  lea     r8, WPP_a22f260487b136bea20259a65a622838_Traceguids
0x18007118b  mov     rcx, cs:WPP_GLOBAL_Control
0x180071192  mov     edx, 0Ah
0x180071197  mov     r9d, eax
0x18007119a  mov     rcx, [rcx+10h]
0x18007119e  call    WPP_SF_DsD
0x1800711a3  lea     rcx, [rsp+58h+arg_0]
0x1800711a8  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x1800711ad  mov     rbx, [rsp+58h+arg_8]
0x1800711b2  mov     eax, edi
0x1800711b4  add     rsp, 30h
0x1800711b8  pop     r15
0x1800711ba  pop     r14
0x1800711bc  pop     rdi
0x1800711bd  pop     rsi
0x1800711be  pop     rbp
0x1800711bf  retn
```
