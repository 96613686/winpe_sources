# CreateDhcpv6Request

- ea: `0x180002328`
- end: `0x1800027da`
- name: `CreateDhcpv6Request`
- size: `1202`
- prototype: `__int64 __fastcall(__int64, __int16 *, int *, int, void *, void *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x180014590`

## callees

- `0x180001d8c`
- `0x180002328`
- `0x180002cac`
- `0x180002f80`
- `0x180003100`
- `0x180004b30`
- `0x18000e1ec`
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
__int64 __fastcall CreateDhcpv6Request(__int64 a1, __int16 *a2, int *a3, int a4, void *a5, void *a6)
{
  void *v6; // r15
  __int64 v8; // rcx
  unsigned int appended; // ebx
  __int16 v12; // ax
  __int64 v13; // rdx
  _QWORD *v14; // r14
  void *v15; // rcx
  __int64 v16; // r8
  void *v17; // rcx
  __int64 v18; // rdx
  u_short v19; // r9
  int v21; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v22; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v24; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v25; // [rsp+84h] [rbp-7Ch] BYREF
  int Src; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v27; // [rsp+8Ch] [rbp-74h] BYREF
  int *v28; // [rsp+90h] [rbp-70h]
  __int16 v29; // [rsp+A0h] [rbp-60h] BYREF
  char v30[206]; // [rsp+A2h] [rbp-5Eh] BYREF
  _BYTE v31[272]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v32[208]; // [rsp+280h] [rbp+180h] BYREF
  _WORD v33[2048]; // [rsp+350h] [rbp+250h] BYREF

  v6 = a6;
  v24 = 0;
  v8 = 259;
  v22 = 259;
  v28 = a3;
  v27 = 0;
  Src = 0;
  if ( a1 && a2 && a1 != -668 && a3 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 66, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
    if ( a4 && (!a5 || !a6) )
    {
      appended = 87;
      goto LABEL_40;
    }
    memset_0(v30, 0, 0xC6u);
    memset_0(v32, 0, 0xC8u);
    v12 = *a2;
    *(_BYTE *)(a1 + 668) = 3;
    *(_WORD *)(a1 + 669) = v12;
    *(_BYTE *)(a1 + 671) = *((_BYTE *)a2 + 2);
    v23 = a1 + 672;
    v21 = 4;
    v25 = 0;
    appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v21, &v23, a1 + 4763);
    if ( appended )
      goto LABEL_40;
    appended = Dhcpv6AppendOption((void *)(a1 + 456), 0x10u, 1u, &v21, &v23, a1 + 4763);
    if ( appended )
      goto LABEL_40;
    if ( !a4 )
      v6 = (void *)(a1 + 480);
    appended = Dhcpv6AppendOption(v6, 0x10u, 2u, &v21, &v23, a1 + 4763);
    if ( appended )
      goto LABEL_40;
    v29 = 2;
    if ( a4 )
    {
      appended = Dhcpv6AppendOption(a5, 0x30u, 0x19u, &v21, &v23, a1 + 4763);
      if ( appended )
        goto LABEL_40;
      v29 = 25;
    }
    else
    {
      v14 = *(_QWORD **)(a1 + 104);
      while ( v14 != (_QWORD *)(a1 + 104) )
      {
        v15 = v14;
        v14 = (_QWORD *)*v14;
        appended = Dhcpv6AppendOption(v15, 0xA8u, 3u, &v21, &v23, a1 + 4763);
        if ( appended )
          goto LABEL_40;
      }
      AddToArray(&v29, v13, &v24, 3);
    }
    if ( !*(_DWORD *)(a1 + 9032) )
    {
      memset_0(v31, 0, 0x104u);
      if ( !(unsigned int)Dhcpv6DynDnsGetDynDNSOption(v31, &v22, *(_QWORD *)(a1 + 648), *(_QWORD *)(a1 + 56)) )
      {
        appended = Dhcpv6AppendOption(v31, v22, 0x27u, &v21, &v23, a1 + 4763);
        if ( appended )
          goto LABEL_40;
      }
      appended = Dhcpv6AppendDefaultVendorClassOption(&v21, (u_short **)&v23, a1 + 4763);
      if ( appended )
        goto LABEL_40;
      v17 = *(void **)(a1 + 656);
      v29 = 16;
      if ( v17 )
      {
        appended = Dhcpv6AppendUserClassOption(v17, *(unsigned __int8 *)(a1 + 664), v16, &v21, &v23, a1 + 4763);
        if ( !appended )
        {
          AddToArray(&v29, v18, &v24, 15);
          goto LABEL_31;
        }
LABEL_40:
        if ( (xmmword_1800423E0 & 2) != 0 )
          WPP_SF_SD(
            1025,
            67,
            (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
            *(_QWORD *)(a1 + 56),
            appended);
        goto LABEL_42;
      }
    }
LABEL_31:
    appended = Dhcpv6AppendSendOptions(
                 a1,
                 (_QWORD **)(a1 + 616),
                 *(_QWORD *)(a1 + 656),
                 *(_DWORD *)(a1 + 664),
                 &v23,
                 &v21,
                 a1 + 4763,
                 (__int64)&v29,
                 &v24,
                 (__int64)v32,
                 &v27,
                 v33,
                 &v25);
    if ( !appended
      && (*(_DWORD *)(a1 + 9032)
       || (unsigned int)IsPresentInArray(&v29, 0)
       || !v25
       || v23 + (unsigned __int64)v25 > a1 + 4763
       || (appended = Dhcpv6AppendOption(v33, v25, v19, &v21, &v23, a1 + 4763)) == 0) )
    {
      *v28 = v21;
      return appended;
    }
    goto LABEL_40;
  }
  appended = 87;
  if ( (xmmword_1800423E0 & 2) != 0 )
  {
    WPP_SF_D(1025, 65, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
    goto LABEL_40;
  }
LABEL_42:
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v8, ErrorCreatingPacket, *(unsigned int *)(a1 + 48), appended);
  TraceLogErrorv6(a1, appended, 48);
  return appended;
}

```

## disassembly

```asm
0x180002328  mov     [rsp-8+arg_8], rbx
0x18000232d  push    rbp
0x18000232e  push    rsi
0x18000232f  push    rdi
0x180002330  push    r12
0x180002332  push    r13
0x180002334  push    r14
0x180002336  push    r15
0x180002338  lea     rbp, [rsp-1260h]
0x180002340  mov     eax, 1360h
0x180002345  call    _alloca_probe
0x18000234a  sub     rsp, rax
0x18000234d  mov     rax, cs:__security_cookie
0x180002354  xor     rax, rsp
0x180002357  mov     [rbp+1290h+var_40], rax
0x18000235e  mov     r13, [rbp+1290h+arg_20]
0x180002365  xor     esi, esi
0x180002367  mov     r15, [rbp+1290h+arg_28]
0x18000236e  mov     rdi, rcx
0x180002371  mov     [rbp+1290h+var_1310], esi
0x180002374  mov     ecx, 103h
0x180002379  mov     [rsp+1390h+var_131C], cx
0x18000237e  mov     rax, r8
0x180002381  mov     [rbp+1290h+var_1300], rax
0x180002385  mov     r14d, r9d
0x180002388  mov     [rbp+1290h+var_1304], esi
0x18000238b  mov     r12, rdx
0x18000238e  mov     [rbp+1290h+Src], esi
0x180002391  test    rdi, rdi
0x180002394  jz      loc_180002735
0x18000239a  test    rdx, rdx
0x18000239d  jz      loc_180002735
0x1800023a3  lea     rbx, [rdi+29Ch]
0x1800023aa  test    rbx, rbx
0x1800023ad  jz      loc_180002735
0x1800023b3  test    rax, rax
0x1800023b6  jz      loc_180002735
0x1800023bc  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800023c3  jz      short loc_1800023DD
0x1800023c5  mov     r9, [rdi+38h]
0x1800023c9  lea     edx, [rsi+42h]
0x1800023cc  mov     ecx, 404h
0x1800023d1  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800023d8  call    WPP_SF_S
0x1800023dd  test    r14d, r14d
0x1800023e0  jz      short loc_1800023F6
0x1800023e2  test    r13, r13
0x1800023e5  jnz     short loc_1800023F1
0x1800023e7  mov     ebx, 57h ; 'W'
0x1800023ec  jmp     loc_18000275A
0x1800023f1  test    r15, r15
0x1800023f4  jz      short loc_1800023E7
0x1800023f6  xor     edx, edx; Val
0x1800023f8  lea     rcx, [rbp+1290h+var_12EE]; void *
0x1800023fc  mov     r8d, 0C6h; Size
0x180002402  call    memset_0
0x180002407  xor     edx, edx; Val
0x180002409  lea     rcx, [rbp+1290h+var_1110]; void *
0x180002410  mov     r8d, 0C8h; Size
0x180002416  call    memset_0
0x18000241b  movzx   eax, word ptr [r12]
0x180002420  lea     r9, [rsp+1390h+var_1320]
0x180002425  mov     ecx, 4
0x18000242a  mov     byte ptr [rbx], 3
0x18000242d  mov     [rbx+1], ax
0x180002431  mov     edx, ecx
0x180002433  mov     al, [r12+2]
0x180002438  mov     [rbx+3], al
0x18000243b  lea     rax, [rbx+4]
0x18000243f  mov     [rsp+1390h+var_1318], rax
0x180002444  lea     r8d, [rcx+4]
0x180002448  lea     rax, [rsp+1390h+var_1318]
0x18000244d  mov     [rsp+1390h+var_1320], ecx
0x180002451  mov     [rbp+1290h+var_130C], esi
0x180002454  lea     rcx, [rbp+1290h+Src]; Src
0x180002458  lea     rsi, [rdi+129Bh]
0x18000245f  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002464  mov     [rsp+1390h+var_1370], rax; __int64
0x180002469  call    Dhcpv6AppendOption
0x18000246e  mov     ebx, eax
0x180002470  test    eax, eax
0x180002472  jnz     loc_18000275A
0x180002478  lea     r12d, [rax+10h]
0x18000247c  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002481  lea     r8d, [rax+1]
0x180002485  mov     edx, r12d
0x180002488  lea     rax, [rsp+1390h+var_1318]
0x18000248d  lea     rcx, [rdi+1C8h]; Src
0x180002494  mov     [rsp+1390h+var_1370], rax; __int64
0x180002499  lea     r9, [rsp+1390h+var_1320]
0x18000249e  call    Dhcpv6AppendOption
0x1800024a3  mov     ebx, eax
0x1800024a5  test    eax, eax
0x1800024a7  jnz     loc_18000275A
0x1800024ad  test    r14d, r14d
0x1800024b0  jnz     short loc_1800024B9
0x1800024b2  lea     r15, [rdi+1E0h]
0x1800024b9  lea     rax, [rsp+1390h+var_1318]
0x1800024be  mov     [rsp+1390h+var_1368], rsi; __int64
0x1800024c3  mov     r8d, 2
0x1800024c9  mov     [rsp+1390h+var_1370], rax; __int64
0x1800024ce  mov     edx, r12d
0x1800024d1  lea     r9, [rsp+1390h+var_1320]
0x1800024d6  mov     rcx, r15; Src
0x1800024d9  call    Dhcpv6AppendOption
0x1800024de  mov     ebx, eax
0x1800024e0  test    eax, eax
0x1800024e2  jnz     loc_18000275A
0x1800024e8  lea     eax, [rbx+2]
0x1800024eb  mov     [rbp+1290h+var_12F0], ax
0x1800024ef  test    r14d, r14d
0x1800024f2  jz      short loc_18000252B
0x1800024f4  lea     rax, [rsp+1390h+var_1318]
0x1800024f9  mov     [rsp+1390h+var_1368], rsi; __int64
0x1800024fe  lea     r14d, [rbx+19h]
0x180002502  mov     [rsp+1390h+var_1370], rax; __int64
0x180002507  mov     r8d, r14d
0x18000250a  lea     edx, [rbx+30h]
0x18000250d  lea     r9, [rsp+1390h+var_1320]
0x180002512  mov     rcx, r13; Src
0x180002515  call    Dhcpv6AppendOption
0x18000251a  mov     ebx, eax
0x18000251c  test    eax, eax
0x18000251e  jnz     loc_18000275A
0x180002524  mov     [rbp+1290h+var_12F0], r14w
0x180002529  jmp     short loc_18000257F
0x18000252b  lea     r15, [rdi+68h]
0x18000252f  mov     r13d, 3
0x180002535  mov     r14, [r15]
0x180002538  cmp     r14, r15
0x18000253b  jz      short loc_18000256F
0x18000253d  lea     rax, [rsp+1390h+var_1318]
0x180002542  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002547  mov     rcx, r14; Src
0x18000254a  mov     [rsp+1390h+var_1370], rax; __int64
0x18000254f  mov     r14, [r14]
0x180002552  lea     r9, [rsp+1390h+var_1320]
0x180002557  mov     r8d, r13d
0x18000255a  mov     edx, 0A8h
0x18000255f  call    Dhcpv6AppendOption
0x180002564  mov     ebx, eax
0x180002566  test    eax, eax
0x180002568  jz      short loc_180002538
0x18000256a  jmp     loc_18000275A
0x18000256f  mov     r9d, r13d
0x180002572  lea     r8, [rbp+1290h+var_1310]
0x180002576  lea     rcx, [rbp+1290h+var_12F0]
0x18000257a  call    AddToArray
0x18000257f  cmp     dword ptr [rdi+2348h], 0
0x180002586  jnz     loc_180002652
0x18000258c  xor     edx, edx; Val
0x18000258e  lea     rcx, [rbp+1290h+var_1220]; void *
0x180002592  mov     r8d, 104h; Size
0x180002598  call    memset_0
0x18000259d  mov     r9, [rdi+38h]
0x1800025a1  lea     rdx, [rsp+1390h+var_131C]
0x1800025a6  mov     r8, [rdi+288h]
0x1800025ad  lea     rcx, [rbp+1290h+var_1220]
0x1800025b1  call    Dhcpv6DynDnsGetDynDNSOption
0x1800025b6  test    eax, eax
0x1800025b8  jnz     short loc_1800025EA
0x1800025ba  movzx   edx, [rsp+1390h+var_131C]
0x1800025bf  lea     r8d, [rax+27h]
0x1800025c3  lea     rax, [rsp+1390h+var_1318]
0x1800025c8  mov     [rsp+1390h+var_1368], rsi; __int64
0x1800025cd  lea     r9, [rsp+1390h+var_1320]
0x1800025d2  mov     [rsp+1390h+var_1370], rax; __int64
0x1800025d7  lea     rcx, [rbp+1290h+var_1220]; Src
0x1800025db  call    Dhcpv6AppendOption
0x1800025e0  mov     ebx, eax
0x1800025e2  test    eax, eax
0x1800025e4  jnz     loc_18000275A
0x1800025ea  mov     r8, rsi
0x1800025ed  lea     rdx, [rsp+1390h+var_1318]
0x1800025f2  lea     rcx, [rsp+1390h+var_1320]
0x1800025f7  call    Dhcpv6AppendDefaultVendorClassOption
0x1800025fc  mov     ebx, eax
0x1800025fe  test    eax, eax
0x180002600  jnz     loc_18000275A
0x180002606  mov     rcx, [rdi+290h]; Src
0x18000260d  mov     [rbp+1290h+var_12F0], r12w
0x180002612  test    rcx, rcx
0x180002615  jz      short loc_180002652
0x180002617  movzx   edx, byte ptr [rdi+298h]
0x18000261e  lea     rax, [rsp+1390h+var_1318]
0x180002623  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002628  lea     r9, [rsp+1390h+var_1320]
0x18000262d  mov     [rsp+1390h+var_1370], rax; __int64
0x180002632  call    Dhcpv6AppendUserClassOption
0x180002637  mov     ebx, eax
0x180002639  test    eax, eax
0x18000263b  jnz     loc_18000275A
0x180002641  lea     r9d, [rax+0Fh]
0x180002645  lea     r8, [rbp+1290h+var_1310]
0x180002649  lea     rcx, [rbp+1290h+var_12F0]
0x18000264d  call    AddToArray
0x180002652  mov     r9d, [rdi+298h]
0x180002659  lea     rax, [rbp+1290h+var_130C]
0x18000265d  mov     r8, [rdi+290h]
0x180002664  lea     rdx, [rdi+268h]
0x18000266b  mov     [rsp+1390h+var_1330], rax
0x180002670  mov     rcx, rdi
0x180002673  lea     rax, [rbp+1290h+var_1040]
0x18000267a  mov     [rsp+1390h+var_1338], rax
0x18000267f  lea     rax, [rbp+1290h+var_1304]
0x180002683  mov     [rsp+1390h+var_1340], rax
0x180002688  lea     rax, [rbp+1290h+var_1110]
0x18000268f  mov     [rsp+1390h+var_1348], rax
0x180002694  lea     rax, [rbp+1290h+var_1310]
0x180002698  mov     [rsp+1390h+var_1350], rax
0x18000269d  lea     rax, [rbp+1290h+var_12F0]
0x1800026a1  mov     [rsp+1390h+var_1358], rax
0x1800026a6  lea     rax, [rsp+1390h+var_1320]
0x1800026ab  mov     [rsp+1390h+var_1360], rsi
0x1800026b0  mov     [rsp+1390h+var_1368], rax
0x1800026b5  lea     rax, [rsp+1390h+var_1318]
0x1800026ba  mov     [rsp+1390h+var_1370], rax
0x1800026bf  call    Dhcpv6AppendSendOptions
0x1800026c4  mov     ebx, eax
0x1800026c6  test    eax, eax
0x1800026c8  jnz     loc_18000275A
0x1800026ce  cmp     [rdi+2348h], eax
0x1800026d4  jnz     short loc_180002725
0x1800026d6  xor     edx, edx
0x1800026d8  lea     r9d, [rax+11h]
0x1800026dc  lea     rcx, [rbp+1290h+var_12F0]
0x1800026e0  call    IsPresentInArray
0x1800026e5  test    eax, eax
0x1800026e7  jnz     short loc_180002725
0x1800026e9  mov     edx, [rbp+1290h+var_130C]
0x1800026ec  test    edx, edx
0x1800026ee  jz      short loc_180002725
0x1800026f0  mov     eax, edx
0x1800026f2  add     rax, [rsp+1390h+var_1318]
0x1800026f7  cmp     rax, rsi
0x1800026fa  ja      short loc_180002725
0x1800026fc  mov     r8d, r9d
0x1800026ff  mov     [rsp+1390h+var_1368], rsi; __int64
0x180002704  lea     rax, [rsp+1390h+var_1318]
0x180002709  lea     r9, [rsp+1390h+var_1320]
0x18000270e  mov     [rsp+1390h+var_1370], rax; __int64
0x180002713  lea     rcx, [rbp+1290h+var_1040]; Src
0x18000271a  call    Dhcpv6AppendOption
0x18000271f  mov     ebx, eax
0x180002721  test    eax, eax
0x180002723  jnz     short loc_18000275A
0x180002725  mov     rcx, [rbp+1290h+var_1300]
0x180002729  mov     eax, [rsp+1390h+var_1320]
0x18000272d  mov     [rcx], eax
0x18000272f  test    ebx, ebx
0x180002731  jnz     short loc_18000275A
0x180002733  jmp     short loc_1800027AD
0x180002735  mov     ebx, 57h ; 'W'
0x18000273a  test    byte ptr cs:xmmword_1800423E0, 2
0x180002741  jz      short loc_180002781
0x180002743  lea     edx, [rbx-16h]
0x180002746  mov     ecx, 401h
0x18000274b  mov     r9d, ebx
0x18000274e  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180002755  call    WPP_SF_D
0x18000275a  test    byte ptr cs:xmmword_1800423E0, 2
0x180002761  jz      short loc_180002781
0x180002763  mov     r9, [rdi+38h]
0x180002767  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18000276e  mov     edx, 43h ; 'C'
0x180002773  mov     dword ptr [rsp+1390h+var_1370], ebx
0x180002777  mov     ecx, 401h
0x18000277c  call    WPP_SF_SD
0x180002781  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180002788  jz      short loc_18000279D
0x18000278a  mov     r8d, [rdi+30h]
0x18000278e  lea     rdx, ErrorCreatingPacket
0x180002795  mov     r9d, ebx
0x180002798  call    McTemplateU0qq_EtwEventWriteTransfer
0x18000279d  mov     r8d, 30h ; '0'
0x1800027a3  mov     edx, ebx
0x1800027a5  mov     rcx, rdi
0x1800027a8  call    TraceLogErrorv6
0x1800027ad  mov     eax, ebx
0x1800027af  mov     rcx, [rbp+1290h+var_40]
0x1800027b6  xor     rcx, rsp; StackCookie
0x1800027b9  call    __security_check_cookie
0x1800027be  mov     rbx, [rsp+1390h+arg_8]
0x1800027c6  add     rsp, 1360h
0x1800027cd  pop     r15
0x1800027cf  pop     r14
0x1800027d1  pop     r13
0x1800027d3  pop     r12
0x1800027d5  pop     rdi
0x1800027d6  pop     rsi
0x1800027d7  pop     rbp
0x1800027d8  retn
```
