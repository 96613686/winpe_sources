# CreateDhcpv6Solicit

- ea: `0x1800200d8`
- end: `0x18002060a`
- name: `CreateDhcpv6Solicit`
- size: `1330`
- prototype: `__int64 __fastcall(_QWORD *, __int16 *, int *, int, void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x180014590`

## callees

- `0x180001d8c`
- `0x180002cac`
- `0x180002f80`
- `0x180003100`
- `0x180004b30`
- `0x180007564`
- `0x18000e1ec`
- `0x18000ed3c`
- `0x180017ffc`
- `0x180018740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800200d8`
- `0x180030920`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033900`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6Solicit(_QWORD *a1, __int16 *a2, int *a3, int a4, void *a5)
{
  __int64 v8; // rdi
  char v9; // al
  unsigned int appended; // ebx
  __int16 v11; // ax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  void *v22; // rcx
  __int64 v23; // rdx
  u_short v24; // r9
  int v26; // [rsp+70h] [rbp-1318h] BYREF
  unsigned int v27; // [rsp+74h] [rbp-1314h] BYREF
  unsigned __int16 v28; // [rsp+78h] [rbp-1310h] BYREF
  __int64 v29; // [rsp+80h] [rbp-1308h] BYREF
  unsigned int v30; // [rsp+88h] [rbp-1300h] BYREF
  int Src; // [rsp+8Ch] [rbp-12FCh] BYREF
  unsigned int v32[4]; // [rsp+90h] [rbp-12F8h] BYREF
  _BYTE v33[208]; // [rsp+A0h] [rbp-12E8h] BYREF
  _BYTE v34[272]; // [rsp+170h] [rbp-1218h] BYREF
  _BYTE v35[208]; // [rsp+280h] [rbp-1108h] BYREF
  _WORD v36[2048]; // [rsp+350h] [rbp-1038h] BYREF

  v27 = 0;
  v32[0] = 0;
  Src = 0;
  v28 = 259;
  v8 = (__int64)a1;
  v9 = xmmword_1800423E0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 62, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    v9 = xmmword_1800423E0;
  }
  if ( v8 && a2 && v8 != -668 && a3 && (!a4 || a5) )
  {
    if ( (v9 & 0x10) != 0 )
      WPP_SF_S(1028, 63, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(v8 + 56));
    memset_0(v33, 0, 0xC8u);
    memset_0(v35, 0, 0xC8u);
    v11 = *a2;
    *(_BYTE *)(v8 + 668) = 1;
    *(_WORD *)(v8 + 669) = v11;
    *(_BYTE *)(v8 + 671) = *((_BYTE *)a2 + 2);
    v29 = v8 + 672;
    v26 = 4;
    v30 = 0;
    appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v26, &v29, v8 + 4763);
    if ( appended )
      goto LABEL_39;
    AddToArray(v33, v12, &v27, 8);
    appended = Dhcpv6AppendOption((void *)(v8 + 456), 0x10u, 1u, &v26, &v29, v8 + 4763);
    if ( appended )
      goto LABEL_39;
    AddToArray(v33, v13, &v27, 1);
    if ( a4 )
    {
      appended = Dhcpv6AppendOption(a5, 0x30u, 0x19u, &v26, &v29, v8 + 4763);
      if ( appended )
        goto LABEL_39;
      v15 = 25;
    }
    else
    {
      v16 = DhcpAlloc(168);
      a1 = (_QWORD *)v16;
      if ( !v16 )
      {
        appended = 8;
        goto LABEL_39;
      }
      *(_DWORD *)(v16 + 32) = *(_DWORD *)(v8 + 136);
      v17 = (_QWORD *)(v8 + 104);
      v18 = *(_QWORD *)(v8 + 104);
      if ( *(_QWORD *)(v18 + 8) != v8 + 104 )
        __fastfail(3u);
      *a1 = v18;
      a1[1] = v17;
      *(_QWORD *)(v18 + 8) = a1;
      *v17 = a1;
      appended = Dhcpv6AppendOption(a1, 0xA8u, 3u, &v26, &v29, v8 + 4763);
      if ( appended )
        goto LABEL_39;
      v15 = 3;
    }
    AddToArray(v33, v14, &v27, v15);
    if ( !*(_DWORD *)(v8 + 9032) )
    {
      memset_0(v34, 0, 0x104u);
      if ( !(unsigned int)Dhcpv6DynDnsGetDynDNSOption(v34, &v28, *(_QWORD *)(v8 + 648), *(_QWORD *)(v8 + 56)) )
      {
        appended = Dhcpv6AppendOption(v34, v28, 0x27u, &v26, &v29, v8 + 4763);
        if ( appended )
          goto LABEL_39;
        AddToArray(v33, v19, &v27, 39);
      }
      appended = Dhcpv6AppendDefaultVendorClassOption(&v26, (u_short **)&v29, v8 + 4763);
      if ( appended )
        goto LABEL_39;
      AddToArray(v33, v20, &v27, 16);
      v22 = *(void **)(v8 + 656);
      if ( v22 )
      {
        appended = Dhcpv6AppendUserClassOption(v22, *(unsigned __int8 *)(v8 + 664), v21, &v26, &v29, v8 + 4763);
        if ( appended )
          goto LABEL_39;
        AddToArray(v33, v23, &v27, 15);
      }
    }
    if ( a4
      || (appended = Dhcpv6AppendSendOptions(
                       v8,
                       (_QWORD **)(v8 + 616),
                       *(_QWORD *)(v8 + 656),
                       *(_DWORD *)(v8 + 664),
                       &v29,
                       &v26,
                       v8 + 4763,
                       (__int64)v33,
                       &v27,
                       (__int64)v35,
                       v32,
                       v36,
                       &v30)) == 0
      && (*(_DWORD *)(v8 + 9032)
       || (unsigned int)IsPresentInArray(v33, 0)
       || !v30
       || v29 + (unsigned __int64)v30 > v8 + 4763
       || (appended = Dhcpv6AppendOption(v36, v30, v24, &v26, &v29, v8 + 4763)) == 0) )
    {
      *a3 = v26;
      goto LABEL_42;
    }
  }
  else
  {
    appended = 87;
  }
LABEL_39:
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(a1, ErrorCreatingPacket, *(unsigned int *)(v8 + 48), appended);
  TraceLogErrorv6(v8, appended, 50);
LABEL_42:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 64, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, appended);
  return appended;
}

```

## disassembly

```asm
0x1800200d8  mov     [rsp+arg_8], rbx
0x1800200dd  mov     [rsp+arg_18], rsi
0x1800200e2  push    rdi
0x1800200e3  push    r12
0x1800200e5  push    r13
0x1800200e7  push    r14
0x1800200e9  push    r15
0x1800200eb  mov     eax, 1360h
0x1800200f0  call    _alloca_probe
0x1800200f5  sub     rsp, rax
0x1800200f8  mov     rax, cs:__security_cookie
0x1800200ff  xor     rax, rsp
0x180020102  mov     [rsp+1388h+var_38], rax
0x18002010a  mov     r15, [rsp+1388h+arg_20]
0x180020112  xor     esi, esi
0x180020114  mov     eax, 103h
0x180020119  mov     [rsp+1388h+var_1314], esi
0x18002011d  mov     [rsp+1388h+var_12F8], esi
0x180020124  mov     r14d, r9d
0x180020127  mov     [rsp+1388h+Src], esi
0x18002012e  mov     r13, r8
0x180020131  mov     [rsp+1388h+var_1310], ax
0x180020136  mov     r12, rdx
0x180020139  mov     rdi, rcx
0x18002013c  mov     al, byte ptr cs:xmmword_1800423E0
0x180020142  test    al, 10h
0x180020144  jz      short loc_180020160
0x180020146  lea     edx, [rsi+3Eh]
0x180020149  mov     ecx, 404h
0x18002014e  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180020155  call    WPP_SF_
0x18002015a  mov     al, byte ptr cs:xmmword_1800423E0
0x180020160  test    rdi, rdi
0x180020163  jnz     short loc_18002016F
0x180020165  mov     ebx, 57h ; 'W'
0x18002016a  jmp     loc_18002058C
0x18002016f  test    r12, r12
0x180020172  jz      short loc_180020165
0x180020174  lea     rbx, [rdi+29Ch]
0x18002017b  test    rbx, rbx
0x18002017e  jz      short loc_180020165
0x180020180  test    r13, r13
0x180020183  jz      short loc_180020165
0x180020185  test    r14d, r14d
0x180020188  jz      short loc_18002018F
0x18002018a  test    r15, r15
0x18002018d  jz      short loc_180020165
0x18002018f  test    al, 10h
0x180020191  jz      short loc_1800201AD
0x180020193  mov     r9, [rdi+38h]
0x180020197  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18002019e  mov     edx, 3Fh ; '?'
0x1800201a3  mov     ecx, 404h
0x1800201a8  call    WPP_SF_S
0x1800201ad  mov     esi, 0C8h
0x1800201b2  lea     rcx, [rsp+1388h+var_12E8]; void *
0x1800201ba  mov     r8d, esi; Size
0x1800201bd  xor     edx, edx; Val
0x1800201bf  call    memset_0
0x1800201c4  mov     r8d, esi; Size
0x1800201c7  lea     rcx, [rsp+1388h+var_1108]; void *
0x1800201cf  xor     edx, edx; Val
0x1800201d1  call    memset_0
0x1800201d6  movzx   eax, word ptr [r12]
0x1800201db  lea     rsi, [rdi+129Bh]
0x1800201e2  mov     ecx, 4
0x1800201e7  mov     byte ptr [rbx], 1
0x1800201ea  mov     [rbx+1], ax
0x1800201ee  lea     r9, [rsp+1388h+var_1318]
0x1800201f3  mov     al, [r12+2]
0x1800201f8  mov     edx, ecx
0x1800201fa  mov     [rbx+3], al
0x1800201fd  lea     rax, [rbx+4]
0x180020201  lea     r12d, [rcx+4]
0x180020205  mov     [rsp+1388h+var_1308], rax
0x18002020d  lea     rax, [rsp+1388h+var_1308]
0x180020215  mov     [rsp+1388h+var_1318], ecx
0x180020219  mov     r8d, r12d
0x18002021c  mov     [rsp+1388h+var_1360], rsi; __int64
0x180020221  lea     rcx, [rsp+1388h+Src]; Src
0x180020229  mov     [rsp+1388h+var_1368], rax; __int64
0x18002022e  mov     [rsp+1388h+var_1300], 0
0x180020239  call    Dhcpv6AppendOption
0x18002023e  mov     ebx, eax
0x180020240  test    eax, eax
0x180020242  jnz     loc_18002058C
0x180020248  mov     r9d, r12d
0x18002024b  lea     r8, [rsp+1388h+var_1314]
0x180020250  lea     rcx, [rsp+1388h+var_12E8]
0x180020258  call    AddToArray
0x18002025d  lea     rax, [rsp+1388h+var_1308]
0x180020265  mov     [rsp+1388h+var_1360], rsi; __int64
0x18002026a  lea     edx, [rbx+10h]
0x18002026d  mov     [rsp+1388h+var_1368], rax; __int64
0x180020272  lea     r8d, [r12-7]
0x180020277  lea     rcx, [rdi+1C8h]; Src
0x18002027e  lea     r9, [rsp+1388h+var_1318]
0x180020283  call    Dhcpv6AppendOption
0x180020288  mov     ebx, eax
0x18002028a  test    eax, eax
0x18002028c  jnz     loc_18002058C
0x180020292  lea     r9d, [r12-7]
0x180020297  lea     r8, [rsp+1388h+var_1314]
0x18002029c  lea     rcx, [rsp+1388h+var_12E8]
0x1800202a4  call    AddToArray
0x1800202a9  test    r14d, r14d
0x1800202ac  jz      short loc_1800202E6
0x1800202ae  lea     rax, [rsp+1388h+var_1308]
0x1800202b6  mov     [rsp+1388h+var_1360], rsi; __int64
0x1800202bb  lea     r12d, [rbx+19h]
0x1800202bf  mov     [rsp+1388h+var_1368], rax; __int64
0x1800202c4  mov     r8d, r12d
0x1800202c7  lea     edx, [rbx+30h]
0x1800202ca  lea     r9, [rsp+1388h+var_1318]
0x1800202cf  mov     rcx, r15; Src
0x1800202d2  call    Dhcpv6AppendOption
0x1800202d7  mov     ebx, eax
0x1800202d9  test    eax, eax
0x1800202db  jnz     loc_18002058C
0x1800202e1  mov     r9d, r12d
0x1800202e4  jmp     short loc_18002035F
0x1800202e6  mov     ebx, 0A8h
0x1800202eb  mov     ecx, ebx
0x1800202ed  call    DhcpAlloc
0x1800202f2  mov     rcx, rax; Src
0x1800202f5  test    rax, rax
0x1800202f8  jnz     short loc_180020302
0x1800202fa  mov     ebx, r12d
0x1800202fd  jmp     loc_18002058C
0x180020302  mov     eax, [rdi+88h]
0x180020308  mov     [rcx+20h], eax
0x18002030b  lea     rax, [rdi+68h]
0x18002030f  mov     rdx, [rax]
0x180020312  cmp     [rdx+8], rax
0x180020316  jz      short loc_18002031F
0x180020318  mov     ecx, 3
0x18002031d  int     29h; Win8: RtlFailFast(ecx)
0x18002031f  mov     [rcx], rdx
0x180020322  lea     r9, [rsp+1388h+var_1318]
0x180020327  mov     [rcx+8], rax
0x18002032b  mov     r8d, 3
0x180020331  mov     [rdx+8], rcx
0x180020335  mov     edx, ebx
0x180020337  mov     [rax], rcx
0x18002033a  lea     rax, [rsp+1388h+var_1308]
0x180020342  mov     [rsp+1388h+var_1360], rsi; __int64
0x180020347  mov     [rsp+1388h+var_1368], rax; __int64
0x18002034c  call    Dhcpv6AppendOption
0x180020351  mov     ebx, eax
0x180020353  test    eax, eax
0x180020355  jnz     loc_18002058C
0x18002035b  lea     r9d, [rax+3]
0x18002035f  lea     r8, [rsp+1388h+var_1314]
0x180020364  lea     rcx, [rsp+1388h+var_12E8]
0x18002036c  call    AddToArray
0x180020371  cmp     dword ptr [rdi+2348h], 0
0x180020378  jnz     loc_180020487
0x18002037e  xor     edx, edx; Val
0x180020380  lea     rcx, [rsp+1388h+var_1218]; void *
0x180020388  mov     r8d, 104h; Size
0x18002038e  call    memset_0
0x180020393  mov     r9, [rdi+38h]
0x180020397  lea     rdx, [rsp+1388h+var_1310]
0x18002039c  mov     r8, [rdi+288h]
0x1800203a3  lea     rcx, [rsp+1388h+var_1218]
0x1800203ab  call    Dhcpv6DynDnsGetDynDNSOption
0x1800203b0  test    eax, eax
0x1800203b2  jnz     short loc_180020403
0x1800203b4  movzx   edx, [rsp+1388h+var_1310]
0x1800203b9  lea     r15d, [rax+27h]
0x1800203bd  lea     rax, [rsp+1388h+var_1308]
0x1800203c5  mov     [rsp+1388h+var_1360], rsi; __int64
0x1800203ca  mov     r8d, r15d
0x1800203cd  mov     [rsp+1388h+var_1368], rax; __int64
0x1800203d2  lea     r9, [rsp+1388h+var_1318]
0x1800203d7  lea     rcx, [rsp+1388h+var_1218]; Src
0x1800203df  call    Dhcpv6AppendOption
0x1800203e4  mov     ebx, eax
0x1800203e6  test    eax, eax
0x1800203e8  jnz     loc_18002058C
0x1800203ee  mov     r9d, r15d
0x1800203f1  lea     r8, [rsp+1388h+var_1314]
0x1800203f6  lea     rcx, [rsp+1388h+var_12E8]
0x1800203fe  call    AddToArray
0x180020403  mov     r8, rsi
0x180020406  lea     rdx, [rsp+1388h+var_1308]
0x18002040e  lea     rcx, [rsp+1388h+var_1318]
0x180020413  call    Dhcpv6AppendDefaultVendorClassOption
0x180020418  mov     ebx, eax
0x18002041a  test    eax, eax
0x18002041c  jnz     loc_18002058C
0x180020422  lea     r9d, [rax+10h]
0x180020426  lea     r8, [rsp+1388h+var_1314]
0x18002042b  lea     rcx, [rsp+1388h+var_12E8]
0x180020433  call    AddToArray
0x180020438  mov     rcx, [rdi+290h]; Src
0x18002043f  test    rcx, rcx
0x180020442  jz      short loc_180020487
0x180020444  movzx   edx, byte ptr [rdi+298h]
0x18002044b  lea     rax, [rsp+1388h+var_1308]
0x180020453  mov     [rsp+1388h+var_1360], rsi; __int64
0x180020458  lea     r9, [rsp+1388h+var_1318]
0x18002045d  mov     [rsp+1388h+var_1368], rax; __int64
0x180020462  call    Dhcpv6AppendUserClassOption
0x180020467  mov     ebx, eax
0x180020469  test    eax, eax
0x18002046b  jnz     loc_18002058C
0x180020471  lea     r9d, [rax+0Fh]
0x180020475  lea     r8, [rsp+1388h+var_1314]
0x18002047a  lea     rcx, [rsp+1388h+var_12E8]
0x180020482  call    AddToArray
0x180020487  test    r14d, r14d
0x18002048a  jnz     loc_180020580
0x180020490  mov     r9d, [rdi+298h]
0x180020497  lea     rax, [rsp+1388h+var_1300]
0x18002049f  mov     r8, [rdi+290h]
0x1800204a6  lea     rdx, [rdi+268h]
0x1800204ad  mov     [rsp+1388h+var_1328], rax
0x1800204b2  mov     rcx, rdi
0x1800204b5  lea     rax, [rsp+1388h+var_1038]
0x1800204bd  mov     [rsp+1388h+var_1330], rax
0x1800204c2  lea     rax, [rsp+1388h+var_12F8]
0x1800204ca  mov     [rsp+1388h+var_1338], rax
0x1800204cf  lea     rax, [rsp+1388h+var_1108]
0x1800204d7  mov     [rsp+1388h+var_1340], rax
0x1800204dc  lea     rax, [rsp+1388h+var_1314]
0x1800204e1  mov     [rsp+1388h+var_1348], rax
0x1800204e6  lea     rax, [rsp+1388h+var_12E8]
0x1800204ee  mov     [rsp+1388h+var_1350], rax
0x1800204f3  lea     rax, [rsp+1388h+var_1318]
0x1800204f8  mov     [rsp+1388h+var_1358], rsi
0x1800204fd  mov     [rsp+1388h+var_1360], rax
0x180020502  lea     rax, [rsp+1388h+var_1308]
0x18002050a  mov     [rsp+1388h+var_1368], rax
0x18002050f  call    Dhcpv6AppendSendOptions
0x180020514  mov     ebx, eax
0x180020516  test    eax, eax
0x180020518  jnz     short loc_18002058C
0x18002051a  cmp     [rdi+2348h], eax
0x180020520  jnz     short loc_180020580
0x180020522  xor     edx, edx
0x180020524  lea     r9d, [r14+11h]
0x180020528  lea     rcx, [rsp+1388h+var_12E8]
0x180020530  call    IsPresentInArray
0x180020535  test    eax, eax
0x180020537  jnz     short loc_180020580
0x180020539  mov     edx, [rsp+1388h+var_1300]
0x180020540  test    edx, edx
0x180020542  jz      short loc_180020580
0x180020544  mov     eax, edx
0x180020546  add     rax, [rsp+1388h+var_1308]
0x18002054e  cmp     rax, rsi
0x180020551  ja      short loc_180020580
0x180020553  mov     r8d, r9d
0x180020556  mov     [rsp+1388h+var_1360], rsi; __int64
0x18002055b  lea     rax, [rsp+1388h+var_1308]
0x180020563  lea     r9, [rsp+1388h+var_1318]
0x180020568  mov     [rsp+1388h+var_1368], rax; __int64
0x18002056d  lea     rcx, [rsp+1388h+var_1038]; Src
0x180020575  call    Dhcpv6AppendOption
0x18002057a  mov     ebx, eax
0x18002057c  test    eax, eax
0x18002057e  jnz     short loc_18002058C
0x180020580  mov     eax, [rsp+1388h+var_1318]
0x180020584  mov     [r13+0], eax
0x180020588  test    ebx, ebx
0x18002058a  jz      short loc_1800205B8
0x18002058c  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180020593  jz      short loc_1800205A8
0x180020595  mov     r8d, [rdi+30h]
0x180020599  lea     rdx, ErrorCreatingPacket
0x1800205a0  mov     r9d, ebx
0x1800205a3  call    McTemplateU0qq_EtwEventWriteTransfer
0x1800205a8  mov     r8d, 32h ; '2'
0x1800205ae  mov     edx, ebx
0x1800205b0  mov     rcx, rdi
0x1800205b3  call    TraceLogErrorv6
0x1800205b8  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800205bf  jz      short loc_1800205DA
0x1800205c1  mov     edx, 40h ; '@'
0x1800205c6  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800205cd  mov     ecx, 404h
0x1800205d2  mov     r9d, ebx
0x1800205d5  call    WPP_SF_D
0x1800205da  mov     eax, ebx
0x1800205dc  mov     rcx, [rsp+1388h+var_38]
0x1800205e4  xor     rcx, rsp; StackCookie
0x1800205e7  call    __security_check_cookie
0x1800205ec  lea     r11, [rsp+1388h+var_28]
0x1800205f4  mov     rbx, [r11+38h]
0x1800205f8  mov     rsi, [r11+48h]
0x1800205fc  mov     rsp, r11
0x1800205ff  pop     r15
0x180020601  pop     r14
0x180020603  pop     r13
0x180020605  pop     r12
0x180020607  pop     rdi
0x180020608  retn
```
