# CreateDhcpv6Renew

- ea: `0x1800027e0`
- end: `0x180002ca4`
- name: `CreateDhcpv6Renew`
- size: `1220`
- prototype: `__int64 __fastcall(__int64, __int16 *, int *, int, void *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180021150`
- `0x180021b58`

## callees

- `0x180001d8c`
- `0x1800027e0`
- `0x180002cac`
- `0x180002f80`
- `0x180003100`
- `0x180004b30`
- `0x18000ed3c`
- `0x180017ffc`
- `0x180018740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180030920`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6Renew(__int64 a1, __int16 *a2, int *a3, int a4, void *a5, void *a6)
{
  __int64 v8; // rcx
  unsigned int appended; // ebx
  __int64 v12; // rdx
  __int16 v13; // ax
  __int64 v14; // rdx
  _QWORD *v15; // r14
  void *v16; // rcx
  __int64 v17; // r8
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v22; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v23; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v25; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v26; // [rsp+84h] [rbp-7Ch] BYREF
  int Src; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v28; // [rsp+8Ch] [rbp-74h] BYREF
  int *v29; // [rsp+90h] [rbp-70h]
  __int16 v30; // [rsp+A0h] [rbp-60h] BYREF
  char v31[206]; // [rsp+A2h] [rbp-5Eh] BYREF
  _BYTE v32[272]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v33[208]; // [rsp+280h] [rbp+180h] BYREF
  _WORD v34[2048]; // [rsp+350h] [rbp+250h] BYREF

  v25 = 0;
  v8 = 259;
  v23 = 259;
  v29 = a3;
  v28 = 0;
  Src = 0;
  if ( a1 && a2 && a1 != -668 && a3 )
  {
    if ( !a4 || a5 )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_S(1028, 70, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
      memset_0(v31, 0, 0xC6u);
      memset_0(v33, 0, 0xC8u);
      v13 = *a2;
      *(_BYTE *)(a1 + 668) = 5;
      *(_WORD *)(a1 + 669) = v13;
      *(_BYTE *)(a1 + 671) = *((_BYTE *)a2 + 2);
      v24 = a1 + 672;
      v22 = 4;
      v26 = 0;
      appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v22, &v24, a1 + 4763);
      if ( appended )
        goto LABEL_41;
      appended = Dhcpv6AppendOption((void *)(a1 + 456), 0x10u, 1u, &v22, &v24, a1 + 4763);
      if ( appended )
        goto LABEL_41;
      if ( !a4 )
        a6 = (void *)(a1 + 480);
      appended = Dhcpv6AppendOption(a6, 0x10u, 2u, &v22, &v24, a1 + 4763);
      if ( appended )
        goto LABEL_41;
      v30 = 2;
      if ( a4 )
      {
        appended = Dhcpv6AppendOption(a5, 0x30u, 0x19u, &v22, &v24, a1 + 4763);
        if ( appended )
          goto LABEL_41;
        v30 = 25;
      }
      else
      {
        v15 = *(_QWORD **)(a1 + 104);
        while ( v15 != (_QWORD *)(a1 + 104) )
        {
          v16 = v15;
          v15 = (_QWORD *)*v15;
          appended = Dhcpv6AppendOption(v16, 0xA8u, 3u, &v22, &v24, a1 + 4763);
          if ( appended )
            goto LABEL_41;
        }
        AddToArray(&v30, v14, &v25, 3);
      }
      if ( !*(_DWORD *)(a1 + 9032) )
      {
        appended = Dhcpv6AppendDefaultVendorClassOption(&v22, (u_short **)&v24, a1 + 4763);
        if ( appended )
          goto LABEL_41;
        v18 = *(void **)(a1 + 656);
        v30 = 16;
        if ( v18 )
        {
          appended = Dhcpv6AppendUserClassOption(v18, *(unsigned __int8 *)(a1 + 664), v17, &v22, &v24, a1 + 4763);
          if ( appended )
            goto LABEL_41;
          AddToArray(&v30, v19, &v25, 15);
        }
        memset_0(v32, 0, 0x104u);
        if ( !(unsigned int)Dhcpv6DynDnsGetDynDNSOption(v32, &v23, *(_QWORD *)(a1 + 648), *(_QWORD *)(a1 + 56)) )
        {
          appended = Dhcpv6AppendOption(v32, v23, 0x27u, &v22, &v24, a1 + 4763);
          if ( appended )
            goto LABEL_41;
          AddToArray(&v30, v20, &v25, 39);
        }
      }
      appended = Dhcpv6AppendSendOptions(
                   a1,
                   (_QWORD **)(a1 + 616),
                   *(_QWORD *)(a1 + 656),
                   *(_DWORD *)(a1 + 664),
                   &v24,
                   &v22,
                   a1 + 4763,
                   (__int64)&v30,
                   &v25,
                   (__int64)v33,
                   &v28,
                   v34,
                   &v26);
      if ( !appended
        && (*(_DWORD *)(a1 + 9032)
         || !v26
         || v24 + (unsigned __int64)v26 > a1 + 4763
         || (appended = Dhcpv6AppendOption(v34, v26, 0x11u, &v22, &v24, a1 + 4763)) == 0) )
      {
        *v29 = v22;
        return appended;
      }
      goto LABEL_41;
    }
    appended = 87;
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      v12 = 69;
LABEL_40:
      WPP_SF_D(1025, v12, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
LABEL_41:
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SD(
          1025,
          71,
          (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
          *(_QWORD *)(a1 + 56),
          appended);
    }
  }
  else
  {
    appended = 87;
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      v12 = 68;
      goto LABEL_40;
    }
  }
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v8, ErrorCreatingPacket, *(unsigned int *)(a1 + 48), appended);
  TraceLogErrorv6(a1, appended, 47);
  return appended;
}

```

## disassembly

```asm
0x1800027e0  mov     [rsp-8+arg_8], rbx
0x1800027e5  push    rbp
0x1800027e6  push    rsi
0x1800027e7  push    rdi
0x1800027e8  push    r12
0x1800027ea  push    r13
0x1800027ec  push    r14
0x1800027ee  push    r15
0x1800027f0  lea     rbp, [rsp-1260h]
0x1800027f8  mov     eax, 1360h
0x1800027fd  call    _alloca_probe
0x180002802  sub     rsp, rax
0x180002805  mov     rax, cs:__security_cookie
0x18000280c  xor     rax, rsp
0x18000280f  mov     [rbp+1290h+var_40], rax
0x180002816  mov     r13, [rbp+1290h+arg_20]
0x18000281d  xor     esi, esi
0x18000281f  mov     r12, [rbp+1290h+arg_28]
0x180002826  mov     rdi, rcx
0x180002829  mov     [rbp+1290h+var_1310], esi
0x18000282c  mov     ecx, 103h
0x180002831  mov     [rsp+1390h+var_131C], cx
0x180002836  mov     rax, r8
0x180002839  mov     [rbp+1290h+var_1300], rax
0x18000283d  mov     r14d, r9d
0x180002840  mov     [rbp+1290h+var_1304], esi
0x180002843  mov     r15, rdx
0x180002846  mov     [rbp+1290h+Src], esi
0x180002849  test    rdi, rdi
0x18000284c  jz      loc_180002BFD
0x180002852  test    rdx, rdx
0x180002855  jz      loc_180002BFD
0x18000285b  lea     rbx, [rdi+29Ch]
0x180002862  test    rbx, rbx
0x180002865  jz      loc_180002BFD
0x18000286b  test    rax, rax
0x18000286e  jz      loc_180002BFD
0x180002874  test    r9d, r9d
0x180002877  jz      short loc_18000289A
0x180002879  test    r13, r13
0x18000287c  jnz     short loc_18000289A
0x18000287e  lea     r9d, [r13+57h]
0x180002882  mov     ebx, r9d
0x180002885  test    byte ptr cs:xmmword_1800423E0, 2
0x18000288c  jz      loc_180002C4B
0x180002892  lea     edx, [rsi+45h]
0x180002895  jmp     loc_180002C13
0x18000289a  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800028a1  jz      short loc_1800028BD
0x1800028a3  mov     r9, [rdi+38h]
0x1800028a7  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800028ae  mov     edx, 46h ; 'F'
0x1800028b3  mov     ecx, 404h
0x1800028b8  call    WPP_SF_S
0x1800028bd  xor     edx, edx; Val
0x1800028bf  lea     rcx, [rbp+1290h+var_12EE]; void *
0x1800028c3  mov     r8d, 0C6h; Size
0x1800028c9  call    memset_0
0x1800028ce  xor     edx, edx; Val
0x1800028d0  lea     rcx, [rbp+1290h+var_1110]; void *
0x1800028d7  mov     r8d, 0C8h; Size
0x1800028dd  call    memset_0
0x1800028e2  movzx   eax, word ptr [r15]
0x1800028e6  lea     r9, [rsp+1390h+var_1320]
0x1800028eb  mov     ecx, 4
0x1800028f0  mov     byte ptr [rbx], 5
0x1800028f3  mov     [rbx+1], ax
0x1800028f7  mov     edx, ecx
0x1800028f9  mov     al, [r15+2]
0x1800028fd  mov     [rbx+3], al
0x180002900  lea     rax, [rbx+4]
0x180002904  mov     [rsp+1390h+var_1318], rax
0x180002909  lea     r8d, [rcx+4]
0x18000290d  lea     rax, [rsp+1390h+var_1318]
0x180002912  mov     [rsp+1390h+var_1320], ecx
0x180002916  mov     [rbp+1290h+var_130C], esi
0x180002919  lea     rcx, [rbp+1290h+Src]; Src
0x18000291d  lea     rsi, [rdi+129Bh]
0x180002924  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002929  mov     [rsp+1390h+var_1370], rax; __int64
0x18000292e  call    Dhcpv6AppendOption
0x180002933  mov     ebx, eax
0x180002935  test    eax, eax
0x180002937  jnz     loc_180002C24
0x18000293d  lea     r15d, [rax+10h]
0x180002941  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002946  lea     r8d, [rax+1]
0x18000294a  mov     edx, r15d
0x18000294d  lea     rax, [rsp+1390h+var_1318]
0x180002952  lea     rcx, [rdi+1C8h]; Src
0x180002959  mov     [rsp+1390h+var_1370], rax; __int64
0x18000295e  lea     r9, [rsp+1390h+var_1320]
0x180002963  call    Dhcpv6AppendOption
0x180002968  mov     ebx, eax
0x18000296a  test    eax, eax
0x18000296c  jnz     loc_180002C24
0x180002972  test    r14d, r14d
0x180002975  jnz     short loc_18000297E
0x180002977  lea     r12, [rdi+1E0h]
0x18000297e  lea     rax, [rsp+1390h+var_1318]
0x180002983  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002988  mov     r8d, 2
0x18000298e  mov     [rsp+1390h+var_1370], rax; __int64
0x180002993  mov     edx, r15d
0x180002996  lea     r9, [rsp+1390h+var_1320]
0x18000299b  mov     rcx, r12; Src
0x18000299e  call    Dhcpv6AppendOption
0x1800029a3  mov     ebx, eax
0x1800029a5  test    eax, eax
0x1800029a7  jnz     loc_180002C24
0x1800029ad  lea     eax, [rbx+2]
0x1800029b0  mov     [rbp+1290h+var_12F0], ax
0x1800029b4  test    r14d, r14d
0x1800029b7  jz      short loc_1800029F0
0x1800029b9  lea     rax, [rsp+1390h+var_1318]
0x1800029be  mov     [rsp+1390h+var_1368], rsi; __int64
0x1800029c3  lea     r14d, [rbx+19h]
0x1800029c7  mov     [rsp+1390h+var_1370], rax; __int64
0x1800029cc  mov     r8d, r14d
0x1800029cf  lea     edx, [rbx+30h]
0x1800029d2  lea     r9, [rsp+1390h+var_1320]
0x1800029d7  mov     rcx, r13; Src
0x1800029da  call    Dhcpv6AppendOption
0x1800029df  mov     ebx, eax
0x1800029e1  test    eax, eax
0x1800029e3  jnz     loc_180002C24
0x1800029e9  mov     [rbp+1290h+var_12F0], r14w
0x1800029ee  jmp     short loc_180002A4A
0x1800029f0  lea     r15, [rdi+68h]
0x1800029f4  mov     r12d, 3
0x1800029fa  mov     r14, [r15]
0x1800029fd  cmp     r14, r15
0x180002a00  jz      short loc_180002A34
0x180002a02  lea     rax, [rsp+1390h+var_1318]
0x180002a07  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002a0c  mov     rcx, r14; Src
0x180002a0f  mov     [rsp+1390h+var_1370], rax; __int64
0x180002a14  mov     r14, [r14]
0x180002a17  lea     r9, [rsp+1390h+var_1320]
0x180002a1c  mov     r8d, r12d
0x180002a1f  mov     edx, 0A8h
0x180002a24  call    Dhcpv6AppendOption
0x180002a29  mov     ebx, eax
0x180002a2b  test    eax, eax
0x180002a2d  jz      short loc_1800029FD
0x180002a2f  jmp     loc_180002C24
0x180002a34  mov     r9d, r12d
0x180002a37  lea     r8, [rbp+1290h+var_1310]
0x180002a3b  lea     rcx, [rbp+1290h+var_12F0]
0x180002a3f  call    AddToArray
0x180002a44  mov     r15d, 10h
0x180002a4a  cmp     dword ptr [rdi+2348h], 0
0x180002a51  jnz     loc_180002B30
0x180002a57  mov     r8, rsi
0x180002a5a  lea     rdx, [rsp+1390h+var_1318]
0x180002a5f  lea     rcx, [rsp+1390h+var_1320]
0x180002a64  call    Dhcpv6AppendDefaultVendorClassOption
0x180002a69  mov     ebx, eax
0x180002a6b  test    eax, eax
0x180002a6d  jnz     loc_180002C24
0x180002a73  mov     rcx, [rdi+290h]; Src
0x180002a7a  mov     [rbp+1290h+var_12F0], r15w
0x180002a7f  test    rcx, rcx
0x180002a82  jz      short loc_180002ABF
0x180002a84  movzx   edx, byte ptr [rdi+298h]
0x180002a8b  lea     rax, [rsp+1390h+var_1318]
0x180002a90  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002a95  lea     r9, [rsp+1390h+var_1320]
0x180002a9a  mov     [rsp+1390h+var_1370], rax; __int64
0x180002a9f  call    Dhcpv6AppendUserClassOption
0x180002aa4  mov     ebx, eax
0x180002aa6  test    eax, eax
0x180002aa8  jnz     loc_180002C24
0x180002aae  lea     r9d, [rax+0Fh]
0x180002ab2  lea     r8, [rbp+1290h+var_1310]
0x180002ab6  lea     rcx, [rbp+1290h+var_12F0]
0x180002aba  call    AddToArray
0x180002abf  xor     edx, edx; Val
0x180002ac1  lea     rcx, [rbp+1290h+var_1220]; void *
0x180002ac5  mov     r8d, 104h; Size
0x180002acb  call    memset_0
0x180002ad0  mov     r9, [rdi+38h]
0x180002ad4  lea     rdx, [rsp+1390h+var_131C]
0x180002ad9  mov     r8, [rdi+288h]
0x180002ae0  lea     rcx, [rbp+1290h+var_1220]
0x180002ae4  call    Dhcpv6DynDnsGetDynDNSOption
0x180002ae9  test    eax, eax
0x180002aeb  jnz     short loc_180002B30
0x180002aed  movzx   edx, [rsp+1390h+var_131C]
0x180002af2  lea     r14d, [rax+27h]
0x180002af6  lea     rax, [rsp+1390h+var_1318]
0x180002afb  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002b00  mov     r8d, r14d
0x180002b03  mov     [rsp+1390h+var_1370], rax; __int64
0x180002b08  lea     r9, [rsp+1390h+var_1320]
0x180002b0d  lea     rcx, [rbp+1290h+var_1220]; Src
0x180002b11  call    Dhcpv6AppendOption
0x180002b16  mov     ebx, eax
0x180002b18  test    eax, eax
0x180002b1a  jnz     loc_180002C24
0x180002b20  mov     r9d, r14d
0x180002b23  lea     r8, [rbp+1290h+var_1310]
0x180002b27  lea     rcx, [rbp+1290h+var_12F0]
0x180002b2b  call    AddToArray
0x180002b30  mov     r9d, [rdi+298h]
0x180002b37  lea     rax, [rbp+1290h+var_130C]
0x180002b3b  mov     r8, [rdi+290h]
0x180002b42  lea     rdx, [rdi+268h]
0x180002b49  mov     [rsp+1390h+var_1330], rax
0x180002b4e  mov     rcx, rdi
0x180002b51  lea     rax, [rbp+1290h+var_1040]
0x180002b58  mov     [rsp+1390h+var_1338], rax
0x180002b5d  lea     rax, [rbp+1290h+var_1304]
0x180002b61  mov     [rsp+1390h+var_1340], rax
0x180002b66  lea     rax, [rbp+1290h+var_1110]
0x180002b6d  mov     [rsp+1390h+var_1348], rax
0x180002b72  lea     rax, [rbp+1290h+var_1310]
0x180002b76  mov     [rsp+1390h+var_1350], rax
0x180002b7b  lea     rax, [rbp+1290h+var_12F0]
0x180002b7f  mov     [rsp+1390h+var_1358], rax
0x180002b84  lea     rax, [rsp+1390h+var_1320]
0x180002b89  mov     [rsp+1390h+var_1360], rsi
0x180002b8e  mov     [rsp+1390h+var_1368], rax
0x180002b93  lea     rax, [rsp+1390h+var_1318]
0x180002b98  mov     [rsp+1390h+var_1370], rax
0x180002b9d  call    Dhcpv6AppendSendOptions
0x180002ba2  mov     ebx, eax
0x180002ba4  test    eax, eax
0x180002ba6  jnz     short loc_180002C24
0x180002ba8  cmp     [rdi+2348h], eax
0x180002bae  jnz     short loc_180002BED
0x180002bb0  mov     edx, [rbp+1290h+var_130C]
0x180002bb3  test    edx, edx
0x180002bb5  jz      short loc_180002BED
0x180002bb7  mov     eax, edx
0x180002bb9  add     rax, [rsp+1390h+var_1318]
0x180002bbe  cmp     rax, rsi
0x180002bc1  ja      short loc_180002BED
0x180002bc3  lea     rax, [rsp+1390h+var_1318]
0x180002bc8  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002bcd  lea     r8d, [rbx+11h]
0x180002bd1  mov     [rsp+1390h+var_1370], rax; __int64
0x180002bd6  lea     r9, [rsp+1390h+var_1320]
0x180002bdb  lea     rcx, [rbp+1290h+var_1040]; Src
0x180002be2  call    Dhcpv6AppendOption
0x180002be7  mov     ebx, eax
0x180002be9  test    eax, eax
0x180002beb  jnz     short loc_180002C24
0x180002bed  mov     rcx, [rbp+1290h+var_1300]
0x180002bf1  mov     eax, [rsp+1390h+var_1320]
0x180002bf5  mov     [rcx], eax
0x180002bf7  test    ebx, ebx
0x180002bf9  jnz     short loc_180002C24
0x180002bfb  jmp     short loc_180002C77
0x180002bfd  mov     r9d, 57h ; 'W'
0x180002c03  mov     ebx, r9d
0x180002c06  test    byte ptr cs:xmmword_1800423E0, 2
0x180002c0d  jz      short loc_180002C4B
0x180002c0f  lea     edx, [r9-13h]
0x180002c13  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180002c1a  mov     ecx, 401h
0x180002c1f  call    WPP_SF_D
0x180002c24  test    byte ptr cs:xmmword_1800423E0, 2
0x180002c2b  jz      short loc_180002C4B
0x180002c2d  mov     r9, [rdi+38h]
0x180002c31  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180002c38  mov     edx, 47h ; 'G'
0x180002c3d  mov     dword ptr [rsp+1390h+var_1370], ebx
0x180002c41  mov     ecx, 401h
0x180002c46  call    WPP_SF_SD
0x180002c4b  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180002c52  jz      short loc_180002C67
0x180002c54  mov     r8d, [rdi+30h]
0x180002c58  lea     rdx, ErrorCreatingPacket
0x180002c5f  mov     r9d, ebx
0x180002c62  call    McTemplateU0qq_EtwEventWriteTransfer
0x180002c67  mov     r8d, 2Fh ; '/'
0x180002c6d  mov     edx, ebx
0x180002c6f  mov     rcx, rdi
0x180002c72  call    TraceLogErrorv6
0x180002c77  mov     eax, ebx
0x180002c79  mov     rcx, [rbp+1290h+var_40]
0x180002c80  xor     rcx, rsp; StackCookie
0x180002c83  call    __security_check_cookie
0x180002c88  mov     rbx, [rsp+1390h+arg_8]
0x180002c90  add     rsp, 1360h
0x180002c97  pop     r15
0x180002c99  pop     r14
0x180002c9b  pop     r13
0x180002c9d  pop     r12
0x180002c9f  pop     rdi
0x180002ca0  pop     rsi
0x180002ca1  pop     rbp
0x180002ca2  retn
```
