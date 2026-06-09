# CipUpdateCiSettingsFromPolicies

- ea: `0x180071460`
- end: `0x1800717f0`
- name: `CipUpdateCiSettingsFromPolicies`
- size: `912`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180058120`
- `0x1800706a0`

## callees

- `0x18001df98`
- `0x18002c8a0`
- `0x180058cc8`
- `0x180058d44`
- `0x1800592f0`
- `0x180061ec8`
- `0x180071460`
- `0x180074968`
- `0x180078f64`
- `0x1800796c4`
- `0x18007a658`
- `0x1800c8760`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800717a7`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800717a7`

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
0x180071460  mov     [rsp+arg_8], rbx
0x180071465  mov     [rsp+arg_10], rbp
0x18007146a  push    rsi
0x18007146b  push    rdi
0x18007146c  push    r14
0x18007146e  sub     rsp, 40h
0x180071472  xor     sil, sil
0x180071475  mov     cs:g_CiPolicyState, 1800h
0x18007147f  xor     edx, edx
0x180071481  cmp     cs:g_NumberOfSiPolicies, edx
0x180071487  jz      short loc_1800714D3
0x180071489  mov     rax, cs:g_SiPolicyHandles
0x180071490  mov     r9, [rax+rdx*8]
0x180071494  mov     r10d, [r9+48h]
0x180071498  test    r10d, r10d
0x18007149b  jz      short loc_1800714C9
0x18007149d  mov     r11, [r9+298h]
0x1800714a4  xor     r8d, r8d
0x1800714a7  mov     r9, [r9+50h]
0x1800714ab  mov     ecx, [r9+r8*4]
0x1800714af  lea     rax, [rcx+rcx*8]
0x1800714b3  add     rax, rax
0x1800714b6  cmp     dword ptr [r11+rax*8], 14h
0x1800714bb  jz      loc_180071675
0x1800714c1  inc     r8d
0x1800714c4  cmp     r8d, r10d
0x1800714c7  jb      short loc_1800714AB
0x1800714c9  inc     edx
0x1800714cb  cmp     edx, cs:g_NumberOfSiPolicies
0x1800714d1  jb      short loc_180071489
0x1800714d3  mov     eax, 41800h
0x1800714d8  mov     cs:g_CiPolicyState, eax
0x1800714de  call    SIPolicyGetActiveState
0x1800714e3  mov     [rsp+58h+arg_0], rax
0x1800714e8  movzx   ecx, byte ptr [rax+20h]
0x1800714ec  mov     eax, cs:g_CiPolicyState
0x1800714f2  and     ecx, 1
0x1800714f5  shl     ecx, 16h
0x1800714f8  btr     eax, 16h
0x1800714fc  or      ecx, eax
0x1800714fe  mov     cs:g_CiPolicyState, ecx
0x180071504  lea     rcx, [rsp+58h+arg_0]
0x180071509  call    SIPolicyReleaseState
0x18007150e  xor     r14d, r14d
0x180071511  cmp     cs:g_NumberOfSiPolicies, r14d
0x180071518  jz      loc_18007173A
0x18007151e  mov     rdi, cs:g_SiPolicyHandles
0x180071525  lea     rdx, SiPolicyIDEndpointSec; Buf2
0x18007152c  mov     r8d, 10h; Size
0x180071532  mov     rax, [rdi+r14*8]
0x180071536  cmp     dword ptr [rax+28h], 6
0x18007153a  sbb     rcx, rcx
0x18007153d  add     rax, 2D0h
0x180071543  and     rcx, 0FFFFFFFFFFFFFD40h
0x18007154a  add     rcx, rax; Buf1
0x18007154d  call    memcmp
0x180071552  test    eax, eax
0x180071554  jz      loc_18007172A
0x18007155a  mov     edx, cs:g_CiPolicyState
0x180071560  mov     r9d, 10000h
0x180071566  or      edx, 1
0x180071569  mov     cs:g_CiPolicyState, edx
0x18007156f  mov     rax, [rdi+r14*8]
0x180071573  mov     r8d, [rax+2Ch]
0x180071577  mov     ebp, r8d
0x18007157a  and     ebp, 4
0x18007157d  jz      short loc_1800715AD
0x18007157f  or      edx, 2
0x180071582  mov     cs:g_CiPolicyState, edx
0x180071588  mov     rax, [rdi+r14*8]
0x18007158c  test    [rax+2Ch], r9d
0x180071590  jnz     short loc_1800715AD
0x180071592  btr     edx, 0Bh
0x180071596  mov     cs:g_CiPolicyState, edx
0x18007159c  bt      r8d, 0Dh
0x1800715a1  jb      short loc_1800715AD
0x1800715a3  btr     edx, 0Ch
0x1800715a7  mov     cs:g_CiPolicyState, edx
0x1800715ad  mov     rax, [rdi+r14*8]
0x1800715b1  test    [rax+2Ch], r9d
0x1800715b5  jz      short loc_1800715C0
0x1800715b7  or      edx, 4
0x1800715ba  mov     cs:g_CiPolicyState, edx
0x1800715c0  test    r8b, r8b
0x1800715c3  jns     short loc_1800715CE
0x1800715c5  or      edx, 8
0x1800715c8  mov     cs:g_CiPolicyState, edx
0x1800715ce  bt      r8d, 15h
0x1800715d3  jnb     short loc_1800715DE
0x1800715d5  or      edx, 10h
0x1800715d8  mov     cs:g_CiPolicyState, edx
0x1800715de  test    r8b, 20h
0x1800715e2  jz      short loc_1800715ED
0x1800715e4  or      edx, 20h
0x1800715e7  mov     cs:g_CiPolicyState, edx
0x1800715ed  bt      r8d, 14h
0x1800715f2  jnb     short loc_1800715FE
0x1800715f4  bts     edx, 8
0x1800715f8  mov     cs:g_CiPolicyState, edx
0x1800715fe  bt      r8d, 8
0x180071603  jnb     short loc_18007160F
0x180071605  bts     edx, 9
0x180071609  mov     cs:g_CiPolicyState, edx
0x18007160f  mov     rax, [rdi+r14*8]
0x180071613  mov     ecx, [rax+2A0h]
0x180071619  test    cl, 1
0x18007161c  jz      short loc_180071627
0x18007161e  or      edx, r9d
0x180071621  mov     cs:g_CiPolicyState, edx
0x180071627  mov     rcx, [rdi+r14*8]; int
0x18007162b  xor     edx, edx; String2
0x18007162d  call    SIPolicyHasPerAppPolicy
0x180071632  test    al, al
0x180071634  jz      short loc_180071640
0x180071636  or      cs:g_CiPolicyState, 80040h
0x180071640  mov     rdx, cs:g_SiPolicyHandles
0x180071647  mov     rax, [rdx+r14*8]
0x18007164b  mov     ecx, [rax+2A0h]
0x180071651  test    cl, 4
0x180071654  jz      short loc_18007165E
0x180071656  bts     cs:g_CiPolicyState, 0Ah
0x18007165e  mov     rcx, [rdx+r14*8]
0x180071662  call    SIPolicyNightsWatchEnabled
0x180071667  test    al, al
0x180071669  jz      short loc_18007167F
0x18007166b  bts     cs:g_CiPolicyState, 0Eh
0x180071673  jmp     short loc_18007169F
0x180071675  mov     eax, 43800h
0x18007167a  jmp     loc_1800714D8
0x18007167f  mov     rcx, cs:g_SiPolicyHandles
0x180071686  mov     rcx, [rcx+r14*8]
0x18007168a  call    SIPolicyIsBasePolicy
0x18007168f  test    al, al
0x180071691  jz      short loc_18007169F
0x180071693  test    ebp, ebp
0x180071695  jz      short loc_18007169F
0x180071697  btr     cs:g_CiPolicyState, 12h
0x18007169f  mov     rdx, cs:g_SiPolicyHandles
0x1800716a6  mov     rax, [rdx+r14*8]
0x1800716aa  mov     ecx, [rax+2Ch]
0x1800716ad  test    cl, 10h
0x1800716b0  jz      short loc_1800716BA
0x1800716b2  bts     cs:g_CiPolicyState, 11h
0x1800716ba  mov     rax, [rdx+r14*8]
0x1800716be  mov     ecx, [rax+2A0h]
0x1800716c4  test    cl, 8
0x1800716c7  jz      short loc_1800716E8
0x1800716c9  or      cs:g_CiPolicyState, 8040h
0x1800716d3  mov     rcx, [rdx+r14*8]
0x1800716d7  call    SIPolicyAppIdTaggingEnforceDLL
0x1800716dc  test    al, al
0x1800716de  jz      short loc_1800716E8
0x1800716e0  bts     cs:g_CiPolicyState, 15h
0x1800716e8  mov     rax, cs:g_SiPolicyHandles
0x1800716ef  mov     rcx, [rax+r14*8]
0x1800716f3  mov     eax, [rcx+2Ch]
0x1800716f6  test    al, 10h
0x1800716f8  jnz     short loc_180071709
0x1800716fa  bt      eax, 1Bh
0x1800716fe  jb      short loc_180071709
0x180071700  call    SIPolicyNightsWatchEnabled
0x180071705  test    al, al
0x180071707  jz      short loc_18007170C
0x180071709  mov     sil, 1
0x18007170c  mov     rdi, cs:g_SiPolicyHandles
0x180071713  mov     rax, [rdi+r14*8]
0x180071717  mov     ecx, [rax+2A0h]
0x18007171d  test    cl, 40h
0x180071720  jz      short loc_18007172A
0x180071722  bts     cs:g_CiPolicyState, 14h
0x18007172a  inc     r14d
0x18007172d  cmp     r14d, cs:g_NumberOfSiPolicies
0x180071734  jb      loc_18007151E
0x18007173a  mov     ecx, cs:g_CiDeveloperMode
0x180071740  bt      ecx, 0Dh
0x180071744  jnb     short loc_180071769
0x180071746  shr     ecx, 0Ah
0x180071749  and     cl, 1
0x18007174c  call    SIPolicyAreCustomKernelSignersAllowed
0x180071751  mov     ecx, cs:g_CiPolicyState
0x180071757  and     eax, 1
0x18007175a  shl     eax, 17h
0x18007175d  btr     ecx, 17h
0x180071761  or      eax, ecx
0x180071763  mov     cs:g_CiPolicyState, eax
0x180071769  mov     cl, sil
0x18007176c  call    CipSetSmartlockerRegEnabled
0x180071771  test    sil, sil
0x180071774  jz      short loc_1800717B3
0x180071776  xor     r9d, r9d
0x180071779  mov     [rsp+58h+var_28], 0
0x180071781  mov     [rsp+58h+var_30], 0
0x180071789  lea     rdx, [rsp+58h+arg_0]
0x18007178e  lea     rcx, WNF_CI_APPLOCKERFLTR_START_REQUESTED
0x180071795  mov     byte ptr [rsp+58h+arg_0], 1
0x18007179a  mov     [rsp+58h+var_38], 0
0x1800717a3  lea     r8d, [r9+1]
0x1800717a7  call    cs:__imp_ZwUpdateWnfStateData
0x1800717ae  nop     dword ptr [rax+rax+00h]
0x1800717b3  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x1800717b8  test    eax, eax
0x1800717ba  jnz     short loc_1800717DC
0x1800717bc  xor     ecx, ecx
0x1800717be  xor     eax, eax
0x1800717c0  lock cmpxchg cs:g_EtwEventHandle, rcx
0x1800717c9  jz      short loc_1800717DC
0x1800717cb  mov     ecx, cs:g_CiPolicyState
0x1800717d1  shr     ecx, 11h
0x1800717d4  and     ecx, 1
0x1800717d7  call    CiCatDbMpSmartLockerEnable
0x1800717dc  mov     rbx, [rsp+58h+arg_8]
0x1800717e1  mov     rbp, [rsp+58h+arg_10]
0x1800717e6  add     rsp, 40h
0x1800717ea  pop     r14
0x1800717ec  pop     rdi
0x1800717ed  pop     rsi
0x1800717ee  retn
```
