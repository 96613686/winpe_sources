# ParseSaveCmdLine

- ea: `0x14000406c`
- end: `0x14000434b`
- name: `ParseSaveCmdLine`
- size: `735`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140003ec4`
- `0x140004518`
- `0x140004708`

## callees

- `0x140001e90`
- `0x140002b70`
- `0x14000406c`
- `0x14000c62c`
- `0x14000cd48`
- `0x14000d010`
- `0x14000daa4`
- `0x14000e228`
- `0x14000e450`
- `0x14000e4e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400040f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400040f7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000418c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400041a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400041f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000418c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400041a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400041f0`

## pseudocode

```c
__int64 __fastcall ParseSaveCmdLine(unsigned int a1, PCNZWCH *a2, const WCHAR *a3, int *a4, _DWORD *a5)
{
  __int64 v8; // rsi
  __int64 v10; // rcx
  __int64 *ResString2FromModule; // rax
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rcx
  int v14; // eax
  unsigned int v15; // r14d
  _WORD *Memory; // rax
  __int64 v17; // rcx
  const WCHAR *v18; // rcx
  __int64 v19; // r8

  LODWORD(v8) = a1;
  if ( !a1 || !a2 || !a3 || !a4 || !a5 || (unsigned int)*a4 > 0xB )
    goto LABEL_51;
  if ( a1 >= 3 && (unsigned int)InString(a2[2], L"-?|/?|-h|/h") == 1 )
  {
    if ( (_DWORD)v8 == 3 )
    {
      *a5 = 1;
      return 1;
    }
    goto LABEL_12;
  }
  if ( *a4 == 6 && (_DWORD)v8 != 4 || *a4 == 5 && (unsigned int)(v8 - 4) > 1 || *a4 == 4 && (unsigned int)(v8 - 4) > 3 )
    goto LABEL_12;
  if ( (unsigned int)StringCompareExW(a2[1], a3, (__int64)a3, 0) )
  {
LABEL_51:
    v17 = 87;
    goto LABEL_52;
  }
  if ( !(unsigned int)BreakDownKeyString((WCHAR *)a2[2], a4) )
    return 0;
  if ( *a4 != 6 || (v12 = (const WCHAR *)*((_QWORD *)a4 + 10)) != 0 && lstrlenW(v12) )
  {
    v13 = a2[3];
    if ( v13 )
      v14 = lstrlenW(v13);
    else
      v14 = 0;
    v15 = v14 + 1;
    Memory = AllocateMemory((unsigned int)(2 * (v14 + 1)));
    *((_QWORD *)a4 + 12) = Memory;
    if ( Memory )
    {
      StringCopyW(Memory, a2[3], v15);
      TrimString2(*((LPCWSTR *)a4 + 12));
      v18 = (const WCHAR *)*((_QWORD *)a4 + 12);
      if ( v18 && lstrlenW(v18) )
      {
        if ( *a4 != 6 )
        {
          while ( (unsigned int)v8 >= 5 )
          {
            v8 = (unsigned int)(v8 - 1);
            if ( (unsigned int)StringCompareExW(a2[v8], L"/y", v19, 0)
              && (unsigned int)StringCompareExW(a2[v8], L"-y", v19, 0) )
            {
              if ( (unsigned int)StringCompareExW(a2[v8], L"/c", v19, 0)
                && (unsigned int)StringCompareExW(a2[v8], L"-c", v19, 0) )
              {
                if ( (unsigned int)StringCompareExW(a2[v8], L"/reg:32", v19, 0)
                  && (unsigned int)StringCompareExW(a2[v8], L"-reg:32", v19, 0) )
                {
                  if ( !(unsigned int)StringCompareExW(a2[v8], L"/reg:64", v19, 0)
                    || !(unsigned int)StringCompareExW(a2[v8], L"-reg:64", v19, 0) )
                  {
                    if ( a4[35] )
                      goto LABEL_12;
                    a4[35] = 256;
                  }
                }
                else
                {
                  if ( a4[35] )
                    goto LABEL_12;
                  a4[35] = 512;
                }
              }
              else
              {
                if ( *a4 != 4 )
                  goto LABEL_12;
                a4[12] = 1;
              }
            }
            else
            {
              if ( *a4 != 4 )
                goto LABEL_12;
              a4[6] = 1;
            }
          }
        }
        return 1;
      }
      goto LABEL_12;
    }
    v17 = 14;
LABEL_52:
    SaveErrorMessage(v17);
    return 0;
  }
LABEL_12:
  SetLastError(0x800401E4);
  ResString2FromModule = GetResString2FromModule(v10, 0x67u, 0);
  SetReason2(1, (const wchar_t *)ResString2FromModule, &g_wszOptions[10 * *a4]);
  return 0;
}

```

## disassembly

```asm
0x14000406c  push    rbx
0x14000406e  push    rbp
0x14000406f  push    rsi
0x140004070  push    rdi
0x140004071  push    r14
0x140004073  push    r15
0x140004075  sub     rsp, 28h
0x140004079  mov     rbx, r9
0x14000407c  mov     rbp, r8
0x14000407f  mov     rdi, rdx
0x140004082  mov     esi, ecx
0x140004084  test    ecx, ecx
0x140004086  jz      loc_140004332
0x14000408c  test    rdx, rdx
0x14000408f  jz      loc_140004332
0x140004095  test    r8, r8
0x140004098  jz      loc_140004332
0x14000409e  test    rbx, rbx
0x1400040a1  jz      loc_140004332
0x1400040a7  mov     r14, [rsp+58h+arg_20]
0x1400040af  test    r14, r14
0x1400040b2  jz      loc_140004332
0x1400040b8  cmp     dword ptr [r9], 0Bh
0x1400040bc  ja      loc_140004332
0x1400040c2  mov     r15d, 1
0x1400040c8  cmp     ecx, 3
0x1400040cb  jb      short loc_14000412B
0x1400040cd  mov     rcx, [rdi+10h]; lpString
0x1400040d1  lea     rdx, aHH; "-?|/?|-h|/h"
0x1400040d8  call    InString
0x1400040dd  cmp     eax, r15d
0x1400040e0  jnz     short loc_14000412B
0x1400040e2  cmp     esi, 3
0x1400040e5  jnz     short loc_1400040F2
0x1400040e7  mov     [r14], r15d
0x1400040ea  mov     eax, r15d
0x1400040ed  jmp     loc_14000433E
0x1400040f2  mov     ecx, 800401E4h; dwErrCode
0x1400040f7  call    cs:__imp_SetLastError
0x1400040fd  xor     r8d, r8d
0x140004100  lea     edx, [r8+67h]
0x140004104  call    GetResString2FromModule
0x140004109  movsxd  rcx, dword ptr [rbx]
0x14000410c  lea     rdx, [rcx+rcx*4]
0x140004110  lea     rcx, g_wszOptions; "QUERY"
0x140004117  lea     r8, [rcx+rdx*4]
0x14000411b  mov     rdx, rax
0x14000411e  mov     ecx, r15d
0x140004121  call    SetReason2
0x140004126  jmp     loc_14000433C
0x14000412b  cmp     dword ptr [rbx], 6
0x14000412e  jnz     short loc_140004135
0x140004130  cmp     esi, 4
0x140004133  jnz     short loc_1400040F2
0x140004135  cmp     dword ptr [rbx], 5
0x140004138  jnz     short loc_140004142
0x14000413a  lea     eax, [rsi-4]
0x14000413d  cmp     eax, r15d
0x140004140  ja      short loc_1400040F2
0x140004142  cmp     dword ptr [rbx], 4
0x140004145  jnz     short loc_14000414F
0x140004147  lea     eax, [rsi-4]
0x14000414a  cmp     eax, 3
0x14000414d  ja      short loc_1400040F2
0x14000414f  mov     rcx, [rdi+8]; lpString1
0x140004153  xor     r9d, r9d
0x140004156  mov     rdx, rbp; lpString2
0x140004159  call    StringCompareExW
0x14000415e  test    eax, eax
0x140004160  jnz     loc_140004332
0x140004166  mov     rcx, [rdi+10h]
0x14000416a  mov     rdx, rbx
0x14000416d  call    BreakDownKeyString
0x140004172  test    eax, eax
0x140004174  jz      loc_14000433C
0x14000417a  cmp     dword ptr [rbx], 6
0x14000417d  jnz     short loc_14000419A
0x14000417f  mov     rcx, [rbx+50h]; lpString
0x140004183  test    rcx, rcx
0x140004186  jz      loc_1400040F2
0x14000418c  call    cs:__imp_lstrlenW
0x140004192  test    eax, eax
0x140004194  jz      loc_1400040F2
0x14000419a  mov     rcx, [rdi+18h]; lpString
0x14000419e  test    rcx, rcx
0x1400041a1  jnz     short loc_1400041A7
0x1400041a3  xor     eax, eax
0x1400041a5  jmp     short loc_1400041AD
0x1400041a7  call    cs:__imp_lstrlenW
0x1400041ad  lea     r14d, [rax+1]
0x1400041b1  lea     ecx, [r14+r14]; dwBytes
0x1400041b5  call    AllocateMemory
0x1400041ba  mov     [rbx+60h], rax
0x1400041be  test    rax, rax
0x1400041c1  jnz     short loc_1400041CB
0x1400041c3  lea     ecx, [rax+0Eh]
0x1400041c6  jmp     loc_140004337
0x1400041cb  mov     rdx, [rdi+18h]
0x1400041cf  mov     r8d, r14d
0x1400041d2  mov     rcx, rax
0x1400041d5  call    StringCopyW
0x1400041da  mov     rcx, [rbx+60h]; lpString
0x1400041de  call    TrimString2
0x1400041e3  mov     rcx, [rbx+60h]; lpString
0x1400041e7  test    rcx, rcx
0x1400041ea  jz      loc_1400040F2
0x1400041f0  call    cs:__imp_lstrlenW
0x1400041f6  test    eax, eax
0x1400041f8  jz      loc_1400040F2
0x1400041fe  cmp     dword ptr [rbx], 6
0x140004201  jz      loc_1400040EA
0x140004207  jmp     loc_140004324
0x14000420c  dec     esi
0x14000420e  lea     rdx, aY_0; "/y"
0x140004215  xor     r9d, r9d
0x140004218  mov     rcx, [rdi+rsi*8]; lpString1
0x14000421c  call    StringCompareExW
0x140004221  test    eax, eax
0x140004223  jz      loc_140004317
0x140004229  mov     rcx, [rdi+rsi*8]; lpString1
0x14000422d  lea     rdx, aY; "-y"
0x140004234  xor     r9d, r9d
0x140004237  call    StringCompareExW
0x14000423c  test    eax, eax
0x14000423e  jz      loc_140004317
0x140004244  mov     rcx, [rdi+rsi*8]; lpString1
0x140004248  lea     rdx, aC_0; "/c"
0x14000424f  xor     r9d, r9d
0x140004252  call    StringCompareExW
0x140004257  test    eax, eax
0x140004259  jz      loc_140004308
0x14000425f  mov     rcx, [rdi+rsi*8]; lpString1
0x140004263  lea     rdx, aC; "-c"
0x14000426a  xor     r9d, r9d
0x14000426d  call    StringCompareExW
0x140004272  test    eax, eax
0x140004274  jz      loc_140004308
0x14000427a  mov     rcx, [rdi+rsi*8]; lpString1
0x14000427e  lea     rdx, aReg32; "/reg:32"
0x140004285  xor     r9d, r9d
0x140004288  call    StringCompareExW
0x14000428d  test    eax, eax
0x14000428f  jz      short loc_1400042EF
0x140004291  mov     rcx, [rdi+rsi*8]; lpString1
0x140004295  lea     rdx, aReg32_0; "-reg:32"
0x14000429c  xor     r9d, r9d
0x14000429f  call    StringCompareExW
0x1400042a4  test    eax, eax
0x1400042a6  jz      short loc_1400042EF
0x1400042a8  mov     rcx, [rdi+rsi*8]; lpString1
0x1400042ac  lea     rdx, aReg64_0; "/reg:64"
0x1400042b3  xor     r9d, r9d
0x1400042b6  call    StringCompareExW
0x1400042bb  test    eax, eax
0x1400042bd  jz      short loc_1400042D6
0x1400042bf  mov     rcx, [rdi+rsi*8]; lpString1
0x1400042c3  lea     rdx, aReg64; "-reg:64"
0x1400042ca  xor     r9d, r9d
0x1400042cd  call    StringCompareExW
0x1400042d2  test    eax, eax
0x1400042d4  jnz     short loc_140004324
0x1400042d6  cmp     dword ptr [rbx+8Ch], 0
0x1400042dd  jnz     loc_1400040F2
0x1400042e3  mov     dword ptr [rbx+8Ch], 100h
0x1400042ed  jmp     short loc_140004324
0x1400042ef  cmp     dword ptr [rbx+8Ch], 0
0x1400042f6  jnz     loc_1400040F2
0x1400042fc  mov     dword ptr [rbx+8Ch], 200h
0x140004306  jmp     short loc_140004324
0x140004308  cmp     dword ptr [rbx], 4
0x14000430b  jnz     loc_1400040F2
0x140004311  mov     [rbx+30h], r15d
0x140004315  jmp     short loc_140004324
0x140004317  cmp     dword ptr [rbx], 4
0x14000431a  jnz     loc_1400040F2
0x140004320  mov     [rbx+18h], r15d
0x140004324  cmp     esi, 5
0x140004327  jnb     loc_14000420C
0x14000432d  jmp     loc_1400040EA
0x140004332  mov     ecx, 57h ; 'W'
0x140004337  call    SaveErrorMessage
0x14000433c  xor     eax, eax
0x14000433e  add     rsp, 28h
0x140004342  pop     r15
0x140004344  pop     r14
0x140004346  pop     rdi
0x140004347  pop     rsi
0x140004348  pop     rbp
0x140004349  pop     rbx
0x14000434a  retn
```
