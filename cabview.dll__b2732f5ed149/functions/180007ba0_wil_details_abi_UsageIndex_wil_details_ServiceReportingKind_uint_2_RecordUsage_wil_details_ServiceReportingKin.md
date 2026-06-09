# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180007ba0`
- end: `0x180007beb`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `75`
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
0x180007ba0  mov     r11, rsp
0x180007ba3  sub     rsp, 58h
0x180007ba7  mov     rax, cs:__security_cookie
0x180007bae  xor     rax, rsp
0x180007bb1  mov     [rsp+58h+var_18], rax
0x180007bb6  mov     [rsp+58h+var_20], edx
0x180007bba  lea     rdx, [r11-20h]; void *
0x180007bbe  mov     [r11-30h], r9d
0x180007bc2  lea     r9, [r11-28h]; void *
0x180007bc6  mov     [r11-28h], r8d
0x180007bca  mov     r8d, 4; unsigned __int64
0x180007bd0  mov     [r11-38h], r8
0x180007bd4  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007bd9  mov     rcx, [rsp+58h+var_18]
0x180007bde  xor     rcx, rsp; StackCookie
0x180007be1  call    __security_check_cookie
0x180007be6  add     rsp, 58h
0x180007bea  retn
```
