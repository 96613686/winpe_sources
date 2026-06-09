# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x10040aa0`
- end: `0x10040bfc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100414d0`

## callees

- `0x1000d7c0`
- `0x1000d8e0`
- `0x1000eb60`
- `0x10040aa0`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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

  v19 = (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor;
  v1 = (*Feature_Standalone_26_02_NonSec__descriptor)[0];
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
    v4 = v3(v3, 58599550, 3, &v18);
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
0x10040aa0  mov     edi, edi
0x10040aa2  push    ebp
0x10040aa3  mov     ebp, esp
0x10040aa5  and     esp, 0FFFFFFF8h
0x10040aa8  sub     esp, 0Ch
0x10040aab  mov     eax, ds:_Feature_Standalone_26_02_NonSec__descriptor
0x10040ab0  push    ebx
0x10040ab1  push    esi
0x10040ab2  mov     esi, [ebp+arg_0]
0x10040ab5  mov     [esp+14h+var_8], eax
0x10040ab9  mov     eax, [eax]
0x10040abb  push    edi; this
0x10040abc  mov     dword ptr [esi], 0
0x10040ac2  mov     [esi], eax
0x10040ac4  and     eax, 6
0x10040ac7  mov     dword ptr [esi+4], 0
0x10040ace  cmp     al, 6
0x10040ad0  jz      loc_10040BF1
0x10040ad6  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x10040adb  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040ae1  mov     [esp+18h+var_4], eax
0x10040ae5  test    edi, edi
0x10040ae7  jnz     short loc_10040AF3
0x10040ae9  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10040aef  test    edi, edi
0x10040af1  jz      short loc_10040B45
0x10040af3  lea     eax, [esp+18h+var_C]
0x10040af7  mov     ecx, edi
0x10040af9  push    eax
0x10040afa  push    3; unsigned int
0x10040afc  push    37E287Eh; void *
0x10040b01  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10040b07  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10040b09  mov     edx, eax
0x10040b0b  and     eax, 40h
0x10040b0e  mov     ebx, edx
0x10040b10  and     edx, 80h
0x10040b16  and     ebx, 0FFFFFF3Fh
0x10040b1c  mov     ecx, ebx
0x10040b1e  and     ecx, 3
0x10040b21  shl     ecx, 2
0x10040b24  or      ecx, eax
0x10040b26  shl     ecx, 2
0x10040b29  or      ecx, edx
0x10040b2b  lea     edi, ds:0[ecx*8]
0x10040b32  test    ebx, ebx
0x10040b34  jz      short loc_10040B47
0x10040b36  xor     eax, eax
0x10040b38  mov     ecx, 40h ; '@'
0x10040b3d  cmp     ebx, 2
0x10040b40  cmovz   eax, ecx
0x10040b43  jmp     short loc_10040B4C
0x10040b45  xor     edi, edi
0x10040b47  mov     eax, 40h ; '@'
0x10040b4c  mov     edx, [esi]
0x10040b4e  or      edi, eax
0x10040b50  mov     ebx, edx
0x10040b52  cmp     [esp+18h+var_C], 0
0x10040b57  mov     ecx, edx
0x10040b59  mov     [esi], edx
0x10040b5b  jz      short loc_10040B8A
0x10040b5d  test    dl, 2
0x10040b60  jnz     short loc_10040B8A
0x10040b62  mov     eax, edi
0x10040b64  xor     eax, edx
0x10040b66  and     eax, 180h
0x10040b6b  xor     eax, edx
0x10040b6d  mov     edx, eax
0x10040b6f  xor     edx, edi
0x10040b71  and     edx, 40h
0x10040b74  xor     edx, eax
0x10040b76  or      edx, 1
0x10040b79  mov     ecx, edx
0x10040b7b  xor     ecx, edi
0x10040b7d  and     ecx, 800h
0x10040b83  xor     ecx, edx
0x10040b85  or      ecx, 2
0x10040b88  mov     [esi], ecx
0x10040b8a  test    bl, 4
0x10040b8d  jnz     short loc_10040B9F
0x10040b8f  mov     eax, edi
0x10040b91  xor     eax, ecx
0x10040b93  and     eax, 400h
0x10040b98  xor     ecx, eax
0x10040b9a  or      ecx, 4
0x10040b9d  mov     [esi], ecx
0x10040b9f  mov     edx, [esp+18h+var_8]
0x10040ba3  mov     eax, ebx
0x10040ba5  lock cmpxchg [edx], ecx
0x10040ba9  mov     edx, eax
0x10040bab  cmp     edx, ebx
0x10040bad  jz      short loc_10040BB3
0x10040baf  mov     ebx, eax
0x10040bb1  jmp     short loc_10040B52
0x10040bb3  test    bl, 4
0x10040bb6  jnz     short loc_10040BC7
0x10040bb8  push    [esp+18h+var_4]
0x10040bbc  push    3
0x10040bbe  push    [esp+20h+var_8]
0x10040bc2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x10040bc7  mov     ecx, [esi]
0x10040bc9  test    cl, 2
0x10040bcc  jnz     short loc_10040BF1
0x10040bce  mov     eax, edi
0x10040bd0  xor     eax, ecx
0x10040bd2  and     eax, 180h
0x10040bd7  xor     eax, ecx
0x10040bd9  mov     ecx, edi
0x10040bdb  xor     ecx, eax
0x10040bdd  and     ecx, 40h
0x10040be0  xor     ecx, eax
0x10040be2  or      ecx, 1
0x10040be5  xor     edi, ecx
0x10040be7  and     edi, 800h
0x10040bed  xor     edi, ecx
0x10040bef  mov     [esi], edi
0x10040bf1  pop     edi
0x10040bf2  mov     eax, esi
0x10040bf4  pop     esi
0x10040bf5  pop     ebx
0x10040bf6  mov     esp, ebp
0x10040bf8  pop     ebp
0x10040bf9  retn    4
```
