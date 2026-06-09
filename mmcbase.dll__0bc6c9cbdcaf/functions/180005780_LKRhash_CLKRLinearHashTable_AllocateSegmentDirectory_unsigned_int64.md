# LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(unsigned __int64)

- ea: `0x180005780`
- end: `0x1800057e8`
- name: `?_AllocateSegmentDirectory@CLKRLinearHashTable@LKRhash@@AEAAQEAVCDirEntry@2@_K@Z`
- size: `104`
- prototype: `struct LKRhash::CDirEntry *__fastcall(LKRhash::CLKRLinearHashTable *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d60`
- `0x18001a07c`

## callees

- `0x180005780`
- `0x18001b522`
- `0x18001d010`

## pseudocode

```c
struct LKRhash::CDirEntry *__fastcall LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(
        LKRhash::CLKRLinearHashTable *this,
        __int64 a2)
{
  __int64 v2; // rdi
  struct LKRhash::CDirEntry *result; // rax
  struct LKRhash::CDirEntry *v5; // rsi

  v2 = 8 * a2;
  result = (struct LKRhash::CDirEntry *)(***((__int64 (__fastcall ****)(_QWORD, __int64, __int64))this + 18))(
                                          *((_QWORD *)this + 18),
                                          8 * a2,
                                          3);
  v5 = result;
  if ( result )
  {
    if ( a2 )
    {
      memset_0(result, 0, v2 & 0xFFFFFFFFFFFFFFF8uLL);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005780  mov     [rsp+arg_0], rbx
0x180005785  mov     [rsp+arg_8], rsi
0x18000578a  push    rdi
0x18000578b  sub     rsp, 20h
0x18000578f  mov     rcx, [rcx+90h]
0x180005796  lea     rdi, ds:0[rdx*8]
0x18000579e  mov     rbx, rdx
0x1800057a1  mov     r8d, 3
0x1800057a7  mov     rdx, rdi
0x1800057aa  mov     rax, [rcx]
0x1800057ad  mov     rax, [rax]
0x1800057b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b5  mov     rsi, rax
0x1800057b8  test    rax, rax
0x1800057bb  jz      short loc_1800057C2
0x1800057bd  test    rbx, rbx
0x1800057c0  jnz     short loc_1800057D2
0x1800057c2  mov     rbx, [rsp+28h+arg_0]
0x1800057c7  mov     rsi, [rsp+28h+arg_8]
0x1800057cc  add     rsp, 20h
0x1800057d0  pop     rdi
0x1800057d1  retn
0x1800057d2  and     rdi, 0FFFFFFFFFFFFFFF8h
0x1800057d6  xor     edx, edx; Val
0x1800057d8  mov     r8, rdi; Size
0x1800057db  mov     rcx, rsi; void *
0x1800057de  call    memset_0
0x1800057e3  mov     rax, rsi
0x1800057e6  jmp     short loc_1800057C2
```
