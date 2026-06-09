# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x140017224`
- end: `0x140017253`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400170f0`

## callees

- `0x140017338`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3,
        unsigned int a4)
{
  int v5; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v5 = a2;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v5, 4u, &v6, 4u, a4);
}

```

## disassembly

```asm
0x140017224  mov     rax, rsp
0x140017227  mov     [rax+18h], r8d
0x14001722b  mov     [rax+10h], edx
0x14001722e  sub     rsp, 38h
0x140017232  mov     [rax-10h], r9d
0x140017236  lea     rdx, [rax+10h]; void *
0x14001723a  mov     r8d, 4; unsigned __int64
0x140017240  lea     r9, [rax+18h]; void *
0x140017244  mov     [rax-18h], r8
0x140017248  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14001724d  add     rsp, 38h
0x140017251  retn
```
