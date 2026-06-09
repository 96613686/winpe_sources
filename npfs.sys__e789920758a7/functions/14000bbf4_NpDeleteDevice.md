# NpDeleteDevice

- ea: `0x14000bbf4`
- end: `0x14000bcbe`
- name: `NpDeleteDevice`
- size: `202`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000bcc4`
- `0x14000bdb0`

## callees

- `0x14000bbf4`
- `0x14000d6dc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bc16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bc16`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bc2e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bc2e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bc64`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bc64`
- `ntoskrnl!IofCompleteRequest` at `0x14000bc8f`
- `ntoskrnl!IofCompleteRequest` at `0x14000bc8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bc70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bc70`
- `ntoskrnl!IoDeleteDevice` at `0x14000bca8`
- `ntoskrnl!IoDeleteDevice` at `0x14000bca8`

## pseudocode

```c
void __fastcall NpDeleteDevice(PDEVICE_OBJECT DeviceObject)
{
  char *DeviceExtension; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *i; // rbx
  _QWORD *v6; // rbx
  IRP *v7; // rcx
  _QWORD v8[7]; // [rsp+20h] [rbp-38h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v8[1] = v8;
  v8[0] = v8;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(DeviceExtension + 192, 0, v3, v4);
  for ( i = DeviceExtension + 200; (_QWORD *)*i != i; NpUnlinkNode(*i - 136LL, DeviceExtension, v8) )
    ;
  ExReleasePushLockExclusiveEx(DeviceExtension + 192, 0);
  KeLeaveCriticalRegion();
  v6 = (_QWORD *)v8[0];
  while ( v6 != v8 )
  {
    v7 = (IRP *)(v6 - 21);
    v6 = (_QWORD *)*v6;
    IofCompleteRequest(v7, 2);
  }
  IoDeleteDevice(DeviceObject);
}

```

## disassembly

```asm
0x14000bbf4  mov     r11, rsp
0x14000bbf7  push    rbx
0x14000bbf8  push    rbp
0x14000bbf9  push    rsi
0x14000bbfa  push    rdi
0x14000bbfb  sub     rsp, 38h
0x14000bbff  mov     rdi, [rcx+40h]
0x14000bc03  lea     rax, [r11-38h]
0x14000bc07  mov     [r11-30h], rax
0x14000bc0b  mov     rsi, rcx
0x14000bc0e  lea     rax, [r11-38h]
0x14000bc12  mov     [r11-38h], rax
0x14000bc16  call    cs:__imp_KeEnterCriticalRegion
0x14000bc1d  nop     dword ptr [rax+rax+00h]
0x14000bc22  lea     rbp, [rdi+0C0h]
0x14000bc29  xor     edx, edx
0x14000bc2b  mov     rcx, rbp
0x14000bc2e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000bc35  nop     dword ptr [rax+rax+00h]
0x14000bc3a  lea     rbx, [rdi+0C8h]
0x14000bc41  mov     rcx, [rbx]
0x14000bc44  cmp     rcx, rbx
0x14000bc47  jz      short loc_14000BC5F
0x14000bc49  add     rcx, 0FFFFFFFFFFFFFF78h
0x14000bc50  lea     r8, [rsp+58h+var_38]
0x14000bc55  mov     rdx, rdi
0x14000bc58  call    NpUnlinkNode
0x14000bc5d  jmp     short loc_14000BC41
0x14000bc5f  xor     edx, edx
0x14000bc61  mov     rcx, rbp
0x14000bc64  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000bc6b  nop     dword ptr [rax+rax+00h]
0x14000bc70  call    cs:__imp_KeLeaveCriticalRegion
0x14000bc77  nop     dword ptr [rax+rax+00h]
0x14000bc7c  mov     rbx, [rsp+58h+var_38]
0x14000bc81  jmp     short loc_14000BC9B
0x14000bc83  lea     rcx, [rbx-0A8h]; Irp
0x14000bc8a  mov     dl, 2; PriorityBoost
0x14000bc8c  mov     rbx, [rbx]
0x14000bc8f  call    cs:__imp_IofCompleteRequest
0x14000bc96  nop     dword ptr [rax+rax+00h]
0x14000bc9b  lea     rax, [rsp+58h+var_38]
0x14000bca0  cmp     rbx, rax
0x14000bca3  jnz     short loc_14000BC83
0x14000bca5  mov     rcx, rsi; DeviceObject
0x14000bca8  call    cs:__imp_IoDeleteDevice
0x14000bcaf  nop     dword ptr [rax+rax+00h]
0x14000bcb4  add     rsp, 38h
0x14000bcb8  pop     rdi
0x14000bcb9  pop     rsi
0x14000bcba  pop     rbp
0x14000bcbb  pop     rbx
0x14000bcbc  retn
```
