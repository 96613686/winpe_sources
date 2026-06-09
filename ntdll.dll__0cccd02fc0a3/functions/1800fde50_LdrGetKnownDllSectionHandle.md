# LdrGetKnownDllSectionHandle

- ea: `0x1800fde50`
- end: `0x1800fdfb0`
- name: `LdrGetKnownDllSectionHandle`
- size: `352`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001eb80`
- `0x18002b2a0`
- `0x1800fde50`
- `0x18015e9b0`

## string_xrefs

- `0x1800fde86`: `LdrGetKnownDllSectionHandle`
- `0x1800fdec1`: `LdrGetKnownDllSectionHandle`
- `0x1800fdf4e`: `LdrGetKnownDllSectionHandle`
- `0x1800fdf7c`: `LdrGetKnownDllSectionHandle`
- `0x1800fde6b`: `DLL name: %ws\n`

## pseudocode

```c
__int64 __fastcall LdrGetKnownDllSectionHandle(__int64 ArgList, char a2, __int64 a3)
{
  __int64 v6; // rdi
  int inited; // ebx
  __int128 v9; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v10[48]; // [rsp+40h] [rbp-30h] BYREF

  v9 = 0;
  memset(v10, 0, 44);
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrapi.c",
    5585,
    (int)"LdrGetKnownDllSectionHandle",
    3,
    "DLL name: %ws\n",
    ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 5586, (int)"LdrGetKnownDllSectionHandle", 5, "%ws\n", ArgList);
  if ( a2 )
    return 3221225485LL;
  v6 = LdrpKnownDllDirectoryHandle;
  if ( LdrpKnownDllDirectoryHandle )
  {
    inited = RtlInitUnicodeStringEx(&v9, ArgList);
    if ( inited >= 0 )
    {
      *(_DWORD *)v10 = 48;
      *(_QWORD *)&v10[16] = &v9;
      *(_QWORD *)&v10[8] = v6;
      *(_DWORD *)&v10[24] = 64;
      *(_OWORD *)&v10[32] = 0;
      inited = NtOpenSection(a3, 13, v10);
    }
  }
  else
  {
    inited = -1073741816;
  }
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrapi.c",
    5615,
    (int)"LdrGetKnownDllSectionHandle",
    4,
    "Status: 0x%08lx\n",
    inited);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 5616, (int)"LdrGetKnownDllSectionHandle", 6, "%x\n", inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800fde50  push    rbp
0x1800fde52  push    rbx
0x1800fde53  push    rsi
0x1800fde54  push    rdi
0x1800fde55  push    r14
0x1800fde57  mov     rbp, rsp
0x1800fde5a  sub     rsp, 70h
0x1800fde5e  xorps   xmm0, xmm0
0x1800fde61  mov     qword ptr [rsp+70h+ArgList], rcx; ArgList
0x1800fde66  xor     eax, eax
0x1800fde68  mov     r14, r8
0x1800fde6b  lea     rax, aDllNameWs; "DLL name: %ws\n"
0x1800fde72  mov     bl, dl
0x1800fde74  mov     rsi, rcx
0x1800fde77  mov     [rsp+70h+Format], rax; Format
0x1800fde7c  movups  [rbp+var_20], xmm0
0x1800fde80  mov     r9d, 3; int
0x1800fde86  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fde8d  mov     edx, 15D1h; int
0x1800fde92  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fde99  movups  [rbp+var_40], xmm0
0x1800fde9d  movups  [rbp+var_30], xmm0
0x1800fdea1  movups  [rbp+var_20+0Ch], xmm0
0x1800fdea5  call    LdrpLogInternal
0x1800fdeaa  lea     rax, aWs; "%ws\n"
0x1800fdeb1  mov     qword ptr [rsp+70h+ArgList], rsi; ArgList
0x1800fdeb6  mov     r9d, 5; int
0x1800fdebc  mov     [rsp+70h+Format], rax; Format
0x1800fdec1  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fdec8  mov     edx, 15D2h; int
0x1800fdecd  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fded4  call    LdrpLogInternal
0x1800fded9  test    bl, bl
0x1800fdedb  jnz     loc_1800FDFA9
0x1800fdee1  mov     rdi, cs:LdrpKnownDllDirectoryHandle
0x1800fdee8  test    rdi, rdi
0x1800fdeeb  jz      loc_1800FDFA2
0x1800fdef1  mov     rdx, rsi
0x1800fdef4  lea     rcx, [rbp+var_40]
0x1800fdef8  call    RtlInitUnicodeStringEx
0x1800fdefd  mov     ebx, eax
0x1800fdeff  test    eax, eax
0x1800fdf01  js      short loc_1800FDF38
0x1800fdf03  lea     rax, [rbp+var_40]
0x1800fdf07  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1800fdf0e  xorps   xmm0, xmm0
0x1800fdf11  mov     qword ptr [rbp+var_20], rax
0x1800fdf15  lea     r8, [rbp+var_30]
0x1800fdf19  mov     qword ptr [rbp+var_30+8], rdi
0x1800fdf1d  mov     edx, 0Dh
0x1800fdf22  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x1800fdf29  mov     rcx, r14
0x1800fdf2c  movdqu  [rbp+var_10], xmm0
0x1800fdf31  call    NtOpenSection
0x1800fdf36  mov     ebx, eax
0x1800fdf38  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x1800fdf3f  mov     dword ptr [rsp+70h+ArgList], ebx; ArgList
0x1800fdf43  mov     r9d, 4; int
0x1800fdf49  mov     [rsp+70h+Format], rax; Format
0x1800fdf4e  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fdf55  mov     edx, 15EFh; int
0x1800fdf5a  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fdf61  call    LdrpLogInternal
0x1800fdf66  lea     rax, asc_180175AB4; "%x\n"
0x1800fdf6d  mov     dword ptr [rsp+70h+ArgList], ebx; ArgList
0x1800fdf71  mov     r9d, 6; int
0x1800fdf77  mov     [rsp+70h+Format], rax; Format
0x1800fdf7c  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fdf83  mov     edx, 15F0h; int
0x1800fdf88  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fdf8f  call    LdrpLogInternal
0x1800fdf94  mov     eax, ebx
0x1800fdf96  add     rsp, 70h
0x1800fdf9a  pop     r14
0x1800fdf9c  pop     rdi
0x1800fdf9d  pop     rsi
0x1800fdf9e  pop     rbx
0x1800fdf9f  pop     rbp
0x1800fdfa0  retn
0x1800fdfa2  mov     ebx, 0C0000008h
0x1800fdfa7  jmp     short loc_1800FDF38
0x1800fdfa9  mov     eax, 0C000000Dh
0x1800fdfae  jmp     short loc_1800FDF96
```
