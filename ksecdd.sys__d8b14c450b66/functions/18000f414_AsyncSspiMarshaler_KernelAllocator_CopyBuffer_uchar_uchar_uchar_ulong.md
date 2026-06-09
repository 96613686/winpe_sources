# AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)

- ea: `0x18000f414`
- end: `0x18000f47b`
- name: `??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002780`
- `0x180025730`
- `0x180027420`

## callees

- `0x18000f414`
- `0x180010980`

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
0x18000f414  push    rbx
0x18000f416  push    rsi
0x18000f417  push    rdi
0x18000f418  push    r14
0x18000f41a  sub     rsp, 28h
0x18000f41e  mov     qword ptr [rdx], 0
0x18000f425  mov     rax, r8
0x18000f428  cmp     qword ptr [rcx+8], 0
0x18000f42d  mov     r14, rdx
0x18000f430  mov     esi, r9d
0x18000f433  mov     rdi, rcx
0x18000f436  jnz     short loc_18000F43F
0x18000f438  mov     eax, 0C00000A0h
0x18000f43d  jmp     short loc_18000F470
0x18000f43f  test    rax, rax
0x18000f442  jz      short loc_18000F46E
0x18000f444  cmp     [rcx+10h], esi
0x18000f447  jnb     short loc_18000F450
0x18000f449  mov     eax, 0C0000023h
0x18000f44e  jmp     short loc_18000F470
0x18000f450  mov     rcx, [rcx]; void *
0x18000f453  mov     r8, rsi; Size
0x18000f456  mov     rdx, rax; Src
0x18000f459  call    memmove
0x18000f45e  mov     rcx, [rdi]
0x18000f461  sub     rcx, [rdi+8]
0x18000f465  mov     [r14], rcx
0x18000f468  add     [rdi], rsi
0x18000f46b  sub     [rdi+10h], esi
0x18000f46e  xor     eax, eax
0x18000f470  add     rsp, 28h
0x18000f474  pop     r14
0x18000f476  pop     rdi
0x18000f477  pop     rsi
0x18000f478  pop     rbx
0x18000f479  retn
```
