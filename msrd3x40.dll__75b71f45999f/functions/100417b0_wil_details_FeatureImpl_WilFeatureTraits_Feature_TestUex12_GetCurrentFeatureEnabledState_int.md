# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)

- ea: `0x100417b0`
- end: `0x1004190b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@PAH@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x10040470`

## callees

- `0x1000eb60`
- `0x1003a210`
- `0x1003fe40`
- `0x10040d80`
- `0x100417b0`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(
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
  _BYTE v13[8]; // [esp+10h] [ebp-10h] BYREF
  int v14; // [esp+18h] [ebp-8h] BYREF
  char v15; // [esp+1Ch] [ebp-4h]

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
  v3 = v2(v2, 58989070, 3, a2);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(v7) )
  {
    v10 = (*Feature_Standalone_26_04_NonSec__descriptor)[0];
    if ( ((*Feature_Standalone_26_04_NonSec__descriptor)[0] & 4) == 0 )
      v10 = *(_DWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(v13);
    v15 = 3;
    v14 = 0;
    wil::details::ReportUsageToService(
      (int)dword_100667C0,
      58599559,
      (v10 >> 10) & 1,
      (v10 >> 11) & 1,
      (unsigned int)&v14,
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
0x100417b0  mov     edi, edi
0x100417b2  push    ebp
0x100417b3  mov     ebp, esp
0x100417b5  sub     esp, 14h
0x100417b8  push    ebx
0x100417b9  push    esi
0x100417ba  mov     esi, [ebp+arg_0]
0x100417bd  push    edi
0x100417be  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x100417c4  test    edi, edi
0x100417c6  jnz     short loc_100417D2
0x100417c8  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x100417ce  test    edi, edi
0x100417d0  jz      short loc_10041833
0x100417d2  push    [ebp+arg_4]
0x100417d5  mov     ecx, edi
0x100417d7  push    3; unsigned int
0x100417d9  push    3841A0Eh; void *
0x100417de  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100417e4  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x100417e6  mov     edx, eax
0x100417e8  mov     dword ptr [esi], 0
0x100417ee  mov     edi, edx
0x100417f0  mov     dword ptr [esi+4], 0
0x100417f7  and     edi, 0FFFFFF3Fh
0x100417fd  and     eax, 40h
0x10041800  mov     ecx, edi
0x10041802  and     edx, 80h
0x10041808  and     ecx, 3
0x1004180b  shl     ecx, 2
0x1004180e  or      ecx, eax
0x10041810  shl     ecx, 2
0x10041813  or      ecx, edx
0x10041815  lea     eax, ds:0[ecx*8]
0x1004181c  mov     [esi], eax
0x1004181e  test    edi, edi
0x10041820  jz      short loc_10041848
0x10041822  xor     ecx, ecx
0x10041824  mov     edx, 40h ; '@'
0x10041829  cmp     edi, 2
0x1004182c  cmovz   ecx, edx
0x1004182f  or      ecx, eax
0x10041831  jmp     short loc_1004184D
0x10041833  mov     dword ptr [esi], 0
0x10041839  xor     eax, eax
0x1004183b  mov     dword ptr [esi+4], 0
0x10041842  mov     dword ptr [esi], 0
0x10041848  mov     ecx, eax
0x1004184a  or      ecx, 40h
0x1004184d  mov     eax, esi
0x1004184f  xor     dl, dl
0x10041851  mov     [eax], ecx
0x10041853  mov     eax, ecx
0x10041855  and     eax, 0C00h
0x1004185a  cmp     eax, 0C00h
0x1004185f  jnz     short loc_10041865
0x10041861  mov     bl, 1
0x10041863  jmp     short loc_1004186C
0x10041865  xor     bl, bl
0x10041867  test    cl, 40h
0x1004186a  jz      short loc_100418D6
0x1004186c  push    ecx
0x1004186d  mov     ecx, offset ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CGAAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x10041872  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QAE_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x10041877  test    al, al
0x10041879  jz      short loc_100418C6
0x1004187b  mov     eax, ds:_Feature_Standalone_26_04_NonSec__descriptor
0x10041880  mov     ecx, [eax]
0x10041882  test    cl, 4
0x10041885  jnz     short loc_10041892
0x10041887  lea     eax, [ebp+var_10]
0x1004188a  push    eax
0x1004188b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)
0x10041890  mov     ecx, [eax]
0x10041892  push    ecx
0x10041893  xor     eax, eax
0x10041895  mov     [ebp+var_4], 3
0x10041899  push    eax
0x1004189a  mov     [ebp+var_8], eax
0x1004189d  mov     edx, 37E2887h
0x100418a2  push    1
0x100418a4  lea     eax, [ebp+var_8]
0x100418a7  push    eax
0x100418a8  mov     eax, ecx
0x100418aa  shr     ecx, 0Ah
0x100418ad  shr     eax, 0Bh
0x100418b0  and     ecx, 1
0x100418b3  and     eax, 1
0x100418b6  push    eax
0x100418b7  push    ecx
0x100418b8  mov     ecx, offset dword_100667C0
0x100418bd  call    ?ReportUsageToService@details@wil@@YGXPAUwil_details_FeatureReportingCache@@IHHPBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,ulong)
0x100418c2  mov     dl, 1
0x100418c4  jmp     short loc_100418C8
0x100418c6  xor     dl, dl
0x100418c8  test    bl, bl
0x100418ca  jz      short loc_100418D6
0x100418cc  test    dl, dl
0x100418ce  jnz     short loc_100418D6
0x100418d0  and     dword ptr [esi], 0FFFFFBFFh
0x100418d6  mov     eax, [esi]
0x100418d8  test    al, 40h
0x100418da  jz      short loc_100418F7
0x100418dc  test    dl, dl
0x100418de  jz      short loc_100418F7
0x100418e0  and     eax, 0FFFFFFFEh
0x100418e3  mov     ecx, 1
0x100418e8  or      eax, ecx
0x100418ea  mov     [esi], eax
0x100418ec  mov     eax, esi
0x100418ee  pop     edi
0x100418ef  pop     esi
0x100418f0  pop     ebx
0x100418f1  mov     esp, ebp
0x100418f3  pop     ebp
0x100418f4  retn    8
0x100418f7  and     eax, 0FFFFFFFEh
0x100418fa  xor     ecx, ecx
0x100418fc  or      eax, ecx
0x100418fe  mov     [esi], eax
0x10041900  mov     eax, esi
0x10041902  pop     edi
0x10041903  pop     esi
0x10041904  pop     ebx
0x10041905  mov     esp, ebp
0x10041907  pop     ebp
0x10041908  retn    8
```
