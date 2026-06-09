# CdLookupAllocation

- ea: `0x14000b1a4`
- end: `0x14000b625`
- name: `CdLookupAllocation`
- size: `1153`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14000fe14`
- `0x140010098`

## callees

- `0x140001114`
- `0x140003300`
- `0x14000b008`
- `0x14000b1a4`
- `0x14000b684`
- `0x140012464`
- `0x140012718`
- `0x14001292c`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000b25b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b504`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b25b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b504`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b3f4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b42c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b578`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b320`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b3f4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b42c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b578`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b320`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000b387`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b2a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000b387`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b2a4`
- `ntoskrnl!CcUnpinData` at `0x14000b39d`
- `ntoskrnl!CcUnpinData` at `0x14001b2b9`
- `ntoskrnl!CcUnpinData` at `0x14000b39d`
- `ntoskrnl!CcUnpinData` at `0x14001b2b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b2e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b2e4`

## pseudocode

```c
void __fastcall CdLookupAllocation(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  _QWORD *v5; // r12
  char v9; // r15
  __int64 v10; // r13
  struct _KTHREAD *CurrentThread; // rdi
  unsigned int v12; // edi
  unsigned int v13; // ecx
  __int64 i; // rdx
  unsigned int v15; // r8d
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r14
  __int64 v19; // rdx
  __int64 j; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  bool v23; // zf
  __int64 v24; // r12
  __int64 v25; // rdx
  struct _KTHREAD *v26; // r15
  char v27; // [rsp+31h] [rbp-147h]
  __int128 v28; // [rsp+68h] [rbp-110h] BYREF
  PVOID Bcb[2]; // [rsp+78h] [rbp-100h]
  __int64 v30; // [rsp+88h] [rbp-F0h]
  PVOID v31[24]; // [rsp+90h] [rbp-E8h] BYREF

  v5 = a4;
  v9 = 1;
  v10 = 0;
  v27 = 0;
  v28 = 0;
  *(_OWORD *)Bcb = 0;
  memset(v31, 0, sizeof(v31));
  if ( a2 == *(_QWORD *)(*(_QWORD *)(a2 + 120) + 72LL) )
  {
    *v5 = a3;
  }
  else
  {
LABEL_4:
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread != *(struct _KTHREAD **)(a2 + 184) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 200) + 136LL));
      *(_QWORD *)(a2 + 184) = CurrentThread;
    }
    ++*(_DWORD *)(a2 + 192);
    v12 = 0;
    v13 = 0;
    for ( i = *(_QWORD *)(a2 + 288); ; i += 40 )
    {
      v15 = *(_DWORD *)(a2 + 284);
      if ( v13 >= v15 )
      {
LABEL_28:
        if ( !v9 )
          CdRaiseStatusEx(a1, -1073741774, 0, 0x20000, 217);
        v23 = (*(_DWORD *)(a2 + 192))-- == 1;
        if ( v23 )
        {
          *(_QWORD *)(a2 + 184) = 0;
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 200) + 136LL));
        }
        v28 = 0;
        *(_OWORD *)Bcb = 0;
        memset(v31, 0, sizeof(v31));
        v10 = *(_QWORD *)(a2 + 128);
        CdAcquireResource(a1, *(struct _ERESOURCE **)(v10 + 8), 0, 1);
        v27 = 1;
        if ( !*(_QWORD *)(v10 + 472) )
          CdCreateInternalStream(a1, *(_QWORD *)(v10 + 120), v10, (UNICODE_STRING *)(v10 + 344));
        v24 = 0;
        v30 = 0;
        CdLookupDirent(a1, v10, *(_DWORD *)(a2 + 152) & 0x7FFFFFFF, (__int64)&v28);
        while ( 1 )
        {
          CdUpdateDirentFromRawDirent(a1, v25, (__int64)&v28, (__int64)v31);
          v26 = KeGetCurrentThread();
          if ( v26 != *(struct _KTHREAD **)(a2 + 184) )
          {
            ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 200) + 136LL));
            *(_QWORD *)(a2 + 184) = v26;
          }
          ++*(_DWORD *)(a2 + 192);
          if ( v12 >= *(_DWORD *)(a2 + 284) )
            CdAddAllocationFromDirent(a1, a2, v12, v24, (__int64)v31);
          v23 = (*(_DWORD *)(a2 + 192))-- == 1;
          if ( v23 )
          {
            *(_QWORD *)(a2 + 184) = 0;
            ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 200) + 136LL));
          }
          if ( SLOBYTE(v31[3]) >= 0 )
            break;
          if ( !CdLookupNextDirent(a1, v10, (unsigned int *)&v28, (__int64)&v28) )
            CdRaiseStatusEx(a1, -1073741774, 0, 0x20000, 302);
          v24 += *(_QWORD *)(*(_QWORD *)(a2 + 288) + 40LL * v12 + 8);
          v30 = v24;
          ++v12;
        }
        v9 = 0;
        v5 = a4;
        goto LABEL_4;
      }
      if ( a3 < *(_QWORD *)(i + 8) + *(_QWORD *)(i + 16) )
        break;
      ++v13;
    }
    if ( v13 >= v15 )
      goto LABEL_28;
    v16 = 5LL * v13;
    v17 = *(_QWORD *)(a2 + 288);
    v18 = a3 - *(_QWORD *)(v17 + 40LL * v13 + 16);
    v19 = *(_QWORD *)(v17 + 40LL * v13 + 24);
    j = *(_QWORD *)(v17 + 40LL * v13 + 8);
    v21 = *(_QWORD *)(v17 + 8 * v16);
    if ( j == v19 )
    {
      *v5 = v18 + v21;
    }
    else
    {
      for ( j = v19; j <= v18; j += v19 )
        v21 += *(_QWORD *)(v17 + 8 * v16 + 32);
      *v5 = v18 + v21 + v19 - j;
      if ( j > *(_QWORD *)(v17 + 8 * v16 + 8) )
        j = *(_QWORD *)(v17 + 8 * v16 + 8);
    }
    v22 = j - v18;
    if ( v22 > 0xFFFFFFFFLL )
      LODWORD(v22) = -1;
    *a5 = v22;
    if ( v27 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
      if ( Bcb[0] )
      {
        CcUnpinData(Bcb[0]);
        Bcb[0] = 0;
      }
      if ( (BYTE1(v31[3]) & 1) != 0 && v31[8] )
        ExFreePoolWithTag(v31[8], 0);
    }
    v23 = (*(_DWORD *)(a2 + 192))-- == 1;
    if ( v23 )
    {
      *(_QWORD *)(a2 + 184) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 200) + 136LL));
    }
  }
}

```

## disassembly

```asm
0x14000b1a4  mov     rax, rsp
0x14000b1a7  mov     [rax+8], rbx
0x14000b1ab  mov     [rax+18h], rsi
0x14000b1af  mov     [rax+20h], r9
0x14000b1b3  mov     [rax+10h], rdx
0x14000b1b7  push    rdi
0x14000b1b8  push    r12
0x14000b1ba  push    r13
0x14000b1bc  push    r14
0x14000b1be  push    r15
0x14000b1c0  sub     rsp, 150h
0x14000b1c7  mov     r12, r9
0x14000b1ca  mov     r14, r8
0x14000b1cd  mov     rbx, rdx
0x14000b1d0  mov     rsi, rcx
0x14000b1d3  mov     r15b, 1
0x14000b1d6  xor     r13d, r13d
0x14000b1d9  mov     [rsp+178h+var_118], r13
0x14000b1de  mov     [rsp+178h+var_147], r13b
0x14000b1e3  mov     [rsp+178h+var_148], r13b
0x14000b1e8  xorps   xmm0, xmm0
0x14000b1eb  movups  [rsp+178h+var_110], xmm0
0x14000b1f0  movups  xmmword ptr [rsp+178h+Bcb], xmm0
0x14000b1f5  xor     edx, edx; Val
0x14000b1f7  mov     r8d, 0C0h; Size
0x14000b1fd  lea     rcx, [rax-0E8h]; void *
0x14000b204  call    memset
0x14000b209  mov     rax, [rbx+78h]
0x14000b20d  cmp     rbx, [rax+48h]
0x14000b211  jnz     short loc_14000B235
0x14000b213  mov     [r12], r14
0x14000b217  lea     r11, [rsp+178h+var_28]
0x14000b21f  mov     rbx, [r11+30h]
0x14000b223  mov     rsi, [r11+40h]
0x14000b227  mov     rsp, r11
0x14000b22a  pop     r15
0x14000b22c  pop     r14
0x14000b22e  pop     r13
0x14000b230  pop     r12
0x14000b232  pop     rdi
0x14000b233  retn
0x14000b235  mov     r9d, 0FFFFFFFFh
0x14000b23b  mov     rdi, gs:188h
0x14000b244  cmp     rdi, [rbx+0B8h]
0x14000b24b  jz      short loc_14000B274
0x14000b24d  mov     rcx, [rbx+0C8h]
0x14000b254  add     rcx, 88h; FastMutex
0x14000b25b  call    cs:__imp_ExAcquireFastMutex
0x14000b262  nop     dword ptr [rax+rax+00h]
0x14000b267  mov     [rbx+0B8h], rdi
0x14000b26e  mov     r9d, 0FFFFFFFFh
0x14000b274  mov     eax, [rbx+0C0h]
0x14000b27a  inc     eax
0x14000b27c  mov     [rbx+0C0h], eax
0x14000b282  mov     [rsp+178h+var_148], 1
0x14000b287  xor     edi, edi
0x14000b289  mov     [rsp+178h+var_144], edi
0x14000b28d  mov     [rsp+178h+var_128], rdi
0x14000b292  mov     ecx, edi
0x14000b294  mov     [rsp+178h+var_144], ecx
0x14000b298  mov     rdx, [rbx+120h]
0x14000b29f  mov     [rsp+178h+var_128], rdx
0x14000b2a4  mov     r8d, [rbx+11Ch]
0x14000b2ab  cmp     ecx, r8d
0x14000b2ae  jnb     loc_14000B405
0x14000b2b4  mov     rax, [rdx+10h]
0x14000b2b8  add     rax, [rdx+8]
0x14000b2bc  cmp     r14, rax
0x14000b2bf  jl      short loc_14000B2D2
0x14000b2c1  inc     ecx
0x14000b2c3  mov     [rsp+178h+var_144], ecx
0x14000b2c7  add     rdx, 28h ; '('
0x14000b2cb  mov     [rsp+178h+var_128], rdx
0x14000b2d0  jmp     short loc_14000B2A4
0x14000b2d2  cmp     ecx, r8d
0x14000b2d5  jnb     loc_14000B405
0x14000b2db  mov     eax, ecx
0x14000b2dd  lea     r8, [rax+rax*4]
0x14000b2e1  mov     r9, [rbx+120h]
0x14000b2e8  mov     [rsp+178h+var_120], rdi
0x14000b2ed  mov     [rsp+178h+var_130], rdi
0x14000b2f2  mov     [rsp+178h+var_140], rdi
0x14000b2f7  sub     r14, [r9+r8*8+10h]
0x14000b2fc  mov     rdx, [r9+r8*8+18h]
0x14000b301  mov     rcx, [r9+r8*8+8]
0x14000b306  mov     rax, [r9+r8*8]
0x14000b30a  cmp     rcx, rdx
0x14000b30d  jnz     short loc_14000B318
0x14000b30f  add     rax, r14
0x14000b312  mov     [r12], rax
0x14000b316  jmp     short loc_14000B35C
0x14000b318  mov     rcx, rdx
0x14000b31b  mov     [rsp+178h+var_130], rdx
0x14000b320  mov     [rsp+178h+var_120], rax
0x14000b325  cmp     rcx, r14
0x14000b328  jg      short loc_14000B33E
0x14000b32a  add     rax, [r9+r8*8+20h]
0x14000b32f  mov     [rsp+178h+var_120], rax
0x14000b334  add     rcx, rdx
0x14000b337  mov     [rsp+178h+var_130], rcx
0x14000b33c  jmp     short loc_14000B325
0x14000b33e  sub     rdx, rcx
0x14000b341  add     rdx, rax
0x14000b344  add     rdx, r14
0x14000b347  mov     [r12], rdx
0x14000b34b  mov     rax, [r9+r8*8+8]
0x14000b350  cmp     rcx, rax
0x14000b353  cmovg   rcx, rax
0x14000b357  mov     [rsp+178h+var_130], rcx
0x14000b35c  sub     rcx, r14
0x14000b35f  mov     rax, rcx
0x14000b362  mov     [rsp+178h+var_140], rcx
0x14000b367  mov     esi, 0FFFFFFFFh
0x14000b36c  cmp     rax, rsi
0x14000b36f  cmovg   ecx, esi
0x14000b372  mov     rax, [rsp+178h+arg_20]
0x14000b37a  mov     [rax], ecx
0x14000b37c  cmp     [rsp+178h+var_147], dil
0x14000b381  jz      short loc_14000B3D3
0x14000b383  mov     rcx, [r13+8]; Resource
0x14000b387  call    cs:__imp_ExReleaseResourceLite
0x14000b38e  nop     dword ptr [rax+rax+00h]
0x14000b393  mov     rcx, [rsp+178h+Bcb]; Bcb
0x14000b398  test    rcx, rcx
0x14000b39b  jz      short loc_14000B3AE
0x14000b39d  call    cs:__imp_CcUnpinData
0x14000b3a4  nop     dword ptr [rax+rax+00h]
0x14000b3a9  mov     [rsp+178h+Bcb], rdi
0x14000b3ae  test    [rsp+178h+var_CF], 1
0x14000b3b6  jz      short loc_14000B3D3
0x14000b3b8  mov     rcx, [rsp+178h+P]; P
0x14000b3c0  test    rcx, rcx
0x14000b3c3  jz      short loc_14000B3D3
0x14000b3c5  xor     edx, edx; Tag
0x14000b3c7  call    cs:__imp_ExFreePoolWithTag
0x14000b3ce  nop     dword ptr [rax+rax+00h]
0x14000b3d3  add     [rbx+0C0h], esi
0x14000b3d9  jnz     loc_14000B217
0x14000b3df  mov     [rbx+0B8h], rdi
0x14000b3e6  mov     rcx, [rbx+0C8h]
0x14000b3ed  add     rcx, 88h; FastMutex
0x14000b3f4  call    cs:__imp_ExReleaseFastMutex
0x14000b3fb  nop     dword ptr [rax+rax+00h]
0x14000b400  jmp     loc_14000B217
0x14000b405  test    r15b, r15b
0x14000b408  jz      loc_14000B5E7
0x14000b40e  add     [rbx+0C0h], r9d
0x14000b415  jnz     short loc_14000B438
0x14000b417  mov     [rbx+0B8h], rdi
0x14000b41e  mov     rcx, [rbx+0C8h]
0x14000b425  add     rcx, 88h; FastMutex
0x14000b42c  call    cs:__imp_ExReleaseFastMutex
0x14000b433  nop     dword ptr [rax+rax+00h]
0x14000b438  mov     [rsp+178h+var_148], dil
0x14000b43d  xorps   xmm0, xmm0
0x14000b440  movups  [rsp+178h+var_110], xmm0
0x14000b445  movups  xmmword ptr [rsp+178h+Bcb], xmm0
0x14000b44a  xor     edx, edx; Val
0x14000b44c  mov     r8d, 0C0h; Size
0x14000b452  lea     rcx, [rsp+178h+var_E8]; void *
0x14000b45a  call    memset
0x14000b45f  mov     r13, [rbx+80h]
0x14000b466  mov     [rsp+178h+var_118], r13
0x14000b46b  mov     r9d, 1
0x14000b471  xor     r8d, r8d
0x14000b474  mov     rdx, [r13+8]
0x14000b478  mov     rcx, rsi
0x14000b47b  call    CdAcquireResource
0x14000b480  mov     [rsp+178h+var_147], 1
0x14000b485  cmp     [r13+1D8h], rdi
0x14000b48c  jnz     short loc_14000B4A4
0x14000b48e  lea     r9, [r13+158h]
0x14000b495  mov     r8, r13
0x14000b498  mov     rdx, [r13+78h]
0x14000b49c  mov     rcx, rsi
0x14000b49f  call    CdCreateInternalStream
0x14000b4a4  mov     r12, rdi
0x14000b4a7  mov     [rsp+178h+var_F0], rdi
0x14000b4af  mov     [rsp+178h+var_138], edi
0x14000b4b3  mov     r8d, [rbx+98h]
0x14000b4ba  btr     r8d, 1Fh
0x14000b4bf  lea     r9, [rsp+178h+var_110]
0x14000b4c4  mov     rdx, r13
0x14000b4c7  mov     rcx, rsi
0x14000b4ca  call    CdLookupDirent
0x14000b4cf  lea     r9, [rsp+178h+var_E8]
0x14000b4d7  lea     r8, [rsp+178h+var_110]
0x14000b4dc  mov     rcx, rsi
0x14000b4df  call    CdUpdateDirentFromRawDirent
0x14000b4e4  mov     r15, gs:188h
0x14000b4ed  cmp     r15, [rbx+0B8h]
0x14000b4f4  jz      short loc_14000B517
0x14000b4f6  mov     rcx, [rbx+0C8h]
0x14000b4fd  add     rcx, 88h; FastMutex
0x14000b504  call    cs:__imp_ExAcquireFastMutex
0x14000b50b  nop     dword ptr [rax+rax+00h]
0x14000b510  mov     [rbx+0B8h], r15
0x14000b517  mov     eax, [rbx+0C0h]
0x14000b51d  inc     eax
0x14000b51f  mov     [rbx+0C0h], eax
0x14000b525  mov     [rsp+178h+var_148], 1
0x14000b52a  cmp     edi, [rbx+11Ch]
0x14000b530  jb      short loc_14000B550
0x14000b532  lea     rax, [rsp+178h+var_E8]
0x14000b53a  mov     [rsp+178h+var_158], rax
0x14000b53f  mov     r9, r12
0x14000b542  mov     r8d, edi
0x14000b545  mov     rdx, rbx
0x14000b548  mov     rcx, rsi
0x14000b54b  call    CdAddAllocationFromDirent
0x14000b550  mov     r9d, 0FFFFFFFFh
0x14000b556  add     [rbx+0C0h], r9d
0x14000b55d  jnz     short loc_14000B58A
0x14000b55f  mov     qword ptr [rbx+0B8h], 0
0x14000b56a  mov     rcx, [rbx+0C8h]
0x14000b571  add     rcx, 88h; FastMutex
0x14000b578  call    cs:__imp_ExReleaseFastMutex
0x14000b57f  nop     dword ptr [rax+rax+00h]
0x14000b584  mov     r9d, 0FFFFFFFFh
0x14000b58a  mov     [rsp+178h+var_148], 0
0x14000b58f  test    [rsp+178h+var_D0], 80h
0x14000b597  jnz     short loc_14000B5A9
0x14000b599  xor     r15b, r15b
0x14000b59c  mov     r12, [rsp+178h+arg_18]
0x14000b5a4  jmp     loc_14000B23B
0x14000b5a9  lea     r9, [rsp+178h+var_110]
0x14000b5ae  lea     r8, [rsp+178h+var_110]
0x14000b5b3  mov     rdx, r13
0x14000b5b6  mov     rcx, rsi
0x14000b5b9  call    CdLookupNextDirent
0x14000b5be  test    al, al
0x14000b5c0  jz      short loc_14000B605
0x14000b5c2  mov     eax, edi
0x14000b5c4  lea     rcx, [rax+rax*4]
0x14000b5c8  mov     rax, [rbx+120h]
0x14000b5cf  add     r12, [rax+rcx*8+8]
0x14000b5d4  mov     [rsp+178h+var_F0], r12
0x14000b5dc  inc     edi
0x14000b5de  mov     [rsp+178h+var_138], edi
0x14000b5e2  jmp     loc_14000B4CF
0x14000b5e7  mov     dword ptr [rsp+178h+var_158], 0D9h
0x14000b5ef  mov     r9d, 20000h
0x14000b5f5  xor     r8d, r8d
0x14000b5f8  mov     edx, 0C0000032h
0x14000b5fd  mov     rcx, rsi
0x14000b600  call    CdRaiseStatusEx
0x14000b605  mov     dword ptr [rsp+178h+var_158], 12Eh
0x14000b60d  mov     r9d, 20000h
0x14000b613  xor     r8d, r8d
0x14000b616  mov     edx, 0C0000032h
0x14000b61b  mov     rcx, rsi
0x14000b61e  call    CdRaiseStatusEx
0x14001b28d  push    rbp
0x14001b28f  sub     rsp, 30h
0x14001b293  mov     rbp, rdx
0x14001b296  cmp     byte ptr [rbp+31h], 0
0x14001b29a  jz      short loc_14001B2F1
0x14001b29c  mov     rcx, [rbp+60h]
0x14001b2a0  mov     rcx, [rcx+8]; Resource
0x14001b2a4  call    cs:__imp_ExReleaseResourceLite
0x14001b2ab  nop     dword ptr [rax+rax+00h]
0x14001b2b0  mov     rcx, [rbp+78h]; Bcb
0x14001b2b4  test    rcx, rcx
0x14001b2b7  jz      short loc_14001B2CD
0x14001b2b9  call    cs:__imp_CcUnpinData
0x14001b2c0  nop     dword ptr [rax+rax+00h]
0x14001b2c5  mov     qword ptr [rbp+78h], 0
0x14001b2cd  test    byte ptr [rbp+0A9h], 1
0x14001b2d4  jz      short loc_14001B2F1
0x14001b2d6  mov     rcx, [rbp+0D0h]; P
0x14001b2dd  test    rcx, rcx
0x14001b2e0  jz      short loc_14001B2F1
0x14001b2e2  xor     edx, edx; Tag
0x14001b2e4  call    cs:__imp_ExFreePoolWithTag
0x14001b2eb  nop     dword ptr [rax+rax+00h]
0x14001b2f0  nop
0x14001b2f1  cmp     byte ptr [rbp+30h], 0
0x14001b2f5  jz      short loc_14001B32D
0x14001b2f7  mov     rcx, [rbp+188h]
0x14001b2fe  sub     dword ptr [rcx+0C0h], 1
0x14001b305  jnz     short loc_14001B32D
0x14001b307  mov     qword ptr [rcx+0B8h], 0
0x14001b312  mov     rcx, [rcx+0C8h]
0x14001b319  add     rcx, 88h; FastMutex
0x14001b320  call    cs:__imp_ExReleaseFastMutex
0x14001b327  nop     dword ptr [rax+rax+00h]
0x14001b32c  nop
0x14001b32d  add     rsp, 30h
0x14001b331  pop     rbp
0x14001b332  retn
```
