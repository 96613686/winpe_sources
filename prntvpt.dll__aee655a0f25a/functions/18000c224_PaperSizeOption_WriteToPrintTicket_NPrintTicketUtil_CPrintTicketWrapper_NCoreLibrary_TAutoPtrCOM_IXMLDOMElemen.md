# PaperSizeOption::WriteToPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &)

- ea: `0x18000c224`
- end: `0x18000c372`
- name: `?WriteToPrintTicket@PaperSizeOption@@QEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@@Z`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be14`
- `0x18001f550`

## callees

- `0x180006c74`
- `0x180006f80`
- `0x18000b0a0`
- `0x18000c224`
- `0x180023010`

## string_xrefs

- `0x18000c29c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18000c2cc`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18000c317`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18000c31e`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall PaperSizeOption::WriteToPrintTicket(
        __int64 a1,
        NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement **a3)
{
  const unsigned __int16 *v3; // r9
  const unsigned __int16 *v7; // r8
  int v8; // eax
  int Property; // ebx
  __int64 v10; // rcx
  struct IXMLDOMElement **v12; // [rsp+30h] [rbp-28h]
  struct IXMLDOMElement **v13; // [rsp+30h] [rbp-28h]
  struct IXMLDOMElement *v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = *(const unsigned __int16 **)a1;
  v14 = 0;
  if ( v3 && (v7 = *(const unsigned __int16 **)(a1 + 8)) != 0 )
    v8 = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(a2, *a3, v7, v3, &v14);
  else
    v8 = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(a2, *a3, L"Option", v3, &v14);
  Property = v8;
  if ( v8 >= 0 )
  {
    Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                 a2,
                 v14,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"MediaSizeWidth",
                 *(_DWORD *)(a1 + 24),
                 1,
                 v12);
    if ( Property >= 0 )
      Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                   a2,
                   v14,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"MediaSizeHeight",
                   *(_DWORD *)(a1 + 28),
                   1,
                   v13);
  }
  v10 = *(_QWORD *)(a1 + 16);
  if ( v10 && *((_DWORD *)a2 + 9) )
    Property = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, __int64, _DWORD, const char *, const char *, _QWORD))(*(_QWORD *)a2 + 8LL))(
                 a2,
                 v14,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"DisplayName",
                 v10,
                 0,
                 L"http://www.w3.org/2001/XMLSchema",
                 L"string",
                 0);
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v14->lpVtbl->Release)(v14);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18000c224  mov     r11, rsp
0x18000c227  mov     [r11+10h], rbx
0x18000c22b  mov     [r11+18h], rsi
0x18000c22f  push    rdi
0x18000c230  sub     rsp, 50h
0x18000c234  mov     r9, [rcx]; unsigned __int16 *
0x18000c237  mov     rax, r8
0x18000c23a  mov     qword ptr [r11+8], 0
0x18000c242  mov     rsi, rdx
0x18000c245  mov     rdi, rcx
0x18000c248  test    r9, r9
0x18000c24b  jz      short loc_18000C26B
0x18000c24d  mov     r8, [rcx+8]; unsigned __int16 *
0x18000c251  test    r8, r8
0x18000c254  jz      short loc_18000C26B
0x18000c256  mov     rdx, [rax]; struct IXMLDOMElement *
0x18000c259  lea     rcx, [r11+8]
0x18000c25d  mov     [r11-38h], rcx
0x18000c261  mov     rcx, rsi; this
0x18000c264  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000c269  jmp     short loc_18000C287
0x18000c26b  mov     rdx, [rax]; struct IXMLDOMElement *
0x18000c26e  lea     rcx, [rsp+58h+arg_0]
0x18000c273  mov     [rsp+58h+var_38], rcx; struct IXMLDOMElement **
0x18000c278  lea     r8, aOption; "Option"
0x18000c27f  mov     rcx, rsi; this
0x18000c282  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000c287  mov     ebx, eax
0x18000c289  test    eax, eax
0x18000c28b  js      short loc_18000C2E9
0x18000c28d  mov     eax, [rdi+18h]
0x18000c290  lea     r9, aMediasizewidth; "MediaSizeWidth"
0x18000c297  mov     rdx, [rsp+58h+arg_0]; struct IXMLDOMElement *
0x18000c29c  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000c2a3  mov     [rsp+58h+var_30], 1; int
0x18000c2ab  mov     rcx, rsi; this
0x18000c2ae  mov     dword ptr [rsp+58h+var_38], eax; int
0x18000c2b2  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18000c2b7  mov     ebx, eax
0x18000c2b9  test    eax, eax
0x18000c2bb  js      short loc_18000C2E9
0x18000c2bd  mov     eax, [rdi+1Ch]
0x18000c2c0  lea     r9, aMediasizeheigh; "MediaSizeHeight"
0x18000c2c7  mov     rdx, [rsp+58h+arg_0]; struct IXMLDOMElement *
0x18000c2cc  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000c2d3  mov     [rsp+58h+var_30], 1; int
0x18000c2db  mov     rcx, rsi; this
0x18000c2de  mov     dword ptr [rsp+58h+var_38], eax; int
0x18000c2e2  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18000c2e7  mov     ebx, eax
0x18000c2e9  mov     rcx, [rdi+10h]
0x18000c2ed  test    rcx, rcx
0x18000c2f0  jz      short loc_18000C34A
0x18000c2f2  cmp     dword ptr [rsi+24h], 0
0x18000c2f6  jz      short loc_18000C34A
0x18000c2f8  mov     rax, [rsi]
0x18000c2fb  lea     rdx, aString; "string"
0x18000c302  mov     [rsp+58h+var_18], 0
0x18000c30b  lea     r9, aDisplayname; "DisplayName"
0x18000c312  mov     [rsp+58h+var_20], rdx
0x18000c317  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000c31e  lea     rdx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18000c325  mov     rax, [rax+8]
0x18000c329  mov     [rsp+58h+var_28], rdx
0x18000c32e  mov     rdx, [rsp+58h+arg_0]
0x18000c333  mov     [rsp+58h+var_30], 0
0x18000c33b  mov     [rsp+58h+var_38], rcx
0x18000c340  mov     rcx, rsi
0x18000c343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c348  mov     ebx, eax
0x18000c34a  mov     rcx, [rsp+58h+arg_0]
0x18000c34f  test    rcx, rcx
0x18000c352  jz      short loc_18000C360
0x18000c354  mov     rax, [rcx]
0x18000c357  mov     rax, [rax+10h]
0x18000c35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c360  mov     rsi, [rsp+58h+arg_10]
0x18000c365  mov     eax, ebx
0x18000c367  mov     rbx, [rsp+58h+arg_8]
0x18000c36c  add     rsp, 50h
0x18000c370  pop     rdi
0x18000c371  retn
```
