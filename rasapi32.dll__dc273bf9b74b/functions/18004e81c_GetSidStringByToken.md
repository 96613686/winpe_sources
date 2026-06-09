# GetSidStringByToken

- ea: `0x18004e81c`
- end: `0x18004e948`
- name: `GetSidStringByToken`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800da068`

## callees

- `0x18000b0f4`
- `0x18000c980`
- `0x180015f3c`
- `0x18004e580`
- `0x18004e81c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e849`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e849`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004e866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004e866`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004e879`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004e879`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e935`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e935`

## pseudocode

```c
__int64 __fastcall GetSidStringByToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  unsigned int LastError; // ebx
  HANDLE CurrentProcess; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    goto LABEL_13;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 18;
LABEL_8:
        WPP_SF_d(v5[2], v6, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, LastError);
        return LastError;
      }
      return LastError;
    }
LABEL_13:
    lpWideCharStr = 0;
    LastError = GetSidFromToken(TokenHandle, (HGLOBAL *)&lpWideCharStr);
    if ( !LastError )
      *a1 = StrdupWtoA(lpWideCharStr);
    Free0(lpWideCharStr);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return LastError;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 19;
    goto LABEL_8;
  }
  return LastError;
}

```

## disassembly

```asm
0x18004e81c  mov     [rsp+arg_0], rbx
0x18004e821  push    rdi
0x18004e822  sub     rsp, 20h
0x18004e826  mov     rdi, rcx
0x18004e829  mov     [rsp+28h+TokenHandle], 0
0x18004e832  call    cs:__imp_GetCurrentThread
0x18004e838  mov     edx, 0Ch; DesiredAccess
0x18004e83d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18004e842  mov     rcx, rax; ThreadHandle
0x18004e845  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18004e849  call    cs:__imp_OpenThreadToken
0x18004e84f  test    eax, eax
0x18004e851  jnz     loc_18004E8F6
0x18004e857  call    cs:__imp_GetLastError
0x18004e85d  mov     ebx, eax
0x18004e85f  cmp     eax, 3F0h
0x18004e864  jnz     short loc_18004E8D0
0x18004e866  call    cs:__imp_GetCurrentProcess
0x18004e86c  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18004e871  mov     edx, 0Ch; DesiredAccess
0x18004e876  mov     rcx, rax; ProcessHandle
0x18004e879  call    cs:__imp_OpenProcessToken
0x18004e87f  test    eax, eax
0x18004e881  jnz     short loc_18004E8F6
0x18004e883  call    cs:__imp_GetLastError
0x18004e889  mov     ebx, eax
0x18004e88b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e892  lea     rdx, WPP_GLOBAL_Control
0x18004e899  cmp     rcx, rdx
0x18004e89c  jz      loc_18004E93B
0x18004e8a2  test    byte ptr [rcx+1Ch], 80h
0x18004e8a6  jz      loc_18004E93B
0x18004e8ac  cmp     byte ptr [rcx+19h], 2
0x18004e8b0  jb      loc_18004E93B
0x18004e8b6  mov     edx, 12h
0x18004e8bb  mov     rcx, [rcx+10h]
0x18004e8bf  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18004e8c6  mov     r9d, ebx
0x18004e8c9  call    WPP_SF_d
0x18004e8ce  jmp     short loc_18004E93B
0x18004e8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e8d7  lea     rdx, WPP_GLOBAL_Control
0x18004e8de  cmp     rcx, rdx
0x18004e8e1  jz      short loc_18004E93B
0x18004e8e3  test    byte ptr [rcx+1Ch], 80h
0x18004e8e7  jz      short loc_18004E93B
0x18004e8e9  cmp     byte ptr [rcx+19h], 2
0x18004e8ed  jb      short loc_18004E93B
0x18004e8ef  mov     edx, 13h
0x18004e8f4  jmp     short loc_18004E8BB
0x18004e8f6  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18004e8fb  lea     rdx, [rsp+28h+lpWideCharStr]
0x18004e900  mov     [rsp+28h+lpWideCharStr], 0
0x18004e909  call    GetSidFromToken
0x18004e90e  mov     ebx, eax
0x18004e910  test    eax, eax
0x18004e912  jnz     short loc_18004E921
0x18004e914  mov     rcx, [rsp+28h+lpWideCharStr]; lpWideCharStr
0x18004e919  call    _StrdupWtoA
0x18004e91e  mov     [rdi], rax
0x18004e921  mov     rcx, [rsp+28h+lpWideCharStr]
0x18004e926  call    Free0
0x18004e92b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18004e930  test    rcx, rcx
0x18004e933  jz      short loc_18004E93B
0x18004e935  call    cs:__imp_CloseHandle
0x18004e93b  mov     eax, ebx
0x18004e93d  mov     rbx, [rsp+28h+arg_0]
0x18004e942  add     rsp, 20h
0x18004e946  pop     rdi
0x18004e947  retn
```
