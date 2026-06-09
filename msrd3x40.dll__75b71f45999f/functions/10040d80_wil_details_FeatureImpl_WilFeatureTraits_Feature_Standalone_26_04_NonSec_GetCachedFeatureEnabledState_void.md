# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x10040d80`
- end: `0x10040edc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AAE?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100417b0`

## callees

- `0x1000d7c0`
- `0x1000d8e0`
- `0x1000eb60`
- `0x10040d80`

## pseudocode

```c
int *__stdcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
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

  v19 = (volatile signed __int32 *)Feature_Standalone_26_04_NonSec__descriptor;
  v1 = (*Feature_Standalone_26_04_NonSec__descriptor)[0];
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
    v4 = v3(v3, 58599559, 3, &v18);
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
0x10040d80  mov     edi, edi
0x10040d82  push    ebp
0x10040d83  mov     ebp, esp
0x10040d85  and     esp, 0FFFFFFF8h
0x10040d88  sub     esp, 0Ch
0x10040d8b  mov     eax, ds:_Feature_Standalone_26_04_NonSec__descriptor
0x10040d90  push    ebx
0x10040d91  push    esi
0x10040d92  mov     esi, [ebp+arg_0]
0x10040d95  mov     [esp+14h+var_8], eax
0x10040d99  mov     eax, [eax]
0x10040d9b  push    edi; this
0x10040d9c  mov     dword ptr [esi], 0
0x10040da2  mov     [esi], eax
0x10040da4  and     eax, 6
0x10040da7  mov     dword ptr [esi+4], 0
0x10040dae  cmp     al, 6
0x10040db0  jz      loc_10040ED1
0x10040db6  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x10040dbb  mov     edi, _g_wil_details_internalGetFeatureEnabledState
0x10040dc1  mov     [esp+18h+var_4], eax
0x10040dc5  test    edi, edi
0x10040dc7  jnz     short loc_10040DD3
0x10040dc9  mov     edi, _g_wil_details_apiGetFeatureEnabledState
0x10040dcf  test    edi, edi
0x10040dd1  jz      short loc_10040E25
0x10040dd3  lea     eax, [esp+18h+var_C]
0x10040dd7  mov     ecx, edi
0x10040dd9  push    eax
0x10040dda  push    3; unsigned int
0x10040ddc  push    37E2887h; void *
0x10040de1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10040de7  call    edi ; _g_wil_details_internalGetFeatureEnabledState
0x10040de9  mov     edx, eax
0x10040deb  and     eax, 40h
0x10040dee  mov     ebx, edx
0x10040df0  and     edx, 80h
0x10040df6  and     ebx, 0FFFFFF3Fh
0x10040dfc  mov     ecx, ebx
0x10040dfe  and     ecx, 3
0x10040e01  shl     ecx, 2
0x10040e04  or      ecx, eax
0x10040e06  shl     ecx, 2
0x10040e09  or      ecx, edx
0x10040e0b  lea     edi, ds:0[ecx*8]
0x10040e12  test    ebx, ebx
0x10040e14  jz      short loc_10040E27
0x10040e16  xor     eax, eax
0x10040e18  mov     ecx, 40h ; '@'
0x10040e1d  cmp     ebx, 2
0x10040e20  cmovz   eax, ecx
0x10040e23  jmp     short loc_10040E2C
0x10040e25  xor     edi, edi
0x10040e27  mov     eax, 40h ; '@'
0x10040e2c  mov     edx, [esi]
0x10040e2e  or      edi, eax
0x10040e30  mov     ebx, edx
0x10040e32  cmp     [esp+18h+var_C], 0
0x10040e37  mov     ecx, edx
0x10040e39  mov     [esi], edx
0x10040e3b  jz      short loc_10040E6A
0x10040e3d  test    dl, 2
0x10040e40  jnz     short loc_10040E6A
0x10040e42  mov     eax, edi
0x10040e44  xor     eax, edx
0x10040e46  and     eax, 180h
0x10040e4b  xor     eax, edx
0x10040e4d  mov     edx, eax
0x10040e4f  xor     edx, edi
0x10040e51  and     edx, 40h
0x10040e54  xor     edx, eax
0x10040e56  or      edx, 1
0x10040e59  mov     ecx, edx
0x10040e5b  xor     ecx, edi
0x10040e5d  and     ecx, 800h
0x10040e63  xor     ecx, edx
0x10040e65  or      ecx, 2
0x10040e68  mov     [esi], ecx
0x10040e6a  test    bl, 4
0x10040e6d  jnz     short loc_10040E7F
0x10040e6f  mov     eax, edi
0x10040e71  xor     eax, ecx
0x10040e73  and     eax, 400h
0x10040e78  xor     ecx, eax
0x10040e7a  or      ecx, 4
0x10040e7d  mov     [esi], ecx
0x10040e7f  mov     edx, [esp+18h+var_8]
0x10040e83  mov     eax, ebx
0x10040e85  lock cmpxchg [edx], ecx
0x10040e89  mov     edx, eax
0x10040e8b  cmp     edx, ebx
0x10040e8d  jz      short loc_10040E93
0x10040e8f  mov     ebx, eax
0x10040e91  jmp     short loc_10040E32
0x10040e93  test    bl, 4
0x10040e96  jnz     short loc_10040EA7
0x10040e98  push    [esp+18h+var_4]
0x10040e9c  push    3
0x10040e9e  push    [esp+20h+var_8]
0x10040ea2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x10040ea7  mov     ecx, [esi]
0x10040ea9  test    cl, 2
0x10040eac  jnz     short loc_10040ED1
0x10040eae  mov     eax, edi
0x10040eb0  xor     eax, ecx
0x10040eb2  and     eax, 180h
0x10040eb7  xor     eax, ecx
0x10040eb9  mov     ecx, edi
0x10040ebb  xor     ecx, eax
0x10040ebd  and     ecx, 40h
0x10040ec0  xor     ecx, eax
0x10040ec2  or      ecx, 1
0x10040ec5  xor     edi, ecx
0x10040ec7  and     edi, 800h
0x10040ecd  xor     edi, ecx
0x10040ecf  mov     [esi], edi
0x10040ed1  pop     edi
0x10040ed2  mov     eax, esi
0x10040ed4  pop     esi
0x10040ed5  pop     ebx
0x10040ed6  mov     esp, ebp
0x10040ed8  pop     ebp
0x10040ed9  retn    4
```
