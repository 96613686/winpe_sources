# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180015980`
- end: `0x180015ab0`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014320`
- `0x1800161a4`

## callees

- `0x180015980`
- `0x180015ab8`
- `0x180019010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  char v9; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v9 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015980  mov     rax, rsp
0x180015983  push    rbx
0x180015984  push    rbp
0x180015985  push    rsi
0x180015986  push    rdi
0x180015987  sub     rsp, 58h
0x18001598b  mov     r11d, [rax+38h]
0x18001598f  mov     esi, edx
0x180015991  mov     rbp, rcx
0x180015994  test    r11d, r11d
0x180015997  jz      loc_180015AA7
0x18001599d  mov     ebx, [rsp+78h+arg_28]
0x1800159a4  mov     r10d, r11d
0x1800159a7  sub     r10d, 1
0x1800159ab  jz      loc_180015A36
0x1800159b1  sub     r10d, 1
0x1800159b5  jz      short loc_180015A28
0x1800159b7  sub     r10d, 1
0x1800159bb  jz      short loc_180015A1A
0x1800159bd  sub     r10d, 1
0x1800159c1  jz      short loc_180015A0C
0x1800159c3  sub     r10d, 1
0x1800159c7  jz      short loc_1800159FE
0x1800159c9  cmp     r10d, 1
0x1800159cd  jz      short loc_1800159F0
0x1800159cf  sub     r11b, 64h ; 'd'
0x1800159d3  cmp     r11b, 31h ; '1'
0x1800159d7  ja      short loc_180015A43
0x1800159d9  mov     eax, ebx
0x1800159db  neg     eax
0x1800159dd  movzx   eax, r11b
0x1800159e1  sbb     ecx, ecx
0x1800159e3  and     ecx, 0FFFFFFCEh
0x1800159e6  add     ecx, 96h
0x1800159ec  add     ecx, eax
0x1800159ee  jmp     short loc_180015A48
0x1800159f0  mov     eax, ebx
0x1800159f2  neg     eax
0x1800159f4  sbb     ecx, ecx
0x1800159f6  and     ecx, 0FFFFFFFEh
0x1800159f9  add     ecx, 0Bh
0x1800159fc  jmp     short loc_180015A48
0x1800159fe  mov     eax, ebx
0x180015a00  neg     eax
0x180015a02  sbb     ecx, ecx
0x180015a04  and     ecx, 0FFFFFFFEh
0x180015a07  add     ecx, 0Ah
0x180015a0a  jmp     short loc_180015A48
0x180015a0c  mov     eax, ebx
0x180015a0e  neg     eax
0x180015a10  sbb     ecx, ecx
0x180015a12  and     ecx, 0FFFFFFFCh
0x180015a15  add     ecx, 7
0x180015a18  jmp     short loc_180015A48
0x180015a1a  mov     eax, ebx
0x180015a1c  neg     eax
0x180015a1e  sbb     ecx, ecx
0x180015a20  and     ecx, 0FFFFFFFCh
0x180015a23  add     ecx, 6
0x180015a26  jmp     short loc_180015A48
0x180015a28  mov     eax, ebx
0x180015a2a  neg     eax
0x180015a2c  sbb     ecx, ecx
0x180015a2e  and     ecx, 0FFFFFFFCh
0x180015a31  add     ecx, 5
0x180015a34  jmp     short loc_180015A48
0x180015a36  mov     eax, ebx
0x180015a38  neg     eax
0x180015a3a  sbb     ecx, ecx
0x180015a3c  not     ecx
0x180015a3e  and     ecx, 4
0x180015a41  jmp     short loc_180015A48
0x180015a43  mov     ecx, 0FFh
0x180015a48  mov     rdi, [rsp+78h+arg_20]
0x180015a50  mov     al, [rdi+4]
0x180015a53  mov     byte ptr [rsp+78h+var_40], al
0x180015a57  mov     dword ptr [rsp+78h+var_58], ecx
0x180015a5b  mov     rcx, rbp
0x180015a5e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180015a63  test    eax, eax
0x180015a65  jz      short loc_180015AA7
0x180015a67  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180015a6e  test    rax, rax
0x180015a71  jz      short loc_180015AA7
0x180015a73  mov     [rsp+78h+var_40], 1
0x180015a7c  lea     rcx, [rsp+78h+arg_30]
0x180015a84  mov     [rsp+78h+var_48], 0
0x180015a89  mov     r9d, ebx
0x180015a8c  mov     [rsp+78h+var_50], 0
0x180015a95  xor     r8d, r8d
0x180015a98  mov     [rsp+78h+var_58], rcx
0x180015a9d  mov     rdx, rdi
0x180015aa0  mov     ecx, esi
0x180015aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa7  add     rsp, 58h
0x180015aab  pop     rdi
0x180015aac  pop     rsi
0x180015aad  pop     rbp
0x180015aae  pop     rbx
0x180015aaf  retn
```
