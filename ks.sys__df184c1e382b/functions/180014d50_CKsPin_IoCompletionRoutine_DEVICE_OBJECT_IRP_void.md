# CKsPin::IoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x180014d50`
- end: `0x180014edd`
- name: `?IoCompletionRoutine@CKsPin@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `397`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000374c`
- `0x180006dc0`
- `0x18000dddc`
- `0x180014d50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180014dd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180014dd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x180014e2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180014e2d`
- `ntoskrnl!IofCompleteRequest` at `0x180014e8c`
- `ntoskrnl!IofCompleteRequest` at `0x180014e8c`
- `ntoskrnl!KeSetEvent` at `0x180014ec0`
- `ntoskrnl!KeSetEvent` at `0x180014ec0`

## pseudocode

```c
__int64 __fastcall CKsPin::IoCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, char *a3)
{
  struct _IRP *v4; // rsi
  KIRQL v5; // r8
  char *v6; // rdx
  __int64 v7; // rax
  char **v8; // rcx
  IRP *v9; // rdi
  __int64 v10; // rcx
  NTSTATUS Status; // eax
  char v13; // [rsp+28h] [rbp-30h]

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v13 = (char)a2;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      65,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
      v13);
  }
  _InterlockedIncrement((volatile signed __int32 *)a3 + 204);
  _InterlockedIncrement((volatile signed __int32 *)a3 + 309);
  v4->Tail.Overlay.CurrentStackLocation->MajorFunction = 0;
  while ( *((_DWORD *)a3 + 204) )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a3 + 101);
    v6 = (char *)*((_QWORD *)a3 + 99);
    if ( v6 == a3 + 792 || *(v6 - 24) )
    {
      v9 = 0;
    }
    else
    {
      v7 = *(_QWORD *)v6;
      if ( *(char **)(*(_QWORD *)v6 + 8LL) != v6 || (v8 = (char **)*((_QWORD *)v6 + 1), *v8 != v6) )
        __fastfail(3u);
      v9 = (IRP *)*((_QWORD *)v6 - 1);
      *v8 = (char *)v7;
      *(_QWORD *)(v7 + 8) = v8;
      *(v6 - 24) = 14;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a3 + 101, v5);
    if ( !v9 )
      break;
    _InterlockedDecrement((volatile signed __int32 *)a3 + 204);
    if ( v9 != v4 )
      ++*((_DWORD *)a3 + 242);
    v10 = *((_QWORD *)a3 + 87);
    if ( v10 )
    {
      Status = v9->IoStatus.Status;
      if ( Status == -1073741808 || Status == -1073741436 )
        KspDiscardKsIrp(v10, (__int64)v9);
      else
        KspTransferKsIrp(v10, (__int64)v9);
    }
    else
    {
      IofCompleteRequest(v9, 0);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 309, 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)(a3 + 1240), 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x180014d50  push    rbx
0x180014d52  push    rbp
0x180014d53  push    rsi
0x180014d54  push    rdi
0x180014d55  push    r14
0x180014d57  sub     rsp, 30h
0x180014d5b  mov     rbx, r8
0x180014d5e  mov     rsi, rdx
0x180014d61  lea     rax, WPP_RECORDER_INITIALIZED
0x180014d68  xor     r14d, r14d
0x180014d6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180014d72  jz      short loc_180014DA6
0x180014d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d7b  cmp     [rcx+48h], r14w
0x180014d80  jz      short loc_180014DA6
0x180014d82  mov     rcx, [rcx+40h]
0x180014d86  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x180014d8d  mov     qword ptr [rsp+58h+var_30], rdx
0x180014d92  lea     r9d, [r14+41h]
0x180014d96  mov     dl, 5
0x180014d98  mov     [rsp+58h+var_38], rax
0x180014d9d  lea     r8d, [r14+1]
0x180014da1  call    WPP_RECORDER_SF_q
0x180014da6  lock inc dword ptr [rbx+330h]
0x180014dad  lock inc dword ptr [rbx+4D4h]
0x180014db4  mov     rax, [rsi+0B8h]
0x180014dbb  mov     [rax], r14b
0x180014dbe  cmp     [rbx+330h], r14d
0x180014dc5  jz      loc_180014EA4
0x180014dcb  lea     rbp, [rbx+328h]
0x180014dd2  mov     rcx, rbp; SpinLock
0x180014dd5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180014ddc  nop     dword ptr [rax+rax+00h]
0x180014de1  lea     rcx, [rbx+318h]
0x180014de8  mov     r8b, al
0x180014deb  mov     rdx, [rcx]
0x180014dee  cmp     rdx, rcx
0x180014df1  jz      short loc_180014E24
0x180014df3  cmp     [rdx-18h], r14b
0x180014df7  jnz     short loc_180014E24
0x180014df9  mov     rax, [rdx]
0x180014dfc  cmp     [rax+8], rdx
0x180014e00  jnz     loc_180014E9D
0x180014e06  mov     rcx, [rdx+8]
0x180014e0a  cmp     [rcx], rdx
0x180014e0d  jnz     loc_180014E9D
0x180014e13  mov     rdi, [rdx-8]
0x180014e17  mov     [rcx], rax
0x180014e1a  mov     [rax+8], rcx
0x180014e1e  mov     byte ptr [rdx-18h], 0Eh
0x180014e22  jmp     short loc_180014E27
0x180014e24  mov     rdi, r14
0x180014e27  mov     dl, r8b; NewIrql
0x180014e2a  mov     rcx, rbp; SpinLock
0x180014e2d  call    cs:__imp_KeReleaseSpinLock
0x180014e34  nop     dword ptr [rax+rax+00h]
0x180014e39  test    rdi, rdi
0x180014e3c  jz      short loc_180014EA4
0x180014e3e  lock dec dword ptr [rbx+330h]
0x180014e45  cmp     rdi, rsi
0x180014e48  jz      short loc_180014E50
0x180014e4a  inc     dword ptr [rbx+3C8h]
0x180014e50  mov     rcx, [rbx+2B8h]
0x180014e57  test    rcx, rcx
0x180014e5a  jz      short loc_180014E87
0x180014e5c  mov     eax, [rdi+30h]
0x180014e5f  cmp     eax, 0C0000010h
0x180014e64  jz      short loc_180014E7A
0x180014e66  cmp     eax, 0C0000184h
0x180014e6b  jz      short loc_180014E7A
0x180014e6d  mov     rdx, rdi
0x180014e70  call    KspTransferKsIrp
0x180014e75  jmp     loc_180014DBE
0x180014e7a  mov     rdx, rdi
0x180014e7d  call    KspDiscardKsIrp
0x180014e82  jmp     loc_180014DBE
0x180014e87  xor     edx, edx; PriorityBoost
0x180014e89  mov     rcx, rdi; Irp
0x180014e8c  call    cs:__imp_IofCompleteRequest
0x180014e93  nop     dword ptr [rax+rax+00h]
0x180014e98  jmp     loc_180014DBE
0x180014e9d  mov     ecx, 3
0x180014ea2  int     29h; Win8: RtlFailFast(ecx)
0x180014ea4  or      eax, 0FFFFFFFFh
0x180014ea7  lock xadd [rbx+4D4h], eax
0x180014eaf  cmp     eax, 1
0x180014eb2  jnz     short loc_180014ECC
0x180014eb4  lea     rcx, [rbx+4D8h]; Event
0x180014ebb  xor     r8d, r8d; Wait
0x180014ebe  xor     edx, edx; Increment
0x180014ec0  call    cs:__imp_KeSetEvent
0x180014ec7  nop     dword ptr [rax+rax+00h]
0x180014ecc  mov     eax, 0C0000016h
0x180014ed1  add     rsp, 30h
0x180014ed5  pop     r14
0x180014ed7  pop     rdi
0x180014ed8  pop     rsi
0x180014ed9  pop     rbp
0x180014eda  pop     rbx
0x180014edb  retn
```
