# MouHid_PassThrough

- ea: `0x1400013c0`
- end: `0x14000145b`
- name: `MouHid_PassThrough`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400013c0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001409`
- `ntoskrnl!IofCompleteRequest` at `0x140001409`
- `ntoskrnl!IofCallDriver` at `0x140001429`
- `ntoskrnl!IofCallDriver` at `0x140001429`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001443`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001443`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400013ef`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400013ef`

## pseudocode

```c
__int64 __fastcall MouHid_PassThrough(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  NTSTATUS v4; // eax
  unsigned int v5; // ebx

  v2 = *(_QWORD *)(a1 + 64);
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 240), a2, File, 1u, 0x20u);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v5 = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 8), a2);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 240), a2, 0x20u);
  }
  else
  {
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x1400013c0  push    rbx
0x1400013c2  push    rbp
0x1400013c3  push    rsi
0x1400013c4  push    rdi
0x1400013c5  sub     rsp, 38h
0x1400013c9  mov     rsi, [rcx+40h]
0x1400013cd  lea     r8, File; File
0x1400013d4  mov     r9d, 1; Line
0x1400013da  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x1400013e2  mov     rdi, rdx
0x1400013e5  lea     rbp, [rsi+0F0h]
0x1400013ec  mov     rcx, rbp; RemoveLock
0x1400013ef  call    cs:__imp_IoAcquireRemoveLockEx
0x1400013f6  nop     dword ptr [rax+rax+00h]
0x1400013fb  mov     ebx, eax
0x1400013fd  test    eax, eax
0x1400013ff  jns     short loc_140001417
0x140001401  xor     edx, edx; PriorityBoost
0x140001403  mov     [rdi+30h], eax
0x140001406  mov     rcx, rdi; Irp
0x140001409  call    cs:__imp_IofCompleteRequest
0x140001410  nop     dword ptr [rax+rax+00h]
0x140001415  jmp     short loc_14000144F
0x140001417  inc     byte ptr [rdi+43h]
0x14000141a  mov     rdx, rdi; Irp
0x14000141d  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140001425  mov     rcx, [rsi+8]; DeviceObject
0x140001429  call    cs:__imp_IofCallDriver
0x140001430  nop     dword ptr [rax+rax+00h]
0x140001435  mov     r8d, 20h ; ' '; RemlockSize
0x14000143b  mov     rdx, rdi; Tag
0x14000143e  mov     rcx, rbp; RemoveLock
0x140001441  mov     ebx, eax
0x140001443  call    cs:__imp_IoReleaseRemoveLockEx
0x14000144a  nop     dword ptr [rax+rax+00h]
0x14000144f  mov     eax, ebx
0x140001451  add     rsp, 38h
0x140001455  pop     rdi
0x140001456  pop     rsi
0x140001457  pop     rbp
0x140001458  pop     rbx
0x140001459  retn
```
