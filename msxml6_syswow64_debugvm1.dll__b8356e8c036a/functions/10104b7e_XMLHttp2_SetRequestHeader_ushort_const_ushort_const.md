# XMLHttp2::_SetRequestHeader(ushort const *,ushort const *)

- ea: `0x10104b7e`
- end: `0x10104c6f`
- name: `?_SetRequestHeader@XMLHttp2@@AAGJPBG0@Z`
- size: `241`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, const wchar_t *pwszHeader@<edx>, const wchar_t *pwszValue)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x10103980`

## callees

- `0x10067bc0`
- `0x10104b7e`
- `0x10180006`
- `0x10180125`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104bd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104bd0`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104be5`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104c03`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104be5`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104c03`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104c2d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104c34`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104c2d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104c34`

## pseudocode

```c
HRESULT __fastcall XMLHttp2::_SetRequestHeader(XMLHttp2 *this, const wchar_t *pwszHeader, const wchar_t *pwszValue)
{
  const OLECHAR *v3; // esi
  XMLHttp2 *v4; // eax
  wchar_t *v5; // edi
  int v6; // esi
  wchar_t *v7; // ebx
  unsigned int m_dwStaThreadId; // esi
  BSTR v12; // [esp+14h] [ebp-4h]

  v3 = pwszHeader;
  v4 = this;
  v5 = 0;
  if ( (byte_101857A0[0] & 2) != 0 )
  {
    WPP_SF_qSS(0x401u, 0x95u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, this, pwszHeader, pwszValue);
    v4 = this;
  }
  if ( v3 )
  {
    if ( v4->m_dwStaThreadId )
    {
      m_dwStaThreadId = v4->m_dwStaThreadId;
      if ( m_dwStaThreadId != GetCurrentThreadId() )
      {
        v6 = -2147417842;
        goto LABEL_5;
      }
      v3 = pwszHeader;
    }
    v12 = SysAllocString(v3);
    if ( v12 && (!pwszValue || (v5 = SysAllocString(pwszValue)) != 0) )
    {
      v7 = v12;
      v6 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLHTTPRequest *, wchar_t *, wchar_t *), XMLHttp *, BSTR, wchar_t *))this->m_pXMLHttp->setRequestHeader)(
             this->m_pXMLHttp->setRequestHeader,
             this->m_pXMLHttp,
             v12,
             v5);
    }
    else
    {
      v7 = v12;
      v6 = -2147024882;
    }
    goto CleanUp_385;
  }
  v6 = -2147024809;
LABEL_5:
  v7 = 0;
CleanUp_385:
  SysFreeString(v7);
  SysFreeString(v5);
  if ( (byte_101857A0[16 * (v6 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 1, 0x96u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10104b7e  mov     edi, edi
0x10104b80  push    ebp
0x10104b81  mov     ebp, esp
0x10104b83  sub     esp, 0Ch
0x10104b86  push    ebx
0x10104b87  push    esi
0x10104b88  mov     esi, pwszHeader
0x10104b8a  mov     eax, this
0x10104b8c  push    edi
0x10104b8d  mov     [ebp+var_C], esi
0x10104b90  xor     edi, edi
0x10104b92  mov     [ebp+var_8], eax
0x10104b95  test    byte_101857A0, 2; __annotation("TMF:",
0x10104b9c  mov     ebx, [ebp+pwszValue]
0x10104b9f  jz      short loc_10104BBB
0x10104ba1  push    ebx; _a3
0x10104ba2  push    esi; _a2
0x10104ba3  push    eax; _a1
0x10104ba4  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10104ba9  mov     pwszHeader, 95h; id
0x10104bae  mov     this, 401h; LevelKeyword
0x10104bb3  call    _WPP_SF_qSS@24; WPP_SF_qSS(x,x,x,x,x,x)
0x10104bb8  mov     eax, [ebp+var_8]
0x10104bbb  test    esi, esi
0x10104bbd  jnz     short loc_10104BC8
0x10104bbf  mov     esi, 80070057h
0x10104bc4  mov     ebx, edi
0x10104bc6  jmp     short CleanUp_385
0x10104bc8  cmp     [eax+1Ch], edi
0x10104bcb  jz      short loc_10104BE4
0x10104bcd  mov     esi, [eax+1Ch]
0x10104bd0  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10104bd6  cmp     esi, eax
0x10104bd8  jz      short loc_10104BE1
0x10104bda  mov     esi, 8001010Eh
0x10104bdf  jmp     short loc_10104BC4
0x10104be1  mov     esi, [ebp+var_C]
0x10104be4  push    esi; psz
0x10104be5  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104beb  mov     esi, eax
0x10104bed  mov     [ebp+var_4], esi
0x10104bf0  test    esi, esi
0x10104bf2  jnz     short loc_10104BFE
0x10104bf4  mov     ebx, [ebp+var_4]
0x10104bf7  mov     esi, 8007000Eh
0x10104bfc  jmp     short CleanUp_385
0x10104bfe  test    ebx, ebx
0x10104c00  jz      short loc_10104C0F
0x10104c02  push    ebx; psz
0x10104c03  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104c09  mov     edi, eax
0x10104c0b  test    edi, edi
0x10104c0d  jz      short loc_10104BF4
0x10104c0f  mov     this, [ebp+var_8]
0x10104c12  mov     ebx, [ebp+var_4]
0x10104c15  push    edi
0x10104c16  push    ebx
0x10104c17  mov     this, [this+18h]
0x10104c1a  push    this
0x10104c1b  mov     eax, [this]
0x10104c1d  mov     esi, [eax+20h]
0x10104c20  mov     this, esi; this
0x10104c22  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10104c28  call    esi
0x10104c2a  mov     esi, eax
0x10104c2c  push    ebx; bstrString
0x10104c2d  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104c33  push    edi; bstrString
0x10104c34  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104c3a  mov     this, esi; __annotation("TMF:",
0x10104c3c  sar     this, 1Fh
0x10104c3f  mov     eax, this
0x10104c41  shl     eax, 4
0x10104c44  test    byte_101857A0[eax], 2
0x10104c4b  jz      short loc_10104C66
0x10104c4d  add     this, 2
0x10104c50  mov     pwszHeader, 96h; id
0x10104c55  push    esi; _a1
0x10104c56  shl     this, 9
0x10104c59  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10104c5e  or      this, 1; LevelKeyword
0x10104c61  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104c66  pop     edi
0x10104c67  mov     eax, esi
0x10104c69  pop     esi
0x10104c6a  pop     ebx
0x10104c6b  leave
0x10104c6c  retn    4
```
