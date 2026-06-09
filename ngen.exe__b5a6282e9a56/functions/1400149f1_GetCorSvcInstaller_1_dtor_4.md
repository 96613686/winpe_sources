# _GetCorSvcInstaller_::_1_::dtor$4

- ea: `0x1400149f1`
- end: `0x1400149fd`
- name: `_GetCorSvcInstaller_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140009cf0`

## pseudocode

```c
__int64 __fastcall GetCorSvcInstaller_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x1400149f1  lea     rcx, [rdx+38h]
0x1400149f8  jmp     ??1?$ReleaseHolder@UICorSvc@@@@QEAA@XZ; ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>(void)
```
