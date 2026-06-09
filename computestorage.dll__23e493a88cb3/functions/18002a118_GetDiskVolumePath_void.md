# GetDiskVolumePath(void *)

- ea: `0x18002a118`
- end: `0x18002a45b`
- name: `?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `835`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800283b4`
- `0x180029b08`

## callees

- `0x180001ed0`
- `0x180002690`
- `0x1800032b8`
- `0x180008584`
- `0x180008fac`
- `0x18000e38c`
- `0x180012818`
- `0x180015a40`
- `0x180015b20`
- `0x1800288b8`
- `0x1800299e4`
- `0x18002a118`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x18002a1db`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x18002a1db`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002a1ca`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002a1ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a197`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a2bc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a197`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a2bc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a2cc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a2cc`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002a433`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002a433`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18002a232`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18002a232`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18002a3ee`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18002a3ee`

## string_xrefs

- `0x18002a26d`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002a449`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002a303`: `GetDiskVolumePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDiskVolumePath(__int64 a1, __int64 a2)
{
  CONFIGRET v3; // eax
  __int64 v4; // rdx
  int v5; // edi
  const struct _tlgProvider_t *v6; // r10
  char *v7; // rax
  DWORD v9; // eax
  ULONG v10; // [rsp+20h] [rbp-E0h]
  int v11; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v12[4]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h] BYREF
  RTL_SRWLOCK SRWLock; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+68h] [rbp-98h]
  RTL_CONDITION_VARIABLE ConditionVariable; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  _OWORD v20[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v22[2]; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER PerformanceCount[2]; // [rsp+C8h] [rbp-38h] BYREF
  LARGE_INTEGER Frequency[3]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v25[4]; // [rsp+F0h] [rbp-10h] BYREF
  GUID v26; // [rsp+100h] [rbp+0h]
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+290h] [rbp+190h] BYREF
  __int64 v28; // [rsp+2A0h] [rbp+1A0h]
  __int16 v29; // [rsp+2A8h] [rbp+1A8h]
  int *v30; // [rsp+2B0h] [rbp+1B0h]
  __int64 v31; // [rsp+2B8h] [rbp+1B8h]
  _QWORD *v32; // [rsp+2C0h] [rbp+1C0h]
  __int64 v33; // [rsp+2C8h] [rbp+1C8h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v12[3] = a1;
  v13 = a2;
  memset_0(v25, 0, 0x1A0u);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  *(_OWORD *)&Frequency[0].LowPart = 0;
  QueryPerformanceCounter(PerformanceCount);
  v25[0] = 416;
  v25[2] = 0;
  v26 = GUID_DEVINTERFACE_VOLUME;
  v15 = 0;
  InitializeSRWLock(&SRWLock);
  InitializeConditionVariable(&ConditionVariable);
  v17 = 1;
  v18 = 0;
  v20[0] = 0;
  v20[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20[0]) = 0;
  v19 = v13;
  v21 = 0;
  v3 = CM_Register_Notification(v25, &SRWLock, &VolumeArrivalCallback, &v21);
  if ( v3 )
  {
    v9 = CM_MapCrToWin32Err(v3, 0x1Fu);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)v9,
      v10);
  }
  v12[0] = a1;
  v12[1] = &v13;
  v12[2] = &SRWLock;
  v27.Ptr = (ULONGLONG)retaddr;
  *(_QWORD *)&v27.Size = "onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp";
  v28 = 0;
  v29 = 360;
  v22[0] = off_18004A968;
  v22[1] = v12;
  v5 = wil::details::ResultFromException(&v27, v4, v22);
  QueryPerformanceCounter(&PerformanceCount[1]);
  QueryPerformanceFrequency(Frequency);
  Frequency[1].QuadPart = 1000000
                        * (PerformanceCount[1].QuadPart - PerformanceCount[0].QuadPart)
                        / Frequency[0].QuadPart;
  if ( (unsigned int)VmlIsDebugTraceEnabled(
                       49152,
                       1000000 * (PerformanceCount[1].QuadPart - PerformanceCount[0].QuadPart) % Frequency[0].QuadPart) )
    VmlDebugTrace(49152, L"%s, Time Taken (us) : %llu\n", L"GetDiskVolumePath", Frequency[1].QuadPart);
  v6 = ComputeService::Diagnostics::TraceProvider::Provider();
  if ( *(_DWORD *)v6 > 5u
    && (*((_QWORD *)v6 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x200000000000LL) == *((_QWORD *)v6 + 3) )
  {
    v22[0] = Frequency[1].QuadPart / 0x3E8uLL;
    v11 = v5;
    v32 = v22;
    v33 = 8;
    v30 = &v11;
    v31 = 4;
    tlgWriteTransfer_EventWriteTransfer((int)v6, (int)&word_1800556C6, 0, 0, 4u, &v27);
  }
  v7 = (char *)std::wstring::wstring(&v27, a1);
  ForceOnlineVolume(v7);
  if ( v21 )
    CM_Unregister_Notification();
  std::wstring::~wstring((char **)v20);
  return a1;
}

```

## disassembly

```asm
0x18002a118  mov     [rsp-8+arg_10], rbx
0x18002a11d  mov     [rsp-8+arg_18], rdi
0x18002a122  push    rbp
0x18002a123  lea     rbp, [rsp-1E0h]
0x18002a12b  sub     rsp, 2E0h
0x18002a132  mov     rax, cs:__security_cookie
0x18002a139  xor     rax, rsp
0x18002a13c  mov     [rbp+1E0h+var_10], rax
0x18002a143  mov     rbx, rcx
0x18002a146  mov     [rsp+2E0h+var_290], rcx
0x18002a14b  mov     [rsp+2E0h+var_288], rdx
0x18002a150  mov     [rsp+2E0h+var_2B0], 0
0x18002a158  xor     edx, edx; Val
0x18002a15a  mov     r8d, 1A0h; Size
0x18002a160  lea     rcx, [rbp+1E0h+var_1F0]; void *
0x18002a164  call    memset_0
0x18002a169  xorps   xmm0, xmm0
0x18002a16c  movups  xmmword ptr [rbx], xmm0
0x18002a16f  mov     qword ptr [rbx+10h], 0
0x18002a177  mov     qword ptr [rbx+18h], 7
0x18002a17f  xor     eax, eax
0x18002a181  mov     [rbx], ax
0x18002a184  lea     edi, [rax+1]
0x18002a187  mov     [rsp+2E0h+var_2B0], edi
0x18002a18b  movups  xmmword ptr [rbp+1E0h+PerformanceCount], xmm0
0x18002a18f  movups  xmmword ptr [rbp+1E0h+Frequency], xmm0
0x18002a193  lea     rcx, [rbp+1E0h+PerformanceCount]; lpPerformanceCount
0x18002a197  call    cs:__imp_QueryPerformanceCounter
0x18002a19e  nop     dword ptr [rax+rax+00h]
0x18002a1a3  mov     [rbp+1E0h+var_1F0], 1A0h
0x18002a1aa  mov     [rbp+1E0h+var_1E8], 0
0x18002a1b1  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x18002a1b8  movdqu  [rbp+1E0h+var_1E0], xmm0
0x18002a1bd  mov     [rsp+2E0h+var_278], 0
0x18002a1c5  lea     rcx, [rsp+2E0h+SRWLock]; SRWLock
0x18002a1ca  call    cs:__imp_InitializeSRWLock
0x18002a1d1  nop     dword ptr [rax+rax+00h]
0x18002a1d6  lea     rcx, [rsp+2E0h+ConditionVariable]; ConditionVariable
0x18002a1db  call    cs:__imp_InitializeConditionVariable
0x18002a1e2  nop     dword ptr [rax+rax+00h]
0x18002a1e7  mov     [rsp+2E0h+var_268], rdi
0x18002a1ec  mov     [rbp+1E0h+var_260], 0
0x18002a1f3  xorps   xmm0, xmm0
0x18002a1f6  movups  [rbp+1E0h+var_250], xmm0
0x18002a1fa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002a202  movdqa  [rbp+1E0h+var_240], xmm1
0x18002a207  xor     eax, eax
0x18002a209  mov     word ptr [rbp+1E0h+var_250], ax
0x18002a20d  mov     rax, [rsp+2E0h+var_288]
0x18002a212  mov     [rbp+1E0h+var_258], rax
0x18002a216  mov     [rbp+1E0h+var_230], 0
0x18002a21e  lea     r9, [rbp+1E0h+var_230]
0x18002a222  lea     r8, ?VolumeArrivalCallback@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; VolumeArrivalCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18002a229  lea     rdx, [rsp+2E0h+SRWLock]
0x18002a22e  lea     rcx, [rbp+1E0h+var_1F0]
0x18002a232  call    cs:__imp_CM_Register_Notification
0x18002a239  nop     dword ptr [rax+rax+00h]
0x18002a23e  test    eax, eax
0x18002a240  jnz     loc_18002A42C
0x18002a246  mov     [rsp+2E0h+var_2A8], rbx
0x18002a24b  lea     rax, [rsp+2E0h+var_288]
0x18002a250  mov     [rsp+2E0h+var_2A0], rax
0x18002a255  lea     rax, [rsp+2E0h+SRWLock]
0x18002a25a  mov     [rsp+2E0h+var_298], rax
0x18002a25f  mov     rax, [rbp+1E8h]
0x18002a266  mov     [rbp+1E0h+var_50.Ptr], rax
0x18002a26d  lea     rax, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002a274  mov     qword ptr [rbp+1E0h+var_50.Size], rax
0x18002a27b  mov     [rbp+1E0h+var_40], 0
0x18002a286  mov     eax, 168h
0x18002a28b  mov     [rbp+1E0h+var_38], ax
0x18002a292  lea     rax, off_18004A968
0x18002a299  mov     [rbp+1E0h+var_228], rax
0x18002a29d  lea     rax, [rsp+2E0h+var_2A8]
0x18002a2a2  mov     [rbp+1E0h+var_220], rax
0x18002a2a6  lea     r8, [rbp+1E0h+var_228]
0x18002a2aa  lea     rcx, [rbp+1E0h+var_50]
0x18002a2b1  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x18002a2b6  mov     edi, eax
0x18002a2b8  lea     rcx, [rbp+1E0h+PerformanceCount+8]; lpPerformanceCount
0x18002a2bc  call    cs:__imp_QueryPerformanceCounter
0x18002a2c3  nop     dword ptr [rax+rax+00h]
0x18002a2c8  lea     rcx, [rbp+1E0h+Frequency]; lpFrequency
0x18002a2cc  call    cs:__imp_QueryPerformanceFrequency
0x18002a2d3  nop     dword ptr [rax+rax+00h]
0x18002a2d8  mov     rax, qword ptr [rbp+1E0h+PerformanceCount+8]
0x18002a2dc  sub     rax, qword ptr [rbp+1E0h+PerformanceCount]
0x18002a2e0  imul    rax, 0F4240h
0x18002a2e7  cqo
0x18002a2e9  idiv    qword ptr [rbp+1E0h+Frequency]
0x18002a2ed  mov     qword ptr [rbp+1E0h+Frequency+8], rax
0x18002a2f1  mov     ecx, 0C000h
0x18002a2f6  call    VmlIsDebugTraceEnabled
0x18002a2fb  test    eax, eax
0x18002a2fd  jz      short loc_18002A31B
0x18002a2ff  mov     r9, qword ptr [rbp+1E0h+Frequency+8]
0x18002a303  lea     r8, aGetdiskvolumep; "GetDiskVolumePath"
0x18002a30a  lea     rdx, aSTimeTakenUsLl; "%s, Time Taken (us) : %llu\n"
0x18002a311  mov     ecx, 0C000h
0x18002a316  call    VmlDebugTrace
0x18002a31b  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18002a320  mov     r10, rax
0x18002a323  mov     eax, [rax]
0x18002a325  cmp     eax, 5
0x18002a328  jbe     loc_18002A3CD
0x18002a32e  mov     rcx, [r10+18h]
0x18002a332  mov     rax, [r10+10h]
0x18002a336  mov     rdx, 200000000000h
0x18002a340  test    rdx, rax
0x18002a343  jz      loc_18002A3CD
0x18002a349  mov     rax, rcx
0x18002a34c  and     rax, rdx
0x18002a34f  cmp     rax, rcx
0x18002a352  jnz     short loc_18002A3CD
0x18002a354  mov     rcx, qword ptr [rbp+1E0h+Frequency+8]
0x18002a358  mov     rax, 624DD2F1A9FBE77h
0x18002a362  mul     rcx
0x18002a365  sub     rcx, rdx
0x18002a368  shr     rcx, 1
0x18002a36b  add     rcx, rdx
0x18002a36e  shr     rcx, 9
0x18002a372  mov     [rbp+1E0h+var_228], rcx
0x18002a376  mov     [rsp+2E0h+var_2AC], edi
0x18002a37a  lea     rax, [rbp+1E0h+var_228]
0x18002a37e  mov     [rbp+1E0h+var_20], rax
0x18002a385  mov     [rbp+1E0h+var_18], 8
0x18002a390  lea     rax, [rsp+2E0h+var_2AC]
0x18002a395  mov     [rbp+1E0h+var_30], rax
0x18002a39c  mov     ecx, 4
0x18002a3a1  mov     [rbp+1E0h+var_28], rcx
0x18002a3a8  lea     rax, [rbp+1E0h+var_50]
0x18002a3af  mov     [rsp+2E0h+var_2B8], rax; PEVENT_DATA_DESCRIPTOR
0x18002a3b4  mov     [rsp+2E0h+var_2C0], ecx; ULONG
0x18002a3b8  xor     r9d, r9d; int
0x18002a3bb  xor     r8d, r8d; int
0x18002a3be  lea     rdx, word_1800556C6; int
0x18002a3c5  mov     rcx, r10; int
0x18002a3c8  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a3cd  mov     rdx, rbx
0x18002a3d0  lea     rcx, [rbp+1E0h+var_50]
0x18002a3d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002a3dc  mov     rcx, rax
0x18002a3df  call    ?ForceOnlineVolume@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ForceOnlineVolume(std::wstring)
0x18002a3e4  nop
0x18002a3e5  mov     rcx, [rbp+1E0h+var_230]
0x18002a3e9  test    rcx, rcx
0x18002a3ec  jz      short loc_18002A3FB
0x18002a3ee  call    cs:__imp_CM_Unregister_Notification
0x18002a3f5  nop     dword ptr [rax+rax+00h]
0x18002a3fa  nop
0x18002a3fb  lea     rcx, [rbp+1E0h+var_250]
0x18002a3ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a404  mov     rax, rbx
0x18002a407  mov     rcx, [rbp+1E0h+var_10]
0x18002a40e  xor     rcx, rsp; StackCookie
0x18002a411  call    __security_check_cookie
0x18002a416  lea     r11, [rsp+2E0h+var_s0]
0x18002a41e  mov     rbx, [r11+20h]
0x18002a422  mov     rdi, [r11+28h]
0x18002a426  mov     rsp, r11
0x18002a429  pop     rbp
0x18002a42a  retn
0x18002a42c  mov     edx, 1Fh; DefaultErr
0x18002a431  mov     ecx, eax; CmReturnCode
0x18002a433  call    cs:__imp_CM_MapCrToWin32Err
0x18002a43a  nop     dword ptr [rax+rax+00h]
0x18002a43f  mov     r9d, eax; char *
0x18002a442  mov     rcx, [rbp+1E8h]; this
0x18002a449  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002a450  mov     edx, 165h; void *
0x18002a455  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
