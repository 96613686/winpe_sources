# BiLookupNtdllProcedureAddress

- ea: `0x180034db0`
- end: `0x180034e69`
- name: `BiLookupNtdllProcedureAddress`
- size: `185`
- prototype: `__int64 __fastcall(PCSZ SourceString)`
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800334d4`
- `0x180033e80`
- `0x180035004`
- `0x180035684`
- `0x1800368f0`
- `0x18003699c`
- `0x180036b18`
- `0x180036d98`
- `0x180037abc`
- `0x180037b54`
- `0x180037c88`
- `0x180037dc4`
- `0x180037e68`

## callees

- `0x180034db0`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x180034e3d`
- `ntdll!LdrGetProcedureAddress` at `0x180034e3d`
- `ntdll!LdrGetDllHandle` at `0x180034e09`
- `ntdll!LdrGetDllHandle` at `0x180034e09`
- `ntdll!RtlInitAnsiString` at `0x180034e22`
- `ntdll!RtlInitAnsiString` at `0x180034e22`
- `ntdll!RtlInitUnicodeString` at `0x180034df1`
- `ntdll!RtlInitUnicodeString` at `0x180034df1`

## string_xrefs

- `0x180034ddb`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall BiLookupNtdllProcedureAddress(PCSZ SourceString, PVOID *a2)
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
0x180034db0  mov     [rsp-8+arg_0], rbx
0x180034db5  mov     [rsp-8+arg_8], rdi
0x180034dba  push    rbp
0x180034dbb  mov     rbp, rsp
0x180034dbe  sub     rsp, 40h
0x180034dc2  mov     rbx, rdx
0x180034dc5  mov     [rbp+ProcedureAddress], 0
0x180034dcd  mov     rdi, rcx
0x180034dd0  mov     [rbp+DllHandle], 0
0x180034dd8  xorps   xmm0, xmm0
0x180034ddb  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180034de2  xorps   xmm1, xmm1
0x180034de5  lea     rcx, [rbp+DestinationString]; DestinationString
0x180034de9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180034ded  movups  xmmword ptr [rbp+Name.Length], xmm1
0x180034df1  call    cs:__imp_RtlInitUnicodeString
0x180034df8  nop     dword ptr [rax+rax+00h]
0x180034dfd  lea     r9, [rbp+DllHandle]; DllHandle
0x180034e01  xor     edx, edx; DllCharacteristics
0x180034e03  lea     r8, [rbp+DestinationString]; DllName
0x180034e07  xor     ecx, ecx; DllPath
0x180034e09  call    cs:__imp_LdrGetDllHandle
0x180034e10  nop     dword ptr [rax+rax+00h]
0x180034e15  mov     ecx, eax
0x180034e17  test    eax, eax
0x180034e19  js      short loc_180034E56
0x180034e1b  mov     rdx, rdi; SourceString
0x180034e1e  lea     rcx, [rbp+Name]; DestinationString
0x180034e22  call    cs:__imp_RtlInitAnsiString
0x180034e29  nop     dword ptr [rax+rax+00h]
0x180034e2e  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180034e32  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x180034e36  xor     r8d, r8d; Ordinal
0x180034e39  lea     rdx, [rbp+Name]; Name
0x180034e3d  call    cs:__imp_LdrGetProcedureAddress
0x180034e44  nop     dword ptr [rax+rax+00h]
0x180034e49  mov     ecx, eax
0x180034e4b  test    eax, eax
0x180034e4d  js      short loc_180034E56
0x180034e4f  mov     rax, [rbp+ProcedureAddress]
0x180034e53  mov     [rbx], rax
0x180034e56  mov     rbx, [rsp+40h+arg_0]
0x180034e5b  mov     eax, ecx
0x180034e5d  mov     rdi, [rsp+40h+arg_8]
0x180034e62  add     rsp, 40h
0x180034e66  pop     rbp
0x180034e67  retn
```
