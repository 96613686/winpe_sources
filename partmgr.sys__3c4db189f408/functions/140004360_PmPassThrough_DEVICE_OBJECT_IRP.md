# PmPassThrough(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140004360`
- end: `0x1400043fa`
- name: `?PmPassThrough@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `154`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004360`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400043b0`
- `ntoskrnl!IofCallDriver` at `0x1400043b0`
- `ntoskrnl!IofCompleteRequest` at `0x1400043ea`
- `ntoskrnl!IofCompleteRequest` at `0x1400043ea`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000438c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000438c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400043ca`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400043ca`

## pseudocode

```c
__int64 __fastcall PmPassThrough(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rdi
  int v4; // eax
  unsigned int v5; // ebp
  NTSTATUS v6; // eax
  struct _IO_REMOVE_LOCK *v7; // rcx
  unsigned int v8; // edi

  DeviceExtension = (char *)a1->DeviceExtension;
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, File, 1u, 0x20u);
  v5 = v4;
  if ( v4 < 0 )
  {
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
    return v5;
  }
  else
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v6 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
    v7 = (struct _IO_REMOVE_LOCK *)(DeviceExtension + 120);
    v8 = v6;
    IoReleaseRemoveLockEx(v7, a2, 0x20u);
    return v8;
  }
}

```

## disassembly

```asm
0x140004360  push    rbx
0x140004362  push    rbp
0x140004363  push    rsi
0x140004364  push    rdi
0x140004365  sub     rsp, 38h
0x140004369  mov     rdi, [rcx+40h]
0x14000436d  lea     r8, File; File
0x140004374  mov     r9d, 1; Line
0x14000437a  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140004382  mov     rbx, rdx
0x140004385  lea     rsi, [rdi+78h]
0x140004389  mov     rcx, rsi; RemoveLock
0x14000438c  call    cs:__imp_IoAcquireRemoveLockEx
0x140004393  nop     dword ptr [rax+rax+00h]
0x140004398  mov     ebp, eax
0x14000439a  test    eax, eax
0x14000439c  js      short loc_1400043E2
0x14000439e  inc     byte ptr [rbx+43h]
0x1400043a1  mov     rdx, rbx; Irp
0x1400043a4  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x1400043ac  mov     rcx, [rdi+10h]; DeviceObject
0x1400043b0  call    cs:__imp_IofCallDriver
0x1400043b7  nop     dword ptr [rax+rax+00h]
0x1400043bc  mov     r8d, 20h ; ' '; RemlockSize
0x1400043c2  mov     rdx, rbx; Tag
0x1400043c5  mov     rcx, rsi; RemoveLock
0x1400043c8  mov     edi, eax
0x1400043ca  call    cs:__imp_IoReleaseRemoveLockEx
0x1400043d1  nop     dword ptr [rax+rax+00h]
0x1400043d6  mov     eax, edi
0x1400043d8  add     rsp, 38h
0x1400043dc  pop     rdi
0x1400043dd  pop     rsi
0x1400043de  pop     rbp
0x1400043df  pop     rbx
0x1400043e0  retn
0x1400043e2  xor     edx, edx; PriorityBoost
0x1400043e4  mov     [rbx+30h], ebp
0x1400043e7  mov     rcx, rbx; Irp
0x1400043ea  call    cs:__imp_IofCompleteRequest
0x1400043f1  nop     dword ptr [rax+rax+00h]
0x1400043f6  mov     eax, ebp
0x1400043f8  jmp     short loc_1400043D8
```
