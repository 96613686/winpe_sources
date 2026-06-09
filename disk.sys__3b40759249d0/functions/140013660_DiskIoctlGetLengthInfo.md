# DiskIoctlGetLengthInfo

- ea: `0x140013660`
- end: `0x140013745`
- name: `DiskIoctlGetLengthInfo`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140013660`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140013737`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140013737`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013670`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013670`
- `CLASSPNP!ClassReadDriveCapacity` at `0x1400136b4`
- `CLASSPNP!ClassReadDriveCapacity` at `0x1400136b4`

## pseudocode

```c
__int64 __fastcall DiskIoctlGetLengthInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // rbp
  __int64 v5; // r14
  __int64 v6; // rdi
  NTSTATUS DriveCapacity; // esi
  __int64 result; // rax

  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) < 8u )
    return 3221225507LL;
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(v4 + 24);
  v6 = *(_QWORD *)(v5 + 96);
  DriveCapacity = ClassReadDriveCapacity(*(PDEVICE_OBJECT *)(v5 + 8));
  if ( *(_DWORD *)(v6 + 4) != _InterlockedExchange((volatile __int32 *)(v6 + 4), DriveCapacity) )
    IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v5 + 512), BusRelations);
  if ( DriveCapacity < 0 )
  {
    *(_DWORD *)(a2 + 48) = DriveCapacity;
    return (unsigned int)DriveCapacity;
  }
  else
  {
    **(_QWORD **)(a2 + 24) = *(_QWORD *)(v4 + 144);
    result = 0;
    *(_DWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 56) = 8;
  }
  return result;
}

```

## disassembly

```asm
0x140013660  mov     [rsp+arg_18], rbx
0x140013665  push    rdi
0x140013666  sub     rsp, 20h
0x14001366a  mov     rbx, rdx
0x14001366d  mov     rdi, rcx
0x140013670  call    cs:__imp_KeGetCurrentIrql
0x140013677  nop     dword ptr [rax+rax+00h]
0x14001367c  cmp     al, 2
0x14001367e  jnb     loc_14001370F
0x140013684  mov     rax, [rbx+0B8h]
0x14001368b  cmp     dword ptr [rax+8], 8
0x14001368f  jb      loc_140013727
0x140013695  mov     [rsp+28h+arg_0], rbp
0x14001369a  mov     rbp, [rdi+40h]
0x14001369e  mov     [rsp+28h+arg_8], rsi
0x1400136a3  mov     [rsp+28h+arg_10], r14
0x1400136a8  mov     r14, [rbp+18h]
0x1400136ac  mov     rcx, [r14+8]; DeviceObject
0x1400136b0  mov     rdi, [r14+60h]
0x1400136b4  call    cs:__imp_ClassReadDriveCapacity
0x1400136bb  nop     dword ptr [rax+rax+00h]
0x1400136c0  mov     r8d, eax
0x1400136c3  mov     esi, eax
0x1400136c5  xchg    r8d, [rdi+4]
0x1400136c9  mov     edx, [rdi+4]
0x1400136cc  cmp     edx, r8d
0x1400136cf  jnz     short loc_14001372E
0x1400136d1  mov     r14, [rsp+28h+arg_10]
0x1400136d6  test    esi, esi
0x1400136d8  js      short loc_140013720
0x1400136da  mov     rax, [rbp+90h]
0x1400136e1  mov     rcx, [rbx+18h]
0x1400136e5  mov     [rcx], rax
0x1400136e8  xor     eax, eax
0x1400136ea  mov     dword ptr [rbx+30h], 0
0x1400136f1  mov     qword ptr [rbx+38h], 8
0x1400136f9  mov     rbp, [rsp+28h+arg_0]
0x1400136fe  mov     rsi, [rsp+28h+arg_8]
0x140013703  mov     rbx, [rsp+28h+arg_18]
0x140013708  add     rsp, 20h
0x14001370c  pop     rdi
0x14001370d  retn
0x14001370f  mov     rbx, [rsp+28h+arg_18]
0x140013714  mov     eax, 0C0000148h
0x140013719  add     rsp, 20h
0x14001371d  pop     rdi
0x14001371e  retn
0x140013720  mov     [rbx+30h], esi
0x140013723  mov     eax, esi
0x140013725  jmp     short loc_1400136F9
0x140013727  mov     eax, 0C0000023h
0x14001372c  jmp     short loc_140013703
0x14001372e  mov     rcx, [r14+200h]; DeviceObject
0x140013735  xor     edx, edx; Type
0x140013737  call    cs:__imp_IoInvalidateDeviceRelations
0x14001373e  nop     dword ptr [rax+rax+00h]
0x140013743  jmp     short loc_1400136D1
```
