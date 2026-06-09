# IsValidCscEnumHandle

- ea: `0x180002a20`
- end: `0x180002a38`
- name: `IsValidCscEnumHandle`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a0`
- `0x180006560`

## callees

- `0x180002a20`

## pseudocode

```c
bool __fastcall IsValidCscEnumHandle(_DWORD *a1)
{
  return (unsigned __int64)a1 - 1 <= 0xFFFFFFFFFFFFFFFDuLL && *a1 == 1130718291;
}

```

## disassembly

```asm
0x180002a20  lea     rax, [rcx-1]
0x180002a24  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002a28  ja      short loc_180002A35
0x180002a2a  cmp     dword ptr [rcx], 43656453h
0x180002a30  jnz     short loc_180002A35
0x180002a32  mov     al, 1
0x180002a34  retn
0x180002a35  xor     al, al
0x180002a37  retn
```
