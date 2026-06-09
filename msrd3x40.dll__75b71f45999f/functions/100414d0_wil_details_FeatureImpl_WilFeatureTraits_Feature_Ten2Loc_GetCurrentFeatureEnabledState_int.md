# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x100414d0`
- end: `0x10041632`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@PAH@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x10040290`

## callees

- `0x1000eb60`
- `0x1003a210`
- `0x1003fd40`
- `0x10040aa0`
- `0x100414d0`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
  v3 = v2(v2, 58989002, 3, a2);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(v7) )
  {
    v10 = (*Feature_Standalone_26_02_NonSec__descriptor)[0];
    if ( ((*Feature_Standalone_26_02_NonSec__descriptor)[0] & 4) == 0 )
      v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(v15);
    v14 = 3;
    v13 = 0;
    wil::details::ReportUsageToService(
      (int)dword_10066850,
      58599550,
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
0x100414d0  mov     edi, edi
0x100414d2  push    ebp
0x100414d3  mov     ebp, esp
0x100414d5  and     esp, 0FFFFFFF8h
0x100414d8  sub     esp, 14h
0x100414db  push    ebx
0x100414dc  push    esi
0x100414dd  mov     esi, [ebp+arg_0]
0x100414e0  push    edi
0x100414e1  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x100414e7  test    edi, edi
0x100414e9  jnz     short loc_100414F5
0x100414eb  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x100414f1  test    edi, edi
0x100414f3  jz      short loc_10041556
0x100414f5  push    [ebp+arg_4]
0x100414f8  mov     ecx, edi
0x100414fa  push    3; unsigned int
0x100414fc  push    38419CAh; void *
0x10041501  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10041507  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10041509  mov     edx, eax
0x1004150b  mov     dword ptr [esi], 0
0x10041511  mov     edi, edx
0x10041513  mov     dword ptr [esi+4], 0
0x1004151a  and     edi, 0FFFFFF3Fh
0x10041520  and     eax, 40h
0x10041523  mov     ecx, edi
0x10041525  and     edx, 80h
0x1004152b  and     ecx, 3
0x1004152e  shl     ecx, 2
0x10041531  or      ecx, eax
0x10041533  shl     ecx, 2
0x10041536  or      ecx, edx
0x10041538  lea     eax, ds:0[ecx*8]
0x1004153f  mov     [esi], eax
0x10041541  test    edi, edi
0x10041543  jz      short loc_1004156B
0x10041545  xor     ecx, ecx
0x10041547  mov     edx, 40h ; '@'
0x1004154c  cmp     edi, 2
0x1004154f  cmovz   ecx, edx
0x10041552  or      ecx, eax
0x10041554  jmp     short loc_10041570
0x10041556  mov     dword ptr [esi], 0
0x1004155c  xor     eax, eax
0x1004155e  mov     dword ptr [esi+4], 0
0x10041565  mov     dword ptr [esi], 0
0x1004156b  mov     ecx, eax
0x1004156d  or      ecx, 40h
0x10041570  mov     eax, esi
0x10041572  xor     dl, dl
0x10041574  mov     [eax], ecx
0x10041576  mov     eax, ecx
0x10041578  and     eax, 0C00h
0x1004157d  cmp     eax, 0C00h
0x10041582  jnz     short loc_10041588
0x10041584  mov     bl, 1
0x10041586  jmp     short loc_1004158F
0x10041588  xor     bl, bl
0x1004158a  test    cl, 40h
0x1004158d  jz      short loc_100415FD
0x1004158f  push    ecx
0x10041590  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x10041595  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QAE_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x1004159a  test    al, al
0x1004159c  jz      short loc_100415ED
0x1004159e  mov     eax, ds:_Feature_Standalone_26_02_NonSec__descriptor
0x100415a3  mov     ecx, [eax]
0x100415a5  test    cl, 4
0x100415a8  jnz     short loc_100415B6
0x100415aa  lea     eax, [esp+20h+var_8]
0x100415ae  push    eax
0x100415af  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x100415b4  mov     ecx, [eax]
0x100415b6  push    ecx
0x100415b7  xor     eax, eax
0x100415b9  mov     [esp+24h+var_C], 3
0x100415be  push    eax
0x100415bf  mov     [esp+28h+var_10], eax
0x100415c3  mov     edx, 37E287Eh
0x100415c8  push    1
0x100415ca  lea     eax, [esp+2Ch+var_10]
0x100415ce  push    eax
0x100415cf  mov     eax, ecx
0x100415d1  shr     ecx, 0Ah
0x100415d4  shr     eax, 0Bh
0x100415d7  and     ecx, 1
0x100415da  and     eax, 1
0x100415dd  push    eax
0x100415de  push    ecx
0x100415df  mov     ecx, offset dword_10066850
0x100415e4  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x100415e9  mov     dl, 1
0x100415eb  jmp     short loc_100415EF
0x100415ed  xor     dl, dl
0x100415ef  test    bl, bl
0x100415f1  jz      short loc_100415FD
0x100415f3  test    dl, dl
0x100415f5  jnz     short loc_100415FD
0x100415f7  and     dword ptr [esi], 0FFFFFBFFh
0x100415fd  mov     eax, [esi]
0x100415ff  test    al, 40h
0x10041601  jz      short loc_1004161E
0x10041603  test    dl, dl
0x10041605  jz      short loc_1004161E
0x10041607  and     eax, 0FFFFFFFEh
0x1004160a  mov     ecx, 1
0x1004160f  or      eax, ecx
0x10041611  mov     [esi], eax
0x10041613  mov     eax, esi
0x10041615  pop     edi
0x10041616  pop     esi
0x10041617  pop     ebx
0x10041618  mov     esp, ebp
0x1004161a  pop     ebp
0x1004161b  retn    8
0x1004161e  and     eax, 0FFFFFFFEh
0x10041621  xor     ecx, ecx
0x10041623  or      eax, ecx
0x10041625  mov     [esi], eax
0x10041627  mov     eax, esi
0x10041629  pop     edi
0x1004162a  pop     esi
0x1004162b  pop     ebx
0x1004162c  mov     esp, ebp
0x1004162e  pop     ebp
0x1004162f  retn    8
```
