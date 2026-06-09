# FIVolumeGetNext

- ea: `0x1400145b8`
- end: `0x140014640`
- name: `FIVolumeGetNext`
- size: `136`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d8cc`
- `0x14000df58`
- `0x140013d70`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x1400145b8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400145dc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400145dc`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001461f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001461f`

## pseudocode

```c
__int64 __fastcall FIVolumeGetNext(struct _EX_RUNDOWN_REF *a1)
{
  struct _EX_RUNDOWN_REF *Count; // rbx
  BOOLEAN v3; // si

  FILockExclusiveAcquire((__int64)&qword_140009388);
  if ( a1 )
  {
    Count = (struct _EX_RUNDOWN_REF *)a1->Count;
    ExReleaseRundownProtection(a1 + 2);
    a1 = 0;
  }
  else
  {
    Count = (struct _EX_RUNDOWN_REF *)qword_140009390;
  }
  v3 = 0;
  while ( Count != (struct _EX_RUNDOWN_REF *)&qword_140009390 )
  {
    a1 = Count;
    v3 = ExAcquireRundownProtection(Count + 2);
    if ( v3 )
      break;
    Count = (struct _EX_RUNDOWN_REF *)Count->Count;
  }
  FILockExclusiveRelease((__int64)&qword_140009388);
  return (unsigned __int64)a1 & -(__int64)(v3 != 0);
}

```

## disassembly

```asm
0x1400145b8  push    rbx
0x1400145ba  push    rbp
0x1400145bb  push    rsi
0x1400145bc  push    rdi
0x1400145bd  sub     rsp, 28h
0x1400145c1  mov     rdi, rcx
0x1400145c4  lea     rcx, qword_140009388
0x1400145cb  call    FILockExclusiveAcquire
0x1400145d0  test    rdi, rdi
0x1400145d3  jz      short loc_140014637
0x1400145d5  mov     rbx, [rdi]
0x1400145d8  lea     rcx, [rdi+10h]; RunRef
0x1400145dc  call    cs:__imp_ExReleaseRundownProtection
0x1400145e3  nop     dword ptr [rax+rax+00h]
0x1400145e8  xor     edi, edi
0x1400145ea  xor     sil, sil
0x1400145ed  lea     rbp, qword_140009390
0x1400145f4  cmp     rbx, rbp
0x1400145f7  jnz     short loc_140014618
0x1400145f9  lea     rcx, qword_140009388
0x140014600  call    FILockExclusiveRelease
0x140014605  neg     sil
0x140014608  sbb     rax, rax
0x14001460b  and     rax, rdi
0x14001460e  add     rsp, 28h
0x140014612  pop     rdi
0x140014613  pop     rsi
0x140014614  pop     rbp
0x140014615  pop     rbx
0x140014616  retn
0x140014618  lea     rcx, [rbx+10h]; RunRef
0x14001461c  mov     rdi, rbx
0x14001461f  call    cs:__imp_ExAcquireRundownProtection
0x140014626  nop     dword ptr [rax+rax+00h]
0x14001462b  mov     sil, al
0x14001462e  test    al, al
0x140014630  jnz     short loc_1400145F9
0x140014632  mov     rbx, [rbx]
0x140014635  jmp     short loc_1400145F4
0x140014637  mov     rbx, cs:qword_140009390
0x14001463e  jmp     short loc_1400145EA
```
