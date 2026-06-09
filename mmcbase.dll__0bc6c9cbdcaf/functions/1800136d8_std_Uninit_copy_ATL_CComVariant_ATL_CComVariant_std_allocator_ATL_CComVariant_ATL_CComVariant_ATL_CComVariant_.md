# std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800136d8`
- end: `0x180013738`
- name: `??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000763c`
- `0x180013c0c`

## callees

- `0x180005728`
- `0x1800136d8`

## pseudocode

```c
VARIANTARG *__fastcall std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(
        struct tagVARIANT *a1,
        const struct tagVARIANT *a2,
        VARIANTARG *a3)
{
  const struct tagVARIANT *i; // rdi

  for ( i = a1; i != a2; ++i )
  {
    a3->vt = 0;
    ATL::CComVariant::InternalCopy(a3++, i);
  }
  return a3;
}

```

## disassembly

```asm
0x1800136d8  mov     rax, rsp
0x1800136db  mov     [rax+8], rbx
0x1800136df  mov     [rax+10h], rsi
0x1800136e3  mov     [rax+20h], r9
0x1800136e7  mov     [rax+18h], r8
0x1800136eb  push    rdi
0x1800136ec  sub     rsp, 20h
0x1800136f0  mov     rbx, r8
0x1800136f3  mov     rsi, rdx
0x1800136f6  mov     rdi, rcx
0x1800136f9  mov     [rsp+28h+arg_18], rbx
0x1800136fe  cmp     rcx, rdx
0x180013701  jz      short loc_180013725
0x180013703  xor     eax, eax
0x180013705  mov     [rbx], ax
0x180013708  mov     rdx, rdi; struct tagVARIANT *
0x18001370b  mov     rcx, rbx; this
0x18001370e  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180013713  add     rbx, 18h
0x180013717  mov     [rsp+28h+arg_10], rbx
0x18001371c  add     rdi, 18h
0x180013720  cmp     rdi, rsi
0x180013723  jnz     short loc_180013703
0x180013725  mov     rax, rbx
0x180013728  mov     rbx, [rsp+28h+arg_0]
0x18001372d  mov     rsi, [rsp+28h+arg_8]
0x180013732  add     rsp, 20h
0x180013736  pop     rdi
0x180013737  retn
```
