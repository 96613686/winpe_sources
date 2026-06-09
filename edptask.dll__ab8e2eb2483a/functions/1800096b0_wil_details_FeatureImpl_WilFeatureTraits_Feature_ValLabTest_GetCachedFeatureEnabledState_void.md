# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800096b0`
- end: `0x180009827`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d5c`

## callees

- `0x1800084b4`
- `0x1800096b0`
- `0x1800113c4`
- `0x180014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(57048226, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValLabTest__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
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
0x1800096b0  mov     [rsp+arg_8], rbx
0x1800096b5  mov     [rsp+arg_10], rbp
0x1800096ba  mov     [rsp+arg_0], rcx
0x1800096bf  push    rsi
0x1800096c0  push    rdi
0x1800096c1  push    r15
0x1800096c3  sub     rsp, 20h
0x1800096c7  mov     rsi, cs:Feature_ValLabTest__descriptor
0x1800096ce  mov     rbx, rdx
0x1800096d1  mov     qword ptr [rdx], 0
0x1800096d8  mov     eax, [rsi]
0x1800096da  mov     [rdx], eax
0x1800096dc  and     eax, 6
0x1800096df  cmp     al, 6
0x1800096e1  jz      loc_180009811
0x1800096e7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800096ec  mov     ebp, eax
0x1800096ee  mov     dword ptr [rsp+38h+arg_0], 0
0x1800096f6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800096fd  test    rax, rax
0x180009700  jz      short loc_18000971A
0x180009702  lea     r8, [rsp+38h+arg_0]
0x180009707  mov     edx, 3
0x18000970c  mov     ecx, 3667CA2h
0x180009711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009716  mov     edx, eax
0x180009718  jmp     short loc_180009728
0x18000971a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180009721  test    rax, rax
0x180009724  jnz     short loc_180009702
0x180009726  xor     edx, edx
0x180009728  mov     r8d, edx
0x18000972b  mov     eax, edx
0x18000972d  and     r8d, 0FFFFFF3Fh
0x180009734  and     edx, 80h
0x18000973a  mov     ecx, r8d
0x18000973d  mov     r15d, 40h ; '@'
0x180009743  and     ecx, 3
0x180009746  and     eax, r15d
0x180009749  shl     ecx, 2
0x18000974c  or      ecx, eax
0x18000974e  shl     ecx, 2
0x180009751  or      ecx, edx
0x180009753  lea     edi, ds:0[rcx*8]
0x18000975a  test    r8d, r8d
0x18000975d  jnz     short loc_180009764
0x18000975f  mov     eax, r15d
0x180009762  jmp     short loc_18000976E
0x180009764  xor     eax, eax
0x180009766  cmp     r8d, 2
0x18000976a  cmovz   eax, r15d
0x18000976e  or      edi, eax
0x180009770  mov     eax, [rbx]
0x180009772  cmp     dword ptr [rsp+38h+arg_0], 0
0x180009777  mov     edx, eax
0x180009779  mov     [rbx], eax
0x18000977b  jz      short loc_1800097AB
0x18000977d  test    dl, 2
0x180009780  jnz     short loc_1800097AB
0x180009782  mov     eax, edi
0x180009784  xor     eax, edx
0x180009786  and     eax, 180h
0x18000978b  xor     eax, edx
0x18000978d  mov     ecx, eax
0x18000978f  xor     ecx, edi
0x180009791  and     ecx, r15d
0x180009794  xor     ecx, eax
0x180009796  or      ecx, 1
0x180009799  mov     eax, ecx
0x18000979b  xor     eax, edi
0x18000979d  and     eax, 800h
0x1800097a2  xor     eax, ecx
0x1800097a4  or      eax, 2
0x1800097a7  mov     [rbx], eax
0x1800097a9  jmp     short loc_1800097AD
0x1800097ab  mov     eax, edx
0x1800097ad  mov     r8d, edx
0x1800097b0  and     r8d, 4
0x1800097b4  jnz     short loc_1800097C9
0x1800097b6  mov     ecx, edi
0x1800097b8  xor     ecx, eax
0x1800097ba  and     ecx, 400h
0x1800097c0  xor     ecx, eax
0x1800097c2  or      ecx, 4
0x1800097c5  mov     [rbx], ecx
0x1800097c7  jmp     short loc_1800097CB
0x1800097c9  mov     ecx, eax
0x1800097cb  mov     eax, edx
0x1800097cd  lock cmpxchg [rsi], ecx
0x1800097d1  jnz     short loc_180009772
0x1800097d3  test    r8d, r8d
0x1800097d6  jnz     short loc_1800097E8
0x1800097d8  mov     r8d, ebp
0x1800097db  mov     edx, 3
0x1800097e0  mov     rcx, rsi
0x1800097e3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800097e8  test    byte ptr [rbx], 2
0x1800097eb  jnz     short loc_180009811
0x1800097ed  mov     eax, [rbx]
0x1800097ef  xor     eax, edi
0x1800097f1  and     eax, 180h
0x1800097f6  xor     eax, [rbx]
0x1800097f8  mov     ecx, eax
0x1800097fa  xor     ecx, edi
0x1800097fc  and     ecx, r15d
0x1800097ff  xor     ecx, eax
0x180009801  or      ecx, 1
0x180009804  mov     eax, ecx
0x180009806  xor     eax, edi
0x180009808  and     eax, 800h
0x18000980d  xor     eax, ecx
0x18000980f  mov     [rbx], eax
0x180009811  mov     rbp, [rsp+38h+arg_10]
0x180009816  mov     rax, rbx
0x180009819  mov     rbx, [rsp+38h+arg_8]
0x18000981e  add     rsp, 20h
0x180009822  pop     r15
0x180009824  pop     rdi
0x180009825  pop     rsi
0x180009826  retn
```
