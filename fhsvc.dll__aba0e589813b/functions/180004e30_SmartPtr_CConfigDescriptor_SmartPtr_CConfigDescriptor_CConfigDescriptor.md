# SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)

- ea: `0x180004e30`
- end: `0x180004e43`
- name: `??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z`
- size: `19`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `13`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800020c0`
- `0x180003190`
- `0x180003f00`
- `0x1800062b0`
- `0x1800065c0`
- `0x180009fd0`
- `0x18000a148`
- `0x18000a254`
- `0x18000ac48`
- `0x18000efb4`
- `0x18000f14c`
- `0x18000f2c0`
- `0x18000feb4`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(_QWORD *a1)
{
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x180004e30  sub     rsp, 28h
0x180004e34  mov     qword ptr [rcx], 0
0x180004e3b  mov     rax, rcx
0x180004e3e  add     rsp, 28h
0x180004e42  retn
```
