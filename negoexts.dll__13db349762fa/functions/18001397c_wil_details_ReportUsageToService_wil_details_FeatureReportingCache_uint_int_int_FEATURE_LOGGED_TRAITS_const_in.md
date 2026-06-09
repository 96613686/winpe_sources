# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001397c`
- end: `0x180013aac`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013868`
- `0x1800138f0`
- `0x180019e60`

## callees

- `0x18001397c`
- `0x180013ab4`
- `0x180020010`

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
0x18001397c  mov     rax, rsp
0x18001397f  push    rbx
0x180013980  push    rbp
0x180013981  push    rsi
0x180013982  push    rdi
0x180013983  sub     rsp, 58h
0x180013987  mov     r11d, [rax+38h]
0x18001398b  mov     esi, edx
0x18001398d  mov     rbp, rcx
0x180013990  test    r11d, r11d
0x180013993  jz      loc_180013AA3
0x180013999  mov     ebx, [rsp+78h+arg_28]
0x1800139a0  mov     r10d, r11d
0x1800139a3  sub     r10d, 1
0x1800139a7  jz      loc_180013A32
0x1800139ad  sub     r10d, 1
0x1800139b1  jz      short loc_180013A24
0x1800139b3  sub     r10d, 1
0x1800139b7  jz      short loc_180013A16
0x1800139b9  sub     r10d, 1
0x1800139bd  jz      short loc_180013A08
0x1800139bf  sub     r10d, 1
0x1800139c3  jz      short loc_1800139FA
0x1800139c5  cmp     r10d, 1
0x1800139c9  jz      short loc_1800139EC
0x1800139cb  sub     r11b, 64h ; 'd'
0x1800139cf  cmp     r11b, 31h ; '1'
0x1800139d3  ja      short loc_180013A3F
0x1800139d5  mov     eax, ebx
0x1800139d7  neg     eax
0x1800139d9  movzx   eax, r11b
0x1800139dd  sbb     ecx, ecx
0x1800139df  and     ecx, 0FFFFFFCEh
0x1800139e2  add     ecx, 96h
0x1800139e8  add     ecx, eax
0x1800139ea  jmp     short loc_180013A44
0x1800139ec  mov     eax, ebx
0x1800139ee  neg     eax
0x1800139f0  sbb     ecx, ecx
0x1800139f2  and     ecx, 0FFFFFFFEh
0x1800139f5  add     ecx, 0Bh
0x1800139f8  jmp     short loc_180013A44
0x1800139fa  mov     eax, ebx
0x1800139fc  neg     eax
0x1800139fe  sbb     ecx, ecx
0x180013a00  and     ecx, 0FFFFFFFEh
0x180013a03  add     ecx, 0Ah
0x180013a06  jmp     short loc_180013A44
0x180013a08  mov     eax, ebx
0x180013a0a  neg     eax
0x180013a0c  sbb     ecx, ecx
0x180013a0e  and     ecx, 0FFFFFFFCh
0x180013a11  add     ecx, 7
0x180013a14  jmp     short loc_180013A44
0x180013a16  mov     eax, ebx
0x180013a18  neg     eax
0x180013a1a  sbb     ecx, ecx
0x180013a1c  and     ecx, 0FFFFFFFCh
0x180013a1f  add     ecx, 6
0x180013a22  jmp     short loc_180013A44
0x180013a24  mov     eax, ebx
0x180013a26  neg     eax
0x180013a28  sbb     ecx, ecx
0x180013a2a  and     ecx, 0FFFFFFFCh
0x180013a2d  add     ecx, 5
0x180013a30  jmp     short loc_180013A44
0x180013a32  mov     eax, ebx
0x180013a34  neg     eax
0x180013a36  sbb     ecx, ecx
0x180013a38  not     ecx
0x180013a3a  and     ecx, 4
0x180013a3d  jmp     short loc_180013A44
0x180013a3f  mov     ecx, 0FFh
0x180013a44  mov     rdi, [rsp+78h+arg_20]
0x180013a4c  mov     al, [rdi+4]
0x180013a4f  mov     byte ptr [rsp+78h+var_40], al
0x180013a53  mov     dword ptr [rsp+78h+var_58], ecx
0x180013a57  mov     rcx, rbp
0x180013a5a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180013a5f  test    eax, eax
0x180013a61  jz      short loc_180013AA3
0x180013a63  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180013a6a  test    rax, rax
0x180013a6d  jz      short loc_180013AA3
0x180013a6f  mov     [rsp+78h+var_40], 1
0x180013a78  lea     rcx, [rsp+78h+arg_30]
0x180013a80  mov     byte ptr [rsp+78h+var_48], 0
0x180013a85  mov     r9d, ebx
0x180013a88  mov     [rsp+78h+var_50], 0
0x180013a91  xor     r8d, r8d
0x180013a94  mov     [rsp+78h+var_58], rcx
0x180013a99  mov     rdx, rdi
0x180013a9c  mov     ecx, esi
0x180013a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aa3  add     rsp, 58h
0x180013aa7  pop     rdi
0x180013aa8  pop     rsi
0x180013aa9  pop     rbp
0x180013aaa  pop     rbx
0x180013aab  retn
```
