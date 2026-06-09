# XMLHttp2::_GetResponseHeader(ushort const *,ushort * *)

- ea: `0x10103ffa`
- end: `0x1010413b`
- name: `?_GetResponseHeader@XMLHttp2@@AAGJPBGPAPAG@Z`
- size: `321`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, const wchar_t *pwszHeader@<edx>, wchar_t **ppwszValue)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10102820`

## callees

- `0x1005536b`
- `0x10067bc0`
- `0x10103ffa`
- `0x10180006`
- `0x10180543`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101040ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x101040ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101040c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x101040c3`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104070`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104070`
- `OLEAUT32!__imp__SysFreeString@4` at `0x101040f7`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104100`
- `OLEAUT32!__imp__SysFreeString@4` at `0x101040f7`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104100`
- `OLEAUT32!__imp__SysStringLen@4` at `0x101040b3`
- `OLEAUT32!__imp__SysStringLen@4` at `0x101040b3`

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
  if ( (byte_101857A0[0] & 2) != 0 )
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
  if ( (byte_101857A0[16 * (v5 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v5 >> 31) + 2) << 9) | 1, 0x9Cu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x10103ffa  mov     edi, edi
0x10103ffc  push    ebp
0x10103ffd  mov     ebp, esp
0x10103fff  sub     esp, 10h
0x10104002  push    ebx
0x10104003  push    esi
0x10104004  mov     esi, this
0x10104006  mov     eax, pwszHeader
0x10104008  xor     this, this
0x1010400a  mov     [ebp+psz], eax
0x1010400d  push    edi
0x1010400e  mov     [ebp+var_C], esi
0x10104011  mov     edi, this
0x10104013  mov     [ebp+bstrString], this
0x10104016  mov     [ebp+bstrValue], this
0x10104019  test    byte_101857A0, 2; __annotation("TMF:",
0x10104020  mov     ebx, [ebp+ppwszValue]
0x10104023  jz      short loc_1010403E
0x10104025  push    ebx; _a3
0x10104026  push    eax; _a2
0x10104027  push    esi; _a1
0x10104028  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1010402d  mov     pwszHeader, 9Bh; id
0x10104032  mov     this, 401h; LevelKeyword
0x10104037  call    _WPP_SF_qSq@24; WPP_SF_qSq(x,x,x,x,x,x)
0x1010403c  xor     this, this
0x1010403e  test    ebx, ebx
0x10104040  jnz     short loc_1010404C
0x10104042  mov     esi, 80004003h
0x10104047  jmp     CleanUp_374
0x1010404c  mov     [ebx], this
0x1010404e  cmp     [esi+1Ch], this
0x10104051  jz      short loc_1010406D
0x10104053  mov     esi, [esi+1Ch]
0x10104056  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1010405c  cmp     esi, eax
0x1010405e  jz      short loc_1010406A
0x10104060  mov     esi, 8001010Eh
0x10104065  jmp     CleanUp_374
0x1010406a  mov     esi, [ebp+var_C]
0x1010406d  push    [ebp+psz]; psz
0x10104070  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104076  mov     pwszHeader, eax
0x10104078  mov     [ebp+bstrString], pwszHeader
0x1010407b  test    pwszHeader, pwszHeader
0x1010407d  jnz     short loc_10104086
0x1010407f  mov     esi, 8007000Eh
0x10104084  jmp     short CleanUp_374
0x10104086  mov     this, [esi+18h]
0x10104089  mov     eax, [this]
0x1010408b  mov     esi, [eax+24h]
0x1010408e  lea     eax, [ebp+bstrValue]
0x10104091  push    eax
0x10104092  push    pwszHeader
0x10104093  push    this
0x10104094  mov     this, esi; this
0x10104096  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1010409c  call    esi
0x1010409e  mov     esi, eax
0x101040a0  test    esi, esi
0x101040a2  js      short CleanUp_374
0x101040a4  mov     eax, [ebp+bstrValue]
0x101040a7  test    eax, eax
0x101040a9  jz      short loc_101040E8
0x101040ab  xor     this, this
0x101040ad  cmp     [eax], cx
0x101040b0  jz      short loc_101040E8
0x101040b2  push    eax; pbstr
0x101040b3  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x101040b9  mov     esi, eax
0x101040bb  lea     this, ds:2[esi*2]
0x101040c2  push    this; cb
0x101040c3  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x101040c9  mov     edi, eax
0x101040cb  test    edi, edi
0x101040cd  jz      short loc_1010407F
0x101040cf  push    [ebp+bstrValue]; pszSrc
0x101040d2  lea     pwszHeader, [esi+1]; cchDest
0x101040d5  mov     this, edi; pszDest
0x101040d7  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x101040dc  mov     esi, eax
0x101040de  test    esi, esi
0x101040e0  js      short CleanUp_374
0x101040e2  mov     [ebx], edi
0x101040e4  xor     edi, edi
0x101040e6  jmp     short CleanUp_374
0x101040e8  mov     esi, 80070002h
0x101040ed  push    edi; pv
0x101040ee  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x101040f4  push    [ebp+bstrString]; bstrString
0x101040f7  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x101040fd  push    [ebp+bstrValue]; bstrString
0x10104100  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104106  mov     this, esi; __annotation("TMF:",
0x10104108  sar     this, 1Fh
0x1010410b  mov     eax, this
0x1010410d  shl     eax, 4
0x10104110  test    byte_101857A0[eax], 2
0x10104117  jz      short loc_10104132
0x10104119  add     this, 2
0x1010411c  mov     pwszHeader, 9Ch; id
0x10104121  push    esi; _a1
0x10104122  shl     this, 9
0x10104125  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x1010412a  or      this, 1; LevelKeyword
0x1010412d  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104132  pop     edi
0x10104133  mov     eax, esi
0x10104135  pop     esi
0x10104136  pop     ebx
0x10104137  leave
0x10104138  retn    4
```
