# ATL::ModuleLockHelper::ModuleLockHelper(void)

- ea: `0x18000209c`
- end: `0x1800020c1`
- name: `??0ModuleLockHelper@ATL@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(ATL::ModuleLockHelper *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180005f70`
- `0x180008220`
- `0x18000b410`

## callees

- `0x18000d010`

## pseudocode

```c
ATL::ModuleLockHelper *__fastcall ATL::ModuleLockHelper::ModuleLockHelper(ATL::ModuleLockHelper *this)
{
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return this;
}

```

## disassembly

```asm
0x18000209c  push    rbx
0x18000209e  sub     rsp, 20h
0x1800020a2  mov     rbx, rcx
0x1800020a5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800020ac  mov     rax, [rcx]
0x1800020af  mov     rax, [rax+8]
0x1800020b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b8  mov     rax, rbx
0x1800020bb  add     rsp, 20h
0x1800020bf  pop     rbx
0x1800020c0  retn
```
