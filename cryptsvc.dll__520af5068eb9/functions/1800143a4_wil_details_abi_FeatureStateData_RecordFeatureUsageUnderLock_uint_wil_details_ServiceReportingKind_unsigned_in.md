# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800143a4`
- end: `0x1800143f9`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a9dc`

## callees

- `0x1800143a4`
- `0x180014450`
- `0x180014484`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v3; // rbx
  int v4; // eax

  v3 = a1 + 8;
  if ( a3 > 7 || (v4 = 204, !_bittest(&v4, a3)) )
  {
    if ( a3 - 256 > 0x7F )
      return wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
               a1 + 72,
               a3,
               a2);
  }
  wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(a1 + 8, a3, a2);
  return *(_BYTE *)(v3 + 56);
}

```

## disassembly

```asm
0x1800143a4  push    rbx
0x1800143a6  sub     rsp, 20h
0x1800143aa  lea     rbx, [rcx+8]
0x1800143ae  mov     r10d, r8d
0x1800143b1  cmp     r8d, 7
0x1800143b5  ja      short loc_1800143C2
0x1800143b7  mov     eax, 0CCh
0x1800143bc  bt      eax, r8d
0x1800143c0  jb      short loc_1800143E2
0x1800143c2  lea     eax, [r8-100h]
0x1800143c9  cmp     eax, 7Fh
0x1800143cc  jbe     short loc_1800143E2
0x1800143ce  mov     r8d, edx
0x1800143d1  lea     rcx, [rbx+40h]
0x1800143d5  mov     edx, r10d
0x1800143d8  add     rsp, 20h
0x1800143dc  pop     rbx
0x1800143dd  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800143e2  mov     r8d, edx
0x1800143e5  mov     rcx, rbx
0x1800143e8  mov     edx, r10d
0x1800143eb  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800143f0  mov     al, [rbx+38h]
0x1800143f3  add     rsp, 20h
0x1800143f7  pop     rbx
0x1800143f8  retn
```
