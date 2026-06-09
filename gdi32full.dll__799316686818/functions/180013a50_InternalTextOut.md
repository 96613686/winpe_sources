# InternalTextOut

- ea: `0x180013a50`
- end: `0x1800141ba`
- name: `InternalTextOut`
- size: `1898`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int x@<edx>, RECT *lprect, void *pString, int, INT *lpDx, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x1800139f0`
- `0x18002fab0`
- `0x18002fdf0`
- `0x180075400`

## callees

- `0x180009d00`
- `0x180009ea0`
- `0x18000db8c`
- `0x18000f630`
- `0x180010d60`
- `0x180010e60`
- `0x180011050`
- `0x180011770`
- `0x180013320`
- `0x180013954`
- `0x180013a50`
- `0x180015020`
- `0x180015aa0`
- `0x180016750`
- `0x180016900`
- `0x180017610`
- `0x180017770`
- `0x180074ae0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013fe4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013fe4`
- `GDI32!ExtTextOutW` at `0x180013da4`
- `GDI32!ExtTextOutW` at `0x180013e02`
- `GDI32!ExtTextOutW` at `0x180013da4`
- `GDI32!ExtTextOutW` at `0x180013e02`
- `win32u!NtGdiAnyLinkedFonts` at `0x180013cb6`
- `win32u!NtGdiAnyLinkedFonts` at `0x180013cb6`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180013b3c`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180013b3c`

## pseudocode

```c
BOOL __fastcall InternalTextOut(
        HDC hdc,
        int x,
        int a3,
        int a4,
        RECT *lprect,
        const WCHAR *pString,
        int a7,
        INT *lpDx,
        int a9)
{
  HDC v9; // rdi
  char v11; // bl
  UINT TextAlign; // eax
  int v13; // r13d
  UINT v14; // r12d
  int CacheUpdateCount; // eax
  unsigned int v16; // ecx
  unsigned __int8 v17; // r14
  int v18; // ebx
  __int16 v19; // r13
  _BYTE *v20; // r11
  int v21; // ecx
  int v22; // ebx
  int v23; // eax
  DWORD dwFlags; // r14d
  const SCRIPT_DIGITSUBSTITUTE *v25; // rcx
  int v26; // eax
  HRESULT v27; // ebx
  UINT v29; // r12d
  signed int v30; // edi
  _BYTE *v31; // rcx
  _BYTE *v32; // rdi
  int v33; // ecx
  int v34; // r8d
  int i; // r8d
  WCHAR v36; // cx
  unsigned __int64 v37; // rax
  SCRIPT_CONTROL psc; // [rsp+78h] [rbp-90h] BYREF
  SCRIPT_STATE pss[2]; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v40; // [rsp+80h] [rbp-88h] BYREF
  int v41; // [rsp+84h] [rbp-84h]
  int iX; // [rsp+88h] [rbp-80h]
  HDC v43; // [rsp+90h] [rbp-78h] BYREF
  DWORD dwReserved; // [rsp+98h] [rbp-70h]
  SCRIPT_STRING_ANALYSIS pssa[2]; // [rsp+A0h] [rbp-68h] BYREF
  INT *piDx; // [rsp+B0h] [rbp-58h]
  RECT *prc; // [rsp+B8h] [rbp-50h]
  const WCHAR *v48; // [rsp+C8h] [rbp-40h]
  _BYTE *v49; // [rsp+D0h] [rbp-38h]
  int v50; // [rsp+D8h] [rbp-30h]
  int v51; // [rsp+DCh] [rbp-2Ch]
  _BYTE *v52; // [rsp+E0h] [rbp-28h]
  _BYTE v53[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v54[64]; // [rsp+128h] [rbp+20h] BYREF
  __int16 v55; // [rsp+168h] [rbp+60h]

  iX = x;
  v9 = hdc;
  v43 = hdc;
  prc = lprect;
  piDx = lpDx;
  v41 = a3;
  pssa[0] = 0;
  if ( !a7 || !pString )
  {
    v29 = a4 | 0x10;
    return ExtTextOutW(hdc, x, a3, v29, lprect, pString, a7, lpDx);
  }
  if ( (a4 & 0x2000) != 0 )
  {
    v29 = a4 | 0x1000;
    return ExtTextOutW(hdc, x, a3, v29, lprect, pString, a7, lpDx);
  }
  v11 = 1;
  *(_DWORD *)pss = (a4 & 0x80u) != 0 || (TextAlign = GetTextAlign(hdc), (TextAlign & 0x100) != 0) && TextAlign != -1;
  if ( (a4 & 0xC00) == 0xC00 )
  {
    v13 = 0;
  }
  else if ( (a4 & 0x400) != 0 )
  {
    v13 = 3;
  }
  else
  {
    v13 = -1;
    if ( (a4 & 0x800) != 0 )
      v13 = 1;
  }
  psc = (SCRIPT_CONTROL)v13;
  v14 = a4 & 0xFFFFF3FF;
  CacheUpdateCount = NlsGetCacheUpdateCount();
  if ( CacheUpdateCount != g_ulNlsUpdateCacheCount )
  {
    g_ulNlsUpdateCacheCount = CacheUpdateCount;
    ReadNLSScriptSettings();
  }
  if ( !v13 || v13 == 3 || *((_BYTE *)&g_DigitSubstitute + 4) != 1 )
    v11 = 3;
  v17 = v11 | 4;
  if ( *(_DWORD *)pss == (GetLayout(v9) & 1) )
    v17 = v11;
  if ( a7 >= 0 )
  {
    v18 = a7 - 1;
    v40 = UspAcquireTempAlloc(v16);
    v19 = v55 | 1;
    v48 = pString;
    v20 = 0;
    v55 |= 1u;
    v21 = 0;
    v49 = 0;
    v50 = a7;
    v51 = a7;
    pssa[1] = 0;
    v52 = 0;
    while ( v21 < v18 )
    {
      if ( (pString[v21] & 0xFC00) == 0xD800 && (pString[v21 + 1] & 0xFC00) == 0xDC00 )
      {
        v19 &= ~1u;
        v55 = v19;
        break;
      }
      ++v21;
    }
    if ( (v19 & 1) != 0 )
      goto LABEL_25;
    if ( a7 <= 16 )
    {
      v33 = 0;
      v34 = 0;
      v49 = v53;
      v51 = 0;
      v32 = v54;
      v52 = v54;
    }
    else
    {
      v30 = 8 * a7;
      if ( (a7 & 0x10000000) != 0 )
        goto LABEL_72;
      if ( !ghHeap )
      {
        if ( gfMemoryInitFailed )
          goto LABEL_72;
        if ( !(unsigned int)UspInitMemory() )
        {
          v19 = v55;
          v20 = v49;
          goto LABEL_72;
        }
      }
      v31 = CTempMemory::Alloc(v30);
      if ( !v31 )
      {
        v31 = HeapAlloc(ghHeap, 0, v30);
        if ( !v31 )
        {
          v19 = v55;
          v20 = 0;
          v49 = 0;
LABEL_72:
          v19 |= 1u;
          v55 = v19;
LABEL_25:
          if ( v20 )
          {
            if ( (v19 & 1) == 0 && v20 != v53 )
              UspFreeMem(v20);
LABEL_27:
            CTempMemory::~CTempMemory((CTempMemory *)&v40);
            v9 = v43;
          }
          else
          {
            for ( i = 0; i < a7; ++i )
            {
              v36 = v48[i];
              if ( (unsigned __int64)pccUnicodeClass < 0x30A )
              {
                LOWORD(v37) = (_WORD)pccUnicodeClass;
              }
              else
              {
                v37 = (unsigned __int64)pccUnicodeClass[HIBYTE(v36)];
                if ( v37 >= 0x30A )
                  LOWORD(v37) = *(_WORD *)(v37 + 2LL * (unsigned __int8)v36);
              }
              if ( (v17 & (unsigned __int8)byte_1800B6FE2[24 * (__int16)v37]) != 0 )
                goto LABEL_27;
            }
            CTempMemory::~CTempMemory((CTempMemory *)&v40);
            v9 = v43;
            if ( (unsigned int)FontHasWesternScript(v43) )
              return ExtTextOutW(v9, iX, v41, v14 | 0x1000, prc, pString, a7, piDx);
          }
          v13 = (int)psc;
          goto LABEL_29;
        }
      }
      v32 = &v31[4 * a7];
      v49 = v31;
      v33 = 0;
      v52 = v32;
      v51 = 0;
      v34 = 0;
    }
    do
    {
      if ( v34 < v18 && (pString[v34] & 0xFC00) == 0xD800 && (pString[v34 + 1] & 0xFC00) == 0xDC00 )
      {
        *(_DWORD *)&v32[4 * v34 + 4] = v33;
        *(_DWORD *)&v52[4 * v34] = v51;
        *(_DWORD *)&v49[4 * v51] = (pString[v34 + 1] & 0x3FF | ((pString[v34] & 0x3FF) << 10)) + 0x10000;
        v33 = v51 + 1;
        ++v34;
      }
      else
      {
        *(_DWORD *)&v32[4 * v34] = v33;
        *(_DWORD *)&v49[4 * v51] = pString[v34];
        v33 = v51 + 1;
      }
      v32 = v52;
      ++v34;
      v51 = v33;
    }
    while ( v34 < a7 );
    LOBYTE(v19) = v55;
    v20 = v49;
    goto LABEL_25;
  }
LABEL_29:
  if ( GetTextCharacterExtra(v9) )
    return ExtTextOutW(v9, iX, v41, v14 | 0x1000, prc, pString, a7, piDx);
  if ( ((GetObjectType(v9) - 4) & 0xFFFFFFF7) != 0 )
    v22 = 128;
  else
    v22 = 1073741952;
  if ( a9 == -1 || (unsigned int)GdiIsPlayMetafileDC(v9) )
    v23 = 32;
  else
    v23 = 0x8000000;
  psc = 0;
  dwFlags = v23 | v22 | (*(_DWORD *)pss << 8);
  pss[0] = 0;
  CheckUpdateNLSScriptSettings();
  if ( v13 >= 0 )
  {
    dwReserved = g_DigitSubstitute.dwReserved;
    LODWORD(v43) = g_DigitSubstitute;
    HIDWORD(v43) = *((_DWORD *)&g_DigitSubstitute + 1) ^ (unsigned __int8)(v13 ^ *((_BYTE *)&g_DigitSubstitute + 4));
    v25 = (const SCRIPT_DIGITSUBSTITUTE *)&v43;
  }
  else
  {
    v25 = &g_DigitSubstitute;
  }
  ScriptApplyDigitSubstitution(v25, &psc, pss);
  v26 = g_iUseFontLinking;
  if ( g_iUseFontLinking == -1 )
  {
    v26 = NtGdiAnyLinkedFonts();
    g_iUseFontLinking = v26;
  }
  if ( v26 )
    dwFlags |= 0x1000u;
  psc = (SCRIPT_CONTROL)(*(_DWORD *)&psc | 0x1800000);
  if ( ScriptStringAnalyse(v9, pString, a7, 0, -1, dwFlags, -1, &psc, pss, piDx, 0, 0, pssa) < 0 )
    return 0;
  v27 = ScriptStringOut(pssa[0], iX, v41, v14, prc, 0, 0, 0);
  ScriptStringFree(pssa);
  return v27 >= 0;
}

```

## disassembly

```asm
0x180013a50  mov     r11, rsp
0x180013a53  push    rbp
0x180013a54  push    rsi
0x180013a55  push    rdi
0x180013a56  push    r12
0x180013a58  push    r14
0x180013a5a  push    r15
0x180013a5c  lea     rbp, [r11-0C8h]
0x180013a63  sub     rsp, 198h
0x180013a6a  mov     rax, cs:__security_cookie
0x180013a71  xor     rax, rsp
0x180013a74  mov     [rbp+0C0h+var_50], rax
0x180013a78  movsxd  rsi, [rbp+0C0h+arg_30]
0x180013a7f  xor     r14d, r14d
0x180013a82  mov     r15, [rbp+0C0h+pString]
0x180013a89  mov     eax, edx
0x180013a8b  mov     [rbp+0C0h+iX], edx
0x180013a8e  mov     rdi, rcx
0x180013a91  mov     rdx, [rbp+0C0h+lpDx]
0x180013a98  mov     r12d, r9d
0x180013a9b  mov     [rbp+0C0h+var_138], rcx
0x180013a9f  mov     rcx, [rbp+0C0h+lprect]
0x180013aa6  mov     [rbp+0C0h+prc], rcx
0x180013aaa  mov     [rbp+0C0h+var_118], rdx
0x180013aae  mov     [rsp+1C0h+var_144], r8d
0x180013ab3  mov     [rbp+0C0h+pssa], r14
0x180013ab7  test    esi, esi
0x180013ab9  jz      loc_180013D85
0x180013abf  test    r15, r15
0x180013ac2  jz      loc_180013D85
0x180013ac8  bt      r9d, 0Dh
0x180013acd  jb      loc_1800141A0
0x180013ad3  mov     [r11-38h], rbx
0x180013ad7  mov     ebx, 1
0x180013adc  mov     [r11-40h], r13
0x180013ae0  test    r12b, r12b
0x180013ae3  js      short loc_180013AFF
0x180013ae5  mov     rcx, rdi; hdc
0x180013ae8  call    GetTextAlign
0x180013aed  bt      eax, 8
0x180013af1  jb      short loc_180013AFA
0x180013af3  mov     dword ptr [rsp+1C0h+pss.uBidiLevel], r14d
0x180013af8  jmp     short loc_180013B03
0x180013afa  cmp     eax, 0FFFFFFFFh
0x180013afd  jz      short loc_180013AF3
0x180013aff  mov     dword ptr [rsp+1C0h+pss.uBidiLevel], ebx
0x180013b03  mov     eax, r12d
0x180013b06  and     eax, 0C00h
0x180013b0b  cmp     eax, 0C00h
0x180013b10  jz      loc_180013E50
0x180013b16  bt      r12d, 0Ah
0x180013b1b  jb      loc_180014160
0x180013b21  bt      r12d, 0Bh
0x180013b26  mov     r13d, 0FFFFFFFFh
0x180013b2c  cmovb   r13d, ebx
0x180013b30  mov     dword ptr [rsp+1C0h+psc.uDefaultLanguage], r13d
0x180013b35  and     r12d, 0FFFFF3FFh
0x180013b3c  call    cs:__imp_NlsGetCacheUpdateCount
0x180013b42  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180013b48  jz      short loc_180013B55
0x180013b4a  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180013b50  call    ReadNLSScriptSettings
0x180013b55  test    r13d, r13d
0x180013b58  jnz     loc_180013E35
0x180013b5e  mov     ebx, 3
0x180013b63  mov     rcx, rdi; hdc
0x180013b66  call    GetLayout
0x180013b6b  and     eax, 1
0x180013b6e  mov     r14d, ebx
0x180013b71  or      r14d, 4
0x180013b75  cmp     dword ptr [rsp+1C0h+pss.uBidiLevel], eax
0x180013b79  cmovz   r14d, ebx
0x180013b7d  test    esi, esi
0x180013b7f  js      loc_180013C2C
0x180013b85  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x180013b8a  movzx   r13d, [rbp+0C0h+var_60]
0x180013b8f  lea     ebx, [rsi-1]
0x180013b92  xor     edi, edi
0x180013b94  mov     [rsp+1C0h+var_148], eax
0x180013b98  or      r13w, 1
0x180013b9d  mov     [rbp+0C0h+var_100], r15
0x180013ba1  xor     r11d, r11d
0x180013ba4  mov     [rbp+0C0h+var_60], r13w
0x180013ba9  xor     ecx, ecx
0x180013bab  mov     [rbp+0C0h+var_F8], r11
0x180013baf  mov     [rbp+0C0h+var_F0], esi
0x180013bb2  mov     r10d, 0FC00h
0x180013bb8  mov     [rbp+0C0h+var_EC], esi
0x180013bbb  mov     r9d, 0D800h
0x180013bc1  mov     [rbp+0C0h+var_120], rdi
0x180013bc5  mov     r8d, 0DC00h
0x180013bcb  mov     [rbp+0C0h+var_E8], rdi
0x180013bcf  nop
0x180013bd0  cmp     ecx, ebx
0x180013bd2  jge     short loc_180013BFC
0x180013bd4  movsxd  rdx, ecx
0x180013bd7  movzx   eax, word ptr [r15+rdx*2]
0x180013bdc  and     ax, r10w
0x180013be0  cmp     ax, r9w
0x180013be4  jz      loc_180014112
0x180013bea  inc     ecx
0x180013bec  jmp     short loc_180013BD0
0x180013bee  mov     eax, 0FFFEh
0x180013bf3  and     r13w, ax
0x180013bf7  mov     [rbp+0C0h+var_60], r13w
0x180013bfc  test    r13b, 1
0x180013c00  jz      loc_180013E58
0x180013c06  test    r11, r11
0x180013c09  jz      loc_180013F07
0x180013c0f  test    r13b, 1
0x180013c13  jz      loc_18001412B
0x180013c19  lea     rcx, [rsp+1C0h+var_148]; this
0x180013c1e  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180013c23  mov     rdi, [rbp+0C0h+var_138]
0x180013c27  mov     r13d, dword ptr [rsp+1C0h+psc.uDefaultLanguage]
0x180013c2c  mov     rcx, rdi; hdc
0x180013c2f  call    GetTextCharacterExtra
0x180013c34  test    eax, eax
0x180013c36  jnz     loc_180013DD4
0x180013c3c  mov     rcx, rdi; h
0x180013c3f  call    GetObjectType
0x180013c44  add     eax, 0FFFFFFFCh
0x180013c47  test    eax, 0FFFFFFF7h
0x180013c4c  jnz     loc_180014108
0x180013c52  mov     ebx, 40000080h
0x180013c57  cmp     [rbp+0C0h+arg_40], 0FFFFFFFFh
0x180013c5e  jnz     loc_180014033
0x180013c64  mov     eax, 20h ; ' '
0x180013c69  mov     r14d, dword ptr [rsp+1C0h+pss.uBidiLevel]
0x180013c6e  shl     r14d, 8
0x180013c72  or      r14d, ebx
0x180013c75  mov     dword ptr [rsp+1C0h+psc.uDefaultLanguage], 0
0x180013c7d  or      r14d, eax
0x180013c80  xor     eax, eax
0x180013c82  mov     word ptr [rsp+1C0h+pss.uBidiLevel], ax
0x180013c87  call    CheckUpdateNLSScriptSettings
0x180013c8c  lea     r8, [rsp+1C0h+pss]; pss
0x180013c91  test    r13d, r13d
0x180013c94  jns     loc_18001416B
0x180013c9a  lea     rcx, g_DigitSubstitute; psds
0x180013ca1  lea     rdx, [rsp+1C0h+psc]; psc
0x180013ca6  call    ScriptApplyDigitSubstitution
0x180013cab  mov     eax, cs:g_iUseFontLinking
0x180013cb1  cmp     eax, 0FFFFFFFFh
0x180013cb4  jnz     short loc_180013CC2
0x180013cb6  call    cs:__imp_NtGdiAnyLinkedFonts
0x180013cbc  mov     cs:g_iUseFontLinking, eax
0x180013cc2  test    eax, eax
0x180013cc4  jz      short loc_180013CCB
0x180013cc6  bts     r14d, 0Ch
0x180013ccb  or      dword ptr [rsp+1C0h+psc.uDefaultLanguage], 1800000h
0x180013cd3  lea     rax, [rbp+0C0h+pssa]
0x180013cd7  mov     [rsp+60h], rax; pssa
0x180013cdc  xor     r9d, r9d; cGlyphs
0x180013cdf  mov     rax, [rbp+0C0h+var_118]
0x180013ce3  mov     r8d, esi; cString
0x180013ce6  mov     [rsp+1C0h+pbInClass], 0; pbInClass
0x180013cef  mov     rdx, r15; pString
0x180013cf2  mov     [rsp+1C0h+pTabdef], 0; pTabdef
0x180013cfb  mov     rcx, rdi; hdc
0x180013cfe  mov     [rsp+1C0h+piDx], rax; piDx
0x180013d03  lea     rax, [rsp+1C0h+pss]
0x180013d08  mov     [rsp+1C0h+psState], rax; psState
0x180013d0d  lea     rax, [rsp+1C0h+psc]
0x180013d12  mov     [rsp+1C0h+psControl], rax; psControl
0x180013d17  mov     [rsp+1C0h+iReqWidth], 0FFFFFFFFh; iReqWidth
0x180013d1f  mov     [rsp+1C0h+dwFlags], r14d; dwFlags
0x180013d24  mov     [rsp+1C0h+iCharset], 0FFFFFFFFh; iCharset
0x180013d2c  call    ScriptStringAnalyse
0x180013d31  test    eax, eax
0x180013d33  js      loc_1800141B3
0x180013d39  mov     rax, [rbp+0C0h+prc]
0x180013d3d  mov     r9d, r12d; uOptions
0x180013d40  mov     r8d, [rsp+1C0h+var_144]; iY
0x180013d45  mov     edx, [rbp+0C0h+iX]; iX
0x180013d48  mov     rcx, [rbp+0C0h+pssa]; ssa
0x180013d4c  mov     dword ptr [rsp+1C0h+psControl], 0; fDisabled
0x180013d54  mov     [rsp+1C0h+iReqWidth], 0; iMaxSel
0x180013d5c  mov     [rsp+1C0h+dwFlags], 0; iMinSel
0x180013d64  mov     qword ptr [rsp+1C0h+iCharset], rax; prc
0x180013d69  call    ScriptStringOut
0x180013d6e  lea     rcx, [rbp+0C0h+pssa]; pssa
0x180013d72  mov     ebx, eax
0x180013d74  call    ScriptStringFree
0x180013d79  xor     eax, eax
0x180013d7b  test    ebx, ebx
0x180013d7d  setns   al
0x180013d80  jmp     loc_180013E08
0x180013d85  or      r12d, 10h
0x180013d89  mov     [rsp+1C0h+psControl], rdx; lpDx
0x180013d8e  mov     r9d, r12d; options
0x180013d91  mov     [rsp+1C0h+iReqWidth], esi; c
0x180013d95  mov     edx, eax; x
0x180013d97  mov     qword ptr [rsp+1C0h+dwFlags], r15; lpString
0x180013d9c  mov     qword ptr [rsp+1C0h+iCharset], rcx; lprect
0x180013da1  mov     rcx, rdi; hdc
0x180013da4  call    cs:__imp_ExtTextOutW
0x180013daa  jmp     short loc_180013E18
0x180013dac  test    r13b, 1
0x180013db0  jz      loc_18001413D
0x180013db6  lea     rcx, [rsp+1C0h+var_148]; this
0x180013dbb  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180013dc0  mov     rdi, [rbp+0C0h+var_138]
0x180013dc4  mov     rcx, rdi; HDC
0x180013dc7  call    ?FontHasWesternScript@@YAHPEAUHDC__@@@Z; FontHasWesternScript(HDC__ *)
0x180013dcc  test    eax, eax
0x180013dce  jz      loc_180013C27
0x180013dd4  mov     rax, [rbp+0C0h+var_118]
0x180013dd8  bts     r12d, 0Ch
0x180013ddd  mov     r8d, [rsp+1C0h+var_144]; y
0x180013de2  mov     r9d, r12d; options
0x180013de5  mov     edx, [rbp+0C0h+iX]; x
0x180013de8  mov     rcx, rdi; hdc
0x180013deb  mov     [rsp+1C0h+psControl], rax; lpDx
0x180013df0  mov     rax, [rbp+0C0h+prc]
0x180013df4  mov     [rsp+1C0h+iReqWidth], esi; c
0x180013df8  mov     qword ptr [rsp+1C0h+dwFlags], r15; lpString
0x180013dfd  mov     qword ptr [rsp+1C0h+iCharset], rax; lprect
0x180013e02  call    cs:__imp_ExtTextOutW
0x180013e08  mov     rbx, [rsp+190h]
0x180013e10  mov     r13, [rsp+1C0h+var_38]
0x180013e18  mov     rcx, [rbp+0C0h+var_50]
0x180013e1c  xor     rcx, rsp; StackCookie
0x180013e1f  call    __security_check_cookie
0x180013e24  add     rsp, 198h
0x180013e2b  pop     r15
0x180013e2d  pop     r14
0x180013e2f  pop     r12
0x180013e31  pop     rdi
0x180013e32  pop     rsi
0x180013e33  pop     rbp
0x180013e34  retn
0x180013e35  cmp     r13d, 3
0x180013e39  jz      loc_180013B5E
0x180013e3f  cmp     cs:g_DigitSubstitute.DigitSubstitute, bl
0x180013e45  jz      loc_180013B63
0x180013e4b  jmp     loc_180013B5E
0x180013e50  mov     r13d, r14d
0x180013e53  jmp     loc_180013B30
0x180013e58  cmp     esi, 10h
0x180013e5b  jle     loc_1800140E3
0x180013e61  lea     edi, ds:0[rsi*8]
0x180013e68  test    edi, edi
0x180013e6a  js      loc_1800141AA
0x180013e70  cmp     cs:?ghHeap@@3PEAXEA, r11; void * ghHeap
0x180013e77  jz      loc_18001404D
0x180013e7d  mov     ecx, edi; unsigned int
0x180013e7f  call    ?Alloc@CTempMemory@@SAPEAXK@Z; CTempMemory::Alloc(ulong)
0x180013e84  mov     rcx, rax
0x180013e87  test    rax, rax
0x180013e8a  jz      loc_180013FD8
0x180013e90  lea     rdi, [rcx+rsi*4]
0x180013e94  mov     [rbp+0C0h+var_F8], rcx
0x180013e98  xor     ecx, ecx
0x180013e9a  mov     [rbp+0C0h+var_E8], rdi
0x180013e9e  mov     [rbp+0C0h+var_EC], ecx
0x180013ea1  xor     r8d, r8d
0x180013ea4  mov     r10d, 0FC00h
0x180013eaa  mov     r9d, 0D800h
0x180013eb0  mov     r11d, 0DC00h
0x180013eb6  cmp     r8d, ebx
0x180013eb9  jge     short loc_180013ED1
0x180013ebb  movsxd  rdx, r8d
0x180013ebe  movzx   eax, word ptr [r15+rdx*2]
0x180013ec3  and     ax, r10w
0x180013ec7  cmp     ax, r9w
0x180013ecb  jz      loc_180014084
0x180013ed1  movsxd  rax, r8d
0x180013ed4  mov     [rdi+rax*4], ecx
0x180013ed7  movzx   edx, word ptr [r15+rax*2]
0x180013edc  movsxd  rcx, [rbp+0C0h+var_EC]
0x180013ee0  mov     rax, [rbp+0C0h+var_F8]
0x180013ee4  mov     [rax+rcx*4], edx
0x180013ee7  mov     ecx, [rbp+0C0h+var_EC]
0x180013eea  inc     ecx
0x180013eec  mov     rdi, [rbp+0C0h+var_E8]
0x180013ef0  inc     r8d
0x180013ef3  mov     [rbp+0C0h+var_EC], ecx
0x180013ef6  cmp     r8d, esi
0x180013ef9  jge     loc_180014076
0x180013eff  mov     r9d, 0D800h
0x180013f05  jmp     short loc_180013EB6
0x180013f07  xor     r8d, r8d
0x180013f0a  lea     rbx, __ImageBase
0x180013f11  mov     r10d, 309h
0x180013f17  cmp     r8d, esi
0x180013f1a  jge     loc_180013DAC
0x180013f20  movsxd  rcx, r8d
0x180013f23  test    r11, r11
0x180013f26  jnz     loc_180014015
0x180013f2c  mov     rax, [rbp+0C0h+var_100]
0x180013f30  movzx   ecx, word ptr [rax+rcx*2]
0x180013f34  mov     edx, ecx
0x180013f36  shr     edx, 10h
0x180013f39  cmp     edx, 11h
0x180013f3c  jnb     loc_18001402A
0x180013f42  mov     r9, ds:rva ?pccUnicodeClass@@3QBQEBQEBFB[rbx+rdx*8]; short const * const * const near * const pccUnicodeClass ...
0x180013f4a  cmp     r9, 30Ah
0x180013f51  jb      short loc_180013FA5
0x180013f53  movsxd  r10, ecx
  ... truncated ...
```
