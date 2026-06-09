# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs>::GetCachedFeatureEnabledState(void)

- ea: `0x1800164c8`
- end: `0x180016622`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `346`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018838`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x1800164c8`
- `0x18002331c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2908EC3,
                            0,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    if ( !v5 )
      LODWORD(v17) = 0;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs__descriptor,
        0,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x1800164c8  mov     [rsp+arg_8], rbx
0x1800164cd  mov     [rsp+arg_10], rbp
0x1800164d2  mov     [rsp+arg_0], rcx
0x1800164d7  push    rsi
0x1800164d8  push    rdi
0x1800164d9  push    r15
0x1800164db  sub     rsp, 20h
0x1800164df  mov     rsi, cs:Feature_BitLocker_Reduce_Auto_DE_Hardware_Reqs__descriptor
0x1800164e6  mov     rbx, rdx
0x1800164e9  mov     qword ptr [rdx], 0
0x1800164f0  mov     eax, [rsi]
0x1800164f2  mov     [rdx], eax
0x1800164f4  and     eax, 6
0x1800164f7  cmp     al, 6
0x1800164f9  jz      loc_18001660C
0x1800164ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016504  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180016509  mov     dword ptr [rsp+38h+arg_0], 0
0x180016511  xor     edx, edx; unsigned int
0x180016513  mov     ecx, 2908EC3h; this
0x180016518  mov     ebp, eax
0x18001651a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001651f  mov     r8d, eax
0x180016522  mov     ecx, eax
0x180016524  and     r8d, 0FFFFFF3Fh
0x18001652b  and     eax, 80h
0x180016530  mov     edx, r8d
0x180016533  mov     r15d, 40h ; '@'
0x180016539  and     edx, 3
0x18001653c  and     ecx, r15d
0x18001653f  shl     edx, 2
0x180016542  or      edx, ecx
0x180016544  shl     edx, 2
0x180016547  or      edx, eax
0x180016549  lea     edi, ds:0[rdx*8]
0x180016550  test    r8d, r8d
0x180016553  jnz     short loc_18001655A
0x180016555  mov     eax, r15d
0x180016558  jmp     short loc_180016564
0x18001655a  xor     eax, eax
0x18001655c  cmp     r8d, 2
0x180016560  cmovz   eax, r15d
0x180016564  or      edi, eax
0x180016566  test    ebp, ebp
0x180016568  jnz     short loc_18001656E
0x18001656a  mov     dword ptr [rsp+38h+arg_0], ebp
0x18001656e  mov     eax, [rbx]
0x180016570  cmp     dword ptr [rsp+38h+arg_0], 0
0x180016575  mov     edx, eax
0x180016577  mov     [rbx], eax
0x180016579  jz      short loc_1800165A9
0x18001657b  test    dl, 2
0x18001657e  jnz     short loc_1800165A9
0x180016580  mov     eax, edi
0x180016582  xor     eax, edx
0x180016584  and     eax, 180h
0x180016589  xor     eax, edx
0x18001658b  mov     ecx, eax
0x18001658d  xor     ecx, edi
0x18001658f  and     ecx, r15d
0x180016592  xor     ecx, eax
0x180016594  or      ecx, 1
0x180016597  mov     eax, ecx
0x180016599  xor     eax, edi
0x18001659b  and     eax, 800h
0x1800165a0  xor     eax, ecx
0x1800165a2  or      eax, 2
0x1800165a5  mov     [rbx], eax
0x1800165a7  jmp     short loc_1800165AB
0x1800165a9  mov     eax, edx
0x1800165ab  mov     r8d, edx
0x1800165ae  and     r8d, 4
0x1800165b2  jnz     short loc_1800165C7
0x1800165b4  mov     ecx, edi
0x1800165b6  xor     ecx, eax
0x1800165b8  and     ecx, 400h
0x1800165be  xor     ecx, eax
0x1800165c0  or      ecx, 4
0x1800165c3  mov     [rbx], ecx
0x1800165c5  jmp     short loc_1800165C9
0x1800165c7  mov     ecx, eax
0x1800165c9  mov     eax, edx
0x1800165cb  lock cmpxchg [rsi], ecx
0x1800165cf  jnz     short loc_180016570
0x1800165d1  test    r8d, r8d
0x1800165d4  jnz     short loc_1800165E3
0x1800165d6  mov     r8d, ebp
0x1800165d9  xor     edx, edx
0x1800165db  mov     rcx, rsi
0x1800165de  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800165e3  test    byte ptr [rbx], 2
0x1800165e6  jnz     short loc_18001660C
0x1800165e8  mov     eax, [rbx]
0x1800165ea  xor     eax, edi
0x1800165ec  and     eax, 180h
0x1800165f1  xor     eax, [rbx]
0x1800165f3  mov     ecx, eax
0x1800165f5  xor     ecx, edi
0x1800165f7  and     ecx, r15d
0x1800165fa  xor     ecx, eax
0x1800165fc  or      ecx, 1
0x1800165ff  mov     eax, ecx
0x180016601  xor     eax, edi
0x180016603  and     eax, 800h
0x180016608  xor     eax, ecx
0x18001660a  mov     [rbx], eax
0x18001660c  mov     rbp, [rsp+38h+arg_10]
0x180016611  mov     rax, rbx
0x180016614  mov     rbx, [rsp+38h+arg_8]
0x180016619  add     rsp, 20h
0x18001661d  pop     r15
0x18001661f  pop     rdi
0x180016620  pop     rsi
0x180016621  retn
```
