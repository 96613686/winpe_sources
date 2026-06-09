# Wow64DetermineEnvironment

- ea: `0x18009f99c`
- end: `0x18009fb3b`
- name: `Wow64DetermineEnvironment`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18009f920`

## callees

- `0x18009f99c`
- `0x1800cd010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18009f9e5`
- `ntdll!RtlInitUnicodeString` at `0x18009f9e5`
- `ntdll!LdrGetProcedureAddress` at `0x18009fa2f`
- `ntdll!LdrGetProcedureAddress` at `0x18009fae2`
- `ntdll!LdrGetProcedureAddress` at `0x18009fa2f`
- `ntdll!LdrGetProcedureAddress` at `0x18009fae2`
- `ntdll!LdrGetDllHandle` at `0x18009f9fd`
- `ntdll!LdrGetDllHandle` at `0x18009f9fd`
- `ntdll!RtlInitString` at `0x18009fa14`
- `ntdll!RtlInitString` at `0x18009fac7`
- `ntdll!RtlInitString` at `0x18009fa14`
- `ntdll!RtlInitString` at `0x18009fac7`

## string_xrefs

- `0x18009f9da`: `ntdll.dll`

## pseudocode

```c
void Wow64DetermineEnvironment()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  _STRING Name; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  char v6; // [rsp+60h] [rbp+18h] BYREF
  PVOID DllHandle; // [rsp+68h] [rbp+20h] BYREF
  PVOID v8; // [rsp+70h] [rbp+28h] BYREF
  PVOID ProcedureAddress; // [rsp+78h] [rbp+30h] BYREF

  DestinationString = 0;
  v6 = 0;
  Name = 0;
  DllHandle = 0;
  ProcedureAddress = 0;
  v8 = 0;
  if ( CachedWow64ProcessEnvironment )
    return;
  RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
  LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
  RtlInitString(&Name, "RtlWow64GetCurrentMachine");
  if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) < 0 )
  {
    CachedWow64ProcessEnvironment = 1;
    return;
  }
  if ( !NtCurrentTeb()->SpareUlong0 )
  {
    CachedWow64ProcessEnvironment = 2;
LABEL_9:
    RtlInitString(&Name, "RtlWow64IsWowGuestMachineSupported");
    if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &v8) >= 0
      && ((int (__fastcall *)(__int64, char *))v8)(332, &v6) >= 0
      && !v6
      && ((int (__fastcall *)(__int64, char *))v8)(452, &v6) >= 0 )
    {
      if ( v6 )
        DefaultGuestMachine = 452;
    }
    return;
  }
  if ( (NtCurrentTeb()->SpareUlong0 & 0x80000000) != 0 )
  {
    CachedWow64ProcessEnvironment = 4;
    CachedMachine = -31132;
    return;
  }
  CachedWow64ProcessEnvironment = 3;
  CachedMachine = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))ProcedureAddress)(v1, v0, v2, v3);
  if ( CachedWow64ProcessEnvironment == 2 )
    goto LABEL_9;
}

```

## disassembly

```asm
0x18009f99c  push    rbp
0x18009f99e  push    rdi
0x18009f99f  mov     rbp, rsp
0x18009f9a2  sub     rsp, 48h
0x18009f9a6  cmp     cs:CachedWow64ProcessEnvironment, 0
0x18009f9ad  xorps   xmm0, xmm0
0x18009f9b0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18009f9b4  mov     [rbp+arg_0], 0
0x18009f9b8  movups  xmmword ptr [rbp+Name.Length], xmm0
0x18009f9bc  mov     [rbp+DllHandle], 0
0x18009f9c4  mov     [rbp+ProcedureAddress], 0
0x18009f9cc  mov     [rbp+arg_10], 0
0x18009f9d4  jnz     loc_18009FB33
0x18009f9da  lea     rdx, ModuleName; "ntdll.dll"
0x18009f9e1  lea     rcx, [rbp+DestinationString]; DestinationString
0x18009f9e5  call    cs:__imp_RtlInitUnicodeString
0x18009f9ec  nop     dword ptr [rax+rax+00h]
0x18009f9f1  lea     r9, [rbp+DllHandle]; DllHandle
0x18009f9f5  xor     edx, edx; DllCharacteristics
0x18009f9f7  lea     r8, [rbp+DestinationString]; DllName
0x18009f9fb  xor     ecx, ecx; DllPath
0x18009f9fd  call    cs:__imp_LdrGetDllHandle
0x18009fa04  nop     dword ptr [rax+rax+00h]
0x18009fa09  lea     rdx, aRtlwow64getcur; "RtlWow64GetCurrentMachine"
0x18009fa10  lea     rcx, [rbp+Name]; DestinationString
0x18009fa14  call    cs:__imp_RtlInitString
0x18009fa1b  nop     dword ptr [rax+rax+00h]
0x18009fa20  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18009fa24  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18009fa28  xor     r8d, r8d; Ordinal
0x18009fa2b  lea     rdx, [rbp+Name]; Name
0x18009fa2f  call    cs:__imp_LdrGetProcedureAddress
0x18009fa36  nop     dword ptr [rax+rax+00h]
0x18009fa3b  test    eax, eax
0x18009fa3d  jns     short loc_18009FA4E
0x18009fa3f  mov     cs:CachedWow64ProcessEnvironment, 1
0x18009fa49  jmp     loc_18009FB33
0x18009fa4e  mov     rax, gs:30h
0x18009fa57  cmp     dword ptr [rax+180Ch], 0
0x18009fa5e  jnz     short loc_18009FA6C
0x18009fa60  mov     cs:CachedWow64ProcessEnvironment, 2
0x18009fa6a  jmp     short loc_18009FABC
0x18009fa6c  mov     rax, gs:30h
0x18009fa75  cmp     dword ptr [rax+180Ch], 0
0x18009fa7c  jge     short loc_18009FA99
0x18009fa7e  mov     eax, 8664h
0x18009fa83  mov     cs:CachedWow64ProcessEnvironment, 4
0x18009fa8d  mov     cs:CachedMachine, ax
0x18009fa94  jmp     loc_18009FB33
0x18009fa99  mov     rax, [rbp+ProcedureAddress]
0x18009fa9d  mov     cs:CachedWow64ProcessEnvironment, 3
0x18009faa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009faac  cmp     cs:CachedWow64ProcessEnvironment, 2
0x18009fab3  mov     cs:CachedMachine, ax
0x18009faba  jnz     short loc_18009FB33
0x18009fabc  lea     rdx, aRtlwow64iswowg; "RtlWow64IsWowGuestMachineSupported"
0x18009fac3  lea     rcx, [rbp+Name]; DestinationString
0x18009fac7  call    cs:__imp_RtlInitString
0x18009face  nop     dword ptr [rax+rax+00h]
0x18009fad3  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18009fad7  lea     r9, [rbp+arg_10]; ProcedureAddress
0x18009fadb  xor     r8d, r8d; Ordinal
0x18009fade  lea     rdx, [rbp+Name]; Name
0x18009fae2  call    cs:__imp_LdrGetProcedureAddress
0x18009fae9  nop     dword ptr [rax+rax+00h]
0x18009faee  test    eax, eax
0x18009faf0  js      short loc_18009FB33
0x18009faf2  mov     rax, [rbp+arg_10]
0x18009faf6  lea     rdx, [rbp+arg_0]
0x18009fafa  mov     ecx, 14Ch
0x18009faff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fb04  test    eax, eax
0x18009fb06  js      short loc_18009FB33
0x18009fb08  cmp     [rbp+arg_0], 0
0x18009fb0c  jnz     short loc_18009FB33
0x18009fb0e  mov     rax, [rbp+arg_10]
0x18009fb12  lea     rdx, [rbp+arg_0]
0x18009fb16  mov     edi, 1C4h
0x18009fb1b  mov     ecx, edi
0x18009fb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fb22  test    eax, eax
0x18009fb24  js      short loc_18009FB33
0x18009fb26  cmp     [rbp+arg_0], 0
0x18009fb2a  jz      short loc_18009FB33
0x18009fb2c  mov     cs:DefaultGuestMachine, di
0x18009fb33  add     rsp, 48h
0x18009fb37  pop     rdi
0x18009fb38  pop     rbp
0x18009fb39  retn
```
