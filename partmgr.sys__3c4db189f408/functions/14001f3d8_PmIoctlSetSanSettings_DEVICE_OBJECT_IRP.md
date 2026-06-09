# PmIoctlSetSanSettings(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001f3d8`
- end: `0x14001f50a`
- name: `?PmIoctlSetSanSettings@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b890`

## callees

- `0x14001f3d8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001f451`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001f451`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14001f474`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14001f474`
- `ntoskrnl!ZwClose` at `0x14001f4d2`
- `ntoskrnl!ZwClose` at `0x14001f4d2`
- `ntoskrnl!ZwSetValueKey` at `0x14001f4a3`
- `ntoskrnl!ZwSetValueKey` at `0x14001f4a3`
- `ntoskrnl!KeReleaseMutex` at `0x14001f4e8`
- `ntoskrnl!KeReleaseMutex` at `0x14001f4e8`

## pseudocode

```c
__int64 __fastcall PmIoctlSetSanSettings(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v3; // ebx
  struct _IRP *MasterIrp; // r14
  char *DeviceExtension; // rbp
  _DWORD *v6; // r14
  char v7; // si
  HANDLE KeyHandle; // [rsp+50h] [rbp+8h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  KeyHandle = 0;
  if ( CurrentStackLocation->Parameters.Create.Options >= 8 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    if ( *(_DWORD *)&MasterIrp->Type == 8 )
    {
      DeviceExtension = (char *)a1->DeviceExtension;
      v6 = &MasterIrp->Size + 1;
      v7 = 1;
      if ( (unsigned int)(*v6 - 1) > 5 )
      {
        v7 = 0;
        v3 = -1073741811;
      }
      else
      {
        KeWaitForSingleObject(DeviceExtension + 16, Executive, 0, 0, 0);
        v3 = IoOpenDriverRegistryKey(*((_QWORD *)DeviceExtension + 1), 1, 2, 0, &KeyHandle);
        if ( v3 >= 0 )
        {
          v3 = ZwSetValueKey(KeyHandle, &SanPolicy, 0, 4u, v6, 4u);
          if ( v3 >= 0 )
            *((_DWORD *)DeviceExtension + 40) = *v6;
        }
      }
      if ( KeyHandle )
        ZwClose(KeyHandle);
      if ( v7 )
        KeReleaseMutex((PRKMUTEX)(DeviceExtension + 16), 0);
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741820;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001f3d8  mov     [rsp+arg_8], rbx
0x14001f3dd  mov     [rsp+arg_10], rbp
0x14001f3e2  push    rsi
0x14001f3e3  push    rdi
0x14001f3e4  push    r14
0x14001f3e6  sub     rsp, 30h
0x14001f3ea  mov     rax, [rdx+0B8h]
0x14001f3f1  mov     [rsp+48h+KeyHandle], 0
0x14001f3fa  cmp     dword ptr [rax+10h], 8
0x14001f3fe  jnb     short loc_14001F40A
0x14001f400  mov     ebx, 0C0000004h
0x14001f405  jmp     loc_14001F4F4
0x14001f40a  mov     r14, [rdx+18h]
0x14001f40e  cmp     dword ptr [r14], 8
0x14001f412  jz      short loc_14001F41E
0x14001f414  mov     ebx, 0C000000Dh
0x14001f419  jmp     loc_14001F4F4
0x14001f41e  mov     rbp, [rcx+40h]
0x14001f422  add     r14, 4
0x14001f426  mov     esi, 1
0x14001f42b  mov     eax, [r14]
0x14001f42e  lea     rdi, [rbp+10h]
0x14001f432  sub     eax, esi
0x14001f434  cmp     eax, 5
0x14001f437  ja      loc_14001F4C0
0x14001f43d  xor     r9d, r9d; Alertable
0x14001f440  mov     [rsp+48h+Timeout], 0; Timeout
0x14001f449  xor     r8d, r8d; WaitMode
0x14001f44c  xor     edx, edx; WaitReason
0x14001f44e  mov     rcx, rdi; Object
0x14001f451  call    cs:__imp_KeWaitForSingleObject
0x14001f458  nop     dword ptr [rax+rax+00h]
0x14001f45d  mov     rcx, [rbp+8]
0x14001f461  lea     rax, [rsp+48h+KeyHandle]
0x14001f466  xor     r9d, r9d
0x14001f469  mov     [rsp+48h+Timeout], rax
0x14001f46e  lea     r8d, [rsi+1]
0x14001f472  mov     edx, esi
0x14001f474  call    cs:__imp_IoOpenDriverRegistryKey
0x14001f47b  nop     dword ptr [rax+rax+00h]
0x14001f480  mov     ebx, eax
0x14001f482  test    eax, eax
0x14001f484  js      short loc_14001F4C8
0x14001f486  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14001f48b  lea     r9d, [rsi+3]; Type
0x14001f48f  mov     [rsp+48h+DataSize], r9d; DataSize
0x14001f494  lea     rdx, ?SanPolicy@@3U_UNICODE_STRING@@A; ValueName
0x14001f49b  xor     r8d, r8d; TitleIndex
0x14001f49e  mov     [rsp+48h+Timeout], r14; Data
0x14001f4a3  call    cs:__imp_ZwSetValueKey
0x14001f4aa  nop     dword ptr [rax+rax+00h]
0x14001f4af  mov     ebx, eax
0x14001f4b1  test    eax, eax
0x14001f4b3  js      short loc_14001F4C8
0x14001f4b5  mov     eax, [r14]
0x14001f4b8  mov     [rbp+0A0h], eax
0x14001f4be  jmp     short loc_14001F4C8
0x14001f4c0  xor     sil, sil
0x14001f4c3  mov     ebx, 0C000000Dh
0x14001f4c8  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x14001f4cd  test    rcx, rcx
0x14001f4d0  jz      short loc_14001F4DE
0x14001f4d2  call    cs:__imp_ZwClose
0x14001f4d9  nop     dword ptr [rax+rax+00h]
0x14001f4de  test    sil, sil
0x14001f4e1  jz      short loc_14001F4F4
0x14001f4e3  xor     edx, edx; Wait
0x14001f4e5  mov     rcx, rdi; Mutex
0x14001f4e8  call    cs:__imp_KeReleaseMutex
0x14001f4ef  nop     dword ptr [rax+rax+00h]
0x14001f4f4  mov     rbp, [rsp+48h+arg_10]
0x14001f4f9  mov     eax, ebx
0x14001f4fb  mov     rbx, [rsp+48h+arg_8]
0x14001f500  add     rsp, 30h
0x14001f504  pop     r14
0x14001f506  pop     rdi
0x14001f507  pop     rsi
0x14001f508  retn
```
