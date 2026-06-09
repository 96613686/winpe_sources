# ParseCompareCmdLine

- ea: `0x14000957c`
- end: `0x140009a47`
- name: `ParseCompareCmdLine`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140008cbc`

## callees

- `0x140001e90`
- `0x140002004`
- `0x1400022dc`
- `0x140002ce4`
- `0x140009374`
- `0x14000957c`
- `0x14000ce50`
- `0x14000d694`
- `0x14000d990`
- `0x14000e600`
- `0x14000ee5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009651`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009980`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009980`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400099cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400099cf`

## string_xrefs

- `0x140009998`: `COMPARE`
- `0x140009616`: `COMPARE`

## pseudocode

```c
__int64 __fastcall ParseCompareCmdLine(unsigned int a1, PCNZWCH *a2, __int64 a3, __int64 a4, _DWORD *a5)
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
    if ( (unsigned int)InString(a2[2], L"/?|-?|/h|-h") == 1 )
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
  if ( (unsigned int)StringCompareExW(a2[1], L"COMPARE", a3, 0) )
  {
LABEL_75:
    v26 = 87;
LABEL_76:
    SaveErrorMessage(v26);
    return 0;
  }
  if ( (unsigned int)BreakDownKeyString(a2[2], (int *)a3) )
  {
    if ( (unsigned int)BreakDownKeyString(a2[3], (int *)a4) )
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
      v12 = BreakDownKeyString(*(const WCHAR **)(a3 + 88), (int *)a4);
    }
    if ( v12 )
    {
LABEL_21:
      LODWORD(v14) = 4;
      if ( a1 > 4 )
      {
        do
        {
          if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/v", v10, 0)
            && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-v", v15, 0) )
          {
            if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/ve", v16, 0)
              && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-ve", v17, 0) )
            {
              if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/oa", v18, 0)
                && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-oa", v10, 0) )
              {
                if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/od", v10, 0)
                  && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-od", v10, 0) )
                {
                  if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/os", v10, 0)
                    && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-os", v10, 0) )
                  {
                    if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/on", v10, 0)
                      && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-on", v10, 0) )
                    {
                      if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/s", v10, 0)
                        && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-s", v10, 0) )
                      {
                        if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/reg:32", v10, 0)
                          && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-reg:32", v10, 0) )
                        {
                          if ( (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"/reg:64", v10, 0)
                            && (unsigned int)StringCompareExW(a2[(unsigned int)v14], L"-reg:64", v10, 0)
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
            v22 = a2[v14];
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
            StringCopyW(v25, a2[v14], v24);
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
0x14000957c  push    rbx
0x14000957e  push    rbp
0x14000957f  push    rsi
0x140009580  push    rdi
0x140009581  push    r12
0x140009583  push    r13
0x140009585  push    r14
0x140009587  push    r15
0x140009589  sub     rsp, 28h
0x14000958d  xor     r12d, r12d
0x140009590  mov     rbp, r9
0x140009593  mov     rbx, r8
0x140009596  mov     rsi, rdx
0x140009599  mov     r13d, ecx
0x14000959c  test    ecx, ecx
0x14000959e  jz      loc_140009A29
0x1400095a4  test    rdx, rdx
0x1400095a7  jz      loc_140009A29
0x1400095ad  test    rbx, rbx
0x1400095b0  jz      loc_140009A29
0x1400095b6  test    r9, r9
0x1400095b9  jz      loc_140009A29
0x1400095bf  mov     r14, [rsp+68h+arg_20]
0x1400095c7  test    r14, r14
0x1400095ca  jz      loc_140009A29
0x1400095d0  cmp     dword ptr [r8], 0Bh
0x1400095d4  ja      loc_140009A29
0x1400095da  lea     edi, [r12+1]
0x1400095df  cmp     ecx, 3
0x1400095e2  jnz     short loc_140009606
0x1400095e4  mov     rcx, [rsi+10h]; lpString
0x1400095e8  lea     rdx, aHH_0; "/?|-?|/h|-h"
0x1400095ef  call    InString
0x1400095f4  cmp     eax, edi
0x1400095f6  jnz     loc_14000997B
0x1400095fc  mov     [r14], edi
0x1400095ff  mov     eax, edi
0x140009601  jmp     loc_140009A35
0x140009606  lea     eax, [rcx-4]
0x140009609  cmp     eax, 5
0x14000960c  ja      loc_14000997B
0x140009612  mov     rcx, [rsi+8]; lpString1
0x140009616  lea     rdx, aCompare; "COMPARE"
0x14000961d  xor     r9d, r9d
0x140009620  call    StringCompareExW
0x140009625  test    eax, eax
0x140009627  jnz     loc_140009A29
0x14000962d  mov     rcx, [rsi+10h]
0x140009631  mov     rdx, rbx
0x140009634  call    BreakDownKeyString
0x140009639  test    eax, eax
0x14000963b  jz      loc_140009A33
0x140009641  mov     rcx, [rsi+18h]
0x140009645  mov     rdx, rbp
0x140009648  call    BreakDownKeyString
0x14000964d  test    eax, eax
0x14000964f  jnz     short loc_1400096BE
0x140009651  call    cs:__imp_GetLastError
0x140009658  nop     dword ptr [rax+rax+00h]
0x14000965d  cmp     eax, 80040152h
0x140009662  jnz     short loc_140009671
0x140009664  mov     rdx, rbp
0x140009667  mov     rcx, rbx
0x14000966a  call    CopyKeyNameFromLeftToRight
0x14000966f  jmp     short loc_1400096B6
0x140009671  mov     rcx, [rbp+48h]; lpString1
0x140009675  test    rcx, rcx
0x140009678  jz      loc_140009A33
0x14000967e  xor     r9d, r9d
0x140009681  lea     rdx, asc_140011848; "\\\\."
0x140009688  call    StringCompareExW
0x14000968d  test    eax, eax
0x14000968f  jnz     loc_140009A33
0x140009695  mov     rcx, rbp
0x140009698  call    FreeGlobalData
0x14000969d  mov     rdx, rbp
0x1400096a0  mov     ecx, 8
0x1400096a5  call    InitGlobalData
0x1400096aa  mov     rcx, [rbx+58h]
0x1400096ae  mov     rdx, rbp
0x1400096b1  call    BreakDownKeyString
0x1400096b6  test    eax, eax
0x1400096b8  jz      loc_140009A33
0x1400096be  mov     r14d, 4
0x1400096c4  cmp     r13d, r14d
0x1400096c7  jbe     loc_140009A0C
0x1400096cd  mov     ebp, r14d
0x1400096d0  lea     rdx, aV_0; "/v"
0x1400096d7  xor     r9d, r9d
0x1400096da  mov     rcx, [rsi+rbp*8]; lpString1
0x1400096de  call    StringCompareExW
0x1400096e3  test    eax, eax
0x1400096e5  jz      loc_1400099AE
0x1400096eb  mov     rcx, [rsi+rbp*8]; lpString1
0x1400096ef  lea     rdx, aV; "-v"
0x1400096f6  xor     r9d, r9d
0x1400096f9  call    StringCompareExW
0x1400096fe  test    eax, eax
0x140009700  jz      loc_1400099AE
0x140009706  mov     rcx, [rsi+rbp*8]; lpString1
0x14000970a  lea     rdx, aVe_0; "/ve"
0x140009711  xor     r9d, r9d
0x140009714  call    StringCompareExW
0x140009719  test    eax, eax
0x14000971b  jz      loc_140009959
0x140009721  mov     rcx, [rsi+rbp*8]; lpString1
0x140009725  lea     rdx, aVe; "-ve"
0x14000972c  xor     r9d, r9d
0x14000972f  call    StringCompareExW
0x140009734  test    eax, eax
0x140009736  jz      loc_140009959
0x14000973c  mov     rcx, [rsi+rbp*8]; lpString1
0x140009740  lea     rdx, aOa; "/oa"
0x140009747  xor     r9d, r9d
0x14000974a  call    StringCompareExW
0x14000974f  test    eax, eax
0x140009751  jz      loc_140009941
0x140009757  mov     rcx, [rsi+rbp*8]; lpString1
0x14000975b  lea     rdx, aOa_0; "-oa"
0x140009762  xor     r9d, r9d
0x140009765  call    StringCompareExW
0x14000976a  test    eax, eax
0x14000976c  jz      loc_140009941
0x140009772  mov     rcx, [rsi+rbp*8]; lpString1
0x140009776  lea     rdx, aOd_0; "/od"
0x14000977d  xor     r9d, r9d
0x140009780  call    StringCompareExW
0x140009785  test    eax, eax
0x140009787  jz      loc_140009929
0x14000978d  mov     rcx, [rsi+rbp*8]; lpString1
0x140009791  lea     rdx, aOd; "-od"
0x140009798  xor     r9d, r9d
0x14000979b  call    StringCompareExW
0x1400097a0  test    eax, eax
0x1400097a2  jz      loc_140009929
0x1400097a8  mov     rcx, [rsi+rbp*8]; lpString1
0x1400097ac  lea     rdx, aOs; "/os"
0x1400097b3  xor     r9d, r9d
0x1400097b6  call    StringCompareExW
0x1400097bb  test    eax, eax
0x1400097bd  jz      loc_140009911
0x1400097c3  mov     rcx, [rsi+rbp*8]; lpString1
0x1400097c7  lea     rdx, aOs_0; "-os"
0x1400097ce  xor     r9d, r9d
0x1400097d1  call    StringCompareExW
0x1400097d6  test    eax, eax
0x1400097d8  jz      loc_140009911
0x1400097de  mov     rcx, [rsi+rbp*8]; lpString1
0x1400097e2  lea     rdx, aOn_0; "/on"
0x1400097e9  xor     r9d, r9d
0x1400097ec  call    StringCompareExW
0x1400097f1  test    eax, eax
0x1400097f3  jz      loc_1400098FD
0x1400097f9  mov     rcx, [rsi+rbp*8]; lpString1
0x1400097fd  lea     rdx, aOn; "-on"
0x140009804  xor     r9d, r9d
0x140009807  call    StringCompareExW
0x14000980c  test    eax, eax
0x14000980e  jz      loc_1400098FD
0x140009814  mov     rcx, [rsi+rbp*8]; lpString1
0x140009818  lea     rdx, aS_4; "/s"
0x14000981f  xor     r9d, r9d
0x140009822  call    StringCompareExW
0x140009827  test    eax, eax
0x140009829  jz      loc_1400098E2
0x14000982f  mov     rcx, [rsi+rbp*8]; lpString1
0x140009833  lea     rdx, aS_3; "-s"
0x14000983a  xor     r9d, r9d
0x14000983d  call    StringCompareExW
0x140009842  test    eax, eax
0x140009844  jz      loc_1400098E2
0x14000984a  mov     rcx, [rsi+rbp*8]; lpString1
0x14000984e  lea     rdx, aReg32; "/reg:32"
0x140009855  xor     r9d, r9d
0x140009858  call    StringCompareExW
0x14000985d  test    eax, eax
0x14000985f  jz      short loc_1400098C6
0x140009861  mov     rcx, [rsi+rbp*8]; lpString1
0x140009865  lea     rdx, aReg32_0; "-reg:32"
0x14000986c  xor     r9d, r9d
0x14000986f  call    StringCompareExW
0x140009874  test    eax, eax
0x140009876  jz      short loc_1400098C6
0x140009878  mov     rcx, [rsi+rbp*8]; lpString1
0x14000987c  lea     rdx, aReg64_0; "/reg:64"
0x140009883  xor     r9d, r9d
0x140009886  call    StringCompareExW
0x14000988b  test    eax, eax
0x14000988d  jz      short loc_1400098AA
0x14000988f  mov     rcx, [rsi+rbp*8]; lpString1
0x140009893  lea     rdx, aReg64; "-reg:64"
0x14000989a  xor     r9d, r9d
0x14000989d  call    StringCompareExW
0x1400098a2  test    eax, eax
0x1400098a4  jnz     loc_14000997B
0x1400098aa  cmp     [rbx+8Ch], r12d
0x1400098b1  jnz     loc_14000997B
0x1400098b7  mov     dword ptr [rbx+8Ch], 100h
0x1400098c1  jmp     loc_140009A00
0x1400098c6  cmp     [rbx+8Ch], r12d
0x1400098cd  jnz     loc_14000997B
0x1400098d3  mov     dword ptr [rbx+8Ch], 200h
0x1400098dd  jmp     loc_140009A00
0x1400098e2  cmp     [rbx+60h], r12
0x1400098e6  jnz     loc_14000997B
0x1400098ec  cmp     [rbx+20h], edi
0x1400098ef  jz      loc_14000997B
0x1400098f5  mov     [rbx+20h], edi
0x1400098f8  jmp     loc_140009A00
0x1400098fd  cmp     [rbx+60h], r12
0x140009901  jnz     short loc_14000997B
0x140009903  cmp     [rbx+34h], r12d
0x140009907  jnz     short loc_14000997B
0x140009909  mov     [rbx+34h], edi
0x14000990c  jmp     loc_140009A00
0x140009911  cmp     [rbx+60h], r12
0x140009915  jnz     short loc_14000997B
0x140009917  cmp     [rbx+34h], r12d
0x14000991b  jnz     short loc_14000997B
0x14000991d  mov     dword ptr [rbx+34h], 2
0x140009924  jmp     loc_140009A00
0x140009929  cmp     [rbx+60h], r12
0x14000992d  jnz     short loc_14000997B
0x14000992f  cmp     [rbx+34h], r12d
0x140009933  jnz     short loc_14000997B
0x140009935  mov     dword ptr [rbx+34h], 3
0x14000993c  jmp     loc_140009A00
0x140009941  cmp     [rbx+60h], r12
0x140009945  jnz     short loc_14000997B
0x140009947  cmp     [rbx+34h], r12d
0x14000994b  jnz     short loc_14000997B
0x14000994d  mov     dword ptr [rbx+34h], 4
0x140009954  jmp     loc_140009A00
0x140009959  cmp     [rbx+60h], r12
0x14000995d  jnz     short loc_14000997B
0x14000995f  cmp     [rbx+20h], edi
0x140009962  jz      short loc_14000997B
0x140009964  mov     ecx, 4; dwBytes
0x140009969  call    AllocateMemory
0x14000996e  mov     [rbx+60h], rax
0x140009972  test    rax, rax
0x140009975  jnz     loc_140009A00
0x14000997b  mov     ecx, 800401E4h; dwErrCode
0x140009980  call    cs:__imp_SetLastError
0x140009987  nop     dword ptr [rax+rax+00h]
0x14000998c  xor     r8d, r8d
0x14000998f  lea     edx, [r8+67h]
0x140009993  call    GetResString2FromModule
0x140009998  lea     r8, aCompare_0; "COMPARE"
0x14000999f  mov     rdx, rax
0x1400099a2  mov     ecx, edi
0x1400099a4  call    SetReason2
0x1400099a9  jmp     loc_140009A33
0x1400099ae  cmp     [rbx+60h], r12
0x1400099b2  jnz     short loc_14000997B
0x1400099b4  cmp     [rbx+20h], edi
0x1400099b7  jz      short loc_14000997B
0x1400099b9  inc     r14d
0x1400099bc  cmp     r14d, r13d
0x1400099bf  jnb     short loc_14000997B
0x1400099c1  mov     rcx, [rsi+r14*8]; lpString
0x1400099c5  test    rcx, rcx
0x1400099c8  jnz     short loc_1400099CF
0x1400099ca  mov     eax, r12d
0x1400099cd  jmp     short loc_1400099DB
0x1400099cf  call    cs:__imp_lstrlenW
0x1400099d6  nop     dword ptr [rax+rax+00h]
0x1400099db  lea     r15d, [rax+1]
0x1400099df  lea     ecx, [r15+r15]; dwBytes
0x1400099e3  call    AllocateMemory
0x1400099e8  mov     [rbx+60h], rax
0x1400099ec  test    rax, rax
0x1400099ef  jz      short loc_140009A22
0x1400099f1  mov     rdx, [rsi+r14*8]
0x1400099f5  mov     r8d, r15d
0x1400099f8  mov     rcx, rax
0x1400099fb  call    StringCopyW
0x140009a00  add     r14d, edi
0x140009a03  cmp     r14d, r13d
0x140009a06  jb      loc_1400096CD
0x140009a0c  cmp     [rbx+34h], r12d
0x140009a10  jnz     loc_1400095FF
0x140009a16  mov     dword ptr [rbx+34h], 3
0x140009a1d  jmp     loc_1400095FF
0x140009a22  mov     ecx, 0Eh
0x140009a27  jmp     short loc_140009A2E
0x140009a29  mov     ecx, 57h ; 'W'
0x140009a2e  call    SaveErrorMessage
0x140009a33  xor     eax, eax
0x140009a35  add     rsp, 28h
0x140009a39  pop     r15
0x140009a3b  pop     r14
0x140009a3d  pop     r13
0x140009a3f  pop     r12
0x140009a41  pop     rdi
0x140009a42  pop     rsi
0x140009a43  pop     rbp
0x140009a44  pop     rbx
0x140009a45  retn
```
