# InternalTextOut

- ea: `0x180022e60`
- end: `0x1800235e9`
- name: `InternalTextOut`
- size: `1929`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, int x@<edx>, RECT *lprect, void *pString, int, INT *lpDx, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x1800157b0`
- `0x180015b10`
- `0x18004cd70`
- `0x180079da0`

## callees

- `0x180006f3c`
- `0x18000d040`
- `0x18000d200`
- `0x18000e3e0`
- `0x18000e550`
- `0x180019520`
- `0x180019630`
- `0x180019840`
- `0x180019b90`
- `0x180020880`
- `0x180020930`
- `0x180021430`
- `0x180022950`
- `0x180022b20`
- `0x180022e60`
- `0x180023a20`
- `0x1800242f0`
- `0x1800793f0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002340d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002340d`
- `GDI32!ExtTextOutW` at `0x1800231bf`
- `GDI32!ExtTextOutW` at `0x180023223`
- `GDI32!ExtTextOutW` at `0x1800231bf`
- `GDI32!ExtTextOutW` at `0x180023223`
- `win32u!NtGdiAnyLinkedFonts` at `0x1800230cb`
- `win32u!NtGdiAnyLinkedFonts` at `0x1800230cb`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180022f4c`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180022f4c`

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
              if ( (v17 & (unsigned __int8)byte_1800B9FE2[24 * (__int16)v37]) != 0 )
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
0x180022e60  mov     r11, rsp
0x180022e63  push    rbp
0x180022e64  push    rsi
0x180022e65  push    rdi
0x180022e66  push    r12
0x180022e68  push    r14
0x180022e6a  push    r15
0x180022e6c  lea     rbp, [r11-0C8h]
0x180022e73  sub     rsp, 198h
0x180022e7a  mov     rax, cs:__security_cookie
0x180022e81  xor     rax, rsp
0x180022e84  mov     [rbp+0C0h+var_50], rax
0x180022e88  movsxd  rsi, [rbp+0C0h+arg_30]
0x180022e8f  xor     r14d, r14d
0x180022e92  mov     r15, [rbp+0C0h+pString]
0x180022e99  mov     eax, edx
0x180022e9b  mov     [rbp+0C0h+iX], edx
0x180022e9e  mov     rdi, rcx
0x180022ea1  mov     rdx, [rbp+0C0h+lpDx]
0x180022ea8  mov     r12d, r9d
0x180022eab  mov     [rbp+0C0h+var_138], rcx
0x180022eaf  mov     rcx, [rbp+0C0h+lprect]
0x180022eb6  mov     [rbp+0C0h+prc], rcx
0x180022eba  mov     [rbp+0C0h+var_118], rdx
0x180022ebe  mov     [rsp+1C0h+var_144], r8d
0x180022ec3  mov     [rbp+0C0h+pssa], r14
0x180022ec7  test    esi, esi
0x180022ec9  jz      loc_1800231A0
0x180022ecf  test    r15, r15
0x180022ed2  jz      loc_1800231A0
0x180022ed8  bt      r9d, 0Dh
0x180022edd  jb      loc_1800235CF
0x180022ee3  mov     [r11-38h], rbx
0x180022ee7  mov     ebx, 1
0x180022eec  mov     [r11-40h], r13
0x180022ef0  test    r12b, r12b
0x180022ef3  js      short loc_180022F0F
0x180022ef5  mov     rcx, rdi; hdc
0x180022ef8  call    GetTextAlign
0x180022efd  bt      eax, 8
0x180022f01  jb      short loc_180022F0A
0x180022f03  mov     dword ptr [rsp+1C0h+pss.uBidiLevel], r14d
0x180022f08  jmp     short loc_180022F13
0x180022f0a  cmp     eax, 0FFFFFFFFh
0x180022f0d  jz      short loc_180022F03
0x180022f0f  mov     dword ptr [rsp+1C0h+pss.uBidiLevel], ebx
0x180022f13  mov     eax, r12d
0x180022f16  and     eax, 0C00h
0x180022f1b  cmp     eax, 0C00h
0x180022f20  jz      loc_180023278
0x180022f26  bt      r12d, 0Ah
0x180022f2b  jb      loc_18002358F
0x180022f31  bt      r12d, 0Bh
0x180022f36  mov     r13d, 0FFFFFFFFh
0x180022f3c  cmovb   r13d, ebx
0x180022f40  mov     dword ptr [rsp+1C0h+psc.uDefaultLanguage], r13d
0x180022f45  and     r12d, 0FFFFF3FFh
0x180022f4c  call    cs:__imp_NlsGetCacheUpdateCount
0x180022f53  nop     dword ptr [rax+rax+00h]
0x180022f58  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180022f5e  jz      short loc_180022F6B
0x180022f60  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180022f66  call    ReadNLSScriptSettings
0x180022f6b  test    r13d, r13d
0x180022f6e  jnz     loc_18002325D
0x180022f74  mov     ebx, 3
0x180022f79  mov     rcx, rdi; hdc
0x180022f7c  call    GetLayout
0x180022f81  and     eax, 1
0x180022f84  mov     r14d, ebx
0x180022f87  or      r14d, 4
0x180022f8b  cmp     dword ptr [rsp+1C0h+pss.uBidiLevel], eax
0x180022f8f  cmovz   r14d, ebx
0x180022f93  test    esi, esi
0x180022f95  js      loc_180023041
0x180022f9b  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x180022fa0  movzx   r13d, [rbp+0C0h+var_60]
0x180022fa5  lea     ebx, [rsi-1]
0x180022fa8  xor     edi, edi
0x180022faa  mov     [rsp+1C0h+var_148], eax
0x180022fae  or      r13w, 1
0x180022fb3  mov     [rbp+0C0h+var_100], r15
0x180022fb7  xor     r11d, r11d
0x180022fba  mov     [rbp+0C0h+var_60], r13w
0x180022fbf  xor     ecx, ecx
0x180022fc1  mov     [rbp+0C0h+var_F8], r11
0x180022fc5  mov     [rbp+0C0h+var_F0], esi
0x180022fc8  mov     r10d, 0FC00h
0x180022fce  mov     [rbp+0C0h+var_EC], esi
0x180022fd1  mov     r9d, 0D800h
0x180022fd7  mov     [rbp+0C0h+var_120], rdi
0x180022fdb  mov     r8d, 0DC00h
0x180022fe1  mov     [rbp+0C0h+var_E8], rdi
0x180022fe5  cmp     ecx, ebx
0x180022fe7  jge     short loc_180023011
0x180022fe9  movsxd  rdx, ecx
0x180022fec  movzx   eax, word ptr [r15+rdx*2]
0x180022ff1  and     ax, r10w
0x180022ff5  cmp     ax, r9w
0x180022ff9  jz      loc_180023541
0x180022fff  inc     ecx
0x180023001  jmp     short loc_180022FE5
0x180023003  mov     eax, 0FFFEh
0x180023008  and     r13w, ax
0x18002300c  mov     [rbp+0C0h+var_60], r13w
0x180023011  test    r13b, 1
0x180023015  jz      loc_180023280
0x18002301b  test    r11, r11
0x18002301e  jz      loc_18002332F
0x180023024  test    r13b, 1
0x180023028  jz      loc_18002355A
0x18002302e  lea     rcx, [rsp+1C0h+var_148]; this
0x180023033  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180023038  mov     rdi, [rbp+0C0h+var_138]
0x18002303c  mov     r13d, dword ptr [rsp+1C0h+psc.uDefaultLanguage]
0x180023041  mov     rcx, rdi; hdc
0x180023044  call    GetTextCharacterExtra
0x180023049  test    eax, eax
0x18002304b  jnz     loc_1800231F5
0x180023051  mov     rcx, rdi; h
0x180023054  call    GetObjectType
0x180023059  add     eax, 0FFFFFFFCh
0x18002305c  test    eax, 0FFFFFFF7h
0x180023061  jnz     loc_180023537
0x180023067  mov     ebx, 40000080h
0x18002306c  cmp     [rbp+0C0h+arg_40], 0FFFFFFFFh
0x180023073  jnz     loc_180023462
0x180023079  mov     eax, 20h ; ' '
0x18002307e  mov     r14d, dword ptr [rsp+1C0h+pss.uBidiLevel]
0x180023083  shl     r14d, 8
0x180023087  or      r14d, ebx
0x18002308a  mov     dword ptr [rsp+1C0h+psc.uDefaultLanguage], 0
0x180023092  or      r14d, eax
0x180023095  xor     eax, eax
0x180023097  mov     word ptr [rsp+1C0h+pss.uBidiLevel], ax
0x18002309c  call    CheckUpdateNLSScriptSettings
0x1800230a1  lea     r8, [rsp+1C0h+pss]; pss
0x1800230a6  test    r13d, r13d
0x1800230a9  jns     loc_18002359A
0x1800230af  lea     rcx, g_DigitSubstitute; psds
0x1800230b6  lea     rdx, [rsp+1C0h+psc]; psc
0x1800230bb  call    ScriptApplyDigitSubstitution
0x1800230c0  mov     eax, cs:g_iUseFontLinking
0x1800230c6  cmp     eax, 0FFFFFFFFh
0x1800230c9  jnz     short loc_1800230DD
0x1800230cb  call    cs:__imp_NtGdiAnyLinkedFonts
0x1800230d2  nop     dword ptr [rax+rax+00h]
0x1800230d7  mov     cs:g_iUseFontLinking, eax
0x1800230dd  test    eax, eax
0x1800230df  jz      short loc_1800230E6
0x1800230e1  bts     r14d, 0Ch
0x1800230e6  or      dword ptr [rsp+1C0h+psc.uDefaultLanguage], 1800000h
0x1800230ee  lea     rax, [rbp+0C0h+pssa]
0x1800230f2  mov     [rsp+60h], rax; pssa
0x1800230f7  xor     r9d, r9d; cGlyphs
0x1800230fa  mov     rax, [rbp+0C0h+var_118]
0x1800230fe  mov     r8d, esi; cString
0x180023101  mov     [rsp+1C0h+pbInClass], 0; pbInClass
0x18002310a  mov     rdx, r15; pString
0x18002310d  mov     [rsp+1C0h+pTabdef], 0; pTabdef
0x180023116  mov     rcx, rdi; hdc
0x180023119  mov     [rsp+1C0h+piDx], rax; piDx
0x18002311e  lea     rax, [rsp+1C0h+pss]
0x180023123  mov     [rsp+1C0h+psState], rax; psState
0x180023128  lea     rax, [rsp+1C0h+psc]
0x18002312d  mov     [rsp+1C0h+psControl], rax; psControl
0x180023132  mov     [rsp+1C0h+iReqWidth], 0FFFFFFFFh; iReqWidth
0x18002313a  mov     [rsp+1C0h+dwFlags], r14d; dwFlags
0x18002313f  mov     [rsp+1C0h+iCharset], 0FFFFFFFFh; iCharset
0x180023147  call    ScriptStringAnalyse
0x18002314c  test    eax, eax
0x18002314e  js      loc_1800235E2
0x180023154  mov     rax, [rbp+0C0h+prc]
0x180023158  mov     r9d, r12d; uOptions
0x18002315b  mov     r8d, [rsp+1C0h+var_144]; iY
0x180023160  mov     edx, [rbp+0C0h+iX]; iX
0x180023163  mov     rcx, [rbp+0C0h+pssa]; ssa
0x180023167  mov     dword ptr [rsp+1C0h+psControl], 0; fDisabled
0x18002316f  mov     [rsp+1C0h+iReqWidth], 0; iMaxSel
0x180023177  mov     [rsp+1C0h+dwFlags], 0; iMinSel
0x18002317f  mov     qword ptr [rsp+1C0h+iCharset], rax; prc
0x180023184  call    ScriptStringOut
0x180023189  lea     rcx, [rbp+0C0h+pssa]; pssa
0x18002318d  mov     ebx, eax
0x18002318f  call    ScriptStringFree
0x180023194  xor     eax, eax
0x180023196  test    ebx, ebx
0x180023198  setns   al
0x18002319b  jmp     loc_18002322F
0x1800231a0  or      r12d, 10h
0x1800231a4  mov     [rsp+1C0h+psControl], rdx; lpDx
0x1800231a9  mov     r9d, r12d; options
0x1800231ac  mov     [rsp+1C0h+iReqWidth], esi; c
0x1800231b0  mov     edx, eax; x
0x1800231b2  mov     qword ptr [rsp+1C0h+dwFlags], r15; lpString
0x1800231b7  mov     qword ptr [rsp+1C0h+iCharset], rcx; lprect
0x1800231bc  mov     rcx, rdi; hdc
0x1800231bf  call    cs:__imp_ExtTextOutW
0x1800231c6  nop     dword ptr [rax+rax+00h]
0x1800231cb  jmp     short loc_18002323F
0x1800231cd  test    r13b, 1
0x1800231d1  jz      loc_18002356C
0x1800231d7  lea     rcx, [rsp+1C0h+var_148]; this
0x1800231dc  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x1800231e1  mov     rdi, [rbp+0C0h+var_138]
0x1800231e5  mov     rcx, rdi; HDC
0x1800231e8  call    ?FontHasWesternScript@@YAHPEAUHDC__@@@Z; FontHasWesternScript(HDC__ *)
0x1800231ed  test    eax, eax
0x1800231ef  jz      loc_18002303C
0x1800231f5  mov     rax, [rbp+0C0h+var_118]
0x1800231f9  bts     r12d, 0Ch
0x1800231fe  mov     r8d, [rsp+1C0h+var_144]; y
0x180023203  mov     r9d, r12d; options
0x180023206  mov     edx, [rbp+0C0h+iX]; x
0x180023209  mov     rcx, rdi; hdc
0x18002320c  mov     [rsp+1C0h+psControl], rax; lpDx
0x180023211  mov     rax, [rbp+0C0h+prc]
0x180023215  mov     [rsp+1C0h+iReqWidth], esi; c
0x180023219  mov     qword ptr [rsp+1C0h+dwFlags], r15; lpString
0x18002321e  mov     qword ptr [rsp+1C0h+iCharset], rax; lprect
0x180023223  call    cs:__imp_ExtTextOutW
0x18002322a  nop     dword ptr [rax+rax+00h]
0x18002322f  mov     rbx, [rsp+190h]
0x180023237  mov     r13, [rsp+1C0h+var_38]
0x18002323f  mov     rcx, [rbp+0C0h+var_50]
0x180023243  xor     rcx, rsp; StackCookie
0x180023246  call    __security_check_cookie
0x18002324b  add     rsp, 198h
0x180023252  pop     r15
0x180023254  pop     r14
0x180023256  pop     r12
0x180023258  pop     rdi
0x180023259  pop     rsi
0x18002325a  pop     rbp
0x18002325b  retn
0x18002325d  cmp     r13d, 3
0x180023261  jz      loc_180022F74
0x180023267  cmp     cs:g_DigitSubstitute.DigitSubstitute, bl
0x18002326d  jz      loc_180022F79
0x180023273  jmp     loc_180022F74
0x180023278  mov     r13d, r14d
0x18002327b  jmp     loc_180022F40
0x180023280  cmp     esi, 10h
0x180023283  jle     loc_180023512
0x180023289  lea     edi, ds:0[rsi*8]
0x180023290  test    edi, edi
0x180023292  js      loc_1800235D9
0x180023298  cmp     cs:?ghHeap@@3PEAXEA, r11; void * ghHeap
0x18002329f  jz      loc_18002347C
0x1800232a5  mov     ecx, edi; unsigned int
0x1800232a7  call    ?Alloc@CTempMemory@@SAPEAXK@Z; CTempMemory::Alloc(ulong)
0x1800232ac  mov     rcx, rax
0x1800232af  test    rax, rax
0x1800232b2  jz      loc_180023401
0x1800232b8  lea     rdi, [rcx+rsi*4]
0x1800232bc  mov     [rbp+0C0h+var_F8], rcx
0x1800232c0  xor     ecx, ecx
0x1800232c2  mov     [rbp+0C0h+var_E8], rdi
0x1800232c6  mov     [rbp+0C0h+var_EC], ecx
0x1800232c9  xor     r8d, r8d
0x1800232cc  mov     r10d, 0FC00h
0x1800232d2  mov     r9d, 0D800h
0x1800232d8  mov     r11d, 0DC00h
0x1800232de  cmp     r8d, ebx
0x1800232e1  jge     short loc_1800232F9
0x1800232e3  movsxd  rdx, r8d
0x1800232e6  movzx   eax, word ptr [r15+rdx*2]
0x1800232eb  and     ax, r10w
0x1800232ef  cmp     ax, r9w
0x1800232f3  jz      loc_1800234B3
0x1800232f9  movsxd  rax, r8d
0x1800232fc  mov     [rdi+rax*4], ecx
0x1800232ff  movzx   edx, word ptr [r15+rax*2]
0x180023304  movsxd  rcx, [rbp+0C0h+var_EC]
0x180023308  mov     rax, [rbp+0C0h+var_F8]
0x18002330c  mov     [rax+rcx*4], edx
0x18002330f  mov     ecx, [rbp+0C0h+var_EC]
0x180023312  inc     ecx
0x180023314  mov     rdi, [rbp+0C0h+var_E8]
0x180023318  inc     r8d
0x18002331b  mov     [rbp+0C0h+var_EC], ecx
0x18002331e  cmp     r8d, esi
0x180023321  jge     loc_1800234A5
0x180023327  mov     r9d, 0D800h
0x18002332d  jmp     short loc_1800232DE
0x18002332f  xor     r8d, r8d
0x180023332  lea     rbx, __ImageBase
0x180023339  mov     r10d, 309h
0x18002333f  nop
0x180023340  cmp     r8d, esi
0x180023343  jge     loc_1800231CD
0x180023349  movsxd  rcx, r8d
0x18002334c  test    r11, r11
0x18002334f  jnz     loc_180023444
0x180023355  mov     rax, [rbp+0C0h+var_100]
0x180023359  movzx   ecx, word ptr [rax+rcx*2]
0x18002335d  mov     edx, ecx
0x18002335f  shr     edx, 10h
0x180023362  cmp     edx, 11h
0x180023365  jnb     loc_180023459
  ... truncated ...
```
