# myLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x1800217d4`
- end: `0x18002191c`
- name: `?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `328`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018310`
- `0x180019998`
- `0x18001a8a4`

## callees

- `0x18000b940`
- `0x180021438`
- `0x1800217d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021904`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021904`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800218a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800218a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021836`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800218f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800218f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800217f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180021857`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800217f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180021857`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002180a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800218ee`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002180a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800218ee`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x1800218c9`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x1800218c9`

## pseudocode

```c
HINSTANCE __fastcall myLoadSystem32LibraryEx(const unsigned __int16 *a1, void *a2)
{
  HMODULE Library; // rsi
  UINT SystemDirectoryW; // eax
  UINT v5; // ebp
  DWORD v6; // ebx
  int v7; // edx
  unsigned int v8; // ecx
  __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // r14
  WCHAR *v12; // rax
  unsigned __int16 *v13; // rdi
  UINT v14; // eax

  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v5 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    v6 = myHLastError();
    v7 = v6;
    v8 = 82117066;
LABEL_3:
    CSPrintErrorLineFile(v8, v7);
LABEL_20:
    SetLastError(v6);
    return Library;
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  v11 = v10 + SystemDirectoryW + 1 + 1LL;
  v12 = (WCHAR *)LocalAlloc(0, 2 * v11);
  v13 = v12;
  if ( !v12 )
  {
    v6 = -2147024882;
    v8 = 82706890;
    v7 = -2147024882;
    goto LABEL_3;
  }
  v14 = GetSystemDirectoryW(v12, v5);
  if ( v14 <= v5 && v14 )
  {
    do
      ++v9;
    while ( v13[v9] );
    if ( v13[v9 - 1] != 92 )
      StringCchCatW(v13, v11, L"\\");
    StringCchCatW(v13, v11, a1);
    Library = LoadLibraryExW(v13, 0, 0);
    if ( Library )
    {
      v6 = 0;
    }
    else
    {
      v6 = myHLastError();
      CSPrintErrorLineFileData2(v13, 0x50A01CAu, v6, -2147024894);
    }
  }
  else
  {
    v6 = myHLastError();
    if ( !v6 )
      v6 = -2147024785;
    CSPrintErrorLineFile(0x4F801CAu, v6);
  }
  LocalFree(v13);
  if ( !Library )
    goto LABEL_20;
  return Library;
}

```

## disassembly

```asm
0x1800217d4  push    rbx
0x1800217d6  push    rbp
0x1800217d7  push    rsi
0x1800217d8  push    rdi
0x1800217d9  push    r12
0x1800217db  push    r14
0x1800217dd  push    r15
0x1800217df  sub     rsp, 20h
0x1800217e3  mov     r15, rcx
0x1800217e6  xor     r12d, r12d
0x1800217e9  xor     ecx, ecx; lpBuffer
0x1800217eb  xor     edx, edx; uSize
0x1800217ed  mov     esi, r12d
0x1800217f0  call    cs:__imp_GetSystemDirectoryW
0x1800217f6  mov     ebp, eax
0x1800217f8  test    eax, eax
0x1800217fa  jnz     short loc_180021815
0x1800217fc  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180021801  mov     ebx, eax
0x180021803  mov     edx, eax
0x180021805  mov     ecx, 4E501CAh
0x18002180a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180021810  jmp     loc_180021902
0x180021815  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021819  mov     rdx, rbx
0x18002181c  inc     rdx
0x18002181f  cmp     [r15+rdx*2], r12w
0x180021824  jnz     short loc_18002181C
0x180021826  lea     r14d, [rax+1]
0x18002182a  xor     ecx, ecx; uFlags
0x18002182c  inc     r14
0x18002182f  add     r14, rdx
0x180021832  lea     rdx, [r14+r14]; uBytes
0x180021836  call    cs:__imp_LocalAlloc
0x18002183c  mov     rdi, rax
0x18002183f  test    rax, rax
0x180021842  jnz     short loc_180021852
0x180021844  mov     ebx, 8007000Eh
0x180021849  mov     ecx, 4EE01CAh
0x18002184e  mov     edx, ebx
0x180021850  jmp     short loc_18002180A
0x180021852  mov     edx, ebp; uSize
0x180021854  mov     rcx, rdi; lpBuffer
0x180021857  call    cs:__imp_GetSystemDirectoryW
0x18002185d  cmp     eax, ebp
0x18002185f  ja      short loc_1800218D6
0x180021861  test    eax, eax
0x180021863  jz      short loc_1800218D6
0x180021865  inc     rbx
0x180021868  cmp     [rdi+rbx*2], r12w
0x18002186d  jnz     short loc_180021865
0x18002186f  mov     eax, 5Ch ; '\'
0x180021874  cmp     ax, [rdi+rbx*2-2]
0x180021879  jz      short loc_18002188D
0x18002187b  lea     r8, SubStr; "\\"
0x180021882  mov     rdx, r14; unsigned __int64
0x180021885  mov     rcx, rdi; unsigned __int16 *
0x180021888  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002188d  mov     r8, r15; unsigned __int16 *
0x180021890  mov     rdx, r14; unsigned __int64
0x180021893  mov     rcx, rdi; unsigned __int16 *
0x180021896  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002189b  xor     r8d, r8d; dwFlags
0x18002189e  xor     edx, edx; hFile
0x1800218a0  mov     rcx, rdi; lpLibFileName
0x1800218a3  call    cs:__imp_LoadLibraryExW
0x1800218a9  mov     rsi, rax
0x1800218ac  test    rax, rax
0x1800218af  jnz     short loc_1800218D1
0x1800218b1  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800218b6  mov     r9d, 80070002h
0x1800218bc  mov     r8d, eax
0x1800218bf  mov     edx, 50A01CAh
0x1800218c4  mov     rcx, rdi
0x1800218c7  mov     ebx, eax
0x1800218c9  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800218cf  jmp     short loc_1800218F4
0x1800218d1  mov     ebx, r12d
0x1800218d4  jmp     short loc_1800218F4
0x1800218d6  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800218db  mov     ebx, eax
0x1800218dd  mov     ecx, 4F801CAh
0x1800218e2  test    ebx, ebx
0x1800218e4  mov     eax, 8007006Fh
0x1800218e9  cmovz   ebx, eax
0x1800218ec  mov     edx, ebx
0x1800218ee  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800218f4  mov     rcx, rdi; hMem
0x1800218f7  call    cs:__imp_LocalFree
0x1800218fd  test    rsi, rsi
0x180021900  jnz     short loc_18002190A
0x180021902  mov     ecx, ebx; dwErrCode
0x180021904  call    cs:__imp_SetLastError
0x18002190a  mov     rax, rsi
0x18002190d  add     rsp, 20h
0x180021911  pop     r15
0x180021913  pop     r14
0x180021915  pop     r12
0x180021917  pop     rdi
0x180021918  pop     rsi
0x180021919  pop     rbp
0x18002191a  pop     rbx
0x18002191b  retn
```
