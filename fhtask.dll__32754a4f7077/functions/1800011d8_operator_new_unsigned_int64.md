# operator new(unsigned __int64)

- ea: `0x1800011d8`
- end: `0x18000121f`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x180001228`
- `0x180003214`
- `0x180003358`
- `0x18000349c`
- `0x180003600`
- `0x180003750`
- `0x1800077ec`
- `0x180007ba0`
- `0x180008b58`
- `0x180009fd8`

## callees

- `0x180001190`
- `0x1800011d8`
- `0x180001d0c`
- `0x180001d18`

## import_xrefs

- `msvcrt!malloc` at `0x1800011f2`
- `msvcrt!malloc` at `0x1800011f2`

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
0x1800011d8  push    rbx
0x1800011da  sub     rsp, 40h
0x1800011de  mov     rbx, rcx
0x1800011e1  jmp     short loc_1800011F2
0x1800011e3  mov     rcx, rbx; Size
0x1800011e6  call    _callnewh_0
0x1800011eb  test    eax, eax
0x1800011ed  jz      short loc_180001203
0x1800011ef  mov     rcx, rbx; Size
0x1800011f2  call    cs:__imp_malloc
0x1800011f8  test    rax, rax
0x1800011fb  jz      short loc_1800011E3
0x1800011fd  add     rsp, 40h
0x180001201  pop     rbx
0x180001202  retn
0x180001203  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001208  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000120d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001214  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001219  call    _CxxThrowException_0
```
