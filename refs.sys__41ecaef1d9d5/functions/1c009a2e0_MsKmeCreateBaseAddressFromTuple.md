# MsKmeCreateBaseAddressFromTuple

- ea: `0x1c009a2e0`
- end: `0x1c009a55b`
- name: `MsKmeCreateBaseAddressFromTuple`
- size: `635`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1c0068960`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c009a2e0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c009a47b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c009a47b`
- `ntoskrnl!IoAllocateMdl` at `0x1c009a369`
- `ntoskrnl!IoAllocateMdl` at `0x1c009a3d9`
- `ntoskrnl!IoAllocateMdl` at `0x1c009a369`
- `ntoskrnl!IoAllocateMdl` at `0x1c009a3d9`
- `ntoskrnl!MmProbeAndLockPages` at `0x1c009a394`
- `ntoskrnl!MmProbeAndLockPages` at `0x1c009a394`
- `ntoskrnl!IoFreeMdl` at `0x1c009a4e0`
- `ntoskrnl!IoFreeMdl` at `0x1c009a51e`
- `ntoskrnl!IoFreeMdl` at `0x1c009a4e0`
- `ntoskrnl!IoFreeMdl` at `0x1c009a51e`
- `ntoskrnl!MmUnlockPages` at `0x1c009a508`
- `ntoskrnl!MmUnlockPages` at `0x1c009a508`

## pseudocode

```c
__int64 __fastcall MsKmeCreateBaseAddressFromTuple(_QWORD *a1, struct _MDL **a2, char a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // r14
  struct _MDL *v5; // rsi
  unsigned int v6; // r13d
  ULONG v7; // r12d
  unsigned __int64 i; // rbx
  struct _MDL *Mdl; // rax
  struct _MDL *v10; // r14
  unsigned int v11; // ebx
  PMDL v12; // rax
  struct _MDL *v13; // r15
  const void **j; // r14
  size_t v15; // rbx
  PVOID v16; // rax
  unsigned int k; // r8d
  __int64 v18; // rdx
  unsigned int m; // r14d
  struct _MDL *v20; // rcx
  PMDL MemoryDescriptorList[8]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-38h] BYREF

  v4 = a4;
  v5 = 0;
  memset(MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v6 = 0;
  v7 = 0;
  for ( i = v4; i < v4 + 128 && *(_QWORD *)(i + 8); i += 32LL )
  {
    Mdl = IoAllocateMdl(*(PVOID *)i, *(_DWORD *)(i + 16), 0, 0, 0);
    v10 = Mdl;
    MemoryDescriptorList[2 * v6] = Mdl;
    if ( !Mdl )
      goto LABEL_5;
    MmProbeAndLockPages(Mdl, 0, IoReadAccess);
    MemoryDescriptorList[2 * v6 + 1] = v10 + 1;
    v7 += *(_DWORD *)(i + 16);
    ++v6;
    v4 = a4;
  }
  v12 = IoAllocateMdl(0, v7, 0, 0, 0);
  v5 = v12;
  if ( !v12 )
    goto LABEL_5;
  v12->Process = 0;
  v12->MappedSystemVa = 0;
  v13 = v12 + 1;
  for ( j = (const void **)MemoryDescriptorList; j < (const void **)&v27 && *j; j += 2 )
  {
    v15 = 8 * (((unsigned __int64)*((unsigned int *)*j + 10) + 4095) >> 12);
    memmove(v13, j[1], v15);
    v13 = (struct _MDL *)((char *)v13 + v15);
  }
  v5->MdlFlags |= 0x2002u;
  v16 = (v5->MdlFlags & 5) != 0
      ? v5->MappedSystemVa
      : MmMapLockedPagesSpecifyCache(v5, 0, MmCached, 0, 0, a3 != 0 ? 1073741840 : -1073741808);
  if ( !v16 )
  {
LABEL_5:
    v11 = -1073741670;
    goto LABEL_20;
  }
  *a2 = v5;
  *a1 = v16;
  v5 = 0;
  for ( k = 0; k < 4; ++k )
  {
    v18 = 2LL * k;
    *(_QWORD *)(32LL * k + a4 + 24) = MemoryDescriptorList[2 * k];
    MemoryDescriptorList[v18 + 1] = 0;
    MemoryDescriptorList[v18] = 0;
  }
  v11 = 0;
LABEL_20:
  if ( v5 )
    IoFreeMdl(v5);
  for ( m = 0; m < 4; ++m )
  {
    if ( MemoryDescriptorList[2 * m + 1] )
      MmUnlockPages(MemoryDescriptorList[2 * m]);
    v20 = MemoryDescriptorList[2 * m];
    if ( v20 )
      IoFreeMdl(v20);
  }
  return v11;
}

```

## disassembly

```asm
0x1c009a2e0  mov     [rsp+arg_10], rbx
0x1c009a2e5  push    rsi
0x1c009a2e6  push    r12
0x1c009a2e8  push    r13
0x1c009a2ea  push    r14
0x1c009a2ec  push    r15
0x1c009a2ee  sub     rsp, 0B0h
0x1c009a2f5  mov     rax, cs:__security_cookie
0x1c009a2fc  xor     rax, rsp
0x1c009a2ff  mov     [rsp+0D8h+var_38], rax
0x1c009a307  mov     r14, r9
0x1c009a30a  mov     [rsp+0D8h+var_A0], r9
0x1c009a30f  mov     [rsp+0D8h+var_A8], r8b
0x1c009a314  mov     [rsp+0D8h+var_90], rdx
0x1c009a319  mov     [rsp+0D8h+var_88], rcx
0x1c009a31e  xor     esi, esi
0x1c009a320  mov     [rsp+0D8h+var_98], rsi
0x1c009a325  xor     edx, edx; Val
0x1c009a327  lea     r8d, [rsi+40h]; Size
0x1c009a32b  lea     rcx, [rsp+0D8h+MemoryDescriptorList]; void *
0x1c009a330  call    memset
0x1c009a335  xor     r13d, r13d
0x1c009a338  xor     r12d, r12d
0x1c009a33b  mov     rbx, r14
0x1c009a33e  lea     rax, [r14+80h]
0x1c009a345  cmp     rbx, rax
0x1c009a348  jnb     short loc_1C009A3C8
0x1c009a34a  cmp     qword ptr [rbx+8], 0
0x1c009a34f  jz      short loc_1C009A3C8
0x1c009a351  mov     r15d, r13d
0x1c009a354  add     r15, r15
0x1c009a357  and     [rsp+0D8h+var_B8], 0
0x1c009a35d  xor     r9d, r9d; ChargeQuota
0x1c009a360  xor     r8d, r8d; SecondaryBuffer
0x1c009a363  mov     edx, [rbx+10h]; Length
0x1c009a366  mov     rcx, [rbx]; VirtualAddress
0x1c009a369  call    cs:__imp_IoAllocateMdl
0x1c009a370  nop     dword ptr [rax+rax+00h]
0x1c009a375  mov     r14, rax
0x1c009a378  mov     [rsp+r15*8+0D8h+MemoryDescriptorList], rax
0x1c009a37d  test    rax, rax
0x1c009a380  jnz     short loc_1C009A38C
0x1c009a382  mov     ebx, 0C000009Ah
0x1c009a387  jmp     loc_1C009A4D8
0x1c009a38c  xor     r8d, r8d; Operation
0x1c009a38f  xor     edx, edx; AccessMode
0x1c009a391  mov     rcx, r14; MemoryDescriptorList
0x1c009a394  call    cs:__imp_MmProbeAndLockPages
0x1c009a39b  nop     dword ptr [rax+rax+00h]
0x1c009a3a0  nop
0x1c009a3a1  lea     rax, [r14+30h]
0x1c009a3a5  mov     [rsp+r15*8+0D8h+var_70], rax
0x1c009a3aa  add     r12d, [rbx+10h]
0x1c009a3ae  inc     r13d
0x1c009a3b1  add     rbx, 20h ; ' '
0x1c009a3b5  mov     r14, [rsp+0D8h+var_A0]
0x1c009a3ba  jmp     short loc_1C009A33E
0x1c009a3bc  mov     ebx, eax
0x1c009a3be  mov     rsi, [rsp+0D8h+var_98]
0x1c009a3c3  jmp     loc_1C009A4D8
0x1c009a3c8  and     [rsp+0D8h+var_B8], 0
0x1c009a3ce  xor     r9d, r9d; ChargeQuota
0x1c009a3d1  xor     r8d, r8d; SecondaryBuffer
0x1c009a3d4  mov     edx, r12d; Length
0x1c009a3d7  xor     ecx, ecx; VirtualAddress
0x1c009a3d9  call    cs:__imp_IoAllocateMdl
0x1c009a3e0  nop     dword ptr [rax+rax+00h]
0x1c009a3e5  mov     rsi, rax
0x1c009a3e8  test    rax, rax
0x1c009a3eb  jz      short loc_1C009A382
0x1c009a3ed  and     qword ptr [rax+10h], 0
0x1c009a3f2  and     qword ptr [rax+18h], 0
0x1c009a3f7  lea     r15, [rax+30h]
0x1c009a3fb  lea     r14, [rsp+0D8h+MemoryDescriptorList]
0x1c009a400  lea     rax, [rsp+0D8h+var_38]
0x1c009a408  cmp     r14, rax
0x1c009a40b  jnb     short loc_1C009A43F
0x1c009a40d  mov     rax, [r14]
0x1c009a410  test    rax, rax
0x1c009a413  jz      short loc_1C009A43F
0x1c009a415  mov     ebx, [rax+28h]
0x1c009a418  add     rbx, 0FFFh
0x1c009a41f  shr     rbx, 0Ch
0x1c009a423  shl     rbx, 3
0x1c009a427  mov     r8, rbx; Size
0x1c009a42a  mov     rdx, [r14+8]; Src
0x1c009a42e  mov     rcx, r15; void *
0x1c009a431  call    memmove
0x1c009a436  add     r15, rbx
0x1c009a439  add     r14, 10h
0x1c009a43d  jmp     short loc_1C009A400
0x1c009a43f  mov     eax, 2002h
0x1c009a444  or      [rsi+0Ah], ax
0x1c009a448  movzx   eax, word ptr [rsi+0Ah]
0x1c009a44c  test    al, 5
0x1c009a44e  jz      short loc_1C009A456
0x1c009a450  mov     rax, [rsi+18h]
0x1c009a454  jmp     short loc_1C009A487
0x1c009a456  neg     [rsp+0D8h+var_A8]
0x1c009a45a  sbb     eax, eax
0x1c009a45c  and     eax, 80000000h
0x1c009a461  add     eax, 0C0000010h
0x1c009a466  mov     [rsp+0D8h+Priority], eax; Priority
0x1c009a46a  and     dword ptr [rsp+0D8h+var_B8], 0
0x1c009a46f  xor     r9d, r9d; RequestedAddress
0x1c009a472  xor     edx, edx; AccessMode
0x1c009a474  lea     r8d, [r9+1]; CacheType
0x1c009a478  mov     rcx, rsi; MemoryDescriptorList
0x1c009a47b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c009a482  nop     dword ptr [rax+rax+00h]
0x1c009a487  test    rax, rax
0x1c009a48a  jz      loc_1C009A382
0x1c009a490  mov     rcx, [rsp+0D8h+var_90]
0x1c009a495  mov     [rcx], rsi
0x1c009a498  mov     rcx, [rsp+0D8h+var_88]
0x1c009a49d  mov     [rcx], rax
0x1c009a4a0  xor     esi, esi
0x1c009a4a2  xor     r8d, r8d
0x1c009a4a5  mov     r9, [rsp+0D8h+var_A0]
0x1c009a4aa  cmp     r8d, 4
0x1c009a4ae  jnb     short loc_1C009A4D6
0x1c009a4b0  mov     ecx, r8d
0x1c009a4b3  mov     edx, r8d
0x1c009a4b6  add     rdx, rdx
0x1c009a4b9  shl     rcx, 5
0x1c009a4bd  mov     rax, [rsp+rdx*8+0D8h+MemoryDescriptorList]
0x1c009a4c2  mov     [rcx+r9+18h], rax
0x1c009a4c7  and     [rsp+rdx*8+0D8h+var_70], rsi
0x1c009a4cc  and     [rsp+rdx*8+0D8h+MemoryDescriptorList], rsi
0x1c009a4d1  inc     r8d
0x1c009a4d4  jmp     short loc_1C009A4AA
0x1c009a4d6  xor     ebx, ebx
0x1c009a4d8  test    rsi, rsi
0x1c009a4db  jz      short loc_1C009A4EC
0x1c009a4dd  mov     rcx, rsi; Mdl
0x1c009a4e0  call    cs:__imp_IoFreeMdl
0x1c009a4e7  nop     dword ptr [rax+rax+00h]
0x1c009a4ec  xor     r14d, r14d
0x1c009a4ef  cmp     r14d, 4
0x1c009a4f3  jnb     short loc_1C009A52F
0x1c009a4f5  mov     esi, r14d
0x1c009a4f8  add     rsi, rsi
0x1c009a4fb  cmp     [rsp+rsi*8+0D8h+var_70], 0
0x1c009a501  jz      short loc_1C009A514
0x1c009a503  mov     rcx, [rsp+rsi*8+0D8h+MemoryDescriptorList]; MemoryDescriptorList
0x1c009a508  call    cs:__imp_MmUnlockPages
0x1c009a50f  nop     dword ptr [rax+rax+00h]
0x1c009a514  mov     rcx, [rsp+rsi*8+0D8h+MemoryDescriptorList]; Mdl
0x1c009a519  test    rcx, rcx
0x1c009a51c  jz      short loc_1C009A52A
0x1c009a51e  call    cs:__imp_IoFreeMdl
0x1c009a525  nop     dword ptr [rax+rax+00h]
0x1c009a52a  inc     r14d
0x1c009a52d  jmp     short loc_1C009A4EF
0x1c009a52f  mov     eax, ebx
0x1c009a531  mov     rcx, [rsp+0D8h+var_38]
0x1c009a539  xor     rcx, rsp; StackCookie
0x1c009a53c  call    __security_check_cookie
0x1c009a541  mov     rbx, [rsp+0D8h+arg_10]
0x1c009a549  add     rsp, 0B0h
0x1c009a550  pop     r15
0x1c009a552  pop     r14
0x1c009a554  pop     r13
0x1c009a556  pop     r12
0x1c009a558  pop     rsi
0x1c009a559  retn
```
