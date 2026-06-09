# PmCreateDisk(_DEVICE_EXTENSION *,_CREATE_DISK *)

- ea: `0x1400208c8`
- end: `0x14002091c`
- name: `?PmCreateDisk@@YAJPEAU_DEVICE_EXTENSION@@PEAU_CREATE_DISK@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _CREATE_DISK *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001d6a4`
- `0x14001d7cc`
- `0x140020afc`

## callees

- `0x140007bcc`
- `0x14000cb34`
- `0x14001ced4`
- `0x1400208c8`

## pseudocode

```c
__int64 __fastcall PmCreateDisk(struct _DEVICE_EXTENSION *a1, struct _CREATE_DISK *a2)
{
  __int64 result; // rax

  if ( !*((_BYTE *)PmControlObject->DeviceExtension + 168) && *((_BYTE *)a1 + 604) )
    return 3221225506LL;
  result = PmCreatePartitionTable(*((struct _DEVICE_OBJECT **)a1 + 1), a2);
  if ( (int)result >= 0 )
  {
    PmInvalidatePartitionTableCache((KSPIN_LOCK *)a1);
    return PmGetDriveLayoutEx((KSPIN_LOCK *)a1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400208c8  push    rbx
0x1400208ca  sub     rsp, 20h
0x1400208ce  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400208d5  mov     rbx, rcx
0x1400208d8  mov     r8, [rax+40h]
0x1400208dc  cmp     byte ptr [r8+0A8h], 0
0x1400208e4  jnz     short loc_1400208F6
0x1400208e6  cmp     byte ptr [rcx+25Ch], 0
0x1400208ed  jz      short loc_1400208F6
0x1400208ef  mov     eax, 0C0000022h
0x1400208f4  jmp     short loc_140020915
0x1400208f6  mov     rcx, [rcx+8]; struct _DEVICE_OBJECT *
0x1400208fa  call    ?PmCreatePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_CREATE_DISK@@@Z; PmCreatePartitionTable(_DEVICE_OBJECT *,_CREATE_DISK *)
0x1400208ff  test    eax, eax
0x140020901  js      short loc_140020915
0x140020903  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140020906  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14002090b  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14002090d  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140020910  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140020915  add     rsp, 20h
0x140020919  pop     rbx
0x14002091a  retn
```
