# PmSetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void *,ulong)

- ea: `0x140023310`
- end: `0x14002338c`
- name: `?PmSetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAXK@Z`
- size: `124`
- prototype: `int(struct _DEVICE_EXTENSION *, unsigned __int16 *, void *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140007bcc`
- `0x14000a964`
- `0x14000ada0`
- `0x14000d878`

## callees

- `0x140023310`
- `0x140023540`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140023373`
- `ntoskrnl!ZwClose` at `0x140023373`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140023358`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140023358`

## pseudocode

```c
__int64 __fastcall PmSetDeviceParameterBinary(struct _DEVICE_EXTENSION *a1, unsigned __int16 *a2, void *a3, ULONG a4)
{
  NTSTATUS v7; // edi
  PCWSTR Path; // [rsp+30h] [rbp-38h] BYREF

  Path = 0;
  v7 = PmOpenDeviceParameter(a1, (void **)&Path);
  if ( v7 >= 0 )
    v7 = RtlWriteRegistryValue(0x40000000u, Path, a2, 3u, a3, a4);
  if ( Path )
    ZwClose((HANDLE)Path);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140023310  push    rbp
0x140023312  push    rsi
0x140023313  push    rdi
0x140023314  push    r14
0x140023316  sub     rsp, 48h
0x14002331a  mov     r14, rdx
0x14002331d  mov     [rsp+68h+Path], 0
0x140023326  lea     rdx, [rsp+68h+Path]; void **
0x14002332b  mov     esi, r9d
0x14002332e  mov     rbp, r8
0x140023331  call    ?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z; PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)
0x140023336  mov     edi, eax
0x140023338  test    eax, eax
0x14002333a  js      short loc_140023366
0x14002333c  mov     rdx, [rsp+68h+Path]; Path
0x140023341  mov     r9d, 3; ValueType
0x140023347  mov     [rsp+68h+ValueLength], esi; ValueLength
0x14002334b  mov     r8, r14; ValueName
0x14002334e  mov     ecx, 40000000h; RelativeTo
0x140023353  mov     [rsp+68h+ValueData], rbp; ValueData
0x140023358  call    cs:__imp_RtlWriteRegistryValue
0x14002335f  nop     dword ptr [rax+rax+00h]
0x140023364  mov     edi, eax
0x140023366  cmp     [rsp+68h+Path], 0
0x14002336c  jz      short loc_14002337F
0x14002336e  mov     rcx, [rsp+68h+Path]; Handle
0x140023373  call    cs:__imp_ZwClose
0x14002337a  nop     dword ptr [rax+rax+00h]
0x14002337f  mov     eax, edi
0x140023381  add     rsp, 48h
0x140023385  pop     r14
0x140023387  pop     rdi
0x140023388  pop     rsi
0x140023389  pop     rbp
0x14002338a  retn
```
