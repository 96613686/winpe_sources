# LcpThisLayerUp

- ea: `0x1800078e0`
- end: `0x180008040`
- name: `LcpThisLayerUp`
- size: `1888`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800078e0`
- `0x180011038`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180007aba`: `PPP Multilink`
- `0x180007ae6`: `	Recv Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x`
- `0x180007e14`: `	Send Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x`

## pseudocode

```c
__int64 __fastcall LcpThisLayerUp(_QWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // r13
  int v4; // ecx
  int v5; // eax
  int v6; // esi
  int v7; // edx
  int v8; // edx
  const char *v9; // rbx
  const char *v10; // rcx
  const char *v11; // rax
  const char *v12; // r12
  const char *v13; // r9
  const char *v14; // r8
  int v15; // r11d
  int v16; // edx
  int v17; // r10d
  int v18; // ecx
  int v19; // r9d
  __int64 v20; // r8
  int v21; // eax
  int v22; // r8d
  int v23; // edx
  int v24; // r15d
  int v25; // r14d
  const char *v26; // rcx
  const char *v27; // rax
  int v28; // edx
  int v29; // ecx
  int v30; // ebx
  int v31; // r11d
  int v32; // r10d
  __int64 v33; // r8
  unsigned int v34; // edx
  int v35; // ecx
  unsigned int v36; // edx
  __int64 v37; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+30h] [rbp-D0h]
  __int64 v40; // [rsp+38h] [rbp-C8h]
  __int64 v41; // [rsp+40h] [rbp-C0h]
  __int64 v42; // [rsp+48h] [rbp-B8h]
  __int64 v43; // [rsp+50h] [rbp-B0h]
  __int64 v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h]
  __int128 v46; // [rsp+78h] [rbp-88h] BYREF
  __int128 v47; // [rsp+88h] [rbp-78h]
  __int128 v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v50[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v49 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  memset_0(v50, 0, sizeof(v50));
  result = GetPCBPointerFromhPort(*a1);
  v3 = result;
  if ( result )
  {
    v4 = *((_DWORD *)a1 + 302);
    v5 = 1500;
    if ( (v4 & 2) != 0 )
      DWORD1(v46) = *((_DWORD *)a1 + 303);
    else
      DWORD1(v46) = 1500;
    v6 = -1;
    if ( (v4 & 4) != 0 )
      HIDWORD(v48) = *((_DWORD *)a1 + 304);
    else
      HIDWORD(v48) = -1;
    v7 = HIDWORD(v47);
    if ( (v4 & 0x80u) != 0 )
      v7 = 1024;
    if ( (v4 & 0x100) != 0 )
      v7 |= 0x200u;
    if ( (v4 & 0x40000) != 0 )
      v7 |= 0x20u;
    if ( (v4 & 8) == 0 )
      *((_DWORD *)a1 + 305) = 0;
    if ( (v4 & 0x20000) != 0 )
    {
      v5 = *((_DWORD *)a1 + 314);
      v7 |= 0x10u;
    }
    v8 = v7 | 0x100;
    HIDWORD(v46) = v5;
    HIDWORD(v47) = v8;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"LCP Local Options-------------");
      LOWORD(v8) = WORD6(v47);
    }
    v9 = "ON";
    if ( (byte_18004CF34 & 1) != 0 )
    {
      v10 = "ON";
      LOWORD(v49) = 0;
      v11 = "ON";
      if ( (v8 & 0x200) == 0 )
        v10 = "OFF";
      HIDWORD(v40) = HIDWORD(v10);
      if ( (v8 & 0x400) == 0 )
        v11 = "OFF";
      HIDWORD(v39) = HIDWORD(v11);
      FormatRRASErrorString(&v49, L"\tMRU=%d,ACCM=%d,Auth=%x,MagicNumber=%d,PFC=%hs,ACFC=%hs");
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
      LOBYTE(v8) = BYTE12(v47);
    }
    v12 = "PPP Multilink";
    if ( (byte_18004CF34 & 1) != 0 )
    {
      v13 = "ON";
      LOWORD(v49) = 0;
      v14 = "PPP Multilink";
      if ( (v8 & 0x20) == 0 )
        v13 = "OFF";
      if ( (v8 & 0x10) == 0 )
        v14 = "PPP";
      FormatRRASErrorString(
        &v49,
        L"\tRecv Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x",
        v14,
        v13,
        HIDWORD(v46),
        *((_DWORD *)a1 + 323));
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
    }
    if ( (a1[151] & 0x80000) != 0 && (byte_18004CF34 & 1) != 0 )
    {
      v15 = *((unsigned __int8 *)a1 + 1282);
      v16 = *((unsigned __int8 *)a1 + 1270);
      v17 = *((unsigned __int8 *)a1 + 1278);
      v18 = *((unsigned __int8 *)a1 + 1266);
      v19 = *((unsigned __int8 *)a1 + 1274);
      v20 = *((unsigned __int8 *)a1 + 1264);
      LOWORD(v49) = 0;
      LODWORD(v40) = 8;
      LODWORD(v39) = *((unsigned __int8 *)a1 + 1272)
                   + (*((unsigned __int8 *)a1 + 1269) << 24)
                   + (*((unsigned __int8 *)a1 + 1271) << 8)
                   + (v16 << 16);
      LODWORD(v38) = 8;
      LODWORD(v37) = *((unsigned __int8 *)a1 + 1268)
                   + (*((unsigned __int8 *)a1 + 1265) << 24)
                   + (*((unsigned __int8 *)a1 + 1267) << 8)
                   + (v18 << 16);
      FormatRRASErrorString(
        &v49,
        L"\tED Class = %d, ED Value = %0*x%0*x%0*x%0*x%0*x",
        v20,
        8,
        v37,
        v38,
        v39,
        v40,
        *((unsigned __int8 *)a1 + 1276)
      + (*((unsigned __int8 *)a1 + 1273) << 24)
      + (*((unsigned __int8 *)a1 + 1275) << 8)
      + (v19 << 16),
        8,
        *((unsigned __int8 *)a1 + 1280)
      + (*((unsigned __int8 *)a1 + 1277) << 24)
      + (*((unsigned __int8 *)a1 + 1279) << 8)
      + (v17 << 16),
        8,
        *((unsigned __int8 *)a1 + 1284)
      + (*((unsigned __int8 *)a1 + 1281) << 24)
      + (*((unsigned __int8 *)a1 + 1283) << 8)
      + (v15 << 16));
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
    }
    v21 = *((_DWORD *)a1 + 352);
    if ( (v21 & 2) != 0 )
    {
      v22 = *((_DWORD *)a1 + 353);
    }
    else
    {
      v22 = 1500;
      *((_DWORD *)a1 + 353) = 1500;
    }
    LODWORD(v46) = v22;
    if ( (v21 & 4) != 0 )
      v6 = *((_DWORD *)a1 + 354);
    v23 = DWORD2(v47);
    DWORD2(v48) = v6;
    if ( (v21 & 0x80u) != 0 )
      v23 = DWORD2(v47) | 0x400;
    if ( (v21 & 0x100) != 0 )
      v23 |= 0x200u;
    if ( (v21 & 0x40000) != 0 )
      v23 |= 0x20u;
    if ( (v21 & 8) != 0 )
    {
      v24 = *((_DWORD *)a1 + 355);
    }
    else
    {
      v24 = 0;
      *((_DWORD *)a1 + 355) = 0;
    }
    if ( (v21 & 0x20) != 0 )
      v25 = *((_DWORD *)a1 + 360);
    else
      v25 = 0;
    if ( (v21 & 0x20000) != 0 )
    {
      v23 |= 0x10u;
      DWORD2(v46) = *((_DWORD *)a1 + 364);
    }
    else
    {
      DWORD2(v46) = 1500;
    }
    DWORD2(v47) = v23 | 0x100;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"LCP Remote Options-------------");
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v49) = 0;
        v26 = "ON";
        v27 = "ON";
        if ( (WORD4(v47) & 0x200) == 0 )
          v26 = "OFF";
        if ( (WORD4(v47) & 0x400) == 0 )
          v27 = "OFF";
        LODWORD(v38) = v25;
        LODWORD(v37) = v24;
        FormatRRASErrorString(
          &v49,
          L"\tMRU=%d,ACCM=%d,Auth=%x,MagicNumber=%d,PFC=%hs,ACFC=%hs",
          (unsigned int)v46,
          DWORD2(v48),
          v37,
          v38,
          v27,
          v26);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v49) = 0;
          if ( (BYTE8(v47) & 0x20) == 0 )
            v9 = "OFF";
          if ( (BYTE8(v47) & 0x10) == 0 )
            v12 = "PPP";
          LODWORD(v38) = *((_DWORD *)a1 + 373);
          LODWORD(v37) = DWORD2(v46);
          FormatRRASErrorString(&v49, L"\tSend Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x", v12, v9, v37, v38);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
        }
      }
    }
    if ( (a1[176] & 0x80000) != 0 && (byte_18004CF34 & 1) != 0 )
    {
      v28 = *((unsigned __int8 *)a1 + 1478);
      v29 = *((unsigned __int8 *)a1 + 1474);
      v30 = *((unsigned __int8 *)a1 + 1482);
      v31 = *((unsigned __int8 *)a1 + 1470);
      v32 = *((unsigned __int8 *)a1 + 1466);
      v33 = *((unsigned __int8 *)a1 + 1464);
      LOWORD(v49) = 0;
      LODWORD(v45) = *((unsigned __int8 *)a1 + 1484)
                   + (*((unsigned __int8 *)a1 + 1481) << 24)
                   + (*((unsigned __int8 *)a1 + 1483) << 8)
                   + (v30 << 16);
      LODWORD(v44) = 8;
      LODWORD(v43) = *((unsigned __int8 *)a1 + 1480)
                   + (*((unsigned __int8 *)a1 + 1477) << 24)
                   + (*((unsigned __int8 *)a1 + 1479) << 8)
                   + (v28 << 16);
      LODWORD(v42) = 8;
      LODWORD(v41) = *((unsigned __int8 *)a1 + 1476)
                   + (*((unsigned __int8 *)a1 + 1473) << 24)
                   + (*((unsigned __int8 *)a1 + 1475) << 8)
                   + (v29 << 16);
      LODWORD(v40) = 8;
      LODWORD(v39) = *((unsigned __int8 *)a1 + 1472)
                   + (*((unsigned __int8 *)a1 + 1469) << 24)
                   + (*((unsigned __int8 *)a1 + 1471) << 8)
                   + (v31 << 16);
      LODWORD(v38) = 8;
      LODWORD(v37) = *((unsigned __int8 *)a1 + 1468)
                   + (*((unsigned __int8 *)a1 + 1465) << 24)
                   + (*((unsigned __int8 *)a1 + 1467) << 8)
                   + (v32 << 16);
      FormatRRASErrorString(
        &v49,
        L"\tED Class = %d, ED Value = %0*x%0*x%0*x%0*x%0*x",
        v33,
        8,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
    }
    v34 = *(_DWORD *)(v3 + 56) | 1;
    if ( (a1[151] & 0x20000) == 0 )
      v34 = *(_DWORD *)(v3 + 56) & 0xFFFFFFFE;
    *(_DWORD *)(v3 + 56) = v34;
    v35 = v34 | 0x10;
    v36 = v34 & 0xFFFFFFEF;
    if ( ((*((_DWORD *)a1 + 352) | *((_DWORD *)a1 + 302)) & 0x2000) != 0 )
      v36 = v35;
    *(_DWORD *)(v3 + 56) = v36;
    result = ((__int64 (__fastcall *)(_QWORD, __int128 *))xmmword_18004C490)(*a1, &v46);
    if ( (_DWORD)result == 2250 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800078e0  push    rbp
0x1800078e2  push    rbx
0x1800078e3  push    rsi
0x1800078e4  push    rdi
0x1800078e5  push    r12
0x1800078e7  push    r13
0x1800078e9  push    r14
0x1800078eb  push    r15
0x1800078ed  lea     rbp, [rsp-7C8h]
0x1800078f5  sub     rsp, 8C8h
0x1800078fc  mov     rax, cs:__security_cookie
0x180007903  xor     rax, rsp
0x180007906  mov     [rbp+800h+var_50], rax
0x18000790d  xorps   xmm0, xmm0
0x180007910  mov     rdi, rcx
0x180007913  xor     eax, eax
0x180007915  lea     rcx, [rbp+800h+var_84C]; void *
0x180007919  xor     edx, edx; Val
0x18000791b  mov     [rbp+800h+var_850], eax
0x18000791e  mov     r8d, 7FCh; Size
0x180007924  movups  [rsp+900h+var_888], xmm0
0x180007929  movups  [rbp+800h+var_878], xmm0
0x18000792d  movups  [rbp+800h+var_868], xmm0
0x180007931  call    memset_0
0x180007936  mov     rcx, [rdi]
0x180007939  call    GetPCBPointerFromhPort
0x18000793e  mov     r13, rax
0x180007941  test    rax, rax
0x180007944  jz      loc_18000801D
0x18000794a  mov     ecx, [rdi+4B8h]
0x180007950  mov     eax, 5DCh
0x180007955  test    cl, 2
0x180007958  jz      short loc_180007968
0x18000795a  mov     r8d, [rdi+4BCh]
0x180007961  mov     dword ptr [rsp+900h+var_888+4], r8d
0x180007966  jmp     short loc_18000796F
0x180007968  mov     r8d, eax
0x18000796b  mov     dword ptr [rsp+900h+var_888+4], eax
0x18000796f  or      esi, 0FFFFFFFFh
0x180007972  test    cl, 4
0x180007975  jz      short loc_180007984
0x180007977  mov     r9d, [rdi+4C0h]
0x18000797e  mov     dword ptr [rbp+800h+var_868+0Ch], r9d
0x180007982  jmp     short loc_18000798A
0x180007984  mov     r9d, esi
0x180007987  mov     dword ptr [rbp+800h+var_868+0Ch], esi
0x18000798a  mov     edx, dword ptr [rbp+800h+var_878+0Ch]
0x18000798d  test    cl, 80h
0x180007990  mov     r11d, 400h
0x180007996  mov     r10d, 100h
0x18000799c  cmovnz  edx, r11d
0x1800079a0  test    r10d, ecx
0x1800079a3  jz      short loc_1800079A9
0x1800079a5  bts     edx, 9
0x1800079a9  bt      ecx, 12h
0x1800079ad  jnb     short loc_1800079B2
0x1800079af  or      edx, 20h
0x1800079b2  mov     ebx, 8
0x1800079b7  test    bl, cl
0x1800079b9  jz      short loc_1800079C4
0x1800079bb  mov     r15d, [rdi+4C4h]
0x1800079c2  jmp     short loc_1800079CE
0x1800079c4  xor     r15d, r15d
0x1800079c7  mov     [rdi+4C4h], r15d
0x1800079ce  test    cl, 20h
0x1800079d1  jz      short loc_1800079DC
0x1800079d3  mov     r14d, [rdi+4D8h]
0x1800079da  jmp     short loc_1800079DF
0x1800079dc  xor     r14d, r14d
0x1800079df  bt      ecx, 11h
0x1800079e3  jnb     short loc_1800079EE
0x1800079e5  mov     eax, [rdi+4E8h]
0x1800079eb  or      edx, 10h
0x1800079ee  or      edx, r10d
0x1800079f1  mov     dword ptr [rbp+800h+var_888+0Ch], eax
0x1800079f4  test    cs:byte_18004CF34, 1
0x1800079fb  mov     dword ptr [rbp+800h+var_878+0Ch], edx
0x1800079fe  jz      short loc_180007A2C
0x180007a00  lea     r8, aLcpLocalOption; "LCP Local Options-------------"
0x180007a07  lea     rdx, RasPppTraceInfo
0x180007a0e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007a15  call    McTemplateU0z_EventWriteTransfer
0x180007a1a  mov     r9d, dword ptr [rbp+800h+var_868+0Ch]
0x180007a1e  mov     r11d, 400h
0x180007a24  mov     edx, dword ptr [rbp+800h+var_878+0Ch]
0x180007a27  mov     r8d, dword ptr [rsp+900h+var_888+4]
0x180007a2c  test    cs:byte_18004CF34, 1
0x180007a33  lea     r10, aOff; "OFF"
0x180007a3a  lea     rbx, aOn; "ON"
0x180007a41  jz      short loc_180007AAC
0x180007a43  xor     eax, eax
0x180007a45  mov     rcx, rbx
0x180007a48  bt      edx, 9
0x180007a4c  mov     word ptr [rbp+800h+var_850], ax
0x180007a50  mov     rax, rbx
0x180007a53  cmovnb  rcx, r10
0x180007a57  test    r11d, edx
0x180007a5a  mov     [rsp+900h+var_8C8], rcx
0x180007a5f  lea     rdx, aMruDAccmDAuthX; "\tMRU=%d,ACCM=%d,Auth=%x,MagicNumber=%d"...
0x180007a66  cmovz   rax, r10
0x180007a6a  lea     rcx, [rbp+800h+var_850]
0x180007a6e  mov     [rsp+900h+var_8D0], rax
0x180007a73  mov     dword ptr [rsp+900h+var_8D8], r14d
0x180007a78  mov     dword ptr [rsp+900h+var_8E0], r15d
0x180007a7d  call    FormatRRASErrorString
0x180007a82  test    cs:byte_18004CF34, 1
0x180007a89  jz      short loc_180007AA2
0x180007a8b  lea     r8, [rbp+800h+var_850]
0x180007a8f  lea     rdx, RasPppTraceInfo
0x180007a96  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007a9d  call    McTemplateU0z_EventWriteTransfer
0x180007aa2  mov     edx, dword ptr [rbp+800h+var_878+0Ch]
0x180007aa5  lea     r10, aOff; "OFF"
0x180007aac  test    cs:byte_18004CF34, 1
0x180007ab3  lea     rcx, aPpp; "PPP"
0x180007aba  lea     r12, aPppMultilink; "PPP Multilink"
0x180007ac1  jz      short loc_180007B1E
0x180007ac3  xor     eax, eax
0x180007ac5  mov     r9, rbx
0x180007ac8  test    dl, 20h
0x180007acb  mov     word ptr [rbp+800h+var_850], ax
0x180007acf  mov     eax, [rdi+50Ch]
0x180007ad5  mov     r8, r12
0x180007ad8  mov     dword ptr [rsp+900h+var_8D8], eax
0x180007adc  cmovz   r9, r10
0x180007ae0  mov     eax, dword ptr [rbp+800h+var_888+0Ch]
0x180007ae3  test    dl, 10h
0x180007ae6  lea     rdx, aRecvFramingHsS; "\tRecv Framing = %hs,SSHF=%hs,MRRU=%d,L"...
0x180007aed  mov     dword ptr [rsp+900h+var_8E0], eax
0x180007af1  cmovz   r8, rcx
0x180007af5  lea     rcx, [rbp+800h+var_850]
0x180007af9  call    FormatRRASErrorString
0x180007afe  test    cs:byte_18004CF34, 1
0x180007b05  jz      short loc_180007B1E
0x180007b07  lea     r8, [rbp+800h+var_850]
0x180007b0b  lea     rdx, RasPppTraceInfo
0x180007b12  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007b19  call    McTemplateU0z_EventWriteTransfer
0x180007b1e  test    dword ptr [rdi+4B8h], 80000h
0x180007b28  jz      loc_180007C95
0x180007b2e  test    cs:byte_18004CF34, 1
0x180007b35  jz      loc_180007C95
0x180007b3b  movzx   r11d, byte ptr [rdi+502h]
0x180007b43  xor     eax, eax
0x180007b45  movzx   edx, byte ptr [rdi+4F6h]
0x180007b4c  mov     r14d, 8
0x180007b52  movzx   r10d, byte ptr [rdi+4FEh]
0x180007b5a  movzx   ecx, byte ptr [rdi+4F2h]
0x180007b61  movzx   r9d, byte ptr [rdi+4FAh]
0x180007b69  movzx   r8d, byte ptr [rdi+4F0h]
0x180007b71  mov     word ptr [rbp+800h+var_850], ax
0x180007b75  movzx   eax, byte ptr [rdi+503h]
0x180007b7c  shl     eax, 8
0x180007b7f  shl     r9d, 10h
0x180007b83  shl     r11d, 10h
0x180007b87  add     r11d, eax
0x180007b8a  shl     edx, 10h
0x180007b8d  movzx   eax, byte ptr [rdi+501h]
0x180007b94  shl     eax, 18h
0x180007b97  add     r11d, eax
0x180007b9a  shl     r10d, 10h
0x180007b9e  movzx   eax, byte ptr [rdi+504h]
0x180007ba5  add     r11d, eax
0x180007ba8  shl     ecx, 10h
0x180007bab  movzx   eax, byte ptr [rdi+4FFh]
0x180007bb2  shl     eax, 8
0x180007bb5  add     r10d, eax
0x180007bb8  mov     dword ptr [rsp+900h+var_8A0], r11d
0x180007bbd  movzx   eax, byte ptr [rdi+4FDh]
0x180007bc4  shl     eax, 18h
0x180007bc7  add     r10d, eax
0x180007bca  mov     dword ptr [rsp+900h+var_8A8], r14d
0x180007bcf  movzx   eax, byte ptr [rdi+500h]
0x180007bd6  add     r10d, eax
0x180007bd9  movzx   eax, byte ptr [rdi+4FBh]
0x180007be0  shl     eax, 8
0x180007be3  add     r9d, eax
0x180007be6  mov     dword ptr [rsp+900h+var_8B0], r10d
0x180007beb  movzx   eax, byte ptr [rdi+4F9h]
0x180007bf2  shl     eax, 18h
0x180007bf5  add     r9d, eax
0x180007bf8  mov     dword ptr [rsp+900h+var_8B8], r14d
0x180007bfd  movzx   eax, byte ptr [rdi+4FCh]
0x180007c04  add     r9d, eax
0x180007c07  movzx   eax, byte ptr [rdi+4F7h]
0x180007c0e  shl     eax, 8
0x180007c11  add     edx, eax
0x180007c13  mov     dword ptr [rsp+900h+var_8C0], r9d
0x180007c18  movzx   eax, byte ptr [rdi+4F5h]
0x180007c1f  mov     r9d, r14d
0x180007c22  shl     eax, 18h
0x180007c25  add     edx, eax
0x180007c27  mov     dword ptr [rsp+900h+var_8C8], r14d
0x180007c2c  movzx   eax, byte ptr [rdi+4F8h]
0x180007c33  add     edx, eax
0x180007c35  movzx   eax, byte ptr [rdi+4F3h]
0x180007c3c  shl     eax, 8
0x180007c3f  add     ecx, eax
0x180007c41  mov     dword ptr [rsp+900h+var_8D0], edx
0x180007c45  movzx   eax, byte ptr [rdi+4F1h]
0x180007c4c  lea     rdx, aEdClassDEdValu; "\tED Class = %d, ED Value = %0*x%0*x%0*"...
0x180007c53  shl     eax, 18h
0x180007c56  add     ecx, eax
0x180007c58  mov     dword ptr [rsp+900h+var_8D8], r14d
0x180007c5d  movzx   eax, byte ptr [rdi+4F4h]
0x180007c64  add     ecx, eax
0x180007c66  mov     dword ptr [rsp+900h+var_8E0], ecx
0x180007c6a  lea     rcx, [rbp+800h+var_850]
0x180007c6e  call    FormatRRASErrorString
0x180007c73  test    cs:byte_18004CF34, 1
0x180007c7a  jz      short loc_180007C9B
0x180007c7c  lea     r8, [rbp+800h+var_850]
0x180007c80  lea     rdx, RasPppTraceInfo
0x180007c87  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007c8e  call    McTemplateU0z_EventWriteTransfer
0x180007c93  jmp     short loc_180007C9B
0x180007c95  mov     r14d, 8
0x180007c9b  mov     eax, [rdi+580h]
0x180007ca1  test    al, 2
0x180007ca3  jz      short loc_180007CAE
0x180007ca5  mov     r8d, [rdi+584h]
0x180007cac  jmp     short loc_180007CBB
0x180007cae  mov     r8d, 5DCh
0x180007cb4  mov     [rdi+584h], r8d
0x180007cbb  mov     dword ptr [rsp+900h+var_888], r8d
0x180007cc0  test    al, 4
0x180007cc2  jz      short loc_180007CCA
0x180007cc4  mov     esi, [rdi+588h]
0x180007cca  mov     edx, dword ptr [rbp+800h+var_878+8]
0x180007ccd  mov     dword ptr [rbp+800h+var_868+8], esi
0x180007cd0  test    al, al
0x180007cd2  jns     short loc_180007CD8
0x180007cd4  bts     edx, 0Ah
0x180007cd8  mov     ecx, 100h
0x180007cdd  test    ecx, eax
0x180007cdf  jz      short loc_180007CE5
0x180007ce1  bts     edx, 9
0x180007ce5  bt      eax, 12h
0x180007ce9  jnb     short loc_180007CEE
0x180007ceb  or      edx, 20h
0x180007cee  test    r14b, al
0x180007cf1  jz      short loc_180007CFC
0x180007cf3  mov     r15d, [rdi+58Ch]
0x180007cfa  jmp     short loc_180007D06
0x180007cfc  xor     r15d, r15d
0x180007cff  mov     [rdi+58Ch], r15d
0x180007d06  test    al, 20h
0x180007d08  jz      short loc_180007D13
0x180007d0a  mov     r14d, [rdi+5A0h]
0x180007d11  jmp     short loc_180007D16
0x180007d13  xor     r14d, r14d
0x180007d16  bt      eax, 11h
0x180007d1a  jnb     short loc_180007D2A
0x180007d1c  mov     eax, [rdi+5B0h]
0x180007d22  or      edx, 10h
0x180007d25  mov     dword ptr [rbp+800h+var_888+8], eax
0x180007d28  jmp     short loc_180007D31
0x180007d2a  mov     dword ptr [rbp+800h+var_888+8], 5DCh
0x180007d31  or      edx, ecx
0x180007d33  test    cs:byte_18004CF34, 1
0x180007d3a  mov     dword ptr [rbp+800h+var_878+8], edx
0x180007d3d  jz      loc_180007E54
0x180007d43  lea     r8, aLcpRemoteOptio; "LCP Remote Options-------------"
0x180007d4a  lea     rdx, RasPppTraceInfo
0x180007d51  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007d58  call    McTemplateU0z_EventWriteTransfer
0x180007d5d  test    cs:byte_18004CF34, 1
0x180007d64  mov     esi, dword ptr [rbp+800h+var_868+8]
0x180007d67  mov     edx, dword ptr [rbp+800h+var_878+8]
0x180007d6a  mov     r8d, dword ptr [rsp+900h+var_888]
0x180007d6f  jz      loc_180007E54
0x180007d75  xor     eax, eax
0x180007d77  lea     r9, aOff; "OFF"
0x180007d7e  bt      edx, 9
0x180007d82  mov     word ptr [rbp+800h+var_850], ax
0x180007d86  mov     rcx, rbx
0x180007d89  mov     rax, rbx
0x180007d8c  cmovnb  rcx, r9
0x180007d90  bt      edx, 0Ah
0x180007d94  mov     [rsp+900h+var_8C8], rcx
0x180007d99  lea     rdx, aMruDAccmDAuthX; "\tMRU=%d,ACCM=%d,Auth=%x,MagicNumber=%d"...
0x180007da0  cmovnb  rax, r9
0x180007da4  lea     rcx, [rbp+800h+var_850]
0x180007da8  mov     [rsp+900h+var_8D0], rax
0x180007dad  mov     r9d, esi
0x180007db0  mov     dword ptr [rsp+900h+var_8D8], r14d
0x180007db5  mov     dword ptr [rsp+900h+var_8E0], r15d
0x180007dba  call    FormatRRASErrorString
0x180007dbf  test    cs:byte_18004CF34, 1
0x180007dc6  jz      short loc_180007DDF
0x180007dc8  lea     r8, [rbp+800h+var_850]
0x180007dcc  lea     rdx, RasPppTraceInfo
0x180007dd3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007dda  call    McTemplateU0z_EventWriteTransfer
0x180007ddf  test    cs:byte_18004CF34, 1
0x180007de6  mov     edx, dword ptr [rbp+800h+var_878+8]
0x180007de9  jz      short loc_180007E54
0x180007deb  xor     eax, eax
0x180007ded  lea     rcx, [rbp+800h+var_850]
0x180007df1  mov     word ptr [rbp+800h+var_850], ax
  ... truncated ...
```
