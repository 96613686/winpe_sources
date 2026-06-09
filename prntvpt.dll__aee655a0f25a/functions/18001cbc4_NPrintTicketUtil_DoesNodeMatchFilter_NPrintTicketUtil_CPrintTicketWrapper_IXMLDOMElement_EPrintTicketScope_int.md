# NPrintTicketUtil::DoesNodeMatchFilter(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,EPrintTicketScope,int *)

- ea: `0x18001cbc4`
- end: `0x18001ccc1`
- name: `?DoesNodeMatchFilter@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@W4EPrintTicketScope@@PEAH@Z`
- size: `253`
- prototype: `__int64 __fastcall(NPrintTicketUtil *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, enum EPrintTicketScope, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bbf0`
- `0x18001d270`
- `0x18001f850`

## callees

- `0x180004b00`
- `0x1800056e0`
- `0x18001cbc4`
- `0x1800225a0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001cc14`
- `OLEAUT32!__imp_SysStringLen` at `0x18001cc14`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::DoesNodeMatchFilter(
        NPrintTicketUtil *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        _DWORD *a4)
{
  int v5; // ebp
  int NameAttribute; // esi
  unsigned __int16 *v8[3]; // [rsp+30h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v5 = (int)a3;
  pbstr = 0;
  v8[0] = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, a2, v8, &pbstr, 0);
  if ( NameAttribute >= 0 && SysStringLen(pbstr) )
  {
    if ( !wcsncmp_0(pbstr, L"Job", 3u) )
    {
      *a4 = v5 == 2;
    }
    else if ( !wcsncmp_0(pbstr, L"Document", 8u) )
    {
      *a4 = (unsigned int)(v5 - 1) <= 1;
    }
    else if ( !wcsncmp_0(pbstr, L"Page", 4u) )
    {
      *a4 = 1;
    }
    else
    {
      *a4 = 0;
      NameAttribute = -2147418113;
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v8);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&pbstr);
  return (unsigned int)NameAttribute;
}

```

## disassembly

```asm
0x18001cbc4  mov     rax, rsp
0x18001cbc7  mov     [rax+8], rbx
0x18001cbcb  mov     [rax+10h], rbp
0x18001cbcf  push    rsi
0x18001cbd0  sub     rsp, 40h
0x18001cbd4  mov     rbx, r9
0x18001cbd7  mov     dword ptr [r9], 0
0x18001cbde  mov     ebp, r8d
0x18001cbe1  mov     qword ptr [rax+20h], 0
0x18001cbe9  lea     r9, [rax+20h]; unsigned __int16 **
0x18001cbed  mov     qword ptr [rax-18h], 0
0x18001cbf5  lea     r8, [rax-18h]; unsigned __int16 **
0x18001cbf9  mov     dword ptr [rax-28h], 0
0x18001cc00  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001cc05  mov     esi, eax
0x18001cc07  test    eax, eax
0x18001cc09  js      loc_18001CC9B
0x18001cc0f  mov     rcx, [rsp+48h+pbstr]; pbstr
0x18001cc14  call    cs:__imp_SysStringLen
0x18001cc1a  test    eax, eax
0x18001cc1c  jz      short loc_18001CC9B
0x18001cc1e  mov     rcx, [rsp+48h+pbstr]; String1
0x18001cc23  lea     rdx, aJob; "Job"
0x18001cc2a  mov     r8d, 3; MaxCount
0x18001cc30  call    wcsncmp_0
0x18001cc35  test    eax, eax
0x18001cc37  jnz     short loc_18001CC43
0x18001cc39  cmp     ebp, 2
0x18001cc3c  setz    al
0x18001cc3f  mov     [rbx], eax
0x18001cc41  jmp     short loc_18001CC9B
0x18001cc43  mov     rcx, [rsp+48h+pbstr]; String1
0x18001cc48  lea     rdx, aDocument; "Document"
0x18001cc4f  mov     r8d, 8; MaxCount
0x18001cc55  call    wcsncmp_0
0x18001cc5a  test    eax, eax
0x18001cc5c  jnz     short loc_18001CC6D
0x18001cc5e  xor     ecx, ecx
0x18001cc60  lea     eax, [rbp-1]
0x18001cc63  cmp     eax, 1
0x18001cc66  setbe   cl
0x18001cc69  mov     [rbx], ecx
0x18001cc6b  jmp     short loc_18001CC9B
0x18001cc6d  mov     rcx, [rsp+48h+pbstr]; String1
0x18001cc72  lea     rdx, aPage; "Page"
0x18001cc79  mov     r8d, 4; MaxCount
0x18001cc7f  call    wcsncmp_0
0x18001cc84  test    eax, eax
0x18001cc86  jnz     short loc_18001CC90
0x18001cc88  mov     dword ptr [rbx], 1
0x18001cc8e  jmp     short loc_18001CC9B
0x18001cc90  mov     dword ptr [rbx], 0
0x18001cc96  mov     esi, 8000FFFFh
0x18001cc9b  lea     rcx, [rsp+48h+var_18]
0x18001cca0  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001cca5  lea     rcx, [rsp+48h+pbstr]
0x18001ccaa  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001ccaf  mov     rbx, [rsp+48h+arg_0]
0x18001ccb4  mov     eax, esi
0x18001ccb6  mov     rbp, [rsp+48h+arg_8]
0x18001ccbb  add     rsp, 40h
0x18001ccbf  pop     rsi
0x18001ccc0  retn
```
