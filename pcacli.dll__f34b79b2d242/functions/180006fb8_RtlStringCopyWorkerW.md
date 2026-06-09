# RtlStringCopyWorkerW

- ea: `0x180006fb8`
- end: `0x180007009`
- name: `RtlStringCopyWorkerW`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007668`
- `0x180008ab0`
- `0x180008e54`

## callees

- `0x180006fb8`

## pseudocode

```c
__int64 __fastcall RtlStringCopyWorkerW(_WORD *a1, __int64 a2, __int64 a3, _WORD *a4)
{
  __int64 v4; // r8
  __int64 i; // rax
  _WORD *v6; // rdx
  __int64 result; // rax

  v4 = a2;
  for ( i = 2147483646; v4; --v4 )
  {
    if ( !i )
      break;
    if ( !*a4 )
      break;
    *a1++ = *a4++;
    --i;
  }
  v6 = a1 - 1;
  result = v4 == 0 ? 0x80000005 : 0;
  if ( v4 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x180006fb8  xor     r10d, r10d
0x180006fbb  mov     r8, rdx
0x180006fbe  mov     eax, 7FFFFFFEh
0x180006fc3  test    rdx, rdx
0x180006fc6  jz      short loc_180006FEA
0x180006fc8  test    rax, rax
0x180006fcb  jz      short loc_180006FEA
0x180006fcd  movzx   edx, word ptr [r9]
0x180006fd1  test    dx, dx
0x180006fd4  jz      short loc_180006FEA
0x180006fd6  mov     [rcx], dx
0x180006fd9  add     r9, 2
0x180006fdd  add     rcx, 2
0x180006fe1  dec     rax
0x180006fe4  sub     r8, 1
0x180006fe8  jnz     short loc_180006FC8
0x180006fea  mov     rax, r8
0x180006fed  lea     rdx, [rcx-2]
0x180006ff1  neg     rax
0x180006ff4  sbb     eax, eax
0x180006ff6  not     eax
0x180006ff8  and     eax, 80000005h
0x180006ffd  test    r8, r8
0x180007000  cmovnz  rdx, rcx
0x180007004  mov     [rdx], r10w
0x180007008  retn
```
