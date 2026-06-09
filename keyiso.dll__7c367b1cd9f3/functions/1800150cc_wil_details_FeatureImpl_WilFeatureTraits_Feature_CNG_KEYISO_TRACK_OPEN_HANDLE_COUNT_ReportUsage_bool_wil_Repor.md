# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x1800150cc`
- end: `0x18001519e`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180016744`

## callees

- `0x1800102ac`
- `0x180012f98`
- `0x1800150cc`
- `0x1800151a4`
- `0x180019010`

## pseudocode

```c
__int64 (__fastcall *wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::ReportUsage(
        __int64 a1,
        unsigned __int8 a2,
        char a3,
        ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // r10d
  __int64 v7; // rdx
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v9; // [rsp+28h] [rbp-30h]
  __int64 v10; // [rsp+30h] [rbp-28h]
  int v11; // [rsp+30h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v14 = va_arg(va1, _QWORD);
  LOBYTE(v13) = a3;
  v4 = a2;
  if ( (*(_DWORD *)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor & 4) == 0 )
    v12 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetCachedFeatureEnabledState(
             (wil::details *)a1,
             &v12);
  WORD2(v14) = 2;
  LODWORD(v14) = 0;
  v13 = 3;
  v5 = wil_details_MapReportingKind(3, v4);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     (struct wil_details_FeatureReportingCache *)(a1 + 8),
                                                                                                     v7,
                                                                                                     (v6 >> 10) & 1,
                                                                                                     (v6 >> 11) & 1,
                                                                                                     v5,
                                                                                                     v9,
                                                                                                     v10,
                                                                                                     2);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      LOBYTE(v11) = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(52061724, (__int64 *)va, 0, v4, &v13, 0, v11, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800150cc  mov     r11, rsp
0x1800150cf  mov     [r11+10h], rbx
0x1800150d3  mov     [r11+20h], r9
0x1800150d7  mov     [r11+18h], r8b
0x1800150db  push    rdi
0x1800150dc  sub     rsp, 50h
0x1800150e0  mov     rax, cs:Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__descriptor
0x1800150e7  mov     rdi, rcx
0x1800150ea  movzx   ebx, dl
0x1800150ed  mov     r10d, [rax]
0x1800150f0  test    r10b, 4
0x1800150f4  jnz     short loc_18001510A
0x1800150f6  lea     rdx, [r11+8]
0x1800150fa  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetCachedFeatureEnabledState(void)
0x1800150ff  mov     r8, [rax]
0x180015102  mov     [rsp+58h+arg_0], r8
0x180015107  mov     r10d, r8d
0x18001510a  xor     eax, eax
0x18001510c  mov     word ptr [rsp+58h+arg_18+4], 2
0x180015113  mov     edx, ebx
0x180015115  mov     dword ptr [rsp+58h+arg_18], eax
0x180015119  lea     ecx, [rax+3]
0x18001511c  mov     [rsp+58h+arg_10], ecx
0x180015120  call    wil_details_MapReportingKind
0x180015125  mov     r9d, r10d
0x180015128  mov     byte ptr [rsp+58h+var_20], 2
0x18001512d  shr     r10d, 0Ah
0x180015131  lea     rcx, [rdi+8]
0x180015135  and     r10d, 1
0x180015139  shr     r9d, 0Bh
0x18001513d  mov     r8d, r10d
0x180015140  mov     dword ptr [rsp+58h+var_38], eax
0x180015144  and     r9d, 1
0x180015148  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001514d  test    eax, eax
0x18001514f  jz      short loc_180015193
0x180015151  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180015158  test    rax, rax
0x18001515b  jz      short loc_180015193
0x18001515d  mov     [rsp+58h+var_20], 1
0x180015166  lea     rcx, [rsp+58h+arg_10]
0x18001516b  mov     byte ptr [rsp+58h+var_28], 0
0x180015170  lea     rdx, [rsp+58h+arg_18]
0x180015175  mov     [rsp+58h+var_30], 0
0x18001517e  mov     r9d, ebx
0x180015181  mov     [rsp+58h+var_38], rcx
0x180015186  xor     r8d, r8d
0x180015189  mov     ecx, 31A661Ch
0x18001518e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015193  mov     rbx, [rsp+58h+arg_8]
0x180015198  add     rsp, 50h
0x18001519c  pop     rdi
0x18001519d  retn
```
