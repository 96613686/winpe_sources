# SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::Rescan(Recycler *,RescanFlags)

- ea: `0x18000a7f0`
- end: `0x18000aa9c`
- name: `?Rescan@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@IEAAIPEAVRecycler@@W4RescanFlags@@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a02c`

## callees

- `0x180009ea8`
- `0x18000a7f0`
- `0x18000b348`
- `0x18025a5ac`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x18000a9f4`
- `KERNEL32!ResetWriteWatch` at `0x18000aa22`
- `KERNEL32!ResetWriteWatch` at `0x18000a9f4`
- `KERNEL32!ResetWriteWatch` at `0x18000aa22`
- `KERNEL32!GetWriteWatch` at `0x18000a8bc`
- `KERNEL32!GetWriteWatch` at `0x18000a970`
- `KERNEL32!GetWriteWatch` at `0x18000a8bc`
- `KERNEL32!GetWriteWatch` at `0x18000a970`

## pseudocode

```c
__int64 __fastcall SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::Rescan(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v5; // r13
  __int64 v6; // rbx
  int v7; // r15d
  void *v8; // rdx
  __int64 v9; // rbx
  int v10; // esi
  void *v11; // rdx
  unsigned int v12; // ebx
  int v14; // ebx
  DWORD dwGranularity; // [rsp+30h] [rbp-20h] BYREF
  ULONG_PTR dwCount; // [rsp+38h] [rbp-18h] BYREF
  PVOID Addresses[2]; // [rsp+40h] [rbp-10h] BYREF

  v5 = a1;
  if ( (*(_DWORD *)a2 & 0x2001) != 0x2001 && !*(_BYTE *)(a2 + 12901) )
    HeapBucketT<SmallFinalizableHeapBlock>::PrepareSweep(a1);
  v6 = *(_QWORD *)(v5 + 72);
  v7 = 0;
  if ( !v6 )
    goto LABEL_16;
  do
  {
    if ( (a3 & 1) != 0 )
    {
      *(_BYTE *)(v6 + 120) = 0;
    }
    else if ( *(_BYTE *)(v6 + 120) )
    {
      if ( (a3 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v6 + 8), 0x1000u);
LABEL_12:
      if ( !*(_BYTE *)(v6 + 120) )
        goto LABEL_14;
      goto LABEL_13;
    }
    if ( !*(_WORD *)(v6 + 80) )
      goto LABEL_12;
    if ( *(_BYTE *)(v6 + 25) )
    {
      if ( *(_BYTE *)(a2 + 12888) )
        goto LABEL_12;
      *(_BYTE *)(v6 + 25) = 0;
    }
    else
    {
      if ( *(_BYTE *)(a2 + 12901) )
        goto LABEL_12;
      v8 = *(void **)(v6 + 8);
      dwCount = 1;
      dwGranularity = 4096;
      Addresses[0] = 0;
      if ( !GetWriteWatch((a3 >> 1) & 1, v8, 0x1000u, Addresses, &dwCount, &dwGranularity) && !dwCount )
        goto LABEL_12;
    }
    SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<0,0>((SmallFinalizableHeapBlock *)v6);
LABEL_13:
    ++v7;
LABEL_14:
    v6 = *(_QWORD *)(v6 + 32);
  }
  while ( v6 );
  v5 = a1;
LABEL_16:
  v9 = *(_QWORD *)(v5 + 80);
  v10 = 0;
  if ( !v9 )
    goto LABEL_28;
  while ( 2 )
  {
    if ( (a3 & 1) != 0 )
    {
      *(_BYTE *)(v9 + 120) = 0;
      goto LABEL_19;
    }
    if ( *(_BYTE *)(v9 + 120) )
    {
      if ( (a3 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v9 + 8), 0x1000u);
LABEL_24:
      if ( *(_BYTE *)(v9 + 120) )
        goto LABEL_25;
    }
    else
    {
LABEL_19:
      if ( !*(_WORD *)(v9 + 80) )
        goto LABEL_24;
      if ( *(_BYTE *)(v9 + 25) )
      {
        if ( *(_BYTE *)(a2 + 12888) )
          goto LABEL_24;
        *(_BYTE *)(v9 + 25) = 0;
      }
      else
      {
        if ( *(_BYTE *)(a2 + 12901) )
          goto LABEL_24;
        v11 = *(void **)(v9 + 8);
        dwCount = 1;
        dwGranularity = 4096;
        Addresses[0] = 0;
        if ( !GetWriteWatch((a3 >> 1) & 1, v11, 0x1000u, Addresses, &dwCount, &dwGranularity) && !dwCount )
          goto LABEL_24;
      }
      SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<0,0>((SmallFinalizableHeapBlock *)v9);
LABEL_25:
      ++v10;
    }
    v9 = *(_QWORD *)(v9 + 32);
    if ( v9 )
      continue;
    break;
  }
  v5 = a1;
LABEL_28:
  v12 = v10 + v7;
  if ( !*(_BYTE *)(a2 + 12903) )
    return v12;
  v14 = SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<1,0>(*(SmallFinalizableHeapBlock **)(v5 + 88))
      + v12;
  return v14
       + (unsigned int)SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<1,0>(*(SmallFinalizableHeapBlock **)(v5 + 96));
}

```

## disassembly

```asm
0x18000a7f0  mov     rax, rsp
0x18000a7f3  mov     [rax+20h], rbx
0x18000a7f7  mov     [rax+18h], r8d
0x18000a7fb  mov     [rax+10h], rdx
0x18000a7ff  mov     [rax+8], rcx
0x18000a803  push    rbp
0x18000a804  push    rsi
0x18000a805  push    rdi
0x18000a806  push    r12
0x18000a808  push    r13
0x18000a80a  push    r14
0x18000a80c  push    r15
0x18000a80e  mov     rbp, rsp
0x18000a811  sub     rsp, 50h
0x18000a815  mov     rdi, [rbp+arg_8]
0x18000a819  mov     ecx, 2001h
0x18000a81e  mov     r14d, [rbp+arg_10]
0x18000a822  xor     r12d, r12d
0x18000a825  mov     r13, [rbp+arg_0]
0x18000a829  mov     eax, [rdi]
0x18000a82b  and     eax, ecx
0x18000a82d  cmp     eax, ecx
0x18000a82f  jz      short loc_18000A842
0x18000a831  cmp     [rdi+3265h], r12b
0x18000a838  jnz     short loc_18000A842
0x18000a83a  mov     rcx, r13
0x18000a83d  call    ?PrepareSweep@?$HeapBucketT@VSmallFinalizableHeapBlock@@@@QEAAXXZ; HeapBucketT<SmallFinalizableHeapBlock>::PrepareSweep(void)
0x18000a842  mov     rbx, [r13+48h]
0x18000a846  mov     r15, r12
0x18000a849  test    rbx, rbx
0x18000a84c  jz      loc_18000A8F4
0x18000a852  mov     esi, r14d
0x18000a855  and     esi, 1
0x18000a858  xor     r13d, r13d
0x18000a85b  test    esi, esi
0x18000a85d  jz      loc_18000A9D7
0x18000a863  mov     [rbx+78h], r13b
0x18000a867  cmp     [rbx+50h], r13w
0x18000a86c  jz      short loc_18000A8DA
0x18000a86e  cmp     [rbx+19h], r13b
0x18000a872  jnz     loc_18000AA33
0x18000a878  cmp     [rdi+3265h], r13b
0x18000a87f  jnz     short loc_18000A8DA
0x18000a881  mov     rdx, [rbx+8]; lpBaseAddress
0x18000a885  lea     rax, [rbp+dwGranularity]
0x18000a889  mov     [rsp+50h+lpdwGranularity], rax; lpdwGranularity
0x18000a88e  lea     r9, [rbp+Addresses]; lpAddresses
0x18000a892  mov     ecx, r14d
0x18000a895  mov     [rbp+dwCount], 1
0x18000a89d  shr     ecx, 1
0x18000a89f  lea     rax, [rbp+dwCount]
0x18000a8a3  and     ecx, 1; dwFlags
0x18000a8a6  mov     [rsp+50h+lpdwCount], rax; lpdwCount
0x18000a8ab  mov     r8d, 1000h; dwRegionSize
0x18000a8b1  mov     [rbp+dwGranularity], 1000h
0x18000a8b8  mov     [rbp+Addresses], r13
0x18000a8bc  call    cs:__imp_GetWriteWatch
0x18000a8c3  nop     dword ptr [rax+rax+00h]
0x18000a8c8  test    eax, eax
0x18000a8ca  jnz     loc_18000AA44
0x18000a8d0  cmp     [rbp+dwCount], r13
0x18000a8d4  jnz     loc_18000AA44
0x18000a8da  cmp     [rbx+78h], r13b
0x18000a8de  jz      short loc_18000A8E3
0x18000a8e0  inc     r15
0x18000a8e3  mov     rbx, [rbx+20h]
0x18000a8e7  test    rbx, rbx
0x18000a8ea  jnz     loc_18000A85B
0x18000a8f0  mov     r13, [rbp+arg_0]
0x18000a8f4  mov     rbx, [r13+50h]
0x18000a8f8  mov     rsi, r12
0x18000a8fb  test    rbx, rbx
0x18000a8fe  jz      loc_18000A9AB
0x18000a904  mov     r12d, r14d
0x18000a907  and     r12d, 1
0x18000a90b  xor     r13d, r13d
0x18000a90e  test    r12d, r12d
0x18000a911  jz      loc_18000AA05
0x18000a917  mov     [rbx+78h], r13b
0x18000a91b  cmp     [rbx+50h], r13w
0x18000a920  jz      short loc_18000A98E
0x18000a922  cmp     [rbx+19h], r13b
0x18000a926  jnz     loc_18000AA54
0x18000a92c  cmp     [rdi+3265h], r13b
0x18000a933  jnz     short loc_18000A98E
0x18000a935  mov     rdx, [rbx+8]; lpBaseAddress
0x18000a939  lea     rax, [rbp+dwGranularity]
0x18000a93d  mov     [rsp+50h+lpdwGranularity], rax; lpdwGranularity
0x18000a942  lea     r9, [rbp+Addresses]; lpAddresses
0x18000a946  mov     ecx, r14d
0x18000a949  mov     [rbp+dwCount], 1
0x18000a951  shr     ecx, 1
0x18000a953  lea     rax, [rbp+dwCount]
0x18000a957  and     ecx, 1; dwFlags
0x18000a95a  mov     [rsp+50h+lpdwCount], rax; lpdwCount
0x18000a95f  mov     r8d, 1000h; dwRegionSize
0x18000a965  mov     [rbp+dwGranularity], 1000h
0x18000a96c  mov     [rbp+Addresses], r13
0x18000a970  call    cs:__imp_GetWriteWatch
0x18000a977  nop     dword ptr [rax+rax+00h]
0x18000a97c  test    eax, eax
0x18000a97e  jnz     loc_18000AA65
0x18000a984  cmp     [rbp+dwCount], r13
0x18000a988  jnz     loc_18000AA65
0x18000a98e  cmp     [rbx+78h], r13b
0x18000a992  jz      short loc_18000A997
0x18000a994  inc     rsi
0x18000a997  mov     rbx, [rbx+20h]
0x18000a99b  test    rbx, rbx
0x18000a99e  jnz     loc_18000A90E
0x18000a9a4  mov     r13, [rbp+arg_0]
0x18000a9a8  xor     r12d, r12d
0x18000a9ab  lea     ebx, [rsi+r15]
0x18000a9af  cmp     [rdi+3267h], r12b
0x18000a9b6  jnz     loc_18000AA75
0x18000a9bc  mov     eax, ebx
0x18000a9be  mov     rbx, [rsp+50h+arg_18]
0x18000a9c6  add     rsp, 50h
0x18000a9ca  pop     r15
0x18000a9cc  pop     r14
0x18000a9ce  pop     r13
0x18000a9d0  pop     r12
0x18000a9d2  pop     rdi
0x18000a9d3  pop     rsi
0x18000a9d4  pop     rbp
0x18000a9d5  retn
0x18000a9d7  cmp     [rbx+78h], r13b
0x18000a9db  jz      loc_18000A867
0x18000a9e1  test    r14b, 2
0x18000a9e5  jz      loc_18000A8DA
0x18000a9eb  mov     rcx, [rbx+8]; lpBaseAddress
0x18000a9ef  mov     edx, 1000h; dwRegionSize
0x18000a9f4  call    cs:__imp_ResetWriteWatch
0x18000a9fb  nop     dword ptr [rax+rax+00h]
0x18000aa00  jmp     loc_18000A8DA
0x18000aa05  cmp     [rbx+78h], r13b
0x18000aa09  jz      loc_18000A91B
0x18000aa0f  test    r14b, 2
0x18000aa13  jz      loc_18000A98E
0x18000aa19  mov     rcx, [rbx+8]; lpBaseAddress
0x18000aa1d  mov     edx, 1000h; dwRegionSize
0x18000aa22  call    cs:__imp_ResetWriteWatch
0x18000aa29  nop     dword ptr [rax+rax+00h]
0x18000aa2e  jmp     loc_18000A98E
0x18000aa33  cmp     [rdi+3258h], r13b
0x18000aa3a  jnz     loc_18000A8DA
0x18000aa40  mov     [rbx+19h], r13b
0x18000aa44  mov     rdx, rdi
0x18000aa47  mov     rcx, rbx; this
0x18000aa4a  call    ??$RescanObjects@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KAXPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<0,0>(SmallFinalizableHeapBlock *,Recycler *)
0x18000aa4f  jmp     loc_18000A8E0
0x18000aa54  cmp     [rdi+3258h], r13b
0x18000aa5b  jnz     loc_18000A98E
0x18000aa61  mov     [rbx+19h], r13b
0x18000aa65  mov     rdx, rdi
0x18000aa68  mov     rcx, rbx; this
0x18000aa6b  call    ??$RescanObjects@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KAXPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<0,0>(SmallFinalizableHeapBlock *,Recycler *)
0x18000aa70  jmp     loc_18000A994
0x18000aa75  mov     rcx, [r13+58h]; this
0x18000aa79  mov     r8d, r14d
0x18000aa7c  mov     rdx, rdi
0x18000aa7f  call    ??$RescanHeapBlockList@$00$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KA_KPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<1,0>(SmallFinalizableHeapBlock *,Recycler *,RescanFlags)
0x18000aa84  mov     rcx, [r13+60h]; this
0x18000aa88  mov     r8d, r14d
0x18000aa8b  mov     rdx, rdi
0x18000aa8e  add     ebx, eax
0x18000aa90  call    ??$RescanHeapBlockList@$00$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KA_KPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<1,0>(SmallFinalizableHeapBlock *,Recycler *,RescanFlags)
0x18000aa95  add     eax, ebx
0x18000aa97  jmp     loc_18000A9BE
```
