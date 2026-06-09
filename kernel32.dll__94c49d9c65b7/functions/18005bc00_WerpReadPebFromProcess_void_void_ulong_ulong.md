# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x18005bc00`
- end: `0x18005bd51`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `337`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *lpBuffer, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180053ef8`

## callees

- `0x18005bc00`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18005bc70`
- `ntdll!DbgPrintEx` at `0x18005bca7`
- `ntdll!DbgPrintEx` at `0x18005bcfc`
- `ntdll!DbgPrintEx` at `0x18005bd3b`
- `ntdll!DbgPrintEx` at `0x18005bc70`
- `ntdll!DbgPrintEx` at `0x18005bca7`
- `ntdll!DbgPrintEx` at `0x18005bcfc`
- `ntdll!DbgPrintEx` at `0x18005bd3b`
- `ntdll!NtQueryInformationProcess` at `0x18005bc47`
- `ntdll!NtQueryInformationProcess` at `0x18005bc47`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005bcd3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005bcd3`

## string_xrefs

- `0x18005bce6`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c
signed int __fastcall WerpReadPebFromProcess(HANDLE hProcess, void *lpBuffer)
{
  signed int result; // eax
  ULONG v5[14]; // [rsp+30h] [rbp-38h] BYREF

  memset(v5, 0, 48);
  if ( hProcess && lpBuffer )
  {
    if ( NtQueryInformationProcess(hProcess, ProcessBasicInformation, v5, 0x30u, 0) >= 0 )
    {
      if ( *(_QWORD *)&v5[2] )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(*(_QWORD *)&v5[2] + 856LL), lpBuffer, 8u, 0) )
        {
          return 0;
        }
        else
        {
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n",
            NtCurrentTeb()->ClientId.UniqueProcess,
            3126);
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
          "WER/CrashAPI/%u:%u: ERROR No PEB for process\n",
          NtCurrentTeb()->ClientId.UniqueProcess,
          3116);
        return -2147467259;
      }
    }
    else
    {
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        3108);
      return -2147024890;
    }
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", NtCurrentTeb()->ClientId.UniqueProcess, 3098);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x18005bc00  mov     rax, rsp
0x18005bc03  mov     [rax+8], rbx
0x18005bc07  push    rdi
0x18005bc08  sub     rsp, 60h
0x18005bc0c  xorps   xmm0, xmm0
0x18005bc0f  mov     rdi, rdx
0x18005bc12  mov     rbx, rcx
0x18005bc15  movups  xmmword ptr [rax-38h], xmm0
0x18005bc19  movups  xmmword ptr [rax-28h], xmm0
0x18005bc1d  movups  xmmword ptr [rax-18h], xmm0
0x18005bc21  test    rcx, rcx
0x18005bc24  jz      loc_18005BD1C
0x18005bc2a  test    rdx, rdx
0x18005bc2d  jz      loc_18005BD1C
0x18005bc33  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18005bc39  mov     qword ptr [rax-48h], 0
0x18005bc41  lea     r8, [rax-38h]; ProcessInformation
0x18005bc45  xor     edx, edx; ProcessInformationClass
0x18005bc47  call    cs:__imp_NtQueryInformationProcess
0x18005bc4d  test    eax, eax
0x18005bc4f  jns     short loc_18005BC80
0x18005bc51  mov     r9, gs:40h
0x18005bc5a  lea     r8, aWerCrashapiUUE_29; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x18005bc61  xor     edx, edx; Level
0x18005bc63  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C24h
0x18005bc6b  mov     ecx, 96h; ComponentId
0x18005bc70  call    cs:__imp_DbgPrintEx
0x18005bc76  mov     eax, 80070006h
0x18005bc7b  jmp     loc_18005BD46
0x18005bc80  mov     rdx, qword ptr [rsp+68h+Level]; Level
0x18005bc85  test    rdx, rdx
0x18005bc88  jnz     short loc_18005BCB7
0x18005bc8a  mov     r9, gs:40h
0x18005bc93  lea     r8, aWerCrashapiUUE_50; "WER/CrashAPI/%u:%u: ERROR No PEB for pr"...
0x18005bc9a  mov     ecx, 96h; ComponentId
0x18005bc9f  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C2Ch
0x18005bca7  call    cs:__imp_DbgPrintEx
0x18005bcad  mov     eax, 80004005h
0x18005bcb2  jmp     loc_18005BD46
0x18005bcb7  add     rdx, 358h; lpBaseAddress
0x18005bcbe  mov     [rsp+68h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18005bcc7  mov     r9d, 8; nSize
0x18005bccd  mov     r8, rdi; lpBuffer
0x18005bcd0  mov     rcx, rbx; hProcess
0x18005bcd3  call    cs:__imp_ReadProcessMemory
0x18005bcd9  test    eax, eax
0x18005bcdb  jnz     short loc_18005BD18
0x18005bcdd  mov     r9, gs:40h
0x18005bce6  lea     r8, aWerCrashapiUUE_26; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x18005bced  xor     edx, edx; Level
0x18005bcef  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C36h
0x18005bcf7  mov     ecx, 96h; ComponentId
0x18005bcfc  call    cs:__imp_DbgPrintEx
0x18005bd02  mov     eax, gs:68h
0x18005bd0a  test    eax, eax
0x18005bd0c  jle     short loc_18005BD46
0x18005bd0e  movzx   eax, ax
0x18005bd11  or      eax, 80070000h
0x18005bd16  jmp     short loc_18005BD46
0x18005bd18  xor     eax, eax
0x18005bd1a  jmp     short loc_18005BD46
0x18005bd1c  mov     r9, gs:40h
0x18005bd25  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x18005bd2c  xor     edx, edx; Level
0x18005bd2e  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C1Ah
0x18005bd36  mov     ecx, 96h; ComponentId
0x18005bd3b  call    cs:__imp_DbgPrintEx
0x18005bd41  mov     eax, 80070057h
0x18005bd46  mov     rbx, [rsp+68h+arg_0]
0x18005bd4b  add     rsp, 60h
0x18005bd4f  pop     rdi
0x18005bd50  retn
```
