# CiValidateImageHeaderMapping

- ea: `0x1800a0360`
- end: `0x1800a0532`
- name: `CiValidateImageHeaderMapping`
- size: `466`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800768c4`
- `0x180077370`
- `0x18009ff0c`
- `0x18009fff8`
- `0x1800a26d4`
- `0x1800d5e30`

## callees

- `0x1800a0360`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a03a3`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a03a3`

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
0x1800a0360  mov     rax, rsp
0x1800a0363  mov     [rax+10h], rbx
0x1800a0367  mov     [rax+18h], rsi
0x1800a036b  push    rdi
0x1800a036c  push    r12
0x1800a036e  push    r13
0x1800a0370  push    r14
0x1800a0372  push    r15
0x1800a0374  sub     rsp, 30h
0x1800a0378  mov     r15, r9
0x1800a037b  mov     r12, r8
0x1800a037e  mov     edi, edx
0x1800a0380  mov     rbx, rcx
0x1800a0383  xor     r13d, r13d
0x1800a0386  mov     [rax+8], r13
0x1800a038a  mov     r8d, edx; Size
0x1800a038d  lea     r14, [rdi+rcx]
0x1800a0391  cmp     r14, rcx
0x1800a0394  jb      loc_1800A052B
0x1800a039a  lea     r9, [rax+8]; NtHeader
0x1800a039e  mov     rdx, rcx; BaseAddress
0x1800a03a1  xor     ecx, ecx; Flags
0x1800a03a3  call    cs:__imp_RtlImageNtHeaderEx
0x1800a03aa  nop     dword ptr [rax+rax+00h]
0x1800a03af  mov     edx, eax
0x1800a03b1  mov     [rsp+58h+var_38], eax
0x1800a03b5  test    eax, eax
0x1800a03b7  js      loc_1800A04DC
0x1800a03bd  mov     r8, [rsp+58h+arg_0]
0x1800a03c2  movzx   ecx, word ptr [r8+14h]
0x1800a03c7  lea     r10, [r8+18h]
0x1800a03cb  lea     rax, [r10+rcx]
0x1800a03cf  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800a03d3  mov     rsi, r9
0x1800a03d6  cmp     rax, r10
0x1800a03d9  cmovnb  rsi, rax
0x1800a03dd  sbb     edx, edx
0x1800a03df  mov     r11d, 0C0000095h
0x1800a03e5  and     edx, r11d
0x1800a03e8  mov     [rsp+58h+var_38], edx
0x1800a03ec  cmp     rax, r10
0x1800a03ef  jb      loc_1800A04FF
0x1800a03f5  cmp     rsi, r14
0x1800a03f8  ja      loc_1800A04FF
0x1800a03fe  cmp     ecx, 1Ah
0x1800a0401  jb      loc_1800A04FF
0x1800a0407  movzx   eax, word ptr [r10]
0x1800a040b  mov     r10d, 20Bh
0x1800a0411  cmp     ax, r10w
0x1800a0415  jnz     short loc_1800A0495
0x1800a0417  cmp     rcx, 0B0h
0x1800a041e  jb      loc_1800A04DE
0x1800a0424  mov     r10d, [r8+54h]
0x1800a0428  cmp     r10d, edi
0x1800a042b  ja      loc_1800A04BB
0x1800a0431  movzx   eax, word ptr [r8+6]
0x1800a0436  test    ax, ax
0x1800a0439  jz      short loc_1800A0487
0x1800a043b  lea     rdi, [r8+18h]
0x1800a043f  add     rdi, rcx
0x1800a0442  cmp     rdi, rsi
0x1800a0445  jb      loc_1800A04E9
0x1800a044b  lea     rcx, [rax+rax*4]
0x1800a044f  shl     rcx, 3
0x1800a0453  mov     [rsp+58h+var_30], rcx
0x1800a0458  mov     [rsp+58h+var_38], r13d
0x1800a045d  mov     ecx, ecx
0x1800a045f  add     rcx, rdi
0x1800a0462  cmp     rcx, rdi
0x1800a0465  cmovnb  r9, rcx
0x1800a0469  sbb     edx, edx
0x1800a046b  and     edx, r11d
0x1800a046e  mov     [rsp+58h+var_38], edx
0x1800a0472  cmp     r9, r14
0x1800a0475  ja      short loc_1800A04C6
0x1800a0477  cmp     rcx, rdi
0x1800a047a  jb      short loc_1800A04C6
0x1800a047c  sub     r9, rbx
0x1800a047f  mov     eax, r10d
0x1800a0482  cmp     r9, rax
0x1800a0485  ja      short loc_1800A04B0
0x1800a0487  mov     [r12], r8
0x1800a048b  test    r15, r15
0x1800a048e  jz      short loc_1800A0493
0x1800a0490  mov     [r15], r10d
0x1800a0493  jmp     short loc_1800A0510
0x1800a0495  mov     r10d, 10Bh
0x1800a049b  cmp     ax, r10w
0x1800a049f  jnz     short loc_1800A04F4
0x1800a04a1  cmp     rcx, 0A0h
0x1800a04a8  jnb     loc_1800A0424
0x1800a04ae  jmp     short loc_1800A04D1
0x1800a04b0  mov     edx, 0C000007Bh
0x1800a04b5  mov     [rsp+58h+var_38], edx
0x1800a04b9  jmp     short loc_1800A0510
0x1800a04bb  mov     edx, 0C0000206h
0x1800a04c0  mov     [rsp+58h+var_38], edx
0x1800a04c4  jmp     short loc_1800A0510
0x1800a04c6  mov     edx, 0C000007Bh
0x1800a04cb  mov     [rsp+58h+var_38], edx
0x1800a04cf  jmp     short loc_1800A0510
0x1800a04d1  mov     edx, 0C000007Bh
0x1800a04d6  mov     [rsp+58h+var_38], edx
0x1800a04da  jmp     short loc_1800A0510
0x1800a04dc  jmp     short loc_1800A0510
0x1800a04de  mov     edx, 0C000007Bh
0x1800a04e3  mov     [rsp+58h+var_38], edx
0x1800a04e7  jmp     short loc_1800A0510
0x1800a04e9  mov     edx, 0C000007Bh
0x1800a04ee  mov     [rsp+58h+var_38], edx
0x1800a04f2  jmp     short loc_1800A0510
0x1800a04f4  mov     edx, 0C000007Bh
0x1800a04f9  mov     [rsp+58h+var_38], edx
0x1800a04fd  jmp     short loc_1800A0510
0x1800a04ff  mov     edx, 0C000007Bh
0x1800a0504  mov     [rsp+58h+var_38], edx
0x1800a0508  jmp     short loc_1800A0510
0x1800a050a  mov     edx, eax
0x1800a050c  mov     [rsp+58h+var_38], eax
0x1800a0510  mov     eax, edx
0x1800a0512  mov     rbx, [rsp+58h+arg_8]
0x1800a0517  mov     rsi, [rsp+58h+arg_10]
0x1800a051c  add     rsp, 30h
0x1800a0520  pop     r15
0x1800a0522  pop     r14
0x1800a0524  pop     r13
0x1800a0526  pop     r12
0x1800a0528  pop     rdi
0x1800a0529  retn
0x1800a052b  mov     edx, 0C0000095h
0x1800a0530  jmp     short loc_1800A0510
```
