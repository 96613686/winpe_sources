# ParseCompareCmdLine

- ea: `0x140008fe8`
- end: `0x140009499`
- name: `ParseCompareCmdLine`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140008788`

## callees

- `0x140001e90`
- `0x140001fec`
- `0x140002234`
- `0x140002b70`
- `0x140008dfc`
- `0x140008fe8`
- `0x14000c62c`
- `0x14000cd48`
- `0x14000d010`
- `0x14000daa4`
- `0x14000e228`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140009428`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140009428`

## string_xrefs

- `0x1400093f4`: `COMPARE`
- `0x140009082`: `COMPARE`

## pseudocode

```c
__int64 __fastcall ParseCompareCmdLine(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // eax
  const WCHAR *v13; // rcx
  __int64 v14; // r14
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  LPVOID Memory; // rax
  __int64 v20; // rcx
  __int64 ResString2FromModule; // rax
  const WCHAR *v22; // rcx
  int v23; // eax
  unsigned int v24; // r15d
  _WORD *v25; // rax
  __int64 v26; // rcx

  if ( !a1 || !a2 || !a3 || !a4 || !a5 || *(_DWORD *)a3 > 0xBu )
    goto LABEL_75;
  if ( a1 == 3 )
  {
    if ( (unsigned int)InString(*(LPCWSTR *)(a2 + 16), L"/?|-?|/h|-h") == 1 )
    {
      *a5 = 1;
      return 1;
    }
    goto LABEL_62;
  }
  if ( a1 - 4 > 5 )
  {
LABEL_62:
    SetLastError(0x800401E4);
    ResString2FromModule = GetResString2FromModule(v20, 103, 0);
    SetReason2(1, ResString2FromModule, L"COMPARE");
    return 0;
  }
  if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8), L"COMPARE", a3, 0) )
  {
LABEL_75:
    v26 = 87;
LABEL_76:
    SaveErrorMessage(v26);
    return 0;
  }
  if ( (unsigned int)BreakDownKeyString(*(_QWORD *)(a2 + 16), a3) )
  {
    if ( (unsigned int)BreakDownKeyString(*(_QWORD *)(a2 + 24), a4) )
      goto LABEL_21;
    if ( GetLastError() == -2147221166 )
    {
      v12 = CopyKeyNameFromLeftToRight(a3, a4);
    }
    else
    {
      v13 = *(const WCHAR **)(a4 + 72);
      if ( !v13 || (unsigned int)StringCompareExW(v13, L"\\\\.", v11, 0) )
        return 0;
      FreeGlobalData(a4);
      InitGlobalData(8, a4);
      v12 = BreakDownKeyString(*(_QWORD *)(a3 + 88), a4);
    }
    if ( v12 )
    {
LABEL_21:
      LODWORD(v14) = 4;
      if ( a1 > 4 )
      {
        do
        {
          if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/v", v10, 0)
            && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-v", v15, 0) )
          {
            if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/ve", v16, 0)
              && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-ve", v17, 0) )
            {
              if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/oa", v18, 0)
                && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-oa", v10, 0) )
              {
                if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/od", v10, 0)
                  && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-od", v10, 0) )
                {
                  if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/os", v10, 0)
                    && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-os", v10, 0) )
                  {
                    if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/on", v10, 0)
                      && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-on", v10, 0) )
                    {
                      if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/s", v10, 0)
                        && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-s", v10, 0) )
                      {
                        if ( (unsigned int)StringCompareExW(
                                             *(PCNZWCH *)(a2 + 8LL * (unsigned int)v14),
                                             L"/reg:32",
                                             v10,
                                             0)
                          && (unsigned int)StringCompareExW(
                                             *(PCNZWCH *)(a2 + 8LL * (unsigned int)v14),
                                             L"-reg:32",
                                             v10,
                                             0) )
                        {
                          if ( (unsigned int)StringCompareExW(
                                               *(PCNZWCH *)(a2 + 8LL * (unsigned int)v14),
                                               L"/reg:64",
                                               v10,
                                               0)
                            && (unsigned int)StringCompareExW(
                                               *(PCNZWCH *)(a2 + 8LL * (unsigned int)v14),
                                               L"-reg:64",
                                               v10,
                                               0)
                            || *(_DWORD *)(a3 + 140) )
                          {
                            goto LABEL_62;
                          }
                          *(_DWORD *)(a3 + 140) = 256;
                        }
                        else
                        {
                          if ( *(_DWORD *)(a3 + 140) )
                            goto LABEL_62;
                          *(_DWORD *)(a3 + 140) = 512;
                        }
                      }
                      else
                      {
                        if ( *(_QWORD *)(a3 + 96) || *(_DWORD *)(a3 + 32) == 1 )
                          goto LABEL_62;
                        *(_DWORD *)(a3 + 32) = 1;
                      }
                    }
                    else
                    {
                      if ( *(_QWORD *)(a3 + 96) || *(_DWORD *)(a3 + 52) )
                        goto LABEL_62;
                      *(_DWORD *)(a3 + 52) = 1;
                    }
                  }
                  else
                  {
                    if ( *(_QWORD *)(a3 + 96) || *(_DWORD *)(a3 + 52) )
                      goto LABEL_62;
                    *(_DWORD *)(a3 + 52) = 2;
                  }
                }
                else
                {
                  if ( *(_QWORD *)(a3 + 96) || *(_DWORD *)(a3 + 52) )
                    goto LABEL_62;
                  *(_DWORD *)(a3 + 52) = 3;
                }
              }
              else
              {
                if ( *(_QWORD *)(a3 + 96) || *(_DWORD *)(a3 + 52) )
                  goto LABEL_62;
                *(_DWORD *)(a3 + 52) = 4;
              }
            }
            else
            {
              if ( *(_QWORD *)(a3 + 96) )
                goto LABEL_62;
              if ( *(_DWORD *)(a3 + 32) == 1 )
                goto LABEL_62;
              Memory = AllocateMemory(4u);
              *(_QWORD *)(a3 + 96) = Memory;
              if ( !Memory )
                goto LABEL_62;
            }
          }
          else
          {
            if ( *(_QWORD *)(a3 + 96) )
              goto LABEL_62;
            if ( *(_DWORD *)(a3 + 32) == 1 )
              goto LABEL_62;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= a1 )
              goto LABEL_62;
            v22 = *(const WCHAR **)(a2 + 8 * v14);
            if ( v22 )
              v23 = lstrlenW(v22);
            else
              v23 = 0;
            v24 = v23 + 1;
            v25 = AllocateMemory((unsigned int)(2 * (v23 + 1)));
            *(_QWORD *)(a3 + 96) = v25;
            if ( !v25 )
            {
              v26 = 14;
              goto LABEL_76;
            }
            StringCopyW(v25, *(_WORD **)(a2 + 8 * v14), v24);
          }
          LODWORD(v14) = v14 + 1;
        }
        while ( (unsigned int)v14 < a1 );
      }
      if ( !*(_DWORD *)(a3 + 52) )
        *(_DWORD *)(a3 + 52) = 3;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008fe8  push    rbx
0x140008fea  push    rbp
0x140008feb  push    rsi
0x140008fec  push    rdi
0x140008fed  push    r12
0x140008fef  push    r13
0x140008ff1  push    r14
0x140008ff3  push    r15
0x140008ff5  sub     rsp, 28h
0x140008ff9  xor     r12d, r12d
0x140008ffc  mov     rbp, r9
0x140008fff  mov     rbx, r8
0x140009002  mov     rsi, rdx
0x140009005  mov     r13d, ecx
0x140009008  test    ecx, ecx
0x14000900a  jz      loc_14000947C
0x140009010  test    rdx, rdx
0x140009013  jz      loc_14000947C
0x140009019  test    rbx, rbx
0x14000901c  jz      loc_14000947C
0x140009022  test    r9, r9
0x140009025  jz      loc_14000947C
0x14000902b  mov     r14, [rsp+68h+arg_20]
0x140009033  test    r14, r14
0x140009036  jz      loc_14000947C
0x14000903c  cmp     dword ptr [r8], 0Bh
0x140009040  ja      loc_14000947C
0x140009046  lea     edi, [r12+1]
0x14000904b  cmp     ecx, 3
0x14000904e  jnz     short loc_140009072
0x140009050  mov     rcx, [rsi+10h]; lpString
0x140009054  lea     rdx, aHH_0; "/?|-?|/h|-h"
0x14000905b  call    InString
0x140009060  cmp     eax, edi
0x140009062  jnz     loc_1400093DD
0x140009068  mov     [r14], edi
0x14000906b  mov     eax, edi
0x14000906d  jmp     loc_140009488
0x140009072  lea     eax, [rcx-4]
0x140009075  cmp     eax, 5
0x140009078  ja      loc_1400093DD
0x14000907e  mov     rcx, [rsi+8]; lpString1
0x140009082  lea     rdx, aCompare; "COMPARE"
0x140009089  xor     r9d, r9d
0x14000908c  call    StringCompareExW
0x140009091  test    eax, eax
0x140009093  jnz     loc_14000947C
0x140009099  mov     rcx, [rsi+10h]
0x14000909d  mov     rdx, rbx
0x1400090a0  call    BreakDownKeyString
0x1400090a5  test    eax, eax
0x1400090a7  jz      loc_140009486
0x1400090ad  mov     rcx, [rsi+18h]
0x1400090b1  mov     rdx, rbp
0x1400090b4  call    BreakDownKeyString
0x1400090b9  test    eax, eax
0x1400090bb  jnz     short loc_140009124
0x1400090bd  call    cs:__imp_GetLastError
0x1400090c3  cmp     eax, 80040152h
0x1400090c8  jnz     short loc_1400090D7
0x1400090ca  mov     rdx, rbp
0x1400090cd  mov     rcx, rbx
0x1400090d0  call    CopyKeyNameFromLeftToRight
0x1400090d5  jmp     short loc_14000911C
0x1400090d7  mov     rcx, [rbp+48h]; lpString1
0x1400090db  test    rcx, rcx
0x1400090de  jz      loc_140009486
0x1400090e4  xor     r9d, r9d
0x1400090e7  lea     rdx, asc_140010848; "\\\\."
0x1400090ee  call    StringCompareExW
0x1400090f3  test    eax, eax
0x1400090f5  jnz     loc_140009486
0x1400090fb  mov     rcx, rbp
0x1400090fe  call    FreeGlobalData
0x140009103  mov     rdx, rbp
0x140009106  mov     ecx, 8
0x14000910b  call    InitGlobalData
0x140009110  mov     rcx, [rbx+58h]
0x140009114  mov     rdx, rbp
0x140009117  call    BreakDownKeyString
0x14000911c  test    eax, eax
0x14000911e  jz      loc_140009486
0x140009124  mov     r14d, 4
0x14000912a  cmp     r13d, r14d
0x14000912d  jbe     loc_14000945F
0x140009133  mov     ebp, r14d
0x140009136  lea     rdx, aV_0; "/v"
0x14000913d  xor     r9d, r9d
0x140009140  mov     rcx, [rsi+rbp*8]; lpString1
0x140009144  call    StringCompareExW
0x140009149  test    eax, eax
0x14000914b  jz      loc_140009407
0x140009151  mov     rcx, [rsi+rbp*8]; lpString1
0x140009155  lea     rdx, aV; "-v"
0x14000915c  xor     r9d, r9d
0x14000915f  call    StringCompareExW
0x140009164  test    eax, eax
0x140009166  jz      loc_140009407
0x14000916c  mov     rcx, [rsi+rbp*8]; lpString1
0x140009170  lea     rdx, aVe_0; "/ve"
0x140009177  xor     r9d, r9d
0x14000917a  call    StringCompareExW
0x14000917f  test    eax, eax
0x140009181  jz      loc_1400093BF
0x140009187  mov     rcx, [rsi+rbp*8]; lpString1
0x14000918b  lea     rdx, aVe; "-ve"
0x140009192  xor     r9d, r9d
0x140009195  call    StringCompareExW
0x14000919a  test    eax, eax
0x14000919c  jz      loc_1400093BF
0x1400091a2  mov     rcx, [rsi+rbp*8]; lpString1
0x1400091a6  lea     rdx, aOa; "/oa"
0x1400091ad  xor     r9d, r9d
0x1400091b0  call    StringCompareExW
0x1400091b5  test    eax, eax
0x1400091b7  jz      loc_1400093A7
0x1400091bd  mov     rcx, [rsi+rbp*8]; lpString1
0x1400091c1  lea     rdx, aOa_0; "-oa"
0x1400091c8  xor     r9d, r9d
0x1400091cb  call    StringCompareExW
0x1400091d0  test    eax, eax
0x1400091d2  jz      loc_1400093A7
0x1400091d8  mov     rcx, [rsi+rbp*8]; lpString1
0x1400091dc  lea     rdx, aOd_0; "/od"
0x1400091e3  xor     r9d, r9d
0x1400091e6  call    StringCompareExW
0x1400091eb  test    eax, eax
0x1400091ed  jz      loc_14000938F
0x1400091f3  mov     rcx, [rsi+rbp*8]; lpString1
0x1400091f7  lea     rdx, aOd; "-od"
0x1400091fe  xor     r9d, r9d
0x140009201  call    StringCompareExW
0x140009206  test    eax, eax
0x140009208  jz      loc_14000938F
0x14000920e  mov     rcx, [rsi+rbp*8]; lpString1
0x140009212  lea     rdx, aOs; "/os"
0x140009219  xor     r9d, r9d
0x14000921c  call    StringCompareExW
0x140009221  test    eax, eax
0x140009223  jz      loc_140009377
0x140009229  mov     rcx, [rsi+rbp*8]; lpString1
0x14000922d  lea     rdx, aOs_0; "-os"
0x140009234  xor     r9d, r9d
0x140009237  call    StringCompareExW
0x14000923c  test    eax, eax
0x14000923e  jz      loc_140009377
0x140009244  mov     rcx, [rsi+rbp*8]; lpString1
0x140009248  lea     rdx, aOn_0; "/on"
0x14000924f  xor     r9d, r9d
0x140009252  call    StringCompareExW
0x140009257  test    eax, eax
0x140009259  jz      loc_140009363
0x14000925f  mov     rcx, [rsi+rbp*8]; lpString1
0x140009263  lea     rdx, aOn; "-on"
0x14000926a  xor     r9d, r9d
0x14000926d  call    StringCompareExW
0x140009272  test    eax, eax
0x140009274  jz      loc_140009363
0x14000927a  mov     rcx, [rsi+rbp*8]; lpString1
0x14000927e  lea     rdx, aS_4; "/s"
0x140009285  xor     r9d, r9d
0x140009288  call    StringCompareExW
0x14000928d  test    eax, eax
0x14000928f  jz      loc_140009348
0x140009295  mov     rcx, [rsi+rbp*8]; lpString1
0x140009299  lea     rdx, aS_3; "-s"
0x1400092a0  xor     r9d, r9d
0x1400092a3  call    StringCompareExW
0x1400092a8  test    eax, eax
0x1400092aa  jz      loc_140009348
0x1400092b0  mov     rcx, [rsi+rbp*8]; lpString1
0x1400092b4  lea     rdx, aReg32; "/reg:32"
0x1400092bb  xor     r9d, r9d
0x1400092be  call    StringCompareExW
0x1400092c3  test    eax, eax
0x1400092c5  jz      short loc_14000932C
0x1400092c7  mov     rcx, [rsi+rbp*8]; lpString1
0x1400092cb  lea     rdx, aReg32_0; "-reg:32"
0x1400092d2  xor     r9d, r9d
0x1400092d5  call    StringCompareExW
0x1400092da  test    eax, eax
0x1400092dc  jz      short loc_14000932C
0x1400092de  mov     rcx, [rsi+rbp*8]; lpString1
0x1400092e2  lea     rdx, aReg64_0; "/reg:64"
0x1400092e9  xor     r9d, r9d
0x1400092ec  call    StringCompareExW
0x1400092f1  test    eax, eax
0x1400092f3  jz      short loc_140009310
0x1400092f5  mov     rcx, [rsi+rbp*8]; lpString1
0x1400092f9  lea     rdx, aReg64; "-reg:64"
0x140009300  xor     r9d, r9d
0x140009303  call    StringCompareExW
0x140009308  test    eax, eax
0x14000930a  jnz     loc_1400093DD
0x140009310  cmp     [rbx+8Ch], r12d
0x140009317  jnz     loc_1400093DD
0x14000931d  mov     dword ptr [rbx+8Ch], 100h
0x140009327  jmp     loc_140009453
0x14000932c  cmp     [rbx+8Ch], r12d
0x140009333  jnz     loc_1400093DD
0x140009339  mov     dword ptr [rbx+8Ch], 200h
0x140009343  jmp     loc_140009453
0x140009348  cmp     [rbx+60h], r12
0x14000934c  jnz     loc_1400093DD
0x140009352  cmp     [rbx+20h], edi
0x140009355  jz      loc_1400093DD
0x14000935b  mov     [rbx+20h], edi
0x14000935e  jmp     loc_140009453
0x140009363  cmp     [rbx+60h], r12
0x140009367  jnz     short loc_1400093DD
0x140009369  cmp     [rbx+34h], r12d
0x14000936d  jnz     short loc_1400093DD
0x14000936f  mov     [rbx+34h], edi
0x140009372  jmp     loc_140009453
0x140009377  cmp     [rbx+60h], r12
0x14000937b  jnz     short loc_1400093DD
0x14000937d  cmp     [rbx+34h], r12d
0x140009381  jnz     short loc_1400093DD
0x140009383  mov     dword ptr [rbx+34h], 2
0x14000938a  jmp     loc_140009453
0x14000938f  cmp     [rbx+60h], r12
0x140009393  jnz     short loc_1400093DD
0x140009395  cmp     [rbx+34h], r12d
0x140009399  jnz     short loc_1400093DD
0x14000939b  mov     dword ptr [rbx+34h], 3
0x1400093a2  jmp     loc_140009453
0x1400093a7  cmp     [rbx+60h], r12
0x1400093ab  jnz     short loc_1400093DD
0x1400093ad  cmp     [rbx+34h], r12d
0x1400093b1  jnz     short loc_1400093DD
0x1400093b3  mov     dword ptr [rbx+34h], 4
0x1400093ba  jmp     loc_140009453
0x1400093bf  cmp     [rbx+60h], r12
0x1400093c3  jnz     short loc_1400093DD
0x1400093c5  cmp     [rbx+20h], edi
0x1400093c8  jz      short loc_1400093DD
0x1400093ca  mov     ecx, 4; dwBytes
0x1400093cf  call    AllocateMemory
0x1400093d4  mov     [rbx+60h], rax
0x1400093d8  test    rax, rax
0x1400093db  jnz     short loc_140009453
0x1400093dd  mov     ecx, 800401E4h; dwErrCode
0x1400093e2  call    cs:__imp_SetLastError
0x1400093e8  xor     r8d, r8d
0x1400093eb  lea     edx, [r8+67h]
0x1400093ef  call    GetResString2FromModule
0x1400093f4  lea     r8, aCompare_0; "COMPARE"
0x1400093fb  mov     rdx, rax
0x1400093fe  mov     ecx, edi
0x140009400  call    SetReason2
0x140009405  jmp     short loc_140009486
0x140009407  cmp     [rbx+60h], r12
0x14000940b  jnz     short loc_1400093DD
0x14000940d  cmp     [rbx+20h], edi
0x140009410  jz      short loc_1400093DD
0x140009412  inc     r14d
0x140009415  cmp     r14d, r13d
0x140009418  jnb     short loc_1400093DD
0x14000941a  mov     rcx, [rsi+r14*8]; lpString
0x14000941e  test    rcx, rcx
0x140009421  jnz     short loc_140009428
0x140009423  mov     eax, r12d
0x140009426  jmp     short loc_14000942E
0x140009428  call    cs:__imp_lstrlenW
0x14000942e  lea     r15d, [rax+1]
0x140009432  lea     ecx, [r15+r15]; dwBytes
0x140009436  call    AllocateMemory
0x14000943b  mov     [rbx+60h], rax
0x14000943f  test    rax, rax
0x140009442  jz      short loc_140009475
0x140009444  mov     rdx, [rsi+r14*8]
0x140009448  mov     r8d, r15d
0x14000944b  mov     rcx, rax
0x14000944e  call    StringCopyW
0x140009453  add     r14d, edi
0x140009456  cmp     r14d, r13d
0x140009459  jb      loc_140009133
0x14000945f  cmp     [rbx+34h], r12d
0x140009463  jnz     loc_14000906B
0x140009469  mov     dword ptr [rbx+34h], 3
0x140009470  jmp     loc_14000906B
0x140009475  mov     ecx, 0Eh
0x14000947a  jmp     short loc_140009481
0x14000947c  mov     ecx, 57h ; 'W'
0x140009481  call    SaveErrorMessage
0x140009486  xor     eax, eax
0x140009488  add     rsp, 28h
0x14000948c  pop     r15
0x14000948e  pop     r14
0x140009490  pop     r13
0x140009492  pop     r12
0x140009494  pop     rdi
0x140009495  pop     rsi
0x140009496  pop     rbp
0x140009497  pop     rbx
0x140009498  retn
```
