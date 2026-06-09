# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000b8ac`
- end: `0x18000b9dc`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000b384`
- `0x18000be20`
- `0x18000bec0`

## callees

- `0x18000b8ac`
- `0x18000b9e4`
- `0x180017010`

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
0x18000b8ac  mov     rax, rsp
0x18000b8af  push    rbx
0x18000b8b0  push    rbp
0x18000b8b1  push    rsi
0x18000b8b2  push    rdi
0x18000b8b3  sub     rsp, 58h
0x18000b8b7  mov     r11d, [rax+38h]
0x18000b8bb  mov     esi, edx
0x18000b8bd  mov     rbp, rcx
0x18000b8c0  test    r11d, r11d
0x18000b8c3  jz      loc_18000B9D3
0x18000b8c9  mov     ebx, [rsp+78h+arg_28]
0x18000b8d0  mov     r10d, r11d
0x18000b8d3  sub     r10d, 1
0x18000b8d7  jz      loc_18000B962
0x18000b8dd  sub     r10d, 1
0x18000b8e1  jz      short loc_18000B954
0x18000b8e3  sub     r10d, 1
0x18000b8e7  jz      short loc_18000B946
0x18000b8e9  sub     r10d, 1
0x18000b8ed  jz      short loc_18000B938
0x18000b8ef  sub     r10d, 1
0x18000b8f3  jz      short loc_18000B92A
0x18000b8f5  cmp     r10d, 1
0x18000b8f9  jz      short loc_18000B91C
0x18000b8fb  sub     r11b, 64h ; 'd'
0x18000b8ff  cmp     r11b, 31h ; '1'
0x18000b903  ja      short loc_18000B96F
0x18000b905  mov     eax, ebx
0x18000b907  neg     eax
0x18000b909  movzx   eax, r11b
0x18000b90d  sbb     ecx, ecx
0x18000b90f  and     ecx, 0FFFFFFCEh
0x18000b912  add     ecx, 96h
0x18000b918  add     ecx, eax
0x18000b91a  jmp     short loc_18000B974
0x18000b91c  mov     eax, ebx
0x18000b91e  neg     eax
0x18000b920  sbb     ecx, ecx
0x18000b922  and     ecx, 0FFFFFFFEh
0x18000b925  add     ecx, 0Bh
0x18000b928  jmp     short loc_18000B974
0x18000b92a  mov     eax, ebx
0x18000b92c  neg     eax
0x18000b92e  sbb     ecx, ecx
0x18000b930  and     ecx, 0FFFFFFFEh
0x18000b933  add     ecx, 0Ah
0x18000b936  jmp     short loc_18000B974
0x18000b938  mov     eax, ebx
0x18000b93a  neg     eax
0x18000b93c  sbb     ecx, ecx
0x18000b93e  and     ecx, 0FFFFFFFCh
0x18000b941  add     ecx, 7
0x18000b944  jmp     short loc_18000B974
0x18000b946  mov     eax, ebx
0x18000b948  neg     eax
0x18000b94a  sbb     ecx, ecx
0x18000b94c  and     ecx, 0FFFFFFFCh
0x18000b94f  add     ecx, 6
0x18000b952  jmp     short loc_18000B974
0x18000b954  mov     eax, ebx
0x18000b956  neg     eax
0x18000b958  sbb     ecx, ecx
0x18000b95a  and     ecx, 0FFFFFFFCh
0x18000b95d  add     ecx, 5
0x18000b960  jmp     short loc_18000B974
0x18000b962  mov     eax, ebx
0x18000b964  neg     eax
0x18000b966  sbb     ecx, ecx
0x18000b968  not     ecx
0x18000b96a  and     ecx, 4
0x18000b96d  jmp     short loc_18000B974
0x18000b96f  mov     ecx, 0FFh
0x18000b974  mov     rdi, [rsp+78h+arg_20]
0x18000b97c  mov     al, [rdi+4]
0x18000b97f  mov     byte ptr [rsp+78h+var_40], al
0x18000b983  mov     dword ptr [rsp+78h+var_58], ecx
0x18000b987  mov     rcx, rbp
0x18000b98a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000b98f  test    eax, eax
0x18000b991  jz      short loc_18000B9D3
0x18000b993  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000b99a  test    rax, rax
0x18000b99d  jz      short loc_18000B9D3
0x18000b99f  mov     [rsp+78h+var_40], 1
0x18000b9a8  lea     rcx, [rsp+78h+arg_30]
0x18000b9b0  mov     [rsp+78h+var_48], 0
0x18000b9b5  mov     r9d, ebx
0x18000b9b8  mov     [rsp+78h+var_50], 0
0x18000b9c1  xor     r8d, r8d
0x18000b9c4  mov     [rsp+78h+var_58], rcx
0x18000b9c9  mov     rdx, rdi
0x18000b9cc  mov     ecx, esi
0x18000b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d3  add     rsp, 58h
0x18000b9d7  pop     rdi
0x18000b9d8  pop     rsi
0x18000b9d9  pop     rbp
0x18000b9da  pop     rbx
0x18000b9db  retn
```
