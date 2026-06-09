# CipUpdateCiSettingsFromPolicies

- ea: `0x1800701b0`
- end: `0x180070540`
- name: `CipUpdateCiSettingsFromPolicies`
- size: `912`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180057408`
- `0x18006f3f0`

## callees

- `0x18001e054`
- `0x18002c860`
- `0x180057fb0`
- `0x18005802c`
- `0x1800585d8`
- `0x180061684`
- `0x1800701b0`
- `0x1800736b8`
- `0x1800779b4`
- `0x180078114`
- `0x1800790a8`
- `0x1800c72e0`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800704f7`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800704f7`

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
0x1800701b0  mov     [rsp+arg_8], rbx
0x1800701b5  mov     [rsp+arg_10], rbp
0x1800701ba  push    rsi
0x1800701bb  push    rdi
0x1800701bc  push    r14
0x1800701be  sub     rsp, 40h
0x1800701c2  xor     sil, sil
0x1800701c5  mov     cs:g_CiPolicyState, 1800h
0x1800701cf  xor     edx, edx
0x1800701d1  cmp     cs:g_NumberOfSiPolicies, edx
0x1800701d7  jz      short loc_180070223
0x1800701d9  mov     rax, cs:g_SiPolicyHandles
0x1800701e0  mov     r9, [rax+rdx*8]
0x1800701e4  mov     r10d, [r9+48h]
0x1800701e8  test    r10d, r10d
0x1800701eb  jz      short loc_180070219
0x1800701ed  mov     r11, [r9+298h]
0x1800701f4  xor     r8d, r8d
0x1800701f7  mov     r9, [r9+50h]
0x1800701fb  mov     ecx, [r9+r8*4]
0x1800701ff  lea     rax, [rcx+rcx*8]
0x180070203  add     rax, rax
0x180070206  cmp     dword ptr [r11+rax*8], 14h
0x18007020b  jz      loc_1800703C5
0x180070211  inc     r8d
0x180070214  cmp     r8d, r10d
0x180070217  jb      short loc_1800701FB
0x180070219  inc     edx
0x18007021b  cmp     edx, cs:g_NumberOfSiPolicies
0x180070221  jb      short loc_1800701D9
0x180070223  mov     eax, 41800h
0x180070228  mov     cs:g_CiPolicyState, eax
0x18007022e  call    SIPolicyGetActiveState
0x180070233  mov     [rsp+58h+arg_0], rax
0x180070238  movzx   ecx, byte ptr [rax+20h]
0x18007023c  mov     eax, cs:g_CiPolicyState
0x180070242  and     ecx, 1
0x180070245  shl     ecx, 16h
0x180070248  btr     eax, 16h
0x18007024c  or      ecx, eax
0x18007024e  mov     cs:g_CiPolicyState, ecx
0x180070254  lea     rcx, [rsp+58h+arg_0]
0x180070259  call    SIPolicyReleaseState
0x18007025e  xor     r14d, r14d
0x180070261  cmp     cs:g_NumberOfSiPolicies, r14d
0x180070268  jz      loc_18007048A
0x18007026e  mov     rdi, cs:g_SiPolicyHandles
0x180070275  lea     rdx, SiPolicyIDEndpointSec; Buf2
0x18007027c  mov     r8d, 10h; Size
0x180070282  mov     rax, [rdi+r14*8]
0x180070286  cmp     dword ptr [rax+28h], 6
0x18007028a  sbb     rcx, rcx
0x18007028d  add     rax, 2D0h
0x180070293  and     rcx, 0FFFFFFFFFFFFFD40h
0x18007029a  add     rcx, rax; Buf1
0x18007029d  call    memcmp
0x1800702a2  test    eax, eax
0x1800702a4  jz      loc_18007047A
0x1800702aa  mov     edx, cs:g_CiPolicyState
0x1800702b0  mov     r9d, 10000h
0x1800702b6  or      edx, 1
0x1800702b9  mov     cs:g_CiPolicyState, edx
0x1800702bf  mov     rax, [rdi+r14*8]
0x1800702c3  mov     r8d, [rax+2Ch]
0x1800702c7  mov     ebp, r8d
0x1800702ca  and     ebp, 4
0x1800702cd  jz      short loc_1800702FD
0x1800702cf  or      edx, 2
0x1800702d2  mov     cs:g_CiPolicyState, edx
0x1800702d8  mov     rax, [rdi+r14*8]
0x1800702dc  test    [rax+2Ch], r9d
0x1800702e0  jnz     short loc_1800702FD
0x1800702e2  btr     edx, 0Bh
0x1800702e6  mov     cs:g_CiPolicyState, edx
0x1800702ec  bt      r8d, 0Dh
0x1800702f1  jb      short loc_1800702FD
0x1800702f3  btr     edx, 0Ch
0x1800702f7  mov     cs:g_CiPolicyState, edx
0x1800702fd  mov     rax, [rdi+r14*8]
0x180070301  test    [rax+2Ch], r9d
0x180070305  jz      short loc_180070310
0x180070307  or      edx, 4
0x18007030a  mov     cs:g_CiPolicyState, edx
0x180070310  test    r8b, r8b
0x180070313  jns     short loc_18007031E
0x180070315  or      edx, 8
0x180070318  mov     cs:g_CiPolicyState, edx
0x18007031e  bt      r8d, 15h
0x180070323  jnb     short loc_18007032E
0x180070325  or      edx, 10h
0x180070328  mov     cs:g_CiPolicyState, edx
0x18007032e  test    r8b, 20h
0x180070332  jz      short loc_18007033D
0x180070334  or      edx, 20h
0x180070337  mov     cs:g_CiPolicyState, edx
0x18007033d  bt      r8d, 14h
0x180070342  jnb     short loc_18007034E
0x180070344  bts     edx, 8
0x180070348  mov     cs:g_CiPolicyState, edx
0x18007034e  bt      r8d, 8
0x180070353  jnb     short loc_18007035F
0x180070355  bts     edx, 9
0x180070359  mov     cs:g_CiPolicyState, edx
0x18007035f  mov     rax, [rdi+r14*8]
0x180070363  mov     ecx, [rax+2A0h]
0x180070369  test    cl, 1
0x18007036c  jz      short loc_180070377
0x18007036e  or      edx, r9d
0x180070371  mov     cs:g_CiPolicyState, edx
0x180070377  mov     rcx, [rdi+r14*8]; int
0x18007037b  xor     edx, edx; String2
0x18007037d  call    SIPolicyHasPerAppPolicy
0x180070382  test    al, al
0x180070384  jz      short loc_180070390
0x180070386  or      cs:g_CiPolicyState, 80040h
0x180070390  mov     rdx, cs:g_SiPolicyHandles
0x180070397  mov     rax, [rdx+r14*8]
0x18007039b  mov     ecx, [rax+2A0h]
0x1800703a1  test    cl, 4
0x1800703a4  jz      short loc_1800703AE
0x1800703a6  bts     cs:g_CiPolicyState, 0Ah
0x1800703ae  mov     rcx, [rdx+r14*8]
0x1800703b2  call    SIPolicyNightsWatchEnabled
0x1800703b7  test    al, al
0x1800703b9  jz      short loc_1800703CF
0x1800703bb  bts     cs:g_CiPolicyState, 0Eh
0x1800703c3  jmp     short loc_1800703EF
0x1800703c5  mov     eax, 43800h
0x1800703ca  jmp     loc_180070228
0x1800703cf  mov     rcx, cs:g_SiPolicyHandles
0x1800703d6  mov     rcx, [rcx+r14*8]
0x1800703da  call    SIPolicyIsBasePolicy
0x1800703df  test    al, al
0x1800703e1  jz      short loc_1800703EF
0x1800703e3  test    ebp, ebp
0x1800703e5  jz      short loc_1800703EF
0x1800703e7  btr     cs:g_CiPolicyState, 12h
0x1800703ef  mov     rdx, cs:g_SiPolicyHandles
0x1800703f6  mov     rax, [rdx+r14*8]
0x1800703fa  mov     ecx, [rax+2Ch]
0x1800703fd  test    cl, 10h
0x180070400  jz      short loc_18007040A
0x180070402  bts     cs:g_CiPolicyState, 11h
0x18007040a  mov     rax, [rdx+r14*8]
0x18007040e  mov     ecx, [rax+2A0h]
0x180070414  test    cl, 8
0x180070417  jz      short loc_180070438
0x180070419  or      cs:g_CiPolicyState, 8040h
0x180070423  mov     rcx, [rdx+r14*8]
0x180070427  call    SIPolicyAppIdTaggingEnforceDLL
0x18007042c  test    al, al
0x18007042e  jz      short loc_180070438
0x180070430  bts     cs:g_CiPolicyState, 15h
0x180070438  mov     rax, cs:g_SiPolicyHandles
0x18007043f  mov     rcx, [rax+r14*8]
0x180070443  mov     eax, [rcx+2Ch]
0x180070446  test    al, 10h
0x180070448  jnz     short loc_180070459
0x18007044a  bt      eax, 1Bh
0x18007044e  jb      short loc_180070459
0x180070450  call    SIPolicyNightsWatchEnabled
0x180070455  test    al, al
0x180070457  jz      short loc_18007045C
0x180070459  mov     sil, 1
0x18007045c  mov     rdi, cs:g_SiPolicyHandles
0x180070463  mov     rax, [rdi+r14*8]
0x180070467  mov     ecx, [rax+2A0h]
0x18007046d  test    cl, 40h
0x180070470  jz      short loc_18007047A
0x180070472  bts     cs:g_CiPolicyState, 14h
0x18007047a  inc     r14d
0x18007047d  cmp     r14d, cs:g_NumberOfSiPolicies
0x180070484  jb      loc_18007026E
0x18007048a  mov     ecx, cs:g_CiDeveloperMode
0x180070490  bt      ecx, 0Dh
0x180070494  jnb     short loc_1800704B9
0x180070496  shr     ecx, 0Ah
0x180070499  and     cl, 1
0x18007049c  call    SIPolicyAreCustomKernelSignersAllowed
0x1800704a1  mov     ecx, cs:g_CiPolicyState
0x1800704a7  and     eax, 1
0x1800704aa  shl     eax, 17h
0x1800704ad  btr     ecx, 17h
0x1800704b1  or      eax, ecx
0x1800704b3  mov     cs:g_CiPolicyState, eax
0x1800704b9  mov     cl, sil
0x1800704bc  call    CipSetSmartlockerRegEnabled
0x1800704c1  test    sil, sil
0x1800704c4  jz      short loc_180070503
0x1800704c6  xor     r9d, r9d
0x1800704c9  mov     [rsp+58h+var_28], 0
0x1800704d1  mov     [rsp+58h+var_30], 0
0x1800704d9  lea     rdx, [rsp+58h+arg_0]
0x1800704de  lea     rcx, WNF_CI_APPLOCKERFLTR_START_REQUESTED
0x1800704e5  mov     byte ptr [rsp+58h+arg_0], 1
0x1800704ea  mov     [rsp+58h+var_38], 0
0x1800704f3  lea     r8d, [r9+1]
0x1800704f7  call    cs:__imp_ZwUpdateWnfStateData
0x1800704fe  nop     dword ptr [rax+rax+00h]
0x180070503  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x180070508  test    eax, eax
0x18007050a  jnz     short loc_18007052C
0x18007050c  xor     ecx, ecx
0x18007050e  xor     eax, eax
0x180070510  lock cmpxchg cs:g_EtwEventHandle, rcx
0x180070519  jz      short loc_18007052C
0x18007051b  mov     ecx, cs:g_CiPolicyState
0x180070521  shr     ecx, 11h
0x180070524  and     ecx, 1
0x180070527  call    CiCatDbMpSmartLockerEnable
0x18007052c  mov     rbx, [rsp+58h+arg_8]
0x180070531  mov     rbp, [rsp+58h+arg_10]
0x180070536  add     rsp, 40h
0x18007053a  pop     r14
0x18007053c  pop     rdi
0x18007053d  pop     rsi
0x18007053e  retn
```
