# operator new(unsigned __int64)

- ea: `0x180002310`
- end: `0x180002358`
- name: `??2@YAPEAX_K@Z`
- size: `72`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x18000252c`
- `0x180003be4`
- `0x180003d18`
- `0x180003e20`
- `0x180003f78`
- `0x1800067a8`
- `0x18000750c`
- `0x180007628`
- `0x180007770`
- `0x180007894`
- `0x180008b90`
- `0x180008ce4`
- `0x1800093cc`
- `0x180009af8`
- `0x18000d260`
- `0x18000ede3`

## callees

- `0x1800020a5`
- `0x18000211c`
- `0x180002310`

## import_xrefs

- `msvcrt!malloc` at `0x18000232b`
- `msvcrt!malloc` at `0x18000232b`
- `msvcrt!_callnewh` at `0x18000231e`
- `msvcrt!_callnewh` at `0x18000231e`

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
0x180002310  push    rbx
0x180002312  sub     rsp, 40h
0x180002316  mov     rbx, rcx
0x180002319  jmp     short loc_18000232B
0x18000231b  mov     rcx, rbx; Size
0x18000231e  call    cs:__imp__callnewh
0x180002324  test    eax, eax
0x180002326  jz      short loc_18000233C
0x180002328  mov     rcx, rbx; Size
0x18000232b  call    cs:__imp_malloc
0x180002331  test    rax, rax
0x180002334  jz      short loc_18000231B
0x180002336  add     rsp, 40h
0x18000233a  pop     rbx
0x18000233b  retn
0x18000233c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002341  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180002346  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000234d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002352  call    _CxxThrowException_0
```
