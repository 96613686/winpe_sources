# CsrpSetToShutdownPriority

- ea: `0x1800083b0`
- end: `0x180008411`
- name: `CsrpSetToShutdownPriority`
- size: `97`
- prototype: `int()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007060`

## callees

- `0x1800083b0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1800083d0`
- `ntdll!RtlAdjustPrivilege` at `0x1800083d0`
- `ntdll!NtSetInformationProcess` at `0x1800083ff`
- `ntdll!NtSetInformationProcess` at `0x1800083ff`

## pseudocode

```c
int CsrpSetToShutdownPriority()
{
  int result; // eax
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF
  int ProcessInformation; // [rsp+38h] [rbp+10h] BYREF

  OldValue = 0;
  ProcessInformation = 0;
  result = RtlAdjustPrivilege(0xEu, 1u, 0, &OldValue);
  if ( result >= 0 )
  {
    ProcessInformation = 15;
    return NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBasePriority, &ProcessInformation, 4u);
  }
  return result;
}

```

## disassembly

```asm
0x1800083b0  sub     rsp, 28h
0x1800083b4  lea     r9, [rsp+28h+OldValue]; OldValue
0x1800083b9  mov     [rsp+28h+OldValue], 0
0x1800083be  xor     r8d, r8d; ForThread
0x1800083c1  mov     [rsp+28h+ProcessInformation], 0
0x1800083c9  mov     dl, 1; NewValue
0x1800083cb  mov     ecx, 0Eh; Privilege
0x1800083d0  call    cs:__imp_RtlAdjustPrivilege
0x1800083d7  nop     dword ptr [rax+rax+00h]
0x1800083dc  test    eax, eax
0x1800083de  js      short loc_18000840B
0x1800083e0  mov     r9d, 4; ProcessInformationLength
0x1800083e6  mov     [rsp+28h+ProcessInformation], 0Fh
0x1800083ee  lea     r8, [rsp+28h+ProcessInformation]; ProcessInformation
0x1800083f3  mov     edx, 5; ProcessInformationClass
0x1800083f8  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800083ff  call    cs:__imp_NtSetInformationProcess
0x180008406  nop     dword ptr [rax+rax+00h]
0x18000840b  add     rsp, 28h
0x18000840f  retn
```
