# KiInitializeNormalPriorityAntiStarvationPolicies

- ea: `0x1405e8fb0`
- end: `0x1405e9190`
- name: `KiInitializeNormalPriorityAntiStarvationPolicies`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140c69b18`

## callees

- `0x1403f2d50`
- `0x1405e8fb0`
- `0x1406daa70`
- `0x1406daad0`
- `0x140a43820`

## string_xrefs

- `0x1405e8fce`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Session Manager\kernel`
- `0x1405e90e5`: `ThreadReadyCount`
- `0x1405e9094`: `ReadyTimeTicks`

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
    if ( (int)RtlQueryImageFileKeyOption(KeyHandle, 4, 0) >= 0 )
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
    if ( (int)RtlQueryImageFileKeyOption(KeyHandle, 4, 0) >= 0 )
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
    if ( (int)RtlQueryImageFileKeyOption(KeyHandle, 4, 0) >= 0 )
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
    result = RtlQueryImageFileKeyOption(KeyHandle, 4, 0);
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
0x1405e8fb0  mov     [rsp-8+arg_8], rdi
0x1405e8fb5  push    rbp
0x1405e8fb6  mov     rbp, rsp
0x1405e8fb9  sub     rsp, 70h
0x1405e8fbd  xorps   xmm0, xmm0
0x1405e8fc0  mov     [rbp+KeyHandle], 0
0x1405e8fc8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1405e8fcc  xor     eax, eax
0x1405e8fce  lea     rdx, aRegistryMachin_115; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1405e8fd5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1405e8fd9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1405e8fdd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1405e8fe1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1405e8fe5  call    RtlInitUnicodeString
0x1405e8fea  lea     rax, [rbp+DestinationString]
0x1405e8fee  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1405e8ff5  xorps   xmm0, xmm0
0x1405e8ff8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1405e8ffc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1405e9000  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1405e9008  mov     edx, 1; DesiredAccess
0x1405e900d  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1405e9014  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1405e9018  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1405e901d  call    ZwOpenKey
0x1405e9022  test    eax, eax
0x1405e9024  js      loc_1405E9181
0x1405e902a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405e902e  lea     r9, KiNormalPriorityBoostScanLatencyTicks
0x1405e9035  mov     edi, 4
0x1405e903a  mov     [rsp+70h+var_48], 0; __int64
0x1405e9043  mov     r8d, edi
0x1405e9046  mov     [rsp+70h+var_50], edi; int
0x1405e904a  lea     rdx, aScanlatencytic; "ScanLatencyTicks"
0x1405e9051  call    RtlQueryImageFileKeyOption
0x1405e9056  test    eax, eax
0x1405e9058  js      short loc_1405E9080
0x1405e905a  mov     eax, cs:KiNormalPriorityBoostScanLatencyTicks
0x1405e9060  cmp     eax, 7
0x1405e9063  jnb     short loc_1405E9071
0x1405e9065  mov     cs:KiNormalPriorityBoostScanLatencyTicks, 7
0x1405e906f  jmp     short loc_1405E9080
0x1405e9071  cmp     eax, 46h ; 'F'
0x1405e9074  jbe     short loc_1405E9080
0x1405e9076  mov     cs:KiNormalPriorityBoostScanLatencyTicks, 46h ; 'F'
0x1405e9080  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405e9084  lea     r9, KiNormalPriorityBoostReadyTimeTicks
0x1405e908b  mov     [rsp+70h+var_48], 0; __int64
0x1405e9094  lea     rdx, aReadytimeticks; "ReadyTimeTicks"
0x1405e909b  mov     r8d, edi
0x1405e909e  mov     [rsp+70h+var_50], edi; int
0x1405e90a2  call    RtlQueryImageFileKeyOption
0x1405e90a7  test    eax, eax
0x1405e90a9  js      short loc_1405E90D1
0x1405e90ab  mov     eax, cs:KiNormalPriorityBoostReadyTimeTicks
0x1405e90b1  cmp     eax, 6
0x1405e90b4  jnb     short loc_1405E90C2
0x1405e90b6  mov     cs:KiNormalPriorityBoostReadyTimeTicks, 6
0x1405e90c0  jmp     short loc_1405E90D1
0x1405e90c2  cmp     eax, 46h ; 'F'
0x1405e90c5  jbe     short loc_1405E90D1
0x1405e90c7  mov     cs:KiNormalPriorityBoostReadyTimeTicks, 46h ; 'F'
0x1405e90d1  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405e90d5  lea     r9, KiNormalPriorityBoostMaximumThreadReadyCount
0x1405e90dc  mov     [rsp+70h+var_48], 0; __int64
0x1405e90e5  lea     rdx, aThreadreadycou; "ThreadReadyCount"
0x1405e90ec  mov     r8d, edi
0x1405e90ef  mov     [rsp+70h+var_50], edi; int
0x1405e90f3  call    RtlQueryImageFileKeyOption
0x1405e90f8  test    eax, eax
0x1405e90fa  js      short loc_1405E9122
0x1405e90fc  mov     eax, cs:KiNormalPriorityBoostMaximumThreadReadyCount
0x1405e9102  cmp     eax, 1
0x1405e9105  jnb     short loc_1405E9113
0x1405e9107  mov     cs:KiNormalPriorityBoostMaximumThreadReadyCount, 1
0x1405e9111  jmp     short loc_1405E9122
0x1405e9113  cmp     eax, 0Ah
0x1405e9116  jbe     short loc_1405E9122
0x1405e9118  mov     cs:KiNormalPriorityBoostMaximumThreadReadyCount, 0Ah
0x1405e9122  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1405e9126  lea     r9, KiNormalPriorityBoostingPeriodMultiplier
0x1405e912d  mov     [rsp+70h+var_48], 0; __int64
0x1405e9136  lea     rdx, aBoostingperiod; "BoostingPeriodMultiplier"
0x1405e913d  mov     r8d, edi
0x1405e9140  mov     [rsp+70h+var_50], edi; int
0x1405e9144  call    RtlQueryImageFileKeyOption
0x1405e9149  test    eax, eax
0x1405e914b  js      short loc_1405E9173
0x1405e914d  mov     eax, cs:KiNormalPriorityBoostingPeriodMultiplier
0x1405e9153  cmp     eax, 1
0x1405e9156  jnb     short loc_1405E9164
0x1405e9158  mov     cs:KiNormalPriorityBoostingPeriodMultiplier, 1
0x1405e9162  jmp     short loc_1405E9173
0x1405e9164  cmp     eax, 14h
0x1405e9167  jbe     short loc_1405E9173
0x1405e9169  mov     cs:KiNormalPriorityBoostingPeriodMultiplier, 14h
0x1405e9173  mov     rcx, [rbp+KeyHandle]; Handle
0x1405e9177  test    rcx, rcx
0x1405e917a  jz      short loc_1405E9181
0x1405e917c  call    ZwClose
0x1405e9181  mov     rdi, [rsp+70h+arg_8]
0x1405e9189  add     rsp, 70h
0x1405e918d  pop     rbp
0x1405e918e  retn
```
