# FatSingleAsync

- ea: `0x14002e6ac`
- end: `0x14002e7d5`
- name: `FatSingleAsync`
- size: `297`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002d918`
- `0x14004573c`
- `0x14004af08`

## callees

- `0x140001ef8`
- `0x14002e6ac`

## import_xrefs

- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14002e7b9`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14002e7b9`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002e764`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002e77d`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002e764`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x14002e77d`

## pseudocode

```c
__int64 __fastcall FatSingleAsync(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  _DWORD *v5; // rbx
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(__int64, __int64, unsigned int *); // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  char v13; // r14
  _BYTE *v14; // rcx
  __int64 v15; // rdi
  void *v16; // rdx
  struct _ERESOURCE *v17; // rcx
  struct _ERESOURCE *v18; // rcx
  _DWORD *v19; // rcx
  __int64 result; // rax
  unsigned int v21; // eax
  __int64 v22; // rdx

  v5 = (_DWORD *)(a1 + 68);
  if ( *(struct _KTHREAD **)(a2 + 880) == KeGetCurrentThread() )
    *v5 |= 0x1000u;
  v9 = *(_QWORD *)(a1 + 80);
  v10 = (__int64 (__fastcall *)(__int64, __int64, unsigned int *))FatSingleSyncCompletionRoutine;
  if ( (*v5 & 2) == 0 )
    v10 = FatSingleAsyncCompletionRoutine;
  v11 = *(_QWORD *)(a5 + 184);
  *(_QWORD *)(v11 - 16) = v10;
  *(_QWORD *)(v11 - 8) = v9;
  *(_BYTE *)(v11 - 69) = -32;
  v12 = *(_QWORD *)(a5 + 184);
  v13 = *(_BYTE *)(a1 + 64);
  *(_BYTE *)(v12 - 72) = v13;
  v14 = (_BYTE *)(v12 - 70);
  *(_DWORD *)(v12 - 64) = a4;
  *(_QWORD *)(v12 - 48) = a3;
  if ( (*v5 & 4) != 0 )
    *v14 |= 4u;
  if ( (*v5 & 0x1000) != 0 )
    *v14 |= 2u;
  if ( (*v5 & 2) == 0 )
  {
    v15 = *(_QWORD *)(a1 + 80);
    v16 = *(void **)(v15 + 40);
    if ( ((unsigned __int8)v16 & 3) != 0 )
    {
      v17 = *(struct _ERESOURCE **)(v15 + 24);
      if ( v17 )
        ExSetResourceOwnerPointer(v17, v16);
      v18 = *(struct _ERESOURCE **)(v15 + 32);
      if ( v18 )
        ExSetResourceOwnerPointer(v18, *(PVOID *)(v15 + 40));
    }
  }
  v19 = *(_DWORD **)(a1 + 80);
  *v19 = *v5;
  result = FatLowLevelReadWrite(v19, *(_QWORD *)(a2 + 136), a5);
  if ( FatDiskAccountingEnabled )
  {
    v21 = 0;
    v22 = a4;
    if ( v13 != 4 )
    {
      v22 = 0;
      v21 = a4;
    }
    return FsRtlUpdateDiskCounters(v21, v22);
  }
  return result;
}

```

## disassembly

```asm
0x14002e6ac  push    rbx
0x14002e6ae  push    rbp
0x14002e6af  push    rsi
0x14002e6b0  push    rdi
0x14002e6b1  push    r13
0x14002e6b3  push    r14
0x14002e6b5  push    r15
0x14002e6b7  sub     rsp, 20h
0x14002e6bb  mov     rax, gs:188h
0x14002e6c4  lea     rbx, [rcx+44h]
0x14002e6c8  mov     ebp, r9d
0x14002e6cb  mov     r15, rdx
0x14002e6ce  mov     rsi, rcx
0x14002e6d1  mov     r10d, 1000h
0x14002e6d7  cmp     [rdx+370h], rax
0x14002e6de  jnz     short loc_14002E6E3
0x14002e6e0  or      [rbx], r10d
0x14002e6e3  mov     rdx, [rcx+50h]
0x14002e6e7  lea     r9, FatSingleAsyncCompletionRoutine
0x14002e6ee  mov     eax, [rbx]
0x14002e6f0  mov     r11b, 2
0x14002e6f3  mov     r13, [rsp+58h+arg_20]
0x14002e6fb  test    r11b, al
0x14002e6fe  lea     rax, FatSingleSyncCompletionRoutine
0x14002e705  cmovz   rax, r9
0x14002e709  mov     rcx, [r13+0B8h]
0x14002e710  mov     [rcx-10h], rax
0x14002e714  mov     [rcx-8], rdx
0x14002e718  mov     byte ptr [rcx-45h], 0E0h
0x14002e71c  mov     rax, [r13+0B8h]
0x14002e723  mov     r14b, [rsi+40h]
0x14002e727  mov     [rax-48h], r14b
0x14002e72b  lea     rcx, [rax-46h]
0x14002e72f  mov     [rax-40h], ebp
0x14002e732  mov     [rax-30h], r8
0x14002e736  mov     eax, [rbx]
0x14002e738  test    al, 4
0x14002e73a  jz      short loc_14002E73F
0x14002e73c  or      byte ptr [rcx], 4
0x14002e73f  test    [rbx], r10d
0x14002e742  jz      short loc_14002E747
0x14002e744  or      [rcx], r11b
0x14002e747  mov     eax, [rbx]
0x14002e749  test    r11b, al
0x14002e74c  jnz     short loc_14002E789
0x14002e74e  mov     rdi, [rsi+50h]
0x14002e752  mov     rdx, [rdi+28h]; OwnerPointer
0x14002e756  test    dl, 3
0x14002e759  jz      short loc_14002E789
0x14002e75b  mov     rcx, [rdi+18h]; Resource
0x14002e75f  test    rcx, rcx
0x14002e762  jz      short loc_14002E770
0x14002e764  call    cs:__imp_ExSetResourceOwnerPointer
0x14002e76b  nop     dword ptr [rax+rax+00h]
0x14002e770  mov     rcx, [rdi+20h]; Resource
0x14002e774  test    rcx, rcx
0x14002e777  jz      short loc_14002E789
0x14002e779  mov     rdx, [rdi+28h]; OwnerPointer
0x14002e77d  call    cs:__imp_ExSetResourceOwnerPointer
0x14002e784  nop     dword ptr [rax+rax+00h]
0x14002e789  mov     rcx, [rsi+50h]
0x14002e78d  mov     r8, r13
0x14002e790  mov     eax, [rbx]
0x14002e792  mov     [rcx], eax
0x14002e794  mov     rdx, [r15+88h]
0x14002e79b  call    FatLowLevelReadWrite
0x14002e7a0  cmp     cs:FatDiskAccountingEnabled, 0
0x14002e7a7  jz      short loc_14002E7C5
0x14002e7a9  xor     eax, eax
0x14002e7ab  mov     edx, ebp
0x14002e7ad  cmp     r14b, 4
0x14002e7b1  cmovnz  edx, eax
0x14002e7b4  cmovnz  eax, ebp
0x14002e7b7  mov     ecx, eax
0x14002e7b9  call    cs:__imp_FsRtlUpdateDiskCounters
0x14002e7c0  nop     dword ptr [rax+rax+00h]
0x14002e7c5  add     rsp, 20h
0x14002e7c9  pop     r15
0x14002e7cb  pop     r14
0x14002e7cd  pop     r13
0x14002e7cf  pop     rdi
0x14002e7d0  pop     rsi
0x14002e7d1  pop     rbp
0x14002e7d2  pop     rbx
0x14002e7d3  retn
```
