# ViewerFactory::NotifyEvent(IXMLNodeSource *,__MIDL___MIDL_itf_xmlparser_0000_0000_0006)

- ea: `0x1800e6310`
- end: `0x1800e66d7`
- name: `?NotifyEvent@ViewerFactory@@UEAAJPEAUIXMLNodeSource@@W4__MIDL___MIDL_itf_xmlparser_0000_0000_0006@@@Z`
- size: `967`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003cbc0`
- `0x1800e5730`
- `0x1800e6310`
- `0x1800e67a0`
- `0x1800e77c8`
- `0x1800e7a1c`
- `0x1800e7b54`
- `0x1800e7e68`
- `0x1800e825c`
- `0x1800e831c`
- `0x180102cde`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e6455`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e6455`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e644a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e644a`
- `OLEAUT32!__imp_VariantInit` at `0x1800e63f1`
- `OLEAUT32!__imp_VariantInit` at `0x1800e63f1`
- `OLEAUT32!__imp_VariantClear` at `0x1800e6467`
- `OLEAUT32!__imp_VariantClear` at `0x1800e6485`
- `OLEAUT32!__imp_VariantClear` at `0x1800e6467`
- `OLEAUT32!__imp_VariantClear` at `0x1800e6485`

## string_xrefs

- `0x1800e6524`: `<XML:NAMESPACE prefix='XMV'/>`

## pseudocode

```c
__int64 __fastcall ViewerFactory::NotifyEvent(__int64 *a1, struct IXMLNodeSource *a2, int a3)
{
  __int64 v3; // rax
  int DOMDocument10; // ebp
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  __int64 v11; // rcx
  OLECHAR *v12; // rcx
  ViewerFactory *v13; // rcx
  __int64 v14; // rcx
  bool v15; // zf
  struct IXMLDOMDocument2 **v16; // rbx
  struct IXMLDOMDocument2 *v17; // rdx
  ViewerFactory *v18; // rcx
  ViewerFactory *v19; // rcx
  int SS; // eax
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF

  v3 = *a1;
  DOMDocument10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  (*(void (__fastcall **)(__int64 *))(v3 + 8))(a1);
  a1[17] = (__int64)a2;
  if ( *((_BYTE *)a1 + 199) )
  {
    if ( !a3 )
      goto LABEL_13;
    DOMDocument10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a1[11] + 24LL))(
                      a1[11],
                      (unsigned __int64)(a1 + 4) & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64),
                      (unsigned int)a3);
    if ( DOMDocument10 < 0 )
      goto LABEL_55;
  }
  if ( a3 > 5 )
  {
    v21 = a3 - 6;
    if ( !v21 )
    {
      ++*((_DWORD *)a1 + 47);
      goto LABEL_55;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      --*((_DWORD *)a1 + 47);
      goto LABEL_55;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v24 = *((_DWORD *)a1 + 51);
      if ( !v24 )
      {
        if ( *((_DWORD *)a1 + 38) == 1 )
        {
          ViewerFactory::CSSWrite((ViewerFactory *)a1, L"</html:body>", 0);
          ViewerFactory::CSSWrite((ViewerFactory *)a1, L"</html:html>", 0);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1[10] + 64LL))(a1[10], 0);
        }
        else
        {
          DOMDocument10 = ViewerFactory::processXSLAsync((ViewerFactory *)a1, a2, 1);
        }
        if ( DOMDocument10 >= 0 )
          goto LABEL_55;
        v24 = DOMDocument10;
      }
      ViewerFactory::reportError((ViewerFactory *)a1, v24, 0);
      goto LABEL_55;
    }
    if ( v23 != 1 )
      goto LABEL_55;
    v15 = *((_DWORD *)a1 + 18) == 0;
    goto LABEL_44;
  }
  if ( a3 == 5 )
  {
    if ( *((_DWORD *)a1 + 38) == 1 )
    {
      ViewerFactory::CSSWrite((ViewerFactory *)a1, L"<XML:NAMESPACE prefix='XMV'/>", 0);
      ViewerFactory::CSSWrite((ViewerFactory *)a1, L"</html:head>", 0);
      *((_BYTE *)a1 + 198) = 0;
      *((_BYTE *)a1 + 200) = 1;
      ViewerFactory::CSSWrite((ViewerFactory *)a1, L"<html:body>", 0);
      *(_BYTE *)(a1[10] + 41) = 1;
      goto LABEL_55;
    }
    v16 = (struct IXMLDOMDocument2 **)(a1 + 16);
    *((_BYTE *)a1 + 198) = 0;
    v17 = (struct IXMLDOMDocument2 *)a1[16];
    if ( !v17 )
    {
      DOMDocument10 = CreateDOMDocument10(&IID_IXMLDOMDocument2, (void **)a1 + 16);
      if ( DOMDocument10 < 0 )
        goto LABEL_55;
      DOMDocument10 = ViewerFactory::setSecurity(v18, (struct IXMLDOMDocument2 *)a1[12], *v16);
      if ( DOMDocument10 < 0 )
        goto LABEL_55;
      v17 = *v16;
    }
    v19 = (ViewerFactory *)*((unsigned int *)a1 + 38);
    if ( !(_DWORD)v19 )
    {
      v19 = (ViewerFactory *)*((unsigned int *)a1 + 42);
      if ( !(_DWORD)v19 )
        goto LABEL_37;
      a1[20] = a1[22];
      *((_DWORD *)a1 + 38) = (_DWORD)v19;
    }
    if ( (_DWORD)v19 == 2 )
    {
      SS = ViewerFactory::loadSS((ViewerFactory *)a1, v17, a2);
LABEL_38:
      DOMDocument10 = SS;
      goto LABEL_55;
    }
LABEL_37:
    *((_DWORD *)a1 + 38) = 2;
    SS = ViewerFactory::loadSSDefault(v19, v17);
    goto LABEL_38;
  }
  if ( !a3 )
  {
LABEL_13:
    DOMDocument10 = ViewerFactory::setGenericParse((ViewerFactory *)a1, -1);
    if ( DOMDocument10 < 0 )
      goto LABEL_55;
    *((_DWORD *)a1 + 51) = 0;
    VariantInit(&pvarg);
    v11 = a1[14];
    if ( v11 )
      DOMDocument10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v11 + 24LL))(
                        v11,
                        L"msoXSLUrl",
                        &pvarg,
                        0);
    if ( !DOMDocument10 && pvarg.vt == 8 && pvarg.llVal && *pvarg.bstrVal )
    {
      v12 = (OLECHAR *)a1[20];
      *((_DWORD *)a1 + 38) = 2;
      SysFreeString(v12);
      a1[20] = (__int64)SysAllocString(pvarg.bstrVal);
      VariantClear(&pvarg);
      if ( !a1[20] )
      {
        DOMDocument10 = -2147024882;
        goto LABEL_55;
      }
    }
    else
    {
      VariantClear(&pvarg);
    }
    DOMDocument10 = CreateDOMDocument10(&IID_IXMLDOMDocument2, (void **)a1 + 16);
    if ( DOMDocument10 < 0 )
      goto LABEL_55;
    DOMDocument10 = ViewerFactory::setSecurity(
                      v13,
                      (struct IXMLDOMDocument2 *)a1[12],
                      (struct IXMLDOMDocument2 *)a1[16]);
    if ( DOMDocument10 < 0 )
      goto LABEL_55;
    memset_0((char *)a1 + 236, 0, 0x7Cu);
    v14 = a1[7];
    *((_DWORD *)a1 + 58) = 128;
    (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v14 + 64LL))(v14, (__int64)a1 + 228, a1 + 29);
    *((_DWORD *)a1 + 57) &= 0xFFFFDFEF;
    v15 = (unsigned int)ViewerFactory::StartAsync(a1, a2, 0) == 0;
LABEL_44:
    if ( !v15 )
      DOMDocument10 = -2147483638;
    goto LABEL_55;
  }
  v8 = a3 - 1;
  if ( !v8 )
    goto LABEL_12;
  v9 = v8 - 1;
  if ( !v9 )
  {
LABEL_11:
    --*((_DWORD *)a1 + 46);
    goto LABEL_55;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_12:
    ++*((_DWORD *)a1 + 46);
    *((_BYTE *)a1 + 192) = 0;
    goto LABEL_55;
  }
  if ( v10 == 1 )
    goto LABEL_11;
LABEL_55:
  (*(void (__fastcall **)(__int64 *))(*a1 + 16))(a1);
  return (unsigned int)DOMDocument10;
}

```

## disassembly

```asm
0x1800e6310  push    rbx
0x1800e6312  push    rbp
0x1800e6313  push    rsi
0x1800e6314  push    rdi
0x1800e6315  push    r14
0x1800e6317  push    r15
0x1800e6319  sub     rsp, 58h
0x1800e631d  xor     eax, eax
0x1800e631f  xorps   xmm0, xmm0
0x1800e6322  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1800e6327  xor     r15d, r15d
0x1800e632a  mov     rax, [rcx]
0x1800e632d  mov     ebx, r8d
0x1800e6330  mov     r14, rdx
0x1800e6333  mov     rsi, rcx
0x1800e6336  mov     ebp, r15d
0x1800e6339  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1800e633e  mov     rax, [rax+8]
0x1800e6342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6347  mov     [rsi+88h], r14
0x1800e634e  cmp     [rsi+0C7h], r15b
0x1800e6355  jz      short loc_1800E6388
0x1800e6357  test    ebx, ebx
0x1800e6359  jz      short loc_1800E63D0
0x1800e635b  mov     rcx, [rsi+58h]
0x1800e635f  lea     r8, [rsi+20h]
0x1800e6363  mov     rax, rsi
0x1800e6366  neg     rax
0x1800e6369  mov     r9, [rcx]
0x1800e636c  sbb     rdx, rdx
0x1800e636f  and     rdx, r8
0x1800e6372  mov     r8d, ebx
0x1800e6375  mov     rax, [r9+18h]
0x1800e6379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e637e  mov     ebp, eax
0x1800e6380  test    eax, eax
0x1800e6382  js      loc_1800E66B9
0x1800e6388  cmp     ebx, 5
0x1800e638b  jg      loc_1800E660A
0x1800e6391  jz      loc_1800E6518
0x1800e6397  test    ebx, ebx
0x1800e6399  jz      short loc_1800E63D0
0x1800e639b  sub     ebx, 1
0x1800e639e  jz      short loc_1800E63BE
0x1800e63a0  sub     ebx, 1
0x1800e63a3  jz      short loc_1800E63B3
0x1800e63a5  sub     ebx, 1
0x1800e63a8  jz      short loc_1800E63BE
0x1800e63aa  cmp     ebx, 1
0x1800e63ad  jnz     loc_1800E66B9
0x1800e63b3  dec     dword ptr [rsi+0B8h]
0x1800e63b9  jmp     loc_1800E66B9
0x1800e63be  inc     dword ptr [rsi+0B8h]
0x1800e63c4  mov     [rsi+0C0h], r15b
0x1800e63cb  jmp     loc_1800E66B9
0x1800e63d0  or      edx, 0FFFFFFFFh; __int16
0x1800e63d3  mov     rcx, rsi; this
0x1800e63d6  call    ?setGenericParse@ViewerFactory@@QEAAJF@Z; ViewerFactory::setGenericParse(short)
0x1800e63db  mov     ebp, eax
0x1800e63dd  test    eax, eax
0x1800e63df  js      loc_1800E66B9
0x1800e63e5  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800e63ea  mov     [rsi+0CCh], r15d
0x1800e63f1  call    cs:__imp_VariantInit
0x1800e63f7  mov     rcx, [rsi+70h]
0x1800e63fb  test    rcx, rcx
0x1800e63fe  jz      short loc_1800E641D
0x1800e6400  mov     rax, [rcx]
0x1800e6403  lea     r8, [rsp+88h+pvarg]
0x1800e6408  xor     r9d, r9d
0x1800e640b  lea     rdx, aMsoxslurl; "msoXSLUrl"
0x1800e6412  mov     rax, [rax+18h]
0x1800e6416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e641b  mov     ebp, eax
0x1800e641d  test    ebp, ebp
0x1800e641f  jnz     short loc_1800E6480
0x1800e6421  cmp     word ptr [rsp+88h+pvarg], 8
0x1800e6427  jnz     short loc_1800E6480
0x1800e6429  mov     rax, qword ptr [rsp+88h+pvarg+8]
0x1800e642e  test    rax, rax
0x1800e6431  jz      short loc_1800E6480
0x1800e6433  cmp     [rax], r15w
0x1800e6437  jz      short loc_1800E6480
0x1800e6439  mov     rcx, [rsi+0A0h]; bstrString
0x1800e6440  mov     dword ptr [rsi+98h], 2
0x1800e644a  call    cs:__imp_SysFreeString
0x1800e6450  mov     rcx, qword ptr [rsp+88h+pvarg+8]; psz
0x1800e6455  call    cs:__imp_SysAllocString
0x1800e645b  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800e6460  mov     [rsi+0A0h], rax
0x1800e6467  call    cs:__imp_VariantClear
0x1800e646d  cmp     [rsi+0A0h], r15
0x1800e6474  jnz     short loc_1800E648B
0x1800e6476  mov     ebp, 8007000Eh
0x1800e647b  jmp     loc_1800E66B9
0x1800e6480  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800e6485  call    cs:__imp_VariantClear
0x1800e648b  lea     rbx, [rsi+80h]
0x1800e6492  mov     rdx, rbx; void **
0x1800e6495  lea     rcx, IID_IXMLDOMDocument2; struct _GUID *
0x1800e649c  call    ?CreateDOMDocument10@@YAJAEBU_GUID@@PEAPEAX@Z; CreateDOMDocument10(_GUID const &,void * *)
0x1800e64a1  mov     ebp, eax
0x1800e64a3  test    eax, eax
0x1800e64a5  js      loc_1800E66B9
0x1800e64ab  mov     r8, [rbx]; struct IXMLDOMDocument2 *
0x1800e64ae  mov     rdx, [rsi+60h]; struct IXMLDOMDocument2 *
0x1800e64b2  call    ?setSecurity@ViewerFactory@@AEAAJPEAUIXMLDOMDocument2@@0@Z; ViewerFactory::setSecurity(IXMLDOMDocument2 *,IXMLDOMDocument2 *)
0x1800e64b7  mov     ebp, eax
0x1800e64b9  test    eax, eax
0x1800e64bb  js      loc_1800E66B9
0x1800e64c1  xor     edx, edx; Val
0x1800e64c3  lea     rcx, [rsi+0ECh]; void *
0x1800e64ca  lea     rdi, [rsi+0E8h]
0x1800e64d1  lea     r8d, [rdx+7Ch]; Size
0x1800e64d5  call    memset_0
0x1800e64da  mov     rcx, [rsi+38h]
0x1800e64de  lea     rbx, [rsi+0E4h]
0x1800e64e5  mov     dword ptr [rdi], 80h
0x1800e64eb  mov     r8, rdi
0x1800e64ee  mov     rdx, rbx
0x1800e64f1  mov     rax, [rcx]
0x1800e64f4  mov     rax, [rax+40h]
0x1800e64f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e64fd  and     dword ptr [rbx], 0FFFFDFEFh
0x1800e6503  xor     r8d, r8d
0x1800e6506  mov     rdx, r14
0x1800e6509  mov     rcx, rsi
0x1800e650c  call    ?StartAsync@ViewerFactory@@AEAAHPEAUIXMLNodeSource@@W4__MIDL___MIDL_itf_xmlparser_0000_0000_0006@@@Z; ViewerFactory::StartAsync(IXMLNodeSource *,__MIDL___MIDL_itf_xmlparser_0000_0000_0006)
0x1800e6511  test    eax, eax
0x1800e6513  jmp     loc_1800E662E
0x1800e6518  cmp     dword ptr [rsi+98h], 1
0x1800e651f  jnz     short loc_1800E6572
0x1800e6521  xor     r8d, r8d; unsigned int
0x1800e6524  lea     rdx, aXmlNamespacePr; "<XML:NAMESPACE prefix='XMV'/>"
0x1800e652b  mov     rcx, rsi; this
0x1800e652e  call    ?CSSWrite@ViewerFactory@@AEAAXPEBGK@Z; ViewerFactory::CSSWrite(ushort const *,ulong)
0x1800e6533  xor     r8d, r8d; unsigned int
0x1800e6536  lea     rdx, aHtmlHead; "</html:head>"
0x1800e653d  mov     rcx, rsi; this
0x1800e6540  call    ?CSSWrite@ViewerFactory@@AEAAXPEBGK@Z; ViewerFactory::CSSWrite(ushort const *,ulong)
0x1800e6545  xor     r8d, r8d; unsigned int
0x1800e6548  mov     [rsi+0C6h], r15b
0x1800e654f  lea     rdx, aHtmlBody_0; "<html:body>"
0x1800e6556  mov     byte ptr [rsi+0C8h], 1
0x1800e655d  mov     rcx, rsi; this
0x1800e6560  call    ?CSSWrite@ViewerFactory@@AEAAXPEBGK@Z; ViewerFactory::CSSWrite(ushort const *,ulong)
0x1800e6565  mov     rax, [rsi+50h]
0x1800e6569  mov     byte ptr [rax+29h], 1
0x1800e656d  jmp     loc_1800E66B9
0x1800e6572  lea     rbx, [rsi+80h]
0x1800e6579  mov     [rsi+0C6h], r15b
0x1800e6580  mov     rdx, [rbx]
0x1800e6583  test    rdx, rdx
0x1800e6586  jnz     short loc_1800E65BA
0x1800e6588  mov     rdx, rbx; void **
0x1800e658b  lea     rcx, IID_IXMLDOMDocument2; struct _GUID *
0x1800e6592  call    ?CreateDOMDocument10@@YAJAEBU_GUID@@PEAPEAX@Z; CreateDOMDocument10(_GUID const &,void * *)
0x1800e6597  mov     ebp, eax
0x1800e6599  test    eax, eax
0x1800e659b  js      loc_1800E66B9
0x1800e65a1  mov     r8, [rbx]; struct IXMLDOMDocument2 *
0x1800e65a4  mov     rdx, [rsi+60h]; struct IXMLDOMDocument2 *
0x1800e65a8  call    ?setSecurity@ViewerFactory@@AEAAJPEAUIXMLDOMDocument2@@0@Z; ViewerFactory::setSecurity(IXMLDOMDocument2 *,IXMLDOMDocument2 *)
0x1800e65ad  mov     ebp, eax
0x1800e65af  test    eax, eax
0x1800e65b1  js      loc_1800E66B9
0x1800e65b7  mov     rdx, [rbx]; struct IXMLDOMDocument2 *
0x1800e65ba  mov     ecx, [rsi+98h]
0x1800e65c0  test    ecx, ecx
0x1800e65c2  jnz     short loc_1800E65E2
0x1800e65c4  mov     ecx, [rsi+0A8h]; this
0x1800e65ca  test    ecx, ecx
0x1800e65cc  jz      short loc_1800E65F4
0x1800e65ce  mov     rax, [rsi+0B0h]
0x1800e65d5  mov     [rsi+0A0h], rax
0x1800e65dc  mov     [rsi+98h], ecx
0x1800e65e2  cmp     ecx, 2
0x1800e65e5  jnz     short loc_1800E65F4
0x1800e65e7  mov     r8, r14; struct IXMLNodeSource *
0x1800e65ea  mov     rcx, rsi; this
0x1800e65ed  call    ?loadSS@ViewerFactory@@AEAAJPEAUIXMLDOMDocument2@@PEAUIXMLNodeSource@@@Z; ViewerFactory::loadSS(IXMLDOMDocument2 *,IXMLNodeSource *)
0x1800e65f2  jmp     short loc_1800E6603
0x1800e65f4  mov     dword ptr [rsi+98h], 2
0x1800e65fe  call    ?loadSSDefault@ViewerFactory@@AEAAJPEAUIXMLDOMDocument2@@@Z; ViewerFactory::loadSSDefault(IXMLDOMDocument2 *)
0x1800e6603  mov     ebp, eax
0x1800e6605  jmp     loc_1800E66B9
0x1800e660a  sub     ebx, 6
0x1800e660d  jz      loc_1800E66B3
0x1800e6613  sub     ebx, 1
0x1800e6616  jz      loc_1800E66AB
0x1800e661c  sub     ebx, 1
0x1800e661f  jz      short loc_1800E663B
0x1800e6621  cmp     ebx, 1
0x1800e6624  jnz     loc_1800E66B9
0x1800e662a  cmp     [rsi+48h], r15d
0x1800e662e  jz      loc_1800E66B9
0x1800e6634  mov     ebp, 8000000Ah
0x1800e6639  jmp     short loc_1800E66B9
0x1800e663b  mov     edx, [rsi+0CCh]; int
0x1800e6641  test    edx, edx
0x1800e6643  jz      short loc_1800E6652
0x1800e6645  xor     r8d, r8d; struct IXMLDOMParseError *
0x1800e6648  mov     rcx, rsi; this
0x1800e664b  call    ?reportError@ViewerFactory@@QEAAJJPEAUIXMLDOMParseError@@@Z; ViewerFactory::reportError(long,IXMLDOMParseError *)
0x1800e6650  jmp     short loc_1800E66B9
0x1800e6652  cmp     dword ptr [rsi+98h], 1
0x1800e6659  mov     rcx, rsi; this
0x1800e665c  jnz     short loc_1800E6693
0x1800e665e  xor     r8d, r8d; unsigned int
0x1800e6661  lea     rdx, aHtmlBody; "</html:body>"
0x1800e6668  call    ?CSSWrite@ViewerFactory@@AEAAXPEBGK@Z; ViewerFactory::CSSWrite(ushort const *,ulong)
0x1800e666d  xor     r8d, r8d; unsigned int
0x1800e6670  lea     rdx, aHtmlHtml_0; "</html:html>"
0x1800e6677  mov     rcx, rsi; this
0x1800e667a  call    ?CSSWrite@ViewerFactory@@AEAAXPEBGK@Z; ViewerFactory::CSSWrite(ushort const *,ulong)
0x1800e667f  mov     rcx, [rsi+50h]
0x1800e6683  xor     edx, edx
0x1800e6685  mov     rax, [rcx]
0x1800e6688  mov     rax, [rax+40h]
0x1800e668c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6691  jmp     short loc_1800E66A3
0x1800e6693  mov     r8d, 1; int
0x1800e6699  mov     rdx, r14; struct IXMLNodeSource *
0x1800e669c  call    ?processXSLAsync@ViewerFactory@@QEAAJPEAUIXMLNodeSource@@H@Z; ViewerFactory::processXSLAsync(IXMLNodeSource *,int)
0x1800e66a1  mov     ebp, eax
0x1800e66a3  test    ebp, ebp
0x1800e66a5  jns     short loc_1800E66B9
0x1800e66a7  mov     edx, ebp
0x1800e66a9  jmp     short loc_1800E6645
0x1800e66ab  dec     dword ptr [rsi+0BCh]
0x1800e66b1  jmp     short loc_1800E66B9
0x1800e66b3  inc     dword ptr [rsi+0BCh]
0x1800e66b9  mov     rax, [rsi]
0x1800e66bc  mov     rcx, rsi
0x1800e66bf  mov     rax, [rax+10h]
0x1800e66c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e66c8  mov     eax, ebp
0x1800e66ca  add     rsp, 58h
0x1800e66ce  pop     r15
0x1800e66d0  pop     r14
0x1800e66d2  pop     rdi
0x1800e66d3  pop     rsi
0x1800e66d4  pop     rbp
0x1800e66d5  pop     rbx
0x1800e66d6  retn
```
