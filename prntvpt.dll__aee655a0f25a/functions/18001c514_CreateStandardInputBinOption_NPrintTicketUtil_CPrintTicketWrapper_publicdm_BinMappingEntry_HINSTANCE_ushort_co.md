# CreateStandardInputBinOption(NPrintTicketUtil::CPrintTicketWrapper *,publicdm::BinMappingEntry *,HINSTANCE__ *,ushort const *,ushort const *,IXMLDOMElement *,IXMLDOMElement * *)

- ea: `0x18001c514`
- end: `0x18001c676`
- name: `?CreateStandardInputBinOption@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUBinMappingEntry@publicdm@@PEAUHINSTANCE__@@PEBG3PEAUIXMLDOMElement@@PEAPEAU6@@Z`
- size: `354`
- prototype: `__int64 __usercall@<rax>(struct NPrintTicketUtil::CPrintTicketWrapper *this@<rcx>, struct IXMLDOMElement *@<rdx>, HINSTANCE@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct IXMLDOMElement *, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e3b0`
- `0x18001e520`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x180006f80`
- `0x18001c514`
- `0x180021dfc`
- `0x180023010`

## string_xrefs

- `0x18001c53d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001c5de`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall CreateStandardInputBinOption(
        struct NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct IXMLDOMElement *a6,
        struct IXMLDOMElement **a7)
{
  struct IXMLDOMElementVtbl *lpVtbl; // r9
  const unsigned __int16 *v12; // r8
  int v13; // eax
  struct publicdm::BinMappingEntry *v14; // r9
  int v15; // ebx
  int v16; // eax
  HINSTANCE lpVtbl_low; // r9
  struct IXMLDOMElement *v18; // rdx
  struct IXMLDOMElement *v20; // [rsp+98h] [rbp+10h] BYREF

  v20 = 0;
  lpVtbl = a2[2].lpVtbl;
  if ( lpVtbl )
  {
    v12 = a5;
    if ( HIDWORD(a2->lpVtbl) != 1 )
      v12 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
    v13 = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(this, a6, v12, (const unsigned __int16 *)lpVtbl, &v20);
  }
  else
  {
    v13 = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
            (__int64 **)this,
            a6,
            (struct IXMLDOMElement *)L"Option",
            0,
            &v20);
  }
  v15 = v13;
  if ( v13 >= 0 )
  {
    v15 = publicdm::WriteInputBinProperties(this, v20, a2, v14);
    if ( v15 >= 0 )
    {
      if ( *((_DWORD *)this + 9) )
      {
        if ( a4 )
        {
          v16 = (*(__int64 (__fastcall **)(struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, const unsigned __int16 *, _DWORD, const char *, const char *, _QWORD))(*(_QWORD *)this + 8LL))(
                  this,
                  v20,
                  L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                  L"DisplayName",
                  a4,
                  0,
                  L"http://www.w3.org/2001/XMLSchema",
                  L"string",
                  0);
          goto LABEL_14;
        }
        lpVtbl_low = (HINSTANCE)LODWORD(a2[1].lpVtbl);
        if ( (_DWORD)lpVtbl_low && a3 )
        {
          v16 = publicdm::WriteDisplayNameFromResourceString(
                  this,
                  (struct NPrintTicketUtil::CPrintTicketWrapper *)v20,
                  a3,
                  lpVtbl_low);
LABEL_14:
          v15 = v16;
          if ( v16 < 0 )
            goto LABEL_19;
        }
      }
      if ( a7 )
      {
        v18 = 0;
        if ( v20 )
        {
          v18 = v20;
          v20 = 0;
        }
        *a7 = v18;
      }
    }
  }
LABEL_19:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v20);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001c514  mov     r11, rsp
0x18001c517  push    rbx
0x18001c518  push    rbp
0x18001c519  push    rsi
0x18001c51a  push    rdi
0x18001c51b  push    r12
0x18001c51d  push    r14
0x18001c51f  sub     rsp, 58h
0x18001c523  mov     r14, r9
0x18001c526  mov     qword ptr [r11+10h], 0
0x18001c52e  mov     r9, [rdx+10h]; unsigned __int16 *
0x18001c532  lea     rax, [r11+10h]
0x18001c536  mov     [r11-68h], rax
0x18001c53a  mov     rbp, r8
0x18001c53d  lea     r12, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001c544  mov     rsi, rdx
0x18001c547  mov     rdi, rcx
0x18001c54a  test    r9, r9
0x18001c54d  jz      short loc_18001C56E
0x18001c54f  cmp     dword ptr [rdx+4], 1
0x18001c553  mov     r8, [rsp+88h+arg_20]
0x18001c55b  mov     rdx, [rsp+88h+arg_28]; struct IXMLDOMElement *
0x18001c563  cmovnz  r8, r12; unsigned __int16 *
0x18001c567  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c56c  jmp     short loc_18001C582
0x18001c56e  mov     rdx, [rsp+88h+arg_28]; struct IXMLDOMElement *
0x18001c576  lea     r8, aOption; "Option"
0x18001c57d  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c582  mov     ebx, eax
0x18001c584  test    eax, eax
0x18001c586  js      loc_18001C65A
0x18001c58c  mov     rdx, [rsp+88h+arg_8]; struct IXMLDOMElement *
0x18001c594  mov     r8, rsi; struct IXMLDOMElement *
0x18001c597  mov     rcx, rdi; this
0x18001c59a  call    ?WriteInputBinProperties@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUBinMappingEntry@1@@Z; publicdm::WriteInputBinProperties(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::BinMappingEntry *)
0x18001c59f  mov     ebx, eax
0x18001c5a1  test    eax, eax
0x18001c5a3  js      loc_18001C65A
0x18001c5a9  cmp     dword ptr [rdi+24h], 0
0x18001c5ad  jz      short loc_18001C62C
0x18001c5af  test    r14, r14
0x18001c5b2  jz      short loc_18001C605
0x18001c5b4  mov     rax, [rdi]
0x18001c5b7  lea     rcx, aString; "string"
0x18001c5be  mov     rdx, [rsp+88h+arg_8]
0x18001c5c6  lea     r9, aDisplayname; "DisplayName"
0x18001c5cd  mov     [rsp+88h+var_48], 0
0x18001c5d6  mov     r8, r12
0x18001c5d9  mov     [rsp+88h+var_50], rcx
0x18001c5de  lea     rcx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001c5e5  mov     rax, [rax+8]
0x18001c5e9  mov     [rsp+88h+var_58], rcx
0x18001c5ee  mov     rcx, rdi
0x18001c5f1  mov     [rsp+88h+var_60], 0
0x18001c5f9  mov     [rsp+88h+var_68], r14
0x18001c5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c603  jmp     short loc_18001C626
0x18001c605  mov     r9d, [rsi+8]; HINSTANCE
0x18001c609  test    r9d, r9d
0x18001c60c  jz      short loc_18001C62C
0x18001c60e  test    rbp, rbp
0x18001c611  jz      short loc_18001C62C
0x18001c613  mov     rdx, [rsp+88h+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c61b  mov     r8, rbp; struct IXMLDOMElement *
0x18001c61e  mov     rcx, rdi; this
0x18001c621  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c626  mov     ebx, eax
0x18001c628  test    eax, eax
0x18001c62a  js      short loc_18001C65A
0x18001c62c  mov     rcx, [rsp+88h+arg_30]
0x18001c634  test    rcx, rcx
0x18001c637  jz      short loc_18001C65A
0x18001c639  mov     rax, [rsp+88h+arg_8]
0x18001c641  xor     edx, edx
0x18001c643  test    rax, rax
0x18001c646  jz      short loc_18001C657
0x18001c648  mov     rdx, rax
0x18001c64b  mov     [rsp+88h+arg_8], 0
0x18001c657  mov     [rcx], rdx
0x18001c65a  lea     rcx, [rsp+88h+arg_8]
0x18001c662  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c667  mov     eax, ebx
0x18001c669  add     rsp, 58h
0x18001c66d  pop     r14
0x18001c66f  pop     r12
0x18001c671  pop     rdi
0x18001c672  pop     rsi
0x18001c673  pop     rbp
0x18001c674  pop     rbx
0x18001c675  retn
```
