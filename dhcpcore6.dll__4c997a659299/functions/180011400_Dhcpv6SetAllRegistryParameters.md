# Dhcpv6SetAllRegistryParameters

- ea: `0x180011400`
- end: `0x180011895`
- name: `Dhcpv6SetAllRegistryParameters`
- size: `1173`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011b98`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`

## callees

- `0x18000163c`
- `0x180004b30`
- `0x180007cc8`
- `0x18000bdd4`
- `0x180011400`
- `0x180019ad0`
- `0x18003176c`
- `0x1800337d0`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011752`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800117ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011752`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800117ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800116f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800116f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800114d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800114d6`

## pseudocode

```c
__int64 __fastcall Dhcpv6SetAllRegistryParameters(__int64 a1)
{
  int v1; // esi
  unsigned int v2; // edi
  int v4; // eax
  RTL_SRWLOCK *v5; // r14
  _DWORD *v6; // r9
  unsigned int v7; // r10d
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r9
  HKEY v12; // r8
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // r15d
  __int64 v16; // rsi
  __int64 v17; // rdi
  int v18; // ecx
  LSTATUS v19; // r14d
  __int64 v20; // r14
  unsigned __int64 v21; // rsi
  __int64 v22; // rcx
  unsigned int v23; // edi
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  int v27; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+3Ch] [rbp-C4h] BYREF
  LPCWSTR v29; // [rsp+40h] [rbp-C0h]
  BYTE *v30; // [rsp+48h] [rbp-B8h]
  DWORD v31[2]; // [rsp+50h] [rbp-B0h]
  const wchar_t *v32; // [rsp+58h] [rbp-A8h]
  int *v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  const wchar_t *v35; // [rsp+70h] [rbp-90h]
  int *v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+80h] [rbp-80h]
  const wchar_t *v38; // [rsp+88h] [rbp-78h]
  int *v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+98h] [rbp-68h]
  const wchar_t *v41; // [rsp+A0h] [rbp-60h]
  int *v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+B0h] [rbp-50h]
  const wchar_t *v44; // [rsp+B8h] [rbp-48h]
  _OWORD *v45; // [rsp+C0h] [rbp-40h]
  int v46; // [rsp+C8h] [rbp-38h]
  const wchar_t *v47; // [rsp+D0h] [rbp-30h]
  __int128 *v48; // [rsp+D8h] [rbp-28h]
  int v49; // [rsp+E0h] [rbp-20h]
  const wchar_t *v50; // [rsp+E8h] [rbp-18h]
  _DWORD *v51; // [rsp+F0h] [rbp-10h]
  int v52; // [rsp+F8h] [rbp-8h]
  const wchar_t *v53; // [rsp+100h] [rbp+0h]
  _DWORD *v54; // [rsp+108h] [rbp+8h]
  int v55; // [rsp+110h] [rbp+10h]
  LPCWSTR lpValueName; // [rsp+120h] [rbp+20h]
  _DWORD v57[2]; // [rsp+128h] [rbp+28h] BYREF
  const WCHAR *v58; // [rsp+130h] [rbp+30h]
  int v59; // [rsp+138h] [rbp+38h]
  const wchar_t *v60; // [rsp+140h] [rbp+40h]
  int v61; // [rsp+148h] [rbp+48h]
  const wchar_t *v62; // [rsp+150h] [rbp+50h]
  int v63; // [rsp+158h] [rbp+58h]
  const WCHAR *v64; // [rsp+160h] [rbp+60h]
  int v65; // [rsp+168h] [rbp+68h]
  _DWORD v66[2]; // [rsp+170h] [rbp+70h] BYREF
  _DWORD v67[4]; // [rsp+178h] [rbp+78h] BYREF
  __int128 v68; // [rsp+188h] [rbp+88h] BYREF
  _OWORD v69[2]; // [rsp+198h] [rbp+98h] BYREF

  v1 = 0;
  v2 = 0;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  v26 = 0;
  lpValueName = L"Dhcpv6State";
  if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    v4 = *(_DWORD *)(a1 + 8880);
  else
    v4 = (*(_DWORD *)(a1 + 8860) >> 5) & 1;
  v5 = (RTL_SRWLOCK *)(a1 + 608);
  v57[0] = (v4 != 0) + 1;
  v58 = L"Dhcpv6MaxLeaseExpireTime";
  v59 = *(_DWORD *)(a1 + 512);
  v60 = L"Dhcpv6ServerPreference";
  v61 = *(char *)(a1 + 554);
  v62 = L"Dhcpv6IsUnicastEnabled";
  v63 = *(_DWORD *)(a1 + 560);
  v64 = L"Dhcpv6LeaseObtainedTime";
  v65 = *(_DWORD *)(a1 + 536);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 608));
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 33, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56));
  v6 = *(_DWORD **)(a1 + 104);
  if ( v6 != (_DWORD *)(a1 + 104) )
  {
    v25 = v6[8];
    v27 = v6[4];
    v28 = v6[6];
    v2 = v6[9];
    if ( v2 )
    {
      v7 = 0;
      do
      {
        if ( v7 >= 2 )
          break;
        v8 = 14LL * v7;
        v67[2 * v7] = v6[v8 + 18];
        v67[2 * v7 + 1] = v6[v8 + 19];
        v9 = v7++;
        v69[v9] = *(_OWORD *)&v6[v8 + 14];
        v2 = v6[9];
      }
      while ( v7 < v2 );
    }
  }
  v10 = *(_QWORD *)(a1 + 120);
  if ( v10 != a1 + 120 )
  {
    v1 = 1;
    v26 = *(_DWORD *)(v10 + 88);
    v66[0] = *(_DWORD *)(v10 + 32);
    v66[1] = *(_DWORD *)(v10 + 36);
    v68 = *(_OWORD *)(v10 + 16);
  }
  v11 = *(_QWORD *)(a1 + 656);
  v29 = L"Dhcpv6ServerDUID";
  v12 = *(HKEY *)(a1 + 648);
  v13 = *(_QWORD *)(a1 + 56);
  v30 = *(BYTE **)(a1 + 480);
  v31[0] = *(_DWORD *)(a1 + 488);
  v32 = L"Dhcpv6IanaIaids";
  v33 = &v25;
  v35 = L"Dhcpv6IataIaids";
  v36 = &v26;
  v37 = 4 * v1;
  v38 = L"Dhcpv6T1";
  v39 = &v27;
  v34 = v2 != 0 ? 4 : 0;
  v41 = L"Dhcpv6T2";
  v42 = &v28;
  v44 = L"Dhcpv6IanaAddr";
  v45 = v69;
  v46 = 16 * v2;
  v47 = L"Dhcpv6IataAddr";
  v48 = &v68;
  v49 = 16 * v1;
  v50 = L"Dhcpv6IanaLeases";
  v51 = v67;
  v52 = 8 * v2;
  v53 = L"Dhcpv6IataLeases";
  v54 = v66;
  v55 = 8 * v1;
  v14 = *(_DWORD *)(a1 + 664);
  v40 = v34;
  v43 = v34;
  Dhcpv6RegSaveOptions((_QWORD **)(a1 + 632), v13, v12, v11, v14);
  ReleaseSRWLockShared(v5);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 34, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56));
  Dhcpv6SaveNetworkHint(a1);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  do
  {
    v19 = RegSetValueExW(*(HKEY *)(a1 + 648), *(LPCWSTR *)&v57[v17 - 2], 0, 4u, (const BYTE *)&v57[v17], 4u);
    if ( v19 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SDS(
          v18,
          35,
          (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
          *(_QWORD *)&v57[v17 - 2],
          v19,
          *(_QWORD *)(a1 + 56));
      v15 = v19;
    }
    ++v16;
    v17 += 4;
  }
  while ( v16 != 5 );
  v20 = 0;
  v21 = 0;
  do
  {
    v23 = RegSetValueExW(*(HKEY *)(a1 + 648), (&v29)[v21 / 8], 0, 3u, *(const BYTE **)&v31[v21 / 4 - 2], v31[v21 / 4]);
    if ( v23 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SDS(
          v22,
          36,
          (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
          (unsigned int)(&v29)[v21 / 8],
          v23,
          *(_QWORD *)(a1 + 56));
      v15 = v23;
    }
    ++v20;
    v21 += 24LL;
  }
  while ( v20 != 9 );
  if ( v23 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_SD(1025, 37, (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56), v23);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0zq_EtwEventWriteTransfer(v22, FailedUpdatingRegistry, *(_QWORD *)(a1 + 56), v23);
    TraceLogErrorv6(a1, v23, 64);
  }
  return v15;
}

```

## disassembly

```asm
0x180011400  mov     [rsp-8+arg_8], rbx
0x180011405  mov     [rsp-8+arg_10], rsi
0x18001140a  push    rbp
0x18001140b  push    rdi
0x18001140c  push    r13
0x18001140e  push    r14
0x180011410  push    r15
0x180011412  lea     rbp, [rsp-0C0h]
0x18001141a  sub     rsp, 1C0h
0x180011421  mov     rax, cs:__security_cookie
0x180011428  xor     rax, rsp
0x18001142b  mov     [rbp+0E0h+var_28], rax
0x180011432  xor     esi, esi
0x180011434  lea     rax, aDhcpv6state; "Dhcpv6State"
0x18001143b  xor     edi, edi
0x18001143d  mov     [rsp+1E0h+var_1A8], esi
0x180011441  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, esi
0x180011447  mov     rbx, rcx
0x18001144a  mov     [rsp+1E0h+var_1A4], esi
0x18001144e  mov     [rsp+1E0h+var_1B0], esi
0x180011452  mov     [rsp+1E0h+var_1AC], esi
0x180011456  mov     [rbp+0E0h+lpValueName], rax
0x18001145a  jz      short loc_180011464
0x18001145c  mov     eax, [rcx+22B0h]
0x180011462  jmp     short loc_180011470
0x180011464  mov     eax, [rcx+229Ch]
0x18001146a  shr     eax, 5
0x18001146d  and     eax, 1
0x180011470  neg     eax
0x180011472  lea     r14, [rcx+260h]
0x180011479  sbb     eax, eax
0x18001147b  neg     eax
0x18001147d  inc     eax
0x18001147f  mov     [rbp+0E0h+var_B8], eax
0x180011482  lea     rax, aDhcpv6maxlease; "Dhcpv6MaxLeaseExpireTime"
0x180011489  mov     [rbp+0E0h+var_B0], rax
0x18001148d  mov     eax, [rcx+200h]
0x180011493  mov     [rbp+0E0h+var_A8], eax
0x180011496  lea     rax, aDhcpv6serverpr; "Dhcpv6ServerPreference"
0x18001149d  mov     [rbp+0E0h+var_A0], rax
0x1800114a1  movsx   eax, byte ptr [rcx+22Ah]
0x1800114a8  mov     [rbp+0E0h+var_98], eax
0x1800114ab  lea     rax, aDhcpv6isunicas; "Dhcpv6IsUnicastEnabled"
0x1800114b2  mov     [rbp+0E0h+var_90], rax
0x1800114b6  mov     eax, [rcx+230h]
0x1800114bc  mov     [rbp+0E0h+var_88], eax
0x1800114bf  lea     rax, aDhcpv6leaseobt; "Dhcpv6LeaseObtainedTime"
0x1800114c6  mov     [rbp+0E0h+var_80], rax
0x1800114ca  mov     eax, [rcx+218h]
0x1800114d0  mov     rcx, r14; SRWLock
0x1800114d3  mov     [rbp+0E0h+var_78], eax
0x1800114d6  call    cs:__imp_AcquireSRWLockShared
0x1800114dd  nop     dword ptr [rax+rax+00h]
0x1800114e2  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800114e9  lea     r13, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800114f0  mov     r15d, 404h
0x1800114f6  jz      short loc_18001150C
0x1800114f8  mov     r9, [rbx+38h]
0x1800114fc  mov     edx, 21h ; '!'
0x180011501  mov     ecx, r15d
0x180011504  mov     r8, r13
0x180011507  call    WPP_SF_S
0x18001150c  lea     rax, [rbx+68h]
0x180011510  mov     r9, [rax]
0x180011513  cmp     r9, rax
0x180011516  jz      short loc_180011586
0x180011518  mov     eax, [r9+20h]
0x18001151c  mov     [rsp+1E0h+var_1B0], eax
0x180011520  mov     eax, [r9+10h]
0x180011524  mov     [rsp+1E0h+var_1A8], eax
0x180011528  mov     eax, [r9+18h]
0x18001152c  mov     [rsp+1E0h+var_1A4], eax
0x180011530  mov     edi, [r9+24h]
0x180011534  test    edi, edi
0x180011536  jz      short loc_180011586
0x180011538  xor     r10d, r10d
0x18001153b  cmp     r10d, 2
0x18001153f  jnb     short loc_180011586
0x180011541  mov     eax, r10d
0x180011544  lea     edx, ds:0[r10*8]
0x18001154c  imul    r8, rax, 38h ; '8'
0x180011550  lea     ecx, [rdx+4]
0x180011553  mov     eax, [r8+r9+48h]
0x180011558  mov     [rbp+rdx+0E0h+var_68], eax
0x18001155c  mov     eax, [r8+r9+4Ch]
0x180011561  mov     [rbp+rcx+0E0h+var_68], eax
0x180011565  mov     eax, r10d
0x180011568  movups  xmm0, xmmword ptr [r8+r9+38h]
0x18001156e  shl     eax, 4
0x180011571  inc     r10d
0x180011574  movdqu  [rbp+rax+0E0h+var_48], xmm0
0x18001157d  mov     edi, [r9+24h]
0x180011581  cmp     r10d, edi
0x180011584  jb      short loc_18001153B
0x180011586  lea     rax, [rbx+78h]
0x18001158a  mov     rcx, [rax]
0x18001158d  cmp     rcx, rax
0x180011590  jz      short loc_1800115B6
0x180011592  mov     eax, [rcx+58h]
0x180011595  mov     esi, 1
0x18001159a  mov     [rsp+1E0h+var_1AC], eax
0x18001159e  mov     eax, [rcx+20h]
0x1800115a1  mov     [rbp+0E0h+var_70], eax
0x1800115a4  mov     eax, [rcx+24h]
0x1800115a7  mov     [rbp+0E0h+var_6C], eax
0x1800115aa  movups  xmm0, xmmword ptr [rcx+10h]
0x1800115ae  movdqu  [rbp+0E0h+var_58], xmm0
0x1800115b6  mov     r9, [rbx+290h]
0x1800115bd  lea     rax, aDhcpv6serverdu; "Dhcpv6ServerDUID"
0x1800115c4  mov     [rsp+1E0h+var_1A0], rax
0x1800115c9  mov     rax, [rbx+1E0h]
0x1800115d0  mov     r8, [rbx+288h]
0x1800115d7  mov     rdx, [rbx+38h]
0x1800115db  mov     [rsp+1E0h+var_198], rax
0x1800115e0  mov     eax, [rbx+1E8h]
0x1800115e6  mov     [rsp+1E0h+var_190], eax
0x1800115ea  lea     rax, aDhcpv6ianaiaid; "Dhcpv6IanaIaids"
0x1800115f1  mov     [rsp+1E0h+var_188], rax
0x1800115f6  lea     rax, [rsp+1E0h+var_1B0]
0x1800115fb  mov     [rsp+1E0h+var_180], rax
0x180011600  mov     eax, edi
0x180011602  neg     eax
0x180011604  lea     rax, aDhcpv6iataiaid; "Dhcpv6IataIaids"
0x18001160b  mov     [rsp+1E0h+var_170], rax
0x180011610  sbb     ecx, ecx
0x180011612  and     ecx, 4
0x180011615  lea     rax, [rsp+1E0h+var_1AC]
0x18001161a  mov     [rsp+1E0h+var_168], rax
0x18001161f  lea     eax, ds:0[rsi*4]
0x180011626  mov     [rbp+0E0h+var_160], eax
0x180011629  lea     rax, aDhcpv6t1; "Dhcpv6T1"
0x180011630  mov     [rbp+0E0h+var_158], rax
0x180011634  lea     rax, [rsp+1E0h+var_1A8]
0x180011639  mov     [rbp+0E0h+var_150], rax
0x18001163d  mov     eax, edi
0x18001163f  neg     eax
0x180011641  mov     [rsp+1E0h+var_178], ecx
0x180011645  lea     rax, aDhcpv6t2; "Dhcpv6T2"
0x18001164c  mov     [rbp+0E0h+var_140], rax
0x180011650  sbb     ecx, ecx
0x180011652  and     ecx, 4
0x180011655  lea     rax, [rsp+1E0h+var_1A4]
0x18001165a  mov     [rbp+0E0h+var_138], rax
0x18001165e  lea     rax, aDhcpv6ianaaddr; "Dhcpv6IanaAddr"
0x180011665  mov     [rbp+0E0h+var_128], rax
0x180011669  lea     rax, [rbp+0E0h+var_48]
0x180011670  mov     [rbp+0E0h+var_120], rax
0x180011674  mov     eax, edi
0x180011676  shl     eax, 4
0x180011679  mov     [rbp+0E0h+var_118], eax
0x18001167c  lea     rax, aDhcpv6iataaddr; "Dhcpv6IataAddr"
0x180011683  mov     [rbp+0E0h+var_110], rax
0x180011687  lea     rax, [rbp+0E0h+var_58]
0x18001168e  mov     [rbp+0E0h+var_108], rax
0x180011692  mov     eax, esi
0x180011694  shl     eax, 4
0x180011697  mov     [rbp+0E0h+var_100], eax
0x18001169a  lea     rax, aDhcpv6ianaleas; "Dhcpv6IanaLeases"
0x1800116a1  mov     [rbp+0E0h+var_F8], rax
0x1800116a5  lea     rax, [rbp+0E0h+var_68]
0x1800116a9  mov     [rbp+0E0h+var_F0], rax
0x1800116ad  lea     eax, ds:0[rdi*8]
0x1800116b4  mov     [rbp+0E0h+var_E8], eax
0x1800116b7  lea     rax, aDhcpv6iataleas; "Dhcpv6IataLeases"
0x1800116be  mov     [rbp+0E0h+var_E0], rax
0x1800116c2  lea     rax, [rbp+0E0h+var_70]
0x1800116c6  mov     [rbp+0E0h+var_D8], rax
0x1800116ca  lea     eax, ds:0[rsi*8]
0x1800116d1  mov     [rbp+0E0h+var_D0], eax
0x1800116d4  mov     eax, [rbx+298h]
0x1800116da  mov     [rbp+0E0h+var_148], ecx
0x1800116dd  mov     [rbp+0E0h+var_130], ecx
0x1800116e0  lea     rcx, [rbx+278h]
0x1800116e7  mov     dword ptr [rsp+1E0h+lpData], eax
0x1800116eb  call    Dhcpv6RegSaveOptions
0x1800116f0  mov     rcx, r14; SRWLock
0x1800116f3  call    cs:__imp_ReleaseSRWLockShared
0x1800116fa  nop     dword ptr [rax+rax+00h]
0x1800116ff  test    byte ptr cs:xmmword_1800423E0, 10h
0x180011706  jz      short loc_18001171C
0x180011708  mov     r9, [rbx+38h]
0x18001170c  mov     edx, 22h ; '"'
0x180011711  mov     ecx, r15d
0x180011714  mov     r8, r13
0x180011717  call    WPP_SF_S
0x18001171c  mov     rcx, rbx
0x18001171f  call    Dhcpv6SaveNetworkHint
0x180011724  xor     r15d, r15d
0x180011727  xor     esi, esi
0x180011729  xor     edi, edi
0x18001172b  mov     rdx, [rbp+rdi+0E0h+lpValueName]; lpValueName
0x180011730  lea     rax, [rbp+0E0h+var_B8]
0x180011734  mov     ecx, 4
0x180011739  add     rax, rdi
0x18001173c  mov     [rsp+1E0h+cbData], ecx; cbData
0x180011740  mov     r9d, ecx; dwType
0x180011743  mov     rcx, [rbx+288h]; hKey
0x18001174a  xor     r8d, r8d; Reserved
0x18001174d  mov     [rsp+1E0h+lpData], rax; lpData
0x180011752  call    cs:__imp_RegSetValueExW
0x180011759  nop     dword ptr [rax+rax+00h]
0x18001175e  mov     r14d, eax
0x180011761  test    eax, eax
0x180011763  jz      short loc_180011791
0x180011765  test    byte ptr cs:xmmword_1800423E0, 2
0x18001176c  jz      short loc_18001178E
0x18001176e  mov     rax, [rbx+38h]
0x180011772  mov     edx, 23h ; '#'
0x180011777  mov     r9, [rbp+rdi+0E0h+lpValueName]
0x18001177c  mov     r8, r13
0x18001177f  mov     qword ptr [rsp+1E0h+cbData], rax
0x180011784  mov     dword ptr [rsp+1E0h+lpData], r14d
0x180011789  call    WPP_SF_SDS
0x18001178e  mov     r15d, r14d
0x180011791  inc     rsi
0x180011794  add     rdi, 10h
0x180011798  cmp     rsi, 5
0x18001179c  jnz     short loc_18001172B
0x18001179e  xor     r14d, r14d
0x1800117a1  xor     esi, esi
0x1800117a3  mov     eax, [rsp+rsi+1E0h+var_190]
0x1800117a7  mov     r9d, 3; dwType
0x1800117ad  mov     rdx, [rsp+rsi+1E0h+var_1A0]; lpValueName
0x1800117b2  xor     r8d, r8d; Reserved
0x1800117b5  mov     rcx, [rbx+288h]; hKey
0x1800117bc  mov     [rsp+1E0h+cbData], eax; cbData
0x1800117c0  mov     rax, [rsp+rsi+1E0h+var_198]
0x1800117c5  mov     [rsp+1E0h+lpData], rax; lpData
0x1800117ca  call    cs:__imp_RegSetValueExW
0x1800117d1  nop     dword ptr [rax+rax+00h]
0x1800117d6  mov     edi, eax
0x1800117d8  test    eax, eax
0x1800117da  jz      short loc_180011807
0x1800117dc  test    byte ptr cs:xmmword_1800423E0, 2
0x1800117e3  jz      short loc_180011804
0x1800117e5  mov     rax, [rbx+38h]
0x1800117e9  mov     edx, 24h ; '$'
0x1800117ee  mov     r9, [rsp+rsi+1E0h+var_1A0]
0x1800117f3  mov     r8, r13
0x1800117f6  mov     qword ptr [rsp+1E0h+cbData], rax
0x1800117fb  mov     dword ptr [rsp+1E0h+lpData], edi
0x1800117ff  call    WPP_SF_SDS
0x180011804  mov     r15d, edi
0x180011807  inc     r14
0x18001180a  add     rsi, 18h
0x18001180e  cmp     r14, 9
0x180011812  jnz     short loc_1800117A3
0x180011814  test    edi, edi
0x180011816  jz      short loc_180011866
0x180011818  test    byte ptr cs:xmmword_1800423E0, 2
0x18001181f  jz      short loc_18001183A
0x180011821  mov     r9, [rbx+38h]
0x180011825  lea     edx, [r14+1Ch]
0x180011829  mov     ecx, 401h
0x18001182e  mov     dword ptr [rsp+1E0h+lpData], edi
0x180011832  mov     r8, r13
0x180011835  call    WPP_SF_SD
0x18001183a  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180011841  jz      short loc_180011856
0x180011843  mov     r8, [rbx+38h]
0x180011847  lea     rdx, FailedUpdatingRegistry
0x18001184e  mov     r9d, edi
0x180011851  call    McTemplateU0zq_EtwEventWriteTransfer
0x180011856  mov     r8d, 40h ; '@'
0x18001185c  mov     edx, edi
0x18001185e  mov     rcx, rbx
0x180011861  call    TraceLogErrorv6
0x180011866  mov     eax, r15d
0x180011869  mov     rcx, [rbp+0E0h+var_28]
0x180011870  xor     rcx, rsp; StackCookie
0x180011873  call    __security_check_cookie
0x180011878  lea     r11, [rsp+1E0h+var_20]
0x180011880  mov     rbx, [r11+38h]
0x180011884  mov     rsi, [r11+40h]
0x180011888  mov     rsp, r11
0x18001188b  pop     r15
0x18001188d  pop     r14
0x18001188f  pop     r13
0x180011891  pop     rdi
0x180011892  pop     rbp
0x180011893  retn
```
