# XMLHttp2::_SetRequestHeader(ushort const *,ushort const *)

- ea: `0x10104c9e`
- end: `0x10104d8f`
- name: `?_SetRequestHeader@XMLHttp2@@AAGJPBG0@Z`
- size: `241`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, const wchar_t *pwszHeader@<edx>, const wchar_t *pwszValue)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x10103aa0`

## callees

- `0x10067b20`
- `0x10104c9e`
- `0x10180006`
- `0x10180125`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104cf0`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104d05`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104d23`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104d05`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10104d23`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104d4d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104d54`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104d4d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x10104d54`

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
  if ( (byte_10185760[0] & 2) != 0 )
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
  if ( (byte_10185760[16 * (v6 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 1, 0x96u, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x10104c9e  mov     edi, edi
0x10104ca0  push    ebp
0x10104ca1  mov     ebp, esp
0x10104ca3  sub     esp, 0Ch
0x10104ca6  push    ebx
0x10104ca7  push    esi
0x10104ca8  mov     esi, pwszHeader
0x10104caa  mov     eax, this
0x10104cac  push    edi
0x10104cad  mov     [ebp+var_C], esi
0x10104cb0  xor     edi, edi
0x10104cb2  mov     [ebp+var_8], eax
0x10104cb5  test    byte_10185760, 2; __annotation("TMF:",
0x10104cbc  mov     ebx, [ebp+pwszValue]
0x10104cbf  jz      short loc_10104CDB
0x10104cc1  push    ebx; _a3
0x10104cc2  push    esi; _a2
0x10104cc3  push    eax; _a1
0x10104cc4  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10104cc9  mov     pwszHeader, 95h; id
0x10104cce  mov     this, 401h; LevelKeyword
0x10104cd3  call    _WPP_SF_qSS@24; WPP_SF_qSS(x,x,x,x,x,x)
0x10104cd8  mov     eax, [ebp+var_8]
0x10104cdb  test    esi, esi
0x10104cdd  jnz     short loc_10104CE8
0x10104cdf  mov     esi, 80070057h
0x10104ce4  mov     ebx, edi
0x10104ce6  jmp     short CleanUp_385
0x10104ce8  cmp     [eax+1Ch], edi
0x10104ceb  jz      short loc_10104D04
0x10104ced  mov     esi, [eax+1Ch]
0x10104cf0  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10104cf6  cmp     esi, eax
0x10104cf8  jz      short loc_10104D01
0x10104cfa  mov     esi, 8001010Eh
0x10104cff  jmp     short loc_10104CE4
0x10104d01  mov     esi, [ebp+var_C]
0x10104d04  push    esi; psz
0x10104d05  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104d0b  mov     esi, eax
0x10104d0d  mov     [ebp+var_4], esi
0x10104d10  test    esi, esi
0x10104d12  jnz     short loc_10104D1E
0x10104d14  mov     ebx, [ebp+var_4]
0x10104d17  mov     esi, 8007000Eh
0x10104d1c  jmp     short CleanUp_385
0x10104d1e  test    ebx, ebx
0x10104d20  jz      short loc_10104D2F
0x10104d22  push    ebx; psz
0x10104d23  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x10104d29  mov     edi, eax
0x10104d2b  test    edi, edi
0x10104d2d  jz      short loc_10104D14
0x10104d2f  mov     this, [ebp+var_8]
0x10104d32  mov     ebx, [ebp+var_4]
0x10104d35  push    edi
0x10104d36  push    ebx
0x10104d37  mov     this, [this+18h]
0x10104d3a  push    this
0x10104d3b  mov     eax, [this]
0x10104d3d  mov     esi, [eax+20h]
0x10104d40  mov     this, esi; this
0x10104d42  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10104d48  call    esi
0x10104d4a  mov     esi, eax
0x10104d4c  push    ebx; bstrString
0x10104d4d  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104d53  push    edi; bstrString
0x10104d54  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10104d5a  mov     this, esi; __annotation("TMF:",
0x10104d5c  sar     this, 1Fh
0x10104d5f  mov     eax, this
0x10104d61  shl     eax, 4
0x10104d64  test    byte_10185760[eax], 2
0x10104d6b  jz      short loc_10104D86
0x10104d6d  add     this, 2
0x10104d70  mov     pwszHeader, 96h; id
0x10104d75  push    esi; _a1
0x10104d76  shl     this, 9
0x10104d79  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10104d7e  or      this, 1; LevelKeyword
0x10104d81  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104d86  pop     edi
0x10104d87  mov     eax, esi
0x10104d89  pop     esi
0x10104d8a  pop     ebx
0x10104d8b  leave
0x10104d8c  retn    4
```
