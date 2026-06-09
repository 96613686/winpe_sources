# IsAuthApp(_tag_FW_RULE *)

- ea: `0x180022aac`
- end: `0x180022adb`
- name: `?IsAuthApp@@YAHPEAU_tag_FW_RULE@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022324`

## callees

- `0x180022aac`

## import_xrefs

- `fwbase!IsRuleOldAuthApp` at `0x180022ac2`
- `fwbase!IsRuleOldAuthApp` at `0x180022ac2`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022ab5`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022ab5`

## pseudocode

```c
_BOOL8 __fastcall IsAuthApp(struct _tag_FW_RULE *a1)
{
  return (unsigned int)IsRuleOpenPortOrAuthApp() && (unsigned int)IsRuleOldAuthApp(a1);
}

```

## disassembly

```asm
0x180022aac  push    rbx
0x180022aae  sub     rsp, 20h
0x180022ab2  mov     rbx, rcx
0x180022ab5  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180022abb  test    eax, eax
0x180022abd  jz      short loc_180022AD3
0x180022abf  mov     rcx, rbx
0x180022ac2  call    cs:__imp_IsRuleOldAuthApp
0x180022ac8  test    eax, eax
0x180022aca  jz      short loc_180022AD3
0x180022acc  mov     eax, 1
0x180022ad1  jmp     short loc_180022AD5
0x180022ad3  xor     eax, eax
0x180022ad5  add     rsp, 20h
0x180022ad9  pop     rbx
0x180022ada  retn
```
