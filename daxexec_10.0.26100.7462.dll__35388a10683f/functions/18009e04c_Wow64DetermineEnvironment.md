# Wow64DetermineEnvironment

- ea: `0x18009e04c`
- end: `0x18009e1e2`
- name: `Wow64DetermineEnvironment`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18009dfd4`

## callees

- `0x18009e04c`
- `0x1800cc010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18009e08c`
- `ntdll!RtlInitUnicodeString` at `0x18009e08c`
- `ntdll!LdrGetProcedureAddress` at `0x18009e0d6`
- `ntdll!LdrGetProcedureAddress` at `0x18009e189`
- `ntdll!LdrGetProcedureAddress` at `0x18009e0d6`
- `ntdll!LdrGetProcedureAddress` at `0x18009e189`
- `ntdll!LdrGetDllHandle` at `0x18009e0a4`
- `ntdll!LdrGetDllHandle` at `0x18009e0a4`
- `ntdll!RtlInitString` at `0x18009e0bb`
- `ntdll!RtlInitString` at `0x18009e16e`
- `ntdll!RtlInitString` at `0x18009e0bb`
- `ntdll!RtlInitString` at `0x18009e16e`

## string_xrefs

- `0x18009e081`: `ntdll.dll`

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

  DllHandle = 0;
  ProcedureAddress = 0;
  v8 = 0;
  v6 = 0;
  DestinationString = 0;
  Name = 0;
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
0x18009e04c  push    rbp
0x18009e04e  push    rdi
0x18009e04f  mov     rbp, rsp
0x18009e052  sub     rsp, 48h
0x18009e056  and     [rbp+DllHandle], 0
0x18009e05b  xorps   xmm0, xmm0
0x18009e05e  and     [rbp+ProcedureAddress], 0
0x18009e063  and     [rbp+arg_10], 0
0x18009e068  cmp     cs:CachedWow64ProcessEnvironment, 0
0x18009e06f  mov     [rbp+arg_0], 0
0x18009e073  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18009e077  movups  xmmword ptr [rbp+Name.Length], xmm0
0x18009e07b  jnz     loc_18009E1DA
0x18009e081  lea     rdx, ModuleName; "ntdll.dll"
0x18009e088  lea     rcx, [rbp+DestinationString]; DestinationString
0x18009e08c  call    cs:__imp_RtlInitUnicodeString
0x18009e093  nop     dword ptr [rax+rax+00h]
0x18009e098  lea     r9, [rbp+DllHandle]; DllHandle
0x18009e09c  xor     edx, edx; DllCharacteristics
0x18009e09e  lea     r8, [rbp+DestinationString]; DllName
0x18009e0a2  xor     ecx, ecx; DllPath
0x18009e0a4  call    cs:__imp_LdrGetDllHandle
0x18009e0ab  nop     dword ptr [rax+rax+00h]
0x18009e0b0  lea     rdx, aRtlwow64getcur; "RtlWow64GetCurrentMachine"
0x18009e0b7  lea     rcx, [rbp+Name]; DestinationString
0x18009e0bb  call    cs:__imp_RtlInitString
0x18009e0c2  nop     dword ptr [rax+rax+00h]
0x18009e0c7  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18009e0cb  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18009e0cf  xor     r8d, r8d; Ordinal
0x18009e0d2  lea     rdx, [rbp+Name]; Name
0x18009e0d6  call    cs:__imp_LdrGetProcedureAddress
0x18009e0dd  nop     dword ptr [rax+rax+00h]
0x18009e0e2  test    eax, eax
0x18009e0e4  jns     short loc_18009E0F5
0x18009e0e6  mov     cs:CachedWow64ProcessEnvironment, 1
0x18009e0f0  jmp     loc_18009E1DA
0x18009e0f5  mov     rax, gs:30h
0x18009e0fe  cmp     dword ptr [rax+180Ch], 0
0x18009e105  jnz     short loc_18009E113
0x18009e107  mov     cs:CachedWow64ProcessEnvironment, 2
0x18009e111  jmp     short loc_18009E163
0x18009e113  mov     rax, gs:30h
0x18009e11c  cmp     dword ptr [rax+180Ch], 0
0x18009e123  jge     short loc_18009E140
0x18009e125  mov     eax, 8664h
0x18009e12a  mov     cs:CachedWow64ProcessEnvironment, 4
0x18009e134  mov     cs:CachedMachine, ax
0x18009e13b  jmp     loc_18009E1DA
0x18009e140  mov     rax, [rbp+ProcedureAddress]
0x18009e144  mov     cs:CachedWow64ProcessEnvironment, 3
0x18009e14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e153  cmp     cs:CachedWow64ProcessEnvironment, 2
0x18009e15a  mov     cs:CachedMachine, ax
0x18009e161  jnz     short loc_18009E1DA
0x18009e163  lea     rdx, aRtlwow64iswowg; "RtlWow64IsWowGuestMachineSupported"
0x18009e16a  lea     rcx, [rbp+Name]; DestinationString
0x18009e16e  call    cs:__imp_RtlInitString
0x18009e175  nop     dword ptr [rax+rax+00h]
0x18009e17a  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18009e17e  lea     r9, [rbp+arg_10]; ProcedureAddress
0x18009e182  xor     r8d, r8d; Ordinal
0x18009e185  lea     rdx, [rbp+Name]; Name
0x18009e189  call    cs:__imp_LdrGetProcedureAddress
0x18009e190  nop     dword ptr [rax+rax+00h]
0x18009e195  test    eax, eax
0x18009e197  js      short loc_18009E1DA
0x18009e199  mov     rax, [rbp+arg_10]
0x18009e19d  lea     rdx, [rbp+arg_0]
0x18009e1a1  mov     ecx, 14Ch
0x18009e1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e1ab  test    eax, eax
0x18009e1ad  js      short loc_18009E1DA
0x18009e1af  cmp     [rbp+arg_0], 0
0x18009e1b3  jnz     short loc_18009E1DA
0x18009e1b5  mov     rax, [rbp+arg_10]
0x18009e1b9  lea     rdx, [rbp+arg_0]
0x18009e1bd  mov     edi, 1C4h
0x18009e1c2  mov     ecx, edi
0x18009e1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e1c9  test    eax, eax
0x18009e1cb  js      short loc_18009E1DA
0x18009e1cd  cmp     [rbp+arg_0], 0
0x18009e1d1  jz      short loc_18009E1DA
0x18009e1d3  mov     cs:DefaultGuestMachine, di
0x18009e1da  add     rsp, 48h
0x18009e1de  pop     rdi
0x18009e1df  pop     rbp
0x18009e1e0  retn
```
