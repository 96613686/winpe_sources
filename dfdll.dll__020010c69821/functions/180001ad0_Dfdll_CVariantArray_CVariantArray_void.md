# Dfdll::CVariantArray::~CVariantArray(void)

- ea: `0x180001ad0`
- end: `0x180001b33`
- name: `??1CVariantArray@Dfdll@@UEAA@XZ`
- size: `99`
- prototype: `void __fastcall(Dfdll::CVariantArray *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001dd0`
- `0x180002720`
- `0x180005010`
- `0x180005130`
- `0x180005400`
- `0x1800060d0`
- `0x1800074c0`
- `0x180007640`
- `0x18001f056`
- `0x18001f176`

## callees

- `0x180002de0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Dfdll::CVariantArray::~CVariantArray(Dfdll::CVariantArray *this)
{
  char *v2; // rsi

  v2 = (char *)this + 8;
  *((_QWORD *)this + 1) = &Dfdll::CVariantBufferBase::`vftable';
  Dfdll::CVariantBufferBase::Free(
    (Dfdll::CVariantArray *)((char *)this + 8),
    (void **)this + 2,
    (unsigned int *)this + 6);
  *((_QWORD *)v2 + 1) = 0;
  *((_DWORD *)v2 + 4) = 0;
  *(_QWORD *)v2 = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180001ad0  mov     [rsp+arg_0], rbx
0x180001ad5  mov     [rsp+arg_8], rsi
0x180001ada  mov     [rsp+arg_10], rdi
0x180001adf  push    r14
0x180001ae1  sub     rsp, 20h
0x180001ae5  mov     r14, rcx
0x180001ae8  lea     rsi, [rcx+8]
0x180001aec  lea     rax, ??_7CVariantBufferBase@Dfdll@@6B@; const Dfdll::CVariantBufferBase::`vftable'
0x180001af3  mov     [rsi], rax
0x180001af6  lea     r8, [rsi+10h]; unsigned int *
0x180001afa  lea     rdx, [rsi+8]; void **
0x180001afe  mov     rcx, rsi; this
0x180001b01  call    ?Free@CVariantBufferBase@Dfdll@@MEAAXAEAPEAXAEAI@Z; Dfdll::CVariantBufferBase::Free(void * &,uint &)
0x180001b06  nop
0x180001b07  and     qword ptr [rsi+8], 0
0x180001b0c  and     dword ptr [rsi+10h], 0
0x180001b10  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180001b17  mov     [rsi], rax
0x180001b1a  mov     [r14], rax
0x180001b1d  mov     rbx, [rsp+28h+arg_0]
0x180001b22  mov     rsi, [rsp+28h+arg_8]
0x180001b27  mov     rdi, [rsp+28h+arg_10]
0x180001b2c  add     rsp, 20h
0x180001b30  pop     r14
0x180001b32  retn
```
