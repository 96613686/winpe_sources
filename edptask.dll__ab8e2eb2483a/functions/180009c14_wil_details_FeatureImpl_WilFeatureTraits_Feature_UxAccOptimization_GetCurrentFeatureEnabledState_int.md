# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180009c14`
- end: `0x180009d56`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800094f0`

## callees

- `0x1800091b0`
- `0x180009c14`
- `0x180010330`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(48433719, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_18001DD00, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180009c14  mov     [rsp+arg_10], rbx
0x180009c19  mov     [rsp+arg_18], rsi
0x180009c1e  mov     [rsp+arg_0], rcx
0x180009c23  push    rdi
0x180009c24  sub     rsp, 40h
0x180009c28  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009c2f  mov     rbx, rdx
0x180009c32  test    rax, rax
0x180009c35  jz      short loc_180009C4A
0x180009c37  mov     edx, 3
0x180009c3c  mov     ecx, 2E30A37h
0x180009c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c46  mov     edx, eax
0x180009c48  jmp     short loc_180009C58
0x180009c4a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009c51  test    rax, rax
0x180009c54  jnz     short loc_180009C37
0x180009c56  xor     edx, edx
0x180009c58  mov     r8d, edx
0x180009c5b  mov     qword ptr [rbx], 0
0x180009c62  and     r8d, 0FFFFFF3Fh
0x180009c69  mov     eax, edx
0x180009c6b  and     edx, 80h
0x180009c71  mov     ecx, r8d
0x180009c74  and     ecx, 3
0x180009c77  mov     esi, 40h ; '@'
0x180009c7c  shl     ecx, 2
0x180009c7f  and     eax, esi
0x180009c81  or      ecx, eax
0x180009c83  shl     ecx, 2
0x180009c86  or      ecx, edx
0x180009c88  shl     ecx, 3
0x180009c8b  test    r8d, r8d
0x180009c8e  jnz     short loc_180009C97
0x180009c90  mov     edx, esi
0x180009c92  mov     r8d, esi
0x180009c95  jmp     short loc_180009CA3
0x180009c97  xor     edx, edx
0x180009c99  cmp     r8d, 2
0x180009c9d  cmovz   edx, esi
0x180009ca0  mov     r8d, edx
0x180009ca3  mov     eax, ecx
0x180009ca5  mov     edi, 1
0x180009caa  or      eax, r8d
0x180009cad  or      ecx, edx
0x180009caf  mov     [rbx], eax
0x180009cb1  bt      ecx, 0Ah
0x180009cb5  jnb     short loc_180009CBF
0x180009cb7  cmp     ecx, 800h
0x180009cbd  jnb     short loc_180009CC6
0x180009cbf  xor     dl, dl
0x180009cc1  test    sil, cl
0x180009cc4  jz      short loc_180009D2F
0x180009cc6  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180009ccd  mov     r8d, [rax]
0x180009cd0  test    r8b, 4
0x180009cd4  jnz     short loc_180009CEB
0x180009cd6  lea     rdx, [rsp+48h+arg_8]
0x180009cdb  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180009ce0  mov     rcx, [rax]
0x180009ce3  mov     [rsp+48h+arg_8], rcx
0x180009ce8  mov     r8d, ecx
0x180009ceb  xor     eax, eax
0x180009ced  mov     word ptr [rsp+48h+arg_0+4], 3
0x180009cf4  mov     r9d, r8d
0x180009cf7  mov     [rsp+48h+var_18], eax
0x180009cfb  mov     dword ptr [rsp+48h+arg_0], eax
0x180009cff  lea     rcx, qword_18001DD00
0x180009d06  shr     r9d, 0Bh
0x180009d0a  lea     rax, [rsp+48h+arg_0]
0x180009d0f  shr     r8d, 0Ah
0x180009d13  and     r9d, edi
0x180009d16  and     r8d, edi
0x180009d19  mov     [rsp+48h+var_20], edi
0x180009d1d  mov     edx, 2F29A04h
0x180009d22  mov     [rsp+48h+var_28], rax
0x180009d27  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009d2c  mov     dl, dil
0x180009d2f  mov     eax, [rbx]
0x180009d31  test    sil, al
0x180009d34  jz      short loc_180009D3A
0x180009d36  test    dl, dl
0x180009d38  jnz     short loc_180009D3C
0x180009d3a  xor     edi, edi
0x180009d3c  mov     rsi, [rsp+48h+arg_18]
0x180009d41  and     eax, 0FFFFFFFEh
0x180009d44  or      eax, edi
0x180009d46  mov     [rbx], eax
0x180009d48  mov     rax, rbx
0x180009d4b  mov     rbx, [rsp+48h+arg_10]
0x180009d50  add     rsp, 40h
0x180009d54  pop     rdi
0x180009d55  retn
```
