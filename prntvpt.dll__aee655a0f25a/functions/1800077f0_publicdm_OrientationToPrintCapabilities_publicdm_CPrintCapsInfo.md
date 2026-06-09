# publicdm::OrientationToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x1800077f0`
- end: `0x1800079fe`
- name: `?OrientationToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `526`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x1800077f0`
- `0x18001c37c`
- `0x180023010`

## string_xrefs

- `0x1800078a1`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180007832`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::OrientationToPrintCapabilities(
        publicdm *this,
        struct publicdm::CPrintCapsInfo *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // r14
  struct NPrintTicketUtil::CPrintTicketWrapper *v6; // rbx
  int v7; // eax
  int QName; // edi
  NPrintTicketUtil::CPrintTicketWrapper *v9; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v10; // rcx
  __int64 v11; // rax
  NPrintTicketUtil::CPrintTicketWrapper *v12; // rcx
  unsigned __int16 *v14; // [rsp+28h] [rbp-18h]
  const unsigned __int16 *v15; // [rsp+30h] [rbp-10h]
  struct IXMLDOMElement **v16; // [rsp+38h] [rbp-8h]
  struct IXMLDOMElement *v17; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v18; // [rsp+78h] [rbp+38h] BYREF

  v4 = *((_QWORD *)this + 14);
  v6 = 0;
  v17 = 0;
  v7 = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
         (__int64 **)v4,
         *(struct IXMLDOMElement **)(v4 + 24),
         (struct IXMLDOMElement *)L"Feature",
         a4,
         &v17);
  v18 = 0;
  QName = v7;
  if ( v7 >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(
              (NPrintTicketUtil *)v4,
              v17,
              (struct IXMLDOMElement *)&stru_180029930,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              (const unsigned __int16 *)&v18,
              (unsigned __int16 **)v14,
              v15);
    if ( QName >= 0 )
    {
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v9, v17, L"name", v18);
      if ( QName >= 0 )
      {
        if ( !*(_DWORD *)(v4 + 36)
          || (QName = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                        (NPrintTicketUtil::CPrintTicketWrapper *)v4,
                        v17,
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                        L"SelectionType",
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                        L"PickOne",
                        0,
                        v16),
              QName >= 0) )
        {
          if ( v17 )
          {
            v6 = (struct NPrintTicketUtil::CPrintTicketWrapper *)v17;
            v17 = 0;
          }
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v18);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
  if ( QName >= 0 )
  {
    QName = publicdm::WriteDisplayNameFromResourceString(
              *((publicdm **)this + 14),
              v6,
              *((struct IXMLDOMElement **)this + 12),
              (HINSTANCE)0xFCE2);
    if ( QName >= 0 )
    {
      v10 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 14);
      v17 = 0;
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                v10,
                (struct IXMLDOMElement *)v6,
                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                L"Portrait",
                &v17);
      if ( QName >= 0 )
        QName = publicdm::WriteDisplayNameFromResourceString(
                  *((publicdm **)this + 14),
                  (struct NPrintTicketUtil::CPrintTicketWrapper *)v17,
                  *((struct IXMLDOMElement **)this + 12),
                  (HINSTANCE)0xFCF1);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
      if ( QName >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 16LL))(this);
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, *((_QWORD *)this + 2)) )
        {
          v12 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 14);
          v17 = 0;
          QName = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                    v12,
                    (struct IXMLDOMElement *)v6,
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    L"Landscape",
                    &v17);
          if ( QName >= 0 )
            QName = publicdm::WriteDisplayNameFromResourceString(
                      *((publicdm **)this + 14),
                      (struct NPrintTicketUtil::CPrintTicketWrapper *)v17,
                      *((struct IXMLDOMElement **)this + 12),
                      (HINSTANCE)0xFCF2);
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
        }
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(struct NPrintTicketUtil::CPrintTicketWrapper *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x1800077f0  mov     [rsp-28h+arg_10], rbx
0x1800077f5  push    rbp
0x1800077f6  push    rsi
0x1800077f7  push    rdi
0x1800077f8  push    r12
0x1800077fa  push    r14
0x1800077fc  mov     rbp, rsp
0x1800077ff  sub     rsp, 40h
0x180007803  mov     r14, [rcx+70h]
0x180007807  lea     rax, [rbp+arg_0]
0x18000780b  mov     rsi, rcx
0x18000780e  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180007813  xor     ebx, ebx
0x180007815  lea     r8, aFeature; "Feature"
0x18000781c  mov     rcx, r14; this
0x18000781f  mov     [rbp+arg_0], rbx
0x180007823  mov     rdx, [r14+18h]; struct IXMLDOMElement *
0x180007827  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000782c  mov     [rbp+arg_8], rbx
0x180007830  mov     edi, eax
0x180007832  lea     r12, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180007839  test    eax, eax
0x18000783b  js      loc_1800078CF
0x180007841  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180007845  lea     rax, [rbp+arg_8]
0x180007849  mov     r9, r12; unsigned __int16 *
0x18000784c  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180007851  lea     r8, stru_180029930; struct IXMLDOMElement *
0x180007858  mov     rcx, r14; this
0x18000785b  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180007860  mov     edi, eax
0x180007862  test    eax, eax
0x180007864  js      short loc_1800078CF
0x180007866  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x18000786a  lea     r8, aName; "name"
0x180007871  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180007875  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18000787a  mov     edi, eax
0x18000787c  test    eax, eax
0x18000787e  js      short loc_1800078CF
0x180007880  cmp     [r14+24h], ebx
0x180007884  jz      short loc_1800078BB
0x180007886  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x18000788a  lea     rax, aPickone; "PickOne"
0x180007891  mov     dword ptr [rsp+40h+var_10], ebx; int
0x180007895  lea     r9, aSelectiontype; "SelectionType"
0x18000789c  mov     [rsp+40h+var_18], rax; unsigned __int16 *
0x1800078a1  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x1800078a8  mov     rcx, r14; this
0x1800078ab  mov     [rsp+40h+var_20], r12; unsigned int
0x1800078b0  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x1800078b5  mov     edi, eax
0x1800078b7  test    eax, eax
0x1800078b9  js      short loc_1800078CF
0x1800078bb  mov     rax, [rbp+arg_0]
0x1800078bf  test    rax, rax
0x1800078c2  jz      short loc_1800078CF
0x1800078c4  mov     rbx, rax
0x1800078c7  mov     [rbp+arg_0], 0
0x1800078cf  lea     rcx, [rbp+arg_8]
0x1800078d3  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800078d8  lea     rcx, [rbp+arg_0]
0x1800078dc  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800078e1  test    edi, edi
0x1800078e3  js      loc_1800079D4
0x1800078e9  mov     r8, [rsi+60h]; struct IXMLDOMElement *
0x1800078ed  mov     r9d, 0FCE2h; HINSTANCE
0x1800078f3  mov     rcx, [rsi+70h]; this
0x1800078f7  mov     rdx, rbx; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800078fa  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x1800078ff  mov     edi, eax
0x180007901  test    eax, eax
0x180007903  js      loc_1800079D4
0x180007909  mov     rcx, [rsi+70h]; this
0x18000790d  lea     rax, [rbp+arg_0]
0x180007911  lea     r9, aPortrait; "Portrait"
0x180007918  mov     [rsp+40h+var_20], rax; unsigned int
0x18000791d  mov     r8, r12; unsigned __int16 *
0x180007920  mov     [rbp+arg_0], 0
0x180007928  mov     rdx, rbx; struct IXMLDOMElement *
0x18000792b  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180007930  mov     edi, eax
0x180007932  test    eax, eax
0x180007934  js      short loc_18000794F
0x180007936  mov     r8, [rsi+60h]; struct IXMLDOMElement *
0x18000793a  mov     r9d, 0FCF1h; HINSTANCE
0x180007940  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180007944  mov     rcx, [rsi+70h]; this
0x180007948  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18000794d  mov     edi, eax
0x18000794f  lea     rcx, [rbp+arg_0]
0x180007953  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180007958  test    edi, edi
0x18000795a  js      short loc_1800079D4
0x18000795c  mov     rax, [rsi]
0x18000795f  mov     rcx, rsi
0x180007962  mov     rax, [rax+10h]
0x180007966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000796b  mov     rdx, [rsi+10h]
0x18000796f  mov     r9, rax
0x180007972  mov     rcx, [rax]
0x180007975  mov     rax, [rcx+18h]
0x180007979  mov     rcx, r9
0x18000797c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007981  test    eax, eax
0x180007983  jz      short loc_1800079D4
0x180007985  mov     rcx, [rsi+70h]; this
0x180007989  lea     rax, [rbp+arg_0]
0x18000798d  lea     r9, aLandscape; "Landscape"
0x180007994  mov     [rsp+40h+var_20], rax; unsigned int
0x180007999  mov     r8, r12; unsigned __int16 *
0x18000799c  mov     [rbp+arg_0], 0
0x1800079a4  mov     rdx, rbx; struct IXMLDOMElement *
0x1800079a7  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800079ac  mov     edi, eax
0x1800079ae  test    eax, eax
0x1800079b0  js      short loc_1800079CB
0x1800079b2  mov     r8, [rsi+60h]; struct IXMLDOMElement *
0x1800079b6  mov     r9d, 0FCF2h; HINSTANCE
0x1800079bc  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800079c0  mov     rcx, [rsi+70h]; this
0x1800079c4  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x1800079c9  mov     edi, eax
0x1800079cb  lea     rcx, [rbp+arg_0]
0x1800079cf  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800079d4  test    rbx, rbx
0x1800079d7  jz      short loc_1800079E8
0x1800079d9  mov     rax, [rbx]
0x1800079dc  mov     rcx, rbx
0x1800079df  mov     rax, [rax+10h]
0x1800079e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e8  mov     rbx, [rsp+40h+arg_10]
0x1800079f0  mov     eax, edi
0x1800079f2  add     rsp, 40h
0x1800079f6  pop     r14
0x1800079f8  pop     r12
0x1800079fa  pop     rdi
0x1800079fb  pop     rsi
0x1800079fc  pop     rbp
0x1800079fd  retn
```
