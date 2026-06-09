# TempBuffer<0>::ReserveBytesNoThrow(unsigned __int64,unsigned __int64)

- ea: `0x18000e530`
- end: `0x18000e580`
- name: `?ReserveBytesNoThrow@?$TempBuffer@$0A@@@IEAA_N_K0@Z`
- size: `80`
- prototype: `char __fastcall(__int64, const struct std::nothrow_t *, size_t)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e4c4`
- `0x1800122b8`
- `0x180013750`

## callees

- `0x18000ab3c`
- `0x18000ab70`
- `0x18000e530`
- `0x180014e8c`

## pseudocode

```c
char __fastcall TempBuffer<0>::ReserveBytesNoThrow(__int64 a1, const struct std::nothrow_t *a2, size_t a3)
{
  void *v6; // rax
  void *v7; // rsi

  if ( (unsigned __int64)a2 <= *(_QWORD *)(a1 + 8) )
    goto LABEL_4;
  v6 = operator new((SIZE_T)a2, a2);
  v7 = v6;
  if ( v6 )
  {
    memcpy_0(v6, *(const void **)a1, a3);
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = v7;
    *(_QWORD *)(a1 + 8) = a2;
LABEL_4:
    LOBYTE(v6) = 1;
  }
  return (char)v6;
}

```

## disassembly

```asm
0x18000e530  push    rbx
0x18000e532  push    rbp
0x18000e533  push    rsi
0x18000e534  push    rdi
0x18000e535  sub     rsp, 28h
0x18000e539  mov     rbp, r8
0x18000e53c  mov     rdi, rdx
0x18000e53f  mov     rbx, rcx
0x18000e542  cmp     rdx, [rcx+8]
0x18000e546  jbe     short loc_18000E575
0x18000e548  mov     rcx, rdx; dwBytes
0x18000e54b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e550  mov     rsi, rax
0x18000e553  test    rax, rax
0x18000e556  jz      short loc_18000E577
0x18000e558  mov     rdx, [rbx]; Src
0x18000e55b  mov     r8, rbp; Size
0x18000e55e  mov     rcx, rsi; void *
0x18000e561  call    memcpy_0
0x18000e566  mov     rcx, [rbx]; lpMem
0x18000e569  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e56e  mov     [rbx], rsi
0x18000e571  mov     [rbx+8], rdi
0x18000e575  mov     al, 1
0x18000e577  add     rsp, 28h
0x18000e57b  pop     rdi
0x18000e57c  pop     rsi
0x18000e57d  pop     rbp
0x18000e57e  pop     rbx
0x18000e57f  retn
```
