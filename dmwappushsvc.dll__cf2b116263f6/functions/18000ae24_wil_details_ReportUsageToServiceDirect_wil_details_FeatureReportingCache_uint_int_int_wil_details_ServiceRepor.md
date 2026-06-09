# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000ae24`
- end: `0x18000aee7`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `195`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ad94`

## callees

- `0x18000a5cc`
- `0x18000ae24`
- `0x18000bfd0`
- `0x18000d908`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v11; // rax
  __int64 v12; // xmm0_8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned int v16; // r9d
  unsigned int v17; // edx
  char *v19; // [rsp+20h] [rbp-48h]
  char v20[16]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v21; // [rsp+40h] [rbp-28h]
  _BYTE v22[32]; // [rsp+48h] [rbp-20h] BYREF

  v11 = wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v12 = *(_QWORD *)(v11 + 16);
  *(_OWORD *)v20 = *(_OWORD *)v11;
  v21 = v12;
  wil::details::RecordFeatureUsageCallback(v13, a5, v14, a1, (RTL_SRWLOCK *)v20);
  if ( a3 )
  {
    v17 = a5 | 0x80000000;
    if ( !a4 )
      v17 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x16B4257, v17, 0, v16, v19);
  }
  if ( (_DWORD)v21 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v15) = a8;
    g_wil_details_realtimeFeatureUsageHook(23806551, a5, v15);
  }
  return 1;
}

```

## disassembly

```asm
0x18000ae24  mov     [rsp+arg_0], rbx
0x18000ae29  mov     [rsp+arg_8], rbp
0x18000ae2e  push    rdi
0x18000ae2f  sub     rsp, 60h
0x18000ae33  mov     edi, r8d
0x18000ae36  mov     rbx, rcx
0x18000ae39  mov     r8d, [rsp+68h+arg_20]
0x18000ae41  mov     rdx, rcx
0x18000ae44  lea     rcx, [rsp+68h+var_20]
0x18000ae49  mov     ebp, r9d
0x18000ae4c  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ae51  mov     edx, [rsp+68h+arg_20]
0x18000ae58  mov     r9, rbx
0x18000ae5b  movups  xmm1, xmmword ptr [rax]
0x18000ae5e  movsd   xmm0, qword ptr [rax+10h]
0x18000ae63  lea     rax, [rsp+68h+var_38]
0x18000ae68  movups  xmmword ptr [rsp+68h+var_38], xmm1
0x18000ae6d  mov     [rsp+68h+var_48], rax; char *
0x18000ae72  movsd   [rsp+68h+var_28], xmm0
0x18000ae78  call    ?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z; wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)
0x18000ae7d  mov     ebx, 16B4257h
0x18000ae82  test    edi, edi
0x18000ae84  jz      short loc_18000AEA5
0x18000ae86  mov     edx, [rsp+68h+arg_20]
0x18000ae8d  mov     ecx, ebx; this
0x18000ae8f  bts     edx, 1Fh
0x18000ae93  test    ebp, ebp
0x18000ae95  cmovz   edx, [rsp+68h+arg_20]; unsigned int
0x18000ae9d  xor     r8d, r8d; unsigned int
0x18000aea0  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000aea5  cmp     dword ptr [rsp+68h+var_28], 0
0x18000aeaa  jnz     short loc_18000AED5
0x18000aeac  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000aeb3  test    rax, rax
0x18000aeb6  jz      short loc_18000AECE
0x18000aeb8  mov     r8b, [rsp+68h+arg_38]
0x18000aec0  mov     ecx, ebx
0x18000aec2  mov     edx, [rsp+68h+arg_20]
0x18000aec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aece  mov     eax, 1
0x18000aed3  jmp     short loc_18000AED7
0x18000aed5  xor     eax, eax
0x18000aed7  mov     rbx, [rsp+68h+arg_0]
0x18000aedc  mov     rbp, [rsp+68h+arg_8]
0x18000aee1  add     rsp, 60h
0x18000aee5  pop     rdi
0x18000aee6  retn
```
