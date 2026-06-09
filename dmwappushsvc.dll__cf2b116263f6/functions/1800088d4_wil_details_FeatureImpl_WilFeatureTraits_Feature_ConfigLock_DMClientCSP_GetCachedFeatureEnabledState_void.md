# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetCachedFeatureEnabledState(void)

- ea: `0x1800088d4`
- end: `0x180008a21`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `333`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ad14`

## callees

- `0x1800084a8`
- `0x1800088d4`
- `0x18000b604`
- `0x18000bfa4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  unsigned int v6; // edx
  wil::details *v7; // rcx
  int *v8; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v10; // r8d
  int v11; // edi
  int v12; // eax
  int v13; // edi
  int v14; // eax
  bool v15; // zf
  signed __int32 v16; // edx
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ConfigLock_DMClientCSP__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ConfigLock_DMClientCSP__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v19) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(v7, v6, (enum FEATURE_CHANGE_TIME)&v19, v8);
    v10 = FeatureEnabledState & 0xFFFFFF3F;
    v11 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v12 = 0;
      if ( v10 == 2 )
        v12 = 64;
    }
    else
    {
      v12 = 64;
    }
    v13 = v12 | v11;
    if ( !v5 )
      LODWORD(v19) = 0;
    v14 = *(_DWORD *)a2;
    do
    {
      v15 = (_DWORD)v19 == 0;
      v16 = v14;
      *(_DWORD *)a2 = v14;
      if ( !v15 && (v14 & 2) == 0 )
      {
        v14 = (v14
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v14)
             & 0x180
             ^ (v13
              ^ v14
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v14)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v13
             ^ ((unsigned __int16)(v14 ^ (v13 ^ v14) & 0x180 ^ (v13 ^ v14 ^ (v13 ^ v14) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v14;
      }
      if ( (v16 & 4) != 0 )
      {
        v17 = v14;
      }
      else
      {
        v17 = v14 ^ ((unsigned __int16)v14 ^ (unsigned __int16)v13) & 0x400 | 4;
        *(_DWORD *)a2 = v17;
      }
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ConfigLock_DMClientCSP__descriptor, v17, v16);
    }
    while ( v16 != v14 );
    if ( (v16 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ConfigLock_DMClientCSP__descriptor, 0, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v13
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v13
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v13
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v13
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v13
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v13
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x1800088d4  mov     [rsp+arg_8], rbx
0x1800088d9  mov     [rsp+arg_10], rbp
0x1800088de  mov     [rsp+arg_0], rcx
0x1800088e3  push    rsi
0x1800088e4  push    rdi
0x1800088e5  push    r15
0x1800088e7  sub     rsp, 20h
0x1800088eb  mov     rsi, cs:Feature_ConfigLock_DMClientCSP__descriptor
0x1800088f2  mov     rbx, rdx
0x1800088f5  mov     qword ptr [rdx], 0
0x1800088fc  mov     eax, [rsi]
0x1800088fe  mov     [rdx], eax
0x180008900  and     eax, 6
0x180008903  cmp     al, 6
0x180008905  jz      loc_180008A0B
0x18000890b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008910  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180008915  mov     dword ptr [rsp+38h+arg_0], 0
0x18000891d  mov     ebp, eax
0x18000891f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008924  mov     r8d, eax
0x180008927  mov     ecx, eax
0x180008929  and     r8d, 0FFFFFF3Fh
0x180008930  and     eax, 80h
0x180008935  mov     edx, r8d
0x180008938  mov     r15d, 40h ; '@'
0x18000893e  and     edx, 3
0x180008941  and     ecx, r15d
0x180008944  shl     edx, 2
0x180008947  or      edx, ecx
0x180008949  shl     edx, 2
0x18000894c  or      edx, eax
0x18000894e  lea     edi, ds:0[rdx*8]
0x180008955  test    r8d, r8d
0x180008958  jnz     short loc_18000895F
0x18000895a  mov     eax, r15d
0x18000895d  jmp     short loc_180008969
0x18000895f  xor     eax, eax
0x180008961  cmp     r8d, 2
0x180008965  cmovz   eax, r15d
0x180008969  or      edi, eax
0x18000896b  test    ebp, ebp
0x18000896d  jnz     short loc_180008973
0x18000896f  mov     dword ptr [rsp+38h+arg_0], ebp
0x180008973  mov     eax, [rbx]
0x180008975  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000897a  mov     edx, eax
0x18000897c  mov     [rbx], eax
0x18000897e  jz      short loc_1800089AA
0x180008980  test    dl, 2
0x180008983  jnz     short loc_1800089AA
0x180008985  xor     eax, edi
0x180008987  and     eax, 180h
0x18000898c  xor     eax, edx
0x18000898e  mov     ecx, eax
0x180008990  xor     ecx, edi
0x180008992  and     ecx, r15d
0x180008995  xor     ecx, eax
0x180008997  or      ecx, 1
0x18000899a  mov     eax, ecx
0x18000899c  xor     eax, edi
0x18000899e  and     eax, 800h
0x1800089a3  xor     eax, ecx
0x1800089a5  or      eax, 2
0x1800089a8  mov     [rbx], eax
0x1800089aa  mov     r8d, edx
0x1800089ad  and     r8d, 4
0x1800089b1  jnz     short loc_1800089C6
0x1800089b3  mov     ecx, edi
0x1800089b5  xor     ecx, eax
0x1800089b7  and     ecx, 400h
0x1800089bd  xor     ecx, eax
0x1800089bf  or      ecx, 4
0x1800089c2  mov     [rbx], ecx
0x1800089c4  jmp     short loc_1800089C8
0x1800089c6  mov     ecx, eax
0x1800089c8  mov     eax, edx
0x1800089ca  lock cmpxchg [rsi], ecx
0x1800089ce  jnz     short loc_180008975
0x1800089d0  test    r8d, r8d
0x1800089d3  jnz     short loc_1800089E2
0x1800089d5  mov     r8d, ebp
0x1800089d8  xor     edx, edx
0x1800089da  mov     rcx, rsi
0x1800089dd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800089e2  test    byte ptr [rbx], 2
0x1800089e5  jnz     short loc_180008A0B
0x1800089e7  mov     eax, [rbx]
0x1800089e9  xor     eax, edi
0x1800089eb  and     eax, 180h
0x1800089f0  xor     eax, [rbx]
0x1800089f2  mov     ecx, eax
0x1800089f4  xor     ecx, edi
0x1800089f6  and     ecx, r15d
0x1800089f9  xor     ecx, eax
0x1800089fb  or      ecx, 1
0x1800089fe  mov     eax, ecx
0x180008a00  xor     eax, edi
0x180008a02  and     eax, 800h
0x180008a07  xor     eax, ecx
0x180008a09  mov     [rbx], eax
0x180008a0b  mov     rbp, [rsp+38h+arg_10]
0x180008a10  mov     rax, rbx
0x180008a13  mov     rbx, [rsp+38h+arg_8]
0x180008a18  add     rsp, 20h
0x180008a1c  pop     r15
0x180008a1e  pop     rdi
0x180008a1f  pop     rsi
0x180008a20  retn
```
