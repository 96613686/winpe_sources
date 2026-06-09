# CdCheckForDismount

- ea: `0x1400024e0`
- end: `0x140002627`
- name: `CdCheckForDismount`
- size: `327`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x1400016b0`
- `0x140001d0c`
- `0x1400028e0`
- `0x14000c0c8`
- `0x14000c374`
- `0x1400142d8`
- `0x140015090`
- `0x140017148`
- `0x14001734c`
- `0x1400174c8`
- `0x14001af0c`

## callees

- `0x1400024e0`
- `0x140002630`
- `0x14000c374`
- `0x1400181a4`
- `0x140018a3c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140002522`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002522`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002566`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400025c8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400025fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002566`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400025c8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400025fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000260a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000260a`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002595`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002595`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400025ae`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400025e1`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400025ae`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400025e1`

## pseudocode

```c
char __fastcall CdCheckForDismount(__int64 a1, __int64 a2, char a3)
{
  struct _ERESOURCE *v3; // rbp
  char v7; // di
  bool v8; // zf
  __int64 v9; // rcx
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF

  v3 = (struct _ERESOURCE *)(a2 + 128);
  Irql = 0;
  CdAcquireResource(a1, a2 + 128, 0, 0);
  CdFspClose(a2);
  ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
  v7 = 1;
  v8 = *(_DWORD *)(a2 + 52) == 4;
  *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
  if ( v8 )
  {
    if ( !*(_DWORD *)(a2 + 60) )
    {
      IoAcquireVpbSpinLock(&Irql);
      if ( *(_DWORD *)(*(_QWORD *)(a2 + 8) + 28LL) == 1 )
      {
        IoReleaseVpbSpinLock(Irql);
        *(_QWORD *)(a2 + 392) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
        CdDeleteVcb(v9, a2);
        return 0;
      }
      IoReleaseVpbSpinLock(Irql);
    }
LABEL_10:
    *(_QWORD *)(a2 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
LABEL_11:
    ExReleaseResourceLite(v3);
    return v7;
  }
  if ( *(_DWORD *)(a2 + 64) > 3u && !a3 )
    goto LABEL_10;
  *(_QWORD *)(a2 + 392) = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
  v7 = CdDismountVcb(a1, a2);
  if ( v7 )
    goto LABEL_11;
  return v7;
}

```

## disassembly

```asm
0x1400024e0  push    rbx
0x1400024e2  push    rbp
0x1400024e3  push    rsi
0x1400024e4  push    rdi
0x1400024e5  push    r14
0x1400024e7  push    r15
0x1400024e9  sub     rsp, 28h
0x1400024ed  lea     rbp, [rdx+80h]
0x1400024f4  mov     [rsp+58h+Irql], 0
0x1400024f9  mov     r14b, r8b
0x1400024fc  mov     rbx, rdx
0x1400024ff  mov     rdx, rbp
0x140002502  xor     r9d, r9d
0x140002505  xor     r8d, r8d
0x140002508  mov     r15, rcx
0x14000250b  call    CdAcquireResource
0x140002510  mov     rcx, rbx
0x140002513  call    CdFspClose
0x140002518  lea     rsi, [rbx+150h]
0x14000251f  mov     rcx, rsi; FastMutex
0x140002522  call    cs:__imp_ExAcquireFastMutex
0x140002529  nop     dword ptr [rax+rax+00h]
0x14000252e  mov     rax, gs:188h
0x140002537  mov     edi, 1
0x14000253c  cmp     dword ptr [rbx+34h], 4
0x140002540  mov     [rbx+188h], rax
0x140002547  jz      short loc_14000258A
0x140002549  cmp     dword ptr [rbx+40h], 3
0x14000254d  jbe     short loc_140002558
0x14000254f  test    r14b, r14b
0x140002552  jz      loc_1400025ED
0x140002558  mov     rcx, rsi; FastMutex
0x14000255b  mov     qword ptr [rbx+188h], 0
0x140002566  call    cs:__imp_ExReleaseFastMutex
0x14000256d  nop     dword ptr [rax+rax+00h]
0x140002572  mov     rdx, rbx
0x140002575  mov     rcx, r15
0x140002578  call    CdDismountVcb
0x14000257d  mov     dil, al
0x140002580  test    al, al
0x140002582  jz      loc_140002616
0x140002588  jmp     short loc_140002607
0x14000258a  cmp     dword ptr [rbx+3Ch], 0
0x14000258e  jnz     short loc_1400025ED
0x140002590  lea     rcx, [rsp+58h+Irql]; Irql
0x140002595  call    cs:__imp_IoAcquireVpbSpinLock
0x14000259c  nop     dword ptr [rax+rax+00h]
0x1400025a1  mov     rax, [rbx+8]
0x1400025a5  mov     cl, [rsp+58h+Irql]; Irql
0x1400025a9  cmp     [rax+1Ch], edi
0x1400025ac  jnz     short loc_1400025E1
0x1400025ae  call    cs:__imp_IoReleaseVpbSpinLock
0x1400025b5  nop     dword ptr [rax+rax+00h]
0x1400025ba  mov     rcx, rsi; FastMutex
0x1400025bd  mov     qword ptr [rbx+188h], 0
0x1400025c8  call    cs:__imp_ExReleaseFastMutex
0x1400025cf  nop     dword ptr [rax+rax+00h]
0x1400025d4  mov     rdx, rbx
0x1400025d7  call    CdDeleteVcb
0x1400025dc  xor     dil, dil
0x1400025df  jmp     short loc_140002616
0x1400025e1  call    cs:__imp_IoReleaseVpbSpinLock
0x1400025e8  nop     dword ptr [rax+rax+00h]
0x1400025ed  mov     rcx, rsi; FastMutex
0x1400025f0  mov     qword ptr [rbx+188h], 0
0x1400025fb  call    cs:__imp_ExReleaseFastMutex
0x140002602  nop     dword ptr [rax+rax+00h]
0x140002607  mov     rcx, rbp; Resource
0x14000260a  call    cs:__imp_ExReleaseResourceLite
0x140002611  nop     dword ptr [rax+rax+00h]
0x140002616  mov     al, dil
0x140002619  add     rsp, 28h
0x14000261d  pop     r15
0x14000261f  pop     r14
0x140002621  pop     rdi
0x140002622  pop     rsi
0x140002623  pop     rbp
0x140002624  pop     rbx
0x140002625  retn
```
