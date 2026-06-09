# Print3MFUtils::ExtractModel(ATL::CComPtr<IStream> &,ATL::CComPtr<IStream> &)

- ea: `0x180009c98`
- end: `0x180009dcc`
- name: `?ExtractModel@Print3MFUtils@@YAJAEAV?$CComPtr@UIStream@@@ATL@@0@Z`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003f40`
- `0x180004020`

## callees

- `0x180009c98`
- `0x180009dd4`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180009d03`
- `ole32!CoCreateInstance` at `0x180009d03`

## pseudocode

```c
__int64 __fastcall Print3MFUtils::ExtractModel(_QWORD *a1, __int64 a2)
{
  HRESULT PartByRelationshipType; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  v8 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a1 + 40LL))(*a1, 0, 0, 0);
  v9 = 0;
  ppv = 0;
  v8 = 0;
  PartByRelationshipType = CoCreateInstance(
                             &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
                             0,
                             1u,
                             &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
                             &ppv);
  if ( PartByRelationshipType >= 0 )
  {
    PartByRelationshipType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(
                               ppv,
                               *a1,
                               2,
                               &v9);
    if ( PartByRelationshipType >= 0 )
    {
      PartByRelationshipType = OpcUtils::FindPartByRelationshipType(&v9, v5, L"image/jpeg", &v8);
      if ( PartByRelationshipType < 0 )
        PartByRelationshipType = OpcUtils::FindPartByRelationshipType(&v9, v6, L"image/png", &v8);
      if ( PartByRelationshipType >= 0 )
        PartByRelationshipType = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, a2);
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)PartByRelationshipType;
}

```

## disassembly

```asm
0x180009c98  mov     [rsp-18h+arg_8], rbx
0x180009c9d  push    rbp
0x180009c9e  push    rsi
0x180009c9f  push    rdi
0x180009ca0  mov     rbp, rsp
0x180009ca3  sub     rsp, 30h
0x180009ca7  mov     rsi, rdx
0x180009caa  mov     rdi, rcx
0x180009cad  mov     [rbp+arg_0], 0
0x180009cb5  mov     rcx, [rcx]
0x180009cb8  mov     rax, [rcx]
0x180009cbb  xor     r9d, r9d
0x180009cbe  xor     r8d, r8d
0x180009cc1  mov     rdx, [rbp+arg_0]
0x180009cc5  mov     rax, [rax+28h]
0x180009cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cce  mov     [rbp+arg_10], 0
0x180009cd6  mov     [rbp+arg_18], 0
0x180009cde  mov     [rbp+arg_0], 0
0x180009ce6  lea     rax, [rbp+arg_18]
0x180009cea  mov     [rsp+30h+ppv], rax; ppv
0x180009cef  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x180009cf6  xor     edx, edx; pUnkOuter
0x180009cf8  lea     r8d, [rdx+1]; dwClsContext
0x180009cfc  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x180009d03  call    cs:__imp_CoCreateInstance
0x180009d09  mov     ebx, eax
0x180009d0b  test    eax, eax
0x180009d0d  js      short loc_180009D7B
0x180009d0f  mov     rcx, [rbp+arg_18]
0x180009d13  mov     rax, [rcx]
0x180009d16  lea     r9, [rbp+arg_10]
0x180009d1a  mov     r8d, 2
0x180009d20  mov     rdx, [rdi]
0x180009d23  mov     rax, [rax+38h]
0x180009d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2c  mov     ebx, eax
0x180009d2e  test    eax, eax
0x180009d30  js      short loc_180009D7B
0x180009d32  lea     r9, [rbp+arg_0]
0x180009d36  lea     r8, aImageJpeg; "image/jpeg"
0x180009d3d  lea     rcx, [rbp+arg_10]
0x180009d41  call    ?FindPartByRelationshipType@OpcUtils@@YAJAEAV?$CComPtr@UIOpcPackage@@@ATL@@PEBG1AEAV?$CComPtr@UIOpcPart@@@3@_N@Z; OpcUtils::FindPartByRelationshipType(ATL::CComPtr<IOpcPackage> &,ushort const *,ushort const *,ATL::CComPtr<IOpcPart> &,bool)
0x180009d46  mov     ebx, eax
0x180009d48  test    eax, eax
0x180009d4a  jns     short loc_180009D62
0x180009d4c  lea     r9, [rbp+arg_0]
0x180009d50  lea     r8, aImagePng; "image/png"
0x180009d57  lea     rcx, [rbp+arg_10]
0x180009d5b  call    ?FindPartByRelationshipType@OpcUtils@@YAJAEAV?$CComPtr@UIOpcPackage@@@ATL@@PEBG1AEAV?$CComPtr@UIOpcPart@@@3@_N@Z; OpcUtils::FindPartByRelationshipType(ATL::CComPtr<IOpcPackage> &,ushort const *,ushort const *,ATL::CComPtr<IOpcPart> &,bool)
0x180009d60  mov     ebx, eax
0x180009d62  test    ebx, ebx
0x180009d64  js      short loc_180009D7B
0x180009d66  mov     rcx, [rbp+arg_0]
0x180009d6a  mov     rax, [rcx]
0x180009d6d  mov     rdx, rsi
0x180009d70  mov     rax, [rax+20h]
0x180009d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d79  mov     ebx, eax
0x180009d7b  mov     rcx, [rbp+arg_0]
0x180009d7f  test    rcx, rcx
0x180009d82  jz      short loc_180009D91
0x180009d84  mov     rax, [rcx]
0x180009d87  mov     rax, [rax+10h]
0x180009d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d90  nop
0x180009d91  mov     rcx, [rbp+arg_18]
0x180009d95  test    rcx, rcx
0x180009d98  jz      short loc_180009DA7
0x180009d9a  mov     rax, [rcx]
0x180009d9d  mov     rax, [rax+10h]
0x180009da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009da6  nop
0x180009da7  mov     rcx, [rbp+arg_10]
0x180009dab  test    rcx, rcx
0x180009dae  jz      short loc_180009DBD
0x180009db0  mov     rax, [rcx]
0x180009db3  mov     rax, [rax+10h]
0x180009db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dbc  nop
0x180009dbd  mov     eax, ebx
0x180009dbf  mov     rbx, [rsp+30h+arg_8]
0x180009dc4  add     rsp, 30h
0x180009dc8  pop     rdi
0x180009dc9  pop     rsi
0x180009dca  pop     rbp
0x180009dcb  retn
```
