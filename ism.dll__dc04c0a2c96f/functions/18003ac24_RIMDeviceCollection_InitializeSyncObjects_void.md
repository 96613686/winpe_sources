# RIMDeviceCollection::InitializeSyncObjects(void)

- ea: `0x18003ac24`
- end: `0x18003aed6`
- name: `?InitializeSyncObjects@RIMDeviceCollection@@IEAAJXZ`
- size: `690`
- prototype: `__int64 __fastcall(RIMDeviceCollection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003a5bc`
- `0x180118a40`

## callees

- `0x18003ac24`
- `0x18003aedc`
- `0x18008daac`
- `0x18008ead4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ac36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003ac36`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18003ad53`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18003ad53`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18003add3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18003add3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ac59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ac76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ace3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ac59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ac76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ace3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003acae`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ad1b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ad8b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ae0b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003acae`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ad1b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ad8b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003ae0b`

## pseudocode

```c
__int64 __fastcall RIMDeviceCollection::InitializeSyncObjects(RIMDeviceCollection *this)
{
  HANDLE CurrentProcess; // rax
  void *v3; // rsi
  HANDLE EventW; // rax
  const char *v5; // r9
  HANDLE v6; // rax
  RIMDeviceCollection *v7; // rcx
  int v8; // edi
  HANDLE v9; // rax
  RIMDeviceCollection *v10; // rcx
  HANDLE WaitableTimer; // rax
  RIMDeviceCollection *v12; // rcx
  HANDLE Semaphore; // rax
  RIMDeviceCollection *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v18; // rdx
  __int64 v19; // rdx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-20h]
  DWORD dwDesiredAccessa; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE TargetHandle; // [rsp+60h] [rbp+20h] BYREF
  HANDLE v24; // [rsp+68h] [rbp+28h] BYREF

  CurrentProcess = GetCurrentProcess();
  TargetHandle = 0;
  v24 = 0;
  v3 = CurrentProcess;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( !EventW )
  {
    v18 = 783;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  v6 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 6) = v6;
  if ( !v6 )
  {
    v18 = 790;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  if ( !DuplicateHandle(v3, v6, v3, &TargetHandle, 0, 0, 2u) )
  {
    v18 = 799;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  v8 = RIMDeviceCollection::RegisterWaitHandler(
         v7,
         TargetHandle,
         (int (*)(void *, unsigned int, void *))RIMDeviceCollection::OnRIMPnpEventStatic,
         this);
  if ( v8 < 0 )
  {
    v19 = 804;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
      (const char *)(unsigned int)v8,
      dwDesiredAccess);
    return (unsigned int)v8;
  }
  v9 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 7) = v9;
  if ( !v9 )
  {
    v18 = 811;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  if ( !DuplicateHandle(v3, v9, v3, &TargetHandle, 0, 0, 2u) )
  {
    v18 = 820;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  v8 = RIMDeviceCollection::RegisterWaitHandler(
         v10,
         TargetHandle,
         (int (*)(void *, unsigned int, void *))RIMDeviceCollection::OnRIMDeferredRead,
         this);
  if ( v8 < 0 )
  {
    v19 = 825;
    goto LABEL_24;
  }
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x100002u);
  *((_QWORD *)this + 8) = WaitableTimer;
  if ( !WaitableTimer )
  {
    v18 = 833;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  if ( !DuplicateHandle(v3, WaitableTimer, v3, &TargetHandle, 0, 0, 2u) )
  {
    v18 = 842;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  v8 = RIMDeviceCollection::RegisterWaitHandler(
         v12,
         TargetHandle,
         (int (*)(void *, unsigned int, void *))RIMDeviceCollection::OnRIMTimerEventStatic,
         this);
  if ( v8 < 0 )
  {
    v19 = 847;
    goto LABEL_24;
  }
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 9) = Semaphore;
  if ( !Semaphore )
  {
    v18 = 857;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  if ( !DuplicateHandle(v3, Semaphore, v3, &v24, 0, 0, 2u) )
  {
    v18 = 866;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v18,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
             v5);
  }
  v15 = RIMDeviceCollection::RegisterWaitHandler(
          v14,
          v24,
          (int (*)(void *, unsigned int, void *))RIMDeviceCollection::OnRIMAsyncPnpWorkNotificationSemaphoreStatic,
          this);
  v16 = v15;
  if ( v15 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x367,
    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\rim\\lib\\rimdevicecollection.cpp",
    (const char *)(unsigned int)v15,
    dwDesiredAccessa);
  return v16;
}

```

## disassembly

```asm
0x18003ac24  mov     [rsp-18h+arg_10], rbx
0x18003ac29  push    rbp
0x18003ac2a  push    rsi
0x18003ac2b  push    rdi
0x18003ac2c  mov     rbp, rsp
0x18003ac2f  sub     rsp, 40h
0x18003ac33  mov     rbx, rcx
0x18003ac36  call    cs:__imp_GetCurrentProcess
0x18003ac3c  xor     r9d, r9d; lpName
0x18003ac3f  mov     [rbp+TargetHandle], 0
0x18003ac47  xor     r8d, r8d; bInitialState
0x18003ac4a  mov     [rbp+arg_8], 0
0x18003ac52  xor     edx, edx; bManualReset
0x18003ac54  xor     ecx, ecx; lpEventAttributes
0x18003ac56  mov     rsi, rax
0x18003ac59  call    cs:__imp_CreateEventW
0x18003ac5f  mov     [rbx+28h], rax
0x18003ac63  test    rax, rax
0x18003ac66  jz      loc_18003AE7E
0x18003ac6c  xor     r9d, r9d; lpName
0x18003ac6f  xor     r8d, r8d; bInitialState
0x18003ac72  xor     edx, edx; bManualReset
0x18003ac74  xor     ecx, ecx; lpEventAttributes
0x18003ac76  call    cs:__imp_CreateEventW
0x18003ac7c  mov     [rbx+30h], rax
0x18003ac80  test    rax, rax
0x18003ac83  jz      loc_18003AE85
0x18003ac89  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18003ac91  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18003ac95  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18003ac9d  mov     r8, rsi; hTargetProcessHandle
0x18003aca0  mov     rdx, rax; hSourceHandle
0x18003aca3  mov     [rsp+40h+dwDesiredAccess], 0; dwDesiredAccess
0x18003acab  mov     rcx, rsi; hSourceProcessHandle
0x18003acae  call    cs:__imp_DuplicateHandle
0x18003acb4  test    eax, eax
0x18003acb6  jz      loc_18003AE8C
0x18003acbc  mov     rdx, [rbp+TargetHandle]; void *
0x18003acc0  lea     r8, ?OnRIMPnpEventStatic@RIMDeviceCollection@@CAJPEAXK0@Z; int (*)(void *, unsigned int, void *)
0x18003acc7  mov     r9, rbx; void *
0x18003acca  call    ?RegisterWaitHandler@RIMDeviceCollection@@AEAAJPEAXP6AJ0K0@Z0@Z; RIMDeviceCollection::RegisterWaitHandler(void *,long (*)(void *,ulong,void *),void *)
0x18003accf  mov     edi, eax
0x18003acd1  test    eax, eax
0x18003acd3  js      loc_18003AE93
0x18003acd9  xor     r9d, r9d; lpName
0x18003acdc  xor     r8d, r8d; bInitialState
0x18003acdf  xor     edx, edx; bManualReset
0x18003ace1  xor     ecx, ecx; lpEventAttributes
0x18003ace3  call    cs:__imp_CreateEventW
0x18003ace9  mov     [rbx+38h], rax
0x18003aced  test    rax, rax
0x18003acf0  jz      loc_18003AEB6
0x18003acf6  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18003acfe  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18003ad02  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18003ad0a  mov     r8, rsi; hTargetProcessHandle
0x18003ad0d  mov     rdx, rax; hSourceHandle
0x18003ad10  mov     [rsp+40h+dwDesiredAccess], 0; dwDesiredAccess
0x18003ad18  mov     rcx, rsi; hSourceProcessHandle
0x18003ad1b  call    cs:__imp_DuplicateHandle
0x18003ad21  test    eax, eax
0x18003ad23  jz      loc_18003AEBD
0x18003ad29  mov     rdx, [rbp+TargetHandle]; void *
0x18003ad2d  lea     r8, ?OnRIMDeferredRead@RIMDeviceCollection@@CAJPEAXK0@Z; int (*)(void *, unsigned int, void *)
0x18003ad34  mov     r9, rbx; void *
0x18003ad37  call    ?RegisterWaitHandler@RIMDeviceCollection@@AEAAJPEAXP6AJ0K0@Z0@Z; RIMDeviceCollection::RegisterWaitHandler(void *,long (*)(void *,ulong,void *),void *)
0x18003ad3c  mov     edi, eax
0x18003ad3e  test    eax, eax
0x18003ad40  js      loc_18003AEC4
0x18003ad46  mov     r9d, 100002h; dwDesiredAccess
0x18003ad4c  xor     r8d, r8d; dwFlags
0x18003ad4f  xor     edx, edx; lpTimerName
0x18003ad51  xor     ecx, ecx; lpTimerAttributes
0x18003ad53  call    cs:__imp_CreateWaitableTimerExW
0x18003ad59  mov     [rbx+40h], rax
0x18003ad5d  test    rax, rax
0x18003ad60  jz      loc_18003AECB
0x18003ad66  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18003ad6e  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18003ad72  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18003ad7a  mov     r8, rsi; hTargetProcessHandle
0x18003ad7d  mov     rdx, rax; hSourceHandle
0x18003ad80  mov     [rsp+40h+dwDesiredAccess], 0; int
0x18003ad88  mov     rcx, rsi; hSourceProcessHandle
0x18003ad8b  call    cs:__imp_DuplicateHandle
0x18003ad91  test    eax, eax
0x18003ad93  jz      loc_18003AE4E
0x18003ad99  mov     rdx, [rbp+TargetHandle]; void *
0x18003ad9d  lea     r8, ?OnRIMTimerEventStatic@RIMDeviceCollection@@CAJPEAXK0@Z; int (*)(void *, unsigned int, void *)
0x18003ada4  mov     r9, rbx; void *
0x18003ada7  call    ?RegisterWaitHandler@RIMDeviceCollection@@AEAAJPEAXP6AJ0K0@Z0@Z; RIMDeviceCollection::RegisterWaitHandler(void *,long (*)(void *,ulong,void *),void *)
0x18003adac  mov     edi, eax
0x18003adae  test    eax, eax
0x18003adb0  js      loc_18003AE9A
0x18003adb6  mov     [rsp+40h+bInheritHandle], 1F0003h; dwDesiredAccess
0x18003adbe  xor     r9d, r9d; lpName
0x18003adc1  xor     edx, edx; lInitialCount
0x18003adc3  mov     [rsp+40h+dwDesiredAccess], 0; dwFlags
0x18003adcb  xor     ecx, ecx; lpSemaphoreAttributes
0x18003adcd  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18003add3  call    cs:__imp_CreateSemaphoreExW
0x18003add9  mov     [rbx+48h], rax
0x18003addd  test    rax, rax
0x18003ade0  jz      loc_18003AE70
0x18003ade6  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18003adee  lea     r9, [rbp+arg_8]; lpTargetHandle
0x18003adf2  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18003adfa  mov     r8, rsi; hTargetProcessHandle
0x18003adfd  mov     rdx, rax; hSourceHandle
0x18003ae00  mov     [rsp+40h+dwDesiredAccess], 0; int
0x18003ae08  mov     rcx, rsi; hSourceProcessHandle
0x18003ae0b  call    cs:__imp_DuplicateHandle
0x18003ae11  test    eax, eax
0x18003ae13  jz      short loc_18003AE77
0x18003ae15  mov     rdx, [rbp+arg_8]; void *
0x18003ae19  lea     r8, ?OnRIMAsyncPnpWorkNotificationSemaphoreStatic@RIMDeviceCollection@@CAJPEAXK0@Z; int (*)(void *, unsigned int, void *)
0x18003ae20  mov     r9, rbx; void *
0x18003ae23  call    ?RegisterWaitHandler@RIMDeviceCollection@@AEAAJPEAXP6AJ0K0@Z0@Z; RIMDeviceCollection::RegisterWaitHandler(void *,long (*)(void *,ulong,void *),void *)
0x18003ae28  mov     ebx, eax
0x18003ae2a  test    eax, eax
0x18003ae2c  jns     loc_18003AED2
0x18003ae32  mov     rcx, [rbp+18h]; this
0x18003ae36  lea     r8, aOnecoreuapWind_233; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003ae3d  mov     r9d, eax; char *
0x18003ae40  mov     edx, 367h; void *
0x18003ae45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae4a  mov     eax, ebx
0x18003ae4c  jmp     short loc_18003AE63
0x18003ae4e  mov     edx, 34Ah; void *
0x18003ae53  mov     rcx, [rbp+18h]; this
0x18003ae57  lea     r8, aOnecoreuapWind_233; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003ae5e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ae63  mov     rbx, [rsp+40h+arg_10]
0x18003ae68  add     rsp, 40h
0x18003ae6c  pop     rdi
0x18003ae6d  pop     rsi
0x18003ae6e  pop     rbp
0x18003ae6f  retn
0x18003ae70  mov     edx, 359h
0x18003ae75  jmp     short loc_18003AE53
0x18003ae77  mov     edx, 362h
0x18003ae7c  jmp     short loc_18003AE53
0x18003ae7e  mov     edx, 30Fh
0x18003ae83  jmp     short loc_18003AE53
0x18003ae85  mov     edx, 316h
0x18003ae8a  jmp     short loc_18003AE53
0x18003ae8c  mov     edx, 31Fh
0x18003ae91  jmp     short loc_18003AE53
0x18003ae93  mov     edx, 324h
0x18003ae98  jmp     short loc_18003AE9F
0x18003ae9a  mov     edx, 34Fh; void *
0x18003ae9f  mov     rcx, [rbp+18h]; this
0x18003aea3  lea     r8, aOnecoreuapWind_233; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003aeaa  mov     r9d, edi; char *
0x18003aead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aeb2  mov     eax, edi
0x18003aeb4  jmp     short loc_18003AE63
0x18003aeb6  mov     edx, 32Bh
0x18003aebb  jmp     short loc_18003AE53
0x18003aebd  mov     edx, 334h
0x18003aec2  jmp     short loc_18003AE53
0x18003aec4  mov     edx, 339h
0x18003aec9  jmp     short loc_18003AE9F
0x18003aecb  mov     edx, 341h
0x18003aed0  jmp     short loc_18003AE53
0x18003aed2  xor     eax, eax
0x18003aed4  jmp     short loc_18003AE63
```
