# Dns_NSPLookupServiceBegin

- ea: `0x180002d00`
- end: `0x1800037fc`
- name: `Dns_NSPLookupServiceBegin`
- size: `2812`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002d00`
- `0x180003804`
- `0x1800038b4`
- `0x180003b10`
- `0x180003ce0`
- `0x180004228`
- `0x1800222f0`
- `0x180038104`
- `0x18003868c`
- `0x180039470`
- `0x18003953c`
- `0x180039654`
- `0x1800398cc`
- `0x180039c24`
- `0x18003ae8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000358b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000365d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000358b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000365d`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000335d`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000335d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000318a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000318a`
- `WS2_32!__imp_ntohs` at `0x180003455`
- `WS2_32!__imp_ntohs` at `0x180003486`
- `WS2_32!__imp_ntohs` at `0x180003455`
- `WS2_32!__imp_ntohs` at `0x180003486`
- `DNSAPI!DnsNameCompare_W` at `0x180003065`
- `DNSAPI!DnsNameCompare_W` at `0x180003083`
- `DNSAPI!DnsNameCompare_W` at `0x1800030a1`
- `DNSAPI!DnsNameCompare_W` at `0x1800030bb`
- `DNSAPI!DnsNameCompare_W` at `0x180003065`
- `DNSAPI!DnsNameCompare_W` at `0x180003083`
- `DNSAPI!DnsNameCompare_W` at `0x1800030a1`
- `DNSAPI!DnsNameCompare_W` at `0x1800030bb`

## string_xrefs

- `0x1800036ba`: `service GUID`

## pseudocode

```c
__int64 __fastcall Dns_NSPLookupServiceBegin(_OWORD *a1, __int64 a2, __int64 a3, unsigned int a4, __int64 *a5)
{
  __int64 v5; // rbx
  unsigned int v6; // r13d
  const WCHAR *v9; // r12
  int v10; // ecx
  unsigned __int16 *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // r14d
  unsigned __int16 *v16; // rcx
  int v17; // r8d
  int v18; // r13d
  BOOL v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // r12d
  int v22; // ebx
  int v23; // r13d
  char ServerAndProtocolsFromString; // al
  int v25; // r8d
  __int64 v26; // rcx
  char v27; // r12
  __int64 v28; // rdx
  int v29; // r12d
  __int64 v30; // rax
  __int128 v31; // xmm0
  int v32; // eax
  int v33; // edx
  DWORD v34; // ecx
  char v35; // al
  int v37; // r10d
  unsigned int *v38; // r9
  unsigned int v39; // eax
  __int64 v40; // rcx
  int v41; // edx
  int v42; // ecx
  int v43; // r8d
  int v44; // edx
  __int64 v45; // rbx
  int i; // eax
  __int64 *v47; // rbx
  int j; // r13d
  unsigned __int16 *v49; // rax
  int v50; // [rsp+B0h] [rbp-118h]
  int v51; // [rsp+B0h] [rbp-118h]
  int v52; // [rsp+B4h] [rbp-114h]
  char v54; // [rsp+C8h] [rbp-100h]
  unsigned int v55; // [rsp+CCh] [rbp-FCh]
  int v56; // [rsp+D0h] [rbp-F8h]
  WCHAR *v57; // [rsp+D8h] [rbp-F0h]
  __int64 v58; // [rsp+E0h] [rbp-E8h]
  __int64 v59; // [rsp+E8h] [rbp-E0h]
  WCHAR S[72]; // [rsp+100h] [rbp-C8h] BYREF

  v5 = 0;
  v6 = -1;
  v9 = *(const WCHAR **)(a2 + 8);
  v57 = (WCHAR *)v9;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_(1025, 21, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_SD(v42, v41, v43, (_DWORD)v9, a4);
  }
  if ( (unsigned __int8)RNRPROV_SockEnterApi() )
  {
    if ( *(_DWORD *)a2 < 0x78u )
    {
      v34 = 10014;
      goto LABEL_69;
    }
    v11 = *(unsigned __int16 **)(a2 + 16);
    if ( !v11 )
      goto LABEL_149;
    v15 = rnr_IdForGuid(*(_QWORD *)(a2 + 16));
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF__guid_(v13, v12, v14, v11);
    if ( (a4 & 0x94000) != 0 || (a4 & 6) == 6 )
      goto LABEL_149;
    v16 = *(unsigned __int16 **)(a2 + 56);
    if ( v16 && *v16 )
    {
      v44 = *v16 - 92;
      if ( *v16 == 92 )
        v44 = v16[1];
      v17 = 0;
      if ( v44 )
        goto LABEL_111;
    }
    else
    {
      v17 = 0;
    }
    if ( (a4 & 2) != 0 )
    {
LABEL_111:
      v34 = 11004;
      goto LABEL_69;
    }
    v56 = 0;
    v55 = 0;
    v58 = 0;
    v59 = 0;
    if ( v15 == 0x80000000 )
    {
      v18 = 2;
    }
    else
    {
      v52 = 0;
      v18 = 0;
      if ( v15 != 2 )
        goto LABEL_13;
      v18 = 16;
      a4 &= ~0x100u;
    }
    v52 = v18;
LABEL_13:
    if ( (a4 & 0x2000000) != 0 && *(_DWORD *)a2 >= 0x90u )
    {
      v58 = *(_QWORD *)(a2 + 128);
      v59 = *(_QWORD *)(a2 + 136);
      v56 = *(_DWORD *)(a2 + 120);
      v55 = *(_DWORD *)(a2 + 124);
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_idL(
          *(_QWORD *)(a2 + 136),
          *(unsigned int *)(a2 + 120),
          0,
          *(_QWORD *)(a2 + 136),
          *(_DWORD *)(a2 + 124),
          *(_DWORD *)(a2 + 120));
        v17 = 0;
      }
    }
    v19 = v15 == 1 || v15 == 268435458 || (unsigned int)(v15 - 268435490) <= 1 || (v15 & 0x3000000) != 0;
    if ( v9 && *v9 )
    {
      if ( !v19 )
        goto LABEL_19;
      if ( DnsNameCompare_W(v9, L"localhost") || DnsNameCompare_W(v9, L"loopback") )
      {
        v52 = v18 | 0x24;
        v17 = 0;
      }
      else
      {
        if ( !DnsNameCompare_W(v9, g_pszHostName) && !DnsNameCompare_W(v9, g_pszHostFqdn) )
          goto LABEL_52;
        v52 = v18 | 4;
        v17 = 0;
      }
LABEL_19:
      v20 = *(_QWORD *)(a2 + 72);
      if ( v20 )
      {
        v33 = *(_DWORD *)(a2 + 64);
        if ( !v33 )
          goto LABEL_68;
        v21 = 0;
        v37 = 12582917;
        do
        {
          --v33;
          v38 = (unsigned int *)(v20 + 8LL * v17);
          if ( *v38 <= 0x17 && _bittest(&v37, *v38) )
          {
            v39 = v38[1];
            switch ( v39 )
            {
              case 0x11u:
                v21 |= 1u;
                break;
              case 6u:
                v21 |= 2u;
                break;
              case 0x16u:
                v21 |= 4u;
                break;
            }
          }
          ++v17;
        }
        while ( v33 );
        if ( !v21 )
        {
LABEL_68:
          v34 = 11004;
          v6 = -1;
          goto LABEL_69;
        }
        v54 = v21;
        if ( (xmmword_180063D60 & 4) != 0 )
          WPP_SF_d(1026, 25, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids, v21);
      }
      else
      {
        v54 = 0;
        LOBYTE(v21) = 3;
      }
      v22 = -1;
      v23 = -1;
      v50 = -1;
      ServerAndProtocolsFromString = GetServerAndProtocolsFromString(*(void **)(a2 + 80));
      v26 = 0;
      v27 = ServerAndProtocolsFromString & v21;
      if ( (v27 & 1) != 0 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
        {
          WPP_SF_(1025, 21, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids);
          v26 = 0;
        }
        if ( (*(_DWORD *)v11 & 0xFFFF0000) != 0xA0000
          || v11[2]
          || *((_BYTE *)v11 + 8) != 0xC0
          || *((_BYTE *)v11 + 9)
          || *((_BYTE *)v11 + 10)
          || *((_BYTE *)v11 + 11)
          || *((_BYTE *)v11 + 12)
          || *((_BYTE *)v11 + 13)
          || *((_BYTE *)v11 + 14)
          || *((_BYTE *)v11 + 15) != 70 )
        {
          if ( (xmmword_180063D60 & 2) != 0 )
          {
            WPP_SF_(1025, 20, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids);
            v26 = 0;
          }
          v28 = a3;
          if ( a3 )
          {
            v45 = *(_QWORD *)(a3 + 24);
            for ( i = *(_DWORD *)(a3 + 16); ; --i )
            {
              v51 = i;
              if ( !i )
                break;
              if ( v45 && *(_QWORD *)v45 )
              {
                if ( !(unsigned int)_o__wcsicmp(L"UdpPort", *(_QWORD *)v45)
                  && *(_DWORD *)(v45 + 12) == 4
                  && *(_DWORD *)(v45 + 16) >= 2u )
                {
                  v26 = 0;
                  v22 = **(unsigned __int16 **)(v45 + 24);
                  v50 = v22;
                  goto LABEL_124;
                }
                i = v51;
              }
              v45 += 32;
            }
            v26 = 0;
            v28 = a3;
          }
          v22 = -1;
          v50 = -1;
LABEL_29:
          if ( (v27 & 2) != 0 )
          {
            if ( (xmmword_180063D60 & 2) != 0 )
            {
              WPP_SF_(1025, 21, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids);
              v26 = 0;
              v28 = a3;
            }
            if ( (*(_DWORD *)v11 & 0xFFFF0000) != 0x90000
              || v11[2]
              || *((_BYTE *)v11 + 8) != 0xC0
              || *((_BYTE *)v11 + 9)
              || *((_BYTE *)v11 + 10)
              || *((_BYTE *)v11 + 11)
              || *((_BYTE *)v11 + 12)
              || *((_BYTE *)v11 + 13)
              || *((_BYTE *)v11 + 14)
              || *((_BYTE *)v11 + 15) != 70 )
            {
              if ( (xmmword_180063D60 & 2) != 0 )
              {
                WPP_SF_(1025, 20, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids);
                v26 = 0;
                v28 = a3;
              }
              if ( v28 )
              {
                v47 = *(__int64 **)(v28 + 24);
                for ( j = *(_DWORD *)(v28 + 16); j; --j )
                {
                  if ( v47 )
                  {
                    v28 = *v47;
                    if ( *v47 )
                    {
                      if ( !(unsigned int)_o__wcsicmp(L"TcpPort", v28)
                        && *((_DWORD *)v47 + 3) == 4
                        && *((_DWORD *)v47 + 4) >= 2u )
                      {
                        v49 = (unsigned __int16 *)v47[3];
                        v22 = v50;
                        v26 = 0;
                        v23 = *v49;
                        goto LABEL_37;
                      }
                    }
                  }
                  v47 += 4;
                }
                v22 = v50;
                v26 = 0;
              }
              v23 = -1;
            }
            else
            {
              v23 = *v11;
            }
          }
LABEL_37:
          if ( (xmmword_180063D60 & 4) != 0 )
            WPP_SF_sDdd(0, v28, v25, (unsigned int)"service GUID", v27, v22, v23);
          if ( v23 == -1 && v22 == -1 )
          {
            if ( (v54 & 2) == 0 || (v54 & 1) != 0 )
            {
              v29 = 0;
              goto LABEL_41;
            }
            v23 = 0;
          }
          v29 = v50;
LABEL_41:
          v30 = RnrCtx_Create(v26, v57, v55, v58);
          v5 = v30;
          if ( v30 )
          {
            v31 = *(_OWORD *)v11;
            *(_DWORD *)(v30 + 60) = a4;
            *(_DWORD *)(v30 + 48) = v15;
            *(_OWORD *)(v30 + 96) = v31;
            *(_DWORD *)(v30 + 68) = v23;
            *(_DWORD *)(v30 + 64) = v29;
            *(_DWORD *)(v30 + 44) = v52;
            *(_OWORD *)(v30 + 112) = *a1;
            *(_DWORD *)(v30 + 52) = *(_DWORD *)(a2 + 40);
            *(_DWORD *)(v30 + 72) = v56;
            *(_QWORD *)(v30 + 176) = v59;
            *(_DWORD *)(v30 + 160) = (a4 >> 27) & 1;
            RnrCtx_Release(v30);
            *a5 = v5;
            if ( (v15 & 0x3000000) != 0 )
            {
              v32 = v11[3];
              *(_DWORD *)(v5 + 56) = v32;
              if ( v32 == 1 )
                *(_DWORD *)(v5 + 56) = 0;
            }
            v6 = 0;
            goto LABEL_70;
          }
          v34 = 8;
          v6 = -1;
LABEL_69:
          SetLastError(v34);
          goto LABEL_70;
        }
        v22 = *v11;
        v50 = v22;
      }
LABEL_124:
      v28 = a3;
      goto LABEL_29;
    }
    if ( v19 )
    {
      v52 = v18 | 4;
      v57 = (WCHAR *)&Data;
      goto LABEL_19;
    }
    if ( (v18 & 2) != 0 )
    {
      v40 = *(_QWORD *)(a2 + 96);
      if ( v40 )
      {
        if ( *(_DWORD *)(a2 + 88) == 1
          && RtlIpv4AddressToStringW((const struct in_addr *)(*(_QWORD *)(v40 + 16) + 4LL), S) )
        {
          v57 = S;
LABEL_52:
          v17 = 0;
          goto LABEL_19;
        }
      }
    }
    v6 = -1;
LABEL_149:
    v34 = 87;
    goto LABEL_69;
  }
LABEL_70:
  v35 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_d(1025, 27, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids, v6);
    v35 = xmmword_180063D60;
  }
  if ( v5 )
  {
    if ( (v35 & 2) != 0 )
      WPP_SF_sqdddDqqDddDddS_guid__guid_i(
        v5 + 112,
        v5 + 96,
        v5 + 184,
        (unsigned int)"Leave LSB RnR Context:",
        v5,
        *(_DWORD *)(v5 + 32),
        *(_DWORD *)(v5 + 36),
        *(_DWORD *)(v5 + 40),
        *(_DWORD *)(v5 + 44),
        *(_QWORD *)(v5 + 16),
        *(_QWORD *)(v5 + 24),
        *(_DWORD *)(v5 + 60),
        *(_DWORD *)(v5 + 68),
        *(_DWORD *)(v5 + 64),
        *(_DWORD *)(v5 + 52),
        *(_DWORD *)(v5 + 76),
        *(_DWORD *)(v5 + 56),
        v5 + 184,
        v5 + 96,
        v5 + 112,
        *(_QWORD *)(v5 + 176));
  }
  else if ( (v35 & 2) != 0 )
  {
    WPP_SF_ss(
      v10,
      21,
      (unsigned int)WPP_1bf4e907990e34109b4356408ced46e7_Traceguids,
      (unsigned int)"Leave LSB RnR Context:",
      (__int64)"NULL RnR Context.");
  }
  return v6;
}

```

## disassembly

```asm
0x180002d00  mov     r11, rsp
0x180002d03  push    rbx
0x180002d04  push    r13
0x180002d06  sub     rsp, 1B8h
0x180002d0d  mov     rax, cs:__security_cookie
0x180002d14  xor     rax, rsp
0x180002d17  mov     [rsp+1C8h+var_38], rax
0x180002d1f  mov     rax, [rsp+1C8h+arg_20]
0x180002d27  xor     ebx, ebx
0x180002d29  mov     [r11+8], rsi
0x180002d2d  mov     r13d, 0FFFFFFFFh
0x180002d33  mov     [r11+20h], rdi
0x180002d37  mov     rsi, rdx
0x180002d3a  mov     [r11-18h], r12
0x180002d3e  mov     edi, r9d
0x180002d41  mov     r12, [rdx+8]
0x180002d45  mov     [rsp+1C8h+var_F0], r12
0x180002d4d  mov     [rsp+1C8h+var_108], r8
0x180002d55  mov     [rsp+1C8h+var_D8], rcx
0x180002d5d  mov     [rsp+1C8h+var_D0], rax
0x180002d65  mov     [r11-110h], rbx
0x180002d6c  movzx   eax, byte ptr cs:xmmword_180063D60
0x180002d73  test    al, 2
0x180002d75  jnz     loc_1800033B9
0x180002d7b  call    RNRPROV_SockEnterApi
0x180002d80  test    al, al
0x180002d82  jz      loc_1800031A6
0x180002d88  cmp     dword ptr [rsi], 78h ; 'x'
0x180002d8b  mov     [rsp+1C8h+var_20], r14
0x180002d93  mov     [rsp+1C8h+var_28], r15
0x180002d9b  jb      loc_1800033EF
0x180002da1  mov     r15, [rsi+10h]
0x180002da5  test    r15, r15
0x180002da8  jz      loc_1800036F5
0x180002dae  mov     rcx, r15
0x180002db1  call    rnr_IdForGuid
0x180002db6  mov     r14d, eax
0x180002db9  test    byte ptr cs:xmmword_180063D60, 2
0x180002dc0  jnz     loc_1800033F9
0x180002dc6  test    edi, 94000h
0x180002dcc  mov     ecx, edi
0x180002dce  setz    dl
0x180002dd1  and     ecx, 6
0x180002dd4  cmp     cl, 6
0x180002dd7  setnz   al
0x180002dda  test    al, dl
0x180002ddc  jz      loc_1800036F5
0x180002de2  mov     rcx, [rsi+38h]
0x180002de6  test    rcx, rcx
0x180002de9  jnz     loc_180003406
0x180002def  xor     r8d, r8d
0x180002df2  test    dil, 2
0x180002df6  jnz     loc_180003431
0x180002dfc  mov     [rsp+1C8h+var_F8], r8d
0x180002e04  mov     [rsp+1C8h+var_FC], r8d
0x180002e0c  mov     [rsp+1C8h+var_E8], r8
0x180002e14  mov     [rsp+1C8h+var_E0], r8
0x180002e1c  cmp     r14d, 80000000h
0x180002e23  jz      loc_1800031FD
0x180002e29  mov     [rsp+1C8h+var_114], r8d
0x180002e31  mov     r13d, r8d
0x180002e34  cmp     r14d, 2
0x180002e38  jz      loc_18000331D
0x180002e3e  bt      edi, 19h
0x180002e42  jb      loc_1800032AA
0x180002e48  cmp     r14d, 1
0x180002e4c  jnz     loc_180003387
0x180002e52  mov     eax, 1
0x180002e57  test    r12, r12
0x180002e5a  jnz     loc_180003048
0x180002e60  test    eax, eax
0x180002e62  jz      loc_18000332C
0x180002e68  or      r13d, 4
0x180002e6c  lea     rax, Data
0x180002e73  mov     [rsp+1C8h+var_114], r13d
0x180002e7b  mov     [rsp+1C8h+var_F0], rax
0x180002e83  mov     rcx, [rsi+48h]
0x180002e87  test    rcx, rcx
0x180002e8a  jnz     loc_180003174
0x180002e90  mov     [rsp+1C8h+var_100], r8d
0x180002e98  mov     r12d, 3
0x180002e9e  mov     rcx, [rsi+50h]; Src
0x180002ea2  lea     r8, [rsp+1C8h+var_110]
0x180002eaa  mov     ebx, 0FFFFFFFFh
0x180002eaf  mov     rdx, r15
0x180002eb2  mov     r13d, ebx
0x180002eb5  mov     [rsp+1C8h+var_118], ebx
0x180002ebc  call    GetServerAndProtocolsFromString
0x180002ec1  mov     rcx, [rsp+1C8h+var_110]
0x180002ec9  and     r12d, eax
0x180002ecc  mov     eax, r12d
0x180002ecf  and     eax, 1
0x180002ed2  test    rcx, rcx
0x180002ed5  jnz     loc_18000344D
0x180002edb  test    eax, eax
0x180002edd  jz      loc_180003535
0x180002ee3  test    byte ptr cs:xmmword_180063D60, 2
0x180002eea  jnz     loc_1800034A3
0x180002ef0  mov     eax, [r15]
0x180002ef3  and     eax, 0FFFF0000h
0x180002ef8  cmp     eax, 0A0000h
0x180002efd  jz      loc_1800034C6
0x180002f03  test    byte ptr cs:xmmword_180063D60, 2
0x180002f0a  jnz     loc_180003542
0x180002f10  mov     rdx, [rsp+1C8h+var_108]
0x180002f18  test    rdx, rdx
0x180002f1b  jnz     loc_180003565
0x180002f21  mov     ebx, r13d
0x180002f24  mov     [rsp+1C8h+var_118], ebx
0x180002f2b  test    r12b, 2
0x180002f2f  jz      short loc_180002F6D
0x180002f31  test    byte ptr cs:xmmword_180063D60, 2
0x180002f38  jnz     loc_1800035E6
0x180002f3e  mov     eax, [r15]
0x180002f41  and     eax, 0FFFF0000h
0x180002f46  cmp     eax, 90000h
0x180002f4b  jz      loc_180003107
0x180002f51  test    byte ptr cs:xmmword_180063D60, 2
0x180002f58  jnz     loc_180003611
0x180002f5e  test    rdx, rdx
0x180002f61  jnz     loc_18000363C
0x180002f67  mov     r13d, 0FFFFFFFFh
0x180002f6d  test    byte ptr cs:xmmword_180063D60, 4
0x180002f74  jnz     loc_1800036B2
0x180002f7a  cmp     r13d, 0FFFFFFFFh
0x180002f7e  jz      loc_1800030D3
0x180002f84  mov     r12d, [rsp+1C8h+var_118]
0x180002f8c  mov     r9, [rsp+1C8h+var_E8]
0x180002f94  mov     r8d, [rsp+1C8h+var_FC]
0x180002f9c  mov     rdx, [rsp+1C8h+var_F0]
0x180002fa4  call    RnrCtx_Create
0x180002fa9  mov     rbx, rax
0x180002fac  test    rax, rax
0x180002faf  jz      loc_18000330D
0x180002fb5  movups  xmm0, xmmword ptr [r15]
0x180002fb9  mov     [rax+3Ch], edi
0x180002fbc  mov     rcx, rbx
0x180002fbf  mov     [rax+30h], r14d
0x180002fc3  movups  xmmword ptr [rax+60h], xmm0
0x180002fc7  mov     [rax+44h], r13d
0x180002fcb  mov     [rax+40h], r12d
0x180002fcf  mov     eax, [rsp+1C8h+var_114]
0x180002fd6  mov     [rbx+2Ch], eax
0x180002fd9  mov     rax, [rsp+1C8h+var_D8]
0x180002fe1  shr     edi, 1Bh
0x180002fe4  and     edi, 1
0x180002fe7  movups  xmm0, xmmword ptr [rax]
0x180002fea  movups  xmmword ptr [rbx+70h], xmm0
0x180002fee  mov     eax, [rsi+28h]
0x180002ff1  mov     [rbx+34h], eax
0x180002ff4  mov     eax, [rsp+1C8h+var_F8]
0x180002ffb  mov     [rbx+48h], eax
0x180002ffe  mov     rax, [rsp+1C8h+var_E0]
0x180003006  mov     [rbx+0B0h], rax
0x18000300d  mov     [rbx+0A0h], edi
0x180003013  call    RnrCtx_Release
0x180003018  mov     rax, [rsp+1C8h+var_D0]
0x180003020  mov     [rax], rbx
0x180003023  test    r14d, 3000000h
0x18000302a  jz      short loc_180003040
0x18000302c  movzx   eax, word ptr [r15+6]
0x180003031  mov     [rbx+38h], eax
0x180003034  cmp     eax, 1
0x180003037  jnz     short loc_180003040
0x180003039  mov     dword ptr [rbx+38h], 0
0x180003040  xor     r13d, r13d
0x180003043  jmp     loc_180003196
0x180003048  cmp     [r12], bx
0x18000304d  jz      loc_180002E60
0x180003053  test    eax, eax
0x180003055  jz      loc_180002E83
0x18000305b  lea     rdx, String2; "localhost"
0x180003062  mov     rcx, r12; pName1
0x180003065  call    cs:__imp_DnsNameCompare_W
0x18000306c  nop     dword ptr [rax+rax+00h]
0x180003071  test    eax, eax
0x180003073  jnz     loc_180003296
0x180003079  lea     rdx, aLoopback; "loopback"
0x180003080  mov     rcx, r12; pName1
0x180003083  call    cs:__imp_DnsNameCompare_W
0x18000308a  nop     dword ptr [rax+rax+00h]
0x18000308f  test    eax, eax
0x180003091  jnz     loc_180003296
0x180003097  mov     rdx, cs:g_pszHostName; pName2
0x18000309e  mov     rcx, r12; pName1
0x1800030a1  call    cs:__imp_DnsNameCompare_W
0x1800030a8  nop     dword ptr [rax+rax+00h]
0x1800030ad  test    eax, eax
0x1800030af  jnz     short loc_1800030F3
0x1800030b1  mov     rdx, cs:g_pszHostFqdn; pName2
0x1800030b8  mov     rcx, r12; pName1
0x1800030bb  call    cs:__imp_DnsNameCompare_W
0x1800030c2  nop     dword ptr [rax+rax+00h]
0x1800030c7  test    eax, eax
0x1800030c9  jnz     short loc_1800030F3
0x1800030cb  xor     r8d, r8d
0x1800030ce  jmp     loc_180002E83
0x1800030d3  cmp     ebx, 0FFFFFFFFh
0x1800030d6  jnz     loc_180002F84
0x1800030dc  mov     eax, [rsp+1C8h+var_100]
0x1800030e3  test    al, 2
0x1800030e5  jnz     loc_1800036DF
0x1800030eb  xor     r12d, r12d
0x1800030ee  jmp     loc_180002F8C
0x1800030f3  or      r13d, 4
0x1800030f7  mov     [rsp+1C8h+var_114], r13d
0x1800030ff  xor     r8d, r8d
0x180003102  jmp     loc_180002E83
0x180003107  cmp     word ptr [r15+4], 0
0x18000310d  jnz     loc_180002F51
0x180003113  cmp     byte ptr [r15+8], 0C0h
0x180003118  jnz     loc_180002F51
0x18000311e  cmp     byte ptr [r15+9], 0
0x180003123  jnz     loc_180002F51
0x180003129  cmp     byte ptr [r15+0Ah], 0
0x18000312e  jnz     loc_180002F51
0x180003134  cmp     byte ptr [r15+0Bh], 0
0x180003139  jnz     loc_180002F51
0x18000313f  cmp     byte ptr [r15+0Ch], 0
0x180003144  jnz     loc_180002F51
0x18000314a  cmp     byte ptr [r15+0Dh], 0
0x18000314f  jnz     loc_180002F51
0x180003155  cmp     byte ptr [r15+0Eh], 0
0x18000315a  jnz     loc_180002F51
0x180003160  cmp     byte ptr [r15+0Fh], 46h ; 'F'
0x180003165  jnz     loc_180002F51
0x18000316b  movzx   r13d, word ptr [r15]
0x18000316f  jmp     loc_180002F6D
0x180003174  mov     edx, [rsi+40h]
0x180003177  test    edx, edx
0x180003179  jnz     loc_180003210
0x18000317f  mov     ecx, 2AFCh; dwErrCode
0x180003184  mov     r13d, 0FFFFFFFFh
0x18000318a  call    cs:__imp_SetLastError
0x180003191  nop     dword ptr [rax+rax+00h]
0x180003196  mov     r14, [rsp+1C8h+var_20]
0x18000319e  mov     r15, [rsp+1C8h+var_28]
0x1800031a6  movzx   eax, byte ptr cs:xmmword_180063D60
0x1800031ad  mov     r12, [rsp+1C8h+var_18]
0x1800031b5  mov     rdi, [rsp+1C8h+arg_18]
0x1800031bd  mov     rsi, [rsp+1C8h+arg_0]
0x1800031c5  test    al, 2
0x1800031c7  jnz     loc_1800036FF
0x1800031cd  test    rbx, rbx
0x1800031d0  jz      loc_180003724
0x1800031d6  test    al, 2
0x1800031d8  jnz     loc_180003755
0x1800031de  mov     eax, r13d
0x1800031e1  mov     rcx, [rsp+1C8h+var_38]
0x1800031e9  xor     rcx, rsp; StackCookie
0x1800031ec  call    __security_check_cookie
0x1800031f1  add     rsp, 1B8h
0x1800031f8  pop     r13
0x1800031fa  pop     rbx
0x1800031fb  retn
0x1800031fd  mov     r13d, 2
0x180003203  mov     [rsp+1C8h+var_114], r13d
0x18000320b  jmp     loc_180002E3E
0x180003210  mov     r12d, r8d
0x180003213  mov     r10d, 0C00005h
0x180003219  nop     dword ptr [rax+00000000h]
0x180003220  movsxd  rax, r8d
0x180003223  dec     edx
0x180003225  lea     r9, [rcx+rax*8]
0x180003229  mov     eax, [rcx+rax*8]
0x18000322c  cmp     eax, 17h
0x18000322f  ja      short loc_180003244
0x180003231  bt      r10d, eax
0x180003235  jnb     short loc_180003244
0x180003237  mov     eax, [r9+4]
0x18000323b  cmp     eax, 11h
0x18000323e  jnz     short loc_180003287
0x180003240  or      r12d, 1
0x180003244  inc     r8d
0x180003247  test    edx, edx
0x180003249  jnz     short loc_180003220
0x18000324b  test    r12d, r12d
0x18000324e  jz      loc_18000317F
0x180003254  mov     [rsp+1C8h+var_100], r12d
0x18000325c  test    byte ptr cs:xmmword_180063D60, 4
0x180003263  jz      loc_180002E9E
0x180003269  mov     edx, 19h
0x18000326e  lea     r8, WPP_a6cfffb9308e3c45e18981891f5b37e8_Traceguids
0x180003275  mov     ecx, 402h
0x18000327a  mov     r9d, r12d
0x18000327d  call    WPP_SF_d
0x180003282  jmp     loc_180002E9E
0x180003287  cmp     eax, 6
0x18000328a  jnz     loc_18000343B
0x180003290  or      r12d, 2
0x180003294  jmp     short loc_180003244
0x180003296  or      r13d, 24h
0x18000329a  mov     [rsp+1C8h+var_114], r13d
0x1800032a2  xor     r8d, r8d
0x1800032a5  jmp     loc_180002E83
0x1800032aa  cmp     dword ptr [rsi], 90h
0x1800032b0  jb      loc_180002E48
0x1800032b6  mov     rcx, [rsi+80h]
0x1800032bd  mov     edx, [rsi+78h]
0x1800032c0  mov     eax, [rsi+7Ch]
  ... truncated ...
```
