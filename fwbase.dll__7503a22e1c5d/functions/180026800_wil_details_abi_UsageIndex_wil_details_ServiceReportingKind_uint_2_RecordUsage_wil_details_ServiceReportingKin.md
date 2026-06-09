# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180026800`
- end: `0x180026851`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `81`
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
0x180026800  sub     rsp, 58h
0x180026804  mov     rax, cs:__security_cookie
0x18002680b  xor     rax, rsp
0x18002680e  mov     [rsp+58h+var_18], rax
0x180026813  mov     [rsp+58h+var_30], r9d; unsigned int
0x180026818  lea     r9, [rsp+58h+var_28]; void *
0x18002681d  mov     [rsp+58h+var_20], edx
0x180026821  lea     rdx, [rsp+58h+var_20]; void *
0x180026826  mov     [rsp+58h+var_28], r8d
0x18002682b  mov     r8d, 4; unsigned __int64
0x180026831  mov     [rsp+58h+var_38], 4; unsigned __int64
0x18002683a  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18002683f  mov     rcx, [rsp+58h+var_18]
0x180026844  xor     rcx, rsp; StackCookie
0x180026847  call    __security_check_cookie
0x18002684c  add     rsp, 58h
0x180026850  retn
```
