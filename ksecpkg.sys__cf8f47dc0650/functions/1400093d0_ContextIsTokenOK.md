# ContextIsTokenOK

- ea: `0x1400093d0`
- end: `0x1400093f2`
- name: `ContextIsTokenOK`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008af4`

## callees

- `0x1400093d0`

## pseudocode

```c
bool __fastcall ContextIsTokenOK(__int64 a1, unsigned int a2)
{
  bool result; // al

  result = 0;
  if ( a1 && (*(_QWORD *)(a1 + 8) || !*(_DWORD *)a1) )
    return !a2 || *(_DWORD *)a1 <= a2;
  return result;
}

```

## disassembly

```asm
0x1400093d0  xor     eax, eax
0x1400093d2  test    rcx, rcx
0x1400093d5  jz      short locret_1400093F1
0x1400093d7  cmp     [rcx+8], rax
0x1400093db  jnz     short loc_1400093E1
0x1400093dd  cmp     [rcx], eax
0x1400093df  jnz     short locret_1400093F1
0x1400093e1  test    edx, edx
0x1400093e3  jz      short loc_1400093EC
0x1400093e5  cmp     [rcx], edx
0x1400093e7  setbe   al
0x1400093ea  retn
0x1400093ec  mov     eax, 1
0x1400093f1  retn
```
