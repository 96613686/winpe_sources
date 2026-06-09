# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800266c8`
- end: `0x180026820`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800273a4`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x18002331c`
- `0x1800266c8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34FD,
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
              (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_11_NonSec__descriptor, 3, v5);
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
0x1800266c8  mov     [rsp+arg_8], rbx
0x1800266cd  mov     [rsp+arg_10], rbp
0x1800266d2  mov     [rsp+arg_0], rcx
0x1800266d7  push    rsi
0x1800266d8  push    rdi
0x1800266d9  push    r15
0x1800266db  sub     rsp, 20h
0x1800266df  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800266e6  mov     rbx, rdx
0x1800266e9  mov     qword ptr [rdx], 0
0x1800266f0  mov     eax, [rsi]
0x1800266f2  mov     [rdx], eax
0x1800266f4  and     eax, 6
0x1800266f7  cmp     al, 6
0x1800266f9  jz      loc_18002680A
0x1800266ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026704  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180026709  mov     dword ptr [rsp+38h+arg_0], 0
0x180026711  mov     edx, 3; unsigned int
0x180026716  mov     ecx, 2AF34FDh; this
0x18002671b  mov     ebp, eax
0x18002671d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180026722  mov     r8d, eax
0x180026725  mov     ecx, eax
0x180026727  and     r8d, 0FFFFFF3Fh
0x18002672e  and     eax, 80h
0x180026733  mov     edx, r8d
0x180026736  mov     r15d, 40h ; '@'
0x18002673c  and     edx, 3
0x18002673f  and     ecx, r15d
0x180026742  shl     edx, 2
0x180026745  or      edx, ecx
0x180026747  shl     edx, 2
0x18002674a  or      edx, eax
0x18002674c  lea     edi, ds:0[rdx*8]
0x180026753  test    r8d, r8d
0x180026756  jnz     short loc_18002675D
0x180026758  mov     eax, r15d
0x18002675b  jmp     short loc_180026767
0x18002675d  xor     eax, eax
0x18002675f  cmp     r8d, 2
0x180026763  cmovz   eax, r15d
0x180026767  or      edi, eax
0x180026769  mov     eax, [rbx]
0x18002676b  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026770  mov     edx, eax
0x180026772  mov     [rbx], eax
0x180026774  jz      short loc_1800267A4
0x180026776  test    dl, 2
0x180026779  jnz     short loc_1800267A4
0x18002677b  mov     eax, edi
0x18002677d  xor     eax, edx
0x18002677f  and     eax, 180h
0x180026784  xor     eax, edx
0x180026786  mov     ecx, eax
0x180026788  xor     ecx, edi
0x18002678a  and     ecx, r15d
0x18002678d  xor     ecx, eax
0x18002678f  or      ecx, 1
0x180026792  mov     eax, ecx
0x180026794  xor     eax, edi
0x180026796  and     eax, 800h
0x18002679b  xor     eax, ecx
0x18002679d  or      eax, 2
0x1800267a0  mov     [rbx], eax
0x1800267a2  jmp     short loc_1800267A6
0x1800267a4  mov     eax, edx
0x1800267a6  mov     r8d, edx
0x1800267a9  and     r8d, 4
0x1800267ad  jnz     short loc_1800267C2
0x1800267af  mov     ecx, edi
0x1800267b1  xor     ecx, eax
0x1800267b3  and     ecx, 400h
0x1800267b9  xor     ecx, eax
0x1800267bb  or      ecx, 4
0x1800267be  mov     [rbx], ecx
0x1800267c0  jmp     short loc_1800267C4
0x1800267c2  mov     ecx, eax
0x1800267c4  mov     eax, edx
0x1800267c6  lock cmpxchg [rsi], ecx
0x1800267ca  jnz     short loc_18002676B
0x1800267cc  test    r8d, r8d
0x1800267cf  jnz     short loc_1800267E1
0x1800267d1  mov     r8d, ebp
0x1800267d4  mov     edx, 3
0x1800267d9  mov     rcx, rsi
0x1800267dc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800267e1  test    byte ptr [rbx], 2
0x1800267e4  jnz     short loc_18002680A
0x1800267e6  mov     eax, [rbx]
0x1800267e8  xor     eax, edi
0x1800267ea  and     eax, 180h
0x1800267ef  xor     eax, [rbx]
0x1800267f1  mov     ecx, eax
0x1800267f3  xor     ecx, edi
0x1800267f5  and     ecx, r15d
0x1800267f8  xor     ecx, eax
0x1800267fa  or      ecx, 1
0x1800267fd  mov     eax, ecx
0x1800267ff  xor     eax, edi
0x180026801  and     eax, 800h
0x180026806  xor     eax, ecx
0x180026808  mov     [rbx], eax
0x18002680a  mov     rbp, [rsp+38h+arg_10]
0x18002680f  mov     rax, rbx
0x180026812  mov     rbx, [rsp+38h+arg_8]
0x180026817  add     rsp, 20h
0x18002681b  pop     r15
0x18002681d  pop     rdi
0x18002681e  pop     rsi
0x18002681f  retn
```
