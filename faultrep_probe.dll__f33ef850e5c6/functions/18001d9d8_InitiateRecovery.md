# InitiateRecovery

- ea: `0x18001d9d8`
- end: `0x18001db24`
- name: `InitiateRecovery`
- size: `332`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001db2c`

## callees

- `0x1800035ff`
- `0x18000360b`
- `0x180003617`
- `0x18001d9d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x18001daff`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThread` at `0x18001daff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da68`
- `ntdll!DbgPrintEx` at `0x18001da10`
- `ntdll!DbgPrintEx` at `0x18001da92`
- `ntdll!DbgPrintEx` at `0x18001dacc`
- `ntdll!DbgPrintEx` at `0x18001da10`
- `ntdll!DbgPrintEx` at `0x18001da92`
- `ntdll!DbgPrintEx` at `0x18001dacc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001da28`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001da28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db16`

## string_xrefs

- `0x18001da57`: `kernel32.dll`

## pseudocode

```c
signed int __fastcall InitiateRecovery(HANDLE hProcess, __int64 a2, void *a3)
{
  DWORD CurrentProcessId_0; // eax
  signed int result; // eax
  HMODULE ModuleHandleW_0; // rax
  DWORD LastError; // ebx
  DWORD v8; // eax
  ULONG (__stdcall *WerpInitiateRemoteRecovery)(PVOID); // rax
  DWORD v10; // eax
  HANDLE v11; // rax
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+5Ch] [rbp+14h]

  v13 = HIDWORD(a2);
  ThreadId = 0;
  if ( !hProcess )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR Invalid process handle passed\n", CurrentProcessId_0, 189);
    return -2147024809;
  }
  if ( !a3 )
  {
    ModuleHandleW_0 = GetModuleHandleW_0(L"kernel32.dll");
    if ( ModuleHandleW_0 )
    {
      WerpInitiateRemoteRecovery = (ULONG (__stdcall *)(PVOID))GetProcAddress_0(
                                                                 ModuleHandleW_0,
                                                                 "WerpInitiateRemoteRecovery");
      if ( WerpInitiateRemoteRecovery )
      {
        v11 = CreateRemoteThread(hProcess, 0, 0, WerpInitiateRemoteRecovery, 0, 0, &ThreadId);
        if ( (unsigned __int64)v11 + 1 <= 1 )
          goto LABEL_5;
        CloseHandle(v11);
        return 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashAPI/%u:%u: ERROR GetModuleHandle failed for kernel32 with %u\n",
        v8,
        4052,
        LastError);
    }
    v10 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/Recovery/%u:%u: ERROR WerpGetRecoveryEntryPointInProcess returned NULL\n", v10, 219);
    return -805306055;
  }
  if ( SetEvent(a3) )
    return 0;
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x18001d9d8  mov     qword ptr [rsp+ThreadId], rdx
0x18001d9dd  push    rbx
0x18001d9de  sub     rsp, 40h
0x18001d9e2  mov     [rsp+48h+ThreadId], 0
0x18001d9ea  mov     rbx, rcx
0x18001d9ed  test    rcx, rcx
0x18001d9f0  jnz     short loc_18001DA20
0x18001d9f2  call    GetCurrentProcessId_0
0x18001d9f7  mov     r9d, eax
0x18001d9fa  mov     dword ptr [rsp+48h+lpParameter], 0BDh
0x18001da02  lea     r8, aWerRecoveryUUE_0; "WER/Recovery/%u:%u: ERROR Invalid proce"...
0x18001da09  xor     edx, edx; Level
0x18001da0b  mov     ecx, 96h; ComponentId
0x18001da10  call    cs:__imp_DbgPrintEx
0x18001da16  mov     eax, 80070057h
0x18001da1b  jmp     loc_18001DB1E
0x18001da20  test    r8, r8
0x18001da23  jz      short loc_18001DA57
0x18001da25  mov     rcx, r8; hEvent
0x18001da28  call    cs:__imp_SetEvent
0x18001da2e  test    eax, eax
0x18001da30  jnz     loc_18001DB1C
0x18001da36  call    cs:__imp_GetLastError
0x18001da3c  test    eax, eax
0x18001da3e  jle     short loc_18001DA48
0x18001da40  movzx   eax, ax
0x18001da43  or      eax, 80070000h
0x18001da48  test    eax, eax
0x18001da4a  mov     ecx, 80004005h
0x18001da4f  cmovns  eax, ecx
0x18001da52  jmp     loc_18001DB1E
0x18001da57  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18001da5e  call    GetModuleHandleW_0
0x18001da63  test    rax, rax
0x18001da66  jnz     short loc_18001DA9A
0x18001da68  call    cs:__imp_GetLastError
0x18001da6e  mov     ebx, eax
0x18001da70  call    GetCurrentProcessId_0
0x18001da75  mov     r9d, eax
0x18001da78  mov     [rsp+48h+dwCreationFlags], ebx
0x18001da7c  lea     r8, aWerCrashapiUUE_17; "WER/CrashAPI/%u:%u: ERROR GetModuleHand"...
0x18001da83  mov     dword ptr [rsp+48h+lpParameter], 0FD4h
0x18001da8b  xor     edx, edx; Level
0x18001da8d  mov     ecx, 96h; ComponentId
0x18001da92  call    cs:__imp_DbgPrintEx
0x18001da98  jmp     short loc_18001DAAE
0x18001da9a  lea     rdx, aWerpinitiatere; "WerpInitiateRemoteRecovery"
0x18001daa1  mov     rcx, rax; hModule
0x18001daa4  call    GetProcAddress_0
0x18001daa9  test    rax, rax
0x18001daac  jnz     short loc_18001DAD9
0x18001daae  call    GetCurrentProcessId_0
0x18001dab3  mov     r9d, eax
0x18001dab6  mov     dword ptr [rsp+48h+lpParameter], 0DBh
0x18001dabe  lea     r8, aWerRecoveryUUE_8; "WER/Recovery/%u:%u: ERROR WerpGetRecove"...
0x18001dac5  xor     edx, edx; Level
0x18001dac7  mov     ecx, 96h; ComponentId
0x18001dacc  call    cs:__imp_DbgPrintEx
0x18001dad2  mov     eax, 0D0000139h
0x18001dad7  jmp     short loc_18001DB1E
0x18001dad9  lea     rcx, [rsp+48h+ThreadId]
0x18001dade  mov     r9, rax; lpStartAddress
0x18001dae1  mov     [rsp+48h+lpThreadId], rcx; lpThreadId
0x18001dae6  xor     r8d, r8d; dwStackSize
0x18001dae9  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18001daf1  mov     rcx, rbx; hProcess
0x18001daf4  xor     edx, edx; lpThreadAttributes
0x18001daf6  mov     [rsp+48h+lpParameter], 0; lpParameter
0x18001daff  call    cs:__imp_CreateRemoteThread
0x18001db05  lea     rcx, [rax+1]
0x18001db09  cmp     rcx, 1
0x18001db0d  jbe     loc_18001DA36
0x18001db13  mov     rcx, rax; hObject
0x18001db16  call    cs:__imp_CloseHandle
0x18001db1c  xor     eax, eax
0x18001db1e  add     rsp, 40h
0x18001db22  pop     rbx
0x18001db23  retn
```
