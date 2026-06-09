# TraceLoggingSetInformation_2U

- ea: `0x140001aec`
- end: `0x140001baf`
- name: `TraceLoggingSetInformation_2U`
- size: `195`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001a48`

## callees

- `0x140001aec`
- `0x140002360`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140001b2c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140001b44`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140001b2c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140001b44`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140001b5a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140001b5a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x140001b80`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x140001b80`

## string_xrefs

- `0x140001b1d`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x140001b3d`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall TraceLoggingSetInformation_2U(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v7; // ebx
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF

  phModule = 0;
  v7 = 50;
  if ( !GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
    && !GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
  {
    return (unsigned __int16)v7 | 0x80070000;
  }
  ProcAddress = GetProcAddress(phModule, "EventSetInformation");
  if ( ProcAddress )
    v7 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 32), 2, a3, a4);
  FreeLibrary(phModule);
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140001aec  mov     [rsp+arg_8], rbx
0x140001af1  push    rbp
0x140001af2  push    rsi
0x140001af3  push    rdi
0x140001af4  sub     rsp, 40h
0x140001af8  mov     rax, cs:__security_cookie
0x140001aff  xor     rax, rsp
0x140001b02  mov     [rsp+58h+var_20], rax
0x140001b07  mov     rsi, r8
0x140001b0a  mov     [rsp+58h+phModule], 0
0x140001b13  mov     rdi, rcx
0x140001b16  lea     r8, [rsp+58h+phModule]; phModule
0x140001b1b  xor     ecx, ecx; dwFlags
0x140001b1d  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x140001b24  mov     ebp, r9d
0x140001b27  mov     ebx, 32h ; '2'
0x140001b2c  call    cs:__imp_GetModuleHandleExW
0x140001b32  test    eax, eax
0x140001b34  jnz     short loc_140001B4E
0x140001b36  lea     r8, [rsp+58h+phModule]; phModule
0x140001b3b  xor     ecx, ecx; dwFlags
0x140001b3d  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x140001b44  call    cs:__imp_GetModuleHandleExW
0x140001b4a  test    eax, eax
0x140001b4c  jz      short loc_140001B8A
0x140001b4e  mov     rcx, [rsp+58h+phModule]; hModule
0x140001b53  lea     rdx, ProcName; "EventSetInformation"
0x140001b5a  call    cs:__imp_GetProcAddress
0x140001b60  test    rax, rax
0x140001b63  jz      short loc_140001B7B
0x140001b65  mov     rcx, [rdi+20h]
0x140001b69  mov     r9d, ebp
0x140001b6c  mov     r8, rsi
0x140001b6f  mov     edx, 2
0x140001b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b79  mov     ebx, eax
0x140001b7b  mov     rcx, [rsp+58h+phModule]; hLibModule
0x140001b80  call    cs:__imp_FreeLibrary
0x140001b86  test    ebx, ebx
0x140001b88  jle     short loc_140001B93
0x140001b8a  movzx   ebx, bx
0x140001b8d  or      ebx, 80070000h
0x140001b93  mov     eax, ebx
0x140001b95  mov     rcx, [rsp+58h+var_20]
0x140001b9a  xor     rcx, rsp; StackCookie
0x140001b9d  call    __security_check_cookie
0x140001ba2  mov     rbx, [rsp+58h+arg_8]
0x140001ba7  add     rsp, 40h
0x140001bab  pop     rdi
0x140001bac  pop     rsi
0x140001bad  pop     rbp
0x140001bae  retn
```
