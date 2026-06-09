# std::rotate<ATL::CComVariant *>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *)

- ea: `0x1800137ec`
- end: `0x180013840`
- name: `??$rotate@PEAVCComVariant@ATL@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000763c`

## callees

- `0x180013584`
- `0x1800137ec`

## pseudocode

```c
char *__fastcall std::rotate<ATL::CComVariant *>(VARIANTARG *a1, __int64 a2, char *a3)
{
  if ( a1 != (VARIANTARG *)a2 && (char *)a2 != a3 )
    std::_Rotate<ATL::CComVariant *,__int64,ATL::CComVariant>(a1, a2, a3);
  return (char *)a1 + 8 * ((__int64)&a3[-a2] >> 3);
}

```

## disassembly

```asm
0x1800137ec  mov     [rsp+arg_0], rbx
0x1800137f1  mov     [rsp+arg_8], rsi
0x1800137f6  push    rdi
0x1800137f7  sub     rsp, 30h
0x1800137fb  mov     rbx, r8
0x1800137fe  mov     rdi, rdx
0x180013801  mov     rsi, rcx
0x180013804  cmp     rcx, rdx
0x180013807  jz      short loc_180013813
0x180013809  cmp     rdx, rbx
0x18001380c  jz      short loc_180013813
0x18001380e  call    ??$_Rotate@PEAVCComVariant@ATL@@_JV12@@std@@YAXPEAVCComVariant@ATL@@00PEA_J0@Z; std::_Rotate<ATL::CComVariant *,__int64,ATL::CComVariant>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,__int64 *,ATL::CComVariant *)
0x180013813  sub     rbx, rdi
0x180013816  mov     rax, 0AAAAAAAAAAAAAAABh
0x180013820  sar     rbx, 3
0x180013824  imul    rbx, rax
0x180013828  lea     rax, [rbx+rbx*2]
0x18001382c  mov     rbx, [rsp+38h+arg_0]
0x180013831  lea     rax, [rsi+rax*8]
0x180013835  mov     rsi, [rsp+38h+arg_8]
0x18001383a  add     rsp, 30h
0x18001383e  pop     rdi
0x18001383f  retn
```
