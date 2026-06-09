# UpdateUserBuffer

- ea: `0x14003a5b8`
- end: `0x14003a99a`
- name: `UpdateUserBuffer`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14003a2dc`

## callees

- `0x14003a5b8`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003a712`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003a800`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003a8dc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003a712`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003a800`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003a8dc`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x14003a64b`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x14003a64b`
- `ntoskrnl!IoAllocateMdl` at `0x14003a696`
- `ntoskrnl!IoAllocateMdl` at `0x14003a696`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003a6ba`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003a6ba`

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
0x14003a5b8  mov     [rsp+arg_10], rbx
0x14003a5bd  mov     [rsp+arg_18], r9
0x14003a5c2  mov     [rsp+arg_0], rcx
0x14003a5c7  push    rsi
0x14003a5c8  push    rdi
0x14003a5c9  push    r12
0x14003a5cb  push    r13
0x14003a5cd  push    r15
0x14003a5cf  sub     rsp, 30h
0x14003a5d3  mov     r13, r9
0x14003a5d6  mov     r15, r8
0x14003a5d9  mov     rdi, rdx
0x14003a5dc  mov     r12, rcx
0x14003a5df  xor     bl, bl
0x14003a5e1  mov     r8d, [rdx+0B0h]
0x14003a5e8  cmp     r8d, 100h
0x14003a5ef  jbe     short loc_14003A60A
0x14003a5f1  mov     edx, [rdx+0A4h]
0x14003a5f7  cmp     edx, 5
0x14003a5fa  ja      short loc_14003A60A
0x14003a5fc  mov     eax, [rcx+10h]
0x14003a5ff  test    al, 1
0x14003a601  jnz     short loc_14003A608
0x14003a603  cmp     edx, 1
0x14003a606  jnz     short loc_14003A60A
0x14003a608  mov     bl, 1
0x14003a60a  test    bl, bl
0x14003a60c  jnz     short loc_14003A663
0x14003a60e  cmp     r8d, [r9]
0x14003a611  ja      short loc_14003A61C
0x14003a613  cmp     dword ptr [rdi+0A4h], 1
0x14003a61a  jbe     short loc_14003A663
0x14003a61c  mov     [rsp+58h+RegionSize], r8
0x14003a621  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003a625  mov     [rdi+98h], rcx
0x14003a62c  lea     rdx, [rdi+88h]; BaseAddress
0x14003a633  mov     [rsp+58h+Protect], 4; Protect
0x14003a63b  mov     [rsp+58h+AllocationType], 1000h; AllocationType
0x14003a643  lea     r9, [rsp+58h+RegionSize]; RegionSize
0x14003a648  xor     r8d, r8d; ZeroBits
0x14003a64b  call    cs:__imp_ZwAllocateVirtualMemory
0x14003a652  nop     dword ptr [rax+rax+00h]
0x14003a657  test    eax, eax
0x14003a659  js      loc_14003A8F0
0x14003a65f  or      dword ptr [rdi+14h], 4
0x14003a663  mov     eax, [rdi+14h]
0x14003a666  mov     ecx, eax
0x14003a668  and     ecx, 2
0x14003a66b  mov     rsi, [rdi+0A8h]
0x14003a672  test    bl, bl
0x14003a674  jz      loc_14003A797
0x14003a67a  test    ecx, ecx
0x14003a67c  jnz     short loc_14003A6D3
0x14003a67e  mov     qword ptr [rsp+58h+AllocationType], 0; Irp
0x14003a687  xor     r9d, r9d; ChargeQuota
0x14003a68a  xor     r8d, r8d; SecondaryBuffer
0x14003a68d  mov     edx, [rdi+0B0h]; Length
0x14003a693  mov     rcx, rsi; VirtualAddress
0x14003a696  call    cs:__imp_IoAllocateMdl
0x14003a69d  nop     dword ptr [rax+rax+00h]
0x14003a6a2  mov     [rdi+90h], rax
0x14003a6a9  test    rax, rax
0x14003a6ac  jz      loc_14003A8F0
0x14003a6b2  xor     r8d, r8d; Operation
0x14003a6b5  mov     dl, 1; AccessMode
0x14003a6b7  mov     rcx, rax; MemoryDescriptorList
0x14003a6ba  call    cs:__imp_MmProbeAndLockPages
0x14003a6c1  nop     dword ptr [rax+rax+00h]
0x14003a6c6  mov     rsi, [rdi+90h]
0x14003a6cd  mov     eax, [rdi+14h]
0x14003a6d0  or      eax, 8
0x14003a6d3  or      eax, 10h
0x14003a6d6  mov     [rdi+14h], eax
0x14003a6d9  mov     dword ptr [rdi+30h], 0
0x14003a6e0  xor     edx, edx
0x14003a6e2  test    rsi, rsi
0x14003a6e5  jz      short loc_14003A743
0x14003a6e7  mov     ebx, edx
0x14003a6e9  mov     ecx, edx
0x14003a6eb  add     rcx, rcx
0x14003a6ee  mov     eax, [rsi+28h]
0x14003a6f1  mov     [rdi+rcx*8+38h], eax
0x14003a6f5  mov     [rsp+58h+Protect], 40000010h; Priority
0x14003a6fd  mov     [rsp+58h+AllocationType], 0; BugCheckOnFailure
0x14003a705  xor     r9d, r9d; RequestedAddress
0x14003a708  lea     r8d, [r9+1]; CacheType
0x14003a70c  mov     dl, r8b; AccessMode
0x14003a70f  mov     rcx, rsi; MemoryDescriptorList
0x14003a712  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003a719  nop     dword ptr [rax+rax+00h]
0x14003a71e  lea     rcx, [rbx+4]
0x14003a722  add     rcx, rcx
0x14003a725  mov     [rdi+rcx*8], rax
0x14003a729  test    rax, rax
0x14003a72c  jnz     short loc_14003A738
0x14003a72e  mov     eax, 0C000009Ah
0x14003a733  jmp     loc_14003A987
0x14003a738  inc     dword ptr [rdi+30h]
0x14003a73b  mov     edx, [rdi+30h]
0x14003a73e  mov     rsi, [rsi]
0x14003a741  jmp     short loc_14003A6E2
0x14003a743  mov     rax, [rsp+58h+arg_0]
0x14003a748  mov     eax, [rax+10h]
0x14003a74b  test    al, 1
0x14003a74d  jz      short loc_14003A774
0x14003a74f  mov     ecx, [r15+4]
0x14003a753  lea     eax, [rcx+rdx]
0x14003a756  mov     [r15], eax
0x14003a759  mov     r8d, [rdi+30h]
0x14003a75d  shl     r8, 4; Size
0x14003a761  lea     rdx, [rdi+38h]; Src
0x14003a765  shl     rcx, 4
0x14003a769  add     rcx, [r15+8]; void *
0x14003a76d  call    memmove
0x14003a772  jmp     short loc_14003A77B
0x14003a774  mov     rax, [rdi+40h]
0x14003a778  mov     [r15], rax
0x14003a77b  mov     eax, [rdi+0B0h]
0x14003a781  mov     rcx, [rsp+58h+arg_18]
0x14003a786  mov     [rcx], eax
0x14003a788  jmp     loc_14003A985
0x14003a78d  mov     eax, 0C000009Ah
0x14003a792  jmp     loc_14003A987
0x14003a797  mov     r9, [rdi+88h]
0x14003a79e  mov     [rsp+58h+RegionSize], r9
0x14003a7a3  test    r9, r9
0x14003a7a6  jz      loc_14003A8B0
0x14003a7ac  mov     r12d, [rdi+0B0h]
0x14003a7b3  test    ecx, ecx
0x14003a7b5  jz      loc_14003A843
0x14003a7bb  test    rsi, rsi
0x14003a7be  jz      loc_14003A853
0x14003a7c4  test    r12d, r12d
0x14003a7c7  jz      loc_14003A853
0x14003a7cd  mov     r13d, [rsi+28h]
0x14003a7d1  cmp     r12d, r13d
0x14003a7d4  cmovb   r13d, r12d
0x14003a7d8  test    byte ptr [rsi+0Ah], 5
0x14003a7dc  jz      short loc_14003A7E4
0x14003a7de  mov     rax, [rsi+18h]
0x14003a7e2  jmp     short loc_14003A811
0x14003a7e4  mov     [rsp+58h+Protect], 40000010h; Priority
0x14003a7ec  mov     [rsp+58h+AllocationType], 0; BugCheckOnFailure
0x14003a7f4  xor     r9d, r9d; RequestedAddress
0x14003a7f7  xor     edx, edx; AccessMode
0x14003a7f9  lea     r8d, [r9+1]; CacheType
0x14003a7fd  mov     rcx, rsi; MemoryDescriptorList
0x14003a800  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003a807  nop     dword ptr [rax+rax+00h]
0x14003a80c  mov     r9, [rsp+58h+RegionSize]
0x14003a811  test    rax, rax
0x14003a814  jz      loc_14003A8F0
0x14003a81a  mov     ebx, r13d
0x14003a81d  mov     r8d, r13d; Size
0x14003a820  mov     rdx, rax; Src
0x14003a823  mov     rcx, r9; void *
0x14003a826  call    memmove
0x14003a82b  mov     r9, [rsp+58h+RegionSize]
0x14003a830  add     r9, rbx
0x14003a833  mov     [rsp+58h+RegionSize], r9
0x14003a838  sub     r12d, r13d
0x14003a83b  mov     rsi, [rsi]
0x14003a83e  jmp     loc_14003A7BB
0x14003a843  mov     r8, r12; Size
0x14003a846  mov     rdx, rsi; Src
0x14003a849  mov     rcx, r9; void *
0x14003a84c  call    memmove
0x14003a851  jmp     short loc_14003A858
0x14003a853  mov     r13, [rsp+58h+arg_18]
0x14003a858  mov     rax, [rsp+58h+arg_0]
0x14003a85d  mov     eax, [rax+10h]
0x14003a860  test    al, 1
0x14003a862  jz      short loc_14003A897
0x14003a864  mov     edx, [r15+4]
0x14003a868  lea     eax, [rdx+1]
0x14003a86b  mov     [r15], eax
0x14003a86e  add     rdx, rdx
0x14003a871  mov     rcx, [r15+8]
0x14003a875  mov     eax, [rdi+0B0h]
0x14003a87b  mov     [rcx+rdx*8], eax
0x14003a87e  mov     edx, [r15+4]
0x14003a882  add     rdx, rdx
0x14003a885  mov     rcx, [r15+8]
0x14003a889  mov     rax, [rdi+88h]
0x14003a890  mov     [rcx+rdx*8+8], rax
0x14003a895  jmp     short loc_14003A8A1
0x14003a897  mov     rax, [rdi+88h]
0x14003a89e  mov     [r15], rax
0x14003a8a1  mov     eax, [rdi+0B0h]
0x14003a8a7  mov     [r13+0], eax
0x14003a8ab  jmp     loc_14003A985
0x14003a8b0  test    ecx, ecx
0x14003a8b2  jz      short loc_14003A8FA
0x14003a8b4  test    byte ptr [rsi+0Ah], 5
0x14003a8b8  jz      short loc_14003A8C0
0x14003a8ba  mov     rsi, [rsi+18h]
0x14003a8be  jmp     short loc_14003A8EB
0x14003a8c0  mov     [rsp+58h+Protect], 40000010h; Priority
0x14003a8c8  mov     [rsp+58h+AllocationType], 0; BugCheckOnFailure
0x14003a8d0  xor     r9d, r9d; RequestedAddress
0x14003a8d3  xor     edx, edx; AccessMode
0x14003a8d5  lea     r8d, [r9+1]; CacheType
0x14003a8d9  mov     rcx, rsi; MemoryDescriptorList
0x14003a8dc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003a8e3  nop     dword ptr [rax+rax+00h]
0x14003a8e8  mov     rsi, rax
0x14003a8eb  test    rsi, rsi
0x14003a8ee  jnz     short loc_14003A8FA
0x14003a8f0  mov     eax, 0C000009Ah
0x14003a8f5  jmp     loc_14003A987
0x14003a8fa  mov     eax, [r12+10h]
0x14003a8ff  test    al, 1
0x14003a901  jz      short loc_14003A962
0x14003a903  mov     eax, [r15+4]
0x14003a907  mov     [r15], eax
0x14003a90a  mov     r12d, [rdi+0B0h]
0x14003a911  test    r12d, r12d
0x14003a914  jz      short loc_14003A95A
0x14003a916  mov     r10d, eax
0x14003a919  add     r10, r10
0x14003a91c  mov     r9, [r15+8]
0x14003a920  mov     ecx, [r9+r10*8]
0x14003a924  mov     eax, r12d
0x14003a927  cmp     r12d, ecx
0x14003a92a  cmovnb  eax, ecx
0x14003a92d  mov     ebx, eax
0x14003a92f  mov     r8d, eax; Size
0x14003a932  mov     rdx, rsi; Src
0x14003a935  mov     rcx, [r9+r10*8+8]; void *
0x14003a93a  call    memmove
0x14003a93f  mov     ecx, [r15]
0x14003a942  add     rcx, rcx
0x14003a945  mov     rax, [r15+8]
0x14003a949  mov     [rax+rcx*8], ebx
0x14003a94c  add     rsi, rbx
0x14003a94f  inc     dword ptr [r15]
0x14003a952  mov     eax, [r15]
0x14003a955  sub     r12d, ebx
0x14003a958  jnz     short loc_14003A916
0x14003a95a  mov     ebx, [rdi+0B0h]
0x14003a960  jmp     short loc_14003A981
0x14003a962  mov     ecx, [r13+0]
0x14003a966  mov     eax, [rdi+0B0h]
0x14003a96c  cmp     eax, ecx
0x14003a96e  cmovnb  eax, ecx
0x14003a971  mov     ebx, eax
0x14003a973  mov     r8d, eax; Size
0x14003a976  mov     rdx, rsi; Src
0x14003a979  mov     rcx, [r15]; void *
0x14003a97c  call    memmove
0x14003a981  mov     [r13+0], ebx
0x14003a985  xor     eax, eax
0x14003a987  mov     rbx, [rsp+58h+arg_10]
0x14003a98c  add     rsp, 30h
0x14003a990  pop     r15
0x14003a992  pop     r13
0x14003a994  pop     r12
0x14003a996  pop     rdi
0x14003a997  pop     rsi
0x14003a998  retn
```
