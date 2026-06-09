# CommunityXML_VerifyUpdateMsgAttributeResponse(ushort *,long *)

- ea: `0x1800c72ac`
- end: `0x1800c73ce`
- name: `?CommunityXML_VerifyUpdateMsgAttributeResponse@@YAJPEAGPEAJ@Z`
- size: `290`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b0f5c`

## callees

- `0x180002098`
- `0x1800c72ac`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c72de`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c72de`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c733d`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c733d`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c735b`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c735b`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c7377`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c7377`
- `SHLWAPI!StrToIntW` at `0x1800c7387`
- `SHLWAPI!StrToIntW` at `0x1800c7387`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7393`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7393`

## string_xrefs

- `0x1800c732e`: `UpdateMsgAttributeResult`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyUpdateMsgAttributeResponse(unsigned __int16 *a1, int *a2)
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
      ElementsByTagName = XMLElem_GetElementsByTagName(v8, L"UpdateMsgAttributeResult", &v12);
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
0x1800c72ac  push    rbp
0x1800c72ae  push    rbx
0x1800c72af  push    rdi
0x1800c72b0  mov     rbp, rsp
0x1800c72b3  sub     rsp, 30h
0x1800c72b7  mov     rdi, rdx
0x1800c72ba  test    rcx, rcx
0x1800c72bd  jz      loc_1800C73C1
0x1800c72c3  test    rdx, rdx
0x1800c72c6  jz      loc_1800C73C1
0x1800c72cc  mov     dword ptr [rdx], 0
0x1800c72d2  lea     rdx, [rbp+var_8]
0x1800c72d6  mov     [rbp+var_8], 0
0x1800c72de  call    cs:__imp_XMLDOMFromBStr
0x1800c72e4  mov     ebx, eax
0x1800c72e6  test    eax, eax
0x1800c72e8  js      loc_1800C73BD
0x1800c72ee  mov     rcx, [rbp+var_8]
0x1800c72f2  lea     rdx, [rbp+var_10]
0x1800c72f6  mov     [rbp+var_10], 0
0x1800c72fe  mov     rax, [rcx]
0x1800c7301  mov     rax, [rax+168h]
0x1800c7308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c730d  mov     ebx, eax
0x1800c730f  cmp     eax, 1
0x1800c7312  jnz     short loc_1800C731E
0x1800c7314  mov     ebx, 80070490h
0x1800c7319  jmp     loc_1800C73B4
0x1800c731e  test    eax, eax
0x1800c7320  js      loc_1800C73B4
0x1800c7326  mov     rcx, [rbp+var_10]
0x1800c732a  lea     r8, [rbp+arg_18]
0x1800c732e  lea     rdx, aUpdatemsgattri; "UpdateMsgAttributeResult"
0x1800c7335  mov     [rbp+arg_18], 0
0x1800c733d  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c7343  mov     ebx, eax
0x1800c7345  test    eax, eax
0x1800c7347  js      short loc_1800C73AB
0x1800c7349  mov     rcx, [rbp+arg_18]
0x1800c734d  lea     r8, [rbp+arg_10]
0x1800c7351  xor     edx, edx
0x1800c7353  mov     [rbp+arg_10], 0
0x1800c735b  call    cs:__imp_XMLNodeList_GetChild
0x1800c7361  mov     ebx, eax
0x1800c7363  test    eax, eax
0x1800c7365  js      short loc_1800C73A2
0x1800c7367  mov     rcx, [rbp+arg_10]
0x1800c736b  lea     rdx, [rbp+pszSrc]
0x1800c736f  mov     [rbp+pszSrc], 0
0x1800c7377  call    cs:__imp_XMLNode_GetTagText
0x1800c737d  mov     ebx, eax
0x1800c737f  test    eax, eax
0x1800c7381  js      short loc_1800C7399
0x1800c7383  mov     rcx, [rbp+pszSrc]; pszSrc
0x1800c7387  call    cs:__imp_StrToIntW
0x1800c738d  mov     rcx, [rbp+pszSrc]; bstrString
0x1800c7391  mov     [rdi], eax
0x1800c7393  call    cs:__imp_SysFreeString
0x1800c7399  lea     rcx, [rbp+arg_10]
0x1800c739d  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c73a2  lea     rcx, [rbp+arg_18]
0x1800c73a6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c73ab  lea     rcx, [rbp+var_10]
0x1800c73af  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c73b4  lea     rcx, [rbp+var_8]
0x1800c73b8  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c73bd  mov     eax, ebx
0x1800c73bf  jmp     short loc_1800C73C6
0x1800c73c1  mov     eax, 80070057h
0x1800c73c6  add     rsp, 30h
0x1800c73ca  pop     rdi
0x1800c73cb  pop     rbx
0x1800c73cc  pop     rbp
0x1800c73cd  retn
```
