# InitiateRefresh

- ea: `0x140052480`
- end: `0x1400525c6`
- name: `InitiateRefresh`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003027c`

## callees

- `0x14000e408`
- `0x140040294`
- `0x140052480`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140052565`
- `ntoskrnl!KeDelayExecutionThread` at `0x140052565`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052494`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005257b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140052494`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005257b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052531`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052593`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400525af`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052531`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052593`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400525af`

## pseudocode

```c
void InitiateRefresh()
{
  KIRQL v0; // al
  KIRQL v1; // bl
  int v2; // edi
  int v3; // esi
  unsigned int i; // edx
  _QWORD **v5; // r8
  _QWORD *v6; // rax
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp+8h] BYREF

  v0 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v1 = v0;
  if ( (NodeType & 1) != 0 )
  {
    KeReleaseSpinLock(&SpinLock, v0);
  }
  else
  {
    v2 = 0;
    v3 = 0;
    for ( i = 0; (signed int)i < *(_DWORD *)qword_140039460; ++i )
    {
      v5 = (_QWORD **)((char *)qword_140039460 + 16 * i + 8);
      v6 = *v5;
      while ( v6 != v5 )
      {
        v6 = (_QWORD *)*v6;
        ++v3;
      }
    }
    while ( (byte_140039680 & 1) != 0 )
    {
      Interval.QuadPart = 0;
      if ( (BYTE2(xmmword_140038420) & 1) != 0 )
        WPP_SF_(1040, 15, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids);
      KeReleaseSpinLock(&SpinLock, v1);
      Interval.QuadPart = -2000LL * v3 * dword_1400395C0 * (unsigned __int16)word_1400395D8;
      KeDelayExecutionThread(0, 0, &Interval);
      if ( (unsigned int)++v2 >= 0xA )
        return;
      v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    }
    KeReleaseSpinLock(&SpinLock, v1);
    ReRegisterLocalNames(0, 0);
  }
}

```

## disassembly

```asm
0x140052480  push    rbx
0x140052482  push    rsi
0x140052483  push    rdi
0x140052484  push    r14
0x140052486  sub     rsp, 28h
0x14005248a  lea     r14, SpinLock
0x140052491  mov     rcx, r14; SpinLock
0x140052494  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005249b  nop     dword ptr [rax+rax+00h]
0x1400524a0  test    byte ptr cs:NodeType, 1
0x1400524a7  mov     bl, al
0x1400524a9  jnz     loc_1400525AA
0x1400524af  mov     rcx, cs:qword_140039460
0x1400524b6  xor     edi, edi
0x1400524b8  xor     esi, esi
0x1400524ba  xor     edx, edx
0x1400524bc  mov     r9d, [rcx]
0x1400524bf  test    r9d, r9d
0x1400524c2  jle     short loc_1400524EE
0x1400524c4  mov     r8, cs:qword_140039460
0x1400524cb  mov     ecx, edx
0x1400524cd  add     r8, 8
0x1400524d1  shl     rcx, 4
0x1400524d5  add     r8, rcx
0x1400524d8  mov     rax, [r8]
0x1400524db  jmp     short loc_1400524E2
0x1400524dd  mov     rax, [rax]
0x1400524e0  inc     esi
0x1400524e2  cmp     rax, r8
0x1400524e5  jnz     short loc_1400524DD
0x1400524e7  inc     edx
0x1400524e9  cmp     edx, r9d
0x1400524ec  jl      short loc_1400524C4
0x1400524ee  cmp     edi, 0Ah
0x1400524f1  jnb     loc_1400525BB
0x1400524f7  test    cs:byte_140039680, 1
0x1400524fe  jz      loc_14005258E
0x140052504  mov     qword ptr [rsp+48h+Interval], 0
0x14005250d  test    byte ptr cs:xmmword_140038420+2, 1
0x140052514  jz      short loc_14005252C
0x140052516  mov     edx, 0Fh
0x14005251b  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x140052522  mov     ecx, 410h
0x140052527  call    WPP_SF_
0x14005252c  mov     dl, bl; NewIrql
0x14005252e  mov     rcx, r14; SpinLock
0x140052531  call    cs:__imp_KeReleaseSpinLock
0x140052538  nop     dword ptr [rax+rax+00h]
0x14005253d  movzx   eax, cs:word_1400395D8
0x140052544  lea     r8, [rsp+48h+Interval]; Interval
0x140052549  imul    eax, cs:dword_1400395C0
0x140052550  xor     edx, edx; Alertable
0x140052552  imul    eax, esi
0x140052555  cdqe
0x140052557  imul    rcx, rax, 0FFFFFFFFFFFFF830h
0x14005255e  mov     qword ptr [rsp+48h+Interval], rcx
0x140052563  xor     ecx, ecx; WaitMode
0x140052565  call    cs:__imp_KeDelayExecutionThread
0x14005256c  nop     dword ptr [rax+rax+00h]
0x140052571  inc     edi
0x140052573  cmp     edi, 0Ah
0x140052576  jnb     short loc_1400525BB
0x140052578  mov     rcx, r14; SpinLock
0x14005257b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140052582  nop     dword ptr [rax+rax+00h]
0x140052587  mov     bl, al
0x140052589  jmp     loc_1400524EE
0x14005258e  mov     dl, bl; NewIrql
0x140052590  mov     rcx, r14; SpinLock
0x140052593  call    cs:__imp_KeReleaseSpinLock
0x14005259a  nop     dword ptr [rax+rax+00h]
0x14005259f  xor     edx, edx
0x1400525a1  xor     ecx, ecx
0x1400525a3  call    ReRegisterLocalNames
0x1400525a8  jmp     short loc_1400525BB
0x1400525aa  mov     dl, al; NewIrql
0x1400525ac  mov     rcx, r14; SpinLock
0x1400525af  call    cs:__imp_KeReleaseSpinLock
0x1400525b6  nop     dword ptr [rax+rax+00h]
0x1400525bb  add     rsp, 28h
0x1400525bf  pop     r14
0x1400525c1  pop     rdi
0x1400525c2  pop     rsi
0x1400525c3  pop     rbx
0x1400525c4  retn
```
