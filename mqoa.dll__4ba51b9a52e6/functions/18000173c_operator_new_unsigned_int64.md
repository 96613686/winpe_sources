# operator new(unsigned __int64)

- ea: `0x18000173c`
- end: `0x180001783`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `72`
- callee_count: `4`
- tags: ``

## callers

- `0x180005880`
- `0x180009a54`
- `0x180009af0`
- `0x180009d90`
- `0x180009f54`
- `0x18000a250`
- `0x18000ba00`
- `0x18000cce4`
- `0x18000cdcc`
- `0x18000ceb4`
- `0x18000cfa8`
- `0x18000d0c0`
- `0x18000d1bc`
- `0x18000d2a4`
- `0x18000d38c`
- `0x18000d474`
- `0x18000d55c`
- `0x18000d644`
- `0x18000d72c`
- `0x18000d814`
- `0x18000d8e4`
- `0x18000d9b4`
- `0x18000da68`
- `0x18000db68`
- `0x18000dc4c`
- `0x18000dd00`
- `0x18000ddd0`
- `0x18000de84`
- `0x18000df38`
- `0x18000dfec`
- `0x18000e0a0`
- `0x18000e170`
- `0x18000e260`
- `0x18000e560`
- `0x18000ec10`
- `0x18000f23c`
- `0x18000fae0`
- `0x1800138e0`
- `0x180013970`
- `0x180013a08`
- `0x18001401c`
- `0x1800140bc`
- `0x18001415c`
- `0x180014210`
- `0x180015a64`
- `0x18001a190`
- `0x18001a270`
- `0x18001a74c`
- `0x18001aa00`
- `0x18001c928`

## callees

- `0x18000173c`
- `0x1800023af`
- `0x1800023bb`
- `0x18000334c`

## import_xrefs

- `msvcrt!malloc` at `0x180001756`
- `msvcrt!malloc` at `0x180001756`

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
0x18000173c  push    rbx
0x18000173e  sub     rsp, 40h
0x180001742  mov     rbx, rcx
0x180001745  jmp     short loc_180001756
0x180001747  mov     rcx, rbx; Size
0x18000174a  call    _callnewh_0
0x18000174f  test    eax, eax
0x180001751  jz      short loc_180001767
0x180001753  mov     rcx, rbx; Size
0x180001756  call    cs:__imp_malloc
0x18000175c  test    rax, rax
0x18000175f  jz      short loc_180001747
0x180001761  add     rsp, 40h
0x180001765  pop     rbx
0x180001766  retn
0x180001767  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000176c  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180001771  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001778  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000177d  call    _CxxThrowException_0
```
