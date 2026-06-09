# ResolveFallbackFont(tag_STRING_ANALYSIS *,int)

- ea: `0x180001f18`
- end: `0x1800023ea`
- name: `?ResolveFallbackFont@@YAXPEAUtag_STRING_ANALYSIS@@H@Z`
- size: `1234`
- prototype: `void __fastcall(struct tag_STRING_ANALYSIS *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180007f48`
- `0x180008554`

## callees

- `0x180001f18`
- `0x180002fd8`
- `0x180004c00`
- `0x1800069b0`
- `0x18002eee0`
- `0x180056600`
- `0x18006c254`
- `0x18007f800`
- `0x180080604`
- `0x18008c824`
- `0x18009cd0c`

## import_xrefs

- `GDI32!SelectObject` at `0x180002123`
- `GDI32!SelectObject` at `0x18000219c`
- `GDI32!SelectObject` at `0x1800022e5`
- `GDI32!SelectObject` at `0x18000235e`
- `GDI32!SelectObject` at `0x1800023a3`
- `GDI32!SelectObject` at `0x180002123`
- `GDI32!SelectObject` at `0x18000219c`
- `GDI32!SelectObject` at `0x1800022e5`
- `GDI32!SelectObject` at `0x18000235e`
- `GDI32!SelectObject` at `0x1800023a3`
- `GDI32!DeleteObject` at `0x1800021ab`
- `GDI32!DeleteObject` at `0x18000236d`
- `GDI32!DeleteObject` at `0x1800023b2`
- `GDI32!DeleteObject` at `0x1800021ab`
- `GDI32!DeleteObject` at `0x18000236d`
- `GDI32!DeleteObject` at `0x1800023b2`

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
  int v9; // r14d
  __int64 v10; // rax
  const char *pszFaceName; // r12
  HFONT FontA; // rax
  HFONT v13; // r12
  WCHAR *v14; // rax
  int v15; // ecx
  int v16; // edx
  struct FONT_VALID_INFO *v17; // r8
  int v18; // eax
  __int64 v19; // rax
  const char *v20; // r12
  HFONT v21; // rax
  WCHAR *v22; // rax
  int v23; // ecx
  int v24; // edx
  struct FONT_VALID_INFO *v25; // r8
  int v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  int pv; // [rsp+80h] [rbp-80h] BYREF
  int cWidth; // [rsp+84h] [rbp-7Ch]
  int cEscapement; // [rsp+88h] [rbp-78h]
  int cOrientation; // [rsp+8Ch] [rbp-74h]
  int cWeight; // [rsp+90h] [rbp-70h]
  unsigned __int8 v33; // [rsp+94h] [rbp-6Ch]
  unsigned __int8 v34; // [rsp+98h] [rbp-68h]
  unsigned __int8 v35; // [rsp+99h] [rbp-67h]
  unsigned __int8 v36; // [rsp+9Ah] [rbp-66h]
  unsigned __int8 v37; // [rsp+9Bh] [rbp-65h]
  char v38[64]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v39; // [rsp+120h] [rbp+20h]
  char v40[64]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v41; // [rsp+170h] [rbp+70h]
  WCHAR WideCharStr[40]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR v43[40]; // [rsp+1D0h] [rbp+D0h] BYREF

  v2 = a2;
  if ( *((_DWORD *)&iStandardFallback + a2) == -1 )
  {
    v4 = 32LL * a2;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl'::`2'::impl) )
    {
      if ( LODWORD(qword_1800B1908[v4 / 8]) == -1 )
      {
        v5 = dword_1800B18F8[v4 / 4];
LABEL_5:
        *((_DWORD *)&iStandardFallback + v2) = v5;
        return;
      }
    }
    else if ( LODWORD(qword_1800AFCE8[v4 / 8]) == -1 )
    {
      v5 = dword_1800AFCD8[v4 / 4];
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
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl'::`2'::impl) )
        {
          while ( v9 < 2 )
          {
            v10 = dword_1800B18F8[8 * v2 + 4 * v9];
            if ( (_DWORD)v10 == -1 )
              break;
            v27 = 0;
            v26 = 0;
            pszFaceName = (const char *)*((_QWORD *)&StandardFallbackFont + 2 * v10);
            if ( (int)StringCchLengthA(pszFaceName, 0x21u, &v27) < 0
              || (int)AnsiToUnicode(pszFaceName, (int)v27 + 1, 0, WideCharStr, &v26) < 0 )
            {
              break;
            }
            FontA = CreateFontA(
                      pv,
                      cWidth,
                      cEscapement,
                      cOrientation,
                      cWeight,
                      v33,
                      0,
                      0,
                      (unsigned __int8)(LODWORD((&ScriptProperties)[v2]) >> 20),
                      v34,
                      v35,
                      v36,
                      v37,
                      pszFaceName);
            v13 = FontA;
            if ( FontA )
            {
              if ( SelectObject(*(HDC *)a1, FontA) )
              {
                v39 = 0;
                if ( (unsigned int)GetTextFaceAliasW(*(_QWORD *)a1, 32, v38) )
                {
                  v14 = WideCharStr;
                  do
                  {
                    v15 = *(v14 - 80);
                    v16 = *v14 - v15;
                    if ( v16 )
                      break;
                    ++v14;
                  }
                  while ( v15 );
                  if ( !v16 )
                  {
                    v17 = (struct FONT_VALID_INFO *)*(&iStandardFallbackCandidates + 4 * v2 + 2 * v9);
                    if ( !v17 || FontIsValid(*(HDC *)a1, *((_DWORD *)a1 + 2), v17) )
                    {
                      v18 = dword_1800B18F8[8 * v2 + 4 * v9];
                      goto LABEL_45;
                    }
                  }
                }
              }
              SelectObject(*(HDC *)a1, v7);
              DeleteObject(v13);
            }
            ++v9;
          }
        }
        else
        {
          while ( v9 < 2 )
          {
            v19 = dword_1800AFCD8[8 * v2 + 4 * v9];
            if ( (_DWORD)v19 == -1 )
              break;
            v27 = 0;
            v26 = 0;
            v20 = (const char *)*((_QWORD *)&StandardFallbackFontOld + 2 * v19);
            if ( (int)StringCchLengthA(v20, 0x21u, &v27) < 0 || (int)AnsiToUnicode(v20, (int)v27 + 1, 0, v43, &v26) < 0 )
              break;
            v21 = CreateFontA(
                    pv,
                    cWidth,
                    cEscapement,
                    cOrientation,
                    cWeight,
                    v33,
                    0,
                    0,
                    (unsigned __int8)(LODWORD((&ScriptProperties)[v2]) >> 20),
                    v34,
                    v35,
                    v36,
                    v37,
                    v20);
            v13 = v21;
            if ( v21 )
            {
              if ( SelectObject(*(HDC *)a1, v21) )
              {
                v41 = 0;
                if ( (unsigned int)GetTextFaceAliasW(*(_QWORD *)a1, 32, v40) )
                {
                  v22 = v43;
                  do
                  {
                    v23 = *(v22 - 80);
                    v24 = *v22 - v23;
                    if ( v24 )
                      break;
                    ++v22;
                  }
                  while ( v23 );
                  if ( !v24 )
                  {
                    v25 = (struct FONT_VALID_INFO *)*(&iStandardFallbackCandidatesOld + 4 * v2 + 2 * v9);
                    if ( !v25 || FontIsValid(*(HDC *)a1, *((_DWORD *)a1 + 2), v25) )
                    {
                      v18 = dword_1800AFCD8[8 * v2 + 4 * v9];
LABEL_45:
                      *((_DWORD *)&iStandardFallback + v2) = v18;
                      SelectObject(*(HDC *)a1, v7);
                      DeleteObject(v13);
                      return;
                    }
                  }
                }
              }
              SelectObject(*(HDC *)a1, v7);
              DeleteObject(v13);
            }
            ++v9;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180001f18  mov     [rsp-8+arg_10], rbx
0x180001f1d  mov     [rsp-8+arg_18], rsi
0x180001f22  push    rbp
0x180001f23  push    rdi
0x180001f24  push    r12
0x180001f26  push    r14
0x180001f28  push    r15
0x180001f2a  lea     rbp, [rsp-130h]
0x180001f32  sub     rsp, 230h
0x180001f39  mov     rax, cs:__security_cookie
0x180001f40  xor     rax, rsp
0x180001f43  mov     [rbp+150h+var_30], rax
0x180001f4a  movsxd  rsi, edx
0x180001f4d  lea     r12, __ImageBase
0x180001f54  mov     rbx, rcx
0x180001f57  cmp     rva ?iStandardFallback@@3PAHA[r12+rsi*4], 0FFFFFFFFh; int near * iStandardFallback ...
0x180001f60  jnz     loc_1800023BE
0x180001f66  mov     rdi, rsi
0x180001f69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl(void)'::`2'::impl
0x180001f70  shl     rdi, 5
0x180001f74  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(void)
0x180001f79  test    al, al
0x180001f7b  jz      short loc_180001F9D
0x180001f7d  cmp     dword ptr [rdi+r12+0B1908h], 0FFFFFFFFh
0x180001f86  jnz     short loc_180001FB2
0x180001f88  mov     eax, [rdi+r12+0B18F8h]
0x180001f90  mov     rva ?iStandardFallback@@3PAHA[r12+rsi*4], eax; int near * iStandardFallback ...
0x180001f98  jmp     loc_1800023BE
0x180001f9d  cmp     dword ptr [rdi+r12+0AFCE8h], 0FFFFFFFFh
0x180001fa6  jnz     short loc_180001FB2
0x180001fa8  mov     eax, [rdi+r12+0AFCD8h]
0x180001fb0  jmp     short loc_180001F90
0x180001fb2  mov     edi, 5Ch ; '\'
0x180001fb7  lea     rcx, [rbp+150h+pv]; void *
0x180001fbb  mov     r8d, edi; Size
0x180001fbe  xor     edx, edx; Val
0x180001fc0  call    memset_0
0x180001fc5  mov     rcx, [rbx]; hdc
0x180001fc8  lea     edx, [rdi-56h]; type
0x180001fcb  call    GetCurrentObject
0x180001fd0  mov     r15, rax
0x180001fd3  test    rax, rax
0x180001fd6  jz      loc_1800023BE
0x180001fdc  mov     r8, [rbx+390h]
0x180001fe3  mov     rcx, rax
0x180001fe6  test    r8, r8
0x180001fe9  mov     edx, edi; c
0x180001feb  cmovnz  rcx, r8; h
0x180001fef  lea     r8, [rbp+150h+pv]; pv
0x180001ff3  call    GetObjectA
0x180001ff8  test    eax, eax
0x180001ffa  jz      loc_1800023BE
0x180002000  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl(void)'::`2'::impl
0x180002007  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(void)
0x18000200c  xor     r14d, r14d
0x18000200f  test    al, al
0x180002011  jz      loc_1800021D9
0x180002017  cmp     r14d, 2
0x18000201b  jge     loc_1800023BE
0x180002021  movsxd  rax, r14d
0x180002024  lea     rdi, [rax+rsi*2]
0x180002028  add     rdi, rdi
0x18000202b  movsxd  rax, ds:rva dword_1800B18F8[r12+rdi*8]
0x180002033  cmp     eax, 0FFFFFFFFh
0x180002036  jz      loc_1800023BE
0x18000203c  add     rax, rax
0x18000203f  mov     [rsp+250h+var_1D8], 0
0x180002048  lea     r8, [rsp+250h+var_1D8]; unsigned __int64 *
0x18000204d  mov     [rsp+250h+var_1E0], 0
0x180002055  mov     edx, 21h ; '!'; unsigned __int64
0x18000205a  mov     r12, ds:rva ?StandardFallbackFont@@3QBUFALLBACK_FONT@@B[r12+rax*8]; FALLBACK_FONT const near * const StandardFallbackFont ...
0x180002062  mov     rcx, r12; char *
0x180002065  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000206a  test    eax, eax
0x18000206c  js      loc_1800023BE
0x180002072  mov     edx, dword ptr [rsp+250h+var_1D8]
0x180002076  lea     rax, [rsp+250h+var_1E0]
0x18000207b  inc     edx; cchWideChar
0x18000207d  mov     qword ptr [rsp+250h+cWeight], rax; int *
0x180002082  lea     r9, [rbp+150h+WideCharStr]; lpWideCharStr
0x180002089  xor     r8d, r8d; lpSrc
0x18000208c  mov     rcx, r12; lpMultiByteStr
0x18000208f  call    ?AnsiToUnicode@@YAJPEBDHIPEA_WPEAH@Z; AnsiToUnicode(char const *,int,uint,wchar_t *,int *)
0x180002094  test    eax, eax
0x180002096  js      loc_1800023BE
0x18000209c  movzx   edx, [rbp+150h+var_1B5]
0x1800020a0  lea     rax, __ImageBase
0x1800020a7  mov     eax, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rax+rsi*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x1800020ae  movzx   r8d, [rbp+150h+var_1B6]
0x1800020b3  movzx   r9d, [rbp+150h+var_1B7]
0x1800020b8  movzx   r10d, [rbp+150h+var_1B8]
0x1800020bd  mov     [rsp+250h+pszFaceName], r12; pszFaceName
0x1800020c2  mov     [rsp+250h+iPitchAndFamily], edx; iPitchAndFamily
0x1800020c6  mov     edx, [rbp+150h+cWidth]; cWidth
0x1800020c9  mov     [rsp+250h+iQuality], r8d; iQuality
0x1800020ce  mov     r8d, [rbp+150h+cEscapement]; cEscapement
0x1800020d2  mov     [rsp+250h+iClipPrecision], r9d; iClipPrecision
0x1800020d7  mov     r9d, [rbp+150h+cOrientation]; cOrientation
0x1800020db  mov     [rsp+250h+iOutPrecision], r10d; iOutPrecision
0x1800020e0  shr     eax, 14h
0x1800020e3  movzx   ecx, al
0x1800020e6  movzx   eax, [rbp+150h+var_1BC]
0x1800020ea  mov     [rsp+250h+iCharSet], ecx; iCharSet
0x1800020ee  mov     ecx, [rbp+150h+pv]; cHeight
0x1800020f1  mov     [rsp+250h+bStrikeOut], 0; bStrikeOut
0x1800020f9  mov     [rsp+250h+bUnderline], 0; bUnderline
0x180002101  mov     [rsp+250h+bItalic], eax; bItalic
0x180002105  mov     eax, [rbp+150h+var_1C0]
0x180002108  mov     [rsp+250h+cWeight], eax; cWeight
0x18000210c  call    CreateFontA
0x180002111  mov     r12, rax
0x180002114  test    rax, rax
0x180002117  jz      loc_1800021B7
0x18000211d  mov     rcx, [rbx]; hdc
0x180002120  mov     rdx, rax; h
0x180002123  call    cs:__imp_SelectObject
0x18000212a  nop     dword ptr [rax+rax+00h]
0x18000212f  test    rax, rax
0x180002132  jz      short loc_180002196
0x180002134  xor     ecx, ecx
0x180002136  lea     r8, [rbp+150h+var_170]
0x18000213a  mov     [rbp+150h+var_130], cx
0x18000213e  lea     edx, [rcx+20h]
0x180002141  mov     rcx, [rbx]
0x180002144  call    GetTextFaceAliasW
0x180002149  test    eax, eax
0x18000214b  jz      short loc_180002196
0x18000214d  lea     rax, [rbp+150h+WideCharStr]
0x180002154  lea     r8, [rbp+150h+var_170]
0x180002158  sub     r8, rax
0x18000215b  movzx   edx, word ptr [rax]
0x18000215e  movzx   ecx, word ptr [rax+r8]
0x180002163  sub     edx, ecx
0x180002165  jnz     short loc_18000216F
0x180002167  add     rax, 2
0x18000216b  test    ecx, ecx
0x18000216d  jnz     short loc_18000215B
0x18000216f  test    edx, edx
0x180002171  jnz     short loc_180002196
0x180002173  lea     rcx, __ImageBase
0x18000217a  mov     r8, ds:rva ?iStandardFallbackCandidates@@3QAY01$$CBUSTANDARD_FALLBACK_CANDIDATES@@A[rcx+rdi*8]; struct FONT_VALID_INFO *
0x180002182  test    r8, r8
0x180002185  jz      short loc_1800021CD
0x180002187  mov     edx, [rbx+8]; unsigned int
0x18000218a  mov     rcx, [rbx]; HDC
0x18000218d  call    ?FontIsValid@@YA_NPEAUHDC__@@KPEAUFONT_VALID_INFO@@@Z; FontIsValid(HDC__ *,ulong,FONT_VALID_INFO *)
0x180002192  test    al, al
0x180002194  jnz     short loc_1800021C6
0x180002196  mov     rcx, [rbx]; hdc
0x180002199  mov     rdx, r15; h
0x18000219c  call    cs:__imp_SelectObject
0x1800021a3  nop     dword ptr [rax+rax+00h]
0x1800021a8  mov     rcx, r12; ho
0x1800021ab  call    cs:__imp_DeleteObject
0x1800021b2  nop     dword ptr [rax+rax+00h]
0x1800021b7  inc     r14d
0x1800021ba  lea     r12, __ImageBase
0x1800021c1  jmp     loc_180002017
0x1800021c6  lea     rcx, __ImageBase
0x1800021cd  mov     eax, ds:rva dword_1800B18F8[rcx+rdi*8]
0x1800021d4  jmp     loc_180002396
0x1800021d9  cmp     r14d, 2
0x1800021dd  jge     loc_1800023BE
0x1800021e3  movsxd  rax, r14d
0x1800021e6  lea     rdi, [rax+rsi*2]
0x1800021ea  add     rdi, rdi
0x1800021ed  movsxd  rax, ds:rva dword_1800AFCD8[r12+rdi*8]
0x1800021f5  cmp     eax, 0FFFFFFFFh
0x1800021f8  jz      loc_1800023BE
0x1800021fe  add     rax, rax
0x180002201  mov     [rsp+250h+var_1D8], 0
0x18000220a  lea     r8, [rsp+250h+var_1D8]; unsigned __int64 *
0x18000220f  mov     [rsp+250h+var_1E0], 0
0x180002217  mov     edx, 21h ; '!'; unsigned __int64
0x18000221c  mov     r12, ds:rva ?StandardFallbackFontOld@@3QBUFALLBACK_FONT@@B[r12+rax*8]; FALLBACK_FONT const near * const StandardFallbackFontOld ...
0x180002224  mov     rcx, r12; char *
0x180002227  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18000222c  test    eax, eax
0x18000222e  js      loc_1800023BE
0x180002234  mov     edx, dword ptr [rsp+250h+var_1D8]
0x180002238  lea     rax, [rsp+250h+var_1E0]
0x18000223d  inc     edx; cchWideChar
0x18000223f  mov     qword ptr [rsp+250h+cWeight], rax; int *
0x180002244  lea     r9, [rbp+150h+var_80]; lpWideCharStr
0x18000224b  xor     r8d, r8d; lpSrc
0x18000224e  mov     rcx, r12; lpMultiByteStr
0x180002251  call    ?AnsiToUnicode@@YAJPEBDHIPEA_WPEAH@Z; AnsiToUnicode(char const *,int,uint,wchar_t *,int *)
0x180002256  test    eax, eax
0x180002258  js      loc_1800023BE
0x18000225e  movzx   edx, [rbp+150h+var_1B5]
0x180002262  lea     rax, __ImageBase
0x180002269  mov     eax, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rax+rsi*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x180002270  movzx   r8d, [rbp+150h+var_1B6]
0x180002275  movzx   r9d, [rbp+150h+var_1B7]
0x18000227a  movzx   r10d, [rbp+150h+var_1B8]
0x18000227f  mov     [rsp+250h+pszFaceName], r12; pszFaceName
0x180002284  mov     [rsp+250h+iPitchAndFamily], edx; iPitchAndFamily
0x180002288  mov     edx, [rbp+150h+cWidth]; cWidth
0x18000228b  mov     [rsp+250h+iQuality], r8d; iQuality
0x180002290  mov     r8d, [rbp+150h+cEscapement]; cEscapement
0x180002294  mov     [rsp+250h+iClipPrecision], r9d; iClipPrecision
0x180002299  mov     r9d, [rbp+150h+cOrientation]; cOrientation
0x18000229d  mov     [rsp+250h+iOutPrecision], r10d; iOutPrecision
0x1800022a2  shr     eax, 14h
0x1800022a5  movzx   ecx, al
0x1800022a8  movzx   eax, [rbp+150h+var_1BC]
0x1800022ac  mov     [rsp+250h+iCharSet], ecx; iCharSet
0x1800022b0  mov     ecx, [rbp+150h+pv]; cHeight
0x1800022b3  mov     [rsp+250h+bStrikeOut], 0; bStrikeOut
0x1800022bb  mov     [rsp+250h+bUnderline], 0; bUnderline
0x1800022c3  mov     [rsp+250h+bItalic], eax; bItalic
0x1800022c7  mov     eax, [rbp+150h+var_1C0]
0x1800022ca  mov     [rsp+250h+cWeight], eax; cWeight
0x1800022ce  call    CreateFontA
0x1800022d3  mov     r12, rax
0x1800022d6  test    rax, rax
0x1800022d9  jz      loc_180002379
0x1800022df  mov     rcx, [rbx]; hdc
0x1800022e2  mov     rdx, rax; h
0x1800022e5  call    cs:__imp_SelectObject
0x1800022ec  nop     dword ptr [rax+rax+00h]
0x1800022f1  test    rax, rax
0x1800022f4  jz      short loc_180002358
0x1800022f6  xor     ecx, ecx
0x1800022f8  lea     r8, [rbp+150h+var_120]
0x1800022fc  mov     [rbp+150h+var_E0], cx
0x180002300  lea     edx, [rcx+20h]
0x180002303  mov     rcx, [rbx]
0x180002306  call    GetTextFaceAliasW
0x18000230b  test    eax, eax
0x18000230d  jz      short loc_180002358
0x18000230f  lea     rax, [rbp+150h+var_80]
0x180002316  lea     r8, [rbp+150h+var_120]
0x18000231a  sub     r8, rax
0x18000231d  movzx   edx, word ptr [rax]
0x180002320  movzx   ecx, word ptr [rax+r8]
0x180002325  sub     edx, ecx
0x180002327  jnz     short loc_180002331
0x180002329  add     rax, 2
0x18000232d  test    ecx, ecx
0x18000232f  jnz     short loc_18000231D
0x180002331  test    edx, edx
0x180002333  jnz     short loc_180002358
0x180002335  lea     rcx, __ImageBase
0x18000233c  mov     r8, ds:rva ?iStandardFallbackCandidatesOld@@3QAY01$$CBUSTANDARD_FALLBACK_CANDIDATES@@A[rcx+rdi*8]; struct FONT_VALID_INFO *
0x180002344  test    r8, r8
0x180002347  jz      short loc_18000238F
0x180002349  mov     edx, [rbx+8]; unsigned int
0x18000234c  mov     rcx, [rbx]; HDC
0x18000234f  call    ?FontIsValid@@YA_NPEAUHDC__@@KPEAUFONT_VALID_INFO@@@Z; FontIsValid(HDC__ *,ulong,FONT_VALID_INFO *)
0x180002354  test    al, al
0x180002356  jnz     short loc_180002388
0x180002358  mov     rcx, [rbx]; hdc
0x18000235b  mov     rdx, r15; h
0x18000235e  call    cs:__imp_SelectObject
0x180002365  nop     dword ptr [rax+rax+00h]
0x18000236a  mov     rcx, r12; ho
0x18000236d  call    cs:__imp_DeleteObject
0x180002374  nop     dword ptr [rax+rax+00h]
0x180002379  inc     r14d
0x18000237c  lea     r12, __ImageBase
0x180002383  jmp     loc_1800021D9
0x180002388  lea     rcx, __ImageBase
0x18000238f  mov     eax, ds:rva dword_1800AFCD8[rcx+rdi*8]
0x180002396  mov     rva ?iStandardFallback@@3PAHA[rcx+rsi*4], eax; int near * iStandardFallback ...
0x18000239d  mov     rdx, r15; h
0x1800023a0  mov     rcx, [rbx]; hdc
0x1800023a3  call    cs:__imp_SelectObject
0x1800023aa  nop     dword ptr [rax+rax+00h]
0x1800023af  mov     rcx, r12; ho
0x1800023b2  call    cs:__imp_DeleteObject
0x1800023b9  nop     dword ptr [rax+rax+00h]
0x1800023be  mov     rcx, [rbp+150h+var_30]
0x1800023c5  xor     rcx, rsp; StackCookie
0x1800023c8  call    __security_check_cookie
0x1800023cd  lea     r11, [rsp+250h+var_20]
0x1800023d5  mov     rbx, [r11+40h]
0x1800023d9  mov     rsi, [r11+48h]
0x1800023dd  mov     rsp, r11
0x1800023e0  pop     r15
0x1800023e2  pop     r14
0x1800023e4  pop     r12
0x1800023e6  pop     rdi
0x1800023e7  pop     rbp
0x1800023e8  retn
```
