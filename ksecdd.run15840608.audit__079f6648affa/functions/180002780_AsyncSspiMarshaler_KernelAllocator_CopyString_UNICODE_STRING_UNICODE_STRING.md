# AsyncSspiMarshaler<KernelAllocator>::CopyString(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180002780`
- end: `0x1800027e5`
- name: `?CopyString@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAU_UNICODE_STRING@@0@Z`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027470`

## callees

- `0x180002780`
- `0x18000f47c`

## pseudocode

```c
__int64 __fastcall AsyncSspiMarshaler<KernelAllocator>::CopyString(__int64 a1, __int64 a2, const void **a3)
{
  __int64 result; // rax

  *(_OWORD *)a2 = 0;
  if ( !*(_QWORD *)(a1 + 8) )
    return 3221225632LL;
  if ( !a3 )
    return 0;
  result = AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<unsigned char>(
             a1,
             (_QWORD *)(a2 + 8),
             a3[1],
             *(unsigned __int16 *)a3);
  if ( (int)result >= 0 )
  {
    *(_WORD *)a2 = *(_WORD *)a3;
    *(_WORD *)(a2 + 2) = *(_WORD *)a3;
  }
  return result;
}

```

## disassembly

```asm
0x180002780  mov     [rsp+arg_0], rbx
0x180002785  push    rdi
0x180002786  sub     rsp, 20h
0x18000278a  xorps   xmm0, xmm0
0x18000278d  mov     rbx, r8
0x180002790  movups  xmmword ptr [rdx], xmm0
0x180002793  cmp     qword ptr [rcx+8], 0
0x180002798  mov     rdi, rdx
0x18000279b  jz      short loc_1800027B0
0x18000279d  test    rbx, rbx
0x1800027a0  jnz     short loc_1800027C1
0x1800027a2  xor     eax, eax
0x1800027a4  mov     rbx, [rsp+28h+arg_0]
0x1800027a9  add     rsp, 20h
0x1800027ad  pop     rdi
0x1800027ae  retn
0x1800027b0  mov     rbx, [rsp+28h+arg_0]
0x1800027b5  mov     eax, 0C00000A0h
0x1800027ba  add     rsp, 20h
0x1800027be  pop     rdi
0x1800027bf  retn
0x1800027c1  movzx   r9d, word ptr [r8]
0x1800027c5  add     rdx, 8
0x1800027c9  mov     r8, [r8+8]
0x1800027cd  call    ??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z; AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)
0x1800027d2  test    eax, eax
0x1800027d4  js      short loc_1800027A4
0x1800027d6  movzx   ecx, word ptr [rbx]
0x1800027d9  mov     [rdi], cx
0x1800027dc  movzx   ecx, word ptr [rbx]
0x1800027df  mov     [rdi+2], cx
0x1800027e3  jmp     short loc_1800027A4
```
