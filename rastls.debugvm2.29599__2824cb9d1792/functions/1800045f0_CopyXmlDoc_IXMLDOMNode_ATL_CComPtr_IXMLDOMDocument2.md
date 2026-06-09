# CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x1800045f0`
- end: `0x1800046d4`
- name: `?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z`
- size: `228`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180060a40`
- `0x180060ce0`
- `0x180060e00`

## callees

- `0x1800045f0`
- `0x180004bd0`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000465c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000465c`

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
0x1800045f0  mov     [rsp+arg_8], rbx
0x1800045f5  push    rdi
0x1800045f6  sub     rsp, 30h
0x1800045fa  mov     rdi, rdx
0x1800045fd  mov     [rsp+38h+arg_0], 0
0x180004606  mov     rax, [rcx]
0x180004609  mov     edx, 0FFFFFFFFh
0x18000460e  lea     r8, [rsp+38h+arg_0]
0x180004613  mov     rax, [rax+0C0h]
0x18000461a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000461f  mov     ebx, eax
0x180004621  test    eax, eax
0x180004623  jnz     short loc_180004684
0x180004625  mov     rcx, [rdi]
0x180004628  test    rcx, rcx
0x18000462b  jz      short loc_180004641
0x18000462d  mov     qword ptr [rdi], 0
0x180004634  mov     rax, [rcx]
0x180004637  mov     rax, [rax+10h]
0x18000463b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004640  nop
0x180004641  mov     [rsp+38h+ppv], rdi; ppv
0x180004646  lea     r9, IID_IXMLDOMDocument2; riid
0x18000464d  xor     edx, edx; pUnkOuter
0x18000464f  mov     r8d, 1; dwClsContext
0x180004655  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000465c  call    cs:__imp_CoCreateInstance
0x180004662  mov     ebx, eax
0x180004664  test    eax, eax
0x180004666  jnz     short loc_180004684
0x180004668  mov     rcx, [rdi]
0x18000466b  mov     rax, [rcx]
0x18000466e  xor     r8d, r8d
0x180004671  mov     rdx, [rsp+38h+arg_0]
0x180004676  mov     rax, [rax+0A8h]
0x18000467d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004682  mov     ebx, eax
0x180004684  lea     rax, WPP_GLOBAL_Control
0x18000468b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004692  cmp     rcx, rax
0x180004695  jz      short loc_1800046B0
0x180004697  mov     edx, 0FAh
0x18000469c  mov     r9d, ebx
0x18000469f  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800046a6  mov     rcx, [rcx+10h]
0x1800046aa  call    WPP_SF_d
0x1800046af  nop
0x1800046b0  mov     rcx, [rsp+38h+arg_0]
0x1800046b5  test    rcx, rcx
0x1800046b8  jz      short loc_1800046C7
0x1800046ba  mov     rax, [rcx]
0x1800046bd  mov     rax, [rax+10h]
0x1800046c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c6  nop
0x1800046c7  mov     eax, ebx
0x1800046c9  mov     rbx, [rsp+38h+arg_8]
0x1800046ce  add     rsp, 30h
0x1800046d2  pop     rdi
0x1800046d3  retn
```
