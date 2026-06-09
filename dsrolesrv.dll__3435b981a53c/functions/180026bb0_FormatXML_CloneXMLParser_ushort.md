# FormatXML(CloneXMLParser *,ushort * *)

- ea: `0x180026bb0`
- end: `0x180026c58`
- name: `?FormatXML@@YAJPEAVCloneXMLParser@@PEAPEAG@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct CloneXMLParser *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002477c`

## callees

- `0x180026bb0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026bf1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026bf1`

## pseudocode

```c
__int64 __fastcall FormatXML(struct CloneXMLParser *a1, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  LPVOID v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  *a2 = 0;
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &v6);
  if ( !v4 )
  {
    v4 = (*(__int64 (__fastcall **)(struct CloneXMLParser *, LPVOID))(*(_QWORD *)a1 + 8LL))(a1, v6);
    if ( !v4 )
      v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 **))(*(_QWORD *)v6 + 272LL))(v6, a2);
  }
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return v4;
}

```

## disassembly

```asm
0x180026bb0  mov     r11, rsp
0x180026bb3  mov     [r11+8], rbx
0x180026bb7  mov     [r11+18h], rsi
0x180026bbb  push    rdi
0x180026bbc  sub     rsp, 30h
0x180026bc0  mov     rdi, rdx
0x180026bc3  mov     rsi, rcx
0x180026bc6  mov     qword ptr [r11+10h], 0
0x180026bce  mov     qword ptr [rdx], 0
0x180026bd5  lea     rax, [r11+10h]
0x180026bd9  mov     [r11-18h], rax
0x180026bdd  lea     r9, IID_IXMLDOMDocument; riid
0x180026be4  xor     edx, edx; pUnkOuter
0x180026be6  lea     r8d, [rdx+1]; dwClsContext
0x180026bea  lea     rcx, CLSID_DOMDocument60; rclsid
0x180026bf1  call    cs:__imp_CoCreateInstance
0x180026bf7  mov     ebx, eax
0x180026bf9  test    eax, eax
0x180026bfb  jnz     short loc_180026C30
0x180026bfd  mov     rax, [rsi]
0x180026c00  mov     rdx, [rsp+38h+arg_8]
0x180026c05  mov     rcx, rsi
0x180026c08  mov     rax, [rax+8]
0x180026c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c11  mov     ebx, eax
0x180026c13  test    eax, eax
0x180026c15  jnz     short loc_180026C30
0x180026c17  mov     rcx, [rsp+38h+arg_8]
0x180026c1c  mov     rax, [rcx]
0x180026c1f  mov     rdx, rdi
0x180026c22  mov     rax, [rax+110h]
0x180026c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c2e  mov     ebx, eax
0x180026c30  mov     rcx, [rsp+38h+arg_8]
0x180026c35  test    rcx, rcx
0x180026c38  jz      short loc_180026C46
0x180026c3a  mov     rax, [rcx]
0x180026c3d  mov     rax, [rax+10h]
0x180026c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c46  mov     eax, ebx
0x180026c48  mov     rbx, [rsp+38h+arg_0]
0x180026c4d  mov     rsi, [rsp+38h+arg_10]
0x180026c52  add     rsp, 30h
0x180026c56  pop     rdi
0x180026c57  retn
0x18002c806  push    rbp
0x18002c808  sub     rsp, 30h
0x18002c80c  mov     rbp, rdx
0x18002c80f  mov     rcx, [rbp+48h]
0x18002c813  test    rcx, rcx
0x18002c816  jz      short loc_18002C825
0x18002c818  mov     rax, [rcx]
0x18002c81b  mov     rax, [rax+10h]
0x18002c81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c824  nop
0x18002c825  add     rsp, 30h
0x18002c829  pop     rbp
0x18002c82a  retn
```
