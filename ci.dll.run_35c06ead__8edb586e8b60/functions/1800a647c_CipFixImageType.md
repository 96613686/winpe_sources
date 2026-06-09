# CipFixImageType

- ea: `0x1800a647c`
- end: `0x1800a65c9`
- name: `CipFixImageType`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800e5fd0`

## callees

- `0x1800a647c`

## import_xrefs

- `ntoskrnl!RtlImageNtHeader` at `0x1800a6496`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a6496`

## pseudocode

```c
__int64 __fastcall CipFixImageType(char *a1, DWORD *a2, _DWORD *a3, bool *a4, DWORD *a5, DWORD *a6)
{
  PIMAGE_NT_HEADERS v10; // rax
  PIMAGE_NT_HEADERS v11; // r10
  WORD Magic; // ax
  WORD DllCharacteristics; // r9
  __int64 SizeOfHeaders; // rdx
  char *v15; // rcx
  unsigned __int64 v16; // rdi
  unsigned int v17; // edx
  char *v18; // r14
  WORD i; // r8
  WORD NumberOfSections; // r11
  bool v21; // cf
  unsigned __int64 v22; // rbx
  int v23; // eax

  v10 = RtlImageNtHeader(a1);
  v11 = v10;
  if ( v10 )
  {
    Magic = v10->OptionalHeader.Magic;
    if ( Magic == 267 || Magic == 523 )
    {
      DllCharacteristics = v11->OptionalHeader.DllCharacteristics;
      *a5 = v11->OptionalHeader.CheckSum;
      *a2 = v11->OptionalHeader.SizeOfImage;
      SizeOfHeaders = v11->OptionalHeader.SizeOfHeaders;
      *a6 = v11->FileHeader.TimeDateStamp;
      v15 = &a1[SizeOfHeaders];
      v16 = -1;
      if ( &a1[SizeOfHeaders] >= a1 )
        v16 = (unsigned __int64)&a1[SizeOfHeaders];
      v17 = &a1[SizeOfHeaders] < a1 ? 0xC0000095 : 0;
      if ( v15 < a1 )
        v16 = (unsigned __int64)a1;
      v18 = (char *)&v11->OptionalHeader + v11->FileHeader.SizeOfOptionalHeader;
      for ( i = 0; ; ++i )
      {
        NumberOfSections = v11->FileHeader.NumberOfSections;
        v21 = i < NumberOfSections;
        if ( i >= NumberOfSections )
          break;
        v22 = (unsigned __int64)&v18[40 * i];
        if ( v22 >= v16 || (unsigned __int64)&v18[40 * i + 40] > v16 )
        {
          i = v11->FileHeader.NumberOfSections;
LABEL_15:
          v21 = i < NumberOfSections;
          break;
        }
        v23 = *(_DWORD *)(v22 + 36);
        if ( (v23 & 0x10000000) != 0 && v23 < 0 )
          goto LABEL_15;
      }
      *a4 = v21;
      if ( (DllCharacteristics & 0x80u) != 0 )
        *a3 |= 0x80000000;
    }
    else
    {
      return (unsigned int)-1073741701;
    }
  }
  else
  {
    return (unsigned int)-1073741701;
  }
  return v17;
}

```

## disassembly

```asm
0x1800a647c  push    rbx
0x1800a647e  push    rsi
0x1800a647f  push    rdi
0x1800a6480  push    r12
0x1800a6482  push    r14
0x1800a6484  push    r15
0x1800a6486  sub     rsp, 38h
0x1800a648a  mov     r15, r9
0x1800a648d  mov     rsi, r8
0x1800a6490  mov     rdi, rdx
0x1800a6493  mov     rbx, rcx
0x1800a6496  call    cs:__imp_RtlImageNtHeader
0x1800a649d  nop     dword ptr [rax+rax+00h]
0x1800a64a2  mov     r10, rax
0x1800a64a5  test    rax, rax
0x1800a64a8  jz      loc_1800A6585
0x1800a64ae  movzx   eax, word ptr [rax+18h]
0x1800a64b2  mov     ecx, 10Bh
0x1800a64b7  cmp     ax, cx
0x1800a64ba  jz      short loc_1800A64CA
0x1800a64bc  mov     ecx, 20Bh
0x1800a64c1  cmp     ax, cx
0x1800a64c4  jnz     loc_1800A659C
0x1800a64ca  movzx   r9d, word ptr [r10+5Eh]
0x1800a64cf  mov     [rsp+68h+var_44], r9w
0x1800a64d5  mov     rax, [rsp+68h+arg_20]
0x1800a64dd  mov     ecx, [r10+58h]
0x1800a64e1  mov     [rax], ecx
0x1800a64e3  mov     eax, [r10+50h]
0x1800a64e7  mov     [rdi], eax
0x1800a64e9  mov     edx, [r10+54h]
0x1800a64ed  mov     ecx, [r10+8]
0x1800a64f1  mov     rax, [rsp+68h+arg_28]
0x1800a64f9  mov     [rax], ecx
0x1800a64fb  lea     rcx, [rbx+rdx]
0x1800a64ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a6503  cmp     rcx, rbx
0x1800a6506  cmovnb  rdi, rcx
0x1800a650a  sbb     edx, edx
0x1800a650c  and     edx, 0C0000095h
0x1800a6512  mov     [rsp+68h+var_40], edx
0x1800a6516  cmp     rcx, rbx
0x1800a6519  cmovb   rdi, rbx
0x1800a651d  movzx   r14d, word ptr [r10+14h]
0x1800a6522  add     r14, 18h
0x1800a6526  add     r14, r10
0x1800a6529  xor     r8d, r8d
0x1800a652c  lea     r12d, [r8+1]
0x1800a6530  mov     [rsp+68h+var_48], r8w
0x1800a6536  movzx   r11d, word ptr [r10+6]
0x1800a653b  cmp     r8w, r11w
0x1800a653f  jnb     short loc_1800A657D
0x1800a6541  movzx   eax, r8w
0x1800a6545  lea     rcx, [rax+rax*4]
0x1800a6549  lea     rbx, [r14+rcx*8]
0x1800a654d  cmp     rbx, rdi
0x1800a6550  jnb     short loc_1800A6590
0x1800a6552  movzx   eax, r8w
0x1800a6556  add     eax, r12d
0x1800a6559  lea     rcx, [rax+rax*4]
0x1800a655d  lea     rax, [r14+rcx*8]
0x1800a6561  cmp     rax, rdi
0x1800a6564  ja      short loc_1800A6590
0x1800a6566  mov     eax, [rbx+24h]
0x1800a6569  bt      eax, 1Ch
0x1800a656d  jb      short loc_1800A6575
0x1800a656f  add     r8w, r12w
0x1800a6573  jmp     short loc_1800A6530
0x1800a6575  test    eax, eax
0x1800a6577  jns     short loc_1800A656F
0x1800a6579  cmp     r8w, r11w
0x1800a657d  setb    al
0x1800a6580  mov     [r15], al
0x1800a6583  jmp     short loc_1800A65AF
0x1800a6585  mov     edx, 0C000007Bh
0x1800a658a  mov     [rsp+68h+var_40], edx
0x1800a658e  jmp     short loc_1800A65B8
0x1800a6590  movzx   r8d, r11w
0x1800a6594  mov     [rsp+68h+var_48], r11w
0x1800a659a  jmp     short loc_1800A6579
0x1800a659c  mov     edx, 0C000007Bh
0x1800a65a1  mov     [rsp+68h+var_40], edx
0x1800a65a5  jmp     short loc_1800A65B8
0x1800a65a7  mov     edx, eax
0x1800a65a9  mov     [rsp+68h+var_40], eax
0x1800a65ad  jmp     short loc_1800A65B8
0x1800a65af  test    r9b, r9b
0x1800a65b2  jns     short loc_1800A65B8
0x1800a65b4  bts     dword ptr [rsi], 1Fh
0x1800a65b8  mov     eax, edx
0x1800a65ba  add     rsp, 38h
0x1800a65be  pop     r15
0x1800a65c0  pop     r14
0x1800a65c2  pop     r12
0x1800a65c4  pop     rdi
0x1800a65c5  pop     rsi
0x1800a65c6  pop     rbx
0x1800a65c7  retn
```
