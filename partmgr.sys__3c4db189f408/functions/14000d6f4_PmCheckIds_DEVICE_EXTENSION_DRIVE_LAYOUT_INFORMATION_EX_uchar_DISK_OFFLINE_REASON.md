# PmCheckIds(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,uchar *,_DISK_OFFLINE_REASON *)

- ea: `0x14000d6f4`
- end: `0x14000d78c`
- name: `?PmCheckIds@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAEPEAW4_DISK_OFFLINE_REASON@@@Z`
- size: `152`
- prototype: `int(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int8 *, enum _DISK_OFFLINE_REASON *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14002184c`

## callees

- `0x14000d6f4`
- `0x140020f90`
- `0x140023f38`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d76d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d76d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d74b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d74b`

## pseudocode

```c
__int64 __fastcall PmCheckIds(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        unsigned __int8 *a3,
        enum _DISK_OFFLINE_REASON *a4)
{
  __int64 v4; // rax
  unsigned int v5; // edi
  int v8; // eax
  KIRQL v9; // al

  v4 = *((_QWORD *)a1 + 66);
  v5 = 0;
  *a3 = 0;
  *(_DWORD *)a4 = 0;
  if ( (v4 & 1) != 0 )
    return v5;
  if ( !a2->PartitionStyle )
  {
    v8 = PmCheckIdsMbr(a1, a2, a3, a4);
LABEL_6:
    v5 = v8;
    if ( v8 < 0 )
      return v5;
    goto LABEL_7;
  }
  if ( a2->PartitionStyle == 1 )
  {
    v8 = PmCheckIdsGpt(a1, a2, a3, a4);
    goto LABEL_6;
  }
LABEL_7:
  if ( *(_DWORD *)a4 == 4 )
  {
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    *((_DWORD *)a1 + 129) |= 0x800u;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v9);
  }
  return v5;
}

```

## disassembly

```asm
0x14000d6f4  mov     [rsp+arg_0], rbx
0x14000d6f9  mov     [rsp+arg_8], rsi
0x14000d6fe  push    rdi
0x14000d6ff  sub     rsp, 20h
0x14000d703  mov     rax, [rcx+210h]
0x14000d70a  xor     edi, edi
0x14000d70c  mov     [r8], dil
0x14000d70f  mov     rbx, r9
0x14000d712  mov     [r9], edi
0x14000d715  mov     rsi, rcx
0x14000d718  test    al, 1
0x14000d71a  jnz     short loc_14000D779
0x14000d71c  mov     r9d, [rdx]
0x14000d71f  test    r9d, r9d
0x14000d722  jz      short loc_14000D734
0x14000d724  cmp     r9d, 1
0x14000d728  jnz     short loc_14000D742
0x14000d72a  mov     r9, rbx; enum _DISK_OFFLINE_REASON *
0x14000d72d  call    ?PmCheckIdsGpt@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAEPEAW4_DISK_OFFLINE_REASON@@@Z; PmCheckIdsGpt(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,uchar *,_DISK_OFFLINE_REASON *)
0x14000d732  jmp     short loc_14000D73C
0x14000d734  mov     r9, rbx; enum _DISK_OFFLINE_REASON *
0x14000d737  call    ?PmCheckIdsMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAEPEAW4_DISK_OFFLINE_REASON@@@Z; PmCheckIdsMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,uchar *,_DISK_OFFLINE_REASON *)
0x14000d73c  mov     edi, eax
0x14000d73e  test    eax, eax
0x14000d740  js      short loc_14000D779
0x14000d742  cmp     dword ptr [rbx], 4
0x14000d745  jnz     short loc_14000D779
0x14000d747  lea     rcx, [rsi+70h]; SpinLock
0x14000d74b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d752  nop     dword ptr [rax+rax+00h]
0x14000d757  mov     edx, [rsi+204h]
0x14000d75d  lea     rcx, [rsi+70h]; SpinLock
0x14000d761  bts     edx, 0Bh
0x14000d765  mov     [rsi+204h], edx
0x14000d76b  mov     dl, al; NewIrql
0x14000d76d  call    cs:__imp_KeReleaseSpinLock
0x14000d774  nop     dword ptr [rax+rax+00h]
0x14000d779  mov     rbx, [rsp+28h+arg_0]
0x14000d77e  mov     eax, edi
0x14000d780  mov     rsi, [rsp+28h+arg_8]
0x14000d785  add     rsp, 20h
0x14000d789  pop     rdi
0x14000d78a  retn
```
