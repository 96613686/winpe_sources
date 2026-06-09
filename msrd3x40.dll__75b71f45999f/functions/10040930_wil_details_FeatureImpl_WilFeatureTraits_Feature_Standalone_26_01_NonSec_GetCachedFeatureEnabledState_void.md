# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x10040930`
- end: `0x10040a8c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10041360`

## callees

- `0x1000d7c0`
- `0x1000d8e0`
- `0x1000eb60`
- `0x10040930`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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

  v19 = (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor;
  v1 = (*Feature_Standalone_26_01_NonSec__descriptor)[0];
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
    v4 = v3(v3, 58599532, 3, &v18);
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
0x10040930  mov     edi, edi
0x10040932  push    ebp
0x10040933  mov     ebp, esp
0x10040935  and     esp, 0FFFFFFF8h
0x10040938  sub     esp, 0Ch
0x1004093b  mov     eax, ds:_Feature_Standalone_26_01_NonSec__descriptor
0x10040940  push    ebx
0x10040941  push    esi
0x10040942  mov     esi, [ebp+arg_0]
0x10040945  mov     [esp+14h+var_8], eax
0x10040949  mov     eax, [eax]
0x1004094b  push    edi; this
0x1004094c  mov     dword ptr [esi], 0
0x10040952  mov     [esi], eax
0x10040954  and     eax, 6
0x10040957  mov     dword ptr [esi+4], 0
0x1004095e  cmp     al, 6
0x10040960  jz      loc_10040A81
0x10040966  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1004096b  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040971  mov     [esp+18h+var_4], eax
0x10040975  test    edi, edi
0x10040977  jnz     short loc_10040983
0x10040979  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x1004097f  test    edi, edi
0x10040981  jz      short loc_100409D5
0x10040983  lea     eax, [esp+18h+var_C]
0x10040987  mov     ecx, edi
0x10040989  push    eax
0x1004098a  push    3; unsigned int
0x1004098c  push    37E286Ch; void *
0x10040991  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10040997  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10040999  mov     edx, eax
0x1004099b  and     eax, 40h
0x1004099e  mov     ebx, edx
0x100409a0  and     edx, 80h
0x100409a6  and     ebx, 0FFFFFF3Fh
0x100409ac  mov     ecx, ebx
0x100409ae  and     ecx, 3
0x100409b1  shl     ecx, 2
0x100409b4  or      ecx, eax
0x100409b6  shl     ecx, 2
0x100409b9  or      ecx, edx
0x100409bb  lea     edi, ds:0[ecx*8]
0x100409c2  test    ebx, ebx
0x100409c4  jz      short loc_100409D7
0x100409c6  xor     eax, eax
0x100409c8  mov     ecx, 40h ; '@'
0x100409cd  cmp     ebx, 2
0x100409d0  cmovz   eax, ecx
0x100409d3  jmp     short loc_100409DC
0x100409d5  xor     edi, edi
0x100409d7  mov     eax, 40h ; '@'
0x100409dc  mov     edx, [esi]
0x100409de  or      edi, eax
0x100409e0  mov     ebx, edx
0x100409e2  cmp     [esp+18h+var_C], 0
0x100409e7  mov     ecx, edx
0x100409e9  mov     [esi], edx
0x100409eb  jz      short loc_10040A1A
0x100409ed  test    dl, 2
0x100409f0  jnz     short loc_10040A1A
0x100409f2  mov     eax, edi
0x100409f4  xor     eax, edx
0x100409f6  and     eax, 180h
0x100409fb  xor     eax, edx
0x100409fd  mov     edx, eax
0x100409ff  xor     edx, edi
0x10040a01  and     edx, 40h
0x10040a04  xor     edx, eax
0x10040a06  or      edx, 1
0x10040a09  mov     ecx, edx
0x10040a0b  xor     ecx, edi
0x10040a0d  and     ecx, 800h
0x10040a13  xor     ecx, edx
0x10040a15  or      ecx, 2
0x10040a18  mov     [esi], ecx
0x10040a1a  test    bl, 4
0x10040a1d  jnz     short loc_10040A2F
0x10040a1f  mov     eax, edi
0x10040a21  xor     eax, ecx
0x10040a23  and     eax, 400h
0x10040a28  xor     ecx, eax
0x10040a2a  or      ecx, 4
0x10040a2d  mov     [esi], ecx
0x10040a2f  mov     edx, [esp+18h+var_8]
0x10040a33  mov     eax, ebx
0x10040a35  lock cmpxchg [edx], ecx
0x10040a39  mov     edx, eax
0x10040a3b  cmp     edx, ebx
0x10040a3d  jz      short loc_10040A43
0x10040a3f  mov     ebx, eax
0x10040a41  jmp     short loc_100409E2
0x10040a43  test    bl, 4
0x10040a46  jnz     short loc_10040A57
0x10040a48  push    [esp+18h+var_4]
0x10040a4c  push    3
0x10040a4e  push    [esp+20h+var_8]
0x10040a52  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x10040a57  mov     ecx, [esi]
0x10040a59  test    cl, 2
0x10040a5c  jnz     short loc_10040A81
0x10040a5e  mov     eax, edi
0x10040a60  xor     eax, ecx
0x10040a62  and     eax, 180h
0x10040a67  xor     eax, ecx
0x10040a69  mov     ecx, edi
0x10040a6b  xor     ecx, eax
0x10040a6d  and     ecx, 40h
0x10040a70  xor     ecx, eax
0x10040a72  or      ecx, 1
0x10040a75  xor     edi, ecx
0x10040a77  and     edi, 800h
0x10040a7d  xor     edi, ecx
0x10040a7f  mov     [esi], edi
0x10040a81  pop     edi
0x10040a82  mov     eax, esi
0x10040a84  pop     esi
0x10040a85  pop     ebx
0x10040a86  mov     esp, ebp
0x10040a88  pop     ebp
0x10040a89  retn    4
```
