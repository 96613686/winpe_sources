# FsmCloseCall

- ea: `0x1400122e0`
- end: `0x1400123ee`
- name: `FsmCloseCall`
- size: `270`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000fd0c`
- `0x14001083c`
- `0x1400109d0`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400123b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001230e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001230e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001231e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012331`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001231e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012331`

## pseudocode

```c
void __fastcall FsmCloseCall(PVOID Entry, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  int v4; // r15d
  int v6; // ebp
  KIRQL v8; // al
  bool v9; // cc
  char v10; // r14
  __int64 v11; // r8
  _WORD *v12; // [rsp+28h] [rbp-60h]

  v4 = *a4;
  v6 = a4[4];
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  *(_BYTE *)(a2 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 40));
  v9 = *(_DWORD *)(a3 + 88) <= 1u;
  *(_BYTE *)(a3 + 48) = v8;
  if ( v9 || (*(_DWORD *)(a3 + 60) & 0x4000) != 0 )
  {
    v11 = 2;
    if ( (_WORD)v4 != 2 )
    {
      LOWORD(v6) = 0;
      LOWORD(v11) = 6;
    }
    v10 = CloseCall2(a2, a3, v11, (unsigned __int16)v6);
  }
  else
  {
    *(_DWORD *)(a3 + 128) = -1073668064;
    *(_DWORD *)(a3 + 88) = 0;
    v10 = 0;
    SendControl(a2, a3, 0xEu, v4, v6, v12, 32);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 40), *(_BYTE *)(a3 + 48));
  if ( v10 )
    CompleteVcs(a2);
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
}

```

## disassembly

```asm
0x1400122e0  push    rbx
0x1400122e2  push    rbp
0x1400122e3  push    rsi
0x1400122e4  push    rdi
0x1400122e5  push    r12
0x1400122e7  push    r13
0x1400122e9  push    r14
0x1400122eb  push    r15
0x1400122ed  sub     rsp, 48h
0x1400122f1  movzx   r15d, word ptr [r9]
0x1400122f5  mov     rdi, rdx
0x1400122f8  movzx   ebp, word ptr [r9+8]
0x1400122fd  mov     rdx, rcx; Entry
0x140012300  mov     rbx, r8
0x140012303  mov     rcx, [rdi+18h]
0x140012307  add     rcx, 3C0h; Lookaside
0x14001230e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140012315  nop     dword ptr [rax+rax+00h]
0x14001231a  lea     rcx, [rdi+20h]; SpinLock
0x14001231e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012325  nop     dword ptr [rax+rax+00h]
0x14001232a  lea     rcx, [rbx+28h]; SpinLock
0x14001232e  mov     [rdi+28h], al
0x140012331  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012338  nop     dword ptr [rax+rax+00h]
0x14001233d  cmp     dword ptr [rbx+58h], 1
0x140012341  mov     [rbx+30h], al
0x140012344  jbe     short loc_140012381
0x140012346  test    dword ptr [rbx+3Ch], 4000h
0x14001234d  jnz     short loc_140012381
0x14001234f  xor     esi, esi
0x140012351  mov     [rsp+88h+var_58], 20h ; ' '
0x140012359  mov     r9d, r15d
0x14001235c  mov     dword ptr [rbx+80h], 0C0012020h
0x140012366  mov     rdx, rbx
0x140012369  mov     [rbx+58h], esi
0x14001236c  mov     rcx, rdi
0x14001236f  mov     [rsp+88h+var_68], ebp
0x140012373  lea     r8d, [rsi+0Eh]
0x140012377  mov     r14b, sil
0x14001237a  call    SendControl
0x14001237f  jmp     short loc_1400123A9
0x140012381  xor     esi, esi
0x140012383  mov     rdx, rbx
0x140012386  mov     rcx, rdi
0x140012389  lea     r8d, [rsi+2]
0x14001238d  cmp     r15w, r8w
0x140012391  lea     eax, [rsi+6]
0x140012394  cmovnz  bp, si
0x140012398  cmovnz  r8w, ax
0x14001239d  movzx   r9d, bp
0x1400123a1  call    CloseCall2
0x1400123a6  mov     r14b, al
0x1400123a9  mov     dl, [rbx+30h]; NewIrql
0x1400123ac  lea     rcx, [rbx+28h]; SpinLock
0x1400123b0  call    cs:__imp_KeReleaseSpinLock
0x1400123b7  nop     dword ptr [rax+rax+00h]
0x1400123bc  test    r14b, r14b
0x1400123bf  jz      short loc_1400123C9
0x1400123c1  mov     rcx, rdi
0x1400123c4  call    CompleteVcs
0x1400123c9  mov     dl, [rdi+28h]; NewIrql
0x1400123cc  lea     rcx, [rdi+20h]; SpinLock
0x1400123d0  call    cs:__imp_KeReleaseSpinLock
0x1400123d7  nop     dword ptr [rax+rax+00h]
0x1400123dc  add     rsp, 48h
0x1400123e0  pop     r15
0x1400123e2  pop     r14
0x1400123e4  pop     r13
0x1400123e6  pop     r12
0x1400123e8  pop     rdi
0x1400123e9  pop     rsi
0x1400123ea  pop     rbp
0x1400123eb  pop     rbx
0x1400123ec  retn
```
