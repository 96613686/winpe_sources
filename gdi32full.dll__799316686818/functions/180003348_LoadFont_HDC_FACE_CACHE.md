# LoadFont(HDC__ *,FACE_CACHE *)

- ea: `0x180003348`
- end: `0x18000391c`
- name: `?LoadFont@@YAJPEAUHDC__@@PEAUFACE_CACHE@@@Z`
- size: `1492`
- prototype: `__int64 __fastcall(HDC hdc, struct FACE_CACHE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800030d4`

## callees

- `0x180001ef8`
- `0x180002750`
- `0x180003348`
- `0x180004660`
- `0x1800055d0`
- `0x180009d00`
- `0x180015c70`
- `0x18002c6c8`
- `0x18002d138`
- `0x18003aea0`
- `0x18003b11c`
- `0x18004cbb4`
- `0x18005212c`
- `0x180054ec4`
- `0x180059bb0`
- `0x180068fa0`
- `0x180077794`
- `0x1800796cc`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000352b`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180003538`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000352b`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180003538`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18000371e`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18000371e`
- `win32u!NtGdiFontIsLinked` at `0x18000350b`
- `win32u!NtGdiFontIsLinked` at `0x18000350b`

## pseudocode

```c
__int64 __fastcall LoadFont(HDC hdc, struct FACE_CACHE *a2)
{
  struct FONTCMAPDESC *v4; // rdi
  __int64 v5; // rdx
  int v6; // r13d
  unsigned int v7; // r8d
  __int64 v8; // rcx
  int v9; // eax
  int *v10; // rsi
  __int16 v11; // ax
  __int64 result; // rax
  int IsLinked; // eax
  __int16 v14; // cx
  wchar_t *v15; // r11
  wchar_t *v16; // r11
  __int16 v17; // ax
  int FontDetails; // esi
  _DWORD *v19; // r14
  int UvsTable; // eax
  int v21; // r9d
  unsigned __int64 v22; // rcx
  union FONTUVSENTRY **v23; // r15
  union FONTUVSENTRY *v24; // rcx
  __int16 UserDefaultLCID; // ax
  unsigned __int64 v26; // rcx
  unsigned __int16 v27; // dx
  unsigned __int16 v28; // dx
  unsigned __int16 v29; // dx
  LPVOID *v30; // rdi
  int Data; // eax
  __int64 v32; // rsi
  char *v33; // rax
  unsigned __int16 *v34; // rdx
  __int16 v35; // r9
  unsigned __int16 v36; // cx
  unsigned __int16 v37; // ax
  int v38; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  struct FONTCMAPDESC *v40; // [rsp+38h] [rbp-C8h] BYREF
  void *v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v43[740]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v44; // [rsp+338h] [rbp+238h]
  _DWORD v45[17]; // [rsp+33Ch] [rbp+23Ch]
  unsigned __int8 v46[16]; // [rsp+380h] [rbp+280h] BYREF
  __int128 v47; // [rsp+390h] [rbp+290h]
  unsigned __int8 v48[544]; // [rsp+3A0h] [rbp+2A0h] BYREF

  memset_0(v48, 0, sizeof(v48));
  v40 = 0;
  v39 = 0;
  v41 = 0;
  *(_OWORD *)v46 = 0;
  v4 = 0;
  v47 = 0;
  memset_0(v43, 0, 0x328u);
  v42 = 812;
  v6 = 1;
  if ( (unsigned int)GetFontRealizationInfo(hdc, &v42) )
  {
    v7 = v44;
    v5 = 0;
    for ( *((_DWORD *)a2 + 543) = v44; (unsigned int)v5 < v7; *((_WORD *)a2 + v8 + 1088) = (v9 + 2) >> 2 )
    {
      v8 = (unsigned int)v5;
      v5 = (unsigned int)(v5 + 1);
      v9 = v45[v8];
      *((_DWORD *)a2 + v8 + 552) = v9;
    }
  }
  else
  {
    *((_DWORD *)a2 + 543) = 0;
  }
  *((_WORD *)a2 + 84) &= 0xFBF7u;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full>::GetImpl'::`2'::impl,
                          v5) )
    *((_WORD *)a2 + 85) = 0;
  else
    *((_WORD *)a2 + 84) &= 0xFC0Fu;
  if ( (*((_BYTE *)a2 + 157) & 0xC) != 8 || IsFontCffOrMM(hdc) )
  {
    v10 = (int *)((char *)a2 + 160);
    if ( v43[0] == 3 )
    {
      GetFontDesc(hdc, (int *)a2 + 40, &v40);
      v4 = v40;
    }
    else
    {
      *v10 = -2;
    }
  }
  else
  {
    v10 = (int *)((char *)a2 + 160);
    *((_DWORD *)a2 + 40) = -3;
  }
  if ( *v10 < -2 )
  {
    *((_DWORD *)a2 + 79) = 0;
    *((_WORD *)a2 + 84) &= 0xFFF8u;
    v11 = (unsigned __int8)*((_WORD *)a2 + 76);
    *((_WORD *)a2 + 140) = 32;
    *((_WORD *)a2 + 141) = v11;
    result = 0;
    *((_WORD *)a2 + 153) = -1;
    *((_DWORD *)a2 + 41) = 0;
    *((_OWORD *)a2 + 20) = 0;
    return result;
  }
  IsLinked = NtGdiFontIsLinked(hdc);
  v14 = *((_WORD *)a2 + 84);
  if ( IsLinked )
  {
    *((_WORD *)a2 + 84) = v14 | 1;
    if ( GetACP() != 932 && GetACP() != 949
      || (unsigned int)UnicodeCmp((wchar_t *)a2 + 10, (wchar_t *)L"Microsoft Sans Serif")
      && (unsigned int)UnicodeCmp(v15, (wchar_t *)L"Tahoma")
      && (unsigned int)UnicodeCmp(v16, (wchar_t *)L"Tahoma Bold") )
    {
      v17 = 0;
    }
    else
    {
      v17 = 2;
    }
    *((_WORD *)a2 + 84) &= ~2u;
    *((_WORD *)a2 + 84) |= v17;
    if ( gFontLinkingData == (wchar_t *)-1LL )
    {
      if ( (unsigned int)IsFontRegLinked((wchar_t *)a2 + 10) )
        *((_WORD *)a2 + 84) |= 8u;
      *((_WORD *)a2 + 84) |= 0x400u;
    }
  }
  else
  {
    *((_WORD *)a2 + 84) = v14 & 0xFBFC | 0x400;
  }
  FontDetails = GetFontDetails(hdc, a2, v48, v46, v4);
  if ( FontDetails < 0 )
    goto LABEL_30;
  FontDetails = AllocateCMAPtables(a2, v48, v46, &v39);
  if ( FontDetails < 0 )
    goto LABEL_30;
  FontDetails = FillCMAP(hdc, v4, v46, a2);
  if ( FontDetails < 0 )
    goto LABEL_30;
  v19 = (_DWORD *)((char *)a2 + 2168);
  UvsTable = LoadUvsTable(v4, 0, (unsigned int *)a2 + 542);
  FontDetails = UvsTable;
  if ( UvsTable < 0 )
    goto LABEL_30;
  if ( UvsTable || !*v19 )
  {
    *((_QWORD *)a2 + 270) = 0;
    *v19 = 0;
    goto LABEL_49;
  }
  v22 = 10LL * (unsigned int)*v19;
  if ( v22 > 0xFFFFFFFF || (unsigned int)v22 > 0x7FFFFFFF )
  {
    FontDetails = -2147024362;
LABEL_30:
    if ( v4 )
      UspFreeMem(v4);
    return (unsigned int)FontDetails;
  }
  v23 = (union FONTUVSENTRY **)((char *)a2 + 2160);
  FontDetails = UspAllocCache(v22, (char *)a2 + 2160);
  if ( FontDetails < 0 )
    goto LABEL_30;
  FontDetails = LoadUvsTable(v4, *v23, (unsigned int *)a2 + 542);
  if ( FontDetails )
  {
    if ( v4 )
      UspFreeMem(v4);
    v24 = *v23;
    *v19 = 0;
    UspFreeMem(v24);
    if ( FontDetails >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)FontDetails;
  }
LABEL_49:
  if ( v4 )
    UspFreeMem(v4);
  if ( gfLocaleInitialized )
  {
    v26 = (unsigned int)gfArabicLocale;
  }
  else
  {
    UserDefaultLCID = GetUserDefaultLCID();
    gfLocaleInitialized = 1;
    UserDefaultLCID &= 0x3FFu;
    v26 = UserDefaultLCID == 1;
    gfArabicLocale = UserDefaultLCID == 1;
  }
  if ( (_DWORD)v26 )
  {
    v26 = *((_QWORD *)a2 + 40);
    v27 = *(_WORD *)(v26 + 2 * (((unsigned __int64)*(unsigned __int16 *)(v26 + 12) << 8) | 0xC));
    if ( !v27 )
      v27 = *(_WORD *)(v26 + 2 * (((unsigned __int64)*(unsigned __int16 *)v26 << 8) | 0x2C));
    *((_WORD *)a2 + 154) = v27;
    v28 = *(_WORD *)(v26 + 2 * (((unsigned __int64)*(unsigned __int16 *)(v26 + 12) << 8) | 0x1B));
    if ( !v28 )
      v28 = *(_WORD *)(v26 + 2 * (((unsigned __int64)*(unsigned __int16 *)v26 << 8) | 0x3B));
    *((_WORD *)a2 + 155) = v28;
    v29 = *(_WORD *)(v26 + 2 * (((unsigned __int64)*(unsigned __int16 *)(v26 + 12) << 8) | 0x1F));
    if ( v29 )
      *((_WORD *)a2 + 156) = v29;
    else
      *((_WORD *)a2 + 156) = *(_WORD *)(v26 + 2 * (((unsigned __int64)*(unsigned __int16 *)v26 << 8) | 0x3F));
  }
  if ( !gfUnistorInitialized )
    InitUnistor();
  v30 = (LPVOID *)((char *)a2 + 320);
  if ( ghUniStore && (Data = UniStorFindData((void *)v26, *v30, v39, v21, v38, &v41), Data >= 0) )
  {
    v32 = (__int64)(*((_QWORD *)a2 + 41) - (_QWORD)*v30) >> 1;
    if ( !Data )
      UspFreeMem(*v30);
    v33 = (char *)v41;
    *v30 = v41;
    *((_QWORD *)a2 + 41) = &v33[2 * v32];
  }
  else
  {
    v6 = 0;
  }
  *((_DWORD *)a2 + 538) = v6;
  v34 = (unsigned __int16 *)*v30;
  v35 = *((_WORD *)a2 + 141);
  *((_WORD *)a2 + 140) = *((_WORD *)*v30 + (((unsigned __int64)*(unsigned __int16 *)*v30 << 8) | 0x20));
  v36 = v34[((unsigned __int64)v34[247] << 8) | 0x1B];
  *((_WORD *)a2 + 142) = v36;
  if ( v36 == v35 )
  {
    v37 = v34[((unsigned __int64)v34[32] << 8) | 0xB];
    *((_WORD *)a2 + 142) = v37;
    if ( v37 == v35 )
      *((_WORD *)a2 + 142) = v34[((unsigned __int64)*v34 << 8) | 0x20];
  }
  GetFontKashidaInfo(hdc, a2);
  result = CheckUpdateFontDescriptor(hdc, a2);
  if ( (int)result >= 0 )
    return ShlLoadFont(hdc, a2);
  return result;
}

```

## disassembly

```asm
0x180003348  mov     [rsp-8+arg_10], rbx
0x18000334d  push    rbp
0x18000334e  push    rsi
0x18000334f  push    rdi
0x180003350  push    r12
0x180003352  push    r13
0x180003354  push    r14
0x180003356  push    r15
0x180003358  lea     rbp, [rsp-4D0h]
0x180003360  sub     rsp, 5D0h
0x180003367  mov     rax, cs:__security_cookie
0x18000336e  xor     rax, rsp
0x180003371  mov     [rbp+500h+var_40], rax
0x180003378  mov     rbx, rdx
0x18000337b  mov     r12, rcx
0x18000337e  xor     edx, edx; Val
0x180003380  lea     rcx, [rbp+500h+var_260]; void *
0x180003387  mov     r8d, 220h; Size
0x18000338d  call    memset_0
0x180003392  xor     r15d, r15d
0x180003395  lea     rcx, [rsp+600h+var_5AC]; void *
0x18000339a  xorps   xmm0, xmm0
0x18000339d  mov     [rsp+600h+var_5C8], r15
0x1800033a2  xor     edx, edx; Val
0x1800033a4  mov     [rsp+600h+var_5D0], r15d
0x1800033a9  mov     r8d, 328h; Size
0x1800033af  mov     [rsp+600h+var_5C0], r15
0x1800033b4  movups  xmmword ptr [rbp+500h+var_280], xmm0
0x1800033bb  mov     edi, r15d
0x1800033be  movups  [rbp+500h+var_270], xmm0
0x1800033c5  call    memset_0
0x1800033ca  lea     rdx, [rsp+600h+var_5B0]
0x1800033cf  mov     [rsp+600h+var_5B0], 32Ch
0x1800033d7  mov     rcx, r12
0x1800033da  call    GetFontRealizationInfo
0x1800033df  lea     r13d, [r15+1]
0x1800033e3  test    eax, eax
0x1800033e5  jnz     short loc_1800033F0
0x1800033e7  mov     [rbx+87Ch], r15d
0x1800033ee  jmp     short loc_18000342C
0x1800033f0  mov     r8d, [rbp+500h+var_2C8]
0x1800033f7  mov     edx, r15d
0x1800033fa  mov     [rbx+87Ch], r8d
0x180003401  test    r8d, r8d
0x180003404  jz      short loc_18000342C
0x180003406  mov     ecx, edx
0x180003408  add     edx, r13d
0x18000340b  mov     eax, [rbp+rcx*4+500h+var_2C4]
0x180003412  mov     [rbx+rcx*4+8A0h], eax
0x180003419  add     eax, 2
0x18000341c  sar     eax, 2
0x18000341f  mov     [rbx+rcx*2+880h], ax
0x180003427  cmp     edx, r8d
0x18000342a  jb      short loc_180003406
0x18000342c  mov     eax, 0FBF7h
0x180003431  and     [rbx+0A8h], ax
0x180003438  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full> `wil::Feature<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full>::GetImpl(void)'::`2'::impl
0x18000343f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full>::__private_IsEnabled(void)
0x180003444  test    al, al
0x180003446  jz      short loc_180003452
0x180003448  mov     [rbx+0AAh], r15w
0x180003450  jmp     short loc_18000345E
0x180003452  mov     eax, 0FC0Fh
0x180003457  and     [rbx+0A8h], ax
0x18000345e  mov     al, [rbx+9Dh]
0x180003464  and     al, 0Ch
0x180003466  cmp     al, 8
0x180003468  jnz     short loc_180003485
0x18000346a  mov     rcx, r12; hdc
0x18000346d  call    ?IsFontCffOrMM@@YAEPEAUHDC__@@@Z; IsFontCffOrMM(HDC__ *)
0x180003472  test    al, al
0x180003474  jnz     short loc_180003485
0x180003476  lea     rsi, [rbx+0A0h]
0x18000347d  mov     dword ptr [rsi], 0FFFFFFFDh
0x180003483  jmp     short loc_1800034B0
0x180003485  cmp     [rsp+600h+var_5AC], 3
0x18000348a  lea     rsi, [rbx+0A0h]
0x180003491  jz      short loc_18000349B
0x180003493  mov     dword ptr [rsi], 0FFFFFFFEh
0x180003499  jmp     short loc_1800034B0
0x18000349b  lea     r8, [rsp+600h+var_5C8]; struct FONTCMAPDESC **
0x1800034a0  mov     rdx, rsi; int *
0x1800034a3  mov     rcx, r12; hdc
0x1800034a6  call    ?GetFontDesc@@YAJPEAUHDC__@@PEAHPEAPEAUFONTCMAPDESC@@@Z; GetFontDesc(HDC__ *,int *,FONTCMAPDESC * *)
0x1800034ab  mov     rdi, [rsp+600h+var_5C8]
0x1800034b0  cmp     dword ptr [rsi], 0FFFFFFFEh
0x1800034b3  jge     short loc_180003508
0x1800034b5  mov     eax, 0FFF8h
0x1800034ba  mov     [rbx+13Ch], r15d
0x1800034c1  and     [rbx+0A8h], ax
0x1800034c8  mov     ecx, 0FFh
0x1800034cd  movzx   eax, word ptr [rbx+98h]
0x1800034d4  xorps   xmm0, xmm0
0x1800034d7  and     ax, cx
0x1800034da  mov     word ptr [rbx+118h], 20h ; ' '
0x1800034e3  mov     [rbx+11Ah], ax
0x1800034ea  xor     eax, eax
0x1800034ec  mov     word ptr [rbx+132h], 0FFFFh
0x1800034f5  mov     [rbx+0A4h], r15d
0x1800034fc  movups  xmmword ptr [rbx+140h], xmm0
0x180003503  jmp     loc_1800038F2
0x180003508  mov     rcx, r12
0x18000350b  call    cs:__imp_NtGdiFontIsLinked
0x180003511  movzx   ecx, word ptr [rbx+0A8h]
0x180003518  test    eax, eax
0x18000351a  jz      loc_1800035CC
0x180003520  or      cx, r13w
0x180003524  mov     [rbx+0A8h], cx
0x18000352b  call    cs:__imp_GetACP
0x180003531  cmp     eax, 3A4h
0x180003536  jz      short loc_180003545
0x180003538  call    cs:__imp_GetACP
0x18000353e  cmp     eax, 3B5h
0x180003543  jnz     short loc_180003582
0x180003545  lea     r11, [rbx+14h]
0x180003549  mov     rcx, r11; wchar_t *
0x18000354c  lea     rdx, aMicrosoftSansS_0; "Microsoft Sans Serif"
0x180003553  call    ?UnicodeCmp@@YAHPEA_W0@Z; UnicodeCmp(wchar_t *,wchar_t *)
0x180003558  test    eax, eax
0x18000355a  jz      short loc_180003587
0x18000355c  lea     rdx, aTahoma_0; "Tahoma"
0x180003563  mov     rcx, r11; wchar_t *
0x180003566  call    ?UnicodeCmp@@YAHPEA_W0@Z; UnicodeCmp(wchar_t *,wchar_t *)
0x18000356b  test    eax, eax
0x18000356d  jz      short loc_180003587
0x18000356f  lea     rdx, aTahomaBold; "Tahoma Bold"
0x180003576  mov     rcx, r11; wchar_t *
0x180003579  call    ?UnicodeCmp@@YAHPEA_W0@Z; UnicodeCmp(wchar_t *,wchar_t *)
0x18000357e  test    eax, eax
0x180003580  jz      short loc_180003587
0x180003582  mov     eax, r15d
0x180003585  jmp     short loc_18000358C
0x180003587  mov     eax, 2
0x18000358c  mov     ecx, 0FFFDh
0x180003591  and     [rbx+0A8h], cx
0x180003598  or      [rbx+0A8h], ax
0x18000359f  cmp     cs:?gFontLinkingData@@3PEA_WEA, 0FFFFFFFFFFFFFFFFh; wchar_t * gFontLinkingData
0x1800035a7  jnz     short loc_1800035E0
0x1800035a9  lea     rcx, [rbx+14h]; wchar_t *
0x1800035ad  call    ?IsFontRegLinked@@YAHPEA_W@Z; IsFontRegLinked(wchar_t *)
0x1800035b2  test    eax, eax
0x1800035b4  jz      short loc_1800035BE
0x1800035b6  or      word ptr [rbx+0A8h], 8
0x1800035be  mov     eax, 400h
0x1800035c3  or      [rbx+0A8h], ax
0x1800035ca  jmp     short loc_1800035E0
0x1800035cc  mov     eax, 0FFFCh
0x1800035d1  and     cx, ax
0x1800035d4  or      cx, 400h
0x1800035d9  mov     [rbx+0A8h], cx
0x1800035e0  lea     r9, [rbp+500h+var_280]; unsigned __int8 *
0x1800035e7  mov     [rsp+600h+var_5E0], rdi; int
0x1800035ec  lea     r8, [rbp+500h+var_260]; unsigned __int8 *
0x1800035f3  mov     rdx, rbx; struct FACE_CACHE *
0x1800035f6  mov     rcx, r12; hdc
0x1800035f9  call    ?GetFontDetails@@YAJPEAUHDC__@@PEAUFACE_CACHE@@PEAE2PEAUFONTCMAPDESC@@@Z; GetFontDetails(HDC__ *,FACE_CACHE *,uchar *,uchar *,FONTCMAPDESC *)
0x1800035fe  mov     esi, eax
0x180003600  test    eax, eax
0x180003602  jns     short loc_180003618
0x180003604  test    rdi, rdi
0x180003607  jz      short loc_180003611
0x180003609  mov     rcx, rdi; lpMem
0x18000360c  call    UspFreeMem
0x180003611  mov     eax, esi
0x180003613  jmp     loc_1800038F2
0x180003618  lea     r9, [rsp+600h+var_5D0]; unsigned int *
0x18000361d  mov     rcx, rbx; struct FACE_CACHE *
0x180003620  lea     r8, [rbp+500h+var_280]; unsigned __int8 *
0x180003627  lea     rdx, [rbp+500h+var_260]; unsigned __int8 *
0x18000362e  call    ?AllocateCMAPtables@@YAJPEAUFACE_CACHE@@PEAE1PEAK@Z; AllocateCMAPtables(FACE_CACHE *,uchar *,uchar *,ulong *)
0x180003633  mov     esi, eax
0x180003635  test    eax, eax
0x180003637  js      short loc_180003604
0x180003639  mov     r9, rbx; struct FACE_CACHE *
0x18000363c  lea     r8, [rbp+500h+var_280]; unsigned __int8 *
0x180003643  mov     rdx, rdi; struct FONTCMAPDESC *
0x180003646  mov     rcx, r12; HDC
0x180003649  call    ?FillCMAP@@YAJPEAUHDC__@@PEAUFONTCMAPDESC@@PEAEPEAUFACE_CACHE@@@Z; FillCMAP(HDC__ *,FONTCMAPDESC *,uchar *,FACE_CACHE *)
0x18000364e  mov     esi, eax
0x180003650  test    eax, eax
0x180003652  js      short loc_180003604
0x180003654  lea     r14, [rbx+878h]
0x18000365b  xor     edx, edx; union FONTUVSENTRY *
0x18000365d  mov     r8, r14; unsigned int *
0x180003660  mov     rcx, rdi; struct FONTCMAPDESC *
0x180003663  call    ?LoadUvsTable@@YAJPEAUFONTCMAPDESC@@PEATFONTUVSENTRY@@PEAK@Z; LoadUvsTable(FONTCMAPDESC *,FONTUVSENTRY *,ulong *)
0x180003668  mov     esi, eax
0x18000366a  test    eax, eax
0x18000366c  js      short loc_180003604
0x18000366e  test    eax, eax
0x180003670  jnz     loc_1800036F9
0x180003676  cmp     [r14], r15d
0x180003679  jz      short loc_1800036F9
0x18000367b  mov     eax, [r14]
0x18000367e  lea     rcx, [rax+rax*4]
0x180003682  mov     eax, 0FFFFFFFFh
0x180003687  add     rcx, rcx
0x18000368a  cmp     rcx, rax
0x18000368d  ja      short loc_1800036EF
0x18000368f  cmp     ecx, 7FFFFFFFh
0x180003695  ja      short loc_1800036EF
0x180003697  lea     r15, [rbx+870h]
0x18000369e  mov     rdx, r15
0x1800036a1  call    UspAllocCache
0x1800036a6  mov     esi, eax
0x1800036a8  test    eax, eax
0x1800036aa  js      loc_180003604
0x1800036b0  mov     rdx, [r15]; union FONTUVSENTRY *
0x1800036b3  mov     r8, r14; unsigned int *
0x1800036b6  mov     rcx, rdi; struct FONTCMAPDESC *
0x1800036b9  call    ?LoadUvsTable@@YAJPEAUFONTCMAPDESC@@PEATFONTUVSENTRY@@PEAK@Z; LoadUvsTable(FONTCMAPDESC *,FONTUVSENTRY *,ulong *)
0x1800036be  mov     esi, eax
0x1800036c0  test    eax, eax
0x1800036c2  jz      short loc_180003705
0x1800036c4  test    rdi, rdi
0x1800036c7  jz      short loc_1800036D1
0x1800036c9  mov     rcx, rdi; lpMem
0x1800036cc  call    UspFreeMem
0x1800036d1  mov     rcx, [r15]; lpMem
0x1800036d4  mov     dword ptr [r14], 0
0x1800036db  call    UspFreeMem
0x1800036e0  test    esi, esi
0x1800036e2  mov     eax, 80004005h
0x1800036e7  cmovns  esi, eax
0x1800036ea  jmp     loc_180003611
0x1800036ef  mov     esi, 80070216h
0x1800036f4  jmp     loc_180003604
0x1800036f9  mov     [rbx+870h], r15
0x180003700  mov     [r14], r15d
0x180003703  jmp     short loc_180003708
0x180003705  xor     r15d, r15d
0x180003708  test    rdi, rdi
0x18000370b  jz      short loc_180003715
0x18000370d  mov     rcx, rdi; lpMem
0x180003710  call    UspFreeMem
0x180003715  cmp     cs:?gfLocaleInitialized@@3HA, r15d; int gfLocaleInitialized
0x18000371c  jnz     short loc_180003745
0x18000371e  call    cs:__imp_GetUserDefaultLCID
0x180003724  mov     ecx, 3FFh
0x180003729  mov     cs:?gfLocaleInitialized@@3HA, r13d; int gfLocaleInitialized
0x180003730  and     ax, cx
0x180003733  mov     ecx, r15d
0x180003736  cmp     ax, r13w
0x18000373a  setz    cl
0x18000373d  mov     cs:?gfArabicLocale@@3HA, ecx; int gfArabicLocale
0x180003743  jmp     short loc_18000374B
0x180003745  mov     ecx, cs:?gfArabicLocale@@3HA; int gfArabicLocale
0x18000374b  test    ecx, ecx
0x18000374d  jz      loc_1800037E4
0x180003753  mov     rcx, [rbx+140h]
0x18000375a  movzx   eax, word ptr [rcx+0Ch]
0x18000375e  shl     rax, 8
0x180003762  or      rax, 0Ch
0x180003766  movzx   edx, word ptr [rcx+rax*2]
0x18000376a  test    dx, dx
0x18000376d  jnz     short loc_18000377E
0x18000376f  movzx   eax, word ptr [rcx]
0x180003772  shl     rax, 8
0x180003776  or      rax, 2Ch
0x18000377a  movzx   edx, word ptr [rcx+rax*2]
0x18000377e  mov     [rbx+134h], dx
0x180003785  movzx   eax, word ptr [rcx+0Ch]
0x180003789  shl     rax, 8
0x18000378d  or      rax, 1Bh
0x180003791  movzx   edx, word ptr [rcx+rax*2]
0x180003795  test    dx, dx
0x180003798  jnz     short loc_1800037A9
0x18000379a  movzx   eax, word ptr [rcx]
0x18000379d  shl     rax, 8
0x1800037a1  or      rax, 3Bh
0x1800037a5  movzx   edx, word ptr [rcx+rax*2]
0x1800037a9  mov     [rbx+136h], dx
0x1800037b0  movzx   eax, word ptr [rcx+0Ch]
0x1800037b4  shl     rax, 8
0x1800037b8  or      rax, 1Fh
0x1800037bc  movzx   edx, word ptr [rcx+rax*2]
0x1800037c0  test    dx, dx
0x1800037c3  jz      short loc_1800037CE
0x1800037c5  mov     [rbx+138h], dx
0x1800037cc  jmp     short loc_1800037E4
0x1800037ce  movzx   eax, word ptr [rcx]
0x1800037d1  shl     rax, 8
0x1800037d5  or      rax, 3Fh
0x1800037d9  movzx   eax, word ptr [rcx+rax*2]
0x1800037dd  mov     [rbx+138h], ax
0x1800037e4  cmp     cs:?gfUnistorInitialized@@3HA, r15d; int gfUnistorInitialized
0x1800037eb  jnz     short loc_1800037F2
0x1800037ed  call    ?InitUnistor@@YAXXZ; InitUnistor(void)
0x1800037f2  cmp     cs:?ghUniStore@@3PEAXEA, r15; void * ghUniStore
0x1800037f9  lea     rdi, [rbx+140h]
0x180003800  jz      short loc_18000384B
0x180003802  mov     r8d, [rsp+600h+var_5D0]; unsigned int
0x180003807  lea     rax, [rsp+600h+var_5C0]
0x18000380c  mov     rdx, [rdi]; void *
0x18000380f  mov     [rsp+600h+var_5D8], rax; void **
0x180003814  call    ?UniStorFindData@@YAJPEAX0KHHPEAPEAX@Z; UniStorFindData(void *,void *,ulong,int,int,void * *)
0x180003819  test    eax, eax
0x18000381b  js      short loc_18000384B
0x18000381d  mov     rsi, [rbx+148h]
0x180003824  sub     rsi, [rdi]
  ... truncated ...
```
