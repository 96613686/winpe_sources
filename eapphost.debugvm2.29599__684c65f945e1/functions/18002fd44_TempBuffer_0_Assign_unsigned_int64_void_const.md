# TempBuffer<0>::Assign(unsigned __int64,void const *)

- ea: `0x18002fd44`
- end: `0x18002fda7`
- name: `?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z`
- size: `99`
- prototype: ``
- caller_count: `26`
- callee_count: `5`
- tags: ``

## callers

- `0x180012900`
- `0x180013430`
- `0x180013800`
- `0x18001446c`
- `0x180014990`
- `0x180015140`
- `0x180015aa0`
- `0x180016610`
- `0x180018020`
- `0x1800183d0`
- `0x180018740`
- `0x180018ffc`
- `0x18001d9bc`
- `0x18001e3a8`
- `0x180025760`
- `0x180025b18`
- `0x1800269ac`
- `0x180026d2c`
- `0x180026e60`
- `0x180028f64`
- `0x18002a0b8`
- `0x1800302fc`
- `0x180030564`
- `0x180032a04`
- `0x1800335f8`
- `0x1800336b4`

## callees

- `0x1800072cc`
- `0x18002ef80`
- `0x18002fd44`
- `0x18002fdb0`
- `0x180033d84`

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
0x18002fd44  mov     [rsp+arg_0], rbx
0x18002fd49  mov     [rsp+arg_8], rsi
0x18002fd4e  push    rdi
0x18002fd4f  sub     rsp, 20h
0x18002fd53  mov     rsi, r8
0x18002fd56  mov     rdi, rdx
0x18002fd59  mov     rbx, rcx
0x18002fd5c  test    rdx, rdx
0x18002fd5f  jnz     short loc_18002FD6E
0x18002fd61  mov     rcx, [rcx]; void *
0x18002fd64  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002fd69  mov     [rbx], rdi
0x18002fd6c  jmp     short loc_18002FD93
0x18002fd6e  xor     r8d, r8d
0x18002fd71  call    ?ReserveBytesNoThrow@?$TempBuffer@$0A@@@IEAA_N_K0@Z; TempBuffer<0>::ReserveBytesNoThrow(unsigned __int64,unsigned __int64)
0x18002fd76  test    al, al
0x18002fd78  jnz     short loc_18002FD80
0x18002fd7a  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
0x18002fd80  test    rsi, rsi
0x18002fd83  jz      short loc_18002FD93
0x18002fd85  mov     rcx, [rbx]; void *
0x18002fd88  mov     r8, rdi; Size
0x18002fd8b  mov     rdx, rsi; Src
0x18002fd8e  call    memmove_0
0x18002fd93  mov     rsi, [rsp+28h+arg_8]
0x18002fd98  mov     [rbx+8], rdi
0x18002fd9c  mov     rbx, [rsp+28h+arg_0]
0x18002fda1  add     rsp, 20h
0x18002fda5  pop     rdi
0x18002fda6  retn
```
