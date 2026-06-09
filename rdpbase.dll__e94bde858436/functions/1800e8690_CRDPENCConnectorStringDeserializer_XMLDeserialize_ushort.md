# CRDPENCConnectorStringDeserializer::XMLDeserialize(ushort *)

- ea: `0x1800e8690`
- end: `0x1800e8a48`
- name: `?XMLDeserialize@CRDPENCConnectorStringDeserializer@@QEAAJPEAG@Z`
- size: `952`
- prototype: `int(CRDPENCConnectorStringDeserializer *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800eb0e0`
- `0x1801292ac`

## callees

- `0x1800018a4`
- `0x180019a80`
- `0x180046a84`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800e8690`
- `0x18015f52c`
- `0x18015fbac`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e86e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e86e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e8888`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e8888`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e89ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8a0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e89ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8a0d`

## string_xrefs

- `0x1800e8725`: `Failed to create the XML document`
- `0x1800e879f`: `Failed to create the transport root node`
- `0x1800e8989`: `XMLDeserialize`

## pseudocode

```c
__int64 __fastcall CRDPENCConnectorStringDeserializer::XMLDeserialize(
        CRDPENCConnectorStringDeserializer *this,
        unsigned __int16 *a2)
{
  OLECHAR *v2; // rsi
  HRESULT Instance; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  struct IXMLDOMNode *v9; // rbx
  int v10; // r8d
  int v11; // r9d
  BSTR v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v16; // [rsp+50h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+Fh] BYREF
  struct IXMLDOMNode *v18; // [rsp+60h] [rbp+17h] BYREF
  struct IXMLDOMNode *ppv; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v20; // [rsp+70h] [rbp+27h] BYREF
  const char *v21; // [rsp+78h] [rbp+2Fh] BYREF
  const char *v22; // [rsp+80h] [rbp+37h] BYREF
  unsigned int v23; // [rsp+C0h] [rbp+77h] BYREF
  int v24; // [rsp+C8h] [rbp+7Fh] BYREF

  v2 = 0;
  bstrString = 0;
  v23 = 0;
  v16 = 0;
  ppv = 0;
  v18 = 0;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = RDPENCHLPXML_AddElementFromXMLString(ppv, a2, &v18);
    if ( Instance >= 0 )
    {
      v9 = v18;
      Instance = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v18->lpVtbl->get_baseName)(v18, &bstrString);
      if ( Instance >= 0 )
      {
        if ( *bstrString != 84 || bstrString[1] )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v23 = 340;
            v20 = "XMLDeserialize";
            v24 = -2147467259;
            v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconser.cpp";
            v22 = "Expecting type T node";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)bstrString,
              (unsigned int)qword_1801BEB58,
              v10,
              v11,
              (__int64)&v22,
              (__int64)&v24,
              (__int64)&v21,
              (__int64)&v23,
              (__int64)&v20);
          }
          Instance = -2147024809;
        }
        else
        {
          Instance = RDPENCHLPXML_GetUintAttribute(v9, L"SID", &v23);
          if ( Instance >= 0 )
          {
            v12 = SysAllocString(L"L[@N!='' and (@P!='' or @U!='')]");
            v2 = v12;
            if ( v12 )
            {
              Instance = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v9->lpVtbl->selectNodes)(
                           v9,
                           v12,
                           &v16);
              if ( Instance >= 0 )
              {
                if ( v16 != *((_QWORD *)this + 1) )
                {
                  TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 8);
                  v14 = v16;
                  *((_QWORD *)this + 1) = v16;
                  if ( v14 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
                }
                *(_DWORD *)this = v23;
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v7 = 40;
                v8 = "Failed to query the nodes";
                goto LABEL_6;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids,
                  v13,
                  -2147024882);
              }
              Instance = -2147024882;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 38;
            v8 = "Failed to get the session id";
            goto LABEL_6;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 37;
        v8 = "Failed to get the base name";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 36;
      v8 = "Failed to create the transport root node";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 35;
    v8 = "Failed to create the XML document";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      Instance);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v2 )
    SysFreeString(v2);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v18);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&ppv);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v16);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800e8690  mov     [rsp-8+arg_0], rbx
0x1800e8695  mov     [rsp-8+arg_8], rsi
0x1800e869a  push    rbp
0x1800e869b  push    rdi
0x1800e869c  push    r14
0x1800e869e  lea     rbp, [rsp-47h]
0x1800e86a3  sub     rsp, 90h
0x1800e86aa  xor     esi, esi
0x1800e86ac  mov     [rbp+57h+bstrString], 0
0x1800e86b4  mov     rbx, rdx
0x1800e86b7  mov     [rbp+57h+arg_10], esi
0x1800e86ba  mov     r14, rcx
0x1800e86bd  mov     [rbp+57h+var_50], rsi
0x1800e86c1  lea     rax, [rbp+57h+var_38]
0x1800e86c5  mov     [rbp+57h+var_38], rsi
0x1800e86c9  lea     r8d, [rsi+1]; dwClsContext
0x1800e86cd  mov     [rbp+57h+var_40], rsi
0x1800e86d1  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800e86d8  mov     [rsp+0A0h+ppv], rax; ppv
0x1800e86dd  xor     edx, edx; pUnkOuter
0x1800e86df  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800e86e6  call    cs:__imp_CoCreateInstance
0x1800e86ec  mov     edi, eax
0x1800e86ee  test    eax, eax
0x1800e86f0  jns     short loc_1800E8754
0x1800e86f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e86f9  lea     rax, WPP_GLOBAL_Control
0x1800e8700  cmp     rcx, rax
0x1800e8703  jz      loc_1800E89F6
0x1800e8709  test    byte ptr [rcx+1Ch], 8
0x1800e870d  jz      loc_1800E89F6
0x1800e8713  cmp     byte ptr [rcx+19h], 2
0x1800e8717  jb      loc_1800E89F6
0x1800e871d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e8722  lea     edx, [rsi+23h]
0x1800e8725  lea     rcx, aFailedToCreate_88; "Failed to create the XML document"
0x1800e872c  mov     dword ptr [rsp+0A0h+var_78], edi
0x1800e8730  lea     r8, WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids
0x1800e8737  mov     [rsp+0A0h+ppv], rcx
0x1800e873c  mov     r9d, eax
0x1800e873f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8746  mov     rcx, [rcx+10h]
0x1800e874a  call    WPP_SF_DsD
0x1800e874f  jmp     loc_1800E89F6
0x1800e8754  mov     rcx, [rbp+57h+var_38]; struct IXMLDOMNode *
0x1800e8758  lea     r8, [rbp+57h+var_40]; struct IXMLDOMNode **
0x1800e875c  mov     rdx, rbx; unsigned __int16 *
0x1800e875f  call    ?RDPENCHLPXML_AddElementFromXMLString@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAU1@@Z; RDPENCHLPXML_AddElementFromXMLString(IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x1800e8764  mov     edi, eax
0x1800e8766  test    eax, eax
0x1800e8768  jns     short loc_1800E87A8
0x1800e876a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8771  lea     rax, WPP_GLOBAL_Control
0x1800e8778  cmp     rcx, rax
0x1800e877b  jz      loc_1800E89F6
0x1800e8781  test    byte ptr [rcx+1Ch], 8
0x1800e8785  jz      loc_1800E89F6
0x1800e878b  cmp     byte ptr [rcx+19h], 2
0x1800e878f  jb      loc_1800E89F6
0x1800e8795  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e879a  mov     edx, 24h ; '$'
0x1800e879f  lea     rcx, aFailedToCreate_92; "Failed to create the transport root nod"...
0x1800e87a6  jmp     short loc_1800E872C
0x1800e87a8  mov     rbx, [rbp+57h+var_40]
0x1800e87ac  lea     rdx, [rbp+57h+bstrString]
0x1800e87b0  mov     rcx, rbx
0x1800e87b3  mov     rax, [rbx]
0x1800e87b6  mov     rax, [rax+148h]
0x1800e87bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e87c2  mov     edi, eax
0x1800e87c4  test    eax, eax
0x1800e87c6  jns     short loc_1800E8809
0x1800e87c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e87cf  lea     rax, WPP_GLOBAL_Control
0x1800e87d6  cmp     rcx, rax
0x1800e87d9  jz      loc_1800E89F6
0x1800e87df  test    byte ptr [rcx+1Ch], 8
0x1800e87e3  jz      loc_1800E89F6
0x1800e87e9  cmp     byte ptr [rcx+19h], 2
0x1800e87ed  jb      loc_1800E89F6
0x1800e87f3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e87f8  mov     edx, 25h ; '%'
0x1800e87fd  lea     rcx, aFailedToGetThe_13; "Failed to get the base name"
0x1800e8804  jmp     loc_1800E872C
0x1800e8809  mov     rcx, [rbp+57h+bstrString]
0x1800e880d  mov     eax, 54h ; 'T'
0x1800e8812  cmp     ax, [rcx]
0x1800e8815  jnz     loc_1800E897E
0x1800e881b  xor     eax, eax
0x1800e881d  cmp     ax, [rcx+2]
0x1800e8821  jnz     loc_1800E897E
0x1800e8827  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x1800e882b  mov     rcx, rbx; struct IXMLDOMNode *
0x1800e882e  lea     rdx, aSid; "SID"
0x1800e8835  call    ?RDPENCHLPXML_GetUintAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAI@Z; RDPENCHLPXML_GetUintAttribute(IXMLDOMNode *,ushort const *,uint *)
0x1800e883a  mov     edi, eax
0x1800e883c  test    eax, eax
0x1800e883e  jns     short loc_1800E8881
0x1800e8840  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8847  lea     rax, WPP_GLOBAL_Control
0x1800e884e  cmp     rcx, rax
0x1800e8851  jz      loc_1800E89F6
0x1800e8857  test    byte ptr [rcx+1Ch], 8
0x1800e885b  jz      loc_1800E89F6
0x1800e8861  cmp     byte ptr [rcx+19h], 2
0x1800e8865  jb      loc_1800E89F6
0x1800e886b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e8870  mov     edx, 26h ; '&'
0x1800e8875  lea     rcx, aFailedToGetThe_33; "Failed to get the session id"
0x1800e887c  jmp     loc_1800E872C
0x1800e8881  lea     rcx, aLNAndPOrU; "L[@N!='' and (@P!='' or @U!='')]"
0x1800e8888  call    cs:__imp_SysAllocString
0x1800e888e  mov     rsi, rax
0x1800e8891  test    rax, rax
0x1800e8894  jnz     short loc_1800E88E9
0x1800e8896  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e889d  lea     rax, WPP_GLOBAL_Control
0x1800e88a4  cmp     rcx, rax
0x1800e88a7  jz      short loc_1800E88DF
0x1800e88a9  test    byte ptr [rcx+1Ch], 8
0x1800e88ad  jz      short loc_1800E88DF
0x1800e88af  cmp     byte ptr [rcx+19h], 2
0x1800e88b3  jb      short loc_1800E88DF
0x1800e88b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e88ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e88c1  lea     edx, [rsi+27h]
0x1800e88c4  mov     r9d, eax
0x1800e88c7  mov     dword ptr [rsp+0A0h+ppv], 8007000Eh
0x1800e88cf  lea     r8, WPP_c63511fa6e173da0847aa5c8f83f7746_Traceguids
0x1800e88d6  mov     rcx, [rcx+10h]
0x1800e88da  call    WPP_SF_Dd
0x1800e88df  mov     edi, 8007000Eh
0x1800e88e4  jmp     loc_1800E89F6
0x1800e88e9  mov     rax, [rbx]
0x1800e88ec  lea     r8, [rbp+57h+var_50]
0x1800e88f0  mov     rdx, rsi
0x1800e88f3  mov     rcx, rbx
0x1800e88f6  mov     rax, [rax+120h]
0x1800e88fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8902  mov     edi, eax
0x1800e8904  test    eax, eax
0x1800e8906  jns     short loc_1800E8949
0x1800e8908  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e890f  lea     rax, WPP_GLOBAL_Control
0x1800e8916  cmp     rcx, rax
0x1800e8919  jz      loc_1800E89F6
0x1800e891f  test    byte ptr [rcx+1Ch], 8
0x1800e8923  jz      loc_1800E89F6
0x1800e8929  cmp     byte ptr [rcx+19h], 2
0x1800e892d  jb      loc_1800E89F6
0x1800e8933  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e8938  mov     edx, 28h ; '('
0x1800e893d  lea     rcx, aFailedToQueryT_5; "Failed to query the nodes"
0x1800e8944  jmp     loc_1800E872C
0x1800e8949  lea     rbx, [r14+8]
0x1800e894d  mov     rax, [rbx]
0x1800e8950  cmp     [rbp+57h+var_50], rax
0x1800e8954  jz      short loc_1800E8976
0x1800e8956  mov     rcx, rbx; void *
0x1800e8959  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800e895e  mov     rcx, [rbp+57h+var_50]
0x1800e8962  mov     [rbx], rcx
0x1800e8965  test    rcx, rcx
0x1800e8968  jz      short loc_1800E8976
0x1800e896a  mov     rax, [rcx]
0x1800e896d  mov     rax, [rax+8]
0x1800e8971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8976  mov     eax, [rbp+57h+arg_10]
0x1800e8979  mov     [r14], eax
0x1800e897c  jmp     short loc_1800E89F6
0x1800e897e  mov     eax, cs:CallbackContext
0x1800e8984  cmp     eax, 2
0x1800e8987  jbe     short loc_1800E89F1
0x1800e8989  lea     rax, aXmldeserialize_1; "XMLDeserialize"
0x1800e8990  mov     [rbp+57h+arg_10], 154h
0x1800e8997  mov     [rbp+57h+var_30], rax
0x1800e899b  lea     rdx, qword_1801BEB58
0x1800e89a2  lea     rax, aOnecoreTermsrv_58; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800e89a9  mov     [rbp+57h+arg_18], 80004005h
0x1800e89b0  mov     [rbp+57h+var_28], rax
0x1800e89b4  lea     rax, aExpectingTypeT; "Expecting type T node"
0x1800e89bb  mov     [rbp+57h+var_20], rax
0x1800e89bf  lea     rax, [rbp+57h+var_30]
0x1800e89c3  mov     [rsp+0A0h+var_60], rax
0x1800e89c8  lea     rax, [rbp+57h+arg_10]
0x1800e89cc  mov     [rsp+0A0h+var_68], rax
0x1800e89d1  lea     rax, [rbp+57h+var_28]
0x1800e89d5  mov     [rsp+0A0h+var_70], rax
0x1800e89da  lea     rax, [rbp+57h+arg_18]
0x1800e89de  mov     [rsp+0A0h+var_78], rax
0x1800e89e3  lea     rax, [rbp+57h+var_20]
0x1800e89e7  mov     [rsp+0A0h+ppv], rax
0x1800e89ec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800e89f1  mov     edi, 80070057h
0x1800e89f6  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800e89fa  test    rcx, rcx
0x1800e89fd  jz      short loc_1800E8A05
0x1800e89ff  call    cs:__imp_SysFreeString
0x1800e8a05  test    rsi, rsi
0x1800e8a08  jz      short loc_1800E8A13
0x1800e8a0a  mov     rcx, rsi; bstrString
0x1800e8a0d  call    cs:__imp_SysFreeString
0x1800e8a13  lea     rcx, [rbp+57h+var_40]; void *
0x1800e8a17  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800e8a1c  lea     rcx, [rbp+57h+var_38]; void *
0x1800e8a20  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800e8a25  lea     rcx, [rbp+57h+var_50]; void *
0x1800e8a29  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800e8a2e  lea     r11, [rsp+0A0h+var_10]
0x1800e8a36  mov     eax, edi
0x1800e8a38  mov     rbx, [r11+20h]
0x1800e8a3c  mov     rsi, [r11+28h]
0x1800e8a40  mov     rsp, r11
0x1800e8a43  pop     r14
0x1800e8a45  pop     rdi
0x1800e8a46  pop     rbp
0x1800e8a47  retn
```
