# PM_DISK::Read(unsigned __int64,ulong,uchar *)

- ea: `0x140023e10`
- end: `0x140023ec3`
- name: `?Read@PM_DISK@@UEAAJ_KKPEAE@Z`
- size: `179`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT *this, union _LARGE_INTEGER, ULONG, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140023e10`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140023e83`
- `ntoskrnl!MmUnlockPages` at `0x140023e83`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140023e71`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140023e71`
- `ntoskrnl!IoFreeIrp` at `0x140023ea2`
- `ntoskrnl!IoFreeIrp` at `0x140023ea2`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140023e48`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140023e48`
- `ntoskrnl!IoFreeMdl` at `0x140023e93`
- `ntoskrnl!IoFreeMdl` at `0x140023e93`

## pseudocode

```c
__int64 __fastcall PM_DISK::Read(PDEVICE_OBJECT *this, union _LARGE_INTEGER a2, ULONG a3, unsigned __int8 *a4)
{
  PIRP v5; // rax
  IRP *v6; // rbx
  unsigned int v7; // edi
  union _LARGE_INTEGER v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = a2;
  v5 = IoBuildAsynchronousFsdRequest(3u, this[51], a4, a3, &v9, 0);
  v6 = v5;
  if ( v5 )
  {
    v5->Tail.Overlay.CurrentStackLocation[-1].Flags |= 0x12u;
    v7 = IoSynchronousCallDriver(this[51], v5);
    MmUnlockPages(v6->MdlAddress);
    IoFreeMdl(v6->MdlAddress);
    IoFreeIrp(v6);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v7;
}

```

## disassembly

```asm
0x140023e10  mov     r11, rsp
0x140023e13  mov     [r11+8], rbx
0x140023e17  mov     [r11+10h], rdx
0x140023e1b  push    rdi
0x140023e1c  sub     rsp, 30h
0x140023e20  mov     rdi, rcx
0x140023e23  mov     qword ptr [r11-10h], 0
0x140023e2b  lea     rcx, [r11+10h]
0x140023e2f  mov     rax, r9
0x140023e32  mov     [r11-18h], rcx
0x140023e36  mov     r9d, r8d; Length
0x140023e39  mov     r8, rax; Buffer
0x140023e3c  mov     ecx, 3; MajorFunction
0x140023e41  mov     rdx, [rdi+198h]; DeviceObject
0x140023e48  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x140023e4f  nop     dword ptr [rax+rax+00h]
0x140023e54  mov     rbx, rax
0x140023e57  test    rax, rax
0x140023e5a  jz      short loc_140023EBC
0x140023e5c  mov     rax, [rax+0B8h]
0x140023e63  mov     rdx, rbx
0x140023e66  or      byte ptr [rax-46h], 12h
0x140023e6a  mov     rcx, [rdi+198h]
0x140023e71  call    cs:__imp_IoSynchronousCallDriver
0x140023e78  nop     dword ptr [rax+rax+00h]
0x140023e7d  mov     edi, eax
0x140023e7f  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140023e83  call    cs:__imp_MmUnlockPages
0x140023e8a  nop     dword ptr [rax+rax+00h]
0x140023e8f  mov     rcx, [rbx+8]; Mdl
0x140023e93  call    cs:__imp_IoFreeMdl
0x140023e9a  nop     dword ptr [rax+rax+00h]
0x140023e9f  mov     rcx, rbx; Irp
0x140023ea2  call    cs:__imp_IoFreeIrp
0x140023ea9  nop     dword ptr [rax+rax+00h]
0x140023eae  mov     rbx, [rsp+38h+arg_0]
0x140023eb3  mov     eax, edi
0x140023eb5  add     rsp, 30h
0x140023eb9  pop     rdi
0x140023eba  retn
0x140023ebc  mov     edi, 0C000009Ah
0x140023ec1  jmp     short loc_140023EAE
```
