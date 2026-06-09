# PnpCleanTaskStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)

- ea: `0x180003ba0`
- end: `0x180003bb2`
- name: `?PnpCleanTaskStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z`
- size: `18`
- prototype: `_BOOL8 __fastcall(struct _PNPCLEAN_STATUS_DATA *, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003ba0`

## pseudocode

```c
_BOOL8 __fastcall PnpCleanTaskStatusCallback(struct _PNPCLEAN_STATUS_DATA *a1, _DWORD *a2)
{
  _BOOL8 result; // rax

  result = 1;
  if ( a2 )
    return *a2 == 0;
  return result;
}

```

## disassembly

```asm
0x180003ba0  mov     eax, 1
0x180003ba5  test    rdx, rdx
0x180003ba8  jz      short locret_180003BB1
0x180003baa  xor     ecx, ecx
0x180003bac  cmp     [rdx], ecx
0x180003bae  cmovnz  eax, ecx
0x180003bb1  retn
```
