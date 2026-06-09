# WerpReadPeb32FromProcess

- ea: `0x18001c040`
- end: `0x18001c198`
- name: `WerpReadPeb32FromProcess`
- size: `344`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001bad4`

## callees

- `0x180003617`
- `0x18001c040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c147`
- `ntdll!NtQueryInformationProcess` at `0x18001c086`
- `ntdll!NtQueryInformationProcess` at `0x18001c086`
- `ntdll!DbgPrintEx` at `0x18001c0b4`
- `ntdll!DbgPrintEx` at `0x18001c0ed`
- `ntdll!DbgPrintEx` at `0x18001c141`
- `ntdll!DbgPrintEx` at `0x18001c17d`
- `ntdll!DbgPrintEx` at `0x18001c0b4`
- `ntdll!DbgPrintEx` at `0x18001c0ed`
- `ntdll!DbgPrintEx` at `0x18001c141`
- `ntdll!DbgPrintEx` at `0x18001c17d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001c119`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001c119`

## string_xrefs

- `0x18001c133`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c
signed int __fastcall WerpReadPeb32FromProcess(HANDLE hProcess, LPVOID lpBuffer)
{
  NTSTATUS v4; // ebx
  DWORD v5; // eax
  signed int result; // eax
  DWORD v7; // eax
  DWORD CurrentProcessId_0; // eax
  DWORD v9; // eax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  if ( hProcess && lpBuffer )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessWow64Information, &v10, 8u, 0);
    if ( v4 >= 0 )
    {
      if ( v10 )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(v10 + 560), lpBuffer, 8u, 0) )
        {
          return 0;
        }
        else
        {
          CurrentProcessId_0 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n",
            CurrentProcessId_0,
            2970);
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        v7 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR No 32 PEB for process\n", v7, 2960);
        return -2147467259;
      }
    }
    else
    {
      v5 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed with status 0x%x\n",
        v5,
        2952,
        v4);
      return v4 | 0x10000000;
    }
  }
  else
  {
    v9 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", v9, 2939);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x18001c040  mov     rax, rsp
0x18001c043  mov     [rax+10h], rbx
0x18001c047  mov     [rax+18h], rsi
0x18001c04b  push    rdi
0x18001c04c  sub     rsp, 30h
0x18001c050  mov     qword ptr [rax+8], 0
0x18001c058  mov     rsi, rdx
0x18001c05b  mov     rdi, rcx
0x18001c05e  test    rcx, rcx
0x18001c061  jz      loc_18001C15F
0x18001c067  test    rdx, rdx
0x18001c06a  jz      loc_18001C15F
0x18001c070  mov     r9d, 8; ProcessInformationLength
0x18001c076  mov     qword ptr [rax-18h], 0
0x18001c07e  lea     r8, [rax+8]; ProcessInformation
0x18001c082  lea     edx, [r9+12h]; ProcessInformationClass
0x18001c086  call    cs:__imp_NtQueryInformationProcess
0x18001c08c  mov     ebx, eax
0x18001c08e  test    eax, eax
0x18001c090  jns     short loc_18001C0C5
0x18001c092  call    GetCurrentProcessId_0
0x18001c097  mov     r9d, eax
0x18001c09a  mov     [rsp+38h+var_10], ebx
0x18001c09e  lea     r8, aWerCrashapiUUE_16; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x18001c0a5  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B88h
0x18001c0ad  xor     edx, edx; Level
0x18001c0af  mov     ecx, 96h; ComponentId
0x18001c0b4  call    cs:__imp_DbgPrintEx
0x18001c0ba  bts     ebx, 1Ch
0x18001c0be  mov     eax, ebx
0x18001c0c0  jmp     loc_18001C188
0x18001c0c5  mov     rdx, [rsp+38h+arg_0]
0x18001c0ca  test    rdx, rdx
0x18001c0cd  jnz     short loc_18001C0FD
0x18001c0cf  call    GetCurrentProcessId_0
0x18001c0d4  mov     r9d, eax
0x18001c0d7  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B90h
0x18001c0df  lea     r8, aWerCrashapiUUE_23; "WER/CrashAPI/%u:%u: ERROR No 32 PEB for"...
0x18001c0e6  xor     edx, edx; Level
0x18001c0e8  mov     ecx, 96h; ComponentId
0x18001c0ed  call    cs:__imp_DbgPrintEx
0x18001c0f3  mov     eax, 80004005h
0x18001c0f8  jmp     loc_18001C188
0x18001c0fd  add     rdx, 230h; lpBaseAddress
0x18001c104  mov     [rsp+38h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18001c10d  mov     r9d, 8; nSize
0x18001c113  mov     r8, rsi; lpBuffer
0x18001c116  mov     rcx, rdi; hProcess
0x18001c119  call    cs:__imp_ReadProcessMemory
0x18001c11f  test    eax, eax
0x18001c121  jnz     short loc_18001C15B
0x18001c123  call    GetCurrentProcessId_0
0x18001c128  mov     r9d, eax
0x18001c12b  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B9Ah
0x18001c133  lea     r8, aWerCrashapiUUE_10; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x18001c13a  xor     edx, edx; Level
0x18001c13c  mov     ecx, 96h; ComponentId
0x18001c141  call    cs:__imp_DbgPrintEx
0x18001c147  call    cs:__imp_GetLastError
0x18001c14d  test    eax, eax
0x18001c14f  jle     short loc_18001C188
0x18001c151  movzx   eax, ax
0x18001c154  or      eax, 80070000h
0x18001c159  jmp     short loc_18001C188
0x18001c15b  xor     eax, eax
0x18001c15d  jmp     short loc_18001C188
0x18001c15f  call    GetCurrentProcessId_0
0x18001c164  mov     r9d, eax
0x18001c167  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B7Bh
0x18001c16f  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x18001c176  xor     edx, edx; Level
0x18001c178  mov     ecx, 96h; ComponentId
0x18001c17d  call    cs:__imp_DbgPrintEx
0x18001c183  mov     eax, 80070057h
0x18001c188  mov     rbx, [rsp+38h+arg_8]
0x18001c18d  mov     rsi, [rsp+38h+arg_10]
0x18001c192  add     rsp, 30h
0x18001c196  pop     rdi
0x18001c197  retn
```
