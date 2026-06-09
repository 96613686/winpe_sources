# URL::resolveURL(ushort const *,ushort const *,ushort * *)

- ea: `0x1800849c0`
- end: `0x180084b40`
- name: `?resolveURL@URL@@SAJPEBG0PEAPEAG@Z`
- size: `384`
- prototype: `__int64 __fastcall(wchar_t *relativeURL, const wchar_t *baseURL, wchar_t **resolvedURL)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180084874`
- `0x1800848b4`
- `0x180084978`
- `0x1801540f0`
- `0x18015b884`

## callees

- `0x18000ae54`
- `0x18003617c`
- `0x1800641d0`
- `0x1800849c0`
- `0x18015382c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180084b02`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180084b02`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180084aaa`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180084aaa`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180084a5c`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180084a5c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x180084ae4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x180084ae4`
- `urlmon!CreateURLMonikerEx` at `0x1800849fa`
- `urlmon!CreateURLMonikerEx` at `0x180084a1b`
- `urlmon!CreateURLMonikerEx` at `0x1800849fa`
- `urlmon!CreateURLMonikerEx` at `0x180084a1b`

## pseudocode

```c
__int64 __fastcall URL::resolveURL(wchar_t *relativeURL, const wchar_t *baseURL, wchar_t **resolvedURL)
{
  HRESULT v5; // ebx
  wchar_t *v6; // rax
  HRESULT v7; // eax
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  wchar_t *v10; // rdx
  IMoniker *pMoniker; // [rsp+48h] [rbp+28h] BYREF
  IMoniker *pBaseMoniker; // [rsp+50h] [rbp+30h] BYREF

  *resolvedURL = 0;
  if ( baseURL && *baseURL )
  {
    pBaseMoniker = 0;
    pMoniker = 0;
    v5 = CreateURLMonikerEx(0, baseURL, &pBaseMoniker, 1u);
    if ( v5 >= 0 )
    {
      v5 = CreateURLMonikerEx(pBaseMoniker, relativeURL, &pMoniker, 1u);
      if ( v5 >= 0 )
      {
        v5 = URL::resolveURL(pMoniker, 0, resolvedURL);
        pMoniker->Release(pMoniker);
      }
      pBaseMoniker->Release(pBaseMoniker);
$CleanUp_81:
      if ( v5 >= 0 )
        return (unsigned int)v5;
    }
  }
  else
  {
    if ( PathIsURLW(relativeURL) )
    {
      v5 = allocStrWHR(relativeURL, resolvedURL);
      goto $CleanUp_81;
    }
    v6 = (wchar_t *)_MemAlloc(0x2000u, 0);
    *resolvedURL = v6;
    if ( v6 )
    {
      LODWORD(pMoniker) = 4096;
      v7 = UrlUnescapeW(relativeURL, v6, (DWORD *)&pMoniker, 0);
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( v7 == -2147467261 )
          v5 = -2147024809;
        goto LABEL_20;
      }
      v8 = (wchar_t *)_MemAlloc(0x2000u, 0);
      v9 = v8;
      if ( v8 )
      {
        if ( PathSearchAndQualifyW(*resolvedURL, v8, 0x1000u) )
        {
          v10 = *resolvedURL;
          LODWORD(pMoniker) = 4096;
          v5 = UrlCreateFromPathW(v9, v10, (DWORD *)&pMoniker, 0);
        }
        else
        {
          v5 = -2147024809;
        }
        MemFree(v9);
        goto $CleanUp_81;
      }
    }
    v5 = -2147024882;
  }
LABEL_20:
  if ( *resolvedURL )
  {
    MemFree(*resolvedURL);
    *resolvedURL = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800849c0  mov     [rsp-18h+arg_0], rbx
0x1800849c5  push    rbp
0x1800849c6  push    rsi
0x1800849c7  push    rdi
0x1800849c8  mov     rbp, rsp
0x1800849cb  sub     rsp, 20h
0x1800849cf  mov     qword ptr [resolvedURL], 0
0x1800849d6  mov     rdi, resolvedURL
0x1800849d9  mov     rsi, relativeURL
0x1800849dc  test    baseURL, baseURL
0x1800849df  jz      short loc_180084A5C
0x1800849e1  xor     eax, eax
0x1800849e3  cmp     ax, [baseURL]
0x1800849e6  jz      short loc_180084A5C
0x1800849e8  lea     r9d, [rax+1]; dwFlags
0x1800849ec  mov     [rbp+pBaseMoniker], rax
0x1800849f0  lea     resolvedURL, [rbp+pBaseMoniker]; ppmk
0x1800849f4  mov     [rbp+pMoniker], rax
0x1800849f8  xor     ecx, ecx; pMkCtx
0x1800849fa  call    cs:__imp_CreateURLMonikerEx
0x180084a00  mov     ebx, eax
0x180084a02  test    eax, eax
0x180084a04  js      loc_180084B1D
0x180084a0a  mov     relativeURL, [rbp+pBaseMoniker]; pMkCtx
0x180084a0e  lea     resolvedURL, [rbp+pMoniker]; ppmk
0x180084a12  mov     r9d, 1; dwFlags
0x180084a18  mov     baseURL, rsi; szURL
0x180084a1b  call    cs:__imp_CreateURLMonikerEx
0x180084a21  mov     ebx, eax
0x180084a23  test    eax, eax
0x180084a25  js      short loc_180084A47
0x180084a27  mov     relativeURL, [rbp+pMoniker]; pmk
0x180084a2b  mov     resolvedURL, rdi; resolvedURL
0x180084a2e  xor     edx, edx; pbc
0x180084a30  call    ?resolveURL@URL@@SAJPEAUIMoniker@@PEAUIBindCtx@@PEAPEAG@Z; URL::resolveURL(IMoniker *,IBindCtx *,ushort * *)
0x180084a35  mov     relativeURL, [rbp+pMoniker]
0x180084a39  mov     ebx, eax
0x180084a3b  mov     rax, [relativeURL]
0x180084a3e  mov     rax, [rax+10h]
0x180084a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a47  mov     relativeURL, [rbp+pBaseMoniker]
0x180084a4b  mov     rax, [relativeURL]
0x180084a4e  mov     rax, [rax+10h]
0x180084a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a57  jmp     $CleanUp_81
0x180084a5c  call    cs:__imp_PathIsURLW
0x180084a62  test    eax, eax
0x180084a64  jz      short loc_180084A78
0x180084a66  mov     baseURL, rdi; ppszDup
0x180084a69  mov     relativeURL, rsi; psz
0x180084a6c  call    ?allocStrWHR@@YAJPEBGPEAPEAG@Z; allocStrWHR(ushort const *,ushort * *)
0x180084a71  mov     ebx, eax
0x180084a73  jmp     $CleanUp_81
0x180084a78  xor     edx, edx; dwFlags
0x180084a7a  mov     ecx, 2000h; cb
0x180084a7f  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180084a84  mov     [rdi], rax
0x180084a87  test    rax, rax
0x180084a8a  jnz     short loc_180084A96
0x180084a8c  mov     ebx, 8007000Eh
0x180084a91  jmp     loc_180084B1D
0x180084a96  xor     r9d, r9d; dwFlags
0x180084a99  mov     dword ptr [rbp+pMoniker], 1000h
0x180084aa0  lea     resolvedURL, [rbp+pMoniker]; pcchUnescaped
0x180084aa4  mov     baseURL, rax; pszUnescaped
0x180084aa7  mov     relativeURL, rsi; pszUrl
0x180084aaa  call    cs:__imp_UrlUnescapeW
0x180084ab0  mov     ebx, eax
0x180084ab2  test    eax, eax
0x180084ab4  jns     short loc_180084AC4
0x180084ab6  cmp     eax, 80004003h
0x180084abb  jnz     short loc_180084B1D
0x180084abd  mov     ebx, 80070057h
0x180084ac2  jmp     short loc_180084B1D
0x180084ac4  xor     edx, edx; dwFlags
0x180084ac6  mov     ecx, 2000h; cb
0x180084acb  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180084ad0  mov     rsi, rax
0x180084ad3  test    rax, rax
0x180084ad6  jz      short loc_180084A8C
0x180084ad8  mov     relativeURL, [rdi]; pszPath
0x180084adb  mov     r8d, 1000h; cchBuf
0x180084ae1  mov     baseURL, rax; pszBuf
0x180084ae4  call    cs:__imp_PathSearchAndQualifyW
0x180084aea  test    eax, eax
0x180084aec  jz      short loc_180084B0C
0x180084aee  mov     baseURL, [rdi]; pszUrl
0x180084af1  lea     resolvedURL, [rbp+pMoniker]; pcchUrl
0x180084af5  xor     r9d, r9d; dwFlags
0x180084af8  mov     dword ptr [rbp+pMoniker], 1000h
0x180084aff  mov     relativeURL, rsi; pszPath
0x180084b02  call    cs:__imp_UrlCreateFromPathW
0x180084b08  mov     ebx, eax
0x180084b0a  jmp     short loc_180084B11
0x180084b0c  mov     ebx, 80070057h
0x180084b11  mov     relativeURL, rsi; pv
0x180084b14  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180084b19  test    ebx, ebx
0x180084b1b  jns     short loc_180084B31
0x180084b1d  mov     relativeURL, [rdi]; pv
0x180084b20  test    relativeURL, relativeURL
0x180084b23  jz      short loc_180084B31
0x180084b25  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180084b2a  mov     qword ptr [rdi], 0
0x180084b31  mov     eax, ebx
0x180084b33  mov     rbx, [rsp+20h+arg_0]
0x180084b38  add     rsp, 20h
0x180084b3c  pop     rdi
0x180084b3d  pop     rsi
0x180084b3e  pop     rbp
0x180084b3f  retn
```
