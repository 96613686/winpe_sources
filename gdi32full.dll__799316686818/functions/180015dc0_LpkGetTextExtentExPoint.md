# LpkGetTextExtentExPoint

- ea: `0x180015dc0`
- end: `0x180016744`
- name: `LpkGetTextExtentExPoint`
- size: `2436`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, int, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800206a0`
- `0x1800367d0`
- `0x180037eec`
- `0x1800588fc`

## callees

- `0x180009d00`
- `0x180009ea0`
- `0x18000db8c`
- `0x180010d60`
- `0x180010e60`
- `0x180011050`
- `0x180013320`
- `0x180015aa0`
- `0x180015c70`
- `0x180015dc0`
- `0x180016750`
- `0x180016900`
- `0x1800169c0`
- `0x180017010`
- `0x180017610`
- `0x180017770`
- `0x18003ac00`
- `0x180074ae0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180015e7b`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180015e7b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180015e9e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180015e9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016455`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800162ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016455`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001628b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001628b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001638b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001638b`
- `win32u!NtGdiGetGlyphIndicesW` at `0x1800163f2`
- `win32u!NtGdiGetGlyphIndicesW` at `0x1800163f2`
- `win32u!NtGdiGetTextExtentExW` at `0x180016312`
- `win32u!NtGdiGetTextExtentExW` at `0x180016312`
- `win32u!NtGdiAnyLinkedFonts` at `0x180016034`
- `win32u!NtGdiAnyLinkedFonts` at `0x180016034`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180015e67`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180015e67`

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
          if ( ((unsigned __int8)v16 & (unsigned __int8)byte_1800B6FE2[24 * (__int16)v41]) != 0 )
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
                v45 = dword_1800FDFA4[v44];
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
            dword_1800FDFA4[2 * g_pCurrentAvailablePos] = 0;
          }
          else
          {
            v46 = g_pCurrentAvailablePos;
            v45 = 1;
            dword_1800FDFA4[2 * g_pCurrentAvailablePos] = 1;
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
0x180015dc0  push    rbp
0x180015dc2  push    rbx
0x180015dc3  push    rsi
0x180015dc4  push    rdi
0x180015dc5  push    r12
0x180015dc7  push    r13
0x180015dc9  push    r14
0x180015dcb  push    r15
0x180015dcd  lea     rbp, [rsp-148h]
0x180015dd5  sub     rsp, 248h
0x180015ddc  mov     rax, cs:__security_cookie
0x180015de3  xor     rax, rsp
0x180015de6  mov     [rbp+180h+var_50], rax
0x180015ded  mov     rax, [rbp+180h+arg_30]
0x180015df4  xor     edi, edi
0x180015df6  mov     r13, rcx
0x180015df9  mov     [rbp+180h+var_1F0], r9d
0x180015dfd  mov     rcx, [rbp+180h+arg_20]
0x180015e04  mov     r15, rdx
0x180015e07  mov     rdx, [rbp+180h+arg_28]
0x180015e0e  mov     [rbp+180h+var_200], rcx
0x180015e12  mov     [rbp+180h+var_1F8], rdx
0x180015e16  movsxd  r14, r8d
0x180015e19  mov     [rbp+180h+var_1D8], rax
0x180015e1d  mov     [rbp+180h+ssa], rdi
0x180015e21  mov     [rbp+180h+var_1E0], rdi
0x180015e25  test    r13, r13
0x180015e28  jz      loc_180016469
0x180015e2e  test    rax, rax
0x180015e31  jz      loc_180016469
0x180015e37  test    r8d, r8d
0x180015e3a  jz      loc_18001668F
0x180015e40  test    r15, r15
0x180015e43  jz      loc_18001668F
0x180015e49  mov     rcx, r13; hdc
0x180015e4c  call    GetTextAlign
0x180015e51  mov     r12d, 1
0x180015e57  bt      eax, 8
0x180015e5b  jb      loc_18001665C
0x180015e61  mov     ebx, edi
0x180015e63  mov     [rsp+280h+var_20C], ebx
0x180015e67  call    cs:__imp_NlsGetCacheUpdateCount
0x180015e6d  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180015e73  jz      short loc_180015ED8
0x180015e75  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180015e7b  call    cs:__imp_GetUserDefaultLCID
0x180015e81  mov     r9d, 50h ; 'P'; cchData
0x180015e87  lea     r8, [rbp+180h+LCData]; lpLCData
0x180015e8e  mov     edx, 58h ; 'X'; LCType
0x180015e93  mov     cs:g_UserLocale, eax
0x180015e99  mov     ecx, 400h; Locale
0x180015e9e  call    cs:__imp_GetLocaleInfoW
0x180015ea4  test    eax, eax
0x180015ea6  jz      loc_18001634B
0x180015eac  mov     eax, 800h
0x180015eb1  test    [rbp+180h+var_E2], ax
0x180015eb8  jz      loc_18001634B
0x180015ebe  mov     eax, r12d
0x180015ec1  lea     rdx, g_DigitSubstitute; psds
0x180015ec8  mov     cs:g_UserBidiLocale, eax
0x180015ece  mov     ecx, 400h; Locale
0x180015ed3  call    ScriptRecordDigitSubstitution
0x180015ed8  cmp     cs:g_DigitSubstitute.DigitSubstitute, r12b
0x180015edf  mov     esi, 3
0x180015ee4  mov     rcx, r13; hdc
0x180015ee7  cmovz   esi, r12d
0x180015eeb  call    GetLayout
0x180015ef0  mov     ecx, esi
0x180015ef2  and     eax, r12d
0x180015ef5  or      ecx, 4; unsigned int
0x180015ef8  cmp     ebx, eax
0x180015efa  cmovnz  esi, ecx
0x180015efd  test    r14d, r14d
0x180015f00  js      loc_180015FB2
0x180015f06  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x180015f0b  movzx   r12d, [rbp+180h+var_110]
0x180015f10  lea     ebx, [r14-1]
0x180015f14  or      r12w, 1
0x180015f19  mov     [rbp+180h+var_1A8], rdi
0x180015f1d  mov     r11, rdi
0x180015f20  mov     [rbp+180h+var_100], rdi
0x180015f27  mov     r10, rdi
0x180015f2a  mov     [rbp+180h+var_198], rdi
0x180015f2e  mov     ecx, edi
0x180015f30  mov     [rbp+180h+var_110], r12w
0x180015f35  mov     dword ptr [rsp+280h+psc.uDefaultLanguage], eax
0x180015f39  mov     edi, 0FC00h
0x180015f3e  mov     [rbp+180h+var_1B0], r15
0x180015f42  mov     r9d, 0D800h
0x180015f48  mov     [rbp+180h+var_1A0], r14d
0x180015f4c  mov     r8d, 0DC00h
0x180015f52  mov     [rbp+180h+var_19C], r14d
0x180015f56  cmp     ecx, ebx
0x180015f58  jge     short loc_180015F81
0x180015f5a  movsxd  rdx, ecx
0x180015f5d  movzx   eax, word ptr [r15+rdx*2]
0x180015f62  and     ax, di
0x180015f65  cmp     ax, r9w
0x180015f69  jz      loc_1800165C6
0x180015f6f  inc     ecx
0x180015f71  jmp     short loc_180015F56
0x180015f73  mov     eax, 0FFFEh
0x180015f78  and     r12w, ax
0x180015f7c  mov     [rbp+180h+var_110], r12w
0x180015f81  test    r12b, 1
0x180015f85  jz      loc_1800160EC
0x180015f8b  test    r11, r11
0x180015f8e  jz      loc_18001619C
0x180015f94  test    r12b, 1
0x180015f98  jz      loc_1800165DE
0x180015f9e  lea     rcx, [rsp+280h+psc]; this
0x180015fa3  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180015fa8  mov     r12d, 1
0x180015fae  mov     ebx, [rsp+280h+var_20C]
0x180015fb2  mov     rcx, r13; hdc
0x180015fb5  call    GetTextCharacterExtra
0x180015fba  test    eax, eax
0x180015fbc  jnz     loc_1800162E2
0x180015fc2  mov     rcx, r13; h
0x180015fc5  call    GetObjectType
0x180015fca  mov     edi, [rbp+180h+arg_40]
0x180015fd0  mov     esi, eax
0x180015fd2  cmp     edi, 0FFFFFFFFh
0x180015fd5  jnz     loc_1800164C8
0x180015fdb  mov     ecx, 20h ; ' '
0x180015fe0  shl     ebx, 8
0x180015fe3  mov     eax, 4000080h
0x180015fe8  mov     [rsp+280h+var_20C], ebx
0x180015fec  mov     r8d, 80h
0x180015ff2  or      ebx, ecx
0x180015ff4  mov     dword ptr [rsp+280h+psc.uDefaultLanguage], 0
0x180015ffc  cmp     [rbp+180h+var_200], 0
0x180016001  cmovz   eax, r8d
0x180016005  or      ebx, eax
0x180016007  xor     eax, eax
0x180016009  mov     word ptr [rsp+280h+pss.uBidiLevel], ax
0x18001600e  call    CheckUpdateNLSScriptSettings
0x180016013  lea     r8, [rsp+280h+pss]; pss
0x180016018  lea     rdx, [rsp+280h+psc]; psc
0x18001601d  lea     rcx, g_DigitSubstitute; psds
0x180016024  call    ScriptApplyDigitSubstitution
0x180016029  mov     eax, cs:g_iUseFontLinking
0x18001602f  cmp     eax, 0FFFFFFFFh
0x180016032  jnz     short loc_180016040
0x180016034  call    cs:__imp_NtGdiAnyLinkedFonts
0x18001603a  mov     cs:g_iUseFontLinking, eax
0x180016040  test    eax, eax
0x180016042  jz      short loc_180016048
0x180016044  bts     ebx, 0Ch
0x180016048  or      dword ptr [rsp+280h+psc.uDefaultLanguage], 1800000h
0x180016050  lea     rax, [rbp+180h+ssa]
0x180016054  mov     [rsp+280h+pssa], rax; pssa
0x180016059  xor     r9d, r9d; cGlyphs
0x18001605c  xor     eax, eax
0x18001605e  mov     r8d, r14d; cString
0x180016061  mov     [rsp+280h+pbInClass], rax; pbInClass
0x180016066  mov     rdx, r15; pString
0x180016069  mov     [rsp+280h+pTabdef], rax; pTabdef
0x18001606e  mov     rcx, r13; hdc
0x180016071  mov     [rsp+280h+piDx], rax; piDx
0x180016076  lea     rax, [rsp+280h+pss]
0x18001607b  mov     [rsp+280h+psState], rax; psState
0x180016080  lea     rax, [rsp+280h+psc]
0x180016085  mov     [rsp+280h+psControl], rax; psControl
0x18001608a  mov     eax, [rbp+180h+var_1F0]
0x18001608d  mov     [rsp+280h+iReqWidth], eax; iReqWidth
0x180016091  mov     [rsp+280h+dwFlags], ebx; dwFlags
0x180016095  mov     [rsp+280h+iCharset], 0FFFFFFFFh; iCharset
0x18001609d  call    ScriptStringAnalyse
0x1800160a2  test    eax, eax
0x1800160a4  js      loc_180016469
0x1800160aa  mov     rdx, [rbp+180h+var_1F8]; piDx
0x1800160ae  mov     rbx, [rbp+180h+ssa]
0x1800160b2  test    rdx, rdx
0x1800160b5  jnz     loc_1800165F0
0x1800160bb  mov     r8, [rbp+180h+var_200]
0x1800160bf  test    r8, r8
0x1800160c2  jz      short loc_1800160CD
0x1800160c4  mov     ecx, [rbx+198h]
0x1800160ca  mov     [r8], ecx
0x1800160cd  mov     rcx, [rbx+1A8h]
0x1800160d4  mov     rax, [rbp+180h+var_1D8]
0x1800160d8  mov     [rax], rcx
0x1800160db  lea     rcx, [rbp+180h+ssa]; pssa
0x1800160df  call    ScriptStringFree
0x1800160e4  mov     eax, r12d
0x1800160e7  jmp     loc_180016318
0x1800160ec  cmp     r14d, 10h
0x1800160f0  jle     loc_180016599
0x1800160f6  lea     edi, ds:0[r14*8]
0x1800160fe  test    edi, edi
0x180016100  js      loc_1800163B4
0x180016106  cmp     cs:?ghHeap@@3PEAXEA, r10; void * ghHeap
0x18001610d  jz      loc_180016480
0x180016113  mov     ecx, edi; unsigned int
0x180016115  call    ?Alloc@CTempMemory@@SAPEAXK@Z; CTempMemory::Alloc(ulong)
0x18001611a  mov     rcx, rax
0x18001611d  test    rax, rax
0x180016120  jz      loc_18001637F
0x180016126  lea     r10, [rcx+r14*4]
0x18001612a  mov     [rbp+180h+var_1A8], rcx
0x18001612e  xor     ecx, ecx
0x180016130  mov     [rbp+180h+var_198], r10
0x180016134  mov     [rbp+180h+var_19C], ecx
0x180016137  xor     r8d, r8d
0x18001613a  mov     edi, 0FC00h
0x18001613f  mov     r9d, 0D800h
0x180016145  mov     r11d, 0DC00h
0x18001614b  cmp     r8d, ebx
0x18001614e  jge     short loc_180016165
0x180016150  movsxd  rdx, r8d
0x180016153  movzx   eax, word ptr [r15+rdx*2]
0x180016158  and     ax, di
0x18001615b  cmp     ax, r9w
0x18001615f  jz      loc_1800164E1
0x180016165  movsxd  rax, r8d
0x180016168  mov     [r10+rax*4], ecx
0x18001616c  movzx   edx, word ptr [r15+rax*2]
0x180016171  movsxd  rcx, [rbp+180h+var_19C]
0x180016175  mov     rax, [rbp+180h+var_1A8]
0x180016179  mov     [rax+rcx*4], edx
0x18001617c  mov     ecx, [rbp+180h+var_19C]
0x18001617f  inc     ecx
0x180016181  mov     r10, [rbp+180h+var_198]
0x180016185  inc     r8d
0x180016188  mov     [rbp+180h+var_19C], ecx
0x18001618b  cmp     r8d, r14d
0x18001618e  jge     loc_1800164B3
0x180016194  mov     r9d, 0D800h
0x18001619a  jmp     short loc_18001614B
0x18001619c  xor     r8d, r8d
0x18001619f  lea     rdi, __ImageBase
0x1800161a6  mov     ebx, 309h
0x1800161ab  nop     dword ptr [rax+rax+00h]
0x1800161b0  cmp     r8d, r14d
0x1800161b3  jge     loc_180016248
0x1800161b9  movsxd  rcx, r8d
0x1800161bc  test    r11, r11
0x1800161bf  jnz     loc_1800163C3
0x1800161c5  mov     rax, [rbp+180h+var_1B0]
0x1800161c9  movzx   ecx, word ptr [rax+rcx*2]
0x1800161cd  mov     edx, ecx
0x1800161cf  shr     edx, 10h
0x1800161d2  cmp     edx, 11h
0x1800161d5  jnb     loc_180016478
0x1800161db  mov     r9, ds:rva ?pccUnicodeClass@@3QBQEBQEBFB[rdi+rdx*8]; short const * const * const near * const pccUnicodeClass ...
0x1800161e3  cmp     r9, 30Ah
0x1800161ea  jb      loc_180016342
0x1800161f0  movsxd  r10, ecx
0x1800161f3  mov     rax, r10
0x1800161f6  sar     rax, 8
0x1800161fa  movzx   eax, al
0x1800161fd  mov     rax, [r9+rax*8]
0x180016201  cmp     rax, 30Ah
0x180016207  jb      short loc_18001623F
0x180016209  movzx   ecx, r10b
0x18001620d  mov     r10, [rbp+180h+var_100]
0x180016214  movzx   eax, word ptr [rax+rcx*2]
0x180016218  test    ax, ax
0x18001621b  jz      loc_180016470
0x180016221  movsx   rcx, ax
0x180016225  lea     rax, [rcx+rcx*2]
0x180016229  test    ds:rva byte_1800B6FE2[rdi+rax*8], sil
0x180016231  jnz     loc_180016352
0x180016237  inc     r8d
0x18001623a  jmp     loc_1800161B0
0x18001623f  mov     r10, [rbp+180h+var_100]
0x180016246  jmp     short loc_180016218
0x180016248  test    r12b, 1
0x18001624c  jz      loc_180016639
0x180016252  lea     rcx, [rsp+280h+psc]; this
0x180016257  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x18001625c  xorps   xmm0, xmm0
0x18001625f  lea     rdx, [rbp+180h+var_1D0]
0x180016263  xor     eax, eax
0x180016265  mov     rcx, r13
0x180016268  movups  [rbp+180h+var_1D0], xmm0
0x18001626c  mov     dword ptr [rbp+180h+var_1D0], 10h
0x180016273  mov     [rbp+180h+var_1C0], rax
0x180016277  call    GetFontRealizationInfo
0x18001627c  test    eax, eax
0x18001627e  jz      loc_180015FA8
0x180016284  lea     rcx, csFontIdCache; lpCriticalSection
0x18001628b  call    cs:__imp_EnterCriticalSection
0x180016291  mov     edx, cs:g_cCachedFontsID
0x180016297  mov     ebx, dword ptr [rbp+180h+var_1D0+0Ch]
0x18001629a  test    edx, edx
0x18001629c  jle     loc_1800163D0
0x1800162a2  xor     ecx, ecx
0x1800162a4  cmp     ecx, edx
0x1800162a6  jge     loc_1800163D0
0x1800162ac  movsxd  rax, ecx
0x1800162af  lea     rax, ds:0[rax*8]
0x1800162b7  cmp     ebx, [rax+rdi+0FDFA0h]
0x1800162be  jnz     short loc_18001633B
0x1800162c0  mov     edi, [rax+rdi+0FDFA4h]
0x1800162c7  lea     rcx, csFontIdCache; lpCriticalSection
0x1800162ce  call    cs:__imp_LeaveCriticalSection
0x1800162d4  mov     r12d, 1
0x1800162da  test    edi, edi
  ... truncated ...
```
