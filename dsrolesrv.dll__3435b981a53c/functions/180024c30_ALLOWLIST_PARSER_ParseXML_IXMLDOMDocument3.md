# ALLOWLIST_PARSER::ParseXML(IXMLDOMDocument3 *)

- ea: `0x180024c30`
- end: `0x18002503b`
- name: `?ParseXML@ALLOWLIST_PARSER@@MEAAJPEAUIXMLDOMDocument3@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(ALLOWLIST_PARSER *__hidden this, struct IXMLDOMDocument3 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180023bac`
- `0x180024c30`
- `0x18002527c`
- `0x1800273e4`
- `0x18002c050`
- `0x18002e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180024f27`
- `msvcrt!_wcsicmp` at `0x180024f27`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180024de3`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180024d6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180024de3`
- `OLEAUT32!__imp_SysFreeString` at `0x180024e7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fca`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fe9`
- `OLEAUT32!__imp_SysFreeString` at `0x180025006`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c686`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c690`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180024e7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fca`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180024fe9`
- `OLEAUT32!__imp_SysFreeString` at `0x180025006`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c686`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c690`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6c2`
- `OLEAUT32!__imp_SysStringLen` at `0x180024eb0`
- `OLEAUT32!__imp_SysStringLen` at `0x180024efa`
- `OLEAUT32!__imp_SysStringLen` at `0x180024eb0`
- `OLEAUT32!__imp_SysStringLen` at `0x180024efa`
- `OLEAUT32!__imp_VariantInit` at `0x180024d1a`
- `OLEAUT32!__imp_VariantInit` at `0x180024d1a`
- `OLEAUT32!__imp_VariantClear` at `0x180024ffd`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6b8`
- `OLEAUT32!__imp_VariantClear` at `0x180024ffd`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6b8`

## string_xrefs

- `0x180024d66`: `xmlns:dc='uri:microsoft.com:schemas:CustomDCCloneAllowList'`
- `0x180024f7e`: `Failed to parse allowed list XML, empty name is specified in the XML\n`
- `0x180024f6b`: `Failed to parse allowed list XML, missing software type for name %s\n`
- `0x180024f3d`: `Failed to parse allowed list XML, invalid software type %s\n`

## pseudocode

```c
__int64 __fastcall ALLOWLIST_PARSER::ParseXML(ALLOWLIST_PARSER *this, struct IXMLDOMDocument3 *a2)
{
  OLECHAR *v4; // r14
  _QWORD *v5; // rsi
  int NodeText; // ebx
  struct IXMLDOMDocument3Vtbl *lpVtbl; // rax
  int v8; // edi
  BSTR v9; // rax
  int v10; // eax
  unsigned int v11; // edi
  signed int i; // ebx
  const wchar_t *v13; // rdx
  __int64 j; // rdi
  struct IXMLDOMNode *v16; // [rsp+20h] [rbp-128h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-120h] BYREF
  BSTR pbstr; // [rsp+30h] [rbp-118h] BYREF
  __int64 v19; // [rsp+38h] [rbp-110h] BYREF
  int v20; // [rsp+40h] [rbp-108h]
  signed int v21; // [rsp+44h] [rbp-104h]
  _QWORD *v22; // [rsp+48h] [rbp-100h]
  OLECHAR *v23; // [rsp+50h] [rbp-F8h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-F0h] BYREF
  VARIANTARG v25; // [rsp+70h] [rbp-D8h] BYREF
  _QWORD v26[8]; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD v27[8]; // [rsp+D0h] [rbp-78h] BYREF

  v19 = 0;
  v16 = 0;
  bstrString = 0;
  pbstr = 0;
  v4 = 0;
  v23 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v26[0] = L"Unused";
  v26[1] = 0;
  v26[2] = L"//AllowList/Allow";
  v26[3] = 0;
  v26[4] = L"Name";
  v26[5] = 0;
  v26[6] = L"Type";
  v26[7] = 0;
  v27[0] = L"Unused";
  v27[1] = 0;
  v27[2] = L"//dc:CustomDCCloneAllowList/Allow";
  v27[3] = 0;
  v27[4] = L"Name";
  v27[5] = 0;
  v27[6] = L"Type";
  v27[7] = 0;
  v5 = v26;
  v22 = v26;
  VariantInit(&pvarg);
  if ( !*((_DWORD *)this + 4) )
    goto LABEL_7;
  v5 = v27;
  v22 = v27;
  v4 = SysAllocString(L"SelectionNamespaces");
  v23 = v4;
  if ( !v4
    || (pvarg.vt = 8,
        (pvarg.llVal = (LONGLONG)SysAllocString(L"xmlns:dc='uri:microsoft.com:schemas:CustomDCCloneAllowList'")) == 0) )
  {
LABEL_3:
    NodeText = 14;
    goto LABEL_43;
  }
  lpVtbl = a2->lpVtbl;
  v25 = pvarg;
  NodeText = ((__int64 (__fastcall *)(struct IXMLDOMDocument3 *, OLECHAR *, VARIANTARG *))lpVtbl->setProperty)(
               a2,
               v4,
               &v25);
  if ( NodeText )
  {
    ClLogPrint(2, L"Failed to set selection namespaces\n");
  }
  else
  {
LABEL_7:
    v8 = 0;
    v20 = 0;
    while ( v8 < 4 )
    {
      v9 = SysAllocString((const OLECHAR *)v5[2 * v8]);
      v5[2 * v8 + 1] = v9;
      if ( !v9 )
        goto LABEL_3;
      v20 = ++v8;
    }
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument3 *, _QWORD, __int64 *))a2->lpVtbl->selectNodes)(
            a2,
            v5[3],
            &v19);
    if ( v10 )
    {
      NodeText = 0;
      if ( v10 != 1 )
        NodeText = v10;
    }
    else
    {
      while ( 1 )
      {
        if ( v16 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
          v16 = 0;
        }
        if ( (*(unsigned int (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v19 + 72LL))(v19, &v16) || !v16 )
          break;
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        NodeText = getNodeText(v16, (unsigned __int16 *)v5[5], &bstrString);
        if ( NodeText < 0 )
          goto LABEL_43;
        if ( !bstrString || !SysStringLen(bstrString) )
        {
          ClLogPrint(2, L"Failed to parse allowed list XML, empty name is specified in the XML\n");
          goto LABEL_41;
        }
        if ( pbstr )
        {
          SysFreeString(pbstr);
          pbstr = 0;
        }
        NodeText = getNodeText(v16, (unsigned __int16 *)v5[7], &pbstr);
        if ( NodeText < 0 )
          goto LABEL_43;
        if ( !pbstr || !SysStringLen(pbstr) )
        {
          v13 = L"Failed to parse allowed list XML, missing software type for name %s\n";
          goto LABEL_39;
        }
        v11 = -1;
        for ( i = 0; ; ++i )
        {
          v21 = i;
          if ( (unsigned __int64)i >= 3 )
            break;
          if ( !_wcsicmp(pbstr, off_18002F378[i]) )
          {
            v11 = i;
            break;
          }
        }
        if ( v11 == -1 )
        {
          v13 = L"Failed to parse allowed list XML, invalid software type %s\n";
LABEL_39:
          ClLogPrint(2, v13);
LABEL_41:
          NodeText = 87;
          goto LABEL_43;
        }
        NodeText = CLONE_SOFTWARE_LIST::AddSoftwareElement(*((_QWORD *)this + 1), bstrString, v11);
        if ( NodeText )
          goto LABEL_43;
      }
      NodeText = 0;
    }
  }
LABEL_43:
  if ( v16 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  SysFreeString(bstrString);
  SysFreeString(pbstr);
  for ( j = 0; j != 4; ++j )
    SysFreeString((BSTR)v5[2 * j + 1]);
  VariantClear(&pvarg);
  SysFreeString(v4);
  return (unsigned int)NodeText;
}

```

## disassembly

```asm
0x180024c30  mov     r11, rsp
0x180024c33  mov     [r11+18h], rbx
0x180024c37  mov     [r11+20h], rsi
0x180024c3b  push    rdi
0x180024c3c  push    r12
0x180024c3e  push    r13
0x180024c40  push    r14
0x180024c42  push    r15
0x180024c44  sub     rsp, 120h
0x180024c4b  mov     rax, cs:__security_cookie
0x180024c52  xor     rax, rsp
0x180024c55  mov     [rsp+148h+var_38], rax
0x180024c5d  mov     r15, rdx
0x180024c60  mov     r13, rcx
0x180024c63  xor     r12d, r12d
0x180024c66  mov     [rsp+148h+var_110], r12
0x180024c6b  mov     [rsp+148h+var_128], r12
0x180024c70  mov     [rsp+148h+bstrString], r12
0x180024c75  mov     [rsp+148h+pbstr], r12
0x180024c7a  mov     r14d, r12d
0x180024c7d  mov     [rsp+148h+var_F8], r12
0x180024c82  xorps   xmm0, xmm0
0x180024c85  xor     eax, eax
0x180024c87  movups  xmmword ptr [rsp+148h+pvarg], xmm0
0x180024c8c  mov     qword ptr [rsp+148h+pvarg+10h], rax
0x180024c91  lea     r8, aUnused; "Unused"
0x180024c98  mov     [r11-0B8h], r8
0x180024c9f  mov     [r11-0B0h], r12
0x180024ca6  lea     rax, aAllowlistAllow; "//AllowList/Allow"
0x180024cad  mov     [r11-0A8h], rax
0x180024cb4  mov     [r11-0A0h], r12
0x180024cbb  lea     rdx, aName; "Name"
0x180024cc2  mov     [r11-98h], rdx
0x180024cc9  mov     [r11-90h], r12
0x180024cd0  lea     rcx, aType; "Type"
0x180024cd7  mov     [r11-88h], rcx
0x180024cde  mov     [r11-80h], r12
0x180024ce2  mov     [r11-78h], r8
0x180024ce6  mov     [r11-70h], r12
0x180024cea  lea     rax, aDcCustomdcclon; "//dc:CustomDCCloneAllowList/Allow"
0x180024cf1  mov     [r11-68h], rax
0x180024cf5  mov     [r11-60h], r12
0x180024cf9  mov     [r11-58h], rdx
0x180024cfd  mov     [r11-50h], r12
0x180024d01  mov     [r11-48h], rcx
0x180024d05  mov     [r11-40h], r12
0x180024d09  lea     rsi, [r11-0B8h]
0x180024d10  mov     [rsp+148h+var_100], rsi
0x180024d15  lea     rcx, [rsp+148h+pvarg]; pvarg
0x180024d1a  call    cs:__imp_VariantInit
0x180024d20  nop
0x180024d21  cmp     [r13+10h], r12d
0x180024d25  jz      loc_180024DCC
0x180024d2b  lea     rsi, [rsp+148h+var_78]
0x180024d33  mov     [rsp+148h+var_100], rsi
0x180024d38  lea     rcx, psz; "SelectionNamespaces"
0x180024d3f  call    cs:__imp_SysAllocString
0x180024d45  mov     r14, rax
0x180024d48  mov     [rsp+148h+var_F8], rax
0x180024d4d  test    rax, rax
0x180024d50  jnz     short loc_180024D5C
0x180024d52  mov     ebx, 0Eh
0x180024d57  jmp     loc_180024F99
0x180024d5c  mov     eax, 8
0x180024d61  mov     word ptr [rsp+148h+pvarg], ax
0x180024d66  lea     rcx, aXmlnsDcUriMicr; "xmlns:dc='uri:microsoft.com:schemas:Cus"...
0x180024d6d  call    cs:__imp_SysAllocString
0x180024d73  mov     qword ptr [rsp+148h+pvarg+8], rax
0x180024d78  test    rax, rax
0x180024d7b  jz      short loc_180024D52
0x180024d7d  mov     rax, [r15]
0x180024d80  movups  xmm0, xmmword ptr [rsp+148h+pvarg]
0x180024d85  movaps  [rsp+148h+var_D8], xmm0
0x180024d8a  movsd   xmm1, qword ptr [rsp+148h+pvarg+10h]
0x180024d90  movsd   [rsp+148h+var_C8], xmm1
0x180024d99  lea     r8, [rsp+148h+var_D8]
0x180024d9e  mov     rdx, r14
0x180024da1  mov     rcx, r15
0x180024da4  mov     rax, [rax+280h]
0x180024dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024db0  mov     ebx, eax
0x180024db2  test    eax, eax
0x180024db4  jz      short loc_180024DCC
0x180024db6  lea     rdx, aFailedToSetSel; "Failed to set selection namespaces\n"
0x180024dbd  mov     ecx, 2
0x180024dc2  call    ClLogPrint
0x180024dc7  jmp     loc_180024F99
0x180024dcc  mov     edi, r12d
0x180024dcf  mov     [rsp+148h+var_108], r12d
0x180024dd4  cmp     edi, 4
0x180024dd7  jge     short loc_180024DFF
0x180024dd9  movsxd  rbx, edi
0x180024ddc  add     rbx, rbx
0x180024ddf  mov     rcx, [rsi+rbx*8]; psz
0x180024de3  call    cs:__imp_SysAllocString
0x180024de9  mov     [rsi+rbx*8+8], rax
0x180024dee  test    rax, rax
0x180024df1  jz      loc_180024D52
0x180024df7  inc     edi
0x180024df9  mov     [rsp+148h+var_108], edi
0x180024dfd  jmp     short loc_180024DD4
0x180024dff  mov     rax, [r15]
0x180024e02  lea     r8, [rsp+148h+var_110]
0x180024e07  mov     rdx, [rsi+18h]
0x180024e0b  mov     rcx, r15
0x180024e0e  mov     rax, [rax+120h]
0x180024e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e1a  test    eax, eax
0x180024e1c  jz      short loc_180024E2C
0x180024e1e  mov     ebx, r12d
0x180024e21  cmp     eax, 1
0x180024e24  cmovnz  ebx, eax
0x180024e27  jmp     loc_180024F99
0x180024e2c  mov     rcx, [rsp+148h+var_128]
0x180024e31  test    rcx, rcx
0x180024e34  jz      short loc_180024E47
0x180024e36  mov     rax, [rcx]
0x180024e39  mov     rax, [rax+10h]
0x180024e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e42  mov     [rsp+148h+var_128], r12
0x180024e47  mov     rcx, [rsp+148h+var_110]
0x180024e4c  mov     rax, [rcx]
0x180024e4f  lea     rdx, [rsp+148h+var_128]
0x180024e54  mov     rax, [rax+48h]
0x180024e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e5d  test    eax, eax
0x180024e5f  jnz     loc_180024F96
0x180024e65  cmp     [rsp+148h+var_128], r12
0x180024e6a  jz      loc_180024F96
0x180024e70  mov     rcx, [rsp+148h+bstrString]; bstrString
0x180024e75  test    rcx, rcx
0x180024e78  jz      short loc_180024E85
0x180024e7a  call    cs:__imp_SysFreeString
0x180024e80  mov     [rsp+148h+bstrString], r12
0x180024e85  lea     r8, [rsp+148h+bstrString]; unsigned __int16 **
0x180024e8a  mov     rdx, [rsi+28h]; unsigned __int16 *
0x180024e8e  mov     rcx, [rsp+148h+var_128]; struct IXMLDOMNode *
0x180024e93  call    ?getNodeText@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; getNodeText(IXMLDOMNode *,ushort *,ushort * *)
0x180024e98  mov     ebx, eax
0x180024e9a  test    eax, eax
0x180024e9c  js      loc_180024F99
0x180024ea2  mov     rcx, [rsp+148h+bstrString]; pbstr
0x180024ea7  test    rcx, rcx
0x180024eaa  jz      loc_180024F7E
0x180024eb0  call    cs:__imp_SysStringLen
0x180024eb6  test    eax, eax
0x180024eb8  jz      loc_180024F7E
0x180024ebe  mov     rcx, [rsp+148h+pbstr]; bstrString
0x180024ec3  test    rcx, rcx
0x180024ec6  jz      short loc_180024ED3
0x180024ec8  call    cs:__imp_SysFreeString
0x180024ece  mov     [rsp+148h+pbstr], r12
0x180024ed3  lea     r8, [rsp+148h+pbstr]; unsigned __int16 **
0x180024ed8  mov     rdx, [rsi+38h]; unsigned __int16 *
0x180024edc  mov     rcx, [rsp+148h+var_128]; struct IXMLDOMNode *
0x180024ee1  call    ?getNodeText@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; getNodeText(IXMLDOMNode *,ushort *,ushort * *)
0x180024ee6  mov     ebx, eax
0x180024ee8  test    eax, eax
0x180024eea  js      loc_180024F99
0x180024ef0  mov     rcx, [rsp+148h+pbstr]; pbstr
0x180024ef5  test    rcx, rcx
0x180024ef8  jz      short loc_180024F66
0x180024efa  call    cs:__imp_SysStringLen
0x180024f00  test    eax, eax
0x180024f02  jz      short loc_180024F66
0x180024f04  or      edi, 0FFFFFFFFh
0x180024f07  mov     ebx, r12d
0x180024f0a  mov     [rsp+148h+var_104], ebx
0x180024f0e  movsxd  rdx, ebx
0x180024f11  cmp     rdx, 3
0x180024f15  jnb     short loc_180024F33
0x180024f17  lea     rax, off_18002F378; "Program"
0x180024f1e  mov     rdx, [rax+rdx*8]; String2
0x180024f22  mov     rcx, [rsp+148h+pbstr]; String1
0x180024f27  call    cs:__imp__wcsicmp
0x180024f2d  test    eax, eax
0x180024f2f  jnz     short loc_180024F46
0x180024f31  mov     edi, ebx
0x180024f33  cmp     edi, 0FFFFFFFFh
0x180024f36  jnz     short loc_180024F4A
0x180024f38  mov     r8, [rsp+148h+pbstr]
0x180024f3d  lea     rdx, aFailedToParseA_1; "Failed to parse allowed list XML, inval"...
0x180024f44  jmp     short loc_180024F72
0x180024f46  inc     ebx
0x180024f48  jmp     short loc_180024F0A
0x180024f4a  mov     r8d, edi
0x180024f4d  mov     rdx, [rsp+148h+bstrString]
0x180024f52  mov     rcx, [r13+8]
0x180024f56  call    ?AddSoftwareElement@CLONE_SOFTWARE_LIST@@QEAAKPEAGW4CLONE_SOFTWARE_TYPE@@@Z; CLONE_SOFTWARE_LIST::AddSoftwareElement(ushort *,CLONE_SOFTWARE_TYPE)
0x180024f5b  mov     ebx, eax
0x180024f5d  test    eax, eax
0x180024f5f  jnz     short loc_180024F99
0x180024f61  jmp     loc_180024E2C
0x180024f66  mov     r8, [rsp+148h+bstrString]
0x180024f6b  lea     rdx, aFailedToParseA; "Failed to parse allowed list XML, missi"...
0x180024f72  mov     ecx, 2
0x180024f77  call    ClLogPrint
0x180024f7c  jmp     short loc_180024F8F
0x180024f7e  lea     rdx, aFailedToParseA_0; "Failed to parse allowed list XML, empty"...
0x180024f85  mov     ecx, 2
0x180024f8a  call    ClLogPrint
0x180024f8f  mov     ebx, 57h ; 'W'
0x180024f94  jmp     short loc_180024F99
0x180024f96  mov     ebx, r12d
0x180024f99  mov     rcx, [rsp+148h+var_128]
0x180024f9e  test    rcx, rcx
0x180024fa1  jz      short loc_180024FAF
0x180024fa3  mov     rax, [rcx]
0x180024fa6  mov     rax, [rax+10h]
0x180024faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024faf  mov     rcx, [rsp+148h+var_110]
0x180024fb4  test    rcx, rcx
0x180024fb7  jz      short loc_180024FC5
0x180024fb9  mov     rax, [rcx]
0x180024fbc  mov     rax, [rax+10h]
0x180024fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fc5  mov     rcx, [rsp+148h+bstrString]; bstrString
0x180024fca  call    cs:__imp_SysFreeString
0x180024fd0  mov     rcx, [rsp+148h+pbstr]; bstrString
0x180024fd5  call    cs:__imp_SysFreeString
0x180024fdb  mov     rdi, r12
0x180024fde  mov     rcx, rdi
0x180024fe1  add     rcx, rcx
0x180024fe4  mov     rcx, [rsi+rcx*8+8]; bstrString
0x180024fe9  call    cs:__imp_SysFreeString
0x180024fef  inc     rdi
0x180024ff2  cmp     rdi, 4
0x180024ff6  jnz     short loc_180024FDE
0x180024ff8  lea     rcx, [rsp+148h+pvarg]; pvarg
0x180024ffd  call    cs:__imp_VariantClear
0x180025003  mov     rcx, r14; bstrString
0x180025006  call    cs:__imp_SysFreeString
0x18002500c  mov     eax, ebx
0x18002500e  mov     rcx, [rsp+148h+var_38]
0x180025016  xor     rcx, rsp; StackCookie
0x180025019  call    __security_check_cookie
0x18002501e  lea     r11, [rsp+148h+var_28]
0x180025026  mov     rbx, [r11+40h]
0x18002502a  mov     rsi, [r11+48h]
0x18002502e  mov     rsp, r11
0x180025031  pop     r15
0x180025033  pop     r14
0x180025035  pop     r13
0x180025037  pop     r12
0x180025039  pop     rdi
0x18002503a  retn
0x18002c64b  push    rbx
0x18002c64d  push    rbp
0x18002c64e  push    rdi
0x18002c64f  sub     rsp, 20h
0x18002c653  mov     rbp, rdx
0x18002c656  mov     rcx, [rbp+20h]
0x18002c65a  test    rcx, rcx
0x18002c65d  jz      short loc_18002C66C
0x18002c65f  mov     rax, [rcx]
0x18002c662  mov     rax, [rax+10h]
0x18002c666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c66b  nop
0x18002c66c  mov     rcx, [rbp+38h]
0x18002c670  test    rcx, rcx
0x18002c673  jz      short loc_18002C682
0x18002c675  mov     rax, [rcx]
0x18002c678  mov     rax, [rax+10h]
0x18002c67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c681  nop
0x18002c682  mov     rcx, [rbp+28h]; bstrString
0x18002c686  call    cs:__imp_SysFreeString
0x18002c68c  mov     rcx, [rbp+30h]; bstrString
0x18002c690  call    cs:__imp_SysFreeString
0x18002c696  xor     ebx, ebx
0x18002c698  mov     rdi, [rbp+48h]
0x18002c69c  movsxd  rcx, ebx
0x18002c69f  add     rcx, rcx
0x18002c6a2  mov     rcx, [rdi+rcx*8+8]; bstrString
0x18002c6a7  call    cs:__imp_SysFreeString
0x18002c6ad  inc     ebx
0x18002c6af  cmp     ebx, 4
0x18002c6b2  jl      short loc_18002C69C
0x18002c6b4  lea     rcx, [rbp+58h]; pvarg
0x18002c6b8  call    cs:__imp_VariantClear
0x18002c6be  mov     rcx, [rbp+50h]; bstrString
0x18002c6c2  call    cs:__imp_SysFreeString
0x18002c6c8  nop
0x18002c6c9  add     rsp, 20h
0x18002c6cd  pop     rdi
0x18002c6ce  pop     rbp
0x18002c6cf  pop     rbx
0x18002c6d0  retn
```
