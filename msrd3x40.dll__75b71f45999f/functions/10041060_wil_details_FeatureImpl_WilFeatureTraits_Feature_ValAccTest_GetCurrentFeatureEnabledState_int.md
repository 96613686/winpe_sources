# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x10041060`
- end: `0x100411e7`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@PAH@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1003ffc0`

## callees

- `0x1000eb60`
- `0x1003a210`
- `0x10040650`
- `0x10040ef0`
- `0x10041060`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        int *a1,
        int a2)
{
  int (__thiscall *v2)(_DWORD, int, int, int); // edi
  int v3; // eax
  unsigned int v4; // edi
  int v5; // eax
  int v6; // ecx
  int v7; // ecx
  char v8; // dl
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  int v11; // eax
  int v13; // [esp+8h] [ebp-10h] BYREF
  char v14; // [esp+Ch] [ebp-Ch]
  _BYTE v15[8]; // [esp+10h] [ebp-8h] BYREF

  v2 = (int (__thiscall *)(_DWORD, int, int, int))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v2 = (int (__thiscall *)(_DWORD, int, int, int))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      *a1 = 0;
      v5 = 0;
      a1[1] = 0;
      *a1 = 0;
      goto LABEL_8;
    }
  }
  v3 = v2(v2, 57048231, 3, a2);
  *a1 = 0;
  a1[1] = 0;
  v4 = v3 & 0xFFFFFF3F;
  v5 = 8 * (v3 & 0x80 | (4 * (v3 & 0x40 | (4 * (v3 & 3)))));
  *a1 = v5;
  if ( !v4 )
  {
LABEL_8:
    v7 = v5 | 0x40;
    goto LABEL_9;
  }
  v6 = 0;
  if ( v4 == 2 )
    v6 = 64;
  v7 = v5 | v6;
LABEL_9:
  v8 = 0;
  *a1 = v7;
  if ( (v7 & 0xC00) == 0xC00 || (v7 & 0x40) != 0 )
  {
    v9 = (*Feature_ValLabTest__descriptor)[0];
    if ( ((*Feature_ValLabTest__descriptor)[0] & 4) == 0 )
      v9 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v15);
    v14 = 3;
    v13 = 0;
    wil::details::ReportUsageToService(
      (int)dword_100667E0,
      57048226,
      (v9 >> 10) & 1,
      (v9 >> 11) & 1,
      (unsigned int)&v13,
      1,
      0,
      v9);
    v10 = (*Feature_Standalone_25_10_NonSec__descriptor)[0];
    if ( ((*Feature_Standalone_25_10_NonSec__descriptor)[0] & 4) == 0 )
      v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(v15);
    v14 = 3;
    v13 = 0;
    wil::details::ReportUsageToService(
      (int)dword_10066830,
      45036792,
      (v10 >> 10) & 1,
      (v10 >> 11) & 1,
      (unsigned int)&v13,
      1,
      0,
      v10);
    v8 = 1;
  }
  v11 = *a1;
  if ( (*a1 & 0x40) != 0 && v8 )
  {
    *a1 = v11 & 0xFFFFFFFE | 1;
    return a1;
  }
  else
  {
    *a1 = v11 & 0xFFFFFFFE;
    return a1;
  }
}

```

## disassembly

```asm
0x10041060  mov     edi, edi
0x10041062  push    ebp
0x10041063  mov     ebp, esp
0x10041065  and     esp, 0FFFFFFF8h
0x10041068  sub     esp, 10h
0x1004106b  push    esi
0x1004106c  mov     esi, [ebp+arg_0]
0x1004106f  push    edi
0x10041070  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10041076  test    edi, edi
0x10041078  jnz     short loc_10041084
0x1004107a  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10041080  test    edi, edi
0x10041082  jz      short loc_100410E5
0x10041084  push    [ebp+arg_4]
0x10041087  mov     ecx, edi
0x10041089  push    3; unsigned int
0x1004108b  push    3667CA7h; void *
0x10041090  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10041096  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10041098  mov     edx, eax
0x1004109a  mov     dword ptr [esi], 0
0x100410a0  mov     edi, edx
0x100410a2  mov     dword ptr [esi+4], 0
0x100410a9  and     edi, 0FFFFFF3Fh
0x100410af  and     eax, 40h
0x100410b2  mov     ecx, edi
0x100410b4  and     edx, 80h
0x100410ba  and     ecx, 3
0x100410bd  shl     ecx, 2
0x100410c0  or      ecx, eax
0x100410c2  shl     ecx, 2
0x100410c5  or      ecx, edx
0x100410c7  lea     eax, ds:0[ecx*8]
0x100410ce  mov     [esi], eax
0x100410d0  test    edi, edi
0x100410d2  jz      short loc_100410FA
0x100410d4  xor     ecx, ecx
0x100410d6  mov     edx, 40h ; '@'
0x100410db  cmp     edi, 2
0x100410de  cmovz   ecx, edx
0x100410e1  or      ecx, eax
0x100410e3  jmp     short loc_100410FF
0x100410e5  mov     dword ptr [esi], 0
0x100410eb  xor     eax, eax
0x100410ed  mov     dword ptr [esi+4], 0
0x100410f4  mov     dword ptr [esi], 0
0x100410fa  mov     ecx, eax
0x100410fc  or      ecx, 40h
0x100410ff  mov     eax, esi
0x10041101  xor     dl, dl
0x10041103  mov     [eax], ecx
0x10041105  mov     eax, ecx
0x10041107  and     eax, 0C00h
0x1004110c  cmp     eax, 0C00h
0x10041111  jz      short loc_1004111C
0x10041113  test    cl, 40h
0x10041116  jz      loc_100411B4
0x1004111c  mov     eax, ds:_Feature_ValLabTest__descriptor
0x10041121  mov     ecx, [eax]
0x10041123  test    cl, 4
0x10041126  jnz     short loc_10041134
0x10041128  lea     eax, [esp+18h+var_8]
0x1004112c  push    eax
0x1004112d  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x10041132  mov     ecx, [eax]
0x10041134  push    ecx
0x10041135  xor     eax, eax
0x10041137  mov     [esp+1Ch+var_C], 3
0x1004113c  push    eax
0x1004113d  mov     [esp+20h+var_10], eax
0x10041141  mov     edx, 3667CA2h
0x10041146  push    1
0x10041148  lea     eax, [esp+24h+var_10]
0x1004114c  push    eax
0x1004114d  mov     eax, ecx
0x1004114f  shr     ecx, 0Ah
0x10041152  shr     eax, 0Bh
0x10041155  and     ecx, 1
0x10041158  and     eax, 1
0x1004115b  push    eax
0x1004115c  push    ecx
0x1004115d  mov     ecx, offset dword_100667E0
0x10041162  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x10041167  mov     eax, ds:_Feature_Standalone_25_10_NonSec__descriptor
0x1004116c  mov     ecx, [eax]
0x1004116e  test    cl, 4
0x10041171  jnz     short loc_1004117F
0x10041173  lea     eax, [esp+18h+var_8]
0x10041177  push    eax
0x10041178  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1004117d  mov     ecx, [eax]
0x1004117f  push    ecx
0x10041180  xor     eax, eax
0x10041182  mov     [esp+1Ch+var_C], 3
0x10041187  push    eax
0x10041188  mov     [esp+20h+var_10], eax
0x1004118c  mov     edx, 2AF34F8h
0x10041191  push    1
0x10041193  lea     eax, [esp+24h+var_10]
0x10041197  push    eax
0x10041198  mov     eax, ecx
0x1004119a  shr     ecx, 0Ah
0x1004119d  shr     eax, 0Bh
0x100411a0  and     ecx, 1
0x100411a3  and     eax, 1
0x100411a6  push    eax
0x100411a7  push    ecx
0x100411a8  mov     ecx, offset dword_10066830
0x100411ad  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x100411b2  mov     dl, 1
0x100411b4  mov     eax, [esi]
0x100411b6  test    al, 40h
0x100411b8  jz      short loc_100411D4
0x100411ba  test    dl, dl
0x100411bc  jz      short loc_100411D4
0x100411be  and     eax, 0FFFFFFFEh
0x100411c1  mov     ecx, 1
0x100411c6  or      eax, ecx
0x100411c8  mov     [esi], eax
0x100411ca  mov     eax, esi
0x100411cc  pop     edi
0x100411cd  pop     esi
0x100411ce  mov     esp, ebp
0x100411d0  pop     ebp
0x100411d1  retn    8
0x100411d4  and     eax, 0FFFFFFFEh
0x100411d7  xor     ecx, ecx
0x100411d9  or      eax, ecx
0x100411db  mov     [esi], eax
0x100411dd  mov     eax, esi
0x100411df  pop     edi
0x100411e0  pop     esi
0x100411e1  mov     esp, ebp
0x100411e3  pop     ebp
0x100411e4  retn    8
```
