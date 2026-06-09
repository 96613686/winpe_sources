# _LookupNtdllProcedureAddress

- ea: `0x18007cce4`
- end: `0x18007cd84`
- name: `_LookupNtdllProcedureAddress`
- size: `160`
- prototype: `__int64 __fastcall(PCSZ SourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800045b0`
- `0x18007d328`
- `0x18007d3e4`
- `0x18007d474`

## callees

- `0x18007cce4`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x18007cd5f`
- `ntdll!LdrGetProcedureAddress` at `0x18007cd5f`
- `ntdll!RtlInitAnsiString` at `0x18007cd4a`
- `ntdll!RtlInitAnsiString` at `0x18007cd4a`
- `ntdll!LdrGetDllHandle` at `0x18007cd37`
- `ntdll!LdrGetDllHandle` at `0x18007cd37`
- `ntdll!RtlInitUnicodeString` at `0x18007cd25`
- `ntdll!RtlInitUnicodeString` at `0x18007cd25`

## string_xrefs

- `0x18007cd0f`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall LookupNtdllProcedureAddress(PCSZ SourceString, PVOID *a2)
{
  NTSTATUS v4; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-20h] BYREF
  _STRING Name; // [rsp+30h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+60h] [rbp+20h] BYREF
  PVOID ProcedureAddress; // [rsp+68h] [rbp+28h] BYREF

  ProcedureAddress = 0;
  DllHandle = 0;
  DestinationString = 0;
  Name = 0;
  RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
  v4 = LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
  if ( v4 >= 0 )
  {
    RtlInitAnsiString(&Name, SourceString);
    v4 = LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress);
    if ( v4 >= 0 )
      *a2 = ProcedureAddress;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007cce4  mov     [rsp-8+arg_0], rbx
0x18007cce9  mov     [rsp-8+arg_8], rdi
0x18007ccee  push    rbp
0x18007ccef  mov     rbp, rsp
0x18007ccf2  sub     rsp, 40h
0x18007ccf6  mov     rbx, rdx
0x18007ccf9  mov     [rbp+ProcedureAddress], 0
0x18007cd01  mov     rdi, rcx
0x18007cd04  mov     [rbp+DllHandle], 0
0x18007cd0c  xorps   xmm0, xmm0
0x18007cd0f  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x18007cd16  xorps   xmm1, xmm1
0x18007cd19  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007cd1d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007cd21  movups  xmmword ptr [rbp+Name.Length], xmm1
0x18007cd25  call    cs:__imp_RtlInitUnicodeString
0x18007cd2b  lea     r9, [rbp+DllHandle]; DllHandle
0x18007cd2f  xor     edx, edx; DllCharacteristics
0x18007cd31  lea     r8, [rbp+DestinationString]; DllName
0x18007cd35  xor     ecx, ecx; DllPath
0x18007cd37  call    cs:__imp_LdrGetDllHandle
0x18007cd3d  mov     ecx, eax
0x18007cd3f  test    eax, eax
0x18007cd41  js      short loc_18007CD72
0x18007cd43  mov     rdx, rdi; SourceString
0x18007cd46  lea     rcx, [rbp+Name]; DestinationString
0x18007cd4a  call    cs:__imp_RtlInitAnsiString
0x18007cd50  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18007cd54  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18007cd58  xor     r8d, r8d; Ordinal
0x18007cd5b  lea     rdx, [rbp+Name]; Name
0x18007cd5f  call    cs:__imp_LdrGetProcedureAddress
0x18007cd65  mov     ecx, eax
0x18007cd67  test    eax, eax
0x18007cd69  js      short loc_18007CD72
0x18007cd6b  mov     rax, [rbp+ProcedureAddress]
0x18007cd6f  mov     [rbx], rax
0x18007cd72  mov     rbx, [rsp+40h+arg_0]
0x18007cd77  mov     eax, ecx
0x18007cd79  mov     rdi, [rsp+40h+arg_8]
0x18007cd7e  add     rsp, 40h
0x18007cd82  pop     rbp
0x18007cd83  retn
```
