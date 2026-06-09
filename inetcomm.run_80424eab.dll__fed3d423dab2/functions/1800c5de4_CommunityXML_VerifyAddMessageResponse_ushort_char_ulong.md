# CommunityXML_VerifyAddMessageResponse(ushort *,char *,ulong)

- ea: `0x1800c5de4`
- end: `0x1800c5f8f`
- name: `?CommunityXML_VerifyAddMessageResponse@@YAJPEAGPEADK@Z`
- size: `427`
- prototype: `int(unsigned __int16 *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b0f5c`

## callees

- `0x180002098`
- `0x18000910c`
- `0x1800c5de4`
- `0x1800c94e4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c5e2a`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c5e2a`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c5e89`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c5e89`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c5eab`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c5eab`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c5ecb`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c5ecb`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c5f28`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c5f28`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5f3b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5f3b`

## string_xrefs

- `0x1800c5e7a`: `UpdateResult`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyAddMessageResponse(unsigned __int16 *a1, char *a2)
{
  int ElementsByTagName; // ebx
  int v4; // eax
  PCWSTR pwszSrc; // [rsp+20h] [rbp-49h] BYREF
  __int64 v7; // [rsp+28h] [rbp-41h] BYREF
  __int64 v8; // [rsp+30h] [rbp-39h] BYREF
  __int64 v9; // [rsp+38h] [rbp-31h] BYREF
  __int64 v10; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID v11; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 v12[40]; // [rsp+60h] [rbp-9h] BYREF

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
      ElementsByTagName = XMLElem_GetElementsByTagName(v9, L"UpdateResult", &v8);
      if ( ElementsByTagName >= 0 )
      {
        v7 = 0;
        ElementsByTagName = XMLNodeList_GetChild(v8, 0, &v7);
        if ( ElementsByTagName >= 0 )
        {
          pwszSrc = 0;
          ElementsByTagName = XMLNode_GetTagText(v7, &pwszSrc);
          if ( ElementsByTagName >= 0 )
          {
            v11 = GUID_NULL;
            memset_0(v12, 0, 0x4Eu);
            StringCchPrintfW(v12, 0x27u, L"{%s}", pwszSrc);
            if ( OEGUIDFromStringW(v12, &v11) )
            {
              SHUnicodeToAnsi(pwszSrc, a2, 39);
              ElementsByTagName = 0;
            }
            else
            {
              ElementsByTagName = -2147467259;
            }
            SysFreeString((BSTR)pwszSrc);
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
0x1800c5de4  mov     [rsp-8+arg_10], rbx
0x1800c5de9  mov     [rsp-8+arg_18], rdi
0x1800c5dee  push    rbp
0x1800c5def  lea     rbp, [rsp-57h]
0x1800c5df4  sub     rsp, 0C0h
0x1800c5dfb  mov     rax, cs:__security_cookie
0x1800c5e02  xor     rax, rsp
0x1800c5e05  mov     [rbp+57h+var_10], rax
0x1800c5e09  mov     rdi, rdx
0x1800c5e0c  test    rcx, rcx
0x1800c5e0f  jz      loc_1800C5F69
0x1800c5e15  test    rdx, rdx
0x1800c5e18  jz      loc_1800C5F69
0x1800c5e1e  lea     rdx, [rbp+57h+var_80]
0x1800c5e22  mov     [rbp+57h+var_80], 0
0x1800c5e2a  call    cs:__imp_XMLDOMFromBStr
0x1800c5e30  mov     ebx, eax
0x1800c5e32  test    eax, eax
0x1800c5e34  js      loc_1800C5F65
0x1800c5e3a  mov     rcx, [rbp+57h+var_80]
0x1800c5e3e  lea     rdx, [rbp+57h+var_88]
0x1800c5e42  mov     [rbp+57h+var_88], 0
0x1800c5e4a  mov     rax, [rcx]
0x1800c5e4d  mov     rax, [rax+168h]
0x1800c5e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5e59  mov     ebx, eax
0x1800c5e5b  cmp     eax, 1
0x1800c5e5e  jnz     short loc_1800C5E6A
0x1800c5e60  mov     ebx, 80070490h
0x1800c5e65  jmp     loc_1800C5F5C
0x1800c5e6a  test    eax, eax
0x1800c5e6c  js      loc_1800C5F5C
0x1800c5e72  mov     rcx, [rbp+57h+var_88]
0x1800c5e76  lea     r8, [rbp+57h+var_90]
0x1800c5e7a  lea     rdx, aUpdateresult; "UpdateResult"
0x1800c5e81  mov     [rbp+57h+var_90], 0
0x1800c5e89  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c5e8f  mov     ebx, eax
0x1800c5e91  test    eax, eax
0x1800c5e93  js      loc_1800C5F53
0x1800c5e99  mov     rcx, [rbp+57h+var_90]
0x1800c5e9d  lea     r8, [rbp+57h+var_98]
0x1800c5ea1  xor     edx, edx
0x1800c5ea3  mov     [rbp+57h+var_98], 0
0x1800c5eab  call    cs:__imp_XMLNodeList_GetChild
0x1800c5eb1  mov     ebx, eax
0x1800c5eb3  test    eax, eax
0x1800c5eb5  js      loc_1800C5F4A
0x1800c5ebb  mov     rcx, [rbp+57h+var_98]
0x1800c5ebf  lea     rdx, [rbp+57h+pwszSrc]
0x1800c5ec3  mov     [rbp+57h+pwszSrc], 0
0x1800c5ecb  call    cs:__imp_XMLNode_GetTagText
0x1800c5ed1  mov     ebx, eax
0x1800c5ed3  test    eax, eax
0x1800c5ed5  js      short loc_1800C5F41
0x1800c5ed7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800c5ede  xor     edx, edx; Val
0x1800c5ee0  lea     rcx, [rbp+57h+var_60]; void *
0x1800c5ee4  movdqu  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x1800c5ee9  lea     r8d, [rdx+4Eh]; Size
0x1800c5eed  call    memset_0
0x1800c5ef2  mov     r9, [rbp+57h+pwszSrc]
0x1800c5ef6  lea     r8, aS_5; "{%s}"
0x1800c5efd  mov     ebx, 27h ; '''
0x1800c5f02  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800c5f06  mov     edx, ebx; unsigned __int64
0x1800c5f08  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c5f0d  lea     rdx, [rbp+57h+var_78]; struct _GUID *
0x1800c5f11  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800c5f15  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x1800c5f1a  test    eax, eax
0x1800c5f1c  jz      short loc_1800C5F32
0x1800c5f1e  mov     rcx, [rbp+57h+pwszSrc]; pwszSrc
0x1800c5f22  mov     r8d, ebx; cchBuf
0x1800c5f25  mov     rdx, rdi; pszDst
0x1800c5f28  call    cs:__imp_SHUnicodeToAnsi
0x1800c5f2e  xor     ebx, ebx
0x1800c5f30  jmp     short loc_1800C5F37
0x1800c5f32  mov     ebx, 80004005h
0x1800c5f37  mov     rcx, [rbp+57h+pwszSrc]; bstrString
0x1800c5f3b  call    cs:__imp_SysFreeString
0x1800c5f41  lea     rcx, [rbp+57h+var_98]
0x1800c5f45  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5f4a  lea     rcx, [rbp+57h+var_90]
0x1800c5f4e  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5f53  lea     rcx, [rbp+57h+var_88]
0x1800c5f57  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5f5c  lea     rcx, [rbp+57h+var_80]
0x1800c5f60  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5f65  mov     eax, ebx
0x1800c5f67  jmp     short loc_1800C5F6E
0x1800c5f69  mov     eax, 80070057h
0x1800c5f6e  mov     rcx, [rbp+57h+var_10]
0x1800c5f72  xor     rcx, rsp; StackCookie
0x1800c5f75  call    __security_check_cookie
0x1800c5f7a  lea     r11, [rsp+0C0h+var_s0]
0x1800c5f82  mov     rbx, [r11+20h]
0x1800c5f86  mov     rdi, [r11+28h]
0x1800c5f8a  mov     rsp, r11
0x1800c5f8d  pop     rbp
0x1800c5f8e  retn
```
