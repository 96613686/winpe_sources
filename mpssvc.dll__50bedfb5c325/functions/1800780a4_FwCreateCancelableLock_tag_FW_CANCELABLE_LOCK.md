# FwCreateCancelableLock(_tag_FW_CANCELABLE_LOCK *)

- ea: `0x1800780a4`
- end: `0x180078240`
- name: `?FwCreateCancelableLock@@YAJPEAU_tag_FW_CANCELABLE_LOCK@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct _tag_FW_CANCELABLE_LOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007a360`

## callees

- `0x18000a710`
- `0x18002f380`
- `0x18002fa40`
- `0x1800780a4`
- `0x180078248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800780e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007813b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800781bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800780e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007813b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800781bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800780d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800780d0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180078126`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180078126`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800781a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800781a8`

## pseudocode

```c
__int64 __fastcall FwCreateCancelableLock(struct _tag_FW_CANCELABLE_LOCK *a1)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  HANDLE MutexW; // rax
  signed int v8; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 v12; // rcx
  char v14; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+34h] [rbp+Ch]

  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  *((_OWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 6) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)a1 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v6 = 10;
LABEL_13:
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids, v4);
LABEL_14:
    if ( (v4 & 0x80000000) != 0 )
      FwDestroyCancelableLock(a1);
    return v4;
  }
  MutexW = CreateMutexW(0, 0, 0);
  *((_QWORD *)a1 + 1) = MutexW;
  if ( !MutexW )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v6 = 11;
    goto LABEL_13;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(FwLockWatchDogTimerCallback, 0, 0);
  v4 = 0;
  *((_QWORD *)a1 + 6) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    v11 = 3000;
    if ( (unsigned int)FwTraceLoggingDiagnosticsEventFeatureEnabled() )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(v12, &v14);
      v11 = v15;
    }
    gFwLockWatchDogFileDueTime = (struct _FILETIME)(-10000 * v11);
  }
  else
  {
    v10 = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids, v10);
  }
  return v4;
}

```

## disassembly

```asm
0x1800780a4  mov     [rsp+arg_8], rbx
0x1800780a9  push    rdi
0x1800780aa  sub     rsp, 20h
0x1800780ae  xorps   xmm0, xmm0
0x1800780b1  xor     eax, eax
0x1800780b3  movups  xmmword ptr [rcx], xmm0
0x1800780b6  mov     rdi, rcx
0x1800780b9  xor     r9d, r9d; lpName
0x1800780bc  movups  xmmword ptr [rcx+10h], xmm0
0x1800780c0  xor     r8d, r8d; bInitialState
0x1800780c3  lea     edx, [rax+1]; bManualReset
0x1800780c6  movups  xmmword ptr [rcx+20h], xmm0
0x1800780ca  mov     [rcx+30h], rax
0x1800780ce  xor     ecx, ecx; lpEventAttributes
0x1800780d0  call    cs:__imp_CreateEventW
0x1800780d7  nop     dword ptr [rax+rax+00h]
0x1800780dc  mov     [rdi], rax
0x1800780df  test    rax, rax
0x1800780e2  jnz     short loc_18007811F
0x1800780e4  call    cs:__imp_GetLastError
0x1800780eb  nop     dword ptr [rax+rax+00h]
0x1800780f0  mov     ebx, eax
0x1800780f2  test    eax, eax
0x1800780f4  jle     short loc_1800780FF
0x1800780f6  movzx   ebx, ax
0x1800780f9  or      ebx, 80070000h
0x1800780ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180078106  lea     rax, WPP_GLOBAL_Control
0x18007810d  cmp     rcx, rax
0x180078110  jz      short loc_180078187
0x180078112  test    byte ptr [rcx+1Ch], 1
0x180078116  jz      short loc_180078187
0x180078118  mov     edx, 0Ah
0x18007811d  jmp     short loc_180078174
0x18007811f  xor     r8d, r8d; lpName
0x180078122  xor     edx, edx; bInitialOwner
0x180078124  xor     ecx, ecx; lpMutexAttributes
0x180078126  call    cs:__imp_CreateMutexW
0x18007812d  nop     dword ptr [rax+rax+00h]
0x180078132  mov     [rdi+8], rax
0x180078136  test    rax, rax
0x180078139  jnz     short loc_18007819C
0x18007813b  call    cs:__imp_GetLastError
0x180078142  nop     dword ptr [rax+rax+00h]
0x180078147  mov     ebx, eax
0x180078149  test    eax, eax
0x18007814b  jle     short loc_180078156
0x18007814d  movzx   ebx, ax
0x180078150  or      ebx, 80070000h
0x180078156  mov     rcx, cs:WPP_GLOBAL_Control
0x18007815d  lea     rax, WPP_GLOBAL_Control
0x180078164  cmp     rcx, rax
0x180078167  jz      short loc_180078187
0x180078169  test    byte ptr [rcx+1Ch], 1
0x18007816d  jz      short loc_180078187
0x18007816f  mov     edx, 0Bh
0x180078174  mov     rcx, [rcx+10h]
0x180078178  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x18007817f  mov     r9d, ebx
0x180078182  call    WPP_SF_d
0x180078187  test    ebx, ebx
0x180078189  jns     loc_180078232
0x18007818f  mov     rcx, rdi; struct _tag_FW_CANCELABLE_LOCK *
0x180078192  call    ?FwDestroyCancelableLock@@YAXPEAU_tag_FW_CANCELABLE_LOCK@@@Z; FwDestroyCancelableLock(_tag_FW_CANCELABLE_LOCK *)
0x180078197  jmp     loc_180078232
0x18007819c  xor     r8d, r8d; pcbe
0x18007819f  lea     rcx, ?FwLockWatchDogTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800781a6  xor     edx, edx; pv
0x1800781a8  call    cs:__imp_CreateThreadpoolTimer
0x1800781af  nop     dword ptr [rax+rax+00h]
0x1800781b4  xor     ebx, ebx
0x1800781b6  mov     [rdi+30h], rax
0x1800781ba  test    rax, rax
0x1800781bd  jnz     short loc_1800781FC
0x1800781bf  call    cs:__imp_GetLastError
0x1800781c6  nop     dword ptr [rax+rax+00h]
0x1800781cb  mov     r9d, eax
0x1800781ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800781d5  lea     rax, WPP_GLOBAL_Control
0x1800781dc  cmp     rcx, rax
0x1800781df  jz      short loc_180078232
0x1800781e1  test    byte ptr [rcx+1Ch], 1
0x1800781e5  jz      short loc_180078232
0x1800781e7  mov     rcx, [rcx+10h]
0x1800781eb  lea     edx, [rbx+0Ch]
0x1800781ee  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x1800781f5  call    WPP_SF_d
0x1800781fa  jmp     short loc_180078232
0x1800781fc  mov     edi, 0BB8h
0x180078201  call    FwTraceLoggingDiagnosticsEventFeatureEnabled
0x180078206  test    eax, eax
0x180078208  jz      short loc_180078218
0x18007820a  lea     rdx, [rsp+28h+arg_0]
0x18007820f  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(void)
0x180078214  mov     edi, [rsp+28h+arg_4]
0x180078218  imul    rcx, rdi, 0FFFFFFFFFFFFD8F0h
0x18007821f  mov     rdx, rcx
0x180078222  mov     cs:?gFwLockWatchDogFileDueTime@@3U_FILETIME@@A.dwLowDateTime, ecx; _FILETIME gFwLockWatchDogFileDueTime ...
0x180078228  shr     rdx, 20h
0x18007822c  mov     cs:?gFwLockWatchDogFileDueTime@@3U_FILETIME@@A.dwHighDateTime, edx; _FILETIME gFwLockWatchDogFileDueTime ...
0x180078232  mov     eax, ebx
0x180078234  mov     rbx, [rsp+28h+arg_8]
0x180078239  add     rsp, 20h
0x18007823d  pop     rdi
0x18007823e  retn
```
