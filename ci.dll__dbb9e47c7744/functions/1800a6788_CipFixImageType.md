# CipFixImageType

- ea: `0x1800a6788`
- end: `0x1800a68d5`
- name: `CipFixImageType`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800e5a50`

## callees

- `0x1800a6788`

## import_xrefs

- `ntoskrnl!RtlImageNtHeader` at `0x1800a67a2`
- `ntoskrnl!RtlImageNtHeader` at `0x1800a67a2`

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
0x1800a6788  push    rbx
0x1800a678a  push    rsi
0x1800a678b  push    rdi
0x1800a678c  push    r12
0x1800a678e  push    r14
0x1800a6790  push    r15
0x1800a6792  sub     rsp, 38h
0x1800a6796  mov     r15, r9
0x1800a6799  mov     rsi, r8
0x1800a679c  mov     rdi, rdx
0x1800a679f  mov     rbx, rcx
0x1800a67a2  call    cs:__imp_RtlImageNtHeader
0x1800a67a9  nop     dword ptr [rax+rax+00h]
0x1800a67ae  mov     r10, rax
0x1800a67b1  test    rax, rax
0x1800a67b4  jz      loc_1800A6891
0x1800a67ba  movzx   eax, word ptr [rax+18h]
0x1800a67be  mov     ecx, 10Bh
0x1800a67c3  cmp     ax, cx
0x1800a67c6  jz      short loc_1800A67D6
0x1800a67c8  mov     ecx, 20Bh
0x1800a67cd  cmp     ax, cx
0x1800a67d0  jnz     loc_1800A68A8
0x1800a67d6  movzx   r9d, word ptr [r10+5Eh]
0x1800a67db  mov     [rsp+68h+var_44], r9w
0x1800a67e1  mov     rax, [rsp+68h+arg_20]
0x1800a67e9  mov     ecx, [r10+58h]
0x1800a67ed  mov     [rax], ecx
0x1800a67ef  mov     eax, [r10+50h]
0x1800a67f3  mov     [rdi], eax
0x1800a67f5  mov     edx, [r10+54h]
0x1800a67f9  mov     ecx, [r10+8]
0x1800a67fd  mov     rax, [rsp+68h+arg_28]
0x1800a6805  mov     [rax], ecx
0x1800a6807  lea     rcx, [rbx+rdx]
0x1800a680b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a680f  cmp     rcx, rbx
0x1800a6812  cmovnb  rdi, rcx
0x1800a6816  sbb     edx, edx
0x1800a6818  and     edx, 0C0000095h
0x1800a681e  mov     [rsp+68h+var_40], edx
0x1800a6822  cmp     rcx, rbx
0x1800a6825  cmovb   rdi, rbx
0x1800a6829  movzx   r14d, word ptr [r10+14h]
0x1800a682e  add     r14, 18h
0x1800a6832  add     r14, r10
0x1800a6835  xor     r8d, r8d
0x1800a6838  lea     r12d, [r8+1]
0x1800a683c  mov     [rsp+68h+var_48], r8w
0x1800a6842  movzx   r11d, word ptr [r10+6]
0x1800a6847  cmp     r8w, r11w
0x1800a684b  jnb     short loc_1800A6889
0x1800a684d  movzx   eax, r8w
0x1800a6851  lea     rcx, [rax+rax*4]
0x1800a6855  lea     rbx, [r14+rcx*8]
0x1800a6859  cmp     rbx, rdi
0x1800a685c  jnb     short loc_1800A689C
0x1800a685e  movzx   eax, r8w
0x1800a6862  add     eax, r12d
0x1800a6865  lea     rcx, [rax+rax*4]
0x1800a6869  lea     rax, [r14+rcx*8]
0x1800a686d  cmp     rax, rdi
0x1800a6870  ja      short loc_1800A689C
0x1800a6872  mov     eax, [rbx+24h]
0x1800a6875  bt      eax, 1Ch
0x1800a6879  jb      short loc_1800A6881
0x1800a687b  add     r8w, r12w
0x1800a687f  jmp     short loc_1800A683C
0x1800a6881  test    eax, eax
0x1800a6883  jns     short loc_1800A687B
0x1800a6885  cmp     r8w, r11w
0x1800a6889  setb    al
0x1800a688c  mov     [r15], al
0x1800a688f  jmp     short loc_1800A68BB
0x1800a6891  mov     edx, 0C000007Bh
0x1800a6896  mov     [rsp+68h+var_40], edx
0x1800a689a  jmp     short loc_1800A68C4
0x1800a689c  movzx   r8d, r11w
0x1800a68a0  mov     [rsp+68h+var_48], r11w
0x1800a68a6  jmp     short loc_1800A6885
0x1800a68a8  mov     edx, 0C000007Bh
0x1800a68ad  mov     [rsp+68h+var_40], edx
0x1800a68b1  jmp     short loc_1800A68C4
0x1800a68b3  mov     edx, eax
0x1800a68b5  mov     [rsp+68h+var_40], eax
0x1800a68b9  jmp     short loc_1800A68C4
0x1800a68bb  test    r9b, r9b
0x1800a68be  jns     short loc_1800A68C4
0x1800a68c0  bts     dword ptr [rsi], 1Fh
0x1800a68c4  mov     eax, edx
0x1800a68c6  add     rsp, 38h
0x1800a68ca  pop     r15
0x1800a68cc  pop     r14
0x1800a68ce  pop     r12
0x1800a68d0  pop     rdi
0x1800a68d1  pop     rsi
0x1800a68d2  pop     rbx
0x1800a68d3  retn
```
