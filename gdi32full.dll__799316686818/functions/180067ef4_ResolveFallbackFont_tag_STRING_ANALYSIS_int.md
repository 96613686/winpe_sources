# ResolveFallbackFont(tag_STRING_ANALYSIS *,int)

- ea: `0x180067ef4`
- end: `0x180068390`
- name: `?ResolveFallbackFont@@YAXPEAUtag_STRING_ANALYSIS@@H@Z`
- size: `1180`
- prototype: `void __fastcall(struct tag_STRING_ANALYSIS *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000b0d4`
- `0x18000b674`

## callees

- `0x18000d650`
- `0x18000e5a0`
- `0x180025f00`
- `0x1800527f0`
- `0x180067ac0`
- `0x180067ef4`
- `0x18007ac50`
- `0x18007ba24`
- `0x1800873fc`
- `0x180099710`
- `0x180099f9c`

## import_xrefs

- `GDI32!SelectObject` at `0x1800680f6`
- `GDI32!SelectObject` at `0x180068169`
- `GDI32!SelectObject` at `0x1800682a5`
- `GDI32!SelectObject` at `0x180068318`
- `GDI32!SelectObject` at `0x180068357`
- `GDI32!SelectObject` at `0x1800680f6`
- `GDI32!SelectObject` at `0x180068169`
- `GDI32!SelectObject` at `0x1800682a5`
- `GDI32!SelectObject` at `0x180068318`
- `GDI32!SelectObject` at `0x180068357`
- `GDI32!DeleteObject` at `0x180068172`
- `GDI32!DeleteObject` at `0x180068321`
- `GDI32!DeleteObject` at `0x180068360`
- `GDI32!DeleteObject` at `0x180068172`
- `GDI32!DeleteObject` at `0x180068321`
- `GDI32!DeleteObject` at `0x180068360`

## pseudocode

```c
void __fastcall ResolveFallbackFont(struct tag_STRING_ANALYSIS *a1, int a2)
{
  __int64 v2; // rsi
  unsigned __int64 v4; // rdi
  int v5; // eax
  HGDIOBJ CurrentObject; // rax
  void *v7; // r15
  void *v8; // rcx
  unsigned int v9; // r14d
  __int64 v10; // r13
  __int64 v11; // rax
  const char *pszFaceName; // r12
  HFONT FontA; // rax
  HFONT v14; // r12
  WCHAR *v15; // rax
  int v16; // ecx
  int v17; // edx
  struct FONT_VALID_INFO *v18; // r8
  int v19; // eax
  __int64 v20; // rax
  const char *v21; // r12
  HFONT v22; // rax
  WCHAR *v23; // rax
  int v24; // ecx
  int v25; // edx
  struct FONT_VALID_INFO *v26; // r8
  int v27; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  int pv; // [rsp+80h] [rbp-80h] BYREF
  int cWidth; // [rsp+84h] [rbp-7Ch]
  int cEscapement; // [rsp+88h] [rbp-78h]
  int cOrientation; // [rsp+8Ch] [rbp-74h]
  int cWeight; // [rsp+90h] [rbp-70h]
  unsigned __int8 v34; // [rsp+94h] [rbp-6Ch]
  unsigned __int8 v35; // [rsp+98h] [rbp-68h]
  unsigned __int8 v36; // [rsp+99h] [rbp-67h]
  unsigned __int8 v37; // [rsp+9Ah] [rbp-66h]
  unsigned __int8 v38; // [rsp+9Bh] [rbp-65h]
  char v39[64]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v40; // [rsp+120h] [rbp+20h]
  char v41[64]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v42; // [rsp+170h] [rbp+70h]
  WCHAR WideCharStr[40]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR v44[40]; // [rsp+1D0h] [rbp+D0h] BYREF

  v2 = a2;
  if ( *((_DWORD *)&iStandardFallback + a2) == -1 )
  {
    v4 = 32LL * a2;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl'::`2'::impl) )
    {
      if ( LODWORD(qword_1800AC7B8[v4 / 8]) == -1 )
      {
        v5 = dword_1800AC7A8[v4 / 4];
LABEL_5:
        *((_DWORD *)&iStandardFallback + v2) = v5;
        return;
      }
    }
    else if ( LODWORD(qword_1800AE668[v4 / 8]) == -1 )
    {
      v5 = dword_1800AE658[v4 / 4];
      goto LABEL_5;
    }
    memset_0(&pv, 0, 0x5Cu);
    CurrentObject = GetCurrentObject(*(HDC *)a1, 6u);
    v7 = CurrentObject;
    if ( CurrentObject )
    {
      v8 = CurrentObject;
      if ( *((_QWORD *)a1 + 114) )
        v8 = (void *)*((_QWORD *)a1 + 114);
      if ( GetObjectA(v8, 92, &pv) )
      {
        v9 = 0;
        v10 = 2 * v2;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl'::`2'::impl) )
        {
          do
          {
            v11 = dword_1800AC7A8[4 * v10 + 4 * v9];
            if ( (_DWORD)v11 == -1 )
              break;
            v28 = 0;
            v27 = 0;
            pszFaceName = (const char *)*((_QWORD *)&StandardFallbackFont + 2 * v11);
            if ( (int)StringCchLengthA(pszFaceName, 0x21u, &v28) < 0
              || (int)AnsiToUnicode(pszFaceName, (int)v28 + 1, 0, WideCharStr, &v27) < 0 )
            {
              break;
            }
            FontA = CreateFontA(
                      pv,
                      cWidth,
                      cEscapement,
                      cOrientation,
                      cWeight,
                      v34,
                      0,
                      0,
                      (unsigned __int8)(LODWORD((&ScriptProperties)[v2]) >> 20),
                      v35,
                      v36,
                      v37,
                      v38,
                      pszFaceName);
            v14 = FontA;
            if ( FontA )
            {
              if ( SelectObject(*(HDC *)a1, FontA) )
              {
                v40 = 0;
                if ( (unsigned int)GetTextFaceAliasW(*(_QWORD *)a1, 32, v39) )
                {
                  v15 = WideCharStr;
                  do
                  {
                    v16 = *(v15 - 80);
                    v17 = *v15 - v16;
                    if ( v17 )
                      break;
                    ++v15;
                  }
                  while ( v16 );
                  if ( !v17 )
                  {
                    v18 = (struct FONT_VALID_INFO *)*(&iStandardFallbackCandidates + 2 * v10 + 2 * v9);
                    if ( !v18 || FontIsValid(*(HDC *)a1, *((_DWORD *)a1 + 2), v18) )
                    {
                      v19 = dword_1800AC7A8[4 * v10 + 4 * v9];
                      goto LABEL_45;
                    }
                  }
                }
              }
              SelectObject(*(HDC *)a1, v7);
              DeleteObject(v14);
            }
            ++v9;
          }
          while ( (int)v9 < 2 );
        }
        else
        {
          do
          {
            v20 = dword_1800AE658[4 * v10 + 4 * v9];
            if ( (_DWORD)v20 == -1 )
              break;
            v28 = 0;
            v27 = 0;
            v21 = (const char *)*((_QWORD *)&StandardFallbackFontOld + 2 * v20);
            if ( (int)StringCchLengthA(v21, 0x21u, &v28) < 0 || (int)AnsiToUnicode(v21, (int)v28 + 1, 0, v44, &v27) < 0 )
              break;
            v22 = CreateFontA(
                    pv,
                    cWidth,
                    cEscapement,
                    cOrientation,
                    cWeight,
                    v34,
                    0,
                    0,
                    (unsigned __int8)(LODWORD((&ScriptProperties)[v2]) >> 20),
                    v35,
                    v36,
                    v37,
                    v38,
                    v21);
            v14 = v22;
            if ( v22 )
            {
              if ( SelectObject(*(HDC *)a1, v22) )
              {
                v42 = 0;
                if ( (unsigned int)GetTextFaceAliasW(*(_QWORD *)a1, 32, v41) )
                {
                  v23 = v44;
                  do
                  {
                    v24 = *(v23 - 80);
                    v25 = *v23 - v24;
                    if ( v25 )
                      break;
                    ++v23;
                  }
                  while ( v24 );
                  if ( !v25 )
                  {
                    v26 = (struct FONT_VALID_INFO *)*(&iStandardFallbackCandidatesOld + 2 * v10 + 2 * v9);
                    if ( !v26 || FontIsValid(*(HDC *)a1, *((_DWORD *)a1 + 2), v26) )
                    {
                      v19 = dword_1800AE658[4 * v10 + 4 * v9];
LABEL_45:
                      *((_DWORD *)&iStandardFallback + v2) = v19;
                      SelectObject(*(HDC *)a1, v7);
                      DeleteObject(v14);
                      return;
                    }
                  }
                }
              }
              SelectObject(*(HDC *)a1, v7);
              DeleteObject(v14);
            }
            ++v9;
          }
          while ( (int)v9 < 2 );
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180067ef4  mov     [rsp-8+arg_10], rbx
0x180067ef9  push    rbp
0x180067efa  push    rsi
0x180067efb  push    rdi
0x180067efc  push    r12
0x180067efe  push    r13
0x180067f00  push    r14
0x180067f02  push    r15
0x180067f04  lea     rbp, [rsp-130h]
0x180067f0c  sub     rsp, 230h
0x180067f13  mov     rax, cs:__security_cookie
0x180067f1a  xor     rax, rsp
0x180067f1d  mov     [rbp+160h+var_40], rax
0x180067f24  movsxd  rsi, edx
0x180067f27  lea     r12, __ImageBase
0x180067f2e  mov     rbx, rcx
0x180067f31  cmp     rva ?iStandardFallback@@3PAHA[r12+rsi*4], 0FFFFFFFFh; int near * iStandardFallback ...
0x180067f3a  jnz     loc_180068366
0x180067f40  mov     rdi, rsi
0x180067f43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl(void)'::`2'::impl
0x180067f4a  shl     rdi, 5
0x180067f4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(void)
0x180067f53  test    al, al
0x180067f55  jz      short loc_180067F77
0x180067f57  cmp     dword ptr [rdi+r12+0AC7B8h], 0FFFFFFFFh
0x180067f60  jnz     short loc_180067F8C
0x180067f62  mov     eax, [rdi+r12+0AC7A8h]
0x180067f6a  mov     rva ?iStandardFallback@@3PAHA[r12+rsi*4], eax; int near * iStandardFallback ...
0x180067f72  jmp     loc_180068366
0x180067f77  cmp     dword ptr [rdi+r12+0AE668h], 0FFFFFFFFh
0x180067f80  jnz     short loc_180067F8C
0x180067f82  mov     eax, [rdi+r12+0AE658h]
0x180067f8a  jmp     short loc_180067F6A
0x180067f8c  mov     edi, 5Ch ; '\'
0x180067f91  lea     rcx, [rbp+160h+pv]; void *
0x180067f95  mov     r8d, edi; Size
0x180067f98  xor     edx, edx; Val
0x180067f9a  call    memset_0
0x180067f9f  mov     rcx, [rbx]; hdc
0x180067fa2  lea     edx, [rdi-56h]; type
0x180067fa5  call    GetCurrentObject
0x180067faa  mov     r15, rax
0x180067fad  test    rax, rax
0x180067fb0  jz      loc_180068366
0x180067fb6  mov     r8, [rbx+390h]
0x180067fbd  mov     rcx, rax
0x180067fc0  test    r8, r8
0x180067fc3  mov     edx, edi; c
0x180067fc5  cmovnz  rcx, r8; h
0x180067fc9  lea     r8, [rbp+160h+pv]; pv
0x180067fcd  call    GetObjectA
0x180067fd2  test    eax, eax
0x180067fd4  jz      loc_180068366
0x180067fda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl(void)'::`2'::impl
0x180067fe1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(void)
0x180067fe6  xor     r14d, r14d
0x180067fe9  lea     r13, [rsi+rsi]
0x180067fed  test    al, al
0x180067fef  jz      loc_1800681A4
0x180067ff5  mov     edi, r14d
0x180067ff8  add     rdi, r13
0x180067ffb  add     rdi, rdi
0x180067ffe  movsxd  rax, ds:rva dword_1800AC7A8[r12+rdi*8]
0x180068006  cmp     eax, 0FFFFFFFFh
0x180068009  jz      loc_180068366
0x18006800f  add     rax, rax
0x180068012  mov     [rsp+260h+var_1E8], 0
0x18006801b  lea     r8, [rsp+260h+var_1E8]; unsigned __int64 *
0x180068020  mov     [rsp+260h+var_1F0], 0
0x180068028  mov     edx, 21h ; '!'; unsigned __int64
0x18006802d  mov     r12, ds:rva ?StandardFallbackFont@@3QBUFALLBACK_FONT@@B[r12+rax*8]; FALLBACK_FONT const near * const StandardFallbackFont ...
0x180068035  mov     rcx, r12; char *
0x180068038  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18006803d  test    eax, eax
0x18006803f  js      loc_180068366
0x180068045  mov     edx, dword ptr [rsp+260h+var_1E8]
0x180068049  lea     rax, [rsp+260h+var_1F0]
0x18006804e  inc     edx; cchWideChar
0x180068050  mov     qword ptr [rsp+260h+cWeight], rax; int *
0x180068055  lea     r9, [rbp+160h+WideCharStr]; lpWideCharStr
0x18006805c  xor     r8d, r8d; lpSrc
0x18006805f  mov     rcx, r12; lpMultiByteStr
0x180068062  call    ?AnsiToUnicode@@YAJPEBDHIPEA_WPEAH@Z; AnsiToUnicode(char const *,int,uint,wchar_t *,int *)
0x180068067  test    eax, eax
0x180068069  js      loc_180068366
0x18006806f  movzx   edx, [rbp+160h+var_1C5]
0x180068073  lea     rax, __ImageBase
0x18006807a  mov     eax, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rax+rsi*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x180068081  movzx   r8d, [rbp+160h+var_1C6]
0x180068086  movzx   r9d, [rbp+160h+var_1C7]
0x18006808b  movzx   r10d, [rbp+160h+var_1C8]
0x180068090  mov     [rsp+260h+pszFaceName], r12; pszFaceName
0x180068095  mov     [rsp+260h+iPitchAndFamily], edx; iPitchAndFamily
0x180068099  mov     edx, [rbp+160h+cWidth]; cWidth
0x18006809c  mov     [rsp+260h+iQuality], r8d; iQuality
0x1800680a1  mov     r8d, [rbp+160h+cEscapement]; cEscapement
0x1800680a5  mov     [rsp+260h+iClipPrecision], r9d; iClipPrecision
0x1800680aa  mov     r9d, [rbp+160h+cOrientation]; cOrientation
0x1800680ae  mov     [rsp+260h+iOutPrecision], r10d; iOutPrecision
0x1800680b3  shr     eax, 14h
0x1800680b6  movzx   ecx, al
0x1800680b9  movzx   eax, [rbp+160h+var_1CC]
0x1800680bd  mov     [rsp+260h+iCharSet], ecx; iCharSet
0x1800680c1  mov     ecx, [rbp+160h+pv]; cHeight
0x1800680c4  mov     [rsp+260h+bStrikeOut], 0; bStrikeOut
0x1800680cc  mov     [rsp+260h+bUnderline], 0; bUnderline
0x1800680d4  mov     [rsp+260h+bItalic], eax; bItalic
0x1800680d8  mov     eax, [rbp+160h+var_1D0]
0x1800680db  mov     [rsp+260h+cWeight], eax; cWeight
0x1800680df  call    CreateFontA
0x1800680e4  mov     r12, rax
0x1800680e7  test    rax, rax
0x1800680ea  jz      loc_180068178
0x1800680f0  mov     rcx, [rbx]; hdc
0x1800680f3  mov     rdx, rax; h
0x1800680f6  call    cs:__imp_SelectObject
0x1800680fc  test    rax, rax
0x1800680ff  jz      short loc_180068163
0x180068101  xor     ecx, ecx
0x180068103  lea     r8, [rbp+160h+var_180]
0x180068107  mov     [rbp+160h+var_140], cx
0x18006810b  lea     edx, [rcx+20h]
0x18006810e  mov     rcx, [rbx]
0x180068111  call    GetTextFaceAliasW
0x180068116  test    eax, eax
0x180068118  jz      short loc_180068163
0x18006811a  lea     rax, [rbp+160h+WideCharStr]
0x180068121  lea     r8, [rbp+160h+var_180]
0x180068125  sub     r8, rax
0x180068128  movzx   edx, word ptr [rax]
0x18006812b  movzx   ecx, word ptr [rax+r8]
0x180068130  sub     edx, ecx
0x180068132  jnz     short loc_18006813C
0x180068134  add     rax, 2
0x180068138  test    ecx, ecx
0x18006813a  jnz     short loc_180068128
0x18006813c  test    edx, edx
0x18006813e  jnz     short loc_180068163
0x180068140  lea     rcx, __ImageBase
0x180068147  mov     r8, ds:rva ?iStandardFallbackCandidates@@3QAY01$$CBUSTANDARD_FALLBACK_CANDIDATES@@A[rcx+rdi*8]; struct FONT_VALID_INFO *
0x18006814f  test    r8, r8
0x180068152  jz      short loc_180068198
0x180068154  mov     edx, [rbx+8]; unsigned int
0x180068157  mov     rcx, [rbx]; HDC
0x18006815a  call    ?FontIsValid@@YA_NPEAUHDC__@@KPEAUFONT_VALID_INFO@@@Z; FontIsValid(HDC__ *,ulong,FONT_VALID_INFO *)
0x18006815f  test    al, al
0x180068161  jnz     short loc_180068191
0x180068163  mov     rcx, [rbx]; hdc
0x180068166  mov     rdx, r15; h
0x180068169  call    cs:__imp_SelectObject
0x18006816f  mov     rcx, r12; ho
0x180068172  call    cs:__imp_DeleteObject
0x180068178  inc     r14d
0x18006817b  cmp     r14d, 2
0x18006817f  jge     loc_180068366
0x180068185  lea     r12, __ImageBase
0x18006818c  jmp     loc_180067FF5
0x180068191  lea     rcx, __ImageBase
0x180068198  mov     eax, ds:rva dword_1800AC7A8[rcx+rdi*8]
0x18006819f  jmp     loc_18006834A
0x1800681a4  mov     edi, r14d
0x1800681a7  add     rdi, r13
0x1800681aa  add     rdi, rdi
0x1800681ad  movsxd  rax, ds:rva dword_1800AE658[r12+rdi*8]
0x1800681b5  cmp     eax, 0FFFFFFFFh
0x1800681b8  jz      loc_180068366
0x1800681be  add     rax, rax
0x1800681c1  mov     [rsp+260h+var_1E8], 0
0x1800681ca  lea     r8, [rsp+260h+var_1E8]; unsigned __int64 *
0x1800681cf  mov     [rsp+260h+var_1F0], 0
0x1800681d7  mov     edx, 21h ; '!'; unsigned __int64
0x1800681dc  mov     r12, ds:rva ?StandardFallbackFontOld@@3QBUFALLBACK_FONT@@B[r12+rax*8]; FALLBACK_FONT const near * const StandardFallbackFontOld ...
0x1800681e4  mov     rcx, r12; char *
0x1800681e7  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800681ec  test    eax, eax
0x1800681ee  js      loc_180068366
0x1800681f4  mov     edx, dword ptr [rsp+260h+var_1E8]
0x1800681f8  lea     rax, [rsp+260h+var_1F0]
0x1800681fd  inc     edx; cchWideChar
0x1800681ff  mov     qword ptr [rsp+260h+cWeight], rax; int *
0x180068204  lea     r9, [rbp+160h+var_90]; lpWideCharStr
0x18006820b  xor     r8d, r8d; lpSrc
0x18006820e  mov     rcx, r12; lpMultiByteStr
0x180068211  call    ?AnsiToUnicode@@YAJPEBDHIPEA_WPEAH@Z; AnsiToUnicode(char const *,int,uint,wchar_t *,int *)
0x180068216  test    eax, eax
0x180068218  js      loc_180068366
0x18006821e  movzx   edx, [rbp+160h+var_1C5]
0x180068222  lea     rax, __ImageBase
0x180068229  mov     eax, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rax+rsi*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x180068230  movzx   r8d, [rbp+160h+var_1C6]
0x180068235  movzx   r9d, [rbp+160h+var_1C7]
0x18006823a  movzx   r10d, [rbp+160h+var_1C8]
0x18006823f  mov     [rsp+260h+pszFaceName], r12; pszFaceName
0x180068244  mov     [rsp+260h+iPitchAndFamily], edx; iPitchAndFamily
0x180068248  mov     edx, [rbp+160h+cWidth]; cWidth
0x18006824b  mov     [rsp+260h+iQuality], r8d; iQuality
0x180068250  mov     r8d, [rbp+160h+cEscapement]; cEscapement
0x180068254  mov     [rsp+260h+iClipPrecision], r9d; iClipPrecision
0x180068259  mov     r9d, [rbp+160h+cOrientation]; cOrientation
0x18006825d  mov     [rsp+260h+iOutPrecision], r10d; iOutPrecision
0x180068262  shr     eax, 14h
0x180068265  movzx   ecx, al
0x180068268  movzx   eax, [rbp+160h+var_1CC]
0x18006826c  mov     [rsp+260h+iCharSet], ecx; iCharSet
0x180068270  mov     ecx, [rbp+160h+pv]; cHeight
0x180068273  mov     [rsp+260h+bStrikeOut], 0; bStrikeOut
0x18006827b  mov     [rsp+260h+bUnderline], 0; bUnderline
0x180068283  mov     [rsp+260h+bItalic], eax; bItalic
0x180068287  mov     eax, [rbp+160h+var_1D0]
0x18006828a  mov     [rsp+260h+cWeight], eax; cWeight
0x18006828e  call    CreateFontA
0x180068293  mov     r12, rax
0x180068296  test    rax, rax
0x180068299  jz      loc_180068327
0x18006829f  mov     rcx, [rbx]; hdc
0x1800682a2  mov     rdx, rax; h
0x1800682a5  call    cs:__imp_SelectObject
0x1800682ab  test    rax, rax
0x1800682ae  jz      short loc_180068312
0x1800682b0  xor     ecx, ecx
0x1800682b2  lea     r8, [rbp+160h+var_130]
0x1800682b6  mov     [rbp+160h+var_F0], cx
0x1800682ba  lea     edx, [rcx+20h]
0x1800682bd  mov     rcx, [rbx]
0x1800682c0  call    GetTextFaceAliasW
0x1800682c5  test    eax, eax
0x1800682c7  jz      short loc_180068312
0x1800682c9  lea     rax, [rbp+160h+var_90]
0x1800682d0  lea     r8, [rbp+160h+var_130]
0x1800682d4  sub     r8, rax
0x1800682d7  movzx   edx, word ptr [rax]
0x1800682da  movzx   ecx, word ptr [rax+r8]
0x1800682df  sub     edx, ecx
0x1800682e1  jnz     short loc_1800682EB
0x1800682e3  add     rax, 2
0x1800682e7  test    ecx, ecx
0x1800682e9  jnz     short loc_1800682D7
0x1800682eb  test    edx, edx
0x1800682ed  jnz     short loc_180068312
0x1800682ef  lea     rcx, __ImageBase
0x1800682f6  mov     r8, ds:rva ?iStandardFallbackCandidatesOld@@3QAY01$$CBUSTANDARD_FALLBACK_CANDIDATES@@A[rcx+rdi*8]; struct FONT_VALID_INFO *
0x1800682fe  test    r8, r8
0x180068301  jz      short loc_180068343
0x180068303  mov     edx, [rbx+8]; unsigned int
0x180068306  mov     rcx, [rbx]; HDC
0x180068309  call    ?FontIsValid@@YA_NPEAUHDC__@@KPEAUFONT_VALID_INFO@@@Z; FontIsValid(HDC__ *,ulong,FONT_VALID_INFO *)
0x18006830e  test    al, al
0x180068310  jnz     short loc_18006833C
0x180068312  mov     rcx, [rbx]; hdc
0x180068315  mov     rdx, r15; h
0x180068318  call    cs:__imp_SelectObject
0x18006831e  mov     rcx, r12; ho
0x180068321  call    cs:__imp_DeleteObject
0x180068327  inc     r14d
0x18006832a  cmp     r14d, 2
0x18006832e  jge     short loc_180068366
0x180068330  lea     r12, __ImageBase
0x180068337  jmp     loc_1800681A4
0x18006833c  lea     rcx, __ImageBase
0x180068343  mov     eax, ds:rva dword_1800AE658[rcx+rdi*8]
0x18006834a  mov     rva ?iStandardFallback@@3PAHA[rcx+rsi*4], eax; int near * iStandardFallback ...
0x180068351  mov     rdx, r15; h
0x180068354  mov     rcx, [rbx]; hdc
0x180068357  call    cs:__imp_SelectObject
0x18006835d  mov     rcx, r12; ho
0x180068360  call    cs:__imp_DeleteObject
0x180068366  mov     rcx, [rbp+160h+var_40]
0x18006836d  xor     rcx, rsp; StackCookie
0x180068370  call    __security_check_cookie
0x180068375  mov     rbx, [rsp+260h+arg_10]
0x18006837d  add     rsp, 230h
0x180068384  pop     r15
0x180068386  pop     r14
0x180068388  pop     r13
0x18006838a  pop     r12
0x18006838c  pop     rdi
0x18006838d  pop     rsi
0x18006838e  pop     rbp
0x18006838f  retn
```
