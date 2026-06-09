# std::_Temporary_owner<MapsBackgroundTransferJob>::~_Temporary_owner<MapsBackgroundTransferJob>(void)

- ea: `0x18000b214`
- end: `0x18000b22f`
- name: `??1?$_Temporary_owner@VMapsBackgroundTransferJob@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void *__fastcall(MapsBackgroundTransferJob **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009754`
- `0x1800140de`

## callees

- `0x18000b214`
- `0x18000b980`

## pseudocode

```c
void *__fastcall std::_Temporary_owner<MapsBackgroundTransferJob>::~_Temporary_owner<MapsBackgroundTransferJob>(
        MapsBackgroundTransferJob **a1)
{
  MapsBackgroundTransferJob *v1; // rcx
  void *result; // rax

  v1 = *a1;
  if ( v1 )
    return MapsBackgroundTransferJob::`vector deleting destructor'(v1, 1u);
  return result;
}

```

## disassembly

```asm
0x18000b214  sub     rsp, 28h
0x18000b218  mov     rcx, [rcx]; this
0x18000b21b  test    rcx, rcx
0x18000b21e  jz      short loc_18000B22A
0x18000b220  mov     edx, 1; unsigned int
0x18000b225  call    ??_EMapsBackgroundTransferJob@@UEAAPEAXI@Z; MapsBackgroundTransferJob::`vector deleting destructor'(uint)
0x18000b22a  add     rsp, 28h
0x18000b22e  retn
```
