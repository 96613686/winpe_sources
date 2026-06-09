# Dfdll::CVariantBufferBase::Free(void * &,uint &)

- ea: `0x180002de0`
- end: `0x180002e43`
- name: `?Free@CVariantBufferBase@Dfdll@@MEAAXAEAPEAXAEAI@Z`
- size: `99`
- prototype: `void __fastcall(Dfdll::CVariantBufferBase *__hidden this, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180001ad0`
- `0x180001e10`

## callees

- `0x180002de0`
- `0x180012b30`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180002e12`
- `OLEAUT32!__imp_VariantClear` at `0x180002e12`

## pseudocode

```c
void __fastcall Dfdll::CVariantBufferBase::Free(Dfdll::CVariantBufferBase *this, VARIANTARG **a2, unsigned int *a3)
{
  VARIANTARG *v3; // rsi
  __int64 i; // rdi

  v3 = *a2;
  if ( *a2 )
  {
    for ( i = 0; (unsigned int)i < *a3; i = (unsigned int)(i + 1) )
      VariantClear(&v3[i]);
    operator delete(v3, (const struct std::nothrow_t *)a2);
    *a2 = 0;
  }
  *a3 = 0;
}

```

## disassembly

```asm
0x180002de0  mov     [rsp+arg_0], rbx
0x180002de5  mov     [rsp+arg_8], rsi
0x180002dea  mov     [rsp+arg_10], rdi
0x180002def  push    r14
0x180002df1  sub     rsp, 20h
0x180002df5  mov     rsi, [rdx]
0x180002df8  mov     rbx, r8
0x180002dfb  mov     r14, rdx
0x180002dfe  test    rsi, rsi
0x180002e01  jz      short loc_180002E2A
0x180002e03  xor     edi, edi
0x180002e05  cmp     [r8], edi
0x180002e08  jbe     short loc_180002E1E
0x180002e0a  lea     rdx, [rdi+rdi*2]
0x180002e0e  lea     rcx, [rsi+rdx*8]; pvarg
0x180002e12  call    cs:__imp_VariantClear
0x180002e18  inc     edi
0x180002e1a  cmp     edi, [rbx]
0x180002e1c  jb      short loc_180002E0A
0x180002e1e  mov     rcx, rsi; void *
0x180002e21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002e26  and     qword ptr [r14], 0
0x180002e2a  and     dword ptr [rbx], 0
0x180002e2d  mov     rbx, [rsp+28h+arg_0]
0x180002e32  mov     rsi, [rsp+28h+arg_8]
0x180002e37  mov     rdi, [rsp+28h+arg_10]
0x180002e3c  add     rsp, 20h
0x180002e40  pop     r14
0x180002e42  retn
```
