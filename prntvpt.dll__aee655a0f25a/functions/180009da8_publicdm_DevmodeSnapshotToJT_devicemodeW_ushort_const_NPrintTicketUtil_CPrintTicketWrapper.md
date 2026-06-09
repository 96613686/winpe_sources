# publicdm::DevmodeSnapshotToJT(_devicemodeW *,ushort const *,NPrintTicketUtil::CPrintTicketWrapper *)

- ea: `0x180009da8`
- end: `0x180009eb3`
- name: `?DevmodeSnapshotToJT@publicdm@@YAJPEAU_devicemodeW@@PEBGPEAVCPrintTicketWrapper@NPrintTicketUtil@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(publicdm *this, struct _devicemodeW *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008848`
- `0x18000ea40`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006d70`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x180009da8`
- `0x180009ec0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009e9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e9d`

## string_xrefs

- `0x180009e6a`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall publicdm::DevmodeSnapshotToJT(
        publicdm *this,
        struct _devicemodeW *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned __int8 *v6; // rdx
  int QName; // ebx
  const unsigned __int16 *v8; // r9
  struct IXMLDOMElement *v9; // rdx
  NPrintTicketUtil::CPrintTicketWrapper *v10; // rcx
  unsigned __int16 **v12; // [rsp+28h] [rbp-18h]
  struct IXMLDOMElement **v13; // [rsp+28h] [rbp-18h]
  unsigned __int16 *v14[2]; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+20h] BYREF
  struct IXMLDOMElement *v16; // [rsp+78h] [rbp+38h] BYREF

  v6 = (unsigned __int8 *)(*((unsigned __int16 *)this + 34) + (unsigned int)*((unsigned __int16 *)this + 35));
  bstrString = 0;
  QName = publicdm::ToBase64BSTR(this, v6, (int)&bstrString, a4);
  if ( QName >= 0 )
  {
    v9 = (struct IXMLDOMElement *)*((_QWORD *)a3 + 3);
    v16 = 0;
    v14[0] = 0;
    QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
              (NPrintTicketUtil::CPrintTicketWrapper *)a3,
              v9,
              L"ParameterInit",
              v8,
              &v16);
    if ( QName >= 0 )
    {
      QName = NPrintTicketUtil::CreateQName(
                (NPrintTicketUtil *)a3,
                v16,
                (struct IXMLDOMElement *)&stru_180029EA8,
                a2->dmDeviceName,
                (const unsigned __int16 *)v14,
                v12,
                v14[0]);
      if ( QName >= 0 )
      {
        QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v10, v16, L"name", v14[0]);
        if ( QName >= 0 )
        {
          if ( bstrString )
            QName = NPrintTicketUtil::CPrintTicketWrapper::CreateValue(
                      (NPrintTicketUtil::CPrintTicketWrapper *)a3,
                      v16,
                      bstrString,
                      L"http://www.w3.org/2001/XMLSchema",
                      L"string",
                      v13);
        }
      }
    }
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v14);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x180009da8  mov     [rsp-18h+arg_8], rbx
0x180009dad  push    rbp
0x180009dae  push    rsi
0x180009daf  push    r14
0x180009db1  mov     rbp, rsp
0x180009db4  sub     rsp, 40h
0x180009db8  movzx   eax, word ptr [rcx+44h]
0x180009dbc  mov     r14, rdx
0x180009dbf  movzx   edx, word ptr [rcx+46h]
0x180009dc3  mov     rsi, r8
0x180009dc6  add     edx, eax; unsigned __int8 *
0x180009dc8  mov     [rbp+bstrString], 0
0x180009dd0  lea     r8, [rbp+bstrString]; int
0x180009dd4  call    ?ToBase64BSTR@publicdm@@YAJPEAEHPEAPEAG@Z; publicdm::ToBase64BSTR(uchar *,int,ushort * *)
0x180009dd9  mov     ebx, eax
0x180009ddb  test    eax, eax
0x180009ddd  js      loc_180009E92
0x180009de3  mov     rdx, [rsi+18h]; struct IXMLDOMElement *
0x180009de7  lea     rax, [rbp+arg_18]
0x180009deb  lea     r8, aParameterinit; "ParameterInit"
0x180009df2  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180009df7  mov     rcx, rsi; this
0x180009dfa  mov     [rbp+arg_18], 0
0x180009e02  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180009e07  mov     [rbp+var_10], 0
0x180009e0f  mov     ebx, eax
0x180009e11  test    eax, eax
0x180009e13  js      short loc_180009E80
0x180009e15  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180009e19  lea     rax, [rbp+var_10]
0x180009e1d  mov     r9, r14; unsigned __int16 *
0x180009e20  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180009e25  lea     r8, stru_180029EA8; struct IXMLDOMElement *
0x180009e2c  mov     rcx, rsi; this
0x180009e2f  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180009e34  mov     ebx, eax
0x180009e36  test    eax, eax
0x180009e38  js      short loc_180009E80
0x180009e3a  mov     r9, [rbp+var_10]; unsigned __int16 *
0x180009e3e  lea     r8, aName; "name"
0x180009e45  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180009e49  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180009e4e  mov     ebx, eax
0x180009e50  test    eax, eax
0x180009e52  js      short loc_180009E80
0x180009e54  cmp     [rbp+bstrString], 0
0x180009e59  jz      short loc_180009E80
0x180009e5b  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x180009e5f  lea     rax, aString; "string"
0x180009e66  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180009e6a  lea     r9, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x180009e71  mov     rcx, rsi; this
0x180009e74  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180009e79  call    ?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180009e7e  mov     ebx, eax
0x180009e80  lea     rcx, [rbp+var_10]
0x180009e84  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180009e89  lea     rcx, [rbp+arg_18]
0x180009e8d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180009e92  cmp     [rbp+bstrString], 0
0x180009e97  jz      short loc_180009EA3
0x180009e99  mov     rcx, [rbp+bstrString]; bstrString
0x180009e9d  call    cs:__imp_SysFreeString
0x180009ea3  mov     eax, ebx
0x180009ea5  mov     rbx, [rsp+40h+arg_8]
0x180009eaa  add     rsp, 40h
0x180009eae  pop     r14
0x180009eb0  pop     rsi
0x180009eb1  pop     rbp
0x180009eb2  retn
```
