# CommunityXML_VerifyUpdateMsgRatingResponse(ushort *,long *)

- ea: `0x1800c73d4`
- end: `0x1800c74f6`
- name: `?CommunityXML_VerifyUpdateMsgRatingResponse@@YAJPEAGPEAJ@Z`
- size: `290`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b0f5c`

## callees

- `0x180002098`
- `0x1800c73d4`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c7406`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c7406`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c7465`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c7465`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c7483`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c7483`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c749f`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c749f`
- `SHLWAPI!StrToIntW` at `0x1800c74af`
- `SHLWAPI!StrToIntW` at `0x1800c74af`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c74bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c74bb`

## string_xrefs

- `0x1800c7456`: `UpdateMsgRatingResult`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyUpdateMsgRatingResponse(unsigned __int16 *a1, int *a2)
{
  int ElementsByTagName; // ebx
  int v4; // eax
  int v5; // eax
  OLECHAR *v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  __int64 v9; // [rsp+28h] [rbp-8h] BYREF
  PCWSTR pszSrc; // [rsp+50h] [rbp+20h] BYREF
  __int64 v11; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  v9 = 0;
  ElementsByTagName = XMLDOMFromBStr(a1, &v9);
  if ( ElementsByTagName >= 0 )
  {
    v8 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 360LL))(v9, &v8);
    ElementsByTagName = v4;
    if ( v4 == 1 )
    {
      ElementsByTagName = -2147023728;
    }
    else if ( v4 >= 0 )
    {
      v12 = 0;
      ElementsByTagName = XMLElem_GetElementsByTagName(v8, L"UpdateMsgRatingResult", &v12);
      if ( ElementsByTagName >= 0 )
      {
        v11 = 0;
        ElementsByTagName = XMLNodeList_GetChild(v12, 0, &v11);
        if ( ElementsByTagName >= 0 )
        {
          pszSrc = 0;
          ElementsByTagName = XMLNode_GetTagText(v11, &pszSrc);
          if ( ElementsByTagName >= 0 )
          {
            v5 = StrToIntW(pszSrc);
            v6 = (OLECHAR *)pszSrc;
            *a2 = v5;
            SysFreeString(v6);
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v11);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v12);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v8);
    }
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v9);
  }
  return (unsigned int)ElementsByTagName;
}

```

## disassembly

```asm
0x1800c73d4  push    rbp
0x1800c73d6  push    rbx
0x1800c73d7  push    rdi
0x1800c73d8  mov     rbp, rsp
0x1800c73db  sub     rsp, 30h
0x1800c73df  mov     rdi, rdx
0x1800c73e2  test    rcx, rcx
0x1800c73e5  jz      loc_1800C74E9
0x1800c73eb  test    rdx, rdx
0x1800c73ee  jz      loc_1800C74E9
0x1800c73f4  mov     dword ptr [rdx], 0
0x1800c73fa  lea     rdx, [rbp+var_8]
0x1800c73fe  mov     [rbp+var_8], 0
0x1800c7406  call    cs:__imp_XMLDOMFromBStr
0x1800c740c  mov     ebx, eax
0x1800c740e  test    eax, eax
0x1800c7410  js      loc_1800C74E5
0x1800c7416  mov     rcx, [rbp+var_8]
0x1800c741a  lea     rdx, [rbp+var_10]
0x1800c741e  mov     [rbp+var_10], 0
0x1800c7426  mov     rax, [rcx]
0x1800c7429  mov     rax, [rax+168h]
0x1800c7430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7435  mov     ebx, eax
0x1800c7437  cmp     eax, 1
0x1800c743a  jnz     short loc_1800C7446
0x1800c743c  mov     ebx, 80070490h
0x1800c7441  jmp     loc_1800C74DC
0x1800c7446  test    eax, eax
0x1800c7448  js      loc_1800C74DC
0x1800c744e  mov     rcx, [rbp+var_10]
0x1800c7452  lea     r8, [rbp+arg_18]
0x1800c7456  lea     rdx, aUpdatemsgratin_1; "UpdateMsgRatingResult"
0x1800c745d  mov     [rbp+arg_18], 0
0x1800c7465  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c746b  mov     ebx, eax
0x1800c746d  test    eax, eax
0x1800c746f  js      short loc_1800C74D3
0x1800c7471  mov     rcx, [rbp+arg_18]
0x1800c7475  lea     r8, [rbp+arg_10]
0x1800c7479  xor     edx, edx
0x1800c747b  mov     [rbp+arg_10], 0
0x1800c7483  call    cs:__imp_XMLNodeList_GetChild
0x1800c7489  mov     ebx, eax
0x1800c748b  test    eax, eax
0x1800c748d  js      short loc_1800C74CA
0x1800c748f  mov     rcx, [rbp+arg_10]
0x1800c7493  lea     rdx, [rbp+pszSrc]
0x1800c7497  mov     [rbp+pszSrc], 0
0x1800c749f  call    cs:__imp_XMLNode_GetTagText
0x1800c74a5  mov     ebx, eax
0x1800c74a7  test    eax, eax
0x1800c74a9  js      short loc_1800C74C1
0x1800c74ab  mov     rcx, [rbp+pszSrc]; pszSrc
0x1800c74af  call    cs:__imp_StrToIntW
0x1800c74b5  mov     rcx, [rbp+pszSrc]; bstrString
0x1800c74b9  mov     [rdi], eax
0x1800c74bb  call    cs:__imp_SysFreeString
0x1800c74c1  lea     rcx, [rbp+arg_10]
0x1800c74c5  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c74ca  lea     rcx, [rbp+arg_18]
0x1800c74ce  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c74d3  lea     rcx, [rbp+var_10]
0x1800c74d7  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c74dc  lea     rcx, [rbp+var_8]
0x1800c74e0  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c74e5  mov     eax, ebx
0x1800c74e7  jmp     short loc_1800C74EE
0x1800c74e9  mov     eax, 80070057h
0x1800c74ee  add     rsp, 30h
0x1800c74f2  pop     rdi
0x1800c74f3  pop     rbx
0x1800c74f4  pop     rbp
0x1800c74f5  retn
```
