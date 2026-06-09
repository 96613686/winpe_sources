# SHGetLogonID

- ea: `0x18000ba08`
- end: `0x18000bc30`
- name: `SHGetLogonID`
- size: `552`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18006e81c`
- `0x18007a060`

## callees

- `0x18000ba08`
- `0x18000bc38`
- `0x180097100`
- `0x1802724e0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000ba8a`
- `KERNEL32!GetCurrentProcess` at `0x18000ba8a`
- `KERNEL32!GetCurrentThread` at `0x18000ba28`
- `KERNEL32!GetCurrentThread` at `0x18000ba28`
- `KERNEL32!GetProcessHeap` at `0x18000bac4`
- `KERNEL32!GetProcessHeap` at `0x18000bbe7`
- `KERNEL32!GetProcessHeap` at `0x18000bac4`
- `KERNEL32!GetProcessHeap` at `0x18000bbe7`
- `KERNEL32!HeapAlloc` at `0x18000bb21`
- `KERNEL32!HeapAlloc` at `0x18000bb21`
- `KERNEL32!CloseHandle` at `0x18000bc13`
- `KERNEL32!CloseHandle` at `0x18000bc13`
- `KERNEL32!GetLastError` at `0x18000ba55`
- `KERNEL32!GetLastError` at `0x18000bb06`
- `KERNEL32!GetLastError` at `0x18000bbcc`
- `KERNEL32!GetLastError` at `0x18000ba55`
- `KERNEL32!GetLastError` at `0x18000bb06`
- `KERNEL32!GetLastError` at `0x18000bbcc`
- `KERNEL32!HeapFree` at `0x18000bb6e`
- `KERNEL32!HeapFree` at `0x18000bbfb`
- `KERNEL32!HeapFree` at `0x18000bb6e`
- `KERNEL32!HeapFree` at `0x18000bbfb`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x18000baa0`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x18000baa0`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x18000baf2`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x18000bb4f`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x18000baf2`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x18000bb4f`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x18000ba45`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x18000ba45`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x18000bbb8`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x18000bbb8`

## pseudocode

```c
__int64 __fastcall SHGetLogonID(LPWSTR *StringSid)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int ErrorError; // ebx
  HANDLE CurrentProcess; // rax
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rsi
  DWORD v9; // eax
  unsigned int *v10; // rdi
  unsigned int i; // eax
  signed int v12; // eax
  HANDLE v13; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  *StringSid = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_9;
  LastError = GetLastError();
  ErrorError = LastError;
  if ( LastError > 0 )
    ErrorError = (unsigned __int16)LastError | 0x80070000;
  if ( ErrorError >= 0 )
    return (unsigned int)-2147467259;
  if ( ErrorError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle)
      || (ErrorError = ResultFromKnownLastError(), ErrorError >= 0) )
    {
LABEL_9:
      v6 = TokenHandle;
      ProcessHeap = GetProcessHeap();
      TokenInformationLength = 0;
      v8 = ProcessHeap;
      if ( GetTokenInformation(v6, TokenGroups, 0, 0, &TokenInformationLength) )
      {
        ErrorError = -2147418113;
      }
      else
      {
        v9 = GetLastError();
        if ( v9 == 122 )
        {
          v10 = (unsigned int *)HeapAlloc(v8, 0, TokenInformationLength);
          if ( v10 )
          {
            if ( GetTokenInformation(v6, TokenGroups, v10, TokenInformationLength, &TokenInformationLength) )
              goto LABEL_17;
            ErrorError = HRESULTFromLastErrorError();
            HeapFree(v8, 0, v10);
          }
          else
          {
            ErrorError = -2147024882;
          }
        }
        else
        {
          ErrorError = HRESULTFromWin32ErrorError(v9);
        }
        v10 = 0;
        if ( ErrorError >= 0 )
        {
LABEL_17:
          ErrorError = -2147467259;
          for ( i = 0; i < *v10; ++i )
          {
            if ( (v10[4 * i + 4] & 0xC0000000) != 0 )
            {
              if ( ConvertSidToStringSidW(*(PSID *)&v10[4 * i + 2], StringSid) )
              {
                ErrorError = 0;
              }
              else
              {
                v12 = GetLastError();
                ErrorError = v12;
                if ( v12 > 0 )
                  ErrorError = (unsigned __int16)v12 | 0x80070000;
              }
              break;
            }
          }
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v10);
        }
      }
      CloseHandle(TokenHandle);
    }
  }
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x18000ba08  mov     [rsp+arg_0], rbx
0x18000ba0d  push    rsi
0x18000ba0e  push    rdi
0x18000ba0f  push    r14
0x18000ba11  sub     rsp, 30h
0x18000ba15  mov     r14, rcx
0x18000ba18  mov     qword ptr [rcx], 0
0x18000ba1f  mov     [rsp+48h+TokenHandle], 0
0x18000ba28  call    cs:__imp_GetCurrentThread
0x18000ba2f  nop     dword ptr [rax+rax+00h]
0x18000ba34  xor     r8d, r8d; OpenAsSelf
0x18000ba37  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18000ba3c  mov     rcx, rax; ThreadHandle
0x18000ba3f  lea     edi, [r8+8]
0x18000ba43  mov     edx, edi; DesiredAccess
0x18000ba45  call    cs:__imp_OpenThreadToken
0x18000ba4c  nop     dword ptr [rax+rax+00h]
0x18000ba51  test    eax, eax
0x18000ba53  jnz     short loc_18000BABF
0x18000ba55  call    cs:__imp_GetLastError
0x18000ba5c  nop     dword ptr [rax+rax+00h]
0x18000ba61  mov     ebx, eax
0x18000ba63  test    eax, eax
0x18000ba65  jle     short loc_18000BA70
0x18000ba67  movzx   ebx, ax
0x18000ba6a  or      ebx, 80070000h
0x18000ba70  test    ebx, ebx
0x18000ba72  js      short loc_18000BA7E
0x18000ba74  mov     ebx, 80004005h
0x18000ba79  jmp     loc_18000BC1F
0x18000ba7e  cmp     ebx, 800703F0h
0x18000ba84  jnz     loc_18000BC1F
0x18000ba8a  call    cs:__imp_GetCurrentProcess
0x18000ba91  nop     dword ptr [rax+rax+00h]
0x18000ba96  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18000ba9b  mov     edx, edi; DesiredAccess
0x18000ba9d  mov     rcx, rax; ProcessHandle
0x18000baa0  call    cs:__imp_OpenProcessToken
0x18000baa7  nop     dword ptr [rax+rax+00h]
0x18000baac  test    eax, eax
0x18000baae  jnz     short loc_18000BABF
0x18000bab0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bab5  mov     ebx, eax
0x18000bab7  test    eax, eax
0x18000bab9  js      loc_18000BC1F
0x18000babf  mov     rbx, [rsp+48h+TokenHandle]
0x18000bac4  call    cs:__imp_GetProcessHeap
0x18000bacb  nop     dword ptr [rax+rax+00h]
0x18000bad0  xor     r9d, r9d; TokenInformationLength
0x18000bad3  mov     [rsp+48h+TokenInformationLength], 0
0x18000badb  mov     rsi, rax
0x18000bade  xor     r8d, r8d; TokenInformation
0x18000bae1  lea     rax, [rsp+48h+TokenInformationLength]
0x18000bae6  mov     rcx, rbx; TokenHandle
0x18000bae9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000baee  lea     edx, [r9+2]; TokenInformationClass
0x18000baf2  call    cs:__imp_GetTokenInformation
0x18000baf9  nop     dword ptr [rax+rax+00h]
0x18000bafe  test    eax, eax
0x18000bb00  jnz     loc_18000BC09
0x18000bb06  call    cs:__imp_GetLastError
0x18000bb0d  nop     dword ptr [rax+rax+00h]
0x18000bb12  cmp     eax, 7Ah ; 'z'
0x18000bb15  jnz     short loc_18000BB83
0x18000bb17  mov     r8d, [rsp+48h+TokenInformationLength]; dwBytes
0x18000bb1c  xor     edx, edx; dwFlags
0x18000bb1e  mov     rcx, rsi; hHeap
0x18000bb21  call    cs:__imp_HeapAlloc
0x18000bb28  nop     dword ptr [rax+rax+00h]
0x18000bb2d  mov     rdi, rax
0x18000bb30  test    rax, rax
0x18000bb33  jz      short loc_18000BB7C
0x18000bb35  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000bb3a  lea     rax, [rsp+48h+TokenInformationLength]
0x18000bb3f  mov     r8, rdi; TokenInformation
0x18000bb42  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000bb47  mov     edx, 2; TokenInformationClass
0x18000bb4c  mov     rcx, rbx; TokenHandle
0x18000bb4f  call    cs:__imp_GetTokenInformation
0x18000bb56  nop     dword ptr [rax+rax+00h]
0x18000bb5b  test    eax, eax
0x18000bb5d  jnz     short loc_18000BB92
0x18000bb5f  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18000bb64  mov     r8, rdi; lpMem
0x18000bb67  xor     edx, edx; dwFlags
0x18000bb69  mov     rcx, rsi; hHeap
0x18000bb6c  mov     ebx, eax
0x18000bb6e  call    cs:__imp_HeapFree
0x18000bb75  nop     dword ptr [rax+rax+00h]
0x18000bb7a  jmp     short loc_18000BB8C
0x18000bb7c  mov     ebx, 8007000Eh
0x18000bb81  jmp     short loc_18000BB8C
0x18000bb83  mov     ecx, eax; unsigned int
0x18000bb85  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x18000bb8a  mov     ebx, eax
0x18000bb8c  xor     edi, edi
0x18000bb8e  test    ebx, ebx
0x18000bb90  js      short loc_18000BC0E
0x18000bb92  mov     ebx, 80004005h
0x18000bb97  xor     eax, eax
0x18000bb99  cmp     eax, [rdi]
0x18000bb9b  jnb     short loc_18000BBE7
0x18000bb9d  mov     ecx, eax
0x18000bb9f  add     rcx, rcx
0x18000bba2  test    dword ptr [rdi+rcx*8+10h], 0C0000000h
0x18000bbaa  jnz     short loc_18000BBB0
0x18000bbac  inc     eax
0x18000bbae  jmp     short loc_18000BB99
0x18000bbb0  mov     rcx, [rdi+rcx*8+8]; Sid
0x18000bbb5  mov     rdx, r14; StringSid
0x18000bbb8  call    cs:__imp_ConvertSidToStringSidW
0x18000bbbf  nop     dword ptr [rax+rax+00h]
0x18000bbc4  test    eax, eax
0x18000bbc6  jz      short loc_18000BBCC
0x18000bbc8  xor     ebx, ebx
0x18000bbca  jmp     short loc_18000BBE7
0x18000bbcc  call    cs:__imp_GetLastError
0x18000bbd3  nop     dword ptr [rax+rax+00h]
0x18000bbd8  mov     ebx, eax
0x18000bbda  test    eax, eax
0x18000bbdc  jle     short loc_18000BBE7
0x18000bbde  movzx   ebx, ax
0x18000bbe1  or      ebx, 80070000h
0x18000bbe7  call    cs:__imp_GetProcessHeap
0x18000bbee  nop     dword ptr [rax+rax+00h]
0x18000bbf3  mov     r8, rdi; lpMem
0x18000bbf6  xor     edx, edx; dwFlags
0x18000bbf8  mov     rcx, rax; hHeap
0x18000bbfb  call    cs:__imp_HeapFree
0x18000bc02  nop     dword ptr [rax+rax+00h]
0x18000bc07  jmp     short loc_18000BC0E
0x18000bc09  mov     ebx, 8000FFFFh
0x18000bc0e  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000bc13  call    cs:__imp_CloseHandle
0x18000bc1a  nop     dword ptr [rax+rax+00h]
0x18000bc1f  mov     eax, ebx
0x18000bc21  mov     rbx, [rsp+48h+arg_0]
0x18000bc26  add     rsp, 30h
0x18000bc2a  pop     r14
0x18000bc2c  pop     rdi
0x18000bc2d  pop     rsi
0x18000bc2e  retn
```
