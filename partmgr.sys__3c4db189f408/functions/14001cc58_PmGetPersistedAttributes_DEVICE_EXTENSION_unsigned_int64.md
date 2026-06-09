# PmGetPersistedAttributes(_DEVICE_EXTENSION *,unsigned __int64 *)

- ea: `0x14001cc58`
- end: `0x14001ccac`
- name: `?PmGetPersistedAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEA_K@Z`
- size: `84`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14002589c`

## callees

- `0x14001cc58`
- `0x14001fbdc`
- `0x14001fcbc`

## pseudocode

```c
__int64 __fastcall PmGetPersistedAttributes(struct _DEVICE_EXTENSION *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdx
  int DeviceParameter; // r8d
  unsigned int v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  DeviceParameter = PmGetDeviceParameter(a1, a2, (unsigned __int64 *)a2);
  if ( DeviceParameter == -1073741788 )
  {
    DeviceParameter = PmGetDeviceParameter(a1, v4, &v7);
    if ( DeviceParameter >= 0 )
      *(_QWORD *)a2 = v7;
  }
  return (unsigned int)DeviceParameter;
}

```

## disassembly

```asm
0x14001cc58  mov     [rsp+arg_0], rbx
0x14001cc5d  push    rdi
0x14001cc5e  sub     rsp, 20h
0x14001cc62  mov     r8, rdx; unsigned __int64 *
0x14001cc65  mov     [rsp+28h+arg_10], 0
0x14001cc6d  mov     rbx, rdx
0x14001cc70  mov     rdi, rcx
0x14001cc73  call    ?PmGetDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEA_K@Z; PmGetDeviceParameter(_DEVICE_EXTENSION *,ushort *,unsigned __int64 *)
0x14001cc78  mov     r8d, eax
0x14001cc7b  cmp     eax, 0C0000024h
0x14001cc80  jnz     short loc_14001CC9D
0x14001cc82  lea     r8, [rsp+28h+arg_10]; unsigned int *
0x14001cc87  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14001cc8a  call    ?PmGetDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAK@Z; PmGetDeviceParameter(_DEVICE_EXTENSION *,ushort *,ulong *)
0x14001cc8f  mov     r8d, eax
0x14001cc92  test    eax, eax
0x14001cc94  js      short loc_14001CC9D
0x14001cc96  mov     eax, [rsp+28h+arg_10]
0x14001cc9a  mov     [rbx], rax
0x14001cc9d  mov     rbx, [rsp+28h+arg_0]
0x14001cca2  mov     eax, r8d
0x14001cca5  add     rsp, 20h
0x14001cca9  pop     rdi
0x14001ccaa  retn
```
