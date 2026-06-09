# ISAPI_DLL_MANAGER::InvalidateEntry(ISAPI_DLL *,void *)

- ea: `0x180002150`
- end: `0x180002160`
- name: `?InvalidateEntry@ISAPI_DLL_MANAGER@@CA?AW4LK_ACTION@@PEAVISAPI_DLL@@PEAX@Z`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall ISAPI_DLL_MANAGER::InvalidateEntry(__int64 a1)
{
  *(_DWORD *)(a1 + 164) = 0;
  return 3;
}

```

## disassembly

```asm
0x180002150  mov     dword ptr [rcx+0A4h], 0
0x18000215a  mov     eax, 3
0x18000215f  retn
```
