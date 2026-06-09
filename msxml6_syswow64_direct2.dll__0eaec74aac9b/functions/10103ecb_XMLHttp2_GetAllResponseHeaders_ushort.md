# XMLHttp2::_GetAllResponseHeaders(ushort * *)

- ea: `0x10103ecb`
- end: `0x10103fe3`
- name: `?_GetAllResponseHeaders@XMLHttp2@@AAGJPAPAG@Z`
- size: `280`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, wchar_t **ppwszHeaders@<edx>)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10102660`

## callees

- `0x100552db`
- `0x10067b20`
- `0x10103ecb`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10103f1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10103f1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10103fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10103fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10103f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x10103f6f`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10103faa`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10103faa`
- `OLEAUT32!__imp__SysStringLen@4` at `0x10103f5f`
- `OLEAUT32!__imp__SysStringLen@4` at `0x10103f5f`

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
  if ( (byte_10185760[0] & 2) != 0 )
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
  if ( (byte_10185760[16 * (v5 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v5 >> 31) + 2) << 9) | 1, 0x98u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x10103ecb  mov     edi, edi
0x10103ecd  push    ebp
0x10103ece  mov     ebp, esp
0x10103ed0  push    this
0x10103ed1  push    this
0x10103ed2  push    ebx
0x10103ed3  mov     eax, this
0x10103ed5  mov     ebx, ppwszHeaders
0x10103ed7  push    esi
0x10103ed8  xor     this, this
0x10103eda  mov     [ebp+var_8], eax
0x10103edd  push    edi
0x10103ede  mov     edi, this
0x10103ee0  mov     [ebp+bstrHeaders], this
0x10103ee3  test    byte_10185760, 2; __annotation("TMF:",
0x10103eea  jz      short loc_10103F07
0x10103eec  push    ebx; _a2
0x10103eed  push    eax; _a1
0x10103eee  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10103ef3  mov     ppwszHeaders, 97h; id
0x10103ef8  mov     this, 401h; LevelKeyword
0x10103efd  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x10103f02  mov     eax, [ebp+var_8]
0x10103f05  xor     this, this
0x10103f07  test    ebx, ebx
0x10103f09  jnz     short loc_10103F15
0x10103f0b  mov     esi, 80004003h
0x10103f10  jmp     CleanUp_371
0x10103f15  mov     [ebx], this
0x10103f17  cmp     [eax+1Ch], this
0x10103f1a  jz      short loc_10103F33
0x10103f1c  mov     esi, [eax+1Ch]
0x10103f1f  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10103f25  cmp     esi, eax
0x10103f27  jz      short loc_10103F30
0x10103f29  mov     esi, 8001010Eh
0x10103f2e  jmp     short CleanUp_371
0x10103f30  mov     eax, [ebp+var_8]
0x10103f33  mov     this, [eax+18h]
0x10103f36  mov     eax, [this]
0x10103f38  mov     esi, [eax+28h]
0x10103f3b  lea     eax, [ebp+bstrHeaders]
0x10103f3e  push    eax
0x10103f3f  push    this
0x10103f40  mov     this, esi; this
0x10103f42  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10103f48  call    esi
0x10103f4a  mov     esi, eax
0x10103f4c  test    esi, esi
0x10103f4e  js      short CleanUp_371
0x10103f50  mov     eax, [ebp+bstrHeaders]
0x10103f53  test    eax, eax
0x10103f55  jz      short loc_10103F9B
0x10103f57  xor     this, this
0x10103f59  cmp     [eax], cx
0x10103f5c  jz      short loc_10103F9B
0x10103f5e  push    eax; pbstr
0x10103f5f  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x10103f65  mov     esi, eax
0x10103f67  lea     eax, ds:2[esi*2]
0x10103f6e  push    eax; cb
0x10103f6f  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10103f75  mov     edi, eax
0x10103f77  test    edi, edi
0x10103f79  jnz     short loc_10103F82
0x10103f7b  mov     esi, 8007000Eh
0x10103f80  jmp     short CleanUp_371
0x10103f82  push    [ebp+bstrHeaders]; pszSrc
0x10103f85  lea     ppwszHeaders, [esi+1]; cchDest
0x10103f88  mov     this, edi; pszDest
0x10103f8a  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x10103f8f  mov     esi, eax
0x10103f91  test    esi, esi
0x10103f93  js      short CleanUp_371
0x10103f95  mov     [ebx], edi
0x10103f97  xor     edi, edi
0x10103f99  jmp     short CleanUp_371
0x10103f9b  mov     esi, 80070002h
0x10103fa0  push    edi; pv
0x10103fa1  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10103fa7  push    [ebp+bstrHeaders]; bstrString
0x10103faa  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10103fb0  mov     this, esi; __annotation("TMF:",
0x10103fb2  sar     this, 1Fh
0x10103fb5  mov     eax, this
0x10103fb7  shl     eax, 4
0x10103fba  test    byte_10185760[eax], 2
0x10103fc1  jz      short loc_10103FDC
0x10103fc3  add     this, 2
0x10103fc6  mov     ppwszHeaders, 98h; id
0x10103fcb  push    esi; _a1
0x10103fcc  shl     this, 9
0x10103fcf  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10103fd4  or      this, 1; LevelKeyword
0x10103fd7  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10103fdc  pop     edi
0x10103fdd  mov     eax, esi
0x10103fdf  pop     esi
0x10103fe0  pop     ebx
0x10103fe1  leave
0x10103fe2  retn
```
