# CheckProcessForSid(void *,int &)

- ea: `0x18001ecdc`
- end: `0x18001eeb5`
- name: `?CheckProcessForSid@@YAJPEAXAEAH@Z`
- size: `473`
- prototype: `__int64 __fastcall(PSID SidToCheck, PBOOL IsMember)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ebe4`
- `0x180038e44`

## callees

- `0x1800084f4`
- `0x18001ecdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ed45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ed45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ed02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ed02`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001eda7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001eda7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ed72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ed72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ede7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ede7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee51`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001ee0c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001ee0c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001eddd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001eddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee9d`

## string_xrefs

- `0x18001edc2`: `OpenProcessToken`
- `0x18001ee37`: `CheckProcessForSid`
- `0x18001ee70`: `CheckProcessForSid`
- `0x18001ed28`: `GetCurrentThread`
- `0x18001ee66`: `OpenThreadToken`
- `0x18001ee27`: `CheckTokenMembership`
- `0x18001edf8`: `DuplicateToken`
- `0x18001ee3e`: `%s: OpenThreadToken found thread token. Only process tokens allowed. 0x%08x.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CheckProcessForSid(PSID SidToCheck, PBOOL IsMember)
{
  HANDLE CurrentThread; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // r8
  signed int v8; // eax
  HANDLE CurrentProcess; // rax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  void *DuplicateTokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  DuplicateTokenHandle = 0;
  CurrentThread = GetCurrentThread();
  *IsMember = 0;
  if ( CurrentThread )
  {
    if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = L"OpenThreadToken";
    }
    else
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 != -2147023888 )
      {
        Logger::TraceError(
          L"%s: OpenThreadToken found thread token. Only process tokens allowed. 0x%08x.\n",
          L"CheckProcessForSid",
          (unsigned int)v8);
        v6 = -2147418113;
        goto LABEL_31;
      }
      CurrentProcess = GetCurrentProcess();
      if ( CurrentProcess )
      {
        if ( OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
        {
          if ( DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle) )
          {
            if ( CheckTokenMembership(DuplicateTokenHandle, SidToCheck, IsMember) )
            {
              v6 = 0;
              goto LABEL_31;
            }
            v13 = GetLastError();
            v6 = v13;
            if ( v13 > 0 )
              v6 = (unsigned __int16)v13 | 0x80070000;
            v7 = L"CheckTokenMembership";
          }
          else
          {
            v12 = GetLastError();
            v6 = v12;
            if ( v12 > 0 )
              v6 = (unsigned __int16)v12 | 0x80070000;
            v7 = L"DuplicateToken";
          }
        }
        else
        {
          v11 = GetLastError();
          v6 = v11;
          if ( v11 > 0 )
            v6 = (unsigned __int16)v11 | 0x80070000;
          v7 = L"OpenProcessToken";
        }
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        v7 = L"GetCurrentProcess";
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = L"GetCurrentThread";
  }
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x", L"CheckProcessForSid", v7, v6);
LABEL_31:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18001ecdc  mov     rax, rsp
0x18001ecdf  mov     [rax+8], rbx
0x18001ece3  mov     [rax+20h], rsi
0x18001ece7  push    rdi
0x18001ece8  sub     rsp, 20h
0x18001ecec  mov     rbx, rdx
0x18001ecef  mov     qword ptr [rax+10h], 0
0x18001ecf7  mov     rsi, rcx
0x18001ecfa  mov     qword ptr [rax+18h], 0
0x18001ed02  call    cs:__imp_GetCurrentThread
0x18001ed08  mov     dword ptr [rbx], 0
0x18001ed0e  test    rax, rax
0x18001ed11  jnz     short loc_18001ED34
0x18001ed13  call    cs:__imp_GetLastError
0x18001ed19  mov     ebx, eax
0x18001ed1b  test    eax, eax
0x18001ed1d  jle     short loc_18001ED28
0x18001ed1f  movzx   ebx, ax
0x18001ed22  or      ebx, 80070000h
0x18001ed28  lea     r8, aGetcurrentthre; "GetCurrentThread"
0x18001ed2f  jmp     loc_18001EE6D
0x18001ed34  mov     edx, 0Ah; DesiredAccess
0x18001ed39  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001ed3e  mov     rcx, rax; ThreadHandle
0x18001ed41  lea     r8d, [rdx-9]; OpenAsSelf
0x18001ed45  call    cs:__imp_OpenThreadToken
0x18001ed4b  test    eax, eax
0x18001ed4d  jnz     loc_18001EE51
0x18001ed53  call    cs:__imp_GetLastError
0x18001ed59  mov     edi, 80070000h
0x18001ed5e  test    eax, eax
0x18001ed60  jle     short loc_18001ED67
0x18001ed62  movzx   eax, ax
0x18001ed65  or      eax, edi
0x18001ed67  cmp     eax, 800703F0h
0x18001ed6c  jnz     loc_18001EE34
0x18001ed72  call    cs:__imp_GetCurrentProcess
0x18001ed78  test    rax, rax
0x18001ed7b  jnz     short loc_18001ED9A
0x18001ed7d  call    cs:__imp_GetLastError
0x18001ed83  mov     ebx, eax
0x18001ed85  test    eax, eax
0x18001ed87  jle     short loc_18001ED8E
0x18001ed89  movzx   ebx, ax
0x18001ed8c  or      ebx, edi
0x18001ed8e  lea     r8, aGetcurrentproc; "GetCurrentProcess"
0x18001ed95  jmp     loc_18001EE6D
0x18001ed9a  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18001ed9f  mov     edx, 2; DesiredAccess
0x18001eda4  mov     rcx, rax; ProcessHandle
0x18001eda7  call    cs:__imp_OpenProcessToken
0x18001edad  test    eax, eax
0x18001edaf  jnz     short loc_18001EDCE
0x18001edb1  call    cs:__imp_GetLastError
0x18001edb7  mov     ebx, eax
0x18001edb9  test    eax, eax
0x18001edbb  jle     short loc_18001EDC2
0x18001edbd  movzx   ebx, ax
0x18001edc0  or      ebx, edi
0x18001edc2  lea     r8, aOpenprocesstok; "OpenProcessToken"
0x18001edc9  jmp     loc_18001EE6D
0x18001edce  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x18001edd3  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18001edd8  mov     edx, 1; ImpersonationLevel
0x18001eddd  call    cs:__imp_DuplicateToken
0x18001ede3  test    eax, eax
0x18001ede5  jnz     short loc_18001EE01
0x18001ede7  call    cs:__imp_GetLastError
0x18001eded  mov     ebx, eax
0x18001edef  test    eax, eax
0x18001edf1  jle     short loc_18001EDF8
0x18001edf3  movzx   ebx, ax
0x18001edf6  or      ebx, edi
0x18001edf8  lea     r8, aDuplicatetoken; "DuplicateToken"
0x18001edff  jmp     short loc_18001EE6D
0x18001ee01  mov     rcx, [rsp+28h+DuplicateTokenHandle]; TokenHandle
0x18001ee06  mov     r8, rbx; IsMember
0x18001ee09  mov     rdx, rsi; SidToCheck
0x18001ee0c  call    cs:__imp_CheckTokenMembership
0x18001ee12  test    eax, eax
0x18001ee14  jnz     short loc_18001EE30
0x18001ee16  call    cs:__imp_GetLastError
0x18001ee1c  mov     ebx, eax
0x18001ee1e  test    eax, eax
0x18001ee20  jle     short loc_18001EE27
0x18001ee22  movzx   ebx, ax
0x18001ee25  or      ebx, edi
0x18001ee27  lea     r8, aChecktokenmemb; "CheckTokenMembership"
0x18001ee2e  jmp     short loc_18001EE6D
0x18001ee30  xor     ebx, ebx
0x18001ee32  jmp     short loc_18001EE83
0x18001ee34  mov     r8d, eax
0x18001ee37  lea     rdx, aCheckprocessfo; "CheckProcessForSid"
0x18001ee3e  lea     rcx, aSOpenthreadtok; "%s: OpenThreadToken found thread token."...
0x18001ee45  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001ee4a  mov     ebx, 8000FFFFh
0x18001ee4f  jmp     short loc_18001EE83
0x18001ee51  call    cs:__imp_GetLastError
0x18001ee57  mov     ebx, eax
0x18001ee59  test    eax, eax
0x18001ee5b  jle     short loc_18001EE66
0x18001ee5d  movzx   ebx, ax
0x18001ee60  or      ebx, 80070000h
0x18001ee66  lea     r8, aOpenthreadtoke; "OpenThreadToken"
0x18001ee6d  mov     r9d, ebx
0x18001ee70  lea     rdx, aCheckprocessfo; "CheckProcessForSid"
0x18001ee77  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18001ee7e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001ee83  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18001ee88  test    rcx, rcx
0x18001ee8b  jz      short loc_18001EE93
0x18001ee8d  call    cs:__imp_CloseHandle
0x18001ee93  mov     rcx, [rsp+28h+DuplicateTokenHandle]; hObject
0x18001ee98  test    rcx, rcx
0x18001ee9b  jz      short loc_18001EEA3
0x18001ee9d  call    cs:__imp_CloseHandle
0x18001eea3  mov     rsi, [rsp+28h+arg_18]
0x18001eea8  mov     eax, ebx
0x18001eeaa  mov     rbx, [rsp+28h+arg_0]
0x18001eeaf  add     rsp, 20h
0x18001eeb3  pop     rdi
0x18001eeb4  retn
```
