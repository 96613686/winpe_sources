# CiValidateImageHeaderMapping

- ea: `0x18009b020`
- end: `0x18009b1f2`
- name: `CiValidateImageHeaderMapping`
- size: `466`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800765e4`
- `0x180077090`
- `0x18009abcc`
- `0x18009acb8`
- `0x18009d40c`
- `0x1800d5e20`

## callees

- `0x18009b020`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x18009b063`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18009b063`

## pseudocode

```c
__int64 __fastcall CiValidateImageHeaderMapping(char *BaseAddress, ULONGLONG Size, _QWORD *a3, DWORD *a4)
{
  DWORD v6; // edi
  char *v8; // r14
  NTSTATUS v9; // edx
  unsigned __int64 SizeOfOptionalHeader; // rcx
  IMAGE_OPTIONAL_HEADER64 *p_OptionalHeader; // r10
  char *v12; // rax
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // rsi
  DWORD SizeOfHeaders; // r10d
  int NumberOfSections; // eax
  char *v17; // rdi
  char *v18; // rcx
  PIMAGE_NT_HEADERS v20; // [rsp+60h] [rbp+8h] BYREF

  v6 = Size;
  v20 = 0;
  v8 = &BaseAddress[(unsigned int)Size];
  if ( v8 < BaseAddress )
    return (unsigned int)-1073741675;
  v9 = RtlImageNtHeaderEx(0, BaseAddress, (unsigned int)Size, &v20);
  if ( v9 < 0 )
    return (unsigned int)v9;
  SizeOfOptionalHeader = v20->FileHeader.SizeOfOptionalHeader;
  p_OptionalHeader = &v20->OptionalHeader;
  v12 = (char *)&v20->OptionalHeader + SizeOfOptionalHeader;
  v13 = -1;
  v14 = -1;
  if ( v12 >= (char *)&v20->OptionalHeader )
    v14 = (unsigned __int64)&v20->OptionalHeader + SizeOfOptionalHeader;
  v9 = v12 < (char *)&v20->OptionalHeader ? 0xC0000095 : 0;
  if ( v12 < (char *)p_OptionalHeader || v14 > (unsigned __int64)v8 || (unsigned int)SizeOfOptionalHeader < 0x1A )
    return (unsigned int)-1073741701;
  if ( p_OptionalHeader->Magic == 523 )
  {
    if ( SizeOfOptionalHeader < 0xB0 )
      return (unsigned int)-1073741701;
  }
  else
  {
    if ( p_OptionalHeader->Magic != 267 )
      return (unsigned int)-1073741701;
    if ( SizeOfOptionalHeader < 0xA0 )
      return (unsigned int)-1073741701;
  }
  SizeOfHeaders = v20->OptionalHeader.SizeOfHeaders;
  if ( SizeOfHeaders > v6 )
  {
    return (unsigned int)-1073741306;
  }
  else
  {
    NumberOfSections = v20->FileHeader.NumberOfSections;
    if ( !(_WORD)NumberOfSections )
      goto LABEL_18;
    v17 = (char *)&v20->OptionalHeader + SizeOfOptionalHeader;
    if ( (unsigned __int64)v17 < v14 )
      return (unsigned int)-1073741701;
    v18 = &v17[40 * NumberOfSections];
    if ( v18 >= v17 )
      v13 = (unsigned __int64)&v17[40 * NumberOfSections];
    v9 = v18 < v17 ? 0xC0000095 : 0;
    if ( v13 > (unsigned __int64)v8 || v18 < v17 )
      return (unsigned int)-1073741701;
    if ( v13 - (unsigned __int64)BaseAddress > SizeOfHeaders )
    {
      return (unsigned int)-1073741701;
    }
    else
    {
LABEL_18:
      *a3 = v20;
      if ( a4 )
        *a4 = SizeOfHeaders;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009b020  mov     rax, rsp
0x18009b023  mov     [rax+10h], rbx
0x18009b027  mov     [rax+18h], rsi
0x18009b02b  push    rdi
0x18009b02c  push    r12
0x18009b02e  push    r13
0x18009b030  push    r14
0x18009b032  push    r15
0x18009b034  sub     rsp, 30h
0x18009b038  mov     r15, r9
0x18009b03b  mov     r12, r8
0x18009b03e  mov     edi, edx
0x18009b040  mov     rbx, rcx
0x18009b043  xor     r13d, r13d
0x18009b046  mov     [rax+8], r13
0x18009b04a  mov     r8d, edx; Size
0x18009b04d  lea     r14, [rdi+rcx]
0x18009b051  cmp     r14, rcx
0x18009b054  jb      loc_18009B1EB
0x18009b05a  lea     r9, [rax+8]; NtHeader
0x18009b05e  mov     rdx, rcx; BaseAddress
0x18009b061  xor     ecx, ecx; Flags
0x18009b063  call    cs:__imp_RtlImageNtHeaderEx
0x18009b06a  nop     dword ptr [rax+rax+00h]
0x18009b06f  mov     edx, eax
0x18009b071  mov     [rsp+58h+var_38], eax
0x18009b075  test    eax, eax
0x18009b077  js      loc_18009B19C
0x18009b07d  mov     r8, [rsp+58h+arg_0]
0x18009b082  movzx   ecx, word ptr [r8+14h]
0x18009b087  lea     r10, [r8+18h]
0x18009b08b  lea     rax, [r10+rcx]
0x18009b08f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009b093  mov     rsi, r9
0x18009b096  cmp     rax, r10
0x18009b099  cmovnb  rsi, rax
0x18009b09d  sbb     edx, edx
0x18009b09f  mov     r11d, 0C0000095h
0x18009b0a5  and     edx, r11d
0x18009b0a8  mov     [rsp+58h+var_38], edx
0x18009b0ac  cmp     rax, r10
0x18009b0af  jb      loc_18009B1BF
0x18009b0b5  cmp     rsi, r14
0x18009b0b8  ja      loc_18009B1BF
0x18009b0be  cmp     ecx, 1Ah
0x18009b0c1  jb      loc_18009B1BF
0x18009b0c7  movzx   eax, word ptr [r10]
0x18009b0cb  mov     r10d, 20Bh
0x18009b0d1  cmp     ax, r10w
0x18009b0d5  jnz     short loc_18009B155
0x18009b0d7  cmp     rcx, 0B0h
0x18009b0de  jb      loc_18009B19E
0x18009b0e4  mov     r10d, [r8+54h]
0x18009b0e8  cmp     r10d, edi
0x18009b0eb  ja      loc_18009B17B
0x18009b0f1  movzx   eax, word ptr [r8+6]
0x18009b0f6  test    ax, ax
0x18009b0f9  jz      short loc_18009B147
0x18009b0fb  lea     rdi, [r8+18h]
0x18009b0ff  add     rdi, rcx
0x18009b102  cmp     rdi, rsi
0x18009b105  jb      loc_18009B1A9
0x18009b10b  lea     rcx, [rax+rax*4]
0x18009b10f  shl     rcx, 3
0x18009b113  mov     [rsp+58h+var_30], rcx
0x18009b118  mov     [rsp+58h+var_38], r13d
0x18009b11d  mov     ecx, ecx
0x18009b11f  add     rcx, rdi
0x18009b122  cmp     rcx, rdi
0x18009b125  cmovnb  r9, rcx
0x18009b129  sbb     edx, edx
0x18009b12b  and     edx, r11d
0x18009b12e  mov     [rsp+58h+var_38], edx
0x18009b132  cmp     r9, r14
0x18009b135  ja      short loc_18009B186
0x18009b137  cmp     rcx, rdi
0x18009b13a  jb      short loc_18009B186
0x18009b13c  sub     r9, rbx
0x18009b13f  mov     eax, r10d
0x18009b142  cmp     r9, rax
0x18009b145  ja      short loc_18009B170
0x18009b147  mov     [r12], r8
0x18009b14b  test    r15, r15
0x18009b14e  jz      short loc_18009B153
0x18009b150  mov     [r15], r10d
0x18009b153  jmp     short loc_18009B1D0
0x18009b155  mov     r10d, 10Bh
0x18009b15b  cmp     ax, r10w
0x18009b15f  jnz     short loc_18009B1B4
0x18009b161  cmp     rcx, 0A0h
0x18009b168  jnb     loc_18009B0E4
0x18009b16e  jmp     short loc_18009B191
0x18009b170  mov     edx, 0C000007Bh
0x18009b175  mov     [rsp+58h+var_38], edx
0x18009b179  jmp     short loc_18009B1D0
0x18009b17b  mov     edx, 0C0000206h
0x18009b180  mov     [rsp+58h+var_38], edx
0x18009b184  jmp     short loc_18009B1D0
0x18009b186  mov     edx, 0C000007Bh
0x18009b18b  mov     [rsp+58h+var_38], edx
0x18009b18f  jmp     short loc_18009B1D0
0x18009b191  mov     edx, 0C000007Bh
0x18009b196  mov     [rsp+58h+var_38], edx
0x18009b19a  jmp     short loc_18009B1D0
0x18009b19c  jmp     short loc_18009B1D0
0x18009b19e  mov     edx, 0C000007Bh
0x18009b1a3  mov     [rsp+58h+var_38], edx
0x18009b1a7  jmp     short loc_18009B1D0
0x18009b1a9  mov     edx, 0C000007Bh
0x18009b1ae  mov     [rsp+58h+var_38], edx
0x18009b1b2  jmp     short loc_18009B1D0
0x18009b1b4  mov     edx, 0C000007Bh
0x18009b1b9  mov     [rsp+58h+var_38], edx
0x18009b1bd  jmp     short loc_18009B1D0
0x18009b1bf  mov     edx, 0C000007Bh
0x18009b1c4  mov     [rsp+58h+var_38], edx
0x18009b1c8  jmp     short loc_18009B1D0
0x18009b1ca  mov     edx, eax
0x18009b1cc  mov     [rsp+58h+var_38], eax
0x18009b1d0  mov     eax, edx
0x18009b1d2  mov     rbx, [rsp+58h+arg_8]
0x18009b1d7  mov     rsi, [rsp+58h+arg_10]
0x18009b1dc  add     rsp, 30h
0x18009b1e0  pop     r15
0x18009b1e2  pop     r14
0x18009b1e4  pop     r13
0x18009b1e6  pop     r12
0x18009b1e8  pop     rdi
0x18009b1e9  retn
0x18009b1eb  mov     edx, 0C0000095h
0x18009b1f0  jmp     short loc_18009B1D0
```
