# std::_Copy_impl<ATL::CComVariant *,ATL::CComVariant *>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *)

- ea: `0x1800133dc`
- end: `0x180013424`
- name: `??$_Copy_impl@PEAVCComVariant@ATL@@PEAV12@@std@@YAPEAVCComVariant@ATL@@PEAV12@00@Z`
- size: `72`
- prototype: `__int64 __fastcall(struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013c0c`

## callees

- `0x180005728`
- `0x1800133dc`

## pseudocode

```c
VARIANTARG *__fastcall std::_Copy_impl<ATL::CComVariant *,ATL::CComVariant *>(
        struct tagVARIANT *a1,
        const struct tagVARIANT *a2,
        VARIANTARG *a3)
{
  const struct tagVARIANT *i; // rdi

  for ( i = a1; i != a2; ++i )
    ATL::CComVariant::InternalCopy(a3++, i);
  return a3;
}

```

## disassembly

```asm
0x1800133dc  mov     [rsp+arg_0], rbx
0x1800133e1  mov     [rsp+arg_8], rsi
0x1800133e6  push    rdi
0x1800133e7  sub     rsp, 20h
0x1800133eb  mov     rbx, r8
0x1800133ee  mov     rsi, rdx
0x1800133f1  mov     rdi, rcx
0x1800133f4  cmp     rcx, rdx
0x1800133f7  jz      short loc_180013411
0x1800133f9  mov     rdx, rdi; struct tagVARIANT *
0x1800133fc  mov     rcx, rbx; this
0x1800133ff  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z
0x180013404  add     rbx, 18h
0x180013408  add     rdi, 18h
0x18001340c  cmp     rdi, rsi
0x18001340f  jnz     short loc_1800133F9
0x180013411  mov     rsi, [rsp+28h+arg_8]
0x180013416  mov     rax, rbx
0x180013419  mov     rbx, [rsp+28h+arg_0]
0x18001341e  add     rsp, 20h
0x180013422  pop     rdi
0x180013423  retn
```
