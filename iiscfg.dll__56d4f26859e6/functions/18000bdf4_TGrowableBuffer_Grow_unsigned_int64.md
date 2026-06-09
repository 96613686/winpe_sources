# TGrowableBuffer::Grow(unsigned __int64)

- ea: `0x18000bdf4`
- end: `0x18000be51`
- name: `?Grow@TGrowableBuffer@@QEAAX_K@Z`
- size: `93`
- prototype: `void(TGrowableBuffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000a1c8`
- `0x18000a6b4`
- `0x18000a898`
- `0x18000c4d0`

## callees

- `0x18000bdf4`
- `0x18002df9b`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000be0d`
- `ole32!CoTaskMemFree` at `0x18000be0d`
- `ole32!CoTaskMemAlloc` at `0x18000be16`
- `ole32!CoTaskMemAlloc` at `0x18000be16`

## pseudocode

```c
void __fastcall TGrowableBuffer::Grow(LPVOID *this, SIZE_T a2)
{
  LPVOID v4; // rax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 > (unsigned __int64)this[1] )
  {
    CoTaskMemFree(*this);
    v4 = CoTaskMemAlloc(a2);
    *this = v4;
    if ( !v4 )
    {
      this[1] = 0;
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    this[1] = (LPVOID)a2;
  }
}

```

## disassembly

```asm
0x18000bdf4  mov     [rsp+arg_8], rbx
0x18000bdf9  push    rdi
0x18000bdfa  sub     rsp, 20h
0x18000bdfe  mov     rdi, rdx
0x18000be01  mov     rbx, rcx
0x18000be04  cmp     rdx, [rcx+8]
0x18000be08  jbe     short loc_18000BE46
0x18000be0a  mov     rcx, [rcx]; pv
0x18000be0d  call    cs:__imp_CoTaskMemFree
0x18000be13  mov     rcx, rdi; cb
0x18000be16  call    cs:__imp_CoTaskMemAlloc
0x18000be1c  mov     [rbx], rax
0x18000be1f  test    rax, rax
0x18000be22  jnz     short loc_18000BE42
0x18000be24  lea     rdx, _TI1J; pThrowInfo
0x18000be2b  mov     [rbx+8], rax
0x18000be2f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000be34  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x18000be3c  call    _CxxThrowException_0
0x18000be42  mov     [rbx+8], rdi
0x18000be46  mov     rbx, [rsp+28h+arg_8]
0x18000be4b  add     rsp, 20h
0x18000be4f  pop     rdi
0x18000be50  retn
```
