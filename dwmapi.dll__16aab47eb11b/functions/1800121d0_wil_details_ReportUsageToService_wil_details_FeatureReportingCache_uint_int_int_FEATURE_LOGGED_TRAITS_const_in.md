# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800121d0`
- end: `0x180012300`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180011e50`
- `0x1800120bc`
- `0x180012148`

## callees

- `0x1800121d0`
- `0x180012308`
- `0x180017010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  unsigned int v10; // ecx
  __int64 v11; // [rsp+28h] [rbp-50h]
  __int64 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v10 = a6 == 0 ? 4 : 0;
        break;
      case 2:
        v10 = a6 != 0 ? 1 : 5;
        break;
      case 3:
        v10 = a6 != 0 ? 2 : 6;
        break;
      case 4:
        v10 = a6 != 0 ? 3 : 7;
        break;
      case 5:
        v10 = a6 != 0 ? 8 : 10;
        break;
      case 6:
        v10 = a6 != 0 ? 9 : 11;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
          v10 = 255;
        else
          v10 = (unsigned __int8)(a7 - 100) + (a6 != 0 ? 100 : 150);
        break;
    }
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1, a2, a3, a4, v10, v11, v12, *(_BYTE *)(a5 + 4));
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        LOBYTE(v13) = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v13, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800121d0  mov     rax, rsp
0x1800121d3  push    rbx
0x1800121d4  push    rbp
0x1800121d5  push    rsi
0x1800121d6  push    rdi
0x1800121d7  sub     rsp, 58h
0x1800121db  mov     r11d, [rax+38h]
0x1800121df  mov     esi, edx
0x1800121e1  mov     rbp, rcx
0x1800121e4  test    r11d, r11d
0x1800121e7  jz      loc_1800122F7
0x1800121ed  mov     ebx, [rsp+78h+arg_28]
0x1800121f4  mov     r10d, r11d
0x1800121f7  sub     r10d, 1
0x1800121fb  jz      loc_180012286
0x180012201  sub     r10d, 1
0x180012205  jz      short loc_180012278
0x180012207  sub     r10d, 1
0x18001220b  jz      short loc_18001226A
0x18001220d  sub     r10d, 1
0x180012211  jz      short loc_18001225C
0x180012213  sub     r10d, 1
0x180012217  jz      short loc_18001224E
0x180012219  cmp     r10d, 1
0x18001221d  jz      short loc_180012240
0x18001221f  sub     r11b, 64h ; 'd'
0x180012223  cmp     r11b, 31h ; '1'
0x180012227  ja      short loc_180012293
0x180012229  mov     eax, ebx
0x18001222b  neg     eax
0x18001222d  movzx   eax, r11b
0x180012231  sbb     ecx, ecx
0x180012233  and     ecx, 0FFFFFFCEh
0x180012236  add     ecx, 96h
0x18001223c  add     ecx, eax
0x18001223e  jmp     short loc_180012298
0x180012240  mov     eax, ebx
0x180012242  neg     eax
0x180012244  sbb     ecx, ecx
0x180012246  and     ecx, 0FFFFFFFEh
0x180012249  add     ecx, 0Bh
0x18001224c  jmp     short loc_180012298
0x18001224e  mov     eax, ebx
0x180012250  neg     eax
0x180012252  sbb     ecx, ecx
0x180012254  and     ecx, 0FFFFFFFEh
0x180012257  add     ecx, 0Ah
0x18001225a  jmp     short loc_180012298
0x18001225c  mov     eax, ebx
0x18001225e  neg     eax
0x180012260  sbb     ecx, ecx
0x180012262  and     ecx, 0FFFFFFFCh
0x180012265  add     ecx, 7
0x180012268  jmp     short loc_180012298
0x18001226a  mov     eax, ebx
0x18001226c  neg     eax
0x18001226e  sbb     ecx, ecx
0x180012270  and     ecx, 0FFFFFFFCh
0x180012273  add     ecx, 6
0x180012276  jmp     short loc_180012298
0x180012278  mov     eax, ebx
0x18001227a  neg     eax
0x18001227c  sbb     ecx, ecx
0x18001227e  and     ecx, 0FFFFFFFCh
0x180012281  add     ecx, 5
0x180012284  jmp     short loc_180012298
0x180012286  mov     eax, ebx
0x180012288  neg     eax
0x18001228a  sbb     ecx, ecx
0x18001228c  not     ecx
0x18001228e  and     ecx, 4
0x180012291  jmp     short loc_180012298
0x180012293  mov     ecx, 0FFh
0x180012298  mov     rdi, [rsp+78h+arg_20]
0x1800122a0  mov     al, [rdi+4]
0x1800122a3  mov     byte ptr [rsp+78h+var_40], al
0x1800122a7  mov     dword ptr [rsp+78h+var_58], ecx
0x1800122ab  mov     rcx, rbp
0x1800122ae  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800122b3  test    eax, eax
0x1800122b5  jz      short loc_1800122F7
0x1800122b7  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800122be  test    rax, rax
0x1800122c1  jz      short loc_1800122F7
0x1800122c3  mov     [rsp+78h+var_40], 1
0x1800122cc  lea     rcx, [rsp+78h+arg_30]
0x1800122d4  mov     byte ptr [rsp+78h+var_48], 0
0x1800122d9  mov     r9d, ebx
0x1800122dc  mov     [rsp+78h+var_50], 0
0x1800122e5  xor     r8d, r8d
0x1800122e8  mov     [rsp+78h+var_58], rcx
0x1800122ed  mov     rdx, rdi
0x1800122f0  mov     ecx, esi
0x1800122f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122f7  add     rsp, 58h
0x1800122fb  pop     rdi
0x1800122fc  pop     rsi
0x1800122fd  pop     rbp
0x1800122fe  pop     rbx
0x1800122ff  retn
```
