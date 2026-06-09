# LcpThisLayerUp

- ea: `0x180007bd0`
- end: `0x180008331`
- name: `LcpThisLayerUp`
- size: `1889`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180007bd0`
- `0x1800115a0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180007daa`: `PPP Multilink`
- `0x180007dd6`: `	Recv Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x`
- `0x180008104`: `	Send Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x`

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
    if ( (byte_18004DF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"LCP Local Options-------------");
      LOWORD(v8) = WORD6(v47);
    }
    v9 = "ON";
    if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
      LOBYTE(v8) = BYTE12(v47);
    }
    v12 = "PPP Multilink";
    if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
    }
    if ( (a1[151] & 0x80000) != 0 && (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
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
    if ( (byte_18004DF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"LCP Remote Options-------------");
      if ( (byte_18004DF34 & 1) != 0 )
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
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v49) = 0;
          if ( (BYTE8(v47) & 0x20) == 0 )
            v9 = "OFF";
          if ( (BYTE8(v47) & 0x10) == 0 )
            v12 = "PPP";
          LODWORD(v38) = *((_DWORD *)a1 + 373);
          LODWORD(v37) = DWORD2(v46);
          FormatRRASErrorString(&v49, L"\tSend Framing = %hs,SSHF=%hs,MRRU=%d,LinkDiscrim=%x", v12, v9, v37, v38);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v49);
        }
      }
    }
    if ( (a1[176] & 0x80000) != 0 && (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
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
    result = ((__int64 (__fastcall *)(_QWORD, __int128 *))xmmword_18004D490)(*a1, &v46);
    if ( (_DWORD)result == 2250 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007bd0  push    rbp
0x180007bd2  push    rbx
0x180007bd3  push    rsi
0x180007bd4  push    rdi
0x180007bd5  push    r12
0x180007bd7  push    r13
0x180007bd9  push    r14
0x180007bdb  push    r15
0x180007bdd  lea     rbp, [rsp-7C8h]
0x180007be5  sub     rsp, 8C8h
0x180007bec  mov     rax, cs:__security_cookie
0x180007bf3  xor     rax, rsp
0x180007bf6  mov     [rbp+800h+var_50], rax
0x180007bfd  xorps   xmm0, xmm0
0x180007c00  mov     rdi, rcx
0x180007c03  xor     eax, eax
0x180007c05  lea     rcx, [rbp+800h+var_84C]; void *
0x180007c09  xor     edx, edx; Val
0x180007c0b  mov     [rbp+800h+var_850], eax
0x180007c0e  mov     r8d, 7FCh; Size
0x180007c14  movups  [rsp+900h+var_888], xmm0
0x180007c19  movups  [rbp+800h+var_878], xmm0
0x180007c1d  movups  [rbp+800h+var_868], xmm0
0x180007c21  call    memset_0
0x180007c26  mov     rcx, [rdi]
0x180007c29  call    GetPCBPointerFromhPort
0x180007c2e  mov     r13, rax
0x180007c31  test    rax, rax
0x180007c34  jz      loc_18000830D
0x180007c3a  mov     ecx, [rdi+4B8h]
0x180007c40  mov     eax, 5DCh
0x180007c45  test    cl, 2
0x180007c48  jz      short loc_180007C58
0x180007c4a  mov     r8d, [rdi+4BCh]
0x180007c51  mov     dword ptr [rsp+900h+var_888+4], r8d
0x180007c56  jmp     short loc_180007C5F
0x180007c58  mov     r8d, eax
0x180007c5b  mov     dword ptr [rsp+900h+var_888+4], eax
0x180007c5f  or      esi, 0FFFFFFFFh
0x180007c62  test    cl, 4
0x180007c65  jz      short loc_180007C74
0x180007c67  mov     r9d, [rdi+4C0h]
0x180007c6e  mov     dword ptr [rbp+800h+var_868+0Ch], r9d
0x180007c72  jmp     short loc_180007C7A
0x180007c74  mov     r9d, esi
0x180007c77  mov     dword ptr [rbp+800h+var_868+0Ch], esi
0x180007c7a  mov     edx, dword ptr [rbp+800h+var_878+0Ch]
0x180007c7d  test    cl, 80h
0x180007c80  mov     r11d, 400h
0x180007c86  mov     r10d, 100h
0x180007c8c  cmovnz  edx, r11d
0x180007c90  test    r10d, ecx
0x180007c93  jz      short loc_180007C99
0x180007c95  bts     edx, 9
0x180007c99  bt      ecx, 12h
0x180007c9d  jnb     short loc_180007CA2
0x180007c9f  or      edx, 20h
0x180007ca2  mov     ebx, 8
0x180007ca7  test    bl, cl
0x180007ca9  jz      short loc_180007CB4
0x180007cab  mov     r15d, [rdi+4C4h]
0x180007cb2  jmp     short loc_180007CBE
0x180007cb4  xor     r15d, r15d
0x180007cb7  mov     [rdi+4C4h], r15d
0x180007cbe  test    cl, 20h
0x180007cc1  jz      short loc_180007CCC
0x180007cc3  mov     r14d, [rdi+4D8h]
0x180007cca  jmp     short loc_180007CCF
0x180007ccc  xor     r14d, r14d
0x180007ccf  bt      ecx, 11h
0x180007cd3  jnb     short loc_180007CDE
0x180007cd5  mov     eax, [rdi+4E8h]
0x180007cdb  or      edx, 10h
0x180007cde  or      edx, r10d
0x180007ce1  mov     dword ptr [rbp+800h+var_888+0Ch], eax
0x180007ce4  test    cs:byte_18004DF34, 1
0x180007ceb  mov     dword ptr [rbp+800h+var_878+0Ch], edx
0x180007cee  jz      short loc_180007D1C
0x180007cf0  lea     r8, aLcpLocalOption; "LCP Local Options-------------"
0x180007cf7  lea     rdx, RasPppTraceInfo
0x180007cfe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007d05  call    McTemplateU0z_EventWriteTransfer
0x180007d0a  mov     r9d, dword ptr [rbp+800h+var_868+0Ch]
0x180007d0e  mov     r11d, 400h
0x180007d14  mov     edx, dword ptr [rbp+800h+var_878+0Ch]
0x180007d17  mov     r8d, dword ptr [rsp+900h+var_888+4]
0x180007d1c  test    cs:byte_18004DF34, 1
0x180007d23  lea     r10, aOff; "OFF"
0x180007d2a  lea     rbx, aOn; "ON"
0x180007d31  jz      short loc_180007D9C
0x180007d33  xor     eax, eax
0x180007d35  mov     rcx, rbx
0x180007d38  bt      edx, 9
0x180007d3c  mov     word ptr [rbp+800h+var_850], ax
0x180007d40  mov     rax, rbx
0x180007d43  cmovnb  rcx, r10
0x180007d47  test    r11d, edx
0x180007d4a  mov     [rsp+900h+var_8C8], rcx
0x180007d4f  lea     rdx, aMruDAccmDAuthX; "\tMRU=%d,ACCM=%d,Auth=%x,MagicNumber=%d"...
0x180007d56  cmovz   rax, r10
0x180007d5a  lea     rcx, [rbp+800h+var_850]
0x180007d5e  mov     [rsp+900h+var_8D0], rax
0x180007d63  mov     dword ptr [rsp+900h+var_8D8], r14d
0x180007d68  mov     dword ptr [rsp+900h+var_8E0], r15d
0x180007d6d  call    FormatRRASErrorString
0x180007d72  test    cs:byte_18004DF34, 1
0x180007d79  jz      short loc_180007D92
0x180007d7b  lea     r8, [rbp+800h+var_850]
0x180007d7f  lea     rdx, RasPppTraceInfo
0x180007d86  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007d8d  call    McTemplateU0z_EventWriteTransfer
0x180007d92  mov     edx, dword ptr [rbp+800h+var_878+0Ch]
0x180007d95  lea     r10, aOff; "OFF"
0x180007d9c  test    cs:byte_18004DF34, 1
0x180007da3  lea     rcx, aPpp; "PPP"
0x180007daa  lea     r12, aPppMultilink; "PPP Multilink"
0x180007db1  jz      short loc_180007E0E
0x180007db3  xor     eax, eax
0x180007db5  mov     r9, rbx
0x180007db8  test    dl, 20h
0x180007dbb  mov     word ptr [rbp+800h+var_850], ax
0x180007dbf  mov     eax, [rdi+50Ch]
0x180007dc5  mov     r8, r12
0x180007dc8  mov     dword ptr [rsp+900h+var_8D8], eax
0x180007dcc  cmovz   r9, r10
0x180007dd0  mov     eax, dword ptr [rbp+800h+var_888+0Ch]
0x180007dd3  test    dl, 10h
0x180007dd6  lea     rdx, aRecvFramingHsS; "\tRecv Framing = %hs,SSHF=%hs,MRRU=%d,L"...
0x180007ddd  mov     dword ptr [rsp+900h+var_8E0], eax
0x180007de1  cmovz   r8, rcx
0x180007de5  lea     rcx, [rbp+800h+var_850]
0x180007de9  call    FormatRRASErrorString
0x180007dee  test    cs:byte_18004DF34, 1
0x180007df5  jz      short loc_180007E0E
0x180007df7  lea     r8, [rbp+800h+var_850]
0x180007dfb  lea     rdx, RasPppTraceInfo
0x180007e02  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007e09  call    McTemplateU0z_EventWriteTransfer
0x180007e0e  test    dword ptr [rdi+4B8h], 80000h
0x180007e18  jz      loc_180007F85
0x180007e1e  test    cs:byte_18004DF34, 1
0x180007e25  jz      loc_180007F85
0x180007e2b  movzx   r11d, byte ptr [rdi+502h]
0x180007e33  xor     eax, eax
0x180007e35  movzx   edx, byte ptr [rdi+4F6h]
0x180007e3c  mov     r14d, 8
0x180007e42  movzx   r10d, byte ptr [rdi+4FEh]
0x180007e4a  movzx   ecx, byte ptr [rdi+4F2h]
0x180007e51  movzx   r9d, byte ptr [rdi+4FAh]
0x180007e59  movzx   r8d, byte ptr [rdi+4F0h]
0x180007e61  mov     word ptr [rbp+800h+var_850], ax
0x180007e65  movzx   eax, byte ptr [rdi+503h]
0x180007e6c  shl     eax, 8
0x180007e6f  shl     r9d, 10h
0x180007e73  shl     r11d, 10h
0x180007e77  add     r11d, eax
0x180007e7a  shl     edx, 10h
0x180007e7d  movzx   eax, byte ptr [rdi+501h]
0x180007e84  shl     eax, 18h
0x180007e87  add     r11d, eax
0x180007e8a  shl     r10d, 10h
0x180007e8e  movzx   eax, byte ptr [rdi+504h]
0x180007e95  add     r11d, eax
0x180007e98  shl     ecx, 10h
0x180007e9b  movzx   eax, byte ptr [rdi+4FFh]
0x180007ea2  shl     eax, 8
0x180007ea5  add     r10d, eax
0x180007ea8  mov     dword ptr [rsp+900h+var_8A0], r11d
0x180007ead  movzx   eax, byte ptr [rdi+4FDh]
0x180007eb4  shl     eax, 18h
0x180007eb7  add     r10d, eax
0x180007eba  mov     dword ptr [rsp+900h+var_8A8], r14d
0x180007ebf  movzx   eax, byte ptr [rdi+500h]
0x180007ec6  add     r10d, eax
0x180007ec9  movzx   eax, byte ptr [rdi+4FBh]
0x180007ed0  shl     eax, 8
0x180007ed3  add     r9d, eax
0x180007ed6  mov     dword ptr [rsp+900h+var_8B0], r10d
0x180007edb  movzx   eax, byte ptr [rdi+4F9h]
0x180007ee2  shl     eax, 18h
0x180007ee5  add     r9d, eax
0x180007ee8  mov     dword ptr [rsp+900h+var_8B8], r14d
0x180007eed  movzx   eax, byte ptr [rdi+4FCh]
0x180007ef4  add     r9d, eax
0x180007ef7  movzx   eax, byte ptr [rdi+4F7h]
0x180007efe  shl     eax, 8
0x180007f01  add     edx, eax
0x180007f03  mov     dword ptr [rsp+900h+var_8C0], r9d
0x180007f08  movzx   eax, byte ptr [rdi+4F5h]
0x180007f0f  mov     r9d, r14d
0x180007f12  shl     eax, 18h
0x180007f15  add     edx, eax
0x180007f17  mov     dword ptr [rsp+900h+var_8C8], r14d
0x180007f1c  movzx   eax, byte ptr [rdi+4F8h]
0x180007f23  add     edx, eax
0x180007f25  movzx   eax, byte ptr [rdi+4F3h]
0x180007f2c  shl     eax, 8
0x180007f2f  add     ecx, eax
0x180007f31  mov     dword ptr [rsp+900h+var_8D0], edx
0x180007f35  movzx   eax, byte ptr [rdi+4F1h]
0x180007f3c  lea     rdx, aEdClassDEdValu; "\tED Class = %d, ED Value = %0*x%0*x%0*"...
0x180007f43  shl     eax, 18h
0x180007f46  add     ecx, eax
0x180007f48  mov     dword ptr [rsp+900h+var_8D8], r14d
0x180007f4d  movzx   eax, byte ptr [rdi+4F4h]
0x180007f54  add     ecx, eax
0x180007f56  mov     dword ptr [rsp+900h+var_8E0], ecx
0x180007f5a  lea     rcx, [rbp+800h+var_850]
0x180007f5e  call    FormatRRASErrorString
0x180007f63  test    cs:byte_18004DF34, 1
0x180007f6a  jz      short loc_180007F8B
0x180007f6c  lea     r8, [rbp+800h+var_850]
0x180007f70  lea     rdx, RasPppTraceInfo
0x180007f77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007f7e  call    McTemplateU0z_EventWriteTransfer
0x180007f83  jmp     short loc_180007F8B
0x180007f85  mov     r14d, 8
0x180007f8b  mov     eax, [rdi+580h]
0x180007f91  test    al, 2
0x180007f93  jz      short loc_180007F9E
0x180007f95  mov     r8d, [rdi+584h]
0x180007f9c  jmp     short loc_180007FAB
0x180007f9e  mov     r8d, 5DCh
0x180007fa4  mov     [rdi+584h], r8d
0x180007fab  mov     dword ptr [rsp+900h+var_888], r8d
0x180007fb0  test    al, 4
0x180007fb2  jz      short loc_180007FBA
0x180007fb4  mov     esi, [rdi+588h]
0x180007fba  mov     edx, dword ptr [rbp+800h+var_878+8]
0x180007fbd  mov     dword ptr [rbp+800h+var_868+8], esi
0x180007fc0  test    al, al
0x180007fc2  jns     short loc_180007FC8
0x180007fc4  bts     edx, 0Ah
0x180007fc8  mov     ecx, 100h
0x180007fcd  test    ecx, eax
0x180007fcf  jz      short loc_180007FD5
0x180007fd1  bts     edx, 9
0x180007fd5  bt      eax, 12h
0x180007fd9  jnb     short loc_180007FDE
0x180007fdb  or      edx, 20h
0x180007fde  test    r14b, al
0x180007fe1  jz      short loc_180007FEC
0x180007fe3  mov     r15d, [rdi+58Ch]
0x180007fea  jmp     short loc_180007FF6
0x180007fec  xor     r15d, r15d
0x180007fef  mov     [rdi+58Ch], r15d
0x180007ff6  test    al, 20h
0x180007ff8  jz      short loc_180008003
0x180007ffa  mov     r14d, [rdi+5A0h]
0x180008001  jmp     short loc_180008006
0x180008003  xor     r14d, r14d
0x180008006  bt      eax, 11h
0x18000800a  jnb     short loc_18000801A
0x18000800c  mov     eax, [rdi+5B0h]
0x180008012  or      edx, 10h
0x180008015  mov     dword ptr [rbp+800h+var_888+8], eax
0x180008018  jmp     short loc_180008021
0x18000801a  mov     dword ptr [rbp+800h+var_888+8], 5DCh
0x180008021  or      edx, ecx
0x180008023  test    cs:byte_18004DF34, 1
0x18000802a  mov     dword ptr [rbp+800h+var_878+8], edx
0x18000802d  jz      loc_180008144
0x180008033  lea     r8, aLcpRemoteOptio; "LCP Remote Options-------------"
0x18000803a  lea     rdx, RasPppTraceInfo
0x180008041  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008048  call    McTemplateU0z_EventWriteTransfer
0x18000804d  test    cs:byte_18004DF34, 1
0x180008054  mov     esi, dword ptr [rbp+800h+var_868+8]
0x180008057  mov     edx, dword ptr [rbp+800h+var_878+8]
0x18000805a  mov     r8d, dword ptr [rsp+900h+var_888]
0x18000805f  jz      loc_180008144
0x180008065  xor     eax, eax
0x180008067  lea     r9, aOff; "OFF"
0x18000806e  bt      edx, 9
0x180008072  mov     word ptr [rbp+800h+var_850], ax
0x180008076  mov     rcx, rbx
0x180008079  mov     rax, rbx
0x18000807c  cmovnb  rcx, r9
0x180008080  bt      edx, 0Ah
0x180008084  mov     [rsp+900h+var_8C8], rcx
0x180008089  lea     rdx, aMruDAccmDAuthX; "\tMRU=%d,ACCM=%d,Auth=%x,MagicNumber=%d"...
0x180008090  cmovnb  rax, r9
0x180008094  lea     rcx, [rbp+800h+var_850]
0x180008098  mov     [rsp+900h+var_8D0], rax
0x18000809d  mov     r9d, esi
0x1800080a0  mov     dword ptr [rsp+900h+var_8D8], r14d
0x1800080a5  mov     dword ptr [rsp+900h+var_8E0], r15d
0x1800080aa  call    FormatRRASErrorString
0x1800080af  test    cs:byte_18004DF34, 1
0x1800080b6  jz      short loc_1800080CF
0x1800080b8  lea     r8, [rbp+800h+var_850]
0x1800080bc  lea     rdx, RasPppTraceInfo
0x1800080c3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800080ca  call    McTemplateU0z_EventWriteTransfer
0x1800080cf  test    cs:byte_18004DF34, 1
0x1800080d6  mov     edx, dword ptr [rbp+800h+var_878+8]
0x1800080d9  jz      short loc_180008144
0x1800080db  xor     eax, eax
0x1800080dd  lea     rcx, [rbp+800h+var_850]
0x1800080e1  mov     word ptr [rbp+800h+var_850], ax
  ... truncated ...
```
