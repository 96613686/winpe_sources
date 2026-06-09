# WerpReadPeb32FromProcess

- ea: `0x180054140`
- end: `0x18005429c`
- name: `WerpReadPeb32FromProcess`
- size: `348`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180053ef8`

## callees

- `0x180054140`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800541b5`
- `ntdll!DbgPrintEx` at `0x1800541ed`
- `ntdll!DbgPrintEx` at `0x180054242`
- `ntdll!DbgPrintEx` at `0x180054281`
- `ntdll!DbgPrintEx` at `0x1800541b5`
- `ntdll!DbgPrintEx` at `0x1800541ed`
- `ntdll!DbgPrintEx` at `0x180054242`
- `ntdll!DbgPrintEx` at `0x180054281`
- `ntdll!NtQueryInformationProcess` at `0x180054186`
- `ntdll!NtQueryInformationProcess` at `0x180054186`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180054219`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180054219`

## string_xrefs

- `0x18005422c`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

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
0x180054140  mov     rax, rsp
0x180054143  mov     [rax+10h], rbx
0x180054147  mov     [rax+18h], rsi
0x18005414b  push    rdi
0x18005414c  sub     rsp, 30h
0x180054150  mov     qword ptr [rax+8], 0
0x180054158  mov     rsi, rdx
0x18005415b  mov     rdi, rcx
0x18005415e  test    rcx, rcx
0x180054161  jz      loc_180054262
0x180054167  test    rdx, rdx
0x18005416a  jz      loc_180054262
0x180054170  mov     r9d, 8; ProcessInformationLength
0x180054176  mov     qword ptr [rax-18h], 0
0x18005417e  lea     r8, [rax+8]; ProcessInformation
0x180054182  lea     edx, [r9+12h]; ProcessInformationClass
0x180054186  call    cs:__imp_NtQueryInformationProcess
0x18005418c  mov     ebx, eax
0x18005418e  test    eax, eax
0x180054190  jns     short loc_1800541C6
0x180054192  mov     r9, gs:40h
0x18005419b  lea     r8, aWerCrashapiUUE_32; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x1800541a2  mov     [rsp+38h+var_10], eax
0x1800541a6  xor     edx, edx; Level
0x1800541a8  mov     ecx, 96h; ComponentId
0x1800541ad  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B88h
0x1800541b5  call    cs:__imp_DbgPrintEx
0x1800541bb  bts     ebx, 1Ch
0x1800541bf  mov     eax, ebx
0x1800541c1  jmp     loc_18005428C
0x1800541c6  mov     rdx, [rsp+38h+Level]; Level
0x1800541cb  test    rdx, rdx
0x1800541ce  jnz     short loc_1800541FD
0x1800541d0  mov     r9, gs:40h
0x1800541d9  lea     r8, aWerCrashapiUUE_40; "WER/CrashAPI/%u:%u: ERROR No 32 PEB for"...
0x1800541e0  mov     ecx, 96h; ComponentId
0x1800541e5  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B90h
0x1800541ed  call    cs:__imp_DbgPrintEx
0x1800541f3  mov     eax, 80004005h
0x1800541f8  jmp     loc_18005428C
0x1800541fd  add     rdx, 230h; lpBaseAddress
0x180054204  mov     [rsp+38h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18005420d  mov     r9d, 8; nSize
0x180054213  mov     r8, rsi; lpBuffer
0x180054216  mov     rcx, rdi; hProcess
0x180054219  call    cs:__imp_ReadProcessMemory
0x18005421f  test    eax, eax
0x180054221  jnz     short loc_18005425E
0x180054223  mov     r9, gs:40h
0x18005422c  lea     r8, aWerCrashapiUUE_20; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x180054233  xor     edx, edx; Level
0x180054235  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B9Ah
0x18005423d  mov     ecx, 96h; ComponentId
0x180054242  call    cs:__imp_DbgPrintEx
0x180054248  mov     eax, gs:68h
0x180054250  test    eax, eax
0x180054252  jle     short loc_18005428C
0x180054254  movzx   eax, ax
0x180054257  or      eax, 80070000h
0x18005425c  jmp     short loc_18005428C
0x18005425e  xor     eax, eax
0x180054260  jmp     short loc_18005428C
0x180054262  mov     r9, gs:40h
0x18005426b  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x180054272  xor     edx, edx; Level
0x180054274  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B7Bh
0x18005427c  mov     ecx, 96h; ComponentId
0x180054281  call    cs:__imp_DbgPrintEx
0x180054287  mov     eax, 80070057h
0x18005428c  mov     rbx, [rsp+38h+arg_8]
0x180054291  mov     rsi, [rsp+38h+arg_10]
0x180054296  add     rsp, 30h
0x18005429a  pop     rdi
0x18005429b  retn
```
