# XMLHttp2::_GetResponseHeader(ushort const *,ushort * *)

- ea: `0x1010411a`
- end: `0x1010425b`
- name: `?_GetResponseHeader@XMLHttp2@@AAGJPBGPAPAG@Z`
- size: `321`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, const wchar_t *pwszHeader@<edx>, wchar_t **ppwszValue)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10102930`

## callees

- `0x100552db`
- `0x10067b20`
- `0x1010411a`
- `0x10180006`
- `0x10180543`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104176`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1010420e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1010420e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101041e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101041e3`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104190`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104190`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104217`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104220`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104217`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104220`
- `OLEAUT32!__imp__SysStringLen@4` at `0x101041d3`
- `OLEAUT32!__imp__SysStringLen@4` at `0x101041d3`

## pseudocode

```c
HRESULT __fastcall XMLHttp2::_GetResponseHeader(XMLHttp2 *this, const wchar_t *pwszHeader, wchar_t **ppwszValue)
{
  XMLHttp2 *v3; // esi
  wchar_t *v4; // edi
  int v5; // esi
  unsigned int m_dwStaThreadId; // esi
  BSTR v7; // edx
  UINT v8; // esi
  wchar_t *v9; // eax
  wchar_t *bstrString; // [esp+14h] [ebp-8h]
  wchar_t *bstrValue; // [esp+18h] [ebp-4h] BYREF

  v3 = this;
  v4 = 0;
  bstrString = 0;
  bstrValue = 0;
  if ( (byte_10185760[0] & 2) != 0 )
    WPP_SF_qSq(0x401u, 0x9Bu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, pwszHeader, ppwszValue);
  if ( !ppwszValue )
  {
    v5 = -2147467261;
    goto CleanUp_374;
  }
  *ppwszValue = 0;
  if ( v3->m_dwStaThreadId )
  {
    m_dwStaThreadId = v3->m_dwStaThreadId;
    if ( m_dwStaThreadId != GetCurrentThreadId() )
    {
      v5 = -2147417842;
      goto CleanUp_374;
    }
    v3 = this;
  }
  v7 = SysAllocString(pwszHeader);
  bstrString = v7;
  if ( !v7 )
    goto LABEL_10;
  v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLHTTPRequest *, wchar_t *, wchar_t **), XMLHttp *, BSTR, wchar_t **))v3->m_pXMLHttp->getResponseHeader)(
         v3->m_pXMLHttp->getResponseHeader,
         v3->m_pXMLHttp,
         v7,
         &bstrValue);
  if ( v5 >= 0 )
  {
    if ( bstrValue && *bstrValue )
    {
      v8 = SysStringLen(bstrValue);
      v9 = (wchar_t *)CoTaskMemAlloc(2 * v8 + 2);
      v4 = v9;
      if ( !v9 )
      {
LABEL_10:
        v5 = -2147024882;
        goto CleanUp_374;
      }
      v5 = StringCchCopyW(v9, v8 + 1, bstrValue);
      if ( v5 >= 0 )
      {
        *ppwszValue = v4;
        v4 = 0;
      }
    }
    else
    {
      v5 = -2147024894;
    }
  }
CleanUp_374:
  CoTaskMemFree(v4);
  SysFreeString(bstrString);
  SysFreeString(bstrValue);
  if ( (byte_10185760[16 * (v5 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v5 >> 31) + 2) << 9) | 1, 0x9Cu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1010411a  mov     edi, edi
0x1010411c  push    ebp
0x1010411d  mov     ebp, esp
0x1010411f  sub     esp, 10h
0x10104122  push    ebx
0x10104123  push    esi
0x10104124  mov     esi, this
0x10104126  mov     eax, pwszHeader
0x10104128  xor     this, this
0x1010412a  mov     [ebp+psz], eax
0x1010412d  push    edi
0x1010412e  mov     [ebp+var_C], esi
0x10104131  mov     edi, this
0x10104133  mov     [ebp+bstrString], this
0x10104136  mov     [ebp+bstrValue], this
0x10104139  test    byte_10185760, 2; __annotation("TMF:",
0x10104140  mov     ebx, [ebp+ppwszValue]
0x10104143  jz      short loc_1010415E
0x10104145  push    ebx; _a3
0x10104146  push    eax; _a2
0x10104147  push    esi; _a1
0x10104148  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1010414d  mov     pwszHeader, 9Bh; id
0x10104152  mov     this, 401h; LevelKeyword
0x10104157  call    _WPP_SF_qSq@24; WPP_SF_qSq(x,x,x,x,x,x)
0x1010415c  xor     this, this
0x1010415e  test    ebx, ebx
0x10104160  jnz     short loc_1010416C
0x10104162  mov     esi, 80004003h
0x10104167  jmp     CleanUp_374
0x1010416c  mov     [ebx], this
0x1010416e  cmp     [esi+1Ch], this
0x10104171  jz      short loc_1010418D
0x10104173  mov     esi, [esi+1Ch]
0x10104176  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1010417c  cmp     esi, eax
0x1010417e  jz      short loc_1010418A
0x10104180  mov     esi, 8001010Eh
0x10104185  jmp     CleanUp_374
0x1010418a  mov     esi, [ebp+var_C]
0x1010418d  push    [ebp+psz]; psz
0x10104190  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104196  mov     pwszHeader, eax
0x10104198  mov     [ebp+bstrString], pwszHeader
0x1010419b  test    pwszHeader, pwszHeader
0x1010419d  jnz     short loc_101041A6
0x1010419f  mov     esi, 8007000Eh
0x101041a4  jmp     short CleanUp_374
0x101041a6  mov     this, [esi+18h]
0x101041a9  mov     eax, [this]
0x101041ab  mov     esi, [eax+24h]
0x101041ae  lea     eax, [ebp+bstrValue]
0x101041b1  push    eax
0x101041b2  push    pwszHeader
0x101041b3  push    this
0x101041b4  mov     this, esi; this
0x101041b6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101041bc  call    esi
0x101041be  mov     esi, eax
0x101041c0  test    esi, esi
0x101041c2  js      short CleanUp_374
0x101041c4  mov     eax, [ebp+bstrValue]
0x101041c7  test    eax, eax
0x101041c9  jz      short loc_10104208
0x101041cb  xor     this, this
0x101041cd  cmp     [eax], cx
0x101041d0  jz      short loc_10104208
0x101041d2  push    eax; pbstr
0x101041d3  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x101041d9  mov     esi, eax
0x101041db  lea     this, ds:2[esi*2]
0x101041e2  push    this; cb
0x101041e3  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x101041e9  mov     edi, eax
0x101041eb  test    edi, edi
0x101041ed  jz      short loc_1010419F
0x101041ef  push    [ebp+bstrValue]; pszSrc
0x101041f2  lea     pwszHeader, [esi+1]; cchDest
0x101041f5  mov     this, edi; pszDest
0x101041f7  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x101041fc  mov     esi, eax
0x101041fe  test    esi, esi
0x10104200  js      short CleanUp_374
0x10104202  mov     [ebx], edi
0x10104204  xor     edi, edi
0x10104206  jmp     short CleanUp_374
0x10104208  mov     esi, 80070002h
0x1010420d  push    edi; pv
0x1010420e  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10104214  push    [ebp+bstrString]; bstrString
0x10104217  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x1010421d  push    [ebp+bstrValue]; bstrString
0x10104220  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104226  mov     this, esi; __annotation("TMF:",
0x10104228  sar     this, 1Fh
0x1010422b  mov     eax, this
0x1010422d  shl     eax, 4
0x10104230  test    byte_10185760[eax], 2
0x10104237  jz      short loc_10104252
0x10104239  add     this, 2
0x1010423c  mov     pwszHeader, 9Ch; id
0x10104241  push    esi; _a1
0x10104242  shl     this, 9
0x10104245  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1010424a  or      this, 1; LevelKeyword
0x1010424d  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104252  pop     edi
0x10104253  mov     eax, esi
0x10104255  pop     esi
0x10104256  pop     ebx
0x10104257  leave
0x10104258  retn    4
```
