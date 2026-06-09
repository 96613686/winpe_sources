# operator new(unsigned __int64)

- ea: `0x18000d98c`
- end: `0x18000d9d4`
- name: `??2@YAPEAX_K@Z`
- size: `72`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x180002428`
- `0x18000dc5c`
- `0x18000eab8`
- `0x18000f538`
- `0x18000f6c0`
- `0x18000f828`
- `0x18000f960`
- `0x18000fac0`
- `0x18000fbec`
- `0x18001053c`
- `0x180012814`
- `0x180014904`
- `0x180016634`
- `0x180016674`
- `0x180017050`
- `0x180018a25`
- `0x180018a9d`

## callees

- `0x180001e0e`
- `0x18000d5c0`
- `0x18000d98c`

## import_xrefs

- `msvcrt!malloc` at `0x18000d9a7`
- `msvcrt!malloc` at `0x18000d9a7`
- `msvcrt!_callnewh` at `0x18000d99a`
- `msvcrt!_callnewh` at `0x18000d99a`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !_callnewh(i) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d98c  push    rbx
0x18000d98e  sub     rsp, 40h
0x18000d992  mov     rbx, rcx
0x18000d995  jmp     short loc_18000D9A7
0x18000d997  mov     rcx, rbx; Size
0x18000d99a  call    cs:__imp__callnewh
0x18000d9a0  test    eax, eax
0x18000d9a2  jz      short loc_18000D9B8
0x18000d9a4  mov     rcx, rbx; Size
0x18000d9a7  call    cs:__imp_malloc
0x18000d9ad  test    rax, rax
0x18000d9b0  jz      short loc_18000D997
0x18000d9b2  add     rsp, 40h
0x18000d9b6  pop     rbx
0x18000d9b7  retn
0x18000d9b8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000d9bd  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000d9c2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000d9c9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000d9ce  call    _CxxThrowException_0
```
