# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x100407c0`
- end: `0x1004091c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100411f0`

## callees

- `0x1000d7c0`
- `0x1000d8e0`
- `0x1000eb60`
- `0x100407c0`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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

  v19 = (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor;
  v1 = (*Feature_Standalone_25_11_NonSec__descriptor)[0];
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
    v4 = v3(v3, 45036797, 3, &v18);
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
0x100407c0  mov     edi, edi
0x100407c2  push    ebp
0x100407c3  mov     ebp, esp
0x100407c5  and     esp, 0FFFFFFF8h
0x100407c8  sub     esp, 0Ch
0x100407cb  mov     eax, ds:_Feature_Standalone_25_11_NonSec__descriptor
0x100407d0  push    ebx
0x100407d1  push    esi
0x100407d2  mov     esi, [ebp+arg_0]
0x100407d5  mov     [esp+14h+var_8], eax
0x100407d9  mov     eax, [eax]
0x100407db  push    edi; this
0x100407dc  mov     dword ptr [esi], 0
0x100407e2  mov     [esi], eax
0x100407e4  and     eax, 6
0x100407e7  mov     dword ptr [esi+4], 0
0x100407ee  cmp     al, 6
0x100407f0  jz      loc_10040911
0x100407f6  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x100407fb  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040801  mov     [esp+18h+var_4], eax
0x10040805  test    edi, edi
0x10040807  jnz     short loc_10040813
0x10040809  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x1004080f  test    edi, edi
0x10040811  jz      short loc_10040865
0x10040813  lea     eax, [esp+18h+var_C]
0x10040817  mov     ecx, edi
0x10040819  push    eax
0x1004081a  push    3; unsigned int
0x1004081c  push    2AF34FDh; void *
0x10040821  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10040827  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10040829  mov     edx, eax
0x1004082b  and     eax, 40h
0x1004082e  mov     ebx, edx
0x10040830  and     edx, 80h
0x10040836  and     ebx, 0FFFFFF3Fh
0x1004083c  mov     ecx, ebx
0x1004083e  and     ecx, 3
0x10040841  shl     ecx, 2
0x10040844  or      ecx, eax
0x10040846  shl     ecx, 2
0x10040849  or      ecx, edx
0x1004084b  lea     edi, ds:0[ecx*8]
0x10040852  test    ebx, ebx
0x10040854  jz      short loc_10040867
0x10040856  xor     eax, eax
0x10040858  mov     ecx, 40h ; '@'
0x1004085d  cmp     ebx, 2
0x10040860  cmovz   eax, ecx
0x10040863  jmp     short loc_1004086C
0x10040865  xor     edi, edi
0x10040867  mov     eax, 40h ; '@'
0x1004086c  mov     edx, [esi]
0x1004086e  or      edi, eax
0x10040870  mov     ebx, edx
0x10040872  cmp     [esp+18h+var_C], 0
0x10040877  mov     ecx, edx
0x10040879  mov     [esi], edx
0x1004087b  jz      short loc_100408AA
0x1004087d  test    dl, 2
0x10040880  jnz     short loc_100408AA
0x10040882  mov     eax, edi
0x10040884  xor     eax, edx
0x10040886  and     eax, 180h
0x1004088b  xor     eax, edx
0x1004088d  mov     edx, eax
0x1004088f  xor     edx, edi
0x10040891  and     edx, 40h
0x10040894  xor     edx, eax
0x10040896  or      edx, 1
0x10040899  mov     ecx, edx
0x1004089b  xor     ecx, edi
0x1004089d  and     ecx, 800h
0x100408a3  xor     ecx, edx
0x100408a5  or      ecx, 2
0x100408a8  mov     [esi], ecx
0x100408aa  test    bl, 4
0x100408ad  jnz     short loc_100408BF
0x100408af  mov     eax, edi
0x100408b1  xor     eax, ecx
0x100408b3  and     eax, 400h
0x100408b8  xor     ecx, eax
0x100408ba  or      ecx, 4
0x100408bd  mov     [esi], ecx
0x100408bf  mov     edx, [esp+18h+var_8]
0x100408c3  mov     eax, ebx
0x100408c5  lock cmpxchg [edx], ecx
0x100408c9  mov     edx, eax
0x100408cb  cmp     edx, ebx
0x100408cd  jz      short loc_100408D3
0x100408cf  mov     ebx, eax
0x100408d1  jmp     short loc_10040872
0x100408d3  test    bl, 4
0x100408d6  jnz     short loc_100408E7
0x100408d8  push    [esp+18h+var_4]
0x100408dc  push    3
0x100408de  push    [esp+20h+var_8]
0x100408e2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x100408e7  mov     ecx, [esi]
0x100408e9  test    cl, 2
0x100408ec  jnz     short loc_10040911
0x100408ee  mov     eax, edi
0x100408f0  xor     eax, ecx
0x100408f2  and     eax, 180h
0x100408f7  xor     eax, ecx
0x100408f9  mov     ecx, edi
0x100408fb  xor     ecx, eax
0x100408fd  and     ecx, 40h
0x10040900  xor     ecx, eax
0x10040902  or      ecx, 1
0x10040905  xor     edi, ecx
0x10040907  and     edi, 800h
0x1004090d  xor     edi, ecx
0x1004090f  mov     [esi], edi
0x10040911  pop     edi
0x10040912  mov     eax, esi
0x10040914  pop     esi
0x10040915  pop     ebx
0x10040916  mov     esp, ebp
0x10040918  pop     ebp
0x10040919  retn    4
```
