# BthGetPolicyRegistryLocation

- ea: `0x14001efd8`
- end: `0x14001f0e1`
- name: `BthGetPolicyRegistryLocation`
- size: `265`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140037080`

## callees

- `0x14001efd8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001f052`
- `ntoskrnl!ExAllocatePool2` at `0x14001f052`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f0c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f0c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f0af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f0af`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14001f01e`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14001f097`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14001f01e`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14001f097`

## string_xrefs

- `0x14001eff8`: `\Registry\Machine\System\CurrentControlSet\Policies\Hardware\Bluetooth`
- `0x14001f07a`: `\Registry\Machine\System\CurrentControlSet\Policies\Hardware\Bluetooth`

## pseudocode

```c
__int64 __fastcall BthGetPolicyRegistryLocation(PUNICODE_STRING DestinationString)
{
  __int64 result; // rax
  void *Pool2; // rbx
  int PersistedStateLocation; // edi
  unsigned int v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  result = RtlGetPersistedStateLocation(
             L"BluetoothPolicy",
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Hardware\\Bluetooth",
             0,
             0,
             0,
             &v5);
  if ( (int)result >= 0 )
    return 3221225473LL;
  if ( (_DWORD)result == -2147483643 )
  {
    Pool2 = (void *)ExAllocatePool2(64, v5, 1953329250);
    if ( Pool2 )
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"BluetoothPolicy",
                                 0,
                                 L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Hardware\\Bluetooth",
                                 0,
                                 Pool2,
                                 v5,
                                 &v5);
      if ( PersistedStateLocation < 0 )
        ExFreePoolWithTag(Pool2, 0);
      else
        RtlInitUnicodeString(DestinationString, (PCWSTR)Pool2);
      return (unsigned int)PersistedStateLocation;
    }
    else
    {
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001efd8  mov     r11, rsp
0x14001efdb  mov     [r11+8], rbx
0x14001efdf  mov     [r11+18h], rsi
0x14001efe3  push    rdi
0x14001efe4  sub     rsp, 40h
0x14001efe8  lea     rax, [r11+10h]
0x14001efec  mov     [rsp+48h+arg_8], 0
0x14001eff4  mov     [r11-18h], rax
0x14001eff8  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001efff  mov     rsi, rcx
0x14001f002  mov     [rsp+48h+var_20], 0
0x14001f00a  xor     r9d, r9d
0x14001f00d  mov     qword ptr [r11-28h], 0
0x14001f015  xor     edx, edx
0x14001f017  lea     rcx, aBluetoothpolic; "BluetoothPolicy"
0x14001f01e  call    cs:__imp_RtlGetPersistedStateLocation
0x14001f025  nop     dword ptr [rax+rax+00h]
0x14001f02a  test    eax, eax
0x14001f02c  js      short loc_14001F038
0x14001f02e  mov     eax, 0C0000001h
0x14001f033  jmp     loc_14001F0D0
0x14001f038  cmp     eax, 80000005h
0x14001f03d  jnz     loc_14001F0D0
0x14001f043  mov     edx, [rsp+48h+arg_8]
0x14001f047  mov     ecx, 40h ; '@'
0x14001f04c  mov     r8d, 746D7062h
0x14001f052  call    cs:__imp_ExAllocatePool2
0x14001f059  nop     dword ptr [rax+rax+00h]
0x14001f05e  mov     rbx, rax
0x14001f061  test    rax, rax
0x14001f064  jnz     short loc_14001F06D
0x14001f066  mov     eax, 0C000009Ah
0x14001f06b  jmp     short loc_14001F0D0
0x14001f06d  lea     rax, [rsp+48h+arg_8]
0x14001f072  xor     r9d, r9d
0x14001f075  mov     [rsp+48h+var_18], rax
0x14001f07a  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001f081  mov     eax, [rsp+48h+arg_8]
0x14001f085  lea     rcx, aBluetoothpolic; "BluetoothPolicy"
0x14001f08c  mov     [rsp+48h+var_20], eax
0x14001f090  xor     edx, edx
0x14001f092  mov     [rsp+48h+var_28], rbx
0x14001f097  call    cs:__imp_RtlGetPersistedStateLocation
0x14001f09e  nop     dword ptr [rax+rax+00h]
0x14001f0a3  mov     edi, eax
0x14001f0a5  test    eax, eax
0x14001f0a7  js      short loc_14001F0BD
0x14001f0a9  mov     rdx, rbx; SourceString
0x14001f0ac  mov     rcx, rsi; DestinationString
0x14001f0af  call    cs:__imp_RtlInitUnicodeString
0x14001f0b6  nop     dword ptr [rax+rax+00h]
0x14001f0bb  jmp     short loc_14001F0CE
0x14001f0bd  xor     edx, edx; Tag
0x14001f0bf  mov     rcx, rbx; P
0x14001f0c2  call    cs:__imp_ExFreePoolWithTag
0x14001f0c9  nop     dword ptr [rax+rax+00h]
0x14001f0ce  mov     eax, edi
0x14001f0d0  mov     rbx, [rsp+48h+arg_0]
0x14001f0d5  mov     rsi, [rsp+48h+arg_10]
0x14001f0da  add     rsp, 40h
0x14001f0de  pop     rdi
0x14001f0df  retn
```
