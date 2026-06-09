# OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)

- ea: `0x180003770`
- end: `0x18000388c`
- name: `?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, void **, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003388`
- `0x18000354c`
- `0x180007170`

## callees

- `0x180003770`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800037f4`
- `KERNEL32!GetLastError` at `0x1800037f4`
- `KERNEL32!CloseHandle` at `0x180003821`
- `KERNEL32!CloseHandle` at `0x180003868`
- `KERNEL32!CloseHandle` at `0x180003821`
- `KERNEL32!CloseHandle` at `0x180003868`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1800037a1`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1800037a1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800037cb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180003837`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800037cb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180003837`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180003877`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180003877`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800037ea`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800037ea`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        void **a2,
        int *a3)
{
  ULONG active; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  BOOL v9; // eax
  DWORD pCount; // [rsp+50h] [rbp+20h] BYREF
  int v12; // [rsp+54h] [rbp+24h]
  void *phToken; // [rsp+58h] [rbp+28h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+60h] [rbp+30h] BYREF

  v12 = HIDWORD(this);
  ppSessionInfo = 0;
  pCount = 0;
  phToken = 0;
  active = WTSGetActiveConsoleSessionId();
  ppSessionInfo = 0;
  *a2 = 0;
  *a3 = 0;
  if ( active == -1 )
    goto LABEL_13;
  if ( WTSQueryUserToken(active, &phToken) )
    goto LABEL_12;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v8 = 0;
    v9 = 0;
    if ( !pCount )
    {
LABEL_13:
      v7 = 0;
      goto LABEL_14;
    }
    while ( !v9 )
    {
      if ( phToken )
        CloseHandle(phToken);
      v9 = WTSQueryUserToken(ppSessionInfo[v8].SessionId, &phToken);
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= pCount )
      {
        if ( !v9 )
          goto LABEL_13;
        break;
      }
    }
LABEL_12:
    *a2 = phToken;
    *a3 = 1;
    phToken = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_14:
  if ( phToken )
    CloseHandle(phToken);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return v7;
}

```

## disassembly

```asm
0x180003770  mov     [rsp-18h+arg_18], rbx
0x180003775  mov     qword ptr [rsp-18h+arg_0], rcx
0x18000377a  push    rbp
0x18000377b  push    rsi
0x18000377c  push    rdi
0x18000377d  mov     rbp, rsp
0x180003780  sub     rsp, 30h
0x180003784  mov     rdi, r8
0x180003787  mov     [rbp+ppSessionInfo], 0
0x18000378f  mov     rsi, rdx
0x180003792  mov     [rbp+arg_0], 0
0x180003799  mov     [rbp+phToken], 0
0x1800037a1  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800037a7  mov     [rbp+ppSessionInfo], 0
0x1800037af  mov     qword ptr [rsi], 0
0x1800037b6  mov     dword ptr [rdi], 0
0x1800037bc  cmp     eax, 0FFFFFFFFh
0x1800037bf  jz      loc_18000385D
0x1800037c5  lea     rdx, [rbp+phToken]; phToken
0x1800037c9  mov     ecx, eax; SessionId
0x1800037cb  call    cs:__imp_WTSQueryUserToken
0x1800037d1  test    eax, eax
0x1800037d3  jnz     short loc_180003848
0x1800037d5  xor     edx, edx; Reserved
0x1800037d7  lea     rax, [rbp+arg_0]
0x1800037db  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1800037df  mov     [rsp+30h+pCount], rax; pCount
0x1800037e4  xor     ecx, ecx; hServer
0x1800037e6  lea     r8d, [rdx+1]; Version
0x1800037ea  call    cs:__imp_WTSEnumerateSessionsW
0x1800037f0  test    eax, eax
0x1800037f2  jnz     short loc_18000380B
0x1800037f4  call    cs:__imp_GetLastError
0x1800037fa  mov     ebx, eax
0x1800037fc  test    eax, eax
0x1800037fe  jle     short loc_18000385F
0x180003800  movzx   ebx, ax
0x180003803  or      ebx, 80070000h
0x180003809  jmp     short loc_18000385F
0x18000380b  xor     ebx, ebx
0x18000380d  xor     eax, eax
0x18000380f  cmp     [rbp+arg_0], eax
0x180003812  jbe     short loc_18000385D
0x180003814  test    eax, eax
0x180003816  jnz     short loc_180003848
0x180003818  mov     rcx, [rbp+phToken]; hObject
0x18000381c  test    rcx, rcx
0x18000381f  jz      short loc_180003827
0x180003821  call    cs:__imp_CloseHandle
0x180003827  mov     rcx, [rbp+ppSessionInfo]
0x18000382b  lea     r8, [rbx+rbx*2]
0x18000382f  lea     rdx, [rbp+phToken]; phToken
0x180003833  mov     ecx, [rcx+r8*8]; SessionId
0x180003837  call    cs:__imp_WTSQueryUserToken
0x18000383d  inc     ebx
0x18000383f  cmp     ebx, [rbp+arg_0]
0x180003842  jb      short loc_180003814
0x180003844  test    eax, eax
0x180003846  jz      short loc_18000385D
0x180003848  mov     rax, [rbp+phToken]
0x18000384c  mov     [rsi], rax
0x18000384f  mov     dword ptr [rdi], 1
0x180003855  mov     [rbp+phToken], 0
0x18000385d  xor     ebx, ebx
0x18000385f  mov     rcx, [rbp+phToken]; hObject
0x180003863  test    rcx, rcx
0x180003866  jz      short loc_18000386E
0x180003868  call    cs:__imp_CloseHandle
0x18000386e  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180003872  test    rcx, rcx
0x180003875  jz      short loc_18000387D
0x180003877  call    cs:__imp_WTSFreeMemory
0x18000387d  mov     eax, ebx
0x18000387f  mov     rbx, [rsp+30h+arg_18]
0x180003884  add     rsp, 30h
0x180003888  pop     rdi
0x180003889  pop     rsi
0x18000388a  pop     rbp
0x18000388b  retn
```
