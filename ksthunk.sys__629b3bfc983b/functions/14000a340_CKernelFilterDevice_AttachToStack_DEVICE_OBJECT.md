# CKernelFilterDevice::AttachToStack(_DEVICE_OBJECT *)

- ea: `0x14000a340`
- end: `0x14000a3b4`
- name: `?AttachToStack@CKernelFilterDevice@@UEAAJPEAU_DEVICE_OBJECT@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(CKernelFilterDevice *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001b70`

## callees

- `0x14000a340`

## import_xrefs

- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14000a35b`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14000a35b`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::AttachToStack(CKernelFilterDevice *this, struct _DEVICE_OBJECT *a2)
{
  PDEVICE_OBJECT v4; // rax

  if ( *((_QWORD *)this + 7) )
    return 3221225473LL;
  v4 = IoAttachDeviceToDeviceStack(*((PDEVICE_OBJECT *)this + 5), a2);
  *((_QWORD *)this + 7) = v4;
  if ( !v4 )
    return 3221225486LL;
  *(_DWORD *)(*((_QWORD *)this + 5) + 48LL) |= v4->Flags & 0x6014;
  *(_DWORD *)(*((_QWORD *)this + 5) + 72LL) = *(_DWORD *)(*((_QWORD *)this + 7) + 72LL);
  *(_DWORD *)(*((_QWORD *)this + 5) + 52LL) = *(_DWORD *)(*((_QWORD *)this + 7) + 52LL);
  *(_DWORD *)(*((_QWORD *)this + 5) + 48LL) &= ~0x80u;
  return 0;
}

```

## disassembly

```asm
0x14000a340  push    rbx
0x14000a342  sub     rsp, 20h
0x14000a346  cmp     qword ptr [rcx+38h], 0
0x14000a34b  mov     rbx, rcx
0x14000a34e  jz      short loc_14000A357
0x14000a350  mov     eax, 0C0000001h
0x14000a355  jmp     short loc_14000A3AD
0x14000a357  mov     rcx, [rcx+28h]; SourceDevice
0x14000a35b  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14000a362  nop     dword ptr [rax+rax+00h]
0x14000a367  mov     [rbx+38h], rax
0x14000a36b  test    rax, rax
0x14000a36e  jnz     short loc_14000A377
0x14000a370  mov     eax, 0C000000Eh
0x14000a375  jmp     short loc_14000A3AD
0x14000a377  mov     eax, [rax+30h]
0x14000a37a  mov     rcx, [rbx+28h]
0x14000a37e  and     eax, 6014h
0x14000a383  or      [rcx+30h], eax
0x14000a386  mov     rax, [rbx+38h]
0x14000a38a  mov     rcx, [rbx+28h]
0x14000a38e  mov     eax, [rax+48h]
0x14000a391  mov     [rcx+48h], eax
0x14000a394  mov     rax, [rbx+38h]
0x14000a398  mov     rcx, [rbx+28h]
0x14000a39c  mov     eax, [rax+34h]
0x14000a39f  mov     [rcx+34h], eax
0x14000a3a2  mov     rax, [rbx+28h]
0x14000a3a6  btr     dword ptr [rax+30h], 7
0x14000a3ab  xor     eax, eax
0x14000a3ad  add     rsp, 20h
0x14000a3b1  pop     rbx
0x14000a3b2  retn
```
