# operator new(unsigned __int64)

- ea: `0x18000cadc`
- end: `0x18000cb23`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180003f00`
- `0x180007330`
- `0x18000b1e8`
- `0x18000bd64`
- `0x18000d0a8`
- `0x18000eefc`

## callees

- `0x18000ca7c`
- `0x18000cadc`
- `0x18000d24c`
- `0x18000d258`

## import_xrefs

- `msvcrt!malloc` at `0x18000caf6`
- `msvcrt!malloc` at `0x18000caf6`

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
    if ( !callnewh_0(i) )
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
0x18000cadc  push    rbx
0x18000cade  sub     rsp, 40h
0x18000cae2  mov     rbx, rcx
0x18000cae5  jmp     short loc_18000CAF6
0x18000cae7  mov     rcx, rbx; Size
0x18000caea  call    _callnewh_0
0x18000caef  test    eax, eax
0x18000caf1  jz      short loc_18000CB07
0x18000caf3  mov     rcx, rbx; Size
0x18000caf6  call    cs:__imp_malloc
0x18000cafc  test    rax, rax
0x18000caff  jz      short loc_18000CAE7
0x18000cb01  add     rsp, 40h
0x18000cb05  pop     rbx
0x18000cb06  retn
0x18000cb07  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000cb0c  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000cb11  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000cb18  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000cb1d  call    _CxxThrowException_0
```
