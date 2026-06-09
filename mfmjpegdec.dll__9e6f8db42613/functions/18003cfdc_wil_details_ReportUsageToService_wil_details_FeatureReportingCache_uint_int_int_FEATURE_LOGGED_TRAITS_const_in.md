# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18003cfdc`
- end: `0x18003d10c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003ce48`
- `0x18003ced0`
- `0x18003cf54`
- `0x1800409ac`
- `0x180042814`
- `0x180059f1c`
- `0x18005f2a8`

## callees

- `0x18003cfdc`
- `0x18003d114`
- `0x180070010`

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
0x18003cfdc  mov     rax, rsp
0x18003cfdf  push    rbx
0x18003cfe0  push    rbp
0x18003cfe1  push    rsi
0x18003cfe2  push    rdi
0x18003cfe3  sub     rsp, 58h
0x18003cfe7  mov     r11d, [rax+38h]
0x18003cfeb  mov     esi, edx
0x18003cfed  mov     rbp, rcx
0x18003cff0  test    r11d, r11d
0x18003cff3  jz      loc_18003D103
0x18003cff9  mov     ebx, [rsp+78h+arg_28]
0x18003d000  mov     r10d, r11d
0x18003d003  sub     r10d, 1
0x18003d007  jz      loc_18003D092
0x18003d00d  sub     r10d, 1
0x18003d011  jz      short loc_18003D084
0x18003d013  sub     r10d, 1
0x18003d017  jz      short loc_18003D076
0x18003d019  sub     r10d, 1
0x18003d01d  jz      short loc_18003D068
0x18003d01f  sub     r10d, 1
0x18003d023  jz      short loc_18003D05A
0x18003d025  cmp     r10d, 1
0x18003d029  jz      short loc_18003D04C
0x18003d02b  sub     r11b, 64h ; 'd'
0x18003d02f  cmp     r11b, 31h ; '1'
0x18003d033  ja      short loc_18003D09F
0x18003d035  mov     eax, ebx
0x18003d037  neg     eax
0x18003d039  movzx   eax, r11b
0x18003d03d  sbb     ecx, ecx
0x18003d03f  and     ecx, 0FFFFFFCEh
0x18003d042  add     ecx, 96h
0x18003d048  add     ecx, eax
0x18003d04a  jmp     short loc_18003D0A4
0x18003d04c  mov     eax, ebx
0x18003d04e  neg     eax
0x18003d050  sbb     ecx, ecx
0x18003d052  and     ecx, 0FFFFFFFEh
0x18003d055  add     ecx, 0Bh
0x18003d058  jmp     short loc_18003D0A4
0x18003d05a  mov     eax, ebx
0x18003d05c  neg     eax
0x18003d05e  sbb     ecx, ecx
0x18003d060  and     ecx, 0FFFFFFFEh
0x18003d063  add     ecx, 0Ah
0x18003d066  jmp     short loc_18003D0A4
0x18003d068  mov     eax, ebx
0x18003d06a  neg     eax
0x18003d06c  sbb     ecx, ecx
0x18003d06e  and     ecx, 0FFFFFFFCh
0x18003d071  add     ecx, 7
0x18003d074  jmp     short loc_18003D0A4
0x18003d076  mov     eax, ebx
0x18003d078  neg     eax
0x18003d07a  sbb     ecx, ecx
0x18003d07c  and     ecx, 0FFFFFFFCh
0x18003d07f  add     ecx, 6
0x18003d082  jmp     short loc_18003D0A4
0x18003d084  mov     eax, ebx
0x18003d086  neg     eax
0x18003d088  sbb     ecx, ecx
0x18003d08a  and     ecx, 0FFFFFFFCh
0x18003d08d  add     ecx, 5
0x18003d090  jmp     short loc_18003D0A4
0x18003d092  mov     eax, ebx
0x18003d094  neg     eax
0x18003d096  sbb     ecx, ecx
0x18003d098  not     ecx
0x18003d09a  and     ecx, 4
0x18003d09d  jmp     short loc_18003D0A4
0x18003d09f  mov     ecx, 0FFh
0x18003d0a4  mov     rdi, [rsp+78h+arg_20]
0x18003d0ac  mov     al, [rdi+4]
0x18003d0af  mov     byte ptr [rsp+78h+var_40], al
0x18003d0b3  mov     dword ptr [rsp+78h+var_58], ecx
0x18003d0b7  mov     rcx, rbp
0x18003d0ba  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18003d0bf  test    eax, eax
0x18003d0c1  jz      short loc_18003D103
0x18003d0c3  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18003d0ca  test    rax, rax
0x18003d0cd  jz      short loc_18003D103
0x18003d0cf  mov     [rsp+78h+var_40], 1
0x18003d0d8  lea     rcx, [rsp+78h+arg_30]
0x18003d0e0  mov     [rsp+78h+var_48], 0
0x18003d0e5  mov     r9d, ebx
0x18003d0e8  mov     [rsp+78h+var_50], 0
0x18003d0f1  xor     r8d, r8d
0x18003d0f4  mov     [rsp+78h+var_58], rcx
0x18003d0f9  mov     rdx, rdi
0x18003d0fc  mov     ecx, esi
0x18003d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d103  add     rsp, 58h
0x18003d107  pop     rdi
0x18003d108  pop     rsi
0x18003d109  pop     rbp
0x18003d10a  pop     rbx
0x18003d10b  retn
```
