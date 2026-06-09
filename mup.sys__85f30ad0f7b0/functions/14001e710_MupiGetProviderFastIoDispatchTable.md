# MupiGetProviderFastIoDispatchTable

- ea: `0x14001e710`
- end: `0x14001e737`
- name: `MupiGetProviderFastIoDispatchTable`
- size: `39`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000f6e0`
- `0x14000f7b0`
- `0x14000f830`
- `0x14000f8a0`
- `0x14000f930`
- `0x14000f9b0`
- `0x14000fa80`
- `0x14000fb50`
- `0x14000fbc0`
- `0x14000fc30`

## callees

- `0x1400023a0`
- `0x14001e710`

## pseudocode

```c
__int64 __fastcall MupiGetProviderFastIoDispatchTable(struct _FILE_OBJECT *a1, __int64 *a2)
{
  __int64 result; // rax
  __int64 v4; // rcx

  result = MupGetUncProviderDeviceObjectFromFileObject(a1);
  if ( result )
  {
    v4 = *(_QWORD *)(result + 8);
    *a2 = result;
    return *(_QWORD *)(v4 + 80);
  }
  return result;
}

```

## disassembly

```asm
0x14001e710  push    rbx
0x14001e712  sub     rsp, 20h
0x14001e716  mov     rbx, rdx
0x14001e719  call    MupGetUncProviderDeviceObjectFromFileObject
0x14001e71e  test    rax, rax
0x14001e721  jz      short loc_14001E735
0x14001e723  mov     rcx, [rax+8]
0x14001e727  mov     [rbx], rax
0x14001e72a  mov     rax, [rcx+50h]
0x14001e72e  add     rsp, 20h
0x14001e732  pop     rbx
0x14001e733  retn
0x14001e735  jmp     short loc_14001E72E
```
