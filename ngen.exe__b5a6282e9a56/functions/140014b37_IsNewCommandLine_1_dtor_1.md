# _IsNewCommandLine_::_1_::dtor$1

- ea: `0x140014b37`
- end: `0x140014b43`
- name: `_IsNewCommandLine_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009cf0`

## pseudocode

```c
__int64 __fastcall IsNewCommandLine_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140014b37  lea     rcx, [rdx+30h]
0x140014b3e  jmp     ??1?$ReleaseHolder@UICorSvc@@@@QEAA@XZ; ReleaseHolder<ICorSvc>::~ReleaseHolder<ICorSvc>(void)
```
