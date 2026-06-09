# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x14000f8b0`
- end: `0x14000f8ff`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `79`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000f800`

## callees

- `0x140002360`
- `0x14000f988`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3)
{
  int v4; // [rsp+30h] [rbp-28h] BYREF
  int v5; // [rsp+38h] [rbp-20h] BYREF

  v5 = a2;
  v4 = a3;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v5, 4u, &v4, 4u, 1u);
}

```

## disassembly

```asm
0x14000f8b0  mov     r11, rsp
0x14000f8b3  sub     rsp, 58h
0x14000f8b7  mov     rax, cs:__security_cookie
0x14000f8be  xor     rax, rsp
0x14000f8c1  mov     [rsp+58h+var_18], rax
0x14000f8c6  mov     [rsp+58h+var_20], edx
0x14000f8ca  lea     r9, [r11-28h]; void *
0x14000f8ce  mov     [r11-28h], r8d
0x14000f8d2  lea     rdx, [r11-20h]; void *
0x14000f8d6  mov     r8d, 4; unsigned __int64
0x14000f8dc  mov     [rsp+58h+var_30], 1; unsigned int
0x14000f8e4  mov     [r11-38h], r8
0x14000f8e8  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000f8ed  mov     rcx, [rsp+58h+var_18]
0x14000f8f2  xor     rcx, rsp; StackCookie
0x14000f8f5  call    __security_check_cookie
0x14000f8fa  add     rsp, 58h
0x14000f8fe  retn
```
