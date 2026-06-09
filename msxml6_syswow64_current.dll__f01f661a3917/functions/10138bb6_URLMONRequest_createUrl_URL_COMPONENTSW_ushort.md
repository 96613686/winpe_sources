# URLMONRequest::createUrl(URL_COMPONENTSW,ushort * *)

- ea: `0x10138bb6`
- end: `0x10138d18`
- name: `?createUrl@URLMONRequest@@IAEJUURL_COMPONENTSW@@PAPAG@Z`
- size: `354`
- prototype: `HRESULT __thiscall(URLMONRequest *this, URL_COMPONENTSW urlComp, wchar_t **ppwszURL)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x101388a0`

## callees

- `0x10040dee`
- `0x100562fe`
- `0x10130de1`
- `0x10138bb6`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10138c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10138c00`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x10138c96`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x10138c96`
- `WININET!InternetCreateUrlW` at `0x10138bf6`
- `WININET!InternetCreateUrlW` at `0x10138bf6`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
  if ( (byte_101857A0[16 * (v6 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xEAu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10138bb6  mov     edi, edi
0x10138bb8  push    ebp
0x10138bb9  mov     ebp, esp
0x10138bbb  push    this
0x10138bbc  push    this
0x10138bbd  push    ebx
0x10138bbe  xor     ebx, ebx
0x10138bc0  push    esi
0x10138bc1  push    edi
0x10138bc2  mov     [ebp+pwszTargetUrl], ebx
0x10138bc5  xor     edi, edi
0x10138bc7  mov     [ebp+cch], ebx
0x10138bca  test    byte_101857A0, 8; __annotation("TMF:",
0x10138bd1  jz      short retryCreateUrl_0
0x10138bd3  push    [ebp+ppwszURL]; _a2
0x10138bd6  mov     edx, 0E9h; id
0x10138bdb  push    this; _a1
0x10138bdc  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10138be1  mov     this, 403h; LevelKeyword
0x10138be6  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x10138beb  lea     eax, [ebp+cch]
0x10138bee  push    eax; lpdwUrlLength
0x10138bef  push    ebx; lpszUrl
0x10138bf0  push    0; dwFlags
0x10138bf2  lea     eax, [ebp+urlComp]
0x10138bf5  push    eax; lpUrlComponents
0x10138bf6  call    ds:__imp__InternetCreateUrlW@16; InternetCreateUrlW(x,x,x,x)
0x10138bfc  test    eax, eax
0x10138bfe  jnz     short loc_10138C42
0x10138c00  call    ds:__imp__GetLastError@0; GetLastError()
0x10138c06  mov     esi, eax
0x10138c08  cmp     esi, 7Ah ; 'z'
0x10138c0b  jnz     short loc_10138C2F
0x10138c0d  shr     [ebp+cch], 1
0x10138c10  mov     this, ebx; pv
0x10138c12  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138c17  mov     this, [ebp+cch]; cch
0x10138c1a  call    ??$new_array_ne@G@@YGPAGJ@Z; new_array_ne<ushort>(long)
0x10138c1f  mov     ebx, eax
0x10138c21  test    ebx, ebx
0x10138c23  jnz     short retryCreateUrl_0
0x10138c25  mov     esi, 8007000Eh
0x10138c2a  jmp     loc_10138CCA
0x10138c2f  test    esi, esi
0x10138c31  jle     CleanUp_506
0x10138c37  movzx   esi, si
0x10138c3a  or      esi, 80070000h
0x10138c40  jmp     short CleanUp_506
0x10138c42  test    ebx, ebx
0x10138c44  jnz     short loc_10138C4D
0x10138c46  mov     esi, 80004005h
0x10138c4b  jmp     short loc_10138CCA
0x10138c4d  lea     eax, [ebp+cch]
0x10138c50  mov     edx, ebx; pchSrc
0x10138c52  push    eax; pcchEncoded
0x10138c53  lea     eax, [ebp+pwszTargetUrl]
0x10138c56  mov     this, offset asc_100366C0; "#"
0x10138c5b  push    eax; ppchEncoded
0x10138c5c  push    [ebp+cch]; cch
0x10138c5f  call    ?EscapeChars@URL@@SGJPBGPAGKPAPAGPAK@Z; URL::EscapeChars(ushort const *,ushort *,ulong,ushort * *,ulong *)
0x10138c64  mov     esi, eax
0x10138c66  test    esi, esi
0x10138c68  js      short CleanUp_506
0x10138c6a  mov     eax, [ebp+cch]
0x10138c6d  lea     this, [eax+1]; cch
0x10138c70  cmp     this, eax
0x10138c72  jb      short loc_10138CB2
0x10138c74  mov     [ebp+cch], this
0x10138c77  call    ??$new_array_ne@G@@YGPAGJ@Z; new_array_ne<ushort>(long)
0x10138c7c  mov     edi, eax
0x10138c7e  test    edi, edi
0x10138c80  jnz     short RetryCanonUrl
0x10138c82  mov     esi, 8007000Eh
0x10138c87  jmp     short CleanUp_506
0x10138c89  push    8000000h; dwFlags
0x10138c8e  lea     eax, [ebp+cch]
0x10138c91  push    eax; pcchCanonicalized
0x10138c92  push    edi; pszCanonicalized
0x10138c93  push    [ebp+pwszTargetUrl]; pszUrl
0x10138c96  call    ds:__imp__UrlCanonicalizeW@16; UrlCanonicalizeW(x,x,x,x)
0x10138c9c  mov     esi, eax
0x10138c9e  cmp     esi, 80004003h
0x10138ca4  jnz     short CleanUp_506
0x10138ca6  mov     this, edi; pv
0x10138ca8  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138cad  mov     this, [ebp+cch]
0x10138cb0  jmp     short loc_10138C77
0x10138cb2  mov     [ebp+cch], 0FFFFFFFFh
0x10138cb9  mov     esi, 80070216h
0x10138cbe  mov     this, [ebp+pwszTargetUrl]; pv
0x10138cc1  cmp     this, ebx
0x10138cc3  jz      short loc_10138CCA
0x10138cc5  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138cca  mov     this, ebx; pv
0x10138ccc  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138cd1  test    esi, esi
0x10138cd3  jns     short loc_10138CDE
0x10138cd5  mov     this, edi; pv
0x10138cd7  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10138cdc  xor     edi, edi
0x10138cde  mov     eax, [ebp+ppwszURL]
0x10138ce1  mov     [eax], edi
0x10138ce3  mov     this, esi; __annotation("TMF:",
0x10138ce5  sar     this, 1Fh
0x10138ce8  mov     eax, this
0x10138cea  shl     eax, 4
0x10138ced  test    byte_101857A0[eax], 8
0x10138cf4  jz      short loc_10138D0F
0x10138cf6  add     this, 2
0x10138cf9  mov     edx, 0EAh; id
0x10138cfe  push    esi; _a1
0x10138cff  shl     this, 9
0x10138d02  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10138d07  or      this, 3; LevelKeyword
0x10138d0a  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10138d0f  pop     edi
0x10138d10  mov     eax, esi
0x10138d12  pop     esi
0x10138d13  pop     ebx
0x10138d14  leave
0x10138d15  retn    40h ; '@'
```
