# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180010550`
- end: `0x180010680`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000cbbc`
- `0x1800104b8`
- `0x180015764`
- `0x180015804`

## callees

- `0x180010550`
- `0x180010688`
- `0x180023010`

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
0x180010550  mov     rax, rsp
0x180010553  push    rbx
0x180010554  push    rbp
0x180010555  push    rsi
0x180010556  push    rdi
0x180010557  sub     rsp, 58h
0x18001055b  mov     r11d, [rax+38h]
0x18001055f  mov     esi, edx
0x180010561  mov     rbp, rcx
0x180010564  test    r11d, r11d
0x180010567  jz      loc_180010677
0x18001056d  mov     ebx, [rsp+78h+arg_28]
0x180010574  mov     r10d, r11d
0x180010577  sub     r10d, 1
0x18001057b  jz      loc_180010606
0x180010581  sub     r10d, 1
0x180010585  jz      short loc_1800105F8
0x180010587  sub     r10d, 1
0x18001058b  jz      short loc_1800105EA
0x18001058d  sub     r10d, 1
0x180010591  jz      short loc_1800105DC
0x180010593  sub     r10d, 1
0x180010597  jz      short loc_1800105CE
0x180010599  cmp     r10d, 1
0x18001059d  jz      short loc_1800105C0
0x18001059f  sub     r11b, 64h ; 'd'
0x1800105a3  cmp     r11b, 31h ; '1'
0x1800105a7  ja      short loc_180010613
0x1800105a9  mov     eax, ebx
0x1800105ab  neg     eax
0x1800105ad  movzx   eax, r11b
0x1800105b1  sbb     ecx, ecx
0x1800105b3  and     ecx, 0FFFFFFCEh
0x1800105b6  add     ecx, 96h
0x1800105bc  add     ecx, eax
0x1800105be  jmp     short loc_180010618
0x1800105c0  mov     eax, ebx
0x1800105c2  neg     eax
0x1800105c4  sbb     ecx, ecx
0x1800105c6  and     ecx, 0FFFFFFFEh
0x1800105c9  add     ecx, 0Bh
0x1800105cc  jmp     short loc_180010618
0x1800105ce  mov     eax, ebx
0x1800105d0  neg     eax
0x1800105d2  sbb     ecx, ecx
0x1800105d4  and     ecx, 0FFFFFFFEh
0x1800105d7  add     ecx, 0Ah
0x1800105da  jmp     short loc_180010618
0x1800105dc  mov     eax, ebx
0x1800105de  neg     eax
0x1800105e0  sbb     ecx, ecx
0x1800105e2  and     ecx, 0FFFFFFFCh
0x1800105e5  add     ecx, 7
0x1800105e8  jmp     short loc_180010618
0x1800105ea  mov     eax, ebx
0x1800105ec  neg     eax
0x1800105ee  sbb     ecx, ecx
0x1800105f0  and     ecx, 0FFFFFFFCh
0x1800105f3  add     ecx, 6
0x1800105f6  jmp     short loc_180010618
0x1800105f8  mov     eax, ebx
0x1800105fa  neg     eax
0x1800105fc  sbb     ecx, ecx
0x1800105fe  and     ecx, 0FFFFFFFCh
0x180010601  add     ecx, 5
0x180010604  jmp     short loc_180010618
0x180010606  mov     eax, ebx
0x180010608  neg     eax
0x18001060a  sbb     ecx, ecx
0x18001060c  not     ecx
0x18001060e  and     ecx, 4
0x180010611  jmp     short loc_180010618
0x180010613  mov     ecx, 0FFh
0x180010618  mov     rdi, [rsp+78h+arg_20]
0x180010620  mov     al, [rdi+4]
0x180010623  mov     byte ptr [rsp+78h+var_40], al
0x180010627  mov     dword ptr [rsp+78h+var_58], ecx
0x18001062b  mov     rcx, rbp
0x18001062e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180010633  test    eax, eax
0x180010635  jz      short loc_180010677
0x180010637  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001063e  test    rax, rax
0x180010641  jz      short loc_180010677
0x180010643  mov     [rsp+78h+var_40], 1
0x18001064c  lea     rcx, [rsp+78h+arg_30]
0x180010654  mov     [rsp+78h+var_48], 0
0x180010659  mov     r9d, ebx
0x18001065c  mov     [rsp+78h+var_50], 0
0x180010665  xor     r8d, r8d
0x180010668  mov     [rsp+78h+var_58], rcx
0x18001066d  mov     rdx, rdi
0x180010670  mov     ecx, esi
0x180010672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010677  add     rsp, 58h
0x18001067b  pop     rdi
0x18001067c  pop     rsi
0x18001067d  pop     rbp
0x18001067e  pop     rbx
0x18001067f  retn
```
