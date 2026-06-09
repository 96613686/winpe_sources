# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180026568`
- end: `0x1800266c0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002764c`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x18002331c`
- `0x180026568`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
                            3u,
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
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v5);
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
0x180026568  mov     [rsp+arg_8], rbx
0x18002656d  mov     [rsp+arg_10], rbp
0x180026572  mov     [rsp+arg_0], rcx
0x180026577  push    rsi
0x180026578  push    rdi
0x180026579  push    r15
0x18002657b  sub     rsp, 20h
0x18002657f  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180026586  mov     rbx, rdx
0x180026589  mov     qword ptr [rdx], 0
0x180026590  mov     eax, [rsi]
0x180026592  mov     [rdx], eax
0x180026594  and     eax, 6
0x180026597  cmp     al, 6
0x180026599  jz      loc_1800266AA
0x18002659f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800265a4  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800265a9  mov     dword ptr [rsp+38h+arg_0], 0
0x1800265b1  mov     edx, 3; unsigned int
0x1800265b6  mov     ecx, 2AF34F8h; this
0x1800265bb  mov     ebp, eax
0x1800265bd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800265c2  mov     r8d, eax
0x1800265c5  mov     ecx, eax
0x1800265c7  and     r8d, 0FFFFFF3Fh
0x1800265ce  and     eax, 80h
0x1800265d3  mov     edx, r8d
0x1800265d6  mov     r15d, 40h ; '@'
0x1800265dc  and     edx, 3
0x1800265df  and     ecx, r15d
0x1800265e2  shl     edx, 2
0x1800265e5  or      edx, ecx
0x1800265e7  shl     edx, 2
0x1800265ea  or      edx, eax
0x1800265ec  lea     edi, ds:0[rdx*8]
0x1800265f3  test    r8d, r8d
0x1800265f6  jnz     short loc_1800265FD
0x1800265f8  mov     eax, r15d
0x1800265fb  jmp     short loc_180026607
0x1800265fd  xor     eax, eax
0x1800265ff  cmp     r8d, 2
0x180026603  cmovz   eax, r15d
0x180026607  or      edi, eax
0x180026609  mov     eax, [rbx]
0x18002660b  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026610  mov     edx, eax
0x180026612  mov     [rbx], eax
0x180026614  jz      short loc_180026644
0x180026616  test    dl, 2
0x180026619  jnz     short loc_180026644
0x18002661b  mov     eax, edi
0x18002661d  xor     eax, edx
0x18002661f  and     eax, 180h
0x180026624  xor     eax, edx
0x180026626  mov     ecx, eax
0x180026628  xor     ecx, edi
0x18002662a  and     ecx, r15d
0x18002662d  xor     ecx, eax
0x18002662f  or      ecx, 1
0x180026632  mov     eax, ecx
0x180026634  xor     eax, edi
0x180026636  and     eax, 800h
0x18002663b  xor     eax, ecx
0x18002663d  or      eax, 2
0x180026640  mov     [rbx], eax
0x180026642  jmp     short loc_180026646
0x180026644  mov     eax, edx
0x180026646  mov     r8d, edx
0x180026649  and     r8d, 4
0x18002664d  jnz     short loc_180026662
0x18002664f  mov     ecx, edi
0x180026651  xor     ecx, eax
0x180026653  and     ecx, 400h
0x180026659  xor     ecx, eax
0x18002665b  or      ecx, 4
0x18002665e  mov     [rbx], ecx
0x180026660  jmp     short loc_180026664
0x180026662  mov     ecx, eax
0x180026664  mov     eax, edx
0x180026666  lock cmpxchg [rsi], ecx
0x18002666a  jnz     short loc_18002660B
0x18002666c  test    r8d, r8d
0x18002666f  jnz     short loc_180026681
0x180026671  mov     r8d, ebp
0x180026674  mov     edx, 3
0x180026679  mov     rcx, rsi
0x18002667c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026681  test    byte ptr [rbx], 2
0x180026684  jnz     short loc_1800266AA
0x180026686  mov     eax, [rbx]
0x180026688  xor     eax, edi
0x18002668a  and     eax, 180h
0x18002668f  xor     eax, [rbx]
0x180026691  mov     ecx, eax
0x180026693  xor     ecx, edi
0x180026695  and     ecx, r15d
0x180026698  xor     ecx, eax
0x18002669a  or      ecx, 1
0x18002669d  mov     eax, ecx
0x18002669f  xor     eax, edi
0x1800266a1  and     eax, 800h
0x1800266a6  xor     eax, ecx
0x1800266a8  mov     [rbx], eax
0x1800266aa  mov     rbp, [rsp+38h+arg_10]
0x1800266af  mov     rax, rbx
0x1800266b2  mov     rbx, [rsp+38h+arg_8]
0x1800266b7  add     rsp, 20h
0x1800266bb  pop     r15
0x1800266bd  pop     rdi
0x1800266be  pop     rsi
0x1800266bf  retn
```
