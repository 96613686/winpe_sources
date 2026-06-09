# CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x180003ad0`
- end: `0x180003bbc`
- name: `?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z`
- size: `236`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001cf30`
- `0x18001d130`
- `0x18001d950`

## callees

- `0x180003ad0`
- `0x180003bd0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003b79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003b79`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CopyXmlDoc(__int64 a1, LPVOID *a2)
{
  unsigned int Instance; // ebx
  LPVOID v5; // rcx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  Instance = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a1 + 192LL))(a1, 0xFFFFFFFFLL, &v6);
  if ( !Instance )
  {
    v5 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    }
    Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, a2);
    if ( !Instance )
      Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)*a2 + 168LL))(*a2, v6, 0);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, Instance);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return Instance;
}

```

## disassembly

```asm
0x180003ad0  mov     [rsp+arg_8], rbx
0x180003ad5  push    rdi
0x180003ad6  sub     rsp, 30h
0x180003ada  mov     rdi, rdx
0x180003add  mov     [rsp+38h+arg_0], 0
0x180003ae6  mov     rax, [rcx]
0x180003ae9  mov     edx, 0FFFFFFFFh
0x180003aee  lea     r8, [rsp+38h+arg_0]
0x180003af3  mov     rax, [rax+0C0h]
0x180003afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aff  mov     ebx, eax
0x180003b01  test    eax, eax
0x180003b03  jz      short loc_180003B56
0x180003b05  lea     rax, WPP_GLOBAL_Control
0x180003b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b13  cmp     rcx, rax
0x180003b16  jnz     short loc_180003B3C
0x180003b18  mov     rcx, [rsp+38h+arg_0]
0x180003b1d  test    rcx, rcx
0x180003b20  jz      short loc_180003B2F
0x180003b22  mov     rax, [rcx]
0x180003b25  mov     rax, [rax+10h]
0x180003b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2e  nop
0x180003b2f  mov     eax, ebx
0x180003b31  mov     rbx, [rsp+38h+arg_8]
0x180003b36  add     rsp, 30h
0x180003b3a  pop     rdi
0x180003b3b  retn
0x180003b3c  mov     edx, 3Ah ; ':'
0x180003b41  mov     r9d, ebx
0x180003b44  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x180003b4b  mov     rcx, [rcx+10h]
0x180003b4f  call    WPP_SF_d
0x180003b54  jmp     short loc_180003B18
0x180003b56  mov     rcx, [rdi]
0x180003b59  test    rcx, rcx
0x180003b5c  jnz     short loc_180003BA6
0x180003b5e  mov     [rsp+38h+ppv], rdi; ppv
0x180003b63  lea     r9, IID_IXMLDOMDocument2; riid
0x180003b6a  xor     edx, edx; pUnkOuter
0x180003b6c  mov     r8d, 1; dwClsContext
0x180003b72  lea     rcx, CLSID_DOMDocument60; rclsid
0x180003b79  call    cs:__imp_CoCreateInstance
0x180003b7f  mov     ebx, eax
0x180003b81  test    eax, eax
0x180003b83  jnz     short loc_180003B05
0x180003b85  mov     rcx, [rdi]
0x180003b88  mov     rax, [rcx]
0x180003b8b  xor     r8d, r8d
0x180003b8e  mov     rdx, [rsp+38h+arg_0]
0x180003b93  mov     rax, [rax+0A8h]
0x180003b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9f  mov     ebx, eax
0x180003ba1  jmp     loc_180003B05
0x180003ba6  mov     qword ptr [rdi], 0
0x180003bad  mov     rax, [rcx]
0x180003bb0  mov     rax, [rax+10h]
0x180003bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb9  jmp     short loc_180003B5E
```
