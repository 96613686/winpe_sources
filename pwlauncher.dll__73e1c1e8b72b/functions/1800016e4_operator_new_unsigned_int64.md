# operator new(unsigned __int64)

- ea: `0x1800016e4`
- end: `0x18000172b`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180001650`
- `0x18000ab94`
- `0x18000bcc4`
- `0x18000bdb0`
- `0x18000beb0`
- `0x18000cbd4`
- `0x18000ccb0`
- `0x18000f288`

## callees

- `0x180001684`
- `0x1800016e4`
- `0x18000213c`
- `0x180002148`

## import_xrefs

- `msvcrt!malloc` at `0x1800016fe`
- `msvcrt!malloc` at `0x1800016fe`

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
0x1800016e4  push    rbx
0x1800016e6  sub     rsp, 40h
0x1800016ea  mov     rbx, rcx
0x1800016ed  jmp     short loc_1800016FE
0x1800016ef  mov     rcx, rbx; Size
0x1800016f2  call    _callnewh_0
0x1800016f7  test    eax, eax
0x1800016f9  jz      short loc_18000170F
0x1800016fb  mov     rcx, rbx; Size
0x1800016fe  call    cs:__imp_malloc
0x180001704  test    rax, rax
0x180001707  jz      short loc_1800016EF
0x180001709  add     rsp, 40h
0x18000170d  pop     rbx
0x18000170e  retn
0x18000170f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001714  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180001719  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001720  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001725  call    _CxxThrowException_0
```
