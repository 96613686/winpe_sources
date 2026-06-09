# GetTracker

- ea: `0x14000b2f0`
- end: `0x14000b45b`
- name: `GetTracker`
- size: `363`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x140001664`
- `0x140006e2c`
- `0x140009844`
- `0x14000cca0`
- `0x14000d310`
- `0x14000d594`
- `0x14000e408`
- `0x14000efd4`
- `0x1400167d4`
- `0x140016c14`
- `0x140018d7c`
- `0x14001f524`
- `0x140022d04`
- `0x1400269a8`
- `0x1400304c8`
- `0x140047f20`
- `0x1400485e8`
- `0x14004f5d4`
- `0x140050860`

## callees

- `0x14000b2f0`
- `0x14000b464`
- `0x140040294`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b308`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b308`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b3c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b416`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b3c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b416`

## pseudocode

```c
__int64 __fastcall GetTracker(__int64 *a1, int a2)
{
  __int64 v3; // r14
  KIRQL v4; // al
  PVOID v5; // rcx
  KIRQL v6; // bp
  _QWORD *v7; // rdx
  unsigned int v8; // edi
  __int64 inited; // rax
  __int64 v10; // rbx
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  unsigned int v13; // ecx
  __int64 result; // rax

  v3 = a2;
  v4 = KeAcquireSpinLockRaiseToDpc(&Lock);
  v5 = qword_140039470;
  v6 = v4;
  if ( qword_140039470 != &qword_140039470 )
  {
    if ( *((PVOID **)qword_140039470 + 1) != &qword_140039470 )
      goto LABEL_11;
    v7 = *(_QWORD **)qword_140039470;
    if ( *(PVOID *)(*(_QWORD *)qword_140039470 + 8LL) != qword_140039470 )
      goto LABEL_11;
    --NumFreeTrackers;
    qword_140039470 = v7;
    v7[1] = &qword_140039470;
LABEL_5:
    v8 = -1073741670;
    inited = NbtAllocInitTracker(v5);
    v10 = inited;
    if ( !inited )
    {
LABEL_10:
      KeReleaseSpinLock(&Lock, v6);
      result = v8;
      *a1 = v10;
      return result;
    }
    *(_DWORD *)(inited + 432) = v3;
    v11 = (_QWORD *)qword_140039428;
    if ( *(__int64 **)qword_140039428 == &UsedTrackers )
    {
      v12 = (_QWORD *)(inited + 416);
      *v12 = &UsedTrackers;
      ++TrackTrackers[v3];
      v12[1] = v11;
      *v11 = v12;
      v13 = TrackTrackers[v3];
      qword_140039428 = (__int64)v12;
      if ( v13 > TrackerHighWaterMark[v3] )
        TrackerHighWaterMark[v3] = v13;
      v8 = 0;
      goto LABEL_10;
    }
LABEL_11:
    __fastfail(3u);
  }
  v5 = 0;
  if ( (unsigned __int16)word_14003950A < (unsigned __int16)word_14003950E )
    goto LABEL_5;
  KeReleaseSpinLock(&Lock, v4);
  if ( (byte_140038419 & 2) != 0 )
    WPP_SF_(777, 0xBu, (ULONGLONG)WPP_87eb87a187c337230802581752a3dec7_Traceguids);
  *a1 = 0;
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000b2f0  push    rbx
0x14000b2f2  push    rbp
0x14000b2f3  push    rsi
0x14000b2f4  push    rdi
0x14000b2f5  push    r14
0x14000b2f7  sub     rsp, 20h
0x14000b2fb  mov     rsi, rcx
0x14000b2fe  movsxd  r14, edx
0x14000b301  lea     rcx, Lock; SpinLock
0x14000b308  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b30f  nop     dword ptr [rax+rax+00h]
0x14000b314  mov     rcx, cs:qword_140039470; void *
0x14000b31b  movzx   ebp, al
0x14000b31e  lea     rax, qword_140039470
0x14000b325  cmp     rcx, rax
0x14000b328  jz      loc_14000B3F5
0x14000b32e  cmp     [rcx+8], rax
0x14000b332  jnz     loc_14000B3EE
0x14000b338  mov     rdx, [rcx]
0x14000b33b  cmp     [rdx+8], rcx
0x14000b33f  jnz     loc_14000B3EE
0x14000b345  dec     cs:NumFreeTrackers
0x14000b34b  mov     cs:qword_140039470, rdx
0x14000b352  mov     [rdx+8], rax
0x14000b356  mov     edi, 0C000009Ah
0x14000b35b  call    NbtAllocInitTracker
0x14000b360  mov     rbx, rax
0x14000b363  test    rax, rax
0x14000b366  jz      short loc_14000B3BC
0x14000b368  mov     [rax+1B0h], r14d
0x14000b36f  lea     rdx, UsedTrackers
0x14000b376  mov     rcx, cs:qword_140039428
0x14000b37d  cmp     [rcx], rdx
0x14000b380  jnz     short loc_14000B3EE
0x14000b382  add     rax, 1A0h
0x14000b388  mov     [rax], rdx
0x14000b38b  lea     rdx, cs:140000000h
0x14000b392  inc     rva TrackTrackers[rdx+r14*4]
0x14000b39a  mov     [rax+8], rcx
0x14000b39e  mov     [rcx], rax
0x14000b3a1  mov     ecx, rva TrackTrackers[rdx+r14*4]
0x14000b3a9  mov     cs:qword_140039428, rax
0x14000b3b0  cmp     ecx, rva TrackerHighWaterMark[rdx+r14*4]
0x14000b3b8  ja      short loc_14000B3E4
0x14000b3ba  xor     edi, edi
0x14000b3bc  movzx   edx, bpl; NewIrql
0x14000b3c0  lea     rcx, Lock; SpinLock
0x14000b3c7  call    cs:__imp_KeReleaseSpinLock
0x14000b3ce  nop     dword ptr [rax+rax+00h]
0x14000b3d3  mov     eax, edi
0x14000b3d5  mov     [rsi], rbx
0x14000b3d8  add     rsp, 20h
0x14000b3dc  pop     r14
0x14000b3de  pop     rdi
0x14000b3df  pop     rsi
0x14000b3e0  pop     rbp
0x14000b3e1  pop     rbx
0x14000b3e2  retn
0x14000b3e4  mov     rva TrackerHighWaterMark[rdx+r14*4], ecx
0x14000b3ec  jmp     short loc_14000B3BA
0x14000b3ee  mov     ecx, 3
0x14000b3f3  int     29h; Win8: RtlFailFast(ecx)
0x14000b3f5  movzx   eax, cs:word_14003950E
0x14000b3fc  xor     ecx, ecx
0x14000b3fe  cmp     cs:word_14003950A, ax
0x14000b405  jb      loc_14000B356
0x14000b40b  movzx   edx, bpl; NewIrql
0x14000b40f  lea     rcx, Lock; SpinLock
0x14000b416  call    cs:__imp_KeReleaseSpinLock
0x14000b41d  nop     dword ptr [rax+rax+00h]
0x14000b422  test    cs:byte_140038419, 2
0x14000b429  jnz     short loc_14000B443
0x14000b42b  mov     qword ptr [rsi], 0
0x14000b432  mov     eax, 0C000009Ah
0x14000b437  add     rsp, 20h
0x14000b43b  pop     r14
0x14000b43d  pop     rdi
0x14000b43e  pop     rsi
0x14000b43f  pop     rbp
0x14000b440  pop     rbx
0x14000b441  retn
0x14000b443  mov     edx, 0Bh
0x14000b448  lea     r8, WPP_87eb87a187c337230802581752a3dec7_Traceguids
0x14000b44f  mov     ecx, 309h
0x14000b454  call    WPP_SF_
0x14000b459  jmp     short loc_14000B42B
```
