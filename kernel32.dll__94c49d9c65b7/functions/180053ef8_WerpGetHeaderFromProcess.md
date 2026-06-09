# WerpGetHeaderFromProcess

- ea: `0x180053ef8`
- end: `0x180054139`
- name: `WerpGetHeaderFromProcess`
- size: `577`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004d31c`
- `0x180053d68`
- `0x18006f1ac`

## callees

- `0x18004c6cc`
- `0x180053ef8`
- `0x180054140`
- `0x18005bc00`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180053fed`
- `ntdll!DbgPrintEx` at `0x18005402d`
- `ntdll!DbgPrintEx` at `0x1800540a5`
- `ntdll!DbgPrintEx` at `0x1800540ec`
- `ntdll!DbgPrintEx` at `0x180054123`
- `ntdll!DbgPrintEx` at `0x180053fed`
- `ntdll!DbgPrintEx` at `0x18005402d`
- `ntdll!DbgPrintEx` at `0x1800540a5`
- `ntdll!DbgPrintEx` at `0x1800540ec`
- `ntdll!DbgPrintEx` at `0x180054123`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005407c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005407c`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180053f38`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180053f59`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180053f73`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180053f38`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180053f59`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180053f73`

## string_xrefs

- `0x18005408f`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`
- `0x180054017`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x180053faf`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x180053fdf`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`

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
0x180053ef8  push    rbp
0x180053efa  push    rbx
0x180053efb  push    rsi
0x180053efc  push    rdi
0x180053efd  push    r14
0x180053eff  mov     rbp, rsp
0x180053f02  sub     rsp, 30h
0x180053f06  mov     [rbp+lpBaseAddress], 0
0x180053f0e  mov     rsi, rdx
0x180053f11  mov     [rbp+Wow64Process], 0
0x180053f18  mov     rdi, rcx
0x180053f1b  mov     [rbp+arg_10], 0
0x180053f22  test    rcx, rcx
0x180053f25  jz      loc_180054104
0x180053f2b  test    rdx, rdx
0x180053f2e  jz      loc_180054104
0x180053f34  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x180053f38  call    cs:__imp_IsWow64Process
0x180053f3e  test    eax, eax
0x180053f40  jnz     short loc_180053F47
0x180053f42  mov     [rbp+Wow64Process], eax
0x180053f45  jmp     short loc_180053F4A
0x180053f47  mov     eax, [rbp+Wow64Process]
0x180053f4a  xor     ebx, ebx
0x180053f4c  lea     rdx, [rbp+arg_10]; Wow64Process
0x180053f50  test    eax, eax
0x180053f52  setz    bl
0x180053f55  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x180053f59  call    cs:__imp_IsWow64Process
0x180053f5f  test    eax, eax
0x180053f61  jnz     short loc_180053F66
0x180053f63  mov     [rbp+arg_10], eax
0x180053f66  cmp     [rbp+arg_10], 0
0x180053f6a  jz      short loc_180053F92
0x180053f6c  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x180053f70  mov     rcx, rdi; hProcess
0x180053f73  call    cs:__imp_IsWow64Process
0x180053f79  test    eax, eax
0x180053f7b  jnz     short loc_180053F82
0x180053f7d  mov     [rbp+Wow64Process], eax
0x180053f80  jmp     short loc_180053F85
0x180053f82  mov     eax, [rbp+Wow64Process]
0x180053f85  test    eax, eax
0x180053f87  jnz     short loc_180053F8E
0x180053f89  lea     ebx, [rax+1]
0x180053f8c  jmp     short loc_180053F9D
0x180053f8e  xor     ebx, ebx
0x180053f90  jmp     short loc_180053F95
0x180053f92  mov     eax, [rbp+Wow64Process]
0x180053f95  test    eax, eax
0x180053f97  jnz     loc_18005403D
0x180053f9d  cmp     [rbp+arg_10], 0
0x180053fa1  jz      short loc_180053FBB
0x180053fa3  test    ebx, ebx
0x180053fa5  jz      short loc_180053FBB
0x180053fa7  mov     [rsp+30h+lpNumberOfBytesRead], 0C8Fh
0x180053faf  lea     r8, aWerCrashapiUUE_15; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x180053fb6  jmp     loc_180054113
0x180053fbb  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x180053fbf  mov     rcx, rdi; hProcess
0x180053fc2  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x180053fc7  mov     r14d, eax
0x180053fca  test    eax, eax
0x180053fcc  jns     short loc_180053FFB
0x180053fce  mov     [rsp+30h+lpNumberOfBytesRead], 0CA4h
0x180053fd6  mov     r9, gs:40h
0x180053fdf  lea     r8, aWerCrashapiUUE_15; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x180053fe6  xor     edx, edx; Level
0x180053fe8  mov     ecx, 96h; ComponentId
0x180053fed  call    cs:__imp_DbgPrintEx
0x180053ff3  mov     eax, r14d
0x180053ff6  jmp     loc_18005412E
0x180053ffb  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180053fff  test    rdx, rdx
0x180054002  jz      short loc_18005405D
0x180054004  cmp     [rbp+arg_10], 0
0x180054008  jz      short loc_180054067
0x18005400a  test    ebx, ebx
0x18005400c  jz      short loc_180054067
0x18005400e  mov     r9, gs:40h
0x180054017  lea     r8, aWerCrashapiUUE_6; "WER/CrashAPI/%u:%u: ERROR WerpNtWow64Re"...
0x18005401e  xor     edx, edx; Level
0x180054020  mov     [rsp+30h+lpNumberOfBytesRead], 0CD4h
0x180054028  mov     ecx, 96h; ComponentId
0x18005402d  call    cs:__imp_DbgPrintEx
0x180054033  mov     eax, 0D0000001h
0x180054038  jmp     loc_18005412E
0x18005403d  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x180054041  mov     rcx, rdi; hProcess
0x180054044  call    WerpReadPeb32FromProcess
0x180054049  mov     r14d, eax
0x18005404c  test    eax, eax
0x18005404e  jns     short loc_180053FFB
0x180054050  mov     [rsp+30h+lpNumberOfBytesRead], 0CB7h
0x180054058  jmp     loc_180053FD6
0x18005405d  mov     eax, 80070490h
0x180054062  jmp     loc_18005412E
0x180054067  mov     r9d, 968h; nSize
0x18005406d  mov     qword ptr [rsp+30h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180054076  mov     r8, rsi; lpBuffer
0x180054079  mov     rcx, rdi; hProcess
0x18005407c  call    cs:__imp_ReadProcessMemory
0x180054082  test    eax, eax
0x180054084  jnz     short loc_1800540C1
0x180054086  mov     r9, gs:40h
0x18005408f  lea     r8, aWerCrashapiUUE_19; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x180054096  xor     edx, edx; Level
0x180054098  mov     [rsp+30h+lpNumberOfBytesRead], 0CE3h
0x1800540a0  mov     ecx, 96h; ComponentId
0x1800540a5  call    cs:__imp_DbgPrintEx
0x1800540ab  mov     eax, gs:68h
0x1800540b3  test    eax, eax
0x1800540b5  jle     short loc_18005412E
0x1800540b7  movzx   eax, ax
0x1800540ba  or      eax, 80070000h
0x1800540bf  jmp     short loc_18005412E
0x1800540c1  mov     rcx, rsi
0x1800540c4  call    WerpValidatePebHeader
0x1800540c9  test    eax, eax
0x1800540cb  jns     short loc_1800540F9
0x1800540cd  mov     r9, gs:40h
0x1800540d6  lea     r8, aWerCrashapiUUE_43; "WER/CrashAPI/%u:%u: ERROR WerpValidateP"...
0x1800540dd  xor     edx, edx; Level
0x1800540df  mov     [rsp+30h+lpNumberOfBytesRead], 0CECh
0x1800540e7  mov     ecx, 96h; ComponentId
0x1800540ec  call    cs:__imp_DbgPrintEx
0x1800540f2  mov     eax, 80004005h
0x1800540f7  jmp     short loc_18005412E
0x1800540f9  xor     eax, eax
0x1800540fb  mov     [rsi+8A6h], ax
0x180054102  jmp     short loc_18005412E
0x180054104  mov     [rsp+30h+lpNumberOfBytesRead], 0C60h
0x18005410c  lea     r8, aWerCrashapiUUE_49; "WER/CrashAPI/%u:%u: ERROR Invalid argum"...
0x180054113  mov     r9, gs:40h
0x18005411c  xor     edx, edx; Level
0x18005411e  mov     ecx, 96h; ComponentId
0x180054123  call    cs:__imp_DbgPrintEx
0x180054129  mov     eax, 80070057h
0x18005412e  add     rsp, 30h
0x180054132  pop     r14
0x180054134  pop     rdi
0x180054135  pop     rsi
0x180054136  pop     rbx
0x180054137  pop     rbp
0x180054138  retn
```
