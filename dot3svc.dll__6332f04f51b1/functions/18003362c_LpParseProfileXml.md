# LpParseProfileXml

- ea: `0x18003362c`
- end: `0x18003375c`
- name: `LpParseProfileXml`
- size: `304`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d2fc`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000c4b0`
- `0x1800328f8`
- `0x18003362c`
- `0x180033764`
- `0x18003a9e0`
- `0x18003b474`
- `0x18003bb70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033747`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180033747`

## pseudocode

```c
__int64 __fastcall LpParseProfileXml(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  unsigned int XmlDoc; // edi
  struct IXMLDOMNode *v6; // rbx
  int v8; // [rsp+20h] [rbp-48h] BYREF
  struct IXMLDOMDocument2 *v9[8]; // [rsp+28h] [rbp-40h] BYREF
  int v10; // [rsp+80h] [rbp+18h] BYREF
  int v11; // [rsp+84h] [rbp+1Ch]

  v11 = HIDWORD(a3);
  v4 = qword_180052CD8;
  v8 = 0;
  v9[0] = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 24, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids);
  }
  XmlDoc = CXcSmartCoInit::Init((CXcSmartCoInit *)&v8);
  if ( !XmlDoc )
  {
    XmlDoc = LpCreateXmlDoc(1, v4, v9);
    if ( !XmlDoc )
    {
      v6 = (struct IXMLDOMNode *)v9[0];
      XmlDoc = XcLoadXml(v9[0], a1, &v10);
      if ( !XmlDoc && (v10 || (XmlDoc = XcGetLoadError((struct IXMLDOMDocument2 *)v6)) == 0) )
        XmlDoc = LpParseProfileXmlDoc(v6);
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 25, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids, XmlDoc);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v9);
  if ( v8 )
    CoUninitialize();
  return XmlDoc;
}

```

## disassembly

```asm
0x18003362c  mov     rax, rsp
0x18003362f  mov     [rax+18h], r8
0x180033633  push    rbx
0x180033634  push    rbp
0x180033635  push    rsi
0x180033636  push    rdi
0x180033637  push    r12
0x180033639  push    r14
0x18003363b  sub     rsp, 38h
0x18003363f  mov     rbp, r9
0x180033642  mov     r14, rdx
0x180033645  mov     rsi, rcx
0x180033648  mov     rbx, cs:qword_180052CD8
0x18003364f  mov     dword ptr [rax-48h], 0
0x180033656  mov     qword ptr [rax-40h], 0
0x18003365e  mov     dword ptr [rax+18h], 0
0x180033665  lea     r12, WPP_GLOBAL_Control
0x18003366c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033673  cmp     rcx, r12
0x180033676  jz      short loc_180033699
0x180033678  cmp     byte ptr [rcx+19h], 4
0x18003367c  jb      short loc_180033699
0x18003367e  test    byte ptr [rcx+1Ch], 1
0x180033682  jz      short loc_180033699
0x180033684  mov     edx, 18h
0x180033689  lea     r8, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x180033690  mov     rcx, [rcx+10h]
0x180033694  call    WPP_SF_
0x180033699  lea     rcx, [rsp+68h+var_48]; this
0x18003369e  call    ?Init@CXcSmartCoInit@@QEAAKXZ; CXcSmartCoInit::Init(void)
0x1800336a3  mov     edi, eax
0x1800336a5  test    eax, eax
0x1800336a7  jnz     short loc_180033704
0x1800336a9  lea     r8, [rsp+68h+var_40]
0x1800336ae  mov     rdx, rbx
0x1800336b1  lea     ecx, [rax+1]
0x1800336b4  call    LpCreateXmlDoc
0x1800336b9  mov     edi, eax
0x1800336bb  test    eax, eax
0x1800336bd  jnz     short loc_180033704
0x1800336bf  lea     r8, [rsp+68h+arg_10]; int *
0x1800336c7  mov     rdx, rsi; unsigned __int16 *
0x1800336ca  mov     rbx, [rsp+68h+var_40]
0x1800336cf  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x1800336d2  call    ?XcLoadXml@@YAKPEAUIXMLDOMDocument2@@PEBGPEAH@Z; XcLoadXml(IXMLDOMDocument2 *,ushort const *,int *)
0x1800336d7  mov     edi, eax
0x1800336d9  test    eax, eax
0x1800336db  jnz     short loc_180033704
0x1800336dd  cmp     [rsp+68h+arg_10], eax
0x1800336e4  jnz     short loc_1800336F4
0x1800336e6  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x1800336e9  call    ?XcGetLoadError@@YAKPEAUIXMLDOMDocument2@@@Z; XcGetLoadError(IXMLDOMDocument2 *)
0x1800336ee  mov     edi, eax
0x1800336f0  test    eax, eax
0x1800336f2  jnz     short loc_180033704
0x1800336f4  mov     r9, rbp
0x1800336f7  mov     rdx, r14
0x1800336fa  mov     rcx, rbx; struct IXMLDOMNode *
0x1800336fd  call    LpParseProfileXmlDoc
0x180033702  mov     edi, eax
0x180033704  mov     rcx, cs:WPP_GLOBAL_Control
0x18003370b  cmp     rcx, r12
0x18003370e  jz      short loc_180033735
0x180033710  cmp     byte ptr [rcx+19h], 4
0x180033714  jb      short loc_180033735
0x180033716  test    byte ptr [rcx+1Ch], 1
0x18003371a  jz      short loc_180033735
0x18003371c  mov     edx, 19h
0x180033721  mov     r9d, edi
0x180033724  lea     r8, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x18003372b  mov     rcx, [rcx+10h]
0x18003372f  call    WPP_SF_d
0x180033734  nop
0x180033735  lea     rcx, [rsp+68h+var_40]
0x18003373a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18003373f  nop
0x180033740  cmp     [rsp+68h+var_48], 0
0x180033745  jz      short loc_18003374D
0x180033747  call    cs:__imp_CoUninitialize
0x18003374d  mov     eax, edi
0x18003374f  add     rsp, 38h
0x180033753  pop     r14
0x180033755  pop     r12
0x180033757  pop     rdi
0x180033758  pop     rsi
0x180033759  pop     rbp
0x18003375a  pop     rbx
0x18003375b  retn
```
