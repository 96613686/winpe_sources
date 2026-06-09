# KiInitializeNormalPriorityAntiStarvationPolicies

- ea: `0x1405efb90`
- end: `0x1405efd70`
- name: `KiInitializeNormalPriorityAntiStarvationPolicies`
- size: `480`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140c6edc8`

## callees

- `0x140403380`
- `0x1405efb90`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x140a4d1f0`

## string_xrefs

- `0x1405efbae`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Session Manager\kernel`
- `0x1405efc74`: `ReadyTimeTicks`
- `0x1405efcc5`: `ThreadReadyCount`

## pseudocode

```c
int KiInitializeNormalPriorityAntiStarvationPolicies()
{
  int result; // eax
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  HANDLE KeyHandle; // [rsp+80h] [rbp+10h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Session Manager\\kernel");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( RtlQueryImageFileKeyOption(KeyHandle, L"ScanLatencyTicks", 4u, &KiNormalPriorityBoostScanLatencyTicks, 4u, 0) >= 0 )
    {
      if ( (unsigned int)KiNormalPriorityBoostScanLatencyTicks >= 7 )
      {
        if ( (unsigned int)KiNormalPriorityBoostScanLatencyTicks > 0x46 )
          KiNormalPriorityBoostScanLatencyTicks = 70;
      }
      else
      {
        KiNormalPriorityBoostScanLatencyTicks = 7;
      }
    }
    if ( RtlQueryImageFileKeyOption(KeyHandle, L"ReadyTimeTicks", 4u, &KiNormalPriorityBoostReadyTimeTicks, 4u, 0) >= 0 )
    {
      if ( (unsigned int)KiNormalPriorityBoostReadyTimeTicks >= 6 )
      {
        if ( (unsigned int)KiNormalPriorityBoostReadyTimeTicks > 0x46 )
          KiNormalPriorityBoostReadyTimeTicks = 70;
      }
      else
      {
        KiNormalPriorityBoostReadyTimeTicks = 6;
      }
    }
    if ( RtlQueryImageFileKeyOption(
           KeyHandle,
           L"ThreadReadyCount",
           4u,
           &KiNormalPriorityBoostMaximumThreadReadyCount,
           4u,
           0) >= 0 )
    {
      if ( KiNormalPriorityBoostMaximumThreadReadyCount )
      {
        if ( (unsigned int)KiNormalPriorityBoostMaximumThreadReadyCount > 0xA )
          KiNormalPriorityBoostMaximumThreadReadyCount = 10;
      }
      else
      {
        KiNormalPriorityBoostMaximumThreadReadyCount = 1;
      }
    }
    result = RtlQueryImageFileKeyOption(
               KeyHandle,
               L"BoostingPeriodMultiplier",
               4u,
               &KiNormalPriorityBoostingPeriodMultiplier,
               4u,
               0);
    if ( result >= 0 )
    {
      result = KiNormalPriorityBoostingPeriodMultiplier;
      if ( KiNormalPriorityBoostingPeriodMultiplier )
      {
        if ( (unsigned int)KiNormalPriorityBoostingPeriodMultiplier > 0x14 )
          KiNormalPriorityBoostingPeriodMultiplier = 20;
      }
      else
      {
        KiNormalPriorityBoostingPeriodMultiplier = 1;
      }
    }
    if ( KeyHandle )
      return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x1405efb90  mov     [rsp-8+arg_8], rdi
0x1405efb95  push    rbp
0x1405efb96  mov     rbp, rsp
0x1405efb99  sub     rsp, 70h
0x1405efb9d  xorps   xmm0, xmm0
0x1405efba0  mov     [rbp+KeyHandle], 0
0x1405efba8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1405efbac  xor     eax, eax
0x1405efbae  lea     rdx, aRegistryMachin_115; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1405efbb5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1405efbb9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1405efbbd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1405efbc1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1405efbc5  call    RtlInitUnicodeString
0x1405efbca  lea     rax, [rbp+DestinationString]
0x1405efbce  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1405efbd5  xorps   xmm0, xmm0
0x1405efbd8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1405efbdc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1405efbe0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1405efbe8  mov     edx, 1; DesiredAccess
0x1405efbed  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1405efbf4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1405efbf8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1405efbfd  call    ZwOpenKey
0x1405efc02  test    eax, eax
0x1405efc04  js      loc_1405EFD61
0x1405efc0a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405efc0e  lea     r9, KiNormalPriorityBoostScanLatencyTicks
0x1405efc15  mov     edi, 4
0x1405efc1a  mov     [rsp+70h+var_48], 0; __int64
0x1405efc23  mov     r8d, edi
0x1405efc26  mov     [rsp+70h+var_50], edi; int
0x1405efc2a  lea     rdx, aScanlatencytic; "ScanLatencyTicks"
0x1405efc31  call    RtlQueryImageFileKeyOption
0x1405efc36  test    eax, eax
0x1405efc38  js      short loc_1405EFC60
0x1405efc3a  mov     eax, cs:KiNormalPriorityBoostScanLatencyTicks
0x1405efc40  cmp     eax, 7
0x1405efc43  jnb     short loc_1405EFC51
0x1405efc45  mov     cs:KiNormalPriorityBoostScanLatencyTicks, 7
0x1405efc4f  jmp     short loc_1405EFC60
0x1405efc51  cmp     eax, 46h ; 'F'
0x1405efc54  jbe     short loc_1405EFC60
0x1405efc56  mov     cs:KiNormalPriorityBoostScanLatencyTicks, 46h ; 'F'
0x1405efc60  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405efc64  lea     r9, KiNormalPriorityBoostReadyTimeTicks
0x1405efc6b  mov     [rsp+70h+var_48], 0; __int64
0x1405efc74  lea     rdx, aReadytimeticks; "ReadyTimeTicks"
0x1405efc7b  mov     r8d, edi
0x1405efc7e  mov     [rsp+70h+var_50], edi; int
0x1405efc82  call    RtlQueryImageFileKeyOption
0x1405efc87  test    eax, eax
0x1405efc89  js      short loc_1405EFCB1
0x1405efc8b  mov     eax, cs:KiNormalPriorityBoostReadyTimeTicks
0x1405efc91  cmp     eax, 6
0x1405efc94  jnb     short loc_1405EFCA2
0x1405efc96  mov     cs:KiNormalPriorityBoostReadyTimeTicks, 6
0x1405efca0  jmp     short loc_1405EFCB1
0x1405efca2  cmp     eax, 46h ; 'F'
0x1405efca5  jbe     short loc_1405EFCB1
0x1405efca7  mov     cs:KiNormalPriorityBoostReadyTimeTicks, 46h ; 'F'
0x1405efcb1  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405efcb5  lea     r9, KiNormalPriorityBoostMaximumThreadReadyCount
0x1405efcbc  mov     [rsp+70h+var_48], 0; __int64
0x1405efcc5  lea     rdx, aThreadreadycou; "ThreadReadyCount"
0x1405efccc  mov     r8d, edi
0x1405efccf  mov     [rsp+70h+var_50], edi; int
0x1405efcd3  call    RtlQueryImageFileKeyOption
0x1405efcd8  test    eax, eax
0x1405efcda  js      short loc_1405EFD02
0x1405efcdc  mov     eax, cs:KiNormalPriorityBoostMaximumThreadReadyCount
0x1405efce2  cmp     eax, 1
0x1405efce5  jnb     short loc_1405EFCF3
0x1405efce7  mov     cs:KiNormalPriorityBoostMaximumThreadReadyCount, 1
0x1405efcf1  jmp     short loc_1405EFD02
0x1405efcf3  cmp     eax, 0Ah
0x1405efcf6  jbe     short loc_1405EFD02
0x1405efcf8  mov     cs:KiNormalPriorityBoostMaximumThreadReadyCount, 0Ah
0x1405efd02  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405efd06  lea     r9, KiNormalPriorityBoostingPeriodMultiplier
0x1405efd0d  mov     [rsp+70h+var_48], 0; __int64
0x1405efd16  lea     rdx, aBoostingperiod; "BoostingPeriodMultiplier"
0x1405efd1d  mov     r8d, edi
0x1405efd20  mov     [rsp+70h+var_50], edi; int
0x1405efd24  call    RtlQueryImageFileKeyOption
0x1405efd29  test    eax, eax
0x1405efd2b  js      short loc_1405EFD53
0x1405efd2d  mov     eax, cs:KiNormalPriorityBoostingPeriodMultiplier
0x1405efd33  cmp     eax, 1
0x1405efd36  jnb     short loc_1405EFD44
0x1405efd38  mov     cs:KiNormalPriorityBoostingPeriodMultiplier, 1
0x1405efd42  jmp     short loc_1405EFD53
0x1405efd44  cmp     eax, 14h
0x1405efd47  jbe     short loc_1405EFD53
0x1405efd49  mov     cs:KiNormalPriorityBoostingPeriodMultiplier, 14h
0x1405efd53  mov     rcx, [rbp+KeyHandle]; Handle
0x1405efd57  test    rcx, rcx
0x1405efd5a  jz      short loc_1405EFD61
0x1405efd5c  call    ZwClose
0x1405efd61  mov     rdi, [rsp+70h+arg_8]
0x1405efd69  add     rsp, 70h
0x1405efd6d  pop     rbp
0x1405efd6e  retn
```
