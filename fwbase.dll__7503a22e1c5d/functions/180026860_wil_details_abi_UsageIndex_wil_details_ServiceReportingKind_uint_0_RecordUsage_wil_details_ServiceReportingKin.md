# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180026860`
- end: `0x1800268b4`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800265d0`

## callees

- `0x18001e1d0`
- `0x180026a40`

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
0x180026860  sub     rsp, 58h
0x180026864  mov     rax, cs:__security_cookie
0x18002686b  xor     rax, rsp
0x18002686e  mov     [rsp+58h+var_18], rax
0x180026873  mov     [rsp+58h+var_20], edx
0x180026877  lea     r9, [rsp+58h+var_28]; void *
0x18002687c  mov     [rsp+58h+var_28], r8d
0x180026881  lea     rdx, [rsp+58h+var_20]; void *
0x180026886  mov     r8d, 4; unsigned __int64
0x18002688c  mov     [rsp+58h+var_30], 1; unsigned int
0x180026894  mov     [rsp+58h+var_38], 4; unsigned __int64
0x18002689d  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800268a2  mov     rcx, [rsp+58h+var_18]
0x1800268a7  xor     rcx, rsp; StackCookie
0x1800268aa  call    __security_check_cookie
0x1800268af  add     rsp, 58h
0x1800268b3  retn
```
