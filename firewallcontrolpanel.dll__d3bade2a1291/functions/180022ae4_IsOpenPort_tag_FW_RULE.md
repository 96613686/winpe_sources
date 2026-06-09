# IsOpenPort(_tag_FW_RULE *)

- ea: `0x180022ae4`
- end: `0x180022b13`
- name: `?IsOpenPort@@YAHPEAU_tag_FW_RULE@@@Z`
- size: `47`
- prototype: `_BOOL8 __fastcall(struct _tag_FW_RULE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180022324`
- `0x18002acc0`

## callees

- `0x180022ae4`

## import_xrefs

- `fwbase!IsRuleOldGlobalOpenPort` at `0x180022afa`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180022afa`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022aed`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022aed`

## pseudocode

```c
_BOOL8 __fastcall IsOpenPort(struct _tag_FW_RULE *a1)
{
  return (unsigned int)IsRuleOpenPortOrAuthApp() && (unsigned int)IsRuleOldGlobalOpenPort(a1);
}

```

## disassembly

```asm
0x180022ae4  push    rbx
0x180022ae6  sub     rsp, 20h
0x180022aea  mov     rbx, rcx
0x180022aed  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180022af3  test    eax, eax
0x180022af5  jz      short loc_180022B0B
0x180022af7  mov     rcx, rbx
0x180022afa  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180022b00  test    eax, eax
0x180022b02  jz      short loc_180022B0B
0x180022b04  mov     eax, 1
0x180022b09  jmp     short loc_180022B0D
0x180022b0b  xor     eax, eax
0x180022b0d  add     rsp, 20h
0x180022b11  pop     rbx
0x180022b12  retn
```
