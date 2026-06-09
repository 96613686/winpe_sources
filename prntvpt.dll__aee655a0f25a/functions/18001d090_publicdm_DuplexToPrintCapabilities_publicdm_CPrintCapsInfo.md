# publicdm::DuplexToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x18001d090`
- end: `0x18001d1aa`
- name: `?DuplexToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `282`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x18000e084`
- `0x18001d090`
- `0x180023010`

## string_xrefs

- `0x18001d0e3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001d142`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::DuplexToPrintCapabilities(
        NPrintTicketUtil::CPrintTicketWrapper **this,
        struct publicdm::CPrintCapsInfo *a2)
{
  int v3; // ebx
  __int64 v4; // rax
  NPrintTicketUtil::CPrintTicketWrapper *v5; // rcx
  int i; // esi
  const unsigned __int16 *v7; // r9
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  struct IXMLDOMElement *v10; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMElement *v11; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v4 = (*((__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper **, struct publicdm::CPrintCapsInfo *))*this + 2))(
         this,
         a2);
  if ( (*(unsigned int (__fastcall **)(__int64, NPrintTicketUtil::CPrintTicketWrapper *))(*(_QWORD *)v4 + 16LL))(
         v4,
         this[2]) )
  {
    v5 = this[14];
    v10 = 0;
    v3 = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
           v5,
           0,
           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
           L"JobDuplexAllDocumentsContiguously",
           &v10);
    if ( v3 >= 0 )
      v3 = publicdm::WriteDisplayNameFromResourceString(
             this[14],
             (struct NPrintTicketUtil::CPrintTicketWrapper *)v10,
             (struct IXMLDOMElement *)this[12],
             (HINSTANCE)0xFCE9);
    for ( i = 0; v3 >= 0; ++i )
    {
      v7 = (const unsigned __int16 *)qword_1800254C0[3 * i + 1];
      if ( !v7 )
        break;
      v8 = this[14];
      v11 = 0;
      v3 = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
             v8,
             v10,
             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
             v7,
             &v11);
      if ( v3 >= 0 )
        v3 = publicdm::WriteDisplayNameFromResourceString(
               this[14],
               (struct NPrintTicketUtil::CPrintTicketWrapper *)v11,
               (struct IXMLDOMElement *)this[12],
               (HINSTANCE)LODWORD(qword_1800254C0[3 * i + 2]));
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v11);
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v10);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001d090  mov     [rsp+arg_10], rbx
0x18001d095  mov     [rsp+arg_18], rbp
0x18001d09a  push    rsi
0x18001d09b  push    rdi
0x18001d09c  push    r14
0x18001d09e  sub     rsp, 30h
0x18001d0a2  mov     rax, [rcx]
0x18001d0a5  mov     rdi, rcx
0x18001d0a8  xor     ebx, ebx
0x18001d0aa  mov     rax, [rax+10h]
0x18001d0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0b3  mov     rdx, [rdi+10h]
0x18001d0b7  mov     rcx, rax
0x18001d0ba  mov     rax, [rax]
0x18001d0bd  mov     rax, [rax+10h]
0x18001d0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0c6  test    eax, eax
0x18001d0c8  jz      loc_18001D195
0x18001d0ce  mov     rcx, [rdi+70h]; this
0x18001d0d2  lea     rax, [rsp+48h+arg_0]
0x18001d0d7  lea     r9, aJobduplexalldo; "JobDuplexAllDocumentsContiguously"
0x18001d0de  mov     [rsp+48h+var_28], rax; unsigned int
0x18001d0e3  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001d0ea  mov     [rsp+48h+arg_0], rbx
0x18001d0ef  xor     edx, edx; struct IXMLDOMElement *
0x18001d0f1  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d0f6  mov     ebx, eax
0x18001d0f8  test    eax, eax
0x18001d0fa  js      short loc_18001D116
0x18001d0fc  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x18001d100  mov     r9d, 0FCE9h; HINSTANCE
0x18001d106  mov     rdx, [rsp+48h+arg_0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001d10b  mov     rcx, [rdi+70h]; this
0x18001d10f  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001d114  mov     ebx, eax
0x18001d116  xor     esi, esi
0x18001d118  test    ebx, ebx
0x18001d11a  js      short loc_18001D18B
0x18001d11c  lea     r14, qword_1800254C0
0x18001d123  movsxd  rax, esi
0x18001d126  lea     rbp, [rax+rax*2]
0x18001d12a  mov     r9, [r14+rbp*8+8]; unsigned __int16 *
0x18001d12f  test    r9, r9
0x18001d132  jz      short loc_18001D18B
0x18001d134  mov     rdx, [rsp+48h+arg_0]; struct IXMLDOMElement *
0x18001d139  lea     rax, [rsp+48h+arg_8]
0x18001d13e  mov     rcx, [rdi+70h]; this
0x18001d142  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001d149  mov     [rsp+48h+var_28], rax; unsigned int
0x18001d14e  mov     [rsp+48h+arg_8], 0
0x18001d157  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d15c  mov     ebx, eax
0x18001d15e  test    eax, eax
0x18001d160  js      short loc_18001D17B
0x18001d162  mov     r9d, [r14+rbp*8+10h]; HINSTANCE
0x18001d167  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x18001d16b  mov     rdx, [rsp+48h+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001d170  mov     rcx, [rdi+70h]; this
0x18001d174  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001d179  mov     ebx, eax
0x18001d17b  lea     rcx, [rsp+48h+arg_8]
0x18001d180  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d185  inc     esi
0x18001d187  test    ebx, ebx
0x18001d189  jns     short loc_18001D123
0x18001d18b  lea     rcx, [rsp+48h+arg_0]
0x18001d190  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d195  mov     rbp, [rsp+48h+arg_18]
0x18001d19a  mov     eax, ebx
0x18001d19c  mov     rbx, [rsp+48h+arg_10]
0x18001d1a1  add     rsp, 30h
0x18001d1a5  pop     r14
0x18001d1a7  pop     rdi
0x18001d1a8  pop     rsi
0x18001d1a9  retn
```
