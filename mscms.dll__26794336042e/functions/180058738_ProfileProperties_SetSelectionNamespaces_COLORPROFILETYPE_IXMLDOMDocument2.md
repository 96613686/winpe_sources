# ProfileProperties::SetSelectionNamespaces(COLORPROFILETYPE,IXMLDOMDocument2 *)

- ea: `0x180058738`
- end: `0x1800588fb`
- name: `?SetSelectionNamespaces@ProfileProperties@@YAJW4COLORPROFILETYPE@@PEAUIXMLDOMDocument2@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(ProfileProperties *__hidden this, enum COLORPROFILETYPE, struct IXMLDOMDocument2 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057204`
- `0x1800576a8`
- `0x1800577f0`

## callees

- `0x18000fe54`
- `0x18001c800`
- `0x18004bed8`
- `0x180057100`
- `0x180058738`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005881c`
- `OLEAUT32!__imp_SysAllocString` at `0x18005881c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005877b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005878a`
- `OLEAUT32!__imp_SysFreeString` at `0x180058868`
- `OLEAUT32!__imp_SysFreeString` at `0x180058877`
- `OLEAUT32!__imp_SysFreeString` at `0x1800588ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800588d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005877b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005878a`
- `OLEAUT32!__imp_SysFreeString` at `0x180058868`
- `OLEAUT32!__imp_SysFreeString` at `0x180058877`
- `OLEAUT32!__imp_SysFreeString` at `0x1800588ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800588d9`
- `OLEAUT32!__imp_VariantClear` at `0x180058809`
- `OLEAUT32!__imp_VariantClear` at `0x18005885e`
- `OLEAUT32!__imp_VariantClear` at `0x1800588c0`
- `OLEAUT32!__imp_VariantClear` at `0x180058809`
- `OLEAUT32!__imp_VariantClear` at `0x18005885e`
- `OLEAUT32!__imp_VariantClear` at `0x1800588c0`

## string_xrefs

- `0x1800587e1`: `xmlns:wcs='http://schemas.microsoft.com/windows/2005/02/color/WcsCommonProfileTypes'`
- `0x1800587b9`: `xmlns:cdm='http://schemas.microsoft.com/windows/2005/02/color/ColorDeviceModel' xmlns:cal='http://schemas.microsoft.com/windows/2007/11/color/Calibration'`
- `0x1800587a3`: `xmlns:cam='http://schemas.microsoft.com/windows/2005/02/color/ColorAppearanceModel'`
- `0x18005879a`: `xmlns:gmm='http://schemas.microsoft.com/windows/2005/02/color/GamutMapModel'`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProfileProperties::SetSelectionNamespaces(
        ProfileProperties *this,
        __int64 a2,
        struct IXMLDOMDocument2 *a3)
{
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  __int64 result; // rax
  const OLECHAR *v8; // rdx
  OLECHAR *v9; // rbx
  unsigned int v10; // edi
  const ATL::CAtlException *v11; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-40h] BYREF
  VARIANTARG v13; // [rsp+40h] [rbp-28h] BYREF
  OLECHAR *psz; // [rsp+80h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  v4 = (int)this;
  try
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
    psz = 0;
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
        {
          SysFreeString(0);
          SysFreeString(bstrString);
          return 2147942487LL;
        }
        v8 = L"xmlns:gmm='http://schemas.microsoft.com/windows/2005/02/color/GamutMapModel'";
      }
      else
      {
        v8 = L"xmlns:cam='http://schemas.microsoft.com/windows/2005/02/color/ColorAppearanceModel'";
      }
      ATL::CComBSTR::operator=(&psz, v8);
    }
    else
    {
      ATL::CComBSTR::operator=(
        &psz,
        L"xmlns:cdm='http://schemas.microsoft.com/windows/2005/02/color/ColorDeviceModel' xmlns:cal='http://schemas.micros"
         "oft.com/windows/2007/11/color/Calibration'");
    }
    ATL::CComBSTR::operator+=((ATL::CComBSTR *)&psz, L" ");
    ATL::CComBSTR::operator+=(
      (ATL::CComBSTR *)&psz,
      L"xmlns:wcs='http://schemas.microsoft.com/windows/2005/02/color/WcsCommonProfileTypes'");
    v9 = psz;
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(v9);
    if ( !pvarg.llVal && v9 )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    if ( pvarg.vt == 8 )
    {
      v13 = pvarg;
      v10 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)a2 + 640LL))(a2, bstrString, &v13);
      VariantClear(&pvarg);
      SysFreeString(v9);
      SysFreeString(bstrString);
      result = v10;
    }
    else
    {
      VariantClear(&pvarg);
      SysFreeString(v9);
      SysFreeString(bstrString);
      result = 2147500037LL;
    }
  }
  catch ( const ATL::CAtlException *v11 )
  {
    LODWORD(psz) = *(_DWORD *)v11;
    return (unsigned int)psz;
  }
  return result;
}

```

## disassembly

```asm
0x180058738  mov     rax, rsp
0x18005873b  mov     [rax+8], rbx
0x18005873f  mov     [rax+10h], rsi
0x180058743  push    rdi
0x180058744  sub     rsp, 60h
0x180058748  mov     rdi, rdx
0x18005874b  mov     ebx, ecx
0x18005874d  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180058754  lea     rcx, [rax+20h]; this
0x180058758  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005875d  nop
0x18005875e  mov     [rsp+68h+psz], 0
0x18005876a  sub     ebx, 1
0x18005876d  jz      short loc_1800587B9
0x18005876f  sub     ebx, 1
0x180058772  jz      short loc_1800587A3
0x180058774  cmp     ebx, 1
0x180058777  jz      short loc_18005879A
0x180058779  xor     ecx, ecx; bstrString
0x18005877b  call    cs:__imp_SysFreeString
0x180058781  nop
0x180058782  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18005878a  call    cs:__imp_SysFreeString
0x180058790  mov     eax, 80070057h
0x180058795  jmp     loc_1800588EA
0x18005879a  lea     rdx, aXmlnsGmmHttpSc; "xmlns:gmm='http://schemas.microsoft.com"...
0x1800587a1  jmp     short loc_1800587AA
0x1800587a3  lea     rdx, aXmlnsCamHttpSc; "xmlns:cam='http://schemas.microsoft.com"...
0x1800587aa  lea     rcx, [rsp+68h+psz]
0x1800587b2  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800587b7  jmp     short loc_1800587CD
0x1800587b9  lea     rdx, aXmlnsCdmHttpSc; "xmlns:cdm='http://schemas.microsoft.com"...
0x1800587c0  lea     rcx, [rsp+68h+psz]
0x1800587c8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800587cd  lea     rdx, asc_18008D0DC; " "
0x1800587d4  lea     rcx, [rsp+68h+psz]
0x1800587dc  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1800587e1  lea     rdx, aXmlnsWcsHttpSc; "xmlns:wcs='http://schemas.microsoft.com"...
0x1800587e8  lea     rcx, [rsp+68h+psz]
0x1800587f0  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1800587f5  mov     rbx, [rsp+68h+psz]
0x1800587fd  xor     eax, eax
0x1800587ff  mov     word ptr [rsp+68h+pvarg], ax
0x180058804  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180058809  call    cs:__imp_VariantClear
0x18005880f  mov     esi, 8
0x180058814  mov     word ptr [rsp+68h+pvarg], si
0x180058819  mov     rcx, rbx; psz
0x18005881c  call    cs:__imp_SysAllocString
0x180058822  mov     dword ptr [rsp+68h+pvarg+8], eax
0x180058826  mov     rcx, rax
0x180058829  sar     rcx, 20h
0x18005882d  mov     dword ptr [rsp+68h+pvarg+0Ch], ecx
0x180058831  test    rax, rax
0x180058834  jnz     short loc_180058852
0x180058836  test    rbx, rbx
0x180058839  jz      short loc_180058852
0x18005883b  lea     eax, [rsi+2]
0x18005883e  mov     word ptr [rsp+68h+pvarg], ax
0x180058843  mov     ecx, 8007000Eh; int
0x180058848  mov     dword ptr [rsp+68h+pvarg+8], ecx
0x18005884c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180058852  cmp     si, word ptr [rsp+68h+pvarg]
0x180058857  jz      short loc_180058884
0x180058859  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18005885e  call    cs:__imp_VariantClear
0x180058864  nop
0x180058865  mov     rcx, rbx; bstrString
0x180058868  call    cs:__imp_SysFreeString
0x18005886e  nop
0x18005886f  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180058877  call    cs:__imp_SysFreeString
0x18005887d  mov     eax, 80004005h
0x180058882  jmp     short loc_1800588EA
0x180058884  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x180058889  movaps  [rsp+68h+var_28], xmm0
0x18005888e  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x180058894  movsd   [rsp+68h+var_18], xmm1
0x18005889a  mov     rax, [rdi]
0x18005889d  lea     r8, [rsp+68h+var_28]
0x1800588a2  mov     rdx, [rsp+68h+bstrString]
0x1800588aa  mov     rcx, rdi
0x1800588ad  mov     rax, [rax+280h]
0x1800588b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588b9  mov     edi, eax
0x1800588bb  lea     rcx, [rsp+68h+pvarg]; pvarg
0x1800588c0  call    cs:__imp_VariantClear
0x1800588c6  nop
0x1800588c7  mov     rcx, rbx; bstrString
0x1800588ca  call    cs:__imp_SysFreeString
0x1800588d0  nop
0x1800588d1  mov     rcx, [rsp+68h+bstrString]; bstrString
0x1800588d9  call    cs:__imp_SysFreeString
0x1800588df  mov     eax, edi
0x1800588e1  jmp     short loc_1800588EA
0x1800588e3  mov     eax, dword ptr [rsp+68h+psz]
0x1800588ea  mov     rbx, [rsp+68h+arg_0]
0x1800588ef  mov     rsi, [rsp+68h+arg_8]
0x1800588f4  add     rsp, 60h
0x1800588f8  pop     rdi
0x1800588f9  retn
```
