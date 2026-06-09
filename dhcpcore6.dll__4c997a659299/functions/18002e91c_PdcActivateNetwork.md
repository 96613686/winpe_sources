# PdcActivateNetwork

- ea: `0x18002e91c`
- end: `0x18002ebf8`
- name: `PdcActivateNetwork`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008440`

## callees

- `0x180019ad0`
- `0x18001a3ee`
- `0x18002e91c`
- `0x1800330cc`
- `0x1800340b4`
- `0x1800341ec`

## import_xrefs

- `UMPDC!Pdcv2ActivationClientActivate` at `0x18002eb6f`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x18002eb6f`

## string_xrefs

- `0x18002eac8`: `DHCPv6Reconfig`

## pseudocode

```c
__int64 __fastcall PdcActivateNetwork(__int64 a1, int a2)
{
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  const wchar_t *v11; // rax
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // eax
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+60h] [rbp-A0h]
  __int128 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[176]; // [rsp+90h] [rbp-70h] BYREF

  v29 = 0;
  v3 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v30, 0, 0xA8u);
  v25 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_ddd(v5, 18, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, 1, a2, 300);
  v7 = g_Pdcv2Handle;
  if ( g_Pdcv2Handle )
  {
    *(_QWORD *)&v26 = 0x12C00000003LL;
    if ( a2 > 10 )
    {
      if ( a2 > 16 )
      {
        v19 = a2 - 17;
        if ( !v19 )
        {
          v11 = L"DHCPv6Decline";
          goto LABEL_50;
        }
        v20 = v19 - 1;
        if ( !v20 )
        {
          v11 = L"DHCPv6Info";
          goto LABEL_50;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
          v11 = L"DHCPv6ReSolicit";
          goto LABEL_50;
        }
        if ( v21 == 1 )
        {
          v11 = L"DHCPv6ReleasePrefix";
          goto LABEL_50;
        }
      }
      else
      {
        if ( a2 == 16 )
        {
          v11 = L"DHCPv6Release";
          goto LABEL_50;
        }
        v15 = a2 - 11;
        if ( !v15 )
        {
          v11 = L"DHCPv6SolicitPrefix";
          goto LABEL_50;
        }
        v16 = v15 - 1;
        if ( !v16 )
        {
          v11 = L"DHCPv6Reconfig";
          goto LABEL_50;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          v11 = L"DHCPv6Renew";
          goto LABEL_50;
        }
        v18 = v17 - 1;
        if ( !v18 )
        {
          v11 = L"DHCPv6Rebind";
          goto LABEL_50;
        }
        if ( v18 == 1 )
        {
          v11 = L"DHCPv6ReConfirm";
          goto LABEL_50;
        }
      }
    }
    else
    {
      if ( a2 == 10 )
      {
        v11 = L"DHCPv6SolicitAndGetAdvertisement";
        goto LABEL_50;
      }
      if ( a2 > 5 )
      {
        v12 = a2 - 6;
        if ( !v12 )
        {
          v11 = L"DHCPv4Decline";
          goto LABEL_50;
        }
        v13 = v12 - 1;
        if ( !v13 )
        {
          v11 = L"DHCPv4Renew";
          goto LABEL_50;
        }
        v14 = v13 - 1;
        if ( !v14 )
        {
          v11 = L"DHCPv4Release";
          goto LABEL_50;
        }
        if ( v14 == 1 )
        {
          v11 = L"DHCPv4ServerAvailability";
          goto LABEL_50;
        }
      }
      else
      {
        if ( a2 == 5 )
        {
          v11 = L"DHCPv4Inform";
          goto LABEL_50;
        }
        if ( !a2 )
        {
          v11 = L"DHCPv4Init";
          goto LABEL_50;
        }
        v8 = a2 - 1;
        if ( !v8 )
        {
          v11 = L"DHCPv4Discover";
          goto LABEL_50;
        }
        v9 = v8 - 1;
        if ( !v9 )
        {
          v11 = L"DHCPv4Offer";
          goto LABEL_50;
        }
        v10 = v9 - 1;
        if ( !v10 )
        {
          v11 = L"DHCPv4Request";
          goto LABEL_50;
        }
        if ( v10 == 1 )
        {
          v11 = L"DHCPv4Ack";
LABEL_50:
          *(_QWORD *)&v27 = v11;
          DWORD2(v28) = 2;
          *((_QWORD *)&v27 + 1) = v30;
          v29 = -1;
          v22 = Pdcv2ActivationClientActivate(g_Pdcv2Handle, &v26, 0, 0, L"DHCPv6", 0, &v25, &v24);
          v3 = v22;
          if ( v22 < 0 )
          {
            v25 = 0;
            if ( (xmmword_1800423E0 & 2) != 0 )
              WPP_SF_dd(1025, 19, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, (unsigned int)v22, v24);
          }
          goto LABEL_53;
        }
      }
    }
    v11 = L"Unknown";
    goto LABEL_50;
  }
LABEL_53:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_dq(v7, v4, v6, v3, v25);
  return v25;
}

```

## disassembly

```asm
0x18002e91c  mov     [rsp-8+arg_0], rbx
0x18002e921  mov     [rsp-8+arg_8], rdi
0x18002e926  push    rbp
0x18002e927  lea     rbp, [rsp-50h]
0x18002e92c  sub     rsp, 150h
0x18002e933  mov     rax, cs:__security_cookie
0x18002e93a  xor     rax, rsp
0x18002e93d  mov     [rbp+50h+var_10], rax
0x18002e941  xorps   xmm0, xmm0
0x18002e944  lea     rcx, [rbp+50h+var_C0]; void *
0x18002e948  xor     eax, eax
0x18002e94a  mov     ebx, edx
0x18002e94c  xor     edx, edx; Val
0x18002e94e  mov     [rbp+50h+var_D0], rax
0x18002e952  xor     edi, edi
0x18002e954  mov     [rsp+150h+var_110], eax
0x18002e958  mov     r8d, 0A8h; Size
0x18002e95e  movups  [rsp+150h+var_100], xmm0
0x18002e963  movups  [rsp+150h+var_F0], xmm0
0x18002e968  movups  [rsp+150h+var_E0], xmm0
0x18002e96d  call    memset_0
0x18002e972  mov     [rsp+150h+var_108], rdi
0x18002e977  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e97e  jz      short loc_18002E99F
0x18002e980  lea     edx, [rdi+12h]
0x18002e983  mov     [rsp+150h+var_128], 12Ch
0x18002e98b  lea     r9d, [rdi+1]
0x18002e98f  mov     dword ptr [rsp+150h+var_130], ebx
0x18002e993  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x18002e99a  call    WPP_SF_ddd
0x18002e99f  mov     rcx, cs:g_Pdcv2Handle
0x18002e9a6  test    rcx, rcx
0x18002e9a9  jz      loc_18002EBB6
0x18002e9af  mov     dword ptr [rsp+150h+var_100], 3
0x18002e9b7  mov     dword ptr [rsp+150h+var_100+4], 12Ch
0x18002e9bf  cmp     ebx, 0Ah
0x18002e9c2  jg      loc_18002EA8D
0x18002e9c8  jz      loc_18002EA81
0x18002e9ce  cmp     ebx, 5
0x18002e9d1  jg      short loc_18002EA39
0x18002e9d3  jz      short loc_18002EA2D
0x18002e9d5  test    ebx, ebx
0x18002e9d7  jz      short loc_18002EA21
0x18002e9d9  sub     ebx, 1
0x18002e9dc  jz      short loc_18002EA15
0x18002e9de  sub     ebx, 1
0x18002e9e1  jz      short loc_18002EA09
0x18002e9e3  sub     ebx, 1
0x18002e9e6  jz      short loc_18002E9FD
0x18002e9e8  cmp     ebx, 1
0x18002e9eb  jnz     loc_18002EAF7
0x18002e9f1  lea     rax, aDhcpv4ack; "DHCPv4Ack"
0x18002e9f8  jmp     loc_18002EB22
0x18002e9fd  lea     rax, aDhcpv4request; "DHCPv4Request"
0x18002ea04  jmp     loc_18002EB22
0x18002ea09  lea     rax, aDhcpv4offer; "DHCPv4Offer"
0x18002ea10  jmp     loc_18002EB22
0x18002ea15  lea     rax, aDhcpv4discover; "DHCPv4Discover"
0x18002ea1c  jmp     loc_18002EB22
0x18002ea21  lea     rax, aDhcpv4init; "DHCPv4Init"
0x18002ea28  jmp     loc_18002EB22
0x18002ea2d  lea     rax, aDhcpv4inform; "DHCPv4Inform"
0x18002ea34  jmp     loc_18002EB22
0x18002ea39  sub     ebx, 6
0x18002ea3c  jz      short loc_18002EA75
0x18002ea3e  sub     ebx, 1
0x18002ea41  jz      short loc_18002EA69
0x18002ea43  sub     ebx, 1
0x18002ea46  jz      short loc_18002EA5D
0x18002ea48  cmp     ebx, 1
0x18002ea4b  jnz     loc_18002EAF7
0x18002ea51  lea     rax, aDhcpv4serverav; "DHCPv4ServerAvailability"
0x18002ea58  jmp     loc_18002EB22
0x18002ea5d  lea     rax, aDhcpv4release; "DHCPv4Release"
0x18002ea64  jmp     loc_18002EB22
0x18002ea69  lea     rax, aDhcpv4renew; "DHCPv4Renew"
0x18002ea70  jmp     loc_18002EB22
0x18002ea75  lea     rax, aDhcpv4decline; "DHCPv4Decline"
0x18002ea7c  jmp     loc_18002EB22
0x18002ea81  lea     rax, aDhcpv6solicita; "DHCPv6SolicitAndGetAdvertisement"
0x18002ea88  jmp     loc_18002EB22
0x18002ea8d  cmp     ebx, 10h
0x18002ea90  jg      short loc_18002EAE3
0x18002ea92  jz      short loc_18002EADA
0x18002ea94  sub     ebx, 0Bh
0x18002ea97  jz      short loc_18002EAD1
0x18002ea99  sub     ebx, 1
0x18002ea9c  jz      short loc_18002EAC8
0x18002ea9e  sub     ebx, 1
0x18002eaa1  jz      short loc_18002EABF
0x18002eaa3  sub     ebx, 1
0x18002eaa6  jz      short loc_18002EAB6
0x18002eaa8  cmp     ebx, 1
0x18002eaab  jnz     short loc_18002EAF7
0x18002eaad  lea     rax, aDhcpv6reconfir; "DHCPv6ReConfirm"
0x18002eab4  jmp     short loc_18002EB22
0x18002eab6  lea     rax, aDhcpv6rebind; "DHCPv6Rebind"
0x18002eabd  jmp     short loc_18002EB22
0x18002eabf  lea     rax, aDhcpv6renew; "DHCPv6Renew"
0x18002eac6  jmp     short loc_18002EB22
0x18002eac8  lea     rax, aDhcpv6reconfig; "DHCPv6Reconfig"
0x18002eacf  jmp     short loc_18002EB22
0x18002ead1  lea     rax, aDhcpv6solicitp; "DHCPv6SolicitPrefix"
0x18002ead8  jmp     short loc_18002EB22
0x18002eada  lea     rax, aDhcpv6release; "DHCPv6Release"
0x18002eae1  jmp     short loc_18002EB22
0x18002eae3  sub     ebx, 11h
0x18002eae6  jz      short loc_18002EB1B
0x18002eae8  sub     ebx, 1
0x18002eaeb  jz      short loc_18002EB12
0x18002eaed  sub     ebx, 1
0x18002eaf0  jz      short loc_18002EB09
0x18002eaf2  cmp     ebx, 1
0x18002eaf5  jz      short loc_18002EB00
0x18002eaf7  lea     rax, aUnknown; "Unknown"
0x18002eafe  jmp     short loc_18002EB22
0x18002eb00  lea     rax, aDhcpv6releasep; "DHCPv6ReleasePrefix"
0x18002eb07  jmp     short loc_18002EB22
0x18002eb09  lea     rax, aDhcpv6resolici; "DHCPv6ReSolicit"
0x18002eb10  jmp     short loc_18002EB22
0x18002eb12  lea     rax, aDhcpv6info; "DHCPv6Info"
0x18002eb19  jmp     short loc_18002EB22
0x18002eb1b  lea     rax, aDhcpv6decline; "DHCPv6Decline"
0x18002eb22  mov     qword ptr [rsp+150h+var_F0], rax
0x18002eb27  lea     rdx, [rsp+150h+var_100]
0x18002eb2c  lea     rax, [rbp+50h+var_C0]
0x18002eb30  mov     dword ptr [rsp+150h+var_E0+8], 2
0x18002eb38  mov     qword ptr [rsp+150h+var_F0+8], rax
0x18002eb3d  xor     r9d, r9d
0x18002eb40  lea     rax, [rsp+150h+var_110]
0x18002eb45  mov     [rbp+50h+var_D0], 0FFFFFFFFFFFFFFFFh
0x18002eb4d  mov     [rsp+150h+var_118], rax
0x18002eb52  xor     r8d, r8d
0x18002eb55  lea     rax, [rsp+150h+var_108]
0x18002eb5a  mov     [rsp+150h+var_120], rax
0x18002eb5f  lea     rax, aDhcpv6; "DHCPv6"
0x18002eb66  mov     [rsp+150h+var_128], edi
0x18002eb6a  mov     [rsp+150h+var_130], rax
0x18002eb6f  call    cs:__imp_Pdcv2ActivationClientActivate
0x18002eb76  nop     dword ptr [rax+rax+00h]
0x18002eb7b  mov     edi, eax
0x18002eb7d  test    eax, eax
0x18002eb7f  jns     short loc_18002EBB6
0x18002eb81  mov     [rsp+150h+var_108], 0
0x18002eb8a  test    byte ptr cs:xmmword_1800423E0, 2
0x18002eb91  jz      short loc_18002EBB6
0x18002eb93  mov     r9d, [rsp+150h+var_110]
0x18002eb98  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x18002eb9f  mov     dword ptr [rsp+150h+var_130], r9d
0x18002eba4  mov     edx, 13h
0x18002eba9  mov     r9d, eax
0x18002ebac  mov     ecx, 401h
0x18002ebb1  call    WPP_SF_dd
0x18002ebb6  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002ebbd  jz      short loc_18002EBD1
0x18002ebbf  mov     rax, [rsp+150h+var_108]
0x18002ebc4  mov     r9d, edi
0x18002ebc7  mov     [rsp+150h+var_130], rax
0x18002ebcc  call    WPP_SF_dq
0x18002ebd1  mov     rax, [rsp+150h+var_108]
0x18002ebd6  mov     rcx, [rbp+50h+var_10]
0x18002ebda  xor     rcx, rsp; StackCookie
0x18002ebdd  call    __security_check_cookie
0x18002ebe2  lea     r11, [rsp+150h+var_s0]
0x18002ebea  mov     rbx, [r11+10h]
0x18002ebee  mov     rdi, [r11+18h]
0x18002ebf2  mov     rsp, r11
0x18002ebf5  pop     rbp
0x18002ebf6  retn
```
