# NPrintTicketUtil::DoesNodeMatchFilterPageScope(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,int *)

- ea: `0x18001ccc8`
- end: `0x18001cdc7`
- name: `?DoesNodeMatchFilterPageScope@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAH@Z`
- size: `255`
- prototype: `__int64 __fastcall(NPrintTicketUtil *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d270`

## callees

- `0x180004b00`
- `0x1800056e0`
- `0x18001ccc8`
- `0x1800225a0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001cd11`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cd11`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::DoesNodeMatchFilterPageScope(
        NPrintTicketUtil *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        int *a4)
{
  int NameAttribute; // esi
  BSTR pbstr; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *v8; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(a3->lpVtbl) = 0;
  pbstr = 0;
  v8 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, a2, &v8, &pbstr, 0);
  if ( NameAttribute >= 0 && SysStringLen(pbstr) )
  {
    if ( !wcsncmp_0(pbstr, L"JobInputBin", 0xBu) || !wcsncmp_0(pbstr, L"Page", 4u) )
    {
      LODWORD(a3->lpVtbl) = 1;
    }
    else if ( !wcsncmp_0(pbstr, L"Job", 3u) || !wcsncmp_0(pbstr, L"Document", 8u) )
    {
      LODWORD(a3->lpVtbl) = 0;
    }
    else
    {
      LODWORD(a3->lpVtbl) = 0;
      NameAttribute = -2147418113;
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v8);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&pbstr);
  return (unsigned int)NameAttribute;
}

```

## disassembly

```asm
0x18001ccc8  mov     rax, rsp
0x18001cccb  mov     [rax+8], rsi
0x18001cccf  push    rdi
0x18001ccd0  sub     rsp, 30h
0x18001ccd4  mov     rdi, r8
0x18001ccd7  mov     dword ptr [r8], 0
0x18001ccde  lea     r8, [rax+20h]; unsigned __int16 **
0x18001cce2  mov     qword ptr [rax+18h], 0
0x18001ccea  lea     r9, [rax+18h]; unsigned __int16 **
0x18001ccee  mov     qword ptr [rax+20h], 0
0x18001ccf6  mov     dword ptr [rax-18h], 0
0x18001ccfd  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001cd02  mov     esi, eax
0x18001cd04  test    eax, eax
0x18001cd06  js      loc_18001CDA6
0x18001cd0c  mov     rcx, [rsp+38h+pbstr]; pbstr
0x18001cd11  call    cs:__imp_SysStringLen
0x18001cd17  test    eax, eax
0x18001cd19  jz      loc_18001CDA6
0x18001cd1f  mov     rcx, [rsp+38h+pbstr]; String1
0x18001cd24  lea     rdx, aJobinputbin; "JobInputBin"
0x18001cd2b  mov     r8d, 0Bh; MaxCount
0x18001cd31  call    wcsncmp_0
0x18001cd36  test    eax, eax
0x18001cd38  jz      short loc_18001CDA0
0x18001cd3a  mov     rcx, [rsp+38h+pbstr]; String1
0x18001cd3f  lea     rdx, aPage; "Page"
0x18001cd46  mov     r8d, 4; MaxCount
0x18001cd4c  call    wcsncmp_0
0x18001cd51  test    eax, eax
0x18001cd53  jz      short loc_18001CDA0
0x18001cd55  mov     rcx, [rsp+38h+pbstr]; String1
0x18001cd5a  lea     rdx, aJob; "Job"
0x18001cd61  mov     r8d, 3; MaxCount
0x18001cd67  call    wcsncmp_0
0x18001cd6c  test    eax, eax
0x18001cd6e  jz      short loc_18001CD98
0x18001cd70  mov     rcx, [rsp+38h+pbstr]; String1
0x18001cd75  lea     rdx, aDocument; "Document"
0x18001cd7c  mov     r8d, 8; MaxCount
0x18001cd82  call    wcsncmp_0
0x18001cd87  test    eax, eax
0x18001cd89  jz      short loc_18001CD98
0x18001cd8b  mov     dword ptr [rdi], 0
0x18001cd91  mov     esi, 8000FFFFh
0x18001cd96  jmp     short loc_18001CDA6
0x18001cd98  mov     dword ptr [rdi], 0
0x18001cd9e  jmp     short loc_18001CDA6
0x18001cda0  mov     dword ptr [rdi], 1
0x18001cda6  lea     rcx, [rsp+38h+arg_18]
0x18001cdab  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001cdb0  lea     rcx, [rsp+38h+pbstr]
0x18001cdb5  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001cdba  mov     eax, esi
0x18001cdbc  mov     rsi, [rsp+38h+arg_0]
0x18001cdc1  add     rsp, 30h
0x18001cdc5  pop     rdi
0x18001cdc6  retn
```
