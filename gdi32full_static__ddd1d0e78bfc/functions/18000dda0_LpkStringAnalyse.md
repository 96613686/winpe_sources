# LpkStringAnalyse

- ea: `0x18000dda0`
- end: `0x18000e3d9`
- name: `LpkStringAnalyse`
- size: `1593`
- prototype: `__int64 __fastcall(int, int, int, int, int, DWORD, int, int, __int64, __int64, int *, SCRIPT_TABDEF *, __int64, __int64)`
- caller_count: `10`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017df0`
- `0x180019cd0`
- `0x18001fc00`
- `0x180021f80`
- `0x180043050`
- `0x180058680`
- `0x1800620ac`
- `0x18006507c`
- `0x18007b6b0`
- `0x1800a26f0`

## callees

- `0x180006f3c`
- `0x18000d040`
- `0x18000d410`
- `0x18000dda0`
- `0x18000e550`
- `0x180019840`
- `0x18001ac40`
- `0x180022950`
- `0x180023af0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18000de44`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18000de44`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000de6a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000de6a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000decf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e043`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e078`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000decf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e043`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000e078`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dfe2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e110`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dfe2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e298`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e298`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df7d`
- `win32u!NtGdiAnyLinkedFonts` at `0x18000e139`
- `win32u!NtGdiAnyLinkedFonts` at `0x18000e139`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18000de24`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18000de24`

## pseudocode

```c
HRESULT __fastcall LpkStringAnalyse(
        HDC a1,
        const void *a2,
        int a3,
        int a4,
        int iCharset,
        DWORD a6,
        int a7,
        int iReqWidth,
        SCRIPT_CONTROL *a9,
        SCRIPT_STATE *a10,
        int *piDx,
        SCRIPT_TABDEF *pTabdef,
        BYTE *a13,
        SCRIPT_STRING_ANALYSIS *a14)
{
  int v14; // r12d
  SCRIPT_CONTROL v15; // esi
  int v16; // r15d
  SCRIPT_STATE v17; // bx
  const void *v18; // r14
  HDC v19; // rdi
  int CacheUpdateCount; // eax
  BOOL v21; // eax
  __int16 i; // r14
  void * near *v23; // rdi
  void * near **v24; // r12
  signed __int32 v25; // edx
  signed __int32 v26; // ecx
  int v27; // eax
  __int64 v28; // r14
  void * near *v29; // rdx
  DWORD v30; // ecx
  int v31; // ecx
  SCRIPT_STATE v32; // bx
  void * near *Value; // rbx
  _QWORD *v34; // rax
  _QWORD *v35; // r8
  __int64 v36; // rcx
  int v37; // ecx
  void * near *v38; // rdx
  char *v39; // rax
  __int64 v40; // rax
  int v41; // eax
  int v42; // eax
  DWORD dwFlags; // ecx
  __int16 v45; // esi^2
  __int16 v46; // r8
  __int16 j; // dx
  void * near *v48; // rax
  signed __int32 v49; // eax
  SCRIPT_CONTROL psc; // [rsp+70h] [rbp-90h] BYREF
  SCRIPT_STATE pss; // [rsp+74h] [rbp-8Ch] BYREF
  int cString; // [rsp+78h] [rbp-88h]
  int cGlyphs; // [rsp+7Ch] [rbp-84h]
  int v54; // [rsp+80h] [rbp-80h] BYREF
  SCRIPT_DIGITSUBSTITUTE pString; // [rsp+88h] [rbp-78h] BYREF
  HDC hdc; // [rsp+98h] [rbp-68h]
  SCRIPT_STRING_ANALYSIS *pssa; // [rsp+A0h] [rbp-60h]
  BYTE *pbInClass; // [rsp+A8h] [rbp-58h]
  WCHAR LCData[80]; // [rsp+B0h] [rbp-50h] BYREF

  v14 = a4;
  v15 = (SCRIPT_CONTROL)a9;
  v16 = a3;
  v17 = (SCRIPT_STATE)a10;
  v18 = a2;
  pbInClass = a13;
  v19 = a1;
  pssa = a14;
  cGlyphs = a4;
  cString = a3;
  *(_QWORD *)&pString = a2;
  hdc = a1;
  if ( a9 )
    v15 = *a9;
  psc = v15;
  if ( a10 )
    v17 = *a10;
  pss = v17;
  CacheUpdateCount = NlsGetCacheUpdateCount();
  if ( CacheUpdateCount != g_ulNlsUpdateCacheCount )
  {
    g_ulNlsUpdateCacheCount = CacheUpdateCount;
    g_UserLocale = GetUserDefaultLCID();
    v21 = GetLocaleInfoW(0x400u, 0x58u, LCData, 80) && (LCData[7] & 0x800) != 0;
    g_UserBidiLocale = v21;
    ScriptRecordDigitSubstitution(0x400u, &g_DigitSubstitute);
  }
  if ( a7 < 0 )
  {
    if ( gdwTlsIndex == -1 || TlsGetValue(gdwTlsIndex) )
      goto LABEL_32;
    if ( ghHeap || !gfMemoryInitFailed && (unsigned int)UspInitMemory() )
    {
      for ( i = 0; i < 5; ++i )
      {
        if ( _InterlockedExchange((volatile __int32 *)&grStaticBufferFreeFlags + i, 0) == 1 )
        {
          v23 = (&grStaticBuffers)[i];
          v24 = &(&grStaticBuffers)[i];
          if ( v23 )
            goto LABEL_27;
          if ( (int)UspAllocCache(0x4000, v24) < 0 )
            *((_DWORD *)&grStaticBufferFreeFlags + i) = 1;
          else
            v23 = *v24;
          v25 = gAllocatedStaticBufferCount;
          v26 = i + 1;
          if ( gAllocatedStaticBufferCount < v26 )
          {
            do
            {
              v49 = _InterlockedCompareExchange(&gAllocatedStaticBufferCount, v26, v25);
              if ( v25 == v49 )
                break;
              v25 = v49;
            }
            while ( v49 < v26 );
          }
          if ( v23 )
            goto LABEL_27;
          break;
        }
      }
    }
    v23 = 0;
    if ( (unsigned int)CheckInitUspMemory() )
    {
      v23 = (void * near *)HeapAlloc(ghHeap, 0, 0x4000u);
      if ( v23 )
      {
        v27 = 0;
      }
      else
      {
        v23 = 0;
        v27 = -2147024882;
      }
    }
    else
    {
      v27 = -2147024882;
    }
    if ( v27 < 0 )
      goto LABEL_32;
    if ( v23 )
    {
LABEL_27:
      v28 = (__int64)(v23 + 5);
      *(_DWORD *)v23 = 0;
      v23[1] = 0;
      v23[2] = 0;
      v23[3] = 0;
      if ( v23 == (void * near *)-40LL )
      {
LABEL_31:
        UspFreeMem((LPVOID)v28);
LABEL_32:
        v31 = 0;
LABEL_33:
        v54 = v31;
        if ( *((unsigned __int8 *)&g_DigitSubstitute + 4) == 1 )
        {
          *((_WORD *)&psc + 1) = (*(_DWORD *)&v15 & 0xFFFEFFFF) >> 16;
          *(_WORD *)&psc = g_DigitSubstitute;
          v32 = (SCRIPT_STATE)(*(_WORD *)&v17 & 0xFEFF);
        }
        else
        {
          if ( *((_BYTE *)&g_DigitSubstitute + 4) )
          {
            if ( *((unsigned __int8 *)&g_DigitSubstitute + 4) == 2 )
            {
              *((_WORD *)&psc + 1) = (*(_DWORD *)&v15 & 0xFFFEFFFF) >> 16;
              v32 = (SCRIPT_STATE)(*(_WORD *)&v17 | 0x100);
              *(_WORD *)&psc = g_DigitSubstitute;
              goto LABEL_35;
            }
            if ( *((unsigned __int8 *)&g_DigitSubstitute + 4) != 3 )
            {
              CTempMemory::~CTempMemory((CTempMemory *)&v54);
LABEL_50:
              v19 = hdc;
              v18 = (const void *)pString;
              v16 = cString;
              v14 = cGlyphs;
              goto LABEL_51;
            }
            v45 = *((_WORD *)&v15 + 1) & 0xFFFE;
          }
          else
          {
            v45 = *((_WORD *)&v15 + 1) | 1;
          }
          v32 = (SCRIPT_STATE)(*(_WORD *)&v17 | 0x100);
          *((_WORD *)&psc + 1) = v45;
          *(_WORD *)&psc = *((_WORD *)&g_DigitSubstitute + 1);
        }
LABEL_35:
        pss = v32;
        if ( v31 )
        {
          Value = (void * near *)TlsGetValue(gdwTlsIndex);
          if ( Value )
          {
            if ( ghHeap || !gfMemoryInitFailed && (unsigned int)UspInitMemory() )
            {
              if ( gdwTlsIndex == -1 )
                goto LABEL_61;
              v34 = TlsGetValue(gdwTlsIndex);
              v35 = v34;
              if ( !v34 )
                goto LABEL_61;
              v36 = v34[1];
              if ( v36 && (unsigned __int64)Value >= v36 + 16 && (unsigned __int64)Value < v34[2] )
              {
                v37 = *((_DWORD *)Value - 3);
                v38 = Value - 2;
                if ( (v37 & 1) != 0 || (v39 = (char *)v34[3], *((_DWORD *)v38 + 1) = v37 | 1, v38 != (void * near *)v39) )
                {
                  v41 = 1;
                }
                else
                {
                  while ( 1 )
                  {
                    v40 = *((unsigned int *)v38 + 3);
                    if ( !(_DWORD)v40 )
                      break;
                    v35[2] = v38;
                    v38 = (void * near *)((char *)v38 - 16 - v40);
                    if ( (*((_BYTE *)v38 + 4) & 1) == 0 )
                      goto LABEL_47;
                  }
                  v38 = 0;
                  v35[2] = v35[1];
LABEL_47:
                  v35[3] = v38;
                  v41 = 1;
                }
              }
              else
              {
                v41 = 0;
              }
              if ( !v41 )
              {
LABEL_61:
                v46 = 5;
                if ( gAllocatedStaticBufferCount < 5 )
                  v46 = gAllocatedStaticBufferCount;
                for ( j = 0; j < v46; ++j )
                {
                  v48 = (&grStaticBuffers)[j];
                  if ( v48 && v48 == Value )
                  {
                    _InterlockedExchange((volatile __int32 *)&grStaticBufferFreeFlags + j, 1);
                    goto LABEL_49;
                  }
                }
                if ( !HeapFree(ghHeap, 0, Value) )
                  GetLastError();
              }
            }
LABEL_49:
            TlsSetValue(gdwTlsIndex, 0);
          }
        }
        goto LABEL_50;
      }
      v29 = v23;
    }
    else
    {
      v29 = 0;
      v28 = 40;
    }
    v30 = gdwTlsIndex;
    *(_DWORD *)v29 = 16344;
    v29[1] = (void *)v28;
    v29[2] = (void *)v28;
    if ( TlsSetValue(v30, v29) )
    {
      v31 = 1;
      goto LABEL_33;
    }
    goto LABEL_31;
  }
  pString.dwReserved = g_DigitSubstitute.dwReserved;
  *(_DWORD *)&pString = g_DigitSubstitute;
  *((_DWORD *)&pString + 1) = *((_DWORD *)&g_DigitSubstitute + 1)
                            ^ (unsigned __int8)(a7 ^ *((_BYTE *)&g_DigitSubstitute + 4));
  ScriptApplyDigitSubstitution(&pString, &psc, &pss);
LABEL_51:
  v42 = g_iUseFontLinking;
  if ( g_iUseFontLinking == -1 )
  {
    v42 = NtGdiAnyLinkedFonts();
    g_iUseFontLinking = v42;
  }
  dwFlags = a6;
  if ( v42 )
    dwFlags = a6 | 0x1000;
  psc = (SCRIPT_CONTROL)(*(_DWORD *)&psc | 0x1800000);
  return ScriptStringAnalyse(
           v19,
           v18,
           v16,
           v14,
           iCharset,
           dwFlags,
           iReqWidth,
           &psc,
           &pss,
           piDx,
           pTabdef,
           pbInClass,
           pssa);
}

```

## disassembly

```asm
0x18000dda0  push    rbp
0x18000dda2  push    rbx
0x18000dda3  push    rsi
0x18000dda4  push    rdi
0x18000dda5  push    r12
0x18000dda7  push    r13
0x18000dda9  push    r14
0x18000ddab  push    r15
0x18000ddad  lea     rbp, [rsp-68h]
0x18000ddb2  sub     rsp, 168h
0x18000ddb9  mov     rax, cs:__security_cookie
0x18000ddc0  xor     rax, rsp
0x18000ddc3  mov     [rbp+0A0h+var_50], rax
0x18000ddc7  mov     rax, [rbp+0A0h+arg_60]
0x18000ddce  mov     r12d, r9d
0x18000ddd1  mov     rsi, [rbp+0A0h+arg_40]
0x18000ddd8  mov     r15d, r8d
0x18000dddb  mov     rbx, [rbp+0A0h+arg_48]
0x18000dde2  mov     r14, rdx
0x18000dde5  mov     [rbp+0A0h+var_F8], rax
0x18000dde9  mov     rdi, rcx
0x18000ddec  mov     rax, [rbp+0A0h+arg_68]
0x18000ddf3  mov     [rbp+0A0h+var_100], rax
0x18000ddf7  mov     [rsp+1A0h+cGlyphs], r9d
0x18000ddfc  mov     [rsp+1A0h+cString], r8d
0x18000de01  mov     [rbp+0A0h+pString], rdx
0x18000de05  mov     [rbp+0A0h+hdc], rcx
0x18000de09  test    rsi, rsi
0x18000de0c  jnz     loc_18000E32F
0x18000de12  mov     dword ptr [rsp+1A0h+psc.uDefaultLanguage], esi
0x18000de16  test    rbx, rbx
0x18000de19  jnz     loc_18000E336
0x18000de1f  mov     word ptr [rsp+1A0h+pss.uBidiLevel], bx
0x18000de24  call    cs:__imp_NlsGetCacheUpdateCount
0x18000de2b  nop     dword ptr [rax+rax+00h]
0x18000de30  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x18000de36  mov     r13d, 1
0x18000de3c  jz      short loc_18000DEA7
0x18000de3e  mov     cs:g_ulNlsUpdateCacheCount, eax
0x18000de44  call    cs:__imp_GetUserDefaultLCID
0x18000de4b  nop     dword ptr [rax+rax+00h]
0x18000de50  mov     r9d, 50h ; 'P'; cchData
0x18000de56  lea     r8, [rbp+0A0h+LCData]; lpLCData
0x18000de5a  mov     edx, 58h ; 'X'; LCType
0x18000de5f  mov     cs:g_UserLocale, eax
0x18000de65  mov     ecx, 400h; Locale
0x18000de6a  call    cs:__imp_GetLocaleInfoW
0x18000de71  nop     dword ptr [rax+rax+00h]
0x18000de76  test    eax, eax
0x18000de78  jz      loc_18000E20F
0x18000de7e  mov     eax, 800h
0x18000de83  test    [rbp+0A0h+var_E2], ax
0x18000de87  jz      loc_18000E20F
0x18000de8d  mov     eax, r13d
0x18000de90  lea     rdx, g_DigitSubstitute; psds
0x18000de97  mov     cs:g_UserBidiLocale, eax
0x18000de9d  mov     ecx, 400h; Locale
0x18000dea2  call    ScriptRecordDigitSubstitution
0x18000dea7  mov     ecx, [rbp+0A0h+arg_30]
0x18000dead  test    ecx, ecx
0x18000deaf  jns     loc_18000E362
0x18000deb5  cmp     cs:?gdwTlsIndex@@3KA, 0FFFFFFFFh; ulong gdwTlsIndex
0x18000debc  lea     rdi, __ImageBase
0x18000dec3  jz      loc_18000DFFF
0x18000dec9  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18000decf  call    cs:__imp_TlsGetValue
0x18000ded6  nop     dword ptr [rax+rax+00h]
0x18000dedb  test    rax, rax
0x18000dede  jnz     loc_18000DFFF
0x18000dee4  cmp     cs:?ghHeap@@3PEAXEA, rax; void * ghHeap
0x18000deeb  jz      loc_18000E2E5
0x18000def1  xor     r14d, r14d
0x18000def4  cmp     r14w, 5
0x18000def9  jge     short loc_18000DF5F
0x18000defb  xor     eax, eax
0x18000defd  movsx   rcx, r14w
0x18000df01  lea     r15, rva ?grStaticBufferFreeFlags@@3PAJA[rdi]; long near * grStaticBufferFreeFlags ...
0x18000df08  xchg    eax, [r15+rcx*4]
0x18000df0c  lea     r15, [r15+rcx*4]
0x18000df10  cmp     eax, r13d
0x18000df13  jnz     loc_18000E2BD
0x18000df19  lea     r12, rva ?grStaticBuffers@@3PAPEAXA[rdi]; void * near * grStaticBuffers ...
0x18000df20  mov     rdi, [r12+rcx*8]
0x18000df24  lea     r12, [r12+rcx*8]
0x18000df28  test    rdi, rdi
0x18000df2b  jnz     short loc_18000DFA4
0x18000df2d  mov     rdx, r12
0x18000df30  mov     ecx, 4000h
0x18000df35  call    UspAllocCache
0x18000df3a  test    eax, eax
0x18000df3c  js      loc_18000E35A
0x18000df42  mov     rdi, [r12]
0x18000df46  mov     edx, cs:?gAllocatedStaticBufferCount@@3JA; long gAllocatedStaticBufferCount
0x18000df4c  movsx   ecx, r14w
0x18000df50  inc     ecx
0x18000df52  cmp     edx, ecx
0x18000df54  jl      loc_18000E3B0
0x18000df5a  test    rdi, rdi
0x18000df5d  jnz     short loc_18000DFA4
0x18000df5f  xor     edi, edi
0x18000df61  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x18000df66  test    eax, eax
0x18000df68  jz      loc_18000E27A
0x18000df6e  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x18000df75  xor     edx, edx; dwFlags
0x18000df77  mov     r8d, 4000h; dwBytes
0x18000df7d  call    cs:__imp_HeapAlloc
0x18000df84  nop     dword ptr [rax+rax+00h]
0x18000df89  mov     rdi, rax
0x18000df8c  test    rax, rax
0x18000df8f  jz      loc_18000E3CD
0x18000df95  xor     eax, eax
0x18000df97  test    eax, eax
0x18000df99  js      short loc_18000DFFF
0x18000df9b  test    rdi, rdi
0x18000df9e  jz      loc_18000E3A5
0x18000dfa4  lea     r14, [rdi+28h]
0x18000dfa8  mov     dword ptr [rdi], 0
0x18000dfae  mov     qword ptr [rdi+8], 0
0x18000dfb6  mov     qword ptr [rdi+10h], 0
0x18000dfbe  mov     qword ptr [rdi+18h], 0
0x18000dfc6  test    r14, r14
0x18000dfc9  jz      short loc_18000DFF7
0x18000dfcb  mov     rdx, rdi; lpTlsValue
0x18000dfce  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18000dfd4  mov     dword ptr [rdx], 3FD8h
0x18000dfda  mov     [rdx+8], r14
0x18000dfde  mov     [rdx+10h], r14
0x18000dfe2  call    cs:__imp_TlsSetValue
0x18000dfe9  nop     dword ptr [rax+rax+00h]
0x18000dfee  test    eax, eax
0x18000dff0  jz      short loc_18000DFF7
0x18000dff2  mov     ecx, r13d
0x18000dff5  jmp     short loc_18000E001
0x18000dff7  mov     rcx, r14; lpMem
0x18000dffa  call    UspFreeMem
0x18000dfff  xor     ecx, ecx
0x18000e001  movzx   eax, cs:g_DigitSubstitute.DigitSubstitute
0x18000e008  mov     [rbp+0A0h+var_120], ecx
0x18000e00b  cmp     eax, r13d
0x18000e00e  jnz     loc_18000E1E9
0x18000e014  movzx   eax, cs:g_DigitSubstitute.NationalDigitLanguage
0x18000e01b  btr     esi, 10h
0x18000e01f  mov     dword ptr [rsp+1A0h+psc.uDefaultLanguage], esi
0x18000e023  mov     word ptr [rsp+1A0h+psc.uDefaultLanguage], ax
0x18000e028  mov     eax, 0FEFFh
0x18000e02d  and     bx, ax
0x18000e030  mov     word ptr [rsp+1A0h+pss.uBidiLevel], bx
0x18000e035  test    ecx, ecx
0x18000e037  jz      loc_18000E11C
0x18000e03d  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18000e043  call    cs:__imp_TlsGetValue
0x18000e04a  nop     dword ptr [rax+rax+00h]
0x18000e04f  mov     rbx, rax
0x18000e052  test    rax, rax
0x18000e055  jz      loc_18000E11C
0x18000e05b  cmp     cs:?ghHeap@@3PEAXEA, 0; void * ghHeap
0x18000e063  jz      loc_18000E2C6
0x18000e069  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18000e06f  cmp     ecx, 0FFFFFFFFh
0x18000e072  jz      loc_18000E21D
0x18000e078  call    cs:__imp_TlsGetValue
0x18000e07f  nop     dword ptr [rax+rax+00h]
0x18000e084  mov     r8, rax
0x18000e087  test    rax, rax
0x18000e08a  jz      loc_18000E21D
0x18000e090  mov     rcx, [rax+8]
0x18000e094  test    rcx, rcx
0x18000e097  jz      loc_18000E216
0x18000e09d  add     rcx, 10h
0x18000e0a1  cmp     rbx, rcx
0x18000e0a4  jb      loc_18000E216
0x18000e0aa  cmp     rbx, [rax+10h]
0x18000e0ae  jnb     loc_18000E216
0x18000e0b4  mov     ecx, [rbx-0Ch]
0x18000e0b7  lea     rdx, [rbx-10h]
0x18000e0bb  test    r13b, cl
0x18000e0be  jnz     loc_18000E284
0x18000e0c4  mov     rax, [rax+18h]
0x18000e0c8  or      ecx, r13d
0x18000e0cb  mov     [rdx+4], ecx
0x18000e0ce  cmp     rdx, rax
0x18000e0d1  jnz     loc_18000E284
0x18000e0d7  mov     eax, [rdx+0Ch]
0x18000e0da  test    eax, eax
0x18000e0dc  jz      loc_18000E26B
0x18000e0e2  mov     [r8+10h], rdx
0x18000e0e6  mov     rcx, 0FFFFFFFFFFFFFFF0h
0x18000e0ed  sub     rcx, rax
0x18000e0f0  add     rdx, rcx
0x18000e0f3  test    [rdx+4], r13b
0x18000e0f7  jnz     short loc_18000E0D7
0x18000e0f9  mov     [r8+18h], rdx
0x18000e0fd  mov     eax, r13d
0x18000e100  test    eax, eax
0x18000e102  jz      loc_18000E21D
0x18000e108  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18000e10e  xor     edx, edx; lpTlsValue
0x18000e110  call    cs:__imp_TlsSetValue
0x18000e117  nop     dword ptr [rax+rax+00h]
0x18000e11c  mov     rdi, [rbp+0A0h+hdc]
0x18000e120  mov     r14, [rbp+0A0h+pString]
0x18000e124  mov     r15d, [rsp+1A0h+cString]
0x18000e129  mov     r12d, [rsp+1A0h+cGlyphs]
0x18000e12e  mov     eax, cs:g_iUseFontLinking
0x18000e134  cmp     eax, 0FFFFFFFFh
0x18000e137  jnz     short loc_18000E14B
0x18000e139  call    cs:__imp_NtGdiAnyLinkedFonts
0x18000e140  nop     dword ptr [rax+rax+00h]
0x18000e145  mov     cs:g_iUseFontLinking, eax
0x18000e14b  mov     ecx, [rbp+0A0h+arg_28]
0x18000e151  test    eax, eax
0x18000e153  jz      short loc_18000E159
0x18000e155  bts     ecx, 0Ch
0x18000e159  mov     rax, [rbp+0A0h+var_100]
0x18000e15d  mov     r9d, r12d; cGlyphs
0x18000e160  or      dword ptr [rsp+1A0h+psc.uDefaultLanguage], 1800000h
0x18000e168  mov     r8d, r15d; cString
0x18000e16b  mov     [rsp+1A0h+pssa], rax; pssa
0x18000e170  mov     rdx, r14; pString
0x18000e173  mov     rax, [rbp+0A0h+var_F8]
0x18000e177  mov     [rsp+1A0h+pbInClass], rax; pbInClass
0x18000e17c  mov     rax, [rbp+0A0h+arg_58]
0x18000e183  mov     [rsp+1A0h+pTabdef], rax; pTabdef
0x18000e188  mov     rax, [rbp+0A0h+arg_50]
0x18000e18f  mov     [rsp+1A0h+piDx], rax; piDx
0x18000e194  lea     rax, [rsp+1A0h+pss]
0x18000e199  mov     [rsp+1A0h+psState], rax; psState
0x18000e19e  lea     rax, [rsp+1A0h+psc]
0x18000e1a3  mov     [rsp+1A0h+psControl], rax; psControl
0x18000e1a8  mov     eax, [rbp+0A0h+arg_38]
0x18000e1ae  mov     [rsp+1A0h+iReqWidth], eax; iReqWidth
0x18000e1b2  mov     eax, [rbp+0A0h+arg_20]
0x18000e1b8  mov     [rsp+1A0h+dwFlags], ecx; dwFlags
0x18000e1bc  mov     rcx, rdi; hdc
0x18000e1bf  mov     [rsp+1A0h+iCharset], eax; iCharset
0x18000e1c3  call    ScriptStringAnalyse
0x18000e1c8  mov     rcx, [rbp+0A0h+var_50]
0x18000e1cc  xor     rcx, rsp; StackCookie
0x18000e1cf  call    __security_check_cookie
0x18000e1d4  add     rsp, 168h
0x18000e1db  pop     r15
0x18000e1dd  pop     r14
0x18000e1df  pop     r13
0x18000e1e1  pop     r12
0x18000e1e3  pop     rdi
0x18000e1e4  pop     rsi
0x18000e1e5  pop     rbx
0x18000e1e6  pop     rbp
0x18000e1e7  retn
0x18000e1e9  test    eax, eax
0x18000e1eb  jnz     loc_18000E30C
0x18000e1f1  bts     esi, 10h
0x18000e1f5  movzx   eax, cs:g_DigitSubstitute.TraditionalDigitLanguage
0x18000e1fc  or      bx, 100h
0x18000e201  mov     dword ptr [rsp+1A0h+psc.uDefaultLanguage], esi
0x18000e205  mov     word ptr [rsp+1A0h+psc.uDefaultLanguage], ax
0x18000e20a  jmp     loc_18000E030
0x18000e20f  xor     eax, eax
0x18000e211  jmp     loc_18000DE90
0x18000e216  xor     eax, eax
0x18000e218  jmp     loc_18000E100
0x18000e21d  mov     eax, cs:?gAllocatedStaticBufferCount@@3JA; long gAllocatedStaticBufferCount
0x18000e223  lea     r9, __ImageBase
0x18000e22a  mov     r8d, 5
0x18000e230  cmp     eax, r8d
0x18000e233  cmovl   r8w, ax
0x18000e238  xor     edx, edx
0x18000e23a  cmp     dx, r8w
0x18000e23e  jge     short loc_18000E28C
0x18000e240  movsx   rcx, dx
0x18000e244  mov     rax, qword ptr rva ?grStaticBuffers@@3PAPEAXA[r9+rcx*8]; void * near * grStaticBuffers ...
0x18000e24c  test    rax, rax
0x18000e24f  jz      loc_18000E304
0x18000e255  cmp     rax, rbx
0x18000e258  jnz     loc_18000E304
0x18000e25e  xchg    r13d, dword ptr rva ?grStaticBufferFreeFlags@@3PAJA[r9+rcx*4]; long near * grStaticBufferFreeFlags ...
0x18000e266  jmp     loc_18000E108
0x18000e26b  mov     rax, [r8+8]
0x18000e26f  xor     edx, edx
0x18000e271  mov     [r8+10h], rax
0x18000e275  jmp     loc_18000E0F9
0x18000e27a  mov     eax, 8007000Eh
0x18000e27f  jmp     loc_18000DF97
0x18000e284  mov     eax, r13d
0x18000e287  jmp     loc_18000E100
0x18000e28c  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x18000e293  mov     r8, rbx; lpMem
0x18000e296  xor     edx, edx; dwFlags
0x18000e298  call    cs:__imp_HeapFree
0x18000e29f  nop     dword ptr [rax+rax+00h]
0x18000e2a4  test    eax, eax
0x18000e2a6  jnz     loc_18000E108
0x18000e2ac  call    cs:__imp_GetLastError
0x18000e2b3  nop     dword ptr [rax+rax+00h]
0x18000e2b8  jmp     loc_18000E108
0x18000e2bd  inc     r14w
0x18000e2c1  jmp     loc_18000DEF4
0x18000e2c6  cmp     cs:?gfMemoryInitFailed@@3HA, 0; int gfMemoryInitFailed
0x18000e2cd  jnz     loc_18000E108
  ... truncated ...
```
