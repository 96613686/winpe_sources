# ParseSaveCmdLine

- ea: `0x14000426c`
- end: `0x140004564`
- name: `ParseSaveCmdLine`
- size: `760`
- prototype: `__int64 __fastcall(unsigned int, PCNZWCH *, const WCHAR *, int *, _DWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400040b8`
- `0x140004764`
- `0x14000496c`

## callees

- `0x140001e90`
- `0x140002ce4`
- `0x14000426c`
- `0x14000ce50`
- `0x14000d694`
- `0x14000d990`
- `0x14000e600`
- `0x14000ee5c`
- `0x14000f0c0`
- `0x14000f15c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400042f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400042f7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140004392`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400043b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140004402`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140004392`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400043b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140004402`

## pseudocode

```c
__int64 __fastcall ParseSaveCmdLine(unsigned int a1, PCNZWCH *a2, const WCHAR *a3, int *a4, _DWORD *a5)
{
  __int64 v8; // rsi
  __int64 v10; // rcx
  __int64 ResString2FromModule; // rax
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rcx
  int v14; // eax
  unsigned int v15; // r14d
  __int64 Memory; // rax
  __int64 v17; // rcx
  const WCHAR *v18; // rcx

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
  if ( (unsigned int)StringCompareExW(a2[1], a3) )
  {
LABEL_51:
    v17 = 87;
    goto LABEL_52;
  }
  if ( !(unsigned int)BreakDownKeyString(a2[2], a4) )
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
            if ( (unsigned int)StringCompareExW(a2[v8], L"/y") && (unsigned int)StringCompareExW(a2[v8], L"-y") )
            {
              if ( (unsigned int)StringCompareExW(a2[v8], L"/c") && (unsigned int)StringCompareExW(a2[v8], L"-c") )
              {
                if ( (unsigned int)StringCompareExW(a2[v8], L"/reg:32")
                  && (unsigned int)StringCompareExW(a2[v8], L"-reg:32") )
                {
                  if ( !(unsigned int)StringCompareExW(a2[v8], L"/reg:64")
                    || !(unsigned int)StringCompareExW(a2[v8], L"-reg:64") )
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
  ResString2FromModule = GetResString2FromModule(v10, 103, 0);
  SetReason2(1, ResString2FromModule, &g_wszOptions[10 * *a4]);
  return 0;
}

```

## disassembly

```asm
0x14000426c  push    rbx
0x14000426e  push    rbp
0x14000426f  push    rsi
0x140004270  push    rdi
0x140004271  push    r14
0x140004273  push    r15
0x140004275  sub     rsp, 28h
0x140004279  mov     rbx, r9
0x14000427c  mov     rbp, r8
0x14000427f  mov     rdi, rdx
0x140004282  mov     esi, ecx
0x140004284  test    ecx, ecx
0x140004286  jz      loc_14000454A
0x14000428c  test    rdx, rdx
0x14000428f  jz      loc_14000454A
0x140004295  test    r8, r8
0x140004298  jz      loc_14000454A
0x14000429e  test    rbx, rbx
0x1400042a1  jz      loc_14000454A
0x1400042a7  mov     r14, [rsp+58h+arg_20]
0x1400042af  test    r14, r14
0x1400042b2  jz      loc_14000454A
0x1400042b8  cmp     dword ptr [r9], 0Bh
0x1400042bc  ja      loc_14000454A
0x1400042c2  mov     r15d, 1
0x1400042c8  cmp     ecx, 3
0x1400042cb  jb      short loc_140004331
0x1400042cd  mov     rcx, [rdi+10h]; lpString
0x1400042d1  lea     rdx, aHH; "-?|/?|-h|/h"
0x1400042d8  call    InString
0x1400042dd  cmp     eax, r15d
0x1400042e0  jnz     short loc_140004331
0x1400042e2  cmp     esi, 3
0x1400042e5  jnz     short loc_1400042F2
0x1400042e7  mov     [r14], r15d
0x1400042ea  mov     eax, r15d
0x1400042ed  jmp     loc_140004556
0x1400042f2  mov     ecx, 800401E4h; dwErrCode
0x1400042f7  call    cs:__imp_SetLastError
0x1400042fe  nop     dword ptr [rax+rax+00h]
0x140004303  xor     r8d, r8d
0x140004306  lea     edx, [r8+67h]
0x14000430a  call    GetResString2FromModule
0x14000430f  movsxd  rcx, dword ptr [rbx]
0x140004312  lea     rdx, [rcx+rcx*4]
0x140004316  lea     rcx, g_wszOptions; "QUERY"
0x14000431d  lea     r8, [rcx+rdx*4]
0x140004321  mov     rdx, rax
0x140004324  mov     ecx, r15d
0x140004327  call    SetReason2
0x14000432c  jmp     loc_140004554
0x140004331  cmp     dword ptr [rbx], 6
0x140004334  jnz     short loc_14000433B
0x140004336  cmp     esi, 4
0x140004339  jnz     short loc_1400042F2
0x14000433b  cmp     dword ptr [rbx], 5
0x14000433e  jnz     short loc_140004348
0x140004340  lea     eax, [rsi-4]
0x140004343  cmp     eax, r15d
0x140004346  ja      short loc_1400042F2
0x140004348  cmp     dword ptr [rbx], 4
0x14000434b  jnz     short loc_140004355
0x14000434d  lea     eax, [rsi-4]
0x140004350  cmp     eax, 3
0x140004353  ja      short loc_1400042F2
0x140004355  mov     rcx, [rdi+8]; lpString1
0x140004359  xor     r9d, r9d
0x14000435c  mov     rdx, rbp; lpString2
0x14000435f  call    StringCompareExW
0x140004364  test    eax, eax
0x140004366  jnz     loc_14000454A
0x14000436c  mov     rcx, [rdi+10h]
0x140004370  mov     rdx, rbx
0x140004373  call    BreakDownKeyString
0x140004378  test    eax, eax
0x14000437a  jz      loc_140004554
0x140004380  cmp     dword ptr [rbx], 6
0x140004383  jnz     short loc_1400043A6
0x140004385  mov     rcx, [rbx+50h]; lpString
0x140004389  test    rcx, rcx
0x14000438c  jz      loc_1400042F2
0x140004392  call    cs:__imp_lstrlenW
0x140004399  nop     dword ptr [rax+rax+00h]
0x14000439e  test    eax, eax
0x1400043a0  jz      loc_1400042F2
0x1400043a6  mov     rcx, [rdi+18h]; lpString
0x1400043aa  test    rcx, rcx
0x1400043ad  jnz     short loc_1400043B3
0x1400043af  xor     eax, eax
0x1400043b1  jmp     short loc_1400043BF
0x1400043b3  call    cs:__imp_lstrlenW
0x1400043ba  nop     dword ptr [rax+rax+00h]
0x1400043bf  lea     r14d, [rax+1]
0x1400043c3  lea     ecx, [r14+r14]; dwBytes
0x1400043c7  call    AllocateMemory
0x1400043cc  mov     [rbx+60h], rax
0x1400043d0  test    rax, rax
0x1400043d3  jnz     short loc_1400043DD
0x1400043d5  lea     ecx, [rax+0Eh]
0x1400043d8  jmp     loc_14000454F
0x1400043dd  mov     rdx, [rdi+18h]
0x1400043e1  mov     r8d, r14d
0x1400043e4  mov     rcx, rax
0x1400043e7  call    StringCopyW
0x1400043ec  mov     rcx, [rbx+60h]; lpString
0x1400043f0  call    TrimString2
0x1400043f5  mov     rcx, [rbx+60h]; lpString
0x1400043f9  test    rcx, rcx
0x1400043fc  jz      loc_1400042F2
0x140004402  call    cs:__imp_lstrlenW
0x140004409  nop     dword ptr [rax+rax+00h]
0x14000440e  test    eax, eax
0x140004410  jz      loc_1400042F2
0x140004416  cmp     dword ptr [rbx], 6
0x140004419  jz      loc_1400042EA
0x14000441f  jmp     loc_14000453C
0x140004424  dec     esi
0x140004426  lea     rdx, aY_0; "/y"
0x14000442d  xor     r9d, r9d
0x140004430  mov     rcx, [rdi+rsi*8]; lpString1
0x140004434  call    StringCompareExW
0x140004439  test    eax, eax
0x14000443b  jz      loc_14000452F
0x140004441  mov     rcx, [rdi+rsi*8]; lpString1
0x140004445  lea     rdx, aY; "-y"
0x14000444c  xor     r9d, r9d
0x14000444f  call    StringCompareExW
0x140004454  test    eax, eax
0x140004456  jz      loc_14000452F
0x14000445c  mov     rcx, [rdi+rsi*8]; lpString1
0x140004460  lea     rdx, aC_0; "/c"
0x140004467  xor     r9d, r9d
0x14000446a  call    StringCompareExW
0x14000446f  test    eax, eax
0x140004471  jz      loc_140004520
0x140004477  mov     rcx, [rdi+rsi*8]; lpString1
0x14000447b  lea     rdx, aC; "-c"
0x140004482  xor     r9d, r9d
0x140004485  call    StringCompareExW
0x14000448a  test    eax, eax
0x14000448c  jz      loc_140004520
0x140004492  mov     rcx, [rdi+rsi*8]; lpString1
0x140004496  lea     rdx, aReg32; "/reg:32"
0x14000449d  xor     r9d, r9d
0x1400044a0  call    StringCompareExW
0x1400044a5  test    eax, eax
0x1400044a7  jz      short loc_140004507
0x1400044a9  mov     rcx, [rdi+rsi*8]; lpString1
0x1400044ad  lea     rdx, aReg32_0; "-reg:32"
0x1400044b4  xor     r9d, r9d
0x1400044b7  call    StringCompareExW
0x1400044bc  test    eax, eax
0x1400044be  jz      short loc_140004507
0x1400044c0  mov     rcx, [rdi+rsi*8]; lpString1
0x1400044c4  lea     rdx, aReg64_0; "/reg:64"
0x1400044cb  xor     r9d, r9d
0x1400044ce  call    StringCompareExW
0x1400044d3  test    eax, eax
0x1400044d5  jz      short loc_1400044EE
0x1400044d7  mov     rcx, [rdi+rsi*8]; lpString1
0x1400044db  lea     rdx, aReg64; "-reg:64"
0x1400044e2  xor     r9d, r9d
0x1400044e5  call    StringCompareExW
0x1400044ea  test    eax, eax
0x1400044ec  jnz     short loc_14000453C
0x1400044ee  cmp     dword ptr [rbx+8Ch], 0
0x1400044f5  jnz     loc_1400042F2
0x1400044fb  mov     dword ptr [rbx+8Ch], 100h
0x140004505  jmp     short loc_14000453C
0x140004507  cmp     dword ptr [rbx+8Ch], 0
0x14000450e  jnz     loc_1400042F2
0x140004514  mov     dword ptr [rbx+8Ch], 200h
0x14000451e  jmp     short loc_14000453C
0x140004520  cmp     dword ptr [rbx], 4
0x140004523  jnz     loc_1400042F2
0x140004529  mov     [rbx+30h], r15d
0x14000452d  jmp     short loc_14000453C
0x14000452f  cmp     dword ptr [rbx], 4
0x140004532  jnz     loc_1400042F2
0x140004538  mov     [rbx+18h], r15d
0x14000453c  cmp     esi, 5
0x14000453f  jnb     loc_140004424
0x140004545  jmp     loc_1400042EA
0x14000454a  mov     ecx, 57h ; 'W'
0x14000454f  call    SaveErrorMessage
0x140004554  xor     eax, eax
0x140004556  add     rsp, 28h
0x14000455a  pop     r15
0x14000455c  pop     r14
0x14000455e  pop     rdi
0x14000455f  pop     rsi
0x140004560  pop     rbp
0x140004561  pop     rbx
0x140004562  retn
```
