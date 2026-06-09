# NpSiloArrival

- ea: `0x14000bcc4`
- end: `0x14000bda0`
- name: `NpSiloArrival`
- size: `220`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bacc`

## callees

- `0x14000bbf4`
- `0x14000bcc4`
- `0x14001655c`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000bcdc`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000bcdc`
- `ntoskrnl!PsCreateSiloContext` at `0x14000bd2b`
- `ntoskrnl!PsCreateSiloContext` at `0x14000bd2b`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14000bd53`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14000bd53`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000bd84`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000bd84`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14000bd66`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14000bd66`

## pseudocode

```c
__int64 __fastcall NpSiloArrival(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbp
  int v4; // eax
  struct _DEVICE_OBJECT *v5; // rbx
  int inserted; // edi
  struct _DEVICE_OBJECT **v8; // [rsp+58h] [rbp+10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  v2 = PsAttachSiloToCurrentThread();
  DeviceObject = 0;
  v3 = v2;
  v4 = NpCreateDevice(&DeviceObject);
  v5 = DeviceObject;
  inserted = v4;
  if ( v4 >= 0 )
  {
    DeviceObject->Flags &= ~0x80u;
    inserted = PsCreateSiloContext(a1, 8, 1, NpSiloContextCleanup, &v8);
    if ( inserted >= 0 )
    {
      *v8 = v5;
      inserted = PsInsertPermanentSiloContext(a1, (unsigned int)NpSiloSlot, v8);
      PsDereferenceSiloContext(v8);
      v5 = 0;
    }
  }
  if ( v5 )
    NpDeleteDevice(v5);
  PsDetachSiloFromCurrentThread(v3);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14000bcc4  mov     [rsp+arg_0], rbx
0x14000bcc9  push    rbp
0x14000bcca  push    rsi
0x14000bccb  push    rdi
0x14000bccc  sub     rsp, 30h
0x14000bcd0  mov     rsi, rcx
0x14000bcd3  mov     [rsp+48h+arg_8], 0
0x14000bcdc  call    cs:__imp_PsAttachSiloToCurrentThread
0x14000bce3  nop     dword ptr [rax+rax+00h]
0x14000bce8  lea     rcx, [rsp+48h+DeviceObject]
0x14000bced  mov     [rsp+48h+DeviceObject], 0
0x14000bcf6  mov     rbp, rax
0x14000bcf9  call    NpCreateDevice
0x14000bcfe  mov     rbx, [rsp+48h+DeviceObject]
0x14000bd03  mov     edi, eax
0x14000bd05  test    eax, eax
0x14000bd07  js      short loc_14000BD74
0x14000bd09  btr     dword ptr [rbx+30h], 7
0x14000bd0e  lea     rax, [rsp+48h+arg_8]
0x14000bd13  mov     edx, 8
0x14000bd18  mov     [rsp+48h+var_28], rax
0x14000bd1d  lea     r9, NpSiloContextCleanup
0x14000bd24  mov     rcx, rsi
0x14000bd27  lea     r8d, [rdx-7]
0x14000bd2b  call    cs:__imp_PsCreateSiloContext
0x14000bd32  nop     dword ptr [rax+rax+00h]
0x14000bd37  mov     edi, eax
0x14000bd39  test    eax, eax
0x14000bd3b  js      short loc_14000BD74
0x14000bd3d  mov     rax, [rsp+48h+arg_8]
0x14000bd42  mov     rcx, rsi
0x14000bd45  mov     [rax], rbx
0x14000bd48  mov     r8, [rsp+48h+arg_8]
0x14000bd4d  mov     edx, cs:NpSiloSlot
0x14000bd53  call    cs:__imp_PsInsertPermanentSiloContext
0x14000bd5a  nop     dword ptr [rax+rax+00h]
0x14000bd5f  mov     rcx, [rsp+48h+arg_8]
0x14000bd64  mov     edi, eax
0x14000bd66  call    cs:__imp_PsDereferenceSiloContext
0x14000bd6d  nop     dword ptr [rax+rax+00h]
0x14000bd72  xor     ebx, ebx
0x14000bd74  test    rbx, rbx
0x14000bd77  jz      short loc_14000BD81
0x14000bd79  mov     rcx, rbx; DeviceObject
0x14000bd7c  call    NpDeleteDevice
0x14000bd81  mov     rcx, rbp
0x14000bd84  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000bd8b  nop     dword ptr [rax+rax+00h]
0x14000bd90  mov     rbx, [rsp+48h+arg_0]
0x14000bd95  mov     eax, edi
0x14000bd97  add     rsp, 30h
0x14000bd9b  pop     rdi
0x14000bd9c  pop     rsi
0x14000bd9d  pop     rbp
0x14000bd9e  retn
```
