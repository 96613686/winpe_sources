# URLMONRequest::createUrl(URL_COMPONENTSW,ushort * *)

- ea: `0x10138cc6`
- end: `0x10138e28`
- name: `?createUrl@URLMONRequest@@IAEJUURL_COMPONENTSW@@PAPAG@Z`
- size: `354`
- prototype: `HRESULT __thiscall(URLMONRequest *this, URL_COMPONENTSW urlComp, wchar_t **ppwszURL)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x101389b0`

## callees

- `0x10040d5e`
- `0x1005626e`
- `0x10130ef1`
- `0x10138cc6`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10138d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10138d10`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x10138da6`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x10138da6`
- `WININET!InternetCreateUrlW` at `0x10138d06`
- `WININET!InternetCreateUrlW` at `0x10138d06`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::createUrl(URLMONRequest *this, URL_COMPONENTSW urlComp, wchar_t **ppwszURL)
{
  wchar_t *v3; // ebx
  wchar_t *v4; // edi
  signed int LastError; // eax
  int v6; // esi
  unsigned int v7; // ecx
  wchar_t *pwszTargetUrl; // [esp+Ch] [ebp-8h] BYREF
  unsigned int cch; // [esp+10h] [ebp-4h] BYREF

  v3 = 0;
  pwszTargetUrl = 0;
  v4 = 0;
  cch = 0;
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_qq(0x403u, 0xE9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, ppwszURL);
  while ( !InternetCreateUrlW(&urlComp, 0, v3, &cch) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto CleanUp_506;
    }
    cch >>= 1;
    MemFree(v3);
    v3 = new_array_ne<unsigned short>(cch);
    if ( !v3 )
    {
      v6 = -2147024882;
      goto LABEL_21;
    }
  }
  if ( !v3 )
  {
    v6 = -2147467259;
    goto LABEL_21;
  }
  v6 = URL::EscapeChars(L"#", v3, cch, &pwszTargetUrl, &cch);
  if ( v6 >= 0 )
  {
    v7 = cch + 1;
    if ( cch + 1 < cch )
    {
      cch = -1;
      v6 = -2147024362;
    }
    else
    {
      ++cch;
      while ( 1 )
      {
        v4 = new_array_ne<unsigned short>(v7);
        if ( !v4 )
          break;
        v6 = UrlCanonicalizeW(pwszTargetUrl, v4, &cch, 0x8000000u);
        if ( v6 != -2147467261 )
          goto CleanUp_506;
        MemFree(v4);
        v7 = cch;
      }
      v6 = -2147024882;
    }
  }
CleanUp_506:
  if ( pwszTargetUrl != v3 )
    MemFree(pwszTargetUrl);
LABEL_21:
  MemFree(v3);
  if ( v6 < 0 )
  {
    MemFree(v4);
    v4 = 0;
  }
  *ppwszURL = v4;
  if ( (byte_10185760[16 * (v6 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xEAu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10138cc6  mov     edi, edi
0x10138cc8  push    ebp
0x10138cc9  mov     ebp, esp
0x10138ccb  push    this
0x10138ccc  push    this
0x10138ccd  push    ebx
0x10138cce  xor     ebx, ebx
0x10138cd0  push    esi
0x10138cd1  push    edi
0x10138cd2  mov     [ebp+pwszTargetUrl], ebx
0x10138cd5  xor     edi, edi
0x10138cd7  mov     [ebp+cch], ebx
0x10138cda  test    byte_10185760, 8; __annotation("TMF:",
0x10138ce1  jz      short retryCreateUrl_0
0x10138ce3  push    [ebp+ppwszURL]; _a2
0x10138ce6  mov     edx, 0E9h; id
0x10138ceb  push    this; _a1
0x10138cec  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10138cf1  mov     this, 403h; LevelKeyword
0x10138cf6  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x10138cfb  lea     eax, [ebp+cch]
0x10138cfe  push    eax; lpdwUrlLength
0x10138cff  push    ebx; lpszUrl
0x10138d00  push    0; dwFlags
0x10138d02  lea     eax, [ebp+urlComp]
0x10138d05  push    eax; lpUrlComponents
0x10138d06  call    ds:__imp__InternetCreateUrlW@16; InternetCreateUrlW(x,x,x,x)
0x10138d0c  test    eax, eax
0x10138d0e  jnz     short loc_10138D52
0x10138d10  call    ds:__imp__GetLastError@0; GetLastError()
0x10138d16  mov     esi, eax
0x10138d18  cmp     esi, 7Ah ; 'z'
0x10138d1b  jnz     short loc_10138D3F
0x10138d1d  shr     [ebp+cch], 1
0x10138d20  mov     this, ebx; pv
0x10138d22  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138d27  mov     this, [ebp+cch]; cch
0x10138d2a  call    ??$new_array_ne@G@@YGPAGJ@Z; new_array_ne<ushort>(long)
0x10138d2f  mov     ebx, eax
0x10138d31  test    ebx, ebx
0x10138d33  jnz     short retryCreateUrl_0
0x10138d35  mov     esi, 8007000Eh
0x10138d3a  jmp     loc_10138DDA
0x10138d3f  test    esi, esi
0x10138d41  jle     CleanUp_506
0x10138d47  movzx   esi, si
0x10138d4a  or      esi, 80070000h
0x10138d50  jmp     short CleanUp_506
0x10138d52  test    ebx, ebx
0x10138d54  jnz     short loc_10138D5D
0x10138d56  mov     esi, 80004005h
0x10138d5b  jmp     short loc_10138DDA
0x10138d5d  lea     eax, [ebp+cch]
0x10138d60  mov     edx, ebx; pchSrc
0x10138d62  push    eax; pcchEncoded
0x10138d63  lea     eax, [ebp+pwszTargetUrl]
0x10138d66  mov     this, offset asc_10036680; "#"
0x10138d6b  push    eax; ppchEncoded
0x10138d6c  push    [ebp+cch]; cch
0x10138d6f  call    ?EscapeChars@URL@@SGJPBGPAGKPAPAGPAK@Z; URL::EscapeChars(ushort const *,ushort *,ulong,ushort * *,ulong *)
0x10138d74  mov     esi, eax
0x10138d76  test    esi, esi
0x10138d78  js      short CleanUp_506
0x10138d7a  mov     eax, [ebp+cch]
0x10138d7d  lea     this, [eax+1]; cch
0x10138d80  cmp     this, eax
0x10138d82  jb      short loc_10138DC2
0x10138d84  mov     [ebp+cch], this
0x10138d87  call    ??$new_array_ne@G@@YGPAGJ@Z; new_array_ne<ushort>(long)
0x10138d8c  mov     edi, eax
0x10138d8e  test    edi, edi
0x10138d90  jnz     short RetryCanonUrl
0x10138d92  mov     esi, 8007000Eh
0x10138d97  jmp     short CleanUp_506
0x10138d99  push    8000000h; dwFlags
0x10138d9e  lea     eax, [ebp+cch]
0x10138da1  push    eax; pcchCanonicalized
0x10138da2  push    edi; pszCanonicalized
0x10138da3  push    [ebp+pwszTargetUrl]; pszUrl
0x10138da6  call    ds:__imp__UrlCanonicalizeW@16; UrlCanonicalizeW(x,x,x,x)
0x10138dac  mov     esi, eax
0x10138dae  cmp     esi, 80004003h
0x10138db4  jnz     short CleanUp_506
0x10138db6  mov     this, edi; pv
0x10138db8  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138dbd  mov     this, [ebp+cch]
0x10138dc0  jmp     short loc_10138D87
0x10138dc2  mov     [ebp+cch], 0FFFFFFFFh
0x10138dc9  mov     esi, 80070216h
0x10138dce  mov     this, [ebp+pwszTargetUrl]; pv
0x10138dd1  cmp     this, ebx
0x10138dd3  jz      short loc_10138DDA
0x10138dd5  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138dda  mov     this, ebx; pv
0x10138ddc  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138de1  test    esi, esi
0x10138de3  jns     short loc_10138DEE
0x10138de5  mov     this, edi; pv
0x10138de7  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138dec  xor     edi, edi
0x10138dee  mov     eax, [ebp+ppwszURL]
0x10138df1  mov     [eax], edi
0x10138df3  mov     this, esi; __annotation("TMF:",
0x10138df5  sar     this, 1Fh
0x10138df8  mov     eax, this
0x10138dfa  shl     eax, 4
0x10138dfd  test    byte_10185760[eax], 8
0x10138e04  jz      short loc_10138E1F
0x10138e06  add     this, 2
0x10138e09  mov     edx, 0EAh; id
0x10138e0e  push    esi; _a1
0x10138e0f  shl     this, 9
0x10138e12  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10138e17  or      this, 3; LevelKeyword
0x10138e1a  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10138e1f  pop     edi
0x10138e20  mov     eax, esi
0x10138e22  pop     esi
0x10138e23  pop     ebx
0x10138e24  leave
0x10138e25  retn    40h ; '@'
```
