# LoadFont(HDC__ *,FACE_CACHE *)

- ea: `0x18001c3c4`
- end: `0x18001c97f`
- name: `?LoadFont@@YAJPEAUHDC__@@PEAUFACE_CACHE@@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(HDC hdc, struct FACE_CACHE *)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c144`

## callees

- `0x18000d040`
- `0x18001ac40`
- `0x18001b0d0`
- `0x18001c3c4`
- `0x18001cacc`
- `0x18001cfc4`
- `0x18001da6c`
- `0x180022cf0`
- `0x180046a00`
- `0x180046e6c`
- `0x180052708`
- `0x180052b50`
- `0x180057cc8`
- `0x180059e3c`
- `0x18005dc40`
- `0x18006b8f0`
- `0x18006d35c`
- `0x18007c230`
- `0x18007e2c8`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18001c5ad`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18001c5c0`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18001c5ad`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18001c5c0`
- `win32u!NtGdiFontIsLinked` at `0x18001c587`
- `win32u!NtGdiFontIsLinked` at `0x18001c587`

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
  unsigned __int64 v21; // rcx
  union FONTUVSENTRY **v22; // r15
  union FONTUVSENTRY *v23; // rcx
  unsigned __int16 *v24; // rcx
  int v25; // r9d
  unsigned __int16 v26; // dx
  unsigned __int16 v27; // dx
  unsigned __int16 v28; // dx
  LPVOID *v29; // rdi
  int Data; // eax
  __int64 v31; // rsi
  char *v32; // rax
  unsigned __int16 *v33; // rdx
  __int16 v34; // r9
  unsigned __int16 v35; // cx
  unsigned __int16 v36; // ax
  int v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+30h] [rbp-D0h] BYREF
  struct FONTCMAPDESC *v39; // [rsp+38h] [rbp-C8h] BYREF
  void *v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v42[740]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v43; // [rsp+338h] [rbp+238h]
  _DWORD v44[17]; // [rsp+33Ch] [rbp+23Ch]
  unsigned __int8 v45[16]; // [rsp+380h] [rbp+280h] BYREF
  __int128 v46; // [rsp+390h] [rbp+290h]
  unsigned __int8 v47[544]; // [rsp+3A0h] [rbp+2A0h] BYREF

  memset_0(v47, 0, sizeof(v47));
  v39 = 0;
  v38 = 0;
  v40 = 0;
  *(_OWORD *)v45 = 0;
  v4 = 0;
  v46 = 0;
  memset_0(v42, 0, 0x328u);
  v41 = 812;
  v6 = 1;
  if ( (unsigned int)GetFontRealizationInfo(hdc, &v41) )
  {
    v7 = v43;
    v5 = 0;
    for ( *((_DWORD *)a2 + 543) = v43; (unsigned int)v5 < v7; *((_WORD *)a2 + v8 + 1088) = (v9 + 2) >> 2 )
    {
      v8 = (unsigned int)v5;
      v5 = (unsigned int)(v5 + 1);
      v9 = v44[v8];
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
    if ( v42[0] == 3 )
    {
      GetFontDesc(hdc, (int *)a2 + 40, &v39);
      v4 = v39;
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
  FontDetails = GetFontDetails(hdc, a2, v47, v45, v4);
  if ( FontDetails < 0 )
    goto LABEL_30;
  FontDetails = AllocateCMAPtables(a2, v47, v45, &v38);
  if ( FontDetails < 0 )
    goto LABEL_30;
  FontDetails = FillCMAP(hdc, v4, v45, a2);
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
  v21 = 10LL * (unsigned int)*v19;
  if ( v21 > 0xFFFFFFFF || (unsigned int)v21 > 0x7FFFFFFF )
  {
    FontDetails = -2147024362;
LABEL_30:
    if ( v4 )
      UspFreeMem(v4);
    return (unsigned int)FontDetails;
  }
  v22 = (union FONTUVSENTRY **)((char *)a2 + 2160);
  FontDetails = UspAllocCache(v21, (char *)a2 + 2160);
  if ( FontDetails < 0 )
    goto LABEL_30;
  FontDetails = LoadUvsTable(v4, *v22, (unsigned int *)a2 + 542);
  if ( FontDetails )
  {
    if ( v4 )
      UspFreeMem(v4);
    v23 = *v22;
    *v19 = 0;
    UspFreeMem(v23);
    if ( FontDetails >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)FontDetails;
  }
LABEL_49:
  if ( v4 )
    UspFreeMem(v4);
  CheckInitLocale();
  if ( gfArabicLocale )
  {
    v24 = (unsigned __int16 *)*((_QWORD *)a2 + 40);
    v26 = v24[((unsigned __int64)v24[6] << 8) | 0xC];
    if ( !v26 )
      v26 = v24[((unsigned __int64)*v24 << 8) | 0x2C];
    *((_WORD *)a2 + 154) = v26;
    v27 = v24[((unsigned __int64)v24[6] << 8) | 0x1B];
    if ( !v27 )
      v27 = v24[((unsigned __int64)*v24 << 8) | 0x3B];
    *((_WORD *)a2 + 155) = v27;
    v28 = v24[((unsigned __int64)v24[6] << 8) | 0x1F];
    if ( v28 )
      *((_WORD *)a2 + 156) = v28;
    else
      *((_WORD *)a2 + 156) = v24[((unsigned __int64)*v24 << 8) | 0x3F];
  }
  if ( !gfUnistorInitialized )
    InitUnistor();
  v29 = (LPVOID *)((char *)a2 + 320);
  if ( ghUniStore && (Data = UniStorFindData(v24, *v29, v38, v25, v37, &v40), Data >= 0) )
  {
    v31 = (__int64)(*((_QWORD *)a2 + 41) - (_QWORD)*v29) >> 1;
    if ( !Data )
      UspFreeMem(*v29);
    v32 = (char *)v40;
    *v29 = v40;
    *((_QWORD *)a2 + 41) = &v32[2 * v31];
  }
  else
  {
    v6 = 0;
  }
  *((_DWORD *)a2 + 538) = v6;
  v33 = (unsigned __int16 *)*v29;
  v34 = *((_WORD *)a2 + 141);
  *((_WORD *)a2 + 140) = *((_WORD *)*v29 + (((unsigned __int64)*(unsigned __int16 *)*v29 << 8) | 0x20));
  v35 = v33[((unsigned __int64)v33[247] << 8) | 0x1B];
  *((_WORD *)a2 + 142) = v35;
  if ( v35 == v34 )
  {
    v36 = v33[((unsigned __int64)v33[32] << 8) | 0xB];
    *((_WORD *)a2 + 142) = v36;
    if ( v36 == v34 )
      *((_WORD *)a2 + 142) = v33[((unsigned __int64)*v33 << 8) | 0x20];
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
0x18001c3c4  mov     [rsp-8+arg_10], rbx
0x18001c3c9  push    rbp
0x18001c3ca  push    rsi
0x18001c3cb  push    rdi
0x18001c3cc  push    r12
0x18001c3ce  push    r13
0x18001c3d0  push    r14
0x18001c3d2  push    r15
0x18001c3d4  lea     rbp, [rsp-4D0h]
0x18001c3dc  sub     rsp, 5D0h
0x18001c3e3  mov     rax, cs:__security_cookie
0x18001c3ea  xor     rax, rsp
0x18001c3ed  mov     [rbp+500h+var_40], rax
0x18001c3f4  mov     rbx, rdx
0x18001c3f7  mov     r12, rcx
0x18001c3fa  xor     edx, edx; Val
0x18001c3fc  lea     rcx, [rbp+500h+var_260]; void *
0x18001c403  mov     r8d, 220h; Size
0x18001c409  call    memset_0
0x18001c40e  xor     r15d, r15d
0x18001c411  lea     rcx, [rsp+600h+var_5AC]; void *
0x18001c416  xorps   xmm0, xmm0
0x18001c419  mov     [rsp+600h+var_5C8], r15
0x18001c41e  xor     edx, edx; Val
0x18001c420  mov     [rsp+600h+var_5D0], r15d
0x18001c425  mov     r8d, 328h; Size
0x18001c42b  mov     [rsp+600h+var_5C0], r15
0x18001c430  movups  xmmword ptr [rbp+500h+var_280], xmm0
0x18001c437  mov     edi, r15d
0x18001c43a  movups  [rbp+500h+var_270], xmm0
0x18001c441  call    memset_0
0x18001c446  lea     rdx, [rsp+600h+var_5B0]
0x18001c44b  mov     [rsp+600h+var_5B0], 32Ch
0x18001c453  mov     rcx, r12
0x18001c456  call    GetFontRealizationInfo
0x18001c45b  lea     r13d, [r15+1]
0x18001c45f  test    eax, eax
0x18001c461  jnz     short loc_18001C46C
0x18001c463  mov     [rbx+87Ch], r15d
0x18001c46a  jmp     short loc_18001C4A8
0x18001c46c  mov     r8d, [rbp+500h+var_2C8]
0x18001c473  mov     edx, r15d
0x18001c476  mov     [rbx+87Ch], r8d
0x18001c47d  test    r8d, r8d
0x18001c480  jz      short loc_18001C4A8
0x18001c482  mov     ecx, edx
0x18001c484  add     edx, r13d
0x18001c487  mov     eax, [rbp+rcx*4+500h+var_2C4]
0x18001c48e  mov     [rbx+rcx*4+8A0h], eax
0x18001c495  add     eax, 2
0x18001c498  sar     eax, 2
0x18001c49b  mov     [rbx+rcx*2+880h], ax
0x18001c4a3  cmp     edx, r8d
0x18001c4a6  jb      short loc_18001C482
0x18001c4a8  mov     eax, 0FBF7h
0x18001c4ad  and     [rbx+0A8h], ax
0x18001c4b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full> `wil::Feature<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full>::GetImpl(void)'::`2'::impl
0x18001c4bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UCSANRacyGdi32Full>::__private_IsEnabled(void)
0x18001c4c0  test    al, al
0x18001c4c2  jz      short loc_18001C4CE
0x18001c4c4  mov     [rbx+0AAh], r15w
0x18001c4cc  jmp     short loc_18001C4DA
0x18001c4ce  mov     eax, 0FC0Fh
0x18001c4d3  and     [rbx+0A8h], ax
0x18001c4da  mov     al, [rbx+9Dh]
0x18001c4e0  and     al, 0Ch
0x18001c4e2  cmp     al, 8
0x18001c4e4  jnz     short loc_18001C501
0x18001c4e6  mov     rcx, r12; hdc
0x18001c4e9  call    ?IsFontCffOrMM@@YAEPEAUHDC__@@@Z; IsFontCffOrMM(HDC__ *)
0x18001c4ee  test    al, al
0x18001c4f0  jnz     short loc_18001C501
0x18001c4f2  lea     rsi, [rbx+0A0h]
0x18001c4f9  mov     dword ptr [rsi], 0FFFFFFFDh
0x18001c4ff  jmp     short loc_18001C52C
0x18001c501  cmp     [rsp+600h+var_5AC], 3
0x18001c506  lea     rsi, [rbx+0A0h]
0x18001c50d  jz      short loc_18001C517
0x18001c50f  mov     dword ptr [rsi], 0FFFFFFFEh
0x18001c515  jmp     short loc_18001C52C
0x18001c517  lea     r8, [rsp+600h+var_5C8]; struct FONTCMAPDESC **
0x18001c51c  mov     rdx, rsi; int *
0x18001c51f  mov     rcx, r12; hdc
0x18001c522  call    ?GetFontDesc@@YAJPEAUHDC__@@PEAHPEAPEAUFONTCMAPDESC@@@Z; GetFontDesc(HDC__ *,int *,FONTCMAPDESC * *)
0x18001c527  mov     rdi, [rsp+600h+var_5C8]
0x18001c52c  cmp     dword ptr [rsi], 0FFFFFFFEh
0x18001c52f  jge     short loc_18001C584
0x18001c531  mov     eax, 0FFF8h
0x18001c536  mov     [rbx+13Ch], r15d
0x18001c53d  and     [rbx+0A8h], ax
0x18001c544  mov     ecx, 0FFh
0x18001c549  movzx   eax, word ptr [rbx+98h]
0x18001c550  xorps   xmm0, xmm0
0x18001c553  and     ax, cx
0x18001c556  mov     word ptr [rbx+118h], 20h ; ' '
0x18001c55f  mov     [rbx+11Ah], ax
0x18001c566  xor     eax, eax
0x18001c568  mov     word ptr [rbx+132h], 0FFFFh
0x18001c571  mov     [rbx+0A4h], r15d
0x18001c578  movups  xmmword ptr [rbx+140h], xmm0
0x18001c57f  jmp     loc_18001C954
0x18001c584  mov     rcx, r12
0x18001c587  call    cs:__imp_NtGdiFontIsLinked
0x18001c58e  nop     dword ptr [rax+rax+00h]
0x18001c593  movzx   ecx, word ptr [rbx+0A8h]
0x18001c59a  test    eax, eax
0x18001c59c  jz      loc_18001C65A
0x18001c5a2  or      cx, r13w
0x18001c5a6  mov     [rbx+0A8h], cx
0x18001c5ad  call    cs:__imp_GetACP
0x18001c5b4  nop     dword ptr [rax+rax+00h]
0x18001c5b9  cmp     eax, 3A4h
0x18001c5be  jz      short loc_18001C5D3
0x18001c5c0  call    cs:__imp_GetACP
0x18001c5c7  nop     dword ptr [rax+rax+00h]
0x18001c5cc  cmp     eax, 3B5h
0x18001c5d1  jnz     short loc_18001C610
0x18001c5d3  lea     r11, [rbx+14h]
0x18001c5d7  mov     rcx, r11; wchar_t *
0x18001c5da  lea     rdx, aMicrosoftSansS_0; "Microsoft Sans Serif"
0x18001c5e1  call    ?UnicodeCmp@@YAHPEA_W0@Z; UnicodeCmp(wchar_t *,wchar_t *)
0x18001c5e6  test    eax, eax
0x18001c5e8  jz      short loc_18001C615
0x18001c5ea  lea     rdx, aTahoma_0; "Tahoma"
0x18001c5f1  mov     rcx, r11; wchar_t *
0x18001c5f4  call    ?UnicodeCmp@@YAHPEA_W0@Z; UnicodeCmp(wchar_t *,wchar_t *)
0x18001c5f9  test    eax, eax
0x18001c5fb  jz      short loc_18001C615
0x18001c5fd  lea     rdx, aTahomaBold; "Tahoma Bold"
0x18001c604  mov     rcx, r11; wchar_t *
0x18001c607  call    ?UnicodeCmp@@YAHPEA_W0@Z; UnicodeCmp(wchar_t *,wchar_t *)
0x18001c60c  test    eax, eax
0x18001c60e  jz      short loc_18001C615
0x18001c610  mov     eax, r15d
0x18001c613  jmp     short loc_18001C61A
0x18001c615  mov     eax, 2
0x18001c61a  mov     ecx, 0FFFDh
0x18001c61f  and     [rbx+0A8h], cx
0x18001c626  or      [rbx+0A8h], ax
0x18001c62d  cmp     cs:?gFontLinkingData@@3PEA_WEA, 0FFFFFFFFFFFFFFFFh; wchar_t * gFontLinkingData
0x18001c635  jnz     short loc_18001C66E
0x18001c637  lea     rcx, [rbx+14h]; wchar_t *
0x18001c63b  call    ?IsFontRegLinked@@YAHPEA_W@Z; IsFontRegLinked(wchar_t *)
0x18001c640  test    eax, eax
0x18001c642  jz      short loc_18001C64C
0x18001c644  or      word ptr [rbx+0A8h], 8
0x18001c64c  mov     eax, 400h
0x18001c651  or      [rbx+0A8h], ax
0x18001c658  jmp     short loc_18001C66E
0x18001c65a  mov     eax, 0FFFCh
0x18001c65f  and     cx, ax
0x18001c662  or      cx, 400h
0x18001c667  mov     [rbx+0A8h], cx
0x18001c66e  lea     r9, [rbp+500h+var_280]; unsigned __int8 *
0x18001c675  mov     [rsp+600h+var_5E0], rdi; int
0x18001c67a  lea     r8, [rbp+500h+var_260]; unsigned __int8 *
0x18001c681  mov     rdx, rbx; struct FACE_CACHE *
0x18001c684  mov     rcx, r12; hdc
0x18001c687  call    ?GetFontDetails@@YAJPEAUHDC__@@PEAUFACE_CACHE@@PEAE2PEAUFONTCMAPDESC@@@Z; GetFontDetails(HDC__ *,FACE_CACHE *,uchar *,uchar *,FONTCMAPDESC *)
0x18001c68c  mov     esi, eax
0x18001c68e  test    eax, eax
0x18001c690  jns     short loc_18001C6A6
0x18001c692  test    rdi, rdi
0x18001c695  jz      short loc_18001C69F
0x18001c697  mov     rcx, rdi; lpMem
0x18001c69a  call    UspFreeMem
0x18001c69f  mov     eax, esi
0x18001c6a1  jmp     loc_18001C954
0x18001c6a6  lea     r9, [rsp+600h+var_5D0]; unsigned int *
0x18001c6ab  mov     rcx, rbx; struct FACE_CACHE *
0x18001c6ae  lea     r8, [rbp+500h+var_280]; unsigned __int8 *
0x18001c6b5  lea     rdx, [rbp+500h+var_260]; unsigned __int8 *
0x18001c6bc  call    ?AllocateCMAPtables@@YAJPEAUFACE_CACHE@@PEAE1PEAK@Z; AllocateCMAPtables(FACE_CACHE *,uchar *,uchar *,ulong *)
0x18001c6c1  mov     esi, eax
0x18001c6c3  test    eax, eax
0x18001c6c5  js      short loc_18001C692
0x18001c6c7  mov     r9, rbx; struct FACE_CACHE *
0x18001c6ca  lea     r8, [rbp+500h+var_280]; unsigned __int8 *
0x18001c6d1  mov     rdx, rdi; struct FONTCMAPDESC *
0x18001c6d4  mov     rcx, r12; HDC
0x18001c6d7  call    ?FillCMAP@@YAJPEAUHDC__@@PEAUFONTCMAPDESC@@PEAEPEAUFACE_CACHE@@@Z; FillCMAP(HDC__ *,FONTCMAPDESC *,uchar *,FACE_CACHE *)
0x18001c6dc  mov     esi, eax
0x18001c6de  test    eax, eax
0x18001c6e0  js      short loc_18001C692
0x18001c6e2  lea     r14, [rbx+878h]
0x18001c6e9  xor     edx, edx; union FONTUVSENTRY *
0x18001c6eb  mov     r8, r14; unsigned int *
0x18001c6ee  mov     rcx, rdi; struct FONTCMAPDESC *
0x18001c6f1  call    ?LoadUvsTable@@YAJPEAUFONTCMAPDESC@@PEATFONTUVSENTRY@@PEAK@Z; LoadUvsTable(FONTCMAPDESC *,FONTUVSENTRY *,ulong *)
0x18001c6f6  mov     esi, eax
0x18001c6f8  test    eax, eax
0x18001c6fa  js      short loc_18001C692
0x18001c6fc  test    eax, eax
0x18001c6fe  jnz     loc_18001C787
0x18001c704  cmp     [r14], r15d
0x18001c707  jz      short loc_18001C787
0x18001c709  mov     eax, [r14]
0x18001c70c  lea     rcx, [rax+rax*4]
0x18001c710  mov     eax, 0FFFFFFFFh
0x18001c715  add     rcx, rcx
0x18001c718  cmp     rcx, rax
0x18001c71b  ja      short loc_18001C77D
0x18001c71d  cmp     ecx, 7FFFFFFFh
0x18001c723  ja      short loc_18001C77D
0x18001c725  lea     r15, [rbx+870h]
0x18001c72c  mov     rdx, r15
0x18001c72f  call    UspAllocCache
0x18001c734  mov     esi, eax
0x18001c736  test    eax, eax
0x18001c738  js      loc_18001C692
0x18001c73e  mov     rdx, [r15]; union FONTUVSENTRY *
0x18001c741  mov     r8, r14; unsigned int *
0x18001c744  mov     rcx, rdi; struct FONTCMAPDESC *
0x18001c747  call    ?LoadUvsTable@@YAJPEAUFONTCMAPDESC@@PEATFONTUVSENTRY@@PEAK@Z; LoadUvsTable(FONTCMAPDESC *,FONTUVSENTRY *,ulong *)
0x18001c74c  mov     esi, eax
0x18001c74e  test    eax, eax
0x18001c750  jz      short loc_18001C793
0x18001c752  test    rdi, rdi
0x18001c755  jz      short loc_18001C75F
0x18001c757  mov     rcx, rdi; lpMem
0x18001c75a  call    UspFreeMem
0x18001c75f  mov     rcx, [r15]; lpMem
0x18001c762  mov     dword ptr [r14], 0
0x18001c769  call    UspFreeMem
0x18001c76e  test    esi, esi
0x18001c770  mov     eax, 80004005h
0x18001c775  cmovns  esi, eax
0x18001c778  jmp     loc_18001C69F
0x18001c77d  mov     esi, 80070216h
0x18001c782  jmp     loc_18001C692
0x18001c787  mov     [rbx+870h], r15
0x18001c78e  mov     [r14], r15d
0x18001c791  jmp     short loc_18001C796
0x18001c793  xor     r15d, r15d
0x18001c796  test    rdi, rdi
0x18001c799  jz      short loc_18001C7A3
0x18001c79b  mov     rcx, rdi; lpMem
0x18001c79e  call    UspFreeMem
0x18001c7a3  call    ?CheckInitLocale@@YAXXZ; CheckInitLocale(void)
0x18001c7a8  cmp     cs:?gfArabicLocale@@3HA, r15d; int gfArabicLocale
0x18001c7af  jz      loc_18001C846
0x18001c7b5  mov     rcx, [rbx+140h]
0x18001c7bc  movzx   eax, word ptr [rcx+0Ch]
0x18001c7c0  shl     rax, 8
0x18001c7c4  or      rax, 0Ch
0x18001c7c8  movzx   edx, word ptr [rcx+rax*2]
0x18001c7cc  test    dx, dx
0x18001c7cf  jnz     short loc_18001C7E0
0x18001c7d1  movzx   eax, word ptr [rcx]
0x18001c7d4  shl     rax, 8
0x18001c7d8  or      rax, 2Ch
0x18001c7dc  movzx   edx, word ptr [rcx+rax*2]
0x18001c7e0  mov     [rbx+134h], dx
0x18001c7e7  movzx   eax, word ptr [rcx+0Ch]
0x18001c7eb  shl     rax, 8
0x18001c7ef  or      rax, 1Bh
0x18001c7f3  movzx   edx, word ptr [rcx+rax*2]
0x18001c7f7  test    dx, dx
0x18001c7fa  jnz     short loc_18001C80B
0x18001c7fc  movzx   eax, word ptr [rcx]
0x18001c7ff  shl     rax, 8
0x18001c803  or      rax, 3Bh
0x18001c807  movzx   edx, word ptr [rcx+rax*2]
0x18001c80b  mov     [rbx+136h], dx
0x18001c812  movzx   eax, word ptr [rcx+0Ch]
0x18001c816  shl     rax, 8
0x18001c81a  or      rax, 1Fh
0x18001c81e  movzx   edx, word ptr [rcx+rax*2]
0x18001c822  test    dx, dx
0x18001c825  jz      short loc_18001C830
0x18001c827  mov     [rbx+138h], dx
0x18001c82e  jmp     short loc_18001C846
0x18001c830  movzx   eax, word ptr [rcx]
0x18001c833  shl     rax, 8
0x18001c837  or      rax, 3Fh
0x18001c83b  movzx   eax, word ptr [rcx+rax*2]
0x18001c83f  mov     [rbx+138h], ax
0x18001c846  cmp     cs:?gfUnistorInitialized@@3HA, r15d; int gfUnistorInitialized
0x18001c84d  jnz     short loc_18001C854
0x18001c84f  call    ?InitUnistor@@YAXXZ; InitUnistor(void)
0x18001c854  cmp     cs:?ghUniStore@@3PEAXEA, r15; void * ghUniStore
0x18001c85b  lea     rdi, [rbx+140h]
0x18001c862  jz      short loc_18001C8AD
0x18001c864  mov     r8d, [rsp+600h+var_5D0]; unsigned int
0x18001c869  lea     rax, [rsp+600h+var_5C0]
0x18001c86e  mov     rdx, [rdi]; void *
0x18001c871  mov     [rsp+600h+var_5D8], rax; void **
0x18001c876  call    ?UniStorFindData@@YAJPEAX0KHHPEAPEAX@Z; UniStorFindData(void *,void *,ulong,int,int,void * *)
0x18001c87b  test    eax, eax
0x18001c87d  js      short loc_18001C8AD
0x18001c87f  mov     rsi, [rbx+148h]
0x18001c886  sub     rsi, [rdi]
0x18001c889  sar     rsi, 1
0x18001c88c  test    eax, eax
0x18001c88e  jnz     short loc_18001C898
0x18001c890  mov     rcx, [rdi]; lpMem
0x18001c893  call    UspFreeMem
0x18001c898  mov     rax, [rsp+600h+var_5C0]
0x18001c89d  mov     [rdi], rax
0x18001c8a0  lea     rax, [rax+rsi*2]
  ... truncated ...
```
