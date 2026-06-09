# HTTPRequest::crackURL(ushort const *,ushort * *)

- ea: `0x10131fa0`
- end: `0x101320f6`
- name: `?crackURL@HTTPRequest@@UAEJPBGPAPAG@Z`
- size: `342`
- prototype: `HRESULT __thiscall(HTTPRequest *this, const wchar_t *pwszUrl, wchar_t **ppwszCrackedUrl)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x10040dee`
- `0x1004fc3e`
- `0x100562fe`
- `0x1006c354`
- `0x10131fa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10131ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101320b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10131ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101320b4`
- `WINHTTP!WinHttpCrackUrl` at `0x10131fe8`
- `WINHTTP!WinHttpCrackUrl` at `0x10131fe8`
- `WINHTTP!WinHttpCreateUrl` at `0x101320a3`
- `WINHTTP!WinHttpCreateUrl` at `0x101320a3`

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
0x10131fa0  mov     edi, edi
0x10131fa2  push    ebp
0x10131fa3  mov     ebp, esp
0x10131fa5  sub     esp, 40h
0x10131fa8  push    ebx
0x10131fa9  push    esi
0x10131faa  push    edi
0x10131fab  push    3Ch ; '<'
0x10131fad  pop     esi
0x10131fae  push    esi; Size
0x10131faf  xor     edi, edi
0x10131fb1  lea     eax, [ebp+urlComp]
0x10131fb4  push    edi; Val
0x10131fb5  push    eax; void *
0x10131fb6  call    _memset
0x10131fbb  mov     ebx, [ebp+ppwszCrackedUrl]
0x10131fbe  add     esp, 0Ch
0x10131fc1  xor     eax, eax
0x10131fc3  mov     [ebp+urlComp.dwStructSize], esi
0x10131fc6  inc     eax
0x10131fc7  mov     [ebp+urlComp.dwSchemeLength], eax
0x10131fca  mov     [ebp+urlComp.dwHostNameLength], eax
0x10131fcd  mov     [ebp+urlComp.nPort], ax
0x10131fd1  mov     [ebp+urlComp.dwUserNameLength], eax
0x10131fd4  mov     [ebp+urlComp.dwPasswordLength], eax
0x10131fd7  mov     [ebp+urlComp.dwUrlPathLength], eax
0x10131fda  mov     [ebp+urlComp.dwExtraInfoLength], eax
0x10131fdd  lea     eax, [ebp+urlComp]
0x10131fe0  push    eax; lpUrlComponents
0x10131fe1  push    edi; dwFlags
0x10131fe2  push    edi; dwUrlLength
0x10131fe3  push    [ebp+pwszUrl]; pwszUrl
0x10131fe6  mov     [ebx], edi
0x10131fe8  call    ds:__imp__WinHttpCrackUrl@16; WinHttpCrackUrl(x,x,x,x)
0x10131fee  test    eax, eax
0x10131ff0  jnz     short loc_10132010
0x10131ff2  call    ds:__imp__GetLastError@0; GetLastError()
0x10131ff8  mov     esi, eax
0x10131ffa  test    esi, esi
0x10131ffc  jle     CleanUp_452
0x10132002  movzx   esi, si
0x10132005  or      esi, 80070000h
0x1013200b  jmp     CleanUp_452
0x10132010  cmp     [ebp+urlComp.lpszUserName], edi
0x10132013  jnz     loc_101320E8
0x10132019  cmp     [ebp+urlComp.lpszPassword], edi
0x1013201c  jnz     loc_101320E8
0x10132022  mov     this, [ebp+pwszUrl]; psz
0x10132025  mov     edx, 7FFFFFFFh; cchMax
0x1013202a  mov     [ebp+urlComp.lpszUserName], edi
0x1013202d  mov     [ebp+urlComp.dwUserNameLength], edi
0x10132030  mov     [ebp+urlComp.lpszPassword], edi
0x10132033  mov     [ebp+urlComp.dwPasswordLength], edi
0x10132036  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x1013203b  mov     this, eax
0x1013203d  or      edi, 0FFFFFFFFh
0x10132040  lea     eax, [this+1]
0x10132043  cmp     eax, this
0x10132045  cmovnb  edi, eax
0x10132048  sbb     esi, esi
0x1013204a  mov     edx, edi
0x1013204c  and     esi, 80070216h
0x10132052  mov     [ebp+cch], edx
0x10132055  cmp     eax, this
0x10132057  jb      CleanUp_452
0x1013205d  cmp     [ebp+urlComp.dwUrlPathLength], 0
0x10132061  jnz     short retryCreateUrl
0x10132063  lea     eax, [edi+1]
0x10132066  mov     [ebp+urlComp.lpszUrlPath], offset asc_1001E7D0; "/" ...
0x1013206d  or      edx, 0FFFFFFFFh
0x10132070  mov     [ebp+urlComp.dwUrlPathLength], 1
0x10132077  cmp     eax, edi
0x10132079  cmovnb  edx, eax
0x1013207c  sbb     esi, esi
0x1013207e  and     esi, 80070216h
0x10132084  mov     [ebp+cch], edx
0x10132087  cmp     eax, edi
0x10132089  jb      short CleanUp_452
0x1013208b  mov     this, edx; cch
0x1013208d  call    ??$new_array_ne@G@@YGPAGJ@Z; new_array_ne<ushort>(long)
0x10132092  mov     edi, eax
0x10132094  test    edi, edi
0x10132096  jz      short loc_101320E1
0x10132098  lea     eax, [ebp+cch]
0x1013209b  push    eax; pdwUrlLength
0x1013209c  push    edi; pwszUrl
0x1013209d  push    0; dwFlags
0x1013209f  lea     eax, [ebp+urlComp]
0x101320a2  push    eax; lpUrlComponents
0x101320a3  call    ds:__imp__WinHttpCreateUrl@16; WinHttpCreateUrl(x,x,x,x)
0x101320a9  test    eax, eax
0x101320ab  jnz     short loc_101320D4
0x101320ad  mov     this, edi; pv
0x101320af  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x101320b4  call    ds:__imp__GetLastError@0; GetLastError()
0x101320ba  cmp     eax, 7Ah ; 'z'
0x101320bd  jnz     short loc_101320C4
0x101320bf  mov     edx, [ebp+cch]
0x101320c2  jmp     short retryCreateUrl
0x101320c4  test    eax, eax
0x101320c6  jg      short loc_101320CC
0x101320c8  mov     esi, eax
0x101320ca  jmp     short CleanUp_452
0x101320cc  movzx   esi, ax
0x101320cf  jmp     loc_10132005
0x101320d4  mov     eax, [ebp+cch]
0x101320d7  xor     this, this
0x101320d9  mov     [edi+eax*2], cx
0x101320dd  mov     [ebx], edi
0x101320df  jmp     short CleanUp_452
0x101320e1  mov     esi, 8007000Eh
0x101320e6  jmp     short CleanUp_452
0x101320e8  mov     esi, 800C0002h
0x101320ed  pop     edi
0x101320ee  mov     eax, esi
0x101320f0  pop     esi
0x101320f1  pop     ebx
0x101320f2  leave
0x101320f3  retn    8
```
