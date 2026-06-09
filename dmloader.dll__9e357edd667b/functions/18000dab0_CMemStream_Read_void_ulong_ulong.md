# CMemStream::Read(void *,ulong,ulong *)

- ea: `0x18000dab0`
- end: `0x18000db02`
- name: `?Read@CMemStream@@UEAAJPEAXKPEAK@Z`
- size: `82`
- prototype: `__int64 __fastcall(CMemStream *this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dab0`
- `0x18000f99c`

## pseudocode

```c
__int64 __fastcall CMemStream::Read(CMemStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v5; // rsi
  __int64 v6; // rcx

  v5 = a3;
  v6 = *((_QWORD *)this + 5);
  if ( v6 + a3 > *((_QWORD *)this + 4) )
    return 2147500037LL;
  memcpy_0(a2, (const void *)(v6 + *((_QWORD *)this + 3)), a3);
  *((_QWORD *)this + 5) += v5;
  if ( a4 )
    *a4 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000dab0  push    rbx
0x18000dab2  push    rbp
0x18000dab3  push    rsi
0x18000dab4  push    rdi
0x18000dab5  sub     rsp, 28h
0x18000dab9  mov     rbx, rcx
0x18000dabc  mov     esi, r8d
0x18000dabf  mov     rcx, [rcx+28h]
0x18000dac3  mov     rdi, r9
0x18000dac6  mov     r9, rdx
0x18000dac9  lea     rax, [rcx+rsi]
0x18000dacd  cmp     rax, [rbx+20h]
0x18000dad1  jg      short loc_18000DAF4
0x18000dad3  mov     rdx, [rbx+18h]
0x18000dad7  mov     r8d, esi; Size
0x18000dada  add     rdx, rcx; Src
0x18000dadd  mov     rcx, r9; void *
0x18000dae0  call    memcpy_0
0x18000dae5  add     [rbx+28h], rsi
0x18000dae9  test    rdi, rdi
0x18000daec  jz      short loc_18000DAF0
0x18000daee  mov     [rdi], esi
0x18000daf0  xor     eax, eax
0x18000daf2  jmp     short loc_18000DAF9
0x18000daf4  mov     eax, 80004005h
0x18000daf9  add     rsp, 28h
0x18000dafd  pop     rdi
0x18000dafe  pop     rsi
0x18000daff  pop     rbp
0x18000db00  pop     rbx
0x18000db01  retn
```
