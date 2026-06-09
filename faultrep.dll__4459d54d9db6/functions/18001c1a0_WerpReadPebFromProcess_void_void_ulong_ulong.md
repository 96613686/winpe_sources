# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x18001c1a0`
- end: `0x18001c2f6`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `342`
- prototype: `signed int __fastcall(HANDLE hProcess, void *lpBuffer, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001bad4`
- `0x1800401c4`

## callees

- `0x180003617`
- `0x18001c1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2a5`
- `ntdll!NtQueryInformationProcess` at `0x18001c1ee`
- `ntdll!NtQueryInformationProcess` at `0x18001c1ee`
- `ntdll!DbgPrintEx` at `0x18001c216`
- `ntdll!DbgPrintEx` at `0x18001c24e`
- `ntdll!DbgPrintEx` at `0x18001c29f`
- `ntdll!DbgPrintEx` at `0x18001c2db`
- `ntdll!DbgPrintEx` at `0x18001c216`
- `ntdll!DbgPrintEx` at `0x18001c24e`
- `ntdll!DbgPrintEx` at `0x18001c29f`
- `ntdll!DbgPrintEx` at `0x18001c2db`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001c277`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001c277`

## string_xrefs

- `0x18001c291`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c
signed int __fastcall WerpReadPebFromProcess(HANDLE hProcess, void *lpBuffer, unsigned int a3)
{
  __int64 v3; // rsi
  DWORD v6; // eax
  signed int result; // eax
  DWORD v8; // eax
  DWORD CurrentProcessId_0; // eax
  DWORD v10; // eax
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF

  v3 = a3;
  memset(v11, 0, 48);
  if ( hProcess && lpBuffer )
  {
    if ( NtQueryInformationProcess(hProcess, ProcessBasicInformation, v11, 0x30u, 0) >= 0 )
    {
      if ( v11[1] )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(v11[1] + v3), lpBuffer, 8u, 0) )
        {
          return 0;
        }
        else
        {
          CurrentProcessId_0 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n",
            CurrentProcessId_0,
            3126);
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        v8 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR No PEB for process\n", v8, 3116);
        return -2147467259;
      }
    }
    else
    {
      v6 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed\n", v6, 3108);
      return -2147024890;
    }
  }
  else
  {
    v10 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", v10, 3098);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x18001c1a0  mov     rax, rsp
0x18001c1a3  mov     [rax+8], rbx
0x18001c1a7  mov     [rax+10h], rsi
0x18001c1ab  push    rdi
0x18001c1ac  sub     rsp, 60h
0x18001c1b0  mov     esi, r8d
0x18001c1b3  xorps   xmm0, xmm0
0x18001c1b6  mov     rdi, rdx
0x18001c1b9  mov     rbx, rcx
0x18001c1bc  movups  xmmword ptr [rax-38h], xmm0
0x18001c1c0  movups  xmmword ptr [rax-28h], xmm0
0x18001c1c4  movups  xmmword ptr [rax-18h], xmm0
0x18001c1c8  test    rcx, rcx
0x18001c1cb  jz      loc_18001C2BD
0x18001c1d1  test    rdx, rdx
0x18001c1d4  jz      loc_18001C2BD
0x18001c1da  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18001c1e0  mov     qword ptr [rax-48h], 0
0x18001c1e8  lea     r8, [rax-38h]; ProcessInformation
0x18001c1ec  xor     edx, edx; ProcessInformationClass
0x18001c1ee  call    cs:__imp_NtQueryInformationProcess
0x18001c1f4  test    eax, eax
0x18001c1f6  jns     short loc_18001C226
0x18001c1f8  call    GetCurrentProcessId_0
0x18001c1fd  mov     r9d, eax
0x18001c200  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C24h
0x18001c208  lea     r8, aWerCrashapiUUE_14; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x18001c20f  xor     edx, edx; Level
0x18001c211  mov     ecx, 96h; ComponentId
0x18001c216  call    cs:__imp_DbgPrintEx
0x18001c21c  mov     eax, 80070006h
0x18001c221  jmp     loc_18001C2E6
0x18001c226  mov     rax, [rsp+68h+var_30]
0x18001c22b  test    rax, rax
0x18001c22e  jnz     short loc_18001C25E
0x18001c230  call    GetCurrentProcessId_0
0x18001c235  mov     r9d, eax
0x18001c238  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C2Ch
0x18001c240  lea     r8, aWerCrashapiUUE_30; "WER/CrashAPI/%u:%u: ERROR No PEB for pr"...
0x18001c247  xor     edx, edx; Level
0x18001c249  mov     ecx, 96h; ComponentId
0x18001c24e  call    cs:__imp_DbgPrintEx
0x18001c254  mov     eax, 80004005h
0x18001c259  jmp     loc_18001C2E6
0x18001c25e  lea     rdx, [rax+rsi]; lpBaseAddress
0x18001c262  mov     [rsp+68h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18001c26b  mov     r9d, 8; nSize
0x18001c271  mov     r8, rdi; lpBuffer
0x18001c274  mov     rcx, rbx; hProcess
0x18001c277  call    cs:__imp_ReadProcessMemory
0x18001c27d  test    eax, eax
0x18001c27f  jnz     short loc_18001C2B9
0x18001c281  call    GetCurrentProcessId_0
0x18001c286  mov     r9d, eax
0x18001c289  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C36h
0x18001c291  lea     r8, aWerCrashapiUUE_11; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x18001c298  xor     edx, edx; Level
0x18001c29a  mov     ecx, 96h; ComponentId
0x18001c29f  call    cs:__imp_DbgPrintEx
0x18001c2a5  call    cs:__imp_GetLastError
0x18001c2ab  test    eax, eax
0x18001c2ad  jle     short loc_18001C2E6
0x18001c2af  movzx   eax, ax
0x18001c2b2  or      eax, 80070000h
0x18001c2b7  jmp     short loc_18001C2E6
0x18001c2b9  xor     eax, eax
0x18001c2bb  jmp     short loc_18001C2E6
0x18001c2bd  call    GetCurrentProcessId_0
0x18001c2c2  mov     r9d, eax
0x18001c2c5  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C1Ah
0x18001c2cd  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x18001c2d4  xor     edx, edx; Level
0x18001c2d6  mov     ecx, 96h; ComponentId
0x18001c2db  call    cs:__imp_DbgPrintEx
0x18001c2e1  mov     eax, 80070057h
0x18001c2e6  mov     rbx, [rsp+68h+arg_0]
0x18001c2eb  mov     rsi, [rsp+68h+arg_8]
0x18001c2f0  add     rsp, 60h
0x18001c2f4  pop     rdi
0x18001c2f5  retn
```
