# HTTPRequest::crackURL(ushort const *,ushort * *)

- ea: `0x101320b0`
- end: `0x10132206`
- name: `?crackURL@HTTPRequest@@UAEJPBGPAPAG@Z`
- size: `342`
- prototype: `HRESULT __thiscall(HTTPRequest *this, const wchar_t *pwszUrl, wchar_t **ppwszCrackedUrl)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x10040d5e`
- `0x1004fbae`
- `0x1005626e`
- `0x1006c2c4`
- `0x101320b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10132102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101321c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10132102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101321c4`
- `WINHTTP!WinHttpCrackUrl` at `0x101320f8`
- `WINHTTP!WinHttpCrackUrl` at `0x101320f8`
- `WINHTTP!WinHttpCreateUrl` at `0x101321b3`
- `WINHTTP!WinHttpCreateUrl` at `0x101321b3`

## pseudocode

```c
HRESULT __thiscall HTTPRequest::crackURL(HTTPRequest *this, const wchar_t *pwszUrl, wchar_t **ppwszCrackedUrl)
{
  signed int v3; // eax
  unsigned int v4; // esi
  int v5; // esi
  unsigned int v6; // ecx
  unsigned int v7; // edi
  unsigned int v8; // eax
  int v9; // edx
  wchar_t *v10; // eax
  wchar_t *v11; // edi
  signed int LastError; // eax
  URL_COMPONENTSW urlComp; // [esp+Ch] [ebp-40h] BYREF
  unsigned int cch; // [esp+48h] [ebp-4h] BYREF

  memset(&urlComp, 0, sizeof(urlComp));
  urlComp.dwStructSize = 60;
  urlComp.dwSchemeLength = 1;
  urlComp.dwHostNameLength = 1;
  urlComp.nPort = 1;
  urlComp.dwUserNameLength = 1;
  urlComp.dwPasswordLength = 1;
  urlComp.dwUrlPathLength = 1;
  urlComp.dwExtraInfoLength = 1;
  *ppwszCrackedUrl = 0;
  if ( WinHttpCrackUrl(pwszUrl, 0, 0, &urlComp) )
  {
    if ( urlComp.lpszUserName || urlComp.lpszPassword )
      return -2146697214;
    memset(&urlComp.lpszUserName, 0, 16);
    v6 = xstrlenw(pwszUrl, 0x7FFFFFFFu);
    v7 = -1;
    v8 = v6 + 1;
    if ( v6 + 1 >= v6 )
      v7 = v6 + 1;
    v9 = v7;
    v4 = v8 < v6 ? 0x80070216 : 0;
    cch = v7;
    if ( v8 >= v6 )
    {
      if ( urlComp.dwUrlPathLength )
        goto LABEL_27;
      urlComp.lpszUrlPath = (wchar_t *)L"/";
      v9 = -1;
      urlComp.dwUrlPathLength = 1;
      if ( v7 + 1 >= v7 )
        v9 = v7 + 1;
      v4 = v7 + 1 < v7 ? 0x80070216 : 0;
      cch = v9;
      if ( v7 + 1 >= v7 )
      {
LABEL_27:
        while ( 1 )
        {
          v10 = new_array_ne<unsigned short>(v9);
          v11 = v10;
          if ( !v10 )
            return -2147024882;
          if ( WinHttpCreateUrl(&urlComp, 0, v10, &cch) )
          {
            v11[cch] = 0;
            *ppwszCrackedUrl = v11;
            return v4;
          }
          MemFree(v11);
          LastError = GetLastError();
          if ( LastError != 122 )
            break;
          v9 = cch;
        }
        if ( LastError <= 0 )
          return LastError;
        v5 = (unsigned __int16)LastError;
        return v5 | 0x80070000;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
    {
      v5 = (unsigned __int16)v3;
      return v5 | 0x80070000;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x101320b0  mov     edi, edi
0x101320b2  push    ebp
0x101320b3  mov     ebp, esp
0x101320b5  sub     esp, 40h
0x101320b8  push    ebx
0x101320b9  push    esi
0x101320ba  push    edi
0x101320bb  push    3Ch ; '<'
0x101320bd  pop     esi
0x101320be  push    esi; Size
0x101320bf  xor     edi, edi
0x101320c1  lea     eax, [ebp+urlComp]
0x101320c4  push    edi; Val
0x101320c5  push    eax; void *
0x101320c6  call    _memset
0x101320cb  mov     ebx, [ebp+ppwszCrackedUrl]
0x101320ce  add     esp, 0Ch
0x101320d1  xor     eax, eax
0x101320d3  mov     [ebp+urlComp.dwStructSize], esi
0x101320d6  inc     eax
0x101320d7  mov     [ebp+urlComp.dwSchemeLength], eax
0x101320da  mov     [ebp+urlComp.dwHostNameLength], eax
0x101320dd  mov     [ebp+urlComp.nPort], ax
0x101320e1  mov     [ebp+urlComp.dwUserNameLength], eax
0x101320e4  mov     [ebp+urlComp.dwPasswordLength], eax
0x101320e7  mov     [ebp+urlComp.dwUrlPathLength], eax
0x101320ea  mov     [ebp+urlComp.dwExtraInfoLength], eax
0x101320ed  lea     eax, [ebp+urlComp]
0x101320f0  push    eax; lpUrlComponents
0x101320f1  push    edi; dwFlags
0x101320f2  push    edi; dwUrlLength
0x101320f3  push    [ebp+pwszUrl]; pwszUrl
0x101320f6  mov     [ebx], edi
0x101320f8  call    ds:__imp__WinHttpCrackUrl@16; WinHttpCrackUrl(x,x,x,x)
0x101320fe  test    eax, eax
0x10132100  jnz     short loc_10132120
0x10132102  call    ds:__imp__GetLastError@0; GetLastError()
0x10132108  mov     esi, eax
0x1013210a  test    esi, esi
0x1013210c  jle     CleanUp_452
0x10132112  movzx   esi, si
0x10132115  or      esi, 80070000h
0x1013211b  jmp     CleanUp_452
0x10132120  cmp     [ebp+urlComp.lpszUserName], edi
0x10132123  jnz     loc_101321F8
0x10132129  cmp     [ebp+urlComp.lpszPassword], edi
0x1013212c  jnz     loc_101321F8
0x10132132  mov     this, [ebp+pwszUrl]; psz
0x10132135  mov     edx, 7FFFFFFFh; cchMax
0x1013213a  mov     [ebp+urlComp.lpszUserName], edi
0x1013213d  mov     [ebp+urlComp.dwUserNameLength], edi
0x10132140  mov     [ebp+urlComp.lpszPassword], edi
0x10132143  mov     [ebp+urlComp.dwPasswordLength], edi
0x10132146  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x1013214b  mov     this, eax
0x1013214d  or      edi, 0FFFFFFFFh
0x10132150  lea     eax, [this+1]
0x10132153  cmp     eax, this
0x10132155  cmovnb  edi, eax
0x10132158  sbb     esi, esi
0x1013215a  mov     edx, edi
0x1013215c  and     esi, 80070216h
0x10132162  mov     [ebp+cch], edx
0x10132165  cmp     eax, this
0x10132167  jb      CleanUp_452
0x1013216d  cmp     [ebp+urlComp.dwUrlPathLength], 0
0x10132171  jnz     short retryCreateUrl
0x10132173  lea     eax, [edi+1]
0x10132176  mov     [ebp+urlComp.lpszUrlPath], offset asc_1001E7D0; "/" ...
0x1013217d  or      edx, 0FFFFFFFFh
0x10132180  mov     [ebp+urlComp.dwUrlPathLength], 1
0x10132187  cmp     eax, edi
0x10132189  cmovnb  edx, eax
0x1013218c  sbb     esi, esi
0x1013218e  and     esi, 80070216h
0x10132194  mov     [ebp+cch], edx
0x10132197  cmp     eax, edi
0x10132199  jb      short CleanUp_452
0x1013219b  mov     this, edx; cch
0x1013219d  call    ??$new_array_ne@G@@YGPAGJ@Z; new_array_ne<ushort>(long)
0x101321a2  mov     edi, eax
0x101321a4  test    edi, edi
0x101321a6  jz      short loc_101321F1
0x101321a8  lea     eax, [ebp+cch]
0x101321ab  push    eax; pdwUrlLength
0x101321ac  push    edi; pwszUrl
0x101321ad  push    0; dwFlags
0x101321af  lea     eax, [ebp+urlComp]
0x101321b2  push    eax; lpUrlComponents
0x101321b3  call    ds:__imp__WinHttpCreateUrl@16; WinHttpCreateUrl(x,x,x,x)
0x101321b9  test    eax, eax
0x101321bb  jnz     short loc_101321E4
0x101321bd  mov     this, edi; pv
0x101321bf  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x101321c4  call    ds:__imp__GetLastError@0; GetLastError()
0x101321ca  cmp     eax, 7Ah ; 'z'
0x101321cd  jnz     short loc_101321D4
0x101321cf  mov     edx, [ebp+cch]
0x101321d2  jmp     short retryCreateUrl
0x101321d4  test    eax, eax
0x101321d6  jg      short loc_101321DC
0x101321d8  mov     esi, eax
0x101321da  jmp     short CleanUp_452
0x101321dc  movzx   esi, ax
0x101321df  jmp     loc_10132115
0x101321e4  mov     eax, [ebp+cch]
0x101321e7  xor     this, this
0x101321e9  mov     [edi+eax*2], cx
0x101321ed  mov     [ebx], edi
0x101321ef  jmp     short CleanUp_452
0x101321f1  mov     esi, 8007000Eh
0x101321f6  jmp     short CleanUp_452
0x101321f8  mov     esi, 800C0002h
0x101321fd  pop     edi
0x101321fe  mov     eax, esi
0x10132200  pop     esi
0x10132201  pop     ebx
0x10132202  leave
0x10132203  retn    8
```
