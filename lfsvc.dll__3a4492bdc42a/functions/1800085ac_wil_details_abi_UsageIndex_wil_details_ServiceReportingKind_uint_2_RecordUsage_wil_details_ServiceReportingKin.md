# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x1800085ac`
- end: `0x1800085f7`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `75`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800084c4`

## callees

- `0x180003494`
- `0x180004310`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3,
        unsigned int a4)
{
  int v5; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h] BYREF

  v6 = a2;
  v5 = a3;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v6, 4u, &v5, 4u, a4);
}

```

## disassembly

```asm
0x1800085ac  mov     r11, rsp
0x1800085af  sub     rsp, 58h
0x1800085b3  mov     rax, cs:__security_cookie
0x1800085ba  xor     rax, rsp
0x1800085bd  mov     [rsp+58h+var_18], rax
0x1800085c2  mov     [rsp+58h+var_20], edx
0x1800085c6  lea     rdx, [r11-20h]; void *
0x1800085ca  mov     [r11-30h], r9d
0x1800085ce  lea     r9, [r11-28h]; void *
0x1800085d2  mov     [r11-28h], r8d
0x1800085d6  mov     r8d, 4; unsigned __int64
0x1800085dc  mov     [r11-38h], r8
0x1800085e0  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800085e5  mov     rcx, [rsp+58h+var_18]
0x1800085ea  xor     rcx, rsp; StackCookie
0x1800085ed  call    __security_check_cookie
0x1800085f2  add     rsp, 58h
0x1800085f6  retn
```
