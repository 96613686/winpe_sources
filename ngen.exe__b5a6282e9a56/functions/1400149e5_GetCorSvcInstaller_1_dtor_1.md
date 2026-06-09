# _GetCorSvcInstaller_::_1_::dtor$1

- ea: `0x1400149e5`
- end: `0x1400149f1`
- name: `_GetCorSvcInstaller_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140009cf0`

## pseudocode

```c
__int64 __fastcall GetCorSvcInstaller_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x1400149e5  lea     rcx, [rdx+28h]
0x1400149ec  jmp     ??1?$ReleaseHolder@UICorSvc@@@@QEAA@XZ; ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>(void)
```
