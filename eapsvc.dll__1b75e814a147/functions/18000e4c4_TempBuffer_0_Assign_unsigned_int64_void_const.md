# TempBuffer<0>::Assign(unsigned __int64,void const *)

- ea: `0x18000e4c4`
- end: `0x18000e527`
- name: `?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z`
- size: `99`
- prototype: `void __fastcall(__int64, size_t, const void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000cf50`

## callees

- `0x18000ab70`
- `0x18000e4ac`
- `0x18000e4c4`
- `0x18000e530`
- `0x180014e98`

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
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = a2;
}

```

## disassembly

```asm
0x18000e4c4  mov     [rsp+arg_0], rbx
0x18000e4c9  mov     [rsp+arg_8], rsi
0x18000e4ce  push    rdi
0x18000e4cf  sub     rsp, 20h
0x18000e4d3  mov     rsi, r8
0x18000e4d6  mov     rdi, rdx
0x18000e4d9  mov     rbx, rcx
0x18000e4dc  test    rdx, rdx
0x18000e4df  jnz     short loc_18000E4EE
0x18000e4e1  mov     rcx, [rcx]; lpMem
0x18000e4e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e4e9  mov     [rbx], rdi
0x18000e4ec  jmp     short loc_18000E50D
0x18000e4ee  xor     r8d, r8d
0x18000e4f1  call    ?ReserveBytesNoThrow@?$TempBuffer@$0A@@@IEAA_N_K0@Z; TempBuffer<0>::ReserveBytesNoThrow(unsigned __int64,unsigned __int64)
0x18000e4f6  test    al, al
0x18000e4f8  jz      short loc_18000E521
0x18000e4fa  test    rsi, rsi
0x18000e4fd  jz      short loc_18000E50D
0x18000e4ff  mov     rcx, [rbx]; void *
0x18000e502  mov     r8, rdi; Size
0x18000e505  mov     rdx, rsi; Src
0x18000e508  call    memmove_0
0x18000e50d  mov     rsi, [rsp+28h+arg_8]
0x18000e512  mov     [rbx+8], rdi
0x18000e516  mov     rbx, [rsp+28h+arg_0]
0x18000e51b  add     rsp, 20h
0x18000e51f  pop     rdi
0x18000e520  retn
0x18000e521  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
```
