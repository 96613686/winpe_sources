# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCachedFeatureEnabledState(void)

- ea: `0x1400052e0`
- end: `0x140005450`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400060cc`

## callees

- `0x140004d88`
- `0x1400052e0`
- `0x140008f34`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_WVD_MultiSession_User_Configuration__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WVD_MultiSession_User_Configuration__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(23685071, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
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
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_WVD_MultiSession_User_Configuration__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_WVD_MultiSession_User_Configuration__descriptor,
        0,
        v4);
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
0x1400052e0  mov     [rsp+arg_8], rbx
0x1400052e5  mov     [rsp+arg_10], rbp
0x1400052ea  mov     [rsp+arg_0], rcx
0x1400052ef  push    rsi
0x1400052f0  push    rdi
0x1400052f1  push    r15
0x1400052f3  sub     rsp, 20h
0x1400052f7  mov     rsi, cs:Feature_WVD_MultiSession_User_Configuration__descriptor
0x1400052fe  mov     rbx, rdx
0x140005301  mov     qword ptr [rdx], 0
0x140005308  mov     eax, [rsi]
0x14000530a  mov     [rdx], eax
0x14000530c  and     eax, 6
0x14000530f  cmp     al, 6
0x140005311  jz      loc_140005439
0x140005317  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000531c  mov     ebp, eax
0x14000531e  mov     dword ptr [rsp+38h+arg_0], 0
0x140005326  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000532d  xor     edx, edx
0x14000532f  test    rax, rax
0x140005332  jnz     short loc_140005340
0x140005334  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000533b  test    rax, rax
0x14000533e  jz      short loc_140005351
0x140005340  lea     r8, [rsp+38h+arg_0]
0x140005345  mov     ecx, 16967CFh
0x14000534a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000534f  mov     edx, eax
0x140005351  mov     r8d, edx
0x140005354  mov     eax, edx
0x140005356  and     r8d, 0FFFFFF3Fh
0x14000535d  and     edx, 80h
0x140005363  mov     ecx, r8d
0x140005366  mov     r15d, 40h ; '@'
0x14000536c  and     ecx, 3
0x14000536f  and     eax, r15d
0x140005372  shl     ecx, 2
0x140005375  or      ecx, eax
0x140005377  shl     ecx, 2
0x14000537a  or      ecx, edx
0x14000537c  lea     edi, ds:0[rcx*8]
0x140005383  test    r8d, r8d
0x140005386  jnz     short loc_14000538D
0x140005388  mov     eax, r15d
0x14000538b  jmp     short loc_140005397
0x14000538d  xor     eax, eax
0x14000538f  cmp     r8d, 2
0x140005393  cmovz   eax, r15d
0x140005397  or      edi, eax
0x140005399  test    ebp, ebp
0x14000539b  jnz     short loc_1400053A1
0x14000539d  mov     dword ptr [rsp+38h+arg_0], ebp
0x1400053a1  mov     eax, [rbx]
0x1400053a3  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400053a8  mov     edx, eax
0x1400053aa  mov     [rbx], eax
0x1400053ac  jz      short loc_1400053D8
0x1400053ae  test    dl, 2
0x1400053b1  jnz     short loc_1400053D8
0x1400053b3  xor     eax, edi
0x1400053b5  and     eax, 180h
0x1400053ba  xor     eax, edx
0x1400053bc  mov     ecx, eax
0x1400053be  xor     ecx, edi
0x1400053c0  and     ecx, r15d
0x1400053c3  xor     ecx, eax
0x1400053c5  or      ecx, 1
0x1400053c8  mov     eax, ecx
0x1400053ca  xor     eax, edi
0x1400053cc  and     eax, 800h
0x1400053d1  xor     eax, ecx
0x1400053d3  or      eax, 2
0x1400053d6  mov     [rbx], eax
0x1400053d8  mov     r8d, edx
0x1400053db  and     r8d, 4
0x1400053df  jnz     short loc_1400053F4
0x1400053e1  mov     ecx, edi
0x1400053e3  xor     ecx, eax
0x1400053e5  and     ecx, 400h
0x1400053eb  xor     ecx, eax
0x1400053ed  or      ecx, 4
0x1400053f0  mov     [rbx], ecx
0x1400053f2  jmp     short loc_1400053F6
0x1400053f4  mov     ecx, eax
0x1400053f6  mov     eax, edx
0x1400053f8  lock cmpxchg [rsi], ecx
0x1400053fc  jnz     short loc_1400053A3
0x1400053fe  test    r8d, r8d
0x140005401  jnz     short loc_140005410
0x140005403  mov     r8d, ebp
0x140005406  xor     edx, edx
0x140005408  mov     rcx, rsi
0x14000540b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140005410  test    byte ptr [rbx], 2
0x140005413  jnz     short loc_140005439
0x140005415  mov     eax, [rbx]
0x140005417  xor     eax, edi
0x140005419  and     eax, 180h
0x14000541e  xor     eax, [rbx]
0x140005420  mov     ecx, eax
0x140005422  xor     ecx, edi
0x140005424  and     ecx, r15d
0x140005427  xor     ecx, eax
0x140005429  or      ecx, 1
0x14000542c  mov     eax, ecx
0x14000542e  xor     eax, edi
0x140005430  and     eax, 800h
0x140005435  xor     eax, ecx
0x140005437  mov     [rbx], eax
0x140005439  mov     rbp, [rsp+38h+arg_10]
0x14000543e  mov     rax, rbx
0x140005441  mov     rbx, [rsp+38h+arg_8]
0x140005446  add     rsp, 20h
0x14000544a  pop     r15
0x14000544c  pop     rdi
0x14000544d  pop     rsi
0x14000544e  retn
```
