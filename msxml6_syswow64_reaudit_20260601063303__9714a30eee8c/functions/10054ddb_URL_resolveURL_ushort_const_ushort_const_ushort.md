# URL::resolveURL(ushort const *,ushort const *,ushort * *)

- ea: `0x10054ddb`
- end: `0x10054f21`
- name: `?resolveURL@URL@@SGJPBG0PAPAG@Z`
- size: `326`
- prototype: `HRESULT __fastcall(wchar_t *relativeURL, const wchar_t *baseURL, wchar_t **resolvedURL)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x10054d3b`
- `0x10131736`
- `0x10131ffe`
- `0x1013d05c`

## callees

- `0x1003f4b8`
- `0x10040d5e`
- `0x10054ddb`
- `0x10065686`
- `0x10067b20`
- `0x101316b7`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x10054ea1`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x10054ea1`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x10054eed`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x10054eed`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x10054e60`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x10054e60`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x10054ed7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x10054ed7`
- `urlmon!CreateURLMonikerEx` at `0x10054e01`
- `urlmon!CreateURLMonikerEx` at `0x10054e1b`
- `urlmon!CreateURLMonikerEx` at `0x10054e01`
- `urlmon!CreateURLMonikerEx` at `0x10054e1b`

## pseudocode

```c
HRESULT __fastcall URL::resolveURL(wchar_t *relativeURL, const wchar_t *baseURL, wchar_t **resolvedURL)
{
  HRESULT v4; // edi
  wchar_t *v5; // eax
  HRESULT v6; // eax
  wchar_t *v7; // eax
  wchar_t *v8; // esi
  IMoniker *pBaseMoniker; // [esp+Ch] [ebp-8h] BYREF
  IMoniker *pMoniker; // [esp+10h] [ebp-4h] BYREF

  *resolvedURL = 0;
  if ( baseURL && *baseURL )
  {
    v4 = CreateURLMonikerEx(0, baseURL, &pBaseMoniker, 1u);
    if ( v4 >= 0 )
    {
      v4 = CreateURLMonikerEx(pBaseMoniker, relativeURL, &pMoniker, 1u);
      if ( v4 >= 0 )
      {
        v4 = URL::resolveURL(pMoniker, 0, resolvedURL);
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pMoniker->Release)(
          pMoniker->Release,
          pMoniker);
      }
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pBaseMoniker->Release)(
        pBaseMoniker->Release,
        pBaseMoniker);
CleanUp_24:
      if ( v4 >= 0 )
        return v4;
    }
  }
  else
  {
    if ( PathIsURLW(relativeURL) )
    {
      v4 = allocStrWHR(relativeURL, resolvedURL);
      goto CleanUp_24;
    }
    v5 = (wchar_t *)_MemAlloc(0x2000u, 0);
    *resolvedURL = v5;
    if ( v5 )
    {
      pMoniker = (IMoniker *)4096;
      v6 = UrlUnescapeW(relativeURL, v5, (DWORD *)&pMoniker, 0);
      v4 = v6;
      if ( v6 < 0 )
      {
        if ( v6 == -2147467261 )
          v4 = -2147024809;
        goto LABEL_20;
      }
      v7 = (wchar_t *)_MemAlloc(0x2000u, 0);
      v8 = v7;
      if ( v7 )
      {
        if ( PathSearchAndQualifyW(*resolvedURL, v7, 0x1000u) )
        {
          pMoniker = (IMoniker *)4096;
          v4 = UrlCreateFromPathW(v8, *resolvedURL, (DWORD *)&pMoniker, 0);
        }
        else
        {
          v4 = -2147024809;
        }
        MemFree(v8);
        goto CleanUp_24;
      }
    }
    v4 = -2147024882;
  }
LABEL_20:
  if ( *resolvedURL )
  {
    MemFree(*resolvedURL);
    *resolvedURL = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x10054ddb  mov     edi, edi
0x10054ddd  push    ebp
0x10054dde  mov     ebp, esp
0x10054de0  push    relativeURL
0x10054de1  push    relativeURL
0x10054de2  push    ebx
0x10054de3  mov     ebx, [ebp+resolvedURL]
0x10054de6  push    esi
0x10054de7  push    edi
0x10054de8  xor     edi, edi
0x10054dea  mov     esi, relativeURL
0x10054dec  mov     [ebx], edi
0x10054dee  test    baseURL, baseURL
0x10054df0  jz      short loc_10054E5F
0x10054df2  xor     eax, eax
0x10054df4  cmp     ax, [baseURL]
0x10054df7  jz      short loc_10054E5F
0x10054df9  push    1; dwFlags
0x10054dfb  lea     eax, [ebp+pBaseMoniker]
0x10054dfe  push    eax; ppmk
0x10054dff  push    baseURL; szURL
0x10054e00  push    edi; pMkCtx
0x10054e01  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x10054e07  mov     edi, eax
0x10054e09  test    edi, edi
0x10054e0b  js      loc_10054F07
0x10054e11  push    1; dwFlags
0x10054e13  lea     eax, [ebp+pMoniker]
0x10054e16  push    eax; ppmk
0x10054e17  push    esi; szURL
0x10054e18  push    [ebp+pBaseMoniker]; pMkCtx
0x10054e1b  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x10054e21  mov     edi, eax
0x10054e23  test    edi, edi
0x10054e25  js      short loc_10054E47
0x10054e27  mov     relativeURL, [ebp+pMoniker]; pmk
0x10054e2a  xor     baseURL, baseURL; pbc
0x10054e2c  push    ebx; resolvedURL
0x10054e2d  call    ?resolveURL@URL@@SGJPAUIMoniker@@PAUIBindCtx@@PAPAG@Z; URL::resolveURL(IMoniker *,IBindCtx *,ushort * *)
0x10054e32  mov     edi, eax
0x10054e34  mov     eax, [ebp+pMoniker]
0x10054e37  push    eax
0x10054e38  mov     relativeURL, [eax]
0x10054e3a  mov     esi, [relativeURL+8]
0x10054e3d  mov     relativeURL, esi; this
0x10054e3f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10054e45  call    esi
0x10054e47  mov     eax, [ebp+pBaseMoniker]
0x10054e4a  push    eax
0x10054e4b  mov     relativeURL, [eax]
0x10054e4d  mov     esi, [relativeURL+8]
0x10054e50  mov     relativeURL, esi; this
0x10054e52  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10054e58  call    esi
0x10054e5a  jmp     CleanUp_24
0x10054e5f  push    esi; pszPath
0x10054e60  call    ds:__imp__PathIsURLW@4; PathIsURLW(x)
0x10054e66  test    eax, eax
0x10054e68  jz      short loc_10054E7A
0x10054e6a  mov     baseURL, ebx; ppszDup
0x10054e6c  mov     relativeURL, esi; psz
0x10054e6e  call    ?allocStrWHR@@YGJPBGPAPAG@Z; allocStrWHR(ushort const *,ushort * *)
0x10054e73  mov     edi, eax
0x10054e75  jmp     CleanUp_24
0x10054e7a  xor     baseURL, baseURL; dwFlags
0x10054e7c  mov     relativeURL, 2000h; cb
0x10054e81  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10054e86  mov     [ebx], eax
0x10054e88  test    eax, eax
0x10054e8a  jnz     short loc_10054E93
0x10054e8c  mov     edi, 8007000Eh
0x10054e91  jmp     short loc_10054F07
0x10054e93  push    edi; dwFlags
0x10054e94  lea     relativeURL, [ebp+pMoniker]
0x10054e97  mov     [ebp+pMoniker], 1000h
0x10054e9e  push    relativeURL; pcchUnescaped
0x10054e9f  push    eax; pszUnescaped
0x10054ea0  push    esi; pszUrl
0x10054ea1  call    ds:__imp__UrlUnescapeW@16; UrlUnescapeW(x,x,x,x)
0x10054ea7  mov     edi, eax
0x10054ea9  test    edi, edi
0x10054eab  jns     short loc_10054EBC
0x10054ead  cmp     edi, 80004003h
0x10054eb3  jnz     short loc_10054F07
0x10054eb5  mov     edi, 80070057h
0x10054eba  jmp     short loc_10054F07
0x10054ebc  xor     baseURL, baseURL; dwFlags
0x10054ebe  mov     relativeURL, 2000h; cb
0x10054ec3  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10054ec8  mov     esi, eax
0x10054eca  test    esi, esi
0x10054ecc  jz      short loc_10054E8C
0x10054ece  mov     edi, 1000h
0x10054ed3  push    edi; cchBuf
0x10054ed4  push    esi; pszBuf
0x10054ed5  push    dword ptr [ebx]; pszPath
0x10054ed7  call    ds:__imp__PathSearchAndQualifyW@12; PathSearchAndQualifyW(x,x,x)
0x10054edd  test    eax, eax
0x10054edf  jz      short loc_10054EF7
0x10054ee1  push    0; dwFlags
0x10054ee3  lea     eax, [ebp+pMoniker]
0x10054ee6  mov     [ebp+pMoniker], edi
0x10054ee9  push    eax; pcchUrl
0x10054eea  push    dword ptr [ebx]; pszUrl
0x10054eec  push    esi; pszPath
0x10054eed  call    ds:__imp__UrlCreateFromPathW@16; UrlCreateFromPathW(x,x,x,x)
0x10054ef3  mov     edi, eax
0x10054ef5  jmp     short loc_10054EFC
0x10054ef7  mov     edi, 80070057h
0x10054efc  mov     relativeURL, esi; pv
0x10054efe  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10054f03  test    edi, edi
0x10054f05  jns     short loc_10054F18
0x10054f07  mov     relativeURL, [ebx]; pv
0x10054f09  test    relativeURL, relativeURL
0x10054f0b  jz      short loc_10054F18
0x10054f0d  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10054f12  mov     dword ptr [ebx], 0
0x10054f18  mov     eax, edi
0x10054f1a  pop     edi
0x10054f1b  pop     esi
0x10054f1c  pop     ebx
0x10054f1d  leave
0x10054f1e  retn    4
```
