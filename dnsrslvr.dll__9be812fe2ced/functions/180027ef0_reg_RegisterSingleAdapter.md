# reg_RegisterSingleAdapter

- ea: `0x180027ef0`
- end: `0x1800287ea`
- name: `reg_RegisterSingleAdapter`
- size: `2298`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x180027c04`
- `0x18003e9b0`

## callees

- `0x18000b130`
- `0x180027ef0`
- `0x1800287f0`
- `0x180028df8`
- `0x1800290dc`
- `0x18002943c`
- `0x18002951c`
- `0x1800296f0`
- `0x180046ec0`
- `0x180047818`
- `0x18007e79c`
- `0x18007e878`
- `0x18007e944`
- `0x18007ecf4`
- `0x180085e68`
- `0x1800864ac`
- `0x180086b1c`
- `0x180086fe4`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x180027fb2`
- `DNSAPI!DnsGlobals` at `0x180028090`
- `DNSAPI!DnsGlobals` at `0x1800281e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002872a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002872a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800283c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800283c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800283dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800287b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800283dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800287b2`

## pseudocode

```c
__int64 __fastcall reg_RegisterSingleAdapter(__int64 a1, __int64 a2, int a3, int a4, unsigned int *a5)
{
  int v8; // edx
  int v9; // ecx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rdi
  unsigned int *v13; // r13
  int v14; // ecx
  int v15; // edx
  __int16 v16; // ax
  BOOL v17; // ecx
  int v18; // esi
  BOOL v19; // eax
  int v20; // edi
  __int16 v21; // r12
  int v22; // ecx
  int v23; // r15d
  int v24; // r14d
  int v25; // esi
  int v26; // r8d
  int v27; // r9d
  _WORD *v28; // rax
  unsigned int appended; // eax
  unsigned int LastError; // edi
  unsigned int *v31; // r12
  int v32; // edx
  int v33; // eax
  __int64 v34; // rdx
  int v35; // r8d
  int v36; // ecx
  ULONGLONG v38; // rsi
  ULONGLONG TickCount64; // rax
  int v40; // r8d
  int v41; // eax
  __int64 v42; // r9
  int v43; // edx
  int v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+28h] [rbp-D8h]
  int v46; // [rsp+50h] [rbp-B0h]
  __int16 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int128 v50; // [rsp+68h] [rbp-98h] BYREF
  __int128 v51; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+88h] [rbp-78h]
  unsigned int *v53; // [rsp+90h] [rbp-70h]
  HANDLE hHandle; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h]
  _DWORD v56[2]; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE *p_hHandle; // [rsp+B8h] [rbp-48h]
  __int64 v58; // [rsp+C0h] [rbp-40h]
  __int64 v59; // [rsp+C8h] [rbp-38h]
  __int64 v60; // [rsp+D0h] [rbp-30h]
  unsigned int *v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  __int64 v63; // [rsp+E8h] [rbp-18h]
  __int128 v64; // [rsp+F0h] [rbp-10h]
  _WORD v65[32]; // [rsp+100h] [rbp+0h] BYREF

  v48 = a3;
  v52 = a1;
  v53 = a5;
  memset_0(v56, 0, 0x50u);
  memset_0(v65, 0, sizeof(v65));
  hHandle = 0;
  v55 = 0;
  v12 = (__int64 *)(a2 + 120);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SqSSSDD(v9, v8, v10, *(_QWORD *)a2, a2, *v12, *(_QWORD *)a2, *(_QWORD *)(a2 + 8), a3, a4);
  if ( a5 )
  {
    v13 = a5;
  }
  else
  {
    v13 = (unsigned int *)DnsAddrArray_Create(64);
    if ( !v13 )
    {
      LastError = 14;
      goto LABEL_55;
    }
  }
  v14 = *(_DWORD *)(a2 + 56);
  v49 = 0;
  v46 = 0;
  if ( (v14 & 1) == 0 )
  {
    v31 = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SS(1035, 18, (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, *v12, *(_QWORD *)a2);
    goto LABEL_70;
  }
  if ( !DnsGlobals[61] && *(_DWORD *)(a2 + 60) == 131 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v42 = *v12;
      v43 = 19;
LABEL_110:
      WPP_SF_SS(1035, v43, (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, v42, *(_QWORD *)a2);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  v15 = 10;
  LOBYTE(v11) = 4;
  if ( (v14 & 0x80) == 0 )
  {
    if ( (v14 & 0x100) == 0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SS(
          1035,
          20,
          (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids,
          *(_QWORD *)(a2 + 120),
          *(_QWORD *)a2);
      LastError = 9851;
      goto LABEL_53;
    }
    v18 = 10;
    v20 = 10;
    goto LABEL_107;
  }
  if ( (v14 & 4) == 0 )
  {
    v18 = 10;
    v20 = 10;
    if ( (v14 & 0x100) == 0 )
      goto LABEL_26;
LABEL_107:
    if ( (v14 & 0x220) == 0 )
      goto LABEL_26;
  }
  v50 = 0;
  v51 = 0;
  if ( (a4 & 0x10000002) == 0
    && ((v14 & 0x80) == 0 || (*(_BYTE *)(a2 + 56) & 4) != 0)
    && ((v14 & 0x100) == 0 || (v14 & 0x220) != 0) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v42 = *(_QWORD *)(a2 + 120);
      v43 = 21;
      goto LABEL_110;
    }
LABEL_80:
    LastError = 87;
    goto LABEL_53;
  }
  v16 = v14;
  v17 = (v14 & 0x80u) != 0 && (v14 & 4) != 0;
  v18 = !v17 ? 0xA : 0;
  v19 = (v16 & 0x100) != 0 && (v16 & 0x220) != 0;
  v20 = !v19 ? 0xA : 0;
  if ( (unsigned int)reg_GetRegistrationInfoFromDhcp(a2, &v50, v10, v11) )
  {
    if ( DWORD1(v51) )
      v18 = HIDWORD(v51);
    if ( DWORD1(v50) )
      v20 = v51;
    if ( (a4 & 0x10001000) == 0 )
    {
      v41 = *(_DWORD *)(a2 + 56);
      if ( ((v41 & 0x80u) == 0 || (v41 & 4) != 0)
        && ((v41 & 0x100) == 0 || (v41 & 0x220) != 0)
        && DWORD2(v51) != 3
        && HIDWORD(v50) != 3 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_SSdd(DWORD2(v51), 22, v10, *(_QWORD *)(a2 + 120), *(_QWORD *)a2, SBYTE8(v51), SBYTE12(v50));
        v46 = 1;
      }
    }
  }
  if ( (a4 & 0x10000000) != 0 )
  {
    if ( (a3 & 0x100) != 0 )
    {
      v18 = a3;
    }
    else if ( (a3 & 0x200) != 0 )
    {
      v20 = a3;
    }
  }
LABEL_26:
  v21 = 2;
  v22 = DnsGlobals[69];
  if ( v22 )
  {
    if ( (v18 & 0x40) != 0 )
    {
      if ( (v20 & 0x40) != 0 )
        goto LABEL_29;
    }
    else if ( (v20 & 0x40) == 0 )
    {
      goto LABEL_29;
    }
    if ( v22 == 1 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SSdd(1, 23, v10, *(_QWORD *)(a2 + 120), *(_QWORD *)a2, v18, v20);
      if ( (v18 & 0x40) != 0 )
      {
LABEL_105:
        v18 = v20;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v22 != 2 )
        goto LABEL_29;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SSdd(2, 24, v10, *(_QWORD *)(a2 + 120), *(_QWORD *)a2, v18, v20);
      if ( (v18 & 0x40) == 0 )
        goto LABEL_105;
    }
    v20 = v18;
  }
LABEL_29:
  v23 = v18 | v20 & 0x12;
  v24 = v20 | v18 & 0x12 | v20 & 0x12;
  v25 = v23 | v24;
  if ( *(_QWORD *)(a2 + 40) && ((v23 & 0x60) == 0 || (v24 & 0x60) == 0) )
    v25 &= 0xFFFFFF9F;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SSDDD(v22, v15, v10, *(_QWORD *)(a2 + 120), *(_QWORD *)a2, v25, v23, v24);
  if ( (*(_BYTE *)(a2 + 56) & 2) != 0 && (v25 & 2) != 0 )
    v49 = *(_QWORD *)(a2 + 8);
  memset_0(v13 + 8, 0, (unsigned __int64)v13[1] << 6);
  v13[1] = 0;
  if ( (v25 & 0x60) != 0 )
    goto LABEL_40;
  if ( !*(_QWORD *)(a2 + 40) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SS(
        1035,
        26,
        (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids,
        *(_QWORD *)(a2 + 120),
        *(_QWORD *)a2);
    LastError = 9852;
    goto LABEL_53;
  }
  if ( (v23 & 0x60) != 0 )
  {
    if ( (v24 & 0x60) != 0 )
      goto LABEL_40;
    v21 = 23;
    goto LABEL_123;
  }
  v28 = 0;
  if ( (v24 & 0x60) != 0 )
  {
LABEL_123:
    memset_0(v65, 0, sizeof(v65));
    v28 = v65;
    v65[0] = v21;
  }
  appended = DnsAddrArray_AppendArrayEx((_DWORD)v13, *(_QWORD *)(a2 + 32), v26, v27, v44, v45, (__int64)v28);
  LastError = appended;
  if ( appended && appended != 234 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      LODWORD(v45) = appended;
      WPP_SF_SSd(
        1035,
        27,
        (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids,
        *(_QWORD *)(a2 + 120),
        *(_QWORD *)a2,
        v45);
    }
    goto LABEL_53;
  }
LABEL_40:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    LODWORD(v45) = v13[1];
    WPP_SF_SSd(
      1035,
      28,
      (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids,
      *(_QWORD *)(a2 + 120),
      *(_QWORD *)a2,
      v45);
  }
  DnsPrint_DnsAddrArray("Registerable addrs", 0, v13);
  if ( !v13[1] )
  {
    v31 = 0;
LABEL_70:
    v25 = 32;
    v23 = 32;
    v24 = 32;
    goto LABEL_44;
  }
  v31 = v13;
LABEL_44:
  v58 = *(_QWORD *)a2;
  v32 = v25 | 0x10000000;
  if ( !v46 )
    v32 = v25;
  v64 = 0;
  v63 = 0;
  v59 = *(_QWORD *)(v52 + 24);
  v60 = v49;
  v62 = *(_QWORD *)(a2 + 40);
  v56[0] = 80;
  v56[1] = 1;
  p_hHandle = 0;
  v61 = v31;
  v33 = v32 | 0x2000;
  LODWORD(v63) = DnsGlobals[63];
  LODWORD(v64) = v23;
  if ( (a4 & 0x60000000) == 0 )
    v33 = v32;
  DWORD1(v64) = v24;
  HIDWORD(v63) = v33;
  DWORD2(v64) = *(_DWORD *)(a2 + 64);
  if ( (v48 & 0x1000) != 0 )
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
    {
      LastError = GetLastError();
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SS(
          1035,
          29,
          (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids,
          *(_QWORD *)(a2 + 120),
          *(_QWORD *)a2);
      goto LABEL_53;
    }
    LODWORD(v55) = 1359;
    p_hHandle = &hHandle;
  }
  Areg_RegisterInit();
  LastError = Areg_RegisterAddrs((__int64)v56, v34, v35);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SSD(
      v36,
      30,
      (unsigned int)WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids,
      *(_QWORD *)(a2 + 120),
      *(_QWORD *)a2,
      LastError);
  if ( !LastError && (v48 & 0x1000) != 0 )
  {
    LODWORD(v38) = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 0x10) != 0 )
      v38 = GetTickCount64() / 0x3E8;
    LastError = 995;
    if ( !WaitForSingleObject(hHandle, 0xFFFFFFFF) )
      LastError = *((_DWORD *)p_hHandle + 2);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      TickCount64 = GetTickCount64();
      WPP_SF_SSdD(
        TickCount64 / 0x3E8 - v38,
        (TickCount64 * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64,
        v40,
        *(_QWORD *)(a2 + 120),
        *(_QWORD *)a2,
        TickCount64 / 0x3E8 - v38,
        LastError);
    }
  }
LABEL_53:
  if ( v13 != v53 )
    MIDL_user_free(v13);
LABEL_55:
  if ( hHandle )
    CloseHandle(hHandle);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 32, WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180027ef0  mov     [rsp-8+arg_18], rbx
0x180027ef5  push    rbp
0x180027ef6  push    rsi
0x180027ef7  push    rdi
0x180027ef8  push    r12
0x180027efa  push    r13
0x180027efc  push    r14
0x180027efe  push    r15
0x180027f00  lea     rbp, [rsp-50h]
0x180027f05  sub     rsp, 150h
0x180027f0c  mov     rax, cs:__security_cookie
0x180027f13  xor     rax, rsp
0x180027f16  mov     [rbp+80h+var_40], rax
0x180027f1a  mov     rsi, [rbp+80h+arg_20]
0x180027f21  mov     rbx, rdx
0x180027f24  xor     edx, edx; Val
0x180027f26  mov     dword ptr [rsp+180h+var_128], r8d
0x180027f2b  mov     r14d, r8d
0x180027f2e  mov     [rbp+80h+var_F8], rcx
0x180027f32  lea     rcx, [rbp+80h+var_D0]; void *
0x180027f36  mov     [rsp+180h+var_12C], r9d
0x180027f3b  mov     r15d, r9d
0x180027f3e  mov     [rbp+80h+var_F0], rsi
0x180027f42  lea     r8d, [rdx+50h]; Size
0x180027f46  call    memset_0
0x180027f4b  mov     r13d, 40h ; '@'
0x180027f51  lea     rcx, [rbp+80h+var_80]; void *
0x180027f55  mov     r8d, r13d; Size
0x180027f58  xor     edx, edx; Val
0x180027f5a  call    memset_0
0x180027f5f  mov     [rbp+80h+hHandle], 0
0x180027f67  mov     [rbp+80h+var_E0], 0
0x180027f6f  mov     r12b, 8
0x180027f72  lea     rdi, [rbx+78h]
0x180027f76  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x180027f7d  jnz     loc_18002851E
0x180027f83  mov     r11d, 40Bh
0x180027f89  test    rsi, rsi
0x180027f8c  jz      loc_1800282FE
0x180027f92  mov     r13, rsi
0x180027f95  mov     ecx, [rbx+38h]
0x180027f98  mov     [rsp+180h+var_120], 0
0x180027fa1  mov     [rsp+180h+var_130], 0
0x180027fa9  test    cl, 1
0x180027fac  jz      loc_180028324
0x180027fb2  mov     rax, cs:__imp_DnsGlobals
0x180027fb9  cmp     dword ptr [rax+0F4h], 0
0x180027fc0  jz      loc_180028485
0x180027fc6  mov     eax, ecx
0x180027fc8  mov     edx, 0Ah
0x180027fcd  mov     r10d, 220h
0x180027fd3  mov     r9b, 4
0x180027fd6  and     eax, 80h
0x180027fdb  jz      loc_1800282C1
0x180027fe1  test    r9b, cl
0x180027fe4  jz      loc_180028502
0x180027fea  xorps   xmm0, xmm0
0x180027fed  movups  [rsp+180h+var_118], xmm0
0x180027ff2  movups  [rsp+180h+var_108], xmm0
0x180027ff7  test    r15d, 10000002h
0x180027ffe  jz      loc_180028368
0x180028004  mov     eax, ecx
0x180028006  test    cl, cl
0x180028008  jns     loc_18002831D
0x18002800e  test    r9b, al
0x180028011  jz      loc_18002831D
0x180028017  mov     ecx, 1
0x18002801c  neg     ecx
0x18002801e  sbb     esi, esi
0x180028020  not     esi
0x180028022  and     esi, edx
0x180028024  bt      eax, 8
0x180028028  jnb     loc_1800282BA
0x18002802e  test    r10d, eax
0x180028031  jz      loc_1800282BA
0x180028037  mov     eax, 1
0x18002803c  neg     eax
0x18002803e  mov     rcx, rbx
0x180028041  sbb     edi, edi
0x180028043  not     edi
0x180028045  and     edi, edx
0x180028047  lea     rdx, [rsp+180h+var_118]
0x18002804c  call    reg_GetRegistrationInfoFromDhcp
0x180028051  test    eax, eax
0x180028053  jz      short loc_180028075
0x180028055  cmp     dword ptr [rsp+180h+var_108+4], 0
0x18002805a  cmovnz  esi, dword ptr [rbp+80h+var_108+0Ch]
0x18002805e  cmp     dword ptr [rsp+180h+var_118+4], 0
0x180028063  cmovnz  edi, dword ptr [rsp+180h+var_108]
0x180028068  test    r15d, 10001000h
0x18002806f  jz      loc_180028418
0x180028075  bt      r15d, 1Ch
0x18002807a  jnb     short loc_180028090
0x18002807c  bt      r14d, 8
0x180028081  jb      loc_180028360
0x180028087  bt      r14d, 9
0x18002808c  cmovb   edi, r14d
0x180028090  mov     rax, cs:__imp_DnsGlobals
0x180028097  mov     r12d, 2
0x18002809d  mov     ecx, [rax+114h]
0x1800280a3  test    ecx, ecx
0x1800280a5  jz      short loc_1800280C1
0x1800280a7  mov     eax, edi
0x1800280a9  mov     r14d, esi
0x1800280ac  and     eax, 40h
0x1800280af  and     r14d, 40h
0x1800280b3  jnz     loc_1800284D4
0x1800280b9  test    eax, eax
0x1800280bb  jnz     loc_1800284DC
0x1800280c1  mov     r15d, edi
0x1800280c4  and     r15d, 12h
0x1800280c8  or      r15d, esi
0x1800280cb  mov     r14d, r15d
0x1800280ce  and     r14d, 12h
0x1800280d2  or      r14d, edi
0x1800280d5  mov     dil, 60h ; '`'
0x1800280d8  mov     esi, r14d
0x1800280db  or      esi, r15d
0x1800280de  cmp     qword ptr [rbx+28h], 0
0x1800280e3  jz      short loc_1800280F1
0x1800280e5  test    dil, r15b
0x1800280e8  jnz     loc_180028606
0x1800280ee  and     esi, 0FFFFFF9Fh
0x1800280f1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800280f8  jnz     loc_180028614
0x1800280fe  test    [rbx+38h], r12b
0x180028102  jnz     loc_180028638
0x180028108  test    r13, r13
0x18002810b  jz      short loc_180028128
0x18002810d  mov     r8d, [r13+4]
0x180028111  lea     rcx, [r13+20h]; void *
0x180028115  shl     r8, 6; Size
0x180028119  xor     edx, edx; Val
0x18002811b  call    memset_0
0x180028120  mov     dword ptr [r13+4], 0
0x180028128  test    dil, sil
0x18002812b  jnz     short loc_180028167
0x18002812d  cmp     qword ptr [rbx+28h], 0
0x180028132  jz      loc_180028346
0x180028138  test    dil, r15b
0x18002813b  jnz     loc_180028676
0x180028141  xor     eax, eax
0x180028143  test    dil, r14b
0x180028146  jnz     loc_180028685
0x18002814c  mov     rdx, [rbx+20h]
0x180028150  mov     rcx, r13
0x180028153  mov     [rsp+180h+var_150], rax
0x180028158  call    DnsAddrArray_AppendArrayEx
0x18002815d  mov     edi, eax
0x18002815f  test    eax, eax
0x180028161  jnz     loc_1800286A2
0x180028167  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002816e  jnz     loc_1800286E8
0x180028174  mov     r8, r13
0x180028177  lea     rcx, aRegisterableAd; "Registerable addrs"
0x18002817e  xor     edx, edx
0x180028180  call    DnsPrint_DnsAddrArray
0x180028185  cmp     dword ptr [r13+4], 0
0x18002818a  jz      loc_180028717
0x180028190  mov     r12, r13
0x180028193  test    r13, r13
0x180028196  jz      loc_180028334
0x18002819c  mov     rax, [rbx]
0x18002819f  mov     edx, esi
0x1800281a1  mov     [rbp+80h+var_C0], rax
0x1800281a5  bts     edx, 1Ch
0x1800281a9  cmp     [rsp+180h+var_130], 0
0x1800281ae  xorps   xmm0, xmm0
0x1800281b1  mov     rax, [rbp+80h+var_F8]
0x1800281b5  mov     r10d, 1
0x1800281bb  cmovz   edx, esi
0x1800281be  movdqa  [rbp+80h+var_90], xmm0
0x1800281c3  mov     esi, dword ptr [rsp+180h+var_128]
0x1800281c7  mov     [rbp+80h+var_98], 0
0x1800281cf  mov     rax, [rax+18h]
0x1800281d3  mov     [rbp+80h+var_B8], rax
0x1800281d7  mov     rax, [rsp+180h+var_120]
0x1800281dc  mov     [rbp+80h+var_B0], rax
0x1800281e0  mov     rax, [rbx+28h]
0x1800281e4  mov     [rbp+80h+var_A0], rax
0x1800281e8  mov     rax, cs:__imp_DnsGlobals
0x1800281ef  mov     [rbp+80h+var_D0], 50h ; 'P'
0x1800281f6  mov     [rbp+80h+var_CC], r10d
0x1800281fa  mov     [rbp+80h+var_C8], 0
0x180028202  mov     [rbp+80h+var_A8], r12
0x180028206  mov     ecx, [rax+0FCh]
0x18002820c  mov     eax, edx
0x18002820e  bts     eax, 0Dh
0x180028212  mov     dword ptr [rbp+80h+var_98], ecx
0x180028215  test    [rsp+180h+var_12C], 60000000h
0x18002821d  mov     dword ptr [rbp+80h+var_90], r15d
0x180028221  cmovz   eax, edx
0x180028224  mov     dword ptr [rbp+80h+var_90+4], r14d
0x180028228  mov     dword ptr [rbp+80h+var_98+4], eax
0x18002822b  mov     eax, [rbx+40h]
0x18002822e  mov     dword ptr [rbp+80h+var_90+8], eax
0x180028231  and     esi, 1000h
0x180028237  jnz     loc_18002871F
0x18002823d  call    Areg_RegisterInit
0x180028242  lea     rcx, [rbp+80h+var_D0]
0x180028246  call    Areg_RegisterAddrs
0x18002824b  mov     edi, eax
0x18002824d  mov     r12b, 8
0x180028250  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x180028257  jnz     loc_18002878C
0x18002825d  test    edi, edi
0x18002825f  jnz     short loc_180028269
0x180028261  test    esi, esi
0x180028263  jnz     loc_18002839C
0x180028269  cmp     r13, [rbp+80h+var_F0]
0x18002826d  jz      short loc_180028277
0x18002826f  mov     rcx, r13; void *
0x180028272  call    MIDL_user_free
0x180028277  mov     rcx, [rbp+80h+hHandle]; hObject
0x18002827b  test    rcx, rcx
0x18002827e  jnz     loc_1800287DF
0x180028284  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x18002828b  jnz     loc_1800284B6
0x180028291  mov     eax, edi
0x180028293  mov     rcx, [rbp+80h+var_40]
0x180028297  xor     rcx, rsp; StackCookie
0x18002829a  call    __security_check_cookie
0x18002829f  mov     rbx, [rsp+180h+arg_18]
0x1800282a7  add     rsp, 150h
0x1800282ae  pop     r15
0x1800282b0  pop     r14
0x1800282b2  pop     r13
0x1800282b4  pop     r12
0x1800282b6  pop     rdi
0x1800282b7  pop     rsi
0x1800282b8  pop     rbp
0x1800282b9  retn
0x1800282ba  xor     eax, eax
0x1800282bc  jmp     loc_18002803C
0x1800282c1  bt      ecx, 8
0x1800282c5  jb      loc_180028599
0x1800282cb  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x1800282d2  jz      short loc_1800282F4
0x1800282d4  mov     rax, [rbx]
0x1800282d7  lea     r8, WPP_89c0ce7151693e3510dba17ca38838c1_Traceguids
0x1800282de  mov     r9, [rbx+78h]
0x1800282e2  mov     edx, 14h
0x1800282e7  mov     ecx, r11d
0x1800282ea  mov     [rsp+180h+var_160], rax
0x1800282ef  call    WPP_SF_SS
0x1800282f4  mov     edi, 267Bh
0x1800282f9  jmp     loc_180028269
0x1800282fe  mov     ecx, r13d
0x180028301  call    DnsAddrArray_Create
0x180028306  mov     r13, rax
0x180028309  test    rax, rax
0x18002830c  jz      loc_1800284AC
0x180028312  mov     r11d, 40Bh
0x180028318  jmp     loc_180027F95
0x18002831d  xor     ecx, ecx
0x18002831f  jmp     loc_18002801C
0x180028324  xor     r12d, r12d
0x180028327  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002832e  jnz     loc_180028550
0x180028334  mov     eax, 20h ; ' '
0x180028339  mov     esi, eax
0x18002833b  mov     r15d, eax
0x18002833e  mov     r14d, eax
0x180028341  jmp     loc_18002819C
0x180028346  mov     r12b, 8
0x180028349  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x180028350  jnz     loc_18002864F
0x180028356  mov     edi, 267Ch
0x18002835b  jmp     loc_180028269
0x180028360  mov     esi, r14d
0x180028363  jmp     loc_180028090
0x180028368  test    eax, eax
0x18002836a  jz      short loc_180028376
0x18002836c  test    [rbx+38h], r9b
0x180028370  jz      loc_180028004
0x180028376  bt      ecx, 8
0x18002837a  jnb     short loc_180028385
0x18002837c  test    r10d, ecx
0x18002837f  jz      loc_180028004
0x180028385  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x18002838c  jnz     loc_180028574
0x180028392  mov     edi, 57h ; 'W'
0x180028397  jmp     loc_180028269
0x18002839c  xor     esi, esi
0x18002839e  mov     r14, 624DD2F1A9FBE77h
0x1800283a8  test    byte ptr cs:xmmword_1800AB5A0+1, 10h
0x1800283af  jnz     loc_1800287B2
0x1800283b5  mov     rcx, [rbp+80h+hHandle]; hHandle
0x1800283b9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800283bc  mov     edi, 3E3h
0x1800283c1  call    cs:__imp_WaitForSingleObject
0x1800283c7  test    eax, eax
0x1800283c9  jz      loc_1800287D3
0x1800283cf  test    byte ptr cs:xmmword_1800AB5A0+1, r12b
0x1800283d6  jz      loc_180028269
0x1800283dc  call    cs:__imp_GetTickCount64
0x1800283e2  mov     r9, [rbx+78h]
0x1800283e6  mov     rcx, rax
0x1800283e9  mov     dword ptr [rsp+180h+var_150], edi
0x1800283ed  mov     rax, r14
  ... truncated ...
```
