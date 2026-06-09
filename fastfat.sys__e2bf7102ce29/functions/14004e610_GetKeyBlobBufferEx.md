# GetKeyBlobBufferEx

- ea: `0x14004e610`
- end: `0x14004e8c5`
- name: `GetKeyBlobBufferEx`
- size: `693`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140007960`
- `0x1400528bc`
- `0x140053c18`
- `0x140053f20`
- `0x140054e5c`
- `0x140055574`
- `0x140056ccc`

## callees

- `0x14000c680`
- `0x14004e610`
- `0x14004e8cc`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004e725`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004e725`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e6b2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e78b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e6b2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e78b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e827`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e827`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004e696`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004e77c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004e696`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004e77c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004e6c8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004e6c8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004e852`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004e852`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004e65a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004e738`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004e65a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004e738`

## pseudocode

```c
_DWORD *__fastcall GetKeyBlobBufferEx(int a1, int a2)
{
  unsigned int KeyBlobLength; // eax
  SIZE_T Size; // r14
  struct _NPAGED_LOOKASIDE_LIST *v6; // rsi
  int v7; // ebp
  __int64 *i; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  __int64 (__fastcall *v20)(int, int, int, int, int); // rax

  KeyBlobLength = GetKeyBlobLength();
  Size = KeyBlobLength;
  if ( !KeyBlobLength )
    return 0;
  v6 = 0;
  if ( a1 == 26128 )
  {
    v7 = 268461584;
  }
  else
  {
    v7 = a1;
    if ( a1 == 26126 )
      v7 = 268461582;
  }
  ExAcquireFastMutex(&FastMutex);
  for ( i = (__int64 *)qword_140017748; i != &qword_140017748; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i - 4) == v7 && *((_DWORD *)i - 3) == (_DWORD)Size )
    {
      v6 = (struct _NPAGED_LOOKASIDE_LIST *)*(i - 1);
      break;
    }
  }
  ExReleaseFastMutex(&FastMutex);
  if ( !v6 )
  {
    v6 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(&stru_140017840);
    v9 = ExAllocateFromPagedLookasideList(&stru_1400177C0);
    v10 = v9;
    if ( v6 )
    {
      if ( v9 )
      {
        v9[2] = 0;
        v9[3] = 0;
        v9[1] = v6;
        *(_DWORD *)v9 = v7;
        *((_DWORD *)v9 + 1) = Size;
        ExInitializeNPagedLookasideList(v6, 0, 0, 0x200u, Size, 0x6D736645u, 0x1Eu);
        ExAcquireFastMutex(&FastMutex);
        v11 = qword_140017748;
        if ( *(__int64 **)(qword_140017748 + 8) != &qword_140017748 )
          __fastfail(3u);
        v10[2] = qword_140017748;
        v10[3] = &qword_140017748;
        *(_QWORD *)(v11 + 8) = v10 + 2;
        qword_140017748 = (__int64)(v10 + 2);
        ExReleaseFastMutex(&FastMutex);
        goto LABEL_19;
      }
      ExFreeToNPagedLookasideList(&stru_140017840, v6);
    }
    else if ( v9 )
    {
      ExFreeToPagedLookasideList(&stru_1400177C0, v9);
    }
    return 0;
  }
LABEL_19:
  v12 = ExAllocateFromNPagedLookasideList(v6);
  v13 = v12;
  if ( v12 )
  {
    memset(v12, 0, Size);
    v13[1] = a1;
    *v13 = Size;
    *((_QWORD *)v13 + 9) = v6;
    v13[6] = a2;
    v14 = a1 - 26113;
    if ( v14 )
    {
      v15 = v14 - 2;
      if ( !v15 )
      {
        *((_QWORD *)v13 + 2) = EfsDes3Enc;
        v20 = EfsDes3Dec;
        goto LABEL_37;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        v13[20] = 5;
LABEL_36:
        *((_QWORD *)v13 + 2) = &EfsCngDesEnc;
        v20 = EfsCngDesDec;
        goto LABEL_37;
      }
      v17 = v16 - 10;
      if ( !v17 || (v18 = v17 - 2) == 0 )
      {
        v13[20] = 1;
        *((_QWORD *)v13 + 11) = 0;
        *((_QWORD *)v13 + 2) = EfsAesEnc;
        v20 = (__int64 (__fastcall *)(int, int, int, int, int))EfsAesDec;
        goto LABEL_37;
      }
      v19 = v18 - 0x20000000;
      if ( !v19 || v19 == 0x20000000 )
      {
        v13[20] = 1;
        *((_QWORD *)v13 + 2) = EfsXtsAesEnc;
        v20 = (__int64 (__fastcall *)(int, int, int, int, int))EfsXtsAesDec;
        *((_QWORD *)v13 + 11) = 0;
LABEL_37:
        *((_QWORD *)v13 + 1) = v20;
        return v13;
      }
    }
    v13[20] = 4;
    goto LABEL_36;
  }
  return v13;
}

```

## disassembly

```asm
0x14004e610  push    rbx
0x14004e612  push    rbp
0x14004e613  push    rsi
0x14004e614  push    rdi
0x14004e615  push    r14
0x14004e617  push    r15
0x14004e619  sub     rsp, 48h
0x14004e61d  mov     r15d, edx
0x14004e620  mov     edi, ecx
0x14004e622  call    GetKeyBlobLength
0x14004e627  mov     r14d, eax
0x14004e62a  test    eax, eax
0x14004e62c  jz      loc_14004E833
0x14004e632  xor     esi, esi
0x14004e634  cmp     edi, 6610h
0x14004e63a  jnz     short loc_14004E643
0x14004e63c  mov     ebp, 10006610h
0x14004e641  jmp     short loc_14004E653
0x14004e643  cmp     edi, 660Eh
0x14004e649  mov     ebp, edi
0x14004e64b  mov     eax, 1000660Eh
0x14004e650  cmovz   ebp, eax
0x14004e653  lea     rcx, FastMutex; FastMutex
0x14004e65a  call    cs:__imp_ExAcquireFastMutex
0x14004e661  nop     dword ptr [rax+rax+00h]
0x14004e666  mov     rax, cs:qword_140017748
0x14004e66d  lea     rcx, qword_140017748
0x14004e674  jmp     short loc_14004E684
0x14004e676  cmp     [rax-10h], ebp
0x14004e679  jnz     short loc_14004E681
0x14004e67b  cmp     [rax-0Ch], r14d
0x14004e67f  jz      short loc_14004E68B
0x14004e681  mov     rax, [rax]
0x14004e684  cmp     rax, rcx
0x14004e687  jnz     short loc_14004E676
0x14004e689  jmp     short loc_14004E68F
0x14004e68b  mov     rsi, [rax-8]
0x14004e68f  lea     rcx, FastMutex; FastMutex
0x14004e696  call    cs:__imp_ExReleaseFastMutex
0x14004e69d  nop     dword ptr [rax+rax+00h]
0x14004e6a2  test    rsi, rsi
0x14004e6a5  jnz     loc_14004E788
0x14004e6ab  lea     rcx, stru_140017840; Lookaside
0x14004e6b2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004e6b9  nop     dword ptr [rax+rax+00h]
0x14004e6be  lea     rcx, stru_1400177C0; Lookaside
0x14004e6c5  mov     rsi, rax
0x14004e6c8  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14004e6cf  nop     dword ptr [rax+rax+00h]
0x14004e6d4  mov     rbx, rax
0x14004e6d7  test    rsi, rsi
0x14004e6da  jz      loc_14004E843
0x14004e6e0  test    rax, rax
0x14004e6e3  jz      loc_14004E81D
0x14004e6e9  mov     qword ptr [rax+10h], 0
0x14004e6f1  mov     r9d, 200h; Flags
0x14004e6f7  mov     qword ptr [rax+18h], 0
0x14004e6ff  xor     r8d, r8d; Free
0x14004e702  mov     [rsp+78h+Depth], 1Eh; Depth
0x14004e709  xor     edx, edx; Allocate
0x14004e70b  mov     [rsp+78h+Tag], 6D736645h; Tag
0x14004e713  mov     rcx, rsi; Lookaside
0x14004e716  mov     [rax+8], rsi
0x14004e71a  mov     [rax], ebp
0x14004e71c  mov     [rax+4], r14d
0x14004e720  mov     [rsp+78h+Size], r14; Size
0x14004e725  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004e72c  nop     dword ptr [rax+rax+00h]
0x14004e731  lea     rcx, FastMutex; FastMutex
0x14004e738  call    cs:__imp_ExAcquireFastMutex
0x14004e73f  nop     dword ptr [rax+rax+00h]
0x14004e744  mov     rcx, cs:qword_140017748
0x14004e74b  lea     rdx, qword_140017748
0x14004e752  cmp     [rcx+8], rdx
0x14004e756  jz      short loc_14004E75F
0x14004e758  mov     ecx, 3
0x14004e75d  int     29h; Win8: RtlFailFast(ecx)
0x14004e75f  lea     rax, [rbx+10h]
0x14004e763  mov     [rax], rcx
0x14004e766  mov     [rax+8], rdx
0x14004e76a  mov     [rcx+8], rax
0x14004e76e  lea     rcx, FastMutex; FastMutex
0x14004e775  mov     cs:qword_140017748, rax
0x14004e77c  call    cs:__imp_ExReleaseFastMutex
0x14004e783  nop     dword ptr [rax+rax+00h]
0x14004e788  mov     rcx, rsi; Lookaside
0x14004e78b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004e792  nop     dword ptr [rax+rax+00h]
0x14004e797  mov     rbx, rax
0x14004e79a  test    rax, rax
0x14004e79d  jz      loc_14004E8BD
0x14004e7a3  mov     r8, r14; Size
0x14004e7a6  xor     edx, edx; Val
0x14004e7a8  mov     rcx, rax; void *
0x14004e7ab  call    memset
0x14004e7b0  mov     [rbx+4], edi
0x14004e7b3  mov     [rbx], r14d
0x14004e7b6  mov     [rbx+48h], rsi
0x14004e7ba  mov     [rbx+18h], r15d
0x14004e7be  sub     edi, 6601h
0x14004e7c4  jz      loc_14004E8A0
0x14004e7ca  sub     edi, 2
0x14004e7cd  jz      loc_14004E88C
0x14004e7d3  sub     edi, 1
0x14004e7d6  jz      loc_14004E883
0x14004e7dc  sub     edi, 0Ah
0x14004e7df  jz      short loc_14004E860
0x14004e7e1  sub     edi, 2
0x14004e7e4  jz      short loc_14004E860
0x14004e7e6  mov     eax, 20000000h
0x14004e7eb  sub     edi, eax
0x14004e7ed  jz      short loc_14004E7F7
0x14004e7ef  cmp     edi, eax
0x14004e7f1  jnz     loc_14004E8A0
0x14004e7f7  lea     rax, EfsXtsAesEnc
0x14004e7fe  mov     dword ptr [rbx+50h], 1
0x14004e805  mov     [rbx+10h], rax
0x14004e809  lea     rax, EfsXtsAesDec
0x14004e810  mov     qword ptr [rbx+58h], 0
0x14004e818  jmp     loc_14004E8B9
0x14004e81d  mov     rdx, rsi; Entry
0x14004e820  lea     rcx, stru_140017840; Lookaside
0x14004e827  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004e82e  nop     dword ptr [rax+rax+00h]
0x14004e833  xor     eax, eax
0x14004e835  add     rsp, 48h
0x14004e839  pop     r15
0x14004e83b  pop     r14
0x14004e83d  pop     rdi
0x14004e83e  pop     rsi
0x14004e83f  pop     rbp
0x14004e840  pop     rbx
0x14004e841  retn
0x14004e843  test    rbx, rbx
0x14004e846  jz      short loc_14004E833
0x14004e848  mov     rdx, rbx; Entry
0x14004e84b  lea     rcx, stru_1400177C0; Lookaside
0x14004e852  call    cs:__imp_ExFreeToPagedLookasideList
0x14004e859  nop     dword ptr [rax+rax+00h]
0x14004e85e  jmp     short loc_14004E833
0x14004e860  lea     rax, EfsAesEnc
0x14004e867  mov     dword ptr [rbx+50h], 1
0x14004e86e  mov     qword ptr [rbx+58h], 0
0x14004e876  mov     [rbx+10h], rax
0x14004e87a  lea     rax, EfsAesDec
0x14004e881  jmp     short loc_14004E8B9
0x14004e883  mov     dword ptr [rbx+50h], 5
0x14004e88a  jmp     short loc_14004E8A7
0x14004e88c  lea     rax, EfsDes3Enc
0x14004e893  mov     [rbx+10h], rax
0x14004e897  lea     rax, EfsDes3Dec
0x14004e89e  jmp     short loc_14004E8B9
0x14004e8a0  mov     dword ptr [rbx+50h], 4
0x14004e8a7  lea     rax, EfsCngDesEnc
0x14004e8ae  mov     [rbx+10h], rax
0x14004e8b2  lea     rax, EfsCngDesDec
0x14004e8b9  mov     [rbx+8], rax
0x14004e8bd  mov     rax, rbx
0x14004e8c0  jmp     loc_14004E835
```
