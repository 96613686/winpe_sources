# publicdm::CollateDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001b4b0`
- end: `0x18001b586`
- name: `?CollateDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `214`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008e68`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18001b4b0`
- `0x180023010`

## string_xrefs

- `0x18001b52e`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001b54c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CollateDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rax
  unsigned int Option; // esi
  const unsigned __int16 *v5; // rbx
  unsigned int (__fastcall ***v6)(_QWORD, _QWORD); // rax
  NPrintTicketUtil::CPrintTicketWrapper *v7; // rcx
  struct IXMLDOMElement *v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 2);
  Option = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x8000) != 0 )
  {
    if ( *(_WORD *)(v2 + 100) )
    {
      if ( *(_WORD *)(v2 + 100) != 1 )
        return Option;
      v5 = L"Collated";
      goto LABEL_8;
    }
  }
  else
  {
    v6 = (unsigned int (__fastcall ***)(_QWORD, _QWORD))(*(__int64 (__fastcall **)(publicdm *, struct publicdm::CConversionInfo *))(*(_QWORD *)this + 16LL))(
                                                          this,
                                                          a2);
    if ( !(**v6)(v6, *((_QWORD *)this + 2)) || *((_DWORD *)this + 16) )
      return Option;
  }
  v5 = L"Uncollated";
LABEL_8:
  v7 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v9 = 0;
  Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
             v7,
             0,
             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
             L"DocumentCollate",
             &v9);
  if ( (Option & 0x80000000) == 0 )
    Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
               *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
               v9,
               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
               v5,
               0);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v9);
  return Option;
}

```

## disassembly

```asm
0x18001b4b0  mov     [rsp+arg_8], rbx
0x18001b4b5  mov     [rsp+arg_10], rsi
0x18001b4ba  push    rdi
0x18001b4bb  sub     rsp, 30h
0x18001b4bf  mov     rax, [rcx+10h]
0x18001b4c3  xor     esi, esi
0x18001b4c5  mov     rdi, rcx
0x18001b4c8  test    dword ptr [rax+48h], 8000h
0x18001b4cf  jz      short loc_18001B4EB
0x18001b4d1  movsx   edx, word ptr [rax+64h]
0x18001b4d5  test    edx, edx
0x18001b4d7  jz      short loc_18001B512
0x18001b4d9  cmp     edx, 1
0x18001b4dc  jnz     loc_18001B574
0x18001b4e2  lea     rbx, aCollated; "Collated"
0x18001b4e9  jmp     short loc_18001B519
0x18001b4eb  mov     rax, [rcx]
0x18001b4ee  mov     rax, [rax+10h]
0x18001b4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4f7  mov     rdx, [rdi+10h]
0x18001b4fb  mov     rcx, rax
0x18001b4fe  mov     rax, [rax]
0x18001b501  mov     rax, [rax]
0x18001b504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b509  test    eax, eax
0x18001b50b  jz      short loc_18001B574
0x18001b50d  cmp     [rdi+40h], esi
0x18001b510  jnz     short loc_18001B574
0x18001b512  lea     rbx, aUncollated; "Uncollated"
0x18001b519  mov     rcx, [rdi+60h]; this
0x18001b51d  lea     rax, [rsp+38h+arg_0]
0x18001b522  lea     r9, aDocumentcollat; "DocumentCollate"
0x18001b529  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001b52e  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b535  mov     [rsp+38h+arg_0], rsi
0x18001b53a  xor     edx, edx; struct IXMLDOMElement *
0x18001b53c  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b541  mov     esi, eax
0x18001b543  test    eax, eax
0x18001b545  js      short loc_18001B56A
0x18001b547  mov     rdx, [rsp+38h+arg_0]; struct IXMLDOMElement *
0x18001b54c  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b553  mov     rcx, [rdi+60h]; this
0x18001b557  mov     r9, rbx; unsigned __int16 *
0x18001b55a  mov     [rsp+38h+var_18], 0; struct IXMLDOMElement **
0x18001b563  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b568  mov     esi, eax
0x18001b56a  lea     rcx, [rsp+38h+arg_0]
0x18001b56f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b574  mov     rbx, [rsp+38h+arg_8]
0x18001b579  mov     eax, esi
0x18001b57b  mov     rsi, [rsp+38h+arg_10]
0x18001b580  add     rsp, 30h
0x18001b584  pop     rdi
0x18001b585  retn
```
