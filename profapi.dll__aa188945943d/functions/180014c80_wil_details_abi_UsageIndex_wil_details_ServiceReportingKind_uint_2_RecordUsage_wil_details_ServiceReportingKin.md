# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180014c80`
- end: `0x180014cae`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `46`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180014bc0`

## callees

- `0x18000f1f0`

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
0x180014c80  mov     rax, rsp
0x180014c83  mov     [rax+18h], r8d
0x180014c87  mov     [rax+10h], edx
0x180014c8a  sub     rsp, 38h
0x180014c8e  mov     [rax-10h], r9d
0x180014c92  lea     rdx, [rax+10h]; void *
0x180014c96  mov     r8d, 4; unsigned __int64
0x180014c9c  lea     r9, [rax+18h]; void *
0x180014ca0  mov     [rax-18h], r8
0x180014ca4  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180014ca9  add     rsp, 38h
0x180014cad  retn
```
