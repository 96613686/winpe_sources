# _GetCorSvcInstaller_::_1_::dtor$0

- ea: `0x140014a9d`
- end: `0x140014aa9`
- name: `_GetCorSvcInstaller_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140009cf0`

## pseudocode

```c
__int64 __fastcall GetCorSvcInstaller_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x140014a9d  lea     rcx, [rdx+48h]
0x140014aa4  jmp     ??1?$ReleaseHolder@UICorSvc@@@@QEAA@XZ; ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>(void)
```
