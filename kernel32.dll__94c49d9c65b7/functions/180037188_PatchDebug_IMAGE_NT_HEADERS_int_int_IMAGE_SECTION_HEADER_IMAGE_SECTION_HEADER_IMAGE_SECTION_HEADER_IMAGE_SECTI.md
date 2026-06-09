# PatchDebug<_IMAGE_NT_HEADERS>(int,int,_IMAGE_SECTION_HEADER *,_IMAGE_SECTION_HEADER *,_IMAGE_SECTION_HEADER *,_IMAGE_SECTION_HEADER *,_IMAGE_NT_HEADERS *,_IMAGE_NT_HEADERS *,ulong,ulong *)

- ea: `0x180037188`
- end: `0x180037379`
- name: `??$PatchDebug@U_IMAGE_NT_HEADERS@@@@YAJHHPEAU_IMAGE_SECTION_HEADER@@000PEAU_IMAGE_NT_HEADERS@@1KPEAK@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180048b68`

## callees

- `0x1800313d0`
- `0x180037188`
- `0x1800373e8`
- `0x180054f0c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003735c`
- `ntdll!RtlFreeHeap` at `0x18003735c`
- `ntdll!RtlAllocateHeap` at `0x1800371f3`
- `ntdll!RtlAllocateHeap` at `0x1800371f3`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800371d2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800371d2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037247`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037333`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037247`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037333`

## pseudocode

```c
__int64 __fastcall PatchDebug<_IMAGE_NT_HEADERS>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned int a9,
        int *a10)
{
  unsigned int v13; // ebx
  _DWORD *GlobalData; // rax
  char *Heap; // rax
  char *v16; // rbx
  int v18; // r12d
  char *v19; // rbp
  __int64 v20; // rdx
  unsigned __int64 v21; // rsi
  char *i; // rcx
  unsigned int v23; // edi
  unsigned int v24; // eax
  HFILE hFile; // [rsp+60h] [rbp+8h]
  int v26; // [rsp+68h] [rbp+10h]
  int v27; // [rsp+80h] [rbp+28h]

  v26 = a2;
  hFile = a1;
  if ( !a5 )
    return 0;
  v13 = *(_DWORD *)(a8 + 172);
  if ( !v13 )
    return 0;
  GlobalData = (_DWORD *)KernelBaseGetGlobalData(a1, a2, a3, a4);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (*GlobalData + 1835008) | 8u, v13);
  v16 = Heap;
  if ( !Heap )
    return 8;
  v18 = 0;
  v19 = Heap;
  if ( !a3 )
    v18 = *a10;
  v27 = *(_DWORD *)(a7 + 168) - *(_DWORD *)(a5 + 12);
  SetFilePointer((HANDLE)hFile, v27 + *(_DWORD *)(a5 + 20), 0, 0);
  v20 = (*(unsigned int *)(a8 + 172) * (unsigned __int128)0x2492492492492493uLL) >> 64;
  v21 = (unsigned __int64)&v16[28 * ((v20 + (((unsigned __int64)*(unsigned int *)(a8 + 172) - v20) >> 1)) >> 4)];
  MuRead(hFile, (unsigned __int8 *)v16, *(_DWORD *)(a8 + 172));
  if ( a3 )
  {
    while ( (unsigned __int64)v16 < v21 )
    {
      *((_DWORD *)v16 + 5) += *(_DWORD *)(a4 + 12) - *(_DWORD *)(a3 + 12);
      *((_DWORD *)v16 + 6) += *(_DWORD *)(a4 + 20) - *(_DWORD *)(a3 + 20);
      v16 += 28;
    }
  }
  else
  {
    i = v16;
    v23 = -1;
    if ( (unsigned __int64)v16 < v21 )
    {
      do
      {
        if ( *((_DWORD *)v16 + 6) >= a9 && *((_DWORD *)v16 + 6) < v23 )
          v23 = *((_DWORD *)v16 + 6);
        v16 += 28;
      }
      while ( (unsigned __int64)v16 < v21 );
      if ( v23 != -1 )
      {
        *a10 = v23;
        goto LABEL_16;
      }
    }
    *a10 = llseek(hFile, 0, 2);
    for ( i = v19; (unsigned __int64)i < v21; i += 28 )
    {
LABEL_16:
      v24 = *((_DWORD *)i + 6);
      if ( v24 >= a9 )
        *((_DWORD *)i + 6) = v18 + v24 - v23;
    }
  }
  SetFilePointer((HANDLE)v26, *(_DWORD *)(a6 + 20) + v27, 0, 0);
  MuWrite(v26, v19, *(_DWORD *)(a8 + 172));
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  return 0;
}

```

## disassembly

```asm
0x180037188  mov     [rsp+arg_10], rbx
0x18003718d  mov     [rsp+arg_8], edx
0x180037191  mov     [rsp+hFile], ecx
0x180037195  push    rbp
0x180037196  push    rsi
0x180037197  push    rdi
0x180037198  push    r12
0x18003719a  push    r13
0x18003719c  push    r14
0x18003719e  push    r15
0x1800371a0  sub     rsp, 20h
0x1800371a4  mov     rsi, [rsp+58h+arg_20]
0x1800371ac  mov     r15, r9
0x1800371af  mov     rdi, r8
0x1800371b2  test    rsi, rsi
0x1800371b5  jz      loc_180037362
0x1800371bb  mov     r13, [rsp+58h+arg_38]
0x1800371c3  mov     ebx, [r13+0ACh]
0x1800371ca  test    ebx, ebx
0x1800371cc  jz      loc_180037362
0x1800371d2  call    cs:__imp_KernelBaseGetGlobalData
0x1800371d8  mov     rcx, gs:60h
0x1800371e1  mov     r8d, ebx; Size
0x1800371e4  mov     edx, [rax]
0x1800371e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800371ea  add     edx, 1C0000h
0x1800371f0  or      edx, 8; Flags
0x1800371f3  call    cs:__imp_RtlAllocateHeap
0x1800371f9  mov     rbx, rax
0x1800371fc  test    rax, rax
0x1800371ff  jnz     short loc_180037209
0x180037201  lea     eax, [rbx+8]
0x180037204  jmp     loc_180037364
0x180037209  mov     r14, [rsp+58h+arg_48]
0x180037211  xor     r12d, r12d
0x180037214  mov     rbp, rbx
0x180037217  test    rdi, rdi
0x18003721a  jnz     short loc_18003721F
0x18003721c  mov     r12d, [r14]
0x18003721f  mov     rax, [rsp+58h+arg_30]
0x180037227  xor     r9d, r9d; dwMoveMethod
0x18003722a  mov     edx, [rsi+14h]
0x18003722d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180037230  mov     ecx, [rax+0A8h]
0x180037236  sub     ecx, [rsi+0Ch]
0x180037239  mov     dword ptr [rsp+58h+arg_20], ecx
0x180037240  add     edx, ecx; lDistanceToMove
0x180037242  movsxd  rcx, [rsp+58h+hFile]; hFile
0x180037247  call    cs:__imp_SetFilePointer
0x18003724d  mov     r8d, [r13+0ACh]; unsigned int
0x180037254  mov     rax, 2492492492492493h
0x18003725e  mov     ecx, [rsp+58h+hFile]; int
0x180037262  mul     r8
0x180037265  mov     eax, r8d
0x180037268  sub     rax, rdx
0x18003726b  shr     rax, 1
0x18003726e  add     rax, rdx
0x180037271  mov     rdx, rbx; unsigned __int8 *
0x180037274  shr     rax, 4
0x180037278  imul    rsi, rax, 1Ch
0x18003727c  add     rsi, rbx
0x18003727f  call    ?MuRead@@YAKHPEAEK@Z; MuRead(int,uchar *,ulong)
0x180037284  test    rdi, rdi
0x180037287  jnz     loc_18003730E
0x18003728d  mov     r15d, [rsp+58h+arg_40]
0x180037295  or      eax, 0FFFFFFFFh
0x180037298  mov     rcx, rbx
0x18003729b  mov     edi, eax
0x18003729d  cmp     rbx, rsi
0x1800372a0  jnb     short loc_1800372C1
0x1800372a2  cmp     [rbx+18h], r15d
0x1800372a6  jb      short loc_1800372AF
0x1800372a8  cmp     [rbx+18h], edi
0x1800372ab  cmovb   edi, [rbx+18h]
0x1800372af  add     rbx, 1Ch
0x1800372b3  cmp     rbx, rsi
0x1800372b6  jb      short loc_1800372A2
0x1800372b8  cmp     edi, eax
0x1800372ba  jz      short loc_1800372C1
0x1800372bc  mov     [r14], edi
0x1800372bf  jmp     short loc_1800372DB
0x1800372c1  mov     ecx, [rsp+58h+hFile]; hFile
0x1800372c5  xor     edx, edx; lOffset
0x1800372c7  lea     r8d, [rdx+2]; iOrigin
0x1800372cb  call    _llseek
0x1800372d0  mov     [r14], eax
0x1800372d3  mov     rcx, rbp
0x1800372d6  cmp     rbp, rsi
0x1800372d9  jnb     short loc_180037313
0x1800372db  mov     eax, [rcx+18h]
0x1800372de  cmp     eax, r15d
0x1800372e1  jb      short loc_1800372EB
0x1800372e3  sub     eax, edi
0x1800372e5  add     eax, r12d
0x1800372e8  mov     [rcx+18h], eax
0x1800372eb  add     rcx, 1Ch
0x1800372ef  cmp     rcx, rsi
0x1800372f2  jb      short loc_1800372DB
0x1800372f4  jmp     short loc_180037313
0x1800372f6  mov     eax, [r15+0Ch]
0x1800372fa  sub     eax, [rdi+0Ch]
0x1800372fd  add     [rbx+14h], eax
0x180037300  mov     eax, [r15+14h]
0x180037304  sub     eax, [rdi+14h]
0x180037307  add     [rbx+18h], eax
0x18003730a  add     rbx, 1Ch
0x18003730e  cmp     rbx, rsi
0x180037311  jb      short loc_1800372F6
0x180037313  mov     rax, [rsp+58h+arg_28]
0x18003731b  xor     r9d, r9d; dwMoveMethod
0x18003731e  mov     edx, dword ptr [rsp+58h+arg_20]
0x180037325  xor     r8d, r8d; lpDistanceToMoveHigh
0x180037328  movsxd  rbx, [rsp+58h+arg_8]
0x18003732d  mov     rcx, rbx; hFile
0x180037330  add     edx, [rax+14h]; lDistanceToMove
0x180037333  call    cs:__imp_SetFilePointer
0x180037339  mov     r8d, [r13+0ACh]; unsigned int
0x180037340  mov     rdx, rbp; void *
0x180037343  mov     ecx, ebx; int
0x180037345  call    ?MuWrite@@YAKHPEBXK@Z; MuWrite(int,void const *,ulong)
0x18003734a  mov     rcx, gs:60h
0x180037353  mov     r8, rbp; P
0x180037356  xor     edx, edx; Flags
0x180037358  mov     rcx, [rcx+30h]; HeapHandle
0x18003735c  call    cs:__imp_RtlFreeHeap
0x180037362  xor     eax, eax
0x180037364  mov     rbx, [rsp+58h+arg_10]
0x180037369  add     rsp, 20h
0x18003736d  pop     r15
0x18003736f  pop     r14
0x180037371  pop     r13
0x180037373  pop     r12
0x180037375  pop     rdi
0x180037376  pop     rsi
0x180037377  pop     rbp
0x180037378  retn
```
