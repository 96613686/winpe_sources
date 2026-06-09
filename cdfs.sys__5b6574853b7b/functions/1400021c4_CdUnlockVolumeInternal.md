# CdUnlockVolumeInternal

- ea: `0x1400021c4`
- end: `0x140002241`
- name: `CdUnlockVolumeInternal`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140014e4c`
- `0x140016fe8`
- `0x14001734c`

## callees

- `0x1400021c4`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400021eb`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400021eb`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140002222`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140002222`

## pseudocode

```c
__int64 __fastcall CdUnlockVolumeInternal(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 Irql; // [rsp+30h] [rbp+8h] BYREF

  Irql = a1;
  LOBYTE(Irql) = 0;
  v5 = -1073741782;
  IoAcquireVpbSpinLock((PKIRQL)&Irql);
  v6 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v6 + 4) & 2) != 0 && a3 == *(_QWORD *)(a2 + 24) )
  {
    *(_DWORD *)(a2 + 48) &= ~0x10u;
    *(_WORD *)(v6 + 4) &= ~2u;
    v5 = 0;
    *(_QWORD *)(a2 + 24) = 0;
  }
  IoReleaseVpbSpinLock(Irql);
  return v5;
}

```

## disassembly

```asm
0x1400021c4  mov     rax, rsp
0x1400021c7  mov     [rax+10h], rbx
0x1400021cb  mov     [rax+18h], rsi
0x1400021cf  mov     [rax+8], rcx
0x1400021d3  push    rdi
0x1400021d4  sub     rsp, 20h
0x1400021d8  lea     rcx, [rax+8]; Irql
0x1400021dc  mov     byte ptr [rax+8], 0
0x1400021e0  mov     rsi, r8
0x1400021e3  mov     rbx, rdx
0x1400021e6  mov     edi, 0C000002Ah
0x1400021eb  call    cs:__imp_IoAcquireVpbSpinLock
0x1400021f2  nop     dword ptr [rax+rax+00h]
0x1400021f7  mov     rcx, [rbx+8]
0x1400021fb  test    byte ptr [rcx+4], 2
0x1400021ff  jz      short loc_14000221E
0x140002201  cmp     rsi, [rbx+18h]
0x140002205  jnz     short loc_14000221E
0x140002207  and     dword ptr [rbx+30h], 0FFFFFFEFh
0x14000220b  mov     eax, 0FFFDh
0x140002210  and     [rcx+4], ax
0x140002214  xor     edi, edi
0x140002216  mov     qword ptr [rbx+18h], 0
0x14000221e  mov     cl, byte ptr [rsp+28h+Irql]; Irql
0x140002222  call    cs:__imp_IoReleaseVpbSpinLock
0x140002229  nop     dword ptr [rax+rax+00h]
0x14000222e  mov     rbx, [rsp+28h+arg_8]
0x140002233  mov     eax, edi
0x140002235  mov     rsi, [rsp+28h+arg_10]
0x14000223a  add     rsp, 20h
0x14000223e  pop     rdi
0x14000223f  retn
```
