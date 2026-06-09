# XMLHttp::getCookie(ushort const *,ushort const *,ulong,ulong *,tagXHR_COOKIE * *)

- ea: `0x10105552`
- end: `0x1010576f`
- name: `?getCookie@XMLHttp@@QAGJPBG0KPAKPAPAUtagXHR_COOKIE@@@Z`
- size: `541`
- prototype: `HRESULT __fastcall(XMLHttp *this, const wchar_t *pwszUrl, const wchar_t *pwszName, unsigned int dwFlags, unsigned int *pcCookies, tagXHR_COOKIE **ppCookies)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10103ec9`

## callees

- `0x10067bc0`
- `0x1006c354`
- `0x10101cf9`
- `0x10105552`
- `0x10180006`
- `0x101801c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101056e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101056f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105703`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1010571b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101056e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101056f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105703`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1010571b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1010561a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1010561a`
- `WININET!InternetFreeCookies` at `0x10105737`
- `WININET!InternetFreeCookies` at `0x10105737`
- `WININET!InternetGetCookieEx2` at `0x101055f8`
- `WININET!InternetGetCookieEx2` at `0x101055f8`

## pseudocode

```c
HRESULT __fastcall XMLHttp::getCookie(
        XMLHttp *this,
        const wchar_t *pwszUrl,
        const wchar_t *pwszName,
        unsigned int dwFlags,
        unsigned int *pcCookies,
        tagXHR_COOKIE **ppCookies)
{
  signed int v6; // edi
  _array<NodeSet *> *v7; // ecx
  unsigned int v8; // ecx
  signed int CookieEx2; // eax
  bool v10; // sf
  tagXHR_COOKIE *v11; // ebx
  unsigned int v12; // ecx
  INTERNET_COOKIE2 *v13; // esi
  const wchar_t *pwszValue; // ecx
  wchar_t **p_pwszUrl; // edx
  wchar_t *dwHighDateTime; // ecx
  unsigned int i; // edi
  int v18; // esi
  wchar_t *v20; // [esp-8h] [ebp-28h]
  wchar_t *v21; // [esp-8h] [ebp-28h]
  unsigned int v22; // [esp+8h] [ebp-18h]
  INTERNET_COOKIE2 *pCookies2; // [esp+10h] [ebp-10h] BYREF
  signed int v25; // [esp+14h] [ebp-Ch]
  tagXHR_COOKIE *v26; // [esp+18h] [ebp-8h]
  unsigned int dwCookie2Count; // [esp+1Ch] [ebp-4h] BYREF

  pCookies2 = 0;
  dwCookie2Count = 0;
  if ( (byte_101857A0[0] & 2) != 0 )
    WPP_SF_qSSDqq(pcCookies, this, pwszUrl, pwszName, dwFlags, pcCookies, ppCookies);
  if ( pcCookies && (*pcCookies = 0, ppCookies) )
  {
    v7 = g_pfnEntry;
    *ppCookies = 0;
    if ( ((int (__thiscall *)(_array<NodeSet *> *))v7)(v7) )
    {
      v8 = dwFlags | 0x1000;
      if ( (dwFlags & 0x2000) == 0 )
        v8 = dwFlags;
      CookieEx2 = InternetGetCookieEx2(pwszUrl, pwszName, v8 & 0x20461010, &pCookies2, &dwCookie2Count);
      v6 = CookieEx2;
      v10 = CookieEx2 < 0;
      if ( CookieEx2 > 0 )
      {
        v6 = (unsigned __int16)CookieEx2 | 0x80070000;
        v10 = 1;
      }
      if ( !v10 )
      {
        v11 = (tagXHR_COOKIE *)CoTaskMemAlloc(28 * dwCookie2Count);
        if ( v11 )
        {
          memset((void *)v11, 0, 28 * dwCookie2Count);
          v12 = 0;
          while ( 1 )
          {
            v22 = v12;
            if ( v12 >= dwCookie2Count )
            {
              *ppCookies = v11;
              *pcCookies = dwCookie2Count;
              goto LABEL_31;
            }
            v13 = &pCookies2[v12];
            v26 = &v11[v12];
            v6 = CoTaskDupStr(pwszUrl, &v26->pwszUrl);
            v25 = v6;
            if ( v6 < 0 )
              break;
            if ( v13->pwszName )
            {
              v6 = CoTaskDupStr(v13->pwszName, &v26->pwszName);
              v25 = v6;
              if ( v6 < 0 )
                break;
            }
            pwszValue = v13->pwszValue;
            if ( pwszValue )
            {
              v6 = CoTaskDupStr(pwszValue, &v26->pwszValue);
              v25 = v6;
              if ( v6 < 0 )
                break;
            }
            p_pwszUrl = &v26->pwszUrl;
            if ( v13->fExpiresSet )
            {
              dwHighDateTime = (wchar_t *)v13->ftExpires.dwHighDateTime;
              v26->ftExpires.dwLowDateTime = v13->ftExpires.dwLowDateTime;
              p_pwszUrl[5] = dwHighDateTime;
            }
            v12 = v22 + 1;
            p_pwszUrl[6] = (wchar_t *)v13->dwFlags;
          }
          if ( dwCookie2Count )
          {
            for ( i = 0; i < dwCookie2Count; ++i )
            {
              v18 = i;
              CoTaskMemFree(v11[i].pwszUrl);
              v20 = v11[i].pwszName;
              v11[v18].pwszUrl = 0;
              CoTaskMemFree(v20);
              v21 = v11[i].pwszValue;
              v11[v18].pwszName = 0;
              CoTaskMemFree(v21);
              v11[v18].pwszValue = 0;
            }
            v6 = v25;
          }
          CoTaskMemFree((LPVOID)v11);
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147467259;
    }
  }
  else
  {
    v6 = -2147467261;
  }
LABEL_31:
  InternetFreeCookies(pCookies2, dwCookie2Count);
  if ( (byte_101857A0[16 * (v6 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 1, 0x56u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10105552  mov     edi, edi
0x10105554  push    ebp
0x10105555  mov     ebp, esp
0x10105557  sub     esp, 18h
0x1010555a  push    ebx
0x1010555b  push    edi
0x1010555c  mov     [ebp+pcwszUrl], pwszUrl
0x1010555f  mov     eax, this
0x10105561  mov     [ebp+pCookies2], 0
0x10105568  mov     [ebp+dwCookie2Count], 0
0x1010556f  test    byte_101857A0, 2; __annotation("TMF:",
0x10105576  mov     edi, [ebp+dwFlags]
0x10105579  mov     ebx, [ebp+ppCookies]
0x1010557c  jz      short loc_10105592
0x1010557e  mov     this, [ebp+pcCookies]
0x10105581  push    ebx; LevelKeyword
0x10105582  push    this; _a6
0x10105583  push    edi; _a5
0x10105584  push    [ebp+pwszName]; _a4
0x10105587  push    pwszUrl; _a3
0x10105588  push    eax; _a2
0x10105589  push    this; _a1
0x1010558a  push    55h ; 'U'
0x1010558c  pop     pwszUrl; id
0x1010558d  call    _WPP_SF_qSSDqq@36; WPP_SF_qSSDqq(x,x,x,x,x,x,x,x,x)
0x10105592  mov     eax, [ebp+pcCookies]
0x10105595  test    eax, eax
0x10105597  jnz     short loc_101055A3
0x10105599  mov     edi, 80004003h
0x1010559e  jmp     loc_10105731
0x101055a3  mov     dword ptr [eax], 0
0x101055a9  test    ebx, ebx
0x101055ab  jz      short loc_10105599
0x101055ad  push    esi
0x101055ae  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x101055b4  mov     this, esi; this
0x101055b6  mov     dword ptr [ebx], 0
0x101055bc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101055c2  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x101055c4  test    eax, eax
0x101055c6  jnz     short loc_101055D2
0x101055c8  mov     edi, 80004005h
0x101055cd  jmp     loc_10105730
0x101055d2  mov     this, edi
0x101055d4  lea     eax, [ebp+dwCookie2Count]
0x101055d7  or      this, 1000h
0x101055dd  test    edi, 2000h
0x101055e3  push    eax; pdwCookieCount
0x101055e4  lea     eax, [ebp+pCookies2]
0x101055e7  cmovz   this, edi
0x101055ea  push    eax; ppCookies
0x101055eb  and     this, 20461010h
0x101055f1  push    this; dwFlags
0x101055f2  push    [ebp+pwszName]; pcwszCookieName
0x101055f5  push    [ebp+pcwszUrl]; pcwszUrl
0x101055f8  call    ds:__imp__InternetGetCookieEx2@20; InternetGetCookieEx2(x,x,x,x,x)
0x101055fe  mov     edi, eax
0x10105600  test    edi, edi
0x10105602  jle     short loc_1010560F
0x10105604  movzx   edi, di
0x10105607  or      edi, 80070000h
0x1010560d  test    edi, edi
0x1010560f  js      loc_10105730
0x10105615  imul    eax, [ebp+dwCookie2Count], 1Ch
0x10105619  push    eax; cb
0x1010561a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10105620  mov     ebx, eax
0x10105622  test    ebx, ebx
0x10105624  jnz     short loc_10105630
0x10105626  mov     edi, 8007000Eh
0x1010562b  jmp     loc_10105730
0x10105630  imul    eax, [ebp+dwCookie2Count], 1Ch
0x10105634  push    eax; Size
0x10105635  push    0; Val
0x10105637  push    ebx; void *
0x10105638  call    _memset
0x1010563d  add     esp, 0Ch
0x10105640  xor     this, this
0x10105642  mov     [ebp+var_18], this
0x10105645  cmp     this, [ebp+dwCookie2Count]
0x10105648  jnb     loc_10105723
0x1010564e  imul    eax, this, 1Ch
0x10105651  mov     esi, this
0x10105653  mov     this, [ebp+pcwszUrl]; pcwszSrc
0x10105656  shl     esi, 5
0x10105659  add     esi, [ebp+pCookies2]
0x1010565c  add     eax, ebx
0x1010565e  mov     pwszUrl, eax; ppwszDst
0x10105660  mov     [ebp+var_8], eax
0x10105663  call    ?CoTaskDupStr@@YGJPBGPAPAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x10105668  mov     edi, eax
0x1010566a  mov     [ebp+var_C], edi
0x1010566d  test    edi, edi
0x1010566f  js      short loc_101056CA
0x10105671  mov     this, [esi]; pcwszSrc
0x10105673  test    this, this
0x10105675  jz      short loc_1010568B
0x10105677  mov     pwszUrl, [ebp+var_8]
0x1010567a  add     pwszUrl, 4; ppwszDst
0x1010567d  call    ?CoTaskDupStr@@YGJPBGPAPAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x10105682  mov     edi, eax
0x10105684  mov     [ebp+var_C], edi
0x10105687  test    edi, edi
0x10105689  js      short loc_101056CA
0x1010568b  mov     this, [esi+4]; pcwszSrc
0x1010568e  test    this, this
0x10105690  jz      short loc_101056A6
0x10105692  mov     pwszUrl, [ebp+var_8]
0x10105695  lea     pwszUrl, [pwszUrl+8]; ppwszDst
0x10105698  call    ?CoTaskDupStr@@YGJPBGPAPAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x1010569d  mov     edi, eax
0x1010569f  mov     [ebp+var_C], edi
0x101056a2  test    edi, edi
0x101056a4  js      short loc_101056CA
0x101056a6  cmp     dword ptr [esi+1Ch], 0
0x101056aa  mov     pwszUrl, [ebp+var_8]
0x101056ad  jz      short loc_101056BB
0x101056af  mov     eax, [esi+14h]
0x101056b2  mov     this, [esi+18h]
0x101056b5  mov     [pwszUrl+10h], eax
0x101056b8  mov     [pwszUrl+14h], this
0x101056bb  mov     this, [ebp+var_18]
0x101056be  mov     eax, [esi+10h]
0x101056c1  inc     this
0x101056c2  mov     [pwszUrl+18h], eax
0x101056c5  jmp     loc_10105642
0x101056ca  cmp     [ebp+dwCookie2Count], 0
0x101056ce  mov     [ebp+var_18], 0
0x101056d5  jbe     short loc_1010571A
0x101056d7  mov     edi, [ebp+var_18]
0x101056da  imul    esi, edi, 1Ch
0x101056dd  push    dword ptr [esi+ebx]; pv
0x101056e0  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101056e6  push    dword ptr [esi+ebx+4]; pv
0x101056ea  mov     dword ptr [esi+ebx], 0
0x101056f1  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101056f7  push    dword ptr [esi+ebx+8]; pv
0x101056fb  mov     dword ptr [esi+ebx+4], 0
0x10105703  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10105709  inc     edi
0x1010570a  mov     dword ptr [esi+ebx+8], 0
0x10105712  cmp     edi, [ebp+dwCookie2Count]
0x10105715  jb      short loc_101056DA
0x10105717  mov     edi, [ebp+var_C]
0x1010571a  push    ebx; pv
0x1010571b  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10105721  jmp     short loc_10105730
0x10105723  mov     eax, [ebp+ppCookies]
0x10105726  mov     this, [ebp+pcCookies]
0x10105729  mov     [eax], ebx
0x1010572b  mov     eax, [ebp+dwCookie2Count]
0x1010572e  mov     [this], eax
0x10105730  pop     esi
0x10105731  push    [ebp+dwCookie2Count]; dwCookieCount
0x10105734  push    [ebp+pCookies2]; pCookies
0x10105737  call    ds:__imp__InternetFreeCookies@8; InternetFreeCookies(x,x)
0x1010573d  mov     this, edi; __annotation("TMF:",
0x1010573f  sar     this, 1Fh
0x10105742  mov     eax, this
0x10105744  shl     eax, 4
0x10105747  test    byte_101857A0[eax], 2
0x1010574e  jz      short loc_10105767
0x10105750  push    edi; _a1
0x10105751  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10105756  add     this, 2
0x10105759  shl     this, 9
0x1010575c  push    56h ; 'V'
0x1010575e  or      this, 1; LevelKeyword
0x10105761  pop     pwszUrl; id
0x10105762  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10105767  mov     eax, edi
0x10105769  pop     edi
0x1010576a  pop     ebx
0x1010576b  leave
0x1010576c  retn    10h
```
