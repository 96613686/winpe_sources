# PM_DISK::Write(unsigned __int64,ulong,uchar *)

- ea: `0x14001d1a0`
- end: `0x14001d253`
- name: `?Write@PM_DISK@@UEAAJ_KKPEAE@Z`
- size: `179`
- prototype: `int(PM_DISK *__hidden this, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001d1a0`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14001d21a`
- `ntoskrnl!MmUnlockPages` at `0x14001d21a`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14001d208`
- `ntoskrnl!IoSynchronousCallDriver` at `0x14001d208`
- `ntoskrnl!IoFreeIrp` at `0x14001d239`
- `ntoskrnl!IoFreeIrp` at `0x14001d239`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14001d1d8`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14001d1d8`
- `ntoskrnl!IoFreeMdl` at `0x14001d22a`
- `ntoskrnl!IoFreeMdl` at `0x14001d22a`

## pseudocode

```c
__int64 __fastcall PM_DISK::Write(PDEVICE_OBJECT *this, union _LARGE_INTEGER a2, ULONG a3, unsigned __int8 *a4)
{
  PIRP v5; // rax
  IRP *v6; // rbx
  unsigned int v7; // edi
  union _LARGE_INTEGER v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = a2;
  v5 = IoBuildAsynchronousFsdRequest(4u, this[51], a4, a3, &v9, 0);
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
0x14001d1a0  mov     r11, rsp
0x14001d1a3  mov     [r11+8], rbx
0x14001d1a7  mov     [r11+10h], rdx
0x14001d1ab  push    rdi
0x14001d1ac  sub     rsp, 30h
0x14001d1b0  mov     rdi, rcx
0x14001d1b3  mov     qword ptr [r11-10h], 0
0x14001d1bb  lea     rcx, [r11+10h]
0x14001d1bf  mov     rax, r9
0x14001d1c2  mov     [r11-18h], rcx
0x14001d1c6  mov     r9d, r8d; Length
0x14001d1c9  mov     r8, rax; Buffer
0x14001d1cc  mov     ecx, 4; MajorFunction
0x14001d1d1  mov     rdx, [rdi+198h]; DeviceObject
0x14001d1d8  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14001d1df  nop     dword ptr [rax+rax+00h]
0x14001d1e4  mov     rbx, rax
0x14001d1e7  test    rax, rax
0x14001d1ea  jnz     short loc_14001D1F3
0x14001d1ec  mov     edi, 0C000009Ah
0x14001d1f1  jmp     short loc_14001D245
0x14001d1f3  mov     rax, [rax+0B8h]
0x14001d1fa  mov     rdx, rbx
0x14001d1fd  or      byte ptr [rax-46h], 12h
0x14001d201  mov     rcx, [rdi+198h]
0x14001d208  call    cs:__imp_IoSynchronousCallDriver
0x14001d20f  nop     dword ptr [rax+rax+00h]
0x14001d214  mov     edi, eax
0x14001d216  mov     rcx, [rbx+8]; MemoryDescriptorList
0x14001d21a  call    cs:__imp_MmUnlockPages
0x14001d221  nop     dword ptr [rax+rax+00h]
0x14001d226  mov     rcx, [rbx+8]; Mdl
0x14001d22a  call    cs:__imp_IoFreeMdl
0x14001d231  nop     dword ptr [rax+rax+00h]
0x14001d236  mov     rcx, rbx; Irp
0x14001d239  call    cs:__imp_IoFreeIrp
0x14001d240  nop     dword ptr [rax+rax+00h]
0x14001d245  mov     rbx, [rsp+38h+arg_0]
0x14001d24a  mov     eax, edi
0x14001d24c  add     rsp, 30h
0x14001d250  pop     rdi
0x14001d251  retn
```
