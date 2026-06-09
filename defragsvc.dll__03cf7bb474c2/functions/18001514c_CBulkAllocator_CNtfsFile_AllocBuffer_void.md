# CBulkAllocator<CNtfsFile>::_AllocBuffer(void)

- ea: `0x18001514c`
- end: `0x180015289`
- name: `?_AllocBuffer@?$CBulkAllocator@VCNtfsFile@@@@AEAAJXZ`
- size: `317`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014f70`
- `0x18001fd00`
- `0x1800208fc`

## callees

- `0x18001514c`
- `0x180067b0a`

## import_xrefs

- `ntdll!RtlInitializeBitMap` at `0x18001525a`
- `ntdll!RtlInitializeBitMap` at `0x18001525a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800151f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015219`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBulkAllocator<CNtfsFile>::_AllocBuffer(__int64 a1)
{
  int v1; // r8d
  unsigned int v2; // ebp
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r12
  struct _RTL_BITMAP *v8; // rax
  struct _RTL_BITMAP *v9; // rdi
  LPVOID v10; // rax
  size_t v11; // r14
  ULONG *v12; // rax
  unsigned int v13; // ebx
  void *v14; // rcx
  size_t v15; // r8

  v1 = 0;
  v2 = 0;
  v4 = 0;
  do
  {
    if ( (unsigned int)v4 >= 0x10000 )
      return (unsigned int)-2147024882;
    v5 = v4;
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4) )
      v5 = v2;
    else
      v1 = 1;
    v4 = (unsigned int)(v4 + 1);
    v2 = v5;
  }
  while ( !v1 );
  v6 = *(_DWORD *)(a1 + 20);
  v7 = *(_QWORD *)(a1 + 32);
  v8 = (struct _RTL_BITMAP *)CoTaskMemAlloc(0x30u);
  v9 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  v10 = CoTaskMemAlloc(v7 * v6);
  *(_QWORD *)&v9->SizeOfBitMap = v10;
  if ( v10 && (v11 = (unsigned __int64)v6 >> 3, v12 = (ULONG *)CoTaskMemAlloc(v11), (v9->Buffer = v12) != 0) )
  {
    v15 = v7 * v6;
    v13 = 0;
    memset_0(*(void **)&v9->SizeOfBitMap, 0, v15);
    memset_0(v9->Buffer, 0, v11);
    RtlInitializeBitMap(v9 + 1, v9->Buffer, *(_DWORD *)(a1 + 20));
    v9[2].SizeOfBitMap = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * v2) = v9;
    if ( v2 < *(_DWORD *)(a1 + 16) )
      *(_DWORD *)(a1 + 16) = v2;
    ++*(_DWORD *)(a1 + 24);
  }
  else
  {
    v13 = -2147024882;
    CoTaskMemFree(v9->Buffer);
    v14 = *(void **)&v9->SizeOfBitMap;
    v9->Buffer = 0;
    CoTaskMemFree(v14);
    *(_QWORD *)&v9->SizeOfBitMap = 0;
    CoTaskMemFree(v9);
  }
  return v13;
}

```

## disassembly

```asm
0x18001514c  push    rbx
0x18001514e  push    rbp
0x18001514f  push    rsi
0x180015150  push    rdi
0x180015151  push    r12
0x180015153  push    r14
0x180015155  push    r15
0x180015157  sub     rsp, 20h
0x18001515b  xor     r8d, r8d
0x18001515e  xor     ebp, ebp
0x180015160  mov     rsi, rcx
0x180015163  xor     r9d, r9d
0x180015166  lea     r10d, [r8+1]
0x18001516a  cmp     r9d, 10000h
0x180015171  jnb     loc_180015221
0x180015177  mov     rax, [rsi+8]
0x18001517b  mov     rcx, [rax+r9*8]
0x18001517f  mov     eax, r9d
0x180015182  test    rcx, rcx
0x180015185  cmovnz  eax, ebp
0x180015188  cmovz   r8d, r10d
0x18001518c  add     r9d, r10d
0x18001518f  mov     ebp, eax
0x180015191  test    r8d, r8d
0x180015194  jz      short loc_18001516A
0x180015196  mov     ebx, [rsi+14h]
0x180015199  mov     ecx, 30h ; '0'; cb
0x18001519e  mov     r12, [rsi+20h]
0x1800151a2  call    cs:__imp_CoTaskMemAlloc
0x1800151a8  mov     rdi, rax
0x1800151ab  test    rax, rax
0x1800151ae  jz      short loc_18001522A
0x1800151b0  xorps   xmm0, xmm0
0x1800151b3  mov     r15d, ebx
0x1800151b6  movups  xmmword ptr [rax], xmm0
0x1800151b9  mov     r14d, ebx
0x1800151bc  movups  xmmword ptr [rax+10h], xmm0
0x1800151c0  imul    r15, r12
0x1800151c4  movups  xmmword ptr [rax+20h], xmm0
0x1800151c8  mov     rcx, r15; cb
0x1800151cb  call    cs:__imp_CoTaskMemAlloc
0x1800151d1  mov     [rdi], rax
0x1800151d4  test    rax, rax
0x1800151d7  jz      short loc_1800151EF
0x1800151d9  shr     r14, 3
0x1800151dd  mov     rcx, r14; cb
0x1800151e0  call    cs:__imp_CoTaskMemAlloc
0x1800151e6  mov     [rdi+8], rax
0x1800151ea  test    rax, rax
0x1800151ed  jnz     short loc_180015231
0x1800151ef  mov     rcx, [rdi+8]; pv
0x1800151f3  mov     ebx, 8007000Eh
0x1800151f8  call    cs:__imp_CoTaskMemFree
0x1800151fe  mov     rcx, [rdi]; pv
0x180015201  mov     qword ptr [rdi+8], 0
0x180015209  call    cs:__imp_CoTaskMemFree
0x18001520f  mov     rcx, rdi; pv
0x180015212  mov     qword ptr [rdi], 0
0x180015219  call    cs:__imp_CoTaskMemFree
0x18001521f  jmp     short loc_180015278
0x180015221  test    r8d, r8d
0x180015224  jnz     loc_180015196
0x18001522a  mov     ebx, 8007000Eh
0x18001522f  jmp     short loc_180015278
0x180015231  mov     rcx, [rdi]; void *
0x180015234  mov     r8, r15; Size
0x180015237  xor     edx, edx; Val
0x180015239  xor     ebx, ebx
0x18001523b  call    memset_0
0x180015240  mov     rcx, [rdi+8]; void *
0x180015244  mov     r8, r14; Size
0x180015247  xor     edx, edx; Val
0x180015249  call    memset_0
0x18001524e  mov     r8d, [rsi+14h]; SizeOfBitMap
0x180015252  lea     rcx, [rdi+10h]; BitMapHeader
0x180015256  mov     rdx, [rdi+8]; BitMapBuffer
0x18001525a  call    cs:__imp_RtlInitializeBitMap
0x180015260  mov     [rdi+20h], ebx
0x180015263  mov     rcx, [rsi+8]
0x180015267  mov     edx, ebp
0x180015269  mov     [rcx+rdx*8], rdi
0x18001526d  cmp     ebp, [rsi+10h]
0x180015270  jnb     short loc_180015275
0x180015272  mov     [rsi+10h], ebp
0x180015275  inc     dword ptr [rsi+18h]
0x180015278  mov     eax, ebx
0x18001527a  add     rsp, 20h
0x18001527e  pop     r15
0x180015280  pop     r14
0x180015282  pop     r12
0x180015284  pop     rdi
0x180015285  pop     rsi
0x180015286  pop     rbp
0x180015287  pop     rbx
0x180015288  retn
```
