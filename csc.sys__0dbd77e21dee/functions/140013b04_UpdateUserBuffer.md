# UpdateUserBuffer

- ea: `0x140013b04`
- end: `0x140013ee6`
- name: `UpdateUserBuffer`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140015c84`

## callees

- `0x140013b04`
- `0x14002f140`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140013be2`
- `ntoskrnl!IoAllocateMdl` at `0x140013be2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013c5e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013d4c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013e28`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013c5e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013d4c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013e28`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x140013b97`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x140013b97`
- `ntoskrnl!MmProbeAndLockPages` at `0x140013c06`
- `ntoskrnl!MmProbeAndLockPages` at `0x140013c06`

## pseudocode

```c
__int64 __fastcall UpdateUserBuffer(__int64 a1, __int64 a2, unsigned int *a3, unsigned int *a4)
{
  unsigned int *v4; // r13
  char v8; // bl
  ULONG_PTR v9; // r8
  unsigned int v10; // edx
  int v11; // eax
  struct _MDL *v12; // rsi
  struct _MDL *Mdl; // rax
  unsigned int v14; // edx
  __int64 v15; // rbx
  PVOID v16; // rax
  __int64 v18; // rcx
  void *v19; // r9
  ULONG v20; // r12d
  ULONG ByteCount; // r13d
  PVOID MappedSystemVa; // rax
  __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned int i; // r12d
  __int64 v26; // r10
  __int64 v27; // r9
  unsigned int v28; // ecx
  unsigned int v29; // eax
  __int64 v30; // rbx
  unsigned int v31; // ebx
  unsigned int v32; // eax
  ULONG_PTR RegionSize; // [rsp+68h] [rbp+10h] BYREF
  unsigned int *v35; // [rsp+78h] [rbp+20h]

  v35 = a4;
  v4 = a4;
  v8 = 0;
  v9 = *(unsigned int *)(a2 + 176);
  if ( (unsigned int)v9 > 0x100 )
  {
    v10 = *(_DWORD *)(a2 + 164);
    if ( v10 <= 5 && ((*(_DWORD *)(a1 + 16) & 1) != 0 || v10 == 1) )
      v8 = 1;
  }
  if ( !v8 && ((unsigned int)v9 > *a4 || *(_DWORD *)(a2 + 164) > 1u) )
  {
    RegionSize = v9;
    *(_QWORD *)(a2 + 152) = -1;
    if ( ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, (PVOID *)(a2 + 136), 0, &RegionSize, 0x1000u, 4u) < 0 )
      return 3221225626LL;
    *(_DWORD *)(a2 + 20) |= 4u;
  }
  v11 = *(_DWORD *)(a2 + 20);
  v12 = *(struct _MDL **)(a2 + 168);
  if ( v8 )
  {
    if ( (v11 & 2) != 0 )
      goto LABEL_15;
    Mdl = IoAllocateMdl(v12, *(_DWORD *)(a2 + 176), 0, 0, 0);
    *(_QWORD *)(a2 + 144) = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 1, IoReadAccess);
      v12 = *(struct _MDL **)(a2 + 144);
      v11 = *(_DWORD *)(a2 + 20) | 8;
LABEL_15:
      *(_DWORD *)(a2 + 20) = v11 | 0x10;
      *(_DWORD *)(a2 + 48) = 0;
      v14 = 0;
      while ( v12 )
      {
        v15 = v14;
        *(_DWORD *)(a2 + 16LL * v14 + 56) = v12->ByteCount;
        v16 = MmMapLockedPagesSpecifyCache(v12, 1, MmCached, 0, 0, 0x40000010u);
        *(_QWORD *)(a2 + 16 * (v15 + 4)) = v16;
        if ( !v16 )
          return 3221225626LL;
        v14 = ++*(_DWORD *)(a2 + 48);
        v12 = v12->Next;
      }
      if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
      {
        v18 = a3[1];
        *a3 = v18 + v14;
        memmove((void *)(*((_QWORD *)a3 + 1) + 16 * v18), (const void *)(a2 + 56), 16LL * *(unsigned int *)(a2 + 48));
      }
      else
      {
        *(_QWORD *)a3 = *(_QWORD *)(a2 + 64);
      }
      *v35 = *(_DWORD *)(a2 + 176);
      return 0;
    }
    return 3221225626LL;
  }
  v19 = *(void **)(a2 + 136);
  RegionSize = (ULONG_PTR)v19;
  if ( v19 )
  {
    v20 = *(_DWORD *)(a2 + 176);
    if ( (v11 & 2) != 0 )
    {
      while ( v12 && v20 )
      {
        ByteCount = v12->ByteCount;
        if ( v20 < ByteCount )
          ByteCount = v20;
        if ( (v12->MdlFlags & 5) != 0 )
        {
          MappedSystemVa = v12->MappedSystemVa;
        }
        else
        {
          MappedSystemVa = MmMapLockedPagesSpecifyCache(v12, 0, MmCached, 0, 0, 0x40000010u);
          v19 = (void *)RegionSize;
        }
        if ( !MappedSystemVa )
          return 3221225626LL;
        memmove(v19, MappedSystemVa, ByteCount);
        v19 = (void *)(ByteCount + RegionSize);
        RegionSize = (ULONG_PTR)v19;
        v20 -= ByteCount;
        v12 = v12->Next;
      }
      v4 = v35;
    }
    else
    {
      memmove(v19, v12, *(unsigned int *)(a2 + 176));
    }
    if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
    {
      v23 = a3[1];
      *a3 = v23 + 1;
      *(_DWORD *)(*((_QWORD *)a3 + 1) + 16 * v23) = *(_DWORD *)(a2 + 176);
      *(_QWORD *)(*((_QWORD *)a3 + 1) + 16LL * a3[1] + 8) = *(_QWORD *)(a2 + 136);
    }
    else
    {
      *(_QWORD *)a3 = *(_QWORD *)(a2 + 136);
    }
    *v4 = *(_DWORD *)(a2 + 176);
    return 0;
  }
  if ( (v11 & 2) != 0 )
  {
    v12 = (struct _MDL *)((v12->MdlFlags & 5) != 0
                        ? v12->MappedSystemVa
                        : MmMapLockedPagesSpecifyCache(v12, 0, MmCached, 0, 0, 0x40000010u));
    if ( !v12 )
      return 3221225626LL;
  }
  if ( (*(_DWORD *)(a1 + 16) & 1) != 0 )
  {
    v24 = a3[1];
    *a3 = v24;
    for ( i = *(_DWORD *)(a2 + 176); i; i -= v30 )
    {
      v26 = 2LL * v24;
      v27 = *((_QWORD *)a3 + 1);
      v28 = *(_DWORD *)(v27 + 16LL * v24);
      v29 = i;
      if ( i >= v28 )
        v29 = v28;
      v30 = v29;
      memmove(*(void **)(v27 + 8 * v26 + 8), v12, v29);
      *(_DWORD *)(*((_QWORD *)a3 + 1) + 16LL * *a3) = v30;
      v12 = (struct _MDL *)((char *)v12 + v30);
      v24 = ++*a3;
    }
    v31 = *(_DWORD *)(a2 + 176);
  }
  else
  {
    v32 = *(_DWORD *)(a2 + 176);
    if ( v32 >= *v4 )
      v32 = *v4;
    v31 = v32;
    memmove(*(void **)a3, v12, v32);
  }
  *v4 = v31;
  return 0;
}

```

## disassembly

```asm
0x140013b04  mov     [rsp+arg_10], rbx
0x140013b09  mov     [rsp+arg_18], r9
0x140013b0e  mov     [rsp+arg_0], rcx
0x140013b13  push    rsi
0x140013b14  push    rdi
0x140013b15  push    r12
0x140013b17  push    r13
0x140013b19  push    r15
0x140013b1b  sub     rsp, 30h
0x140013b1f  mov     r13, r9
0x140013b22  mov     r15, r8
0x140013b25  mov     rdi, rdx
0x140013b28  mov     r12, rcx
0x140013b2b  xor     bl, bl
0x140013b2d  mov     r8d, [rdx+0B0h]
0x140013b34  cmp     r8d, 100h
0x140013b3b  jbe     short loc_140013B56
0x140013b3d  mov     edx, [rdx+0A4h]
0x140013b43  cmp     edx, 5
0x140013b46  ja      short loc_140013B56
0x140013b48  mov     eax, [rcx+10h]
0x140013b4b  test    al, 1
0x140013b4d  jnz     short loc_140013B54
0x140013b4f  cmp     edx, 1
0x140013b52  jnz     short loc_140013B56
0x140013b54  mov     bl, 1
0x140013b56  test    bl, bl
0x140013b58  jnz     short loc_140013BAF
0x140013b5a  cmp     r8d, [r9]
0x140013b5d  ja      short loc_140013B68
0x140013b5f  cmp     dword ptr [rdi+0A4h], 1
0x140013b66  jbe     short loc_140013BAF
0x140013b68  mov     [rsp+58h+RegionSize], r8
0x140013b6d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140013b71  mov     [rdi+98h], rcx
0x140013b78  lea     rdx, [rdi+88h]; BaseAddress
0x140013b7f  mov     [rsp+58h+Protect], 4; Protect
0x140013b87  mov     [rsp+58h+AllocationType], 1000h; AllocationType
0x140013b8f  lea     r9, [rsp+58h+RegionSize]; RegionSize
0x140013b94  xor     r8d, r8d; ZeroBits
0x140013b97  call    cs:__imp_ZwAllocateVirtualMemory
0x140013b9e  nop     dword ptr [rax+rax+00h]
0x140013ba3  test    eax, eax
0x140013ba5  js      loc_140013E3C
0x140013bab  or      dword ptr [rdi+14h], 4
0x140013baf  mov     eax, [rdi+14h]
0x140013bb2  mov     ecx, eax
0x140013bb4  and     ecx, 2
0x140013bb7  mov     rsi, [rdi+0A8h]
0x140013bbe  test    bl, bl
0x140013bc0  jz      loc_140013CE3
0x140013bc6  test    ecx, ecx
0x140013bc8  jnz     short loc_140013C1F
0x140013bca  mov     qword ptr [rsp+58h+AllocationType], 0; Irp
0x140013bd3  xor     r9d, r9d; ChargeQuota
0x140013bd6  xor     r8d, r8d; SecondaryBuffer
0x140013bd9  mov     edx, [rdi+0B0h]; Length
0x140013bdf  mov     rcx, rsi; VirtualAddress
0x140013be2  call    cs:__imp_IoAllocateMdl
0x140013be9  nop     dword ptr [rax+rax+00h]
0x140013bee  mov     [rdi+90h], rax
0x140013bf5  test    rax, rax
0x140013bf8  jz      loc_140013E3C
0x140013bfe  xor     r8d, r8d; Operation
0x140013c01  mov     dl, 1; AccessMode
0x140013c03  mov     rcx, rax; MemoryDescriptorList
0x140013c06  call    cs:__imp_MmProbeAndLockPages
0x140013c0d  nop     dword ptr [rax+rax+00h]
0x140013c12  mov     rsi, [rdi+90h]
0x140013c19  mov     eax, [rdi+14h]
0x140013c1c  or      eax, 8
0x140013c1f  or      eax, 10h
0x140013c22  mov     [rdi+14h], eax
0x140013c25  mov     dword ptr [rdi+30h], 0
0x140013c2c  xor     edx, edx
0x140013c2e  test    rsi, rsi
0x140013c31  jz      short loc_140013C8F
0x140013c33  mov     ebx, edx
0x140013c35  mov     ecx, edx
0x140013c37  add     rcx, rcx
0x140013c3a  mov     eax, [rsi+28h]
0x140013c3d  mov     [rdi+rcx*8+38h], eax
0x140013c41  mov     [rsp+58h+Protect], 40000010h; Priority
0x140013c49  mov     [rsp+58h+AllocationType], 0; BugCheckOnFailure
0x140013c51  xor     r9d, r9d; RequestedAddress
0x140013c54  lea     r8d, [r9+1]; CacheType
0x140013c58  mov     dl, r8b; AccessMode
0x140013c5b  mov     rcx, rsi; MemoryDescriptorList
0x140013c5e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140013c65  nop     dword ptr [rax+rax+00h]
0x140013c6a  lea     rcx, [rbx+4]
0x140013c6e  add     rcx, rcx
0x140013c71  mov     [rdi+rcx*8], rax
0x140013c75  test    rax, rax
0x140013c78  jnz     short loc_140013C84
0x140013c7a  mov     eax, 0C000009Ah
0x140013c7f  jmp     loc_140013ED3
0x140013c84  inc     dword ptr [rdi+30h]
0x140013c87  mov     edx, [rdi+30h]
0x140013c8a  mov     rsi, [rsi]
0x140013c8d  jmp     short loc_140013C2E
0x140013c8f  mov     rax, [rsp+58h+arg_0]
0x140013c94  mov     eax, [rax+10h]
0x140013c97  test    al, 1
0x140013c99  jz      short loc_140013CC0
0x140013c9b  mov     ecx, [r15+4]
0x140013c9f  lea     eax, [rcx+rdx]
0x140013ca2  mov     [r15], eax
0x140013ca5  mov     r8d, [rdi+30h]
0x140013ca9  shl     r8, 4; Size
0x140013cad  lea     rdx, [rdi+38h]; Src
0x140013cb1  shl     rcx, 4
0x140013cb5  add     rcx, [r15+8]; void *
0x140013cb9  call    memmove
0x140013cbe  jmp     short loc_140013CC7
0x140013cc0  mov     rax, [rdi+40h]
0x140013cc4  mov     [r15], rax
0x140013cc7  mov     eax, [rdi+0B0h]
0x140013ccd  mov     rcx, [rsp+58h+arg_18]
0x140013cd2  mov     [rcx], eax
0x140013cd4  jmp     loc_140013ED1
0x140013cd9  mov     eax, 0C000009Ah
0x140013cde  jmp     loc_140013ED3
0x140013ce3  mov     r9, [rdi+88h]
0x140013cea  mov     [rsp+58h+RegionSize], r9
0x140013cef  test    r9, r9
0x140013cf2  jz      loc_140013DFC
0x140013cf8  mov     r12d, [rdi+0B0h]
0x140013cff  test    ecx, ecx
0x140013d01  jz      loc_140013D8F
0x140013d07  test    rsi, rsi
0x140013d0a  jz      loc_140013D9F
0x140013d10  test    r12d, r12d
0x140013d13  jz      loc_140013D9F
0x140013d19  mov     r13d, [rsi+28h]
0x140013d1d  cmp     r12d, r13d
0x140013d20  cmovb   r13d, r12d
0x140013d24  test    byte ptr [rsi+0Ah], 5
0x140013d28  jz      short loc_140013D30
0x140013d2a  mov     rax, [rsi+18h]
0x140013d2e  jmp     short loc_140013D5D
0x140013d30  mov     [rsp+58h+Protect], 40000010h; Priority
0x140013d38  mov     [rsp+58h+AllocationType], 0; BugCheckOnFailure
0x140013d40  xor     r9d, r9d; RequestedAddress
0x140013d43  xor     edx, edx; AccessMode
0x140013d45  lea     r8d, [r9+1]; CacheType
0x140013d49  mov     rcx, rsi; MemoryDescriptorList
0x140013d4c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140013d53  nop     dword ptr [rax+rax+00h]
0x140013d58  mov     r9, [rsp+58h+RegionSize]
0x140013d5d  test    rax, rax
0x140013d60  jz      loc_140013E3C
0x140013d66  mov     ebx, r13d
0x140013d69  mov     r8d, r13d; Size
0x140013d6c  mov     rdx, rax; Src
0x140013d6f  mov     rcx, r9; void *
0x140013d72  call    memmove
0x140013d77  mov     r9, [rsp+58h+RegionSize]
0x140013d7c  add     r9, rbx
0x140013d7f  mov     [rsp+58h+RegionSize], r9
0x140013d84  sub     r12d, r13d
0x140013d87  mov     rsi, [rsi]
0x140013d8a  jmp     loc_140013D07
0x140013d8f  mov     r8, r12; Size
0x140013d92  mov     rdx, rsi; Src
0x140013d95  mov     rcx, r9; void *
0x140013d98  call    memmove
0x140013d9d  jmp     short loc_140013DA4
0x140013d9f  mov     r13, [rsp+58h+arg_18]
0x140013da4  mov     rax, [rsp+58h+arg_0]
0x140013da9  mov     eax, [rax+10h]
0x140013dac  test    al, 1
0x140013dae  jz      short loc_140013DE3
0x140013db0  mov     edx, [r15+4]
0x140013db4  lea     eax, [rdx+1]
0x140013db7  mov     [r15], eax
0x140013dba  add     rdx, rdx
0x140013dbd  mov     rcx, [r15+8]
0x140013dc1  mov     eax, [rdi+0B0h]
0x140013dc7  mov     [rcx+rdx*8], eax
0x140013dca  mov     edx, [r15+4]
0x140013dce  add     rdx, rdx
0x140013dd1  mov     rcx, [r15+8]
0x140013dd5  mov     rax, [rdi+88h]
0x140013ddc  mov     [rcx+rdx*8+8], rax
0x140013de1  jmp     short loc_140013DED
0x140013de3  mov     rax, [rdi+88h]
0x140013dea  mov     [r15], rax
0x140013ded  mov     eax, [rdi+0B0h]
0x140013df3  mov     [r13+0], eax
0x140013df7  jmp     loc_140013ED1
0x140013dfc  test    ecx, ecx
0x140013dfe  jz      short loc_140013E46
0x140013e00  test    byte ptr [rsi+0Ah], 5
0x140013e04  jz      short loc_140013E0C
0x140013e06  mov     rsi, [rsi+18h]
0x140013e0a  jmp     short loc_140013E37
0x140013e0c  mov     [rsp+58h+Protect], 40000010h; Priority
0x140013e14  mov     [rsp+58h+AllocationType], 0; BugCheckOnFailure
0x140013e1c  xor     r9d, r9d; RequestedAddress
0x140013e1f  xor     edx, edx; AccessMode
0x140013e21  lea     r8d, [r9+1]; CacheType
0x140013e25  mov     rcx, rsi; MemoryDescriptorList
0x140013e28  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140013e2f  nop     dword ptr [rax+rax+00h]
0x140013e34  mov     rsi, rax
0x140013e37  test    rsi, rsi
0x140013e3a  jnz     short loc_140013E46
0x140013e3c  mov     eax, 0C000009Ah
0x140013e41  jmp     loc_140013ED3
0x140013e46  mov     eax, [r12+10h]
0x140013e4b  test    al, 1
0x140013e4d  jz      short loc_140013EAE
0x140013e4f  mov     eax, [r15+4]
0x140013e53  mov     [r15], eax
0x140013e56  mov     r12d, [rdi+0B0h]
0x140013e5d  test    r12d, r12d
0x140013e60  jz      short loc_140013EA6
0x140013e62  mov     r10d, eax
0x140013e65  add     r10, r10
0x140013e68  mov     r9, [r15+8]
0x140013e6c  mov     ecx, [r9+r10*8]
0x140013e70  mov     eax, r12d
0x140013e73  cmp     r12d, ecx
0x140013e76  cmovnb  eax, ecx
0x140013e79  mov     ebx, eax
0x140013e7b  mov     r8d, eax; Size
0x140013e7e  mov     rdx, rsi; Src
0x140013e81  mov     rcx, [r9+r10*8+8]; void *
0x140013e86  call    memmove
0x140013e8b  mov     ecx, [r15]
0x140013e8e  add     rcx, rcx
0x140013e91  mov     rax, [r15+8]
0x140013e95  mov     [rax+rcx*8], ebx
0x140013e98  add     rsi, rbx
0x140013e9b  inc     dword ptr [r15]
0x140013e9e  mov     eax, [r15]
0x140013ea1  sub     r12d, ebx
0x140013ea4  jnz     short loc_140013E62
0x140013ea6  mov     ebx, [rdi+0B0h]
0x140013eac  jmp     short loc_140013ECD
0x140013eae  mov     ecx, [r13+0]
0x140013eb2  mov     eax, [rdi+0B0h]
0x140013eb8  cmp     eax, ecx
0x140013eba  cmovnb  eax, ecx
0x140013ebd  mov     ebx, eax
0x140013ebf  mov     r8d, eax; Size
0x140013ec2  mov     rdx, rsi; Src
0x140013ec5  mov     rcx, [r15]; void *
0x140013ec8  call    memmove
0x140013ecd  mov     [r13+0], ebx
0x140013ed1  xor     eax, eax
0x140013ed3  mov     rbx, [rsp+58h+arg_10]
0x140013ed8  add     rsp, 30h
0x140013edc  pop     r15
0x140013ede  pop     r13
0x140013ee0  pop     r12
0x140013ee2  pop     rdi
0x140013ee3  pop     rsi
0x140013ee4  retn
```
