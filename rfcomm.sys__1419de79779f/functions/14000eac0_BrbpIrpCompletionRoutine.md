# BrbpIrpCompletionRoutine

- ea: `0x14000eac0`
- end: `0x14000ebcb`
- name: `BrbpIrpCompletionRoutine`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000eac0`
- `0x14000f60c`
- `0x14001a49c`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eb38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eb38`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb6e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb6e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000eb9d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000eb9d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000eaeb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000eaeb`

## pseudocode

```c
__int64 __fastcall BrbpIrpCompletionRoutine(__int64 a1, IRP *a2, __int64 *a3)
{
  __int64 v3; // rbp
  void *v5; // rsi
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  unsigned int Status; // r15d
  __int64 *v11; // rdx
  __int64 **v12; // rax

  v3 = a3[2];
  v5 = (void *)a3[4];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    WPP_RECORDER_SF_qqddhd(WPP_GLOBAL_Control->DeviceExtension, v7, v8, v9);
  }
  Status = a2->IoStatus.Status;
  *(_BYTE *)(v3 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 24));
  v11 = (__int64 *)*a3;
  if ( *(__int64 **)(*a3 + 8) != a3 || (v12 = (__int64 **)a3[1], *v12 != a3) )
    __fastfail(3u);
  *v12 = v11;
  v11[1] = (__int64)v12;
  a3[1] = (__int64)a3;
  *a3 = (__int64)a3;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 24), *(_BYTE *)(v3 + 32));
  ((void (__fastcall *)(__int64, void *, __int64, _QWORD))a3[6])(v3, v5, a3[5], Status);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 40), v5, 0x20u);
  IrpFreeWithContext(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000eac0  push    rbx
0x14000eac2  push    rbp
0x14000eac3  push    rsi
0x14000eac4  push    rdi
0x14000eac5  push    r14
0x14000eac7  push    r15
0x14000eac9  sub     rsp, 68h
0x14000eacd  mov     rbp, [r8+10h]
0x14000ead1  mov     rbx, r8
0x14000ead4  mov     rsi, [r8+20h]
0x14000ead8  mov     r14, rdx
0x14000eadb  lea     rax, WPP_RECORDER_INITIALIZED
0x14000eae2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eae9  jz      short loc_14000EB30
0x14000eaeb  call    cs:__imp_KeGetCurrentIrql
0x14000eaf2  nop     dword ptr [rax+rax+00h]
0x14000eaf7  movzx   ecx, byte ptr [rsi+20h]
0x14000eafb  movzx   eax, al
0x14000eafe  mov     [rsp+98h+var_48], eax
0x14000eb02  mov     eax, [rsi+1Ch]
0x14000eb05  mov     [rsp+98h+var_50], cx
0x14000eb0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb11  mov     [rsp+98h+var_58], eax
0x14000eb15  mov     eax, [r14+30h]
0x14000eb19  mov     [rsp+98h+var_60], eax
0x14000eb1d  mov     rcx, [rcx+40h]
0x14000eb21  mov     [rsp+98h+var_68], r14
0x14000eb26  mov     [rsp+98h+var_70], rsi
0x14000eb2b  call    WPP_RECORDER_SF_qqddhd
0x14000eb30  mov     r15d, [r14+30h]
0x14000eb34  lea     rcx, [rbp+18h]; SpinLock
0x14000eb38  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000eb3f  nop     dword ptr [rax+rax+00h]
0x14000eb44  mov     [rbp+20h], al
0x14000eb47  mov     rdx, [rbx]
0x14000eb4a  cmp     [rdx+8], rbx
0x14000eb4e  jnz     short loc_14000EBC4
0x14000eb50  mov     rax, [rbx+8]
0x14000eb54  cmp     [rax], rbx
0x14000eb57  jnz     short loc_14000EBC4
0x14000eb59  mov     [rax], rdx
0x14000eb5c  lea     rcx, [rbp+18h]; SpinLock
0x14000eb60  mov     [rdx+8], rax
0x14000eb64  mov     [rbx+8], rbx
0x14000eb68  mov     [rbx], rbx
0x14000eb6b  mov     dl, [rbp+20h]; NewIrql
0x14000eb6e  call    cs:__imp_KeReleaseSpinLock
0x14000eb75  nop     dword ptr [rax+rax+00h]
0x14000eb7a  mov     rax, [rbx+30h]
0x14000eb7e  mov     r9d, r15d
0x14000eb81  mov     r8, [rbx+28h]
0x14000eb85  mov     rdx, rsi
0x14000eb88  mov     rcx, rbp
0x14000eb8b  call    _guard_dispatch_icall
0x14000eb90  lea     rcx, [rbp+28h]; RemoveLock
0x14000eb94  mov     r8d, 20h ; ' '; RemlockSize
0x14000eb9a  mov     rdx, rsi; Tag
0x14000eb9d  call    cs:__imp_IoReleaseRemoveLockEx
0x14000eba4  nop     dword ptr [rax+rax+00h]
0x14000eba9  mov     rcx, r14; Irp
0x14000ebac  call    IrpFreeWithContext
0x14000ebb1  mov     eax, 0C0000016h
0x14000ebb6  add     rsp, 68h
0x14000ebba  pop     r15
0x14000ebbc  pop     r14
0x14000ebbe  pop     rdi
0x14000ebbf  pop     rsi
0x14000ebc0  pop     rbp
0x14000ebc1  pop     rbx
0x14000ebc2  retn
0x14000ebc4  mov     ecx, 3
0x14000ebc9  int     29h; Win8: RtlFailFast(ecx)
```
