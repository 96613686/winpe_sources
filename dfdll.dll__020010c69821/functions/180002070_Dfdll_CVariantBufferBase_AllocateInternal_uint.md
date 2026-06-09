# Dfdll::CVariantBufferBase::AllocateInternal(uint)

- ea: `0x180002070`
- end: `0x1800020d3`
- name: `?AllocateInternal@CVariantBufferBase@Dfdll@@MEAAPEAXI@Z`
- size: `99`
- prototype: `void *__fastcall(Dfdll::CVariantBufferBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002070`
- `0x180012c08`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800020b0`
- `OLEAUT32!__imp_VariantInit` at `0x1800020b0`

## pseudocode

```c
VARIANTARG *__fastcall Dfdll::CVariantBufferBase::AllocateInternal(Dfdll::CVariantBufferBase *this, unsigned int a2)
{
  __int64 v3; // rsi
  VARIANTARG *v4; // rax
  VARIANTARG *v5; // rdi
  VARIANTARG *v6; // rbx

  v3 = a2;
  v4 = (VARIANTARG *)operator new[](saturated_mul(a2, 0x18u));
  v5 = v4;
  if ( v4 && a2 )
  {
    v6 = v4;
    do
    {
      VariantInit(v6++);
      --v3;
    }
    while ( v3 );
  }
  return v5;
}

```

## disassembly

```asm
0x180002070  mov     [rsp+arg_0], rbx
0x180002075  mov     [rsp+arg_8], rsi
0x18000207a  push    rdi
0x18000207b  sub     rsp, 20h
0x18000207f  mov     ebx, edx
0x180002081  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002088  mov     esi, edx
0x18000208a  mov     eax, 18h
0x18000208f  mul     rbx
0x180002092  cmovo   rax, rcx
0x180002096  mov     rcx, rax; unsigned __int64
0x180002099  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000209e  mov     rdi, rax
0x1800020a1  test    rax, rax
0x1800020a4  jz      short loc_1800020C0
0x1800020a6  test    ebx, ebx
0x1800020a8  jz      short loc_1800020C0
0x1800020aa  mov     rbx, rax
0x1800020ad  mov     rcx, rbx; pvarg
0x1800020b0  call    cs:__imp_VariantInit
0x1800020b6  add     rbx, 18h
0x1800020ba  sub     rsi, 1
0x1800020be  jnz     short loc_1800020AD
0x1800020c0  mov     rbx, [rsp+28h+arg_0]
0x1800020c5  mov     rax, rdi
0x1800020c8  mov     rsi, [rsp+28h+arg_8]
0x1800020cd  add     rsp, 20h
0x1800020d1  pop     rdi
0x1800020d2  retn
```
