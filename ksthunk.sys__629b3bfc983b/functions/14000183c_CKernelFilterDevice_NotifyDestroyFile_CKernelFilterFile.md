# CKernelFilterDevice::NotifyDestroyFile(CKernelFilterFile *)

- ea: `0x14000183c`
- end: `0x1400018a6`
- name: `?NotifyDestroyFile@CKernelFilterDevice@@QEAAJPEAVCKernelFilterFile@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(CKernelFilterDevice *__hidden this, struct CKernelFilterFile *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a318`
- `0x14000ad00`

## callees

- `0x14000183c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001885`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001885`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001850`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001850`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::NotifyDestroyFile(KSPIN_LOCK *this, struct CKernelFilterFile *a2)
{
  KSPIN_LOCK *v2; // rdi
  KIRQL v4; // al
  _QWORD *v5; // rbx
  __int64 v6; // r8
  _QWORD *v7; // rdx

  v2 = this + 1;
  v4 = KeAcquireSpinLockRaiseToDpc(this + 1);
  v5 = (_QWORD *)((char *)a2 + 8);
  v6 = *v5;
  if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  *v5 = 0;
  KeReleaseSpinLock(v2, v4);
  return 0;
}

```

## disassembly

```asm
0x14000183c  mov     [rsp+arg_0], rbx
0x140001841  push    rdi
0x140001842  sub     rsp, 20h
0x140001846  lea     rdi, [rcx+8]
0x14000184a  mov     rbx, rdx
0x14000184d  mov     rcx, rdi; SpinLock
0x140001850  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001857  nop     dword ptr [rax+rax+00h]
0x14000185c  add     rbx, 8
0x140001860  mov     r8, [rbx]
0x140001863  cmp     [r8+8], rbx
0x140001867  jnz     short loc_14000189F
0x140001869  mov     rdx, [rbx+8]
0x14000186d  cmp     [rdx], rbx
0x140001870  jnz     short loc_14000189F
0x140001872  mov     [rdx], r8
0x140001875  mov     rcx, rdi; SpinLock
0x140001878  mov     [r8+8], rdx
0x14000187c  mov     dl, al; NewIrql
0x14000187e  mov     qword ptr [rbx], 0
0x140001885  call    cs:__imp_KeReleaseSpinLock
0x14000188c  nop     dword ptr [rax+rax+00h]
0x140001891  mov     rbx, [rsp+28h+arg_0]
0x140001896  xor     eax, eax
0x140001898  add     rsp, 20h
0x14000189c  pop     rdi
0x14000189d  retn
0x14000189f  mov     ecx, 3
0x1400018a4  int     29h; Win8: RtlFailFast(ecx)
```
