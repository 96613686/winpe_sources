# XMLHttp2::_GetAllResponseHeaders(ushort * *)

- ea: `0x10103dab`
- end: `0x10103ec3`
- name: `?_GetAllResponseHeaders@XMLHttp2@@AAGJPAPAG@Z`
- size: `280`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, wchar_t **ppwszHeaders@<edx>)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10102550`

## callees

- `0x1005536b`
- `0x10067bc0`
- `0x10103dab`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10103dff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10103dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10103e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10103e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10103e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10103e4f`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10103e8a`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10103e8a`
- `OLEAUT32!__imp__SysStringLen@4` at `0x10103e3f`
- `OLEAUT32!__imp__SysStringLen@4` at `0x10103e3f`

## pseudocode

```c
HRESULT __fastcall XMLHttp2::_GetAllResponseHeaders(XMLHttp2 *this, wchar_t **ppwszHeaders)
{
  XMLHttp2 *v2; // eax
  wchar_t *v4; // edi
  int v5; // esi
  unsigned int m_dwStaThreadId; // esi
  UINT v7; // esi
  wchar_t *v8; // eax
  wchar_t *bstrHeaders; // [esp+10h] [ebp-4h] BYREF

  v2 = this;
  v4 = 0;
  bstrHeaders = 0;
  if ( (byte_101857A0[0] & 2) != 0 )
  {
    WPP_SF_qq(0x401u, 0x97u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, ppwszHeaders);
    v2 = this;
  }
  if ( !ppwszHeaders )
  {
    v5 = -2147467261;
    goto CleanUp_371;
  }
  *ppwszHeaders = 0;
  if ( v2->m_dwStaThreadId )
  {
    m_dwStaThreadId = v2->m_dwStaThreadId;
    if ( m_dwStaThreadId != GetCurrentThreadId() )
    {
      v5 = -2147417842;
      goto CleanUp_371;
    }
    v2 = this;
  }
  v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLHTTPRequest *, wchar_t **), XMLHttp *, wchar_t **))v2->m_pXMLHttp->getAllResponseHeaders)(
         v2->m_pXMLHttp->getAllResponseHeaders,
         v2->m_pXMLHttp,
         &bstrHeaders);
  if ( v5 >= 0 )
  {
    if ( bstrHeaders && *bstrHeaders )
    {
      v7 = SysStringLen(bstrHeaders);
      v8 = (wchar_t *)CoTaskMemAlloc(2 * v7 + 2);
      v4 = v8;
      if ( v8 )
      {
        v5 = StringCchCopyW(v8, v7 + 1, bstrHeaders);
        if ( v5 >= 0 )
        {
          *ppwszHeaders = v4;
          v4 = 0;
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
    else
    {
      v5 = -2147024894;
    }
  }
CleanUp_371:
  CoTaskMemFree(v4);
  SysFreeString(bstrHeaders);
  if ( (byte_101857A0[16 * (v5 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v5 >> 31) + 2) << 9) | 1, 0x98u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x10103dab  mov     edi, edi
0x10103dad  push    ebp
0x10103dae  mov     ebp, esp
0x10103db0  push    this
0x10103db1  push    this
0x10103db2  push    ebx
0x10103db3  mov     eax, this
0x10103db5  mov     ebx, ppwszHeaders
0x10103db7  push    esi
0x10103db8  xor     this, this
0x10103dba  mov     [ebp+var_8], eax
0x10103dbd  push    edi
0x10103dbe  mov     edi, this
0x10103dc0  mov     [ebp+bstrHeaders], this
0x10103dc3  test    byte_101857A0, 2; __annotation("TMF:",
0x10103dca  jz      short loc_10103DE7
0x10103dcc  push    ebx; _a2
0x10103dcd  push    eax; _a1
0x10103dce  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10103dd3  mov     ppwszHeaders, 97h; id
0x10103dd8  mov     this, 401h; LevelKeyword
0x10103ddd  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x10103de2  mov     eax, [ebp+var_8]
0x10103de5  xor     this, this
0x10103de7  test    ebx, ebx
0x10103de9  jnz     short loc_10103DF5
0x10103deb  mov     esi, 80004003h
0x10103df0  jmp     CleanUp_371
0x10103df5  mov     [ebx], this
0x10103df7  cmp     [eax+1Ch], this
0x10103dfa  jz      short loc_10103E13
0x10103dfc  mov     esi, [eax+1Ch]
0x10103dff  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10103e05  cmp     esi, eax
0x10103e07  jz      short loc_10103E10
0x10103e09  mov     esi, 8001010Eh
0x10103e0e  jmp     short CleanUp_371
0x10103e10  mov     eax, [ebp+var_8]
0x10103e13  mov     this, [eax+18h]
0x10103e16  mov     eax, [this]
0x10103e18  mov     esi, [eax+28h]
0x10103e1b  lea     eax, [ebp+bstrHeaders]
0x10103e1e  push    eax
0x10103e1f  push    this
0x10103e20  mov     this, esi; this
0x10103e22  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10103e28  call    esi
0x10103e2a  mov     esi, eax
0x10103e2c  test    esi, esi
0x10103e2e  js      short CleanUp_371
0x10103e30  mov     eax, [ebp+bstrHeaders]
0x10103e33  test    eax, eax
0x10103e35  jz      short loc_10103E7B
0x10103e37  xor     this, this
0x10103e39  cmp     [eax], cx
0x10103e3c  jz      short loc_10103E7B
0x10103e3e  push    eax; pbstr
0x10103e3f  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x10103e45  mov     esi, eax
0x10103e47  lea     eax, ds:2[esi*2]
0x10103e4e  push    eax; cb
0x10103e4f  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10103e55  mov     edi, eax
0x10103e57  test    edi, edi
0x10103e59  jnz     short loc_10103E62
0x10103e5b  mov     esi, 8007000Eh
0x10103e60  jmp     short CleanUp_371
0x10103e62  push    [ebp+bstrHeaders]; pszSrc
0x10103e65  lea     ppwszHeaders, [esi+1]; cchDest
0x10103e68  mov     this, edi; pszDest
0x10103e6a  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x10103e6f  mov     esi, eax
0x10103e71  test    esi, esi
0x10103e73  js      short CleanUp_371
0x10103e75  mov     [ebx], edi
0x10103e77  xor     edi, edi
0x10103e79  jmp     short CleanUp_371
0x10103e7b  mov     esi, 80070002h
0x10103e80  push    edi; pv
0x10103e81  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10103e87  push    [ebp+bstrHeaders]; bstrString
0x10103e8a  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10103e90  mov     this, esi; __annotation("TMF:",
0x10103e92  sar     this, 1Fh
0x10103e95  mov     eax, this
0x10103e97  shl     eax, 4
0x10103e9a  test    byte_101857A0[eax], 2
0x10103ea1  jz      short loc_10103EBC
0x10103ea3  add     this, 2
0x10103ea6  mov     ppwszHeaders, 98h; id
0x10103eab  push    esi; _a1
0x10103eac  shl     this, 9
0x10103eaf  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10103eb4  or      this, 1; LevelKeyword
0x10103eb7  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10103ebc  pop     edi
0x10103ebd  mov     eax, esi
0x10103ebf  pop     esi
0x10103ec0  pop     ebx
0x10103ec1  leave
0x10103ec2  retn
```
