# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000fa2c`
- end: `0x18000fb5c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `18`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000d544`
- `0x18000d6a4`
- `0x18000d7ec`
- `0x1800107bc`
- `0x18001085c`
- `0x1800108fc`
- `0x180010998`
- `0x180012dd0`
- `0x180012f40`
- `0x1800130b0`
- `0x180013220`
- `0x180013390`
- `0x18001363c`
- `0x1800136dc`
- `0x180013778`
- `0x180013814`
- `0x1800138b0`
- `0x18001394c`

## callees

- `0x18000fa2c`
- `0x18000fb64`
- `0x180018010`

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
0x18000fa2c  mov     rax, rsp
0x18000fa2f  push    rbx
0x18000fa30  push    rbp
0x18000fa31  push    rsi
0x18000fa32  push    rdi
0x18000fa33  sub     rsp, 58h
0x18000fa37  mov     r11d, [rax+38h]
0x18000fa3b  mov     esi, edx
0x18000fa3d  mov     rbp, rcx
0x18000fa40  test    r11d, r11d
0x18000fa43  jz      loc_18000FB53
0x18000fa49  mov     ebx, [rsp+78h+arg_28]
0x18000fa50  mov     r10d, r11d
0x18000fa53  sub     r10d, 1
0x18000fa57  jz      loc_18000FAE2
0x18000fa5d  sub     r10d, 1
0x18000fa61  jz      short loc_18000FAD4
0x18000fa63  sub     r10d, 1
0x18000fa67  jz      short loc_18000FAC6
0x18000fa69  sub     r10d, 1
0x18000fa6d  jz      short loc_18000FAB8
0x18000fa6f  sub     r10d, 1
0x18000fa73  jz      short loc_18000FAAA
0x18000fa75  cmp     r10d, 1
0x18000fa79  jz      short loc_18000FA9C
0x18000fa7b  sub     r11b, 64h ; 'd'
0x18000fa7f  cmp     r11b, 31h ; '1'
0x18000fa83  ja      short loc_18000FAEF
0x18000fa85  mov     eax, ebx
0x18000fa87  neg     eax
0x18000fa89  movzx   eax, r11b
0x18000fa8d  sbb     ecx, ecx
0x18000fa8f  and     ecx, 0FFFFFFCEh
0x18000fa92  add     ecx, 96h
0x18000fa98  add     ecx, eax
0x18000fa9a  jmp     short loc_18000FAF4
0x18000fa9c  mov     eax, ebx
0x18000fa9e  neg     eax
0x18000faa0  sbb     ecx, ecx
0x18000faa2  and     ecx, 0FFFFFFFEh
0x18000faa5  add     ecx, 0Bh
0x18000faa8  jmp     short loc_18000FAF4
0x18000faaa  mov     eax, ebx
0x18000faac  neg     eax
0x18000faae  sbb     ecx, ecx
0x18000fab0  and     ecx, 0FFFFFFFEh
0x18000fab3  add     ecx, 0Ah
0x18000fab6  jmp     short loc_18000FAF4
0x18000fab8  mov     eax, ebx
0x18000faba  neg     eax
0x18000fabc  sbb     ecx, ecx
0x18000fabe  and     ecx, 0FFFFFFFCh
0x18000fac1  add     ecx, 7
0x18000fac4  jmp     short loc_18000FAF4
0x18000fac6  mov     eax, ebx
0x18000fac8  neg     eax
0x18000faca  sbb     ecx, ecx
0x18000facc  and     ecx, 0FFFFFFFCh
0x18000facf  add     ecx, 6
0x18000fad2  jmp     short loc_18000FAF4
0x18000fad4  mov     eax, ebx
0x18000fad6  neg     eax
0x18000fad8  sbb     ecx, ecx
0x18000fada  and     ecx, 0FFFFFFFCh
0x18000fadd  add     ecx, 5
0x18000fae0  jmp     short loc_18000FAF4
0x18000fae2  mov     eax, ebx
0x18000fae4  neg     eax
0x18000fae6  sbb     ecx, ecx
0x18000fae8  not     ecx
0x18000faea  and     ecx, 4
0x18000faed  jmp     short loc_18000FAF4
0x18000faef  mov     ecx, 0FFh
0x18000faf4  mov     rdi, [rsp+78h+arg_20]
0x18000fafc  mov     al, [rdi+4]
0x18000faff  mov     byte ptr [rsp+78h+var_40], al
0x18000fb03  mov     dword ptr [rsp+78h+var_58], ecx
0x18000fb07  mov     rcx, rbp
0x18000fb0a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000fb0f  test    eax, eax
0x18000fb11  jz      short loc_18000FB53
0x18000fb13  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fb1a  test    rax, rax
0x18000fb1d  jz      short loc_18000FB53
0x18000fb1f  mov     [rsp+78h+var_40], 1
0x18000fb28  lea     rcx, [rsp+78h+arg_30]
0x18000fb30  mov     [rsp+78h+var_48], 0
0x18000fb35  mov     r9d, ebx
0x18000fb38  mov     [rsp+78h+var_50], 0
0x18000fb41  xor     r8d, r8d
0x18000fb44  mov     [rsp+78h+var_58], rcx
0x18000fb49  mov     rdx, rdi
0x18000fb4c  mov     ecx, esi
0x18000fb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb53  add     rsp, 58h
0x18000fb57  pop     rdi
0x18000fb58  pop     rsi
0x18000fb59  pop     rbp
0x18000fb5a  pop     rbx
0x18000fb5b  retn
```
