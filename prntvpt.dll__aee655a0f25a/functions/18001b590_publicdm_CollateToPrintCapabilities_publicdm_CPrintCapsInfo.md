# publicdm::CollateToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x18001b590`
- end: `0x18001b6e5`
- name: `?CollateToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `341`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001adb4`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x18000e084`
- `0x18001b590`
- `0x180023010`

## string_xrefs

- `0x18001b5e1`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001b631`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001b689`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CollateToPrintCapabilities(
        NPrintTicketUtil::CPrintTicketWrapper **this,
        struct publicdm::CPrintCapsInfo *a2)
{
  int v3; // ebx
  unsigned int (__fastcall ***v4)(_QWORD, NPrintTicketUtil::CPrintTicketWrapper *); // rax
  NPrintTicketUtil::CPrintTicketWrapper *v5; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v6; // rcx
  NPrintTicketUtil::CPrintTicketWrapper *v7; // rcx
  unsigned int v9; // [rsp+20h] [rbp-10h]
  unsigned int v10; // [rsp+20h] [rbp-10h]
  unsigned int v11; // [rsp+20h] [rbp-10h]
  struct IXMLDOMElement *v12; // [rsp+40h] [rbp+10h] BYREF
  struct IXMLDOMElement *v13; // [rsp+48h] [rbp+18h] BYREF

  v3 = 0;
  v4 = (unsigned int (__fastcall ***)(_QWORD, NPrintTicketUtil::CPrintTicketWrapper *))(*((__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper **, struct publicdm::CPrintCapsInfo *))*this
                                                                                        + 2))(
                                                                                         this,
                                                                                         a2);
  if ( (**v4)(v4, this[2]) )
  {
    v5 = this[14];
    v12 = 0;
    v3 = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
           v5,
           0,
           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
           L"DocumentCollate",
           &v12);
    if ( v3 >= 0 )
    {
      v3 = publicdm::WriteDisplayNameFromResourceString(
             this[14],
             (struct NPrintTicketUtil::CPrintTicketWrapper *)v12,
             (struct IXMLDOMElement *)this[12],
             (HINSTANCE)0xFCF4,
             v9);
      if ( v3 >= 0 )
      {
        v6 = this[14];
        v13 = 0;
        v3 = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
               v6,
               v12,
               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
               L"Collated",
               &v13);
        if ( v3 >= 0 )
          v3 = publicdm::WriteDisplayNameFromResourceString(
                 this[14],
                 (struct NPrintTicketUtil::CPrintTicketWrapper *)v13,
                 (struct IXMLDOMElement *)this[12],
                 (HINSTANCE)0xFCD9,
                 v10);
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
        if ( v3 >= 0 )
        {
          v7 = this[14];
          v13 = 0;
          v3 = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                 v7,
                 v12,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"Uncollated",
                 &v13);
          if ( v3 >= 0 )
            v3 = publicdm::WriteDisplayNameFromResourceString(
                   this[14],
                   (struct NPrintTicketUtil::CPrintTicketWrapper *)v13,
                   (struct IXMLDOMElement *)this[12],
                   (HINSTANCE)0xFCD8,
                   v11);
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
        }
      }
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001b590  mov     [rsp-8+arg_10], rbx
0x18001b595  mov     [rsp-8+arg_18], rdi
0x18001b59a  push    rbp
0x18001b59b  mov     rbp, rsp
0x18001b59e  sub     rsp, 30h
0x18001b5a2  mov     rax, [rcx]
0x18001b5a5  mov     rdi, rcx
0x18001b5a8  xor     ebx, ebx
0x18001b5aa  mov     rax, [rax+10h]
0x18001b5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5b3  mov     rdx, [rdi+10h]
0x18001b5b7  mov     rcx, rax
0x18001b5ba  mov     rax, [rax]
0x18001b5bd  mov     rax, [rax]
0x18001b5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5c5  test    eax, eax
0x18001b5c7  jz      loc_18001B6D3
0x18001b5cd  mov     rcx, [rdi+70h]; this
0x18001b5d1  lea     rax, [rbp+arg_0]
0x18001b5d5  lea     r9, aDocumentcollat; "DocumentCollate"
0x18001b5dc  mov     qword ptr [rsp+30h+var_10], rax; unsigned int
0x18001b5e1  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b5e8  mov     [rbp+arg_0], rbx
0x18001b5ec  xor     edx, edx; struct IXMLDOMElement *
0x18001b5ee  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b5f3  mov     ebx, eax
0x18001b5f5  test    eax, eax
0x18001b5f7  js      loc_18001B6CA
0x18001b5fd  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x18001b601  mov     r9d, 0FCF4h; HINSTANCE
0x18001b607  mov     rdx, [rbp+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001b60b  mov     rcx, [rdi+70h]; this
0x18001b60f  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001b614  mov     ebx, eax
0x18001b616  test    eax, eax
0x18001b618  js      loc_18001B6CA
0x18001b61e  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x18001b622  lea     rax, [rbp+arg_8]
0x18001b626  mov     rcx, [rdi+70h]; this
0x18001b62a  lea     r9, aCollated; "Collated"
0x18001b631  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b638  mov     qword ptr [rsp+30h+var_10], rax; unsigned int
0x18001b63d  mov     [rbp+arg_8], 0
0x18001b645  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b64a  mov     ebx, eax
0x18001b64c  test    eax, eax
0x18001b64e  js      short loc_18001B669
0x18001b650  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x18001b654  mov     r9d, 0FCD9h; HINSTANCE
0x18001b65a  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001b65e  mov     rcx, [rdi+70h]; this
0x18001b662  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001b667  mov     ebx, eax
0x18001b669  lea     rcx, [rbp+arg_8]
0x18001b66d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b672  test    ebx, ebx
0x18001b674  js      short loc_18001B6CA
0x18001b676  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x18001b67a  lea     rax, [rbp+arg_8]
0x18001b67e  mov     rcx, [rdi+70h]; this
0x18001b682  lea     r9, aUncollated; "Uncollated"
0x18001b689  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b690  mov     qword ptr [rsp+30h+var_10], rax; unsigned int
0x18001b695  mov     [rbp+arg_8], 0
0x18001b69d  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b6a2  mov     ebx, eax
0x18001b6a4  test    eax, eax
0x18001b6a6  js      short loc_18001B6C1
0x18001b6a8  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x18001b6ac  mov     r9d, 0FCD8h; HINSTANCE
0x18001b6b2  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001b6b6  mov     rcx, [rdi+70h]; this
0x18001b6ba  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001b6bf  mov     ebx, eax
0x18001b6c1  lea     rcx, [rbp+arg_8]
0x18001b6c5  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b6ca  lea     rcx, [rbp+arg_0]
0x18001b6ce  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b6d3  mov     rdi, [rsp+30h+arg_18]
0x18001b6d8  mov     eax, ebx
0x18001b6da  mov     rbx, [rsp+30h+arg_10]
0x18001b6df  add     rsp, 30h
0x18001b6e3  pop     rbp
0x18001b6e4  retn
```
