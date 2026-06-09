# XMLHttp::getCookie(ushort const *,ushort const *,ulong,ulong *,tagXHR_COOKIE * *)

- ea: `0x18013f9bc`
- end: `0x18013fc5f`
- name: `?getCookie@XMLHttp@@QEAAJPEBG0KPEAKPEAPEAUtagXHR_COOKIE@@@Z`
- size: `675`
- prototype: `HRESULT __fastcall(XMLHttp *this, const wchar_t *pwszUrl, const wchar_t *pwszName, unsigned int dwFlags, unsigned int *pcCookies, tagXHR_COOKIE **ppCookies)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013e704`

## callees

- `0x18009582c`
- `0x1800cd3e4`
- `0x18013f9bc`
- `0x180189008`
- `0x180189314`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fb90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fbbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fbd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fb90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fbbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013fbd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18013faaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18013faaf`
- `WININET!InternetFreeCookies` at `0x18013fbf7`
- `WININET!InternetFreeCookies` at `0x18013fbf7`
- `WININET!InternetGetCookieEx2` at `0x18013fa81`
- `WININET!InternetGetCookieEx2` at `0x18013fa81`

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
  if ( (xmmword_1801FAD20 & 2) != 0 )
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
0x18013f9bc  mov     rax, rsp
0x18013f9bf  mov     [rax+10h], pwszUrl
0x18013f9c3  push    rbp
0x18013f9c4  push    rbx
0x18013f9c5  push    rsi
0x18013f9c6  push    rdi
0x18013f9c7  push    r12
0x18013f9c9  push    r13
0x18013f9cb  push    r14
0x18013f9cd  push    r15
0x18013f9cf  mov     rbp, rsp
0x18013f9d2  sub     rsp, 68h
0x18013f9d6  xor     r14d, r14d
0x18013f9d9  mov     ebx, dwFlags
0x18013f9dc  mov     [rbp+pCookies2], r14
0x18013f9e0  mov     rdi, pwszName
0x18013f9e3  mov     [rbp+dwCookie2Count], r14d
0x18013f9e7  mov     rsi, pwszUrl
0x18013f9ea  test    byte ptr cs:xmmword_1801FAD20, 2; __annotation("TMF:",
0x18013f9f1  mov     r12, [rbp+arg_28]
0x18013f9f5  mov     r15, [rbp+arg_20]
0x18013f9f9  jz      short loc_18013FA1B
0x18013f9fb  mov     [rax-68h], r12
0x18013f9ff  lea     edx, [r14+55h]; _a1
0x18013fa03  mov     [rax-70h], r15
0x18013fa07  mov     r9, this; _a3
0x18013fa0a  mov     [rax-78h], ebx
0x18013fa0d  mov     [rax-80h], pwszName
0x18013fa11  mov     [rsp+68h+_a4], rsi; _a4
0x18013fa16  call    WPP_SF_qSSDqq
0x18013fa1b  mov     r13d, 1
0x18013fa21  test    r15, r15
0x18013fa24  jnz     short loc_18013FA30
0x18013fa26  mov     edi, 80004003h
0x18013fa2b  jmp     loc_18013FBF0
0x18013fa30  mov     [r15], r14d
0x18013fa33  test    r12, r12
0x18013fa36  jz      short loc_18013FA26
0x18013fa38  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18013fa3f  mov     [r12], r14
0x18013fa43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fa48  test    rax, rax
0x18013fa4b  jnz     short loc_18013FA57
0x18013fa4d  mov     edi, 80004005h
0x18013fa52  jmp     loc_18013FBF0
0x18013fa57  mov     r8d, ebx
0x18013fa5a  lea     rax, [rbp+dwCookie2Count]
0x18013fa5e  bts     r8d, 0Ch
0x18013fa63  mov     [rsp+68h+_a4], rax; pdwCookieCount
0x18013fa68  bt      ebx, 0Dh
0x18013fa6c  lea     r9, [rbp+pCookies2]; ppCookies
0x18013fa70  mov     pwszUrl, rdi; pcwszCookieName
0x18013fa73  mov     this, rsi; pcwszUrl
0x18013fa76  cmovnb  r8d, ebx
0x18013fa7a  and     r8d, 20461010h; dwFlags
0x18013fa81  call    cs:__imp_InternetGetCookieEx2
0x18013fa88  nop     dword ptr [rax+rax+00h]
0x18013fa8d  mov     edi, eax
0x18013fa8f  test    eax, eax
0x18013fa91  jle     short loc_18013FA9C
0x18013fa93  movzx   edi, ax
0x18013fa96  or      edi, 80070000h
0x18013fa9c  test    edi, edi
0x18013fa9e  js      loc_18013FBF0
0x18013faa4  mov     eax, [rbp+dwCookie2Count]
0x18013faa7  lea     this, [rax+rax*2]
0x18013faab  shl     this, 4; cb
0x18013faaf  call    cs:__imp_CoTaskMemAlloc
0x18013fab6  nop     dword ptr [rax+rax+00h]
0x18013fabb  mov     rsi, rax
0x18013fabe  test    rax, rax
0x18013fac1  jnz     short loc_18013FACD
0x18013fac3  mov     edi, 8007000Eh
0x18013fac8  jmp     loc_18013FBF0
0x18013facd  mov     eax, [rbp+dwCookie2Count]
0x18013fad0  xor     edx, edx; Val
0x18013fad2  mov     this, rsi; void *
0x18013fad5  lea     pwszName, [rax+rax*2]
0x18013fad9  shl     pwszName, 4; Size
0x18013fadd  call    memset_0
0x18013fae2  mov     eax, r14d
0x18013fae5  mov     dword ptr [rbp+arg_20], eax
0x18013fae8  cmp     eax, [rbp+dwCookie2Count]
0x18013faeb  jnb     loc_18013FBE6
0x18013faf1  mov     this, [rbp+pcwszSrc]; pcwszSrc
0x18013faf5  lea     rbx, [rax+rax*2]
0x18013faf9  mov     r14, [rbp+pCookies2]
0x18013fafd  add     rbx, rbx
0x18013fb00  lea     r13, [rsi+rbx*8]
0x18013fb04  mov     pwszUrl, r13; ppwszDst
0x18013fb07  call    ?CoTaskDupStr@@YAJPEBGPEAPEAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x18013fb0c  mov     edi, eax
0x18013fb0e  test    eax, eax
0x18013fb10  js      short loc_18013FB6E
0x18013fb12  mov     this, [r14+rbx*8]; pcwszSrc
0x18013fb16  test    this, this
0x18013fb19  jz      short loc_18013FB2A
0x18013fb1b  lea     pwszUrl, [r13+8]; ppwszDst
0x18013fb1f  call    ?CoTaskDupStr@@YAJPEBGPEAPEAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x18013fb24  mov     edi, eax
0x18013fb26  test    eax, eax
0x18013fb28  js      short loc_18013FB6E
0x18013fb2a  mov     this, [r14+rbx*8+8]; pcwszSrc
0x18013fb2f  test    this, this
0x18013fb32  jz      short loc_18013FB43
0x18013fb34  lea     pwszUrl, [r13+10h]; ppwszDst
0x18013fb38  call    ?CoTaskDupStr@@YAJPEBGPEAPEAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x18013fb3d  mov     edi, eax
0x18013fb3f  test    eax, eax
0x18013fb41  js      short loc_18013FB6E
0x18013fb43  cmp     dword ptr [r14+rbx*8+2Ch], 0
0x18013fb49  jz      short loc_18013FB54
0x18013fb4b  mov     rax, [r14+rbx*8+24h]
0x18013fb50  mov     [r13+20h], rax
0x18013fb54  mov     eax, [r14+rbx*8+20h]
0x18013fb59  mov     [r13+28h], eax
0x18013fb5d  mov     r13d, 1
0x18013fb63  mov     eax, dword ptr [rbp+arg_20]
0x18013fb66  add     eax, r13d
0x18013fb69  jmp     loc_18013FAE5
0x18013fb6e  xor     r12d, r12d
0x18013fb71  mov     r14, rsi
0x18013fb74  mov     r15d, r12d
0x18013fb77  lea     r13d, [r12+1]
0x18013fb7c  cmp     [rbp+dwCookie2Count], r12d
0x18013fb80  jbe     short loc_18013FBD5
0x18013fb82  mov     eax, r15d
0x18013fb85  lea     rbx, [rax+rax*2]
0x18013fb89  add     rbx, rbx
0x18013fb8c  mov     this, [r14+rbx*8]; pv
0x18013fb90  call    cs:__imp_CoTaskMemFree
0x18013fb97  nop     dword ptr [rax+rax+00h]
0x18013fb9c  mov     this, [r14+rbx*8+8]; pv
0x18013fba1  mov     [r14+rbx*8], r12
0x18013fba5  call    cs:__imp_CoTaskMemFree
0x18013fbac  nop     dword ptr [rax+rax+00h]
0x18013fbb1  mov     this, [r14+rbx*8+10h]; pv
0x18013fbb6  mov     [r14+rbx*8+8], r12
0x18013fbbb  call    cs:__imp_CoTaskMemFree
0x18013fbc2  nop     dword ptr [rax+rax+00h]
0x18013fbc7  add     r15d, r13d
0x18013fbca  mov     [r14+rbx*8+10h], r12
0x18013fbcf  cmp     r15d, [rbp+dwCookie2Count]
0x18013fbd3  jb      short loc_18013FB82
0x18013fbd5  mov     this, rsi; pv
0x18013fbd8  call    cs:__imp_CoTaskMemFree
0x18013fbdf  nop     dword ptr [rax+rax+00h]
0x18013fbe4  jmp     short loc_18013FBF0
0x18013fbe6  mov     eax, [rbp+dwCookie2Count]
0x18013fbe9  mov     [r12], rsi
0x18013fbed  mov     [r15], eax
0x18013fbf0  mov     edx, [rbp+dwCookie2Count]; dwCookieCount
0x18013fbf3  mov     this, [rbp+pCookies2]; pCookies
0x18013fbf7  call    cs:__imp_InternetFreeCookies
0x18013fbfe  nop     dword ptr [rax+rax+00h]
0x18013fc03  mov     r8d, edi; __annotation("TMF:",
0x18013fc06  sar     r8d, 1Fh
0x18013fc0a  lea     eax, ds:4[pwszName*2]
0x18013fc12  movsxd  this, eax
0x18013fc15  lea     rax, g_rgFastWppLevelEnabledFlags
0x18013fc1c  test    byte ptr [rax+this*8], 2
0x18013fc20  jz      short loc_18013FC4B
0x18013fc22  add     r8w, 2
0x18013fc27  mov     eax, 200h
0x18013fc2c  movzx   ecx, r8w
0x18013fc30  mov     edx, 56h ; 'V'; id
0x18013fc35  imul    ecx, eax
0x18013fc38  lea     pwszName, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x18013fc3f  mov     dwFlags, edi; _a1
0x18013fc42  or      cx, r13w; LevelKeyword
0x18013fc46  call    WPP_SF_d
0x18013fc4b  mov     eax, edi
0x18013fc4d  add     rsp, 68h
0x18013fc51  pop     r15
0x18013fc53  pop     r14
0x18013fc55  pop     r13
0x18013fc57  pop     r12
0x18013fc59  pop     rdi
0x18013fc5a  pop     rsi
0x18013fc5b  pop     rbx
0x18013fc5c  pop     rbp
0x18013fc5d  retn
```
