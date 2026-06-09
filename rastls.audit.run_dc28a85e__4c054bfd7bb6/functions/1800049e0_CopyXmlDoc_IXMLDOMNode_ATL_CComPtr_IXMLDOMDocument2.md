# CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x1800049e0`
- end: `0x180004acb`
- name: `?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z`
- size: `235`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800643c0`
- `0x180064670`
- `0x180064790`

## callees

- `0x1800049e0`
- `0x180005010`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004a4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004a4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CopyXmlDoc(__int64 a1, LPVOID *a2)
{
  unsigned int Instance; // ebx
  LPVOID v4; // rcx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a1 + 192LL))(a1, 0xFFFFFFFFLL, &v6);
  if ( !Instance )
  {
    v4 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, a2);
    if ( !Instance )
      Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)*a2 + 168LL))(*a2, v6, 0);
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, Instance);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return Instance;
}

```

## disassembly

```asm
0x1800049e0  mov     [rsp+arg_8], rbx
0x1800049e5  push    rdi
0x1800049e6  sub     rsp, 30h
0x1800049ea  mov     rdi, rdx
0x1800049ed  mov     [rsp+38h+arg_0], 0
0x1800049f6  mov     rax, [rcx]
0x1800049f9  mov     edx, 0FFFFFFFFh
0x1800049fe  lea     r8, [rsp+38h+arg_0]
0x180004a03  mov     rax, [rax+0C0h]
0x180004a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0f  mov     ebx, eax
0x180004a11  test    eax, eax
0x180004a13  jnz     short loc_180004A7A
0x180004a15  mov     rcx, [rdi]
0x180004a18  test    rcx, rcx
0x180004a1b  jz      short loc_180004A31
0x180004a1d  mov     qword ptr [rdi], 0
0x180004a24  mov     rax, [rcx]
0x180004a27  mov     rax, [rax+10h]
0x180004a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a30  nop
0x180004a31  mov     [rsp+38h+ppv], rdi; ppv
0x180004a36  lea     r9, IID_IXMLDOMDocument2; riid
0x180004a3d  xor     edx, edx; pUnkOuter
0x180004a3f  mov     r8d, 1; dwClsContext
0x180004a45  lea     rcx, CLSID_DOMDocument60; rclsid
0x180004a4c  call    cs:__imp_CoCreateInstance
0x180004a53  nop     dword ptr [rax+rax+00h]
0x180004a58  mov     ebx, eax
0x180004a5a  test    eax, eax
0x180004a5c  jnz     short loc_180004A7A
0x180004a5e  mov     rcx, [rdi]
0x180004a61  mov     rax, [rcx]
0x180004a64  xor     r8d, r8d
0x180004a67  mov     rdx, [rsp+38h+arg_0]
0x180004a6c  mov     rax, [rax+0A8h]
0x180004a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a78  mov     ebx, eax
0x180004a7a  lea     rax, WPP_GLOBAL_Control
0x180004a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a88  cmp     rcx, rax
0x180004a8b  jz      short loc_180004AA6
0x180004a8d  mov     edx, 0FAh
0x180004a92  mov     r9d, ebx
0x180004a95  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180004a9c  mov     rcx, [rcx+10h]
0x180004aa0  call    WPP_SF_d
0x180004aa5  nop
0x180004aa6  mov     rcx, [rsp+38h+arg_0]
0x180004aab  test    rcx, rcx
0x180004aae  jz      short loc_180004ABD
0x180004ab0  mov     rax, [rcx]
0x180004ab3  mov     rax, [rax+10h]
0x180004ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abc  nop
0x180004abd  mov     eax, ebx
0x180004abf  mov     rbx, [rsp+38h+arg_8]
0x180004ac4  add     rsp, 30h
0x180004ac8  pop     rdi
0x180004ac9  retn
```
