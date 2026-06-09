# HTTPRequest::crackURL(ushort const *,ushort * *)

- ea: `0x1801541d0`
- end: `0x180154364`
- name: `?crackURL@HTTPRequest@@UEAAJPEBGPEAPEAG@Z`
- size: `404`
- prototype: `__int64 __fastcall(HTTPRequest *this, const wchar_t *pwszUrl, wchar_t **ppwszCrackedUrl)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180009f88`
- `0x18000ae54`
- `0x1800502b0`
- `0x1800cba94`
- `0x1801541d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015423c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015423c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154320`
- `WINHTTP!WinHttpCrackUrl` at `0x180154232`
- `WINHTTP!WinHttpCrackUrl` at `0x180154232`
- `WINHTTP!WinHttpCreateUrl` at `0x18015430e`
- `WINHTTP!WinHttpCreateUrl` at `0x18015430e`

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
0x1801541d0  push    rbp
0x1801541d2  push    rbx
0x1801541d3  push    rsi
0x1801541d4  push    rdi
0x1801541d5  lea     rbp, [rsp-3Fh]
0x1801541da  sub     rsp, 98h
0x1801541e1  mov     rsi, ppwszCrackedUrl
0x1801541e4  mov     [rbp+57h+cch], 0
0x1801541eb  mov     rbx, pwszUrl
0x1801541ee  lea     this, [rbp+57h+urlComp]; void *
0x1801541f2  mov     edi, 68h ; 'h'
0x1801541f7  xor     edx, edx; Val
0x1801541f9  mov     r8d, edi; Size
0x1801541fc  call    memset_0
0x180154201  mov     [rbp+57h+urlComp.dwStructSize], edi
0x180154204  lea     r9, [rbp+57h+urlComp]; lpUrlComponents
0x180154208  mov     edi, 1
0x18015420d  mov     qword ptr [rsi], 0
0x180154214  xor     r8d, r8d; dwFlags
0x180154217  mov     [rbp+57h+urlComp.dwSchemeLength], edi
0x18015421a  xor     edx, edx; dwUrlLength
0x18015421c  mov     [rbp+57h+urlComp.dwHostNameLength], edi
0x18015421f  mov     this, rbx; pwszUrl
0x180154222  mov     [rbp+57h+urlComp.nPort], di
0x180154226  mov     [rbp+57h+urlComp.dwUserNameLength], edi
0x180154229  mov     [rbp+57h+urlComp.dwPasswordLength], edi
0x18015422c  mov     [rbp+57h+urlComp.dwUrlPathLength], edi
0x18015422f  mov     [rbp+57h+urlComp.dwExtraInfoLength], edi
0x180154232  call    cs:__imp_WinHttpCrackUrl
0x180154238  test    eax, eax
0x18015423a  jnz     short loc_18015425A
0x18015423c  call    cs:__imp_GetLastError
0x180154242  mov     ebx, eax
0x180154244  test    eax, eax
0x180154246  jle     $CleanUp_504
0x18015424c  movzx   ebx, ax
0x18015424f  or      ebx, 80070000h
0x180154255  jmp     $CleanUp_504
0x18015425a  cmp     [rbp+57h+urlComp.lpszUserName], 0
0x18015425f  jnz     loc_180154351
0x180154265  cmp     [rbp+57h+urlComp.lpszPassword], 0
0x18015426a  jnz     loc_180154351
0x180154270  mov     edx, 7FFFFFFFh; cchMax
0x180154275  mov     [rbp+57h+urlComp.lpszUserName], 0
0x18015427d  mov     this, rbx; psz
0x180154280  mov     [rbp+57h+urlComp.dwUserNameLength], 0
0x180154287  mov     [rbp+57h+urlComp.lpszPassword], 0
0x18015428f  mov     [rbp+57h+urlComp.dwPasswordLength], 0
0x180154296  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x18015429b  or      r9d, 0FFFFFFFFh
0x18015429f  mov     r10d, 80070216h
0x1801542a5  mov     r8d, r9d
0x1801542a8  lea     ecx, [rax+1]
0x1801542ab  cmp     ecx, eax
0x1801542ad  cmovnb  r8d, ecx
0x1801542b1  sbb     ebx, ebx
0x1801542b3  and     ebx, r10d
0x1801542b6  mov     edx, r8d
0x1801542b9  mov     [rbp+57h+cch], edx
0x1801542bc  cmp     ecx, eax
0x1801542be  jb      $CleanUp_504
0x1801542c4  cmp     [rbp+57h+urlComp.dwUrlPathLength], 0
0x1801542c8  jnz     short $retryCreateUrl_0
0x1801542ca  lea     rax, asc_1801BFB38; "/"
0x1801542d1  mov     [rbp+57h+urlComp.dwUrlPathLength], edi
0x1801542d4  mov     [rbp+57h+urlComp.lpszUrlPath], rax
0x1801542d8  mov     edx, r9d
0x1801542db  lea     eax, [ppwszCrackedUrl+1]
0x1801542df  cmp     eax, r8d
0x1801542e2  cmovnb  edx, eax
0x1801542e5  sbb     ebx, ebx
0x1801542e7  and     ebx, r10d
0x1801542ea  mov     [rbp+57h+cch], edx
0x1801542ed  cmp     eax, r8d
0x1801542f0  jb      short $CleanUp_504
0x1801542f2  mov     ecx, edx; cch
0x1801542f4  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x1801542f9  mov     rdi, rax
0x1801542fc  test    rax, rax
0x1801542ff  jz      short loc_18015434A
0x180154301  lea     r9, [rbp+57h+cch]; pdwUrlLength
0x180154305  mov     ppwszCrackedUrl, rax; pwszUrl
0x180154308  xor     edx, edx; dwFlags
0x18015430a  lea     this, [rbp+57h+urlComp]; lpUrlComponents
0x18015430e  call    cs:__imp_WinHttpCreateUrl
0x180154314  test    eax, eax
0x180154316  jnz     short loc_18015433C
0x180154318  mov     this, rdi; pv
0x18015431b  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180154320  call    cs:__imp_GetLastError
0x180154326  cmp     eax, 7Ah ; 'z'
0x180154329  jnz     short loc_180154330
0x18015432b  mov     edx, [rbp+57h+cch]
0x18015432e  jmp     short $retryCreateUrl_0
0x180154330  test    eax, eax
0x180154332  jg      loc_18015424C
0x180154338  mov     ebx, eax
0x18015433a  jmp     short $CleanUp_504
0x18015433c  mov     ecx, [rbp+57h+cch]
0x18015433f  xor     eax, eax
0x180154341  mov     [rdi+this*2], ax
0x180154345  mov     [rsi], rdi
0x180154348  jmp     short $CleanUp_504
0x18015434a  mov     ebx, 8007000Eh
0x18015434f  jmp     short $CleanUp_504
0x180154351  mov     ebx, 800C0002h
0x180154356  mov     eax, ebx
0x180154358  add     rsp, 98h
0x18015435f  pop     rdi
0x180154360  pop     rsi
0x180154361  pop     rbx
0x180154362  pop     rbp
0x180154363  retn
```
