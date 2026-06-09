# PmInitializeSnapshotDataCache(_DEVICE_EXTENSION *)

- ea: `0x14000da9c`
- end: `0x14000db56`
- name: `?PmInitializeSnapshotDataCache@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140007674`

## callees

- `0x14000da9c`
- `0x14001c20c`
- `0x14001fda0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000db37`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db37`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000db1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000db1f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000daf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000daf8`

## string_xrefs

- `0x14000dac3`: `SnapshotDataCache`

## pseudocode

```c
__int64 __fastcall PmInitializeSnapshotDataCache(struct _DEVICE_EXTENSION *a1)
{
  int DeviceParameterBinary; // edi
  KIRQL v3; // al
  unsigned int v5; // [rsp+38h] [rbp+10h] BYREF
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  P = 0;
  DeviceParameterBinary = PmGetDeviceParameterBinary(a1, L"SnapshotDataCache", &P, &v5);
  if ( DeviceParameterBinary >= 0 )
  {
    if ( PmVerifySnapshotData((UCHAR *)P, v5, 1) )
    {
      v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      *((_QWORD *)a1 + 142) = P;
      P = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v3);
    }
    else
    {
      DeviceParameterBinary = -1073739509;
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)DeviceParameterBinary;
}

```

## disassembly

```asm
0x14000da9c  mov     rax, rsp
0x14000da9f  mov     [rax+8], rbx
0x14000daa3  mov     [rax+20h], rsi
0x14000daa7  push    rdi
0x14000daa8  sub     rsp, 20h
0x14000daac  lea     r9, [rax+10h]; unsigned int *
0x14000dab0  mov     dword ptr [rax+10h], 0
0x14000dab7  lea     r8, [rax+18h]; void **
0x14000dabb  mov     qword ptr [rax+18h], 0
0x14000dac3  lea     rdx, aSnapshotdataca; "SnapshotDataCache"
0x14000daca  mov     rsi, rcx
0x14000dacd  call    ?PmGetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAPEAXPEAK@Z; PmGetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void * *,ulong *)
0x14000dad2  mov     edi, eax
0x14000dad4  test    eax, eax
0x14000dad6  js      short loc_14000DB2B
0x14000dad8  mov     edx, [rsp+28h+arg_8]; unsigned int
0x14000dadc  mov     r8b, 1; unsigned __int8
0x14000dadf  mov     rcx, [rsp+28h+P]; Buffer
0x14000dae4  call    ?PmVerifySnapshotData@@YAEPEAU_DISK_SNAPSHOT_DATA@@KE@Z; PmVerifySnapshotData(_DISK_SNAPSHOT_DATA *,ulong,uchar)
0x14000dae9  test    al, al
0x14000daeb  jnz     short loc_14000DAF4
0x14000daed  mov     edi, 0C000090Bh
0x14000daf2  jmp     short loc_14000DB2B
0x14000daf4  lea     rcx, [rsi+70h]; SpinLock
0x14000daf8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000daff  nop     dword ptr [rax+rax+00h]
0x14000db04  mov     rdx, [rsp+28h+P]
0x14000db09  lea     rcx, [rsi+70h]; SpinLock
0x14000db0d  mov     [rsi+470h], rdx
0x14000db14  mov     dl, al; NewIrql
0x14000db16  mov     [rsp+28h+P], 0
0x14000db1f  call    cs:__imp_KeReleaseSpinLock
0x14000db26  nop     dword ptr [rax+rax+00h]
0x14000db2b  mov     rcx, [rsp+28h+P]; P
0x14000db30  test    rcx, rcx
0x14000db33  jz      short loc_14000DB43
0x14000db35  xor     edx, edx; Tag
0x14000db37  call    cs:__imp_ExFreePoolWithTag
0x14000db3e  nop     dword ptr [rax+rax+00h]
0x14000db43  mov     rbx, [rsp+28h+arg_0]
0x14000db48  mov     eax, edi
0x14000db4a  mov     rsi, [rsp+28h+arg_18]
0x14000db4f  add     rsp, 20h
0x14000db53  pop     rdi
0x14000db54  retn
```
