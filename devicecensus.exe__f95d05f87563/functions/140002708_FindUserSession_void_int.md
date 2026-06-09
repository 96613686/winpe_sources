# FindUserSession(void * *,int *)

- ea: `0x140002708`
- end: `0x14000283d`
- name: `?FindUserSession@@YAJPEAPEAXPEAH@Z`
- size: `309`
- prototype: `__int64 __fastcall(void **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003610`

## callees

- `0x1400023e0`
- `0x140002708`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002799`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400027c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400027c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002828`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x14000275b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x14000275b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x140002819`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x140002819`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x14000278f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x14000278f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140002770`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1400027d6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140002770`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1400027d6`

## pseudocode

```c
__int64 __fastcall FindUserSession(void **a1, int *a2)
{
  DWORD active; // eax
  signed int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  DWORD pCount; // [rsp+50h] [rbp+20h] BYREF
  void *phToken; // [rsp+58h] [rbp+28h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+60h] [rbp+30h] BYREF

  phToken = 0;
  ppSessionInfo = 0;
  pCount = 0;
  *a1 = 0;
  *a2 = 0;
  if ( !(unsigned __int8)IsWTSFreeMemoryPresent() || !(unsigned __int8)IsWTSFreeMemoryPresent() )
  {
    v6 = -2147467259;
    goto LABEL_17;
  }
  active = WTSGetActiveConsoleSessionId();
  if ( active == -1 )
    goto LABEL_15;
  if ( WTSQueryUserToken(active, &phToken) )
    goto LABEL_14;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v7 = 0;
    if ( !pCount )
    {
LABEL_15:
      v6 = 0;
      goto LABEL_17;
    }
    while ( 1 )
    {
      if ( phToken )
        CloseHandle(phToken);
      if ( WTSQueryUserToken(ppSessionInfo[v7].SessionId, &phToken) )
        break;
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= pCount )
        goto LABEL_15;
    }
LABEL_14:
    *a1 = phToken;
    *a2 = 1;
    phToken = 0;
    goto LABEL_15;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_17:
  if ( (unsigned __int8)IsWTSFreeMemoryPresent() && ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  if ( phToken )
    CloseHandle(phToken);
  return v6;
}

```

## disassembly

```asm
0x140002708  mov     [rsp-18h+arg_18], rbx
0x14000270d  push    rbp
0x14000270e  push    rsi
0x14000270f  push    rdi
0x140002710  mov     rbp, rsp
0x140002713  sub     rsp, 30h
0x140002717  mov     rdi, rdx
0x14000271a  mov     [rbp+phToken], 0
0x140002722  mov     rsi, rcx
0x140002725  mov     [rbp+ppSessionInfo], 0
0x14000272d  mov     [rbp+arg_0], 0
0x140002734  mov     qword ptr [rcx], 0
0x14000273b  mov     dword ptr [rdx], 0
0x140002741  call    IsWTSFreeMemoryPresent
0x140002746  test    al, al
0x140002748  jz      loc_140002802
0x14000274e  call    IsWTSFreeMemoryPresent
0x140002753  test    al, al
0x140002755  jz      loc_140002802
0x14000275b  call    cs:__imp_WTSGetActiveConsoleSessionId
0x140002761  cmp     eax, 0FFFFFFFFh
0x140002764  jz      loc_1400027FE
0x14000276a  lea     rdx, [rbp+phToken]; phToken
0x14000276e  mov     ecx, eax; SessionId
0x140002770  call    cs:__imp_WTSQueryUserToken
0x140002776  test    eax, eax
0x140002778  jnz     short loc_1400027E9
0x14000277a  xor     edx, edx; Reserved
0x14000277c  lea     rax, [rbp+arg_0]
0x140002780  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x140002784  mov     [rsp+30h+pCount], rax; pCount
0x140002789  xor     ecx, ecx; hServer
0x14000278b  lea     r8d, [rdx+1]; Version
0x14000278f  call    cs:__imp_WTSEnumerateSessionsW
0x140002795  test    eax, eax
0x140002797  jnz     short loc_1400027B0
0x140002799  call    cs:__imp_GetLastError
0x14000279f  mov     ebx, eax
0x1400027a1  test    eax, eax
0x1400027a3  jle     short loc_140002807
0x1400027a5  movzx   ebx, ax
0x1400027a8  or      ebx, 80070000h
0x1400027ae  jmp     short loc_140002807
0x1400027b0  xor     ebx, ebx
0x1400027b2  cmp     [rbp+arg_0], ebx
0x1400027b5  jbe     short loc_1400027FE
0x1400027b7  mov     rcx, [rbp+phToken]; hObject
0x1400027bb  test    rcx, rcx
0x1400027be  jz      short loc_1400027C6
0x1400027c0  call    cs:__imp_CloseHandle
0x1400027c6  mov     rcx, [rbp+ppSessionInfo]
0x1400027ca  lea     r8, [rbx+rbx*2]
0x1400027ce  lea     rdx, [rbp+phToken]; phToken
0x1400027d2  mov     ecx, [rcx+r8*8]; SessionId
0x1400027d6  call    cs:__imp_WTSQueryUserToken
0x1400027dc  test    eax, eax
0x1400027de  jnz     short loc_1400027E9
0x1400027e0  inc     ebx
0x1400027e2  cmp     ebx, [rbp+arg_0]
0x1400027e5  jb      short loc_1400027B7
0x1400027e7  jmp     short loc_1400027FE
0x1400027e9  mov     rax, [rbp+phToken]
0x1400027ed  mov     [rsi], rax
0x1400027f0  mov     dword ptr [rdi], 1
0x1400027f6  mov     [rbp+phToken], 0
0x1400027fe  xor     ebx, ebx
0x140002800  jmp     short loc_140002807
0x140002802  mov     ebx, 80004005h
0x140002807  call    IsWTSFreeMemoryPresent
0x14000280c  test    al, al
0x14000280e  jz      short loc_14000281F
0x140002810  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x140002814  test    rcx, rcx
0x140002817  jz      short loc_14000281F
0x140002819  call    cs:__imp_WTSFreeMemory
0x14000281f  mov     rcx, [rbp+phToken]; hObject
0x140002823  test    rcx, rcx
0x140002826  jz      short loc_14000282E
0x140002828  call    cs:__imp_CloseHandle
0x14000282e  mov     eax, ebx
0x140002830  mov     rbx, [rsp+30h+arg_18]
0x140002835  add     rsp, 30h
0x140002839  pop     rdi
0x14000283a  pop     rsi
0x14000283b  pop     rbp
0x14000283c  retn
```
