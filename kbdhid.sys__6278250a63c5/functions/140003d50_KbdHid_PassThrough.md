# KbdHid_PassThrough

- ea: `0x140003d50`
- end: `0x140003ded`
- name: `KbdHid_PassThrough`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003d50`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140003da3`
- `ntoskrnl!IofCallDriver` at `0x140003da3`
- `ntoskrnl!IofCompleteRequest` at `0x140003ddd`
- `ntoskrnl!IofCompleteRequest` at `0x140003ddd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003dbd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003dbd`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003d7f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003d7f`

## pseudocode

```c
__int64 __fastcall KbdHid_PassThrough(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi
  NTSTATUS v4; // eax
  unsigned int v5; // ebp
  NTSTATUS v6; // eax
  struct _IO_REMOVE_LOCK *v7; // rcx
  unsigned int v8; // edi

  v2 = *(_QWORD *)(a1 + 64);
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 152), a2, File, 1u, 0x20u);
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
    v6 = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 8), a2);
    v7 = (struct _IO_REMOVE_LOCK *)(v2 + 152);
    v8 = v6;
    IoReleaseRemoveLockEx(v7, a2, 0x20u);
    return v8;
  }
}

```

## disassembly

```asm
0x140003d50  push    rbx
0x140003d52  push    rbp
0x140003d53  push    rsi
0x140003d54  push    rdi
0x140003d55  sub     rsp, 38h
0x140003d59  mov     rdi, [rcx+40h]
0x140003d5d  lea     r8, File; File
0x140003d64  mov     r9d, 1; Line
0x140003d6a  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140003d72  mov     rbx, rdx
0x140003d75  lea     rsi, [rdi+98h]
0x140003d7c  mov     rcx, rsi; RemoveLock
0x140003d7f  call    cs:__imp_IoAcquireRemoveLockEx
0x140003d86  nop     dword ptr [rax+rax+00h]
0x140003d8b  mov     ebp, eax
0x140003d8d  test    eax, eax
0x140003d8f  js      short loc_140003DD5
0x140003d91  inc     byte ptr [rbx+43h]
0x140003d94  mov     rdx, rbx; Irp
0x140003d97  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140003d9f  mov     rcx, [rdi+8]; DeviceObject
0x140003da3  call    cs:__imp_IofCallDriver
0x140003daa  nop     dword ptr [rax+rax+00h]
0x140003daf  mov     r8d, 20h ; ' '; RemlockSize
0x140003db5  mov     rdx, rbx; Tag
0x140003db8  mov     rcx, rsi; RemoveLock
0x140003dbb  mov     edi, eax
0x140003dbd  call    cs:__imp_IoReleaseRemoveLockEx
0x140003dc4  nop     dword ptr [rax+rax+00h]
0x140003dc9  mov     eax, edi
0x140003dcb  add     rsp, 38h
0x140003dcf  pop     rdi
0x140003dd0  pop     rsi
0x140003dd1  pop     rbp
0x140003dd2  pop     rbx
0x140003dd3  retn
0x140003dd5  xor     edx, edx; PriorityBoost
0x140003dd7  mov     [rbx+30h], ebp
0x140003dda  mov     rcx, rbx; Irp
0x140003ddd  call    cs:__imp_IofCompleteRequest
0x140003de4  nop     dword ptr [rax+rax+00h]
0x140003de9  mov     eax, ebp
0x140003deb  jmp     short loc_140003DCB
```
