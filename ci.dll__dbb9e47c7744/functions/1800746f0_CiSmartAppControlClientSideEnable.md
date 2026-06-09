# CiSmartAppControlClientSideEnable

- ea: `0x1800746f0`
- end: `0x1800747ea`
- name: `CiSmartAppControlClientSideEnable`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180073acc`

## callees

- `0x18001d2e8`
- `0x18005abe8`
- `0x1800739d0`
- `0x1800746f0`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180074718`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180074718`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074799`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180074799`

## string_xrefs

- `0x180074755`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x18007478b`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x1800746f0  mov     [rsp-8+arg_18], rdi
0x1800746f5  push    rbp
0x1800746f6  mov     rbp, rsp
0x1800746f9  sub     rsp, 40h
0x1800746fd  lea     rcx, [rbp+arg_10]
0x180074701  mov     [rbp+arg_0], 0
0x180074708  mov     [rbp+arg_10], 0
0x180074710  mov     [rbp+arg_8], 0
0x180074718  call    cs:__imp_KeQuerySystemTimePrecise
0x18007471f  nop     dword ptr [rax+rax+00h]
0x180074724  lea     rcx, [rbp+arg_8]
0x180074728  call    CiGetOOBECompleteTime
0x18007472d  mov     edi, 1
0x180074732  test    eax, eax
0x180074734  jns     short loc_1800747A9
0x180074736  lea     rax, [rbp+arg_0]
0x18007473a  mov     r9d, edi
0x18007473d  mov     [rsp+40h+var_10], rax
0x180074742  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180074749  lea     rax, [rbp+arg_8]
0x18007474d  mov     [rsp+40h+ValueLength], 8
0x180074755  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18007475c  mov     [rsp+40h+ValueData], rax
0x180074761  xor     ecx, ecx
0x180074763  call    CipGetRegistryValue
0x180074768  test    eax, eax
0x18007476a  jns     short loc_1800747A9
0x18007476c  mov     rax, [rbp+arg_10]
0x180074770  lea     r9d, [rdi+2]; ValueType
0x180074774  mov     [rbp+arg_8], rax
0x180074778  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x18007477f  lea     rax, [rbp+arg_8]
0x180074783  mov     [rsp+40h+ValueLength], 8; ValueLength
0x18007478b  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074792  mov     [rsp+40h+ValueData], rax; ValueData
0x180074797  xor     ecx, ecx; RelativeTo
0x180074799  call    cs:__imp_RtlWriteRegistryValue
0x1800747a0  nop     dword ptr [rax+rax+00h]
0x1800747a5  test    eax, eax
0x1800747a7  js      short loc_1800747DC
0x1800747a9  mov     rcx, [rbp+arg_10]
0x1800747ad  cmp     rcx, [rbp+arg_8]
0x1800747b1  jle     short loc_1800747DC
0x1800747b3  sub     rcx, [rbp+arg_8]
0x1800747b7  mov     rdx, 0C92A69C000h
0x1800747c1  cmp     rcx, rdx
0x1800747c4  jle     short loc_1800747DC
0x1800747c6  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x1800747cb  test    eax, eax
0x1800747cd  jnz     short loc_1800747D7
0x1800747cf  lock cmpxchg cs:g_SmartAppControlEnforcementReason, edi
0x1800747d7  mov     al, dil
0x1800747da  jmp     short loc_1800747DE
0x1800747dc  xor     al, al
0x1800747de  mov     rdi, [rsp+40h+arg_18]
0x1800747e3  add     rsp, 40h
0x1800747e7  pop     rbp
0x1800747e8  retn
```
