# GetNTSecurityParameters

- ea: `0x1400133c4`
- end: `0x140013654`
- name: `GetNTSecurityParameters`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013a7c`

## callees

- `0x1400133c4`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140013562`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140013562`
- `ntoskrnl!ExAllocatePool2` at `0x1400134c2`
- `ntoskrnl!ExAllocatePool2` at `0x1400134c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013542`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013542`
- `rdbss!RxAllocateMdl2` at `0x14001351a`
- `rdbss!RxAllocateMdl2` at `0x14001351a`

## pseudocode

```c
__int64 __fastcall GetNTSecurityParameters(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        struct _MDL **a8,
        unsigned int *a9)
{
  __int64 v9; // rax
  unsigned __int8 *v12; // r15
  unsigned int v13; // esi
  __int64 v14; // r10
  __int64 v15; // rcx
  unsigned int v16; // r14d
  void *Pool2; // rax
  unsigned int v18; // edx
  struct _MDL *Mdl2; // rcx
  __int64 result; // rax
  int v21; // eax
  __int64 v22; // rax
  unsigned __int16 v23; // r10
  unsigned __int8 *v24; // rdx

  v9 = *a4;
  v12 = &a4[2 * v9 + 3];
  v13 = 0;
  *a7 += 37;
  v14 = *(unsigned __int16 *)&a4[2 * v9 + 1];
  *(_DWORD *)(a2 + 32) = a4[3] & 1;
  LOBYTE(v9) = (a4[3] & 2) != 0;
  *(_WORD *)(a2 + 112) = 0;
  *(_BYTE *)(a2 + 102) = v9;
  *(_BYTE *)(a2 + 103) = (a4[3] & 4) != 0;
  *(_BYTE *)(a2 + 104) = (a4[3] & 8) != 0;
  if ( *(int *)(a2 + 128) >= 0 )
  {
    if ( (unsigned int)v14 <= a5 && (unsigned int)v14 + *a7 <= a5 )
    {
      *a7 = a6;
      *(_DWORD *)(a2 + 24) = *((_DWORD *)a4 + 4);
      if ( !*(_BYTE *)(a2 + 102) )
        return v13;
      if ( a5 >= (unsigned __int64)(v14 + 69) )
      {
        v21 = a4[34];
        *(_WORD *)(a2 + 112) = v21;
        if ( !(_WORD)v21 )
          return v13;
        if ( v21 == 8 && (unsigned int)v14 >= 8 )
        {
          *(_QWORD *)(a2 + 114) = *(_QWORD *)v12;
          v22 = *(unsigned __int16 *)(a2 + 112);
          if ( (int)v14 - (int)v22 > 0 )
          {
            v23 = v14 - v22;
            *(_WORD *)a3 = v23;
            if ( v23 > *(_WORD *)(a3 + 2) )
            {
              *(_WORD *)a3 = 0;
              return (unsigned int)-2147483643;
            }
            else
            {
              v24 = &v12[v22];
              if ( (v23 & 1) != 0 )
              {
                ++v24;
                *(_WORD *)a3 = --v23;
              }
              memmove(*(void **)(a3 + 8), v24, v23);
            }
          }
          return v13;
        }
        goto LABEL_17;
      }
    }
  }
  else if ( (unsigned __int16)v14 >= 0x10u && (unsigned int)v14 <= a6 )
  {
    v15 = *a7;
    if ( (int)v14 + (int)v15 <= a6 && v15 + 16 <= (unsigned __int64)a5 )
    {
      *(_OWORD *)(a2 + 132) = *(_OWORD *)v12;
      *a7 += 16;
      if ( *(_QWORD *)(a2 + 152) )
        return v13;
      v16 = v14 - 16;
      if ( (_DWORD)v14 == 16 )
        return v13;
      Pool2 = (void *)ExAllocatePool2(66, v16, 1682009427);
      *(_QWORD *)(a2 + 152) = Pool2;
      if ( !Pool2 )
        return (unsigned int)-1073741670;
      *(_DWORD *)(a2 + 148) = v16;
      v18 = v16 + *a7;
      if ( v18 <= a5 )
      {
        memmove(Pool2, v12 + 16, v16);
        *a7 += v16;
        return v13;
      }
      if ( v18 <= a6 )
      {
        Mdl2 = (struct _MDL *)RxAllocateMdl2(Pool2, v16, 0, 0, 0);
        *a8 = Mdl2;
        if ( Mdl2 )
        {
          MmBuildMdlForNonPagedPool(Mdl2);
          v13 = -1073741802;
          *a9 = v16;
          return v13;
        }
        ExFreePoolWithTag(*(PVOID *)(a2 + 152), 0);
        *(_QWORD *)(a2 + 152) = 0;
        *(_DWORD *)(a2 + 148) = 0;
        return (unsigned int)-1073741670;
      }
      *a7 = a6;
LABEL_17:
      *(_DWORD *)(a1 + 48) = -1073741629;
      return v13;
    }
  }
  *a7 = a6;
  result = 0;
  *(_DWORD *)(a1 + 48) = -1073741629;
  return result;
}

```

## disassembly

```asm
0x1400133c4  push    rbx
0x1400133c6  push    rbp
0x1400133c7  push    rsi
0x1400133c8  push    rdi
0x1400133c9  push    r12
0x1400133cb  push    r13
0x1400133cd  push    r14
0x1400133cf  push    r15
0x1400133d1  sub     rsp, 38h
0x1400133d5  movzx   eax, byte ptr [r9]
0x1400133d9  lea     r15, [r9+3]
0x1400133dd  mov     rdi, [rsp+78h+arg_30]
0x1400133e5  xor     r12d, r12d
0x1400133e8  mov     ebp, [rsp+78h+arg_28]
0x1400133ef  mov     r11, r8
0x1400133f2  mov     rbx, rdx
0x1400133f5  mov     r13, rcx
0x1400133f8  lea     r15, [r15+rax*2]
0x1400133fc  mov     esi, r12d
0x1400133ff  add     dword ptr [rdi], 25h ; '%'
0x140013402  lea     r14d, [r12+1]
0x140013407  movzx   r10d, word ptr [r9+rax*2+1]
0x14001340d  movzx   eax, byte ptr [r9+3]
0x140013412  and     eax, r14d
0x140013415  mov     [rdx+20h], eax
0x140013418  mov     al, [r9+3]
0x14001341c  shr     al, 1
0x14001341e  and     al, r14b
0x140013421  mov     [rdx+70h], r12w
0x140013426  mov     [rdx+66h], al
0x140013429  mov     al, [r9+3]
0x14001342d  shr     al, 2
0x140013430  and     al, r14b
0x140013433  mov     [rdx+67h], al
0x140013436  mov     al, [r9+3]
0x14001343a  shr     al, 3
0x14001343d  and     al, r14b
0x140013440  mov     [rdx+68h], al
0x140013443  cmp     [rdx+80h], r12d
0x14001344a  jge     loc_140013591
0x140013450  lea     edx, [r12+10h]
0x140013455  cmp     r10w, dx
0x140013459  jb      loc_140013636
0x14001345f  mov     r14d, r10d
0x140013462  cmp     r10d, ebp
0x140013465  ja      loc_140013636
0x14001346b  mov     ecx, [rdi]
0x14001346d  lea     eax, [r10+rcx]
0x140013471  cmp     eax, ebp
0x140013473  ja      loc_140013636
0x140013479  mov     eax, [rsp+78h+arg_20]
0x140013480  add     rcx, rdx
0x140013483  cmp     rcx, rax
0x140013486  ja      loc_140013636
0x14001348c  movups  xmm0, xmmword ptr [r15]
0x140013490  movdqu  xmmword ptr [rbx+84h], xmm0
0x140013498  add     [rdi], edx
0x14001349a  cmp     [rbx+98h], r12
0x1400134a1  jnz     loc_14001358A
0x1400134a7  add     r14d, 0FFFFFFF0h
0x1400134ab  jz      loc_14001358A
0x1400134b1  mov     r8d, 64416D53h
0x1400134b7  mov     edx, r14d
0x1400134ba  mov     ecx, 42h ; 'B'
0x1400134bf  mov     r12d, r14d
0x1400134c2  call    cs:__imp_ExAllocatePool2
0x1400134c9  nop     dword ptr [rax+rax+00h]
0x1400134ce  mov     [rbx+98h], rax
0x1400134d5  mov     rcx, rax; void *
0x1400134d8  test    rax, rax
0x1400134db  jz      short loc_14001355B
0x1400134dd  mov     [rbx+94h], r14d
0x1400134e4  mov     edx, [rdi]
0x1400134e6  add     edx, r14d
0x1400134e9  cmp     edx, [rsp+78h+arg_20]
0x1400134f0  ja      short loc_140013506
0x1400134f2  lea     rdx, [r15+10h]; Src
0x1400134f6  mov     r8d, r12d; Size
0x1400134f9  call    memmove
0x1400134fe  add     [rdi], r14d
0x140013501  jmp     loc_14001358A
0x140013506  cmp     edx, ebp
0x140013508  ja      short loc_140013580
0x14001350a  xor     edi, edi
0x14001350c  xor     r9d, r9d
0x14001350f  xor     r8d, r8d
0x140013512  mov     [rsp+78h+var_58], rdi
0x140013517  mov     edx, r14d
0x14001351a  call    cs:__imp_RxAllocateMdl2
0x140013521  nop     dword ptr [rax+rax+00h]
0x140013526  mov     rcx, rax; MemoryDescriptorList
0x140013529  mov     rax, [rsp+78h+arg_38]
0x140013531  mov     [rax], rcx
0x140013534  test    rcx, rcx
0x140013537  jnz     short loc_140013562
0x140013539  mov     rcx, [rbx+98h]; P
0x140013540  xor     edx, edx; Tag
0x140013542  call    cs:__imp_ExFreePoolWithTag
0x140013549  nop     dword ptr [rax+rax+00h]
0x14001354e  mov     [rbx+98h], rdi
0x140013555  mov     [rbx+94h], edi
0x14001355b  mov     esi, 0C000009Ah
0x140013560  jmp     short loc_14001358A
0x140013562  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140013569  nop     dword ptr [rax+rax+00h]
0x14001356e  mov     rax, [rsp+78h+arg_40]
0x140013576  mov     esi, 0C0000016h
0x14001357b  mov     [rax], r14d
0x14001357e  jmp     short loc_14001358A
0x140013580  mov     [rdi], ebp
0x140013582  mov     dword ptr [r13+30h], 0C00000C3h
0x14001358a  mov     eax, esi
0x14001358c  jmp     loc_140013642
0x140013591  mov     r8d, [rsp+78h+arg_20]
0x140013599  mov     edx, r10d
0x14001359c  cmp     r10d, r8d
0x14001359f  ja      loc_140013636
0x1400135a5  mov     ecx, [rdi]
0x1400135a7  add     ecx, edx
0x1400135a9  cmp     ecx, r8d
0x1400135ac  ja      loc_140013636
0x1400135b2  mov     [rdi], ebp
0x1400135b4  mov     eax, [r9+10h]
0x1400135b8  mov     [rbx+18h], eax
0x1400135bb  cmp     [rbx+66h], r12b
0x1400135bf  jz      short loc_14001358A
0x1400135c1  lea     rcx, [r10+45h]
0x1400135c5  cmp     r8, rcx
0x1400135c8  jb      short loc_140013636
0x1400135ca  movzx   eax, byte ptr [r9+22h]
0x1400135cf  mov     [rbx+70h], ax
0x1400135d3  test    ax, ax
0x1400135d6  jz      short loc_14001358A
0x1400135d8  cmp     eax, 8
0x1400135db  jnz     short loc_140013582
0x1400135dd  cmp     r10d, eax
0x1400135e0  jb      short loc_140013582
0x1400135e2  mov     rax, [r15]
0x1400135e5  mov     [rbx+72h], rax
0x1400135e9  movzx   eax, word ptr [rbx+70h]
0x1400135ed  sub     edx, eax
0x1400135ef  test    edx, edx
0x1400135f1  jle     short loc_14001358A
0x1400135f3  sub     r10w, ax
0x1400135f7  mov     [r11], r10w
0x1400135fb  cmp     r10w, [r11+2]
0x140013600  ja      short loc_140013628
0x140013602  lea     rdx, [r15+rax]
0x140013606  test    r14b, r10b
0x140013609  jz      short loc_140013616
0x14001360b  inc     rdx; Src
0x14001360e  sub     r10w, r14w
0x140013612  mov     [r11], r10w
0x140013616  mov     rcx, [r11+8]; void *
0x14001361a  movzx   r8d, r10w; Size
0x14001361e  call    memmove
0x140013623  jmp     loc_14001358A
0x140013628  mov     [r11], r12w
0x14001362c  mov     esi, 80000005h
0x140013631  jmp     loc_14001358A
0x140013636  mov     [rdi], ebp
0x140013638  xor     eax, eax
0x14001363a  mov     dword ptr [r13+30h], 0C00000C3h
0x140013642  add     rsp, 38h
0x140013646  pop     r15
0x140013648  pop     r14
0x14001364a  pop     r13
0x14001364c  pop     r12
0x14001364e  pop     rdi
0x14001364f  pop     rsi
0x140013650  pop     rbp
0x140013651  pop     rbx
0x140013652  retn
```
