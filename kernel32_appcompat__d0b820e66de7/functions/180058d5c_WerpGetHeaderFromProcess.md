# WerpGetHeaderFromProcess

- ea: `0x180058d5c`
- end: `0x180058fd8`
- name: `WerpGetHeaderFromProcess`
- size: `636`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180052d7c`
- `0x180058bb4`
- `0x180076c60`

## callees

- `0x180050e58`
- `0x180058d5c`
- `0x180058fe0`
- `0x180061594`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180058e63`
- `ntdll!DbgPrintEx` at `0x180058ea9`
- `ntdll!DbgPrintEx` at `0x180058f2d`
- `ntdll!DbgPrintEx` at `0x180058f7e`
- `ntdll!DbgPrintEx` at `0x180058fbb`
- `ntdll!DbgPrintEx` at `0x180058e63`
- `ntdll!DbgPrintEx` at `0x180058ea9`
- `ntdll!DbgPrintEx` at `0x180058f2d`
- `ntdll!DbgPrintEx` at `0x180058f7e`
- `ntdll!DbgPrintEx` at `0x180058fbb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180058efe`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180058efe`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180058d9c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180058dc3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180058de3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180058d9c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180058dc3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180058de3`

## string_xrefs

- `0x180058f17`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`
- `0x180058e93`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x180058e25`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x180058e55`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`

## pseudocode

```c
signed int __fastcall WerpGetHeaderFromProcess(HANDLE hProcess, _WORD *lpBuffer)
{
  BOOL v4; // eax
  BOOL v5; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r9d
  BOOL v8; // eax
  const CHAR *v9; // r8
  int v10; // r14d
  signed int result; // eax
  int lpNumberOfBytesRead; // [rsp+20h] [rbp-10h]
  int lpNumberOfBytesReada; // [rsp+20h] [rbp-10h]
  BOOL Wow64Process; // [rsp+60h] [rbp+30h] BYREF
  BOOL v15; // [rsp+70h] [rbp+40h] BYREF
  LPCVOID lpBaseAddress; // [rsp+78h] [rbp+48h] BYREF

  lpBaseAddress = 0;
  Wow64Process = 0;
  v15 = 0;
  if ( !hProcess || !lpBuffer )
  {
    lpNumberOfBytesRead = 3168;
    v9 = "WER/CrashAPI/%u:%u: ERROR Invalid arguments\n";
    goto LABEL_37;
  }
  v4 = IsWow64Process(hProcess, &Wow64Process);
  if ( v4 )
    v4 = Wow64Process;
  else
    Wow64Process = 0;
  v5 = !v4;
  if ( !IsWow64Process((HANDLE)0xFFFFFFFFFFFFFFFFLL, &v15) )
    v15 = 0;
  if ( v15 )
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
      if ( v15 && v5 )
      {
        lpNumberOfBytesRead = 3215;
        v9 = "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n";
LABEL_37:
        DbgPrintEx(0x96u, 0, v9, NtCurrentTeb()->ClientId.UniqueProcess, lpNumberOfBytesRead);
        return -2147024809;
      }
      v10 = WerpReadPebFromProcess(hProcess, &lpBaseAddress, v6, v7);
      if ( v10 < 0 )
      {
        lpNumberOfBytesReada = 3236;
LABEL_22:
        DbgPrintEx(
          0x96u,
          0,
          "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n",
          NtCurrentTeb()->ClientId.UniqueProcess,
          lpNumberOfBytesReada);
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
    lpNumberOfBytesReada = 3255;
    goto LABEL_22;
  }
LABEL_23:
  if ( !lpBaseAddress )
    return -2147023728;
  if ( v15 && v5 )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
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
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashAPI/%u:%u: ERROR WerpValidatePebHeader failed\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        3308);
      return -2147467259;
    }
  }
  else
  {
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      3299);
    result = NtCurrentTeb()->LastErrorValue;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180058d5c  push    rbp
0x180058d5e  push    rbx
0x180058d5f  push    rsi
0x180058d60  push    rdi
0x180058d61  push    r14
0x180058d63  mov     rbp, rsp
0x180058d66  sub     rsp, 30h
0x180058d6a  mov     [rbp+lpBaseAddress], 0
0x180058d72  mov     rsi, rdx
0x180058d75  mov     [rbp+Wow64Process], 0
0x180058d7c  mov     rdi, rcx
0x180058d7f  mov     [rbp+arg_10], 0
0x180058d86  test    rcx, rcx
0x180058d89  jz      loc_180058F9C
0x180058d8f  test    rdx, rdx
0x180058d92  jz      loc_180058F9C
0x180058d98  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x180058d9c  call    cs:__imp_IsWow64Process
0x180058da3  nop     dword ptr [rax+rax+00h]
0x180058da8  test    eax, eax
0x180058daa  jnz     short loc_180058DB1
0x180058dac  mov     [rbp+Wow64Process], eax
0x180058daf  jmp     short loc_180058DB4
0x180058db1  mov     eax, [rbp+Wow64Process]
0x180058db4  xor     ebx, ebx
0x180058db6  lea     rdx, [rbp+arg_10]; Wow64Process
0x180058dba  test    eax, eax
0x180058dbc  setz    bl
0x180058dbf  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x180058dc3  call    cs:__imp_IsWow64Process
0x180058dca  nop     dword ptr [rax+rax+00h]
0x180058dcf  test    eax, eax
0x180058dd1  jnz     short loc_180058DD6
0x180058dd3  mov     [rbp+arg_10], eax
0x180058dd6  cmp     [rbp+arg_10], 0
0x180058dda  jz      short loc_180058E08
0x180058ddc  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x180058de0  mov     rcx, rdi; hProcess
0x180058de3  call    cs:__imp_IsWow64Process
0x180058dea  nop     dword ptr [rax+rax+00h]
0x180058def  test    eax, eax
0x180058df1  jnz     short loc_180058DF8
0x180058df3  mov     [rbp+Wow64Process], eax
0x180058df6  jmp     short loc_180058DFB
0x180058df8  mov     eax, [rbp+Wow64Process]
0x180058dfb  test    eax, eax
0x180058dfd  jnz     short loc_180058E04
0x180058dff  lea     ebx, [rax+1]
0x180058e02  jmp     short loc_180058E13
0x180058e04  xor     ebx, ebx
0x180058e06  jmp     short loc_180058E0B
0x180058e08  mov     eax, [rbp+Wow64Process]
0x180058e0b  test    eax, eax
0x180058e0d  jnz     loc_180058EBF
0x180058e13  cmp     [rbp+arg_10], 0
0x180058e17  jz      short loc_180058E31
0x180058e19  test    ebx, ebx
0x180058e1b  jz      short loc_180058E31
0x180058e1d  mov     [rsp+30h+lpNumberOfBytesRead], 0C8Fh
0x180058e25  lea     r8, aWerCrashapiUUE_15; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x180058e2c  jmp     loc_180058FAB
0x180058e31  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x180058e35  mov     rcx, rdi; hProcess
0x180058e38  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x180058e3d  mov     r14d, eax
0x180058e40  test    eax, eax
0x180058e42  jns     short loc_180058E77
0x180058e44  mov     [rsp+30h+lpNumberOfBytesRead], 0CA4h
0x180058e4c  mov     r9, gs:40h
0x180058e55  lea     r8, aWerCrashapiUUE_15; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x180058e5c  xor     edx, edx; Level
0x180058e5e  mov     ecx, 96h; ComponentId
0x180058e63  call    cs:__imp_DbgPrintEx
0x180058e6a  nop     dword ptr [rax+rax+00h]
0x180058e6f  mov     eax, r14d
0x180058e72  jmp     loc_180058FCC
0x180058e77  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180058e7b  test    rdx, rdx
0x180058e7e  jz      short loc_180058EDF
0x180058e80  cmp     [rbp+arg_10], 0
0x180058e84  jz      short loc_180058EE9
0x180058e86  test    ebx, ebx
0x180058e88  jz      short loc_180058EE9
0x180058e8a  mov     r9, gs:40h
0x180058e93  lea     r8, aWerCrashapiUUE_6; "WER/CrashAPI/%u:%u: ERROR WerpNtWow64Re"...
0x180058e9a  xor     edx, edx; Level
0x180058e9c  mov     [rsp+30h+lpNumberOfBytesRead], 0CD4h
0x180058ea4  mov     ecx, 96h; ComponentId
0x180058ea9  call    cs:__imp_DbgPrintEx
0x180058eb0  nop     dword ptr [rax+rax+00h]
0x180058eb5  mov     eax, 0D0000001h
0x180058eba  jmp     loc_180058FCC
0x180058ebf  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x180058ec3  mov     rcx, rdi; hProcess
0x180058ec6  call    WerpReadPeb32FromProcess
0x180058ecb  mov     r14d, eax
0x180058ece  test    eax, eax
0x180058ed0  jns     short loc_180058E77
0x180058ed2  mov     [rsp+30h+lpNumberOfBytesRead], 0CB7h
0x180058eda  jmp     loc_180058E4C
0x180058edf  mov     eax, 80070490h
0x180058ee4  jmp     loc_180058FCC
0x180058ee9  mov     r9d, 968h; nSize
0x180058eef  mov     qword ptr [rsp+30h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180058ef8  mov     r8, rsi; lpBuffer
0x180058efb  mov     rcx, rdi; hProcess
0x180058efe  call    cs:__imp_ReadProcessMemory
0x180058f05  nop     dword ptr [rax+rax+00h]
0x180058f0a  test    eax, eax
0x180058f0c  jnz     short loc_180058F53
0x180058f0e  mov     r9, gs:40h
0x180058f17  lea     r8, aWerCrashapiUUE_19; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x180058f1e  xor     edx, edx; Level
0x180058f20  mov     [rsp+30h+lpNumberOfBytesRead], 0CE3h
0x180058f28  mov     ecx, 96h; ComponentId
0x180058f2d  call    cs:__imp_DbgPrintEx
0x180058f34  nop     dword ptr [rax+rax+00h]
0x180058f39  mov     eax, gs:68h
0x180058f41  test    eax, eax
0x180058f43  jle     loc_180058FCC
0x180058f49  movzx   eax, ax
0x180058f4c  or      eax, 80070000h
0x180058f51  jmp     short loc_180058FCC
0x180058f53  mov     rcx, rsi
0x180058f56  call    WerpValidatePebHeader
0x180058f5b  test    eax, eax
0x180058f5d  jns     short loc_180058F91
0x180058f5f  mov     r9, gs:40h
0x180058f68  lea     r8, aWerCrashapiUUE_43; "WER/CrashAPI/%u:%u: ERROR WerpValidateP"...
0x180058f6f  xor     edx, edx; Level
0x180058f71  mov     [rsp+30h+lpNumberOfBytesRead], 0CECh
0x180058f79  mov     ecx, 96h; ComponentId
0x180058f7e  call    cs:__imp_DbgPrintEx
0x180058f85  nop     dword ptr [rax+rax+00h]
0x180058f8a  mov     eax, 80004005h
0x180058f8f  jmp     short loc_180058FCC
0x180058f91  xor     eax, eax
0x180058f93  mov     [rsi+8A6h], ax
0x180058f9a  jmp     short loc_180058FCC
0x180058f9c  mov     [rsp+30h+lpNumberOfBytesRead], 0C60h
0x180058fa4  lea     r8, aWerCrashapiUUE_49; "WER/CrashAPI/%u:%u: ERROR Invalid argum"...
0x180058fab  mov     r9, gs:40h
0x180058fb4  xor     edx, edx; Level
0x180058fb6  mov     ecx, 96h; ComponentId
0x180058fbb  call    cs:__imp_DbgPrintEx
0x180058fc2  nop     dword ptr [rax+rax+00h]
0x180058fc7  mov     eax, 80070057h
0x180058fcc  add     rsp, 30h
0x180058fd0  pop     r14
0x180058fd2  pop     rdi
0x180058fd3  pop     rsi
0x180058fd4  pop     rbx
0x180058fd5  pop     rbp
0x180058fd6  retn
```
