# FwCreateCancelableLock(_tag_FW_CANCELABLE_LOCK *)

- ea: `0x180074b3c`
- end: `0x180074cb3`
- name: `?FwCreateCancelableLock@@YAJPEAU_tag_FW_CANCELABLE_LOCK@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(struct _tag_FW_CANCELABLE_LOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180076c20`

## callees

- `0x18000af3c`
- `0x18002bd88`
- `0x18002c430`
- `0x180074b3c`
- `0x180074cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c39`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180074bb2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180074bb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180074b68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180074b68`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180074c28`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180074c28`

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
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids, v4);
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
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids, v10);
  }
  return v4;
}

```

## disassembly

```asm
0x180074b3c  mov     [rsp+arg_8], rbx
0x180074b41  push    rdi
0x180074b42  sub     rsp, 20h
0x180074b46  xorps   xmm0, xmm0
0x180074b49  xor     eax, eax
0x180074b4b  movups  xmmword ptr [rcx], xmm0
0x180074b4e  mov     rdi, rcx
0x180074b51  xor     r9d, r9d; lpName
0x180074b54  movups  xmmword ptr [rcx+10h], xmm0
0x180074b58  xor     r8d, r8d; bInitialState
0x180074b5b  lea     edx, [rax+1]; bManualReset
0x180074b5e  movups  xmmword ptr [rcx+20h], xmm0
0x180074b62  mov     [rcx+30h], rax
0x180074b66  xor     ecx, ecx; lpEventAttributes
0x180074b68  call    cs:__imp_CreateEventW
0x180074b6e  mov     [rdi], rax
0x180074b71  test    rax, rax
0x180074b74  jnz     short loc_180074BAB
0x180074b76  call    cs:__imp_GetLastError
0x180074b7c  mov     ebx, eax
0x180074b7e  test    eax, eax
0x180074b80  jle     short loc_180074B8B
0x180074b82  movzx   ebx, ax
0x180074b85  or      ebx, 80070000h
0x180074b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180074b92  lea     rax, WPP_GLOBAL_Control
0x180074b99  cmp     rcx, rax
0x180074b9c  jz      short loc_180074C07
0x180074b9e  test    byte ptr [rcx+1Ch], 1
0x180074ba2  jz      short loc_180074C07
0x180074ba4  mov     edx, 0Ah
0x180074ba9  jmp     short loc_180074BF4
0x180074bab  xor     r8d, r8d; lpName
0x180074bae  xor     edx, edx; bInitialOwner
0x180074bb0  xor     ecx, ecx; lpMutexAttributes
0x180074bb2  call    cs:__imp_CreateMutexW
0x180074bb8  mov     [rdi+8], rax
0x180074bbc  test    rax, rax
0x180074bbf  jnz     short loc_180074C1C
0x180074bc1  call    cs:__imp_GetLastError
0x180074bc7  mov     ebx, eax
0x180074bc9  test    eax, eax
0x180074bcb  jle     short loc_180074BD6
0x180074bcd  movzx   ebx, ax
0x180074bd0  or      ebx, 80070000h
0x180074bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180074bdd  lea     rax, WPP_GLOBAL_Control
0x180074be4  cmp     rcx, rax
0x180074be7  jz      short loc_180074C07
0x180074be9  test    byte ptr [rcx+1Ch], 1
0x180074bed  jz      short loc_180074C07
0x180074bef  mov     edx, 0Bh
0x180074bf4  mov     rcx, [rcx+10h]
0x180074bf8  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074bff  mov     r9d, ebx
0x180074c02  call    WPP_SF_d
0x180074c07  test    ebx, ebx
0x180074c09  jns     loc_180074CA6
0x180074c0f  mov     rcx, rdi; struct _tag_FW_CANCELABLE_LOCK *
0x180074c12  call    ?FwDestroyCancelableLock@@YAXPEAU_tag_FW_CANCELABLE_LOCK@@@Z; FwDestroyCancelableLock(_tag_FW_CANCELABLE_LOCK *)
0x180074c17  jmp     loc_180074CA6
0x180074c1c  xor     r8d, r8d; pcbe
0x180074c1f  lea     rcx, ?FwLockWatchDogTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180074c26  xor     edx, edx; pv
0x180074c28  call    cs:__imp_CreateThreadpoolTimer
0x180074c2e  xor     ebx, ebx
0x180074c30  mov     [rdi+30h], rax
0x180074c34  test    rax, rax
0x180074c37  jnz     short loc_180074C70
0x180074c39  call    cs:__imp_GetLastError
0x180074c3f  mov     r9d, eax
0x180074c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180074c49  lea     rax, WPP_GLOBAL_Control
0x180074c50  cmp     rcx, rax
0x180074c53  jz      short loc_180074CA6
0x180074c55  test    byte ptr [rcx+1Ch], 1
0x180074c59  jz      short loc_180074CA6
0x180074c5b  mov     rcx, [rcx+10h]
0x180074c5f  lea     edx, [rbx+0Ch]
0x180074c62  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180074c69  call    WPP_SF_d
0x180074c6e  jmp     short loc_180074CA6
0x180074c70  mov     edi, 0BB8h
0x180074c75  call    FwTraceLoggingDiagnosticsEventFeatureEnabled
0x180074c7a  test    eax, eax
0x180074c7c  jz      short loc_180074C8C
0x180074c7e  lea     rdx, [rsp+28h+arg_0]
0x180074c83  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(void)
0x180074c88  mov     edi, [rsp+28h+arg_4]
0x180074c8c  imul    rcx, rdi, 0FFFFFFFFFFFFD8F0h
0x180074c93  mov     rdx, rcx
0x180074c96  mov     cs:?gFwLockWatchDogFileDueTime@@3U_FILETIME@@A.dwLowDateTime, ecx; _FILETIME gFwLockWatchDogFileDueTime ...
0x180074c9c  shr     rdx, 20h
0x180074ca0  mov     cs:?gFwLockWatchDogFileDueTime@@3U_FILETIME@@A.dwHighDateTime, edx; _FILETIME gFwLockWatchDogFileDueTime ...
0x180074ca6  mov     eax, ebx
0x180074ca8  mov     rbx, [rsp+28h+arg_8]
0x180074cad  add     rsp, 20h
0x180074cb1  pop     rdi
0x180074cb2  retn
```
