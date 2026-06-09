# CPCStreamWorker::DecoupleStreamEvent(CPCStream *,ulong,long,IUnknown *)

- ea: `0x140080610`
- end: `0x14008088c`
- name: `?DecoupleStreamEvent@CPCStreamWorker@@QEAAJPEAVCPCStream@@KJPEAUIUnknown@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(CPCStreamWorker *__hidden this, struct CPCStream *, unsigned int, int, struct IUnknown *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14007e830`
- `0x14007e958`
- `0x14007eb4c`
- `0x14007f040`

## callees

- `0x140003b2c`
- `0x14000b7d8`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000d078`
- `0x140080480`
- `0x140080610`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140080782`
- `KERNEL32!CreateThread` at `0x140080782`
- `KERNEL32!CreateEventW` at `0x1400806c6`
- `KERNEL32!CreateEventW` at `0x1400806c6`
- `KERNEL32!CloseHandle` at `0x1400807fd`
- `KERNEL32!CloseHandle` at `0x14008080b`
- `KERNEL32!CloseHandle` at `0x1400807fd`
- `KERNEL32!CloseHandle` at `0x14008080b`
- `KERNEL32!GetLastError` at `0x1400806ff`
- `KERNEL32!GetLastError` at `0x140080744`
- `KERNEL32!GetLastError` at `0x1400807b4`
- `KERNEL32!GetLastError` at `0x1400806ff`
- `KERNEL32!GetLastError` at `0x140080744`
- `KERNEL32!GetLastError` at `0x1400807b4`
- `KERNEL32!WaitForSingleObject` at `0x1400807e3`
- `KERNEL32!WaitForSingleObject` at `0x1400807e3`

## string_xrefs

- `0x1400807cf`: `hThread`

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
  unsigned int v16; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v18; // edx
  const char *v19; // rcx
  signed int v20; // eax
  unsigned int v21; // edx
  signed int LastError; // eax
  unsigned int v23; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-30h]
  struct CPCStream *v26; // [rsp+60h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  v26 = 0;
  ThreadId = 0;
  if ( a2 )
  {
    TCntPtr<CTSCoreEventSink>::SafeRelease(&v26);
    v5 = a2;
    v26 = a2;
    TCntPtr<CTscSettings>::SafeAddRef(&v26);
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
          v16 = (unsigned __int16)LastError | 0x80070000;
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
          v16 = (unsigned __int16)v15 | 0x80070000;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 11;
        v19 = "hEvent";
LABEL_13:
        LODWORD(lpThreadId) = v16;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          (unsigned int)WPP_a22f260487b136bea20259a65a622838_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v19,
          lpThreadId);
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
      -2147024882);
  }
LABEL_34:
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v26);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140080610  mov     rax, rsp
0x140080613  mov     [rax+10h], rbx
0x140080617  mov     [rax+20h], r9d
0x14008061b  mov     [rax+8], rcx
0x14008061f  push    rbp
0x140080620  push    rsi
0x140080621  push    rdi
0x140080622  push    r14
0x140080624  push    r15
0x140080626  sub     rsp, 30h
0x14008062a  xor     ebx, ebx
0x14008062c  xor     ebp, ebp
0x14008062e  mov     [rax+8], rbx
0x140080632  mov     r14d, r8d
0x140080635  mov     [rax+20h], ebx
0x140080638  mov     rdi, rdx
0x14008063b  test    rdx, rdx
0x14008063e  jz      short loc_14008065E
0x140080640  lea     rcx, [rax+8]
0x140080644  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x140080649  mov     rbx, rdi
0x14008064c  lea     rcx, [rsp+58h+arg_0]
0x140080651  mov     [rsp+58h+arg_0], rbx
0x140080656  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x14008065b  mov     rbp, rdi
0x14008065e  mov     ecx, 20h ; ' '; Size
0x140080663  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140080668  mov     rsi, rax
0x14008066b  test    rax, rax
0x14008066e  jz      loc_140080813
0x140080674  mov     rcx, rax
0x140080677  mov     qword ptr [rax], 0
0x14008067e  neg     rcx
0x140080681  sbb     edi, edi
0x140080683  not     edi
0x140080685  and     edi, 8007000Eh
0x14008068b  cmp     rbp, [rax]
0x14008068e  jz      short loc_1400806A3
0x140080690  mov     rcx, rax
0x140080693  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x140080698  mov     rcx, rsi
0x14008069b  mov     [rsi], rbx
0x14008069e  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x1400806a3  mov     rax, [rsp+58h+arg_20]
0x1400806ab  xor     r9d, r9d; lpName
0x1400806ae  xor     r8d, r8d; bInitialState
0x1400806b1  mov     [rsi+8], r14d
0x1400806b5  xor     ecx, ecx; lpEventAttributes
0x1400806b7  mov     dword ptr [rsi+0Ch], 0
0x1400806be  mov     [rsi+10h], rax
0x1400806c2  lea     edx, [r9+1]; bManualReset
0x1400806c6  call    cs:__imp_CreateEventW
0x1400806cc  mov     r14, rax
0x1400806cf  test    rax, rax
0x1400806d2  jnz     loc_14008075E
0x1400806d8  xor     r15d, r15d
0x1400806db  mov     rdx, cs:WPP_GLOBAL_Control
0x1400806e2  lea     rcx, WPP_GLOBAL_Control
0x1400806e9  mov     ebp, 80070000h
0x1400806ee  cmp     rdx, rcx
0x1400806f1  jz      short loc_140080744
0x1400806f3  test    byte ptr [rdx+1Ch], 8
0x1400806f7  jz      short loc_140080744
0x1400806f9  cmp     byte ptr [rdx+19h], 2
0x1400806fd  jb      short loc_140080744
0x1400806ff  call    cs:__imp_GetLastError
0x140080705  mov     ebx, eax
0x140080707  test    eax, eax
0x140080709  jle     short loc_140080710
0x14008070b  movzx   ebx, ax
0x14008070e  or      ebx, ebp
0x140080710  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140080715  mov     edx, 0Bh
0x14008071a  lea     rcx, aHevent; "hEvent"
0x140080721  mov     dword ptr [rsp+58h+lpThreadId], ebx
0x140080725  lea     r8, WPP_a22f260487b136bea20259a65a622838_Traceguids
0x14008072c  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x140080731  mov     r9d, eax
0x140080734  mov     rcx, cs:WPP_GLOBAL_Control
0x14008073b  mov     rcx, [rcx+10h]
0x14008073f  call    WPP_SF_DsD
0x140080744  call    cs:__imp_GetLastError
0x14008074a  mov     edi, eax
0x14008074c  test    eax, eax
0x14008074e  jle     loc_1400807E9
0x140080754  movzx   edi, ax
0x140080757  or      edi, ebp
0x140080759  jmp     loc_1400807E9
0x14008075e  lea     rax, [rsp+58h+ThreadId]
0x140080763  mov     [rsi+18h], r14
0x140080767  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x14008076c  lea     r8, ?STATIC_Fire_Decouple_Notification@CPCStreamWorker@@SAKPEAX@Z; lpStartAddress
0x140080773  mov     r9, rsi; lpParameter
0x140080776  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14008077e  xor     edx, edx; dwStackSize
0x140080780  xor     ecx, ecx; lpThreadAttributes
0x140080782  call    cs:__imp_CreateThread
0x140080788  mov     r15, rax
0x14008078b  test    rax, rax
0x14008078e  jnz     short loc_1400807DB
0x140080790  mov     rdx, cs:WPP_GLOBAL_Control
0x140080797  lea     rcx, WPP_GLOBAL_Control
0x14008079e  mov     ebp, 80070000h
0x1400807a3  cmp     rdx, rcx
0x1400807a6  jz      short loc_140080744
0x1400807a8  test    byte ptr [rdx+1Ch], 8
0x1400807ac  jz      short loc_140080744
0x1400807ae  cmp     byte ptr [rdx+19h], 2
0x1400807b2  jb      short loc_140080744
0x1400807b4  call    cs:__imp_GetLastError
0x1400807ba  mov     ebx, eax
0x1400807bc  test    eax, eax
0x1400807be  jle     short loc_1400807C5
0x1400807c0  movzx   ebx, ax
0x1400807c3  or      ebx, ebp
0x1400807c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400807ca  mov     edx, 0Ch
0x1400807cf  lea     rcx, aHthread; "hThread"
0x1400807d6  jmp     loc_140080721
0x1400807db  mov     edx, 2710h; dwMilliseconds
0x1400807e0  mov     rcx, r14; hHandle
0x1400807e3  call    cs:__imp_WaitForSingleObject
0x1400807e9  test    edi, edi
0x1400807eb  jns     short loc_1400807F5
0x1400807ed  mov     rcx, rsi; this
0x1400807f0  call    ??_GPC_EVENT_INTERNAL@@QEAAPEAXI@Z; PC_EVENT_INTERNAL::`scalar deleting destructor'(uint)
0x1400807f5  test    r14, r14
0x1400807f8  jz      short loc_140080803
0x1400807fa  mov     rcx, r14; hObject
0x1400807fd  call    cs:__imp_CloseHandle
0x140080803  test    r15, r15
0x140080806  jz      short loc_14008086F
0x140080808  mov     rcx, r15; hObject
0x14008080b  call    cs:__imp_CloseHandle
0x140080811  jmp     short loc_14008086F
0x140080813  mov     edi, 8007000Eh
0x140080818  mov     rax, cs:WPP_GLOBAL_Control
0x14008081f  lea     rcx, WPP_GLOBAL_Control
0x140080826  cmp     rax, rcx
0x140080829  jz      short loc_14008086F
0x14008082b  test    byte ptr [rax+1Ch], 8
0x14008082f  jz      short loc_14008086F
0x140080831  cmp     byte ptr [rax+19h], 2
0x140080835  jb      short loc_14008086F
0x140080837  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14008083c  lea     rcx, aOom; "OOM..."
0x140080843  mov     dword ptr [rsp+58h+lpThreadId], 8007000Eh
0x14008084b  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x140080850  lea     r8, WPP_a22f260487b136bea20259a65a622838_Traceguids
0x140080857  mov     rcx, cs:WPP_GLOBAL_Control
0x14008085e  mov     edx, 0Ah
0x140080863  mov     r9d, eax
0x140080866  mov     rcx, [rcx+10h]
0x14008086a  call    WPP_SF_DsD
0x14008086f  lea     rcx, [rsp+58h+arg_0]
0x140080874  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x140080879  mov     rbx, [rsp+58h+arg_8]
0x14008087e  mov     eax, edi
0x140080880  add     rsp, 30h
0x140080884  pop     r15
0x140080886  pop     r14
0x140080888  pop     rdi
0x140080889  pop     rsi
0x14008088a  pop     rbp
0x14008088b  retn
```
