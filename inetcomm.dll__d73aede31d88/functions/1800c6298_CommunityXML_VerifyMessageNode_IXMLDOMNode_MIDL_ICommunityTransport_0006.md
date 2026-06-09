# CommunityXML_VerifyMessageNode(IXMLDOMNode *,__MIDL_ICommunityTransport_0006 *)

- ea: `0x1800c6298`
- end: `0x1800c660b`
- name: `?CommunityXML_VerifyMessageNode@@YAJPEAUIXMLDOMNode@@PEAU__MIDL_ICommunityTransport_0006@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct __MIDL_ICommunityTransport_0006 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c6614`

## callees

- `0x1800055bc`
- `0x18000910c`
- `0x180024b14`
- `0x180026290`
- `0x1800c6298`
- `0x1800c94e4`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c62ea`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c638f`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6453`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6492`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c64ed`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6588`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c62ea`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c638f`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6453`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6492`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c64ed`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6588`
- `SHLWAPI!StrToIntW` at `0x1800c64a6`
- `SHLWAPI!StrToIntW` at `0x1800c64a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c636b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6405`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6476`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c64d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6568`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c65a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c636b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6405`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6476`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c64d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6568`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c65a7`

## string_xrefs

- `0x1800c62e3`: `ThreadID`
- `0x1800c6440`: `ThreadAttributeID`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyMessageNode(struct IXMLDOMNode *a1, struct _GUID *a2)
{
  int AttributeValue; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  const wchar_t *v9; // rdx
  int CategoryType; // eax
  OLECHAR *v11; // rcx
  int v12; // ecx
  int v13; // eax
  int v14; // eax
  int PosterType; // eax
  OLECHAR *v16; // rcx
  __int64 v17; // rax
  BSTR v19; // [rsp+20h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-31h] BYREF
  unsigned __int16 v21[40]; // [rsp+30h] [rbp-29h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  bstrString = 0;
  AttributeValue = XMLNode_GetAttributeValue(a1, L"ThreadID", &bstrString);
  if ( AttributeValue >= 0 )
  {
    memset_0(v21, 0, 0x4Eu);
    if ( bstrString )
    {
      if ( *bstrString == 123 )
        v5 = StringCchCopyW(v21, 0x27u, bstrString);
      else
        v5 = StringCchPrintfW(v21, 0x27u, L"{%s}", bstrString);
      AttributeValue = v5;
      if ( v5 >= 0 && !OEGUIDFromStringW(v21, a2 + 19) )
        AttributeValue = -2147467259;
    }
    else
    {
      AttributeValue = -2147024809;
    }
    SysFreeString(bstrString);
    if ( AttributeValue >= 0 )
    {
      v19 = 0;
      AttributeValue = XMLNode_GetAttributeValue(a1, L"MsgID", &v19);
      if ( AttributeValue >= 0 )
      {
        memset_0(v21, 0, 0x4Eu);
        if ( v19 )
        {
          if ( *v19 == 123 )
            v6 = StringCchCopyW(v21, 0x27u, v19);
          else
            v6 = StringCchPrintfW(v21, 0x27u, L"{%s}", v19);
          AttributeValue = v6;
          if ( v6 >= 0 && !OEGUIDFromStringW(v21, a2 + 18) )
            AttributeValue = -2147467259;
        }
        else
        {
          AttributeValue = -2147024809;
        }
        SysFreeString(v19);
        if ( AttributeValue >= 0 )
        {
          v7 = *(_QWORD *)&a2[19].Data1;
          v19 = 0;
          v8 = v7 - *(_QWORD *)&a2[18].Data1;
          if ( !v8 )
            v8 = *(_QWORD *)a2[19].Data4 - *(_QWORD *)a2[18].Data4;
          v9 = L"ThreadAttributeID";
          if ( v8 )
            v9 = L"MsgAttribute";
          AttributeValue = XMLNode_GetAttributeValue(a1, v9, &v19);
          if ( AttributeValue >= 0 )
          {
            CategoryType = _GetCategoryType(v19);
            v11 = v19;
            *(_DWORD *)&a2[16].Data4[4] = CategoryType;
            SysFreeString(v11);
            v19 = 0;
            AttributeValue = XMLNode_GetAttributeValue(a1, L"HelpfulMsg", &v19);
            if ( AttributeValue >= 0 )
            {
              v12 = StrToIntW(v19);
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
              SysFreeString(v19);
              v19 = 0;
              AttributeValue = XMLNode_GetAttributeValue(a1, L"ContribID", &v19);
              if ( AttributeValue >= 0 )
              {
                memset_0(v21, 0, 0x4Eu);
                if ( v19 )
                {
                  if ( *v19 == 123 )
                    v14 = StringCchCopyW(v21, 0x27u, v19);
                  else
                    v14 = StringCchPrintfW(v21, 0x27u, L"{%s}", v19);
                  AttributeValue = v14;
                  if ( v14 >= 0 && !OEGUIDFromStringW(v21, a2 + 17) )
                    AttributeValue = -2147467259;
                }
                else
                {
                  AttributeValue = -2147024809;
                }
                SysFreeString(v19);
                if ( AttributeValue >= 0 )
                {
                  v19 = 0;
                  AttributeValue = XMLNode_GetAttributeValue(a1, L"ContribRatingTaxManID", &v19);
                  if ( AttributeValue >= 0 )
                  {
                    PosterType = _GetPosterType(v19);
                    v16 = v19;
                    *(_DWORD *)a2[16].Data4 = PosterType;
                    SysFreeString(v16);
                    v17 = *(_QWORD *)&a2[17].Data1 - COMMUNITYPOSTER_UNAUTHENTICATED;
                    if ( !v17 )
                      v17 = *(_QWORD *)a2[17].Data4 - 0x52C4B63807728480LL;
                    BYTE1(a2[20].Data1) = 1;
                    LOBYTE(a2[20].Data1) = v17 != 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)AttributeValue;
}

```

## disassembly

```asm
0x1800c6298  mov     [rsp-8+arg_10], rbx
0x1800c629d  push    rbp
0x1800c629e  push    rdi
0x1800c629f  push    r12
0x1800c62a1  push    r13
0x1800c62a3  push    r14
0x1800c62a5  lea     rbp, [rsp-37h]
0x1800c62aa  sub     rsp, 90h
0x1800c62b1  mov     rax, cs:__security_cookie
0x1800c62b8  xor     rax, rsp
0x1800c62bb  mov     [rbp+57h+var_30], rax
0x1800c62bf  mov     rdi, rdx
0x1800c62c2  mov     r14, rcx
0x1800c62c5  test    rcx, rcx
0x1800c62c8  jz      loc_1800C65E2
0x1800c62ce  test    rdx, rdx
0x1800c62d1  jz      loc_1800C65E2
0x1800c62d7  lea     r8, [rbp+57h+bstrString]
0x1800c62db  mov     [rbp+57h+bstrString], 0
0x1800c62e3  lea     rdx, aThreadid; "ThreadID"
0x1800c62ea  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c62f0  mov     ebx, eax
0x1800c62f2  test    eax, eax
0x1800c62f4  js      loc_1800C65DE
0x1800c62fa  xor     edx, edx; Val
0x1800c62fc  lea     rcx, [rbp+57h+var_80]; void *
0x1800c6300  lea     r8d, [rdx+4Eh]; Size
0x1800c6304  call    memset_0
0x1800c6309  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x1800c630d  mov     r12d, 7Bh ; '{'
0x1800c6313  lea     r13d, [r12-54h]
0x1800c6318  test    r8, r8
0x1800c631b  jz      short loc_1800C6362
0x1800c631d  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800c6321  mov     edx, r13d; unsigned __int64
0x1800c6324  cmp     r12w, [r8]
0x1800c6328  jz      short loc_1800C633B
0x1800c632a  mov     r9, r8
0x1800c632d  lea     r8, aS_5; "{%s}"
0x1800c6334  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c6339  jmp     short loc_1800C6340
0x1800c633b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c6340  mov     ebx, eax
0x1800c6342  test    eax, eax
0x1800c6344  js      short loc_1800C6367
0x1800c6346  lea     rdx, [rdi+130h]; struct _GUID *
0x1800c634d  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800c6351  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x1800c6356  test    eax, eax
0x1800c6358  mov     eax, 80004005h
0x1800c635d  cmovz   ebx, eax
0x1800c6360  jmp     short loc_1800C6367
0x1800c6362  mov     ebx, 80070057h
0x1800c6367  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800c636b  call    cs:__imp_SysFreeString
0x1800c6371  test    ebx, ebx
0x1800c6373  js      loc_1800C65DE
0x1800c6379  lea     r8, [rbp+57h+var_90]
0x1800c637d  mov     [rbp+57h+var_90], 0
0x1800c6385  lea     rdx, aMsgid; "MsgID"
0x1800c638c  mov     rcx, r14
0x1800c638f  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c6395  mov     ebx, eax
0x1800c6397  test    eax, eax
0x1800c6399  js      loc_1800C65DE
0x1800c639f  xor     edx, edx; Val
0x1800c63a1  lea     rcx, [rbp+57h+var_80]; void *
0x1800c63a5  lea     r8d, [rdx+4Eh]; Size
0x1800c63a9  call    memset_0
0x1800c63ae  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1800c63b2  test    r8, r8
0x1800c63b5  jz      short loc_1800C63FC
0x1800c63b7  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800c63bb  mov     rdx, r13; unsigned __int64
0x1800c63be  cmp     r12w, [r8]
0x1800c63c2  jz      short loc_1800C63D5
0x1800c63c4  mov     r9, r8
0x1800c63c7  lea     r8, aS_5; "{%s}"
0x1800c63ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c63d3  jmp     short loc_1800C63DA
0x1800c63d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c63da  mov     ebx, eax
0x1800c63dc  test    eax, eax
0x1800c63de  js      short loc_1800C6401
0x1800c63e0  lea     rdx, [rdi+120h]; struct _GUID *
0x1800c63e7  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800c63eb  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x1800c63f0  test    eax, eax
0x1800c63f2  mov     eax, 80004005h
0x1800c63f7  cmovz   ebx, eax
0x1800c63fa  jmp     short loc_1800C6401
0x1800c63fc  mov     ebx, 80070057h
0x1800c6401  mov     rcx, [rbp+57h+var_90]; bstrString
0x1800c6405  call    cs:__imp_SysFreeString
0x1800c640b  test    ebx, ebx
0x1800c640d  js      loc_1800C65DE
0x1800c6413  mov     rax, [rdi+130h]
0x1800c641a  mov     [rbp+57h+var_90], 0
0x1800c6422  sub     rax, [rdi+120h]
0x1800c6429  jnz     short loc_1800C6439
0x1800c642b  mov     rax, [rdi+138h]
0x1800c6432  sub     rax, [rdi+128h]
0x1800c6439  lea     r8, [rbp+57h+var_90]
0x1800c643d  mov     rcx, r14
0x1800c6440  lea     rdx, aThreadattribut; "ThreadAttributeID"
0x1800c6447  test    rax, rax
0x1800c644a  jz      short loc_1800C6453
0x1800c644c  lea     rdx, aMsgattribute; "MsgAttribute"
0x1800c6453  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c6459  mov     ebx, eax
0x1800c645b  test    eax, eax
0x1800c645d  js      loc_1800C65DE
0x1800c6463  mov     rcx, [rbp+57h+var_90]
0x1800c6467  call    ?_GetCategoryType@@YA?AW4__MIDL_ICommunityTransport_0002@@PEAG@Z; _GetCategoryType(ushort *)
0x1800c646c  mov     rcx, [rbp+57h+var_90]; bstrString
0x1800c6470  mov     [rdi+10Ch], eax
0x1800c6476  call    cs:__imp_SysFreeString
0x1800c647c  lea     r8, [rbp+57h+var_90]
0x1800c6480  mov     [rbp+57h+var_90], 0
0x1800c6488  lea     rdx, aHelpfulmsg; "HelpfulMsg"
0x1800c648f  mov     rcx, r14
0x1800c6492  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c6498  mov     ebx, eax
0x1800c649a  test    eax, eax
0x1800c649c  js      loc_1800C65DE
0x1800c64a2  mov     rcx, [rbp+57h+var_90]; pszSrc
0x1800c64a6  call    cs:__imp_StrToIntW
0x1800c64ac  mov     ecx, eax
0x1800c64ae  mov     r12d, 1
0x1800c64b4  test    eax, eax
0x1800c64b6  jle     short loc_1800C64BC
0x1800c64b8  xor     eax, eax
0x1800c64ba  jmp     short loc_1800C64C7
0x1800c64bc  test    ecx, ecx
0x1800c64be  mov     eax, 5
0x1800c64c3  cmovnz  eax, r12d
0x1800c64c7  mov     [rdi+104h], eax
0x1800c64cd  mov     rcx, [rbp+57h+var_90]; bstrString
0x1800c64d1  call    cs:__imp_SysFreeString
0x1800c64d7  lea     r8, [rbp+57h+var_90]
0x1800c64db  mov     [rbp+57h+var_90], 0
0x1800c64e3  lea     rdx, aContribid; "ContribID"
0x1800c64ea  mov     rcx, r14
0x1800c64ed  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c64f3  mov     ebx, eax
0x1800c64f5  test    eax, eax
0x1800c64f7  js      loc_1800C65DE
0x1800c64fd  xor     edx, edx; Val
0x1800c64ff  lea     rcx, [rbp+57h+var_80]; void *
0x1800c6503  lea     r8d, [rdx+4Eh]; Size
0x1800c6507  call    memset_0
0x1800c650c  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1800c6510  test    r8, r8
0x1800c6513  jz      short loc_1800C655F
0x1800c6515  mov     eax, 7Bh ; '{'
0x1800c651a  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800c651e  mov     rdx, r13; unsigned __int64
0x1800c6521  cmp     ax, [r8]
0x1800c6525  jz      short loc_1800C6538
0x1800c6527  mov     r9, r8
0x1800c652a  lea     r8, aS_5; "{%s}"
0x1800c6531  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c6536  jmp     short loc_1800C653D
0x1800c6538  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c653d  mov     ebx, eax
0x1800c653f  test    eax, eax
0x1800c6541  js      short loc_1800C6564
0x1800c6543  lea     rdx, [rdi+110h]; struct _GUID *
0x1800c654a  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800c654e  call    ?OEGUIDFromStringW@@YAHPEBGPEAU_GUID@@@Z; OEGUIDFromStringW(ushort const *,_GUID *)
0x1800c6553  test    eax, eax
0x1800c6555  mov     eax, 80004005h
0x1800c655a  cmovz   ebx, eax
0x1800c655d  jmp     short loc_1800C6564
0x1800c655f  mov     ebx, 80070057h
0x1800c6564  mov     rcx, [rbp+57h+var_90]; bstrString
0x1800c6568  call    cs:__imp_SysFreeString
0x1800c656e  test    ebx, ebx
0x1800c6570  js      short loc_1800C65DE
0x1800c6572  lea     r8, [rbp+57h+var_90]
0x1800c6576  mov     [rbp+57h+var_90], 0
0x1800c657e  lea     rdx, aContribratingt; "ContribRatingTaxManID"
0x1800c6585  mov     rcx, r14
0x1800c6588  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c658e  mov     ebx, eax
0x1800c6590  test    eax, eax
0x1800c6592  js      short loc_1800C65DE
0x1800c6594  mov     rcx, [rbp+57h+var_90]
0x1800c6598  call    ?_GetPosterType@@YA?AW4__MIDL_ICommunityTransport_0003@@PEAG@Z; _GetPosterType(ushort *)
0x1800c659d  mov     rcx, [rbp+57h+var_90]; bstrString
0x1800c65a1  mov     [rdi+108h], eax
0x1800c65a7  call    cs:__imp_SysFreeString
0x1800c65ad  mov     rax, [rdi+110h]
0x1800c65b4  sub     rax, cs:COMMUNITYPOSTER_UNAUTHENTICATED
0x1800c65bb  jnz     short loc_1800C65CB
0x1800c65bd  mov     rax, [rdi+118h]
0x1800c65c4  sub     rax, cs:qword_1800DB3A8
0x1800c65cb  test    rax, rax
0x1800c65ce  mov     [rdi+141h], r12b
0x1800c65d5  setnz   al
0x1800c65d8  mov     [rdi+140h], al
0x1800c65de  mov     eax, ebx
0x1800c65e0  jmp     short loc_1800C65E7
0x1800c65e2  mov     eax, 80070057h
0x1800c65e7  mov     rcx, [rbp+57h+var_30]
0x1800c65eb  xor     rcx, rsp; StackCookie
0x1800c65ee  call    __security_check_cookie
0x1800c65f3  mov     rbx, [rsp+0B0h+arg_10]
0x1800c65fb  add     rsp, 90h
0x1800c6602  pop     r14
0x1800c6604  pop     r13
0x1800c6606  pop     r12
0x1800c6608  pop     rdi
0x1800c6609  pop     rbp
0x1800c660a  retn
```
