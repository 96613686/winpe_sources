# CNfsXmlSharePermission::NfsXmlReadPermissionEntry(IXMLDOMNode *)

- ea: `0x180027d18`
- end: `0x180027f99`
- name: `?NfsXmlReadPermissionEntry@CNfsXmlSharePermission@@QEAAJPEAUIXMLDOMNode@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(CNfsXmlSharePermission *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180028148`

## callees

- `0x18000ec88`
- `0x18000efc8`
- `0x18002795c`
- `0x180027d18`
- `0x180027fa0`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027da8`
- `msvcrt!_wcsicmp` at `0x180027e73`
- `msvcrt!_wcsicmp` at `0x180027ec4`
- `msvcrt!_wcsicmp` at `0x180027f0e`
- `msvcrt!_wcsicmp` at `0x180027da8`
- `msvcrt!_wcsicmp` at `0x180027e73`
- `msvcrt!_wcsicmp` at `0x180027ec4`
- `msvcrt!_wcsicmp` at `0x180027f0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180027f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180027f84`

## pseudocode

```c
__int64 __fastcall CNfsXmlSharePermission::NfsXmlReadPermissionEntry(
        CNfsXmlSharePermission *this,
        struct IXMLDOMNode *a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_nodeType)(IXMLDOMNode *, DOMNodeType *); // rax
  int NodeText; // ebx
  unsigned int i; // edi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  struct IXMLDOMNode *v12; // rdx
  wchar_t *String1; // [rsp+20h] [rbp-30h] BYREF
  __int64 v15; // [rsp+28h] [rbp-28h] BYREF
  struct tagVARIANT v16; // [rsp+30h] [rbp-20h] BYREF
  int v17; // [rsp+78h] [rbp+28h] BYREF
  int v18; // [rsp+80h] [rbp+30h] BYREF
  struct IXMLDOMNode *v19; // [rsp+88h] [rbp+38h] BYREF

  lpVtbl = a2->lpVtbl;
  v17 = 0;
  String1 = 0;
  v18 = 0;
  get_nodeType = lpVtbl->get_nodeType;
  v19 = 0;
  v15 = 0;
  NodeText = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))get_nodeType)(a2, &v17);
  if ( NodeText >= 0 )
  {
    if ( v17 == 1 )
    {
      NodeText = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))a2->lpVtbl->get_nodeName)(a2, &String1);
      if ( NodeText >= 0 && !_wcsicmp(String1, L"PermissionEntry") )
      {
        NodeText = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_childNodes)(a2, &v15);
        if ( NodeText >= 0 )
          NodeText = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 64LL))(v15, &v18);
        for ( i = 0; NodeText >= 0 && (int)i < v18; ++i )
        {
          NodeText = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v15 + 56LL))(
                       v15,
                       i,
                       &v19);
          if ( NodeText >= 0 )
          {
            NodeText = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v19->lpVtbl->get_nodeType)(v19, &v17);
            if ( NodeText >= 0 && v17 == 1 )
            {
              NodeText = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v19->lpVtbl->get_nodeName)(
                           v19,
                           &String1);
              if ( NodeText >= 0 )
              {
                memset(&v16, 0, sizeof(v16));
                if ( _wcsicmp(String1, L"Permission") )
                {
                  if ( _wcsicmp(String1, L"Encoding") )
                  {
                    if ( _wcsicmp(String1, L"Name") )
                    {
                      NodeText = -2147024809;
                    }
                    else
                    {
                      NodeText = NfsXmlGetNodeText(v19, &v16);
                      if ( NodeText >= 0 )
                      {
                        v10 = std::char_traits<unsigned short>::length(v16.llVal);
                        std::wstring::assign(this, v11, v10);
                        v12 = v19;
                        *((_BYTE *)this + 136) = 1;
                        NodeText = CNfsXmlSharePermission::NfsXmlReadPermissionEntryAttributes(this, v12);
                      }
                    }
                  }
                  else
                  {
                    NodeText = NfsXmlGetNodeText(v19, &v16);
                    if ( NodeText >= 0 )
                    {
                      v9 = std::char_traits<unsigned short>::length(v16.llVal);
                      std::wstring::assign((char *)this + 104, v16.llVal, v9);
                      *((_BYTE *)this + 140) = 1;
                    }
                  }
                }
                else
                {
                  NodeText = NfsXmlGetNodeText(v19, &v16);
                  if ( NodeText >= 0 )
                  {
                    v8 = std::char_traits<unsigned short>::length(v16.llVal);
                    std::wstring::assign((char *)this + 64, v16.llVal, v8);
                    *((_BYTE *)this + 138) = 1;
                  }
                }
              }
              ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
            }
          }
          v19 = 0;
        }
      }
    }
    else
    {
      NodeText = -2147024809;
    }
  }
  SysFreeString(String1);
  return (unsigned int)NodeText;
}

```

## disassembly

```asm
0x180027d18  mov     [rsp-18h+arg_0], rbx
0x180027d1d  push    rbp
0x180027d1e  push    rsi
0x180027d1f  push    rdi
0x180027d20  mov     rbp, rsp
0x180027d23  sub     rsp, 50h
0x180027d27  mov     rax, [rdx]
0x180027d2a  mov     rdi, rdx
0x180027d2d  mov     rsi, rcx
0x180027d30  mov     [rbp+arg_8], 0
0x180027d37  lea     rdx, [rbp+arg_8]
0x180027d3b  mov     [rbp+String1], 0
0x180027d43  mov     rcx, rdi
0x180027d46  mov     [rbp+arg_10], 0
0x180027d4d  mov     rax, [rax+50h]
0x180027d51  mov     [rbp+arg_18], 0
0x180027d59  mov     [rbp+var_28], 0
0x180027d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d66  mov     ebx, eax
0x180027d68  test    eax, eax
0x180027d6a  js      loc_180027F80
0x180027d70  cmp     [rbp+arg_8], 1
0x180027d74  jz      short loc_180027D80
0x180027d76  mov     ebx, 80070057h
0x180027d7b  jmp     loc_180027F80
0x180027d80  mov     rax, [rdi]
0x180027d83  lea     rdx, [rbp+String1]
0x180027d87  mov     rcx, rdi
0x180027d8a  mov     rax, [rax+38h]
0x180027d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d93  mov     ebx, eax
0x180027d95  test    eax, eax
0x180027d97  js      loc_180027F80
0x180027d9d  mov     rcx, [rbp+String1]; String1
0x180027da1  lea     rdx, aPermissionentr; "PermissionEntry"
0x180027da8  call    cs:__imp__wcsicmp
0x180027dae  test    eax, eax
0x180027db0  jnz     loc_180027F80
0x180027db6  mov     rax, [rdi]
0x180027db9  lea     rdx, [rbp+var_28]
0x180027dbd  mov     rcx, rdi
0x180027dc0  mov     rax, [rax+60h]
0x180027dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dc9  mov     ebx, eax
0x180027dcb  test    eax, eax
0x180027dcd  js      short loc_180027DE5
0x180027dcf  mov     rcx, [rbp+var_28]
0x180027dd3  lea     rdx, [rbp+arg_10]
0x180027dd7  mov     rax, [rcx]
0x180027dda  mov     rax, [rax+40h]
0x180027dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027de3  mov     ebx, eax
0x180027de5  xor     edi, edi
0x180027de7  jmp     loc_180027F78
0x180027dec  cmp     edi, [rbp+arg_10]
0x180027def  jge     loc_180027F80
0x180027df5  mov     rcx, [rbp+var_28]
0x180027df9  lea     r8, [rbp+arg_18]
0x180027dfd  mov     edx, edi
0x180027dff  mov     rax, [rcx]
0x180027e02  mov     rax, [rax+38h]
0x180027e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e0b  mov     ebx, eax
0x180027e0d  test    eax, eax
0x180027e0f  js      loc_180027F6E
0x180027e15  mov     rcx, [rbp+arg_18]
0x180027e19  lea     rdx, [rbp+arg_8]
0x180027e1d  mov     rax, [rcx]
0x180027e20  mov     rax, [rax+50h]
0x180027e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e29  mov     ebx, eax
0x180027e2b  test    eax, eax
0x180027e2d  js      loc_180027F6E
0x180027e33  cmp     [rbp+arg_8], 1
0x180027e37  jnz     loc_180027F6E
0x180027e3d  mov     rcx, [rbp+arg_18]
0x180027e41  lea     rdx, [rbp+String1]
0x180027e45  mov     rax, [rcx]
0x180027e48  mov     rax, [rax+38h]
0x180027e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e51  mov     ebx, eax
0x180027e53  test    eax, eax
0x180027e55  js      loc_180027F5E
0x180027e5b  mov     rcx, [rbp+String1]; String1
0x180027e5f  lea     rdx, aPermission_0; "Permission"
0x180027e66  xorps   xmm0, xmm0
0x180027e69  xor     eax, eax
0x180027e6b  movups  xmmword ptr [rbp+var_20], xmm0
0x180027e6f  mov     qword ptr [rbp+var_20+10h], rax
0x180027e73  call    cs:__imp__wcsicmp
0x180027e79  test    eax, eax
0x180027e7b  jnz     short loc_180027EB9
0x180027e7d  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x180027e81  lea     rdx, [rbp+var_20]; struct tagVARIANT *
0x180027e85  call    ?NfsXmlGetNodeText@@YAJPEAUIXMLDOMNode@@AEAUtagVARIANT@@@Z; NfsXmlGetNodeText(IXMLDOMNode *,tagVARIANT &)
0x180027e8a  mov     ebx, eax
0x180027e8c  test    eax, eax
0x180027e8e  js      loc_180027F5E
0x180027e94  mov     rcx, qword ptr [rbp+var_20+8]
0x180027e98  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180027e9d  mov     rdx, qword ptr [rbp+var_20+8]
0x180027ea1  lea     rcx, [rsi+40h]
0x180027ea5  mov     r8, rax
0x180027ea8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027ead  mov     byte ptr [rsi+8Ah], 1
0x180027eb4  jmp     loc_180027F5E
0x180027eb9  mov     rcx, [rbp+String1]; String1
0x180027ebd  lea     rdx, aEncoding; "Encoding"
0x180027ec4  call    cs:__imp__wcsicmp
0x180027eca  test    eax, eax
0x180027ecc  jnz     short loc_180027F03
0x180027ece  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x180027ed2  lea     rdx, [rbp+var_20]; struct tagVARIANT *
0x180027ed6  call    ?NfsXmlGetNodeText@@YAJPEAUIXMLDOMNode@@AEAUtagVARIANT@@@Z; NfsXmlGetNodeText(IXMLDOMNode *,tagVARIANT &)
0x180027edb  mov     ebx, eax
0x180027edd  test    eax, eax
0x180027edf  js      short loc_180027F5E
0x180027ee1  mov     rcx, qword ptr [rbp+var_20+8]
0x180027ee5  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180027eea  mov     rdx, qword ptr [rbp+var_20+8]
0x180027eee  lea     rcx, [rsi+68h]
0x180027ef2  mov     r8, rax
0x180027ef5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027efa  mov     byte ptr [rsi+8Ch], 1
0x180027f01  jmp     short loc_180027F5E
0x180027f03  mov     rcx, [rbp+String1]; String1
0x180027f07  lea     rdx, aName; "Name"
0x180027f0e  call    cs:__imp__wcsicmp
0x180027f14  test    eax, eax
0x180027f16  jnz     short loc_180027F59
0x180027f18  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x180027f1c  lea     rdx, [rbp+var_20]; struct tagVARIANT *
0x180027f20  call    ?NfsXmlGetNodeText@@YAJPEAUIXMLDOMNode@@AEAUtagVARIANT@@@Z; NfsXmlGetNodeText(IXMLDOMNode *,tagVARIANT &)
0x180027f25  mov     ebx, eax
0x180027f27  test    eax, eax
0x180027f29  js      short loc_180027F5E
0x180027f2b  mov     rcx, qword ptr [rbp+var_20+8]
0x180027f2f  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180027f34  mov     rdx, rcx
0x180027f37  mov     r8, rax
0x180027f3a  mov     rcx, rsi
0x180027f3d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027f42  mov     rdx, [rbp+arg_18]; struct IXMLDOMNode *
0x180027f46  mov     rcx, rsi; this
0x180027f49  mov     byte ptr [rsi+88h], 1
0x180027f50  call    ?NfsXmlReadPermissionEntryAttributes@CNfsXmlSharePermission@@AEAAJPEAUIXMLDOMNode@@@Z; CNfsXmlSharePermission::NfsXmlReadPermissionEntryAttributes(IXMLDOMNode *)
0x180027f55  mov     ebx, eax
0x180027f57  jmp     short loc_180027F5E
0x180027f59  mov     ebx, 80070057h
0x180027f5e  mov     rcx, [rbp+arg_18]
0x180027f62  mov     rax, [rcx]
0x180027f65  mov     rax, [rax+10h]
0x180027f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f6e  mov     [rbp+arg_18], 0
0x180027f76  inc     edi
0x180027f78  test    ebx, ebx
0x180027f7a  jns     loc_180027DEC
0x180027f80  mov     rcx, [rbp+String1]; bstrString
0x180027f84  call    cs:__imp_SysFreeString
0x180027f8a  mov     eax, ebx
0x180027f8c  mov     rbx, [rsp+50h+arg_0]
0x180027f91  add     rsp, 50h
0x180027f95  pop     rdi
0x180027f96  pop     rsi
0x180027f97  pop     rbp
0x180027f98  retn
```
