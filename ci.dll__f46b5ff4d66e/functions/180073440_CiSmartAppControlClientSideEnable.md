# CiSmartAppControlClientSideEnable

- ea: `0x180073440`
- end: `0x18007353a`
- name: `CiSmartAppControlClientSideEnable`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007281c`

## callees

- `0x18001d350`
- `0x180059ed0`
- `0x180072720`
- `0x180073440`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180073468`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x180073468`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800734e9`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800734e9`

## string_xrefs

- `0x1800734a5`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`
- `0x1800734db`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x180073440  mov     [rsp-8+arg_18], rdi
0x180073445  push    rbp
0x180073446  mov     rbp, rsp
0x180073449  sub     rsp, 40h
0x18007344d  lea     rcx, [rbp+arg_10]
0x180073451  mov     [rbp+arg_0], 0
0x180073458  mov     [rbp+arg_10], 0
0x180073460  mov     [rbp+arg_8], 0
0x180073468  call    cs:__imp_KeQuerySystemTimePrecise
0x18007346f  nop     dword ptr [rax+rax+00h]
0x180073474  lea     rcx, [rbp+arg_8]
0x180073478  call    CiGetOOBECompleteTime
0x18007347d  mov     edi, 1
0x180073482  test    eax, eax
0x180073484  jns     short loc_1800734F9
0x180073486  lea     rax, [rbp+arg_0]
0x18007348a  mov     r9d, edi
0x18007348d  mov     [rsp+40h+var_10], rax
0x180073492  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x180073499  lea     rax, [rbp+arg_8]
0x18007349d  mov     [rsp+40h+ValueLength], 8
0x1800734a5  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800734ac  mov     [rsp+40h+ValueData], rax
0x1800734b1  xor     ecx, ecx
0x1800734b3  call    CipGetRegistryValue
0x1800734b8  test    eax, eax
0x1800734ba  jns     short loc_1800734F9
0x1800734bc  mov     rax, [rbp+arg_10]
0x1800734c0  lea     r9d, [rdi+2]; ValueType
0x1800734c4  mov     [rbp+arg_8], rax
0x1800734c8  lea     r8, aOobesafetytime; "OOBESafetyTimer"
0x1800734cf  lea     rax, [rbp+arg_8]
0x1800734d3  mov     [rsp+40h+ValueLength], 8; ValueLength
0x1800734db  lea     rdx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800734e2  mov     [rsp+40h+ValueData], rax; ValueData
0x1800734e7  xor     ecx, ecx; RelativeTo
0x1800734e9  call    cs:__imp_RtlWriteRegistryValue
0x1800734f0  nop     dword ptr [rax+rax+00h]
0x1800734f5  test    eax, eax
0x1800734f7  js      short loc_18007352C
0x1800734f9  mov     rcx, [rbp+arg_10]
0x1800734fd  cmp     rcx, [rbp+arg_8]
0x180073501  jle     short loc_18007352C
0x180073503  sub     rcx, [rbp+arg_8]
0x180073507  mov     rdx, 0C92A69C000h
0x180073511  cmp     rcx, rdx
0x180073514  jle     short loc_18007352C
0x180073516  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x18007351b  test    eax, eax
0x18007351d  jnz     short loc_180073527
0x18007351f  lock cmpxchg cs:g_SmartAppControlEnforcementReason, edi
0x180073527  mov     al, dil
0x18007352a  jmp     short loc_18007352E
0x18007352c  xor     al, al
0x18007352e  mov     rdi, [rsp+40h+arg_18]
0x180073533  add     rsp, 40h
0x180073537  pop     rbp
0x180073538  retn
```
