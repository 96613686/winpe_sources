# PmVolumeManagerArrival(_CONTROL_EXTENSION *,_UNICODE_STRING *)

- ea: `0x14000e398`
- end: `0x14000e5aa`
- name: `?PmVolumeManagerArrival@@YAJPEAU_CONTROL_EXTENSION@@PEAU_UNICODE_STRING@@@Z`
- size: `530`
- prototype: `int(struct _CONTROL_EXTENSION *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c660`

## callees

- `0x14000a014`
- `0x14000e398`
- `0x14001c9a8`
- `0x14002249c`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e3d3`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3d3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e405`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000e405`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000e441`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000e441`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e57a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e57a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e524`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e524`

## pseudocode

```c
__int64 __fastcall PmVolumeManagerArrival(struct _CONTROL_EXTENSION *a1, struct _UNICODE_STRING *a2)
{
  __int64 MaximumLength; // r14
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v6; // rdi
  NTSTATUS DeviceObjectPointer; // esi
  struct _CONTROL_EXTENSION *v8; // rcx
  struct _DEVICE_OBJECT *Buffer; // rcx
  struct _UNICODE_STRING *i; // rax
  struct _UNICODE_STRING **v11; // rcx
  struct _CONTROL_EXTENSION *j; // rbx
  char v13; // r14
  KIRQL v14; // r12
  _QWORD *v15; // r8
  __int128 InputBuffer; // [rsp+40h] [rbp-68h] BYREF
  __int128 v18; // [rsp+50h] [rbp-58h]
  void (__fastcall *v19)(struct _PERF_COUNTER_CONTEXT *, struct _DISK_PERFORMANCE *, unsigned __int16 *, unsigned int); // [rsp+60h] [rbp-48h]

  MaximumLength = a2->MaximumLength;
  v19 = 0;
  InputBuffer = 0;
  v18 = 0;
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(66, MaximumLength + 64, 1163291984);
  v6 = Pool2;
  if ( Pool2 )
  {
    Pool2[1].MaximumLength = MaximumLength;
    Pool2[1].Buffer = &Pool2[4].Length;
    RtlCopyUnicodeString(Pool2 + 1, a2);
    *(_DWORD *)&v6[2].Length = 0;
    v6[2].Buffer = 0;
    *(_QWORD *)&v6[3].Length = 0;
    v6->Buffer = &v6->Length;
    *(_QWORD *)&v6->Length = v6;
    DeviceObjectPointer = IoGetDeviceObjectPointer(v6 + 1, 1u, (PFILE_OBJECT *)&v6[3], (PDEVICE_OBJECT *)&v6[2].Buffer);
    if ( DeviceObjectPointer < 0 )
      goto LABEL_20;
    Buffer = (struct _DEVICE_OBJECT *)v6[2].Buffer;
    *(_QWORD *)&InputBuffer = PmWmiCounterEnable;
    *((_QWORD *)&InputBuffer + 1) = PmWmiCounterDisable;
    *(_QWORD *)&v18 = PmWmiCounterIoStart;
    *((_QWORD *)&v18 + 1) = PmWmiCounterIoComplete;
    v19 = PmWmiCounterQuery;
    PmSendDeviceControl(Buffer, 0x760024u, &InputBuffer, 0x28u, 0, 0, 1u);
    DeviceObjectPointer = PmSetVolumeManagerAltitude((struct _VOLUME_MANAGER *)v6);
    if ( DeviceObjectPointer < 0 )
    {
LABEL_20:
      PmVolumeManagerRemoval(v8, (struct _VOLUME_MANAGER *)v6);
    }
    else
    {
      for ( i = (struct _UNICODE_STRING *)*((_QWORD *)a1 + 9);
            i != (struct _UNICODE_STRING *)((char *)a1 + 72);
            i = *(struct _UNICODE_STRING **)&i->Length )
      {
        if ( LODWORD(i[3].Buffer) > LODWORD(v6[3].Buffer) )
          break;
      }
      v11 = (struct _UNICODE_STRING **)i->Buffer;
      if ( *v11 != i )
        __fastfail(3u);
      *(_QWORD *)&v6->Length = i;
      v6->Buffer = (PWSTR)v11;
      *v11 = v6;
      i->Buffer = &v6->Length;
      for ( j = (struct _CONTROL_EXTENSION *)*((_QWORD *)a1 + 11);
            j != (struct _CONTROL_EXTENSION *)((char *)a1 + 88);
            j = *(struct _CONTROL_EXTENSION **)j )
      {
        v13 = 0;
        v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)j - 5);
        v15 = (_QWORD *)*((_QWORD *)j + 93);
        if ( v15 != (_QWORD *)((char *)j + 744) )
        {
          do
          {
            if ( !*(v15 - 4) )
            {
              v13 = 1;
              *((_DWORD *)v15 - 26) &= ~1u;
            }
            v15 = (_QWORD *)*v15;
          }
          while ( v15 != (_QWORD *)((char *)j + 744) );
          if ( v13 )
            PmQueueNotificationWorkItem(
              (struct _CONTROL_EXTENSION *)((char *)j - 152),
              "PmVolumeManagerArrival",
              (int)v15);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)j - 5, v14);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x14000e398  push    rbx
0x14000e39a  push    rbp
0x14000e39b  push    rsi
0x14000e39c  push    rdi
0x14000e39d  push    r12
0x14000e39f  push    r14
0x14000e3a1  push    r15
0x14000e3a3  sub     rsp, 70h
0x14000e3a7  movzx   r14d, word ptr [rdx+2]
0x14000e3ac  xor     eax, eax
0x14000e3ae  xorps   xmm0, xmm0
0x14000e3b1  mov     [rsp+0A8h+var_48], rax
0x14000e3b6  mov     rsi, rdx
0x14000e3b9  mov     rbp, rcx
0x14000e3bc  mov     r8d, 45566D50h
0x14000e3c2  lea     rdx, [r14+40h]
0x14000e3c6  lea     ecx, [rax+42h]
0x14000e3c9  movups  [rsp+0A8h+InputBuffer], xmm0
0x14000e3ce  movups  [rsp+0A8h+var_58], xmm0
0x14000e3d3  call    cs:__imp_ExAllocatePool2
0x14000e3da  nop     dword ptr [rax+rax+00h]
0x14000e3df  mov     rdi, rax
0x14000e3e2  test    rax, rax
0x14000e3e5  jnz     short loc_14000E3F1
0x14000e3e7  mov     esi, 0C000009Ah
0x14000e3ec  jmp     loc_14000E598
0x14000e3f1  add     rax, 40h ; '@'
0x14000e3f5  mov     [rdi+12h], r14w
0x14000e3fa  mov     rdx, rsi; SourceString
0x14000e3fd  mov     [rdi+18h], rax
0x14000e401  lea     rcx, [rdi+10h]; DestinationString
0x14000e405  call    cs:__imp_RtlCopyUnicodeString
0x14000e40c  nop     dword ptr [rax+rax+00h]
0x14000e411  lea     r14, [rdi+28h]
0x14000e415  mov     dword ptr [rdi+20h], 0
0x14000e41c  mov     qword ptr [r14], 0
0x14000e423  lea     r8, [rdi+30h]; FileObject
0x14000e427  mov     r9, r14; DeviceObject
0x14000e42a  mov     qword ptr [r8], 0
0x14000e431  mov     edx, 1; DesiredAccess
0x14000e436  mov     [rdi+8], rdi
0x14000e43a  lea     rcx, [rdi+10h]; ObjectName
0x14000e43e  mov     [rdi], rdi
0x14000e441  call    cs:__imp_IoGetDeviceObjectPointer
0x14000e448  nop     dword ptr [rax+rax+00h]
0x14000e44d  mov     esi, eax
0x14000e44f  test    eax, eax
0x14000e451  js      loc_14000E590
0x14000e457  mov     rcx, [r14]; DeviceObject
0x14000e45a  lea     rax, ?PmWmiCounterEnable@@YAJPEAPEAU_PERF_COUNTER_CONTEXT@@@Z; PmWmiCounterEnable(_PERF_COUNTER_CONTEXT * *)
0x14000e461  mov     qword ptr [rsp+0A8h+InputBuffer], rax
0x14000e466  lea     r8, [rsp+0A8h+InputBuffer]; InputBuffer
0x14000e46b  lea     rax, ?PmWmiCounterDisable@@YAEPEAPEAU_PERF_COUNTER_CONTEXT@@EE@Z; PmWmiCounterDisable(_PERF_COUNTER_CONTEXT * *,uchar,uchar)
0x14000e472  mov     [rsp+0A8h+var_78], 1; BOOLEAN
0x14000e477  mov     qword ptr [rsp+0A8h+InputBuffer+8], rax
0x14000e47c  mov     r9d, 28h ; '('; InputBufferLength
0x14000e482  lea     rax, ?PmWmiCounterIoStart@@YAXPEAU_PERF_COUNTER_CONTEXT@@PEAT_LARGE_INTEGER@@PEAK@Z; PmWmiCounterIoStart(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER *,ulong *)
0x14000e489  mov     [rsp+0A8h+var_80], 0; ULONG
0x14000e491  mov     qword ptr [rsp+0A8h+var_58], rax
0x14000e496  mov     edx, 760024h; IoControlCode
0x14000e49b  lea     rax, ?PmWmiCounterIoComplete@@YAXPEAU_PERF_COUNTER_CONTEXT@@PEAU_IRP@@PEAT_LARGE_INTEGER@@PEAK@Z; PmWmiCounterIoComplete(_PERF_COUNTER_CONTEXT *,_IRP *,_LARGE_INTEGER *,ulong *)
0x14000e4a2  mov     [rsp+0A8h+var_88], 0; PVOID
0x14000e4ab  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x14000e4b0  lea     rax, ?PmWmiCounterQuery@@YAXPEAU_PERF_COUNTER_CONTEXT@@PEAU_DISK_PERFORMANCE@@PEAGK@Z; PmWmiCounterQuery(_PERF_COUNTER_CONTEXT *,_DISK_PERFORMANCE *,ushort *,ulong)
0x14000e4b7  mov     [rsp+0A8h+var_48], rax
0x14000e4bc  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14000e4c1  mov     rcx, rdi; struct _VOLUME_MANAGER *
0x14000e4c4  call    ?PmSetVolumeManagerAltitude@@YAJPEAU_VOLUME_MANAGER@@@Z; PmSetVolumeManagerAltitude(_VOLUME_MANAGER *)
0x14000e4c9  mov     esi, eax
0x14000e4cb  test    eax, eax
0x14000e4cd  js      loc_14000E590
0x14000e4d3  lea     rcx, [rbp+48h]
0x14000e4d7  mov     rax, [rcx]
0x14000e4da  cmp     rax, rcx
0x14000e4dd  jz      short loc_14000E4EF
0x14000e4df  mov     edx, [rdi+38h]
0x14000e4e2  cmp     [rax+38h], edx
0x14000e4e5  ja      short loc_14000E4EF
0x14000e4e7  mov     rax, [rax]
0x14000e4ea  cmp     rax, rcx
0x14000e4ed  jnz     short loc_14000E4E2
0x14000e4ef  mov     rcx, [rax+8]
0x14000e4f3  cmp     [rcx], rax
0x14000e4f6  jz      short loc_14000E4FF
0x14000e4f8  mov     ecx, 3
0x14000e4fd  int     29h; Win8: RtlFailFast(ecx)
0x14000e4ff  mov     [rdi], rax
0x14000e502  mov     [rdi+8], rcx
0x14000e506  mov     [rcx], rdi
0x14000e509  mov     [rax+8], rdi
0x14000e50d  lea     rdi, [rbp+58h]
0x14000e511  mov     rbx, [rdi]
0x14000e514  jmp     short loc_14000E589
0x14000e516  lea     rbp, [rbx-98h]
0x14000e51d  xor     r14b, r14b
0x14000e520  lea     rcx, [rbp+70h]; SpinLock
0x14000e524  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e52b  nop     dword ptr [rax+rax+00h]
0x14000e530  lea     r9, [rbp+380h]
0x14000e537  mov     r12b, al
0x14000e53a  mov     r8, [r9]
0x14000e53d  cmp     r8, r9
0x14000e540  jz      short loc_14000E573
0x14000e542  cmp     qword ptr [r8-20h], 0
0x14000e547  jnz     short loc_14000E557
0x14000e549  mov     edx, [r8-68h]
0x14000e54d  mov     r14b, 1
0x14000e550  and     edx, 0FFFFFFFEh
0x14000e553  mov     [r8-68h], edx
0x14000e557  mov     r8, [r8]
0x14000e55a  cmp     r8, r9
0x14000e55d  jnz     short loc_14000E542
0x14000e55f  test    r14b, r14b
0x14000e562  jz      short loc_14000E573
0x14000e564  lea     rdx, aPmvolumemanage; "PmVolumeManagerArrival"
0x14000e56b  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14000e56e  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000e573  mov     dl, r12b; NewIrql
0x14000e576  lea     rcx, [rbp+70h]; SpinLock
0x14000e57a  call    cs:__imp_KeReleaseSpinLock
0x14000e581  nop     dword ptr [rax+rax+00h]
0x14000e586  mov     rbx, [rbx]
0x14000e589  cmp     rbx, rdi
0x14000e58c  jnz     short loc_14000E516
0x14000e58e  jmp     short loc_14000E598
0x14000e590  mov     rdx, rdi; struct _VOLUME_MANAGER *
0x14000e593  call    ?PmVolumeManagerRemoval@@YAJPEAU_CONTROL_EXTENSION@@PEAU_VOLUME_MANAGER@@@Z; PmVolumeManagerRemoval(_CONTROL_EXTENSION *,_VOLUME_MANAGER *)
0x14000e598  mov     eax, esi
0x14000e59a  add     rsp, 70h
0x14000e59e  pop     r15
0x14000e5a0  pop     r14
0x14000e5a2  pop     r12
0x14000e5a4  pop     rdi
0x14000e5a5  pop     rsi
0x14000e5a6  pop     rbp
0x14000e5a7  pop     rbx
0x14000e5a8  retn
```
