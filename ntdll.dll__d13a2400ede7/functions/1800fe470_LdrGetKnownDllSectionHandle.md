# LdrGetKnownDllSectionHandle

- ea: `0x1800fe470`
- end: `0x1800fe5d0`
- name: `LdrGetKnownDllSectionHandle`
- size: `352`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001eb80`
- `0x18002a5b0`
- `0x1800fe470`
- `0x18015f1c0`

## string_xrefs

- `0x1800fe4a6`: `LdrGetKnownDllSectionHandle`
- `0x1800fe4e1`: `LdrGetKnownDllSectionHandle`
- `0x1800fe56e`: `LdrGetKnownDllSectionHandle`
- `0x1800fe59c`: `LdrGetKnownDllSectionHandle`
- `0x1800fe48b`: `DLL name: %ws\n`

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
0x1800fe470  push    rbp
0x1800fe472  push    rbx
0x1800fe473  push    rsi
0x1800fe474  push    rdi
0x1800fe475  push    r14
0x1800fe477  mov     rbp, rsp
0x1800fe47a  sub     rsp, 70h
0x1800fe47e  xorps   xmm0, xmm0
0x1800fe481  mov     qword ptr [rsp+70h+ArgList], rcx; ArgList
0x1800fe486  xor     eax, eax
0x1800fe488  mov     r14, r8
0x1800fe48b  lea     rax, aDllNameWs; "DLL name: %ws\n"
0x1800fe492  mov     bl, dl
0x1800fe494  mov     rsi, rcx
0x1800fe497  mov     [rsp+70h+Format], rax; Format
0x1800fe49c  movups  [rbp+var_20], xmm0
0x1800fe4a0  mov     r9d, 3; int
0x1800fe4a6  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fe4ad  mov     edx, 15D1h; int
0x1800fe4b2  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fe4b9  movups  [rbp+var_40], xmm0
0x1800fe4bd  movups  [rbp+var_30], xmm0
0x1800fe4c1  movups  [rbp+var_20+0Ch], xmm0
0x1800fe4c5  call    LdrpLogInternal
0x1800fe4ca  lea     rax, aWs; "%ws\n"
0x1800fe4d1  mov     qword ptr [rsp+70h+ArgList], rsi; ArgList
0x1800fe4d6  mov     r9d, 5; int
0x1800fe4dc  mov     [rsp+70h+Format], rax; Format
0x1800fe4e1  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fe4e8  mov     edx, 15D2h; int
0x1800fe4ed  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fe4f4  call    LdrpLogInternal
0x1800fe4f9  test    bl, bl
0x1800fe4fb  jnz     loc_1800FE5C9
0x1800fe501  mov     rdi, cs:LdrpKnownDllDirectoryHandle
0x1800fe508  test    rdi, rdi
0x1800fe50b  jz      loc_1800FE5C2
0x1800fe511  mov     rdx, rsi
0x1800fe514  lea     rcx, [rbp+var_40]
0x1800fe518  call    RtlInitUnicodeStringEx
0x1800fe51d  mov     ebx, eax
0x1800fe51f  test    eax, eax
0x1800fe521  js      short loc_1800FE558
0x1800fe523  lea     rax, [rbp+var_40]
0x1800fe527  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1800fe52e  xorps   xmm0, xmm0
0x1800fe531  mov     qword ptr [rbp+var_20], rax
0x1800fe535  lea     r8, [rbp+var_30]
0x1800fe539  mov     qword ptr [rbp+var_30+8], rdi
0x1800fe53d  mov     edx, 0Dh
0x1800fe542  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x1800fe549  mov     rcx, r14
0x1800fe54c  movdqu  [rbp+var_10], xmm0
0x1800fe551  call    NtOpenSection
0x1800fe556  mov     ebx, eax
0x1800fe558  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x1800fe55f  mov     dword ptr [rsp+70h+ArgList], ebx; ArgList
0x1800fe563  mov     r9d, 4; int
0x1800fe569  mov     [rsp+70h+Format], rax; Format
0x1800fe56e  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fe575  mov     edx, 15EFh; int
0x1800fe57a  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fe581  call    LdrpLogInternal
0x1800fe586  lea     rax, asc_180175AB4; "%x\n"
0x1800fe58d  mov     dword ptr [rsp+70h+ArgList], ebx; ArgList
0x1800fe591  mov     r9d, 6; int
0x1800fe597  mov     [rsp+70h+Format], rax; Format
0x1800fe59c  lea     r8, aLdrgetknowndll_0; "LdrGetKnownDllSectionHandle"
0x1800fe5a3  mov     edx, 15F0h; int
0x1800fe5a8  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x1800fe5af  call    LdrpLogInternal
0x1800fe5b4  mov     eax, ebx
0x1800fe5b6  add     rsp, 70h
0x1800fe5ba  pop     r14
0x1800fe5bc  pop     rdi
0x1800fe5bd  pop     rsi
0x1800fe5be  pop     rbx
0x1800fe5bf  pop     rbp
0x1800fe5c0  retn
0x1800fe5c2  mov     ebx, 0C0000008h
0x1800fe5c7  jmp     short loc_1800FE558
0x1800fe5c9  mov     eax, 0C000000Dh
0x1800fe5ce  jmp     short loc_1800FE5B6
```
