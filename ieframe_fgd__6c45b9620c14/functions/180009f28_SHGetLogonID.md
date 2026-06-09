# SHGetLogonID

- ea: `0x180009f28`
- end: `0x18000a0ef`
- name: `SHGetLogonID`
- size: `455`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180068ce8`
- `0x1800740bc`

## callees

- `0x180009f28`
- `0x18000a0f8`
- `0x1800906d4`
- `0x180253388`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180009f98`
- `KERNEL32!GetCurrentProcess` at `0x180009f98`
- `KERNEL32!GetCurrentThread` at `0x180009f48`
- `KERNEL32!GetCurrentThread` at `0x180009f48`
- `KERNEL32!GetProcessHeap` at `0x180009fc6`
- `KERNEL32!GetProcessHeap` at `0x18000a0b9`
- `KERNEL32!GetProcessHeap` at `0x180009fc6`
- `KERNEL32!GetProcessHeap` at `0x18000a0b9`
- `KERNEL32!HeapAlloc` at `0x18000a011`
- `KERNEL32!HeapAlloc` at `0x18000a011`
- `KERNEL32!CloseHandle` at `0x18000a0d9`
- `KERNEL32!CloseHandle` at `0x18000a0d9`
- `KERNEL32!GetLastError` at `0x180009f69`
- `KERNEL32!GetLastError` at `0x180009ffc`
- `KERNEL32!GetLastError` at `0x18000a0a4`
- `KERNEL32!GetLastError` at `0x180009f69`
- `KERNEL32!GetLastError` at `0x180009ffc`
- `KERNEL32!GetLastError` at `0x18000a0a4`
- `KERNEL32!HeapFree` at `0x18000a052`
- `KERNEL32!HeapFree` at `0x18000a0c7`
- `KERNEL32!HeapFree` at `0x18000a052`
- `KERNEL32!HeapFree` at `0x18000a0c7`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x180009fa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x180009fa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x180009fee`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x18000a039`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x180009fee`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetTokenInformation` at `0x18000a039`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x180009f5f`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenThreadToken` at `0x180009f5f`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x18000a096`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x18000a096`

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
0x180009f28  mov     [rsp+arg_0], rbx
0x180009f2d  push    rsi
0x180009f2e  push    rdi
0x180009f2f  push    r14
0x180009f31  sub     rsp, 30h
0x180009f35  mov     r14, rcx
0x180009f38  mov     qword ptr [rcx], 0
0x180009f3f  mov     [rsp+48h+TokenHandle], 0
0x180009f48  call    cs:__imp_GetCurrentThread
0x180009f4e  xor     r8d, r8d; OpenAsSelf
0x180009f51  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180009f56  mov     rcx, rax; ThreadHandle
0x180009f59  lea     edi, [r8+8]
0x180009f5d  mov     edx, edi; DesiredAccess
0x180009f5f  call    cs:__imp_OpenThreadToken
0x180009f65  test    eax, eax
0x180009f67  jnz     short loc_180009FC1
0x180009f69  call    cs:__imp_GetLastError
0x180009f6f  mov     ebx, eax
0x180009f71  test    eax, eax
0x180009f73  jle     short loc_180009F7E
0x180009f75  movzx   ebx, ax
0x180009f78  or      ebx, 80070000h
0x180009f7e  test    ebx, ebx
0x180009f80  js      short loc_180009F8C
0x180009f82  mov     ebx, 80004005h
0x180009f87  jmp     loc_18000A0DF
0x180009f8c  cmp     ebx, 800703F0h
0x180009f92  jnz     loc_18000A0DF
0x180009f98  call    cs:__imp_GetCurrentProcess
0x180009f9e  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180009fa3  mov     edx, edi; DesiredAccess
0x180009fa5  mov     rcx, rax; ProcessHandle
0x180009fa8  call    cs:__imp_OpenProcessToken
0x180009fae  test    eax, eax
0x180009fb0  jnz     short loc_180009FC1
0x180009fb2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009fb7  mov     ebx, eax
0x180009fb9  test    eax, eax
0x180009fbb  js      loc_18000A0DF
0x180009fc1  mov     rbx, [rsp+48h+TokenHandle]
0x180009fc6  call    cs:__imp_GetProcessHeap
0x180009fcc  xor     r9d, r9d; TokenInformationLength
0x180009fcf  mov     [rsp+48h+TokenInformationLength], 0
0x180009fd7  mov     rsi, rax
0x180009fda  xor     r8d, r8d; TokenInformation
0x180009fdd  lea     rax, [rsp+48h+TokenInformationLength]
0x180009fe2  mov     rcx, rbx; TokenHandle
0x180009fe5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180009fea  lea     edx, [r9+2]; TokenInformationClass
0x180009fee  call    cs:__imp_GetTokenInformation
0x180009ff4  test    eax, eax
0x180009ff6  jnz     loc_18000A0CF
0x180009ffc  call    cs:__imp_GetLastError
0x18000a002  cmp     eax, 7Ah ; 'z'
0x18000a005  jnz     short loc_18000A061
0x18000a007  mov     r8d, [rsp+48h+TokenInformationLength]; dwBytes
0x18000a00c  xor     edx, edx; dwFlags
0x18000a00e  mov     rcx, rsi; hHeap
0x18000a011  call    cs:__imp_HeapAlloc
0x18000a017  mov     rdi, rax
0x18000a01a  test    rax, rax
0x18000a01d  jz      short loc_18000A05A
0x18000a01f  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000a024  lea     rax, [rsp+48h+TokenInformationLength]
0x18000a029  mov     r8, rdi; TokenInformation
0x18000a02c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000a031  mov     edx, 2; TokenInformationClass
0x18000a036  mov     rcx, rbx; TokenHandle
0x18000a039  call    cs:__imp_GetTokenInformation
0x18000a03f  test    eax, eax
0x18000a041  jnz     short loc_18000A070
0x18000a043  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18000a048  mov     r8, rdi; lpMem
0x18000a04b  xor     edx, edx; dwFlags
0x18000a04d  mov     rcx, rsi; hHeap
0x18000a050  mov     ebx, eax
0x18000a052  call    cs:__imp_HeapFree
0x18000a058  jmp     short loc_18000A06A
0x18000a05a  mov     ebx, 8007000Eh
0x18000a05f  jmp     short loc_18000A06A
0x18000a061  mov     ecx, eax; unsigned int
0x18000a063  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x18000a068  mov     ebx, eax
0x18000a06a  xor     edi, edi
0x18000a06c  test    ebx, ebx
0x18000a06e  js      short loc_18000A0D4
0x18000a070  mov     ebx, 80004005h
0x18000a075  xor     eax, eax
0x18000a077  cmp     eax, [rdi]
0x18000a079  jnb     short loc_18000A0B9
0x18000a07b  mov     ecx, eax
0x18000a07d  add     rcx, rcx
0x18000a080  test    dword ptr [rdi+rcx*8+10h], 0C0000000h
0x18000a088  jnz     short loc_18000A08E
0x18000a08a  inc     eax
0x18000a08c  jmp     short loc_18000A077
0x18000a08e  mov     rcx, [rdi+rcx*8+8]; Sid
0x18000a093  mov     rdx, r14; StringSid
0x18000a096  call    cs:__imp_ConvertSidToStringSidW
0x18000a09c  test    eax, eax
0x18000a09e  jz      short loc_18000A0A4
0x18000a0a0  xor     ebx, ebx
0x18000a0a2  jmp     short loc_18000A0B9
0x18000a0a4  call    cs:__imp_GetLastError
0x18000a0aa  mov     ebx, eax
0x18000a0ac  test    eax, eax
0x18000a0ae  jle     short loc_18000A0B9
0x18000a0b0  movzx   ebx, ax
0x18000a0b3  or      ebx, 80070000h
0x18000a0b9  call    cs:__imp_GetProcessHeap
0x18000a0bf  mov     r8, rdi; lpMem
0x18000a0c2  xor     edx, edx; dwFlags
0x18000a0c4  mov     rcx, rax; hHeap
0x18000a0c7  call    cs:__imp_HeapFree
0x18000a0cd  jmp     short loc_18000A0D4
0x18000a0cf  mov     ebx, 8000FFFFh
0x18000a0d4  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000a0d9  call    cs:__imp_CloseHandle
0x18000a0df  mov     eax, ebx
0x18000a0e1  mov     rbx, [rsp+48h+arg_0]
0x18000a0e6  add     rsp, 30h
0x18000a0ea  pop     r14
0x18000a0ec  pop     rdi
0x18000a0ed  pop     rsi
0x18000a0ee  retn
```
