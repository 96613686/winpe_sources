# GraphDeserializerBase::DeserializeImage(IXmlReader *,ID2D1Image * *)

- ea: `0x180228020`
- end: `0x180228170`
- name: `?DeserializeImage@GraphDeserializerBase@@MEAAJPEAUIXmlReader@@PEAPEAUID2D1Image@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(GraphDeserializerBase *__hidden this, struct IXmlReader *, struct ID2D1Image **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x180228020`
- `0x180228178`
- `0x18025b100`
- `0x1802f5370`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1802280e5`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1802280e5`

## string_xrefs

- `0x18022808f`: `CLSID`

## pseudocode

```c
__int64 __fastcall GraphDeserializerBase::DeserializeImage(
        __int64 (__fastcall ***this)(GraphDeserializerBase *, GUID *, __int64 **),
        struct IXmlReader *a2,
        struct ID2D1Image **a3)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  HRESULT v7; // ebx
  int v8; // eax
  __int64 (__fastcall **v9)(GraphDeserializerBase *, GUID *, __int64 **); // rax
  int v10; // eax
  __int64 *v12; // [rsp+20h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+28h] [rbp-28h] BYREF
  GUID iid; // [rsp+30h] [rbp-20h] BYREF

  *a3 = 0;
  lpVtbl = a2->lpVtbl;
  String1 = 0;
  v7 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, _QWORD))lpVtbl->GetLocalName)(a2, &String1, 0);
  if ( v7 < 0 )
    goto LABEL_12;
  if ( wcscmp_0(String1, L"Effect") )
    goto LABEL_11;
  v8 = ((__int64 (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
         a2,
         L"CLSID",
         0);
  v7 = v8;
  if ( v8 < 0 )
  {
LABEL_12:
    DoStackCapture(v7);
    return (unsigned int)v7;
  }
  if ( v8 )
  {
LABEL_11:
    v7 = -2147467259;
    goto LABEL_12;
  }
  v7 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, _QWORD))a2->lpVtbl->GetValue)(a2, &String1, 0);
  if ( v7 < 0 )
    goto LABEL_12;
  iid = 0;
  v7 = IIDFromString(String1, &iid);
  if ( v7 < 0 )
    goto LABEL_12;
  v9 = *this;
  v12 = 0;
  v10 = (*v9)((GraphDeserializerBase *)this, &iid, &v12);
  v7 = v10;
  if ( v10 >= 0 )
  {
    SetElementProperties((__int64 *)a2, v12);
    (*(void (__fastcall **)(__int64 *, struct ID2D1Image **))(*v12 + 144))(v12, a3);
  }
  else
  {
    DoStackCapture(v10);
  }
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180228020  push    rbp
0x180228022  push    rbx
0x180228023  push    rsi
0x180228024  push    rdi
0x180228025  push    r14
0x180228027  mov     rbp, rsp
0x18022802a  sub     rsp, 50h
0x18022802e  mov     rax, cs:__security_cookie
0x180228035  xor     rax, rsp
0x180228038  mov     [rbp+var_10], rax
0x18022803c  mov     qword ptr [r8], 0
0x180228043  mov     rdi, rdx
0x180228046  mov     rax, [rdx]
0x180228049  mov     r14, r8
0x18022804c  mov     rsi, rcx
0x18022804f  mov     [rbp+String1], 0
0x180228057  xor     r8d, r8d
0x18022805a  lea     rdx, [rbp+String1]
0x18022805e  mov     rcx, rdi
0x180228061  mov     rax, [rax+70h]
0x180228065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022806a  mov     ebx, eax
0x18022806c  test    eax, eax
0x18022806e  js      loc_180228150
0x180228074  mov     rcx, [rbp+String1]; String1
0x180228078  lea     rdx, aEffect; "Effect"
0x18022807f  call    wcscmp_0
0x180228084  test    eax, eax
0x180228086  jnz     loc_18022814B
0x18022808c  mov     rax, [rdi]
0x18022808f  lea     rdx, aClsid_0; "CLSID"
0x180228096  xor     r8d, r8d
0x180228099  mov     rcx, rdi
0x18022809c  mov     rax, [rax+50h]
0x1802280a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802280a5  mov     ebx, eax
0x1802280a7  test    eax, eax
0x1802280a9  js      loc_180228150
0x1802280af  test    eax, eax
0x1802280b1  jnz     loc_18022814B
0x1802280b7  mov     rax, [rdi]
0x1802280ba  lea     rdx, [rbp+String1]
0x1802280be  xor     r8d, r8d
0x1802280c1  mov     rcx, rdi
0x1802280c4  mov     rax, [rax+80h]
0x1802280cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802280d0  mov     ebx, eax
0x1802280d2  test    eax, eax
0x1802280d4  js      short loc_180228150
0x1802280d6  mov     rcx, [rbp+String1]; lpsz
0x1802280da  lea     rdx, [rbp+iid]; lpiid
0x1802280de  xorps   xmm0, xmm0
0x1802280e1  movups  xmmword ptr [rbp+iid.Data1], xmm0
0x1802280e5  call    cs:__imp_IIDFromString
0x1802280eb  mov     ebx, eax
0x1802280ed  test    eax, eax
0x1802280ef  js      short loc_180228150
0x1802280f1  mov     rax, [rsi]
0x1802280f4  lea     r8, [rbp+var_30]
0x1802280f8  lea     rdx, [rbp+iid]
0x1802280fc  mov     [rbp+var_30], 0
0x180228104  mov     rcx, rsi
0x180228107  mov     rax, [rax]
0x18022810a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022810f  mov     ebx, eax
0x180228111  test    eax, eax
0x180228113  jns     short loc_180228127
0x180228115  mov     ecx, eax; int
0x180228117  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18022811c  lea     rcx, [rbp+var_30]; void *
0x180228120  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x180228125  jmp     short loc_180228157
0x180228127  mov     rdx, [rbp+var_30]
0x18022812b  mov     rcx, rdi
0x18022812e  call    ?SetElementProperties@@YAJPEAUIXmlReader@@PEAV?$CDIProperties@UID2D1InkEffect@@@@@Z; SetElementProperties(IXmlReader *,CDIProperties<ID2D1InkEffect> *)
0x180228133  mov     rcx, [rbp+var_30]
0x180228137  mov     rdx, r14
0x18022813a  mov     rax, [rcx]
0x18022813d  mov     rax, [rax+90h]
0x180228144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180228149  jmp     short loc_18022811C
0x18022814b  mov     ebx, 80004005h
0x180228150  mov     ecx, ebx; int
0x180228152  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180228157  mov     eax, ebx
0x180228159  mov     rcx, [rbp+var_10]
0x18022815d  xor     rcx, rsp; StackCookie
0x180228160  call    __security_check_cookie
0x180228165  add     rsp, 50h
0x180228169  pop     r14
0x18022816b  pop     rdi
0x18022816c  pop     rsi
0x18022816d  pop     rbx
0x18022816e  pop     rbp
0x18022816f  retn
```
