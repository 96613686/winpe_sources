# NsippFindIrp

- ea: `0x140004f90`
- end: `0x14000505a`
- name: `NsippFindIrp`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004e30`

## callees

- `0x140004f90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004fae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004fae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005017`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000502f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005017`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000502f`

## pseudocode

```c
_QWORD *__fastcall NsippFindIrp(_QWORD **a1, __int64 a2, KSPIN_LOCK *a3, _QWORD *a4)
{
  _QWORD *v5; // rdi
  KIRQL v9; // al
  _QWORD *v10; // rbx
  KIRQL v11; // dl
  _QWORD *v12; // rcx
  _QWORD *v13; // rax

  v5 = 0;
  v9 = KeAcquireSpinLockRaiseToDpc(a3);
  v10 = *a1;
  v11 = v9;
  while ( v10 != a1 )
  {
    v5 = v10 - 21;
    if ( a2 && v5[12] == a2 || a4 && a4 == v5 )
    {
      *((_DWORD *)v5 + 12) = -1073741536;
      v5[7] = 0;
      _InterlockedExchange64(v5 + 13, 0);
      v12 = (_QWORD *)*v10;
      if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v13 = (_QWORD *)v10[1], (_QWORD *)*v13 != v10) )
        __fastfail(3u);
      *v13 = v12;
      v12[1] = v13;
      if ( v13 != v12 )
      {
        KeReleaseSpinLock(a3, v11);
        return v5;
      }
      break;
    }
    v10 = (_QWORD *)*v10;
  }
  KeReleaseSpinLock(a3, v11);
  if ( v10 == a1 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x140004f90  push    rbx
0x140004f92  push    rbp
0x140004f93  push    rsi
0x140004f94  push    rdi
0x140004f95  push    r14
0x140004f97  push    r15
0x140004f99  sub     rsp, 28h
0x140004f9d  mov     r14, rcx
0x140004fa0  xor     edi, edi
0x140004fa2  mov     rcx, r8; SpinLock
0x140004fa5  mov     rbp, r9
0x140004fa8  mov     r15, r8
0x140004fab  mov     rsi, rdx
0x140004fae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004fb5  nop     dword ptr [rax+rax+00h]
0x140004fba  mov     rbx, [r14]
0x140004fbd  movzx   edx, al; NewIrql
0x140004fc0  cmp     rbx, r14
0x140004fc3  jz      short loc_140005014
0x140004fc5  lea     rdi, [rbx-0A8h]
0x140004fcc  test    rsi, rsi
0x140004fcf  jz      short loc_140004FD7
0x140004fd1  cmp     [rdi+60h], rsi
0x140004fd5  jz      short loc_140004FE1
0x140004fd7  test    rbp, rbp
0x140004fda  jnz     short loc_14000504C
0x140004fdc  mov     rbx, [rbx]
0x140004fdf  jmp     short loc_140004FC0
0x140004fe1  mov     dword ptr [rdi+30h], 0C0000120h
0x140004fe8  xor     eax, eax
0x140004fea  mov     qword ptr [rdi+38h], 0
0x140004ff2  xchg    rax, [rdi+68h]
0x140004ff6  mov     rcx, [rbx]
0x140004ff9  cmp     [rcx+8], rbx
0x140004ffd  jnz     short loc_140005053
0x140004fff  mov     rax, [rbx+8]
0x140005003  cmp     [rax], rbx
0x140005006  jnz     short loc_140005053
0x140005008  mov     [rax], rcx
0x14000500b  mov     [rcx+8], rax
0x14000500f  cmp     rax, rcx
0x140005012  jnz     short loc_14000502C
0x140005014  mov     rcx, r15; SpinLock
0x140005017  call    cs:__imp_KeReleaseSpinLock
0x14000501e  nop     dword ptr [rax+rax+00h]
0x140005023  cmp     rbx, r14
0x140005026  jnz     short loc_14000503B
0x140005028  xor     eax, eax
0x14000502a  jmp     short loc_14000503E
0x14000502c  mov     rcx, r15; SpinLock
0x14000502f  call    cs:__imp_KeReleaseSpinLock
0x140005036  nop     dword ptr [rax+rax+00h]
0x14000503b  mov     rax, rdi
0x14000503e  add     rsp, 28h
0x140005042  pop     r15
0x140005044  pop     r14
0x140005046  pop     rdi
0x140005047  pop     rsi
0x140005048  pop     rbp
0x140005049  pop     rbx
0x14000504a  retn
0x14000504c  cmp     rbp, rdi
0x14000504f  jnz     short loc_140004FDC
0x140005051  jmp     short loc_140004FE1
0x140005053  mov     ecx, 3
0x140005058  int     29h; Win8: RtlFailFast(ecx)
```
