# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180018968`
- end: `0x180018a20`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `184`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800188c4`

## callees

- `0x18000c5f4`
- `0x18001852c`
- `0x180018968`
- `0x180023618`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v12; // rax
  __int64 v13; // xmm0_8
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned int v16; // r9d
  unsigned int v17; // edx
  char *v19; // [rsp+20h] [rbp-68h]
  char v20[16]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+40h] [rbp-48h]
  _BYTE v22[64]; // [rsp+48h] [rbp-40h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v13 = *(_QWORD *)(v12 + 16);
  *(_OWORD *)v20 = *(_OWORD *)v12;
  v21 = v13;
  wil::details::RecordFeatureUsageCallback(a2, a5, v14, a1, (RTL_SRWLOCK *)v20);
  if ( a3 )
  {
    v17 = a5 | 0x80000000;
    if ( !a4 )
      v17 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v17, 0, v16, v19);
  }
  if ( (_DWORD)v21 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v15) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v15);
  }
  return 1;
}

```

## disassembly

```asm
0x180018968  push    rbx
0x18001896a  push    rbp
0x18001896b  push    rdi
0x18001896c  push    r14
0x18001896e  sub     rsp, 68h
0x180018972  mov     ebp, edx
0x180018974  mov     edi, r8d
0x180018977  mov     r8d, [rsp+88h+arg_20]
0x18001897f  mov     rdx, rcx
0x180018982  mov     rbx, rcx
0x180018985  mov     r14d, r9d
0x180018988  lea     rcx, [rsp+88h+var_40]
0x18001898d  call    wil_details_FeatureReporting_RecordUsageInCache
0x180018992  mov     edx, [rsp+88h+arg_20]
0x180018999  mov     r9, rbx
0x18001899c  mov     ecx, ebp
0x18001899e  movups  xmm1, xmmword ptr [rax]
0x1800189a1  movsd   xmm0, qword ptr [rax+10h]
0x1800189a6  lea     rax, [rsp+88h+var_58]
0x1800189ab  movups  xmmword ptr [rsp+88h+var_58], xmm1
0x1800189b0  mov     [rsp+88h+var_68], rax; char *
0x1800189b5  movsd   [rsp+88h+var_48], xmm0
0x1800189bb  call    ?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z; wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)
0x1800189c0  test    edi, edi
0x1800189c2  jz      short loc_1800189E4
0x1800189c4  mov     edx, [rsp+88h+arg_20]
0x1800189cb  mov     ecx, ebp; this
0x1800189cd  bts     edx, 1Fh
0x1800189d1  test    r14d, r14d
0x1800189d4  cmovz   edx, [rsp+88h+arg_20]; unsigned int
0x1800189dc  xor     r8d, r8d; unsigned int
0x1800189df  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800189e4  cmp     dword ptr [rsp+88h+var_48], 0
0x1800189e9  jnz     short loc_180018A14
0x1800189eb  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800189f2  test    rax, rax
0x1800189f5  jz      short loc_180018A0D
0x1800189f7  mov     r8b, [rsp+88h+arg_38]
0x1800189ff  mov     ecx, ebp
0x180018a01  mov     edx, [rsp+88h+arg_20]
0x180018a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a0d  mov     eax, 1
0x180018a12  jmp     short loc_180018A16
0x180018a14  xor     eax, eax
0x180018a16  add     rsp, 68h
0x180018a1a  pop     r14
0x180018a1c  pop     rdi
0x180018a1d  pop     rbp
0x180018a1e  pop     rbx
0x180018a1f  retn
```
