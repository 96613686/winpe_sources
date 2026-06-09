# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000cbbc`
- end: `0x18000ccfe`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c6c4`

## callees

- `0x18000c544`
- `0x18000cbbc`
- `0x180010550`
- `0x180023010`

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
    wil::details::ReportUsageToService(&qword_18002F6B8, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x18000cbbc  mov     [rsp+arg_10], rbx
0x18000cbc1  mov     [rsp+arg_18], rsi
0x18000cbc6  mov     [rsp+arg_0], rcx
0x18000cbcb  push    rdi
0x18000cbcc  sub     rsp, 40h
0x18000cbd0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000cbd7  mov     rbx, rdx
0x18000cbda  test    rax, rax
0x18000cbdd  jz      short loc_18000CBF2
0x18000cbdf  mov     edx, 3
0x18000cbe4  mov     ecx, 2E30A37h
0x18000cbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbee  mov     edx, eax
0x18000cbf0  jmp     short loc_18000CC00
0x18000cbf2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000cbf9  test    rax, rax
0x18000cbfc  jnz     short loc_18000CBDF
0x18000cbfe  xor     edx, edx
0x18000cc00  mov     r8d, edx
0x18000cc03  mov     qword ptr [rbx], 0
0x18000cc0a  and     r8d, 0FFFFFF3Fh
0x18000cc11  mov     eax, edx
0x18000cc13  and     edx, 80h
0x18000cc19  mov     ecx, r8d
0x18000cc1c  and     ecx, 3
0x18000cc1f  mov     esi, 40h ; '@'
0x18000cc24  shl     ecx, 2
0x18000cc27  and     eax, esi
0x18000cc29  or      ecx, eax
0x18000cc2b  shl     ecx, 2
0x18000cc2e  or      ecx, edx
0x18000cc30  shl     ecx, 3
0x18000cc33  test    r8d, r8d
0x18000cc36  jnz     short loc_18000CC3F
0x18000cc38  mov     edx, esi
0x18000cc3a  mov     r8d, esi
0x18000cc3d  jmp     short loc_18000CC4B
0x18000cc3f  xor     edx, edx
0x18000cc41  cmp     r8d, 2
0x18000cc45  cmovz   edx, esi
0x18000cc48  mov     r8d, edx
0x18000cc4b  mov     eax, ecx
0x18000cc4d  mov     edi, 1
0x18000cc52  or      eax, r8d
0x18000cc55  or      ecx, edx
0x18000cc57  mov     [rbx], eax
0x18000cc59  bt      ecx, 0Ah
0x18000cc5d  jnb     short loc_18000CC67
0x18000cc5f  cmp     ecx, 800h
0x18000cc65  jnb     short loc_18000CC6E
0x18000cc67  xor     dl, dl
0x18000cc69  test    sil, cl
0x18000cc6c  jz      short loc_18000CCD7
0x18000cc6e  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18000cc75  mov     r8d, [rax]
0x18000cc78  test    r8b, 4
0x18000cc7c  jnz     short loc_18000CC93
0x18000cc7e  lea     rdx, [rsp+48h+arg_8]
0x18000cc83  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18000cc88  mov     rcx, [rax]
0x18000cc8b  mov     [rsp+48h+arg_8], rcx
0x18000cc90  mov     r8d, ecx
0x18000cc93  xor     eax, eax
0x18000cc95  mov     word ptr [rsp+48h+arg_0+4], 3
0x18000cc9c  mov     r9d, r8d
0x18000cc9f  mov     [rsp+48h+var_18], eax
0x18000cca3  mov     dword ptr [rsp+48h+arg_0], eax
0x18000cca7  lea     rcx, qword_18002F6B8
0x18000ccae  shr     r9d, 0Bh
0x18000ccb2  lea     rax, [rsp+48h+arg_0]
0x18000ccb7  shr     r8d, 0Ah
0x18000ccbb  and     r9d, edi
0x18000ccbe  and     r8d, edi
0x18000ccc1  mov     [rsp+48h+var_20], edi
0x18000ccc5  mov     edx, 2F29A04h
0x18000ccca  mov     [rsp+48h+var_28], rax
0x18000cccf  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ccd4  mov     dl, dil
0x18000ccd7  mov     eax, [rbx]
0x18000ccd9  test    sil, al
0x18000ccdc  jz      short loc_18000CCE2
0x18000ccde  test    dl, dl
0x18000cce0  jnz     short loc_18000CCE4
0x18000cce2  xor     edi, edi
0x18000cce4  mov     rsi, [rsp+48h+arg_18]
0x18000cce9  and     eax, 0FFFFFFFEh
0x18000ccec  or      eax, edi
0x18000ccee  mov     [rbx], eax
0x18000ccf0  mov     rax, rbx
0x18000ccf3  mov     rbx, [rsp+48h+arg_10]
0x18000ccf8  add     rsp, 40h
0x18000ccfc  pop     rdi
0x18000ccfd  retn
```
