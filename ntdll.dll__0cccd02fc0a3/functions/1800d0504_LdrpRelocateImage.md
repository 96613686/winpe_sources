# LdrpRelocateImage

- ea: `0x1800d0504`
- end: `0x1800d0669`
- name: `LdrpRelocateImage`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800fc74c`

## callees

- `0x18001eb80`
- `0x180066020`
- `0x1800d0504`
- `0x1800d0670`
- `0x1800d0834`

## string_xrefs

- `0x1800d0512`: `DLL name: %wZ\n`

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
0x1800d0504  push    rbx
0x1800d0506  push    rbp
0x1800d0507  push    rsi
0x1800d0508  push    rdi
0x1800d0509  sub     rsp, 38h
0x1800d050d  mov     qword ptr [rsp+58h+ArgList], r9; ArgList
0x1800d0512  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x1800d0519  mov     rdi, r9
0x1800d051c  mov     [rsp+58h+Format], rax; Format
0x1800d0521  mov     rsi, r8
0x1800d0524  mov     [rsp+58h+arg_10], 0
0x1800d052c  mov     rbp, rdx
0x1800d052f  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d0536  mov     rbx, rcx
0x1800d0539  mov     r9d, 3; int
0x1800d053f  mov     edx, 166h; int
0x1800d0544  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d054b  call    LdrpLogInternal
0x1800d0550  lea     rax, aWz_0; "%wZ\n"
0x1800d0557  mov     qword ptr [rsp+58h+ArgList], rdi; ArgList
0x1800d055c  mov     r9d, 5; int
0x1800d0562  mov     [rsp+58h+Format], rax; Format
0x1800d0567  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d056e  mov     edx, 167h; int
0x1800d0573  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d057a  call    LdrpLogInternal
0x1800d057f  test    byte ptr [rsi+16h], 1
0x1800d0583  jnz     loc_1800D0614
0x1800d0589  mov     r8d, 5
0x1800d058f  lea     r9, [rsp+58h+arg_10]
0x1800d0594  mov     dl, 1
0x1800d0596  mov     rcx, rbx
0x1800d0599  call    RtlImageDirectoryEntryToData
0x1800d059e  test    rax, rax
0x1800d05a1  jnz     short loc_1800D060D
0x1800d05a3  xor     ebx, ebx
0x1800d05a5  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x1800d05ac  mov     dword ptr [rsp+58h+ArgList], ebx; ArgList
0x1800d05b0  mov     r9d, 4; int
0x1800d05b6  mov     [rsp+58h+Format], rax; Format
0x1800d05bb  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d05c2  mov     edx, 18Dh; int
0x1800d05c7  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d05ce  call    LdrpLogInternal
0x1800d05d3  lea     rax, asc_180175AB4; "%x\n"
0x1800d05da  mov     dword ptr [rsp+58h+ArgList], ebx; ArgList
0x1800d05de  mov     r9d, 6; int
0x1800d05e4  mov     [rsp+58h+Format], rax; Format
0x1800d05e9  lea     r8, aLdrprelocateim; "LdrpRelocateImage"
0x1800d05f0  mov     edx, 18Eh; int
0x1800d05f5  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x1800d05fc  call    LdrpLogInternal
0x1800d0601  mov     eax, ebx
0x1800d0603  add     rsp, 38h
0x1800d0607  pop     rdi
0x1800d0608  pop     rsi
0x1800d0609  pop     rbp
0x1800d060a  pop     rbx
0x1800d060b  retn
0x1800d060d  cmp     [rsp+58h+arg_10], 0
0x1800d0612  jz      short loc_1800D05A3
0x1800d0614  mov     r8d, 0Eh
0x1800d061a  mov     [rsp+58h+arg_10], 0
0x1800d0622  lea     r9, [rsp+58h+arg_10]
0x1800d0627  mov     dl, 1
0x1800d0629  mov     rcx, rbx
0x1800d062c  call    RtlImageDirectoryEntryToData
0x1800d0631  test    rax, rax
0x1800d0634  jnz     short loc_1800D0657
0x1800d0636  mov     rdx, [rsi+30h]
0x1800d063a  mov     r9, rbp
0x1800d063d  mov     r8, rbx
0x1800d0640  mov     rcx, rdi
0x1800d0643  call    LdrpLogDllRelocationEtwEvent
0x1800d0648  mov     rcx, rbx; ArgList
0x1800d064b  call    LdrpProtectAndRelocateImage
0x1800d0650  mov     ebx, eax
0x1800d0652  jmp     loc_1800D05A5
0x1800d0657  cmp     [rsp+58h+arg_10], 48h ; 'H'
0x1800d065c  jb      short loc_1800D0636
0x1800d065e  test    byte ptr [rax+10h], 1
0x1800d0662  jz      short loc_1800D0636
0x1800d0664  jmp     loc_1800D05A3
```
