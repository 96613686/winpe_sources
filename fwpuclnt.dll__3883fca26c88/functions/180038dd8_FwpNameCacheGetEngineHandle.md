# FwpNameCacheGetEngineHandle

- ea: `0x180038dd8`
- end: `0x180038ebe`
- name: `FwpNameCacheGetEngineHandle`
- size: `230`
- prototype: `__int64 __fastcall(HANDLE *engineHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180009340`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180007e38`
- `0x18000d7a8`
- `0x180038a44`
- `0x180038ae8`
- `0x180038dd8`
- `0x180039480`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038e47`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180038e39`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180038e39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e82`

## string_xrefs

- `0x180038e1f`: `FwpNameCacheGetEngineHandle`
- `0x180038e9b`: `FwpNameCacheGetEngineHandle`

## pseudocode

```c
__int64 __fastcall FwpNameCacheGetEngineHandle(HANDLE *engineHandle, __int64 a2, LPVOID *a3)
{
  __int64 TokenUserFromThread; // rbx
  __int64 v7; // rcx
  __int64 EngineHandleFromSid; // rax
  DWORD ThreadId; // ebx

  *a3 = 0;
  TokenUserFromThread = FwppGetTokenUserFromThread(a3);
  if ( TokenUserFromThread
    || ((WfpCriticalSectionEnterBusyWait(&gNameCacheState), !byte_18007C401)
      ? (!hObject || (ThreadId = GetThreadId(hObject), ThreadId != GetCurrentThreadId())
       ? (EngineHandleFromSid = FwpGetEngineHandleFromSid(*(PSID *)*a3, engineHandle))
       : (EngineHandleFromSid = FwpGetEngineHandleFromReresolve(a2, engineHandle)))
      : (EngineHandleFromSid = WfpReportSysErrorAsWinError(v7, "FwpNameCacheGetEngineHandle", 641)),
        TokenUserFromThread = EngineHandleFromSid,
        LeaveCriticalSection(&gNameCacheState),
        TokenUserFromThread) )
  {
    WfpMemFree(a3);
    *a3 = 0;
    WfpReportError(TokenUserFromThread, "FwpNameCacheGetEngineHandle");
  }
  return TokenUserFromThread;
}

```

## disassembly

```asm
0x180038dd8  push    rbx
0x180038dda  push    rbp
0x180038ddb  push    rsi
0x180038ddc  push    rdi
0x180038ddd  sub     rsp, 28h
0x180038de1  mov     rsi, rcx
0x180038de4  mov     qword ptr [r8], 0
0x180038deb  mov     rcx, r8
0x180038dee  mov     rdi, r8
0x180038df1  mov     rbp, rdx
0x180038df4  call    FwppGetTokenUserFromThread
0x180038df9  mov     rbx, rax
0x180038dfc  test    rax, rax
0x180038dff  jnz     loc_180038E93
0x180038e05  lea     rcx, gNameCacheState
0x180038e0c  call    WfpCriticalSectionEnterBusyWait
0x180038e11  cmp     cs:byte_18007C401, bl
0x180038e17  jz      short loc_180038E2D
0x180038e19  mov     r8d, 281h
0x180038e1f  lea     rdx, aFwpnamecachege; "FwpNameCacheGetEngineHandle"
0x180038e26  call    WfpReportSysErrorAsWinError
0x180038e2b  jmp     short loc_180038E78
0x180038e2d  mov     rcx, cs:hObject; Thread
0x180038e34  test    rcx, rcx
0x180038e37  jz      short loc_180038E64
0x180038e39  call    cs:__imp_GetThreadId
0x180038e40  nop     dword ptr [rax+rax+00h]
0x180038e45  mov     ebx, eax
0x180038e47  call    cs:__imp_GetCurrentThreadId
0x180038e4e  nop     dword ptr [rax+rax+00h]
0x180038e53  cmp     ebx, eax
0x180038e55  jnz     short loc_180038E64
0x180038e57  mov     rdx, rsi
0x180038e5a  mov     rcx, rbp
0x180038e5d  call    FwpGetEngineHandleFromReresolve
0x180038e62  jmp     short loc_180038E78
0x180038e64  mov     rcx, [rdi]
0x180038e67  mov     r8d, 1
0x180038e6d  mov     rdx, rsi; engineHandle
0x180038e70  mov     rcx, [rcx]; Sid2
0x180038e73  call    FwpGetEngineHandleFromSid
0x180038e78  mov     rbx, rax
0x180038e7b  lea     rcx, gNameCacheState; lpCriticalSection
0x180038e82  call    cs:__imp_LeaveCriticalSection
0x180038e89  nop     dword ptr [rax+rax+00h]
0x180038e8e  test    rbx, rbx
0x180038e91  jz      short loc_180038EB1
0x180038e93  mov     rcx, rdi
0x180038e96  call    WfpMemFree
0x180038e9b  lea     rdx, aFwpnamecachege; "FwpNameCacheGetEngineHandle"
0x180038ea2  mov     qword ptr [rdi], 0
0x180038ea9  mov     rcx, rbx
0x180038eac  call    WfpReportError
0x180038eb1  mov     rax, rbx
0x180038eb4  add     rsp, 28h
0x180038eb8  pop     rdi
0x180038eb9  pop     rsi
0x180038eba  pop     rbp
0x180038ebb  pop     rbx
0x180038ebc  retn
```
