# CPCStreamWorker::DecoupleStreamEvent(CPCStream *,ulong,long,IUnknown *)

- ea: `0x14007e4a0`
- end: `0x14007e71c`
- name: `?DecoupleStreamEvent@CPCStreamWorker@@QEAAJPEAVCPCStream@@KJPEAUIUnknown@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(CPCStreamWorker *__hidden this, struct CPCStream *, unsigned int, int, struct IUnknown *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14007c6c0`
- `0x14007c7e8`
- `0x14007c9dc`
- `0x14007ced0`

## callees

- `0x140003b2c`
- `0x14000b7d8`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000d078`
- `0x14007e310`
- `0x14007e4a0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14007e612`
- `KERNEL32!CreateThread` at `0x14007e612`
- `KERNEL32!CreateEventW` at `0x14007e556`
- `KERNEL32!CreateEventW` at `0x14007e556`
- `KERNEL32!CloseHandle` at `0x14007e68d`
- `KERNEL32!CloseHandle` at `0x14007e69b`
- `KERNEL32!CloseHandle` at `0x14007e68d`
- `KERNEL32!CloseHandle` at `0x14007e69b`
- `KERNEL32!GetLastError` at `0x14007e58f`
- `KERNEL32!GetLastError` at `0x14007e5d4`
- `KERNEL32!GetLastError` at `0x14007e644`
- `KERNEL32!GetLastError` at `0x14007e58f`
- `KERNEL32!GetLastError` at `0x14007e5d4`
- `KERNEL32!GetLastError` at `0x14007e644`
- `KERNEL32!WaitForSingleObject` at `0x14007e673`
- `KERNEL32!WaitForSingleObject` at `0x14007e673`

## string_xrefs

- `0x14007e65f`: `hThread`

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
    TCntPtr<CTSCoreEventSink>::SafeRelease(&v25);
    v5 = a2;
    v25 = a2;
    TCntPtr<CTscSettings>::SafeAddRef(&v25);
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
      TCntPtr<CTSCoreEventSink>::SafeRelease(v9);
      *v10 = v5;
      TCntPtr<CTscSettings>::SafeAddRef(v10);
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
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14007e4a0  mov     rax, rsp
0x14007e4a3  mov     [rax+10h], rbx
0x14007e4a7  mov     [rax+20h], r9d
0x14007e4ab  mov     [rax+8], rcx
0x14007e4af  push    rbp
0x14007e4b0  push    rsi
0x14007e4b1  push    rdi
0x14007e4b2  push    r14
0x14007e4b4  push    r15
0x14007e4b6  sub     rsp, 30h
0x14007e4ba  xor     ebx, ebx
0x14007e4bc  xor     ebp, ebp
0x14007e4be  mov     [rax+8], rbx
0x14007e4c2  mov     r14d, r8d
0x14007e4c5  mov     [rax+20h], ebx
0x14007e4c8  mov     rdi, rdx
0x14007e4cb  test    rdx, rdx
0x14007e4ce  jz      short loc_14007E4EE
0x14007e4d0  lea     rcx, [rax+8]
0x14007e4d4  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14007e4d9  mov     rbx, rdi
0x14007e4dc  lea     rcx, [rsp+58h+arg_0]
0x14007e4e1  mov     [rsp+58h+arg_0], rbx
0x14007e4e6  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x14007e4eb  mov     rbp, rdi
0x14007e4ee  mov     ecx, 20h ; ' '; Size
0x14007e4f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007e4f8  mov     rsi, rax
0x14007e4fb  test    rax, rax
0x14007e4fe  jz      loc_14007E6A3
0x14007e504  mov     rcx, rax
0x14007e507  mov     qword ptr [rax], 0
0x14007e50e  neg     rcx
0x14007e511  sbb     edi, edi
0x14007e513  not     edi
0x14007e515  and     edi, 8007000Eh
0x14007e51b  cmp     rbp, [rax]
0x14007e51e  jz      short loc_14007E533
0x14007e520  mov     rcx, rax
0x14007e523  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14007e528  mov     rcx, rsi
0x14007e52b  mov     [rsi], rbx
0x14007e52e  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x14007e533  mov     rax, [rsp+58h+arg_20]
0x14007e53b  xor     r9d, r9d; lpName
0x14007e53e  xor     r8d, r8d; bInitialState
0x14007e541  mov     [rsi+8], r14d
0x14007e545  xor     ecx, ecx; lpEventAttributes
0x14007e547  mov     dword ptr [rsi+0Ch], 0
0x14007e54e  mov     [rsi+10h], rax
0x14007e552  lea     edx, [r9+1]; bManualReset
0x14007e556  call    cs:__imp_CreateEventW
0x14007e55c  mov     r14, rax
0x14007e55f  test    rax, rax
0x14007e562  jnz     loc_14007E5EE
0x14007e568  xor     r15d, r15d
0x14007e56b  mov     rdx, cs:WPP_GLOBAL_Control
0x14007e572  lea     rcx, WPP_GLOBAL_Control
0x14007e579  mov     ebp, 80070000h
0x14007e57e  cmp     rdx, rcx
0x14007e581  jz      short loc_14007E5D4
0x14007e583  test    byte ptr [rdx+1Ch], 8
0x14007e587  jz      short loc_14007E5D4
0x14007e589  cmp     byte ptr [rdx+19h], 2
0x14007e58d  jb      short loc_14007E5D4
0x14007e58f  call    cs:__imp_GetLastError
0x14007e595  mov     ebx, eax
0x14007e597  test    eax, eax
0x14007e599  jle     short loc_14007E5A0
0x14007e59b  movzx   ebx, ax
0x14007e59e  or      ebx, ebp
0x14007e5a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007e5a5  mov     edx, 0Bh
0x14007e5aa  lea     rcx, aHevent; "hEvent"
0x14007e5b1  mov     dword ptr [rsp+58h+lpThreadId], ebx
0x14007e5b5  lea     r8, WPP_a22f260487b136bea20259a65a622838_Traceguids
0x14007e5bc  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x14007e5c1  mov     r9d, eax
0x14007e5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5cb  mov     rcx, [rcx+10h]
0x14007e5cf  call    WPP_SF_DsD
0x14007e5d4  call    cs:__imp_GetLastError
0x14007e5da  mov     edi, eax
0x14007e5dc  test    eax, eax
0x14007e5de  jle     loc_14007E679
0x14007e5e4  movzx   edi, ax
0x14007e5e7  or      edi, ebp
0x14007e5e9  jmp     loc_14007E679
0x14007e5ee  lea     rax, [rsp+58h+ThreadId]
0x14007e5f3  mov     [rsi+18h], r14
0x14007e5f7  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x14007e5fc  lea     r8, ?STATIC_Fire_Decouple_Notification@CPCStreamWorker@@SAKPEAX@Z; lpStartAddress
0x14007e603  mov     r9, rsi; lpParameter
0x14007e606  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14007e60e  xor     edx, edx; dwStackSize
0x14007e610  xor     ecx, ecx; lpThreadAttributes
0x14007e612  call    cs:__imp_CreateThread
0x14007e618  mov     r15, rax
0x14007e61b  test    rax, rax
0x14007e61e  jnz     short loc_14007E66B
0x14007e620  mov     rdx, cs:WPP_GLOBAL_Control
0x14007e627  lea     rcx, WPP_GLOBAL_Control
0x14007e62e  mov     ebp, 80070000h
0x14007e633  cmp     rdx, rcx
0x14007e636  jz      short loc_14007E5D4
0x14007e638  test    byte ptr [rdx+1Ch], 8
0x14007e63c  jz      short loc_14007E5D4
0x14007e63e  cmp     byte ptr [rdx+19h], 2
0x14007e642  jb      short loc_14007E5D4
0x14007e644  call    cs:__imp_GetLastError
0x14007e64a  mov     ebx, eax
0x14007e64c  test    eax, eax
0x14007e64e  jle     short loc_14007E655
0x14007e650  movzx   ebx, ax
0x14007e653  or      ebx, ebp
0x14007e655  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007e65a  mov     edx, 0Ch
0x14007e65f  lea     rcx, aHthread; "hThread"
0x14007e666  jmp     loc_14007E5B1
0x14007e66b  mov     edx, 2710h; dwMilliseconds
0x14007e670  mov     rcx, r14; hHandle
0x14007e673  call    cs:__imp_WaitForSingleObject
0x14007e679  test    edi, edi
0x14007e67b  jns     short loc_14007E685
0x14007e67d  mov     rcx, rsi; this
0x14007e680  call    ??_GPC_EVENT_INTERNAL@@QEAAPEAXI@Z; PC_EVENT_INTERNAL::`scalar deleting destructor'(uint)
0x14007e685  test    r14, r14
0x14007e688  jz      short loc_14007E693
0x14007e68a  mov     rcx, r14; hObject
0x14007e68d  call    cs:__imp_CloseHandle
0x14007e693  test    r15, r15
0x14007e696  jz      short loc_14007E6FF
0x14007e698  mov     rcx, r15; hObject
0x14007e69b  call    cs:__imp_CloseHandle
0x14007e6a1  jmp     short loc_14007E6FF
0x14007e6a3  mov     edi, 8007000Eh
0x14007e6a8  mov     rax, cs:WPP_GLOBAL_Control
0x14007e6af  lea     rcx, WPP_GLOBAL_Control
0x14007e6b6  cmp     rax, rcx
0x14007e6b9  jz      short loc_14007E6FF
0x14007e6bb  test    byte ptr [rax+1Ch], 8
0x14007e6bf  jz      short loc_14007E6FF
0x14007e6c1  cmp     byte ptr [rax+19h], 2
0x14007e6c5  jb      short loc_14007E6FF
0x14007e6c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007e6cc  lea     rcx, aOom; "OOM..."
0x14007e6d3  mov     dword ptr [rsp+58h+lpThreadId], 8007000Eh
0x14007e6db  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x14007e6e0  lea     r8, WPP_a22f260487b136bea20259a65a622838_Traceguids
0x14007e6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e6ee  mov     edx, 0Ah
0x14007e6f3  mov     r9d, eax
0x14007e6f6  mov     rcx, [rcx+10h]
0x14007e6fa  call    WPP_SF_DsD
0x14007e6ff  lea     rcx, [rsp+58h+arg_0]
0x14007e704  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14007e709  mov     rbx, [rsp+58h+arg_8]
0x14007e70e  mov     eax, edi
0x14007e710  add     rsp, 30h
0x14007e714  pop     r15
0x14007e716  pop     r14
0x14007e718  pop     rdi
0x14007e719  pop     rsi
0x14007e71a  pop     rbp
0x14007e71b  retn
```
