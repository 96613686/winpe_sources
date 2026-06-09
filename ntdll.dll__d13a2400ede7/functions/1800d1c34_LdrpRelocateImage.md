# LdrpRelocateImage

- ea: `0x1800d1c34`
- end: `0x1800d1d99`
- name: `LdrpRelocateImage`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800fcd6c`

## callees

- `0x18001eb80`
- `0x180082a00`
- `0x1800d1c34`
- `0x1800d1da0`
- `0x1800d1f64`

## string_xrefs

- `0x1800d1c42`: `DLL name: %wZ\n`

## pseudocode

```c
__int64 __fastcall LdrpRelocateImage(__int64 ArgList, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  __int64 v10; // rax
  unsigned int v11; // [rsp+70h] [rbp+18h] BYREF

  v11 = 0;
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 358, (int)"LdrpRelocateImage", 3, "DLL name: %wZ\n", a4);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 359, (int)"LdrpRelocateImage", 5, "%wZ\n", a4);
  if ( ((*(_BYTE *)(a3 + 22) & 1) != 0 || RtlImageDirectoryEntryToData(ArgList, 1, 5u, &v11) && v11)
    && ((v11 = 0, (v10 = RtlImageDirectoryEntryToData(ArgList, 1, 0xEu, &v11)) == 0)
     || v11 < 0x48
     || (*(_BYTE *)(v10 + 16) & 1) == 0) )
  {
    LdrpLogDllRelocationEtwEvent(a4, *(_QWORD *)(a3 + 48), ArgList, a2);
    v8 = LdrpProtectAndRelocateImage(ArgList);
  }
  else
  {
    v8 = 0;
  }
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 397, (int)"LdrpRelocateImage", 4, "Status: 0x%08lx\n", v8);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrmap.c", 398, (int)"LdrpRelocateImage", 6, "%x\n", v8);
  return v8;
}

```

## disassembly

```asm
0x1800d1c34  push    rbx
0x1800d1c36  push    rbp
0x1800d1c37  push    rsi
0x1800d1c38  push    rdi
0x1800d1c39  sub     rsp, 38h
0x1800d1c3d  mov     qword ptr [rsp+58h+ArgList], r9; ArgList
0x1800d1c42  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800d1c49  mov     rdi, r9
0x1800d1c4c  mov     [rsp+58h+Format], rax; Format
0x1800d1c51  mov     rsi, r8
0x1800d1c54  mov     [rsp+58h+arg_10], 0
0x1800d1c5c  mov     rbp, rdx
0x1800d1c5f  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d1c66  mov     rbx, rcx
0x1800d1c69  mov     r9d, 3; int
0x1800d1c6f  mov     edx, 166h; int
0x1800d1c74  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d1c7b  call    LdrpLogInternal
0x1800d1c80  lea     rax, aWz_0; "%wZ\n"
0x1800d1c87  mov     qword ptr [rsp+58h+ArgList], rdi; ArgList
0x1800d1c8c  mov     r9d, 5; int
0x1800d1c92  mov     [rsp+58h+Format], rax; Format
0x1800d1c97  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d1c9e  mov     edx, 167h; int
0x1800d1ca3  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d1caa  call    LdrpLogInternal
0x1800d1caf  test    byte ptr [rsi+16h], 1
0x1800d1cb3  jnz     loc_1800D1D44
0x1800d1cb9  mov     r8d, 5
0x1800d1cbf  lea     r9, [rsp+58h+arg_10]
0x1800d1cc4  mov     dl, 1
0x1800d1cc6  mov     rcx, rbx
0x1800d1cc9  call    RtlImageDirectoryEntryToData
0x1800d1cce  test    rax, rax
0x1800d1cd1  jnz     short loc_1800D1D3D
0x1800d1cd3  xor     ebx, ebx
0x1800d1cd5  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x1800d1cdc  mov     dword ptr [rsp+58h+ArgList], ebx; ArgList
0x1800d1ce0  mov     r9d, 4; int
0x1800d1ce6  mov     [rsp+58h+Format], rax; Format
0x1800d1ceb  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d1cf2  mov     edx, 18Dh; int
0x1800d1cf7  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d1cfe  call    LdrpLogInternal
0x1800d1d03  lea     rax, asc_180175AB4; "%x\n"
0x1800d1d0a  mov     dword ptr [rsp+58h+ArgList], ebx; ArgList
0x1800d1d0e  mov     r9d, 6; int
0x1800d1d14  mov     [rsp+58h+Format], rax; Format
0x1800d1d19  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d1d20  mov     edx, 18Eh; int
0x1800d1d25  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d1d2c  call    LdrpLogInternal
0x1800d1d31  mov     eax, ebx
0x1800d1d33  add     rsp, 38h
0x1800d1d37  pop     rdi
0x1800d1d38  pop     rsi
0x1800d1d39  pop     rbp
0x1800d1d3a  pop     rbx
0x1800d1d3b  retn
0x1800d1d3d  cmp     [rsp+58h+arg_10], 0
0x1800d1d42  jz      short loc_1800D1CD3
0x1800d1d44  mov     r8d, 0Eh
0x1800d1d4a  mov     [rsp+58h+arg_10], 0
0x1800d1d52  lea     r9, [rsp+58h+arg_10]
0x1800d1d57  mov     dl, 1
0x1800d1d59  mov     rcx, rbx
0x1800d1d5c  call    RtlImageDirectoryEntryToData
0x1800d1d61  test    rax, rax
0x1800d1d64  jnz     short loc_1800D1D87
0x1800d1d66  mov     rdx, [rsi+30h]
0x1800d1d6a  mov     r9, rbp
0x1800d1d6d  mov     r8, rbx
0x1800d1d70  mov     rcx, rdi
0x1800d1d73  call    LdrpLogDllRelocationEtwEvent
0x1800d1d78  mov     rcx, rbx; ArgList
0x1800d1d7b  call    LdrpProtectAndRelocateImage
0x1800d1d80  mov     ebx, eax
0x1800d1d82  jmp     loc_1800D1CD5
0x1800d1d87  cmp     [rsp+58h+arg_10], 48h ; 'H'
0x1800d1d8c  jb      short loc_1800D1D66
0x1800d1d8e  test    byte ptr [rax+10h], 1
0x1800d1d92  jz      short loc_1800D1D66
0x1800d1d94  jmp     loc_1800D1CD3
```
