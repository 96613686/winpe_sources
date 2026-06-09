# NPrintTicketUtil::CreateDomDocument(IXMLDOMDocument2 * *)

- ea: `0x180008da4`
- end: `0x180008e62`
- name: `?CreateDomDocument@NPrintTicketUtil@@YAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(LPVOID *ppv, struct IXMLDOMDocument2 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000825c`
- `0x180008acc`
- `0x18000e608`

## callees

- `0x180008da4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008de0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008de0`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CreateDomDocument(LPVOID *ppv, struct IXMLDOMDocument2 **a2)
{
  HRESULT Instance; // edi

  if ( !ppv )
    return 2147942487LL;
  *ppv = 0;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, ppv);
  if ( Instance < 0
    || (Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 504LL))(*ppv, 0), Instance < 0)
    || (Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 544LL))(*ppv, 0), Instance < 0)
    || (Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 560LL))(*ppv, 0), Instance < 0) )
  {
    if ( *ppv )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
      *ppv = 0;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180008da4  mov     [rsp+arg_0], rbx
0x180008da9  push    rdi
0x180008daa  sub     rsp, 30h
0x180008dae  mov     rbx, rcx
0x180008db1  test    rcx, rcx
0x180008db4  jnz     short loc_180008DC0
0x180008db6  mov     eax, 80070057h
0x180008dbb  jmp     loc_180008E57
0x180008dc0  xor     edx, edx; pUnkOuter
0x180008dc2  mov     qword ptr [rcx], 0
0x180008dc9  lea     r9, IID_IXMLDOMDocument2; riid
0x180008dd0  mov     [rsp+38h+ppv], rbx; ppv
0x180008dd5  lea     rcx, CLSID_DOMDocument60; rclsid
0x180008ddc  lea     r8d, [rdx+1]; dwClsContext
0x180008de0  call    cs:__imp_CoCreateInstance
0x180008de6  mov     edi, eax
0x180008de8  test    eax, eax
0x180008dea  js      short loc_180008E3A
0x180008dec  mov     rcx, [rbx]
0x180008def  xor     edx, edx
0x180008df1  mov     rax, [rcx]
0x180008df4  mov     rax, [rax+1F8h]
0x180008dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e00  mov     edi, eax
0x180008e02  test    eax, eax
0x180008e04  js      short loc_180008E3A
0x180008e06  mov     rcx, [rbx]
0x180008e09  xor     edx, edx
0x180008e0b  mov     rax, [rcx]
0x180008e0e  mov     rax, [rax+220h]
0x180008e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1a  mov     edi, eax
0x180008e1c  test    eax, eax
0x180008e1e  js      short loc_180008E3A
0x180008e20  mov     rcx, [rbx]
0x180008e23  xor     edx, edx
0x180008e25  mov     rax, [rcx]
0x180008e28  mov     rax, [rax+230h]
0x180008e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e34  mov     edi, eax
0x180008e36  test    eax, eax
0x180008e38  jns     short loc_180008E55
0x180008e3a  mov     rcx, [rbx]
0x180008e3d  test    rcx, rcx
0x180008e40  jz      short loc_180008E55
0x180008e42  mov     rax, [rcx]
0x180008e45  mov     rax, [rax+10h]
0x180008e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e4e  mov     qword ptr [rbx], 0
0x180008e55  mov     eax, edi
0x180008e57  mov     rbx, [rsp+38h+arg_0]
0x180008e5c  add     rsp, 30h
0x180008e60  pop     rdi
0x180008e61  retn
```
