# SymCommonTlbImpManagedDll

- ea: `0x18002441c`
- end: `0x180024627`
- name: `SymCommonTlbImpManagedDll`
- size: `523`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800239a8`

## callees

- `0x18002441c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x1800244fd`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x1800244fd`
- `ntdll!RtlImageRvaToVa` at `0x1800244e1`
- `ntdll!RtlImageRvaToVa` at `0x180024541`
- `ntdll!RtlImageRvaToVa` at `0x180024594`
- `ntdll!RtlImageRvaToVa` at `0x1800245ce`
- `ntdll!RtlImageRvaToVa` at `0x1800244e1`
- `ntdll!RtlImageRvaToVa` at `0x180024541`
- `ntdll!RtlImageRvaToVa` at `0x180024594`
- `ntdll!RtlImageRvaToVa` at `0x1800245ce`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180024450`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180024483`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180024450`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180024483`

## string_xrefs

- `0x1800244f3`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall SymCommonTlbImpManagedDll(char *BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)
{
  unsigned int v6; // ebx
  ULONG *v7; // r14
  char *v8; // rsi
  __int64 v9; // r8
  char *v10; // rax
  char *v11; // rax
  __int64 v12; // r8
  __int64 *v13; // rax
  __int64 v14; // rcx
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF

  v6 = 1;
  Size = 0;
  v7 = 0;
  v8 = 0;
  if ( RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, 0, &Size) || Size )
    goto LABEL_15;
  v7 = (ULONG *)RtlImageDirectoryEntryToData(BaseAddress, MappedAsImage, 1u, &Size);
  if ( !v7 )
    return 0;
  if ( !Size )
    return 0;
  v9 = v7[3];
  if ( !(_DWORD)v9 || !*v7 || v7[2] || Size >= 0x28 && v7[8] )
    return 0;
  v10 = MappedAsImage ? &BaseAddress[v9] : (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v9, 0);
  if ( (unsigned int)_o__memicmp(v10, "mscoree.dll", 12) )
LABEL_15:
    v6 = 0;
  if ( !v6 )
    return v6;
  if ( NtHeader->OptionalHeader.Magic == 267 )
  {
    if ( MappedAsImage )
      v11 = &BaseAddress[*v7];
    else
      v11 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
    v12 = *(unsigned int *)v11;
    if ( (int)v12 < 0 || *((_DWORD *)v11 + 1) )
      return 0;
    if ( MappedAsImage )
    {
      v8 = &BaseAddress[v12];
      goto LABEL_36;
    }
LABEL_34:
    v8 = (char *)RtlImageRvaToVa(NtHeader, BaseAddress, v12, 0);
    goto LABEL_36;
  }
  if ( NtHeader->OptionalHeader.Magic == 523 )
  {
    if ( MappedAsImage )
      v13 = (__int64 *)&BaseAddress[*v7];
    else
      v13 = (__int64 *)RtlImageRvaToVa(NtHeader, BaseAddress, *v7, 0);
    if ( *v13 < 0 || v13[1] )
      return 0;
    if ( MappedAsImage )
    {
      v8 = &BaseAddress[*v13];
      goto LABEL_36;
    }
    LODWORD(v12) = *(_DWORD *)v13;
    goto LABEL_34;
  }
  v6 = 0;
LABEL_36:
  if ( v6 )
  {
    v14 = *(_QWORD *)(v8 + 2) - 0x4D6C6C44726F435FLL;
    if ( *(_QWORD *)(v8 + 2) == 0x4D6C6C44726F435FLL )
      v14 = *(unsigned int *)(v8 + 10) - 7235937LL;
    if ( v14 )
      return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18002441c  mov     rax, rsp
0x18002441f  push    rbx
0x180024420  push    rsi
0x180024421  push    rdi
0x180024422  push    r12
0x180024424  push    r14
0x180024426  push    r15
0x180024428  sub     rsp, 38h
0x18002442c  mov     r15b, r8b
0x18002442f  mov     r12, rdx
0x180024432  mov     rdi, rcx
0x180024435  mov     ebx, 1
0x18002443a  mov     dword ptr [rax+20h], 0
0x180024441  xor     r14d, r14d
0x180024444  xor     esi, esi
0x180024446  xor     r8d, r8d; Directory
0x180024449  lea     r9, [rax+20h]; Size
0x18002444d  mov     dl, r15b; MappedAsImage
0x180024450  call    cs:__imp_RtlImageDirectoryEntryToData
0x180024457  nop     dword ptr [rax+rax+00h]
0x18002445c  test    rax, rax
0x18002445f  jnz     loc_18002450D
0x180024465  cmp     [rsp+68h+Size], eax
0x18002446c  jnz     loc_18002450D
0x180024472  mov     r8d, ebx; Directory
0x180024475  lea     r9, [rsp+68h+Size]; Size
0x18002447d  mov     dl, r15b; MappedAsImage
0x180024480  mov     rcx, rdi; BaseAddress
0x180024483  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002448a  nop     dword ptr [rax+rax+00h]
0x18002448f  mov     r14, rax
0x180024492  test    rax, rax
0x180024495  jz      short loc_1800244C6
0x180024497  mov     eax, [rsp+68h+Size]
0x18002449e  test    eax, eax
0x1800244a0  jz      short loc_1800244C6
0x1800244a2  mov     [rsp+68h+var_40], r14
0x1800244a7  mov     r8d, [r14+0Ch]; Rva
0x1800244ab  test    r8d, r8d
0x1800244ae  jz      short loc_1800244C6
0x1800244b0  cmp     [r14], esi
0x1800244b3  jz      short loc_1800244C6
0x1800244b5  cmp     [r14+8], esi
0x1800244b9  jnz     short loc_1800244C6
0x1800244bb  cmp     eax, 28h ; '('
0x1800244be  jb      short loc_1800244CD
0x1800244c0  cmp     [r14+20h], esi
0x1800244c4  jz      short loc_1800244CD
0x1800244c6  xor     ebx, ebx
0x1800244c8  jmp     loc_18002460A
0x1800244cd  test    r15b, r15b
0x1800244d0  jz      short loc_1800244D8
0x1800244d2  lea     rax, [rdi+r8]
0x1800244d6  jmp     short loc_1800244ED
0x1800244d8  xor     r9d, r9d; SectionHeader
0x1800244db  mov     rdx, rdi; BaseAddress
0x1800244de  mov     rcx, r12; NtHeader
0x1800244e1  call    cs:__imp_RtlImageRvaToVa
0x1800244e8  nop     dword ptr [rax+rax+00h]
0x1800244ed  mov     r8d, 0Ch
0x1800244f3  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x1800244fa  mov     rcx, rax
0x1800244fd  call    cs:__imp__o__memicmp
0x180024504  nop     dword ptr [rax+rax+00h]
0x180024509  test    eax, eax
0x18002450b  jz      short loc_180024513
0x18002450d  xor     ebx, ebx
0x18002450f  mov     [rsp+68h+var_48], ebx
0x180024513  test    ebx, ebx
0x180024515  jz      loc_18002460E
0x18002451b  mov     eax, 10Bh
0x180024520  cmp     [r12+18h], ax
0x180024526  jnz     short loc_18002456E
0x180024528  test    r15b, r15b
0x18002452b  jz      short loc_180024535
0x18002452d  mov     eax, [r14]
0x180024530  add     rax, rdi
0x180024533  jmp     short loc_18002454D
0x180024535  xor     r9d, r9d; SectionHeader
0x180024538  mov     r8d, [r14]; Rva
0x18002453b  mov     rdx, rdi; BaseAddress
0x18002453e  mov     rcx, r12; NtHeader
0x180024541  call    cs:__imp_RtlImageRvaToVa
0x180024548  nop     dword ptr [rax+rax+00h]
0x18002454d  mov     r8d, [rax]
0x180024550  test    r8d, r8d
0x180024553  js      loc_1800244C6
0x180024559  cmp     dword ptr [rax+4], 0
0x18002455d  jnz     loc_1800244C6
0x180024563  test    r15b, r15b
0x180024566  jz      short loc_1800245C5
0x180024568  lea     rsi, [rdi+r8]
0x18002456c  jmp     short loc_1800245E5
0x18002456e  mov     eax, 20Bh
0x180024573  cmp     [r12+18h], ax
0x180024579  jnz     short loc_1800245DF
0x18002457b  test    r15b, r15b
0x18002457e  jz      short loc_180024588
0x180024580  mov     eax, [r14]
0x180024583  add     rax, rdi
0x180024586  jmp     short loc_1800245A0
0x180024588  xor     r9d, r9d; SectionHeader
0x18002458b  mov     r8d, [r14]; Rva
0x18002458e  mov     rdx, rdi; BaseAddress
0x180024591  mov     rcx, r12; NtHeader
0x180024594  call    cs:__imp_RtlImageRvaToVa
0x18002459b  nop     dword ptr [rax+rax+00h]
0x1800245a0  mov     rcx, [rax]
0x1800245a3  test    rcx, rcx
0x1800245a6  js      loc_1800244C6
0x1800245ac  cmp     qword ptr [rax+8], 0
0x1800245b1  jnz     loc_1800244C6
0x1800245b7  test    r15b, r15b
0x1800245ba  jz      short loc_1800245C2
0x1800245bc  lea     rsi, [rcx+rdi]
0x1800245c0  jmp     short loc_1800245E5
0x1800245c2  mov     r8d, [rax]; Rva
0x1800245c5  xor     r9d, r9d; SectionHeader
0x1800245c8  mov     rdx, rdi; BaseAddress
0x1800245cb  mov     rcx, r12; NtHeader
0x1800245ce  call    cs:__imp_RtlImageRvaToVa
0x1800245d5  nop     dword ptr [rax+rax+00h]
0x1800245da  mov     rsi, rax
0x1800245dd  jmp     short loc_1800245E5
0x1800245df  xor     ebx, ebx
0x1800245e1  mov     [rsp+68h+var_48], ebx
0x1800245e5  test    ebx, ebx
0x1800245e7  jz      short loc_18002460E
0x1800245e9  mov     rcx, [rsi+2]
0x1800245ed  sub     rcx, cs:qword_18002C780
0x1800245f4  jnz     short loc_180024602
0x1800245f6  mov     ecx, [rsi+0Ah]
0x1800245f9  mov     eax, cs:dword_18002C788
0x1800245ff  sub     rcx, rax
0x180024602  xor     eax, eax
0x180024604  test    rcx, rcx
0x180024607  cmovnz  ebx, eax
0x18002460a  mov     [rsp+68h+var_48], ebx
0x18002460e  jmp     short loc_180024616
0x180024610  xor     ebx, ebx
0x180024612  mov     [rsp+68h+var_48], ebx
0x180024616  mov     eax, ebx
0x180024618  add     rsp, 38h
0x18002461c  pop     r15
0x18002461e  pop     r14
0x180024620  pop     r12
0x180024622  pop     rdi
0x180024623  pop     rsi
0x180024624  pop     rbx
0x180024625  retn
```
