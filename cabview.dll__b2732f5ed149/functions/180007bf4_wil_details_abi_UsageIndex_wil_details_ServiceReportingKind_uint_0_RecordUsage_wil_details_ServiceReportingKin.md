# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180007bf4`
- end: `0x180007c43`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007af4`

## callees

- `0x180002620`
- `0x180007ccc`

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
0x180007bf4  mov     r11, rsp
0x180007bf7  sub     rsp, 58h
0x180007bfb  mov     rax, cs:__security_cookie
0x180007c02  xor     rax, rsp
0x180007c05  mov     [rsp+58h+var_18], rax
0x180007c0a  mov     [rsp+58h+var_20], edx
0x180007c0e  lea     r9, [r11-28h]; void *
0x180007c12  mov     [r11-28h], r8d
0x180007c16  lea     rdx, [r11-20h]; void *
0x180007c1a  mov     r8d, 4; unsigned __int64
0x180007c20  mov     [rsp+58h+var_30], 1; unsigned int
0x180007c28  mov     [r11-38h], r8
0x180007c2c  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007c31  mov     rcx, [rsp+58h+var_18]
0x180007c36  xor     rcx, rsp; StackCookie
0x180007c39  call    __security_check_cookie
0x180007c3e  add     rsp, 58h
0x180007c42  retn
```
