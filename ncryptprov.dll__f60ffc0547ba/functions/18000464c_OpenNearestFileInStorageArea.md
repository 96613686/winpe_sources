# OpenNearestFileInStorageArea

- ea: `0x18000464c`
- end: `0x180004848`
- name: `OpenNearestFileInStorageArea`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006e80`
- `0x18000ed10`

## callees

- `0x18000464c`
- `0x180004c04`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x180010530`
- `0x180017a50`
- `0x180038970`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800046e3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800046e3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800047d7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800047d7`

## string_xrefs

- `0x180004775`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x1800047ec`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180004818`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall OpenNearestFileInStorageArea(
        unsigned int a1,
        __int64 a2,
        _WORD *a3,
        _WORD *a4,
        wchar_t *pszDest,
        __int64 a6,
        _QWORD *a7)
{
  int v10; // edx
  unsigned int KeyFileFullPath; // ebx
  int v12; // r8d
  HANDLE FirstFile; // rsi
  int v15; // edx
  int v16; // r8d
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-298h] BYREF
  _BYTE FindFileData[44]; // [rsp+50h] [rbp-288h] BYREF
  wchar_t pszSrc[274]; // [rsp+7Ch] [rbp-25Ch] BYREF

  lpFileName[0] = 0;
  memset_0(FindFileData, 0, 0x250u);
  *a7 = -1;
  KeyFileFullPath = GetKeyFileFullPath(a3, a4, lpFileName);
  if ( KeyFileFullPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v12,
        (unsigned int)"Status",
        KeyFileFullPath,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        72);
  }
  else
  {
    FirstFile = FindFirstFileExW(lpFileName[0], FindExInfoStandard, FindFileData, FindExSearchNameMatch, 0, 0);
    if ( FirstFile == (HANDLE)-1LL )
    {
      KeyFileFullPath = GetLastError();
      if ( KeyFileFullPath - 2 > 1 )
        DebugTraceError(KeyFileFullPath, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 863);
      else
        KeyFileFullPath = -2146893802;
    }
    else
    {
      KeyFileFullPath = OpenFileInStorageArea(a1, 0x80000000, a3, pszSrc, a7);
      if ( KeyFileFullPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            v16,
            (unsigned int)"Status",
            KeyFileFullPath,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
            108);
      }
      else
      {
        StringCchCopyW(pszDest, 0x6Eu, pszSrc);
        KeyFileFullPath = 0;
      }
      FindClose(FirstFile);
    }
  }
  if ( lpFileName[0] )
    MSCryptFree(lpFileName[0]);
  return KeyFileFullPath;
}

```

## disassembly

```asm
0x18000464c  mov     [rsp+arg_8], rbx
0x180004651  push    rbp
0x180004652  push    rsi
0x180004653  push    r12
0x180004655  push    r14
0x180004657  push    r15
0x180004659  sub     rsp, 2B0h
0x180004660  mov     rax, cs:__security_cookie
0x180004667  xor     rax, rsp
0x18000466a  mov     [rsp+2D8h+var_38], rax
0x180004672  mov     r15, [rsp+2D8h+pszDest]
0x18000467a  mov     rbp, r8
0x18000467d  mov     r14, [rsp+2D8h+arg_30]
0x180004685  mov     r12d, ecx
0x180004688  mov     r8d, 250h; Size
0x18000468e  mov     [rsp+2D8h+lpFileName], 0
0x180004697  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x18000469c  xor     edx, edx; Val
0x18000469e  mov     rbx, r9
0x1800046a1  call    memset_0
0x1800046a6  lea     r8, [rsp+2D8h+lpFileName]
0x1800046ab  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800046b2  mov     rdx, rbx; void *
0x1800046b5  mov     rcx, rbp; Src
0x1800046b8  call    GetKeyFileFullPath
0x1800046bd  mov     ebx, eax
0x1800046bf  test    eax, eax
0x1800046c1  jnz     loc_180004758
0x1800046c7  mov     rcx, [rsp+2D8h+lpFileName]; lpFileName
0x1800046cc  lea     r8, [rsp+2D8h+FindFileData]; lpFindFileData
0x1800046d1  mov     [rsp+2D8h+dwAdditionalFlags], eax; dwAdditionalFlags
0x1800046d5  xor     r9d, r9d; fSearchOp
0x1800046d8  xor     edx, edx; fInfoLevelId
0x1800046da  mov     [rsp+2D8h+lpSearchFilter], 0; lpSearchFilter
0x1800046e3  call    cs:__imp_FindFirstFileExW
0x1800046ea  nop     dword ptr [rax+rax+00h]
0x1800046ef  mov     rsi, rax
0x1800046f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800046f6  jnz     loc_18000479B
0x1800046fc  call    cs:__imp_GetLastError
0x180004703  nop     dword ptr [rax+rax+00h]
0x180004708  mov     ebx, eax
0x18000470a  add     eax, 0FFFFFFFEh
0x18000470d  cmp     eax, 1
0x180004710  ja      loc_180004812
0x180004716  mov     ebx, 80090016h
0x18000471b  cmp     [rsp+2D8h+lpFileName], 0
0x180004721  jz      short loc_18000472D
0x180004723  mov     rcx, [rsp+2D8h+lpFileName]
0x180004728  call    MSCryptFree
0x18000472d  mov     eax, ebx
0x18000472f  mov     rcx, [rsp+2D8h+var_38]
0x180004737  xor     rcx, rsp; StackCookie
0x18000473a  call    __security_check_cookie
0x18000473f  mov     rbx, [rsp+2D8h+arg_8]
0x180004747  add     rsp, 2B0h
0x18000474e  pop     r15
0x180004750  pop     r14
0x180004752  pop     r12
0x180004754  pop     rsi
0x180004755  pop     rbp
0x180004756  retn
0x180004758  mov     rcx, cs:WPP_GLOBAL_Control
0x18000475f  lea     rax, WPP_GLOBAL_Control
0x180004766  cmp     rcx, rax
0x180004769  jz      short loc_18000471B
0x18000476b  test    byte ptr [rcx+1Ch], 1
0x18000476f  jz      short loc_18000471B
0x180004771  mov     rcx, [rcx+10h]
0x180004775  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000477c  mov     [rsp+2D8h+var_2A8], 348h
0x180004784  lea     r9, aStatus; "Status"
0x18000478b  mov     qword ptr [rsp+2D8h+dwAdditionalFlags], rax
0x180004790  mov     dword ptr [rsp+2D8h+lpSearchFilter], ebx
0x180004794  call    WPP_SF_sDsd
0x180004799  jmp     short loc_18000471B
0x18000479b  lea     r9, [rsp+2D8h+pszSrc]
0x1800047a0  mov     [rsp+2D8h+lpSearchFilter], r14
0x1800047a5  mov     r8, rbp
0x1800047a8  mov     edx, 80000000h
0x1800047ad  mov     ecx, r12d
0x1800047b0  call    OpenFileInStorageArea
0x1800047b5  mov     ebx, eax
0x1800047b7  test    eax, eax
0x1800047b9  jz      short loc_180004832
0x1800047bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047c2  lea     rax, WPP_GLOBAL_Control
0x1800047c9  cmp     rcx, rax
0x1800047cc  jz      short loc_1800047D4
0x1800047ce  test    byte ptr [rcx+1Ch], 1
0x1800047d2  jnz     short loc_1800047E8
0x1800047d4  mov     rcx, rsi; hFindFile
0x1800047d7  call    cs:__imp_FindClose
0x1800047de  nop     dword ptr [rax+rax+00h]
0x1800047e3  jmp     loc_18000471B
0x1800047e8  mov     rcx, [rcx+10h]
0x1800047ec  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800047f3  mov     [rsp+2D8h+var_2A8], 36Ch
0x1800047fb  lea     r9, aStatus; "Status"
0x180004802  mov     qword ptr [rsp+2D8h+dwAdditionalFlags], rax
0x180004807  mov     dword ptr [rsp+2D8h+lpSearchFilter], ebx
0x18000480b  call    WPP_SF_sDsd
0x180004810  jmp     short loc_1800047D4
0x180004812  mov     r9d, 35Fh
0x180004818  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000481f  lea     rdx, aStatus; "Status"
0x180004826  mov     ecx, ebx
0x180004828  call    DebugTraceError
0x18000482d  jmp     loc_18000471B
0x180004832  lea     r8, [rsp+2D8h+pszSrc]; pszSrc
0x180004837  mov     edx, 6Eh ; 'n'; cchDest
0x18000483c  mov     rcx, r15; pszDest
0x18000483f  call    StringCchCopyW
0x180004844  xor     ebx, ebx
0x180004846  jmp     short loc_1800047D4
```
