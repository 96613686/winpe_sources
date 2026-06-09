# NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)

- ea: `0x18001c37c`
- end: `0x18001c464`
- name: `?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z`
- size: `232`
- prototype: `int(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, struct IXMLDOMElement **)`
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006130`
- `0x1800077f0`
- `0x18000e084`
- `0x18001beb8`
- `0x18001c060`
- `0x18001ca28`
- `0x180020710`
- `0x180020bd0`
- `0x180021dfc`
- `0x180021f4c`

## callees

- `0x1800056e0`
- `0x1800070e0`
- `0x18001c37c`
- `0x180023010`

## string_xrefs

- `0x18001c409`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IXMLDOMElement *a6,
        int a7,
        struct IXMLDOMElement **a8)
{
  struct IXMLDOMElement *v10; // rbx
  int QName; // esi
  unsigned __int16 **v14; // [rsp+28h] [rbp-50h]
  const unsigned __int16 *v15; // [rsp+30h] [rbp-48h]

  a8 = 0;
  v10 = a2;
  if ( a5 && a6 )
  {
    if ( !a2 )
      v10 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
    QName = NPrintTicketUtil::CreateQName(this, v10, a6, a5, (const unsigned __int16 *)&a8, v14, v15);
    if ( QName >= 0 )
      QName = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **, int, const char *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
                this,
                v10,
                a3,
                a4,
                a8,
                a7,
                L"http://www.w3.org/2001/XMLSchema",
                L"QName",
                0);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&a8);
    return (unsigned int)QName;
  }
  else
  {
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&a8);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001c37c  mov     rax, rsp
0x18001c37f  push    rbx
0x18001c380  push    rbp
0x18001c381  push    rsi
0x18001c382  push    rdi
0x18001c383  push    r14
0x18001c385  sub     rsp, 50h
0x18001c389  mov     rbp, r9
0x18001c38c  mov     qword ptr [rax+40h], 0
0x18001c394  mov     r9, [rsp+78h+arg_20]; unsigned __int16 *
0x18001c39c  mov     r14, r8
0x18001c39f  mov     rbx, rdx
0x18001c3a2  mov     rdi, rcx
0x18001c3a5  test    r9, r9
0x18001c3a8  jz      loc_18001C447
0x18001c3ae  mov     r8, [rsp+78h+arg_28]; struct IXMLDOMElement *
0x18001c3b6  test    r8, r8
0x18001c3b9  jz      loc_18001C447
0x18001c3bf  test    rdx, rdx
0x18001c3c2  jnz     short loc_18001C3C8
0x18001c3c4  mov     rbx, [rcx+18h]
0x18001c3c8  lea     rax, [rsp+78h+arg_38]
0x18001c3d0  mov     rdx, rbx; struct IXMLDOMElement *
0x18001c3d3  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18001c3d8  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18001c3dd  mov     esi, eax
0x18001c3df  test    eax, eax
0x18001c3e1  js      short loc_18001C436
0x18001c3e3  mov     rax, [rdi]
0x18001c3e6  lea     rcx, aQname; "QName"
0x18001c3ed  mov     rdx, [rsp+78h+arg_38]
0x18001c3f5  mov     r9, rbp
0x18001c3f8  mov     [rsp+78h+var_38], 0
0x18001c401  mov     r8, r14
0x18001c404  mov     [rsp+78h+var_40], rcx
0x18001c409  lea     rcx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001c410  mov     rax, [rax+8]
0x18001c414  mov     [rsp+78h+var_48], rcx
0x18001c419  mov     ecx, [rsp+78h+arg_30]
0x18001c420  mov     dword ptr [rsp+78h+var_50], ecx
0x18001c424  mov     rcx, rdi
0x18001c427  mov     [rsp+78h+var_58], rdx
0x18001c42c  mov     rdx, rbx
0x18001c42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c434  mov     esi, eax
0x18001c436  lea     rcx, [rsp+78h+arg_38]
0x18001c43e  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001c443  mov     eax, esi
0x18001c445  jmp     short loc_18001C459
0x18001c447  lea     rcx, [rsp+78h+arg_38]
0x18001c44f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001c454  mov     eax, 80070057h
0x18001c459  add     rsp, 50h
0x18001c45d  pop     r14
0x18001c45f  pop     rdi
0x18001c460  pop     rsi
0x18001c461  pop     rbp
0x18001c462  pop     rbx
0x18001c463  retn
```
