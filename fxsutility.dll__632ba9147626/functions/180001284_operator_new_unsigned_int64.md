# operator new(unsigned __int64)

- ea: `0x180001284`
- end: `0x1800012ca`
- name: `??2@YAPEAX_K@Z`
- size: `70`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180001320`
- `0x180001f9c`
- `0x18000212c`
- `0x180002b80`
- `0x180002c50`
- `0x180004bf0`
- `0x180013b44`

## callees

- `0x18000122c`
- `0x180001284`
- `0x180001869`
- `0x180001875`
- `0x1800018bc`

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
0x180001284  push    rbx
0x180001286  sub     rsp, 40h
0x18000128a  mov     rbx, rcx
0x18000128d  jmp     short loc_18000129E
0x18000128f  mov     rcx, rbx; Size
0x180001292  call    _callnewh_0
0x180001297  test    eax, eax
0x180001299  jz      short loc_1800012AE
0x18000129b  mov     rcx, rbx; Size
0x18000129e  call    malloc_0
0x1800012a3  test    rax, rax
0x1800012a6  jz      short loc_18000128F
0x1800012a8  add     rsp, 40h
0x1800012ac  pop     rbx
0x1800012ad  retn
0x1800012ae  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800012b3  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800012b8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800012bf  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800012c4  call    _CxxThrowException_0
```
