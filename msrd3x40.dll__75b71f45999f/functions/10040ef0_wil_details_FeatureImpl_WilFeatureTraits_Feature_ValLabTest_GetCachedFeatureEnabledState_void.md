# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x10040ef0`
- end: `0x1004104c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
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
- `0x10040ef0`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(int *a1)
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

  v19 = (volatile signed __int32 *)Feature_ValLabTest__descriptor;
  v1 = (*Feature_ValLabTest__descriptor)[0];
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
    v4 = v3(v3, 57048226, 3, &v18);
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
0x10040ef0  mov     edi, edi
0x10040ef2  push    ebp
0x10040ef3  mov     ebp, esp
0x10040ef5  and     esp, 0FFFFFFF8h
0x10040ef8  sub     esp, 0Ch
0x10040efb  mov     eax, ds:_Feature_ValLabTest__descriptor
0x10040f00  push    ebx
0x10040f01  push    esi
0x10040f02  mov     esi, [ebp+arg_0]
0x10040f05  mov     [esp+14h+var_8], eax
0x10040f09  mov     eax, [eax]
0x10040f0b  push    edi; this
0x10040f0c  mov     dword ptr [esi], 0
0x10040f12  mov     [esi], eax
0x10040f14  and     eax, 6
0x10040f17  mov     dword ptr [esi+4], 0
0x10040f1e  cmp     al, 6
0x10040f20  jz      loc_10041041
0x10040f26  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x10040f2b  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040f31  mov     [esp+18h+var_4], eax
0x10040f35  test    edi, edi
0x10040f37  jnz     short loc_10040F43
0x10040f39  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10040f3f  test    edi, edi
0x10040f41  jz      short loc_10040F95
0x10040f43  lea     eax, [esp+18h+var_C]
0x10040f47  mov     ecx, edi
0x10040f49  push    eax
0x10040f4a  push    3; unsigned int
0x10040f4c  push    3667CA2h; void *
0x10040f51  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10040f57  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10040f59  mov     edx, eax
0x10040f5b  and     eax, 40h
0x10040f5e  mov     ebx, edx
0x10040f60  and     edx, 80h
0x10040f66  and     ebx, 0FFFFFF3Fh
0x10040f6c  mov     ecx, ebx
0x10040f6e  and     ecx, 3
0x10040f71  shl     ecx, 2
0x10040f74  or      ecx, eax
0x10040f76  shl     ecx, 2
0x10040f79  or      ecx, edx
0x10040f7b  lea     edi, ds:0[ecx*8]
0x10040f82  test    ebx, ebx
0x10040f84  jz      short loc_10040F97
0x10040f86  xor     eax, eax
0x10040f88  mov     ecx, 40h ; '@'
0x10040f8d  cmp     ebx, 2
0x10040f90  cmovz   eax, ecx
0x10040f93  jmp     short loc_10040F9C
0x10040f95  xor     edi, edi
0x10040f97  mov     eax, 40h ; '@'
0x10040f9c  mov     edx, [esi]
0x10040f9e  or      edi, eax
0x10040fa0  mov     ebx, edx
0x10040fa2  cmp     [esp+18h+var_C], 0
0x10040fa7  mov     ecx, edx
0x10040fa9  mov     [esi], edx
0x10040fab  jz      short loc_10040FDA
0x10040fad  test    dl, 2
0x10040fb0  jnz     short loc_10040FDA
0x10040fb2  mov     eax, edi
0x10040fb4  xor     eax, edx
0x10040fb6  and     eax, 180h
0x10040fbb  xor     eax, edx
0x10040fbd  mov     edx, eax
0x10040fbf  xor     edx, edi
0x10040fc1  and     edx, 40h
0x10040fc4  xor     edx, eax
0x10040fc6  or      edx, 1
0x10040fc9  mov     ecx, edx
0x10040fcb  xor     ecx, edi
0x10040fcd  and     ecx, 800h
0x10040fd3  xor     ecx, edx
0x10040fd5  or      ecx, 2
0x10040fd8  mov     [esi], ecx
0x10040fda  test    bl, 4
0x10040fdd  jnz     short loc_10040FEF
0x10040fdf  mov     eax, edi
0x10040fe1  xor     eax, ecx
0x10040fe3  and     eax, 400h
0x10040fe8  xor     ecx, eax
0x10040fea  or      ecx, 4
0x10040fed  mov     [esi], ecx
0x10040fef  mov     edx, [esp+18h+var_8]
0x10040ff3  mov     eax, ebx
0x10040ff5  lock cmpxchg [edx], ecx
0x10040ff9  mov     edx, eax
0x10040ffb  cmp     edx, ebx
0x10040ffd  jz      short loc_10041003
0x10040fff  mov     ebx, eax
0x10041001  jmp     short loc_10040FA2
0x10041003  test    bl, 4
0x10041006  jnz     short loc_10041017
0x10041008  push    [esp+18h+var_4]
0x1004100c  push    3
0x1004100e  push    [esp+20h+var_8]
0x10041012  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x10041017  mov     ecx, [esi]
0x10041019  test    cl, 2
0x1004101c  jnz     short loc_10041041
0x1004101e  mov     eax, edi
0x10041020  xor     eax, ecx
0x10041022  and     eax, 180h
0x10041027  xor     eax, ecx
0x10041029  mov     ecx, edi
0x1004102b  xor     ecx, eax
0x1004102d  and     ecx, 40h
0x10041030  xor     ecx, eax
0x10041032  or      ecx, 1
0x10041035  xor     edi, ecx
0x10041037  and     edi, 800h
0x1004103d  xor     edi, ecx
0x1004103f  mov     [esi], edi
0x10041041  pop     edi
0x10041042  mov     eax, esi
0x10041044  pop     esi
0x10041045  pop     ebx
0x10041046  mov     esp, ebp
0x10041048  pop     ebp
0x10041049  retn    4
```
