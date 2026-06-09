# HTTPRequest::crackURL(ushort const *,ushort * *)

- ea: `0x180157770`
- end: `0x18015791d`
- name: `?crackURL@HTTPRequest@@UEAAJPEBGPEAPEAG@Z`
- size: `429`
- prototype: `HRESULT __fastcall(HTTPRequest *this, const wchar_t *pwszUrl, wchar_t **ppwszCrackedUrl)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180016588`
- `0x180017480`
- `0x180054310`
- `0x1800cd3e4`
- `0x180157770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801577e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801578d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801577e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801578d2`
- `WINHTTP!WinHttpCrackUrl` at `0x1801577d2`
- `WINHTTP!WinHttpCrackUrl` at `0x1801577d2`
- `WINHTTP!WinHttpCreateUrl` at `0x1801578ba`
- `WINHTTP!WinHttpCreateUrl` at `0x1801578ba`

## pseudocode

```c
__int64 __fastcall HTTPRequest::crackURL(HTTPRequest *this, const wchar_t *pwszUrl, wchar_t **ppwszCrackedUrl)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ecx
  unsigned int v10; // edx
  unsigned int v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  URL_COMPONENTSW urlComp; // [rsp+20h] [rbp-39h] BYREF
  unsigned int cch; // [rsp+D0h] [rbp+77h] BYREF

  cch = 0;
  memset_0(&urlComp, 0, sizeof(urlComp));
  urlComp.dwStructSize = 104;
  *ppwszCrackedUrl = 0;
  urlComp.dwSchemeLength = 1;
  urlComp.dwHostNameLength = 1;
  urlComp.nPort = 1;
  urlComp.dwUserNameLength = 1;
  urlComp.dwPasswordLength = 1;
  urlComp.dwUrlPathLength = 1;
  urlComp.dwExtraInfoLength = 1;
  if ( WinHttpCrackUrl(pwszUrl, 0, 0, &urlComp) )
  {
    if ( urlComp.lpszUserName || urlComp.lpszPassword )
    {
      return (unsigned int)-2146697214;
    }
    else
    {
      urlComp.lpszUserName = 0;
      urlComp.dwUserNameLength = 0;
      urlComp.lpszPassword = 0;
      urlComp.dwPasswordLength = 0;
      v7 = xstrlenw(pwszUrl, 0x7FFFFFFFu);
      v8 = -1;
      v9 = v7 + 1;
      if ( v7 + 1 >= v7 )
        v8 = v7 + 1;
      v6 = v9 < v7 ? 0x80070216 : 0;
      v10 = v8;
      cch = v8;
      if ( v9 >= v7 )
      {
        if ( urlComp.dwUrlPathLength )
          goto LABEL_25;
        urlComp.dwUrlPathLength = 1;
        urlComp.lpszUrlPath = (wchar_t *)L"/";
        v10 = -1;
        v11 = v8 + 1;
        if ( v8 + 1 >= v8 )
          v10 = v8 + 1;
        v6 = v11 < v8 ? 0x80070216 : 0;
        cch = v10;
        if ( v11 >= v8 )
        {
LABEL_25:
          while ( 1 )
          {
            v12 = new_array_ne<unsigned short>(v10);
            v13 = v12;
            if ( !v12 )
              return (unsigned int)-2147024882;
            if ( WinHttpCreateUrl(&urlComp, 0, v12, &cch) )
            {
              v13[cch] = 0;
              *ppwszCrackedUrl = v13;
              return v6;
            }
            MemFree(v13);
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            v10 = cch;
          }
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return (unsigned int)LastError;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180157770  push    rbp
0x180157772  push    rbx
0x180157773  push    rsi
0x180157774  push    rdi
0x180157775  lea     rbp, [rsp-3Fh]
0x18015777a  sub     rsp, 98h
0x180157781  mov     rsi, ppwszCrackedUrl
0x180157784  mov     [rbp+57h+cch], 0
0x18015778b  mov     rbx, pwszUrl
0x18015778e  lea     this, [rbp+57h+urlComp]; void *
0x180157792  mov     edi, 68h ; 'h'
0x180157797  xor     edx, edx; Val
0x180157799  mov     r8d, edi; Size
0x18015779c  call    memset_0
0x1801577a1  mov     [rbp+57h+urlComp.dwStructSize], edi
0x1801577a4  lea     r9, [rbp+57h+urlComp]; lpUrlComponents
0x1801577a8  mov     edi, 1
0x1801577ad  mov     qword ptr [rsi], 0
0x1801577b4  xor     r8d, r8d; dwFlags
0x1801577b7  mov     [rbp+57h+urlComp.dwSchemeLength], edi
0x1801577ba  xor     edx, edx; dwUrlLength
0x1801577bc  mov     [rbp+57h+urlComp.dwHostNameLength], edi
0x1801577bf  mov     this, rbx; pwszUrl
0x1801577c2  mov     [rbp+57h+urlComp.nPort], di
0x1801577c6  mov     [rbp+57h+urlComp.dwUserNameLength], edi
0x1801577c9  mov     [rbp+57h+urlComp.dwPasswordLength], edi
0x1801577cc  mov     [rbp+57h+urlComp.dwUrlPathLength], edi
0x1801577cf  mov     [rbp+57h+urlComp.dwExtraInfoLength], edi
0x1801577d2  call    cs:__imp_WinHttpCrackUrl
0x1801577d9  nop     dword ptr [rax+rax+00h]
0x1801577de  test    eax, eax
0x1801577e0  jnz     short loc_180157806
0x1801577e2  call    cs:__imp_GetLastError
0x1801577e9  nop     dword ptr [rax+rax+00h]
0x1801577ee  mov     ebx, eax
0x1801577f0  test    eax, eax
0x1801577f2  jle     $CleanUp_504
0x1801577f8  movzx   ebx, ax
0x1801577fb  or      ebx, 80070000h
0x180157801  jmp     $CleanUp_504
0x180157806  cmp     [rbp+57h+urlComp.lpszUserName], 0
0x18015780b  jnz     loc_180157909
0x180157811  cmp     [rbp+57h+urlComp.lpszPassword], 0
0x180157816  jnz     loc_180157909
0x18015781c  mov     edx, 7FFFFFFFh; cchMax
0x180157821  mov     [rbp+57h+urlComp.lpszUserName], 0
0x180157829  mov     this, rbx; psz
0x18015782c  mov     [rbp+57h+urlComp.dwUserNameLength], 0
0x180157833  mov     [rbp+57h+urlComp.lpszPassword], 0
0x18015783b  mov     [rbp+57h+urlComp.dwPasswordLength], 0
0x180157842  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x180157847  or      r9d, 0FFFFFFFFh
0x18015784b  mov     r10d, 80070216h
0x180157851  mov     r8d, r9d
0x180157854  lea     ecx, [rax+1]
0x180157857  cmp     ecx, eax
0x180157859  cmovnb  r8d, ecx
0x18015785d  sbb     ebx, ebx
0x18015785f  and     ebx, r10d
0x180157862  mov     edx, r8d
0x180157865  mov     [rbp+57h+cch], edx
0x180157868  cmp     ecx, eax
0x18015786a  jb      $CleanUp_504
0x180157870  cmp     [rbp+57h+urlComp.dwUrlPathLength], 0
0x180157874  jnz     short $retryCreateUrl_0
0x180157876  lea     rax, asc_1801BF460; "/"
0x18015787d  mov     [rbp+57h+urlComp.dwUrlPathLength], edi
0x180157880  mov     [rbp+57h+urlComp.lpszUrlPath], rax
0x180157884  mov     edx, r9d
0x180157887  lea     eax, [ppwszCrackedUrl+1]
0x18015788b  cmp     eax, r8d
0x18015788e  cmovnb  edx, eax
0x180157891  sbb     ebx, ebx
0x180157893  and     ebx, r10d
0x180157896  mov     [rbp+57h+cch], edx
0x180157899  cmp     eax, r8d
0x18015789c  jb      short $CleanUp_504
0x18015789e  mov     ecx, edx; cch
0x1801578a0  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x1801578a5  mov     rdi, rax
0x1801578a8  test    rax, rax
0x1801578ab  jz      short loc_180157902
0x1801578ad  lea     r9, [rbp+57h+cch]; pdwUrlLength
0x1801578b1  mov     ppwszCrackedUrl, rax; pwszUrl
0x1801578b4  xor     edx, edx; dwFlags
0x1801578b6  lea     this, [rbp+57h+urlComp]; lpUrlComponents
0x1801578ba  call    cs:__imp_WinHttpCreateUrl
0x1801578c1  nop     dword ptr [rax+rax+00h]
0x1801578c6  test    eax, eax
0x1801578c8  jnz     short loc_1801578F4
0x1801578ca  mov     this, rdi; pv
0x1801578cd  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1801578d2  call    cs:__imp_GetLastError
0x1801578d9  nop     dword ptr [rax+rax+00h]
0x1801578de  cmp     eax, 7Ah ; 'z'
0x1801578e1  jnz     short loc_1801578E8
0x1801578e3  mov     edx, [rbp+57h+cch]
0x1801578e6  jmp     short $retryCreateUrl_0
0x1801578e8  test    eax, eax
0x1801578ea  jg      loc_1801577F8
0x1801578f0  mov     ebx, eax
0x1801578f2  jmp     short $CleanUp_504
0x1801578f4  mov     ecx, [rbp+57h+cch]
0x1801578f7  xor     eax, eax
0x1801578f9  mov     [rdi+this*2], ax
0x1801578fd  mov     [rsi], rdi
0x180157900  jmp     short $CleanUp_504
0x180157902  mov     ebx, 8007000Eh
0x180157907  jmp     short $CleanUp_504
0x180157909  mov     ebx, 800C0002h
0x18015790e  mov     eax, ebx
0x180157910  add     rsp, 98h
0x180157917  pop     rdi
0x180157918  pop     rsi
0x180157919  pop     rbx
0x18015791a  pop     rbp
0x18015791b  retn
```
