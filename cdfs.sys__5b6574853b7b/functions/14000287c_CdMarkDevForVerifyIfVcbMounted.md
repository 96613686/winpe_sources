# CdMarkDevForVerifyIfVcbMounted

- ea: `0x14000287c`
- end: `0x1400028d9`
- name: `CdMarkDevForVerifyIfVcbMounted`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400016b0`
- `0x14001a400`

## callees

- `0x14000287c`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002894`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002894`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400028bf`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400028bf`

## pseudocode

```c
char __fastcall CdMarkDevForVerifyIfVcbMounted(__int64 a1)
{
  char v2; // bl
  __int64 v3; // rax
  __int64 v4; // rdx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  Irql = 0;
  IoAcquireVpbSpinLock(&Irql);
  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD *)(v3 + 16);
  if ( *(_QWORD *)(v4 + 56) == v3 )
  {
    *(_DWORD *)(v4 + 48) |= 2u;
    v2 = 1;
  }
  else
  {
    *(_DWORD *)(a1 + 48) |= 0x200u;
  }
  IoReleaseVpbSpinLock(Irql);
  return v2;
}

```

## disassembly

```asm
0x14000287c  mov     [rsp+arg_8], rbx
0x140002881  push    rdi
0x140002882  sub     rsp, 20h
0x140002886  mov     rdi, rcx
0x140002889  xor     ebx, ebx
0x14000288b  lea     rcx, [rsp+28h+Irql]; Irql
0x140002890  mov     [rsp+28h+Irql], bl
0x140002894  call    cs:__imp_IoAcquireVpbSpinLock
0x14000289b  nop     dword ptr [rax+rax+00h]
0x1400028a0  mov     rax, [rdi+8]
0x1400028a4  mov     rdx, [rax+10h]
0x1400028a8  cmp     [rdx+38h], rax
0x1400028ac  jnz     short loc_1400028B6
0x1400028ae  or      dword ptr [rdx+30h], 2
0x1400028b2  mov     bl, 1
0x1400028b4  jmp     short loc_1400028BB
0x1400028b6  bts     dword ptr [rdi+30h], 9
0x1400028bb  mov     cl, [rsp+28h+Irql]; Irql
0x1400028bf  call    cs:__imp_IoReleaseVpbSpinLock
0x1400028c6  nop     dword ptr [rax+rax+00h]
0x1400028cb  mov     al, bl
0x1400028cd  mov     rbx, [rsp+28h+arg_8]
0x1400028d2  add     rsp, 20h
0x1400028d6  pop     rdi
0x1400028d7  retn
```
