# operator new(unsigned __int64)

- ea: `0x180001484`
- end: `0x1800014ca`
- name: `??2@YAPEAX_K@Z`
- size: `70`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ef4`
- `0x18000ce20`
- `0x1800110a4`
- `0x180013114`
- `0x180013390`
- `0x180017374`
- `0x180017428`
- `0x180017fe0`
- `0x1800180ec`
- `0x18001884c`
- `0x180019b1c`
- `0x180019e70`
- `0x18001a24c`
- `0x18001b428`
- `0x18001c4b8`

## callees

- `0x180001444`
- `0x180001484`
- `0x18000208d`
- `0x1800020a5`
- `0x1800020bd`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
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
0x180001484  push    rbx
0x180001486  sub     rsp, 40h
0x18000148a  mov     rbx, rcx
0x18000148d  jmp     short loc_18000149E
0x18000148f  mov     rcx, rbx; Size
0x180001492  call    _callnewh_0
0x180001497  test    eax, eax
0x180001499  jz      short loc_1800014AE
0x18000149b  mov     rcx, rbx; Size
0x18000149e  call    malloc_0
0x1800014a3  test    rax, rax
0x1800014a6  jz      short loc_18000148F
0x1800014a8  add     rsp, 40h
0x1800014ac  pop     rbx
0x1800014ad  retn
0x1800014ae  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800014b3  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800014b8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800014bf  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800014c4  call    _CxxThrowException_0
```
