# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180010330`
- end: `0x180010460`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `10`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009934`
- `0x180009aa4`
- `0x180009c14`
- `0x180009d5c`
- `0x180011ff4`
- `0x180012090`
- `0x180012130`
- `0x1800121cc`
- `0x180012268`
- `0x180012304`

## callees

- `0x180010330`
- `0x180010468`
- `0x180014010`

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
0x180010330  mov     rax, rsp
0x180010333  push    rbx
0x180010334  push    rbp
0x180010335  push    rsi
0x180010336  push    rdi
0x180010337  sub     rsp, 58h
0x18001033b  mov     r11d, [rax+38h]
0x18001033f  mov     esi, edx
0x180010341  mov     rbp, rcx
0x180010344  test    r11d, r11d
0x180010347  jz      loc_180010457
0x18001034d  mov     ebx, [rsp+78h+arg_28]
0x180010354  mov     r10d, r11d
0x180010357  sub     r10d, 1
0x18001035b  jz      loc_1800103E6
0x180010361  sub     r10d, 1
0x180010365  jz      short loc_1800103D8
0x180010367  sub     r10d, 1
0x18001036b  jz      short loc_1800103CA
0x18001036d  sub     r10d, 1
0x180010371  jz      short loc_1800103BC
0x180010373  sub     r10d, 1
0x180010377  jz      short loc_1800103AE
0x180010379  cmp     r10d, 1
0x18001037d  jz      short loc_1800103A0
0x18001037f  sub     r11b, 64h ; 'd'
0x180010383  cmp     r11b, 31h ; '1'
0x180010387  ja      short loc_1800103F3
0x180010389  mov     eax, ebx
0x18001038b  neg     eax
0x18001038d  movzx   eax, r11b
0x180010391  sbb     ecx, ecx
0x180010393  and     ecx, 0FFFFFFCEh
0x180010396  add     ecx, 96h
0x18001039c  add     ecx, eax
0x18001039e  jmp     short loc_1800103F8
0x1800103a0  mov     eax, ebx
0x1800103a2  neg     eax
0x1800103a4  sbb     ecx, ecx
0x1800103a6  and     ecx, 0FFFFFFFEh
0x1800103a9  add     ecx, 0Bh
0x1800103ac  jmp     short loc_1800103F8
0x1800103ae  mov     eax, ebx
0x1800103b0  neg     eax
0x1800103b2  sbb     ecx, ecx
0x1800103b4  and     ecx, 0FFFFFFFEh
0x1800103b7  add     ecx, 0Ah
0x1800103ba  jmp     short loc_1800103F8
0x1800103bc  mov     eax, ebx
0x1800103be  neg     eax
0x1800103c0  sbb     ecx, ecx
0x1800103c2  and     ecx, 0FFFFFFFCh
0x1800103c5  add     ecx, 7
0x1800103c8  jmp     short loc_1800103F8
0x1800103ca  mov     eax, ebx
0x1800103cc  neg     eax
0x1800103ce  sbb     ecx, ecx
0x1800103d0  and     ecx, 0FFFFFFFCh
0x1800103d3  add     ecx, 6
0x1800103d6  jmp     short loc_1800103F8
0x1800103d8  mov     eax, ebx
0x1800103da  neg     eax
0x1800103dc  sbb     ecx, ecx
0x1800103de  and     ecx, 0FFFFFFFCh
0x1800103e1  add     ecx, 5
0x1800103e4  jmp     short loc_1800103F8
0x1800103e6  mov     eax, ebx
0x1800103e8  neg     eax
0x1800103ea  sbb     ecx, ecx
0x1800103ec  not     ecx
0x1800103ee  and     ecx, 4
0x1800103f1  jmp     short loc_1800103F8
0x1800103f3  mov     ecx, 0FFh
0x1800103f8  mov     rdi, [rsp+78h+arg_20]
0x180010400  mov     al, [rdi+4]
0x180010403  mov     byte ptr [rsp+78h+var_40], al
0x180010407  mov     dword ptr [rsp+78h+var_58], ecx
0x18001040b  mov     rcx, rbp
0x18001040e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180010413  test    eax, eax
0x180010415  jz      short loc_180010457
0x180010417  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001041e  test    rax, rax
0x180010421  jz      short loc_180010457
0x180010423  mov     [rsp+78h+var_40], 1
0x18001042c  lea     rcx, [rsp+78h+arg_30]
0x180010434  mov     [rsp+78h+var_48], 0
0x180010439  mov     r9d, ebx
0x18001043c  mov     [rsp+78h+var_50], 0
0x180010445  xor     r8d, r8d
0x180010448  mov     [rsp+78h+var_58], rcx
0x18001044d  mov     rdx, rdi
0x180010450  mov     ecx, esi
0x180010452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010457  add     rsp, 58h
0x18001045b  pop     rdi
0x18001045c  pop     rsi
0x18001045d  pop     rbp
0x18001045e  pop     rbx
0x18001045f  retn
```
