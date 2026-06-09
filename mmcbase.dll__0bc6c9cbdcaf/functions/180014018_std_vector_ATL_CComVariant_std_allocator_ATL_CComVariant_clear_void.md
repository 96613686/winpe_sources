# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::clear(void)

- ea: `0x180014018`
- end: `0x18001403a`
- name: `?clear@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAAXXZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013c0c`

## callees

- `0x180013e30`

## pseudocode

```c
VARIANTARG *__fastcall std::vector<ATL::CComVariant>::clear(VARIANTARG **a1)
{
  VARIANTARG *result; // rax

  std::vector<ATL::CComVariant>::_Destroy((__int64)a1, *a1, a1[1]);
  result = *a1;
  a1[1] = *a1;
  return result;
}

```

## disassembly

```asm
0x180014018  push    rbx
0x18001401a  sub     rsp, 20h
0x18001401e  mov     r8, [rcx+8]
0x180014022  mov     rbx, rcx
0x180014025  mov     rdx, [rcx]
0x180014028  call    ?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z; std::vector<ATL::CComVariant>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)
0x18001402d  mov     rax, [rbx]
0x180014030  mov     [rbx+8], rax
0x180014034  add     rsp, 20h
0x180014038  pop     rbx
0x180014039  retn
```
