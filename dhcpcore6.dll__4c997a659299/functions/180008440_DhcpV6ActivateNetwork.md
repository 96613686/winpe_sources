# DhcpV6ActivateNetwork

- ea: `0x180008440`
- end: `0x180008905`
- name: `DhcpV6ActivateNetwork`
- size: `1221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008a70`
- `0x180008f80`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`
- `0x1800216a4`
- `0x1800218e0`
- `0x180021b58`
- `0x1800225c8`
- `0x180022b80`
- `0x180023c2c`
- `0x180025094`

## callees

- `0x180001ca4`
- `0x1800075b0`
- `0x180008440`
- `0x180013028`
- `0x180016d50`
- `0x1800173fc`
- `0x1800190c0`
- `0x180019194`
- `0x180019ad0`
- `0x18001bbb0`
- `0x18001e5c0`
- `0x180020824`
- `0x18002e91c`
- `0x18002ec28`
- `0x18002f42c`
- `0x180031f44`
- `0x180031fa4`
- `0x1800320f0`
- `0x1800338c0`
- `0x180033900`
- `0x180033de4`
- `0x1800343ec`
- `0x18003471c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008597`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008597`

## pseudocode

```c
__int64 __fastcall DhcpV6ActivateNetwork(__int64 a1, __int64 *a2, __int64 a3, unsigned int a4)
{
  int v4; // r12d
  __int64 v5; // r14
  __int64 *v8; // rsi
  _QWORD *v9; // r15
  _DWORD *v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  DWORD v13; // eax
  DWORD v14; // ebx
  unsigned int IsMachineInCs; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // r15d
  int v20; // esi
  unsigned int v21; // eax
  int IsMachineInDs; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  bool v26; // zf
  int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // r9
  __int64 v31; // [rsp+20h] [rbp-79h]
  int v32; // [rsp+60h] [rbp-39h] BYREF
  int v33; // [rsp+64h] [rbp-35h] BYREF
  int v34; // [rsp+68h] [rbp-31h] BYREF
  __int64 v35; // [rsp+70h] [rbp-29h] BYREF
  int v36; // [rsp+78h] [rbp-21h] BYREF
  int v37; // [rsp+7Ch] [rbp-1Dh] BYREF
  int v38; // [rsp+80h] [rbp-19h]
  __int64 *v39; // [rsp+88h] [rbp-11h]
  _QWORD *v40; // [rsp+90h] [rbp-9h]
  __int128 v41; // [rsp+98h] [rbp-1h] BYREF

  v4 = 0;
  v39 = a2;
  v35 = 0;
  v5 = 0;
  v33 = 0;
  v37 = 0;
  v32 = 0;
  v36 = 0;
  v8 = a2;
  v41 = 0;
  v34 = 0;
  v9 = (_QWORD *)a1;
  v40 = (_QWORD *)a1;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    v31 = *(_QWORD *)(a3 + 24);
    WPP_SF_dJlld((unsigned int)**(_DWORD **)&pDhcpv6GlobalIsShuttingDown, a2);
  }
  v10 = *(_DWORD **)&pDhcpv6GlobalIsShuttingDown;
  *v9 = 0;
  *v8 = 0;
  if ( *v10 && a4 != 16 )
  {
    v11 = 65;
    if ( (xmmword_1800423E0 & 2) == 0 )
      goto LABEL_62;
    v12 = 11;
    goto LABEL_7;
  }
  if ( !(unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( (unsigned int)Dhcpv6IsMachineInCs(a1) && (unsigned int)DhcpStandbyGetNetworkBlocked(a3 + 8936) )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_(1025, 13, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      v11 = 21;
      goto LABEL_62;
    }
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 14, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    v13 = WaitForSingleObject(Dhcpv6GlobalFirewallReadyEvent, 0x1F4u);
    v14 = v13;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 15, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v13);
    if ( v14 && (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(a1, (__int64)FirewallExemptionGrantDelayed, v14);
    if ( !Dhcpv6GlobalDsFeatureEnabled && (unsigned int)((__int64 (*)(void))Dhcpv6IsMachineInDs)() )
    {
      v11 = 1236;
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_(1025, 16, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      goto LABEL_62;
    }
    v11 = 0;
    if ( Dhcpv6GlobalAllowActivationInMos || !(unsigned int)Dhcpv6IsMachineInModernStandby() )
      goto LABEL_44;
    if ( *(_DWORD *)(a3 + 9152) )
    {
      v11 = 1236;
      if ( (xmmword_1800423E0 & 2) != 0 )
      {
        IsMachineInCs = Dhcpv6IsMachineInCs(a1);
        Dhcpv6IsMachineInDs(IsMachineInCs);
        WPP_SF__guid_Dll(v17, v16, v18, a3 + 32);
      }
      goto LABEL_62;
    }
    v19 = 0;
    v38 = IsDHCPV6AddrPlumbed(a3, &v41, &v32, &v36);
    if ( v38 && !v32 )
    {
      v4 = Dhcpv6CheckDhcpv4Address(a3, &v37, &v33);
      if ( !v4 || v33 )
      {
        v20 = 0;
        v19 = 1;
        goto LABEL_38;
      }
      v19 = 1;
    }
    v11 = 1236;
    v20 = 1;
LABEL_38:
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      v21 = Dhcpv6IsMachineInCs(a1);
      IsMachineInDs = Dhcpv6IsMachineInDs(v21);
      LODWORD(v31) = v20;
      WPP_SF__guid_llllllll(v24, v23, v25, a3 + 32, v31, v19, v4, v33, v38, v32, IsMachineInDs, v24);
    }
    if ( v20 )
    {
      *(_DWORD *)(a3 + 9152) = 1;
      goto LABEL_62;
    }
    v8 = v39;
    v9 = v40;
LABEL_44:
    v26 = g_PdcActivationDisabled == 0;
    *(_DWORD *)(a3 + 9152) = 0;
    if ( !v26 )
      goto LABEL_56;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_Jq(1028, 19, a3, *(_QWORD *)(a3 + 24), a3);
    v5 = PdcActivateNetwork(a1, a4);
    if ( v5 )
    {
LABEL_56:
      if ( !Dhcpv6GlobalDsFeatureEnabled || **(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
        goto LABEL_57;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 21, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      v27 = Dhcpv6IsMachineInCs(a1);
      v28 = DhcpWcmAcquireRef((int)a3 + 32, (int)a3 + 8936, v27, a4, (__int64)&v34, (__int64)&v35);
      v11 = v28;
      if ( v34 )
        DhcpV6TraceWcmError(a3, v28);
      if ( !v11 )
      {
LABEL_57:
        if ( v5 )
        {
          v29 = (unsigned int)_InterlockedIncrement(&Dhcpv6GlobalPdcCount);
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_d(1028, 22, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v29);
          *v8 = v5;
          v5 = 0;
        }
        *v9 = v35;
        v35 = 0;
      }
    }
    else
    {
      v11 = 1168;
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_Jq(1025, 20, a3, *(_QWORD *)(a3 + 24), a3);
    }
    goto LABEL_62;
  }
  v11 = 50;
  if ( (xmmword_1800423E0 & 2) != 0 )
  {
    v12 = 12;
LABEL_7:
    WPP_SF_D(1025, v12, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v11);
  }
LABEL_62:
  if ( v35 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_(1025, 23, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    DhcpWcmReleaseRef(&v35);
  }
  if ( v5 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_(1025, 24, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    PdcDeactivateNetwork(v5, a2, a4);
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    LODWORD(v31) = a4;
    WPP_SF_DdJ(a1, a2, a3, v11, v31, *(_QWORD *)(a3 + 24));
  }
  return v11;
}

```

## disassembly

```asm
0x180008440  push    rbp
0x180008442  push    rbx
0x180008443  push    rsi
0x180008444  push    rdi
0x180008445  push    r12
0x180008447  push    r13
0x180008449  push    r14
0x18000844b  push    r15
0x18000844d  lea     rbp, [rsp-1Fh]
0x180008452  sub     rsp, 0B8h
0x180008459  mov     rax, cs:__security_cookie
0x180008460  xor     rax, rsp
0x180008463  mov     [rbp+57h+var_48], rax
0x180008467  xor     r12d, r12d
0x18000846a  mov     [rbp+57h+var_68], rdx
0x18000846e  xorps   xmm0, xmm0
0x180008471  mov     [rbp+57h+var_80], r12
0x180008475  mov     r14d, r12d
0x180008478  mov     [rbp+57h+var_8C], r12d
0x18000847c  mov     [rbp+57h+var_74], r12d
0x180008480  mov     r13d, r9d
0x180008483  mov     [rbp+57h+var_90], r12d
0x180008487  mov     rdi, r8
0x18000848a  mov     [rbp+57h+var_78], r12d
0x18000848e  mov     rsi, rdx
0x180008491  movups  [rbp+57h+var_58], xmm0
0x180008495  mov     [rbp+57h+var_88], r12d
0x180008499  mov     r15, rcx
0x18000849c  mov     [rbp+57h+var_60], rcx
0x1800084a0  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800084a7  jz      short loc_1800084C4
0x1800084a9  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x1800084b0  mov     ecx, [rax]
0x1800084b2  mov     rax, [r8+18h]
0x1800084b6  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x1800084ba  mov     [rsp+0F0h+var_D0], rax
0x1800084bf  call    WPP_SF_dJlld
0x1800084c4  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x1800084cb  mov     [r15], r12
0x1800084ce  mov     [rsi], r12
0x1800084d1  cmp     [rax], r12d
0x1800084d4  jz      short loc_18000850A
0x1800084d6  cmp     r13d, 10h
0x1800084da  jz      short loc_18000850A
0x1800084dc  mov     ebx, 41h ; 'A'
0x1800084e1  test    byte ptr cs:xmmword_1800423E0, 2
0x1800084e8  jz      loc_180008866
0x1800084ee  lea     edx, [rbx-36h]
0x1800084f1  mov     ecx, 401h
0x1800084f6  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800084fd  mov     r9d, ebx
0x180008500  call    WPP_SF_D
0x180008505  jmp     loc_180008866
0x18000850a  call    DhcpIsFSEGuestSystem
0x18000850f  test    eax, eax
0x180008511  jz      short loc_18000852A
0x180008513  mov     ebx, 32h ; '2'
0x180008518  test    byte ptr cs:xmmword_1800423E0, 2
0x18000851f  jz      loc_180008866
0x180008525  lea     edx, [rbx-26h]
0x180008528  jmp     short loc_1800084F1
0x18000852a  call    Dhcpv6IsMachineInCs
0x18000852f  test    eax, eax
0x180008531  jz      short loc_18000856C
0x180008533  lea     rcx, [rdi+22E8h]
0x18000853a  call    DhcpStandbyGetNetworkBlocked
0x18000853f  test    eax, eax
0x180008541  jz      short loc_18000856C
0x180008543  test    byte ptr cs:xmmword_1800423E0, 2
0x18000854a  jz      short loc_180008562
0x18000854c  mov     edx, 0Dh
0x180008551  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180008558  mov     ecx, 401h
0x18000855d  call    WPP_SF_
0x180008562  mov     ebx, 15h
0x180008567  jmp     loc_180008866
0x18000856c  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008573  jz      short loc_18000858B
0x180008575  mov     edx, 0Eh
0x18000857a  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180008581  mov     ecx, 404h
0x180008586  call    WPP_SF_
0x18000858b  mov     rcx, cs:Dhcpv6GlobalFirewallReadyEvent; hHandle
0x180008592  mov     edx, 1F4h; dwMilliseconds
0x180008597  call    cs:__imp_WaitForSingleObject
0x18000859e  nop     dword ptr [rax+rax+00h]
0x1800085a3  mov     ebx, eax
0x1800085a5  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800085ac  jz      short loc_1800085C7
0x1800085ae  mov     edx, 0Fh
0x1800085b3  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800085ba  mov     ecx, 404h
0x1800085bf  mov     r9d, eax
0x1800085c2  call    WPP_SF_D
0x1800085c7  test    ebx, ebx
0x1800085c9  jz      short loc_1800085E3
0x1800085cb  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x1800085d2  jz      short loc_1800085E3
0x1800085d4  mov     r8d, ebx
0x1800085d7  lea     rdx, FirewallExemptionGrantDelayed
0x1800085de  call    McTemplateU0q_EtwEventWriteTransfer
0x1800085e3  cmp     cs:Dhcpv6GlobalDsFeatureEnabled, r12d
0x1800085ea  jnz     short loc_180008622
0x1800085ec  call    Dhcpv6IsMachineInDs
0x1800085f1  test    eax, eax
0x1800085f3  jz      short loc_180008622
0x1800085f5  mov     ebx, 4D4h
0x1800085fa  test    byte ptr cs:xmmword_1800423E0, 2
0x180008601  jz      loc_180008866
0x180008607  mov     edx, 10h
0x18000860c  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180008613  mov     ecx, 401h
0x180008618  call    WPP_SF_
0x18000861d  jmp     loc_180008866
0x180008622  cmp     cs:Dhcpv6GlobalAllowActivationInMos, r12d
0x180008629  mov     ebx, r12d
0x18000862c  jnz     loc_18000873A
0x180008632  call    Dhcpv6IsMachineInModernStandby
0x180008637  test    eax, eax
0x180008639  jz      loc_18000873A
0x18000863f  cmp     [rdi+23C0h], r12d
0x180008646  jz      short loc_18000867C
0x180008648  mov     ebx, 4D4h
0x18000864d  test    byte ptr cs:xmmword_1800423E0, 2
0x180008654  jz      loc_180008866
0x18000865a  call    Dhcpv6IsMachineInCs
0x18000865f  mov     ecx, eax
0x180008661  call    Dhcpv6IsMachineInDs
0x180008666  mov     [rsp+0F0h+var_C0], ecx
0x18000866a  lea     r9, [rdi+20h]
0x18000866e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180008672  call    WPP_SF__guid_Dll
0x180008677  jmp     loc_180008866
0x18000867c  lea     r9, [rbp+57h+var_78]
0x180008680  mov     rcx, rdi
0x180008683  lea     r8, [rbp+57h+var_90]
0x180008687  xor     r15d, r15d
0x18000868a  lea     rdx, [rbp+57h+var_58]
0x18000868e  call    IsDHCPV6AddrPlumbed
0x180008693  mov     [rbp+57h+var_70], eax
0x180008696  test    eax, eax
0x180008698  jz      short loc_1800086C1
0x18000869a  cmp     [rbp+57h+var_90], ebx
0x18000869d  jnz     short loc_1800086C1
0x18000869f  lea     r8, [rbp+57h+var_8C]
0x1800086a3  mov     rcx, rdi
0x1800086a6  lea     rdx, [rbp+57h+var_74]
0x1800086aa  call    Dhcpv6CheckDhcpv4Address
0x1800086af  mov     r12d, eax
0x1800086b2  test    eax, eax
0x1800086b4  jz      short loc_18000872A
0x1800086b6  cmp     [rbp+57h+var_8C], ebx
0x1800086b9  jnz     short loc_18000872A
0x1800086bb  mov     r15d, 1
0x1800086c1  mov     ebx, 4D4h
0x1800086c6  mov     esi, 1
0x1800086cb  test    byte ptr cs:xmmword_1800423E0, 2
0x1800086d2  jz      short loc_180008714
0x1800086d4  call    Dhcpv6IsMachineInCs
0x1800086d9  mov     ecx, eax
0x1800086db  call    Dhcpv6IsMachineInDs
0x1800086e0  mov     [rsp+0F0h+var_98], ecx
0x1800086e4  lea     r9, [rdi+20h]
0x1800086e8  mov     [rsp+0F0h+var_A0], eax
0x1800086ec  mov     eax, [rbp+57h+var_90]
0x1800086ef  mov     [rsp+0F0h+var_A8], eax
0x1800086f3  mov     eax, [rbp+57h+var_70]
0x1800086f6  mov     [rsp+0F0h+var_B0], eax
0x1800086fa  mov     eax, [rbp+57h+var_8C]
0x1800086fd  mov     [rsp+0F0h+var_B8], eax
0x180008701  mov     [rsp+0F0h+var_C0], r12d
0x180008706  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x18000870b  mov     dword ptr [rsp+0F0h+var_D0], esi
0x18000870f  call    WPP_SF__guid_llllllll
0x180008714  xor     r12d, r12d
0x180008717  test    esi, esi
0x180008719  jz      short loc_180008732
0x18000871b  mov     dword ptr [rdi+23C0h], 1
0x180008725  jmp     loc_180008866
0x18000872a  xor     esi, esi
0x18000872c  lea     r15d, [rsi+1]
0x180008730  jmp     short loc_1800086CB
0x180008732  mov     rsi, [rbp+57h+var_68]
0x180008736  mov     r15, [rbp+57h+var_60]
0x18000873a  cmp     cs:g_PdcActivationDisabled, r12d
0x180008741  mov     [rdi+23C0h], r12d
0x180008748  jnz     short loc_1800087A8
0x18000874a  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008751  jz      short loc_18000876B
0x180008753  mov     r9, [rdi+18h]
0x180008757  mov     edx, 13h
0x18000875c  mov     ecx, 404h
0x180008761  mov     [rsp+0F0h+var_D0], rdi
0x180008766  call    WPP_SF_Jq
0x18000876b  mov     edx, r13d
0x18000876e  call    PdcActivateNetwork
0x180008773  mov     r14, rax
0x180008776  test    rax, rax
0x180008779  jnz     short loc_1800087A8
0x18000877b  mov     ebx, 490h
0x180008780  test    byte ptr cs:xmmword_1800423E0, 2
0x180008787  jz      loc_180008866
0x18000878d  mov     r9, [rdi+18h]
0x180008791  lea     edx, [rax+14h]
0x180008794  mov     ecx, 401h
0x180008799  mov     [rsp+0F0h+var_D0], rdi
0x18000879e  call    WPP_SF_Jq
0x1800087a3  jmp     loc_180008866
0x1800087a8  cmp     cs:Dhcpv6GlobalDsFeatureEnabled, r12d
0x1800087af  jz      short loc_18000881F
0x1800087b1  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x1800087b8  cmp     [rax], r12d
0x1800087bb  jnz     short loc_18000881F
0x1800087bd  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800087c4  jz      short loc_1800087DC
0x1800087c6  mov     edx, 15h
0x1800087cb  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800087d2  mov     ecx, 404h
0x1800087d7  call    WPP_SF_
0x1800087dc  call    Dhcpv6IsMachineInCs
0x1800087e1  mov     r8d, eax
0x1800087e4  lea     rdx, [rdi+22E8h]
0x1800087eb  lea     rax, [rbp+57h+var_80]
0x1800087ef  mov     r9d, r13d
0x1800087f2  mov     [rsp+0F0h+var_C8], rax
0x1800087f7  lea     rcx, [rdi+20h]
0x1800087fb  lea     rax, [rbp+57h+var_88]
0x1800087ff  mov     [rsp+0F0h+var_D0], rax
0x180008804  call    DhcpWcmAcquireRef
0x180008809  mov     ebx, eax
0x18000880b  cmp     [rbp+57h+var_88], r12d
0x18000880f  jz      short loc_18000881B
0x180008811  mov     edx, eax
0x180008813  mov     rcx, rdi
0x180008816  call    DhcpV6TraceWcmError
0x18000881b  test    ebx, ebx
0x18000881d  jnz     short loc_180008866
0x18000881f  test    r14, r14
0x180008822  jz      short loc_18000885B
0x180008824  mov     r9d, 1
0x18000882a  lock xadd cs:Dhcpv6GlobalPdcCount, r9d
0x180008833  inc     r9d
0x180008836  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000883d  jz      short loc_180008855
0x18000883f  mov     edx, 16h
0x180008844  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18000884b  mov     ecx, 404h
0x180008850  call    WPP_SF_d
0x180008855  mov     [rsi], r14
0x180008858  mov     r14, r12
0x18000885b  mov     rax, [rbp+57h+var_80]
0x18000885f  mov     [r15], rax
0x180008862  mov     [rbp+57h+var_80], r12
0x180008866  cmp     [rbp+57h+var_80], r12
0x18000886a  jz      short loc_180008894
0x18000886c  test    byte ptr cs:xmmword_1800423E0, 2
0x180008873  jz      short loc_18000888B
0x180008875  mov     edx, 17h
0x18000887a  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180008881  mov     ecx, 401h
0x180008886  call    WPP_SF_
0x18000888b  lea     rcx, [rbp+57h+var_80]
0x18000888f  call    DhcpWcmReleaseRef
0x180008894  test    r14, r14
0x180008897  jz      short loc_1800088C3
0x180008899  test    byte ptr cs:xmmword_1800423E0, 2
0x1800088a0  jz      short loc_1800088B8
0x1800088a2  mov     edx, 18h
0x1800088a7  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800088ae  mov     ecx, 401h
0x1800088b3  call    WPP_SF_
0x1800088b8  mov     r8d, r13d
0x1800088bb  mov     rcx, r14
0x1800088be  call    PdcDeactivateNetwork
0x1800088c3  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800088ca  jz      short loc_1800088E2
0x1800088cc  mov     rax, [rdi+18h]
0x1800088d0  mov     r9d, ebx
0x1800088d3  mov     [rsp+0F0h+var_C8], rax
0x1800088d8  mov     dword ptr [rsp+0F0h+var_D0], r13d
0x1800088dd  call    WPP_SF_DdJ
0x1800088e2  mov     eax, ebx
0x1800088e4  mov     rcx, [rbp+57h+var_48]
0x1800088e8  xor     rcx, rsp; StackCookie
0x1800088eb  call    __security_check_cookie
0x1800088f0  add     rsp, 0B8h
0x1800088f7  pop     r15
0x1800088f9  pop     r14
0x1800088fb  pop     r13
0x1800088fd  pop     r12
0x1800088ff  pop     rdi
0x180008900  pop     rsi
0x180008901  pop     rbx
0x180008902  pop     rbp
0x180008903  retn
```
