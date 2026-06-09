# CiSmartAppControlClientSideEnable

- ea: `0x1800749d0`
- end: `0x180074aca`
- name: `CiSmartAppControlClientSideEnable`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180073dac`

## callees

- `0x18001d3a0`
- `0x18005ab10`
- `0x180073cb0`
- `0x1800749d0`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800749f8`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1800749f8`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074a79`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074a79`

## string_xrefs

- `0x180074a35`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x180074a6b`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

## pseudocode

```c
char CiSmartAppControlClientSideEnable()
{
  int v1; // [rsp+50h] [rbp+10h] BYREF
  __int64 ValueData; // [rsp+58h] [rbp+18h] BYREF
  __int64 v3; // [rsp+60h] [rbp+20h] BYREF

  v1 = 0;
  v3 = 0;
  ValueData = 0;
  KeQuerySystemTimePrecise(&v3);
  if ( (int)CiGetOOBECompleteTime(&ValueData) < 0
    && (int)CipGetRegistryValue(
              0,
              L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
              (__int64)L"OOBESafetyTimer",
              1,
              (__int64)&ValueData,
              8,
              (__int64)&v1) < 0 )
  {
    ValueData = v3;
    if ( RtlWriteRegistryValue(
           0,
           L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
           L"OOBESafetyTimer",
           3u,
           &ValueData,
           8u) < 0 )
      return 0;
  }
  if ( v3 <= ValueData || v3 - ValueData <= 864000000000LL )
    return 0;
  if ( !(unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
    _InterlockedCompareExchange(&g_SmartAppControlEnforcementReason, 1, 0);
  return 1;
}

```

## disassembly

```asm
0x1800749d0  mov     [rsp-8+arg_18], rdi
0x1800749d5  push    rbp
0x1800749d6  mov     rbp, rsp
0x1800749d9  sub     rsp, 40h
0x1800749dd  lea     rcx, [rbp+arg_10]
0x1800749e1  mov     [rbp+arg_0], 0
0x1800749e8  mov     [rbp+arg_10], 0
0x1800749f0  mov     [rbp+arg_8], 0
0x1800749f8  call    cs:__imp_KeQuerySystemTimePrecise
0x1800749ff  nop     dword ptr [rax+rax+00h]
0x180074a04  lea     rcx, [rbp+arg_8]
0x180074a08  call    CiGetOOBECompleteTime
0x180074a0d  mov     edi, 1
0x180074a12  test    eax, eax
0x180074a14  jns     short loc_180074A89
0x180074a16  lea     rax, [rbp+arg_0]
0x180074a1a  mov     r9d, edi
0x180074a1d  mov     [rsp+40h+var_10], rax
0x180074a22  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180074a29  lea     rax, [rbp+arg_8]
0x180074a2d  mov     [rsp+40h+ValueLength], 8
0x180074a35  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074a3c  mov     [rsp+40h+ValueData], rax
0x180074a41  xor     ecx, ecx
0x180074a43  call    CipGetRegistryValue
0x180074a48  test    eax, eax
0x180074a4a  jns     short loc_180074A89
0x180074a4c  mov     rax, [rbp+arg_10]
0x180074a50  lea     r9d, [rdi+2]; ValueType
0x180074a54  mov     [rbp+arg_8], rax
0x180074a58  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180074a5f  lea     rax, [rbp+arg_8]
0x180074a63  mov     [rsp+40h+ValueLength], 8; ValueLength
0x180074a6b  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074a72  mov     [rsp+40h+ValueData], rax; ValueData
0x180074a77  xor     ecx, ecx; RelativeTo
0x180074a79  call    cs:__imp_RtlWriteRegistryValue
0x180074a80  nop     dword ptr [rax+rax+00h]
0x180074a85  test    eax, eax
0x180074a87  js      short loc_180074ABC
0x180074a89  mov     rcx, [rbp+arg_10]
0x180074a8d  cmp     rcx, [rbp+arg_8]
0x180074a91  jle     short loc_180074ABC
0x180074a93  sub     rcx, [rbp+arg_8]
0x180074a97  mov     rdx, 0C92A69C000h
0x180074aa1  cmp     rcx, rdx
0x180074aa4  jle     short loc_180074ABC
0x180074aa6  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180074aab  test    eax, eax
0x180074aad  jnz     short loc_180074AB7
0x180074aaf  lock cmpxchg cs:g_SmartAppControlEnforcementReason, edi
0x180074ab7  mov     al, dil
0x180074aba  jmp     short loc_180074ABE
0x180074abc  xor     al, al
0x180074abe  mov     rdi, [rsp+40h+arg_18]
0x180074ac3  add     rsp, 40h
0x180074ac7  pop     rbp
0x180074ac8  retn
```
