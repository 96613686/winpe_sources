# ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,long,void (*)(void))

- ea: `0x18000c520`
- end: `0x18000c75f`
- name: `??0ScopedWatchdogTimer@@QEAA@KJP6AXXZ@Z`
- size: `575`
- prototype: `ScopedWatchdogTimer *__fastcall(PVOID Context, ULONG dwMilliseconds, int, void (*)(void))`
- caller_count: `32`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800094cc`
- `0x180009d48`
- `0x18000a24c`
- `0x18000a544`
- `0x18000a9dc`
- `0x18000ace0`
- `0x18000b0b0`
- `0x18000b0f8`
- `0x18000b1f0`
- `0x18000b640`
- `0x18000bf90`
- `0x180030480`
- `0x180032db0`
- `0x1800361b8`
- `0x180045ea0`
- `0x180046f5c`
- `0x180059bd4`
- `0x18005fe4c`
- `0x1800606e4`
- `0x18006089c`
- `0x180068880`
- `0x18006c12c`
- `0x180077d24`
- `0x180078060`
- `0x180079058`
- `0x18007cb80`
- `0x18008030c`
- `0x180080678`
- `0x180081f0c`
- `0x180095384`
- `0x18009a840`
- `0x18009aae4`

## callees

- `0x18000c520`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c5d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c5d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c57b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c57b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c62b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c62b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c614`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c614`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c6c5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c6c5`

## pseudocode

```c
ScopedWatchdogTimer *__fastcall ScopedWatchdogTimer::ScopedWatchdogTimer(
        _QWORD *Context,
        ULONG dwMilliseconds,
        int a3,
        void (*a4)(void))
{
  PVOID v5; // rbx
  HANDLE EventW; // rax
  unsigned int LastError; // ecx
  unsigned int v8; // ecx
  const ComError *v10; // [rsp+30h] [rbp-148h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-138h] BYREF
  __int128 v12; // [rsp+48h] [rbp-130h]
  int v13; // [rsp+58h] [rbp-120h]
  int v14; // [rsp+5Ch] [rbp-11Ch]
  int v15; // [rsp+60h] [rbp-118h]
  void **v16; // [rsp+A0h] [rbp-D8h] BYREF
  __int128 v17; // [rsp+A8h] [rbp-D0h]
  unsigned int v18; // [rsp+B8h] [rbp-C0h]
  int v19; // [rsp+BCh] [rbp-BCh]
  int v20; // [rsp+C0h] [rbp-B8h]
  void **v21; // [rsp+100h] [rbp-78h] BYREF
  __int128 v22; // [rsp+108h] [rbp-70h]
  unsigned int v23; // [rsp+118h] [rbp-60h]
  int v24; // [rsp+11Ch] [rbp-5Ch]
  int v25; // [rsp+120h] [rbp-58h]
  LPVOID Contexta; // [rsp+198h] [rbp+20h] BYREF

  Contexta = a4;
  v5 = Context;
  *(_DWORD *)Context = a3;
  Context[1] = 0;
  *((_DWORD *)Context + 4) = GetCurrentThreadId();
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  Contexta = 0;
  if ( !InitOnceExecuteOnce(
          &g_GlobalWatchdogTimerConfigInfo,
          LazyGlobal<WatchdogTimerConfigInfo>::LazyGlobalInitializer,
          0,
          &Contexta) )
  {
    v12 = 0;
    pExceptionObject = &ComError::`vftable';
    v13 = -2147024882;
    v14 = 51;
    v15 = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( *((_BYTE *)Contexta + 4) && !IsDebuggerPresent() )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_a2fd4d7841f73b87c8a9d4021a310f46_Traceguids, v5);
    *((_QWORD *)v5 + 5) = GetTickCount64();
    EventW = CreateEventW(0, 1, 0, 0);
    try
    {
      *((_QWORD *)v5 + 4) = EventW;
      if ( !EventW )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v17 = 0;
        v16 = &ComError::`vftable';
        v18 = LastError;
        v19 = 70;
        v20 = 1;
        throw (ComError *)&v16;
      }
      if ( !RegisterWaitForSingleObject(
              (PHANDLE)v5 + 3,
              EventW,
              ScopedWatchdogTimer::WaitCallback,
              v5,
              dwMilliseconds,
              8u) )
      {
        if ( (int)GetLastError() > 0 )
          v8 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v8 = GetLastError();
        v22 = 0;
        v21 = &ComError::`vftable';
        v23 = v8;
        v24 = 81;
        v25 = 1;
        throw (ComError *)&v21;
      }
    }
    catch ( const ComError *v10 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_a2fd4d7841f73b87c8a9d4021a310f46_Traceguids,
          *((unsigned int *)v10 + 6));
      return (ScopedWatchdogTimer *)Context;
    }
  }
  return (ScopedWatchdogTimer *)v5;
}

```

## disassembly

```asm
0x18000c520  mov     [rsp+arg_8], rbx
0x18000c525  mov     [rsp+Context], r9
0x18000c52a  mov     [rsp+arg_0], rcx
0x18000c52f  push    rsi
0x18000c530  push    rdi
0x18000c531  push    r14
0x18000c533  sub     rsp, 160h
0x18000c53a  mov     esi, edx
0x18000c53c  mov     rbx, rcx
0x18000c53f  mov     [rcx], r8d
0x18000c542  xor     r14d, r14d
0x18000c545  mov     [rcx+8], r14
0x18000c549  call    cs:__imp_GetCurrentThreadId
0x18000c54f  mov     [rbx+10h], eax
0x18000c552  mov     [rbx+18h], r14
0x18000c556  mov     [rbx+20h], r14
0x18000c55a  mov     [rsp+178h+Context], r14
0x18000c562  lea     r9, [rsp+178h+Context]; Context
0x18000c56a  xor     r8d, r8d; Parameter
0x18000c56d  lea     rdx, ?LazyGlobalInitializer@?$LazyGlobal@VWatchdogTimerConfigInfo@@@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000c574  lea     rcx, ?g_GlobalWatchdogTimerConfigInfo@@3V?$LazyGlobal@VWatchdogTimerConfigInfo@@@@A; InitOnce
0x18000c57b  call    cs:__imp_InitOnceExecuteOnce
0x18000c581  test    eax, eax
0x18000c583  jnz     short loc_18000C5C3
0x18000c585  xorps   xmm0, xmm0
0x18000c588  movups  [rsp+178h+var_130], xmm0
0x18000c58d  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000c594  mov     [rsp+178h+pExceptionObject], rax
0x18000c599  mov     [rsp+178h+var_120], 8007000Eh
0x18000c5a1  mov     [rsp+178h+var_11C], 33h ; '3'
0x18000c5a9  mov     [rsp+178h+var_118], 1
0x18000c5b1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000c5b8  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18000c5bd  call    _CxxThrowException_0
0x18000c5c3  mov     rax, [rsp+178h+Context]
0x18000c5cb  cmp     [rax+4], r14b
0x18000c5cf  jz      loc_18000C748
0x18000c5d5  call    cs:__imp_IsDebuggerPresent
0x18000c5db  test    eax, eax
0x18000c5dd  jnz     loc_18000C748
0x18000c5e3  lea     rax, WPP_GLOBAL_Control
0x18000c5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5f1  cmp     rcx, rax
0x18000c5f4  jz      short loc_18000C614
0x18000c5f6  test    byte ptr [rcx+1Ch], 1
0x18000c5fa  jz      short loc_18000C614
0x18000c5fc  mov     edx, 0Bh
0x18000c601  mov     r9, rbx
0x18000c604  lea     r8, WPP_a2fd4d7841f73b87c8a9d4021a310f46_Traceguids
0x18000c60b  mov     rcx, [rcx+10h]
0x18000c60f  call    WPP_SF_q
0x18000c614  call    cs:__imp_GetTickCount64
0x18000c61a  mov     [rbx+28h], rax
0x18000c61e  xor     r9d, r9d; lpName
0x18000c621  xor     r8d, r8d; bInitialState
0x18000c624  mov     edx, 1; bManualReset
0x18000c629  xor     ecx, ecx; lpEventAttributes
0x18000c62b  call    cs:__imp_CreateEventW
0x18000c631  mov     [rbx+20h], rax
0x18000c635  test    rax, rax
0x18000c638  jnz     short loc_18000C6A8
0x18000c63a  call    cs:__imp_GetLastError
0x18000c640  test    eax, eax
0x18000c642  jg      short loc_18000C64E
0x18000c644  call    cs:__imp_GetLastError
0x18000c64a  mov     ecx, eax
0x18000c64c  jmp     short loc_18000C65D
0x18000c64e  call    cs:__imp_GetLastError
0x18000c654  movzx   ecx, ax
0x18000c657  or      ecx, 80070000h
0x18000c65d  xorps   xmm0, xmm0
0x18000c660  movups  [rsp+178h+var_D0], xmm0
0x18000c668  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000c66f  mov     [rsp+178h+var_D8], rax
0x18000c677  mov     [rsp+178h+var_C0], ecx
0x18000c67e  mov     [rsp+178h+var_BC], 46h ; 'F'
0x18000c689  mov     [rsp+178h+var_B8], 1
0x18000c694  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000c69b  lea     rcx, [rsp+178h+var_D8]; pExceptionObject
0x18000c6a3  call    _CxxThrowException_0
0x18000c6a8  mov     [rsp+178h+dwFlags], 8; dwFlags
0x18000c6b0  mov     [rsp+178h+dwMilliseconds], esi; dwMilliseconds
0x18000c6b4  mov     r9, rbx; Context
0x18000c6b7  lea     r8, ?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z; Callback
0x18000c6be  mov     rdx, rax; hObject
0x18000c6c1  lea     rcx, [rbx+18h]; phNewWaitObject
0x18000c6c5  call    cs:__imp_RegisterWaitForSingleObject
0x18000c6cb  test    eax, eax
0x18000c6cd  jnz     short loc_18000C73E
0x18000c6cf  call    cs:__imp_GetLastError
0x18000c6d5  test    eax, eax
0x18000c6d7  jg      short loc_18000C6E3
0x18000c6d9  call    cs:__imp_GetLastError
0x18000c6df  mov     ecx, eax
0x18000c6e1  jmp     short loc_18000C6F2
0x18000c6e3  call    cs:__imp_GetLastError
0x18000c6e9  movzx   ecx, ax
0x18000c6ec  or      ecx, 80070000h
0x18000c6f2  xorps   xmm0, xmm0
0x18000c6f5  movups  [rsp+178h+var_70], xmm0
0x18000c6fd  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000c704  mov     [rsp+178h+var_78], rax
0x18000c70c  mov     [rsp+178h+var_60], ecx
0x18000c713  mov     [rsp+178h+var_5C], 51h ; 'Q'
0x18000c71e  mov     [rsp+178h+var_58], 1
0x18000c729  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000c730  lea     rcx, [rsp+178h+var_78]; pExceptionObject
0x18000c738  call    _CxxThrowException_0
0x18000c73e  jmp     short loc_18000C748
0x18000c740  mov     rbx, [rsp+178h+arg_0]
0x18000c748  mov     rax, rbx
0x18000c74b  mov     rbx, [rsp+178h+arg_8]
0x18000c753  add     rsp, 160h
0x18000c75a  pop     r14
0x18000c75c  pop     rdi
0x18000c75d  pop     rsi
0x18000c75e  retn
```
