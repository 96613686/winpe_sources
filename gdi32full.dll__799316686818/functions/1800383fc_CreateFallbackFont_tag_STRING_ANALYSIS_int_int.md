# CreateFallbackFont(tag_STRING_ANALYSIS *,int,int)

- ea: `0x1800383fc`
- end: `0x180038894`
- name: `?CreateFallbackFont@@YAJPEAUtag_STRING_ANALYSIS@@HH@Z`
- size: `1176`
- prototype: `__int64 __fastcall(struct tag_STRING_ANALYSIS *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180038300`

## callees

- `0x180002c10`
- `0x18000d650`
- `0x18000e5a0`
- `0x180011380`
- `0x180025f00`
- `0x1800383fc`
- `0x18006a6d8`
- `0x180099710`

## import_xrefs

- `GDI32!SelectObject` at `0x180038603`
- `GDI32!SelectObject` at `0x180038663`
- `GDI32!SelectObject` at `0x180038809`
- `GDI32!SelectObject` at `0x180038824`
- `GDI32!SelectObject` at `0x18003885e`
- `GDI32!SelectObject` at `0x180038603`
- `GDI32!SelectObject` at `0x180038663`
- `GDI32!SelectObject` at `0x180038809`
- `GDI32!SelectObject` at `0x180038824`
- `GDI32!SelectObject` at `0x18003885e`
- `GDI32!DeleteObject` at `0x180038616`
- `GDI32!DeleteObject` at `0x180038653`
- `GDI32!DeleteObject` at `0x1800387f9`
- `GDI32!DeleteObject` at `0x180038832`
- `GDI32!DeleteObject` at `0x180038874`
- `GDI32!DeleteObject` at `0x180038616`
- `GDI32!DeleteObject` at `0x180038653`
- `GDI32!DeleteObject` at `0x1800387f9`
- `GDI32!DeleteObject` at `0x180038832`
- `GDI32!DeleteObject` at `0x180038874`

## pseudocode

```c
__int64 __fastcall CreateFallbackFont(struct tag_STRING_ANALYSIS *a1, int a2, int a3)
{
  __int64 v3; // r12
  int v5; // esi
  int v6; // ebx
  __int64 v7; // rbp
  __int64 result; // rax
  __int64 v9; // rdi
  HGDIOBJ CurrentObject; // rax
  int *v11; // r15
  const CHAR *pszFaceName; // r11
  HFONT FontA; // rax
  void **v14; // r13
  int v15; // ebx
  int v16; // r9d
  int v17; // r8d
  __int64 v18; // rax
  int v19; // r11d
  int v20; // r10d
  int v21; // ecx
  int v22; // eax
  bool v23; // cc
  HFONT v24; // rax
  HGDIOBJ v25; // rax
  const CHAR *v26; // [rsp+B0h] [rbp+8h]
  int v27; // [rsp+B8h] [rbp+10h]

  v3 = a2;
  v5 = 1;
  if ( a2 == 12 )
    v6 = *(unsigned __int8 *)(*((_QWORD *)a1 + 27) + a3);
  else
    v6 = *((_DWORD *)&iStandardFallback + a2) + 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl'::`2'::impl);
  v7 = v6;
  if ( *((_QWORD *)a1 + v6 + 114) )
    return 0;
  v9 = *((_QWORD *)a1 + 55);
  if ( !v9 || !*(_QWORD *)(v9 + 80) )
    return 2147500037LL;
  if ( *((_QWORD *)a1 + 114) )
  {
    v11 = (int *)((char *)a1 + 340);
  }
  else
  {
    CurrentObject = GetCurrentObject(*(HDC *)a1, 6u);
    *((_QWORD *)a1 + 114) = CurrentObject;
    if ( !CurrentObject || (v11 = (int *)((char *)a1 + 340), !GetObjectA(CurrentObject, 60, (char *)a1 + 340)) )
    {
      *((_QWORD *)a1 + v6 + 114) = -1;
      return 2147500037LL;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl'::`2'::impl) )
  {
    if ( (_DWORD)v3 != 12 )
    {
      pszFaceName = (const CHAR *)qword_1800B0260[2 * v6];
      goto LABEL_20;
    }
LABEL_18:
    pszFaceName = GetSurrogateFontName(*(struct FACE_CACHE **)(v9 + 80), v6 - 42);
    v26 = pszFaceName;
    goto LABEL_21;
  }
  if ( (_DWORD)v3 == 12 )
    goto LABEL_18;
  pszFaceName = (const CHAR *)qword_1800AE3B0[2 * v6];
LABEL_20:
  v26 = pszFaceName;
LABEL_21:
  FontA = CreateFontA(
            *v11,
            *((_DWORD *)a1 + 86),
            *((_DWORD *)a1 + 87),
            *((_DWORD *)a1 + 88),
            *((_DWORD *)a1 + 89),
            *((unsigned __int8 *)a1 + 360),
            0,
            0,
            (unsigned __int8)(LODWORD((&ScriptProperties)[v3]) >> 20),
            *((unsigned __int8 *)a1 + 364),
            *((unsigned __int8 *)a1 + 365),
            *((unsigned __int8 *)a1 + 366),
            *((unsigned __int8 *)a1 + 367),
            pszFaceName);
  *((_QWORD *)a1 + v6 + 114) = FontA;
  if ( !FontA )
  {
LABEL_22:
    result = 2147746304LL;
    *((_QWORD *)a1 + v6 + 114) = -1;
    return result;
  }
  if ( !SelectObject(*(HDC *)a1, FontA) )
  {
    DeleteObject(*((HGDIOBJ *)a1 + v6 + 114));
    goto LABEL_22;
  }
  *((_DWORD *)a1 + 84) = v6;
  v14 = (void **)((char *)a1 + 8 * v6 + 440);
  *v14 = 0;
  v15 = ScriptCheckCache(v14, v3, *(HDC *)a1);
  if ( v15 >= 0 )
  {
    v16 = *((_DWORD *)*v14 + 12);
    if ( v16 <= 0 )
      return 0;
    v17 = *((_DWORD *)*v14 + 4) - v16;
    if ( v17 <= 0 )
      return 0;
    v18 = *((_QWORD *)a1 + 55);
    v19 = *(_DWORD *)(v18 + 48);
    v20 = *(_DWORD *)(v18 + 16) - v19;
    v21 = (v19 << 10) / v16;
    v22 = (v20 << 10) / v17;
    v23 = v21 < v22;
    if ( v21 != v22 )
    {
      if ( v21 >= v22 )
        v5 = -1;
      v21 = ((v5 + v19) << 10) / v16;
      v22 = ((v20 - v5) << 10) / v17;
      v23 = v21 < v22;
    }
    if ( !v23 )
      v21 = v22;
    v27 = 768;
    if ( v21 >= 768 )
    {
      v27 = v21;
      if ( (unsigned int)(v21 - 1000) <= 0x30 )
        return 0;
    }
    ScriptFreeCache((SCRIPT_CACHE *)a1 + v7 + 55);
    v24 = CreateFontA(
            *((_DWORD *)a1 + 85) * v27 / 1024,
            *((_DWORD *)a1 + 86) * v27 / 1024,
            *((_DWORD *)a1 + 87),
            *((_DWORD *)a1 + 88),
            *((_DWORD *)a1 + 89),
            *((unsigned __int8 *)a1 + 360),
            0,
            0,
            (unsigned __int8)(LODWORD((&ScriptProperties)[v3]) >> 20),
            *((unsigned __int8 *)a1 + 364),
            *((unsigned __int8 *)a1 + 365),
            *((unsigned __int8 *)a1 + 366),
            *((unsigned __int8 *)a1 + 367),
            v26);
    if ( v24 && (*((_QWORD *)a1 + v7 + 114) = v24, (v25 = SelectObject(*(HDC *)a1, v24)) != 0) )
    {
      DeleteObject(v25);
      *v14 = 0;
      v15 = ScriptCheckCache((void **)a1 + v7 + 55, v3, *(HDC *)a1);
      if ( v15 >= 0 )
        return 0;
      SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
      if ( v15 == -2147220992 )
        goto LABEL_44;
      DeleteObject(*((HGDIOBJ *)a1 + v7 + 114));
    }
    else
    {
      DeleteObject(*((HGDIOBJ *)a1 + v7 + 114));
      SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
      v15 = -2147220992;
    }
    *((_QWORD *)a1 + v7 + 114) = -1;
  }
  else
  {
    DeleteObject(*((HGDIOBJ *)a1 + v7 + 114));
    SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
    *((_QWORD *)a1 + v7 + 114) = -(__int64)(v15 != -2147220992);
  }
LABEL_44:
  *v14 = 0;
  result = (unsigned int)v15;
  *((_DWORD *)a1 + 84) = 0;
  return result;
}

```

## disassembly

```asm
0x1800383fc  mov     [rsp+arg_10], rbx
0x180038401  push    rbp
0x180038402  push    rsi
0x180038403  push    rdi
0x180038404  push    r12
0x180038406  push    r13
0x180038408  push    r14
0x18003840a  push    r15
0x18003840c  sub     rsp, 70h
0x180038410  movsxd  r12, edx
0x180038413  mov     r14, rcx
0x180038416  lea     rcx, __ImageBase
0x18003841d  mov     esi, 1
0x180038422  cmp     r12d, 0Ch
0x180038426  jnz     short loc_180038439
0x180038428  mov     rax, [r14+0D8h]
0x18003842f  movsxd  r8, r8d
0x180038432  movzx   ebx, byte ptr [rax+r8]
0x180038437  jmp     short loc_180038443
0x180038439  mov     ebx, rva ?iStandardFallback@@3PAHA[rcx+r12*4]; int near * iStandardFallback ...
0x180038441  add     ebx, esi
0x180038443  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl(void)'::`2'::impl
0x18003844a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(void)
0x18003844f  movsxd  rbp, ebx
0x180038452  xor     r13d, r13d
0x180038455  cmp     [r14+rbp*8+390h], r13
0x18003845d  jz      short loc_180038463
0x18003845f  xor     eax, eax
0x180038461  jmp     short loc_1800384C3
0x180038463  mov     rdi, [r14+1B8h]
0x18003846a  test    rdi, rdi
0x18003846d  jz      short loc_1800384BE
0x18003846f  cmp     [rdi+50h], r13
0x180038473  jz      short loc_1800384BE
0x180038475  cmp     [r14+390h], r13
0x18003847c  jnz     short loc_1800384DB
0x18003847e  mov     rcx, [r14]; hdc
0x180038481  mov     edx, 6; type
0x180038486  call    GetCurrentObject
0x18003848b  mov     [r14+390h], rax
0x180038492  test    rax, rax
0x180038495  jz      short loc_1800384B2
0x180038497  lea     r15, [r14+154h]
0x18003849e  mov     edx, 3Ch ; '<'; c
0x1800384a3  mov     r8, r15; pv
0x1800384a6  mov     rcx, rax; h
0x1800384a9  call    GetObjectA
0x1800384ae  test    eax, eax
0x1800384b0  jnz     short loc_1800384E2
0x1800384b2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800384b6  mov     [r14+rbp*8+390h], r15
0x1800384be  mov     eax, 80004005h
0x1800384c3  mov     rbx, [rsp+0A8h+arg_10]
0x1800384cb  add     rsp, 70h
0x1800384cf  pop     r15
0x1800384d1  pop     r14
0x1800384d3  pop     r13
0x1800384d5  pop     r12
0x1800384d7  pop     rdi
0x1800384d8  pop     rsi
0x1800384d9  pop     rbp
0x1800384da  retn
0x1800384db  lea     r15, [r14+154h]
0x1800384e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::GetImpl(void)'::`2'::impl
0x1800384e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EUDCCharacterSupport>::__private_IsEnabled(void)
0x1800384ee  test    al, al
0x1800384f0  jz      short loc_18003850F
0x1800384f2  cmp     r12d, 0Ch
0x1800384f6  jz      short loc_180038515
0x1800384f8  mov     rax, rbp
0x1800384fb  lea     rcx, __ImageBase
0x180038502  add     rax, rax
0x180038505  mov     r11, ds:rva qword_1800AE3B0[rcx+rax*8]
0x18003850d  jmp     short loc_18003854A
0x18003850f  cmp     r12d, 0Ch
0x180038513  jnz     short loc_180038535
0x180038515  mov     rcx, [rdi+50h]; struct FACE_CACHE *
0x180038519  lea     edx, [rbx-2Ah]; int
0x18003851c  call    ?GetSurrogateFontName@@YAPEADPEAUFACE_CACHE@@H@Z; GetSurrogateFontName(FACE_CACHE *,int)
0x180038521  mov     r11, rax
0x180038524  mov     [rsp+0A8h+arg_0], rax
0x18003852c  lea     rcx, __ImageBase
0x180038533  jmp     short loc_180038552
0x180038535  mov     rax, rbp
0x180038538  lea     rcx, __ImageBase
0x18003853f  add     rax, rax
0x180038542  mov     r11, ds:rva qword_1800B0260[rcx+rax*8]
0x18003854a  mov     [rsp+0A8h+arg_0], r11
0x180038552  mov     eax, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rcx+r12*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x18003855a  movzx   edx, byte ptr [r14+16Fh]
0x180038562  movzx   r8d, byte ptr [r14+16Eh]
0x18003856a  movzx   r9d, byte ptr [r14+16Dh]
0x180038572  movzx   r10d, byte ptr [r14+16Ch]
0x18003857a  mov     [rsp+0A8h+pszFaceName], r11; pszFaceName
0x18003857f  mov     [rsp+0A8h+iPitchAndFamily], edx; iPitchAndFamily
0x180038583  mov     edx, [r14+158h]; cWidth
0x18003858a  mov     [rsp+0A8h+iQuality], r8d; iQuality
0x18003858f  mov     r8d, [r14+15Ch]; cEscapement
0x180038596  mov     [rsp+0A8h+iClipPrecision], r9d; iClipPrecision
0x18003859b  mov     r9d, [r14+160h]; cOrientation
0x1800385a2  mov     [rsp+0A8h+iOutPrecision], r10d; iOutPrecision
0x1800385a7  shr     eax, 14h
0x1800385aa  movzx   ecx, al
0x1800385ad  movzx   eax, byte ptr [r14+168h]
0x1800385b5  mov     [rsp+0A8h+iCharSet], ecx; iCharSet
0x1800385b9  mov     ecx, [r15]; cHeight
0x1800385bc  mov     [rsp+0A8h+bStrikeOut], r13d; bStrikeOut
0x1800385c1  mov     [rsp+0A8h+bUnderline], r13d; bUnderline
0x1800385c6  mov     [rsp+0A8h+bItalic], eax; bItalic
0x1800385ca  mov     eax, [r14+164h]
0x1800385d1  mov     [rsp+0A8h+cWeight], eax; cWeight
0x1800385d5  call    CreateFontA
0x1800385da  mov     [r14+rbp*8+390h], rax
0x1800385e2  test    rax, rax
0x1800385e5  jnz     short loc_1800385FD
0x1800385e7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800385eb  mov     eax, 80040200h
0x1800385f0  mov     [r14+rbp*8+390h], r15
0x1800385f8  jmp     loc_1800384C3
0x1800385fd  mov     rcx, [r14]; hdc
0x180038600  mov     rdx, rax; h
0x180038603  call    cs:__imp_SelectObject
0x180038609  test    rax, rax
0x18003860c  jnz     short loc_18003861E
0x18003860e  mov     rcx, [r14+rbp*8+390h]; ho
0x180038616  call    cs:__imp_DeleteObject
0x18003861c  jmp     short loc_1800385E7
0x18003861e  mov     [r14+150h], ebx
0x180038625  lea     r13, [r14+1B8h]
0x18003862c  lea     r13, [r13+rbp*8+0]
0x180038631  xor     edi, edi
0x180038633  mov     [r13+0], rdi
0x180038637  mov     edx, r12d; int
0x18003863a  mov     r8, [r14]; HDC
0x18003863d  mov     rcx, r13; void **
0x180038640  call    ?ScriptCheckCache@@YAJPEAPEAXHPEAUHDC__@@@Z; ScriptCheckCache(void * *,int,HDC__ *)
0x180038645  mov     ebx, eax
0x180038647  test    eax, eax
0x180038649  jns     short loc_180038681
0x18003864b  mov     rcx, [r14+rbp*8+390h]; ho
0x180038653  call    cs:__imp_DeleteObject
0x180038659  mov     rdx, [r14+390h]; h
0x180038660  mov     rcx, [r14]; hdc
0x180038663  call    cs:__imp_SelectObject
0x180038669  lea     ecx, [rbx+7FFBFE00h]
0x18003866f  neg     ecx
0x180038671  sbb     rax, rax
0x180038674  mov     [r14+rbp*8+390h], rax
0x18003867c  jmp     loc_180038882
0x180038681  mov     r8, [r13+0]
0x180038685  mov     r9d, [r8+30h]
0x180038689  test    r9d, r9d
0x18003868c  jle     loc_18003845F
0x180038692  mov     r8d, [r8+10h]
0x180038696  sub     r8d, r9d
0x180038699  test    r8d, r8d
0x18003869c  jle     loc_18003845F
0x1800386a2  mov     rax, [r14+1B8h]
0x1800386a9  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800386ad  mov     r11d, [rax+30h]
0x1800386b1  mov     r10d, [rax+10h]
0x1800386b5  mov     eax, r11d
0x1800386b8  shl     eax, 0Ah
0x1800386bb  sub     r10d, r11d
0x1800386be  cdq
0x1800386bf  idiv    r9d
0x1800386c2  mov     ecx, eax
0x1800386c4  mov     eax, r10d
0x1800386c7  shl     eax, 0Ah
0x1800386ca  cdq
0x1800386cb  idiv    r8d
0x1800386ce  cmp     ecx, eax
0x1800386d0  jz      short loc_1800386F3
0x1800386d2  cmovge  esi, r15d
0x1800386d6  sub     r10d, esi
0x1800386d9  shl     r10d, 0Ah
0x1800386dd  lea     eax, [rsi+r11]
0x1800386e1  shl     eax, 0Ah
0x1800386e4  cdq
0x1800386e5  idiv    r9d
0x1800386e8  mov     ecx, eax
0x1800386ea  mov     eax, r10d
0x1800386ed  cdq
0x1800386ee  idiv    r8d
0x1800386f1  cmp     ecx, eax
0x1800386f3  cmovge  ecx, eax
0x1800386f6  mov     eax, 300h
0x1800386fb  mov     [rsp+0A8h+arg_8], eax
0x180038702  cmp     ecx, eax
0x180038704  jl      short loc_18003871C
0x180038706  lea     eax, [rcx-3E8h]
0x18003870c  mov     [rsp+0A8h+arg_8], ecx
0x180038713  cmp     eax, 30h ; '0'
0x180038716  jbe     loc_18003845F
0x18003871c  mov     rcx, r13; psc
0x18003871f  call    ScriptFreeCache
0x180038724  movzx   r9d, byte ptr [r14+16Fh]
0x18003872c  lea     rax, __ImageBase
0x180038733  mov     ecx, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rax+r12*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x18003873b  movzx   edi, byte ptr [r14+16Ch]
0x180038743  movzx   r11d, byte ptr [r14+16Eh]
0x18003874b  movzx   ebx, byte ptr [r14+16Dh]
0x180038753  movzx   esi, byte ptr [r14+168h]
0x18003875b  shr     ecx, 14h
0x18003875e  movzx   r8d, cl
0x180038762  mov     ecx, [rsp+0A8h+arg_8]
0x180038769  mov     eax, ecx
0x18003876b  imul    eax, [r14+158h]
0x180038773  imul    ecx, [r14+154h]
0x18003877b  cdq
0x18003877c  and     edx, 3FFh
0x180038782  lea     r10d, [rdx+rax]
0x180038786  mov     eax, ecx
0x180038788  cdq
0x180038789  sar     r10d, 0Ah
0x18003878d  and     edx, 3FFh
0x180038793  lea     ecx, [rdx+rax]
0x180038796  mov     rax, [rsp+0A8h+arg_0]
0x18003879e  mov     [rsp+0A8h+pszFaceName], rax; pszFaceName
0x1800387a3  mov     edx, r10d; cWidth
0x1800387a6  mov     eax, [r14+164h]
0x1800387ad  mov     [rsp+0A8h+iPitchAndFamily], r9d; iPitchAndFamily
0x1800387b2  mov     r9d, [r14+160h]; cOrientation
0x1800387b9  mov     [rsp+0A8h+iQuality], r11d; iQuality
0x1800387be  mov     [rsp+0A8h+iClipPrecision], ebx; iClipPrecision
0x1800387c2  mov     [rsp+0A8h+iOutPrecision], edi; iOutPrecision
0x1800387c6  xor     edi, edi
0x1800387c8  mov     [rsp+0A8h+iCharSet], r8d; iCharSet
0x1800387cd  mov     r8d, [r14+15Ch]; cEscapement
0x1800387d4  mov     [rsp+0A8h+bStrikeOut], edi; bStrikeOut
0x1800387d8  mov     [rsp+0A8h+bUnderline], edi; bUnderline
0x1800387dc  mov     [rsp+0A8h+bItalic], esi; bItalic
0x1800387e0  sar     ecx, 0Ah; cHeight
0x1800387e3  mov     [rsp+0A8h+cWeight], eax; cWeight
0x1800387e7  call    CreateFontA
0x1800387ec  test    rax, rax
0x1800387ef  jnz     short loc_180038816
0x1800387f1  mov     rcx, [r14+rbp*8+390h]; ho
0x1800387f9  call    cs:__imp_DeleteObject
0x1800387ff  mov     rdx, [r14+390h]; h
0x180038806  mov     rcx, [r14]; hdc
0x180038809  call    cs:__imp_SelectObject
0x18003880f  mov     ebx, 80040200h
0x180038814  jmp     short loc_18003887A
0x180038816  mov     [r14+rbp*8+390h], rax
0x18003881e  mov     rdx, rax; h
0x180038821  mov     rcx, [r14]; hdc
0x180038824  call    cs:__imp_SelectObject
0x18003882a  test    rax, rax
0x18003882d  jz      short loc_1800387F1
0x18003882f  mov     rcx, rax; ho
0x180038832  call    cs:__imp_DeleteObject
0x180038838  mov     [r13+0], rdi
0x18003883c  mov     edx, r12d; int
0x18003883f  mov     r8, [r14]; HDC
0x180038842  mov     rcx, r13; void **
0x180038845  call    ?ScriptCheckCache@@YAJPEAPEAXHPEAUHDC__@@@Z; ScriptCheckCache(void * *,int,HDC__ *)
0x18003884a  mov     ebx, eax
0x18003884c  test    eax, eax
0x18003884e  jns     loc_18003845F
0x180038854  mov     rdx, [r14+390h]; h
0x18003885b  mov     rcx, [r14]; hdc
0x18003885e  call    cs:__imp_SelectObject
0x180038864  cmp     ebx, 80040200h
0x18003886a  jz      short loc_180038882
0x18003886c  mov     rcx, [r14+rbp*8+390h]; ho
0x180038874  call    cs:__imp_DeleteObject
0x18003887a  mov     [r14+rbp*8+390h], r15
0x180038882  mov     [r13+0], rdi
0x180038886  mov     eax, ebx
0x180038888  mov     [r14+150h], edi
0x18003888f  jmp     loc_1800384C3
```
