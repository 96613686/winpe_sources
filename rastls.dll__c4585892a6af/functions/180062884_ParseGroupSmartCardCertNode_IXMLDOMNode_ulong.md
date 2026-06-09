# ParseGroupSmartCardCertNode(IXMLDOMNode *,ulong *)

- ea: `0x180062884`
- end: `0x180062a48`
- name: `?ParseGroupSmartCardCertNode@@YAKPEAUIXMLDOMNode@@PEAK@Z`
- size: `452`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cbc4`

## callees

- `0x180007d00`
- `0x180010140`
- `0x1800104b0`
- `0x18001b4b0`
- `0x180021e74`
- `0x180062884`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180062929`
- `OLEAUT32!__imp_SysFreeString` at `0x180062a03`
- `OLEAUT32!__imp_SysFreeString` at `0x180062a14`
- `OLEAUT32!__imp_SysFreeString` at `0x180062929`
- `OLEAUT32!__imp_SysFreeString` at `0x180062a03`
- `OLEAUT32!__imp_SysFreeString` at `0x180062a14`

## string_xrefs

- `0x1800628e5`: `eaptlsconnectionpropertiesv2:TLSExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ParseGroupSmartCardCertNode(struct IXMLDOMNode *a1, unsigned int *a2)
{
  OLECHAR *v4; // rbx
  int SingleNode; // eax
  unsigned int v6; // edi
  int v7; // eax
  bool v8; // bl
  const wchar_t *v9; // r9
  struct IXMLDOMNode *v11; // [rsp+20h] [rbp-10h] BYREF
  struct IXMLDOMNode *v12; // [rsp+28h] [rbp-8h] BYREF
  bool v13; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  v12 = 0;
  v11 = 0;
  v4 = 0;
  bstrString = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  SingleNode = getSingleNode(a1, L"eaptlsconnectionpropertiesv2:TLSExtensions", &v12);
  if ( !SingleNode )
  {
    v6 = 0;
    v7 = getSingleNode(v12, L"eaptlsconnectionpropertiesv2:GroupSmartCardCerts", &v11);
    if ( !v7 )
    {
      if ( (unsigned int)ReadBOOLEANFromXMLNode(v11, &v13, &bstrString) )
      {
        v4 = bstrString;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            193,
            WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
            bstrString);
        v6 = 13;
      }
      else
      {
        v8 = v13;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v9 = L"TRUE";
          if ( !v13 )
            v9 = L"FALSE";
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v9);
        }
        if ( !v8 )
          *a2 |= 0x400u;
        SysFreeString(bstrString);
        v4 = 0;
      }
      goto LABEL_24;
    }
    if ( v7 != -2147024882 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      goto LABEL_24;
    }
LABEL_5:
    v6 = 14;
LABEL_24:
    SysFreeString(v4);
    goto LABEL_25;
  }
  if ( SingleNode == -2147024882 )
    goto LABEL_5;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  SysFreeString(0);
  v6 = 0;
LABEL_25:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v11);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v12);
  return v6;
}

```

## disassembly

```asm
0x180062884  mov     [rsp-28h+arg_0], rbx
0x180062889  push    rbp
0x18006288a  push    rsi
0x18006288b  push    rdi
0x18006288c  push    r12
0x18006288e  push    r15
0x180062890  mov     rbp, rsp
0x180062893  sub     rsp, 30h
0x180062897  mov     rsi, rdx
0x18006289a  mov     rdi, rcx
0x18006289d  mov     [rbp+var_8], 0
0x1800628a5  mov     [rbp+var_10], 0
0x1800628ad  xor     ebx, ebx
0x1800628af  mov     [rbp+bstrString], rbx
0x1800628b3  mov     [rbp+arg_10], bl
0x1800628b6  lea     r15, WPP_GLOBAL_Control
0x1800628bd  lea     r12, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800628c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800628cb  cmp     rcx, r15
0x1800628ce  jz      short loc_1800628E1
0x1800628d0  mov     edx, 0BEh
0x1800628d5  mov     r8, r12
0x1800628d8  mov     rcx, [rcx+10h]
0x1800628dc  call    WPP_SF_
0x1800628e1  lea     r8, [rbp+var_8]; struct IXMLDOMNode **
0x1800628e5  lea     rdx, aEaptlsconnecti_22; "eaptlsconnectionpropertiesv2:TLSExtensi"...
0x1800628ec  mov     rcx, rdi; struct IXMLDOMNode *
0x1800628ef  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x1800628f4  test    eax, eax
0x1800628f6  jz      short loc_18006293C
0x1800628f8  cmp     eax, 8007000Eh
0x1800628fd  jnz     short loc_180062909
0x1800628ff  mov     edi, 0Eh
0x180062904  jmp     loc_180062A11
0x180062909  mov     rcx, cs:WPP_GLOBAL_Control
0x180062910  cmp     rcx, r15
0x180062913  jz      short loc_180062927
0x180062915  mov     edx, 0BFh
0x18006291a  mov     r8, r12
0x18006291d  mov     rcx, [rcx+10h]
0x180062921  call    WPP_SF_
0x180062926  nop
0x180062927  xor     ecx, ecx; bstrString
0x180062929  call    cs:__imp_SysFreeString
0x180062930  nop     dword ptr [rax+rax+00h]
0x180062935  xor     edi, edi
0x180062937  jmp     loc_180062A21
0x18006293c  xor     edi, edi
0x18006293e  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x180062942  lea     rdx, aEaptlsconnecti_8; "eaptlsconnectionpropertiesv2:GroupSmart"...
0x180062949  mov     rcx, [rbp+var_8]; struct IXMLDOMNode *
0x18006294d  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180062952  test    eax, eax
0x180062954  jz      short loc_180062983
0x180062956  cmp     eax, 8007000Eh
0x18006295b  jz      short loc_1800628FF
0x18006295d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062964  cmp     rcx, r15
0x180062967  jz      loc_180062A11
0x18006296d  mov     edx, 0C0h
0x180062972  mov     r8, r12
0x180062975  mov     rcx, [rcx+10h]
0x180062979  call    WPP_SF_
0x18006297e  jmp     loc_180062A11
0x180062983  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180062987  lea     rdx, [rbp+arg_10]; bool *
0x18006298b  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18006298f  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x180062994  test    eax, eax
0x180062996  jz      short loc_1800629C3
0x180062998  mov     rbx, [rbp+bstrString]
0x18006299c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629a3  cmp     rcx, r15
0x1800629a6  jz      short loc_1800629BC
0x1800629a8  mov     edx, 0C1h
0x1800629ad  mov     r9, rbx
0x1800629b0  mov     r8, r12
0x1800629b3  mov     rcx, [rcx+10h]
0x1800629b7  call    WPP_SF_S
0x1800629bc  mov     edi, 0Dh
0x1800629c1  jmp     short loc_180062A11
0x1800629c3  mov     bl, [rbp+arg_10]
0x1800629c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629cd  cmp     rcx, r15
0x1800629d0  jz      short loc_1800629F7
0x1800629d2  lea     r9, aTrue_1; "TRUE"
0x1800629d9  lea     rax, aFalse_1; "FALSE"
0x1800629e0  test    bl, bl
0x1800629e2  cmovz   r9, rax
0x1800629e6  mov     edx, 0C2h
0x1800629eb  mov     r8, r12
0x1800629ee  mov     rcx, [rcx+10h]
0x1800629f2  call    WPP_SF_S
0x1800629f7  test    bl, bl
0x1800629f9  jnz     short loc_1800629FF
0x1800629fb  bts     dword ptr [rsi], 0Ah
0x1800629ff  mov     rcx, [rbp+bstrString]; bstrString
0x180062a03  call    cs:__imp_SysFreeString
0x180062a0a  nop     dword ptr [rax+rax+00h]
0x180062a0f  xor     ebx, ebx
0x180062a11  mov     rcx, rbx; bstrString
0x180062a14  call    cs:__imp_SysFreeString
0x180062a1b  nop     dword ptr [rax+rax+00h]
0x180062a20  nop
0x180062a21  lea     rcx, [rbp+var_10]
0x180062a25  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180062a2a  nop
0x180062a2b  lea     rcx, [rbp+var_8]
0x180062a2f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180062a34  mov     eax, edi
0x180062a36  mov     rbx, [rsp+30h+arg_0]
0x180062a3b  add     rsp, 30h
0x180062a3f  pop     r15
0x180062a41  pop     r12
0x180062a43  pop     rdi
0x180062a44  pop     rsi
0x180062a45  pop     rbp
0x180062a46  retn
```
