# CreateFallbackFont(tag_STRING_ANALYSIS *,int,int)

- ea: `0x180002ac8`
- end: `0x180002fd2`
- name: `?CreateFallbackFont@@YAJPEAUtag_STRING_ANALYSIS@@HH@Z`
- size: `1290`
- prototype: `__int64 __fastcall(struct tag_STRING_ANALYSIS *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800029c0`

## callees

- `0x180002ac8`
- `0x180002fd8`
- `0x180003014`
- `0x180004c00`
- `0x180006a28`
- `0x18001bc70`
- `0x180025cb0`
- `0x18002eee0`

## import_xrefs

- `GDI32!SelectObject` at `0x180002cdb`
- `GDI32!SelectObject` at `0x180002e9d`
- `GDI32!SelectObject` at `0x180002ee7`
- `GDI32!SelectObject` at `0x180002f7a`
- `GDI32!SelectObject` at `0x180002fbc`
- `GDI32!SelectObject` at `0x180002cdb`
- `GDI32!SelectObject` at `0x180002e9d`
- `GDI32!SelectObject` at `0x180002ee7`
- `GDI32!SelectObject` at `0x180002f7a`
- `GDI32!SelectObject` at `0x180002fbc`
- `GDI32!DeleteObject` at `0x180002eb5`
- `GDI32!DeleteObject` at `0x180002f03`
- `GDI32!DeleteObject` at `0x180002f31`
- `GDI32!DeleteObject` at `0x180002f64`
- `GDI32!DeleteObject` at `0x180002fa6`
- `GDI32!DeleteObject` at `0x180002eb5`
- `GDI32!DeleteObject` at `0x180002f03`
- `GDI32!DeleteObject` at `0x180002f31`
- `GDI32!DeleteObject` at `0x180002f64`
- `GDI32!DeleteObject` at `0x180002fa6`

## pseudocode

```c
__int64 __fastcall CreateFallbackFont(struct tag_STRING_ANALYSIS *a1, int a2, int a3)
{
  __int64 v3; // r12
  int v5; // esi
  int v6; // ebx
  __int64 v7; // rbp
  __int64 v8; // rdi
  int *v9; // r15
  const CHAR *pszFaceName; // r11
  void *DCObject; // rax
  __int64 result; // rax
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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl'::`2'::impl);
  v7 = v6;
  if ( *((_QWORD *)a1 + v6 + 114) )
    return 0;
  v8 = *((_QWORD *)a1 + 55);
  if ( !v8 || !*(_QWORD *)(v8 + 80) )
    return 2147500037LL;
  if ( *((_QWORD *)a1 + 114) )
  {
    v9 = (int *)((char *)a1 + 340);
    goto LABEL_8;
  }
  DCObject = (void *)GetDCObject(*(_QWORD *)a1, 655360);
  *((_QWORD *)a1 + 114) = DCObject;
  if ( !DCObject || (v9 = (int *)((char *)a1 + 340), !GetObjectA(DCObject, 60, (char *)a1 + 340)) )
  {
    *((_QWORD *)a1 + v6 + 114) = -1;
    return 2147500037LL;
  }
LABEL_8:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl'::`2'::impl) )
  {
    if ( (_DWORD)v3 != 12 )
    {
      pszFaceName = (&off_1800AFA30)[2 * v6];
      goto LABEL_11;
    }
  }
  else if ( (_DWORD)v3 != 12 )
  {
    pszFaceName = off_1800AF7A0[2 * v6];
LABEL_11:
    v26 = pszFaceName;
    goto LABEL_19;
  }
  pszFaceName = GetSurrogateFontName(*(struct FACE_CACHE **)(v8 + 80), v6 - 42);
  v26 = pszFaceName;
LABEL_19:
  FontA = CreateFontA(
            *v9,
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
LABEL_20:
    result = 2147746304LL;
    *((_QWORD *)a1 + v6 + 114) = -1;
    return result;
  }
  if ( !SelectObject(*(HDC *)a1, FontA) )
  {
    DeleteObject(*((HGDIOBJ *)a1 + v6 + 114));
    goto LABEL_20;
  }
  *((_DWORD *)a1 + 84) = v6;
  v14 = (void **)((char *)a1 + 8 * v6 + 440);
  *v14 = 0;
  v15 = ScriptCheckCache(v14, v3, *(HDC *)a1);
  if ( v15 < 0 )
  {
    DeleteObject(*((HGDIOBJ *)a1 + v7 + 114));
    SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
    *((_QWORD *)a1 + v7 + 114) = -(__int64)(v15 != -2147220992);
    goto LABEL_40;
  }
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
  if ( !v24 || (*((_QWORD *)a1 + v7 + 114) = v24, (v25 = SelectObject(*(HDC *)a1, v24)) == 0) )
  {
    DeleteObject(*((HGDIOBJ *)a1 + v7 + 114));
    SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
    v15 = -2147220992;
    goto LABEL_39;
  }
  DeleteObject(v25);
  *v14 = 0;
  v15 = ScriptCheckCache((void **)a1 + v7 + 55, v3, *(HDC *)a1);
  if ( v15 >= 0 )
    return 0;
  SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
  if ( v15 != -2147220992 )
  {
    DeleteObject(*((HGDIOBJ *)a1 + v7 + 114));
LABEL_39:
    *((_QWORD *)a1 + v7 + 114) = -1;
  }
LABEL_40:
  *v14 = 0;
  result = (unsigned int)v15;
  *((_DWORD *)a1 + 84) = 0;
  return result;
}

```

## disassembly

```asm
0x180002ac8  mov     [rsp+arg_10], rbx
0x180002acd  push    rbp
0x180002ace  push    rsi
0x180002acf  push    rdi
0x180002ad0  push    r12
0x180002ad2  push    r13
0x180002ad4  push    r14
0x180002ad6  push    r15
0x180002ad8  sub     rsp, 70h
0x180002adc  movsxd  r12, edx
0x180002adf  mov     r14, rcx
0x180002ae2  lea     rcx, __ImageBase
0x180002ae9  mov     esi, 1
0x180002aee  cmp     r12d, 0Ch
0x180002af2  jz      loc_180002B8C
0x180002af8  mov     ebx, rva ?iStandardFallback@@3PAHA[rcx+r12*4]; int near * iStandardFallback ...
0x180002b00  add     ebx, esi
0x180002b02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl(void)'::`2'::impl
0x180002b09  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(void)
0x180002b0e  movsxd  rbp, ebx
0x180002b11  xor     r13d, r13d
0x180002b14  cmp     [r14+rbp*8+390h], r13
0x180002b1c  jnz     loc_180002DB4
0x180002b22  mov     rdi, [r14+1B8h]
0x180002b29  test    rdi, rdi
0x180002b2c  jz      loc_180002BE4
0x180002b32  cmp     [rdi+50h], r13
0x180002b36  jz      loc_180002BE4
0x180002b3c  cmp     [r14+390h], r13
0x180002b43  jz      short loc_180002BA0
0x180002b45  lea     r15, [r14+154h]
0x180002b4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DengXianFont>::GetImpl(void)'::`2'::impl
0x180002b53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DengXianFont@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DengXianFont>::__private_IsEnabled(void)
0x180002b58  test    al, al
0x180002b5a  jnz     loc_180002BEE
0x180002b60  cmp     r12d, 0Ch
0x180002b64  jz      loc_180002BF8
0x180002b6a  mov     rax, rbp
0x180002b6d  lea     rcx, __ImageBase
0x180002b74  add     rax, rax
0x180002b77  mov     r11, ds:rva off_1800AF7A0[rcx+rax*8]; "wglMakeCurrent" ...
0x180002b7f  mov     [rsp+0A8h+arg_0], r11
0x180002b87  jmp     loc_180002C16
0x180002b8c  mov     rax, [r14+0D8h]
0x180002b93  movsxd  r8, r8d
0x180002b96  movzx   ebx, byte ptr [rax+r8]
0x180002b9b  jmp     loc_180002B02
0x180002ba0  mov     rcx, [r14]
0x180002ba3  mov     edx, 0A0000h
0x180002ba8  call    GetDCObject
0x180002bad  mov     [r14+390h], rax
0x180002bb4  test    rax, rax
0x180002bb7  jz      short loc_180002BD8
0x180002bb9  lea     r15, [r14+154h]
0x180002bc0  mov     edx, 3Ch ; '<'; c
0x180002bc5  mov     r8, r15; pv
0x180002bc8  mov     rcx, rax; h
0x180002bcb  call    GetObjectA
0x180002bd0  test    eax, eax
0x180002bd2  jnz     loc_180002B4C
0x180002bd8  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002bdc  mov     [r14+rbp*8+390h], r15
0x180002be4  mov     eax, 80004005h
0x180002be9  jmp     loc_180002CBC
0x180002bee  cmp     r12d, 0Ch
0x180002bf2  jnz     loc_180002F42
0x180002bf8  mov     rcx, [rdi+50h]; struct FACE_CACHE *
0x180002bfc  lea     edx, [rbx-2Ah]; int
0x180002bff  call    ?GetSurrogateFontName@@YAPEADPEAUFACE_CACHE@@H@Z; GetSurrogateFontName(FACE_CACHE *,int)
0x180002c04  mov     r11, rax
0x180002c07  mov     [rsp+0A8h+arg_0], rax
0x180002c0f  lea     rcx, __ImageBase
0x180002c16  mov     eax, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rcx+r12*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x180002c1e  movzx   edx, byte ptr [r14+16Fh]
0x180002c26  movzx   r8d, byte ptr [r14+16Eh]
0x180002c2e  movzx   r9d, byte ptr [r14+16Dh]
0x180002c36  movzx   r10d, byte ptr [r14+16Ch]
0x180002c3e  mov     [rsp+0A8h+pszFaceName], r11; pszFaceName
0x180002c43  mov     [rsp+0A8h+iPitchAndFamily], edx; iPitchAndFamily
0x180002c47  mov     edx, [r14+158h]; cWidth
0x180002c4e  mov     [rsp+0A8h+iQuality], r8d; iQuality
0x180002c53  mov     r8d, [r14+15Ch]; cEscapement
0x180002c5a  mov     [rsp+0A8h+iClipPrecision], r9d; iClipPrecision
0x180002c5f  mov     r9d, [r14+160h]; cOrientation
0x180002c66  mov     [rsp+0A8h+iOutPrecision], r10d; iOutPrecision
0x180002c6b  shr     eax, 14h
0x180002c6e  movzx   ecx, al
0x180002c71  movzx   eax, byte ptr [r14+168h]
0x180002c79  mov     [rsp+0A8h+iCharSet], ecx; iCharSet
0x180002c7d  mov     ecx, [r15]; cHeight
0x180002c80  mov     [rsp+0A8h+bStrikeOut], r13d; bStrikeOut
0x180002c85  mov     [rsp+0A8h+bUnderline], r13d; bUnderline
0x180002c8a  mov     [rsp+0A8h+bItalic], eax; bItalic
0x180002c8e  mov     eax, [r14+164h]
0x180002c95  mov     [rsp+0A8h+cWeight], eax; cWeight
0x180002c99  call    CreateFontA
0x180002c9e  mov     [r14+rbp*8+390h], rax
0x180002ca6  test    rax, rax
0x180002ca9  jnz     short loc_180002CD5
0x180002cab  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002caf  mov     eax, 80040200h
0x180002cb4  mov     [r14+rbp*8+390h], r15
0x180002cbc  mov     rbx, [rsp+0A8h+arg_10]
0x180002cc4  add     rsp, 70h
0x180002cc8  pop     r15
0x180002cca  pop     r14
0x180002ccc  pop     r13
0x180002cce  pop     r12
0x180002cd0  pop     rdi
0x180002cd1  pop     rsi
0x180002cd2  pop     rbp
0x180002cd3  retn
0x180002cd5  mov     rcx, [r14]; hdc
0x180002cd8  mov     rdx, rax; h
0x180002cdb  call    cs:__imp_SelectObject
0x180002ce2  nop     dword ptr [rax+rax+00h]
0x180002ce7  test    rax, rax
0x180002cea  jz      loc_180002F29
0x180002cf0  mov     [r14+150h], ebx
0x180002cf7  lea     r13, [r14+1B8h]
0x180002cfe  lea     r13, [r13+rbp*8+0]
0x180002d03  xor     edi, edi
0x180002d05  mov     [r13+0], rdi
0x180002d09  mov     edx, r12d; int
0x180002d0c  mov     r8, [r14]; HDC
0x180002d0f  mov     rcx, r13; void **
0x180002d12  call    ?ScriptCheckCache@@YAJPEAPEAXHPEAUHDC__@@@Z; ScriptCheckCache(void * *,int,HDC__ *)
0x180002d17  mov     ebx, eax
0x180002d19  test    eax, eax
0x180002d1b  js      loc_180002F5C
0x180002d21  mov     r8, [r13+0]
0x180002d25  mov     r9d, [r8+30h]
0x180002d29  test    r9d, r9d
0x180002d2c  jle     loc_180002DB4
0x180002d32  mov     r8d, [r8+10h]
0x180002d36  sub     r8d, r9d
0x180002d39  test    r8d, r8d
0x180002d3c  jle     short loc_180002DB4
0x180002d3e  mov     rax, [r14+1B8h]
0x180002d45  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002d49  mov     r11d, [rax+30h]
0x180002d4d  mov     r10d, [rax+10h]
0x180002d51  mov     eax, r11d
0x180002d54  shl     eax, 0Ah
0x180002d57  sub     r10d, r11d
0x180002d5a  cdq
0x180002d5b  idiv    r9d
0x180002d5e  mov     ecx, eax
0x180002d60  mov     eax, r10d
0x180002d63  shl     eax, 0Ah
0x180002d66  cdq
0x180002d67  idiv    r8d
0x180002d6a  cmp     ecx, eax
0x180002d6c  jz      short loc_180002D8F
0x180002d6e  cmovge  esi, r15d
0x180002d72  sub     r10d, esi
0x180002d75  shl     r10d, 0Ah
0x180002d79  lea     eax, [rsi+r11]
0x180002d7d  shl     eax, 0Ah
0x180002d80  cdq
0x180002d81  idiv    r9d
0x180002d84  mov     ecx, eax
0x180002d86  mov     eax, r10d
0x180002d89  cdq
0x180002d8a  idiv    r8d
0x180002d8d  cmp     ecx, eax
0x180002d8f  cmovge  ecx, eax
0x180002d92  mov     eax, 300h
0x180002d97  mov     [rsp+0A8h+arg_8], eax
0x180002d9e  cmp     ecx, eax
0x180002da0  jl      short loc_180002DBB
0x180002da2  lea     eax, [rcx-3E8h]
0x180002da8  mov     [rsp+0A8h+arg_8], ecx
0x180002daf  cmp     eax, 30h ; '0'
0x180002db2  ja      short loc_180002DBB
0x180002db4  xor     eax, eax
0x180002db6  jmp     loc_180002CBC
0x180002dbb  mov     rcx, r13; psc
0x180002dbe  call    ScriptFreeCache
0x180002dc3  movzx   r9d, byte ptr [r14+16Fh]
0x180002dcb  lea     rax, __ImageBase
0x180002dd2  mov     ecx, ds:rva ?ScriptProperties@@3QBUSCRIPT_PROPERTIES@@B[rax+r12*8]; SCRIPT_PROPERTIES const near * const ScriptProperties ...
0x180002dda  mov     r10d, 400h
0x180002de0  movzx   edi, byte ptr [r14+16Ch]
0x180002de8  movzx   r11d, byte ptr [r14+16Eh]
0x180002df0  movzx   ebx, byte ptr [r14+16Dh]
0x180002df8  movzx   esi, byte ptr [r14+168h]
0x180002e00  shr     ecx, 14h
0x180002e03  movzx   r8d, cl
0x180002e07  mov     ecx, [rsp+0A8h+arg_8]
0x180002e0e  mov     eax, ecx
0x180002e10  imul    eax, [r14+158h]
0x180002e18  imul    ecx, [r14+154h]
0x180002e20  cdq
0x180002e21  idiv    r10d
0x180002e24  mov     r10d, eax
0x180002e27  mov     eax, ecx
0x180002e29  cdq
0x180002e2a  mov     ecx, 400h
0x180002e2f  idiv    ecx
0x180002e31  mov     edx, r10d; cWidth
0x180002e34  mov     ecx, eax; cHeight
0x180002e36  mov     rax, [rsp+0A8h+arg_0]
0x180002e3e  mov     [rsp+0A8h+pszFaceName], rax; pszFaceName
0x180002e43  mov     eax, [r14+164h]
0x180002e4a  mov     [rsp+0A8h+iPitchAndFamily], r9d; iPitchAndFamily
0x180002e4f  mov     r9d, [r14+160h]; cOrientation
0x180002e56  mov     [rsp+0A8h+iQuality], r11d; iQuality
0x180002e5b  mov     [rsp+0A8h+iClipPrecision], ebx; iClipPrecision
0x180002e5f  mov     [rsp+0A8h+iOutPrecision], edi; iOutPrecision
0x180002e63  xor     edi, edi
0x180002e65  mov     [rsp+0A8h+iCharSet], r8d; iCharSet
0x180002e6a  mov     r8d, [r14+15Ch]; cEscapement
0x180002e71  mov     [rsp+0A8h+bStrikeOut], edi; bStrikeOut
0x180002e75  mov     [rsp+0A8h+bUnderline], edi; bUnderline
0x180002e79  mov     [rsp+0A8h+bItalic], esi; bItalic
0x180002e7d  mov     [rsp+0A8h+cWeight], eax; cWeight
0x180002e81  call    CreateFontA
0x180002e86  test    rax, rax
0x180002e89  jz      loc_180002F9E
0x180002e8f  mov     [r14+rbp*8+390h], rax
0x180002e97  mov     rdx, rax; h
0x180002e9a  mov     rcx, [r14]; hdc
0x180002e9d  call    cs:__imp_SelectObject
0x180002ea4  nop     dword ptr [rax+rax+00h]
0x180002ea9  test    rax, rax
0x180002eac  jz      loc_180002F9E
0x180002eb2  mov     rcx, rax; ho
0x180002eb5  call    cs:__imp_DeleteObject
0x180002ebc  nop     dword ptr [rax+rax+00h]
0x180002ec1  mov     [r13+0], rdi
0x180002ec5  mov     edx, r12d; int
0x180002ec8  mov     r8, [r14]; HDC
0x180002ecb  mov     rcx, r13; void **
0x180002ece  call    ?ScriptCheckCache@@YAJPEAPEAXHPEAUHDC__@@@Z; ScriptCheckCache(void * *,int,HDC__ *)
0x180002ed3  mov     ebx, eax
0x180002ed5  test    eax, eax
0x180002ed7  jns     loc_180002DB4
0x180002edd  mov     rdx, [r14+390h]; h
0x180002ee4  mov     rcx, [r14]; hdc
0x180002ee7  call    cs:__imp_SelectObject
0x180002eee  nop     dword ptr [rax+rax+00h]
0x180002ef3  cmp     ebx, 80040200h
0x180002ef9  jz      short loc_180002F17
0x180002efb  mov     rcx, [r14+rbp*8+390h]; ho
0x180002f03  call    cs:__imp_DeleteObject
0x180002f0a  nop     dword ptr [rax+rax+00h]
0x180002f0f  mov     [r14+rbp*8+390h], r15
0x180002f17  mov     [r13+0], rdi
0x180002f1b  mov     eax, ebx
0x180002f1d  mov     [r14+150h], edi
0x180002f24  jmp     loc_180002CBC
0x180002f29  mov     rcx, [r14+rbp*8+390h]; ho
0x180002f31  call    cs:__imp_DeleteObject
0x180002f38  nop     dword ptr [rax+rax+00h]
0x180002f3d  jmp     loc_180002CAB
0x180002f42  mov     rax, rbp
0x180002f45  lea     rcx, __ImageBase
0x180002f4c  add     rax, rax
0x180002f4f  mov     r11, ds:rva off_1800AFA30[rcx+rax*8]; "Segoe UI Emoji" ...
0x180002f57  jmp     loc_180002B7F
0x180002f5c  mov     rcx, [r14+rbp*8+390h]; ho
0x180002f64  call    cs:__imp_DeleteObject
0x180002f6b  nop     dword ptr [rax+rax+00h]
0x180002f70  mov     rdx, [r14+390h]; h
0x180002f77  mov     rcx, [r14]; hdc
0x180002f7a  call    cs:__imp_SelectObject
0x180002f81  nop     dword ptr [rax+rax+00h]
0x180002f86  lea     ecx, [rbx+7FFBFE00h]
0x180002f8c  neg     ecx
0x180002f8e  sbb     rax, rax
0x180002f91  mov     [r14+rbp*8+390h], rax
0x180002f99  jmp     loc_180002F17
0x180002f9e  mov     rcx, [r14+rbp*8+390h]; ho
0x180002fa6  call    cs:__imp_DeleteObject
0x180002fad  nop     dword ptr [rax+rax+00h]
0x180002fb2  mov     rdx, [r14+390h]; h
0x180002fb9  mov     rcx, [r14]; hdc
0x180002fbc  call    cs:__imp_SelectObject
0x180002fc3  nop     dword ptr [rax+rax+00h]
0x180002fc8  mov     ebx, 80040200h
0x180002fcd  jmp     loc_180002F0F
```
