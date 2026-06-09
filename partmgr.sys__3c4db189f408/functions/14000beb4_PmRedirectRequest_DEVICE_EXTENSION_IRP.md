# PmRedirectRequest(_DEVICE_EXTENSION *,_IRP *)

- ea: `0x14000beb4`
- end: `0x14000bf55`
- name: `?PmRedirectRequest@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z`
- size: `161`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _IRP *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002550`
- `0x140002730`
- `0x14001ed38`

## callees

- `0x14000a014`
- `0x14000beb4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000bf3d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bf3d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bec9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bec9`

## pseudocode

```c
void __fastcall PmRedirectRequest(KSPIN_LOCK *a1, struct _IRP *a2)
{
  struct _LIST_ENTRY *v4; // rbx
  KIRQL v5; // r14
  int v6; // r8d
  struct _LIST_ENTRY *v7; // rcx

  v4 = (struct _LIST_ENTRY *)(a1 + 82);
  v5 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  if ( v4->Flink == v4 )
  {
    v6 = *((_DWORD *)a1 + 129) | 0x400000;
    *((_DWORD *)a1 + 129) = v6;
    PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)a1, "PmRedirectRequest", v6);
  }
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v7 = (struct _LIST_ENTRY *)a1[83];
  if ( v7->Flink != v4 )
    __fastfail(3u);
  a2->Tail.Overlay.ListEntry.Blink = v7;
  a2->Tail.Overlay.ListEntry.Flink = v4;
  v7->Flink = &a2->Tail.Overlay.ListEntry;
  a1[83] = (KSPIN_LOCK)&a2->Tail.Overlay.ListEntry;
  KeReleaseSpinLock(a1 + 14, v5);
}

```

## disassembly

```asm
0x14000beb4  push    rbx
0x14000beb6  push    rbp
0x14000beb7  push    rsi
0x14000beb8  push    rdi
0x14000beb9  push    r14
0x14000bebb  sub     rsp, 20h
0x14000bebf  mov     rdi, rcx
0x14000bec2  mov     rsi, rdx
0x14000bec5  add     rcx, 70h ; 'p'; SpinLock
0x14000bec9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bed0  nop     dword ptr [rax+rax+00h]
0x14000bed5  lea     rbx, [rdi+290h]
0x14000bedc  mov     r14b, al
0x14000bedf  cmp     [rbx], rbx
0x14000bee2  jnz     short loc_14000BF06
0x14000bee4  mov     r8d, [rdi+204h]
0x14000beeb  lea     rdx, aPmredirectrequ; "PmRedirectRequest"
0x14000bef2  bts     r8d, 16h
0x14000bef7  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000befa  mov     [rdi+204h], r8d
0x14000bf01  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000bf06  mov     rcx, [rsi+0B8h]
0x14000bf0d  or      byte ptr [rcx+3], 1
0x14000bf11  mov     rcx, [rbx+8]
0x14000bf15  cmp     [rcx], rbx
0x14000bf18  jz      short loc_14000BF21
0x14000bf1a  mov     ecx, 3
0x14000bf1f  int     29h; Win8: RtlFailFast(ecx)
0x14000bf21  lea     rax, [rsi+0A8h]
0x14000bf28  mov     dl, r14b; NewIrql
0x14000bf2b  mov     [rax+8], rcx
0x14000bf2f  mov     [rax], rbx
0x14000bf32  mov     [rcx], rax
0x14000bf35  lea     rcx, [rdi+70h]; SpinLock
0x14000bf39  mov     [rbx+8], rax
0x14000bf3d  call    cs:__imp_KeReleaseSpinLock
0x14000bf44  nop     dword ptr [rax+rax+00h]
0x14000bf49  add     rsp, 20h
0x14000bf4d  pop     r14
0x14000bf4f  pop     rdi
0x14000bf50  pop     rsi
0x14000bf51  pop     rbp
0x14000bf52  pop     rbx
0x14000bf53  retn
```
