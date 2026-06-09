# AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)

- ea: `0x18000f47c`
- end: `0x18000f4e3`
- name: `??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002780`
- `0x180025780`
- `0x180027470`

## callees

- `0x18000f47c`
- `0x180010a00`

## pseudocode

```c
__int64 __fastcall AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<unsigned char>(
        __int64 a1,
        _QWORD *a2,
        const void *a3,
        unsigned int a4)
{
  __int64 v5; // rsi

  *a2 = 0;
  v5 = a4;
  if ( !*(_QWORD *)(a1 + 8) )
    return 3221225632LL;
  if ( a3 )
  {
    if ( *(_DWORD *)(a1 + 16) < a4 )
      return 3221225507LL;
    memmove(*(void **)a1, a3, a4);
    *a2 = *(_QWORD *)a1 - *(_QWORD *)(a1 + 8);
    *(_QWORD *)a1 += v5;
    *(_DWORD *)(a1 + 16) -= v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f47c  push    rbx
0x18000f47e  push    rsi
0x18000f47f  push    rdi
0x18000f480  push    r14
0x18000f482  sub     rsp, 28h
0x18000f486  mov     qword ptr [rdx], 0
0x18000f48d  mov     rax, r8
0x18000f490  cmp     qword ptr [rcx+8], 0
0x18000f495  mov     r14, rdx
0x18000f498  mov     esi, r9d
0x18000f49b  mov     rdi, rcx
0x18000f49e  jnz     short loc_18000F4A7
0x18000f4a0  mov     eax, 0C00000A0h
0x18000f4a5  jmp     short loc_18000F4D8
0x18000f4a7  test    rax, rax
0x18000f4aa  jz      short loc_18000F4D6
0x18000f4ac  cmp     [rcx+10h], esi
0x18000f4af  jnb     short loc_18000F4B8
0x18000f4b1  mov     eax, 0C0000023h
0x18000f4b6  jmp     short loc_18000F4D8
0x18000f4b8  mov     rcx, [rcx]; void *
0x18000f4bb  mov     r8, rsi; Size
0x18000f4be  mov     rdx, rax; Src
0x18000f4c1  call    memmove
0x18000f4c6  mov     rcx, [rdi]
0x18000f4c9  sub     rcx, [rdi+8]
0x18000f4cd  mov     [r14], rcx
0x18000f4d0  add     [rdi], rsi
0x18000f4d3  sub     [rdi+10h], esi
0x18000f4d6  xor     eax, eax
0x18000f4d8  add     rsp, 28h
0x18000f4dc  pop     r14
0x18000f4de  pop     rdi
0x18000f4df  pop     rsi
0x18000f4e0  pop     rbx
0x18000f4e1  retn
```
