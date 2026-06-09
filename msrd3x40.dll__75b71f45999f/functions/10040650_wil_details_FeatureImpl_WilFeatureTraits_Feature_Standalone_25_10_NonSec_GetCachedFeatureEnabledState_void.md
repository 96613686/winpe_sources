# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x10040650`
- end: `0x100407ac`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10041060`

## callees

- `0x1000d7c0`
- `0x1000d8e0`
- `0x1000eb60`
- `0x10040650`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        int *a1)
{
  int v1; // eax
  int v2; // eax
  int (__thiscall *v3)(_DWORD, int, int, int *); // edi
  int v4; // eax
  unsigned int v5; // ebx
  __int16 v6; // di
  __int16 v7; // ax
  signed __int32 v8; // edx
  unsigned __int16 v9; // di
  signed __int32 i; // ebx
  bool v11; // zf
  signed __int32 v12; // ecx
  int v13; // edx
  signed __int32 v14; // eax
  int v15; // eax
  int v16; // ecx
  int v18; // [esp+Ch] [ebp-Ch] BYREF
  volatile signed __int32 *v19; // [esp+10h] [ebp-8h]
  int v20; // [esp+14h] [ebp-4h]

  v19 = (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor;
  v1 = (*Feature_Standalone_25_10_NonSec__descriptor)[0];
  *a1 = 0;
  *a1 = v1;
  a1[1] = 0;
  if ( (v1 & 6) == 6 )
    return a1;
  v2 = wil::details::EnsureSubscribedToFeatureConfigurationChanges();
  v3 = (int (__thiscall *)(_DWORD, int, int, int *))g_wil_details_internalGetFeatureEnabledState;
  v20 = v2;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v3 = (int (__thiscall *)(_DWORD, int, int, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v3(v3, 45036792, 3, &v18);
    v5 = v4 & 0xFFFFFF3F;
    v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
    if ( (v4 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( v5 == 2 )
        v7 = 64;
      goto LABEL_10;
    }
  }
  else
  {
    v6 = 0;
  }
  v7 = 64;
LABEL_10:
  v8 = *a1;
  v9 = v7 | v6;
  for ( i = *a1; ; i = v14 )
  {
    v11 = v18 == 0;
    v12 = v8;
    *a1 = v8;
    if ( !v11 && (v8 & 2) == 0 )
    {
      v13 = v8
          ^ ((unsigned __int16)v8
           ^ v9)
          & 0x180
          ^ ((unsigned __int8)v9
           ^ (unsigned __int8)(v8 ^ (v8 ^ v9) & 0x80))
          & 0x40
          | 1;
      v12 = v13 ^ (v9 ^ (unsigned __int16)v13) & 0x800 | 2;
      *a1 = v12;
    }
    if ( (i & 4) == 0 )
    {
      v12 = ((unsigned __int16)v12 ^ v9) & 0x400 ^ v12 | 4;
      *a1 = v12;
    }
    v14 = _InterlockedCompareExchange(v19, v12, i);
    v8 = v14;
    if ( v14 == i )
      break;
  }
  if ( (i & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v19, 3, v20);
  if ( (*a1 & 2) == 0 )
  {
    v15 = *a1 ^ ((unsigned __int16)*a1 ^ v9) & 0x180;
    v16 = v15 ^ ((unsigned __int8)v15 ^ (unsigned __int8)v9) & 0x40 | 1;
    *a1 = v16 ^ ((unsigned __int16)v16 ^ v9) & 0x800;
  }
  return a1;
}

```

## disassembly

```asm
0x10040650  mov     edi, edi
0x10040652  push    ebp
0x10040653  mov     ebp, esp
0x10040655  and     esp, 0FFFFFFF8h
0x10040658  sub     esp, 0Ch
0x1004065b  mov     eax, ds:_Feature_Standalone_25_10_NonSec__descriptor
0x10040660  push    ebx
0x10040661  push    esi
0x10040662  mov     esi, [ebp+arg_0]
0x10040665  mov     [esp+14h+var_8], eax
0x10040669  mov     eax, [eax]
0x1004066b  push    edi; this
0x1004066c  mov     dword ptr [esi], 0
0x10040672  mov     [esi], eax
0x10040674  and     eax, 6
0x10040677  mov     dword ptr [esi+4], 0
0x1004067e  cmp     al, 6
0x10040680  jz      loc_100407A1
0x10040686  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1004068b  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040691  mov     [esp+18h+var_4], eax
0x10040695  test    edi, edi
0x10040697  jnz     short loc_100406A3
0x10040699  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x1004069f  test    edi, edi
0x100406a1  jz      short loc_100406F5
0x100406a3  lea     eax, [esp+18h+var_C]
0x100406a7  mov     ecx, edi
0x100406a9  push    eax
0x100406aa  push    3; unsigned int
0x100406ac  push    2AF34F8h; void *
0x100406b1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100406b7  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x100406b9  mov     edx, eax
0x100406bb  and     eax, 40h
0x100406be  mov     ebx, edx
0x100406c0  and     edx, 80h
0x100406c6  and     ebx, 0FFFFFF3Fh
0x100406cc  mov     ecx, ebx
0x100406ce  and     ecx, 3
0x100406d1  shl     ecx, 2
0x100406d4  or      ecx, eax
0x100406d6  shl     ecx, 2
0x100406d9  or      ecx, edx
0x100406db  lea     edi, ds:0[ecx*8]
0x100406e2  test    ebx, ebx
0x100406e4  jz      short loc_100406F7
0x100406e6  xor     eax, eax
0x100406e8  mov     ecx, 40h ; '@'
0x100406ed  cmp     ebx, 2
0x100406f0  cmovz   eax, ecx
0x100406f3  jmp     short loc_100406FC
0x100406f5  xor     edi, edi
0x100406f7  mov     eax, 40h ; '@'
0x100406fc  mov     edx, [esi]
0x100406fe  or      edi, eax
0x10040700  mov     ebx, edx
0x10040702  cmp     [esp+18h+var_C], 0
0x10040707  mov     ecx, edx
0x10040709  mov     [esi], edx
0x1004070b  jz      short loc_1004073A
0x1004070d  test    dl, 2
0x10040710  jnz     short loc_1004073A
0x10040712  mov     eax, edi
0x10040714  xor     eax, edx
0x10040716  and     eax, 180h
0x1004071b  xor     eax, edx
0x1004071d  mov     edx, eax
0x1004071f  xor     edx, edi
0x10040721  and     edx, 40h
0x10040724  xor     edx, eax
0x10040726  or      edx, 1
0x10040729  mov     ecx, edx
0x1004072b  xor     ecx, edi
0x1004072d  and     ecx, 800h
0x10040733  xor     ecx, edx
0x10040735  or      ecx, 2
0x10040738  mov     [esi], ecx
0x1004073a  test    bl, 4
0x1004073d  jnz     short loc_1004074F
0x1004073f  mov     eax, edi
0x10040741  xor     eax, ecx
0x10040743  and     eax, 400h
0x10040748  xor     ecx, eax
0x1004074a  or      ecx, 4
0x1004074d  mov     [esi], ecx
0x1004074f  mov     edx, [esp+18h+var_8]
0x10040753  mov     eax, ebx
0x10040755  lock cmpxchg [edx], ecx
0x10040759  mov     edx, eax
0x1004075b  cmp     edx, ebx
0x1004075d  jz      short loc_10040763
0x1004075f  mov     ebx, eax
0x10040761  jmp     short loc_10040702
0x10040763  test    bl, 4
0x10040766  jnz     short loc_10040777
0x10040768  push    [esp+18h+var_4]
0x1004076c  push    3
0x1004076e  push    [esp+20h+var_8]
0x10040772  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x10040777  mov     ecx, [esi]
0x10040779  test    cl, 2
0x1004077c  jnz     short loc_100407A1
0x1004077e  mov     eax, edi
0x10040780  xor     eax, ecx
0x10040782  and     eax, 180h
0x10040787  xor     eax, ecx
0x10040789  mov     ecx, edi
0x1004078b  xor     ecx, eax
0x1004078d  and     ecx, 40h
0x10040790  xor     ecx, eax
0x10040792  or      ecx, 1
0x10040795  xor     edi, ecx
0x10040797  and     edi, 800h
0x1004079d  xor     edi, ecx
0x1004079f  mov     [esi], edi
0x100407a1  pop     edi
0x100407a2  mov     eax, esi
0x100407a4  pop     esi
0x100407a5  pop     ebx
0x100407a6  mov     esp, ebp
0x100407a8  pop     ebp
0x100407a9  retn    4
```
