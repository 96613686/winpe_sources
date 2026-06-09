# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x10041360`
- end: `0x100414c2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@PAH@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x100401a0`

## callees

- `0x1000eb60`
- `0x1003a210`
- `0x1003fcc0`
- `0x10040930`
- `0x10041360`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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
  v3 = v2(v2, 58988972, 3, a2);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(v7) )
  {
    v10 = (*Feature_Standalone_26_01_NonSec__descriptor)[0];
    if ( ((*Feature_Standalone_26_01_NonSec__descriptor)[0] & 4) == 0 )
      v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(v15);
    v14 = 3;
    v13 = 0;
    wil::details::ReportUsageToService(
      (int)dword_10066810,
      58599532,
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
0x10041360  mov     edi, edi
0x10041362  push    ebp
0x10041363  mov     ebp, esp
0x10041365  and     esp, 0FFFFFFF8h
0x10041368  sub     esp, 14h
0x1004136b  push    ebx
0x1004136c  push    esi
0x1004136d  mov     esi, [ebp+arg_0]
0x10041370  push    edi
0x10041371  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10041377  test    edi, edi
0x10041379  jnz     short loc_10041385
0x1004137b  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10041381  test    edi, edi
0x10041383  jz      short loc_100413E6
0x10041385  push    [ebp+arg_4]
0x10041388  mov     ecx, edi
0x1004138a  push    3; unsigned int
0x1004138c  push    38419ACh; void *
0x10041391  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10041397  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10041399  mov     edx, eax
0x1004139b  mov     dword ptr [esi], 0
0x100413a1  mov     edi, edx
0x100413a3  mov     dword ptr [esi+4], 0
0x100413aa  and     edi, 0FFFFFF3Fh
0x100413b0  and     eax, 40h
0x100413b3  mov     ecx, edi
0x100413b5  and     edx, 80h
0x100413bb  and     ecx, 3
0x100413be  shl     ecx, 2
0x100413c1  or      ecx, eax
0x100413c3  shl     ecx, 2
0x100413c6  or      ecx, edx
0x100413c8  lea     eax, ds:0[ecx*8]
0x100413cf  mov     [esi], eax
0x100413d1  test    edi, edi
0x100413d3  jz      short loc_100413FB
0x100413d5  xor     ecx, ecx
0x100413d7  mov     edx, 40h ; '@'
0x100413dc  cmp     edi, 2
0x100413df  cmovz   ecx, edx
0x100413e2  or      ecx, eax
0x100413e4  jmp     short loc_10041400
0x100413e6  mov     dword ptr [esi], 0
0x100413ec  xor     eax, eax
0x100413ee  mov     dword ptr [esi+4], 0
0x100413f5  mov     dword ptr [esi], 0
0x100413fb  mov     ecx, eax
0x100413fd  or      ecx, 40h
0x10041400  mov     eax, esi
0x10041402  xor     dl, dl
0x10041404  mov     [eax], ecx
0x10041406  mov     eax, ecx
0x10041408  and     eax, 0C00h
0x1004140d  cmp     eax, 0C00h
0x10041412  jnz     short loc_10041418
0x10041414  mov     bl, 1
0x10041416  jmp     short loc_1004141F
0x10041418  xor     bl, bl
0x1004141a  test    cl, 40h
0x1004141d  jz      short loc_1004148D
0x1004141f  push    ecx
0x10041420  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x10041425  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QAE_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x1004142a  test    al, al
0x1004142c  jz      short loc_1004147D
0x1004142e  mov     eax, ds:_Feature_Standalone_26_01_NonSec__descriptor
0x10041433  mov     ecx, [eax]
0x10041435  test    cl, 4
0x10041438  jnz     short loc_10041446
0x1004143a  lea     eax, [esp+20h+var_8]
0x1004143e  push    eax
0x1004143f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x10041444  mov     ecx, [eax]
0x10041446  push    ecx
0x10041447  xor     eax, eax
0x10041449  mov     [esp+24h+var_C], 3
0x1004144e  push    eax
0x1004144f  mov     [esp+28h+var_10], eax
0x10041453  mov     edx, 37E286Ch
0x10041458  push    1
0x1004145a  lea     eax, [esp+2Ch+var_10]
0x1004145e  push    eax
0x1004145f  mov     eax, ecx
0x10041461  shr     ecx, 0Ah
0x10041464  shr     eax, 0Bh
0x10041467  and     ecx, 1
0x1004146a  and     eax, 1
0x1004146d  push    eax
0x1004146e  push    ecx
0x1004146f  mov     ecx, offset dword_10066810
0x10041474  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x10041479  mov     dl, 1
0x1004147b  jmp     short loc_1004147F
0x1004147d  xor     dl, dl
0x1004147f  test    bl, bl
0x10041481  jz      short loc_1004148D
0x10041483  test    dl, dl
0x10041485  jnz     short loc_1004148D
0x10041487  and     dword ptr [esi], 0FFFFFBFFh
0x1004148d  mov     eax, [esi]
0x1004148f  test    al, 40h
0x10041491  jz      short loc_100414AE
0x10041493  test    dl, dl
0x10041495  jz      short loc_100414AE
0x10041497  and     eax, 0FFFFFFFEh
0x1004149a  mov     ecx, 1
0x1004149f  or      eax, ecx
0x100414a1  mov     [esi], eax
0x100414a3  mov     eax, esi
0x100414a5  pop     edi
0x100414a6  pop     esi
0x100414a7  pop     ebx
0x100414a8  mov     esp, ebp
0x100414aa  pop     ebp
0x100414ab  retn    8
0x100414ae  and     eax, 0FFFFFFFEh
0x100414b1  xor     ecx, ecx
0x100414b3  or      eax, ecx
0x100414b5  mov     [esi], eax
0x100414b7  mov     eax, esi
0x100414b9  pop     edi
0x100414ba  pop     esi
0x100414bb  pop     ebx
0x100414bc  mov     esp, ebp
0x100414be  pop     ebp
0x100414bf  retn    8
```
