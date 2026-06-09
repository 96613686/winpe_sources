# CNumInfo::Init(ulong,ulong,char * *)

- ea: `0x180003148`
- end: `0x180003648`
- name: `?Init@CNumInfo@@AEAAJKKPEAPEAD@Z`
- size: `1280`
- prototype: `int(CNumInfo *__hidden this, unsigned int, unsigned int, char **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180005988`

## callees

- `0x180003148`
- `0x1800044c4`
- `0x18004d900`
- `0x18004d924`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003308`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000333e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003377`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800033a2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800033d0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003414`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000344a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003308`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000333e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003377`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800033a2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800033d0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180003414`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000344a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800031a2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800031da`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800031fe`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003224`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000324a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003270`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800032ea`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000332c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003365`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003390`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800033be`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003402`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000343c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800031a2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800031da`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800031fe`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003224`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000324a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003270`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800032ea`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000332c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003365`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003390`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800033be`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180003402`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000343c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180003565`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180003586`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180003565`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180003586`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoA` at `0x1800032c4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoA` at `0x1800032c4`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18000348d`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18000348d`

## pseudocode

```c
__int64 __fastcall CNumInfo::Init(CNumInfo *this, unsigned __int64 a2, int a3, char **a4)
{
  LCID v6; // r14d
  WCHAR *v8; // r12
  int v9; // eax
  WCHAR v10; // ax
  int LocaleInfoW; // eax
  WCHAR v12; // dx
  __int16 v13; // ax
  int v14; // r12d
  int v15; // r13d
  int v16; // ecx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // eax
  int CacheUpdateCount; // eax
  char **v25; // rcx
  int v27; // ecx
  CHAR v28[8]; // [rsp+30h] [rbp-39h] BYREF
  char **v29; // [rsp+38h] [rbp-31h]
  WCHAR LCData; // [rsp+40h] [rbp-29h] BYREF
  WCHAR lpDestStr[12]; // [rsp+48h] [rbp-21h] BYREF
  WCHAR DestStr[12]; // [rsp+60h] [rbp-9h] BYREF

  v29 = a4;
  v6 = a2;
  if ( a3 == 0x80000000 && (_DWORD)a2 == 1033 )
  {
    *(_OWORD *)this = xmmword_1800ACAF0;
    *((_OWORD *)this + 1) = xmmword_1800ACB00;
    *((_OWORD *)this + 2) = xmmword_1800ACB10;
    *((_OWORD *)this + 3) = xmmword_1800ACB20;
    *((_OWORD *)this + 4) = xmmword_1800ACB30;
    *((_OWORD *)this + 5) = xmmword_1800ACB40;
    if ( *a4 )
    {
      operator delete(*a4, a2);
      *a4 = 0;
    }
    return 0;
  }
  v8 = (WCHAR *)((char *)this + 32);
  v9 = GetLocaleInfoW(a2, a3 | 0x14, (LPWSTR)this + 16, 10) - 1;
  if ( v9 > 0 )
  {
    *((_DWORD *)this + 6) = v9;
    *((_DWORD *)this + 7) = 0;
    if ( v9 != 1 )
      goto LABEL_5;
    LCMapStringW(v6, 0x400100u, v8, 1, DestStr, 1);
    LCMapStringW(v6, 0x800200u, v8, 1, lpDestStr, 1);
    if ( DestStr[0] != lpDestStr[0] )
      goto LABEL_5;
  }
  else
  {
    *v8 = 36;
    *((_DWORD *)this + 6) = 1;
  }
  *((_DWORD *)this + 7) = 1;
LABEL_5:
  if ( GetLocaleInfoW(v6, a3 | 0xE, &LCData, 4) > 1 )
    *((_WORD *)this + 26) = LCData;
  else
    *((_WORD *)this + 26) = 46;
  if ( GetLocaleInfoW(v6, a3 | 0x16, &LCData, 4) <= 1 )
    v10 = *((_WORD *)this + 26);
  else
    v10 = LCData;
  *((_WORD *)this + 31) = v10;
  if ( GetLocaleInfoW(v6, a3 | 0x51, &LCData, 4) <= 1 )
    *((_WORD *)this + 30) = 45;
  else
    *((_WORD *)this + 30) = LCData;
  if ( GetLocaleInfoW(v6, a3 | 0x17, &LCData, 4) <= 1 )
    *((_WORD *)this + 32) = 44;
  else
    *((_WORD *)this + 32) = LCData;
  LocaleInfoW = GetLocaleInfoW(v6, a3 | 0xF, &LCData, 4);
  v12 = 0;
  if ( LocaleInfoW > 1 )
    v12 = LCData;
  *((_WORD *)this + 27) = v12;
  if ( v12 == *((_WORD *)this + 26) )
    *((_WORD *)this + 27) = 0;
  if ( (unsigned int)IsCharType(v6) )
    v13 = 32;
  else
    v13 = *((_WORD *)this + 27);
  *((_WORD *)this + 28) = v13;
  v28[0] = 49;
  GetLocaleInfoA(v6, a3 | 0x12, v28, 2);
  *((_WORD *)this + 29) = v28[0] != 48;
  v14 = 0x2000;
  v15 = 3;
  if ( GetLocaleInfoW(v6, a3 | 0x10, &LCData, 4) <= 1 )
  {
    v17 = 0;
    v16 = 3;
  }
  else
  {
    v16 = _o__wtoi(&LCData);
    v17 = 0x2000;
  }
  *((_DWORD *)this + 17) = v16;
  *((_DWORD *)this + 18) = v17;
  if ( GetLocaleInfoW(v6, a3 | 0x18, &LCData, 4) <= 1 )
    v14 = 0;
  else
    v15 = _o__wtoi(&LCData);
  *((_DWORD *)this + 21) = v15;
  *((_DWORD *)this + 22) = v14;
  if ( GetLocaleInfoW(v6, a3 | 0x11, &LCData, 4) <= 1 )
    v18 = 0;
  else
    v18 = _o__wtoi(&LCData);
  *((_DWORD *)this + 20) = v18;
  if ( GetLocaleInfoW(v6, a3 | 0x19, &LCData, 4) <= 1 )
    v19 = 0;
  else
    v19 = _o__wtoi(&LCData);
  *((_DWORD *)this + 23) = v19;
  if ( GetLocaleInfoW(v6, a3 | 0x1010, &LCData, 4) <= 1 )
    v20 = 0;
  else
    v20 = _o__wtoi(&LCData);
  *((_DWORD *)this + 19) = v20;
  if ( v20 < 5 )
    *((_DWORD *)this + 18) |= dword_1800B2F10[v20];
  if ( GetLocaleInfoW(v6, a3 | 0x1C, &LCData, 4) <= 1 )
  {
    v21 = 0;
  }
  else
  {
    v21 = _o__wtoi(&LCData);
    if ( v21 >= 0x10 )
      goto LABEL_34;
  }
  *((_DWORD *)this + 22) |= dword_1800B2EC0[v21];
LABEL_34:
  if ( GetLocaleInfoW(v6, a3 | 0x1B, &LCData, 4) <= 1 )
  {
    v22 = 0;
LABEL_38:
    *((_DWORD *)this + 22) |= dword_1800B2F00[v22];
    goto LABEL_39;
  }
  v22 = _o__wtoi(&LCData);
  if ( v22 < 4 )
    goto LABEL_38;
LABEL_39:
  if ( *((_WORD *)this + 29) )
  {
    *((_DWORD *)this + 22) |= 1u;
    *((_DWORD *)this + 18) |= 1u;
  }
  v23 = *((_DWORD *)this + 22);
  if ( (v23 & 2) != 0 )
  {
    v27 = *((_DWORD *)this + 18);
    if ( (v27 & 2) != 0 )
    {
      *((_DWORD *)this + 18) = v27 | 4;
      *((_DWORD *)this + 22) = v23 | 4;
    }
    else
    {
      *((_DWORD *)this + 22) = v23 | *((_DWORD *)this + 18) & 0x3C;
    }
  }
  else if ( (*((_BYTE *)this + 72) & 2) != 0 )
  {
    *((_DWORD *)this + 18) |= *((_DWORD *)this + 22) & 0x3C;
  }
  *((_DWORD *)this + 4) = v6;
  *((_DWORD *)this + 5) = a3;
  CacheUpdateCount = NlsGetCacheUpdateCount();
  v25 = v29;
  *(_DWORD *)this = CacheUpdateCount;
  *((_QWORD *)this + 1) = *v25;
  *v25 = 0;
  return 0;
}

```

## disassembly

```asm
0x180003148  push    rbp
0x18000314a  push    rbx
0x18000314b  push    rsi
0x18000314c  push    rdi
0x18000314d  push    r12
0x18000314f  push    r13
0x180003151  push    r14
0x180003153  push    r15
0x180003155  lea     rbp, [rsp-1Fh]
0x18000315a  sub     rsp, 88h
0x180003161  mov     rax, cs:__security_cookie
0x180003168  xor     rax, rsp
0x18000316b  mov     [rbp+57h+var_48], rax
0x18000316f  mov     [rbp+57h+var_88], r9
0x180003173  mov     rdi, r9
0x180003176  mov     r15d, r8d
0x180003179  mov     r14d, edx
0x18000317c  mov     rbx, rcx
0x18000317f  cmp     r8d, 80000000h
0x180003186  jz      loc_1800035B8
0x18000318c  lea     r12, [rcx+20h]
0x180003190  mov     edx, r15d
0x180003193  or      edx, 14h; LCType
0x180003196  mov     r8, r12; lpLCData
0x180003199  mov     r9d, 0Ah; cchData
0x18000319f  mov     ecx, r14d; Locale
0x1800031a2  call    cs:__imp_GetLocaleInfoW
0x1800031a8  xor     esi, esi
0x1800031aa  dec     eax
0x1800031ac  lea     edi, [rsi+1]
0x1800031af  test    eax, eax
0x1800031b1  jg      loc_18000353C
0x1800031b7  mov     word ptr [r12], 24h ; '$'
0x1800031be  mov     [rbx+18h], edi
0x1800031c1  mov     [rbx+1Ch], edi
0x1800031c4  mov     edx, r15d
0x1800031c7  lea     r8, [rbp+57h+LCData]; lpLCData
0x1800031cb  mov     r12d, 4
0x1800031d1  or      edx, 0Eh; LCType
0x1800031d4  mov     r9d, r12d; cchData
0x1800031d7  mov     ecx, r14d; Locale
0x1800031da  call    cs:__imp_GetLocaleInfoW
0x1800031e0  cmp     eax, edi
0x1800031e2  jg      loc_1800034C5
0x1800031e8  mov     word ptr [rbx+34h], 2Eh ; '.'
0x1800031ee  mov     edx, r15d
0x1800031f1  lea     r8, [rbp+57h+LCData]; lpLCData
0x1800031f5  or      edx, 16h; LCType
0x1800031f8  mov     r9d, r12d; cchData
0x1800031fb  mov     ecx, r14d; Locale
0x1800031fe  call    cs:__imp_GetLocaleInfoW
0x180003204  cmp     eax, edi
0x180003206  jle     loc_180003514
0x18000320c  movzx   eax, [rbp+57h+LCData]
0x180003210  mov     edx, r15d
0x180003213  mov     [rbx+3Eh], ax
0x180003217  or      edx, 51h; LCType
0x18000321a  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000321e  mov     r9d, r12d; cchData
0x180003221  mov     ecx, r14d; Locale
0x180003224  call    cs:__imp_GetLocaleInfoW
0x18000322a  cmp     eax, edi
0x18000322c  jle     loc_18000351D
0x180003232  movzx   eax, [rbp+57h+LCData]
0x180003236  mov     [rbx+3Ch], ax
0x18000323a  mov     edx, r15d
0x18000323d  lea     r8, [rbp+57h+LCData]; lpLCData
0x180003241  or      edx, 17h; LCType
0x180003244  mov     r9d, r12d; cchData
0x180003247  mov     ecx, r14d; Locale
0x18000324a  call    cs:__imp_GetLocaleInfoW
0x180003250  cmp     eax, edi
0x180003252  jle     loc_1800034F6
0x180003258  movzx   eax, [rbp+57h+LCData]
0x18000325c  mov     [rbx+40h], ax
0x180003260  mov     edx, r15d
0x180003263  lea     r8, [rbp+57h+LCData]; lpLCData
0x180003267  or      edx, 0Fh; LCType
0x18000326a  mov     r9d, r12d; cchData
0x18000326d  mov     ecx, r14d; Locale
0x180003270  call    cs:__imp_GetLocaleInfoW
0x180003276  movzx   edx, si
0x180003279  cmp     eax, edi
0x18000327b  jle     short loc_180003281
0x18000327d  movzx   edx, [rbp+57h+LCData]
0x180003281  mov     [rbx+36h], dx
0x180003285  cmp     dx, [rbx+34h]
0x180003289  jz      loc_180003620
0x18000328f  mov     r8d, 8
0x180003295  mov     ecx, r14d; Locale
0x180003298  call    IsCharType
0x18000329d  test    eax, eax
0x18000329f  jnz     loc_180003532
0x1800032a5  movzx   eax, word ptr [rbx+36h]
0x1800032a9  mov     edx, r15d
0x1800032ac  mov     [rbx+38h], ax
0x1800032b0  or      edx, 12h; LCType
0x1800032b3  mov     [rbp+57h+var_90], 31h ; '1'
0x1800032b7  mov     r9d, 2; cchData
0x1800032bd  lea     r8, [rbp+57h+var_90]; lpLCData
0x1800032c1  mov     ecx, r14d; Locale
0x1800032c4  call    cs:__imp_GetLocaleInfoA
0x1800032ca  cmp     [rbp+57h+var_90], 30h ; '0'
0x1800032ce  jz      loc_1800034D2
0x1800032d4  mov     eax, edi
0x1800032d6  mov     edx, r15d
0x1800032d9  mov     [rbx+3Ah], ax
0x1800032dd  or      edx, 10h; LCType
0x1800032e0  lea     r8, [rbp+57h+LCData]; lpLCData
0x1800032e4  mov     r9d, r12d; cchData
0x1800032e7  mov     ecx, r14d; Locale
0x1800032ea  call    cs:__imp_GetLocaleInfoW
0x1800032f0  mov     r12d, 2000h
0x1800032f6  mov     r13d, 3
0x1800032fc  cmp     eax, edi
0x1800032fe  jle     loc_180003528
0x180003304  lea     rcx, [rbp+57h+LCData]
0x180003308  call    cs:__imp__o__wtoi
0x18000330e  mov     ecx, eax
0x180003310  mov     eax, r12d
0x180003313  mov     [rbx+44h], ecx
0x180003316  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000331a  mov     edx, r15d
0x18000331d  mov     [rbx+48h], eax
0x180003320  or      edx, 18h; LCType
0x180003323  mov     r9d, 4; cchData
0x180003329  mov     ecx, r14d; Locale
0x18000332c  call    cs:__imp_GetLocaleInfoW
0x180003332  cmp     eax, edi
0x180003334  jle     loc_180003501
0x18000333a  lea     rcx, [rbp+57h+LCData]
0x18000333e  call    cs:__imp__o__wtoi
0x180003344  mov     r13d, eax
0x180003347  mov     [rbx+54h], r13d
0x18000334b  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000334f  mov     [rbx+58h], r12d
0x180003353  mov     edx, r15d
0x180003356  mov     r12d, 4
0x18000335c  or      edx, 11h; LCType
0x18000335f  mov     r9d, r12d; cchData
0x180003362  mov     ecx, r14d; Locale
0x180003365  call    cs:__imp_GetLocaleInfoW
0x18000336b  cmp     eax, edi
0x18000336d  jle     loc_1800034DA
0x180003373  lea     rcx, [rbp+57h+LCData]
0x180003377  call    cs:__imp__o__wtoi
0x18000337d  mov     edx, r15d
0x180003380  mov     [rbx+50h], eax
0x180003383  or      edx, 19h; LCType
0x180003386  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000338a  mov     r9d, r12d; cchData
0x18000338d  mov     ecx, r14d; Locale
0x180003390  call    cs:__imp_GetLocaleInfoW
0x180003396  cmp     eax, edi
0x180003398  jle     loc_1800034E1
0x18000339e  lea     rcx, [rbp+57h+LCData]
0x1800033a2  call    cs:__imp__o__wtoi
0x1800033a8  mov     edx, r15d
0x1800033ab  mov     [rbx+5Ch], eax
0x1800033ae  or      edx, 1010h; LCType
0x1800033b4  lea     r8, [rbp+57h+LCData]; lpLCData
0x1800033b8  mov     r9d, r12d; cchData
0x1800033bb  mov     ecx, r14d; Locale
0x1800033be  call    cs:__imp_GetLocaleInfoW
0x1800033c4  cmp     eax, edi
0x1800033c6  jle     loc_1800034E8
0x1800033cc  lea     rcx, [rbp+57h+LCData]
0x1800033d0  call    cs:__imp__o__wtoi
0x1800033d6  mov     [rbx+4Ch], eax
0x1800033d9  lea     r13, __ImageBase
0x1800033e0  cmp     eax, 5
0x1800033e3  jnb     short loc_1800033F2
0x1800033e5  cdqe
0x1800033e7  mov     eax, ds:rva dword_1800B2F10[r13+rax*4]
0x1800033ef  or      [rbx+48h], eax
0x1800033f2  mov     edx, r15d
0x1800033f5  lea     r8, [rbp+57h+LCData]; lpLCData
0x1800033f9  or      edx, 1Ch; LCType
0x1800033fc  mov     r9d, r12d; cchData
0x1800033ff  mov     ecx, r14d; Locale
0x180003402  call    cs:__imp_GetLocaleInfoW
0x180003408  cmp     eax, edi
0x18000340a  jle     loc_1800034EF
0x180003410  lea     rcx, [rbp+57h+LCData]
0x180003414  call    cs:__imp__o__wtoi
0x18000341a  cmp     eax, 10h
0x18000341d  jnb     short loc_18000342C
0x18000341f  cdqe
0x180003421  mov     eax, ds:rva dword_1800B2EC0[r13+rax*4]
0x180003429  or      [rbx+58h], eax
0x18000342c  mov     edx, r15d
0x18000342f  lea     r8, [rbp+57h+LCData]; lpLCData
0x180003433  or      edx, 1Bh; LCType
0x180003436  mov     r9d, r12d; cchData
0x180003439  mov     ecx, r14d; Locale
0x18000343c  call    cs:__imp_GetLocaleInfoW
0x180003442  cmp     eax, edi
0x180003444  jle     short loc_180003457
0x180003446  lea     rcx, [rbp+57h+LCData]
0x18000344a  call    cs:__imp__o__wtoi
0x180003450  cmp     eax, r12d
0x180003453  jnb     short loc_180003466
0x180003455  jmp     short loc_180003459
0x180003457  mov     eax, esi
0x180003459  cdqe
0x18000345b  mov     eax, ds:rva dword_1800B2F00[r13+rax*4]
0x180003463  or      [rbx+58h], eax
0x180003466  cmp     [rbx+3Ah], si
0x18000346a  jnz     loc_180003509
0x180003470  mov     eax, [rbx+58h]
0x180003473  test    al, 2
0x180003475  jnz     loc_18000359F
0x18000347b  test    byte ptr [rbx+48h], 2
0x18000347f  jnz     loc_18000362C
0x180003485  mov     [rbx+10h], r14d
0x180003489  mov     [rbx+14h], r15d
0x18000348d  call    cs:__imp_NlsGetCacheUpdateCount
0x180003493  mov     rcx, [rbp+57h+var_88]
0x180003497  mov     [rbx], eax
0x180003499  mov     rax, [rcx]
0x18000349c  mov     [rbx+8], rax
0x1800034a0  mov     [rcx], rsi
0x1800034a3  xor     eax, eax
0x1800034a5  mov     rcx, [rbp+57h+var_48]
0x1800034a9  xor     rcx, rsp; StackCookie
0x1800034ac  call    __security_check_cookie
0x1800034b1  add     rsp, 88h
0x1800034b8  pop     r15
0x1800034ba  pop     r14
0x1800034bc  pop     r13
0x1800034be  pop     r12
0x1800034c0  pop     rdi
0x1800034c1  pop     rsi
0x1800034c2  pop     rbx
0x1800034c3  pop     rbp
0x1800034c4  retn
0x1800034c5  movzx   eax, [rbp+57h+LCData]
0x1800034c9  mov     [rbx+34h], ax
0x1800034cd  jmp     loc_1800031EE
0x1800034d2  movzx   eax, si
0x1800034d5  jmp     loc_1800032D6
0x1800034da  mov     eax, esi
0x1800034dc  jmp     loc_18000337D
0x1800034e1  mov     eax, esi
0x1800034e3  jmp     loc_1800033A8
0x1800034e8  mov     eax, esi
0x1800034ea  jmp     loc_1800033D6
0x1800034ef  mov     eax, esi
0x1800034f1  jmp     loc_18000341F
0x1800034f6  mov     word ptr [rbx+40h], 2Ch ; ','
0x1800034fc  jmp     loc_180003260
0x180003501  mov     r12d, esi
0x180003504  jmp     loc_180003347
0x180003509  or      [rbx+58h], edi
0x18000350c  or      [rbx+48h], edi
0x18000350f  jmp     loc_180003470
0x180003514  movzx   eax, word ptr [rbx+34h]
0x180003518  jmp     loc_180003210
0x18000351d  mov     word ptr [rbx+3Ch], 2Dh ; '-'
0x180003523  jmp     loc_18000323A
0x180003528  mov     eax, esi
0x18000352a  mov     ecx, r13d
0x18000352d  jmp     loc_180003313
0x180003532  mov     eax, 20h ; ' '
0x180003537  jmp     loc_1800032A9
0x18000353c  mov     [rbx+18h], eax
0x18000353f  mov     [rbx+1Ch], esi
0x180003542  cmp     eax, edi
0x180003544  jnz     loc_1800031C4
0x18000354a  lea     rax, [rbp+57h+DestStr]
0x18000354e  mov     [rsp+0C0h+cchDest], edi; cchDest
0x180003552  mov     r9d, edi; cchSrc
0x180003555  mov     [rsp+0C0h+lpDestStr], rax; lpDestStr
0x18000355a  mov     r8, r12; lpSrcStr
0x18000355d  mov     edx, 400100h; dwMapFlags
0x180003562  mov     ecx, r14d; Locale
0x180003565  call    cs:__imp_LCMapStringW
0x18000356b  lea     rax, [rbp+57h+var_78]
0x18000356f  mov     [rsp+0C0h+cchDest], edi; cchDest
0x180003573  mov     r9d, edi; cchSrc
0x180003576  mov     [rsp+0C0h+lpDestStr], rax; lpDestStr
0x18000357b  mov     r8, r12; lpSrcStr
0x18000357e  mov     edx, 800200h; dwMapFlags
0x180003583  mov     ecx, r14d; Locale
0x180003586  call    cs:__imp_LCMapStringW
0x18000358c  movzx   eax, [rbp+57h+var_78]
0x180003590  cmp     [rbp+57h+DestStr], ax
0x180003594  jz      loc_1800031C1
0x18000359a  jmp     loc_1800031C4
0x18000359f  mov     ecx, [rbx+48h]
0x1800035a2  test    cl, 2
0x1800035a5  jnz     loc_180003637
0x1800035ab  and     ecx, 3Ch
0x1800035ae  or      ecx, eax
0x1800035b0  mov     [rbx+58h], ecx
0x1800035b3  jmp     loc_180003485
0x1800035b8  cmp     edx, 409h
0x1800035be  jnz     loc_18000318C
0x1800035c4  movaps  xmm0, cs:xmmword_1800ACAF0
0x1800035cb  xor     esi, esi
  ... truncated ...
```
