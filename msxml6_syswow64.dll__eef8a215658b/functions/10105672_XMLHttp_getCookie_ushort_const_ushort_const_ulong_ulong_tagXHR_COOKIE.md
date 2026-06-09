# XMLHttp::getCookie(ushort const *,ushort const *,ulong,ulong *,tagXHR_COOKIE * *)

- ea: `0x10105672`
- end: `0x1010588f`
- name: `?getCookie@XMLHttp@@QAGJPBG0KPAKPAPAUtagXHR_COOKIE@@@Z`
- size: `541`
- prototype: `HRESULT __fastcall(XMLHttp *this, const wchar_t *pwszUrl, const wchar_t *pwszName, unsigned int dwFlags, unsigned int *pcCookies, tagXHR_COOKIE **ppCookies)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10103fe9`

## callees

- `0x10067b20`
- `0x1006c2c4`
- `0x10101e09`
- `0x10105672`
- `0x10180006`
- `0x101801c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1010583b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105811`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10105823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1010583b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1010573a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1010573a`
- `WININET!InternetFreeCookies` at `0x10105857`
- `WININET!InternetFreeCookies` at `0x10105857`
- `WININET!InternetGetCookieEx2` at `0x10105718`
- `WININET!InternetGetCookieEx2` at `0x10105718`

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
  if ( (byte_10185760[0] & 2) != 0 )
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
  if ( (byte_10185760[16 * (v6 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 1, 0x56u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10105672  mov     edi, edi
0x10105674  push    ebp
0x10105675  mov     ebp, esp
0x10105677  sub     esp, 18h
0x1010567a  push    ebx
0x1010567b  push    edi
0x1010567c  mov     [ebp+pcwszUrl], pwszUrl
0x1010567f  mov     eax, this
0x10105681  mov     [ebp+pCookies2], 0
0x10105688  mov     [ebp+dwCookie2Count], 0
0x1010568f  test    byte_10185760, 2; __annotation("TMF:",
0x10105696  mov     edi, [ebp+dwFlags]
0x10105699  mov     ebx, [ebp+ppCookies]
0x1010569c  jz      short loc_101056B2
0x1010569e  mov     this, [ebp+pcCookies]
0x101056a1  push    ebx; LevelKeyword
0x101056a2  push    this; _a6
0x101056a3  push    edi; _a5
0x101056a4  push    [ebp+pwszName]; _a4
0x101056a7  push    pwszUrl; _a3
0x101056a8  push    eax; _a2
0x101056a9  push    this; _a1
0x101056aa  push    55h ; 'U'
0x101056ac  pop     pwszUrl; id
0x101056ad  call    _WPP_SF_qSSDqq@36; WPP_SF_qSSDqq(x,x,x,x,x,x,x,x,x)
0x101056b2  mov     eax, [ebp+pcCookies]
0x101056b5  test    eax, eax
0x101056b7  jnz     short loc_101056C3
0x101056b9  mov     edi, 80004003h
0x101056be  jmp     loc_10105851
0x101056c3  mov     dword ptr [eax], 0
0x101056c9  test    ebx, ebx
0x101056cb  jz      short loc_101056B9
0x101056cd  push    esi
0x101056ce  mov     esi, ?g_pfnEntry@@3P6GPAUTLSDATA@@XZA; TLSDATA * (*g_pfnEntry)(void)
0x101056d4  mov     this, esi; this
0x101056d6  mov     dword ptr [ebx], 0
0x101056dc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101056e2  call    esi ; TLSDATA * (*g_pfnEntry)(void)
0x101056e4  test    eax, eax
0x101056e6  jnz     short loc_101056F2
0x101056e8  mov     edi, 80004005h
0x101056ed  jmp     loc_10105850
0x101056f2  mov     this, edi
0x101056f4  lea     eax, [ebp+dwCookie2Count]
0x101056f7  or      this, 1000h
0x101056fd  test    edi, 2000h
0x10105703  push    eax; pdwCookieCount
0x10105704  lea     eax, [ebp+pCookies2]
0x10105707  cmovz   this, edi
0x1010570a  push    eax; ppCookies
0x1010570b  and     this, 20461010h
0x10105711  push    this; dwFlags
0x10105712  push    [ebp+pwszName]; pcwszCookieName
0x10105715  push    [ebp+pcwszUrl]; pcwszUrl
0x10105718  call    ds:__imp__InternetGetCookieEx2@20; InternetGetCookieEx2(x,x,x,x,x)
0x1010571e  mov     edi, eax
0x10105720  test    edi, edi
0x10105722  jle     short loc_1010572F
0x10105724  movzx   edi, di
0x10105727  or      edi, 80070000h
0x1010572d  test    edi, edi
0x1010572f  js      loc_10105850
0x10105735  imul    eax, [ebp+dwCookie2Count], 1Ch
0x10105739  push    eax; cb
0x1010573a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10105740  mov     ebx, eax
0x10105742  test    ebx, ebx
0x10105744  jnz     short loc_10105750
0x10105746  mov     edi, 8007000Eh
0x1010574b  jmp     loc_10105850
0x10105750  imul    eax, [ebp+dwCookie2Count], 1Ch
0x10105754  push    eax; Size
0x10105755  push    0; Val
0x10105757  push    ebx; void *
0x10105758  call    _memset
0x1010575d  add     esp, 0Ch
0x10105760  xor     this, this
0x10105762  mov     [ebp+var_18], this
0x10105765  cmp     this, [ebp+dwCookie2Count]
0x10105768  jnb     loc_10105843
0x1010576e  imul    eax, this, 1Ch
0x10105771  mov     esi, this
0x10105773  mov     this, [ebp+pcwszUrl]; pcwszSrc
0x10105776  shl     esi, 5
0x10105779  add     esi, [ebp+pCookies2]
0x1010577c  add     eax, ebx
0x1010577e  mov     pwszUrl, eax; ppwszDst
0x10105780  mov     [ebp+var_8], eax
0x10105783  call    ?CoTaskDupStr@@YGJPBGPAPAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x10105788  mov     edi, eax
0x1010578a  mov     [ebp+var_C], edi
0x1010578d  test    edi, edi
0x1010578f  js      short loc_101057EA
0x10105791  mov     this, [esi]; pcwszSrc
0x10105793  test    this, this
0x10105795  jz      short loc_101057AB
0x10105797  mov     pwszUrl, [ebp+var_8]
0x1010579a  add     pwszUrl, 4; ppwszDst
0x1010579d  call    ?CoTaskDupStr@@YGJPBGPAPAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x101057a2  mov     edi, eax
0x101057a4  mov     [ebp+var_C], edi
0x101057a7  test    edi, edi
0x101057a9  js      short loc_101057EA
0x101057ab  mov     this, [esi+4]; pcwszSrc
0x101057ae  test    this, this
0x101057b0  jz      short loc_101057C6
0x101057b2  mov     pwszUrl, [ebp+var_8]
0x101057b5  lea     pwszUrl, [pwszUrl+8]; ppwszDst
0x101057b8  call    ?CoTaskDupStr@@YGJPBGPAPAG@Z; CoTaskDupStr(ushort const *,ushort * *)
0x101057bd  mov     edi, eax
0x101057bf  mov     [ebp+var_C], edi
0x101057c2  test    edi, edi
0x101057c4  js      short loc_101057EA
0x101057c6  cmp     dword ptr [esi+1Ch], 0
0x101057ca  mov     pwszUrl, [ebp+var_8]
0x101057cd  jz      short loc_101057DB
0x101057cf  mov     eax, [esi+14h]
0x101057d2  mov     this, [esi+18h]
0x101057d5  mov     [pwszUrl+10h], eax
0x101057d8  mov     [pwszUrl+14h], this
0x101057db  mov     this, [ebp+var_18]
0x101057de  mov     eax, [esi+10h]
0x101057e1  inc     this
0x101057e2  mov     [pwszUrl+18h], eax
0x101057e5  jmp     loc_10105762
0x101057ea  cmp     [ebp+dwCookie2Count], 0
0x101057ee  mov     [ebp+var_18], 0
0x101057f5  jbe     short loc_1010583A
0x101057f7  mov     edi, [ebp+var_18]
0x101057fa  imul    esi, edi, 1Ch
0x101057fd  push    dword ptr [esi+ebx]; pv
0x10105800  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10105806  push    dword ptr [esi+ebx+4]; pv
0x1010580a  mov     dword ptr [esi+ebx], 0
0x10105811  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10105817  push    dword ptr [esi+ebx+8]; pv
0x1010581b  mov     dword ptr [esi+ebx+4], 0
0x10105823  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10105829  inc     edi
0x1010582a  mov     dword ptr [esi+ebx+8], 0
0x10105832  cmp     edi, [ebp+dwCookie2Count]
0x10105835  jb      short loc_101057FA
0x10105837  mov     edi, [ebp+var_C]
0x1010583a  push    ebx; pv
0x1010583b  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10105841  jmp     short loc_10105850
0x10105843  mov     eax, [ebp+ppCookies]
0x10105846  mov     this, [ebp+pcCookies]
0x10105849  mov     [eax], ebx
0x1010584b  mov     eax, [ebp+dwCookie2Count]
0x1010584e  mov     [this], eax
0x10105850  pop     esi
0x10105851  push    [ebp+dwCookie2Count]; dwCookieCount
0x10105854  push    [ebp+pCookies2]; pCookies
0x10105857  call    ds:__imp__InternetFreeCookies@8; InternetFreeCookies(x,x)
0x1010585d  mov     this, edi; __annotation("TMF:",
0x1010585f  sar     this, 1Fh
0x10105862  mov     eax, this
0x10105864  shl     eax, 4
0x10105867  test    byte_10185760[eax], 2
0x1010586e  jz      short loc_10105887
0x10105870  push    edi; _a1
0x10105871  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10105876  add     this, 2
0x10105879  shl     this, 9
0x1010587c  push    56h ; 'V'
0x1010587e  or      this, 1; LevelKeyword
0x10105881  pop     pwszUrl; id
0x10105882  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10105887  mov     eax, edi
0x10105889  pop     edi
0x1010588a  pop     ebx
0x1010588b  leave
0x1010588c  retn    10h
```
