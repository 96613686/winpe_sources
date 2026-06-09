# URLMONRequest::createUrl(URL_COMPONENTSW,ushort * *)

- ea: `0x180097684`
- end: `0x18009783e`
- name: `?createUrl@URLMONRequest@@IEAAJUURL_COMPONENTSW@@PEAPEAG@Z`
- size: `442`
- prototype: `__int64 __fastcall(URLMONRequest *this, URL_COMPONENTSW *urlComp, wchar_t **ppwszURL)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009aa30`

## callees

- `0x180009f88`
- `0x18000ae54`
- `0x180097684`
- `0x180097844`
- `0x180185008`
- `0x180185d8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976e5`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x180097794`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x180097794`
- `WININET!InternetCreateUrlW` at `0x1800976db`
- `WININET!InternetCreateUrlW` at `0x1800976db`

## pseudocode

```c
__int64 __fastcall URLMONRequest::createUrl(URLMONRequest *this, URL_COMPONENTSW *urlComp, wchar_t **ppwszURL)
{
  wchar_t *v3; // rsi
  wchar_t *v5; // rdi
  signed int LastError; // eax
  int v8; // ebx
  __int64 v9; // rcx
  wchar_t *v10; // rax
  unsigned int cch; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *pwszTargetUrl; // [rsp+78h] [rbp+48h] BYREF

  v3 = 0;
  pwszTargetUrl = 0;
  v5 = 0;
  cch = 0;
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_qq(0x403u, 0xE9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, ppwszURL);
  while ( !InternetCreateUrlW(urlComp, 0, v3, &cch) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      goto $CleanUp_119;
    }
    cch >>= 1;
    MemFree(v3);
    v3 = new_array_ne<unsigned short>(cch);
    if ( !v3 )
    {
      v8 = -2147024882;
      goto LABEL_21;
    }
  }
  if ( !v3 )
  {
    v8 = -2147467259;
    goto LABEL_21;
  }
  v8 = URL::EscapeChars(L"#", v3, cch, &pwszTargetUrl, &cch);
  if ( v8 >= 0 )
  {
    v9 = cch + 1;
    if ( (unsigned int)v9 < cch )
    {
      cch = -1;
      v8 = -2147024362;
    }
    else
    {
      ++cch;
      while ( 1 )
      {
        v10 = new_array_ne<unsigned short>(v9);
        v5 = v10;
        if ( !v10 )
          break;
        v8 = UrlCanonicalizeW(pwszTargetUrl, v10, &cch, 0x8000000u);
        if ( v8 != -2147467261 )
          goto $CleanUp_119;
        MemFree(v5);
        v9 = cch;
      }
      v8 = -2147024882;
    }
  }
$CleanUp_119:
  if ( pwszTargetUrl != v3 )
    MemFree(pwszTargetUrl);
LABEL_21:
  MemFree(v3);
  if ( v8 < 0 )
  {
    MemFree(v5);
    v5 = 0;
  }
  *ppwszURL = v5;
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v8 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v8 >> 31) + 2) << 9) | 3, 0xEAu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180097684  mov     [rsp-28h+arg_0], rbx
0x180097689  push    rbp
0x18009768a  push    rsi
0x18009768b  push    rdi
0x18009768c  push    r14
0x18009768e  push    r15
0x180097690  mov     rbp, rsp
0x180097693  sub     rsp, 30h
0x180097697  xor     esi, esi
0x180097699  mov     r15, ppwszURL
0x18009769c  mov     [rbp+pwszTargetUrl], rsi
0x1800976a0  xor     edi, edi
0x1800976a2  mov     [rbp+cch], esi
0x1800976a5  mov     r14, urlComp
0x1800976a8  mov     r9, this; _a1
0x1800976ab  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x1800976b2  jz      short $retryCreateUrl
0x1800976b4  mov     [rsp+30h+_a2], ppwszURL; _a2
0x1800976b9  mov     edx, 0E9h; id
0x1800976be  lea     ppwszURL, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800976c5  mov     ecx, 403h; LevelKeyword
0x1800976ca  call    WPP_SF_qq
0x1800976cf  lea     r9, [rbp+cch]; lpdwUrlLength
0x1800976d3  mov     ppwszURL, rsi; lpszUrl
0x1800976d6  xor     edx, edx; dwFlags
0x1800976d8  mov     this, r14; lpUrlComponents
0x1800976db  call    cs:__imp_InternetCreateUrlW
0x1800976e1  test    eax, eax
0x1800976e3  jnz     short loc_18009772D
0x1800976e5  call    cs:__imp_GetLastError
0x1800976eb  mov     ebx, eax
0x1800976ed  cmp     eax, 7Ah ; 'z'
0x1800976f0  jnz     short loc_180097717
0x1800976f2  shr     [rbp+cch], 1
0x1800976f5  mov     this, rsi; pv
0x1800976f8  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800976fd  mov     ecx, [rbp+cch]; cch
0x180097700  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x180097705  mov     rsi, rax
0x180097708  test    rax, rax
0x18009770b  jnz     short $retryCreateUrl
0x18009770d  mov     ebx, 8007000Eh
0x180097712  jmp     loc_1800977CA
0x180097717  test    eax, eax
0x180097719  jle     $CleanUp_119
0x18009771f  movzx   ebx, ax
0x180097722  or      ebx, 80070000h
0x180097728  jmp     $CleanUp_119
0x18009772d  test    rsi, rsi
0x180097730  jnz     short loc_18009773C
0x180097732  mov     ebx, 80004005h
0x180097737  jmp     loc_1800977CA
0x18009773c  mov     r8d, [rbp+cch]; cch
0x180097740  lea     rax, [rbp+cch]
0x180097744  lea     r9, [rbp+pwszTargetUrl]; ppchEncoded
0x180097748  mov     [rsp+30h+_a2], rax; pcchEncoded
0x18009774d  mov     urlComp, rsi; pchSrc
0x180097750  lea     this, szURLChars; "#"
0x180097757  call    ?EscapeChars@URL@@SAJPEBGPEAGKPEAPEAGPEAK@Z; URL::EscapeChars(ushort const *,ushort *,ulong,ushort * *,ulong *)
0x18009775c  mov     ebx, eax
0x18009775e  test    eax, eax
0x180097760  js      short $CleanUp_119
0x180097762  mov     eax, [rbp+cch]
0x180097765  lea     ecx, [rax+1]; cch
0x180097768  cmp     ecx, eax
0x18009776a  jb      short loc_1800977B0
0x18009776c  mov     [rbp+cch], ecx
0x18009776f  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x180097774  mov     rdi, rax
0x180097777  test    rax, rax
0x18009777a  jnz     short $RetryCanonUrl
0x18009777c  mov     ebx, 8007000Eh
0x180097781  jmp     short $CleanUp_119
0x180097783  mov     this, [rbp+pwszTargetUrl]; pszUrl
0x180097787  lea     ppwszURL, [rbp+cch]; pcchCanonicalized
0x18009778b  mov     r9d, 8000000h; dwFlags
0x180097791  mov     urlComp, rdi; pszCanonicalized
0x180097794  call    cs:__imp_UrlCanonicalizeW
0x18009779a  mov     ebx, eax
0x18009779c  cmp     eax, 80004003h
0x1800977a1  jnz     short $CleanUp_119
0x1800977a3  mov     this, rdi; pv
0x1800977a6  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800977ab  mov     ecx, [rbp+cch]
0x1800977ae  jmp     short loc_18009776F
0x1800977b0  mov     [rbp+cch], 0FFFFFFFFh
0x1800977b7  mov     ebx, 80070216h
0x1800977bc  mov     this, [rbp+pwszTargetUrl]; pv
0x1800977c0  cmp     this, rsi
0x1800977c3  jz      short loc_1800977CA
0x1800977c5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800977ca  mov     this, rsi; pv
0x1800977cd  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800977d2  test    ebx, ebx
0x1800977d4  jns     short loc_1800977E0
0x1800977d6  mov     this, rdi; pv
0x1800977d9  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800977de  xor     edi, edi
0x1800977e0  mov     [r15], rdi
0x1800977e3  mov     r9d, ebx; __annotation("TMF:",
0x1800977e6  sar     r9d, 1Fh
0x1800977ea  lea     eax, ds:4[r9*2]
0x1800977f2  movsxd  this, eax
0x1800977f5  lea     rax, g_rgFastWppLevelEnabledFlags
0x1800977fc  test    byte ptr [rax+this*8], 8
0x180097800  jz      short loc_18009782B
0x180097802  add     r9w, 2
0x180097807  lea     ppwszURL, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009780e  movzx   ecx, r9w
0x180097812  mov     eax, 200h
0x180097817  imul    ecx, eax
0x18009781a  mov     edx, 0EAh; id
0x18009781f  mov     r9d, ebx; _a1
0x180097822  or      cx, 3; LevelKeyword
0x180097826  call    WPP_SF_d
0x18009782b  mov     eax, ebx
0x18009782d  mov     rbx, [rsp+30h+arg_0]
0x180097832  add     rsp, 30h
0x180097836  pop     r15
0x180097838  pop     r14
0x18009783a  pop     rdi
0x18009783b  pop     rsi
0x18009783c  pop     rbp
0x18009783d  retn
```
