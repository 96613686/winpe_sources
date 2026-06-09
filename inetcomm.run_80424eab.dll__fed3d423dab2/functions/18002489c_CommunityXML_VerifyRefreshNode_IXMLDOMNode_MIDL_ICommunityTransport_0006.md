# CommunityXML_VerifyRefreshNode(IXMLDOMNode *,__MIDL_ICommunityTransport_0006 *)

- ea: `0x18002489c`
- end: `0x180024b0b`
- name: `?CommunityXML_VerifyRefreshNode@@YAJPEAUIXMLDOMNode@@PEAU__MIDL_ICommunityTransport_0006@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct __MIDL_ICommunityTransport_0006 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c6a74`

## callees

- `0x1800055bc`
- `0x18000910c`
- `0x18002489c`
- `0x180026290`
- `0x1800c94e4`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800248ed`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024992`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024a4f`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024a67`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024aa2`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800248ed`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024992`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024a4f`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024a67`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x180024aa2`
- `SHLWAPI!StrToIntW` at `0x180024ab2`
- `SHLWAPI!StrToIntW` at `0x180024ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002496e`
- `OLEAUT32!__imp_SysFreeString` at `0x180024a08`
- `OLEAUT32!__imp_SysFreeString` at `0x180024a86`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ad9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002496e`
- `OLEAUT32!__imp_SysFreeString` at `0x180024a08`
- `OLEAUT32!__imp_SysFreeString` at `0x180024a86`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ad9`

## string_xrefs

- `0x1800248e6`: `ThreadID`
- `0x180024a48`: `ThreadAttribute`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyRefreshNode(struct IXMLDOMNode *a1, struct _GUID *a2)
{
  int AttributeValue; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  struct IXMLDOMNode *v9; // rcx
  int CategoryType; // eax
  OLECHAR *v11; // rcx
  int v12; // ecx
  int v13; // eax
  BSTR v15; // [rsp+20h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-31h] BYREF
  unsigned __int16 v17[40]; // [rsp+30h] [rbp-29h] BYREF

  if ( a1 && a2 )
  {
    bstrString = 0;
    AttributeValue = XMLNode_GetAttributeValue(a1, L"ThreadID", &bstrString);
    if ( AttributeValue < 0 )
      return (unsigned int)AttributeValue;
    memset_0(v17, 0, 0x4Eu);
    if ( bstrString )
    {
      if ( *bstrString == 123 )
        v5 = StringCchCopyW(v17, 0x27u, bstrString);
      else
        v5 = StringCchPrintfW(v17, 0x27u, L"{%s}", bstrString);
      AttributeValue = v5;
      if ( v5 >= 0 && !OEGUIDFromStringW(v17, a2 + 19) )
        AttributeValue = -2147467259;
    }
    else
    {
      AttributeValue = -2147024809;
    }
    SysFreeString(bstrString);
    if ( AttributeValue < 0 )
      return (unsigned int)AttributeValue;
    v15 = 0;
    AttributeValue = XMLNode_GetAttributeValue(a1, L"MsgID", &v15);
    if ( AttributeValue < 0 )
      return (unsigned int)AttributeValue;
    memset_0(v17, 0, 0x4Eu);
    if ( v15 )
    {
      if ( *v15 == 123 )
        v6 = StringCchCopyW(v17, 0x27u, v15);
      else
        v6 = StringCchPrintfW(v17, 0x27u, L"{%s}", v15);
      AttributeValue = v6;
      if ( v6 >= 0 && !OEGUIDFromStringW(v17, a2 + 18) )
        AttributeValue = -2147467259;
    }
    else
    {
      AttributeValue = -2147024809;
    }
    SysFreeString(v15);
    if ( AttributeValue < 0 )
      return (unsigned int)AttributeValue;
    v7 = *(_QWORD *)&a2[19].Data1;
    v15 = 0;
    v8 = v7 - *(_QWORD *)&a2[18].Data1;
    if ( !v8 )
      v8 = *(_QWORD *)a2[19].Data4 - *(_QWORD *)a2[18].Data4;
    v9 = a1;
    if ( !v8 )
    {
      if ( (int)XMLNode_GetAttributeValue(a1, L"ThreadAttribute", &v15) >= 0 )
        goto LABEL_31;
      v9 = a1;
    }
    AttributeValue = XMLNode_GetAttributeValue(v9, L"MsgAttribute", &v15);
    if ( AttributeValue < 0 )
      return (unsigned int)AttributeValue;
LABEL_31:
    CategoryType = _GetCategoryType(v15);
    v11 = v15;
    *(_DWORD *)&a2[16].Data4[4] = CategoryType;
    SysFreeString(v11);
    v15 = 0;
    AttributeValue = XMLNode_GetAttributeValue(a1, L"HelpfulMsg", &v15);
    if ( AttributeValue >= 0 )
    {
      v12 = StrToIntW(v15);
      if ( v12 <= 0 )
      {
        v13 = 5;
        if ( v12 )
          v13 = 1;
      }
      else
      {
        v13 = 0;
      }
      *(_DWORD *)&a2[16].Data2 = v13;
      SysFreeString(v15);
    }
    return (unsigned int)AttributeValue;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002489c  mov     [rsp-8+arg_10], rbx
0x1800248a1  push    rbp
0x1800248a2  push    rsi
0x1800248a3  push    rdi
0x1800248a4  push    r12
0x1800248a6  push    r15
0x1800248a8  lea     rbp, [rsp-37h]
0x1800248ad  sub     rsp, 90h
0x1800248b4  mov     rax, cs:__security_cookie
0x1800248bb  xor     rax, rsp
0x1800248be  mov     [rbp+57h+var_30], rax
0x1800248c2  mov     rdi, rdx
0x1800248c5  mov     rsi, rcx
0x1800248c8  test    rcx, rcx
0x1800248cb  jz      loc_180024AE3
0x1800248d1  test    rdx, rdx
0x1800248d4  jz      loc_180024AE3
0x1800248da  lea     r8, [rbp+57h+bstrString]
0x1800248de  mov     [rbp+57h+bstrString], 0
0x1800248e6  lea     rdx, aThreadid; "ThreadID"
0x1800248ed  call    cs:__imp_XMLNode_GetAttributeValue
0x1800248f3  mov     ebx, eax
0x1800248f5  test    eax, eax
0x1800248f7  js      loc_180024ADF
0x1800248fd  xor     edx, edx; Val
0x1800248ff  lea     rcx, [rbp+57h+var_80]; void *
0x180024903  lea     r8d, [rdx+4Eh]; Size
0x180024907  call    memset_0
0x18002490c  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x180024910  mov     r12d, 7Bh ; '{'
0x180024916  lea     r15d, [r12-54h]
0x18002491b  test    r8, r8
0x18002491e  jz      short loc_180024965
0x180024920  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180024924  mov     edx, r15d; unsigned __int64
0x180024927  cmp     r12w, [r8]
0x18002492b  jz      short loc_18002493E
0x18002492d  mov     r9, r8
0x180024930  lea     r8, aS_5; "{%s}"
0x180024937  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002493c  jmp     short loc_180024943
0x18002493e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024943  mov     ebx, eax
0x180024945  test    eax, eax
0x180024947  js      short loc_18002496A
0x180024949  lea     rdx, [rdi+130h]; struct _GUID *
0x180024950  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180024954  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x180024959  test    eax, eax
0x18002495b  mov     eax, 80004005h
0x180024960  cmovz   ebx, eax
0x180024963  jmp     short loc_18002496A
0x180024965  mov     ebx, 80070057h
0x18002496a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002496e  call    cs:__imp_SysFreeString
0x180024974  test    ebx, ebx
0x180024976  js      loc_180024ADF
0x18002497c  lea     r8, [rbp+57h+var_90]
0x180024980  mov     [rbp+57h+var_90], 0
0x180024988  lea     rdx, aMsgid; "MsgID"
0x18002498f  mov     rcx, rsi
0x180024992  call    cs:__imp_XMLNode_GetAttributeValue
0x180024998  mov     ebx, eax
0x18002499a  test    eax, eax
0x18002499c  js      loc_180024ADF
0x1800249a2  xor     edx, edx; Val
0x1800249a4  lea     rcx, [rbp+57h+var_80]; void *
0x1800249a8  lea     r8d, [rdx+4Eh]; Size
0x1800249ac  call    memset_0
0x1800249b1  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1800249b5  test    r8, r8
0x1800249b8  jz      short loc_1800249FF
0x1800249ba  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800249be  mov     rdx, r15; unsigned __int64
0x1800249c1  cmp     r12w, [r8]
0x1800249c5  jz      short loc_1800249D8
0x1800249c7  mov     r9, r8
0x1800249ca  lea     r8, aS_5; "{%s}"
0x1800249d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800249d6  jmp     short loc_1800249DD
0x1800249d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800249dd  mov     ebx, eax
0x1800249df  test    eax, eax
0x1800249e1  js      short loc_180024A04
0x1800249e3  lea     rdx, [rdi+120h]; struct _GUID *
0x1800249ea  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800249ee  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x1800249f3  test    eax, eax
0x1800249f5  mov     eax, 80004005h
0x1800249fa  cmovz   ebx, eax
0x1800249fd  jmp     short loc_180024A04
0x1800249ff  mov     ebx, 80070057h
0x180024a04  mov     rcx, [rbp+57h+var_90]; bstrString
0x180024a08  call    cs:__imp_SysFreeString
0x180024a0e  test    ebx, ebx
0x180024a10  js      loc_180024ADF
0x180024a16  mov     rax, [rdi+130h]
0x180024a1d  mov     [rbp+57h+var_90], 0
0x180024a25  sub     rax, [rdi+120h]
0x180024a2c  jnz     short loc_180024A3C
0x180024a2e  mov     rax, [rdi+138h]
0x180024a35  sub     rax, [rdi+128h]
0x180024a3c  lea     r8, [rbp+57h+var_90]
0x180024a40  mov     rcx, rsi
0x180024a43  test    rax, rax
0x180024a46  jnz     short loc_180024A60
0x180024a48  lea     rdx, aThreadattribut_0; "ThreadAttribute"
0x180024a4f  call    cs:__imp_XMLNode_GetAttributeValue
0x180024a55  test    eax, eax
0x180024a57  jns     short loc_180024A73
0x180024a59  lea     r8, [rbp+57h+var_90]
0x180024a5d  mov     rcx, rsi
0x180024a60  lea     rdx, aMsgattribute; "MsgAttribute"
0x180024a67  call    cs:__imp_XMLNode_GetAttributeValue
0x180024a6d  mov     ebx, eax
0x180024a6f  test    eax, eax
0x180024a71  js      short loc_180024ADF
0x180024a73  mov     rcx, [rbp+57h+var_90]
0x180024a77  call    ?_GetCategoryType@@YA?AW4__MIDL_ICommunityTransport_0002@@PEAG@Z; _GetCategoryType(ushort *)
0x180024a7c  mov     rcx, [rbp+57h+var_90]; bstrString
0x180024a80  mov     [rdi+10Ch], eax
0x180024a86  call    cs:__imp_SysFreeString
0x180024a8c  lea     r8, [rbp+57h+var_90]
0x180024a90  mov     [rbp+57h+var_90], 0
0x180024a98  lea     rdx, aHelpfulmsg; "HelpfulMsg"
0x180024a9f  mov     rcx, rsi
0x180024aa2  call    cs:__imp_XMLNode_GetAttributeValue
0x180024aa8  mov     ebx, eax
0x180024aaa  test    eax, eax
0x180024aac  js      short loc_180024ADF
0x180024aae  mov     rcx, [rbp+57h+var_90]; pszSrc
0x180024ab2  call    cs:__imp_StrToIntW
0x180024ab8  mov     ecx, eax
0x180024aba  test    eax, eax
0x180024abc  jle     short loc_180024AC2
0x180024abe  xor     eax, eax
0x180024ac0  jmp     short loc_180024ACF
0x180024ac2  mov     eax, 5
0x180024ac7  test    ecx, ecx
0x180024ac9  lea     edx, [rax-4]
0x180024acc  cmovnz  eax, edx
0x180024acf  mov     [rdi+104h], eax
0x180024ad5  mov     rcx, [rbp+57h+var_90]; bstrString
0x180024ad9  call    cs:__imp_SysFreeString
0x180024adf  mov     eax, ebx
0x180024ae1  jmp     short loc_180024AE8
0x180024ae3  mov     eax, 80070057h
0x180024ae8  mov     rcx, [rbp+57h+var_30]
0x180024aec  xor     rcx, rsp; StackCookie
0x180024aef  call    __security_check_cookie
0x180024af4  mov     rbx, [rsp+0B0h+arg_10]
0x180024afc  add     rsp, 90h
0x180024b03  pop     r15
0x180024b05  pop     r12
0x180024b07  pop     rdi
0x180024b08  pop     rsi
0x180024b09  pop     rbp
0x180024b0a  retn
```
