# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007af4`
- end: `0x180007b49`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007a24`

## callees

- `0x180007af4`
- `0x180007ba0`
- `0x180007bf4`

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
0x180007af4  push    rbx
0x180007af6  sub     rsp, 20h
0x180007afa  lea     rbx, [rcx+8]
0x180007afe  mov     r10d, r8d
0x180007b01  cmp     r8d, 7
0x180007b05  ja      short loc_180007B12
0x180007b07  mov     eax, 0CCh
0x180007b0c  bt      eax, r8d
0x180007b10  jb      short loc_180007B32
0x180007b12  lea     eax, [r8-100h]
0x180007b19  cmp     eax, 7Fh
0x180007b1c  jbe     short loc_180007B32
0x180007b1e  mov     r8d, edx
0x180007b21  lea     rcx, [rbx+40h]
0x180007b25  mov     edx, r10d
0x180007b28  add     rsp, 20h
0x180007b2c  pop     rbx
0x180007b2d  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b32  mov     r8d, edx
0x180007b35  mov     rcx, rbx
0x180007b38  mov     edx, r10d
0x180007b3b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b40  mov     al, [rbx+38h]
0x180007b43  add     rsp, 20h
0x180007b47  pop     rbx
0x180007b48  retn
```
