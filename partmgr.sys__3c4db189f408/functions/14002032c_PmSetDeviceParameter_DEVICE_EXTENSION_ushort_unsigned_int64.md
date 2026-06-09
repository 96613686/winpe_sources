# PmSetDeviceParameter(_DEVICE_EXTENSION *,ushort *,unsigned __int64)

- ea: `0x14002032c`
- end: `0x1400203ac`
- name: `?PmSetDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAG_K@Z`
- size: `128`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ab3c`

## callees

- `0x14002032c`
- `0x140023540`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140020397`
- `ntoskrnl!ZwClose` at `0x140020397`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14002037c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14002037c`

## pseudocode

```c
__int64 __fastcall PmSetDeviceParameter(struct _DEVICE_EXTENSION *a1, unsigned __int16 *a2, __int64 a3)
{
  NTSTATUS v3; // edi
  PCWSTR Path; // [rsp+48h] [rbp+10h] BYREF
  __int64 ValueData; // [rsp+50h] [rbp+18h] BYREF

  ValueData = a3;
  Path = 0;
  v3 = PmOpenDeviceParameter(a1, (void **)&Path);
  if ( v3 >= 0 )
    v3 = RtlWriteRegistryValue(0x40000000u, Path, ATTRIBUTES, 0xBu, &ValueData, 8u);
  if ( Path )
    ZwClose((HANDLE)Path);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002032c  mov     rax, rsp
0x14002032f  mov     [rax+18h], r8
0x140020333  mov     [rax+10h], rdx
0x140020337  push    rdi
0x140020338  sub     rsp, 30h
0x14002033c  lea     rdx, [rax+10h]; void **
0x140020340  mov     qword ptr [rax+10h], 0
0x140020348  call    ?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z; PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)
0x14002034d  mov     edi, eax
0x14002034f  test    eax, eax
0x140020351  js      short loc_14002038A
0x140020353  mov     rdx, [rsp+38h+Path]; Path
0x140020358  lea     rax, [rsp+38h+arg_10]
0x14002035d  mov     [rsp+38h+ValueLength], 8; ValueLength
0x140020365  lea     r8, ?ATTRIBUTES@@3PAGA; "Attributes"
0x14002036c  mov     r9d, 0Bh; ValueType
0x140020372  mov     [rsp+38h+ValueData], rax; ValueData
0x140020377  mov     ecx, 40000000h; RelativeTo
0x14002037c  call    cs:__imp_RtlWriteRegistryValue
0x140020383  nop     dword ptr [rax+rax+00h]
0x140020388  mov     edi, eax
0x14002038a  cmp     [rsp+38h+Path], 0
0x140020390  jz      short loc_1400203A3
0x140020392  mov     rcx, [rsp+38h+Path]; Handle
0x140020397  call    cs:__imp_ZwClose
0x14002039e  nop     dword ptr [rax+rax+00h]
0x1400203a3  mov     eax, edi
0x1400203a5  add     rsp, 30h
0x1400203a9  pop     rdi
0x1400203aa  retn
```
