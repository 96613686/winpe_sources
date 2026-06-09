# WerpGetHeaderFromProcess

- ea: `0x18001bad4`
- end: `0x18001bd23`
- name: `WerpGetHeaderFromProcess`
- size: `591`
- prototype: `signed int __fastcall(HANDLE hProcess, _WORD *lpBuffer)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b9ec`
- `0x18001bd2c`
- `0x18001bec8`
- `0x18001c87c`
- `0x18001ca08`

## callees

- `0x180003617`
- `0x18001bad4`
- `0x18001c040`
- `0x18001c1a0`
- `0x18001c2fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bb2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc99`
- `ntdll!DbgPrintEx` at `0x18001bbd8`
- `ntdll!DbgPrintEx` at `0x18001bc17`
- `ntdll!DbgPrintEx` at `0x18001bc93`
- `ntdll!DbgPrintEx` at `0x18001bcd7`
- `ntdll!DbgPrintEx` at `0x18001bd0d`
- `ntdll!DbgPrintEx` at `0x18001bbd8`
- `ntdll!DbgPrintEx` at `0x18001bc17`
- `ntdll!DbgPrintEx` at `0x18001bc93`
- `ntdll!DbgPrintEx` at `0x18001bcd7`
- `ntdll!DbgPrintEx` at `0x18001bd0d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001bc6b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001bc6b`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001bb14`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001bb3a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001bb54`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001bb14`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001bb3a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001bb54`

## string_xrefs

- `0x18001bb8d`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18001bbca`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18001bc09`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x18001bc85`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`

## pseudocode

```c
signed int __fastcall WerpGetHeaderFromProcess(HANDLE hProcess, _WORD *lpBuffer)
{
  int v4; // eax
  BOOL v5; // ebx
  HANDLE CurrentProcess; // rax
  unsigned int v7; // r9d
  int v8; // eax
  DWORD v9; // eax
  int v10; // r14d
  DWORD v11; // eax
  signed int result; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD CurrentProcessId_0; // eax
  WINBOOL Wow64Process; // [rsp+60h] [rbp+30h] BYREF
  WINBOOL v19; // [rsp+70h] [rbp+40h] BYREF
  LPCVOID lpBaseAddress; // [rsp+78h] [rbp+48h] BYREF

  lpBaseAddress = 0;
  Wow64Process = 0;
  v19 = 0;
  if ( !hProcess || !lpBuffer )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arguments\n", CurrentProcessId_0, 3168);
    return -2147024809;
  }
  v4 = IsWow64Process(hProcess, &Wow64Process);
  if ( v4 )
    v4 = Wow64Process;
  else
    Wow64Process = 0;
  v5 = v4 == 0;
  CurrentProcess = GetCurrentProcess();
  if ( !IsWow64Process(CurrentProcess, &v19) )
    v19 = 0;
  if ( v19 )
  {
    v8 = IsWow64Process(hProcess, &Wow64Process);
    if ( v8 )
      v8 = Wow64Process;
    else
      Wow64Process = 0;
    if ( !v8 )
    {
      v5 = 1;
LABEL_17:
      if ( v19 && v5 )
      {
        v9 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n", v9, 3215);
        return -2147024809;
      }
      v10 = WerpReadPebFromProcess(hProcess, &lpBaseAddress, 0x358u, v7);
      if ( v10 < 0 )
      {
        v11 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n", v11, 3236);
        return v10;
      }
      goto LABEL_23;
    }
    v5 = 0;
  }
  else
  {
    v8 = Wow64Process;
  }
  if ( !v8 )
    goto LABEL_17;
  v10 = WerpReadPeb32FromProcess(hProcess, &lpBaseAddress);
  if ( v10 < 0 )
  {
    v14 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n", v14, 3255);
    return v10;
  }
LABEL_23:
  if ( !lpBaseAddress )
    return -2147023728;
  if ( v19 && v5 )
  {
    v13 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n",
      v13,
      3284);
    return -805306367;
  }
  else if ( ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x968u, 0) )
  {
    if ( (int)WerpValidatePebHeader(lpBuffer) >= 0 )
    {
      result = 0;
      lpBuffer[1107] = 0;
    }
    else
    {
      v16 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR WerpValidatePebHeader failed\n", v16, 3308);
      return -2147467259;
    }
  }
  else
  {
    v15 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n",
      v15,
      3299);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001bad4  push    rbp
0x18001bad6  push    rbx
0x18001bad7  push    rsi
0x18001bad8  push    rdi
0x18001bad9  push    r14
0x18001badb  mov     rbp, rsp
0x18001bade  sub     rsp, 30h
0x18001bae2  mov     [rbp+lpBaseAddress], 0
0x18001baea  mov     rsi, rdx
0x18001baed  mov     [rbp+Wow64Process], 0
0x18001baf4  mov     rdi, rcx
0x18001baf7  mov     [rbp+arg_10], 0
0x18001bafe  test    rcx, rcx
0x18001bb01  jz      loc_18001BCEF
0x18001bb07  test    rdx, rdx
0x18001bb0a  jz      loc_18001BCEF
0x18001bb10  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x18001bb14  call    cs:__imp_IsWow64Process
0x18001bb1a  test    eax, eax
0x18001bb1c  jnz     short loc_18001BB23
0x18001bb1e  mov     [rbp+Wow64Process], eax
0x18001bb21  jmp     short loc_18001BB26
0x18001bb23  mov     eax, [rbp+Wow64Process]
0x18001bb26  xor     ebx, ebx
0x18001bb28  test    eax, eax
0x18001bb2a  setz    bl
0x18001bb2d  call    cs:__imp_GetCurrentProcess
0x18001bb33  mov     rcx, rax; hProcess
0x18001bb36  lea     rdx, [rbp+arg_10]; Wow64Process
0x18001bb3a  call    cs:__imp_IsWow64Process
0x18001bb40  test    eax, eax
0x18001bb42  jnz     short loc_18001BB47
0x18001bb44  mov     [rbp+arg_10], eax
0x18001bb47  cmp     [rbp+arg_10], 0
0x18001bb4b  jz      short loc_18001BB73
0x18001bb4d  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x18001bb51  mov     rcx, rdi; hProcess
0x18001bb54  call    cs:__imp_IsWow64Process
0x18001bb5a  test    eax, eax
0x18001bb5c  jnz     short loc_18001BB63
0x18001bb5e  mov     [rbp+Wow64Process], eax
0x18001bb61  jmp     short loc_18001BB66
0x18001bb63  mov     eax, [rbp+Wow64Process]
0x18001bb66  test    eax, eax
0x18001bb68  jnz     short loc_18001BB6F
0x18001bb6a  lea     ebx, [rax+1]
0x18001bb6d  jmp     short loc_18001BB7E
0x18001bb6f  xor     ebx, ebx
0x18001bb71  jmp     short loc_18001BB76
0x18001bb73  mov     eax, [rbp+Wow64Process]
0x18001bb76  test    eax, eax
0x18001bb78  jnz     loc_18001BC27
0x18001bb7e  cmp     [rbp+arg_10], 0
0x18001bb82  jz      short loc_18001BBA1
0x18001bb84  test    ebx, ebx
0x18001bb86  jz      short loc_18001BBA1
0x18001bb88  call    GetCurrentProcessId_0
0x18001bb8d  lea     r8, aWerCrashapiUUE_6; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x18001bb94  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0C8Fh
0x18001bb9c  jmp     loc_18001BD03
0x18001bba1  mov     r8d, 358h; unsigned int
0x18001bba7  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x18001bbab  mov     rcx, rdi; hProcess
0x18001bbae  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x18001bbb3  mov     r14d, eax
0x18001bbb6  test    eax, eax
0x18001bbb8  jns     short loc_18001BBE6
0x18001bbba  call    GetCurrentProcessId_0
0x18001bbbf  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CA4h
0x18001bbc7  mov     r9d, eax
0x18001bbca  lea     r8, aWerCrashapiUUE_6; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x18001bbd1  xor     edx, edx; Level
0x18001bbd3  mov     ecx, 96h; ComponentId
0x18001bbd8  call    cs:__imp_DbgPrintEx
0x18001bbde  mov     eax, r14d
0x18001bbe1  jmp     loc_18001BD18
0x18001bbe6  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x18001bbea  test    rdx, rdx
0x18001bbed  jz      short loc_18001BC4C
0x18001bbef  cmp     [rbp+arg_10], 0
0x18001bbf3  jz      short loc_18001BC56
0x18001bbf5  test    ebx, ebx
0x18001bbf7  jz      short loc_18001BC56
0x18001bbf9  call    GetCurrentProcessId_0
0x18001bbfe  mov     r9d, eax
0x18001bc01  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CD4h
0x18001bc09  lea     r8, aWerCrashapiUUE_3; "WER/CrashAPI/%u:%u: ERROR WerpNtWow64Re"...
0x18001bc10  xor     edx, edx; Level
0x18001bc12  mov     ecx, 96h; ComponentId
0x18001bc17  call    cs:__imp_DbgPrintEx
0x18001bc1d  mov     eax, 0D0000001h
0x18001bc22  jmp     loc_18001BD18
0x18001bc27  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x18001bc2b  mov     rcx, rdi; hProcess
0x18001bc2e  call    WerpReadPeb32FromProcess
0x18001bc33  mov     r14d, eax
0x18001bc36  test    eax, eax
0x18001bc38  jns     short loc_18001BBE6
0x18001bc3a  call    GetCurrentProcessId_0
0x18001bc3f  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CB7h
0x18001bc47  jmp     loc_18001BBC7
0x18001bc4c  mov     eax, 80070490h
0x18001bc51  jmp     loc_18001BD18
0x18001bc56  mov     r9d, 968h; nSize
0x18001bc5c  mov     [rsp+30h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18001bc65  mov     r8, rsi; lpBuffer
0x18001bc68  mov     rcx, rdi; hProcess
0x18001bc6b  call    cs:__imp_ReadProcessMemory
0x18001bc71  test    eax, eax
0x18001bc73  jnz     short loc_18001BCAD
0x18001bc75  call    GetCurrentProcessId_0
0x18001bc7a  mov     r9d, eax
0x18001bc7d  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CE3h
0x18001bc85  lea     r8, aWerCrashapiUUE_8; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x18001bc8c  xor     edx, edx; Level
0x18001bc8e  mov     ecx, 96h; ComponentId
0x18001bc93  call    cs:__imp_DbgPrintEx
0x18001bc99  call    cs:__imp_GetLastError
0x18001bc9f  test    eax, eax
0x18001bca1  jle     short loc_18001BD18
0x18001bca3  movzx   eax, ax
0x18001bca6  or      eax, 80070000h
0x18001bcab  jmp     short loc_18001BD18
0x18001bcad  mov     rcx, rsi
0x18001bcb0  call    WerpValidatePebHeader
0x18001bcb5  test    eax, eax
0x18001bcb7  jns     short loc_18001BCE4
0x18001bcb9  call    GetCurrentProcessId_0
0x18001bcbe  mov     r9d, eax
0x18001bcc1  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CECh
0x18001bcc9  lea     r8, aWerCrashapiUUE_24; "WER/CrashAPI/%u:%u: ERROR WerpValidateP"...
0x18001bcd0  xor     edx, edx; Level
0x18001bcd2  mov     ecx, 96h; ComponentId
0x18001bcd7  call    cs:__imp_DbgPrintEx
0x18001bcdd  mov     eax, 80004005h
0x18001bce2  jmp     short loc_18001BD18
0x18001bce4  xor     eax, eax
0x18001bce6  mov     [rsi+8A6h], ax
0x18001bced  jmp     short loc_18001BD18
0x18001bcef  call    GetCurrentProcessId_0
0x18001bcf4  lea     r8, aWerCrashapiUUE_29; "WER/CrashAPI/%u:%u: ERROR Invalid argum"...
0x18001bcfb  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0C60h
0x18001bd03  mov     r9d, eax
0x18001bd06  xor     edx, edx; Level
0x18001bd08  mov     ecx, 96h; ComponentId
0x18001bd0d  call    cs:__imp_DbgPrintEx
0x18001bd13  mov     eax, 80070057h
0x18001bd18  add     rsp, 30h
0x18001bd1c  pop     r14
0x18001bd1e  pop     rdi
0x18001bd1f  pop     rsi
0x18001bd20  pop     rbx
0x18001bd21  pop     rbp
0x18001bd22  retn
```
