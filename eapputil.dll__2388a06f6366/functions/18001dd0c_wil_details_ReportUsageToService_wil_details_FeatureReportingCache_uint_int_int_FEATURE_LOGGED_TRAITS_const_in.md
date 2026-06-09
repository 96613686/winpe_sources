# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001dd0c`
- end: `0x18001de44`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001bd78`
- `0x180023af4`
- `0x180023b94`
- `0x180023c34`

## callees

- `0x18001dd0c`
- `0x18001de4c`
- `0x180033010`

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
0x18001dd0c  mov     rax, rsp
0x18001dd0f  push    rbx
0x18001dd10  push    rbp
0x18001dd11  push    rsi
0x18001dd12  push    rdi
0x18001dd13  sub     rsp, 58h
0x18001dd17  mov     r11d, [rax+38h]
0x18001dd1b  mov     esi, edx
0x18001dd1d  mov     rbp, rcx
0x18001dd20  test    r11d, r11d
0x18001dd23  jz      loc_18001DE3B
0x18001dd29  mov     ebx, [rsp+78h+arg_28]
0x18001dd30  mov     r10d, r11d
0x18001dd33  sub     r10d, 1
0x18001dd37  jz      loc_18001DDC2
0x18001dd3d  sub     r10d, 1
0x18001dd41  jz      short loc_18001DDB4
0x18001dd43  sub     r10d, 1
0x18001dd47  jz      short loc_18001DDA6
0x18001dd49  sub     r10d, 1
0x18001dd4d  jz      short loc_18001DD98
0x18001dd4f  sub     r10d, 1
0x18001dd53  jz      short loc_18001DD8A
0x18001dd55  cmp     r10d, 1
0x18001dd59  jz      short loc_18001DD7C
0x18001dd5b  sub     r11b, 64h ; 'd'
0x18001dd5f  cmp     r11b, 31h ; '1'
0x18001dd63  ja      short loc_18001DDCF
0x18001dd65  mov     eax, ebx
0x18001dd67  neg     eax
0x18001dd69  movzx   eax, r11b
0x18001dd6d  sbb     ecx, ecx
0x18001dd6f  and     ecx, 0FFFFFFCEh
0x18001dd72  add     ecx, 96h
0x18001dd78  add     ecx, eax
0x18001dd7a  jmp     short loc_18001DDD4
0x18001dd7c  mov     eax, ebx
0x18001dd7e  neg     eax
0x18001dd80  sbb     ecx, ecx
0x18001dd82  and     ecx, 0FFFFFFFEh
0x18001dd85  add     ecx, 0Bh
0x18001dd88  jmp     short loc_18001DDD4
0x18001dd8a  mov     eax, ebx
0x18001dd8c  neg     eax
0x18001dd8e  sbb     ecx, ecx
0x18001dd90  and     ecx, 0FFFFFFFEh
0x18001dd93  add     ecx, 0Ah
0x18001dd96  jmp     short loc_18001DDD4
0x18001dd98  mov     eax, ebx
0x18001dd9a  neg     eax
0x18001dd9c  sbb     ecx, ecx
0x18001dd9e  and     ecx, 0FFFFFFFCh
0x18001dda1  add     ecx, 7
0x18001dda4  jmp     short loc_18001DDD4
0x18001dda6  mov     eax, ebx
0x18001dda8  neg     eax
0x18001ddaa  sbb     ecx, ecx
0x18001ddac  and     ecx, 0FFFFFFFCh
0x18001ddaf  add     ecx, 6
0x18001ddb2  jmp     short loc_18001DDD4
0x18001ddb4  mov     eax, ebx
0x18001ddb6  neg     eax
0x18001ddb8  sbb     ecx, ecx
0x18001ddba  and     ecx, 0FFFFFFFCh
0x18001ddbd  add     ecx, 5
0x18001ddc0  jmp     short loc_18001DDD4
0x18001ddc2  mov     eax, ebx
0x18001ddc4  neg     eax
0x18001ddc6  sbb     ecx, ecx
0x18001ddc8  not     ecx
0x18001ddca  and     ecx, 4
0x18001ddcd  jmp     short loc_18001DDD4
0x18001ddcf  mov     ecx, 0FFh
0x18001ddd4  mov     rdi, [rsp+78h+arg_20]
0x18001dddc  mov     al, [rdi+4]
0x18001dddf  mov     byte ptr [rsp+78h+var_40], al
0x18001dde3  mov     dword ptr [rsp+78h+var_50], 0
0x18001ddeb  mov     dword ptr [rsp+78h+var_58], ecx
0x18001ddef  mov     rcx, rbp
0x18001ddf2  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001ddf7  test    eax, eax
0x18001ddf9  jz      short loc_18001DE3B
0x18001ddfb  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001de02  test    rax, rax
0x18001de05  jz      short loc_18001DE3B
0x18001de07  mov     [rsp+78h+var_40], 1
0x18001de10  lea     rcx, [rsp+78h+arg_30]
0x18001de18  mov     [rsp+78h+var_48], 0
0x18001de1d  mov     r9d, ebx
0x18001de20  mov     [rsp+78h+var_50], 0
0x18001de29  xor     r8d, r8d
0x18001de2c  mov     [rsp+78h+var_58], rcx
0x18001de31  mov     rdx, rdi
0x18001de34  mov     ecx, esi
0x18001de36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de3b  add     rsp, 58h
0x18001de3f  pop     rdi
0x18001de40  pop     rsi
0x18001de41  pop     rbp
0x18001de42  pop     rbx
0x18001de43  retn
```
