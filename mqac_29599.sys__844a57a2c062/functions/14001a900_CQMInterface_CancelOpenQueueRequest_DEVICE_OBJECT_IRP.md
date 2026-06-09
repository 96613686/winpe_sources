# CQMInterface::CancelOpenQueueRequest(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001a900`
- end: `0x14001a9fb`
- name: `?CancelOpenQueueRequest@CQMInterface@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `251`
- prototype: `static void(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001ac74`

## callees

- `0x1400010a4`
- `0x140003d84`
- `0x14001a900`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a98f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001a98f`
- `ntoskrnl!IofCompleteRequest` at `0x14001a9e1`
- `ntoskrnl!IofCompleteRequest` at `0x14001a9e1`

## pseudocode

```c
void __fastcall CQMInterface::CancelOpenQueueRequest(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rdx
  _QWORD **v4; // rdx
  _QWORD *i; // r9
  _QWORD *v6; // r8
  _QWORD *v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rcx

  DeviceExtension = (char *)a1->DeviceExtension;
  if ( *((struct _DEVICE_OBJECT **)DeviceExtension + 9) != a1 )
    __int2c();
  v4 = (_QWORD **)(DeviceExtension + 144);
  for ( i = *v4; ; i = (_QWORD *)*i )
  {
    v6 = 0;
    if ( v4 != i )
      v6 = i;
    if ( !v6 )
      break;
    v7 = i;
    if ( v4 == i )
      v7 = 0;
    if ( (struct _IRP *)v7[2] == a2 )
      break;
  }
  v8 = *v6;
  if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v9 = (_QWORD *)v6[1], (_QWORD *)*v9 != v6) )
    __fastfail(3u);
  *v9 = v8;
  *(_QWORD *)(v8 + 8) = v9;
  *v6 = 0;
  v6[1] = 0;
  **(_QWORD **)(v6[3] + 32LL) = 0;
  operator delete(v6);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 22, &WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids, a2);
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14001a900  push    rbx
0x14001a902  sub     rsp, 20h
0x14001a906  mov     rbx, rdx
0x14001a909  mov     rdx, [rcx+40h]
0x14001a90d  cmp     [rdx+48h], rcx
0x14001a911  jz      short loc_14001A915
0x14001a913  int     2Ch; Windows NT - assertion failure
0x14001a915  add     rdx, 90h
0x14001a91c  mov     r9, [rdx]
0x14001a91f  xor     r8d, r8d
0x14001a922  cmp     rdx, r9
0x14001a925  cmovnz  r8, r9
0x14001a929  test    r8, r8
0x14001a92c  jz      short loc_14001A945
0x14001a92e  xor     eax, eax
0x14001a930  mov     rcx, r9
0x14001a933  cmp     rdx, r9
0x14001a936  cmovz   rcx, rax
0x14001a93a  cmp     [rcx+10h], rbx
0x14001a93e  jz      short loc_14001A945
0x14001a940  mov     r9, [r9]
0x14001a943  jmp     short loc_14001A91F
0x14001a945  mov     rax, [r8]
0x14001a948  cmp     [rax+8], r8
0x14001a94c  jnz     loc_14001A9F4
0x14001a952  mov     rcx, [r8+8]
0x14001a956  cmp     [rcx], r8
0x14001a959  jnz     loc_14001A9F4
0x14001a95f  mov     [rcx], rax
0x14001a962  mov     [rax+8], rcx
0x14001a966  mov     rcx, r8; void *
0x14001a969  mov     qword ptr [r8], 0
0x14001a970  mov     qword ptr [r8+8], 0
0x14001a978  mov     rax, [r8+18h]
0x14001a97c  mov     rdx, [rax+20h]
0x14001a980  mov     qword ptr [rdx], 0
0x14001a987  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001a98c  mov     cl, [rbx+45h]; Irql
0x14001a98f  call    cs:__imp_IoReleaseCancelSpinLock
0x14001a996  nop     dword ptr [rax+rax+00h]
0x14001a99b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9a2  lea     rax, WPP_GLOBAL_Control
0x14001a9a9  cmp     rcx, rax
0x14001a9ac  jz      short loc_14001A9CD
0x14001a9ae  mov     eax, [rcx+6Ch]
0x14001a9b1  test    al, 4
0x14001a9b3  jz      short loc_14001A9CD
0x14001a9b5  mov     rcx, [rcx+58h]
0x14001a9b9  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001a9c0  mov     edx, 16h
0x14001a9c5  mov     r9, rbx
0x14001a9c8  call    WPP_SF_q
0x14001a9cd  xor     edx, edx; PriorityBoost
0x14001a9cf  mov     qword ptr [rbx+38h], 0
0x14001a9d7  mov     rcx, rbx; Irp
0x14001a9da  mov     dword ptr [rbx+30h], 0C0000120h
0x14001a9e1  call    cs:__imp_IofCompleteRequest
0x14001a9e8  nop     dword ptr [rax+rax+00h]
0x14001a9ed  add     rsp, 20h
0x14001a9f1  pop     rbx
0x14001a9f2  retn
0x14001a9f4  mov     ecx, 3
0x14001a9f9  int     29h; Win8: RtlFailFast(ecx)
```
