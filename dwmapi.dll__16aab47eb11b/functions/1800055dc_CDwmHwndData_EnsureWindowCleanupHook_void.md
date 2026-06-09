# CDwmHwndData::EnsureWindowCleanupHook(void)

- ea: `0x1800055dc`
- end: `0x1800056c1`
- name: `?EnsureWindowCleanupHook@CDwmHwndData@@SAJXZ`
- size: `229`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180005534`

## callees

- `0x180003370`
- `0x1800055dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000565c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000565c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005674`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000561a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000561a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005620`
- `USER32!UnhookWinEvent` at `0x1800056ad`
- `USER32!UnhookWinEvent` at `0x1800056ad`
- `USER32!SetWinEventHook` at `0x18000564b`
- `USER32!SetWinEventHook` at `0x18000564b`

## pseudocode

```c
__int64 CDwmHwndData::EnsureWindowCleanupHook(void)
{
  unsigned int v0; // ebx
  DWORD idProcess; // eax
  HWINEVENTHOOK v3; // rdi
  signed int LastError; // eax

  v0 = 0;
  if ( !CDwmHwndData::s_hCleanupHook )
  {
    LeaveCriticalSection(&CDwmHwndData::s_cs);
    SetLastError(0);
    idProcess = GetCurrentProcessId();
    v3 = SetWinEventHook(0x8001u, 0x8001u, g_hDwmApiInstance, CDwmHwndData::WinEventCallback, idProcess, 0, 4u);
    if ( v3 )
    {
      EnterCriticalSection(&CDwmHwndData::s_cs);
      if ( !CDwmHwndData::s_hCleanupHook )
      {
        CDwmHwndData::s_hCleanupHook = v3;
        return v0;
      }
      LeaveCriticalSection(&CDwmHwndData::s_cs);
      UnhookWinEvent(v3);
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      if ( (v0 & 0x80000000) == 0 )
        v0 = -2003304445;
      DoStackCaptureDirect(v0, 0x36u);
    }
    EnterCriticalSection(&CDwmHwndData::s_cs);
  }
  return v0;
}

```

## disassembly

```asm
0x1800055dc  mov     [rsp+arg_0], rbx
0x1800055e1  mov     [rsp+arg_8], rbp
0x1800055e6  push    rdi
0x1800055e7  sub     rsp, 40h
0x1800055eb  xor     ebx, ebx
0x1800055ed  cmp     cs:?s_hCleanupHook@CDwmHwndData@@0PEAUHWINEVENTHOOK__@@EA, rbx; HWINEVENTHOOK__ * CDwmHwndData::s_hCleanupHook
0x1800055f4  jz      short loc_180005608
0x1800055f6  mov     rbp, [rsp+48h+arg_8]
0x1800055fb  mov     eax, ebx
0x1800055fd  mov     rbx, [rsp+48h+arg_0]
0x180005602  add     rsp, 40h
0x180005606  pop     rdi
0x180005607  retn
0x180005608  lea     rbp, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; CDwmCS CDwmHwndData::s_cs
0x18000560f  mov     rcx, rbp; lpCriticalSection
0x180005612  call    cs:__imp_LeaveCriticalSection
0x180005618  xor     ecx, ecx; dwErrCode
0x18000561a  call    cs:__imp_SetLastError
0x180005620  call    cs:__imp_GetCurrentProcessId
0x180005626  mov     r8, cs:?g_hDwmApiInstance@@3PEAUHINSTANCE__@@EA; hmodWinEventProc
0x18000562d  lea     r9, ?WinEventCallback@CDwmHwndData@@CAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z; pfnWinEventProc
0x180005634  mov     ecx, 8001h; eventMin
0x180005639  mov     [rsp+48h+dwFlags], 4; dwFlags
0x180005641  mov     edx, ecx; eventMax
0x180005643  mov     [rsp+48h+idThread], ebx; idThread
0x180005647  mov     [rsp+48h+idProcess], eax; idProcess
0x18000564b  call    cs:__imp_SetWinEventHook
0x180005651  mov     rdi, rax
0x180005654  test    rax, rax
0x180005657  jz      short loc_180005674
0x180005659  mov     rcx, rbp; lpCriticalSection
0x18000565c  call    cs:__imp_EnterCriticalSection
0x180005662  cmp     cs:?s_hCleanupHook@CDwmHwndData@@0PEAUHWINEVENTHOOK__@@EA, rbx; HWINEVENTHOOK__ * CDwmHwndData::s_hCleanupHook
0x180005669  jnz     short loc_1800056A1
0x18000566b  mov     cs:?s_hCleanupHook@CDwmHwndData@@0PEAUHWINEVENTHOOK__@@EA, rdi; HWINEVENTHOOK__ * CDwmHwndData::s_hCleanupHook
0x180005672  jmp     short loc_1800055F6
0x180005674  call    cs:__imp_GetLastError
0x18000567a  mov     ebx, eax
0x18000567c  test    eax, eax
0x18000567e  jle     short loc_180005689
0x180005680  movzx   ebx, ax
0x180005683  or      ebx, 80070000h
0x180005689  test    ebx, ebx
0x18000568b  mov     eax, 88980003h
0x180005690  mov     edx, 36h ; '6'; unsigned int
0x180005695  cmovns  ebx, eax
0x180005698  mov     ecx, ebx; int
0x18000569a  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000569f  jmp     short loc_1800056B3
0x1800056a1  mov     rcx, rbp; lpCriticalSection
0x1800056a4  call    cs:__imp_LeaveCriticalSection
0x1800056aa  mov     rcx, rdi; hWinEventHook
0x1800056ad  call    cs:__imp_UnhookWinEvent
0x1800056b3  mov     rcx, rbp; lpCriticalSection
0x1800056b6  call    cs:__imp_EnterCriticalSection
0x1800056bc  jmp     loc_1800055F6
```
