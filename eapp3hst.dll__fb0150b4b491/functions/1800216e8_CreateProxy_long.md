# CreateProxy(long *)

- ea: `0x1800216e8`
- end: `0x180021767`
- name: `?CreateProxy@@YA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@PEAJ@Z`
- size: `127`
- prototype: `_QWORD *__fastcall(_QWORD *, HRESULT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021770`

## callees

- `0x18000d0e8`
- `0x1800216e8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021720`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021720`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall CreateProxy(_QWORD *a1, HRESULT *a2)
{
  HRESULT v4; // eax
  LPVOID v5; // rcx
  LPVOID v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v4 = CoCreateInstance(
         &GUID_1f7d1be9_7a50_40b6_a605_c4f3696f49c0,
         0,
         0x10004u,
         &GUID_32c5a81f_27c0_4e66_a894_786f646f1236,
         &v7);
  *a2 = v4;
  if ( v4 >= 0 )
  {
    v5 = v7;
    *a1 = v7;
    if ( v5 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 8LL))(v5);
  }
  else
  {
    *a1 = 0;
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v7);
  return a1;
}

```

## disassembly

```asm
0x1800216e8  mov     r11, rsp
0x1800216eb  mov     [r11+8], rbx
0x1800216ef  push    rdi
0x1800216f0  sub     rsp, 30h
0x1800216f4  mov     rbx, rdx
0x1800216f7  mov     rdi, rcx
0x1800216fa  mov     qword ptr [r11+10h], 0
0x180021702  lea     rax, [r11+10h]
0x180021706  mov     [r11-18h], rax
0x18002170a  lea     r9, _GUID_32c5a81f_27c0_4e66_a894_786f646f1236; riid
0x180021711  xor     edx, edx; pUnkOuter
0x180021713  mov     r8d, 10004h; dwClsContext
0x180021719  lea     rcx, _GUID_1f7d1be9_7a50_40b6_a605_c4f3696f49c0; rclsid
0x180021720  call    cs:__imp_CoCreateInstance
0x180021726  mov     [rbx], eax
0x180021728  test    eax, eax
0x18002172a  jns     short loc_180021735
0x18002172c  mov     qword ptr [rdi], 0
0x180021733  jmp     short loc_18002174F
0x180021735  mov     rcx, [rsp+38h+arg_8]
0x18002173a  mov     [rdi], rcx
0x18002173d  test    rcx, rcx
0x180021740  jz      short loc_18002174F
0x180021742  mov     rax, [rcx]
0x180021745  mov     rax, [rax+8]
0x180021749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002174e  nop
0x18002174f  lea     rcx, [rsp+38h+arg_8]
0x180021754  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180021759  mov     rax, rdi
0x18002175c  mov     rbx, [rsp+38h+arg_0]
0x180021761  add     rsp, 30h
0x180021765  pop     rdi
0x180021766  retn
```
