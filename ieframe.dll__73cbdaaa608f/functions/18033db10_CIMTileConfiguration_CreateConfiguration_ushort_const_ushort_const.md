# CIMTileConfiguration::CreateConfiguration(ushort const *,ushort const *)

- ea: `0x18033db10`
- end: `0x18033dd1f`
- name: `?CreateConfiguration@CIMTileConfiguration@@UEAAJPEBG0@Z`
- size: `527`
- prototype: `__int64 __fastcall(CIMTileConfiguration *__hidden this, OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800617f8`
- `0x18008934c`
- `0x18033db10`
- `0x18033e710`
- `0x180443c2c`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18033db3d`
- `KERNEL32!CreateDirectoryW` at `0x18033db3d`
- `KERNEL32!GetLastError` at `0x18033db47`
- `KERNEL32!GetLastError` at `0x18033db51`
- `KERNEL32!GetLastError` at `0x18033db5b`
- `KERNEL32!GetLastError` at `0x18033db47`
- `KERNEL32!GetLastError` at `0x18033db51`
- `KERNEL32!GetLastError` at `0x18033db5b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033db2e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033dc3d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033dc8e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033dcdc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033db2e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033dc3d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033dc8e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18033dcdc`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dc04`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dc16`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dc67`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dcb5`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dc04`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dc16`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dc67`
- `OLEAUT32!__imp_SysAllocString` at `0x18033dcb5`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dc2f`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dc80`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dcce`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dd04`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dc2f`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dc80`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dcce`
- `OLEAUT32!__imp_SysFreeString` at `0x18033dd04`
- `OLEAUT32!__imp_SysStringLen` at `0x18033dbb1`
- `OLEAUT32!__imp_SysStringLen` at `0x18033dbc8`
- `OLEAUT32!__imp_SysStringLen` at `0x18033dbb1`
- `OLEAUT32!__imp_SysStringLen` at `0x18033dbc8`

## string_xrefs

- `0x18033db80`: `<?xml version="1.0" encoding="utf-8"?><browserconfig><msapplication></msapplication></browserconfig>`
- `0x18033dbe8`: `config/site`

## pseudocode

```c
__int64 __fastcall CIMTileConfiguration::CreateConfiguration(
        struct IUnknown **this,
        OLECHAR *psz,
        const unsigned __int16 *a3)
{
  signed int LastError; // edi
  const unsigned __int16 **v7; // r14
  OLECHAR *v8; // rcx
  unsigned __int16 *v9; // rbx
  OLECHAR *v10; // rbx
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // rbx
  LPCWSTR pszPath; // [rsp+58h] [rbp+20h] BYREF

  if ( PathFileExistsW(psz)
    || CreateDirectoryW(psz, 0)
    || ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0x80070000)
      : (LastError = GetLastError()),
        LastError >= 0) )
  {
    v7 = (const unsigned __int16 **)(this + 2);
    LastError = CXMLDOMNode::CreateFromString(
                  this + 16,
                  (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><browserconfig><msapplication></msapplication></browserconfig>",
                  &CLSID_DOMDocument);
    ATL::CComBSTR::operator=(this + 2, a3);
    if ( LastError >= 0 && *v7 && SysStringLen((BSTR)*v7) )
    {
      v8 = (OLECHAR *)this[12];
      if ( !v8 || !SysStringLen(v8) )
        ATL::CComBSTR::operator=(this + 12, psz);
      LastError = CIMTileConfiguration::SetConfigValue((CIMTileConfiguration *)this, L"config/site", L"src", *v7);
      if ( LastError >= 0 )
      {
        pszPath = SysAllocString(psz);
        v9 = SysAllocString(L"\\squaretile.png");
        ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&pszPath, v9);
        SysFreeString(v9);
        v10 = (OLECHAR *)pszPath;
        if ( PathFileExistsW(pszPath) )
        {
          v11 = L"\\squaretile.png";
        }
        else
        {
          ATL::CComBSTR::operator=(&pszPath, psz);
          v12 = SysAllocString(L"\\hires.png");
          ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&pszPath, v12);
          SysFreeString(v12);
          v10 = (OLECHAR *)pszPath;
          if ( PathFileExistsW(pszPath) )
          {
            v11 = L"\\hires.png";
          }
          else
          {
            ATL::CComBSTR::operator=(&pszPath, psz);
            v13 = SysAllocString(L"\\lowres.png");
            ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&pszPath, v13);
            SysFreeString(v13);
            v10 = (OLECHAR *)pszPath;
            if ( !PathFileExistsW(pszPath) )
            {
LABEL_21:
              SysFreeString(v10);
              return (unsigned int)LastError;
            }
            v11 = L"\\lowres.png";
          }
        }
        LastError = CIMTileConfiguration::SetConfigValue((CIMTileConfiguration *)this, L"tile/selection", 0, v11);
        goto LABEL_21;
      }
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18033db10  mov     [rsp+arg_0], rbx
0x18033db15  mov     [rsp+arg_8], rbp
0x18033db1a  push    rsi
0x18033db1b  push    rdi
0x18033db1c  push    r14
0x18033db1e  sub     rsp, 20h
0x18033db22  mov     rsi, rcx
0x18033db25  mov     rbx, r8
0x18033db28  mov     rcx, rdx; pszPath
0x18033db2b  mov     rbp, rdx
0x18033db2e  call    cs:__imp_PathFileExistsW
0x18033db34  test    eax, eax
0x18033db36  jnz     short loc_18033DB72
0x18033db38  xor     edx, edx; lpSecurityAttributes
0x18033db3a  mov     rcx, rbp; lpPathName
0x18033db3d  call    cs:__imp_CreateDirectoryW
0x18033db43  test    eax, eax
0x18033db45  jnz     short loc_18033DB72
0x18033db47  call    cs:__imp_GetLastError
0x18033db4d  test    eax, eax
0x18033db4f  jg      short loc_18033DB5B
0x18033db51  call    cs:__imp_GetLastError
0x18033db57  mov     edi, eax
0x18033db59  jmp     short loc_18033DB6A
0x18033db5b  call    cs:__imp_GetLastError
0x18033db61  movzx   edi, ax
0x18033db64  or      edi, 80070000h
0x18033db6a  test    edi, edi
0x18033db6c  js      loc_18033DD0A
0x18033db72  lea     rcx, [rsi+80h]; this
0x18033db79  lea     r8, CLSID_DOMDocument; rclsid
0x18033db80  lea     rdx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18033db87  call    ?CreateFromString@CXMLDOMNode@@QEAAJPEBGAEBU_GUID@@@Z; CXMLDOMNode::CreateFromString(ushort const *,_GUID const &)
0x18033db8c  lea     r14, [rsi+10h]
0x18033db90  mov     rdx, rbx
0x18033db93  mov     rcx, r14
0x18033db96  mov     edi, eax
0x18033db98  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18033db9d  test    edi, edi
0x18033db9f  js      loc_18033DD0A
0x18033dba5  mov     rcx, [r14]; pbstr
0x18033dba8  test    rcx, rcx
0x18033dbab  jz      loc_18033DD0A
0x18033dbb1  call    cs:__imp_SysStringLen
0x18033dbb7  test    eax, eax
0x18033dbb9  jz      loc_18033DD0A
0x18033dbbf  mov     rcx, [rsi+60h]; pbstr
0x18033dbc3  test    rcx, rcx
0x18033dbc6  jz      short loc_18033DBD2
0x18033dbc8  call    cs:__imp_SysStringLen
0x18033dbce  test    eax, eax
0x18033dbd0  jnz     short loc_18033DBDE
0x18033dbd2  mov     rdx, rbp
0x18033dbd5  lea     rcx, [rsi+60h]
0x18033dbd9  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18033dbde  mov     r9, [r14]; unsigned __int16 *
0x18033dbe1  lea     r8, aSrc_2; "src"
0x18033dbe8  lea     rdx, aConfigSite; "config/site"
0x18033dbef  mov     rcx, rsi; this
0x18033dbf2  call    ?SetConfigValue@CIMTileConfiguration@@UEAAJPEBG00@Z; CIMTileConfiguration::SetConfigValue(ushort const *,ushort const *,ushort const *)
0x18033dbf7  mov     edi, eax
0x18033dbf9  test    eax, eax
0x18033dbfb  js      loc_18033DD0A
0x18033dc01  mov     rcx, rbp; psz
0x18033dc04  call    cs:__imp_SysAllocString
0x18033dc0a  lea     rcx, aSquaretilePng; "\\squaretile.png"
0x18033dc11  mov     [rsp+38h+pszPath], rax
0x18033dc16  call    cs:__imp_SysAllocString
0x18033dc1c  mov     rdx, rax; unsigned __int16 *
0x18033dc1f  lea     rcx, [rsp+38h+pszPath]; this
0x18033dc24  mov     rbx, rax
0x18033dc27  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18033dc2c  mov     rcx, rbx; bstrString
0x18033dc2f  call    cs:__imp_SysFreeString
0x18033dc35  mov     rbx, [rsp+38h+pszPath]
0x18033dc3a  mov     rcx, rbx; pszPath
0x18033dc3d  call    cs:__imp_PathFileExistsW
0x18033dc43  test    eax, eax
0x18033dc45  jz      short loc_18033DC53
0x18033dc47  lea     r9, aSquaretilePng; "\\squaretile.png"
0x18033dc4e  jmp     loc_18033DCED
0x18033dc53  mov     rdx, rbp
0x18033dc56  lea     rcx, [rsp+38h+pszPath]
0x18033dc5b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18033dc60  lea     rcx, aHiresPng; "\\hires.png"
0x18033dc67  call    cs:__imp_SysAllocString
0x18033dc6d  mov     rdx, rax; unsigned __int16 *
0x18033dc70  lea     rcx, [rsp+38h+pszPath]; this
0x18033dc75  mov     rbx, rax
0x18033dc78  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18033dc7d  mov     rcx, rbx; bstrString
0x18033dc80  call    cs:__imp_SysFreeString
0x18033dc86  mov     rbx, [rsp+38h+pszPath]
0x18033dc8b  mov     rcx, rbx; pszPath
0x18033dc8e  call    cs:__imp_PathFileExistsW
0x18033dc94  test    eax, eax
0x18033dc96  jz      short loc_18033DCA1
0x18033dc98  lea     r9, aHiresPng; "\\hires.png"
0x18033dc9f  jmp     short loc_18033DCED
0x18033dca1  mov     rdx, rbp
0x18033dca4  lea     rcx, [rsp+38h+pszPath]
0x18033dca9  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18033dcae  lea     rcx, aLowresPng; "\\lowres.png"
0x18033dcb5  call    cs:__imp_SysAllocString
0x18033dcbb  mov     rdx, rax; unsigned __int16 *
0x18033dcbe  lea     rcx, [rsp+38h+pszPath]; this
0x18033dcc3  mov     rbx, rax
0x18033dcc6  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18033dccb  mov     rcx, rbx; bstrString
0x18033dcce  call    cs:__imp_SysFreeString
0x18033dcd4  mov     rbx, [rsp+38h+pszPath]
0x18033dcd9  mov     rcx, rbx; pszPath
0x18033dcdc  call    cs:__imp_PathFileExistsW
0x18033dce2  test    eax, eax
0x18033dce4  jz      short loc_18033DD01
0x18033dce6  lea     r9, aLowresPng; "\\lowres.png"
0x18033dced  xor     r8d, r8d; unsigned __int16 *
0x18033dcf0  lea     rdx, aTileSelection; "tile/selection"
0x18033dcf7  mov     rcx, rsi; this
0x18033dcfa  call    ?SetConfigValue@CIMTileConfiguration@@UEAAJPEBG00@Z; CIMTileConfiguration::SetConfigValue(ushort const *,ushort const *,ushort const *)
0x18033dcff  mov     edi, eax
0x18033dd01  mov     rcx, rbx; bstrString
0x18033dd04  call    cs:__imp_SysFreeString
0x18033dd0a  mov     rbx, [rsp+38h+arg_0]
0x18033dd0f  mov     eax, edi
0x18033dd11  mov     rbp, [rsp+38h+arg_8]
0x18033dd16  add     rsp, 20h
0x18033dd1a  pop     r14
0x18033dd1c  pop     rdi
0x18033dd1d  pop     rsi
0x18033dd1e  retn
```
