# Wow64DetermineEnvironment

- ea: `0x18001db60`
- end: `0x18001dcda`
- name: `Wow64DetermineEnvironment`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001dae8`

## callees

- `0x18001db60`
- `0x18001f010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001dba9`
- `ntdll!RtlInitUnicodeString` at `0x18001dba9`
- `ntdll!LdrGetProcedureAddress` at `0x18001dbe1`
- `ntdll!LdrGetProcedureAddress` at `0x18001dc88`
- `ntdll!LdrGetProcedureAddress` at `0x18001dbe1`
- `ntdll!LdrGetProcedureAddress` at `0x18001dc88`
- `ntdll!LdrGetDllHandle` at `0x18001dbbb`
- `ntdll!LdrGetDllHandle` at `0x18001dbbb`
- `ntdll!RtlInitString` at `0x18001dbcc`
- `ntdll!RtlInitString` at `0x18001dc73`
- `ntdll!RtlInitString` at `0x18001dbcc`
- `ntdll!RtlInitString` at `0x18001dc73`

## string_xrefs

- `0x18001db9e`: `ntdll.dll`

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
0x18001db60  push    rbp
0x18001db62  push    rdi
0x18001db63  mov     rbp, rsp
0x18001db66  sub     rsp, 48h
0x18001db6a  cmp     cs:CachedWow64ProcessEnvironment, 0
0x18001db71  xorps   xmm0, xmm0
0x18001db74  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001db78  mov     [rbp+arg_0], 0
0x18001db7c  movups  xmmword ptr [rbp+Name.Length], xmm0
0x18001db80  mov     [rbp+DllHandle], 0
0x18001db88  mov     [rbp+ProcedureAddress], 0
0x18001db90  mov     [rbp+arg_10], 0
0x18001db98  jnz     loc_18001DCD3
0x18001db9e  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001dba5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001dba9  call    cs:__imp_RtlInitUnicodeString
0x18001dbaf  lea     r9, [rbp+DllHandle]; DllHandle
0x18001dbb3  xor     edx, edx; DllCharacteristics
0x18001dbb5  lea     r8, [rbp+DestinationString]; DllName
0x18001dbb9  xor     ecx, ecx; DllPath
0x18001dbbb  call    cs:__imp_LdrGetDllHandle
0x18001dbc1  lea     rdx, aRtlwow64getcur; "RtlWow64GetCurrentMachine"
0x18001dbc8  lea     rcx, [rbp+Name]; DestinationString
0x18001dbcc  call    cs:__imp_RtlInitString
0x18001dbd2  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18001dbd6  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18001dbda  xor     r8d, r8d; Ordinal
0x18001dbdd  lea     rdx, [rbp+Name]; Name
0x18001dbe1  call    cs:__imp_LdrGetProcedureAddress
0x18001dbe7  test    eax, eax
0x18001dbe9  jns     short loc_18001DBFA
0x18001dbeb  mov     cs:CachedWow64ProcessEnvironment, 1
0x18001dbf5  jmp     loc_18001DCD3
0x18001dbfa  mov     rax, gs:30h
0x18001dc03  cmp     dword ptr [rax+180Ch], 0
0x18001dc0a  jnz     short loc_18001DC18
0x18001dc0c  mov     cs:CachedWow64ProcessEnvironment, 2
0x18001dc16  jmp     short loc_18001DC68
0x18001dc18  mov     rax, gs:30h
0x18001dc21  cmp     dword ptr [rax+180Ch], 0
0x18001dc28  jge     short loc_18001DC45
0x18001dc2a  mov     eax, 8664h
0x18001dc2f  mov     cs:CachedWow64ProcessEnvironment, 4
0x18001dc39  mov     cs:CachedMachine, ax
0x18001dc40  jmp     loc_18001DCD3
0x18001dc45  mov     rax, [rbp+ProcedureAddress]
0x18001dc49  mov     cs:CachedWow64ProcessEnvironment, 3
0x18001dc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc58  cmp     cs:CachedWow64ProcessEnvironment, 2
0x18001dc5f  mov     cs:CachedMachine, ax
0x18001dc66  jnz     short loc_18001DCD3
0x18001dc68  lea     rdx, aRtlwow64iswowg; "RtlWow64IsWowGuestMachineSupported"
0x18001dc6f  lea     rcx, [rbp+Name]; DestinationString
0x18001dc73  call    cs:__imp_RtlInitString
0x18001dc79  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18001dc7d  lea     r9, [rbp+arg_10]; ProcedureAddress
0x18001dc81  xor     r8d, r8d; Ordinal
0x18001dc84  lea     rdx, [rbp+Name]; Name
0x18001dc88  call    cs:__imp_LdrGetProcedureAddress
0x18001dc8e  test    eax, eax
0x18001dc90  js      short loc_18001DCD3
0x18001dc92  mov     rax, [rbp+arg_10]
0x18001dc96  lea     rdx, [rbp+arg_0]
0x18001dc9a  mov     ecx, 14Ch
0x18001dc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca4  test    eax, eax
0x18001dca6  js      short loc_18001DCD3
0x18001dca8  cmp     [rbp+arg_0], 0
0x18001dcac  jnz     short loc_18001DCD3
0x18001dcae  mov     rax, [rbp+arg_10]
0x18001dcb2  lea     rdx, [rbp+arg_0]
0x18001dcb6  mov     edi, 1C4h
0x18001dcbb  mov     ecx, edi
0x18001dcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcc2  test    eax, eax
0x18001dcc4  js      short loc_18001DCD3
0x18001dcc6  cmp     [rbp+arg_0], 0
0x18001dcca  jz      short loc_18001DCD3
0x18001dccc  mov     cs:DefaultGuestMachine, di
0x18001dcd3  add     rsp, 48h
0x18001dcd7  pop     rdi
0x18001dcd8  pop     rbp
0x18001dcd9  retn
```
