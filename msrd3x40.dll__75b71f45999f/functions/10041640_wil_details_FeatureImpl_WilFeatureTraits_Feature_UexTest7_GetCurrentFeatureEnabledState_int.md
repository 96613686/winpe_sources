# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x10041640`
- end: `0x100417a2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@PAH@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x10040380`

## callees

- `0x1000eb60`
- `0x1003a210`
- `0x1003fdc0`
- `0x10040c10`
- `0x10041640`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
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
  v3 = v2(v2, 58989021, 3, a2);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(v7) )
  {
    v10 = (*Feature_Standalone_26_03_NonSec__descriptor)[0];
    if ( ((*Feature_Standalone_26_03_NonSec__descriptor)[0] & 4) == 0 )
      v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(v15);
    v14 = 3;
    v13 = 0;
    wil::details::ReportUsageToService(
      (int)dword_10066840,
      58599553,
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
0x10041640  mov     edi, edi
0x10041642  push    ebp
0x10041643  mov     ebp, esp
0x10041645  and     esp, 0FFFFFFF8h
0x10041648  sub     esp, 14h
0x1004164b  push    ebx
0x1004164c  push    esi
0x1004164d  mov     esi, [ebp+arg_0]
0x10041650  push    edi
0x10041651  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10041657  test    edi, edi
0x10041659  jnz     short loc_10041665
0x1004165b  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10041661  test    edi, edi
0x10041663  jz      short loc_100416C6
0x10041665  push    [ebp+arg_4]
0x10041668  mov     ecx, edi
0x1004166a  push    3; unsigned int
0x1004166c  push    38419DDh; void *
0x10041671  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10041677  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10041679  mov     edx, eax
0x1004167b  mov     dword ptr [esi], 0
0x10041681  mov     edi, edx
0x10041683  mov     dword ptr [esi+4], 0
0x1004168a  and     edi, 0FFFFFF3Fh
0x10041690  and     eax, 40h
0x10041693  mov     ecx, edi
0x10041695  and     edx, 80h
0x1004169b  and     ecx, 3
0x1004169e  shl     ecx, 2
0x100416a1  or      ecx, eax
0x100416a3  shl     ecx, 2
0x100416a6  or      ecx, edx
0x100416a8  lea     eax, ds:0[ecx*8]
0x100416af  mov     [esi], eax
0x100416b1  test    edi, edi
0x100416b3  jz      short loc_100416DB
0x100416b5  xor     ecx, ecx
0x100416b7  mov     edx, 40h ; '@'
0x100416bc  cmp     edi, 2
0x100416bf  cmovz   ecx, edx
0x100416c2  or      ecx, eax
0x100416c4  jmp     short loc_100416E0
0x100416c6  mov     dword ptr [esi], 0
0x100416cc  xor     eax, eax
0x100416ce  mov     dword ptr [esi+4], 0
0x100416d5  mov     dword ptr [esi], 0
0x100416db  mov     ecx, eax
0x100416dd  or      ecx, 40h
0x100416e0  mov     eax, esi
0x100416e2  xor     dl, dl
0x100416e4  mov     [eax], ecx
0x100416e6  mov     eax, ecx
0x100416e8  and     eax, 0C00h
0x100416ed  cmp     eax, 0C00h
0x100416f2  jnz     short loc_100416F8
0x100416f4  mov     bl, 1
0x100416f6  jmp     short loc_100416FF
0x100416f8  xor     bl, bl
0x100416fa  test    cl, 40h
0x100416fd  jz      short loc_1004176D
0x100416ff  push    ecx
0x10041700  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x10041705  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QAE_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x1004170a  test    al, al
0x1004170c  jz      short loc_1004175D
0x1004170e  mov     eax, ds:_Feature_Standalone_26_03_NonSec__descriptor
0x10041713  mov     ecx, [eax]
0x10041715  test    cl, 4
0x10041718  jnz     short loc_10041726
0x1004171a  lea     eax, [esp+20h+var_8]
0x1004171e  push    eax
0x1004171f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x10041724  mov     ecx, [eax]
0x10041726  push    ecx
0x10041727  xor     eax, eax
0x10041729  mov     [esp+24h+var_C], 3
0x1004172e  push    eax
0x1004172f  mov     [esp+28h+var_10], eax
0x10041733  mov     edx, 37E2881h
0x10041738  push    1
0x1004173a  lea     eax, [esp+2Ch+var_10]
0x1004173e  push    eax
0x1004173f  mov     eax, ecx
0x10041741  shr     ecx, 0Ah
0x10041744  shr     eax, 0Bh
0x10041747  and     ecx, 1
0x1004174a  and     eax, 1
0x1004174d  push    eax
0x1004174e  push    ecx
0x1004174f  mov     ecx, offset dword_10066840
0x10041754  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x10041759  mov     dl, 1
0x1004175b  jmp     short loc_1004175F
0x1004175d  xor     dl, dl
0x1004175f  test    bl, bl
0x10041761  jz      short loc_1004176D
0x10041763  test    dl, dl
0x10041765  jnz     short loc_1004176D
0x10041767  and     dword ptr [esi], 0FFFFFBFFh
0x1004176d  mov     eax, [esi]
0x1004176f  test    al, 40h
0x10041771  jz      short loc_1004178E
0x10041773  test    dl, dl
0x10041775  jz      short loc_1004178E
0x10041777  and     eax, 0FFFFFFFEh
0x1004177a  mov     ecx, 1
0x1004177f  or      eax, ecx
0x10041781  mov     [esi], eax
0x10041783  mov     eax, esi
0x10041785  pop     edi
0x10041786  pop     esi
0x10041787  pop     ebx
0x10041788  mov     esp, ebp
0x1004178a  pop     ebp
0x1004178b  retn    8
0x1004178e  and     eax, 0FFFFFFFEh
0x10041791  xor     ecx, ecx
0x10041793  or      eax, ecx
0x10041795  mov     [esi], eax
0x10041797  mov     eax, esi
0x10041799  pop     edi
0x1004179a  pop     esi
0x1004179b  pop     ebx
0x1004179c  mov     esp, ebp
0x1004179e  pop     ebp
0x1004179f  retn    8
```
