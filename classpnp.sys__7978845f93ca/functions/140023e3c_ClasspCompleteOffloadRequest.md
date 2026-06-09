# ClasspCompleteOffloadRequest

- ea: `0x140023e3c`
- end: `0x140023f1b`
- name: `ClasspCompleteOffloadRequest`
- size: `223`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023d08`
- `0x140023f24`
- `0x140056294`
- `0x140056664`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x140023e3c`
- `0x14002693c`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140023e86`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140023e86`

## pseudocode

```c
void __fastcall ClasspCompleteOffloadRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp, NTSTATUS a3)
{
  _DWORD *DeviceExtension; // r14
  bool v4; // di
  struct _DEVICE_OBJECT *v7; // rsi
  int ActivityIdIrp; // eax
  NTSTATUS v9; // [rsp+38h] [rbp-40h]
  __int128 v10; // [rsp+40h] [rbp-38h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  v4 = 0;
  v7 = DeviceObject;
  v10 = 0;
  if ( ClassPnPETWEnabled )
  {
    ActivityIdIrp = IoGetActivityIdIrp(Irp, &v10);
    LODWORD(DeviceObject) = 1;
    v4 = ActivityIdIrp >= 0;
  }
  Irp->IoStatus.Status = a3;
  if ( v4 && ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 0x20) != 0 )
  {
    v9 = a3;
    McTemplateK0qpxdd_EtwWriteTransfer(
      (_DWORD)DeviceObject,
      (_DWORD)Irp,
      (unsigned int)&v10,
      DeviceExtension[147],
      (char)Irp,
      (char)Irp->AssociatedIrp.MasterIrp->MdlAddress,
      *(_DWORD *)Irp->AssociatedIrp.MasterIrp,
      v9,
      v10);
  }
  ClassReleaseRemoveLock(v7, Irp);
  ClassCompleteRequest(v7, Irp, 0);
}

```

## disassembly

```asm
0x140023e3c  mov     [rsp+arg_10], rbx
0x140023e41  mov     [rsp+arg_18], rbp
0x140023e46  push    rsi
0x140023e47  push    rdi
0x140023e48  push    r14
0x140023e4a  sub     rsp, 60h
0x140023e4e  mov     rax, cs:__security_cookie
0x140023e55  xor     rax, rsp
0x140023e58  mov     [rsp+78h+var_28], rax
0x140023e5d  mov     r14, [rcx+40h]
0x140023e61  xor     dil, dil
0x140023e64  cmp     cs:ClassPnPETWEnabled, dil
0x140023e6b  xorps   xmm0, xmm0
0x140023e6e  mov     ebp, r8d
0x140023e71  mov     rbx, rdx
0x140023e74  mov     rsi, rcx
0x140023e77  movups  [rsp+78h+var_38], xmm0
0x140023e7c  jz      short loc_140023EA0
0x140023e7e  lea     rdx, [rsp+78h+var_38]
0x140023e83  mov     rcx, rbx
0x140023e86  call    cs:__imp_IoGetActivityIdIrp
0x140023e8d  nop     dword ptr [rax+rax+00h]
0x140023e92  movzx   edi, dil
0x140023e96  mov     ecx, 1
0x140023e9b  test    eax, eax
0x140023e9d  cmovns  edi, ecx
0x140023ea0  mov     [rbx+30h], ebp
0x140023ea3  test    dil, dil
0x140023ea6  jz      short loc_140023EDF
0x140023ea8  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 20h
0x140023eaf  jz      short loc_140023EDF
0x140023eb1  mov     r8, [rbx+18h]
0x140023eb5  mov     r9d, [r14+24Ch]
0x140023ebc  mov     [rsp+78h+var_40], ebp
0x140023ec0  mov     eax, [r8]
0x140023ec3  mov     [rsp+78h+var_48], eax
0x140023ec7  mov     rax, [r8+8]
0x140023ecb  lea     r8, [rsp+78h+var_38]
0x140023ed0  mov     [rsp+78h+var_50], rax
0x140023ed5  mov     [rsp+78h+var_58], rbx
0x140023eda  call    McTemplateK0qpxdd_EtwWriteTransfer
0x140023edf  mov     rdx, rbx; Tag
0x140023ee2  mov     rcx, rsi; DeviceObject
0x140023ee5  call    ClassReleaseRemoveLock
0x140023eea  xor     r8d, r8d; PriorityBoost
0x140023eed  mov     rdx, rbx; Irp
0x140023ef0  mov     rcx, rsi; DeviceObject
0x140023ef3  call    ClassCompleteRequest
0x140023ef8  mov     rcx, [rsp+78h+var_28]
0x140023efd  xor     rcx, rsp; StackCookie
0x140023f00  call    __security_check_cookie
0x140023f05  lea     r11, [rsp+78h+var_18]
0x140023f0a  mov     rbx, [r11+30h]
0x140023f0e  mov     rbp, [r11+38h]
0x140023f12  mov     rsp, r11
0x140023f15  pop     r14
0x140023f17  pop     rdi
0x140023f18  pop     rsi
0x140023f19  retn
```
