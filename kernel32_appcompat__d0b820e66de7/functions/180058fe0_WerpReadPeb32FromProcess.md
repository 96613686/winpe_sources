# WerpReadPeb32FromProcess

- ea: `0x180058fe0`
- end: `0x180059161`
- name: `WerpReadPeb32FromProcess`
- size: `385`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180058d5c`

## callees

- `0x180058fe0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18005905b`
- `ntdll!DbgPrintEx` at `0x180059099`
- `ntdll!DbgPrintEx` at `0x1800590fa`
- `ntdll!DbgPrintEx` at `0x18005913f`
- `ntdll!DbgPrintEx` at `0x18005905b`
- `ntdll!DbgPrintEx` at `0x180059099`
- `ntdll!DbgPrintEx` at `0x1800590fa`
- `ntdll!DbgPrintEx` at `0x18005913f`
- `ntdll!NtQueryInformationProcess` at `0x180059026`
- `ntdll!NtQueryInformationProcess` at `0x180059026`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800590cb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800590cb`

## string_xrefs

- `0x1800590e4`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c
signed int __fastcall WerpReadPeb32FromProcess(HANDLE hProcess, LPVOID lpBuffer)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  signed int result; // eax
  __int64 Level; // [rsp+40h] [rbp+8h] BYREF

  Level = 0;
  if ( hProcess && lpBuffer )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessWow64Information, &Level, 8u, 0);
    v5 = v4;
    if ( v4 >= 0 )
    {
      if ( Level )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(Level + 560), lpBuffer, 8u, 0) )
        {
          return 0;
        }
        else
        {
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n",
            NtCurrentTeb()->ClientId.UniqueProcess,
            2970);
          result = NtCurrentTeb()->LastErrorValue;
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        DbgPrintEx(
          0x96u,
          0,
          "WER/CrashAPI/%u:%u: ERROR No 32 PEB for process\n",
          NtCurrentTeb()->ClientId.UniqueProcess,
          2960);
        return -2147467259;
      }
    }
    else
    {
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed with status 0x%x\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        2952,
        v4);
      return v5 | 0x10000000;
    }
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", NtCurrentTeb()->ClientId.UniqueProcess, 2939);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180058fe0  mov     rax, rsp
0x180058fe3  mov     [rax+10h], rbx
0x180058fe7  mov     [rax+18h], rsi
0x180058feb  push    rdi
0x180058fec  sub     rsp, 30h
0x180058ff0  mov     qword ptr [rax+8], 0
0x180058ff8  mov     rsi, rdx
0x180058ffb  mov     rdi, rcx
0x180058ffe  test    rcx, rcx
0x180059001  jz      loc_180059120
0x180059007  test    rdx, rdx
0x18005900a  jz      loc_180059120
0x180059010  mov     r9d, 8; ProcessInformationLength
0x180059016  mov     qword ptr [rax-18h], 0
0x18005901e  lea     r8, [rax+8]; ProcessInformation
0x180059022  lea     edx, [r9+12h]; ProcessInformationClass
0x180059026  call    cs:__imp_NtQueryInformationProcess
0x18005902d  nop     dword ptr [rax+rax+00h]
0x180059032  mov     ebx, eax
0x180059034  test    eax, eax
0x180059036  jns     short loc_180059072
0x180059038  mov     r9, gs:40h
0x180059041  lea     r8, aWerCrashapiUUE_32; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x180059048  mov     [rsp+38h+var_10], eax
0x18005904c  xor     edx, edx; Level
0x18005904e  mov     ecx, 96h; ComponentId
0x180059053  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B88h
0x18005905b  call    cs:__imp_DbgPrintEx
0x180059062  nop     dword ptr [rax+rax+00h]
0x180059067  bts     ebx, 1Ch
0x18005906b  mov     eax, ebx
0x18005906d  jmp     loc_180059150
0x180059072  mov     rdx, [rsp+38h+Level]; Level
0x180059077  test    rdx, rdx
0x18005907a  jnz     short loc_1800590AF
0x18005907c  mov     r9, gs:40h
0x180059085  lea     r8, aWerCrashapiUUE_40; "WER/CrashAPI/%u:%u: ERROR No 32 PEB for"...
0x18005908c  mov     ecx, 96h; ComponentId
0x180059091  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B90h
0x180059099  call    cs:__imp_DbgPrintEx
0x1800590a0  nop     dword ptr [rax+rax+00h]
0x1800590a5  mov     eax, 80004005h
0x1800590aa  jmp     loc_180059150
0x1800590af  add     rdx, 230h; lpBaseAddress
0x1800590b6  mov     [rsp+38h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800590bf  mov     r9d, 8; nSize
0x1800590c5  mov     r8, rsi; lpBuffer
0x1800590c8  mov     rcx, rdi; hProcess
0x1800590cb  call    cs:__imp_ReadProcessMemory
0x1800590d2  nop     dword ptr [rax+rax+00h]
0x1800590d7  test    eax, eax
0x1800590d9  jnz     short loc_18005911C
0x1800590db  mov     r9, gs:40h
0x1800590e4  lea     r8, aWerCrashapiUUE_20; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x1800590eb  xor     edx, edx; Level
0x1800590ed  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B9Ah
0x1800590f5  mov     ecx, 96h; ComponentId
0x1800590fa  call    cs:__imp_DbgPrintEx
0x180059101  nop     dword ptr [rax+rax+00h]
0x180059106  mov     eax, gs:68h
0x18005910e  test    eax, eax
0x180059110  jle     short loc_180059150
0x180059112  movzx   eax, ax
0x180059115  or      eax, 80070000h
0x18005911a  jmp     short loc_180059150
0x18005911c  xor     eax, eax
0x18005911e  jmp     short loc_180059150
0x180059120  mov     r9, gs:40h
0x180059129  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x180059130  xor     edx, edx; Level
0x180059132  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B7Bh
0x18005913a  mov     ecx, 96h; ComponentId
0x18005913f  call    cs:__imp_DbgPrintEx
0x180059146  nop     dword ptr [rax+rax+00h]
0x18005914b  mov     eax, 80070057h
0x180059150  mov     rbx, [rsp+38h+arg_8]
0x180059155  mov     rsi, [rsp+38h+arg_10]
0x18005915a  add     rsp, 30h
0x18005915e  pop     rdi
0x18005915f  retn
```
