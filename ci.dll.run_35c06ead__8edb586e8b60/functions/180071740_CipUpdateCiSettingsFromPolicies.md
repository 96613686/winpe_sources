# CipUpdateCiSettingsFromPolicies

- ea: `0x180071740`
- end: `0x180071ad0`
- name: `CipUpdateCiSettingsFromPolicies`
- size: `912`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180058048`
- `0x180070980`

## callees

- `0x18001e06c`
- `0x18002ca20`
- `0x180058bf0`
- `0x180058c6c`
- `0x180059218`
- `0x18006202c`
- `0x180071740`
- `0x180074c48`
- `0x180079280`
- `0x1800799d4`
- `0x18007a968`
- `0x1800c8770`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x180071a87`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180071a87`

## pseudocode

```c
__int64 CipUpdateCiSettingsFromPolicies()
{
  char v0; // si
  __int64 v1; // rdx
  __int64 v2; // r9
  unsigned int v3; // r10d
  __int64 v4; // r11
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  __int64 i; // r14
  _QWORD *v9; // rdi
  int v10; // edx
  int v11; // r8d
  int v12; // ebp
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 result; // rax
  __int64 ActiveState; // [rsp+60h] [rbp+8h] BYREF

  v0 = 0;
  g_CiPolicyState = 6144;
  v1 = 0;
  if ( g_NumberOfSiPolicies )
  {
    while ( 1 )
    {
      v2 = *((_QWORD *)g_SiPolicyHandles + v1);
      v3 = *(_DWORD *)(v2 + 72);
      if ( v3 )
        break;
LABEL_6:
      v1 = (unsigned int)(v1 + 1);
      if ( (unsigned int)v1 >= g_NumberOfSiPolicies )
        goto LABEL_7;
    }
    v4 = *(_QWORD *)(v2 + 664);
    v5 = 0;
    v6 = *(_QWORD *)(v2 + 80);
    while ( *(_DWORD *)(v4 + 144LL * *(unsigned int *)(v6 + 4 * v5)) != 20 )
    {
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= v3 )
        goto LABEL_6;
    }
    v7 = 276480;
  }
  else
  {
LABEL_7:
    v7 = 268288;
  }
  g_CiPolicyState = v7;
  ActiveState = SIPolicyGetActiveState();
  g_CiPolicyState = g_CiPolicyState & 0xFFBFFFFF | ((*(_BYTE *)(ActiveState + 32) & 1) << 22);
  SIPolicyReleaseState(&ActiveState);
  for ( i = 0; (unsigned int)i < g_NumberOfSiPolicies; i = (unsigned int)(i + 1) )
  {
    v9 = g_SiPolicyHandles;
    if ( memcmp(
           (const void *)(*((_QWORD *)g_SiPolicyHandles + i)
                        + 720LL
                        + (-(__int64)(*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + i) + 40LL) < 6u)
                         & 0xFFFFFFFFFFFFFD40uLL)),
           &SiPolicyIDEndpointSec,
           0x10u) )
    {
      v10 = g_CiPolicyState | 1;
      g_CiPolicyState |= 1u;
      v11 = *(_DWORD *)(v9[i] + 44LL);
      v12 = v11 & 4;
      if ( (v11 & 4) != 0 )
      {
        v10 |= 2u;
        g_CiPolicyState = v10;
        if ( (*(_DWORD *)(v9[i] + 44LL) & 0x10000) == 0 )
        {
          v10 &= ~0x800u;
          g_CiPolicyState = v10;
          if ( (v11 & 0x2000) == 0 )
          {
            v10 &= ~0x1000u;
            g_CiPolicyState = v10;
          }
        }
      }
      if ( (*(_DWORD *)(v9[i] + 44LL) & 0x10000) != 0 )
      {
        v10 |= 4u;
        g_CiPolicyState = v10;
      }
      if ( (v11 & 0x80u) != 0 )
      {
        v10 |= 8u;
        g_CiPolicyState = v10;
      }
      if ( (v11 & 0x200000) != 0 )
      {
        v10 |= 0x10u;
        g_CiPolicyState = v10;
      }
      if ( (v11 & 0x20) != 0 )
      {
        v10 |= 0x20u;
        g_CiPolicyState = v10;
      }
      if ( (v11 & 0x100000) != 0 )
      {
        v10 |= 0x100u;
        g_CiPolicyState = v10;
      }
      if ( (v11 & 0x100) != 0 )
      {
        v10 |= 0x200u;
        g_CiPolicyState = v10;
      }
      if ( (*(_DWORD *)(v9[i] + 672LL) & 1) != 0 )
        g_CiPolicyState = v10 | 0x10000;
      if ( (unsigned __int8)SIPolicyHasPerAppPolicy(v9[i], 0) )
        g_CiPolicyState |= 0x80040u;
      if ( (*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + i) + 672LL) & 4) != 0 )
        g_CiPolicyState |= 0x400u;
      if ( (unsigned __int8)SIPolicyNightsWatchEnabled(*((_QWORD *)g_SiPolicyHandles + i)) )
      {
        g_CiPolicyState |= 0x4000u;
      }
      else if ( (unsigned __int8)SIPolicyIsBasePolicy(*((_QWORD *)g_SiPolicyHandles + i)) && v12 )
      {
        g_CiPolicyState &= ~0x40000u;
      }
      if ( (*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + i) + 44LL) & 0x10) != 0 )
        g_CiPolicyState |= 0x20000u;
      if ( (*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + i) + 672LL) & 8) != 0 )
      {
        g_CiPolicyState |= 0x8040u;
        if ( (unsigned __int8)SIPolicyAppIdTaggingEnforceDLL(*((_QWORD *)g_SiPolicyHandles + i)) )
          g_CiPolicyState |= 0x200000u;
      }
      v13 = *((_QWORD *)g_SiPolicyHandles + i);
      v14 = *(_DWORD *)(v13 + 44);
      if ( (v14 & 0x10) != 0 || (v14 & 0x8000000) != 0 || (unsigned __int8)SIPolicyNightsWatchEnabled(v13) )
        v0 = 1;
      if ( (*(_DWORD *)(*((_QWORD *)g_SiPolicyHandles + i) + 672LL) & 0x40) != 0 )
        g_CiPolicyState |= 0x100000u;
    }
  }
  if ( (g_CiDeveloperMode & 0x2000) != 0 )
  {
    v15 = (unsigned int)g_CiDeveloperMode >> 10;
    LOBYTE(v15) = (g_CiDeveloperMode & 0x400) != 0;
    g_CiPolicyState = g_CiPolicyState & 0xFF7FFFFF | ((SIPolicyAreCustomKernelSignersAllowed(v15) & 1) << 23);
  }
  CipSetSmartlockerRegEnabled(v0);
  if ( v0 )
  {
    LOBYTE(ActiveState) = 1;
    ZwUpdateWnfStateData(&WNF_CI_APPLOCKERFLTR_START_REQUESTED, &ActiveState, 1);
  }
  result = Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v17, v16, v18);
  if ( !(_DWORD)result )
  {
    result = _InterlockedCompareExchange64((volatile signed __int64 *)&g_EtwEventHandle, 0, 0);
    if ( result )
      return CiCatDbMpSmartLockerEnable(((unsigned int)g_CiPolicyState >> 17) & 1);
  }
  return result;
}

```

## disassembly

```asm
0x180071740  mov     [rsp+arg_8], rbx
0x180071745  mov     [rsp+arg_10], rbp
0x18007174a  push    rsi
0x18007174b  push    rdi
0x18007174c  push    r14
0x18007174e  sub     rsp, 40h
0x180071752  xor     sil, sil
0x180071755  mov     cs:g_CiPolicyState, 1800h
0x18007175f  xor     edx, edx
0x180071761  cmp     cs:g_NumberOfSiPolicies, edx
0x180071767  jz      short loc_1800717B3
0x180071769  mov     rax, cs:g_SiPolicyHandles
0x180071770  mov     r9, [rax+rdx*8]
0x180071774  mov     r10d, [r9+48h]
0x180071778  test    r10d, r10d
0x18007177b  jz      short loc_1800717A9
0x18007177d  mov     r11, [r9+298h]
0x180071784  xor     r8d, r8d
0x180071787  mov     r9, [r9+50h]
0x18007178b  mov     ecx, [r9+r8*4]
0x18007178f  lea     rax, [rcx+rcx*8]
0x180071793  add     rax, rax
0x180071796  cmp     dword ptr [r11+rax*8], 14h
0x18007179b  jz      loc_180071955
0x1800717a1  inc     r8d
0x1800717a4  cmp     r8d, r10d
0x1800717a7  jb      short loc_18007178B
0x1800717a9  inc     edx
0x1800717ab  cmp     edx, cs:g_NumberOfSiPolicies
0x1800717b1  jb      short loc_180071769
0x1800717b3  mov     eax, 41800h
0x1800717b8  mov     cs:g_CiPolicyState, eax
0x1800717be  call    SIPolicyGetActiveState
0x1800717c3  mov     [rsp+58h+arg_0], rax
0x1800717c8  movzx   ecx, byte ptr [rax+20h]
0x1800717cc  mov     eax, cs:g_CiPolicyState
0x1800717d2  and     ecx, 1
0x1800717d5  shl     ecx, 16h
0x1800717d8  btr     eax, 16h
0x1800717dc  or      ecx, eax
0x1800717de  mov     cs:g_CiPolicyState, ecx
0x1800717e4  lea     rcx, [rsp+58h+arg_0]
0x1800717e9  call    SIPolicyReleaseState
0x1800717ee  xor     r14d, r14d
0x1800717f1  cmp     cs:g_NumberOfSiPolicies, r14d
0x1800717f8  jz      loc_180071A1A
0x1800717fe  mov     rdi, cs:g_SiPolicyHandles
0x180071805  lea     rdx, SiPolicyIDEndpointSec; Buf2
0x18007180c  mov     r8d, 10h; Size
0x180071812  mov     rax, [rdi+r14*8]
0x180071816  cmp     dword ptr [rax+28h], 6
0x18007181a  sbb     rcx, rcx
0x18007181d  add     rax, 2D0h
0x180071823  and     rcx, 0FFFFFFFFFFFFFD40h
0x18007182a  add     rcx, rax; Buf1
0x18007182d  call    memcmp
0x180071832  test    eax, eax
0x180071834  jz      loc_180071A0A
0x18007183a  mov     edx, cs:g_CiPolicyState
0x180071840  mov     r9d, 10000h
0x180071846  or      edx, 1
0x180071849  mov     cs:g_CiPolicyState, edx
0x18007184f  mov     rax, [rdi+r14*8]
0x180071853  mov     r8d, [rax+2Ch]
0x180071857  mov     ebp, r8d
0x18007185a  and     ebp, 4
0x18007185d  jz      short loc_18007188D
0x18007185f  or      edx, 2
0x180071862  mov     cs:g_CiPolicyState, edx
0x180071868  mov     rax, [rdi+r14*8]
0x18007186c  test    [rax+2Ch], r9d
0x180071870  jnz     short loc_18007188D
0x180071872  btr     edx, 0Bh
0x180071876  mov     cs:g_CiPolicyState, edx
0x18007187c  bt      r8d, 0Dh
0x180071881  jb      short loc_18007188D
0x180071883  btr     edx, 0Ch
0x180071887  mov     cs:g_CiPolicyState, edx
0x18007188d  mov     rax, [rdi+r14*8]
0x180071891  test    [rax+2Ch], r9d
0x180071895  jz      short loc_1800718A0
0x180071897  or      edx, 4
0x18007189a  mov     cs:g_CiPolicyState, edx
0x1800718a0  test    r8b, r8b
0x1800718a3  jns     short loc_1800718AE
0x1800718a5  or      edx, 8
0x1800718a8  mov     cs:g_CiPolicyState, edx
0x1800718ae  bt      r8d, 15h
0x1800718b3  jnb     short loc_1800718BE
0x1800718b5  or      edx, 10h
0x1800718b8  mov     cs:g_CiPolicyState, edx
0x1800718be  test    r8b, 20h
0x1800718c2  jz      short loc_1800718CD
0x1800718c4  or      edx, 20h
0x1800718c7  mov     cs:g_CiPolicyState, edx
0x1800718cd  bt      r8d, 14h
0x1800718d2  jnb     short loc_1800718DE
0x1800718d4  bts     edx, 8
0x1800718d8  mov     cs:g_CiPolicyState, edx
0x1800718de  bt      r8d, 8
0x1800718e3  jnb     short loc_1800718EF
0x1800718e5  bts     edx, 9
0x1800718e9  mov     cs:g_CiPolicyState, edx
0x1800718ef  mov     rax, [rdi+r14*8]
0x1800718f3  mov     ecx, [rax+2A0h]
0x1800718f9  test    cl, 1
0x1800718fc  jz      short loc_180071907
0x1800718fe  or      edx, r9d
0x180071901  mov     cs:g_CiPolicyState, edx
0x180071907  mov     rcx, [rdi+r14*8]; int
0x18007190b  xor     edx, edx; String2
0x18007190d  call    SIPolicyHasPerAppPolicy
0x180071912  test    al, al
0x180071914  jz      short loc_180071920
0x180071916  or      cs:g_CiPolicyState, 80040h
0x180071920  mov     rdx, cs:g_SiPolicyHandles
0x180071927  mov     rax, [rdx+r14*8]
0x18007192b  mov     ecx, [rax+2A0h]
0x180071931  test    cl, 4
0x180071934  jz      short loc_18007193E
0x180071936  bts     cs:g_CiPolicyState, 0Ah
0x18007193e  mov     rcx, [rdx+r14*8]
0x180071942  call    SIPolicyNightsWatchEnabled
0x180071947  test    al, al
0x180071949  jz      short loc_18007195F
0x18007194b  bts     cs:g_CiPolicyState, 0Eh
0x180071953  jmp     short loc_18007197F
0x180071955  mov     eax, 43800h
0x18007195a  jmp     loc_1800717B8
0x18007195f  mov     rcx, cs:g_SiPolicyHandles
0x180071966  mov     rcx, [rcx+r14*8]
0x18007196a  call    SIPolicyIsBasePolicy
0x18007196f  test    al, al
0x180071971  jz      short loc_18007197F
0x180071973  test    ebp, ebp
0x180071975  jz      short loc_18007197F
0x180071977  btr     cs:g_CiPolicyState, 12h
0x18007197f  mov     rdx, cs:g_SiPolicyHandles
0x180071986  mov     rax, [rdx+r14*8]
0x18007198a  mov     ecx, [rax+2Ch]
0x18007198d  test    cl, 10h
0x180071990  jz      short loc_18007199A
0x180071992  bts     cs:g_CiPolicyState, 11h
0x18007199a  mov     rax, [rdx+r14*8]
0x18007199e  mov     ecx, [rax+2A0h]
0x1800719a4  test    cl, 8
0x1800719a7  jz      short loc_1800719C8
0x1800719a9  or      cs:g_CiPolicyState, 8040h
0x1800719b3  mov     rcx, [rdx+r14*8]
0x1800719b7  call    SIPolicyAppIdTaggingEnforceDLL
0x1800719bc  test    al, al
0x1800719be  jz      short loc_1800719C8
0x1800719c0  bts     cs:g_CiPolicyState, 15h
0x1800719c8  mov     rax, cs:g_SiPolicyHandles
0x1800719cf  mov     rcx, [rax+r14*8]
0x1800719d3  mov     eax, [rcx+2Ch]
0x1800719d6  test    al, 10h
0x1800719d8  jnz     short loc_1800719E9
0x1800719da  bt      eax, 1Bh
0x1800719de  jb      short loc_1800719E9
0x1800719e0  call    SIPolicyNightsWatchEnabled
0x1800719e5  test    al, al
0x1800719e7  jz      short loc_1800719EC
0x1800719e9  mov     sil, 1
0x1800719ec  mov     rdi, cs:g_SiPolicyHandles
0x1800719f3  mov     rax, [rdi+r14*8]
0x1800719f7  mov     ecx, [rax+2A0h]
0x1800719fd  test    cl, 40h
0x180071a00  jz      short loc_180071A0A
0x180071a02  bts     cs:g_CiPolicyState, 14h
0x180071a0a  inc     r14d
0x180071a0d  cmp     r14d, cs:g_NumberOfSiPolicies
0x180071a14  jb      loc_1800717FE
0x180071a1a  mov     ecx, cs:g_CiDeveloperMode
0x180071a20  bt      ecx, 0Dh
0x180071a24  jnb     short loc_180071A49
0x180071a26  shr     ecx, 0Ah
0x180071a29  and     cl, 1
0x180071a2c  call    SIPolicyAreCustomKernelSignersAllowed
0x180071a31  mov     ecx, cs:g_CiPolicyState
0x180071a37  and     eax, 1
0x180071a3a  shl     eax, 17h
0x180071a3d  btr     ecx, 17h
0x180071a41  or      eax, ecx
0x180071a43  mov     cs:g_CiPolicyState, eax
0x180071a49  mov     cl, sil
0x180071a4c  call    CipSetSmartlockerRegEnabled
0x180071a51  test    sil, sil
0x180071a54  jz      short loc_180071A93
0x180071a56  xor     r9d, r9d
0x180071a59  mov     [rsp+58h+var_28], 0
0x180071a61  mov     [rsp+58h+var_30], 0
0x180071a69  lea     rdx, [rsp+58h+arg_0]
0x180071a6e  lea     rcx, WNF_CI_APPLOCKERFLTR_START_REQUESTED
0x180071a75  mov     byte ptr [rsp+58h+arg_0], 1
0x180071a7a  mov     [rsp+58h+var_38], 0
0x180071a83  lea     r8d, [r9+1]
0x180071a87  call    cs:__imp_ZwUpdateWnfStateData
0x180071a8e  nop     dword ptr [rax+rax+00h]
0x180071a93  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x180071a98  test    eax, eax
0x180071a9a  jnz     short loc_180071ABC
0x180071a9c  xor     ecx, ecx
0x180071a9e  xor     eax, eax
0x180071aa0  lock cmpxchg cs:g_EtwEventHandle, rcx
0x180071aa9  jz      short loc_180071ABC
0x180071aab  mov     ecx, cs:g_CiPolicyState
0x180071ab1  shr     ecx, 11h
0x180071ab4  and     ecx, 1
0x180071ab7  call    CiCatDbMpSmartLockerEnable
0x180071abc  mov     rbx, [rsp+58h+arg_8]
0x180071ac1  mov     rbp, [rsp+58h+arg_10]
0x180071ac6  add     rsp, 40h
0x180071aca  pop     r14
0x180071acc  pop     rdi
0x180071acd  pop     rsi
0x180071ace  retn
```
