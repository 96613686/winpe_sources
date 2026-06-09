# CiValidateImageHeaderMapping

- ea: `0x1800999f0`
- end: `0x180099bc2`
- name: `CiValidateImageHeaderMapping`
- size: `466`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONGLONG Size)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180075028`
- `0x180075ae0`
- `0x18009959c`
- `0x180099688`
- `0x18009bddc`
- `0x1800d4960`

## callees

- `0x1800999f0`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x180099a33`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x180099a33`

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
0x1800999f0  mov     rax, rsp
0x1800999f3  mov     [rax+10h], rbx
0x1800999f7  mov     [rax+18h], rsi
0x1800999fb  push    rdi
0x1800999fc  push    r12
0x1800999fe  push    r13
0x180099a00  push    r14
0x180099a02  push    r15
0x180099a04  sub     rsp, 30h
0x180099a08  mov     r15, r9
0x180099a0b  mov     r12, r8
0x180099a0e  mov     edi, edx
0x180099a10  mov     rbx, rcx
0x180099a13  xor     r13d, r13d
0x180099a16  mov     [rax+8], r13
0x180099a1a  mov     r8d, edx; Size
0x180099a1d  lea     r14, [rdi+rcx]
0x180099a21  cmp     r14, rcx
0x180099a24  jb      loc_180099BBB
0x180099a2a  lea     r9, [rax+8]; NtHeader
0x180099a2e  mov     rdx, rcx; BaseAddress
0x180099a31  xor     ecx, ecx; Flags
0x180099a33  call    cs:__imp_RtlImageNtHeaderEx
0x180099a3a  nop     dword ptr [rax+rax+00h]
0x180099a3f  mov     edx, eax
0x180099a41  mov     [rsp+58h+var_38], eax
0x180099a45  test    eax, eax
0x180099a47  js      loc_180099B6C
0x180099a4d  mov     r8, [rsp+58h+arg_0]
0x180099a52  movzx   ecx, word ptr [r8+14h]
0x180099a57  lea     r10, [r8+18h]
0x180099a5b  lea     rax, [r10+rcx]
0x180099a5f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180099a63  mov     rsi, r9
0x180099a66  cmp     rax, r10
0x180099a69  cmovnb  rsi, rax
0x180099a6d  sbb     edx, edx
0x180099a6f  mov     r11d, 0C0000095h
0x180099a75  and     edx, r11d
0x180099a78  mov     [rsp+58h+var_38], edx
0x180099a7c  cmp     rax, r10
0x180099a7f  jb      loc_180099B8F
0x180099a85  cmp     rsi, r14
0x180099a88  ja      loc_180099B8F
0x180099a8e  cmp     ecx, 1Ah
0x180099a91  jb      loc_180099B8F
0x180099a97  movzx   eax, word ptr [r10]
0x180099a9b  mov     r10d, 20Bh
0x180099aa1  cmp     ax, r10w
0x180099aa5  jnz     short loc_180099B25
0x180099aa7  cmp     rcx, 0B0h
0x180099aae  jb      loc_180099B6E
0x180099ab4  mov     r10d, [r8+54h]
0x180099ab8  cmp     r10d, edi
0x180099abb  ja      loc_180099B4B
0x180099ac1  movzx   eax, word ptr [r8+6]
0x180099ac6  test    ax, ax
0x180099ac9  jz      short loc_180099B17
0x180099acb  lea     rdi, [r8+18h]
0x180099acf  add     rdi, rcx
0x180099ad2  cmp     rdi, rsi
0x180099ad5  jb      loc_180099B79
0x180099adb  lea     rcx, [rax+rax*4]
0x180099adf  shl     rcx, 3
0x180099ae3  mov     [rsp+58h+var_30], rcx
0x180099ae8  mov     [rsp+58h+var_38], r13d
0x180099aed  mov     ecx, ecx
0x180099aef  add     rcx, rdi
0x180099af2  cmp     rcx, rdi
0x180099af5  cmovnb  r9, rcx
0x180099af9  sbb     edx, edx
0x180099afb  and     edx, r11d
0x180099afe  mov     [rsp+58h+var_38], edx
0x180099b02  cmp     r9, r14
0x180099b05  ja      short loc_180099B56
0x180099b07  cmp     rcx, rdi
0x180099b0a  jb      short loc_180099B56
0x180099b0c  sub     r9, rbx
0x180099b0f  mov     eax, r10d
0x180099b12  cmp     r9, rax
0x180099b15  ja      short loc_180099B40
0x180099b17  mov     [r12], r8
0x180099b1b  test    r15, r15
0x180099b1e  jz      short loc_180099B23
0x180099b20  mov     [r15], r10d
0x180099b23  jmp     short loc_180099BA0
0x180099b25  mov     r10d, 10Bh
0x180099b2b  cmp     ax, r10w
0x180099b2f  jnz     short loc_180099B84
0x180099b31  cmp     rcx, 0A0h
0x180099b38  jnb     loc_180099AB4
0x180099b3e  jmp     short loc_180099B61
0x180099b40  mov     edx, 0C000007Bh
0x180099b45  mov     [rsp+58h+var_38], edx
0x180099b49  jmp     short loc_180099BA0
0x180099b4b  mov     edx, 0C0000206h
0x180099b50  mov     [rsp+58h+var_38], edx
0x180099b54  jmp     short loc_180099BA0
0x180099b56  mov     edx, 0C000007Bh
0x180099b5b  mov     [rsp+58h+var_38], edx
0x180099b5f  jmp     short loc_180099BA0
0x180099b61  mov     edx, 0C000007Bh
0x180099b66  mov     [rsp+58h+var_38], edx
0x180099b6a  jmp     short loc_180099BA0
0x180099b6c  jmp     short loc_180099BA0
0x180099b6e  mov     edx, 0C000007Bh
0x180099b73  mov     [rsp+58h+var_38], edx
0x180099b77  jmp     short loc_180099BA0
0x180099b79  mov     edx, 0C000007Bh
0x180099b7e  mov     [rsp+58h+var_38], edx
0x180099b82  jmp     short loc_180099BA0
0x180099b84  mov     edx, 0C000007Bh
0x180099b89  mov     [rsp+58h+var_38], edx
0x180099b8d  jmp     short loc_180099BA0
0x180099b8f  mov     edx, 0C000007Bh
0x180099b94  mov     [rsp+58h+var_38], edx
0x180099b98  jmp     short loc_180099BA0
0x180099b9a  mov     edx, eax
0x180099b9c  mov     [rsp+58h+var_38], eax
0x180099ba0  mov     eax, edx
0x180099ba2  mov     rbx, [rsp+58h+arg_8]
0x180099ba7  mov     rsi, [rsp+58h+arg_10]
0x180099bac  add     rsp, 30h
0x180099bb0  pop     r15
0x180099bb2  pop     r14
0x180099bb4  pop     r13
0x180099bb6  pop     r12
0x180099bb8  pop     rdi
0x180099bb9  retn
0x180099bbb  mov     edx, 0C0000095h
0x180099bc0  jmp     short loc_180099BA0
```
