# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180009670`
- end: `0x1800097a0`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180006520`
- `0x180006668`
- `0x18000c5f4`
- `0x18000c694`
- `0x180012c68`
- `0x180012dd8`
- `0x180012f48`
- `0x180013a04`
- `0x180013aa4`
- `0x180013b40`
- `0x180013bdc`

## callees

- `0x180009670`
- `0x1800097a8`
- `0x180015010`

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
0x180009670  mov     rax, rsp
0x180009673  push    rbx
0x180009674  push    rbp
0x180009675  push    rsi
0x180009676  push    rdi
0x180009677  sub     rsp, 58h
0x18000967b  mov     r11d, [rax+38h]
0x18000967f  mov     esi, edx
0x180009681  mov     rbp, rcx
0x180009684  test    r11d, r11d
0x180009687  jz      loc_180009797
0x18000968d  mov     ebx, [rsp+78h+arg_28]
0x180009694  mov     r10d, r11d
0x180009697  sub     r10d, 1
0x18000969b  jz      loc_180009726
0x1800096a1  sub     r10d, 1
0x1800096a5  jz      short loc_180009718
0x1800096a7  sub     r10d, 1
0x1800096ab  jz      short loc_18000970A
0x1800096ad  sub     r10d, 1
0x1800096b1  jz      short loc_1800096FC
0x1800096b3  sub     r10d, 1
0x1800096b7  jz      short loc_1800096EE
0x1800096b9  cmp     r10d, 1
0x1800096bd  jz      short loc_1800096E0
0x1800096bf  sub     r11b, 64h ; 'd'
0x1800096c3  cmp     r11b, 31h ; '1'
0x1800096c7  ja      short loc_180009733
0x1800096c9  mov     eax, ebx
0x1800096cb  neg     eax
0x1800096cd  movzx   eax, r11b
0x1800096d1  sbb     ecx, ecx
0x1800096d3  and     ecx, 0FFFFFFCEh
0x1800096d6  add     ecx, 96h
0x1800096dc  add     ecx, eax
0x1800096de  jmp     short loc_180009738
0x1800096e0  mov     eax, ebx
0x1800096e2  neg     eax
0x1800096e4  sbb     ecx, ecx
0x1800096e6  and     ecx, 0FFFFFFFEh
0x1800096e9  add     ecx, 0Bh
0x1800096ec  jmp     short loc_180009738
0x1800096ee  mov     eax, ebx
0x1800096f0  neg     eax
0x1800096f2  sbb     ecx, ecx
0x1800096f4  and     ecx, 0FFFFFFFEh
0x1800096f7  add     ecx, 0Ah
0x1800096fa  jmp     short loc_180009738
0x1800096fc  mov     eax, ebx
0x1800096fe  neg     eax
0x180009700  sbb     ecx, ecx
0x180009702  and     ecx, 0FFFFFFFCh
0x180009705  add     ecx, 7
0x180009708  jmp     short loc_180009738
0x18000970a  mov     eax, ebx
0x18000970c  neg     eax
0x18000970e  sbb     ecx, ecx
0x180009710  and     ecx, 0FFFFFFFCh
0x180009713  add     ecx, 6
0x180009716  jmp     short loc_180009738
0x180009718  mov     eax, ebx
0x18000971a  neg     eax
0x18000971c  sbb     ecx, ecx
0x18000971e  and     ecx, 0FFFFFFFCh
0x180009721  add     ecx, 5
0x180009724  jmp     short loc_180009738
0x180009726  mov     eax, ebx
0x180009728  neg     eax
0x18000972a  sbb     ecx, ecx
0x18000972c  not     ecx
0x18000972e  and     ecx, 4
0x180009731  jmp     short loc_180009738
0x180009733  mov     ecx, 0FFh
0x180009738  mov     rdi, [rsp+78h+arg_20]
0x180009740  mov     al, [rdi+4]
0x180009743  mov     byte ptr [rsp+78h+var_40], al
0x180009747  mov     dword ptr [rsp+78h+var_58], ecx
0x18000974b  mov     rcx, rbp
0x18000974e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180009753  test    eax, eax
0x180009755  jz      short loc_180009797
0x180009757  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000975e  test    rax, rax
0x180009761  jz      short loc_180009797
0x180009763  mov     [rsp+78h+var_40], 1
0x18000976c  lea     rcx, [rsp+78h+arg_30]
0x180009774  mov     [rsp+78h+var_48], 0
0x180009779  mov     r9d, ebx
0x18000977c  mov     [rsp+78h+var_50], 0
0x180009785  xor     r8d, r8d
0x180009788  mov     [rsp+78h+var_58], rcx
0x18000978d  mov     rdx, rdi
0x180009790  mov     ecx, esi
0x180009792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009797  add     rsp, 58h
0x18000979b  pop     rdi
0x18000979c  pop     rsi
0x18000979d  pop     rbp
0x18000979e  pop     rbx
0x18000979f  retn
```
