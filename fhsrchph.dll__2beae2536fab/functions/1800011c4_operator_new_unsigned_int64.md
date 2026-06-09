# operator new(unsigned __int64)

- ea: `0x1800011c4`
- end: `0x18000120b`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180001170`
- `0x180004224`
- `0x180004350`
- `0x1800044dc`
- `0x180004628`
- `0x180004750`
- `0x18000487c`
- `0x180006418`
- `0x180006b60`
- `0x180007dac`
- `0x18000a77c`
- `0x18000b26c`

## callees

- `0x18000117c`
- `0x1800011c4`
- `0x180001cf8`
- `0x180001d04`

## import_xrefs

- `msvcrt!malloc` at `0x1800011de`
- `msvcrt!malloc` at `0x1800011de`

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
0x1800011c4  push    rbx
0x1800011c6  sub     rsp, 40h
0x1800011ca  mov     rbx, rcx
0x1800011cd  jmp     short loc_1800011DE
0x1800011cf  mov     rcx, rbx; Size
0x1800011d2  call    _callnewh_0
0x1800011d7  test    eax, eax
0x1800011d9  jz      short loc_1800011EF
0x1800011db  mov     rcx, rbx; Size
0x1800011de  call    cs:__imp_malloc
0x1800011e4  test    rax, rax
0x1800011e7  jz      short loc_1800011CF
0x1800011e9  add     rsp, 40h
0x1800011ed  pop     rbx
0x1800011ee  retn
0x1800011ef  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800011f4  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800011f9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001200  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001205  call    _CxxThrowException_0
```
