# URLMONRequest::createUrl(URL_COMPONENTSW,ushort * *)

- ea: `0x180098214`
- end: `0x1800983e1`
- name: `?createUrl@URLMONRequest@@IEAAJUURL_COMPONENTSW@@PEAPEAG@Z`
- size: `461`
- prototype: `HRESULT __fastcall(URLMONRequest *this, URL_COMPONENTSW urlComp, wchar_t **ppwszURL)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009c230`

## callees

- `0x180016588`
- `0x180017480`
- `0x180098214`
- `0x1800983e8`
- `0x180189008`
- `0x180189d98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009827b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009827b`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x180098330`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x180098330`
- `WININET!InternetCreateUrlW` at `0x18009826b`
- `WININET!InternetCreateUrlW` at `0x18009826b`

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
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_qq(0x403u, 0xE9u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, ppwszURL);
  while ( !InternetCreateUrlW(urlComp, 0, v3, &cch) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      goto $CleanUp_117;
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
          goto $CleanUp_117;
        MemFree(v5);
        v9 = cch;
      }
      v8 = -2147024882;
    }
  }
$CleanUp_117:
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
0x180098214  mov     [rsp-28h+arg_0], rbx
0x180098219  push    rbp
0x18009821a  push    rsi
0x18009821b  push    rdi
0x18009821c  push    r14
0x18009821e  push    r15
0x180098220  mov     rbp, rsp
0x180098223  sub     rsp, 30h
0x180098227  xor     esi, esi
0x180098229  mov     r15, ppwszURL
0x18009822c  mov     [rbp+pwszTargetUrl], rsi
0x180098230  xor     edi, edi
0x180098232  mov     [rbp+cch], esi
0x180098235  mov     r14, urlComp
0x180098238  mov     r9, this; _a1
0x18009823b  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180098242  jz      short $retryCreateUrl
0x180098244  mov     [rsp+30h+_a2], ppwszURL; _a2
0x180098249  mov     edx, 0E9h; id
0x18009824e  lea     ppwszURL, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180098255  mov     ecx, 403h; LevelKeyword
0x18009825a  call    WPP_SF_qq
0x18009825f  lea     r9, [rbp+cch]; lpdwUrlLength
0x180098263  mov     ppwszURL, rsi; lpszUrl
0x180098266  xor     edx, edx; dwFlags
0x180098268  mov     this, r14; lpUrlComponents
0x18009826b  call    cs:__imp_InternetCreateUrlW
0x180098272  nop     dword ptr [rax+rax+00h]
0x180098277  test    eax, eax
0x180098279  jnz     short loc_1800982C9
0x18009827b  call    cs:__imp_GetLastError
0x180098282  nop     dword ptr [rax+rax+00h]
0x180098287  mov     ebx, eax
0x180098289  cmp     eax, 7Ah ; 'z'
0x18009828c  jnz     short loc_1800982B3
0x18009828e  shr     [rbp+cch], 1
0x180098291  mov     this, rsi; pv
0x180098294  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180098299  mov     ecx, [rbp+cch]; cch
0x18009829c  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x1800982a1  mov     rsi, rax
0x1800982a4  test    rax, rax
0x1800982a7  jnz     short $retryCreateUrl
0x1800982a9  mov     ebx, 8007000Eh
0x1800982ae  jmp     loc_18009836C
0x1800982b3  test    eax, eax
0x1800982b5  jle     $CleanUp_117
0x1800982bb  movzx   ebx, ax
0x1800982be  or      ebx, 80070000h
0x1800982c4  jmp     $CleanUp_117
0x1800982c9  test    rsi, rsi
0x1800982cc  jnz     short loc_1800982D8
0x1800982ce  mov     ebx, 80004005h
0x1800982d3  jmp     loc_18009836C
0x1800982d8  mov     r8d, [rbp+cch]; cch
0x1800982dc  lea     rax, [rbp+cch]
0x1800982e0  lea     r9, [rbp+pwszTargetUrl]; ppchEncoded
0x1800982e4  mov     [rsp+30h+_a2], rax; pcchEncoded
0x1800982e9  mov     urlComp, rsi; pchSrc
0x1800982ec  lea     this, szURLChars; "#"
0x1800982f3  call    ?EscapeChars@URL@@SAJPEBGPEAGKPEAPEAGPEAK@Z; URL::EscapeChars(ushort const *,ushort *,ulong,ushort * *,ulong *)
0x1800982f8  mov     ebx, eax
0x1800982fa  test    eax, eax
0x1800982fc  js      short $CleanUp_117
0x1800982fe  mov     eax, [rbp+cch]
0x180098301  lea     ecx, [rax+1]; cch
0x180098304  cmp     ecx, eax
0x180098306  jb      short loc_180098352
0x180098308  mov     [rbp+cch], ecx
0x18009830b  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x180098310  mov     rdi, rax
0x180098313  test    rax, rax
0x180098316  jnz     short $RetryCanonUrl
0x180098318  mov     ebx, 8007000Eh
0x18009831d  jmp     short $CleanUp_117
0x18009831f  mov     this, [rbp+pwszTargetUrl]; pszUrl
0x180098323  lea     ppwszURL, [rbp+cch]; pcchCanonicalized
0x180098327  mov     r9d, 8000000h; dwFlags
0x18009832d  mov     urlComp, rdi; pszCanonicalized
0x180098330  call    cs:__imp_UrlCanonicalizeW
0x180098337  nop     dword ptr [rax+rax+00h]
0x18009833c  mov     ebx, eax
0x18009833e  cmp     eax, 80004003h
0x180098343  jnz     short $CleanUp_117
0x180098345  mov     this, rdi; pv
0x180098348  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18009834d  mov     ecx, [rbp+cch]
0x180098350  jmp     short loc_18009830B
0x180098352  mov     [rbp+cch], 0FFFFFFFFh
0x180098359  mov     ebx, 80070216h
0x18009835e  mov     this, [rbp+pwszTargetUrl]; pv
0x180098362  cmp     this, rsi
0x180098365  jz      short loc_18009836C
0x180098367  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18009836c  mov     this, rsi; pv
0x18009836f  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180098374  test    ebx, ebx
0x180098376  jns     short loc_180098382
0x180098378  mov     this, rdi; pv
0x18009837b  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180098380  xor     edi, edi
0x180098382  mov     [r15], rdi
0x180098385  mov     r9d, ebx; __annotation("TMF:",
0x180098388  sar     r9d, 1Fh
0x18009838c  lea     eax, ds:4[r9*2]
0x180098394  movsxd  this, eax
0x180098397  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009839e  test    byte ptr [rax+this*8], 8
0x1800983a2  jz      short loc_1800983CD
0x1800983a4  add     r9w, 2
0x1800983a9  lea     ppwszURL, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800983b0  movzx   ecx, r9w
0x1800983b4  mov     eax, 200h
0x1800983b9  imul    ecx, eax
0x1800983bc  mov     edx, 0EAh; id
0x1800983c1  mov     r9d, ebx; _a1
0x1800983c4  or      cx, 3; LevelKeyword
0x1800983c8  call    WPP_SF_d
0x1800983cd  mov     eax, ebx
0x1800983cf  mov     rbx, [rsp+30h+arg_0]
0x1800983d4  add     rsp, 30h
0x1800983d8  pop     r15
0x1800983da  pop     r14
0x1800983dc  pop     rdi
0x1800983dd  pop     rsi
0x1800983de  pop     rbp
0x1800983df  retn
```
