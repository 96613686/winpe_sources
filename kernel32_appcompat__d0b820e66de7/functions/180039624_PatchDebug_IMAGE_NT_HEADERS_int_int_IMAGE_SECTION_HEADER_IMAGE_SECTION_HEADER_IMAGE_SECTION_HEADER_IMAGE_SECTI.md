# PatchDebug<_IMAGE_NT_HEADERS>(int,int,_IMAGE_SECTION_HEADER *,_IMAGE_SECTION_HEADER *,_IMAGE_SECTION_HEADER *,_IMAGE_SECTION_HEADER *,_IMAGE_NT_HEADERS *,_IMAGE_NT_HEADERS *,ulong,ulong *)

- ea: `0x180039624`
- end: `0x180039834`
- name: `??$PatchDebug@U_IMAGE_NT_HEADERS@@@@YAJHHPEAU_IMAGE_SECTION_HEADER@@000PEAU_IMAGE_NT_HEADERS@@1KPEAK@Z`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18004d0dc`

## callees

- `0x180033330`
- `0x180039624`
- `0x1800398a4`
- `0x18005987c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180039810`
- `ntdll!RtlFreeHeap` at `0x180039810`
- `ntdll!RtlAllocateHeap` at `0x180039695`
- `ntdll!RtlAllocateHeap` at `0x180039695`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003966e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003966e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800396ef`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800397e1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800396ef`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800397e1`

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
0x180039624  mov     [rsp+arg_10], rbx
0x180039629  mov     [rsp+arg_8], edx
0x18003962d  mov     [rsp+hFile], ecx
0x180039631  push    rbp
0x180039632  push    rsi
0x180039633  push    rdi
0x180039634  push    r12
0x180039636  push    r13
0x180039638  push    r14
0x18003963a  push    r15
0x18003963c  sub     rsp, 20h
0x180039640  mov     rsi, [rsp+58h+arg_20]
0x180039648  mov     r15, r9
0x18003964b  mov     rdi, r8
0x18003964e  test    rsi, rsi
0x180039651  jz      loc_18003981C
0x180039657  mov     r13, [rsp+58h+arg_38]
0x18003965f  mov     ebx, [r13+0ACh]
0x180039666  test    ebx, ebx
0x180039668  jz      loc_18003981C
0x18003966e  call    cs:__imp_KernelBaseGetGlobalData
0x180039675  nop     dword ptr [rax+rax+00h]
0x18003967a  mov     rcx, gs:60h
0x180039683  mov     r8d, ebx; Size
0x180039686  mov     edx, [rax]
0x180039688  mov     rcx, [rcx+30h]; HeapHandle
0x18003968c  add     edx, 1C0000h
0x180039692  or      edx, 8; Flags
0x180039695  call    cs:__imp_RtlAllocateHeap
0x18003969c  nop     dword ptr [rax+rax+00h]
0x1800396a1  mov     rbx, rax
0x1800396a4  test    rax, rax
0x1800396a7  jnz     short loc_1800396B1
0x1800396a9  lea     eax, [rbx+8]
0x1800396ac  jmp     loc_18003981E
0x1800396b1  mov     r14, [rsp+58h+arg_48]
0x1800396b9  xor     r12d, r12d
0x1800396bc  mov     rbp, rbx
0x1800396bf  test    rdi, rdi
0x1800396c2  jnz     short loc_1800396C7
0x1800396c4  mov     r12d, [r14]
0x1800396c7  mov     rax, [rsp+58h+arg_30]
0x1800396cf  xor     r9d, r9d; dwMoveMethod
0x1800396d2  mov     edx, [rsi+14h]
0x1800396d5  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800396d8  mov     ecx, [rax+0A8h]
0x1800396de  sub     ecx, [rsi+0Ch]
0x1800396e1  mov     dword ptr [rsp+58h+arg_20], ecx
0x1800396e8  add     edx, ecx; lDistanceToMove
0x1800396ea  movsxd  rcx, [rsp+58h+hFile]; hFile
0x1800396ef  call    cs:__imp_SetFilePointer
0x1800396f6  nop     dword ptr [rax+rax+00h]
0x1800396fb  mov     r8d, [r13+0ACh]; unsigned int
0x180039702  mov     rax, 2492492492492493h
0x18003970c  mov     ecx, [rsp+58h+hFile]; int
0x180039710  mul     r8
0x180039713  mov     eax, r8d
0x180039716  sub     rax, rdx
0x180039719  shr     rax, 1
0x18003971c  add     rax, rdx
0x18003971f  mov     rdx, rbx; unsigned __int8 *
0x180039722  shr     rax, 4
0x180039726  imul    rsi, rax, 1Ch
0x18003972a  add     rsi, rbx
0x18003972d  call    ?MuRead@@YAKHPEAEK@Z; MuRead(int,uchar *,ulong)
0x180039732  test    rdi, rdi
0x180039735  jnz     loc_1800397BC
0x18003973b  mov     r15d, [rsp+58h+arg_40]
0x180039743  or      eax, 0FFFFFFFFh
0x180039746  mov     rcx, rbx
0x180039749  mov     edi, eax
0x18003974b  cmp     rbx, rsi
0x18003974e  jnb     short loc_18003976F
0x180039750  cmp     [rbx+18h], r15d
0x180039754  jb      short loc_18003975D
0x180039756  cmp     [rbx+18h], edi
0x180039759  cmovb   edi, [rbx+18h]
0x18003975d  add     rbx, 1Ch
0x180039761  cmp     rbx, rsi
0x180039764  jb      short loc_180039750
0x180039766  cmp     edi, eax
0x180039768  jz      short loc_18003976F
0x18003976a  mov     [r14], edi
0x18003976d  jmp     short loc_180039789
0x18003976f  mov     ecx, [rsp+58h+hFile]; hFile
0x180039773  xor     edx, edx; lOffset
0x180039775  lea     r8d, [rdx+2]; iOrigin
0x180039779  call    _llseek
0x18003977e  mov     [r14], eax
0x180039781  mov     rcx, rbp
0x180039784  cmp     rbp, rsi
0x180039787  jnb     short loc_1800397C1
0x180039789  mov     eax, [rcx+18h]
0x18003978c  cmp     eax, r15d
0x18003978f  jb      short loc_180039799
0x180039791  sub     eax, edi
0x180039793  add     eax, r12d
0x180039796  mov     [rcx+18h], eax
0x180039799  add     rcx, 1Ch
0x18003979d  cmp     rcx, rsi
0x1800397a0  jb      short loc_180039789
0x1800397a2  jmp     short loc_1800397C1
0x1800397a4  mov     eax, [r15+0Ch]
0x1800397a8  sub     eax, [rdi+0Ch]
0x1800397ab  add     [rbx+14h], eax
0x1800397ae  mov     eax, [r15+14h]
0x1800397b2  sub     eax, [rdi+14h]
0x1800397b5  add     [rbx+18h], eax
0x1800397b8  add     rbx, 1Ch
0x1800397bc  cmp     rbx, rsi
0x1800397bf  jb      short loc_1800397A4
0x1800397c1  mov     rax, [rsp+58h+arg_28]
0x1800397c9  xor     r9d, r9d; dwMoveMethod
0x1800397cc  mov     edx, dword ptr [rsp+58h+arg_20]
0x1800397d3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800397d6  movsxd  rbx, [rsp+58h+arg_8]
0x1800397db  mov     rcx, rbx; hFile
0x1800397de  add     edx, [rax+14h]; lDistanceToMove
0x1800397e1  call    cs:__imp_SetFilePointer
0x1800397e8  nop     dword ptr [rax+rax+00h]
0x1800397ed  mov     r8d, [r13+0ACh]; unsigned int
0x1800397f4  mov     rdx, rbp; void *
0x1800397f7  mov     ecx, ebx; int
0x1800397f9  call    ?MuWrite@@YAKHPEBXK@Z; MuWrite(int,void const *,ulong)
0x1800397fe  mov     rcx, gs:60h
0x180039807  mov     r8, rbp; P
0x18003980a  xor     edx, edx; Flags
0x18003980c  mov     rcx, [rcx+30h]; HeapHandle
0x180039810  call    cs:__imp_RtlFreeHeap
0x180039817  nop     dword ptr [rax+rax+00h]
0x18003981c  xor     eax, eax
0x18003981e  mov     rbx, [rsp+58h+arg_10]
0x180039823  add     rsp, 20h
0x180039827  pop     r15
0x180039829  pop     r14
0x18003982b  pop     r13
0x18003982d  pop     r12
0x18003982f  pop     rdi
0x180039830  pop     rsi
0x180039831  pop     rbp
0x180039832  retn
```
