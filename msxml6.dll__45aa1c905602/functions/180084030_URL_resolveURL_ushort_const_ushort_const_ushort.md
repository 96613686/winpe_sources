# URL::resolveURL(ushort const *,ushort const *,ushort * *)

- ea: `0x180084030`
- end: `0x1800841dd`
- name: `?resolveURL@URL@@SAJPEBG0PEAPEAG@Z`
- size: `429`
- prototype: `HRESULT __fastcall(const wchar_t *relativeURL, const wchar_t *baseURL, wchar_t **resolvedURL)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180083ee4`
- `0x180083f24`
- `0x180083fe8`
- `0x180157690`
- `0x18015f0d4`

## callees

- `0x1800101e4`
- `0x180017480`
- `0x18003938c`
- `0x180084030`
- `0x180156d68`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180084198`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180084198`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180084134`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180084134`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1800840e0`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1800840e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x180084174`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSearchAndQualifyW` at `0x180084174`
- `urlmon!CreateURLMonikerEx` at `0x180084072`
- `urlmon!CreateURLMonikerEx` at `0x180084099`
- `urlmon!CreateURLMonikerEx` at `0x180084072`
- `urlmon!CreateURLMonikerEx` at `0x180084099`

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
$CleanUp_80:
      if ( v5 >= 0 )
        return (unsigned int)v5;
    }
  }
  else
  {
    if ( PathIsURLW(relativeURL) )
    {
      v5 = allocStrWHR(relativeURL, resolvedURL);
      goto $CleanUp_80;
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
        goto $CleanUp_80;
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
0x180084030  mov     [rsp-18h+arg_0], rbx
0x180084035  push    rbp
0x180084036  push    rsi
0x180084037  push    rdi
0x180084038  mov     rbp, rsp
0x18008403b  sub     rsp, 20h
0x18008403f  mov     qword ptr [resolvedURL], 0
0x180084046  mov     rdi, resolvedURL
0x180084049  mov     rsi, relativeURL
0x18008404c  test    baseURL, baseURL
0x18008404f  jz      loc_1800840E0
0x180084055  xor     eax, eax
0x180084057  cmp     ax, [baseURL]
0x18008405a  jz      loc_1800840E0
0x180084060  lea     r9d, [rax+1]; dwFlags
0x180084064  mov     [rbp+pBaseMoniker], rax
0x180084068  lea     resolvedURL, [rbp+pBaseMoniker]; ppmk
0x18008406c  mov     [rbp+pMoniker], rax
0x180084070  xor     ecx, ecx; pMkCtx
0x180084072  call    cs:__imp_CreateURLMonikerEx
0x180084079  nop     dword ptr [rax+rax+00h]
0x18008407e  mov     ebx, eax
0x180084080  test    eax, eax
0x180084082  js      loc_1800841B9
0x180084088  mov     relativeURL, [rbp+pBaseMoniker]; pMkCtx
0x18008408c  lea     resolvedURL, [rbp+pMoniker]; ppmk
0x180084090  mov     r9d, 1; dwFlags
0x180084096  mov     baseURL, rsi; szURL
0x180084099  call    cs:__imp_CreateURLMonikerEx
0x1800840a0  nop     dword ptr [rax+rax+00h]
0x1800840a5  mov     ebx, eax
0x1800840a7  test    eax, eax
0x1800840a9  js      short loc_1800840CB
0x1800840ab  mov     relativeURL, [rbp+pMoniker]; pmk
0x1800840af  mov     resolvedURL, rdi; resolvedURL
0x1800840b2  xor     edx, edx; pbc
0x1800840b4  call    ?resolveURL@URL@@SAJPEAUIMoniker@@PEAUIBindCtx@@PEAPEAG@Z; URL::resolveURL(IMoniker *,IBindCtx *,ushort * *)
0x1800840b9  mov     relativeURL, [rbp+pMoniker]
0x1800840bd  mov     ebx, eax
0x1800840bf  mov     rax, [relativeURL]
0x1800840c2  mov     rax, [rax+10h]
0x1800840c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800840cb  mov     relativeURL, [rbp+pBaseMoniker]
0x1800840cf  mov     rax, [relativeURL]
0x1800840d2  mov     rax, [rax+10h]
0x1800840d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800840db  jmp     $CleanUp_80
0x1800840e0  call    cs:__imp_PathIsURLW
0x1800840e7  nop     dword ptr [rax+rax+00h]
0x1800840ec  test    eax, eax
0x1800840ee  jz      short loc_180084102
0x1800840f0  mov     baseURL, rdi; ppszDup
0x1800840f3  mov     relativeURL, rsi; psz
0x1800840f6  call    ?allocStrWHR@@YAJPEBGPEAPEAG@Z; allocStrWHR(ushort const *,ushort * *)
0x1800840fb  mov     ebx, eax
0x1800840fd  jmp     $CleanUp_80
0x180084102  xor     edx, edx; dwFlags
0x180084104  mov     ecx, 2000h; cb
0x180084109  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18008410e  mov     [rdi], rax
0x180084111  test    rax, rax
0x180084114  jnz     short loc_180084120
0x180084116  mov     ebx, 8007000Eh
0x18008411b  jmp     loc_1800841B9
0x180084120  xor     r9d, r9d; dwFlags
0x180084123  mov     dword ptr [rbp+pMoniker], 1000h
0x18008412a  lea     resolvedURL, [rbp+pMoniker]; pcchUnescaped
0x18008412e  mov     baseURL, rax; pszUnescaped
0x180084131  mov     relativeURL, rsi; pszUrl
0x180084134  call    cs:__imp_UrlUnescapeW
0x18008413b  nop     dword ptr [rax+rax+00h]
0x180084140  mov     ebx, eax
0x180084142  test    eax, eax
0x180084144  jns     short loc_180084154
0x180084146  cmp     eax, 80004003h
0x18008414b  jnz     short loc_1800841B9
0x18008414d  mov     ebx, 80070057h
0x180084152  jmp     short loc_1800841B9
0x180084154  xor     edx, edx; dwFlags
0x180084156  mov     ecx, 2000h; cb
0x18008415b  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180084160  mov     rsi, rax
0x180084163  test    rax, rax
0x180084166  jz      short loc_180084116
0x180084168  mov     relativeURL, [rdi]; pszPath
0x18008416b  mov     r8d, 1000h; cchBuf
0x180084171  mov     baseURL, rax; pszBuf
0x180084174  call    cs:__imp_PathSearchAndQualifyW
0x18008417b  nop     dword ptr [rax+rax+00h]
0x180084180  test    eax, eax
0x180084182  jz      short loc_1800841A8
0x180084184  mov     baseURL, [rdi]; pszUrl
0x180084187  lea     resolvedURL, [rbp+pMoniker]; pcchUrl
0x18008418b  xor     r9d, r9d; dwFlags
0x18008418e  mov     dword ptr [rbp+pMoniker], 1000h
0x180084195  mov     relativeURL, rsi; pszPath
0x180084198  call    cs:__imp_UrlCreateFromPathW
0x18008419f  nop     dword ptr [rax+rax+00h]
0x1800841a4  mov     ebx, eax
0x1800841a6  jmp     short loc_1800841AD
0x1800841a8  mov     ebx, 80070057h
0x1800841ad  mov     relativeURL, rsi; pv
0x1800841b0  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800841b5  test    ebx, ebx
0x1800841b7  jns     short loc_1800841CD
0x1800841b9  mov     relativeURL, [rdi]; pv
0x1800841bc  test    relativeURL, relativeURL
0x1800841bf  jz      short loc_1800841CD
0x1800841c1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800841c6  mov     qword ptr [rdi], 0
0x1800841cd  mov     eax, ebx
0x1800841cf  mov     rbx, [rsp+20h+arg_0]
0x1800841d4  add     rsp, 20h
0x1800841d8  pop     rdi
0x1800841d9  pop     rsi
0x1800841da  pop     rbp
0x1800841db  retn
```
