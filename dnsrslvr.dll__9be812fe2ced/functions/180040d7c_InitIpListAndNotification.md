# InitIpListAndNotification

- ea: `0x180040d7c`
- end: `0x180040e76`
- name: `InitIpListAndNotification`
- size: `250`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800495c0`

## callees

- `0x180040d7c`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e47`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040dab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040deb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040dab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040deb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180040e35`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180040e35`

## pseudocode

```c
__int64 InitIpListAndNotification()
{
  DWORD LastError; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 28, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids);
  g_hIpNotifyThreadStopEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hIpNotifyThreadStopEvent )
  {
    g_IpNotifyEvent = CreateEventW(0, 1, 0, 0);
    if ( g_IpNotifyEvent )
    {
      g_IpNotifyThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)Ip_NotifyThread, 0, 0, &g_IpNotifyThreadId);
      if ( g_IpNotifyThread )
        return 0;
      LastError = GetLastError();
      if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
        return 0;
      v1 = 31;
    }
    else
    {
      LastError = GetLastError();
      if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
        return 0;
      v1 = 30;
    }
    v2 = 1055;
    goto LABEL_13;
  }
  LastError = GetLastError();
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v1 = 29;
    v2 = 1035;
LABEL_13:
    WPP_SF_d(v2, v1, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180040d7c  sub     rsp, 38h
0x180040d80  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040d87  jz      short loc_180040D9F
0x180040d89  mov     edx, 1Ch
0x180040d8e  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x180040d95  mov     ecx, 40Bh
0x180040d9a  call    WPP_SF_
0x180040d9f  xor     r9d, r9d; lpName
0x180040da2  xor     r8d, r8d; bInitialState
0x180040da5  xor     ecx, ecx; lpEventAttributes
0x180040da7  lea     edx, [r9+1]; bManualReset
0x180040dab  call    cs:__imp_CreateEventW
0x180040db1  mov     cs:g_hIpNotifyThreadStopEvent, rax
0x180040db8  test    rax, rax
0x180040dbb  jnz     short loc_180040DDF
0x180040dbd  call    cs:__imp_GetLastError
0x180040dc3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180040dca  jz      loc_180040E6F
0x180040dd0  mov     edx, 1Dh
0x180040dd5  mov     ecx, 40Bh
0x180040dda  jmp     loc_180040E60
0x180040ddf  xor     r9d, r9d; lpName
0x180040de2  xor     r8d, r8d; bInitialState
0x180040de5  xor     ecx, ecx; lpEventAttributes
0x180040de7  lea     edx, [r9+1]; bManualReset
0x180040deb  call    cs:__imp_CreateEventW
0x180040df1  mov     cs:g_IpNotifyEvent, rax
0x180040df8  test    rax, rax
0x180040dfb  jnz     short loc_180040E13
0x180040dfd  call    cs:__imp_GetLastError
0x180040e03  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x180040e0a  jge     short loc_180040E6F
0x180040e0c  mov     edx, 1Eh
0x180040e11  jmp     short loc_180040E5B
0x180040e13  lea     rax, g_IpNotifyThreadId
0x180040e1a  xor     r9d, r9d; lpParameter
0x180040e1d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180040e22  lea     r8, Ip_NotifyThread; lpStartAddress
0x180040e29  xor     edx, edx; dwStackSize
0x180040e2b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180040e33  xor     ecx, ecx; lpThreadAttributes
0x180040e35  call    cs:__imp_CreateThread
0x180040e3b  mov     cs:g_IpNotifyThread, rax
0x180040e42  test    rax, rax
0x180040e45  jnz     short loc_180040E6F
0x180040e47  call    cs:__imp_GetLastError
0x180040e4d  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x180040e54  jge     short loc_180040E6F
0x180040e56  mov     edx, 1Fh
0x180040e5b  mov     ecx, 41Fh
0x180040e60  mov     r9d, eax
0x180040e63  lea     r8, WPP_47231b6fde0d38f61fe3f363a8d5ac3f_Traceguids
0x180040e6a  call    WPP_SF_d
0x180040e6f  xor     eax, eax
0x180040e71  add     rsp, 38h
0x180040e75  retn
```
