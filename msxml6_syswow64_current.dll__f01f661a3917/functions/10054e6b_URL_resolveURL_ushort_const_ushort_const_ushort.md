# URL::resolveURL(ushort const *,ushort const *,ushort * *)

- ea: `0x10054e6b`
- end: `0x10054fb1`
- name: `?resolveURL@URL@@SGJPBG0PAPAG@Z`
- size: `326`
- prototype: `HRESULT __fastcall(wchar_t *relativeURL, const wchar_t *baseURL, wchar_t **resolvedURL)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x10054dcb`
- `0x10131626`
- `0x10131eee`
- `0x1013cf4c`

## callees

- `0x1003f548`
- `0x10040dee`
- `0x10054e6b`
- `0x10065726`
- `0x10067bc0`
- `0x101315a7`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x10054f31`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x10054f31`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x10054f7d`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x10054f7d`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x10054ef0`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x10054ef0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x10054f67`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x10054f67`
- `urlmon!CreateURLMonikerEx` at `0x10054e91`
- `urlmon!CreateURLMonikerEx` at `0x10054eab`
- `urlmon!CreateURLMonikerEx` at `0x10054e91`
- `urlmon!CreateURLMonikerEx` at `0x10054eab`

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
0x10054e6b  mov     edi, edi
0x10054e6d  push    ebp
0x10054e6e  mov     ebp, esp
0x10054e70  push    relativeURL
0x10054e71  push    relativeURL
0x10054e72  push    ebx
0x10054e73  mov     ebx, [ebp+resolvedURL]
0x10054e76  push    esi
0x10054e77  push    edi
0x10054e78  xor     edi, edi
0x10054e7a  mov     esi, relativeURL
0x10054e7c  mov     [ebx], edi
0x10054e7e  test    baseURL, baseURL
0x10054e80  jz      short loc_10054EEF
0x10054e82  xor     eax, eax
0x10054e84  cmp     ax, [baseURL]
0x10054e87  jz      short loc_10054EEF
0x10054e89  push    1; dwFlags
0x10054e8b  lea     eax, [ebp+pBaseMoniker]
0x10054e8e  push    eax; ppmk
0x10054e8f  push    baseURL; szURL
0x10054e90  push    edi; pMkCtx
0x10054e91  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x10054e97  mov     edi, eax
0x10054e99  test    edi, edi
0x10054e9b  js      loc_10054F97
0x10054ea1  push    1; dwFlags
0x10054ea3  lea     eax, [ebp+pMoniker]
0x10054ea6  push    eax; ppmk
0x10054ea7  push    esi; szURL
0x10054ea8  push    [ebp+pBaseMoniker]; pMkCtx
0x10054eab  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x10054eb1  mov     edi, eax
0x10054eb3  test    edi, edi
0x10054eb5  js      short loc_10054ED7
0x10054eb7  mov     relativeURL, [ebp+pMoniker]; pmk
0x10054eba  xor     baseURL, baseURL; pbc
0x10054ebc  push    ebx; resolvedURL
0x10054ebd  call    ?resolveURL@URL@@SGJPAUIMoniker@@PAUIBindCtx@@PAPAG@Z; URL::resolveURL(IMoniker *,IBindCtx *,ushort * *)
0x10054ec2  mov     edi, eax
0x10054ec4  mov     eax, [ebp+pMoniker]
0x10054ec7  push    eax
0x10054ec8  mov     relativeURL, [eax]
0x10054eca  mov     esi, [relativeURL+8]
0x10054ecd  mov     relativeURL, esi; this
0x10054ecf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10054ed5  call    esi
0x10054ed7  mov     eax, [ebp+pBaseMoniker]
0x10054eda  push    eax
0x10054edb  mov     relativeURL, [eax]
0x10054edd  mov     esi, [relativeURL+8]
0x10054ee0  mov     relativeURL, esi; this
0x10054ee2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10054ee8  call    esi
0x10054eea  jmp     CleanUp_24
0x10054eef  push    esi; pszPath
0x10054ef0  call    ds:__imp__PathIsURLW@4; PathIsURLW(x)
0x10054ef6  test    eax, eax
0x10054ef8  jz      short loc_10054F0A
0x10054efa  mov     baseURL, ebx; ppszDup
0x10054efc  mov     relativeURL, esi; psz
0x10054efe  call    ?allocStrWHR@@YGJPBGPAPAG@Z; allocStrWHR(ushort const *,ushort * *)
0x10054f03  mov     edi, eax
0x10054f05  jmp     CleanUp_24
0x10054f0a  xor     baseURL, baseURL; dwFlags
0x10054f0c  mov     relativeURL, 2000h; cb
0x10054f11  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10054f16  mov     [ebx], eax
0x10054f18  test    eax, eax
0x10054f1a  jnz     short loc_10054F23
0x10054f1c  mov     edi, 8007000Eh
0x10054f21  jmp     short loc_10054F97
0x10054f23  push    edi; dwFlags
0x10054f24  lea     relativeURL, [ebp+pMoniker]
0x10054f27  mov     [ebp+pMoniker], 1000h
0x10054f2e  push    relativeURL; pcchUnescaped
0x10054f2f  push    eax; pszUnescaped
0x10054f30  push    esi; pszUrl
0x10054f31  call    ds:__imp__UrlUnescapeW@16; UrlUnescapeW(x,x,x,x)
0x10054f37  mov     edi, eax
0x10054f39  test    edi, edi
0x10054f3b  jns     short loc_10054F4C
0x10054f3d  cmp     edi, 80004003h
0x10054f43  jnz     short loc_10054F97
0x10054f45  mov     edi, 80070057h
0x10054f4a  jmp     short loc_10054F97
0x10054f4c  xor     baseURL, baseURL; dwFlags
0x10054f4e  mov     relativeURL, 2000h; cb
0x10054f53  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10054f58  mov     esi, eax
0x10054f5a  test    esi, esi
0x10054f5c  jz      short loc_10054F1C
0x10054f5e  mov     edi, 1000h
0x10054f63  push    edi; cchBuf
0x10054f64  push    esi; pszBuf
0x10054f65  push    dword ptr [ebx]; pszPath
0x10054f67  call    ds:__imp__PathSearchAndQualifyW@12; PathSearchAndQualifyW(x,x,x)
0x10054f6d  test    eax, eax
0x10054f6f  jz      short loc_10054F87
0x10054f71  push    0; dwFlags
0x10054f73  lea     eax, [ebp+pMoniker]
0x10054f76  mov     [ebp+pMoniker], edi
0x10054f79  push    eax; pcchUrl
0x10054f7a  push    dword ptr [ebx]; pszUrl
0x10054f7c  push    esi; pszPath
0x10054f7d  call    ds:__imp__UrlCreateFromPathW@16; UrlCreateFromPathW(x,x,x,x)
0x10054f83  mov     edi, eax
0x10054f85  jmp     short loc_10054F8C
0x10054f87  mov     edi, 80070057h
0x10054f8c  mov     relativeURL, esi; pv
0x10054f8e  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10054f93  test    edi, edi
0x10054f95  jns     short loc_10054FA8
0x10054f97  mov     relativeURL, [ebx]; pv
0x10054f99  test    relativeURL, relativeURL
0x10054f9b  jz      short loc_10054FA8
0x10054f9d  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10054fa2  mov     dword ptr [ebx], 0
0x10054fa8  mov     eax, edi
0x10054faa  pop     edi
0x10054fab  pop     esi
0x10054fac  pop     ebx
0x10054fad  leave
0x10054fae  retn    4
```
