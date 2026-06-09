# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x18000a3d4`
- end: `0x18000a3fd`
- name: `??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a404`
- `0x180014190`
- `0x18001425c`
- `0x180019710`
- `0x1800205ac`
- `0x18002194c`
- `0x1800219d4`
- `0x180023ca8`
- `0x18002dd84`
- `0x18002ebdc`

## import_xrefs

- `MSDART!MPInitializeCriticalSection` at `0x18000a3e7`
- `MSDART!MPInitializeCriticalSection` at `0x18000a3e7`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(
        _DWORD *a1)
{
  *a1 = 0;
  MPInitializeCriticalSection(a1 + 2);
  return a1;
}

```

## disassembly

```asm
0x18000a3d4  push    rbx
0x18000a3d6  sub     rsp, 20h
0x18000a3da  mov     rbx, rcx
0x18000a3dd  mov     dword ptr [rcx], 0
0x18000a3e3  add     rcx, 8
0x18000a3e7  call    cs:__imp_MPInitializeCriticalSection
0x18000a3ee  nop     dword ptr [rax+rax+00h]
0x18000a3f3  mov     rax, rbx
0x18000a3f6  add     rsp, 20h
0x18000a3fa  pop     rbx
0x18000a3fb  retn
```
