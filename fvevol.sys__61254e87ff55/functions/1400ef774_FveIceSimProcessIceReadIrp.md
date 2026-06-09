# FveIceSimProcessIceReadIrp

- ea: `0x1400ef774`
- end: `0x1400ef9d1`
- name: `FveIceSimProcessIceReadIrp`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400ef498`

## callees

- `0x140008348`
- `0x140008d20`
- `0x140022d40`
- `0x140023040`
- `0x1400ef774`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400ef822`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ef822`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400ef94c`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400ef94c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400ef88a`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400ef88a`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400ef924`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400ef924`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ef85e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ef85e`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef9af`
- `ntoskrnl!KeBugCheckEx` at `0x1400ef9af`

## pseudocode

```c
__int64 __fastcall FveIceSimProcessIceReadIrp(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rdi
  __int64 v7; // r12
  __int64 v9; // rdx
  __int64 v10; // rcx
  char v11; // bp
  __int64 result; // rax
  ULONG v13; // r15d
  __int64 v14; // rcx
  __int64 v15; // r10
  PVOID v16; // rdi
  PVOID v17; // rax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int16 v21; // di
  __int64 v22; // rcx
  int v23[64]; // [rsp+40h] [rbp-148h] BYREF

  v5 = a2;
  v7 = a3;
  memset(v23, 0, sizeof(v23));
  v11 = 0;
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v10, v9) )
    *(_QWORD *)&v23[16] = *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 152LL);
  else
    *(_QWORD *)&v23[16] = *(_QWORD *)(a1 + 1008);
  v23[29] = *(_DWORD *)(a1 + 1308);
  while ( 1 )
  {
    result = 0x100000;
    if ( !a4 )
      break;
    v13 = a4;
    if ( a4 > 0x100000 )
      v13 = 0x100000;
    IoBuildPartialMdl(
      *(PMDL *)(v5 + 8),
      *(PMDL *)(*(_QWORD *)(a1 + 4768) + 48LL),
      (PVOID)(v7 + *(_QWORD *)(*(_QWORD *)(v5 + 8) + 32LL) + *(unsigned int *)(*(_QWORD *)(v5 + 8) + 44LL) - a3),
      v13);
    v14 = *(_QWORD *)(a1 + 4768);
    v15 = *(_QWORD *)(v14 + 48);
    if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
    {
      v16 = *(PVOID *)(v15 + 24);
    }
    else
    {
      v17 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
      v14 = *(_QWORD *)(a1 + 4768);
      v16 = v17;
    }
    if ( !v16 )
    {
      v16 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v14 + 64), 0x30455646u, *(PMDL *)(v14 + 48), MmCached);
      v11 = 1;
    }
    memmove(*(void **)(*(_QWORD *)(a1 + 4768) + 56LL), v16, v13);
    v18 = FveFilteredDecrypt(
            3,
            (int)v23,
            v7,
            -1,
            v13,
            *(PUCHAR *)(*(_QWORD *)(a1 + 4768) + 56LL),
            *(PUCHAR *)(*(_QWORD *)(a1 + 4768) + 56LL),
            0);
    if ( v18 < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, v18);
    memmove(v16, *(const void **)(*(_QWORD *)(a1 + 4768) + 56LL), v13);
    if ( v11 )
      MmUnmapReservedMapping(
        *(PVOID *)(*(_QWORD *)(a1 + 4768) + 64LL),
        0x30455646u,
        *(PMDL *)(*(_QWORD *)(a1 + 4768) + 48LL));
    v19 = *(_QWORD *)(a1 + 4768);
    v20 = *(_QWORD *)(v19 + 48);
    v21 = *(_WORD *)(v20 + 8);
    if ( (*(_BYTE *)(v20 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v20 + 24), *(PMDL *)(v19 + 48));
    v11 = 0;
    v7 += v13;
    a4 -= v13;
    v22 = *(_QWORD *)(*(_QWORD *)(a1 + 4768) + 48LL);
    *(_QWORD *)v22 = 0;
    *(_DWORD *)(v22 + 8) = 48;
    *(_QWORD *)(v22 + 32) = 0;
    *(_QWORD *)(v22 + 40) = 0;
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 4768) + 48LL) + 8LL) = v21;
    v5 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1400ef774  mov     [rsp+arg_8], rdx
0x1400ef779  push    rbx
0x1400ef77a  push    rbp
0x1400ef77b  push    rsi
0x1400ef77c  push    rdi
0x1400ef77d  push    r12
0x1400ef77f  push    r13
0x1400ef781  push    r14
0x1400ef783  push    r15
0x1400ef785  sub     rsp, 148h
0x1400ef78c  mov     r13, r8
0x1400ef78f  mov     rdi, rdx
0x1400ef792  mov     rbx, rcx
0x1400ef795  mov     r12, r8
0x1400ef798  xor     edx, edx; Val
0x1400ef79a  lea     rcx, [rsp+188h+var_148]; void *
0x1400ef79f  mov     r8d, 100h; Size
0x1400ef7a5  mov     esi, r9d
0x1400ef7a8  call    memset
0x1400ef7ad  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ef7b2  xor     ebp, ebp
0x1400ef7b4  test    eax, eax
0x1400ef7b6  jnz     short loc_1400EF7C9
0x1400ef7b8  mov     rax, [rbx+3F0h]
0x1400ef7bf  mov     [rsp+188h+var_108], rax
0x1400ef7c7  jmp     short loc_1400EF7DF
0x1400ef7c9  mov     rax, [rbx+12A0h]
0x1400ef7d0  mov     rcx, [rax+98h]
0x1400ef7d7  mov     [rsp+188h+var_108], rcx
0x1400ef7df  mov     eax, [rbx+51Ch]
0x1400ef7e5  mov     [rsp+188h+var_D4], eax
0x1400ef7ec  mov     eax, 100000h
0x1400ef7f1  test    esi, esi
0x1400ef7f3  jz      loc_1400EF9BC
0x1400ef7f9  mov     rcx, [rdi+8]; SourceMdl
0x1400ef7fd  cmp     esi, eax
0x1400ef7ff  mov     rdx, [rbx+12A0h]
0x1400ef806  mov     r15d, esi
0x1400ef809  cmova   r15d, eax
0x1400ef80d  mov     r9d, r15d; Length
0x1400ef810  mov     r8d, [rcx+2Ch]
0x1400ef814  add     r8, [rcx+20h]
0x1400ef818  mov     rdx, [rdx+30h]; TargetMdl
0x1400ef81c  sub     r8, r13
0x1400ef81f  add     r8, r12; VirtualAddress
0x1400ef822  call    cs:__imp_IoBuildPartialMdl
0x1400ef829  nop     dword ptr [rax+rax+00h]
0x1400ef82e  mov     rcx, [rbx+12A0h]
0x1400ef835  mov     r10, [rcx+30h]
0x1400ef839  test    byte ptr [r10+0Ah], 5
0x1400ef83e  jz      short loc_1400EF846
0x1400ef840  mov     rdi, [r10+18h]
0x1400ef844  jmp     short loc_1400EF874
0x1400ef846  xor     r9d, r9d; RequestedAddress
0x1400ef849  mov     [rsp+188h+Priority], 40000010h; Priority
0x1400ef851  xor     edx, edx; AccessMode
0x1400ef853  mov     [rsp+188h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400ef857  mov     rcx, r10; MemoryDescriptorList
0x1400ef85a  lea     r8d, [r9+1]; CacheType
0x1400ef85e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ef865  nop     dword ptr [rax+rax+00h]
0x1400ef86a  mov     rcx, [rbx+12A0h]
0x1400ef871  mov     rdi, rax
0x1400ef874  test    rdi, rdi
0x1400ef877  jnz     short loc_1400EF89C
0x1400ef879  mov     r8, [rcx+30h]; MemoryDescriptorList
0x1400ef87d  lea     r9d, [rdi+1]; CacheType
0x1400ef881  mov     rcx, [rcx+40h]; MappingAddress
0x1400ef885  mov     edx, 30455646h; PoolTag
0x1400ef88a  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400ef891  nop     dword ptr [rax+rax+00h]
0x1400ef896  mov     rdi, rax
0x1400ef899  mov     bpl, 1
0x1400ef89c  mov     rcx, [rbx+12A0h]
0x1400ef8a3  mov     rdx, rdi; Src
0x1400ef8a6  mov     r8d, r15d; Size
0x1400ef8a9  mov     r14d, r15d
0x1400ef8ac  mov     rcx, [rcx+38h]; void *
0x1400ef8b0  call    memmove
0x1400ef8b5  mov     rax, [rbx+12A0h]
0x1400ef8bc  lea     rdx, [rsp+188h+var_148]; int
0x1400ef8c1  mov     [rsp+188h+var_150], 0; __int64
0x1400ef8ca  or      r9, 0FFFFFFFFFFFFFFFFh; int
0x1400ef8ce  mov     r8, r12; int
0x1400ef8d1  mov     rcx, [rax+38h]
0x1400ef8d5  mov     [rsp+188h+var_158], rcx; PUCHAR
0x1400ef8da  mov     qword ptr [rsp+188h+Priority], rcx; PUCHAR
0x1400ef8df  lea     ecx, [r9+4]; int
0x1400ef8e3  mov     [rsp+188h+BugCheckOnFailure], r15d; int
0x1400ef8e8  call    FveFilteredDecrypt
0x1400ef8ed  test    eax, eax
0x1400ef8ef  js      loc_1400EF999
0x1400ef8f5  mov     rdx, [rbx+12A0h]
0x1400ef8fc  mov     r8d, r14d; Size
0x1400ef8ff  mov     rcx, rdi; void *
0x1400ef902  mov     rdx, [rdx+38h]; Src
0x1400ef906  call    memmove
0x1400ef90b  test    bpl, bpl
0x1400ef90e  jz      short loc_1400EF930
0x1400ef910  mov     rcx, [rbx+12A0h]
0x1400ef917  mov     edx, 30455646h; PoolTag
0x1400ef91c  mov     r8, [rcx+30h]; MemoryDescriptorList
0x1400ef920  mov     rcx, [rcx+40h]; BaseAddress
0x1400ef924  call    cs:__imp_MmUnmapReservedMapping
0x1400ef92b  nop     dword ptr [rax+rax+00h]
0x1400ef930  mov     rax, [rbx+12A0h]
0x1400ef937  mov     rcx, [rax+30h]
0x1400ef93b  test    byte ptr [rcx+0Ah], 20h
0x1400ef93f  movzx   edi, word ptr [rcx+8]
0x1400ef943  jz      short loc_1400EF958
0x1400ef945  mov     rdx, rcx; MemoryDescriptorList
0x1400ef948  mov     rcx, [rcx+18h]; BaseAddress
0x1400ef94c  call    cs:__imp_MmUnmapLockedPages
0x1400ef953  nop     dword ptr [rax+rax+00h]
0x1400ef958  mov     rax, [rbx+12A0h]
0x1400ef95f  xor     ebp, ebp
0x1400ef961  add     r12, r14
0x1400ef964  sub     esi, r15d
0x1400ef967  mov     rcx, [rax+30h]
0x1400ef96b  mov     [rcx], rbp
0x1400ef96e  mov     dword ptr [rcx+8], 30h ; '0'
0x1400ef975  mov     [rcx+20h], rbp
0x1400ef979  mov     [rcx+28h], rbp
0x1400ef97d  mov     rax, [rbx+12A0h]
0x1400ef984  mov     rcx, [rax+30h]
0x1400ef988  mov     [rcx+8], di
0x1400ef98c  mov     rdi, [rsp+188h+arg_8]
0x1400ef994  jmp     loc_1400EF7EC
0x1400ef999  xor     r9d, r9d; BugCheckParameter3
0x1400ef99c  cdqe
0x1400ef99e  xor     r8d, r8d; BugCheckParameter2
0x1400ef9a1  mov     qword ptr [rsp+188h+BugCheckOnFailure], rax; BugCheckParameter4
0x1400ef9a6  mov     ecx, 120h; BugCheckCode
0x1400ef9ab  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ef9af  call    cs:__imp_KeBugCheckEx
0x1400ef9bc  add     rsp, 148h
0x1400ef9c3  pop     r15
0x1400ef9c5  pop     r14
0x1400ef9c7  pop     r13
0x1400ef9c9  pop     r12
0x1400ef9cb  pop     rdi
0x1400ef9cc  pop     rsi
0x1400ef9cd  pop     rbp
0x1400ef9ce  pop     rbx
0x1400ef9cf  retn
```
