# FatAdjustAllCleanVolumeTimers

- ea: `0x1400066a0`
- end: `0x1400067c1`
- name: `FatAdjustAllCleanVolumeTimers`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400068b0`

## callees

- `0x140005e48`
- `0x1400066a0`
- `0x14004d454`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140006751`
- `ntoskrnl!KeCancelTimer` at `0x140006751`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140006764`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140006764`
- `ntoskrnl!KeSetTimer` at `0x140006786`
- `ntoskrnl!KeSetTimer` at `0x140006786`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400067a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400067a5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400066bb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400066bb`

## pseudocode

```c
void __fastcall FatAdjustAllCleanVolumeTimers(char a1)
{
  __int64 v2; // rbx
  __int64 i; // rsi
  _BYTE *v4; // rcx
  __int64 v5; // rcx

  ExAcquireResourceSharedLite(&Resource, 1u);
  v2 = MEMORY[0xFFFFF78000000014];
  for ( i = qword_140017CB0; (__int64 *)i != &qword_140017CB0; i = *(_QWORD *)i )
  {
    v4 = (_BYTE *)(i + 1128);
    if ( v2 + 36000000000LL < *(_QWORD *)(i + 1112) )
      *v4 = 1;
    v2 = MEMORY[0xFFFFF78000000014];
    if ( *v4 && (unsigned __int8)FatTelemetryGuard(i - 120) )
      FatTelemetryPeriodicVolume(v5, i - 120);
    if ( (*(_DWORD *)(i + 80) & 0x40) == 0
      && (*(_DWORD *)(i + 80) & 0x10000) == 0
      && (*(_DWORD *)(i + 80) & 0x1000) == 0
      && (*(_DWORD *)(i + 80) & 4) != 0 )
    {
      KeCancelTimer((PKTIMER)(i + 832));
      KeRemoveQueueDpc((PRKDPC)(i + 768));
      if ( a1 )
        KeSetTimer((PKTIMER)(i + 832), (LARGE_INTEGER)-20000000LL, (PKDPC)(i + 768));
    }
  }
  ExReleaseResourceLite(&Resource);
}

```

## disassembly

```asm
0x1400066a0  push    rbx
0x1400066a2  push    rbp
0x1400066a3  push    rsi
0x1400066a4  push    rdi
0x1400066a5  push    r12
0x1400066a7  push    r14
0x1400066a9  push    r15
0x1400066ab  sub     rsp, 20h
0x1400066af  mov     r14b, cl
0x1400066b2  mov     dl, 1; Wait
0x1400066b4  lea     rcx, Resource; Resource
0x1400066bb  call    cs:__imp_ExAcquireResourceSharedLite
0x1400066c2  nop     dword ptr [rax+rax+00h]
0x1400066c7  mov     r12, 0FFFFF78000000014h
0x1400066d1  lea     r15, qword_140017CB0
0x1400066d8  mov     rbx, [r12]
0x1400066dc  mov     rsi, cs:qword_140017CB0
0x1400066e3  jmp     loc_140006795
0x1400066e8  mov     rax, 861C46800h
0x1400066f2  lea     rcx, [rsi+468h]
0x1400066f9  add     rax, rbx
0x1400066fc  cmp     rax, [rsi+458h]
0x140006703  jge     short loc_140006708
0x140006705  mov     byte ptr [rcx], 1
0x140006708  mov     rbx, [r12]
0x14000670c  cmp     byte ptr [rcx], 0
0x14000670f  jz      short loc_140006727
0x140006711  lea     rcx, [rsi-78h]
0x140006715  call    FatTelemetryGuard
0x14000671a  test    al, al
0x14000671c  jz      short loc_140006727
0x14000671e  lea     rdx, [rsi-78h]
0x140006722  call    FatTelemetryPeriodicVolume
0x140006727  mov     eax, [rsi+50h]
0x14000672a  test    al, 40h
0x14000672c  jnz     short loc_140006792
0x14000672e  mov     eax, [rsi+50h]
0x140006731  bt      eax, 10h
0x140006735  jb      short loc_140006792
0x140006737  mov     eax, [rsi+50h]
0x14000673a  bt      eax, 0Ch
0x14000673e  jb      short loc_140006792
0x140006740  mov     eax, [rsi+50h]
0x140006743  test    al, 4
0x140006745  jz      short loc_140006792
0x140006747  lea     rbp, [rsi+340h]
0x14000674e  mov     rcx, rbp; PKTIMER
0x140006751  call    cs:__imp_KeCancelTimer
0x140006758  nop     dword ptr [rax+rax+00h]
0x14000675d  lea     rcx, [rsi+300h]; Dpc
0x140006764  call    cs:__imp_KeRemoveQueueDpc
0x14000676b  nop     dword ptr [rax+rax+00h]
0x140006770  test    r14b, r14b
0x140006773  jz      short loc_140006792
0x140006775  lea     r8, [rsi+300h]; Dpc
0x14000677c  mov     rdx, 0FFFFFFFFFECED300h; DueTime
0x140006783  mov     rcx, rbp; Timer
0x140006786  call    cs:__imp_KeSetTimer
0x14000678d  nop     dword ptr [rax+rax+00h]
0x140006792  mov     rsi, [rsi]
0x140006795  cmp     rsi, r15
0x140006798  jnz     loc_1400066E8
0x14000679e  lea     rcx, Resource; Resource
0x1400067a5  call    cs:__imp_ExReleaseResourceLite
0x1400067ac  nop     dword ptr [rax+rax+00h]
0x1400067b1  add     rsp, 20h
0x1400067b5  pop     r15
0x1400067b7  pop     r14
0x1400067b9  pop     r12
0x1400067bb  pop     rdi
0x1400067bc  pop     rsi
0x1400067bd  pop     rbp
0x1400067be  pop     rbx
0x1400067bf  retn
```
