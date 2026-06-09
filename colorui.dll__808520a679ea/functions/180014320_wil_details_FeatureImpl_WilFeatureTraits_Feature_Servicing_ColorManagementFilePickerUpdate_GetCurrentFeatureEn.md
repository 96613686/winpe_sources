# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014320`
- end: `0x180014462`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180014030`

## callees

- `0x180014110`
- `0x180014320`
- `0x180015980`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate>::GetCurrentFeatureEnabledState(
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
    v4 = v2(52147586, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_24_08_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_24_08_NonSec__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_24_08_NonSec>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180021DB8, 45034786, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180014320  mov     [rsp+arg_10], rbx
0x180014325  mov     [rsp+arg_18], rsi
0x18001432a  mov     [rsp+arg_0], rcx
0x18001432f  push    rdi
0x180014330  sub     rsp, 40h
0x180014334  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001433b  mov     rbx, rdx
0x18001433e  test    rax, rax
0x180014341  jz      short loc_180014356
0x180014343  mov     edx, 3
0x180014348  mov     ecx, 31BB582h
0x18001434d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014352  mov     edx, eax
0x180014354  jmp     short loc_180014364
0x180014356  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001435d  test    rax, rax
0x180014360  jnz     short loc_180014343
0x180014362  xor     edx, edx
0x180014364  mov     r8d, edx
0x180014367  mov     qword ptr [rbx], 0
0x18001436e  and     r8d, 0FFFFFF3Fh
0x180014375  mov     eax, edx
0x180014377  and     edx, 80h
0x18001437d  mov     ecx, r8d
0x180014380  and     ecx, 3
0x180014383  mov     esi, 40h ; '@'
0x180014388  shl     ecx, 2
0x18001438b  and     eax, esi
0x18001438d  or      ecx, eax
0x18001438f  shl     ecx, 2
0x180014392  or      ecx, edx
0x180014394  shl     ecx, 3
0x180014397  test    r8d, r8d
0x18001439a  jnz     short loc_1800143A3
0x18001439c  mov     edx, esi
0x18001439e  mov     r8d, esi
0x1800143a1  jmp     short loc_1800143AF
0x1800143a3  xor     edx, edx
0x1800143a5  cmp     r8d, 2
0x1800143a9  cmovz   edx, esi
0x1800143ac  mov     r8d, edx
0x1800143af  mov     eax, ecx
0x1800143b1  mov     edi, 1
0x1800143b6  or      eax, r8d
0x1800143b9  or      ecx, edx
0x1800143bb  mov     [rbx], eax
0x1800143bd  bt      ecx, 0Ah
0x1800143c1  jnb     short loc_1800143CB
0x1800143c3  cmp     ecx, 800h
0x1800143c9  jnb     short loc_1800143D2
0x1800143cb  xor     dl, dl
0x1800143cd  test    sil, cl
0x1800143d0  jz      short loc_18001443B
0x1800143d2  mov     rax, cs:Feature_Standalone_24_08_NonSec__descriptor
0x1800143d9  mov     r8d, [rax]
0x1800143dc  test    r8b, 4
0x1800143e0  jnz     short loc_1800143F7
0x1800143e2  lea     rdx, [rsp+48h+arg_8]
0x1800143e7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_24_08_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_24_08_NonSec>::GetCachedFeatureEnabledState(void)
0x1800143ec  mov     rcx, [rax]
0x1800143ef  mov     [rsp+48h+arg_8], rcx
0x1800143f4  mov     r8d, ecx
0x1800143f7  xor     eax, eax
0x1800143f9  mov     word ptr [rsp+48h+arg_0+4], 3
0x180014400  mov     r9d, r8d
0x180014403  mov     [rsp+48h+var_18], eax
0x180014407  mov     dword ptr [rsp+48h+arg_0], eax
0x18001440b  lea     rcx, qword_180021DB8
0x180014412  shr     r9d, 0Bh
0x180014416  lea     rax, [rsp+48h+arg_0]
0x18001441b  shr     r8d, 0Ah
0x18001441f  and     r9d, edi
0x180014422  and     r8d, edi
0x180014425  mov     [rsp+48h+var_20], edi
0x180014429  mov     edx, 2AF2D22h
0x18001442e  mov     [rsp+48h+var_28], rax
0x180014433  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014438  mov     dl, dil
0x18001443b  mov     eax, [rbx]
0x18001443d  test    sil, al
0x180014440  jz      short loc_180014446
0x180014442  test    dl, dl
0x180014444  jnz     short loc_180014448
0x180014446  xor     edi, edi
0x180014448  mov     rsi, [rsp+48h+arg_18]
0x18001444d  and     eax, 0FFFFFFFEh
0x180014450  or      eax, edi
0x180014452  mov     [rbx], eax
0x180014454  mov     rax, rbx
0x180014457  mov     rbx, [rsp+48h+arg_10]
0x18001445c  add     rsp, 40h
0x180014460  pop     rdi
0x180014461  retn
```
