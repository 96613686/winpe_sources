# operator new(unsigned __int64)

- ea: `0x180001f90`
- end: `0x180001fd7`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ae4`

## callees

- `0x180001f30`
- `0x180001f90`
- `0x18000205c`
- `0x180002068`

## import_xrefs

- `msvcrt!malloc` at `0x180001faa`
- `msvcrt!malloc` at `0x180001faa`

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
0x180001f90  push    rbx
0x180001f92  sub     rsp, 40h
0x180001f96  mov     rbx, rcx
0x180001f99  jmp     short loc_180001FAA
0x180001f9b  mov     rcx, rbx; Size
0x180001f9e  call    _callnewh_0
0x180001fa3  test    eax, eax
0x180001fa5  jz      short loc_180001FBB
0x180001fa7  mov     rcx, rbx; Size
0x180001faa  call    cs:__imp_malloc
0x180001fb0  test    rax, rax
0x180001fb3  jz      short loc_180001F9B
0x180001fb5  add     rsp, 40h
0x180001fb9  pop     rbx
0x180001fba  retn
0x180001fbb  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001fc0  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180001fc5  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001fcc  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001fd1  call    _CxxThrowException_0
```
