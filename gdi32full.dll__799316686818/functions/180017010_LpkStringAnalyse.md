# LpkStringAnalyse

- ea: `0x180017010`
- end: `0x180017600`
- name: `LpkStringAnalyse`
- size: `1520`
- prototype: `__int64 __fastcall(int, int, int, int, int, DWORD, int, int, __int64, __int64, int *, SCRIPT_TABDEF *, __int64, __int64)`
- caller_count: `10`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f270`
- `0x18000f6f0`
- `0x180015dc0`
- `0x18002e380`
- `0x1800374c0`
- `0x180053610`
- `0x18005e24c`
- `0x1800607dc`
- `0x180076c30`
- `0x18009f800`

## callees

- `0x1800055d0`
- `0x180009d00`
- `0x18000a090`
- `0x18000db8c`
- `0x180011050`
- `0x180016750`
- `0x1800169c0`
- `0x180017010`
- `0x180017770`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800170ae`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800170ae`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800170ce`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800170ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001712d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001728f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800172be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001712d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001728f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800172be`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180017234`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180017350`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180017234`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180017350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800174cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800174cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800171d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800171d5`
- `win32u!NtGdiAnyLinkedFonts` at `0x180017373`
- `win32u!NtGdiAnyLinkedFonts` at `0x180017373`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180017094`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180017094`

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
0x180017010  push    rbp
0x180017012  push    rbx
0x180017013  push    rsi
0x180017014  push    rdi
0x180017015  push    r12
0x180017017  push    r13
0x180017019  push    r14
0x18001701b  push    r15
0x18001701d  lea     rbp, [rsp-68h]
0x180017022  sub     rsp, 168h
0x180017029  mov     rax, cs:__security_cookie
0x180017030  xor     rax, rsp
0x180017033  mov     [rbp+0A0h+var_50], rax
0x180017037  mov     rax, [rbp+0A0h+arg_60]
0x18001703e  mov     r12d, r9d
0x180017041  mov     rsi, [rbp+0A0h+arg_40]
0x180017048  mov     r15d, r8d
0x18001704b  mov     rbx, [rbp+0A0h+arg_48]
0x180017052  mov     r14, rdx
0x180017055  mov     [rbp+0A0h+var_F8], rax
0x180017059  mov     rdi, rcx
0x18001705c  mov     rax, [rbp+0A0h+arg_68]
0x180017063  mov     [rbp+0A0h+var_100], rax
0x180017067  mov     [rsp+1A0h+cGlyphs], r9d
0x18001706c  mov     [rsp+1A0h+cString], r8d
0x180017071  mov     [rbp+0A0h+pString], rdx
0x180017075  mov     [rbp+0A0h+hdc], rcx
0x180017079  test    rsi, rsi
0x18001707c  jnz     loc_180017556
0x180017082  mov     dword ptr [rsp+1A0h+psc.uDefaultLanguage], esi
0x180017086  test    rbx, rbx
0x180017089  jnz     loc_18001755D
0x18001708f  mov     word ptr [rsp+1A0h+pss.uBidiLevel], bx
0x180017094  call    cs:__imp_NlsGetCacheUpdateCount
0x18001709a  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x1800170a0  mov     r13d, 1
0x1800170a6  jz      short loc_180017105
0x1800170a8  mov     cs:g_ulNlsUpdateCacheCount, eax
0x1800170ae  call    cs:__imp_GetUserDefaultLCID
0x1800170b4  mov     r9d, 50h ; 'P'; cchData
0x1800170ba  lea     r8, [rbp+0A0h+LCData]; lpLCData
0x1800170be  mov     edx, 58h ; 'X'; LCType
0x1800170c3  mov     cs:g_UserLocale, eax
0x1800170c9  mov     ecx, 400h; Locale
0x1800170ce  call    cs:__imp_GetLocaleInfoW
0x1800170d4  test    eax, eax
0x1800170d6  jz      loc_180017442
0x1800170dc  mov     eax, 800h
0x1800170e1  test    [rbp+0A0h+var_E2], ax
0x1800170e5  jz      loc_180017442
0x1800170eb  mov     eax, r13d
0x1800170ee  lea     rdx, g_DigitSubstitute; psds
0x1800170f5  mov     cs:g_UserBidiLocale, eax
0x1800170fb  mov     ecx, 400h; Locale
0x180017100  call    ScriptRecordDigitSubstitution
0x180017105  mov     ecx, [rbp+0A0h+arg_30]
0x18001710b  test    ecx, ecx
0x18001710d  jns     loc_180017589
0x180017113  cmp     cs:?gdwTlsIndex@@3KA, 0FFFFFFFFh; ulong gdwTlsIndex
0x18001711a  lea     rdi, __ImageBase
0x180017121  jz      loc_18001724B
0x180017127  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18001712d  call    cs:__imp_TlsGetValue
0x180017133  test    rax, rax
0x180017136  jnz     loc_18001724B
0x18001713c  cmp     cs:?ghHeap@@3PEAXEA, rax; void * ghHeap
0x180017143  jz      loc_18001750C
0x180017149  xor     r14d, r14d
0x18001714c  cmp     r14w, 5
0x180017151  jge     short loc_1800171B7
0x180017153  xor     eax, eax
0x180017155  movsx   rcx, r14w
0x180017159  lea     r15, rva ?grStaticBufferFreeFlags@@3PAJA[rdi]; long near * grStaticBufferFreeFlags ...
0x180017160  xchg    eax, [r15+rcx*4]
0x180017164  lea     r15, [r15+rcx*4]
0x180017168  cmp     eax, r13d
0x18001716b  jnz     loc_1800174E4
0x180017171  lea     r12, rva ?grStaticBuffers@@3PAPEAXA[rdi]; void * near * grStaticBuffers ...
0x180017178  mov     rdi, [r12+rcx*8]
0x18001717c  lea     r12, [r12+rcx*8]
0x180017180  test    rdi, rdi
0x180017183  jnz     short loc_1800171F6
0x180017185  mov     rdx, r12
0x180017188  mov     ecx, 4000h
0x18001718d  call    UspAllocCache
0x180017192  test    eax, eax
0x180017194  js      loc_180017581
0x18001719a  mov     rdi, [r12]
0x18001719e  mov     edx, cs:?gAllocatedStaticBufferCount@@3JA; long gAllocatedStaticBufferCount
0x1800171a4  movsx   ecx, r14w
0x1800171a8  inc     ecx
0x1800171aa  cmp     edx, ecx
0x1800171ac  jl      loc_1800175D7
0x1800171b2  test    rdi, rdi
0x1800171b5  jnz     short loc_1800171F6
0x1800171b7  xor     edi, edi
0x1800171b9  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x1800171be  test    eax, eax
0x1800171c0  jz      loc_1800174AD
0x1800171c6  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x1800171cd  xor     edx, edx; dwFlags
0x1800171cf  mov     r8d, 4000h; dwBytes
0x1800171d5  call    cs:__imp_HeapAlloc
0x1800171db  mov     rdi, rax
0x1800171de  test    rax, rax
0x1800171e1  jz      loc_1800175F4
0x1800171e7  xor     eax, eax
0x1800171e9  test    eax, eax
0x1800171eb  js      short loc_18001724B
0x1800171ed  test    rdi, rdi
0x1800171f0  jz      loc_1800175CC
0x1800171f6  lea     r14, [rdi+28h]
0x1800171fa  mov     dword ptr [rdi], 0
0x180017200  mov     qword ptr [rdi+8], 0
0x180017208  mov     qword ptr [rdi+10h], 0
0x180017210  mov     qword ptr [rdi+18h], 0
0x180017218  test    r14, r14
0x18001721b  jz      short loc_180017243
0x18001721d  mov     rdx, rdi; lpTlsValue
0x180017220  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x180017226  mov     dword ptr [rdx], 3FD8h
0x18001722c  mov     [rdx+8], r14
0x180017230  mov     [rdx+10h], r14
0x180017234  call    cs:__imp_TlsSetValue
0x18001723a  test    eax, eax
0x18001723c  jz      short loc_180017243
0x18001723e  mov     ecx, r13d
0x180017241  jmp     short loc_18001724D
0x180017243  mov     rcx, r14; lpMem
0x180017246  call    UspFreeMem
0x18001724b  xor     ecx, ecx
0x18001724d  movzx   eax, cs:g_DigitSubstitute.DigitSubstitute
0x180017254  mov     [rbp+0A0h+var_120], ecx
0x180017257  cmp     eax, r13d
0x18001725a  jnz     loc_18001741C
0x180017260  movzx   eax, cs:g_DigitSubstitute.NationalDigitLanguage
0x180017267  btr     esi, 10h
0x18001726b  mov     dword ptr [rsp+1A0h+psc.uDefaultLanguage], esi
0x18001726f  mov     word ptr [rsp+1A0h+psc.uDefaultLanguage], ax
0x180017274  mov     eax, 0FEFFh
0x180017279  and     bx, ax
0x18001727c  mov     word ptr [rsp+1A0h+pss.uBidiLevel], bx
0x180017281  test    ecx, ecx
0x180017283  jz      loc_180017356
0x180017289  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18001728f  call    cs:__imp_TlsGetValue
0x180017295  mov     rbx, rax
0x180017298  test    rax, rax
0x18001729b  jz      loc_180017356
0x1800172a1  cmp     cs:?ghHeap@@3PEAXEA, 0; void * ghHeap
0x1800172a9  jz      loc_1800174ED
0x1800172af  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x1800172b5  cmp     ecx, 0FFFFFFFFh
0x1800172b8  jz      loc_180017450
0x1800172be  call    cs:__imp_TlsGetValue
0x1800172c4  mov     r8, rax
0x1800172c7  test    rax, rax
0x1800172ca  jz      loc_180017450
0x1800172d0  mov     rcx, [rax+8]
0x1800172d4  test    rcx, rcx
0x1800172d7  jz      loc_180017449
0x1800172dd  add     rcx, 10h
0x1800172e1  cmp     rbx, rcx
0x1800172e4  jb      loc_180017449
0x1800172ea  cmp     rbx, [rax+10h]
0x1800172ee  jnb     loc_180017449
0x1800172f4  mov     ecx, [rbx-0Ch]
0x1800172f7  lea     rdx, [rbx-10h]
0x1800172fb  test    r13b, cl
0x1800172fe  jnz     loc_1800174B7
0x180017304  mov     rax, [rax+18h]
0x180017308  or      ecx, r13d
0x18001730b  mov     [rdx+4], ecx
0x18001730e  cmp     rdx, rax
0x180017311  jnz     loc_1800174B7
0x180017317  mov     eax, [rdx+0Ch]
0x18001731a  test    eax, eax
0x18001731c  jz      loc_18001749E
0x180017322  mov     [r8+10h], rdx
0x180017326  mov     rcx, 0FFFFFFFFFFFFFFF0h
0x18001732d  sub     rcx, rax
0x180017330  add     rdx, rcx
0x180017333  test    [rdx+4], r13b
0x180017337  jnz     short loc_180017317
0x180017339  mov     [r8+18h], rdx
0x18001733d  mov     eax, r13d
0x180017340  test    eax, eax
0x180017342  jz      loc_180017450
0x180017348  mov     ecx, cs:?gdwTlsIndex@@3KA; dwTlsIndex
0x18001734e  xor     edx, edx; lpTlsValue
0x180017350  call    cs:__imp_TlsSetValue
0x180017356  mov     rdi, [rbp+0A0h+hdc]
0x18001735a  mov     r14, [rbp+0A0h+pString]
0x18001735e  mov     r15d, [rsp+1A0h+cString]
0x180017363  mov     r12d, [rsp+1A0h+cGlyphs]
0x180017368  mov     eax, cs:g_iUseFontLinking
0x18001736e  cmp     eax, 0FFFFFFFFh
0x180017371  jnz     short loc_18001737F
0x180017373  call    cs:__imp_NtGdiAnyLinkedFonts
0x180017379  mov     cs:g_iUseFontLinking, eax
0x18001737f  mov     ecx, [rbp+0A0h+arg_28]
0x180017385  test    eax, eax
0x180017387  jz      short loc_18001738D
0x180017389  bts     ecx, 0Ch
0x18001738d  mov     rax, [rbp+0A0h+var_100]
0x180017391  mov     r9d, r12d; cGlyphs
0x180017394  or      dword ptr [rsp+1A0h+psc.uDefaultLanguage], 1800000h
0x18001739c  mov     r8d, r15d; cString
0x18001739f  mov     [rsp+1A0h+pssa], rax; pssa
0x1800173a4  mov     rdx, r14; pString
0x1800173a7  mov     rax, [rbp+0A0h+var_F8]
0x1800173ab  mov     [rsp+1A0h+pbInClass], rax; pbInClass
0x1800173b0  mov     rax, [rbp+0A0h+arg_58]
0x1800173b7  mov     [rsp+1A0h+pTabdef], rax; pTabdef
0x1800173bc  mov     rax, [rbp+0A0h+arg_50]
0x1800173c3  mov     [rsp+1A0h+piDx], rax; piDx
0x1800173c8  lea     rax, [rsp+1A0h+pss]
0x1800173cd  mov     [rsp+1A0h+psState], rax; psState
0x1800173d2  lea     rax, [rsp+1A0h+psc]
0x1800173d7  mov     [rsp+1A0h+psControl], rax; psControl
0x1800173dc  mov     eax, [rbp+0A0h+arg_38]
0x1800173e2  mov     [rsp+1A0h+iReqWidth], eax; iReqWidth
0x1800173e6  mov     eax, [rbp+0A0h+arg_20]
0x1800173ec  mov     [rsp+1A0h+dwFlags], ecx; dwFlags
0x1800173f0  mov     rcx, rdi; hdc
0x1800173f3  mov     [rsp+1A0h+iCharset], eax; iCharset
0x1800173f7  call    ScriptStringAnalyse
0x1800173fc  mov     rcx, [rbp+0A0h+var_50]
0x180017400  xor     rcx, rsp; StackCookie
0x180017403  call    __security_check_cookie
0x180017408  add     rsp, 168h
0x18001740f  pop     r15
0x180017411  pop     r14
0x180017413  pop     r13
0x180017415  pop     r12
0x180017417  pop     rdi
0x180017418  pop     rsi
0x180017419  pop     rbx
0x18001741a  pop     rbp
0x18001741b  retn
0x18001741c  test    eax, eax
0x18001741e  jnz     loc_180017533
0x180017424  bts     esi, 10h
0x180017428  movzx   eax, cs:g_DigitSubstitute.TraditionalDigitLanguage
0x18001742f  or      bx, 100h
0x180017434  mov     dword ptr [rsp+1A0h+psc.uDefaultLanguage], esi
0x180017438  mov     word ptr [rsp+1A0h+psc.uDefaultLanguage], ax
0x18001743d  jmp     loc_18001727C
0x180017442  xor     eax, eax
0x180017444  jmp     loc_1800170EE
0x180017449  xor     eax, eax
0x18001744b  jmp     loc_180017340
0x180017450  mov     eax, cs:?gAllocatedStaticBufferCount@@3JA; long gAllocatedStaticBufferCount
0x180017456  lea     r9, __ImageBase
0x18001745d  mov     r8d, 5
0x180017463  cmp     eax, r8d
0x180017466  cmovl   r8w, ax
0x18001746b  xor     edx, edx
0x18001746d  cmp     dx, r8w
0x180017471  jge     short loc_1800174BF
0x180017473  movsx   rcx, dx
0x180017477  mov     rax, qword ptr rva ?grStaticBuffers@@3PAPEAXA[r9+rcx*8]; void * near * grStaticBuffers ...
0x18001747f  test    rax, rax
0x180017482  jz      loc_18001752B
0x180017488  cmp     rax, rbx
0x18001748b  jnz     loc_18001752B
0x180017491  xchg    r13d, dword ptr rva ?grStaticBufferFreeFlags@@3PAJA[r9+rcx*4]; long near * grStaticBufferFreeFlags ...
0x180017499  jmp     loc_180017348
0x18001749e  mov     rax, [r8+8]
0x1800174a2  xor     edx, edx
0x1800174a4  mov     [r8+10h], rax
0x1800174a8  jmp     loc_180017339
0x1800174ad  mov     eax, 8007000Eh
0x1800174b2  jmp     loc_1800171E9
0x1800174b7  mov     eax, r13d
0x1800174ba  jmp     loc_180017340
0x1800174bf  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x1800174c6  mov     r8, rbx; lpMem
0x1800174c9  xor     edx, edx; dwFlags
0x1800174cb  call    cs:__imp_HeapFree
0x1800174d1  test    eax, eax
0x1800174d3  jnz     loc_180017348
0x1800174d9  call    cs:__imp_GetLastError
0x1800174df  jmp     loc_180017348
0x1800174e4  inc     r14w
0x1800174e8  jmp     loc_18001714C
0x1800174ed  cmp     cs:?gfMemoryInitFailed@@3HA, 0; int gfMemoryInitFailed
0x1800174f4  jnz     loc_180017348
0x1800174fa  call    ?UspInitMemory@@YAHXZ; UspInitMemory(void)
0x1800174ff  test    eax, eax
0x180017501  jnz     loc_1800172AF
0x180017507  jmp     loc_180017348
0x18001750c  cmp     cs:?gfMemoryInitFailed@@3HA, 0; int gfMemoryInitFailed
0x180017513  jnz     loc_1800171B7
0x180017519  call    ?UspInitMemory@@YAHXZ; UspInitMemory(void)
0x18001751e  test    eax, eax
0x180017520  jnz     loc_180017149
0x180017526  jmp     loc_1800171B7
0x18001752b  inc     dx
0x18001752e  jmp     loc_18001746D
  ... truncated ...
```
