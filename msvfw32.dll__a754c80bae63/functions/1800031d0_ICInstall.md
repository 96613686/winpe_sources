# ICInstall

- ea: `0x1800031d0`
- end: `0x1800033da`
- name: `ICInstall`
- size: `522`
- prototype: `BOOL __stdcall(DWORD fccType, DWORD fccHandler, LPARAM lParam, LPSTR szDesc, UINT wFlags)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800014b0`
- `0x1800014f0`
- `0x180001d62`
- `0x18000222c`
- `0x180002280`
- `0x18000250c`
- `0x180002584`
- `0x1800031d0`
- `0x180003f98`
- `0x180004024`
- `0x1800043b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000321c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000321c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000328c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003329`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000328c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800032f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003329`

## string_xrefs

- `0x18000335e`: `Installable Compressors`

## pseudocode

```c
BOOL __stdcall ICInstall(DWORD fccType, DWORD fccHandler, LPARAM lParam, LPSTR szDesc, UINT wFlags)
{
  unsigned int v9; // r15d
  unsigned int v10; // eax
  __int64 Converter; // rax
  unsigned int v12; // r11d
  __int64 v13; // rbx
  __int64 v14; // rax
  LPCWSTR v15; // r11
  int v16; // eax
  __int64 v17; // rax
  wchar_t *v18; // rbx
  WCHAR ValueName[24]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t pszDest[256]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(pszDest, 0, sizeof(pszDest));
  EnterCriticalSection(&ICOpenCritSec);
  v9 = Fix4CC(fccType);
  v10 = Fix4CC(fccHandler);
  Converter = FindConverter(v9, v10);
  if ( !Converter )
    Converter = FindConverter(0, 0);
  if ( (wFlags & 2) != 0 )
  {
    ictokey(v9, v12, ValueName);
    if ( (wFlags & 0x8000) != 0 )
    {
      StringCchCopyW(pszDest, 0x100u, (STRSAFE_LPCWSTR)lParam);
      v13 = (unsigned int)(lstrlenW(pszDest) + 1);
      v14 = v13;
      if ( szDesc )
      {
        StringCchCopyNW(&pszDest[v13], 256 - v13, (STRSAFE_PCNZWCH)szDesc, 256 - v13);
        v14 = (unsigned int)(v13 + lstrlenW(v15));
      }
      if ( (unsigned __int64)(2 * v14) >= 0x200 )
        _report_rangecheckfailure();
      pszDest[v14] = 0;
    }
    else
    {
      StringCchPrintfW(pszDest, 0x100u, L"%hs", lParam);
      v16 = lstrlenW(pszDest);
      if ( szDesc )
      {
        v17 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v17 < 0x100 )
        {
          v18 = &pszDest[v17];
          StringCchPrintfW(v18, 256 - v17, L"%hs", szDesc);
          lstrlenW(v18);
        }
      }
    }
    LeaveCriticalSection(&ICOpenCritSec);
    if ( myWritePrivateProfileString(aDrivers32, ValueName, pszDest) )
    {
      myWritePrivateProfileString(aInstallableCom, ValueName, 0);
      return 1;
    }
  }
  else
  {
    if ( (wFlags & 1) != 0 && Converter )
    {
      *(_DWORD *)Converter = 1734438227;
      *(_DWORD *)(Converter + 16) = v9;
      *(_DWORD *)(Converter + 20) = v12;
      *(_QWORD *)(Converter + 32) = 0;
      *(_QWORD *)(Converter + 24) = 0;
      *(_QWORD *)(Converter + 40) = lParam;
      LeaveCriticalSection(&ICOpenCritSec);
      return 1;
    }
    LeaveCriticalSection(&ICOpenCritSec);
  }
  return 0;
}

```

## disassembly

```asm
0x1800031d0  push    rbp
0x1800031d2  push    rbx
0x1800031d3  push    rsi
0x1800031d4  push    rdi
0x1800031d5  push    r14
0x1800031d7  push    r15
0x1800031d9  lea     rbp, [rsp-168h]
0x1800031e1  sub     rsp, 268h
0x1800031e8  mov     rax, cs:__security_cookie
0x1800031ef  xor     rax, rsp
0x1800031f2  mov     [rbp+190h+var_40], rax
0x1800031f9  mov     r14, r8
0x1800031fc  mov     edi, edx
0x1800031fe  mov     ebx, ecx
0x180003200  xor     edx, edx; Val
0x180003202  mov     r8d, 200h; Size
0x180003208  lea     rcx, [rsp+290h+pszDest]; void *
0x18000320d  mov     rsi, r9
0x180003210  call    memset_0
0x180003215  lea     rcx, ICOpenCritSec; lpCriticalSection
0x18000321c  call    cs:__imp_EnterCriticalSection
0x180003222  mov     ecx, ebx
0x180003224  call    Fix4CC
0x180003229  mov     ecx, edi
0x18000322b  mov     r15d, eax
0x18000322e  call    Fix4CC
0x180003233  mov     edx, eax
0x180003235  mov     ecx, r15d
0x180003238  mov     r11d, eax
0x18000323b  call    FindConverter
0x180003240  test    rax, rax
0x180003243  jnz     short loc_18000324E
0x180003245  xor     edx, edx
0x180003247  xor     ecx, ecx
0x180003249  call    FindConverter
0x18000324e  mov     ebx, [rbp+190h+wFlags]
0x180003254  test    bl, 2
0x180003257  jz      loc_180003371
0x18000325d  lea     r8, [rsp+290h+ValueName]
0x180003262  mov     edx, r11d
0x180003265  mov     ecx, r15d
0x180003268  call    ictokey
0x18000326d  lea     rcx, [rsp+290h+pszDest]; pszDest
0x180003272  mov     edi, 100h
0x180003277  mov     edx, edi; cchDest
0x180003279  bt      ebx, 0Fh
0x18000327d  jnb     short loc_1800032E0
0x18000327f  mov     r8, r14; pszSrc
0x180003282  call    StringCchCopyW
0x180003287  lea     rcx, [rsp+290h+pszDest]; lpString
0x18000328c  call    cs:__imp_lstrlenW
0x180003292  lea     ebx, [rax+1]
0x180003295  mov     eax, ebx
0x180003297  test    rsi, rsi
0x18000329a  jz      short loc_1800032C4
0x18000329c  sub     rdi, rax
0x18000329f  lea     r11, [rsp+290h+pszDest]
0x1800032a4  lea     r11, [r11+rbx*2]
0x1800032a8  mov     r9, rdi; cchToCopy
0x1800032ab  mov     rcx, r11; pszDest
0x1800032ae  mov     r8, rsi; pszSrc
0x1800032b1  mov     rdx, rdi; cchDest
0x1800032b4  call    StringCchCopyNW
0x1800032b9  mov     rcx, r11; lpString
0x1800032bc  call    cs:__imp_lstrlenW
0x1800032c2  add     eax, ebx
0x1800032c4  lea     rcx, [rax+rax]
0x1800032c8  cmp     rcx, 200h
0x1800032cf  jnb     short loc_1800032DA
0x1800032d1  xor     eax, eax
0x1800032d3  mov     [rsp+rcx+290h+pszDest], ax
0x1800032d8  jmp     short loc_18000332F
0x1800032da  call    __report_rangecheckfailure
0x1800032e0  mov     r9, r14
0x1800032e3  lea     r8, aHs; "%hs"
0x1800032ea  call    StringCchPrintfW
0x1800032ef  lea     rcx, [rsp+290h+pszDest]; lpString
0x1800032f4  call    cs:__imp_lstrlenW
0x1800032fa  test    rsi, rsi
0x1800032fd  jz      short loc_18000332F
0x1800032ff  inc     eax
0x180003301  cmp     eax, edi
0x180003303  jnb     short loc_18000332F
0x180003305  sub     rdi, rax
0x180003308  lea     rbx, [rsp+290h+pszDest]
0x18000330d  lea     rbx, [rbx+rax*2]
0x180003311  mov     r9, rsi
0x180003314  mov     rcx, rbx; pszDest
0x180003317  lea     r8, aHs; "%hs"
0x18000331e  mov     rdx, rdi; cchDest
0x180003321  call    StringCchPrintfW
0x180003326  mov     rcx, rbx; lpString
0x180003329  call    cs:__imp_lstrlenW
0x18000332f  lea     rcx, ICOpenCritSec; lpCriticalSection
0x180003336  call    cs:__imp_LeaveCriticalSection
0x18000333c  lea     r8, [rsp+290h+pszDest]; LPCWSTR
0x180003341  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x180003346  lea     rcx, aDrivers32; "DRIVERS32"
0x18000334d  call    myWritePrivateProfileString
0x180003352  test    eax, eax
0x180003354  jz      short loc_1800033B9
0x180003356  xor     r8d, r8d; LPCWSTR
0x180003359  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x18000335e  lea     rcx, aInstallableCom; "Installable Compressors"
0x180003365  call    myWritePrivateProfileString
0x18000336a  mov     eax, 1
0x18000336f  jmp     short loc_1800033BB
0x180003371  test    bl, 1
0x180003374  jz      short loc_1800033AC
0x180003376  test    rax, rax
0x180003379  jz      short loc_1800033AC
0x18000337b  lea     rcx, ICOpenCritSec; lpCriticalSection
0x180003382  mov     dword ptr [rax], 67616D53h
0x180003388  mov     [rax+10h], r15d
0x18000338c  mov     [rax+14h], r11d
0x180003390  mov     qword ptr [rax+20h], 0
0x180003398  mov     qword ptr [rax+18h], 0
0x1800033a0  mov     [rax+28h], r14
0x1800033a4  call    cs:__imp_LeaveCriticalSection
0x1800033aa  jmp     short loc_18000336A
0x1800033ac  lea     rcx, ICOpenCritSec; lpCriticalSection
0x1800033b3  call    cs:__imp_LeaveCriticalSection
0x1800033b9  xor     eax, eax
0x1800033bb  mov     rcx, [rbp+190h+var_40]
0x1800033c2  xor     rcx, rsp; StackCookie
0x1800033c5  call    __security_check_cookie
0x1800033ca  add     rsp, 268h
0x1800033d1  pop     r15
0x1800033d3  pop     r14
0x1800033d5  pop     rdi
0x1800033d6  pop     rsi
0x1800033d7  pop     rbx
0x1800033d8  pop     rbp
0x1800033d9  retn
```
