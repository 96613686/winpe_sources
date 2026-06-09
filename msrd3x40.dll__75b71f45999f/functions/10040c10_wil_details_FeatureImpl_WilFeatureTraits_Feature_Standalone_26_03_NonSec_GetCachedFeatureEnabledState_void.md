# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x10040c10`
- end: `0x10040d6c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10041640`

## callees

- `0x1000d7c0`
- `0x1000d8e0`
- `0x1000eb60`
- `0x10040c10`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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

  v19 = (volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor;
  v1 = (*Feature_Standalone_26_03_NonSec__descriptor)[0];
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
    v4 = v3(v3, 58599553, 3, &v18);
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
0x10040c10  mov     edi, edi
0x10040c12  push    ebp
0x10040c13  mov     ebp, esp
0x10040c15  and     esp, 0FFFFFFF8h
0x10040c18  sub     esp, 0Ch
0x10040c1b  mov     eax, ds:_Feature_Standalone_26_03_NonSec__descriptor
0x10040c20  push    ebx
0x10040c21  push    esi
0x10040c22  mov     esi, [ebp+arg_0]
0x10040c25  mov     [esp+14h+var_8], eax
0x10040c29  mov     eax, [eax]
0x10040c2b  push    edi; this
0x10040c2c  mov     dword ptr [esi], 0
0x10040c32  mov     [esi], eax
0x10040c34  and     eax, 6
0x10040c37  mov     dword ptr [esi+4], 0
0x10040c3e  cmp     al, 6
0x10040c40  jz      loc_10040D61
0x10040c46  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x10040c4b  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040c51  mov     [esp+18h+var_4], eax
0x10040c55  test    edi, edi
0x10040c57  jnz     short loc_10040C63
0x10040c59  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10040c5f  test    edi, edi
0x10040c61  jz      short loc_10040CB5
0x10040c63  lea     eax, [esp+18h+var_C]
0x10040c67  mov     ecx, edi
0x10040c69  push    eax
0x10040c6a  push    3; unsigned int
0x10040c6c  push    37E2881h; void *
0x10040c71  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10040c77  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10040c79  mov     edx, eax
0x10040c7b  and     eax, 40h
0x10040c7e  mov     ebx, edx
0x10040c80  and     edx, 80h
0x10040c86  and     ebx, 0FFFFFF3Fh
0x10040c8c  mov     ecx, ebx
0x10040c8e  and     ecx, 3
0x10040c91  shl     ecx, 2
0x10040c94  or      ecx, eax
0x10040c96  shl     ecx, 2
0x10040c99  or      ecx, edx
0x10040c9b  lea     edi, ds:0[ecx*8]
0x10040ca2  test    ebx, ebx
0x10040ca4  jz      short loc_10040CB7
0x10040ca6  xor     eax, eax
0x10040ca8  mov     ecx, 40h ; '@'
0x10040cad  cmp     ebx, 2
0x10040cb0  cmovz   eax, ecx
0x10040cb3  jmp     short loc_10040CBC
0x10040cb5  xor     edi, edi
0x10040cb7  mov     eax, 40h ; '@'
0x10040cbc  mov     edx, [esi]
0x10040cbe  or      edi, eax
0x10040cc0  mov     ebx, edx
0x10040cc2  cmp     [esp+18h+var_C], 0
0x10040cc7  mov     ecx, edx
0x10040cc9  mov     [esi], edx
0x10040ccb  jz      short loc_10040CFA
0x10040ccd  test    dl, 2
0x10040cd0  jnz     short loc_10040CFA
0x10040cd2  mov     eax, edi
0x10040cd4  xor     eax, edx
0x10040cd6  and     eax, 180h
0x10040cdb  xor     eax, edx
0x10040cdd  mov     edx, eax
0x10040cdf  xor     edx, edi
0x10040ce1  and     edx, 40h
0x10040ce4  xor     edx, eax
0x10040ce6  or      edx, 1
0x10040ce9  mov     ecx, edx
0x10040ceb  xor     ecx, edi
0x10040ced  and     ecx, 800h
0x10040cf3  xor     ecx, edx
0x10040cf5  or      ecx, 2
0x10040cf8  mov     [esi], ecx
0x10040cfa  test    bl, 4
0x10040cfd  jnz     short loc_10040D0F
0x10040cff  mov     eax, edi
0x10040d01  xor     eax, ecx
0x10040d03  and     eax, 400h
0x10040d08  xor     ecx, eax
0x10040d0a  or      ecx, 4
0x10040d0d  mov     [esi], ecx
0x10040d0f  mov     edx, [esp+18h+var_8]
0x10040d13  mov     eax, ebx
0x10040d15  lock cmpxchg [edx], ecx
0x10040d19  mov     edx, eax
0x10040d1b  cmp     edx, ebx
0x10040d1d  jz      short loc_10040D23
0x10040d1f  mov     ebx, eax
0x10040d21  jmp     short loc_10040CC2
0x10040d23  test    bl, 4
0x10040d26  jnz     short loc_10040D37
0x10040d28  push    [esp+18h+var_4]
0x10040d2c  push    3
0x10040d2e  push    [esp+20h+var_8]
0x10040d32  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x10040d37  mov     ecx, [esi]
0x10040d39  test    cl, 2
0x10040d3c  jnz     short loc_10040D61
0x10040d3e  mov     eax, edi
0x10040d40  xor     eax, ecx
0x10040d42  and     eax, 180h
0x10040d47  xor     eax, ecx
0x10040d49  mov     ecx, edi
0x10040d4b  xor     ecx, eax
0x10040d4d  and     ecx, 40h
0x10040d50  xor     ecx, eax
0x10040d52  or      ecx, 1
0x10040d55  xor     edi, ecx
0x10040d57  and     edi, 800h
0x10040d5d  xor     edi, ecx
0x10040d5f  mov     [esi], edi
0x10040d61  pop     edi
0x10040d62  mov     eax, esi
0x10040d64  pop     esi
0x10040d65  pop     ebx
0x10040d66  mov     esp, ebp
0x10040d68  pop     ebp
0x10040d69  retn    4
```
