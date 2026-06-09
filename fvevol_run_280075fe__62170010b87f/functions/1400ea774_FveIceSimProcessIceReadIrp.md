# FveIceSimProcessIceReadIrp

- ea: `0x1400ea774`
- end: `0x1400ea9d1`
- name: `FveIceSimProcessIceReadIrp`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400ea498`

## callees

- `0x140008288`
- `0x140008c60`
- `0x140021a00`
- `0x140021d00`
- `0x1400ea774`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea822`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400ea822`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400ea94c`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400ea94c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400ea88a`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400ea88a`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400ea924`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400ea924`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ea85e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ea85e`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea9af`
- `ntoskrnl!KeBugCheckEx` at `0x1400ea9af`

## pseudocode

```c
__int64 __fastcall FveIceSimProcessIceReadIrp(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rdi
  __int64 v7; // r12
  __int64 v9; // rcx
  char v10; // bp
  __int64 result; // rax
  ULONG v12; // r15d
  __int64 v13; // rcx
  __int64 v14; // r10
  PVOID v15; // rdi
  PVOID v16; // rax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int16 v20; // di
  __int64 v21; // rcx
  int v22[64]; // [rsp+40h] [rbp-148h] BYREF

  v5 = a2;
  v7 = a3;
  memset(v22, 0, sizeof(v22));
  v10 = 0;
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v9) )
    *(_QWORD *)&v22[16] = *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 152LL);
  else
    *(_QWORD *)&v22[16] = *(_QWORD *)(a1 + 1008);
  v22[29] = *(_DWORD *)(a1 + 1308);
  while ( 1 )
  {
    result = 0x100000;
    if ( !a4 )
      break;
    v12 = a4;
    if ( a4 > 0x100000 )
      v12 = 0x100000;
    IoBuildPartialMdl(
      *(PMDL *)(v5 + 8),
      *(PMDL *)(*(_QWORD *)(a1 + 4752) + 48LL),
      (PVOID)(v7 + *(_QWORD *)(*(_QWORD *)(v5 + 8) + 32LL) + *(unsigned int *)(*(_QWORD *)(v5 + 8) + 44LL) - a3),
      v12);
    v13 = *(_QWORD *)(a1 + 4752);
    v14 = *(_QWORD *)(v13 + 48);
    if ( (*(_BYTE *)(v14 + 10) & 5) != 0 )
    {
      v15 = *(PVOID *)(v14 + 24);
    }
    else
    {
      v16 = MmMapLockedPagesSpecifyCache((PMDL)v14, 0, MmCached, 0, 0, 0x40000010u);
      v13 = *(_QWORD *)(a1 + 4752);
      v15 = v16;
    }
    if ( !v15 )
    {
      v15 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v13 + 64), 0x30455646u, *(PMDL *)(v13 + 48), MmCached);
      v10 = 1;
    }
    memmove(*(void **)(*(_QWORD *)(a1 + 4752) + 56LL), v15, v12);
    v17 = FveFilteredDecrypt(
            3,
            (int)v22,
            v7,
            -1,
            v12,
            *(PUCHAR *)(*(_QWORD *)(a1 + 4752) + 56LL),
            *(PUCHAR *)(*(_QWORD *)(a1 + 4752) + 56LL),
            0);
    if ( v17 < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, v17);
    memmove(v15, *(const void **)(*(_QWORD *)(a1 + 4752) + 56LL), v12);
    if ( v10 )
      MmUnmapReservedMapping(
        *(PVOID *)(*(_QWORD *)(a1 + 4752) + 64LL),
        0x30455646u,
        *(PMDL *)(*(_QWORD *)(a1 + 4752) + 48LL));
    v18 = *(_QWORD *)(a1 + 4752);
    v19 = *(_QWORD *)(v18 + 48);
    v20 = *(_WORD *)(v19 + 8);
    if ( (*(_BYTE *)(v19 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v19 + 24), *(PMDL *)(v18 + 48));
    v10 = 0;
    v7 += v12;
    a4 -= v12;
    v21 = *(_QWORD *)(*(_QWORD *)(a1 + 4752) + 48LL);
    *(_QWORD *)v21 = 0;
    *(_DWORD *)(v21 + 8) = 48;
    *(_QWORD *)(v21 + 32) = 0;
    *(_QWORD *)(v21 + 40) = 0;
    *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 4752) + 48LL) + 8LL) = v20;
    v5 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1400ea774  mov     [rsp+arg_8], rdx
0x1400ea779  push    rbx
0x1400ea77a  push    rbp
0x1400ea77b  push    rsi
0x1400ea77c  push    rdi
0x1400ea77d  push    r12
0x1400ea77f  push    r13
0x1400ea781  push    r14
0x1400ea783  push    r15
0x1400ea785  sub     rsp, 148h
0x1400ea78c  mov     r13, r8
0x1400ea78f  mov     rdi, rdx
0x1400ea792  mov     rbx, rcx
0x1400ea795  mov     r12, r8
0x1400ea798  xor     edx, edx; Val
0x1400ea79a  lea     rcx, [rsp+188h+var_148]; void *
0x1400ea79f  mov     r8d, 100h; Size
0x1400ea7a5  mov     esi, r9d
0x1400ea7a8  call    memset
0x1400ea7ad  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ea7b2  xor     ebp, ebp
0x1400ea7b4  test    eax, eax
0x1400ea7b6  jnz     short loc_1400EA7C9
0x1400ea7b8  mov     rax, [rbx+3F0h]
0x1400ea7bf  mov     [rsp+188h+var_108], rax
0x1400ea7c7  jmp     short loc_1400EA7DF
0x1400ea7c9  mov     rax, [rbx+1290h]
0x1400ea7d0  mov     rcx, [rax+98h]
0x1400ea7d7  mov     [rsp+188h+var_108], rcx
0x1400ea7df  mov     eax, [rbx+51Ch]
0x1400ea7e5  mov     [rsp+188h+var_D4], eax
0x1400ea7ec  mov     eax, 100000h
0x1400ea7f1  test    esi, esi
0x1400ea7f3  jz      loc_1400EA9BC
0x1400ea7f9  mov     rcx, [rdi+8]; SourceMdl
0x1400ea7fd  cmp     esi, eax
0x1400ea7ff  mov     rdx, [rbx+1290h]
0x1400ea806  mov     r15d, esi
0x1400ea809  cmova   r15d, eax
0x1400ea80d  mov     r9d, r15d; Length
0x1400ea810  mov     r8d, [rcx+2Ch]
0x1400ea814  add     r8, [rcx+20h]
0x1400ea818  mov     rdx, [rdx+30h]; TargetMdl
0x1400ea81c  sub     r8, r13
0x1400ea81f  add     r8, r12; VirtualAddress
0x1400ea822  call    cs:__imp_IoBuildPartialMdl
0x1400ea829  nop     dword ptr [rax+rax+00h]
0x1400ea82e  mov     rcx, [rbx+1290h]
0x1400ea835  mov     r10, [rcx+30h]
0x1400ea839  test    byte ptr [r10+0Ah], 5
0x1400ea83e  jz      short loc_1400EA846
0x1400ea840  mov     rdi, [r10+18h]
0x1400ea844  jmp     short loc_1400EA874
0x1400ea846  xor     r9d, r9d; RequestedAddress
0x1400ea849  mov     [rsp+188h+Priority], 40000010h; Priority
0x1400ea851  xor     edx, edx; AccessMode
0x1400ea853  mov     [rsp+188h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400ea857  mov     rcx, r10; MemoryDescriptorList
0x1400ea85a  lea     r8d, [r9+1]; CacheType
0x1400ea85e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ea865  nop     dword ptr [rax+rax+00h]
0x1400ea86a  mov     rcx, [rbx+1290h]
0x1400ea871  mov     rdi, rax
0x1400ea874  test    rdi, rdi
0x1400ea877  jnz     short loc_1400EA89C
0x1400ea879  mov     r8, [rcx+30h]; MemoryDescriptorList
0x1400ea87d  lea     r9d, [rdi+1]; CacheType
0x1400ea881  mov     rcx, [rcx+40h]; MappingAddress
0x1400ea885  mov     edx, 30455646h; PoolTag
0x1400ea88a  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400ea891  nop     dword ptr [rax+rax+00h]
0x1400ea896  mov     rdi, rax
0x1400ea899  mov     bpl, 1
0x1400ea89c  mov     rcx, [rbx+1290h]
0x1400ea8a3  mov     rdx, rdi; Src
0x1400ea8a6  mov     r8d, r15d; Size
0x1400ea8a9  mov     r14d, r15d
0x1400ea8ac  mov     rcx, [rcx+38h]; void *
0x1400ea8b0  call    memmove
0x1400ea8b5  mov     rax, [rbx+1290h]
0x1400ea8bc  lea     rdx, [rsp+188h+var_148]; int
0x1400ea8c1  mov     [rsp+188h+var_150], 0; __int64
0x1400ea8ca  or      r9, 0FFFFFFFFFFFFFFFFh; int
0x1400ea8ce  mov     r8, r12; int
0x1400ea8d1  mov     rcx, [rax+38h]
0x1400ea8d5  mov     [rsp+188h+var_158], rcx; PUCHAR
0x1400ea8da  mov     qword ptr [rsp+188h+Priority], rcx; PUCHAR
0x1400ea8df  lea     ecx, [r9+4]; int
0x1400ea8e3  mov     [rsp+188h+BugCheckOnFailure], r15d; int
0x1400ea8e8  call    FveFilteredDecrypt
0x1400ea8ed  test    eax, eax
0x1400ea8ef  js      loc_1400EA999
0x1400ea8f5  mov     rdx, [rbx+1290h]
0x1400ea8fc  mov     r8d, r14d; Size
0x1400ea8ff  mov     rcx, rdi; void *
0x1400ea902  mov     rdx, [rdx+38h]; Src
0x1400ea906  call    memmove
0x1400ea90b  test    bpl, bpl
0x1400ea90e  jz      short loc_1400EA930
0x1400ea910  mov     rcx, [rbx+1290h]
0x1400ea917  mov     edx, 30455646h; PoolTag
0x1400ea91c  mov     r8, [rcx+30h]; MemoryDescriptorList
0x1400ea920  mov     rcx, [rcx+40h]; BaseAddress
0x1400ea924  call    cs:__imp_MmUnmapReservedMapping
0x1400ea92b  nop     dword ptr [rax+rax+00h]
0x1400ea930  mov     rax, [rbx+1290h]
0x1400ea937  mov     rcx, [rax+30h]
0x1400ea93b  test    byte ptr [rcx+0Ah], 20h
0x1400ea93f  movzx   edi, word ptr [rcx+8]
0x1400ea943  jz      short loc_1400EA958
0x1400ea945  mov     rdx, rcx; MemoryDescriptorList
0x1400ea948  mov     rcx, [rcx+18h]; BaseAddress
0x1400ea94c  call    cs:__imp_MmUnmapLockedPages
0x1400ea953  nop     dword ptr [rax+rax+00h]
0x1400ea958  mov     rax, [rbx+1290h]
0x1400ea95f  xor     ebp, ebp
0x1400ea961  add     r12, r14
0x1400ea964  sub     esi, r15d
0x1400ea967  mov     rcx, [rax+30h]
0x1400ea96b  mov     [rcx], rbp
0x1400ea96e  mov     dword ptr [rcx+8], 30h ; '0'
0x1400ea975  mov     [rcx+20h], rbp
0x1400ea979  mov     [rcx+28h], rbp
0x1400ea97d  mov     rax, [rbx+1290h]
0x1400ea984  mov     rcx, [rax+30h]
0x1400ea988  mov     [rcx+8], di
0x1400ea98c  mov     rdi, [rsp+188h+arg_8]
0x1400ea994  jmp     loc_1400EA7EC
0x1400ea999  xor     r9d, r9d; BugCheckParameter3
0x1400ea99c  cdqe
0x1400ea99e  xor     r8d, r8d; BugCheckParameter2
0x1400ea9a1  mov     qword ptr [rsp+188h+BugCheckOnFailure], rax; BugCheckParameter4
0x1400ea9a6  mov     ecx, 120h; BugCheckCode
0x1400ea9ab  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400ea9af  call    cs:__imp_KeBugCheckEx
0x1400ea9bc  add     rsp, 148h
0x1400ea9c3  pop     r15
0x1400ea9c5  pop     r14
0x1400ea9c7  pop     r13
0x1400ea9c9  pop     r12
0x1400ea9cb  pop     rdi
0x1400ea9cc  pop     rsi
0x1400ea9cd  pop     rbp
0x1400ea9ce  pop     rbx
0x1400ea9cf  retn
```
