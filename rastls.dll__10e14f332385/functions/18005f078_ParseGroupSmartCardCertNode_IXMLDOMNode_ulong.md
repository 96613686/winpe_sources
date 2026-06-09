# ParseGroupSmartCardCertNode(IXMLDOMNode *,ulong *)

- ea: `0x18005f078`
- end: `0x18005f229`
- name: `?ParseGroupSmartCardCertNode@@YAKPEAUIXMLDOMNode@@PEAK@Z`
- size: `433`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c1e0`

## callees

- `0x1800075b0`
- `0x18000f350`
- `0x18000f690`
- `0x180019c80`
- `0x1800200b4`
- `0x18005f078`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005f11d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f1f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f1fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f11d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f1f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f1fc`

## string_xrefs

- `0x18005f0d9`: `eaptlsconnectionpropertiesv2:TLSExtensions`

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
0x18005f078  mov     [rsp-28h+arg_0], rbx
0x18005f07d  push    rbp
0x18005f07e  push    rsi
0x18005f07f  push    rdi
0x18005f080  push    r12
0x18005f082  push    r15
0x18005f084  mov     rbp, rsp
0x18005f087  sub     rsp, 30h
0x18005f08b  mov     rsi, rdx
0x18005f08e  mov     rdi, rcx
0x18005f091  mov     [rbp+var_8], 0
0x18005f099  mov     [rbp+var_10], 0
0x18005f0a1  xor     ebx, ebx
0x18005f0a3  mov     [rbp+bstrString], rbx
0x18005f0a7  mov     [rbp+arg_10], bl
0x18005f0aa  lea     r15, WPP_GLOBAL_Control
0x18005f0b1  lea     r12, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f0bf  cmp     rcx, r15
0x18005f0c2  jz      short loc_18005F0D5
0x18005f0c4  mov     edx, 0BEh
0x18005f0c9  mov     r8, r12
0x18005f0cc  mov     rcx, [rcx+10h]
0x18005f0d0  call    WPP_SF_
0x18005f0d5  lea     r8, [rbp+var_8]; struct IXMLDOMNode **
0x18005f0d9  lea     rdx, aEaptlsconnecti_22; "eaptlsconnectionpropertiesv2:TLSExtensi"...
0x18005f0e0  mov     rcx, rdi; struct IXMLDOMNode *
0x18005f0e3  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005f0e8  test    eax, eax
0x18005f0ea  jz      short loc_18005F12A
0x18005f0ec  cmp     eax, 8007000Eh
0x18005f0f1  jnz     short loc_18005F0FD
0x18005f0f3  mov     edi, 0Eh
0x18005f0f8  jmp     loc_18005F1F9
0x18005f0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f104  cmp     rcx, r15
0x18005f107  jz      short loc_18005F11B
0x18005f109  mov     edx, 0BFh
0x18005f10e  mov     r8, r12
0x18005f111  mov     rcx, [rcx+10h]
0x18005f115  call    WPP_SF_
0x18005f11a  nop
0x18005f11b  xor     ecx, ecx; bstrString
0x18005f11d  call    cs:__imp_SysFreeString
0x18005f123  xor     edi, edi
0x18005f125  jmp     loc_18005F203
0x18005f12a  xor     edi, edi
0x18005f12c  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x18005f130  lea     rdx, aEaptlsconnecti_8; "eaptlsconnectionpropertiesv2:GroupSmart"...
0x18005f137  mov     rcx, [rbp+var_8]; struct IXMLDOMNode *
0x18005f13b  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005f140  test    eax, eax
0x18005f142  jz      short loc_18005F171
0x18005f144  cmp     eax, 8007000Eh
0x18005f149  jz      short loc_18005F0F3
0x18005f14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f152  cmp     rcx, r15
0x18005f155  jz      loc_18005F1F9
0x18005f15b  mov     edx, 0C0h
0x18005f160  mov     r8, r12
0x18005f163  mov     rcx, [rcx+10h]
0x18005f167  call    WPP_SF_
0x18005f16c  jmp     loc_18005F1F9
0x18005f171  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18005f175  lea     rdx, [rbp+arg_10]; bool *
0x18005f179  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18005f17d  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x18005f182  test    eax, eax
0x18005f184  jz      short loc_18005F1B1
0x18005f186  mov     rbx, [rbp+bstrString]
0x18005f18a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f191  cmp     rcx, r15
0x18005f194  jz      short loc_18005F1AA
0x18005f196  mov     edx, 0C1h
0x18005f19b  mov     r9, rbx
0x18005f19e  mov     r8, r12
0x18005f1a1  mov     rcx, [rcx+10h]
0x18005f1a5  call    WPP_SF_S
0x18005f1aa  mov     edi, 0Dh
0x18005f1af  jmp     short loc_18005F1F9
0x18005f1b1  mov     bl, [rbp+arg_10]
0x18005f1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f1bb  cmp     rcx, r15
0x18005f1be  jz      short loc_18005F1E5
0x18005f1c0  lea     r9, aTrue_1; "TRUE"
0x18005f1c7  lea     rax, aFalse_1; "FALSE"
0x18005f1ce  test    bl, bl
0x18005f1d0  cmovz   r9, rax
0x18005f1d4  mov     edx, 0C2h
0x18005f1d9  mov     r8, r12
0x18005f1dc  mov     rcx, [rcx+10h]
0x18005f1e0  call    WPP_SF_S
0x18005f1e5  test    bl, bl
0x18005f1e7  jnz     short loc_18005F1ED
0x18005f1e9  bts     dword ptr [rsi], 0Ah
0x18005f1ed  mov     rcx, [rbp+bstrString]; bstrString
0x18005f1f1  call    cs:__imp_SysFreeString
0x18005f1f7  xor     ebx, ebx
0x18005f1f9  mov     rcx, rbx; bstrString
0x18005f1fc  call    cs:__imp_SysFreeString
0x18005f202  nop
0x18005f203  lea     rcx, [rbp+var_10]
0x18005f207  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f20c  nop
0x18005f20d  lea     rcx, [rbp+var_8]
0x18005f211  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f216  mov     eax, edi
0x18005f218  mov     rbx, [rsp+30h+arg_0]
0x18005f21d  add     rsp, 30h
0x18005f221  pop     r15
0x18005f223  pop     r12
0x18005f225  pop     rdi
0x18005f226  pop     rsi
0x18005f227  pop     rbp
0x18005f228  retn
```
