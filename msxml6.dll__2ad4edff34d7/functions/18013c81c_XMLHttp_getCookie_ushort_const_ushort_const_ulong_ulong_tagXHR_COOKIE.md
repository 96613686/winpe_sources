# XMLHttp::getCookie(ushort const *,ushort const *,ulong,ulong *,tagXHR_COOKIE * *)

- ea: `0x18013c81c`
- end: `0x18013ca94`
- name: `?getCookie@XMLHttp@@QEAAJPEBG0KPEAKPEAPEAUtagXHR_COOKIE@@@Z`
- size: `632`
- prototype: `__int64 __fastcall(XMLHttp *this, const wchar_t *pwszUrl, const _GUID *pwszName, unsigned int dwFlags, unsigned int *pcCookies, tagXHR_COOKIE **ppCookies)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013b5d4`

## callees

- `0x1800955e8`
- `0x1800cba94`
- `0x18013c81c`
- `0x180185008`
- `0x18018530c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013c9e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013c9f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ca03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ca1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013c9e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013c9f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ca03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013ca1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18013c909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18013c909`
- `WININET!InternetFreeCookies` at `0x18013ca33`
- `WININET!InternetFreeCookies` at `0x18013ca33`
- `WININET!InternetGetCookieEx2` at `0x18013c8e1`
- `WININET!InternetGetCookieEx2` at `0x18013c8e1`

## pseudocode

```c
__int64 __fastcall XMLHttp::getCookie(
        XMLHttp *this,
        const wchar_t *pwszUrl,
        const _GUID *pwszName,
        unsigned int dwFlags,
        unsigned int *pcCookies,
        tagXHR_COOKIE **ppCookies)
{
  signed int v10; // edi
  TLSDATA *(__fastcall *v11)(); // rax
  unsigned int v12; // r8d
  signed int CookieEx2; // eax
  tagXHR_COOKIE *v14; // rsi
  __int64 i; // rax
  INTERNET_COOKIE2 *v16; // r14
  __int64 v17; // rbx
  tagXHR_COOKIE *v18; // r13
  const wchar_t *v19; // rcx
  const wchar_t *pwszValue; // rcx
  unsigned int j; // r15d
  __int64 v22; // rbx
  wchar_t *v23; // rcx
  wchar_t *v24; // rcx
  unsigned int v25; // eax
  unsigned int dwCookie2Count; // [rsp+50h] [rbp-18h] BYREF
  INTERNET_COOKIE2 *pCookies2; // [rsp+58h] [rbp-10h] BYREF
  int v30; // [rsp+D0h] [rbp+68h]

  pCookies2 = 0;
  dwCookie2Count = 0;
  if ( (xmmword_1801F6C20 & 2) != 0 )
    WPP_SF_qSSDqq(
      (unsigned __int16)this,
      0x55u,
      pwszName,
      this,
      pwszUrl,
      (const wchar_t *)pwszName,
      dwFlags,
      pcCookies,
      ppCookies);
  if ( pcCookies && (*pcCookies = 0, ppCookies) )
  {
    v11 = g_pfnEntry;
    *ppCookies = 0;
    if ( ((__int64 (__fastcall *)(XMLHttp *))v11)(this) )
    {
      v12 = dwFlags | 0x1000;
      if ( (dwFlags & 0x2000) == 0 )
        v12 = dwFlags;
      CookieEx2 = InternetGetCookieEx2(pwszUrl, (PCWSTR)pwszName, v12 & 0x20461010, &pCookies2, &dwCookie2Count);
      v10 = CookieEx2;
      if ( CookieEx2 > 0 )
        v10 = (unsigned __int16)CookieEx2 | 0x80070000;
      if ( v10 >= 0 )
      {
        v14 = (tagXHR_COOKIE *)CoTaskMemAlloc(48LL * dwCookie2Count);
        if ( v14 )
        {
          memset_0((void *)v14, 0, 48LL * dwCookie2Count);
          for ( i = 0; ; i = (unsigned int)(v30 + 1) )
          {
            v30 = i;
            if ( (unsigned int)i >= dwCookie2Count )
            {
              v25 = dwCookie2Count;
              *ppCookies = v14;
              *pcCookies = v25;
              goto LABEL_29;
            }
            v16 = pCookies2;
            v17 = i;
            v18 = &v14[i];
            v10 = CoTaskDupStr(pwszUrl, &v18->pwszUrl);
            if ( v10 < 0 )
              break;
            v19 = v16[v17].pwszName;
            if ( v19 )
            {
              v10 = CoTaskDupStr(v19, &v18->pwszName);
              if ( v10 < 0 )
                break;
            }
            pwszValue = v16[v17].pwszValue;
            if ( pwszValue )
            {
              v10 = CoTaskDupStr(pwszValue, &v18->pwszValue);
              if ( v10 < 0 )
                break;
            }
            if ( v16[v17].fExpiresSet )
              v18->ftExpires = v16[v17].ftExpires;
            v18->dwFlags = v16[v17].dwFlags;
          }
          for ( j = 0; j < dwCookie2Count; v14[v22].pwszValue = 0 )
          {
            v22 = j;
            CoTaskMemFree(v14[j].pwszUrl);
            v23 = v14[j].pwszName;
            v14[j].pwszUrl = 0;
            CoTaskMemFree(v23);
            v24 = v14[j].pwszValue;
            v14[j].pwszName = 0;
            CoTaskMemFree(v24);
            ++j;
          }
          CoTaskMemFree((LPVOID)v14);
        }
        else
        {
          v10 = -2147024882;
        }
      }
    }
    else
    {
      v10 = -2147467259;
    }
  }
  else
  {
    v10 = -2147467261;
  }
LABEL_29:
  InternetFreeCookies(pCookies2, dwCookie2Count);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v10 >> 31) + 4].rgbFlags[0] & 2) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(v10 >> 31) + 2) << 9) | 1,
      0x56u,
      WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids,
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18013c81c  mov     rax, rsp
0x18013c81f  mov     [rax+10h], pwszUrl
0x18013c823  push    rbp
0x18013c824  push    rbx
0x18013c825  push    rsi
0x18013c826  push    rdi
0x18013c827  push    r12
0x18013c829  push    r13
0x18013c82b  push    r14
0x18013c82d  push    r15
0x18013c82f  mov     rbp, rsp
0x18013c832  sub     rsp, 68h
0x18013c836  xor     r14d, r14d
0x18013c839  mov     ebx, dwFlags
0x18013c83c  mov     [rbp+pCookies2], r14
0x18013c840  mov     rdi, pwszName
0x18013c843  mov     [rbp+dwCookie2Count], r14d
0x18013c847  mov     rsi, pwszUrl
0x18013c84a  test    byte ptr cs:xmmword_1801F6C20, 2; __annotation("TMF:",
0x18013c851  mov     r12, [rbp+arg_28]
0x18013c855  mov     r15, [rbp+arg_20]
0x18013c859  jz      short loc_18013C87B
0x18013c85b  mov     [rax-68h], r12
0x18013c85f  lea     edx, [r14+55h]; _a1
0x18013c863  mov     [rax-70h], r15
0x18013c867  mov     r9, this; _a3
0x18013c86a  mov     [rax-78h], ebx
0x18013c86d  mov     [rax-80h], pwszName
0x18013c871  mov     [rsp+68h+_a4], rsi; _a4
0x18013c876  call    WPP_SF_qSSDqq
0x18013c87b  mov     r13d, 1
0x18013c881  test    r15, r15
0x18013c884  jnz     short loc_18013C890
0x18013c886  mov     edi, 80004003h
0x18013c88b  jmp     loc_18013CA2C
0x18013c890  mov     [r15], r14d
0x18013c893  test    r12, r12
0x18013c896  jz      short loc_18013C886
0x18013c898  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18013c89f  mov     [r12], r14
0x18013c8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c8a8  test    rax, rax
0x18013c8ab  jnz     short loc_18013C8B7
0x18013c8ad  mov     edi, 80004005h
0x18013c8b2  jmp     loc_18013CA2C
0x18013c8b7  mov     r8d, ebx
0x18013c8ba  lea     rax, [rbp+dwCookie2Count]
0x18013c8be  bts     r8d, 0Ch
0x18013c8c3  mov     [rsp+68h+_a4], rax; pdwCookieCount
0x18013c8c8  bt      ebx, 0Dh
0x18013c8cc  lea     r9, [rbp+pCookies2]; ppCookies
0x18013c8d0  mov     pwszUrl, rdi; pcwszCookieName
0x18013c8d3  mov     this, rsi; pcwszUrl
0x18013c8d6  cmovnb  r8d, ebx
0x18013c8da  and     r8d, 20461010h; dwFlags
0x18013c8e1  call    cs:__imp_InternetGetCookieEx2
0x18013c8e7  mov     edi, eax
0x18013c8e9  test    eax, eax
0x18013c8eb  jle     short loc_18013C8F6
0x18013c8ed  movzx   edi, ax
0x18013c8f0  or      edi, 80070000h
0x18013c8f6  test    edi, edi
0x18013c8f8  js      loc_18013CA2C
0x18013c8fe  mov     eax, [rbp+dwCookie2Count]
0x18013c901  lea     this, [rax+rax*2]
0x18013c905  shl     this, 4; cb
0x18013c909  call    cs:__imp_CoTaskMemAlloc
0x18013c90f  mov     rsi, rax
0x18013c912  test    rax, rax
0x18013c915  jnz     short loc_18013C921
0x18013c917  mov     edi, 8007000Eh
0x18013c91c  jmp     loc_18013CA2C
0x18013c921  mov     eax, [rbp+dwCookie2Count]
0x18013c924  xor     edx, edx; Val
0x18013c926  mov     this, rsi; void *
0x18013c929  lea     pwszName, [rax+rax*2]
0x18013c92d  shl     pwszName, 4; Size
0x18013c931  call    memset_0
0x18013c936  mov     eax, r14d
0x18013c939  mov     dword ptr [rbp+arg_20], eax
0x18013c93c  cmp     eax, [rbp+dwCookie2Count]
0x18013c93f  jnb     loc_18013CA22
0x18013c945  mov     this, [rbp+pcwszSrc]; pcwszSrc
0x18013c949  lea     rbx, [rax+rax*2]
0x18013c94d  mov     r14, [rbp+pCookies2]
0x18013c951  add     rbx, rbx
0x18013c954  lea     r13, [rsi+rbx*8]
0x18013c958  mov     pwszUrl, r13; ppwszDst
0x18013c95b  call    ?CoTaskDupStr@@YAJPEBGPEAPEAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x18013c960  mov     edi, eax
0x18013c962  test    eax, eax
0x18013c964  js      short loc_18013C9C2
0x18013c966  mov     this, [r14+rbx*8]; pcwszSrc
0x18013c96a  test    this, this
0x18013c96d  jz      short loc_18013C97E
0x18013c96f  lea     pwszUrl, [r13+8]; ppwszDst
0x18013c973  call    ?CoTaskDupStr@@YAJPEBGPEAPEAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x18013c978  mov     edi, eax
0x18013c97a  test    eax, eax
0x18013c97c  js      short loc_18013C9C2
0x18013c97e  mov     this, [r14+rbx*8+8]; pcwszSrc
0x18013c983  test    this, this
0x18013c986  jz      short loc_18013C997
0x18013c988  lea     pwszUrl, [r13+10h]; ppwszDst
0x18013c98c  call    ?CoTaskDupStr@@YAJPEBGPEAPEAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x18013c991  mov     edi, eax
0x18013c993  test    eax, eax
0x18013c995  js      short loc_18013C9C2
0x18013c997  cmp     dword ptr [r14+rbx*8+2Ch], 0
0x18013c99d  jz      short loc_18013C9A8
0x18013c99f  mov     rax, [r14+rbx*8+24h]
0x18013c9a4  mov     [r13+20h], rax
0x18013c9a8  mov     eax, [r14+rbx*8+20h]
0x18013c9ad  mov     [r13+28h], eax
0x18013c9b1  mov     r13d, 1
0x18013c9b7  mov     eax, dword ptr [rbp+arg_20]
0x18013c9ba  add     eax, r13d
0x18013c9bd  jmp     loc_18013C939
0x18013c9c2  xor     r12d, r12d
0x18013c9c5  mov     r14, rsi
0x18013c9c8  mov     r15d, r12d
0x18013c9cb  lea     r13d, [r12+1]
0x18013c9d0  cmp     [rbp+dwCookie2Count], r12d
0x18013c9d4  jbe     short loc_18013CA17
0x18013c9d6  mov     eax, r15d
0x18013c9d9  lea     rbx, [rax+rax*2]
0x18013c9dd  add     rbx, rbx
0x18013c9e0  mov     this, [r14+rbx*8]; pv
0x18013c9e4  call    cs:__imp_CoTaskMemFree
0x18013c9ea  mov     this, [r14+rbx*8+8]; pv
0x18013c9ef  mov     [r14+rbx*8], r12
0x18013c9f3  call    cs:__imp_CoTaskMemFree
0x18013c9f9  mov     this, [r14+rbx*8+10h]; pv
0x18013c9fe  mov     [r14+rbx*8+8], r12
0x18013ca03  call    cs:__imp_CoTaskMemFree
0x18013ca09  add     r15d, r13d
0x18013ca0c  mov     [r14+rbx*8+10h], r12
0x18013ca11  cmp     r15d, [rbp+dwCookie2Count]
0x18013ca15  jb      short loc_18013C9D6
0x18013ca17  mov     this, rsi; pv
0x18013ca1a  call    cs:__imp_CoTaskMemFree
0x18013ca20  jmp     short loc_18013CA2C
0x18013ca22  mov     eax, [rbp+dwCookie2Count]
0x18013ca25  mov     [r12], rsi
0x18013ca29  mov     [r15], eax
0x18013ca2c  mov     edx, [rbp+dwCookie2Count]; dwCookieCount
0x18013ca2f  mov     this, [rbp+pCookies2]; pCookies
0x18013ca33  call    cs:__imp_InternetFreeCookies
0x18013ca39  mov     r8d, edi; __annotation("TMF:",
0x18013ca3c  sar     r8d, 1Fh
0x18013ca40  lea     eax, ds:4[pwszName*2]
0x18013ca48  movsxd  this, eax
0x18013ca4b  lea     rax, g_rgFastWppLevelEnabledFlags
0x18013ca52  test    byte ptr [rax+this*8], 2
0x18013ca56  jz      short loc_18013CA81
0x18013ca58  add     r8w, 2
0x18013ca5d  mov     eax, 200h
0x18013ca62  movzx   ecx, r8w
0x18013ca66  mov     edx, 56h ; 'V'; id
0x18013ca6b  imul    ecx, eax
0x18013ca6e  lea     pwszName, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18013ca75  mov     dwFlags, edi; _a1
0x18013ca78  or      cx, r13w; LevelKeyword
0x18013ca7c  call    WPP_SF_d
0x18013ca81  mov     eax, edi
0x18013ca83  add     rsp, 68h
0x18013ca87  pop     r15
0x18013ca89  pop     r14
0x18013ca8b  pop     r13
0x18013ca8d  pop     r12
0x18013ca8f  pop     rdi
0x18013ca90  pop     rsi
0x18013ca91  pop     rbx
0x18013ca92  pop     rbp
0x18013ca93  retn
```
