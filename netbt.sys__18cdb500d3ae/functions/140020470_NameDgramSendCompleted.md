# NameDgramSendCompleted

- ea: `0x140020470`
- end: `0x14002052b`
- name: `NameDgramSendCompleted`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000b810`
- `0x140020470`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020484`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140020484`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400204d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400204d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020499`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020499`

## pseudocode

```c
void __fastcall NameDgramSendCompleted(__int64 a1)
{
  KIRQL v2; // di

  v2 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  ExFreePoolWithTag(*(PVOID *)(a1 + 64), 0);
  *(_QWORD *)(a1 + 64) = 0;
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *(_DWORD *)(a1 + 20) - 1,
      84,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) - 1,
      67,
      (__int64)"minio\\netbt\\sys\\udpsend.c");
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
    FreeTracker(a1, 4);
  KeReleaseSpinLock(&SpinLock, v2);
}

```

## disassembly

```asm
0x140020470  mov     [rsp+arg_0], rbx
0x140020475  push    rdi
0x140020476  sub     rsp, 40h
0x14002047a  mov     rbx, rcx
0x14002047d  lea     rcx, SpinLock; SpinLock
0x140020484  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002048b  nop     dword ptr [rax+rax+00h]
0x140020490  mov     rcx, [rbx+40h]; P
0x140020494  xor     edx, edx; Tag
0x140020496  mov     dil, al
0x140020499  call    cs:__imp_ExFreePoolWithTag
0x1400204a0  nop     dword ptr [rax+rax+00h]
0x1400204a5  mov     qword ptr [rbx+40h], 0
0x1400204ad  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400204b4  jnz     short loc_1400204F0
0x1400204b6  or      eax, 0FFFFFFFFh
0x1400204b9  lock xadd [rbx+14h], eax
0x1400204be  cmp     eax, 1
0x1400204c1  jnz     short loc_1400204CE
0x1400204c3  lea     edx, [rax+3]
0x1400204c6  mov     rcx, rbx
0x1400204c9  call    FreeTracker
0x1400204ce  mov     dl, dil; NewIrql
0x1400204d1  lea     rcx, SpinLock; SpinLock
0x1400204d8  call    cs:__imp_KeReleaseSpinLock
0x1400204df  nop     dword ptr [rax+rax+00h]
0x1400204e4  mov     rbx, [rsp+48h+arg_0]
0x1400204e9  add     rsp, 40h
0x1400204ed  pop     rdi
0x1400204ee  retn
0x1400204f0  mov     r8d, [rbx+14h]
0x1400204f4  lea     rax, aMinioNetbtSysU; "minio\\netbt\\sys\\udpsend.c"
0x1400204fb  mov     [rsp+48h+var_10], rax
0x140020500  mov     edx, 54h ; 'T'
0x140020505  mov     [rsp+48h+var_18], 243h
0x14002050d  mov     r9, rbx
0x140020510  lea     ecx, [r8-1]
0x140020514  mov     [rsp+48h+var_20], ecx
0x140020518  mov     [rsp+48h+var_28], r8d
0x14002051d  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140020524  call    WPP_SF_qddds
0x140020529  jmp     short loc_1400204B6
```
