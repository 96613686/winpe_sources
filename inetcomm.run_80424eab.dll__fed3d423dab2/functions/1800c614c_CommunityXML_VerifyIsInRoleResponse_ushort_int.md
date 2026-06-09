# CommunityXML_VerifyIsInRoleResponse(ushort *,int *)

- ea: `0x1800c614c`
- end: `0x1800c6291`
- name: `?CommunityXML_VerifyIsInRoleResponse@@YAJPEAGPEAH@Z`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b0f5c`

## callees

- `0x180002098`
- `0x1800c614c`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c6178`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c6178`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c61d7`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c61d7`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c61f9`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c61f9`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c6215`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c6215`
- `KERNEL32!CompareStringW` at `0x1800c6241`
- `KERNEL32!CompareStringW` at `0x1800c6241`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6256`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6256`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyIsInRoleResponse(unsigned __int16 *a1, int *a2)
{
  int ElementsByTagName; // ebx
  int v4; // eax
  __int64 v6; // [rsp+30h] [rbp-10h] BYREF
  __int64 v7; // [rsp+38h] [rbp-8h] BYREF
  PCNZWCH lpString1; // [rsp+60h] [rbp+20h] BYREF
  __int64 v9; // [rsp+70h] [rbp+30h] BYREF
  __int64 v10; // [rsp+78h] [rbp+38h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  v7 = 0;
  ElementsByTagName = XMLDOMFromBStr(a1, &v7);
  if ( ElementsByTagName >= 0 )
  {
    v6 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 360LL))(v7, &v6);
    ElementsByTagName = v4;
    if ( v4 == 1 )
    {
      ElementsByTagName = -2147023728;
    }
    else if ( v4 >= 0 )
    {
      v10 = 0;
      ElementsByTagName = XMLElem_GetElementsByTagName(v6, L"IsInRoleResult", &v10);
      if ( ElementsByTagName >= 0 )
      {
        v9 = 0;
        ElementsByTagName = XMLNodeList_GetChild(v10, 0, &v9);
        if ( ElementsByTagName >= 0 )
        {
          lpString1 = 0;
          ElementsByTagName = XMLNode_GetTagText(v9, &lpString1);
          if ( ElementsByTagName >= 0 )
          {
            if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"TRUE", -1) == 2 )
              *a2 = 1;
            SysFreeString((BSTR)lpString1);
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v9);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v6);
    }
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v7);
  }
  return (unsigned int)ElementsByTagName;
}

```

## disassembly

```asm
0x1800c614c  push    rbp
0x1800c614e  push    rbx
0x1800c614f  push    rdi
0x1800c6150  mov     rbp, rsp
0x1800c6153  sub     rsp, 40h
0x1800c6157  mov     rdi, rdx
0x1800c615a  test    rcx, rcx
0x1800c615d  jz      loc_1800C6284
0x1800c6163  test    rdx, rdx
0x1800c6166  jz      loc_1800C6284
0x1800c616c  lea     rdx, [rbp+var_8]
0x1800c6170  mov     [rbp+var_8], 0
0x1800c6178  call    cs:__imp_XMLDOMFromBStr
0x1800c617e  mov     ebx, eax
0x1800c6180  test    eax, eax
0x1800c6182  js      loc_1800C6280
0x1800c6188  mov     rcx, [rbp+var_8]
0x1800c618c  lea     rdx, [rbp+var_10]
0x1800c6190  mov     [rbp+var_10], 0
0x1800c6198  mov     rax, [rcx]
0x1800c619b  mov     rax, [rax+168h]
0x1800c61a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c61a7  mov     ebx, eax
0x1800c61a9  cmp     eax, 1
0x1800c61ac  jnz     short loc_1800C61B8
0x1800c61ae  mov     ebx, 80070490h
0x1800c61b3  jmp     loc_1800C6277
0x1800c61b8  test    eax, eax
0x1800c61ba  js      loc_1800C6277
0x1800c61c0  mov     rcx, [rbp+var_10]
0x1800c61c4  lea     r8, [rbp+arg_18]
0x1800c61c8  lea     rdx, aIsinroleresult; "IsInRoleResult"
0x1800c61cf  mov     [rbp+arg_18], 0
0x1800c61d7  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c61dd  mov     ebx, eax
0x1800c61df  test    eax, eax
0x1800c61e1  js      loc_1800C626E
0x1800c61e7  mov     rcx, [rbp+arg_18]
0x1800c61eb  lea     r8, [rbp+arg_10]
0x1800c61ef  xor     edx, edx
0x1800c61f1  mov     [rbp+arg_10], 0
0x1800c61f9  call    cs:__imp_XMLNodeList_GetChild
0x1800c61ff  mov     ebx, eax
0x1800c6201  test    eax, eax
0x1800c6203  js      short loc_1800C6265
0x1800c6205  mov     rcx, [rbp+arg_10]
0x1800c6209  lea     rdx, [rbp+lpString1]
0x1800c620d  mov     [rbp+lpString1], 0
0x1800c6215  call    cs:__imp_XMLNode_GetTagText
0x1800c621b  mov     ebx, eax
0x1800c621d  test    eax, eax
0x1800c621f  js      short loc_1800C625C
0x1800c6221  mov     r8, [rbp+lpString1]; lpString1
0x1800c6225  lea     rax, aTrue; "TRUE"
0x1800c622c  or      r9d, 0FFFFFFFFh; cchCount1
0x1800c6230  mov     [rsp+40h+cchCount2], r9d; cchCount2
0x1800c6235  mov     [rsp+40h+lpString2], rax; lpString2
0x1800c623a  lea     edx, [r9+2]; dwCmpFlags
0x1800c623e  lea     ecx, [rdx+7Eh]; Locale
0x1800c6241  call    cs:__imp_CompareStringW
0x1800c6247  cmp     eax, 2
0x1800c624a  jnz     short loc_1800C6252
0x1800c624c  mov     dword ptr [rdi], 1
0x1800c6252  mov     rcx, [rbp+lpString1]; bstrString
0x1800c6256  call    cs:__imp_SysFreeString
0x1800c625c  lea     rcx, [rbp+arg_10]
0x1800c6260  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6265  lea     rcx, [rbp+arg_18]
0x1800c6269  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c626e  lea     rcx, [rbp+var_10]
0x1800c6272  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6277  lea     rcx, [rbp+var_8]
0x1800c627b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6280  mov     eax, ebx
0x1800c6282  jmp     short loc_1800C6289
0x1800c6284  mov     eax, 80070057h
0x1800c6289  add     rsp, 40h
0x1800c628d  pop     rdi
0x1800c628e  pop     rbx
0x1800c628f  pop     rbp
0x1800c6290  retn
```
