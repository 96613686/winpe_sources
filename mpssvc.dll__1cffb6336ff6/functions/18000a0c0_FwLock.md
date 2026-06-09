# FwLock

- ea: `0x18000a0c0`
- end: `0x18000a496`
- name: `FwLock`
- size: `982`
- prototype: `__int64(void)`
- caller_count: `70`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007484`
- `0x180008bc0`
- `0x1800097b0`
- `0x18002f7d4`
- `0x1800314c4`
- `0x180031b34`
- `0x180032b6c`
- `0x180033580`
- `0x1800350b0`
- `0x18003be24`
- `0x18003d0d8`
- `0x180042098`
- `0x18004236c`
- `0x180042fec`
- `0x180050be8`
- `0x180051eec`
- `0x180052ca0`
- `0x1800540a0`
- `0x180054748`
- `0x1800558ec`
- `0x180055f28`
- `0x180058430`
- `0x180059130`
- `0x18005f698`
- `0x180060a20`
- `0x180060bf0`
- `0x180060f00`
- `0x1800617c0`
- `0x18006a7e0`
- `0x18006b914`
- `0x180074d20`
- `0x1800755e0`
- `0x18007d2b8`
- `0x1800808a0`
- `0x180084d70`
- `0x180084f10`
- `0x18008a430`
- `0x180090d30`
- `0x180093130`
- `0x18009612c`
- `0x180096624`
- `0x180096b10`
- `0x180097df8`
- `0x18009866c`
- `0x1800989bc`
- `0x180098cd8`
- `0x180099038`
- `0x18009934c`
- `0x180099770`
- `0x180099b5c`

## callees

- `0x1800091dc`
- `0x18000a0c0`
- `0x18000af3c`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a3da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a472`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a3da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a0e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a27d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a0e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a175`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a168`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a168`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a29e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a29e`
- `fwbase!FwReportReturnError` at `0x18000a270`
- `fwbase!FwReportReturnError` at `0x18000a270`

## string_xrefs

- `0x18000a180`: `mpssvc.dll`
- `0x18000a1a4`: `mpssvc.dll`
- `0x18000a2d3`: `mpssvc.dll`

## pseudocode

```c
__int64 FwLock()
{
  ULONGLONG TickCount64; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v2; // r8
  unsigned int v3; // edi
  DWORD v4; // eax
  DWORD LastError; // eax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v9; // [rsp+34h] [rbp-45h] BYREF
  __int64 v10; // [rsp+38h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-29h] BYREF
  char *v13; // [rsp+60h] [rbp-19h]
  int v14; // [rsp+68h] [rbp-11h]
  int v15; // [rsp+6Ch] [rbp-Dh]
  unsigned int *v16; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  __int64 *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]

  TickCount64 = GetTickCount64();
  CurrentThreadId = GetCurrentThreadId();
  v3 = CurrentThreadId;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      14,
      WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
      CurrentThreadId,
      dword_18012BEC8);
  if ( gFwMain && hMutex )
  {
    v4 = WaitForMultipleObjectsEx(2u, &gFwMain, 0, 0xFFFFFFFF, 0);
    if ( v4 == 258 )
    {
      LastError = GetLastError();
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", 258, LastError);
      v6 = 0;
    }
    else if ( v4 == 129 )
    {
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)dword_18012BEC4, 0);
      dword_18012BEC4 = 1;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
          (unsigned int)dword_18012BEC8);
      v6 = 0;
    }
    else if ( v4 )
    {
      v6 = 0;
      if ( v4 == 1 )
      {
        dword_18012BEC8 = v3;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids, v3);
      }
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids, v3);
      v6 = -2147023781;
    }
  }
  else
  {
    v6 = -2147024809;
    FwReportReturnError("FwAcquireCancelableLock", 2147942487LL, v2);
  }
  qword_18012BED0 = TickCount64;
  qword_18012BED8 = GetTickCount64();
  SetThreadpoolTimer(pti, &gFwLockWatchDogFileDueTime, 0, 0);
  _InterlockedCompareExchange(&gIsFwWatchDogCanceled, 0, 1);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147023781 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v6, 0);
    if ( (unsigned int)dword_180126458 >= 6
      && (qword_180126468 & 0x400000000000LL) != 0
      && (qword_180126470 & 0x400000000000LL) == qword_180126470 )
    {
      EventDescriptor.Keyword = 0x400000000000LL;
      v18 = &v10;
      v10 = 0x1000000;
      v16 = &v8;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_180126460;
      v8 = v6;
      v19 = 8;
      v17 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = (unsigned __int16)*off_180126460;
      v13 = byte_18010E7AD;
      UserData.Reserved = 2;
      v14 = 42;
      v15 = 1;
      v9 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    if ( (unsigned int)dword_1801263B0 > 5 )
    {
      v9 = v6;
      v16 = &v9;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_1801263B8;
      v17 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_1801263B8;
      v13 = &byte_18010E507;
      UserData.Reserved = 2;
      v14 = 27;
      v15 = 1;
      v8 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1801263D0, &EventDescriptor, 0, 0, 3u, &UserData);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000a0c0  push    rbp
0x18000a0c2  push    rbx
0x18000a0c3  push    rsi
0x18000a0c4  push    rdi
0x18000a0c5  push    r14
0x18000a0c7  push    r15
0x18000a0c9  lea     rbp, [rsp-2Fh]
0x18000a0ce  sub     rsp, 0A8h
0x18000a0d5  mov     rax, cs:__security_cookie
0x18000a0dc  xor     rax, rsp
0x18000a0df  mov     [rbp+57h+var_40], rax
0x18000a0e3  call    cs:__imp_GetTickCount64
0x18000a0e9  mov     rsi, rax
0x18000a0ec  call    cs:__imp_GetCurrentThreadId
0x18000a0f2  mov     edi, eax
0x18000a0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0fb  lea     r15, WPP_GLOBAL_Control
0x18000a102  cmp     rcx, r15
0x18000a105  jz      short loc_18000A131
0x18000a107  test    byte ptr [rcx+1Ch], 4
0x18000a10b  jz      short loc_18000A131
0x18000a10d  mov     r8d, cs:dword_18012BEC8
0x18000a114  mov     edx, 0Eh
0x18000a119  mov     rcx, [rcx+10h]
0x18000a11d  mov     r9d, eax
0x18000a120  mov     [rsp+0D0h+bAlertable], r8d
0x18000a125  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18000a12c  call    WPP_SF_dd
0x18000a131  xor     r14d, r14d
0x18000a134  cmp     cs:?gFwMain@@3UFW_MAIN_COMPONENT@@A, r14; FW_MAIN_COMPONENT gFwMain
0x18000a13b  jz      loc_18000A262
0x18000a141  cmp     cs:hMutex, r14
0x18000a148  jz      loc_18000A262
0x18000a14e  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a154  mov     [rsp+0D0h+bAlertable], r14d; bAlertable
0x18000a159  xor     r8d, r8d; bWaitAll
0x18000a15c  lea     rdx, ?gFwMain@@3UFW_MAIN_COMPONENT@@A; lpHandles
0x18000a163  mov     ecx, 2; nCount
0x18000a168  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a16e  cmp     eax, 102h
0x18000a173  jnz     short loc_18000A197
0x18000a175  call    cs:__imp_GetLastError
0x18000a17b  mov     edx, 102h
0x18000a180  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18000a187  mov     r8d, eax
0x18000a18a  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000a18f  mov     ebx, r14d
0x18000a192  jmp     loc_18000A276
0x18000a197  cmp     eax, 81h
0x18000a19c  jnz     short loc_18000A1F3
0x18000a19e  mov     edx, cs:dword_18012BEC4
0x18000a1a4  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18000a1ab  xor     r8d, r8d
0x18000a1ae  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000a1b3  mov     cs:dword_18012BEC4, 1
0x18000a1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1c4  cmp     rcx, r15
0x18000a1c7  jz      short loc_18000A1EB
0x18000a1c9  test    byte ptr [rcx+1Ch], 1
0x18000a1cd  jz      short loc_18000A1EB
0x18000a1cf  mov     r9d, cs:dword_18012BEC8
0x18000a1d6  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18000a1dd  mov     rcx, [rcx+10h]
0x18000a1e1  mov     edx, 0Fh
0x18000a1e6  call    WPP_SF_d
0x18000a1eb  mov     ebx, r14d
0x18000a1ee  jmp     loc_18000A276
0x18000a1f3  test    eax, eax
0x18000a1f5  jnz     short loc_18000A228
0x18000a1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1fe  cmp     rcx, r15
0x18000a201  jz      short loc_18000A221
0x18000a203  test    byte ptr [rcx+1Ch], 4
0x18000a207  jz      short loc_18000A221
0x18000a209  mov     rcx, [rcx+10h]
0x18000a20d  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18000a214  mov     edx, 10h
0x18000a219  mov     r9d, edi
0x18000a21c  call    WPP_SF_d
0x18000a221  mov     ebx, 8007045Bh
0x18000a226  jmp     short loc_18000A276
0x18000a228  mov     ebx, r14d
0x18000a22b  cmp     eax, 1
0x18000a22e  jnz     short loc_18000A276
0x18000a230  mov     cs:dword_18012BEC8, edi
0x18000a236  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a23d  cmp     rcx, r15
0x18000a240  jz      short loc_18000A276
0x18000a242  test    byte ptr [rcx+1Ch], 4
0x18000a246  jz      short loc_18000A276
0x18000a248  mov     rcx, [rcx+10h]
0x18000a24c  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x18000a253  mov     edx, 11h
0x18000a258  mov     r9d, edi
0x18000a25b  call    WPP_SF_d
0x18000a260  jmp     short loc_18000A276
0x18000a262  mov     ebx, 80070057h
0x18000a267  lea     rcx, aFwacquirecance; "FwAcquireCancelableLock"
0x18000a26e  mov     edx, ebx
0x18000a270  call    cs:__imp_FwReportReturnError
0x18000a276  mov     cs:qword_18012BED0, rsi
0x18000a27d  call    cs:__imp_GetTickCount64
0x18000a283  mov     rcx, cs:pti; pti
0x18000a28a  lea     rdx, ?gFwLockWatchDogFileDueTime@@3U_FILETIME@@A; pftDueTime
0x18000a291  xor     r9d, r9d; msWindowLength
0x18000a294  mov     cs:qword_18012BED8, rax
0x18000a29b  xor     r8d, r8d; msPeriod
0x18000a29e  call    cs:__imp_SetThreadpoolTimer
0x18000a2a4  mov     edx, r14d
0x18000a2a7  mov     eax, 1
0x18000a2ac  lock cmpxchg cs:?gIsFwWatchDogCanceled@@3HC, edx; int volatile gIsFwWatchDogCanceled
0x18000a2b4  mov     edx, 80000000h
0x18000a2b9  lea     eax, [rbx+rdx]
0x18000a2bc  test    edx, eax
0x18000a2be  jnz     loc_18000A478
0x18000a2c4  cmp     ebx, 8007045Bh
0x18000a2ca  jz      loc_18000A478
0x18000a2d0  xor     r8d, r8d
0x18000a2d3  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18000a2da  mov     edx, ebx
0x18000a2dc  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000a2e1  mov     eax, cs:dword_180126458
0x18000a2e7  lea     rdi, _TraceLoggingMetadataEnd
0x18000a2ee  lea     rsi, _TraceLoggingMetadata
0x18000a2f5  test    eax, eax
0x18000a2f7  jz      loc_18000A3E0
0x18000a2fd  mov     eax, cs:dword_180126458
0x18000a303  cmp     eax, 5
0x18000a306  jbe     loc_18000A3E0
0x18000a30c  mov     rcx, cs:qword_180126470
0x18000a313  mov     rdx, 400000000000h
0x18000a31d  mov     rax, cs:qword_180126468
0x18000a324  test    rdx, rax
0x18000a327  jz      loc_18000A3E0
0x18000a32d  mov     rax, rcx
0x18000a330  and     rax, rdx
0x18000a333  cmp     rax, rcx
0x18000a336  jnz     loc_18000A3E0
0x18000a33c  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x18000a340  lea     rax, [rbp+57h+var_98]
0x18000a344  mov     [rbp+57h+var_50], rax
0x18000a348  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000a34c  lea     rax, [rbp+57h+var_A0]
0x18000a350  mov     [rbp+57h+var_98], 1000000h
0x18000a358  mov     [rbp+57h+var_60], rax
0x18000a35c  xor     r9d, r9d; RelatedActivityId
0x18000a35f  movzx   eax, cs:word_18010E7A3
0x18000a366  xor     r8d, r8d; ActivityId
0x18000a369  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000a36c  mov     rax, cs:off_180126460
0x18000a373  mov     [rbp+57h+var_80.Ptr], rax
0x18000a377  mov     [rbp+57h+var_A0], ebx
0x18000a37a  mov     [rbp+57h+var_48], 8
0x18000a382  mov     [rbp+57h+var_58], 4
0x18000a38a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000a391  movzx   eax, word ptr [rax]
0x18000a394  mov     [rbp+57h+var_80.Size], eax
0x18000a397  lea     rax, byte_18010E7AD
0x18000a39e  mov     [rbp+57h+var_70], rax
0x18000a3a2  mov     rax, rdi
0x18000a3a5  sub     eax, esi
0x18000a3a7  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000a3ae  mov     [rbp+57h+var_68], 2Ah ; '*'
0x18000a3b5  mov     [rbp+57h+var_64], 1
0x18000a3bc  mov     [rbp+57h+var_9C], eax
0x18000a3bf  mov     eax, [rbp+57h+var_9C]
0x18000a3c2  mov     rcx, cs:RegHandle; RegHandle
0x18000a3c9  lea     rax, [rbp+57h+var_80]
0x18000a3cd  mov     [rsp+0D0h+UserData], rax; UserData
0x18000a3d2  mov     [rsp+0D0h+bAlertable], 4; UserDataCount
0x18000a3da  call    cs:__imp_EventWriteTransfer
0x18000a3e0  mov     eax, cs:dword_1801263B0
0x18000a3e6  cmp     eax, 5
0x18000a3e9  jbe     loc_18000A478
0x18000a3ef  lea     rax, [rbp+57h+var_9C]
0x18000a3f3  mov     [rbp+57h+var_9C], ebx
0x18000a3f6  mov     [rbp+57h+var_60], rax
0x18000a3fa  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000a3fe  movzx   eax, cs:word_18010E4FD
0x18000a405  sub     edi, esi
0x18000a407  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000a40a  xor     r9d, r9d; RelatedActivityId
0x18000a40d  mov     rax, cs:off_1801263B8
0x18000a414  xor     r8d, r8d; ActivityId
0x18000a417  mov     [rbp+57h+var_80.Ptr], rax
0x18000a41b  mov     [rbp+57h+var_58], 4
0x18000a423  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000a42a  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000a42e  movzx   eax, word ptr [rax]
0x18000a431  mov     [rbp+57h+var_80.Size], eax
0x18000a434  lea     rax, byte_18010E507
0x18000a43b  mov     [rbp+57h+var_70], rax
0x18000a43f  lea     rax, [rbp+57h+var_80]
0x18000a443  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x18000a44a  mov     [rbp+57h+var_68], 1Bh
0x18000a451  mov     [rbp+57h+var_64], 1
0x18000a458  mov     [rsp+0D0h+UserData], rax; UserData
0x18000a45d  mov     [rbp+57h+var_A0], edi
0x18000a460  mov     ecx, [rbp+57h+var_A0]
0x18000a463  mov     rcx, cs:qword_1801263D0; RegHandle
0x18000a46a  mov     [rsp+0D0h+bAlertable], 3; UserDataCount
0x18000a472  call    cs:__imp_EventWriteTransfer
0x18000a478  mov     eax, ebx
0x18000a47a  mov     rcx, [rbp+57h+var_40]
0x18000a47e  xor     rcx, rsp; StackCookie
0x18000a481  call    __security_check_cookie
0x18000a486  add     rsp, 0A8h
0x18000a48d  pop     r15
0x18000a48f  pop     r14
0x18000a491  pop     rdi
0x18000a492  pop     rsi
0x18000a493  pop     rbx
0x18000a494  pop     rbp
0x18000a495  retn
```
