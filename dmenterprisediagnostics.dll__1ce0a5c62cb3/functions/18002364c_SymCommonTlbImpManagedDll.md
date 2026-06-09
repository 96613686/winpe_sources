# SymCommonTlbImpManagedDll

- ea: `0x18002364c`
- end: `0x180023828`
- name: `SymCommonTlbImpManagedDll`
- size: `476`
- prototype: `__int64 __fastcall(PVOID BaseAddress, PIMAGE_NT_HEADERS NtHeader, BOOLEAN MappedAsImage)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022c08`

## callees

- `0x18002364c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18002371b`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x18002371b`
- `ntdll!RtlImageRvaToVa` at `0x180023705`
- `ntdll!RtlImageRvaToVa` at `0x180023759`
- `ntdll!RtlImageRvaToVa` at `0x1800237a2`
- `ntdll!RtlImageRvaToVa` at `0x1800237d6`
- `ntdll!RtlImageRvaToVa` at `0x180023705`
- `ntdll!RtlImageRvaToVa` at `0x180023759`
- `ntdll!RtlImageRvaToVa` at `0x1800237a2`
- `ntdll!RtlImageRvaToVa` at `0x1800237d6`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023680`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800236ad`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023680`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800236ad`

## string_xrefs

- `0x180023711`: `mscoree.dll`

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
0x18002364c  mov     rax, rsp
0x18002364f  push    rbx
0x180023650  push    rsi
0x180023651  push    rdi
0x180023652  push    r12
0x180023654  push    r14
0x180023656  push    r15
0x180023658  sub     rsp, 38h
0x18002365c  mov     r15b, r8b
0x18002365f  mov     r12, rdx
0x180023662  mov     rdi, rcx
0x180023665  mov     ebx, 1
0x18002366a  mov     dword ptr [rax+20h], 0
0x180023671  xor     r14d, r14d
0x180023674  xor     esi, esi
0x180023676  xor     r8d, r8d; Directory
0x180023679  lea     r9, [rax+20h]; Size
0x18002367d  mov     dl, r15b; MappedAsImage
0x180023680  call    cs:__imp_RtlImageDirectoryEntryToData
0x180023686  test    rax, rax
0x180023689  jnz     loc_180023725
0x18002368f  cmp     [rsp+68h+Size], eax
0x180023696  jnz     loc_180023725
0x18002369c  mov     r8d, ebx; Directory
0x18002369f  lea     r9, [rsp+68h+Size]; Size
0x1800236a7  mov     dl, r15b; MappedAsImage
0x1800236aa  mov     rcx, rdi; BaseAddress
0x1800236ad  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800236b3  mov     r14, rax
0x1800236b6  test    rax, rax
0x1800236b9  jz      short loc_1800236EA
0x1800236bb  mov     eax, [rsp+68h+Size]
0x1800236c2  test    eax, eax
0x1800236c4  jz      short loc_1800236EA
0x1800236c6  mov     [rsp+68h+var_40], r14
0x1800236cb  mov     r8d, [r14+0Ch]; Rva
0x1800236cf  test    r8d, r8d
0x1800236d2  jz      short loc_1800236EA
0x1800236d4  cmp     [r14], esi
0x1800236d7  jz      short loc_1800236EA
0x1800236d9  cmp     [r14+8], esi
0x1800236dd  jnz     short loc_1800236EA
0x1800236df  cmp     eax, 28h ; '('
0x1800236e2  jb      short loc_1800236F1
0x1800236e4  cmp     [r14+20h], esi
0x1800236e8  jz      short loc_1800236F1
0x1800236ea  xor     ebx, ebx
0x1800236ec  jmp     loc_18002380C
0x1800236f1  test    r15b, r15b
0x1800236f4  jz      short loc_1800236FC
0x1800236f6  lea     rax, [rdi+r8]
0x1800236fa  jmp     short loc_18002370B
0x1800236fc  xor     r9d, r9d; SectionHeader
0x1800236ff  mov     rdx, rdi; BaseAddress
0x180023702  mov     rcx, r12; NtHeader
0x180023705  call    cs:__imp_RtlImageRvaToVa
0x18002370b  mov     r8d, 0Ch
0x180023711  lea     rdx, aMscoreeDll_0; "mscoree.dll"
0x180023718  mov     rcx, rax
0x18002371b  call    cs:__imp__o__memicmp
0x180023721  test    eax, eax
0x180023723  jz      short loc_18002372B
0x180023725  xor     ebx, ebx
0x180023727  mov     [rsp+68h+var_48], ebx
0x18002372b  test    ebx, ebx
0x18002372d  jz      loc_180023810
0x180023733  mov     eax, 10Bh
0x180023738  cmp     [r12+18h], ax
0x18002373e  jnz     short loc_18002377C
0x180023740  test    r15b, r15b
0x180023743  jz      short loc_18002374D
0x180023745  mov     eax, [r14]
0x180023748  add     rax, rdi
0x18002374b  jmp     short loc_18002375F
0x18002374d  xor     r9d, r9d; SectionHeader
0x180023750  mov     r8d, [r14]; Rva
0x180023753  mov     rdx, rdi; BaseAddress
0x180023756  mov     rcx, r12; NtHeader
0x180023759  call    cs:__imp_RtlImageRvaToVa
0x18002375f  mov     r8d, [rax]
0x180023762  test    r8d, r8d
0x180023765  js      short loc_1800236EA
0x180023767  cmp     dword ptr [rax+4], 0
0x18002376b  jnz     loc_1800236EA
0x180023771  test    r15b, r15b
0x180023774  jz      short loc_1800237CD
0x180023776  lea     rsi, [rdi+r8]
0x18002377a  jmp     short loc_1800237E7
0x18002377c  mov     eax, 20Bh
0x180023781  cmp     [r12+18h], ax
0x180023787  jnz     short loc_1800237E1
0x180023789  test    r15b, r15b
0x18002378c  jz      short loc_180023796
0x18002378e  mov     eax, [r14]
0x180023791  add     rax, rdi
0x180023794  jmp     short loc_1800237A8
0x180023796  xor     r9d, r9d; SectionHeader
0x180023799  mov     r8d, [r14]; Rva
0x18002379c  mov     rdx, rdi; BaseAddress
0x18002379f  mov     rcx, r12; NtHeader
0x1800237a2  call    cs:__imp_RtlImageRvaToVa
0x1800237a8  mov     rcx, [rax]
0x1800237ab  test    rcx, rcx
0x1800237ae  js      loc_1800236EA
0x1800237b4  cmp     qword ptr [rax+8], 0
0x1800237b9  jnz     loc_1800236EA
0x1800237bf  test    r15b, r15b
0x1800237c2  jz      short loc_1800237CA
0x1800237c4  lea     rsi, [rcx+rdi]
0x1800237c8  jmp     short loc_1800237E7
0x1800237ca  mov     r8d, [rax]; Rva
0x1800237cd  xor     r9d, r9d; SectionHeader
0x1800237d0  mov     rdx, rdi; BaseAddress
0x1800237d3  mov     rcx, r12; NtHeader
0x1800237d6  call    cs:__imp_RtlImageRvaToVa
0x1800237dc  mov     rsi, rax
0x1800237df  jmp     short loc_1800237E7
0x1800237e1  xor     ebx, ebx
0x1800237e3  mov     [rsp+68h+var_48], ebx
0x1800237e7  test    ebx, ebx
0x1800237e9  jz      short loc_180023810
0x1800237eb  mov     rcx, [rsi+2]
0x1800237ef  sub     rcx, cs:qword_18002B780
0x1800237f6  jnz     short loc_180023804
0x1800237f8  mov     ecx, [rsi+0Ah]
0x1800237fb  mov     eax, cs:dword_18002B788
0x180023801  sub     rcx, rax
0x180023804  xor     eax, eax
0x180023806  test    rcx, rcx
0x180023809  cmovnz  ebx, eax
0x18002380c  mov     [rsp+68h+var_48], ebx
0x180023810  jmp     short loc_180023818
0x180023812  xor     ebx, ebx
0x180023814  mov     [rsp+68h+var_48], ebx
0x180023818  mov     eax, ebx
0x18002381a  add     rsp, 38h
0x18002381e  pop     r15
0x180023820  pop     r14
0x180023822  pop     r12
0x180023824  pop     rdi
0x180023825  pop     rsi
0x180023826  pop     rbx
0x180023827  retn
```
