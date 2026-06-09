# CKernelFilterDevice::NotifyNewFile(CKernelFilterFile *)

- ea: `0x1400018ac`
- end: `0x14000191e`
- name: `?NotifyNewFile@CKernelFilterDevice@@AEAAJPEAVCKernelFilterFile@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CKernelFilterDevice *__hidden this, struct CKernelFilterFile *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a400`

## callees

- `0x1400018ac`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400018ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018ff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400018c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400018c8`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::NotifyNewFile(KSPIN_LOCK *this, struct CKernelFilterFile *a2)
{
  KSPIN_LOCK *v2; // rdi
  KIRQL v5; // al
  char **v6; // rcx
  char *v7; // rbx

  v2 = this + 1;
  v5 = KeAcquireSpinLockRaiseToDpc(this + 1);
  v6 = (char **)this[3];
  v7 = (char *)(this + 2);
  if ( *v6 != v7 )
    __fastfail(3u);
  *((_QWORD *)a2 + 2) = v6;
  *((_QWORD *)a2 + 1) = v7;
  *v6 = (char *)a2 + 8;
  *((_QWORD *)v7 + 1) = (char *)a2 + 8;
  KeReleaseSpinLock(v2, v5);
  return 0;
}

```

## disassembly

```asm
0x1400018ac  mov     [rsp+arg_0], rbx
0x1400018b1  mov     [rsp+arg_8], rsi
0x1400018b6  push    rdi
0x1400018b7  sub     rsp, 20h
0x1400018bb  lea     rdi, [rcx+8]
0x1400018bf  mov     rbx, rcx
0x1400018c2  mov     rcx, rdi; SpinLock
0x1400018c5  mov     rsi, rdx
0x1400018c8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400018cf  nop     dword ptr [rax+rax+00h]
0x1400018d4  mov     rcx, [rbx+18h]
0x1400018d8  add     rbx, 10h
0x1400018dc  mov     dl, al; NewIrql
0x1400018de  cmp     [rcx], rbx
0x1400018e1  jz      short loc_1400018EA
0x1400018e3  mov     ecx, 3
0x1400018e8  int     29h; Win8: RtlFailFast(ecx)
0x1400018ea  lea     rax, [rsi+8]
0x1400018ee  mov     [rax+8], rcx
0x1400018f2  mov     [rax], rbx
0x1400018f5  mov     [rcx], rax
0x1400018f8  mov     rcx, rdi; SpinLock
0x1400018fb  mov     [rbx+8], rax
0x1400018ff  call    cs:__imp_KeReleaseSpinLock
0x140001906  nop     dword ptr [rax+rax+00h]
0x14000190b  mov     rbx, [rsp+28h+arg_0]
0x140001910  xor     eax, eax
0x140001912  mov     rsi, [rsp+28h+arg_8]
0x140001917  add     rsp, 20h
0x14000191b  pop     rdi
0x14000191c  retn
```
