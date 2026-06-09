# CipFixImageType

- ea: `0x1800a5158`
- end: `0x1800a52a5`
- name: `CipFixImageType`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800e55e0`

## callees

- `0x1800a5158`

## import_xrefs

- `ntoskrnl!RtlImageNtHeader` at `0x1800a5172`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a5172`

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
0x1800a5158  push    rbx
0x1800a515a  push    rsi
0x1800a515b  push    rdi
0x1800a515c  push    r12
0x1800a515e  push    r14
0x1800a5160  push    r15
0x1800a5162  sub     rsp, 38h
0x1800a5166  mov     r15, r9
0x1800a5169  mov     rsi, r8
0x1800a516c  mov     rdi, rdx
0x1800a516f  mov     rbx, rcx
0x1800a5172  call    cs:__imp_RtlImageNtHeader
0x1800a5179  nop     dword ptr [rax+rax+00h]
0x1800a517e  mov     r10, rax
0x1800a5181  test    rax, rax
0x1800a5184  jz      loc_1800A5261
0x1800a518a  movzx   eax, word ptr [rax+18h]
0x1800a518e  mov     ecx, 10Bh
0x1800a5193  cmp     ax, cx
0x1800a5196  jz      short loc_1800A51A6
0x1800a5198  mov     ecx, 20Bh
0x1800a519d  cmp     ax, cx
0x1800a51a0  jnz     loc_1800A5278
0x1800a51a6  movzx   r9d, word ptr [r10+5Eh]
0x1800a51ab  mov     [rsp+68h+var_44], r9w
0x1800a51b1  mov     rax, [rsp+68h+arg_20]
0x1800a51b9  mov     ecx, [r10+58h]
0x1800a51bd  mov     [rax], ecx
0x1800a51bf  mov     eax, [r10+50h]
0x1800a51c3  mov     [rdi], eax
0x1800a51c5  mov     edx, [r10+54h]
0x1800a51c9  mov     ecx, [r10+8]
0x1800a51cd  mov     rax, [rsp+68h+arg_28]
0x1800a51d5  mov     [rax], ecx
0x1800a51d7  lea     rcx, [rbx+rdx]
0x1800a51db  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a51df  cmp     rcx, rbx
0x1800a51e2  cmovnb  rdi, rcx
0x1800a51e6  sbb     edx, edx
0x1800a51e8  and     edx, 0C0000095h
0x1800a51ee  mov     [rsp+68h+var_40], edx
0x1800a51f2  cmp     rcx, rbx
0x1800a51f5  cmovb   rdi, rbx
0x1800a51f9  movzx   r14d, word ptr [r10+14h]
0x1800a51fe  add     r14, 18h
0x1800a5202  add     r14, r10
0x1800a5205  xor     r8d, r8d
0x1800a5208  lea     r12d, [r8+1]
0x1800a520c  mov     [rsp+68h+var_48], r8w
0x1800a5212  movzx   r11d, word ptr [r10+6]
0x1800a5217  cmp     r8w, r11w
0x1800a521b  jnb     short loc_1800A5259
0x1800a521d  movzx   eax, r8w
0x1800a5221  lea     rcx, [rax+rax*4]
0x1800a5225  lea     rbx, [r14+rcx*8]
0x1800a5229  cmp     rbx, rdi
0x1800a522c  jnb     short loc_1800A526C
0x1800a522e  movzx   eax, r8w
0x1800a5232  add     eax, r12d
0x1800a5235  lea     rcx, [rax+rax*4]
0x1800a5239  lea     rax, [r14+rcx*8]
0x1800a523d  cmp     rax, rdi
0x1800a5240  ja      short loc_1800A526C
0x1800a5242  mov     eax, [rbx+24h]
0x1800a5245  bt      eax, 1Ch
0x1800a5249  jb      short loc_1800A5251
0x1800a524b  add     r8w, r12w
0x1800a524f  jmp     short loc_1800A520C
0x1800a5251  test    eax, eax
0x1800a5253  jns     short loc_1800A524B
0x1800a5255  cmp     r8w, r11w
0x1800a5259  setb    al
0x1800a525c  mov     [r15], al
0x1800a525f  jmp     short loc_1800A528B
0x1800a5261  mov     edx, 0C000007Bh
0x1800a5266  mov     [rsp+68h+var_40], edx
0x1800a526a  jmp     short loc_1800A5294
0x1800a526c  movzx   r8d, r11w
0x1800a5270  mov     [rsp+68h+var_48], r11w
0x1800a5276  jmp     short loc_1800A5255
0x1800a5278  mov     edx, 0C000007Bh
0x1800a527d  mov     [rsp+68h+var_40], edx
0x1800a5281  jmp     short loc_1800A5294
0x1800a5283  mov     edx, eax
0x1800a5285  mov     [rsp+68h+var_40], eax
0x1800a5289  jmp     short loc_1800A5294
0x1800a528b  test    r9b, r9b
0x1800a528e  jns     short loc_1800A5294
0x1800a5290  bts     dword ptr [rsi], 1Fh
0x1800a5294  mov     eax, edx
0x1800a5296  add     rsp, 38h
0x1800a529a  pop     r15
0x1800a529c  pop     r14
0x1800a529e  pop     r12
0x1800a52a0  pop     rdi
0x1800a52a1  pop     rsi
0x1800a52a2  pop     rbx
0x1800a52a3  retn
```
