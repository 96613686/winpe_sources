# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x100411f0`
- end: `0x10041352`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@PAH@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100400b0`

## callees

- `0x1000eb60`
- `0x1003a210`
- `0x1003fc40`
- `0x100407c0`
- `0x100411f0`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
  char v9; // bl
  unsigned int v10; // ecx
  int v11; // eax
  int v13; // [esp+10h] [ebp-10h] BYREF
  char v14; // [esp+14h] [ebp-Ch]
  _BYTE v15[8]; // [esp+18h] [ebp-8h] BYREF

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
  v3 = v2(v2, 57048237, 3, a2);
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
  if ( (v7 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    if ( (v7 & 0x40) == 0 )
      goto LABEL_20;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(v7) )
  {
    v10 = (*Feature_Standalone_25_11_NonSec__descriptor)[0];
    if ( ((*Feature_Standalone_25_11_NonSec__descriptor)[0] & 4) == 0 )
      v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(v15);
    v14 = 3;
    v13 = 0;
    wil::details::ReportUsageToService(
      (int)dword_10066800,
      45036797,
      (v10 >> 10) & 1,
      (v10 >> 11) & 1,
      (unsigned int)&v13,
      1,
      0,
      v10);
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  if ( v9 && !v8 )
    *a1 &= ~0x400u;
LABEL_20:
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
0x100411f0  mov     edi, edi
0x100411f2  push    ebp
0x100411f3  mov     ebp, esp
0x100411f5  and     esp, 0FFFFFFF8h
0x100411f8  sub     esp, 14h
0x100411fb  push    ebx
0x100411fc  push    esi
0x100411fd  mov     esi, [ebp+arg_0]
0x10041200  push    edi
0x10041201  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10041207  test    edi, edi
0x10041209  jnz     short loc_10041215
0x1004120b  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10041211  test    edi, edi
0x10041213  jz      short loc_10041276
0x10041215  push    [ebp+arg_4]
0x10041218  mov     ecx, edi
0x1004121a  push    3; unsigned int
0x1004121c  push    3667CADh; void *
0x10041221  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10041227  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10041229  mov     edx, eax
0x1004122b  mov     dword ptr [esi], 0
0x10041231  mov     edi, edx
0x10041233  mov     dword ptr [esi+4], 0
0x1004123a  and     edi, 0FFFFFF3Fh
0x10041240  and     eax, 40h
0x10041243  mov     ecx, edi
0x10041245  and     edx, 80h
0x1004124b  and     ecx, 3
0x1004124e  shl     ecx, 2
0x10041251  or      ecx, eax
0x10041253  shl     ecx, 2
0x10041256  or      ecx, edx
0x10041258  lea     eax, ds:0[ecx*8]
0x1004125f  mov     [esi], eax
0x10041261  test    edi, edi
0x10041263  jz      short loc_1004128B
0x10041265  xor     ecx, ecx
0x10041267  mov     edx, 40h ; '@'
0x1004126c  cmp     edi, 2
0x1004126f  cmovz   ecx, edx
0x10041272  or      ecx, eax
0x10041274  jmp     short loc_10041290
0x10041276  mov     dword ptr [esi], 0
0x1004127c  xor     eax, eax
0x1004127e  mov     dword ptr [esi+4], 0
0x10041285  mov     dword ptr [esi], 0
0x1004128b  mov     ecx, eax
0x1004128d  or      ecx, 40h
0x10041290  mov     eax, esi
0x10041292  xor     dl, dl
0x10041294  mov     [eax], ecx
0x10041296  mov     eax, ecx
0x10041298  and     eax, 0C00h
0x1004129d  cmp     eax, 0C00h
0x100412a2  jnz     short loc_100412A8
0x100412a4  mov     bl, 1
0x100412a6  jmp     short loc_100412AF
0x100412a8  xor     bl, bl
0x100412aa  test    cl, 40h
0x100412ad  jz      short loc_1004131D
0x100412af  push    ecx
0x100412b0  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x100412b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QAE_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x100412ba  test    al, al
0x100412bc  jz      short loc_1004130D
0x100412be  mov     eax, ds:_Feature_Standalone_25_11_NonSec__descriptor
0x100412c3  mov     ecx, [eax]
0x100412c5  test    cl, 4
0x100412c8  jnz     short loc_100412D6
0x100412ca  lea     eax, [esp+20h+var_8]
0x100412ce  push    eax
0x100412cf  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x100412d4  mov     ecx, [eax]
0x100412d6  push    ecx
0x100412d7  xor     eax, eax
0x100412d9  mov     [esp+24h+var_C], 3
0x100412de  push    eax
0x100412df  mov     [esp+28h+var_10], eax
0x100412e3  mov     edx, 2AF34FDh
0x100412e8  push    1
0x100412ea  lea     eax, [esp+2Ch+var_10]
0x100412ee  push    eax
0x100412ef  mov     eax, ecx
0x100412f1  shr     ecx, 0Ah
0x100412f4  shr     eax, 0Bh
0x100412f7  and     ecx, 1
0x100412fa  and     eax, 1
0x100412fd  push    eax
0x100412fe  push    ecx
0x100412ff  mov     ecx, offset dword_10066800
0x10041304  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x10041309  mov     dl, 1
0x1004130b  jmp     short loc_1004130F
0x1004130d  xor     dl, dl
0x1004130f  test    bl, bl
0x10041311  jz      short loc_1004131D
0x10041313  test    dl, dl
0x10041315  jnz     short loc_1004131D
0x10041317  and     dword ptr [esi], 0FFFFFBFFh
0x1004131d  mov     eax, [esi]
0x1004131f  test    al, 40h
0x10041321  jz      short loc_1004133E
0x10041323  test    dl, dl
0x10041325  jz      short loc_1004133E
0x10041327  and     eax, 0FFFFFFFEh
0x1004132a  mov     ecx, 1
0x1004132f  or      eax, ecx
0x10041331  mov     [esi], eax
0x10041333  mov     eax, esi
0x10041335  pop     edi
0x10041336  pop     esi
0x10041337  pop     ebx
0x10041338  mov     esp, ebp
0x1004133a  pop     ebp
0x1004133b  retn    8
0x1004133e  and     eax, 0FFFFFFFEh
0x10041341  xor     ecx, ecx
0x10041343  or      eax, ecx
0x10041345  mov     [esi], eax
0x10041347  mov     eax, esi
0x10041349  pop     edi
0x1004134a  pop     esi
0x1004134b  pop     ebx
0x1004134c  mov     esp, ebp
0x1004134e  pop     ebp
0x1004134f  retn    8
```
