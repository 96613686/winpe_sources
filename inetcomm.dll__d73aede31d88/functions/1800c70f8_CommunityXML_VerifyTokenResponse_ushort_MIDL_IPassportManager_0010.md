# CommunityXML_VerifyTokenResponse(ushort *,__MIDL_IPassportManager_0010 *)

- ea: `0x1800c70f8`
- end: `0x1800c72a5`
- name: `?CommunityXML_VerifyTokenResponse@@YAJPEAGPEAU__MIDL_IPassportManager_0010@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct __MIDL_IPassportManager_0010 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800afa10`

## callees

- `0x180002098`
- `0x1800c70f8`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c7128`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c7128`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c7187`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c7187`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c71a9`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c71a9`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c71dc`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c7235`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c71dc`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c7235`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c7202`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c725b`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c7202`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c725b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c71c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c7221`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c71c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c7221`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c71e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c720c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7240`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7265`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c71e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c720c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7240`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7265`

## string_xrefs

- `0x1800c7178`: `GetUsernameTokenResult`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyTokenResponse(unsigned __int16 *a1, CHAR *a2)
{
  int ElementsByTagName; // edi
  int v4; // eax
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rbx
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v10[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF
  PCWSTR pwszSrc; // [rsp+70h] [rbp+30h] BYREF
  PCWSTR v13; // [rsp+78h] [rbp+38h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  v10[0] = 0;
  ElementsByTagName = XMLDOMFromBStr(a1, v10);
  if ( ElementsByTagName >= 0 )
  {
    v9 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v10[0] + 360LL))(v10[0], &v9);
    ElementsByTagName = v4;
    if ( v4 == 1 )
    {
      ElementsByTagName = -2147023728;
    }
    else if ( v4 >= 0 )
    {
      v8 = 0;
      ElementsByTagName = XMLElem_GetElementsByTagName(v9, L"GetUsernameTokenResult", &v8);
      if ( ElementsByTagName >= 0 )
      {
        v11 = 0;
        ElementsByTagName = XMLNodeList_GetChild(v8, 0, &v11);
        if ( ElementsByTagName >= 0 )
        {
          pwszSrc = 0;
          v5 = SysAllocString(L"Username");
          ElementsByTagName = XMLNode_GetChildTagTextValue(v11, v5, &pwszSrc);
          SysFreeString(v5);
          if ( ElementsByTagName >= 0 )
          {
            SHUnicodeToAnsi(pwszSrc, a2 + 8212, 256);
            SysFreeString((BSTR)pwszSrc);
            v13 = 0;
            v6 = SysAllocString(L"Password");
            ElementsByTagName = XMLNode_GetChildTagTextValue(v11, v6, &v13);
            SysFreeString(v6);
            if ( ElementsByTagName >= 0 )
            {
              SHUnicodeToAnsi(v13, a2 + 8468, 256);
              SysFreeString((BSTR)v13);
            }
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v11);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v8);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v9);
    }
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(v10);
  }
  return (unsigned int)ElementsByTagName;
}

```

## disassembly

```asm
0x1800c70f8  mov     [rsp-18h+arg_8], rbx
0x1800c70fd  push    rbp
0x1800c70fe  push    rsi
0x1800c70ff  push    rdi
0x1800c7100  mov     rbp, rsp
0x1800c7103  sub     rsp, 40h
0x1800c7107  mov     rsi, rdx
0x1800c710a  test    rcx, rcx
0x1800c710d  jz      loc_1800C7293
0x1800c7113  test    rdx, rdx
0x1800c7116  jz      loc_1800C7293
0x1800c711c  lea     rdx, [rbp+var_10]
0x1800c7120  mov     [rbp+var_10], 0
0x1800c7128  call    cs:__imp_XMLDOMFromBStr
0x1800c712e  mov     edi, eax
0x1800c7130  test    eax, eax
0x1800c7132  js      loc_1800C728F
0x1800c7138  mov     rcx, [rbp+var_10]
0x1800c713c  lea     rdx, [rbp+var_18]
0x1800c7140  mov     [rbp+var_18], 0
0x1800c7148  mov     rax, [rcx]
0x1800c714b  mov     rax, [rax+168h]
0x1800c7152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7157  mov     edi, eax
0x1800c7159  cmp     eax, 1
0x1800c715c  jnz     short loc_1800C7168
0x1800c715e  mov     edi, 80070490h
0x1800c7163  jmp     loc_1800C7286
0x1800c7168  test    eax, eax
0x1800c716a  js      loc_1800C7286
0x1800c7170  mov     rcx, [rbp+var_18]
0x1800c7174  lea     r8, [rbp+var_20]
0x1800c7178  lea     rdx, aGetusernametok; "GetUsernameTokenResult"
0x1800c717f  mov     [rbp+var_20], 0
0x1800c7187  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c718d  mov     edi, eax
0x1800c718f  test    eax, eax
0x1800c7191  js      loc_1800C727D
0x1800c7197  mov     rcx, [rbp+var_20]
0x1800c719b  lea     r8, [rbp+arg_0]
0x1800c719f  xor     edx, edx
0x1800c71a1  mov     [rbp+arg_0], 0
0x1800c71a9  call    cs:__imp_XMLNodeList_GetChild
0x1800c71af  mov     edi, eax
0x1800c71b1  test    eax, eax
0x1800c71b3  js      loc_1800C7274
0x1800c71b9  lea     rcx, psz; "Username"
0x1800c71c0  mov     [rbp+pwszSrc], 0
0x1800c71c8  call    cs:__imp_SysAllocString
0x1800c71ce  mov     rcx, [rbp+arg_0]
0x1800c71d2  lea     r8, [rbp+pwszSrc]
0x1800c71d6  mov     rdx, rax
0x1800c71d9  mov     rbx, rax
0x1800c71dc  call    cs:__imp_XMLNode_GetChildTagTextValue
0x1800c71e2  mov     rcx, rbx; bstrString
0x1800c71e5  mov     edi, eax
0x1800c71e7  call    cs:__imp_SysFreeString
0x1800c71ed  test    edi, edi
0x1800c71ef  js      short loc_1800C726B
0x1800c71f1  mov     rcx, [rbp+pwszSrc]; pwszSrc
0x1800c71f5  lea     rdx, [rsi+2014h]; pszDst
0x1800c71fc  mov     r8d, 100h; cchBuf
0x1800c7202  call    cs:__imp_SHUnicodeToAnsi
0x1800c7208  mov     rcx, [rbp+pwszSrc]; bstrString
0x1800c720c  call    cs:__imp_SysFreeString
0x1800c7212  lea     rcx, aPassword; "Password"
0x1800c7219  mov     [rbp+arg_18], 0
0x1800c7221  call    cs:__imp_SysAllocString
0x1800c7227  mov     rcx, [rbp+arg_0]
0x1800c722b  lea     r8, [rbp+arg_18]
0x1800c722f  mov     rdx, rax
0x1800c7232  mov     rbx, rax
0x1800c7235  call    cs:__imp_XMLNode_GetChildTagTextValue
0x1800c723b  mov     rcx, rbx; bstrString
0x1800c723e  mov     edi, eax
0x1800c7240  call    cs:__imp_SysFreeString
0x1800c7246  test    edi, edi
0x1800c7248  js      short loc_1800C726B
0x1800c724a  mov     rcx, [rbp+arg_18]; pwszSrc
0x1800c724e  lea     rdx, [rsi+2114h]; pszDst
0x1800c7255  mov     r8d, 100h; cchBuf
0x1800c725b  call    cs:__imp_SHUnicodeToAnsi
0x1800c7261  mov     rcx, [rbp+arg_18]; bstrString
0x1800c7265  call    cs:__imp_SysFreeString
0x1800c726b  lea     rcx, [rbp+arg_0]
0x1800c726f  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c7274  lea     rcx, [rbp+var_20]
0x1800c7278  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c727d  lea     rcx, [rbp+var_18]
0x1800c7281  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c7286  lea     rcx, [rbp+var_10]
0x1800c728a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c728f  mov     eax, edi
0x1800c7291  jmp     short loc_1800C7298
0x1800c7293  mov     eax, 80070057h
0x1800c7298  mov     rbx, [rsp+40h+arg_8]
0x1800c729d  add     rsp, 40h
0x1800c72a1  pop     rdi
0x1800c72a2  pop     rsi
0x1800c72a3  pop     rbp
0x1800c72a4  retn
```
