# CIMTileConfiguration::CreateConfiguration(ushort const *,ushort const *)

- ea: `0x18036a270`
- end: `0x18036a4d0`
- name: `?CreateConfiguration@CIMTileConfiguration@@UEAAJPEBG0@Z`
- size: `608`
- prototype: `__int64 __fastcall(CIMTileConfiguration *__hidden this, OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18007bf04`
- `0x1800805d4`
- `0x18008f218`
- `0x18036a270`
- `0x18036af30`
- `0x18047e940`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18036a2a3`
- `KERNEL32!CreateDirectoryW` at `0x18036a2a3`
- `KERNEL32!GetLastError` at `0x18036a2b3`
- `KERNEL32!GetLastError` at `0x18036a2c3`
- `KERNEL32!GetLastError` at `0x18036a2d3`
- `KERNEL32!GetLastError` at `0x18036a2b3`
- `KERNEL32!GetLastError` at `0x18036a2c3`
- `KERNEL32!GetLastError` at `0x18036a2d3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a28e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a3bd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a420`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a480`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a28e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a3bd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a420`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18036a480`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a372`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a38a`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a3ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a44d`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a372`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a38a`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a3ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18036a44d`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a3a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a40c`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a46c`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a4ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a3a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a40c`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a46c`
- `OLEAUT32!__imp_SysFreeString` at `0x18036a4ae`

## string_xrefs

- `0x18036a2fe`: `<?xml version="1.0" encoding="utf-8"?><browserconfig><msapplication></msapplication></browserconfig>`
- `0x18036a356`: `config/site`

## pseudocode

```c
__int64 __fastcall CIMTileConfiguration::CreateConfiguration(
        CIMTileConfiguration *this,
        OLECHAR *psz,
        const unsigned __int16 *a3)
{
  signed int LastError; // edi
  unsigned __int16 *v7; // rbx
  OLECHAR *v8; // rbx
  const unsigned __int16 *v9; // r9
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rbx
  LPCWSTR pszPath; // [rsp+58h] [rbp+20h] BYREF

  if ( PathFileExistsW(psz)
    || CreateDirectoryW(psz, 0)
    || ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0x80070000)
      : (LastError = GetLastError()),
        LastError >= 0) )
  {
    LastError = CXMLDOMNode::CreateFromString(
                  (struct IUnknown **)this + 16,
                  (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><browserconfig><msapplication></msapplication></browserconfig>",
                  &CLSID_DOMDocument);
    ATL::CComBSTR::operator=((char *)this + 16, a3);
    if ( LastError >= 0 )
    {
      if ( ATL::CComBSTR::Length((CIMTileConfiguration *)((char *)this + 16)) )
      {
        if ( !ATL::CComBSTR::Length((CIMTileConfiguration *)((char *)this + 96)) )
          ATL::CComBSTR::operator=((char *)this + 96, psz);
        LastError = CIMTileConfiguration::SetConfigValue(
                      this,
                      L"config/site",
                      L"src",
                      *((const unsigned __int16 **)this + 2));
        if ( LastError >= 0 )
        {
          pszPath = SysAllocString(psz);
          v7 = SysAllocString(L"\\squaretile.png");
          ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&pszPath, v7);
          SysFreeString(v7);
          v8 = (OLECHAR *)pszPath;
          if ( PathFileExistsW(pszPath) )
          {
            v9 = L"\\squaretile.png";
          }
          else
          {
            ATL::CComBSTR::operator=(&pszPath, psz);
            v10 = SysAllocString(L"\\hires.png");
            ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&pszPath, v10);
            SysFreeString(v10);
            v8 = (OLECHAR *)pszPath;
            if ( PathFileExistsW(pszPath) )
            {
              v9 = L"\\hires.png";
            }
            else
            {
              ATL::CComBSTR::operator=(&pszPath, psz);
              v11 = SysAllocString(L"\\lowres.png");
              ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&pszPath, v11);
              SysFreeString(v11);
              v8 = (OLECHAR *)pszPath;
              if ( !PathFileExistsW(pszPath) )
              {
LABEL_19:
                SysFreeString(v8);
                return (unsigned int)LastError;
              }
              v9 = L"\\lowres.png";
            }
          }
          LastError = CIMTileConfiguration::SetConfigValue(this, L"tile/selection", 0, v9);
          goto LABEL_19;
        }
      }
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18036a270  mov     [rsp+arg_0], rbx
0x18036a275  mov     [rsp+arg_8], rbp
0x18036a27a  push    rsi
0x18036a27b  push    rdi
0x18036a27c  push    r14
0x18036a27e  sub     rsp, 20h
0x18036a282  mov     rsi, rcx
0x18036a285  mov     r14, r8
0x18036a288  mov     rcx, rdx; pszPath
0x18036a28b  mov     rbp, rdx
0x18036a28e  call    cs:__imp_PathFileExistsW
0x18036a295  nop     dword ptr [rax+rax+00h]
0x18036a29a  test    eax, eax
0x18036a29c  jnz     short loc_18036A2F0
0x18036a29e  xor     edx, edx; lpSecurityAttributes
0x18036a2a0  mov     rcx, rbp; lpPathName
0x18036a2a3  call    cs:__imp_CreateDirectoryW
0x18036a2aa  nop     dword ptr [rax+rax+00h]
0x18036a2af  test    eax, eax
0x18036a2b1  jnz     short loc_18036A2F0
0x18036a2b3  call    cs:__imp_GetLastError
0x18036a2ba  nop     dword ptr [rax+rax+00h]
0x18036a2bf  test    eax, eax
0x18036a2c1  jg      short loc_18036A2D3
0x18036a2c3  call    cs:__imp_GetLastError
0x18036a2ca  nop     dword ptr [rax+rax+00h]
0x18036a2cf  mov     edi, eax
0x18036a2d1  jmp     short loc_18036A2E8
0x18036a2d3  call    cs:__imp_GetLastError
0x18036a2da  nop     dword ptr [rax+rax+00h]
0x18036a2df  movzx   edi, ax
0x18036a2e2  or      edi, 80070000h
0x18036a2e8  test    edi, edi
0x18036a2ea  js      loc_18036A4BA
0x18036a2f0  lea     rcx, [rsi+80h]; this
0x18036a2f7  lea     r8, CLSID_DOMDocument; rclsid
0x18036a2fe  lea     rdx, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18036a305  call    ?CreateFromString@CXMLDOMNode@@QEAAJPEBGAEBU_GUID@@@Z; CXMLDOMNode::CreateFromString(ushort const *,_GUID const &)
0x18036a30a  lea     rbx, [rsi+10h]
0x18036a30e  mov     rdx, r14
0x18036a311  mov     rcx, rbx
0x18036a314  mov     edi, eax
0x18036a316  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18036a31b  test    edi, edi
0x18036a31d  js      loc_18036A4BA
0x18036a323  mov     rcx, rbx; this
0x18036a326  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18036a32b  test    eax, eax
0x18036a32d  jz      loc_18036A4BA
0x18036a333  lea     rcx, [rsi+60h]; this
0x18036a337  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18036a33c  test    eax, eax
0x18036a33e  jnz     short loc_18036A34C
0x18036a340  mov     rdx, rbp
0x18036a343  lea     rcx, [rsi+60h]
0x18036a347  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18036a34c  mov     r9, [rbx]; unsigned __int16 *
0x18036a34f  lea     r8, aSrc_3; "src"
0x18036a356  lea     rdx, aConfigSite; "config/site"
0x18036a35d  mov     rcx, rsi; this
0x18036a360  call    ?SetConfigValue@CIMTileConfiguration@@UEAAJPEBG00@Z; CIMTileConfiguration::SetConfigValue(ushort const *,ushort const *,ushort const *)
0x18036a365  mov     edi, eax
0x18036a367  test    eax, eax
0x18036a369  js      loc_18036A4BA
0x18036a36f  mov     rcx, rbp; psz
0x18036a372  call    cs:__imp_SysAllocString
0x18036a379  nop     dword ptr [rax+rax+00h]
0x18036a37e  lea     rcx, aSquaretilePng; "\\squaretile.png"
0x18036a385  mov     [rsp+38h+pszPath], rax
0x18036a38a  call    cs:__imp_SysAllocString
0x18036a391  nop     dword ptr [rax+rax+00h]
0x18036a396  mov     rdx, rax; unsigned __int16 *
0x18036a399  lea     rcx, [rsp+38h+pszPath]; this
0x18036a39e  mov     rbx, rax
0x18036a3a1  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18036a3a6  mov     rcx, rbx; bstrString
0x18036a3a9  call    cs:__imp_SysFreeString
0x18036a3b0  nop     dword ptr [rax+rax+00h]
0x18036a3b5  mov     rbx, [rsp+38h+pszPath]
0x18036a3ba  mov     rcx, rbx; pszPath
0x18036a3bd  call    cs:__imp_PathFileExistsW
0x18036a3c4  nop     dword ptr [rax+rax+00h]
0x18036a3c9  test    eax, eax
0x18036a3cb  jz      short loc_18036A3D9
0x18036a3cd  lea     r9, aSquaretilePng; "\\squaretile.png"
0x18036a3d4  jmp     loc_18036A497
0x18036a3d9  mov     rdx, rbp
0x18036a3dc  lea     rcx, [rsp+38h+pszPath]
0x18036a3e1  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18036a3e6  lea     rcx, aHiresPng; "\\hires.png"
0x18036a3ed  call    cs:__imp_SysAllocString
0x18036a3f4  nop     dword ptr [rax+rax+00h]
0x18036a3f9  mov     rdx, rax; unsigned __int16 *
0x18036a3fc  lea     rcx, [rsp+38h+pszPath]; this
0x18036a401  mov     rbx, rax
0x18036a404  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18036a409  mov     rcx, rbx; bstrString
0x18036a40c  call    cs:__imp_SysFreeString
0x18036a413  nop     dword ptr [rax+rax+00h]
0x18036a418  mov     rbx, [rsp+38h+pszPath]
0x18036a41d  mov     rcx, rbx; pszPath
0x18036a420  call    cs:__imp_PathFileExistsW
0x18036a427  nop     dword ptr [rax+rax+00h]
0x18036a42c  test    eax, eax
0x18036a42e  jz      short loc_18036A439
0x18036a430  lea     r9, aHiresPng; "\\hires.png"
0x18036a437  jmp     short loc_18036A497
0x18036a439  mov     rdx, rbp
0x18036a43c  lea     rcx, [rsp+38h+pszPath]
0x18036a441  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18036a446  lea     rcx, aLowresPng; "\\lowres.png"
0x18036a44d  call    cs:__imp_SysAllocString
0x18036a454  nop     dword ptr [rax+rax+00h]
0x18036a459  mov     rdx, rax; unsigned __int16 *
0x18036a45c  lea     rcx, [rsp+38h+pszPath]; this
0x18036a461  mov     rbx, rax
0x18036a464  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18036a469  mov     rcx, rbx; bstrString
0x18036a46c  call    cs:__imp_SysFreeString
0x18036a473  nop     dword ptr [rax+rax+00h]
0x18036a478  mov     rbx, [rsp+38h+pszPath]
0x18036a47d  mov     rcx, rbx; pszPath
0x18036a480  call    cs:__imp_PathFileExistsW
0x18036a487  nop     dword ptr [rax+rax+00h]
0x18036a48c  test    eax, eax
0x18036a48e  jz      short loc_18036A4AB
0x18036a490  lea     r9, aLowresPng; "\\lowres.png"
0x18036a497  xor     r8d, r8d; unsigned __int16 *
0x18036a49a  lea     rdx, aTileSelection; "tile/selection"
0x18036a4a1  mov     rcx, rsi; this
0x18036a4a4  call    ?SetConfigValue@CIMTileConfiguration@@UEAAJPEBG00@Z; CIMTileConfiguration::SetConfigValue(ushort const *,ushort const *,ushort const *)
0x18036a4a9  mov     edi, eax
0x18036a4ab  mov     rcx, rbx; bstrString
0x18036a4ae  call    cs:__imp_SysFreeString
0x18036a4b5  nop     dword ptr [rax+rax+00h]
0x18036a4ba  mov     rbx, [rsp+38h+arg_0]
0x18036a4bf  mov     eax, edi
0x18036a4c1  mov     rbp, [rsp+38h+arg_8]
0x18036a4c6  add     rsp, 20h
0x18036a4ca  pop     r14
0x18036a4cc  pop     rdi
0x18036a4cd  pop     rsi
0x18036a4ce  retn
```
