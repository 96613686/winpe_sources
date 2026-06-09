# TempBuffer<0>::Assign(unsigned __int64,void const *)

- ea: `0x180030f54`
- end: `0x180030fb8`
- name: `?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z`
- size: `100`
- prototype: ``
- caller_count: `26`
- callee_count: `5`
- tags: ``

## callers

- `0x180013090`
- `0x180013bfc`
- `0x180013ff0`
- `0x180014c8c`
- `0x1800151b0`
- `0x180015980`
- `0x180016300`
- `0x180016e90`
- `0x180018990`
- `0x180018d40`
- `0x1800190d0`
- `0x1800199bc`
- `0x18001e4ac`
- `0x18001eec4`
- `0x180026488`
- `0x180026850`
- `0x180027708`
- `0x180027a98`
- `0x180027bcc`
- `0x180029d84`
- `0x18002aee0`
- `0x18003152c`
- `0x180031778`
- `0x180033da0`
- `0x1800349ac`
- `0x180034a68`

## callees

- `0x180007564`
- `0x180030088`
- `0x180030f54`
- `0x180030fc0`
- `0x180035144`

## pseudocode

```c
void __fastcall TempBuffer<0>::Assign(__int64 a1, size_t a2, const void *a3)
{
  if ( a2 )
  {
    if ( !(unsigned __int8)TempBuffer<0>::ReserveBytesNoThrow(a1, a2, 0) )
      ThrowNewFailure();
    if ( a3 )
      memmove_0(*(void **)a1, a3, a2);
  }
  else
  {
    HeapAllocator::Free(*(void **)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = a2;
}

```

## disassembly

```asm
0x180030f54  mov     [rsp+arg_0], rbx
0x180030f59  mov     [rsp+arg_8], rsi
0x180030f5e  push    rdi
0x180030f5f  sub     rsp, 20h
0x180030f63  mov     rsi, r8
0x180030f66  mov     rdi, rdx
0x180030f69  mov     rbx, rcx
0x180030f6c  test    rdx, rdx
0x180030f6f  jnz     short loc_180030F7E
0x180030f71  mov     rcx, [rcx]; void *
0x180030f74  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030f79  mov     [rbx], rdi
0x180030f7c  jmp     short loc_180030FA3
0x180030f7e  xor     r8d, r8d
0x180030f81  call    ?ReserveBytesNoThrow@?$TempBuffer@$0A@@@IEAA_N_K0@Z; TempBuffer<0>::ReserveBytesNoThrow(unsigned __int64,unsigned __int64)
0x180030f86  test    al, al
0x180030f88  jnz     short loc_180030F90
0x180030f8a  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
0x180030f90  test    rsi, rsi
0x180030f93  jz      short loc_180030FA3
0x180030f95  mov     rcx, [rbx]; void *
0x180030f98  mov     r8, rdi; Size
0x180030f9b  mov     rdx, rsi; Src
0x180030f9e  call    memmove_0
0x180030fa3  mov     rsi, [rsp+28h+arg_8]
0x180030fa8  mov     [rbx+8], rdi
0x180030fac  mov     rbx, [rsp+28h+arg_0]
0x180030fb1  add     rsp, 20h
0x180030fb5  pop     rdi
0x180030fb6  retn
```
