# CdLockVolumeInternal

- ea: `0x140001fd0`
- end: `0x1400020c9`
- name: `CdLockVolumeInternal`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400141e0`
- `0x140017148`

## callees

- `0x140001fd0`
- `0x14000bcf8`
- `0x14000c374`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140002024`
- `ntoskrnl!ExReleaseResourceLite` at `0x140002024`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x14000206b`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x14000206b`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400020a3`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400020a3`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140002030`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140002030`

## pseudocode

```c
__int64 __fastcall CdLockVolumeInternal(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // esi
  int v7; // r14d
  NTSTATUS v8; // eax
  int v9; // r15d
  __int64 v11; // rcx
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  Irql = 0;
  v6 = a3 != 0 ? -1073741790 : -2147483631;
  v7 = a3 != 0;
  CdPurgeVolume(a1, a2, 0);
  ExReleaseResourceLite((PERESOURCE)(a2 + 128));
  v8 = CcWaitForCurrentLazyWriterActivity();
  *(_DWORD *)(a1 + 32) |= 4u;
  v9 = v8;
  CdAcquireResource(a1, a2 + 128, 0, 0);
  if ( v9 < 0 )
    return (unsigned int)v9;
  CdFspClose(a2);
  IoAcquireVpbSpinLock(&Irql);
  v11 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v11 + 4) & 2) == 0 && *(_DWORD *)(a2 + 56) == v7 && *(_DWORD *)(a2 + 64) == v7 + 3 )
  {
    *(_DWORD *)(a2 + 48) |= 0x10u;
    *(_WORD *)(v11 + 4) |= 2u;
    v6 = 0;
    *(_QWORD *)(a2 + 24) = a3;
  }
  IoReleaseVpbSpinLock(Irql);
  return v6;
}

```

## disassembly

```asm
0x140001fd0  mov     [rsp+arg_8], rbx
0x140001fd5  mov     [rsp+arg_10], rbp
0x140001fda  push    rsi
0x140001fdb  push    rdi
0x140001fdc  push    r12
0x140001fde  push    r14
0x140001fe0  push    r15
0x140001fe2  sub     rsp, 20h
0x140001fe6  mov     rax, r8
0x140001fe9  mov     [rsp+48h+Irql], 0
0x140001fee  neg     rax
0x140001ff1  mov     r12, r8
0x140001ff4  mov     rbp, rdx
0x140001ff7  mov     rdi, rcx
0x140001ffa  sbb     esi, esi
0x140001ffc  xor     r14d, r14d
0x140001fff  and     esi, 40000011h
0x140002005  add     esi, 80000011h
0x14000200b  test    r8, r8
0x14000200e  setnz   r14b
0x140002012  xor     r8d, r8d
0x140002015  call    CdPurgeVolume
0x14000201a  lea     rbx, [rbp+80h]
0x140002021  mov     rcx, rbx; Resource
0x140002024  call    cs:__imp_ExReleaseResourceLite
0x14000202b  nop     dword ptr [rax+rax+00h]
0x140002030  call    cs:__imp_CcWaitForCurrentLazyWriterActivity
0x140002037  nop     dword ptr [rax+rax+00h]
0x14000203c  or      dword ptr [rdi+20h], 4
0x140002040  xor     r9d, r9d
0x140002043  xor     r8d, r8d
0x140002046  mov     rdx, rbx
0x140002049  mov     rcx, rdi
0x14000204c  mov     r15d, eax
0x14000204f  call    CdAcquireResource
0x140002054  test    r15d, r15d
0x140002057  jns     short loc_14000205E
0x140002059  mov     eax, r15d
0x14000205c  jmp     short loc_1400020B1
0x14000205e  mov     rcx, rbp
0x140002061  call    CdFspClose
0x140002066  lea     rcx, [rsp+48h+Irql]; Irql
0x14000206b  call    cs:__imp_IoAcquireVpbSpinLock
0x140002072  nop     dword ptr [rax+rax+00h]
0x140002077  mov     rcx, [rbp+8]
0x14000207b  test    byte ptr [rcx+4], 2
0x14000207f  jnz     short loc_14000209F
0x140002081  cmp     [rbp+38h], r14d
0x140002085  jnz     short loc_14000209F
0x140002087  lea     eax, [r14+3]
0x14000208b  cmp     [rbp+40h], eax
0x14000208e  jnz     short loc_14000209F
0x140002090  or      dword ptr [rbp+30h], 10h
0x140002094  or      word ptr [rcx+4], 2
0x140002099  xor     esi, esi
0x14000209b  mov     [rbp+18h], r12
0x14000209f  mov     cl, [rsp+48h+Irql]; Irql
0x1400020a3  call    cs:__imp_IoReleaseVpbSpinLock
0x1400020aa  nop     dword ptr [rax+rax+00h]
0x1400020af  mov     eax, esi
0x1400020b1  mov     rbx, [rsp+48h+arg_8]
0x1400020b6  mov     rbp, [rsp+48h+arg_10]
0x1400020bb  add     rsp, 20h
0x1400020bf  pop     r15
0x1400020c1  pop     r14
0x1400020c3  pop     r12
0x1400020c5  pop     rdi
0x1400020c6  pop     rsi
0x1400020c7  retn
```
