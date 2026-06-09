# LpkGetTextExtentExPoint

- ea: `0x180021f80`
- end: `0x180022944`
- name: `LpkGetTextExtentExPoint`
- size: `2500`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, int, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800293b0`
- `0x180042290`
- `0x180043a90`
- `0x18005bf20`

## callees

- `0x180006f3c`
- `0x18000d040`
- `0x18000d200`
- `0x18000dda0`
- `0x18000e3e0`
- `0x18000e550`
- `0x180019520`
- `0x180019630`
- `0x180019840`
- `0x180020930`
- `0x180021f80`
- `0x180022950`
- `0x180022b20`
- `0x180022cf0`
- `0x180023a20`
- `0x180023af0`
- `0x180046760`
- `0x1800793f0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180022041`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180022041`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002206a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002206a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002264b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002264b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002245e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002245e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022575`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022575`
- `win32u!NtGdiGetGlyphIndicesW` at `0x1800225e2`
- `win32u!NtGdiGetGlyphIndicesW` at `0x1800225e2`
- `win32u!NtGdiGetTextExtentExW` at `0x1800224f5`
- `win32u!NtGdiGetTextExtentExW` at `0x1800224f5`
- `win32u!NtGdiAnyLinkedFonts` at `0x180022206`
- `win32u!NtGdiAnyLinkedFonts` at `0x180022206`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180022027`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180022027`

## pseudocode

```c
__int64 __fastcall LpkGetTextExtentExPoint(
        HDC a1,
        _WORD *a2,
        int a3,
        int a4,
        _DWORD *a5,
        int *a6,
        _QWORD *a7,
        int a8,
        int a9)
{
  __int64 v11; // r14
  UINT TextAlign; // eax
  unsigned int v13; // ebx
  int CacheUpdateCount; // eax
  BOOL v15; // eax
  int v16; // esi
  char Layout; // al
  unsigned int v18; // ecx
  SCRIPT_CONTROL v19; // eax
  int v20; // ebx
  __int16 v21; // r12
  _BYTE *v22; // r11
  int v23; // ecx
  DWORD ObjectType; // eax
  DWORD v25; // esi
  int v26; // ecx
  int v27; // eax
  int v28; // ebx
  DWORD dwFlags; // ebx
  int v30; // eax
  _DWORD *v31; // rbx
  _DWORD *v32; // r8
  signed int v34; // edi
  _BYTE *v35; // rcx
  _BYTE *v36; // r10
  int v37; // ecx
  int v38; // r8d
  int i; // r8d
  __int16 v40; // cx
  unsigned __int64 v41; // rax
  int v42; // ebx
  int j; // ecx
  __int64 v44; // rax
  int v45; // edi
  int v46; // ecx
  __int64 v47; // rax
  int v48; // ecx
  int *v49; // rdi
  int k; // edx
  int v51; // eax
  int v52; // r8d
  int v53; // eax
  SCRIPT_CONTROL psc; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v55; // [rsp+74h] [rbp-8Ch]
  SCRIPT_STATE pss; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v57; // [rsp+80h] [rbp-80h]
  int *v58; // [rsp+88h] [rbp-78h]
  int iReqWidth; // [rsp+90h] [rbp-70h]
  SCRIPT_STRING_ANALYSIS ssa; // [rsp+98h] [rbp-68h] BYREF
  SCRIPT_STRING_ANALYSIS v61; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v62; // [rsp+A8h] [rbp-58h]
  __int128 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h]
  _WORD *v65; // [rsp+D0h] [rbp-30h]
  _BYTE *v66; // [rsp+D8h] [rbp-28h]
  int v67; // [rsp+E0h] [rbp-20h]
  int v68; // [rsp+E4h] [rbp-1Ch]
  _BYTE *v69; // [rsp+E8h] [rbp-18h]
  _BYTE v70[64]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v71[64]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v72; // [rsp+170h] [rbp+70h]
  _BYTE *v73; // [rsp+180h] [rbp+80h] BYREF
  WCHAR LCData[80]; // [rsp+190h] [rbp+90h] BYREF

  iReqWidth = a4;
  v57 = a5;
  v58 = a6;
  v11 = a3;
  v62 = a7;
  ssa = 0;
  v61 = 0;
  if ( !a1 || !a7 )
    return 0;
  if ( a3 && a2 )
  {
    TextAlign = GetTextAlign(a1);
    v13 = (TextAlign & 0x100) != 0 && TextAlign != -1;
    v55 = v13;
    CacheUpdateCount = NlsGetCacheUpdateCount();
    if ( CacheUpdateCount != g_ulNlsUpdateCacheCount )
    {
      g_ulNlsUpdateCacheCount = CacheUpdateCount;
      g_UserLocale = GetUserDefaultLCID();
      v15 = GetLocaleInfoW(0x400u, 0x58u, LCData, 80) && (LCData[7] & 0x800) != 0;
      g_UserBidiLocale = v15;
      ScriptRecordDigitSubstitution(0x400u, &g_DigitSubstitute);
    }
    v16 = 3;
    if ( *((_BYTE *)&g_DigitSubstitute + 4) == 1 )
      v16 = 1;
    Layout = GetLayout(a1);
    v18 = v16 | 4;
    if ( v13 != (Layout & 1) )
      LOBYTE(v16) = v16 | 4;
    if ( (int)v11 < 0 )
      goto LABEL_26;
    v19 = (SCRIPT_CONTROL)UspAcquireTempAlloc(v18);
    v20 = v11 - 1;
    v21 = v72 | 1;
    v66 = 0;
    v22 = 0;
    v73 = 0;
    v69 = 0;
    v23 = 0;
    v72 |= 1u;
    psc = v19;
    v65 = a2;
    v67 = v11;
    v68 = v11;
    while ( v23 < v20 )
    {
      if ( (a2[v23] & 0xFC00) == 0xD800 && (a2[v23 + 1] & 0xFC00) == 0xDC00 )
      {
        v21 &= ~1u;
        v72 = v21;
        break;
      }
      ++v23;
    }
    if ( (v21 & 1) != 0 )
    {
LABEL_22:
      if ( v22 )
      {
        if ( (v21 & 1) == 0 && v22 != v70 )
          UspFreeMem(v22);
LABEL_24:
        CTempMemory::~CTempMemory((CTempMemory *)&psc);
      }
      else
      {
        for ( i = 0; i < (int)v11; ++i )
        {
          v40 = v65[i];
          if ( (unsigned __int64)pccUnicodeClass < 0x30A )
          {
            LOWORD(v41) = (_WORD)pccUnicodeClass;
          }
          else
          {
            v41 = (unsigned __int64)pccUnicodeClass[HIBYTE(v40)];
            if ( v41 >= 0x30A )
              LOWORD(v41) = *(_WORD *)(v41 + 2LL * (unsigned __int8)v40);
          }
          if ( ((unsigned __int8)v16 & (unsigned __int8)byte_1800B9FE2[24 * (__int16)v41]) != 0 )
            goto LABEL_24;
        }
        CTempMemory::~CTempMemory((CTempMemory *)&psc);
        v63 = 0;
        LODWORD(v63) = 16;
        v64 = 0;
        if ( (unsigned int)GetFontRealizationInfo(a1, &v63) )
        {
          EnterCriticalSection(&csFontIdCache);
          v42 = HIDWORD(v63);
          if ( g_cCachedFontsID > 0 )
          {
            for ( j = 0; j < g_cCachedFontsID; ++j )
            {
              v44 = 2LL * j;
              if ( HIDWORD(v63) == g_FontIDCache[v44] )
              {
                v45 = dword_180100E24[v44];
                LeaveCriticalSection(&csFontIdCache);
                goto LABEL_65;
              }
            }
          }
          if ( (unsigned int)NtGdiGetGlyphIndicesW(a1, L"dMr\"", 4, &v73, 1) != 4
            || (_WORD)v73 == 0xFFFF
            || WORD1(v73) == 0xFFFF
            || WORD2(v73) == 0xFFFF
            || HIWORD(v73) == 0xFFFF )
          {
            v46 = g_pCurrentAvailablePos;
            v45 = 0;
            dword_180100E24[2 * g_pCurrentAvailablePos] = 0;
          }
          else
          {
            v46 = g_pCurrentAvailablePos;
            v45 = 1;
            dword_180100E24[2 * g_pCurrentAvailablePos] = 1;
          }
          v47 = v46;
          v48 = v46 + 1;
          g_pCurrentAvailablePos = v48;
          g_FontIDCache[2 * v47] = v42;
          if ( v48 >= 30 )
            g_pCurrentAvailablePos = 0;
          if ( g_cCachedFontsID < 30 )
            ++g_cCachedFontsID;
          LeaveCriticalSection(&csFontIdCache);
LABEL_65:
          if ( v45 )
            return NtGdiGetTextExtentExW(a1, a2, (unsigned int)v11, (unsigned int)iReqWidth, v57, v58, v62, 0);
        }
      }
      v13 = v55;
LABEL_26:
      if ( !GetTextCharacterExtra(a1) )
      {
        ObjectType = GetObjectType(a1);
        v25 = ObjectType;
        if ( a9 == -1 || ((ObjectType - 4) & 0xFFFFFFF7) == 0 )
          v26 = 32;
        else
          v26 = 0x8000000;
        v27 = 67108992;
        v55 = v13 << 8;
        v28 = v26 | (v13 << 8);
        psc = 0;
        if ( !v57 )
          v27 = 128;
        dwFlags = v27 | v28;
        pss = 0;
        CheckUpdateNLSScriptSettings();
        ScriptApplyDigitSubstitution(&g_DigitSubstitute, &psc, &pss);
        v30 = g_iUseFontLinking;
        if ( g_iUseFontLinking == -1 )
        {
          v30 = NtGdiAnyLinkedFonts();
          g_iUseFontLinking = v30;
        }
        if ( v30 )
          dwFlags |= 0x1000u;
        psc = (SCRIPT_CONTROL)(*(_DWORD *)&psc | 0x1800000);
        if ( ScriptStringAnalyse(a1, a2, v11, 0, -1, dwFlags, iReqWidth, &psc, &pss, 0, 0, 0, &ssa) >= 0 )
        {
          v31 = ssa;
          if ( !v58 )
          {
            v32 = v57;
LABEL_38:
            if ( v32 )
              *v32 = v31[102];
            *v62 = *((_QWORD *)v31 + 53);
            ScriptStringFree(&ssa);
            return 1;
          }
          if ( !v57 || *((_DWORD *)ssa + 102) >= (int)v11 )
          {
            ScriptStringGetLogicalWidths(ssa, v58);
            v32 = v57;
            if ( !v57 )
              goto LABEL_104;
          }
          v52 = v31[102];
          if ( v52 >= (int)v11 || v52 <= 0 )
          {
            v32 = v57;
LABEL_104:
            v49 = v58;
            goto LABEL_105;
          }
          if ( a9 == -1 || ((v25 - 4) & 0xFFFFFFF7) == 0 )
            v53 = 160;
          else
            v53 = 134217856;
          if ( (int)LpkStringAnalyse((int)a1, (int)a2, v52, 0, -1, v53 | v55, -1, 0, 0, 0, 0, 0, 0, (__int64)&v61) >= 0 )
          {
            v49 = v58;
            ScriptStringGetLogicalWidths(v61, v58);
            ScriptStringFree(&v61);
            v32 = v57;
LABEL_105:
            for ( k = 1; ; ++k )
            {
              v51 = v32 ? v31[102] : v11;
              if ( k >= v51 )
                break;
              v49[k] += v49[k - 1];
            }
            goto LABEL_38;
          }
          ScriptStringFree(&ssa);
        }
        return 0;
      }
      return NtGdiGetTextExtentExW(a1, a2, (unsigned int)v11, (unsigned int)iReqWidth, v57, v58, v62, 0);
    }
    if ( (int)v11 <= 16 )
    {
      v37 = 0;
      v36 = v71;
      v38 = 0;
      v73 = v71;
      v69 = v71;
      v22 = v70;
      v66 = v70;
      v68 = 0;
      if ( (int)v11 <= 0 )
        goto LABEL_22;
    }
    else
    {
      v34 = 8 * v11;
      if ( (v11 & 0x10000000) != 0 )
      {
LABEL_73:
        v21 |= 1u;
        v72 = v21;
        goto LABEL_22;
      }
      if ( !ghHeap )
      {
        if ( gfMemoryInitFailed )
          goto LABEL_73;
        if ( !(unsigned int)UspInitMemory() )
        {
          v21 = v72;
          v22 = v66;
          v73 = v69;
          goto LABEL_73;
        }
      }
      v35 = CTempMemory::Alloc(v34);
      if ( !v35 )
      {
        v35 = HeapAlloc(ghHeap, 0, v34);
        if ( !v35 )
        {
          v22 = 0;
          v21 = v72;
          v66 = 0;
          v73 = v69;
          goto LABEL_73;
        }
      }
      v36 = &v35[4 * v11];
      v66 = v35;
      v37 = 0;
      v69 = v36;
      v68 = 0;
      v38 = 0;
    }
    do
    {
      if ( v38 < v20 && (a2[v38] & 0xFC00) == 0xD800 && (a2[v38 + 1] & 0xFC00) == 0xDC00 )
      {
        *(_DWORD *)&v36[4 * v38 + 4] = v37;
        *(_DWORD *)&v69[4 * v38] = v68;
        *(_DWORD *)&v66[4 * v68] = (a2[v38 + 1] & 0x3FF | ((a2[v38] & 0x3FF) << 10)) + 0x10000;
        v37 = v68 + 1;
        ++v38;
      }
      else
      {
        *(_DWORD *)&v36[4 * v38] = v37;
        *(_DWORD *)&v66[4 * v68] = (unsigned __int16)a2[v38];
        v37 = v68 + 1;
      }
      v36 = v69;
      ++v38;
      v68 = v37;
    }
    while ( v38 < (int)v11 );
    LOBYTE(v21) = v72;
    v22 = v66;
    v73 = v69;
    goto LABEL_22;
  }
  *a7 = 0;
  if ( a5 )
    *a5 = 0;
  return 1;
}

```

## disassembly

```asm
0x180021f80  push    rbp
0x180021f82  push    rbx
0x180021f83  push    rsi
0x180021f84  push    rdi
0x180021f85  push    r12
0x180021f87  push    r13
0x180021f89  push    r14
0x180021f8b  push    r15
0x180021f8d  lea     rbp, [rsp-148h]
0x180021f95  sub     rsp, 248h
0x180021f9c  mov     rax, cs:__security_cookie
0x180021fa3  xor     rax, rsp
0x180021fa6  mov     [rbp+180h+var_50], rax
0x180021fad  mov     rax, [rbp+180h+arg_30]
0x180021fb4  xor     edi, edi
0x180021fb6  mov     r13, rcx
0x180021fb9  mov     [rbp+180h+var_1F0], r9d
0x180021fbd  mov     rcx, [rbp+180h+arg_20]
0x180021fc4  mov     r15, rdx
0x180021fc7  mov     rdx, [rbp+180h+arg_28]
0x180021fce  mov     [rbp+180h+var_200], rcx
0x180021fd2  mov     [rbp+180h+var_1F8], rdx
0x180021fd6  movsxd  r14, r8d
0x180021fd9  mov     [rbp+180h+var_1D8], rax
0x180021fdd  mov     [rbp+180h+ssa], rdi
0x180021fe1  mov     [rbp+180h+var_1E0], rdi
0x180021fe5  test    r13, r13
0x180021fe8  jz      loc_180022665
0x180021fee  test    rax, rax
0x180021ff1  jz      loc_180022665
0x180021ff7  test    r8d, r8d
0x180021ffa  jz      loc_18002288F
0x180022000  test    r15, r15
0x180022003  jz      loc_18002288F
0x180022009  mov     rcx, r13; hdc
0x18002200c  call    GetTextAlign
0x180022011  mov     r12d, 1
0x180022017  bt      eax, 8
0x18002201b  jb      loc_18002285C
0x180022021  mov     ebx, edi
0x180022023  mov     [rsp+280h+var_20C], ebx
0x180022027  call    cs:__imp_NlsGetCacheUpdateCount
0x18002202e  nop     dword ptr [rax+rax+00h]
0x180022033  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180022039  jz      short loc_1800220AA
0x18002203b  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180022041  call    cs:__imp_GetUserDefaultLCID
0x180022048  nop     dword ptr [rax+rax+00h]
0x18002204d  mov     r9d, 50h ; 'P'; cchData
0x180022053  lea     r8, [rbp+180h+LCData]; lpLCData
0x18002205a  mov     edx, 58h ; 'X'; LCType
0x18002205f  mov     cs:g_UserLocale, eax
0x180022065  mov     ecx, 400h; Locale
0x18002206a  call    cs:__imp_GetLocaleInfoW
0x180022071  nop     dword ptr [rax+rax+00h]
0x180022076  test    eax, eax
0x180022078  jz      loc_180022535
0x18002207e  mov     eax, 800h
0x180022083  test    [rbp+180h+var_E2], ax
0x18002208a  jz      loc_180022535
0x180022090  mov     eax, r12d
0x180022093  lea     rdx, g_DigitSubstitute; psds
0x18002209a  mov     cs:g_UserBidiLocale, eax
0x1800220a0  mov     ecx, 400h; Locale
0x1800220a5  call    ScriptRecordDigitSubstitution
0x1800220aa  cmp     cs:g_DigitSubstitute.DigitSubstitute, r12b
0x1800220b1  mov     esi, 3
0x1800220b6  mov     rcx, r13; hdc
0x1800220b9  cmovz   esi, r12d
0x1800220bd  call    GetLayout
0x1800220c2  mov     ecx, esi
0x1800220c4  and     eax, r12d
0x1800220c7  or      ecx, 4; unsigned int
0x1800220ca  cmp     ebx, eax
0x1800220cc  cmovnz  esi, ecx
0x1800220cf  test    r14d, r14d
0x1800220d2  js      loc_180022184
0x1800220d8  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x1800220dd  movzx   r12d, [rbp+180h+var_110]
0x1800220e2  lea     ebx, [r14-1]
0x1800220e6  or      r12w, 1
0x1800220eb  mov     [rbp+180h+var_1A8], rdi
0x1800220ef  mov     r11, rdi
0x1800220f2  mov     [rbp+180h+var_100], rdi
0x1800220f9  mov     r10, rdi
0x1800220fc  mov     [rbp+180h+var_198], rdi
0x180022100  mov     ecx, edi
0x180022102  mov     [rbp+180h+var_110], r12w
0x180022107  mov     dword ptr [rsp+280h+psc.uDefaultLanguage], eax
0x18002210b  mov     edi, 0FC00h
0x180022110  mov     [rbp+180h+var_1B0], r15
0x180022114  mov     r9d, 0D800h
0x18002211a  mov     [rbp+180h+var_1A0], r14d
0x18002211e  mov     r8d, 0DC00h
0x180022124  mov     [rbp+180h+var_19C], r14d
0x180022128  cmp     ecx, ebx
0x18002212a  jge     short loc_180022153
0x18002212c  movsxd  rdx, ecx
0x18002212f  movzx   eax, word ptr [r15+rdx*2]
0x180022134  and     ax, di
0x180022137  cmp     ax, r9w
0x18002213b  jz      loc_1800227C2
0x180022141  inc     ecx
0x180022143  jmp     short loc_180022128
0x180022145  mov     eax, 0FFFEh
0x18002214a  and     r12w, ax
0x18002214e  mov     [rbp+180h+var_110], r12w
0x180022153  test    r12b, 1
0x180022157  jz      loc_1800222C4
0x18002215d  test    r11, r11
0x180022160  jz      loc_180022374
0x180022166  test    r12b, 1
0x18002216a  jz      loc_1800227DA
0x180022170  lea     rcx, [rsp+280h+psc]; this
0x180022175  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x18002217a  mov     r12d, 1
0x180022180  mov     ebx, [rsp+280h+var_20C]
0x180022184  mov     rcx, r13; hdc
0x180022187  call    GetTextCharacterExtra
0x18002218c  test    eax, eax
0x18002218e  jnz     loc_1800224C5
0x180022194  mov     rcx, r13; h
0x180022197  call    GetObjectType
0x18002219c  mov     edi, [rbp+180h+arg_40]
0x1800221a2  mov     esi, eax
0x1800221a4  cmp     edi, 0FFFFFFFFh
0x1800221a7  jnz     loc_1800226C4
0x1800221ad  mov     ecx, 20h ; ' '
0x1800221b2  shl     ebx, 8
0x1800221b5  mov     eax, 4000080h
0x1800221ba  mov     [rsp+280h+var_20C], ebx
0x1800221be  mov     r8d, 80h
0x1800221c4  or      ebx, ecx
0x1800221c6  mov     dword ptr [rsp+280h+psc.uDefaultLanguage], 0
0x1800221ce  cmp     [rbp+180h+var_200], 0
0x1800221d3  cmovz   eax, r8d
0x1800221d7  or      ebx, eax
0x1800221d9  xor     eax, eax
0x1800221db  mov     word ptr [rsp+280h+pss.uBidiLevel], ax
0x1800221e0  call    CheckUpdateNLSScriptSettings
0x1800221e5  lea     r8, [rsp+280h+pss]; pss
0x1800221ea  lea     rdx, [rsp+280h+psc]; psc
0x1800221ef  lea     rcx, g_DigitSubstitute; psds
0x1800221f6  call    ScriptApplyDigitSubstitution
0x1800221fb  mov     eax, cs:g_iUseFontLinking
0x180022201  cmp     eax, 0FFFFFFFFh
0x180022204  jnz     short loc_180022218
0x180022206  call    cs:__imp_NtGdiAnyLinkedFonts
0x18002220d  nop     dword ptr [rax+rax+00h]
0x180022212  mov     cs:g_iUseFontLinking, eax
0x180022218  test    eax, eax
0x18002221a  jz      short loc_180022220
0x18002221c  bts     ebx, 0Ch
0x180022220  or      dword ptr [rsp+280h+psc.uDefaultLanguage], 1800000h
0x180022228  lea     rax, [rbp+180h+ssa]
0x18002222c  mov     [rsp+280h+pssa], rax; pssa
0x180022231  xor     r9d, r9d; cGlyphs
0x180022234  xor     eax, eax
0x180022236  mov     r8d, r14d; cString
0x180022239  mov     [rsp+280h+pbInClass], rax; pbInClass
0x18002223e  mov     rdx, r15; pString
0x180022241  mov     [rsp+280h+pTabdef], rax; pTabdef
0x180022246  mov     rcx, r13; hdc
0x180022249  mov     [rsp+280h+piDx], rax; piDx
0x18002224e  lea     rax, [rsp+280h+pss]
0x180022253  mov     [rsp+280h+psState], rax; psState
0x180022258  lea     rax, [rsp+280h+psc]
0x18002225d  mov     [rsp+280h+psControl], rax; psControl
0x180022262  mov     eax, [rbp+180h+var_1F0]
0x180022265  mov     [rsp+280h+iReqWidth], eax; iReqWidth
0x180022269  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x18002226d  mov     [rsp+280h+iCharset], 0FFFFFFFFh; iCharset
0x180022275  call    ScriptStringAnalyse
0x18002227a  test    eax, eax
0x18002227c  js      loc_180022665
0x180022282  mov     rdx, [rbp+180h+var_1F8]; piDx
0x180022286  mov     rbx, [rbp+180h+ssa]
0x18002228a  test    rdx, rdx
0x18002228d  jnz     loc_1800227EC
0x180022293  mov     r8, [rbp+180h+var_200]
0x180022297  test    r8, r8
0x18002229a  jz      short loc_1800222A5
0x18002229c  mov     ecx, [rbx+198h]
0x1800222a2  mov     [r8], ecx
0x1800222a5  mov     rcx, [rbx+1A8h]
0x1800222ac  mov     rax, [rbp+180h+var_1D8]
0x1800222b0  mov     [rax], rcx
0x1800222b3  lea     rcx, [rbp+180h+ssa]; pssa
0x1800222b7  call    ScriptStringFree
0x1800222bc  mov     eax, r12d
0x1800222bf  jmp     loc_180022501
0x1800222c4  cmp     r14d, 10h
0x1800222c8  jle     loc_180022795
0x1800222ce  lea     edi, ds:0[r14*8]
0x1800222d6  test    edi, edi
0x1800222d8  js      loc_1800225A4
0x1800222de  cmp     cs:?ghHeap@@3PEAXEA, r10; void * ghHeap
0x1800222e5  jz      loc_18002267C
0x1800222eb  mov     ecx, edi; unsigned int
0x1800222ed  call    ?Alloc@CTempMemory@@SAPEAXK@Z; CTempMemory::Alloc(ulong)
0x1800222f2  mov     rcx, rax
0x1800222f5  test    rax, rax
0x1800222f8  jz      loc_180022569
0x1800222fe  lea     r10, [rcx+r14*4]
0x180022302  mov     [rbp+180h+var_1A8], rcx
0x180022306  xor     ecx, ecx
0x180022308  mov     [rbp+180h+var_198], r10
0x18002230c  mov     [rbp+180h+var_19C], ecx
0x18002230f  xor     r8d, r8d
0x180022312  mov     edi, 0FC00h
0x180022317  mov     r9d, 0D800h
0x18002231d  mov     r11d, 0DC00h
0x180022323  cmp     r8d, ebx
0x180022326  jge     short loc_18002233D
0x180022328  movsxd  rdx, r8d
0x18002232b  movzx   eax, word ptr [r15+rdx*2]
0x180022330  and     ax, di
0x180022333  cmp     ax, r9w
0x180022337  jz      loc_1800226DD
0x18002233d  movsxd  rax, r8d
0x180022340  mov     [r10+rax*4], ecx
0x180022344  movzx   edx, word ptr [r15+rax*2]
0x180022349  movsxd  rcx, [rbp+180h+var_19C]
0x18002234d  mov     rax, [rbp+180h+var_1A8]
0x180022351  mov     [rax+rcx*4], edx
0x180022354  mov     ecx, [rbp+180h+var_19C]
0x180022357  inc     ecx
0x180022359  mov     r10, [rbp+180h+var_198]
0x18002235d  inc     r8d
0x180022360  mov     [rbp+180h+var_19C], ecx
0x180022363  cmp     r8d, r14d
0x180022366  jge     loc_1800226AF
0x18002236c  mov     r9d, 0D800h
0x180022372  jmp     short loc_180022323
0x180022374  xor     r8d, r8d
0x180022377  lea     rdi, __ImageBase
0x18002237e  mov     ebx, 309h
0x180022383  cmp     r8d, r14d
0x180022386  jge     loc_18002241B
0x18002238c  movsxd  rcx, r8d
0x18002238f  test    r11, r11
0x180022392  jnz     loc_1800225B3
0x180022398  mov     rax, [rbp+180h+var_1B0]
0x18002239c  movzx   ecx, word ptr [rax+rcx*2]
0x1800223a0  mov     edx, ecx
0x1800223a2  shr     edx, 10h
0x1800223a5  cmp     edx, 11h
0x1800223a8  jnb     loc_180022674
0x1800223ae  mov     r9, ds:rva ?pccUnicodeClass@@3QBQEBQEBFB[rdi+rdx*8]; short const * const * const near * const pccUnicodeClass ...
0x1800223b6  cmp     r9, 30Ah
0x1800223bd  jb      loc_18002252C
0x1800223c3  movsxd  r10, ecx
0x1800223c6  mov     rax, r10
0x1800223c9  sar     rax, 8
0x1800223cd  movzx   eax, al
0x1800223d0  mov     rax, [r9+rax*8]
0x1800223d4  cmp     rax, 30Ah
0x1800223da  jb      short loc_180022412
0x1800223dc  movzx   ecx, r10b
0x1800223e0  mov     r10, [rbp+180h+var_100]
0x1800223e7  movzx   eax, word ptr [rax+rcx*2]
0x1800223eb  test    ax, ax
0x1800223ee  jz      loc_18002266C
0x1800223f4  movsx   rcx, ax
0x1800223f8  lea     rax, [rcx+rcx*2]
0x1800223fc  test    ds:rva byte_1800B9FE2[rdi+rax*8], sil
0x180022404  jnz     loc_18002253C
0x18002240a  inc     r8d
0x18002240d  jmp     loc_180022383
0x180022412  mov     r10, [rbp+180h+var_100]
0x180022419  jmp     short loc_1800223EB
0x18002241b  test    r12b, 1
0x18002241f  jz      loc_180022839
0x180022425  lea     rcx, [rsp+280h+psc]; this
0x18002242a  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x18002242f  xorps   xmm0, xmm0
0x180022432  lea     rdx, [rbp+180h+var_1D0]
0x180022436  xor     eax, eax
0x180022438  mov     rcx, r13
0x18002243b  movups  [rbp+180h+var_1D0], xmm0
0x18002243f  mov     dword ptr [rbp+180h+var_1D0], 10h
0x180022446  mov     [rbp+180h+var_1C0], rax
0x18002244a  call    GetFontRealizationInfo
0x18002244f  test    eax, eax
0x180022451  jz      loc_18002217A
0x180022457  lea     rcx, csFontIdCache; lpCriticalSection
0x18002245e  call    cs:__imp_EnterCriticalSection
0x180022465  nop     dword ptr [rax+rax+00h]
0x18002246a  mov     edx, cs:g_cCachedFontsID
0x180022470  mov     ebx, dword ptr [rbp+180h+var_1D0+0Ch]
0x180022473  test    edx, edx
0x180022475  jle     loc_1800225C0
0x18002247b  xor     ecx, ecx
0x18002247d  cmp     ecx, edx
0x18002247f  jge     loc_1800225C0
0x180022485  movsxd  rax, ecx
0x180022488  lea     rax, ds:0[rax*8]
0x180022490  cmp     ebx, [rax+rdi+100E20h]
0x180022497  jnz     loc_180022525
0x18002249d  mov     edi, [rax+rdi+100E24h]
  ... truncated ...
```
