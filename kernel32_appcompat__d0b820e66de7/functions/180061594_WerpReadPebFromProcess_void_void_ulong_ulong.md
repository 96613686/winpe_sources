# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x180061594`
- end: `0x18006170a`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `374`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *lpBuffer, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180058d5c`

## callees

- `0x180061594`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18006160a`
- `ntdll!DbgPrintEx` at `0x180061647`
- `ntdll!DbgPrintEx` at `0x1800616a8`
- `ntdll!DbgPrintEx` at `0x1800616ed`
- `ntdll!DbgPrintEx` at `0x18006160a`
- `ntdll!DbgPrintEx` at `0x180061647`
- `ntdll!DbgPrintEx` at `0x1800616a8`
- `ntdll!DbgPrintEx` at `0x1800616ed`
- `ntdll!NtQueryInformationProcess` at `0x1800615db`
- `ntdll!NtQueryInformationProcess` at `0x1800615db`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180061679`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180061679`

## string_xrefs

- `0x180061692`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

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
0x180061594  mov     rax, rsp
0x180061597  mov     [rax+8], rbx
0x18006159b  push    rdi
0x18006159c  sub     rsp, 60h
0x1800615a0  xorps   xmm0, xmm0
0x1800615a3  mov     rdi, rdx
0x1800615a6  mov     rbx, rcx
0x1800615a9  movups  xmmword ptr [rax-38h], xmm0
0x1800615ad  movups  xmmword ptr [rax-28h], xmm0
0x1800615b1  movups  xmmword ptr [rax-18h], xmm0
0x1800615b5  test    rcx, rcx
0x1800615b8  jz      loc_1800616CE
0x1800615be  test    rdx, rdx
0x1800615c1  jz      loc_1800616CE
0x1800615c7  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800615cd  mov     qword ptr [rax-48h], 0
0x1800615d5  lea     r8, [rax-38h]; ProcessInformation
0x1800615d9  xor     edx, edx; ProcessInformationClass
0x1800615db  call    cs:__imp_NtQueryInformationProcess
0x1800615e2  nop     dword ptr [rax+rax+00h]
0x1800615e7  test    eax, eax
0x1800615e9  jns     short loc_180061620
0x1800615eb  mov     r9, gs:40h
0x1800615f4  lea     r8, aWerCrashapiUUE_29; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x1800615fb  xor     edx, edx; Level
0x1800615fd  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C24h
0x180061605  mov     ecx, 96h; ComponentId
0x18006160a  call    cs:__imp_DbgPrintEx
0x180061611  nop     dword ptr [rax+rax+00h]
0x180061616  mov     eax, 80070006h
0x18006161b  jmp     loc_1800616FE
0x180061620  mov     rdx, qword ptr [rsp+68h+Level]; Level
0x180061625  test    rdx, rdx
0x180061628  jnz     short loc_18006165D
0x18006162a  mov     r9, gs:40h
0x180061633  lea     r8, aWerCrashapiUUE_50; "WER/CrashAPI/%u:%u: ERROR No PEB for pr"...
0x18006163a  mov     ecx, 96h; ComponentId
0x18006163f  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C2Ch
0x180061647  call    cs:__imp_DbgPrintEx
0x18006164e  nop     dword ptr [rax+rax+00h]
0x180061653  mov     eax, 80004005h
0x180061658  jmp     loc_1800616FE
0x18006165d  add     rdx, 358h; lpBaseAddress
0x180061664  mov     [rsp+68h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18006166d  mov     r9d, 8; nSize
0x180061673  mov     r8, rdi; lpBuffer
0x180061676  mov     rcx, rbx; hProcess
0x180061679  call    cs:__imp_ReadProcessMemory
0x180061680  nop     dword ptr [rax+rax+00h]
0x180061685  test    eax, eax
0x180061687  jnz     short loc_1800616CA
0x180061689  mov     r9, gs:40h
0x180061692  lea     r8, aWerCrashapiUUE_26; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x180061699  xor     edx, edx; Level
0x18006169b  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C36h
0x1800616a3  mov     ecx, 96h; ComponentId
0x1800616a8  call    cs:__imp_DbgPrintEx
0x1800616af  nop     dword ptr [rax+rax+00h]
0x1800616b4  mov     eax, gs:68h
0x1800616bc  test    eax, eax
0x1800616be  jle     short loc_1800616FE
0x1800616c0  movzx   eax, ax
0x1800616c3  or      eax, 80070000h
0x1800616c8  jmp     short loc_1800616FE
0x1800616ca  xor     eax, eax
0x1800616cc  jmp     short loc_1800616FE
0x1800616ce  mov     r9, gs:40h
0x1800616d7  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x1800616de  xor     edx, edx; Level
0x1800616e0  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C1Ah
0x1800616e8  mov     ecx, 96h; ComponentId
0x1800616ed  call    cs:__imp_DbgPrintEx
0x1800616f4  nop     dword ptr [rax+rax+00h]
0x1800616f9  mov     eax, 80070057h
0x1800616fe  mov     rbx, [rsp+68h+arg_0]
0x180061703  add     rsp, 60h
0x180061707  pop     rdi
0x180061708  retn
```
