# PdcActivateNetwork

- ea: `0x1800456f0`
- end: `0x1800459d5`
- name: `PdcActivateNetwork`
- size: `741`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000a8bc`

## callees

- `0x18001cef0`
- `0x18001d826`
- `0x1800456f0`
- `0x18004b4bc`
- `0x18004dc0c`
- `0x18004dd28`

## import_xrefs

- `UMPDC!Pdcv2ActivationClientActivate` at `0x180045947`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x180045947`

## string_xrefs

- `0x1800458a0`: `DHCPv6Reconfig`

## pseudocode

```c
__int64 __fastcall PdcActivateNetwork(__int64 a1, int a2)
{
  unsigned int v3; // edi
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  const wchar_t *v8; // rax
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // eax
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h]
  __int128 v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  _BYTE v27[176]; // [rsp+90h] [rbp-70h] BYREF

  v26 = 0;
  v3 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  memset_0(v27, 0, 0xA8u);
  v22 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_ddD(1028, 18, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, 0, a2, 300);
  v4 = g_Pdcv2Handle;
  if ( g_Pdcv2Handle )
  {
    *(_QWORD *)&v23 = 0x12C00000003LL;
    if ( a2 > 10 )
    {
      if ( a2 > 16 )
      {
        v16 = a2 - 17;
        if ( !v16 )
        {
          v8 = L"DHCPv6Decline";
          goto LABEL_50;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v8 = L"DHCPv6Info";
          goto LABEL_50;
        }
        v18 = v17 - 1;
        if ( !v18 )
        {
          v8 = L"DHCPv6ReSolicit";
          goto LABEL_50;
        }
        if ( v18 == 1 )
        {
          v8 = L"DHCPv6ReleasePrefix";
          goto LABEL_50;
        }
      }
      else
      {
        if ( a2 == 16 )
        {
          v8 = L"DHCPv6Release";
          goto LABEL_50;
        }
        v12 = a2 - 11;
        if ( !v12 )
        {
          v8 = L"DHCPv6SolicitPrefix";
          goto LABEL_50;
        }
        v13 = v12 - 1;
        if ( !v13 )
        {
          v8 = L"DHCPv6Reconfig";
          goto LABEL_50;
        }
        v14 = v13 - 1;
        if ( !v14 )
        {
          v8 = L"DHCPv6Renew";
          goto LABEL_50;
        }
        v15 = v14 - 1;
        if ( !v15 )
        {
          v8 = L"DHCPv6Rebind";
          goto LABEL_50;
        }
        if ( v15 == 1 )
        {
          v8 = L"DHCPv6ReConfirm";
          goto LABEL_50;
        }
      }
    }
    else
    {
      if ( a2 == 10 )
      {
        v8 = L"DHCPv6SolicitAndGetAdvertisement";
        goto LABEL_50;
      }
      if ( a2 > 5 )
      {
        v9 = a2 - 6;
        if ( !v9 )
        {
          v8 = L"DHCPv4Decline";
          goto LABEL_50;
        }
        v10 = v9 - 1;
        if ( !v10 )
        {
          v8 = L"DHCPv4Renew";
          goto LABEL_50;
        }
        v11 = v10 - 1;
        if ( !v11 )
        {
          v8 = L"DHCPv4Release";
          goto LABEL_50;
        }
        if ( v11 == 1 )
        {
          v8 = L"DHCPv4ServerAvailability";
          goto LABEL_50;
        }
      }
      else
      {
        if ( a2 == 5 )
        {
          v8 = L"DHCPv4Inform";
          goto LABEL_50;
        }
        if ( !a2 )
        {
          v8 = L"DHCPv4Init";
          goto LABEL_50;
        }
        v5 = a2 - 1;
        if ( !v5 )
        {
          v8 = L"DHCPv4Discover";
          goto LABEL_50;
        }
        v6 = v5 - 1;
        if ( !v6 )
        {
          v8 = L"DHCPv4Offer";
          goto LABEL_50;
        }
        v7 = v6 - 1;
        if ( !v7 )
        {
          v8 = L"DHCPv4Request";
          goto LABEL_50;
        }
        if ( v7 == 1 )
        {
          v8 = L"DHCPv4Ack";
LABEL_50:
          *(_QWORD *)&v24 = v8;
          DWORD2(v25) = 2;
          *((_QWORD *)&v24 + 1) = v27;
          v26 = -1;
          v19 = Pdcv2ActivationClientActivate(g_Pdcv2Handle, &v23, 0, 0, L"DHCPv4", 0, &v22, &v21);
          v3 = v19;
          if ( v19 < 0 )
          {
            v22 = 0;
            if ( (xmmword_1800616A0 & 2) != 0 )
              WPP_SF_Dd(1025, 19, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, (unsigned int)v19, v21);
          }
          goto LABEL_53;
        }
      }
    }
    v8 = L"Unknown";
    goto LABEL_50;
  }
LABEL_53:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dq(v4, 20, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, v3, v22);
  return v22;
}

```

## disassembly

```asm
0x1800456f0  mov     [rsp-8+arg_0], rbx
0x1800456f5  mov     [rsp-8+arg_8], rdi
0x1800456fa  push    rbp
0x1800456fb  lea     rbp, [rsp-50h]
0x180045700  sub     rsp, 150h
0x180045707  mov     rax, cs:__security_cookie
0x18004570e  xor     rax, rsp
0x180045711  mov     [rbp+50h+var_10], rax
0x180045715  xorps   xmm0, xmm0
0x180045718  lea     rcx, [rbp+50h+var_C0]; void *
0x18004571c  xor     eax, eax
0x18004571e  mov     ebx, edx
0x180045720  xor     edx, edx; Val
0x180045722  mov     [rbp+50h+var_D0], rax
0x180045726  xor     edi, edi
0x180045728  mov     [rsp+150h+var_110], eax
0x18004572c  mov     r8d, 0A8h; Size
0x180045732  movups  [rsp+150h+var_100], xmm0
0x180045737  movups  [rsp+150h+var_F0], xmm0
0x18004573c  movups  [rsp+150h+var_E0], xmm0
0x180045741  call    memset_0
0x180045746  mov     [rsp+150h+var_108], rdi
0x18004574b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045752  jz      short loc_180045777
0x180045754  lea     edx, [rdi+12h]
0x180045757  mov     [rsp+150h+var_128], 12Ch
0x18004575f  mov     ecx, 404h
0x180045764  mov     dword ptr [rsp+150h+var_130], ebx
0x180045768  xor     r9d, r9d
0x18004576b  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x180045772  call    WPP_SF_ddD
0x180045777  mov     rcx, cs:g_Pdcv2Handle
0x18004577e  test    rcx, rcx
0x180045781  jz      loc_180045988
0x180045787  mov     dword ptr [rsp+150h+var_100], 3
0x18004578f  mov     dword ptr [rsp+150h+var_100+4], 12Ch
0x180045797  cmp     ebx, 0Ah
0x18004579a  jg      loc_180045865
0x1800457a0  jz      loc_180045859
0x1800457a6  cmp     ebx, 5
0x1800457a9  jg      short loc_180045811
0x1800457ab  jz      short loc_180045805
0x1800457ad  test    ebx, ebx
0x1800457af  jz      short loc_1800457F9
0x1800457b1  sub     ebx, 1
0x1800457b4  jz      short loc_1800457ED
0x1800457b6  sub     ebx, 1
0x1800457b9  jz      short loc_1800457E1
0x1800457bb  sub     ebx, 1
0x1800457be  jz      short loc_1800457D5
0x1800457c0  cmp     ebx, 1
0x1800457c3  jnz     loc_1800458CF
0x1800457c9  lea     rax, aDhcpv4ack; "DHCPv4Ack"
0x1800457d0  jmp     loc_1800458FA
0x1800457d5  lea     rax, aDhcpv4request; "DHCPv4Request"
0x1800457dc  jmp     loc_1800458FA
0x1800457e1  lea     rax, aDhcpv4offer; "DHCPv4Offer"
0x1800457e8  jmp     loc_1800458FA
0x1800457ed  lea     rax, aDhcpv4discover; "DHCPv4Discover"
0x1800457f4  jmp     loc_1800458FA
0x1800457f9  lea     rax, aDhcpv4init; "DHCPv4Init"
0x180045800  jmp     loc_1800458FA
0x180045805  lea     rax, aDhcpv4inform; "DHCPv4Inform"
0x18004580c  jmp     loc_1800458FA
0x180045811  sub     ebx, 6
0x180045814  jz      short loc_18004584D
0x180045816  sub     ebx, 1
0x180045819  jz      short loc_180045841
0x18004581b  sub     ebx, 1
0x18004581e  jz      short loc_180045835
0x180045820  cmp     ebx, 1
0x180045823  jnz     loc_1800458CF
0x180045829  lea     rax, aDhcpv4serverav; "DHCPv4ServerAvailability"
0x180045830  jmp     loc_1800458FA
0x180045835  lea     rax, aDhcpv4release; "DHCPv4Release"
0x18004583c  jmp     loc_1800458FA
0x180045841  lea     rax, aDhcpv4renew; "DHCPv4Renew"
0x180045848  jmp     loc_1800458FA
0x18004584d  lea     rax, aDhcpv4decline; "DHCPv4Decline"
0x180045854  jmp     loc_1800458FA
0x180045859  lea     rax, aDhcpv6solicita; "DHCPv6SolicitAndGetAdvertisement"
0x180045860  jmp     loc_1800458FA
0x180045865  cmp     ebx, 10h
0x180045868  jg      short loc_1800458BB
0x18004586a  jz      short loc_1800458B2
0x18004586c  sub     ebx, 0Bh
0x18004586f  jz      short loc_1800458A9
0x180045871  sub     ebx, 1
0x180045874  jz      short loc_1800458A0
0x180045876  sub     ebx, 1
0x180045879  jz      short loc_180045897
0x18004587b  sub     ebx, 1
0x18004587e  jz      short loc_18004588E
0x180045880  cmp     ebx, 1
0x180045883  jnz     short loc_1800458CF
0x180045885  lea     rax, aDhcpv6reconfir; "DHCPv6ReConfirm"
0x18004588c  jmp     short loc_1800458FA
0x18004588e  lea     rax, aDhcpv6rebind; "DHCPv6Rebind"
0x180045895  jmp     short loc_1800458FA
0x180045897  lea     rax, aDhcpv6renew; "DHCPv6Renew"
0x18004589e  jmp     short loc_1800458FA
0x1800458a0  lea     rax, aDhcpv6reconfig; "DHCPv6Reconfig"
0x1800458a7  jmp     short loc_1800458FA
0x1800458a9  lea     rax, aDhcpv6solicitp; "DHCPv6SolicitPrefix"
0x1800458b0  jmp     short loc_1800458FA
0x1800458b2  lea     rax, aDhcpv6release; "DHCPv6Release"
0x1800458b9  jmp     short loc_1800458FA
0x1800458bb  sub     ebx, 11h
0x1800458be  jz      short loc_1800458F3
0x1800458c0  sub     ebx, 1
0x1800458c3  jz      short loc_1800458EA
0x1800458c5  sub     ebx, 1
0x1800458c8  jz      short loc_1800458E1
0x1800458ca  cmp     ebx, 1
0x1800458cd  jz      short loc_1800458D8
0x1800458cf  lea     rax, aUnknown_0; "Unknown"
0x1800458d6  jmp     short loc_1800458FA
0x1800458d8  lea     rax, aDhcpv6releasep; "DHCPv6ReleasePrefix"
0x1800458df  jmp     short loc_1800458FA
0x1800458e1  lea     rax, aDhcpv6resolici; "DHCPv6ReSolicit"
0x1800458e8  jmp     short loc_1800458FA
0x1800458ea  lea     rax, aDhcpv6info; "DHCPv6Info"
0x1800458f1  jmp     short loc_1800458FA
0x1800458f3  lea     rax, aDhcpv6decline; "DHCPv6Decline"
0x1800458fa  mov     qword ptr [rsp+150h+var_F0], rax
0x1800458ff  lea     rdx, [rsp+150h+var_100]
0x180045904  lea     rax, [rbp+50h+var_C0]
0x180045908  mov     dword ptr [rsp+150h+var_E0+8], 2
0x180045910  mov     qword ptr [rsp+150h+var_F0+8], rax
0x180045915  xor     r9d, r9d
0x180045918  lea     rax, [rsp+150h+var_110]
0x18004591d  mov     [rbp+50h+var_D0], 0FFFFFFFFFFFFFFFFh
0x180045925  mov     [rsp+150h+var_118], rax
0x18004592a  xor     r8d, r8d
0x18004592d  lea     rax, [rsp+150h+var_108]
0x180045932  mov     [rsp+150h+var_120], rax
0x180045937  lea     rax, aDhcpv4; "DHCPv4"
0x18004593e  mov     [rsp+150h+var_128], edi
0x180045942  mov     [rsp+150h+var_130], rax
0x180045947  call    cs:__imp_Pdcv2ActivationClientActivate
0x18004594d  mov     edi, eax
0x18004594f  test    eax, eax
0x180045951  jns     short loc_180045988
0x180045953  mov     [rsp+150h+var_108], 0
0x18004595c  test    byte ptr cs:xmmword_1800616A0, 2
0x180045963  jz      short loc_180045988
0x180045965  mov     r8d, [rsp+150h+var_110]
0x18004596a  mov     edx, 13h
0x18004596f  mov     dword ptr [rsp+150h+var_130], r8d
0x180045974  mov     ecx, 401h
0x180045979  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x180045980  mov     r9d, eax
0x180045983  call    WPP_SF_Dd
0x180045988  test    byte ptr cs:xmmword_1800616A0, 10h
0x18004598f  jz      short loc_1800459AF
0x180045991  mov     rax, [rsp+150h+var_108]
0x180045996  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x18004599d  mov     edx, 14h
0x1800459a2  mov     [rsp+150h+var_130], rax
0x1800459a7  mov     r9d, edi
0x1800459aa  call    WPP_SF_dq
0x1800459af  mov     rax, [rsp+150h+var_108]
0x1800459b4  mov     rcx, [rbp+50h+var_10]
0x1800459b8  xor     rcx, rsp; StackCookie
0x1800459bb  call    __security_check_cookie
0x1800459c0  lea     r11, [rsp+150h+var_s0]
0x1800459c8  mov     rbx, [r11+10h]
0x1800459cc  mov     rdi, [r11+18h]
0x1800459d0  mov     rsp, r11
0x1800459d3  pop     rbp
0x1800459d4  retn
```
