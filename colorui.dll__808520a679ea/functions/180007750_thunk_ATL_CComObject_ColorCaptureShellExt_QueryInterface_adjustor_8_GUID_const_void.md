# [thunk]:ATL::CComObject<ColorCaptureShellExt>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007750`
- end: `0x180007759`
- name: `?QueryInterface@?$CComObject@VColorCaptureShellExt@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007730`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorCaptureShellExt>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<ColorCaptureShellExt>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180007750  sub     rcx, 8
0x180007754  jmp     ?QueryInterface@?$CComObject@VColorCaptureShellExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<ColorCaptureShellExt>::QueryInterface(_GUID const &,void * *)
```
