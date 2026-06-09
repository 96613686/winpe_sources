# CommunityXML_VerifyContribIDResponse(ushort *,char *,ulong)

- ea: `0x1800c5f98`
- end: `0x1800c6143`
- name: `?CommunityXML_VerifyContribIDResponse@@YAJPEAGPEADK@Z`
- size: `427`
- prototype: `int(unsigned __int16 *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b0f5c`

## callees

- `0x180002098`
- `0x18000910c`
- `0x1800c5f98`
- `0x1800c94e4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c5fde`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c5fde`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c603d`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c603d`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c605f`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c605f`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c607f`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c607f`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c60dc`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c60dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c60ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c60ef`

## string_xrefs

- `0x1800c602e`: `GetContribIDFromSIDResult`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyContribIDResponse(unsigned __int16 *a1, char *a2)
{
  int ElementsByTagName; // ebx
  int v4; // eax
  BSTR bstrString; // [rsp+20h] [rbp-49h] BYREF
  __int64 v7; // [rsp+28h] [rbp-41h] BYREF
  __int64 v8; // [rsp+30h] [rbp-39h] BYREF
  __int64 v9; // [rsp+38h] [rbp-31h] BYREF
  __int64 v10; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID v11; // [rsp+48h] [rbp-21h] BYREF
  WCHAR pwszSrc[40]; // [rsp+60h] [rbp-9h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  v10 = 0;
  ElementsByTagName = XMLDOMFromBStr(a1, &v10);
  if ( ElementsByTagName >= 0 )
  {
    v9 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 360LL))(v10, &v9);
    ElementsByTagName = v4;
    if ( v4 == 1 )
    {
      ElementsByTagName = -2147023728;
    }
    else if ( v4 >= 0 )
    {
      v8 = 0;
      ElementsByTagName = XMLElem_GetElementsByTagName(v9, L"GetContribIDFromSIDResult", &v8);
      if ( ElementsByTagName >= 0 )
      {
        v7 = 0;
        ElementsByTagName = XMLNodeList_GetChild(v8, 0, &v7);
        if ( ElementsByTagName >= 0 )
        {
          bstrString = 0;
          ElementsByTagName = XMLNode_GetTagText(v7, &bstrString);
          if ( ElementsByTagName >= 0 )
          {
            v11 = GUID_NULL;
            memset_0(pwszSrc, 0, 0x4Eu);
            StringCchPrintfW(pwszSrc, 0x27u, L"{%s}", bstrString);
            if ( OEGUIDFromStringW(pwszSrc, &v11) )
            {
              SHUnicodeToAnsi(pwszSrc, a2, 39);
              ElementsByTagName = 0;
            }
            else
            {
              ElementsByTagName = -2147467259;
            }
            SysFreeString(bstrString);
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v7);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v8);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v9);
    }
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
  }
  return (unsigned int)ElementsByTagName;
}

```

## disassembly

```asm
0x1800c5f98  mov     [rsp-8+arg_10], rbx
0x1800c5f9d  mov     [rsp-8+arg_18], rdi
0x1800c5fa2  push    rbp
0x1800c5fa3  lea     rbp, [rsp-57h]
0x1800c5fa8  sub     rsp, 0C0h
0x1800c5faf  mov     rax, cs:__security_cookie
0x1800c5fb6  xor     rax, rsp
0x1800c5fb9  mov     [rbp+57h+var_10], rax
0x1800c5fbd  mov     rdi, rdx
0x1800c5fc0  test    rcx, rcx
0x1800c5fc3  jz      loc_1800C611D
0x1800c5fc9  test    rdx, rdx
0x1800c5fcc  jz      loc_1800C611D
0x1800c5fd2  lea     rdx, [rbp+57h+var_80]
0x1800c5fd6  mov     [rbp+57h+var_80], 0
0x1800c5fde  call    cs:__imp_XMLDOMFromBStr
0x1800c5fe4  mov     ebx, eax
0x1800c5fe6  test    eax, eax
0x1800c5fe8  js      loc_1800C6119
0x1800c5fee  mov     rcx, [rbp+57h+var_80]
0x1800c5ff2  lea     rdx, [rbp+57h+var_88]
0x1800c5ff6  mov     [rbp+57h+var_88], 0
0x1800c5ffe  mov     rax, [rcx]
0x1800c6001  mov     rax, [rax+168h]
0x1800c6008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c600d  mov     ebx, eax
0x1800c600f  cmp     eax, 1
0x1800c6012  jnz     short loc_1800C601E
0x1800c6014  mov     ebx, 80070490h
0x1800c6019  jmp     loc_1800C6110
0x1800c601e  test    eax, eax
0x1800c6020  js      loc_1800C6110
0x1800c6026  mov     rcx, [rbp+57h+var_88]
0x1800c602a  lea     r8, [rbp+57h+var_90]
0x1800c602e  lea     rdx, aGetcontribidfr_1; "GetContribIDFromSIDResult"
0x1800c6035  mov     [rbp+57h+var_90], 0
0x1800c603d  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c6043  mov     ebx, eax
0x1800c6045  test    eax, eax
0x1800c6047  js      loc_1800C6107
0x1800c604d  mov     rcx, [rbp+57h+var_90]
0x1800c6051  lea     r8, [rbp+57h+var_98]
0x1800c6055  xor     edx, edx
0x1800c6057  mov     [rbp+57h+var_98], 0
0x1800c605f  call    cs:__imp_XMLNodeList_GetChild
0x1800c6065  mov     ebx, eax
0x1800c6067  test    eax, eax
0x1800c6069  js      loc_1800C60FE
0x1800c606f  mov     rcx, [rbp+57h+var_98]
0x1800c6073  lea     rdx, [rbp+57h+bstrString]
0x1800c6077  mov     [rbp+57h+bstrString], 0
0x1800c607f  call    cs:__imp_XMLNode_GetTagText
0x1800c6085  mov     ebx, eax
0x1800c6087  test    eax, eax
0x1800c6089  js      short loc_1800C60F5
0x1800c608b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800c6092  xor     edx, edx; Val
0x1800c6094  lea     rcx, [rbp+57h+pwszSrc]; void *
0x1800c6098  movdqu  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x1800c609d  lea     r8d, [rdx+4Eh]; Size
0x1800c60a1  call    memset_0
0x1800c60a6  mov     r9, [rbp+57h+bstrString]
0x1800c60aa  lea     r8, aS_5; "{%s}"
0x1800c60b1  mov     ebx, 27h ; '''
0x1800c60b6  lea     rcx, [rbp+57h+pwszSrc]; unsigned __int16 *
0x1800c60ba  mov     edx, ebx; unsigned __int64
0x1800c60bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c60c1  lea     rdx, [rbp+57h+var_78]; struct _GUID *
0x1800c60c5  lea     rcx, [rbp+57h+pwszSrc]; unsigned __int16 *
0x1800c60c9  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x1800c60ce  test    eax, eax
0x1800c60d0  jz      short loc_1800C60E6
0x1800c60d2  mov     r8d, ebx; cchBuf
0x1800c60d5  lea     rcx, [rbp+57h+pwszSrc]; pwszSrc
0x1800c60d9  mov     rdx, rdi; pszDst
0x1800c60dc  call    cs:__imp_SHUnicodeToAnsi
0x1800c60e2  xor     ebx, ebx
0x1800c60e4  jmp     short loc_1800C60EB
0x1800c60e6  mov     ebx, 80004005h
0x1800c60eb  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800c60ef  call    cs:__imp_SysFreeString
0x1800c60f5  lea     rcx, [rbp+57h+var_98]
0x1800c60f9  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c60fe  lea     rcx, [rbp+57h+var_90]
0x1800c6102  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6107  lea     rcx, [rbp+57h+var_88]
0x1800c610b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6110  lea     rcx, [rbp+57h+var_80]
0x1800c6114  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6119  mov     eax, ebx
0x1800c611b  jmp     short loc_1800C6122
0x1800c611d  mov     eax, 80070057h
0x1800c6122  mov     rcx, [rbp+57h+var_10]
0x1800c6126  xor     rcx, rsp; StackCookie
0x1800c6129  call    __security_check_cookie
0x1800c612e  lea     r11, [rsp+0C0h+var_s0]
0x1800c6136  mov     rbx, [r11+20h]
0x1800c613a  mov     rdi, [r11+28h]
0x1800c613e  mov     rsp, r11
0x1800c6141  pop     rbp
0x1800c6142  retn
```
