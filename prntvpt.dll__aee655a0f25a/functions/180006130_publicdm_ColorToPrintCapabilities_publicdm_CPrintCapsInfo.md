# publicdm::ColorToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x180006130`
- end: `0x18000633e`
- name: `?ColorToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `526`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006130`
- `0x180006344`
- `0x180006c74`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x18001c37c`
- `0x180023010`

## string_xrefs

- `0x1800061e1`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180006172`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ColorToPrintCapabilities(
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
              (struct IXMLDOMElement *)&stru_18002A1F0,
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
              (HINSTANCE)0xFCE8);
    if ( QName >= 0 )
    {
      v10 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 14);
      v17 = 0;
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                v10,
                (struct IXMLDOMElement *)v6,
                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                L"Monochrome",
                &v17);
      if ( QName >= 0 )
        QName = publicdm::WriteDisplayNameFromResourceString(
                  *((publicdm **)this + 14),
                  (struct NPrintTicketUtil::CPrintTicketWrapper *)v17,
                  *((struct IXMLDOMElement **)this + 12),
                  (HINSTANCE)0xFCFE);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
      if ( QName >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 16LL))(this);
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, *((_QWORD *)this + 2)) )
        {
          v12 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 14);
          v17 = 0;
          QName = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                    v12,
                    (struct IXMLDOMElement *)v6,
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    L"Color",
                    &v17);
          if ( QName >= 0 )
            QName = publicdm::WriteDisplayNameFromResourceString(
                      *((publicdm **)this + 14),
                      (struct NPrintTicketUtil::CPrintTicketWrapper *)v17,
                      *((struct IXMLDOMElement **)this + 12),
                      (HINSTANCE)0xFCFC);
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
0x180006130  mov     [rsp-28h+arg_10], rbx
0x180006135  push    rbp
0x180006136  push    rsi
0x180006137  push    rdi
0x180006138  push    r12
0x18000613a  push    r14
0x18000613c  mov     rbp, rsp
0x18000613f  sub     rsp, 40h
0x180006143  mov     r14, [rcx+70h]
0x180006147  lea     rax, [rbp+arg_0]
0x18000614b  mov     rsi, rcx
0x18000614e  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180006153  xor     ebx, ebx
0x180006155  lea     r8, aFeature; "Feature"
0x18000615c  mov     rcx, r14; this
0x18000615f  mov     [rbp+arg_0], rbx
0x180006163  mov     rdx, [r14+18h]; struct IXMLDOMElement *
0x180006167  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000616c  mov     [rbp+arg_8], rbx
0x180006170  mov     edi, eax
0x180006172  lea     r12, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180006179  test    eax, eax
0x18000617b  js      loc_18000620F
0x180006181  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180006185  lea     rax, [rbp+arg_8]
0x180006189  mov     r9, r12; unsigned __int16 *
0x18000618c  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180006191  lea     r8, stru_18002A1F0; struct IXMLDOMElement *
0x180006198  mov     rcx, r14; this
0x18000619b  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x1800061a0  mov     edi, eax
0x1800061a2  test    eax, eax
0x1800061a4  js      short loc_18000620F
0x1800061a6  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x1800061aa  lea     r8, aName; "name"
0x1800061b1  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x1800061b5  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x1800061ba  mov     edi, eax
0x1800061bc  test    eax, eax
0x1800061be  js      short loc_18000620F
0x1800061c0  cmp     [r14+24h], ebx
0x1800061c4  jz      short loc_1800061FB
0x1800061c6  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x1800061ca  lea     rax, aPickone; "PickOne"
0x1800061d1  mov     dword ptr [rsp+40h+var_10], ebx; int
0x1800061d5  lea     r9, aSelectiontype; "SelectionType"
0x1800061dc  mov     [rsp+40h+var_18], rax; unsigned __int16 *
0x1800061e1  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x1800061e8  mov     rcx, r14; this
0x1800061eb  mov     [rsp+40h+var_20], r12; unsigned int
0x1800061f0  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x1800061f5  mov     edi, eax
0x1800061f7  test    eax, eax
0x1800061f9  js      short loc_18000620F
0x1800061fb  mov     rax, [rbp+arg_0]
0x1800061ff  test    rax, rax
0x180006202  jz      short loc_18000620F
0x180006204  mov     rbx, rax
0x180006207  mov     [rbp+arg_0], 0
0x18000620f  lea     rcx, [rbp+arg_8]
0x180006213  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180006218  lea     rcx, [rbp+arg_0]
0x18000621c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180006221  test    edi, edi
0x180006223  js      loc_180006314
0x180006229  mov     r8, [rsi+60h]; struct IXMLDOMElement *
0x18000622d  mov     r9d, 0FCE8h; HINSTANCE
0x180006233  mov     rcx, [rsi+70h]; this
0x180006237  mov     rdx, rbx; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000623a  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18000623f  mov     edi, eax
0x180006241  test    eax, eax
0x180006243  js      loc_180006314
0x180006249  mov     rcx, [rsi+70h]; this
0x18000624d  lea     rax, [rbp+arg_0]
0x180006251  lea     r9, aMonochrome; "Monochrome"
0x180006258  mov     [rsp+40h+var_20], rax; unsigned int
0x18000625d  mov     r8, r12; unsigned __int16 *
0x180006260  mov     [rbp+arg_0], 0
0x180006268  mov     rdx, rbx; struct IXMLDOMElement *
0x18000626b  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180006270  mov     edi, eax
0x180006272  test    eax, eax
0x180006274  js      short loc_18000628F
0x180006276  mov     r8, [rsi+60h]; struct IXMLDOMElement *
0x18000627a  mov     r9d, 0FCFEh; HINSTANCE
0x180006280  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180006284  mov     rcx, [rsi+70h]; this
0x180006288  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18000628d  mov     edi, eax
0x18000628f  lea     rcx, [rbp+arg_0]
0x180006293  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180006298  test    edi, edi
0x18000629a  js      short loc_180006314
0x18000629c  mov     rax, [rsi]
0x18000629f  mov     rcx, rsi
0x1800062a2  mov     rax, [rax+10h]
0x1800062a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ab  mov     rdx, [rsi+10h]
0x1800062af  mov     r9, rax
0x1800062b2  mov     rcx, [rax]
0x1800062b5  mov     rax, [rcx+8]
0x1800062b9  mov     rcx, r9
0x1800062bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c1  test    eax, eax
0x1800062c3  jz      short loc_180006314
0x1800062c5  mov     rcx, [rsi+70h]; this
0x1800062c9  lea     rax, [rbp+arg_0]
0x1800062cd  lea     r9, aColor; "Color"
0x1800062d4  mov     [rsp+40h+var_20], rax; unsigned int
0x1800062d9  mov     r8, r12; unsigned __int16 *
0x1800062dc  mov     [rbp+arg_0], 0
0x1800062e4  mov     rdx, rbx; struct IXMLDOMElement *
0x1800062e7  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800062ec  mov     edi, eax
0x1800062ee  test    eax, eax
0x1800062f0  js      short loc_18000630B
0x1800062f2  mov     r8, [rsi+60h]; struct IXMLDOMElement *
0x1800062f6  mov     r9d, 0FCFCh; HINSTANCE
0x1800062fc  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180006300  mov     rcx, [rsi+70h]; this
0x180006304  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x180006309  mov     edi, eax
0x18000630b  lea     rcx, [rbp+arg_0]
0x18000630f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180006314  test    rbx, rbx
0x180006317  jz      short loc_180006328
0x180006319  mov     rax, [rbx]
0x18000631c  mov     rcx, rbx
0x18000631f  mov     rax, [rax+10h]
0x180006323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006328  mov     rbx, [rsp+40h+arg_10]
0x180006330  mov     eax, edi
0x180006332  add     rsp, 40h
0x180006336  pop     r14
0x180006338  pop     r12
0x18000633a  pop     rdi
0x18000633b  pop     rsi
0x18000633c  pop     rbp
0x18000633d  retn
```
