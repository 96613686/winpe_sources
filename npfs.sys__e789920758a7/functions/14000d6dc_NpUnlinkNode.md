# NpUnlinkNode

- ea: `0x14000d6dc`
- end: `0x14000d721`
- name: `NpUnlinkNode`
- size: `69`
- prototype: `void __fastcall(char *, struct _UNICODE_PREFIX_TABLE *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x14000bbf4`
- `0x14000e570`

## callees

- `0x14000c548`
- `0x14000d6dc`
- `0x14000e570`
- `0x1400107c0`

## pseudocode

```c
void __fastcall NpUnlinkNode(char *a1, struct _UNICODE_PREFIX_TABLE *a2, __int64 a3)
{
  switch ( *(_WORD *)a1 )
  {
    case 0x202:
      NpUnlinkFcb((__int64)a2, (__int64)a1, a3);
      break;
    case 0x203:
      NpUnlinkProtectedPrefix(a2, (__int64)a1, a3);
      break;
    case 0x207:
      NpDeleteSymlink(a1, a2);
      break;
  }
}

```

## disassembly

```asm
0x14000d6dc  sub     rsp, 28h
0x14000d6e0  movzx   r9d, word ptr [rcx]
0x14000d6e4  mov     r10, rdx
0x14000d6e7  sub     r9d, 202h
0x14000d6ee  jz      short loc_14000D714
0x14000d6f0  sub     r9d, 1
0x14000d6f4  jnz     short loc_14000D707
0x14000d6f6  mov     rdx, rcx
0x14000d6f9  mov     rcx, r10
0x14000d6fc  call    NpUnlinkProtectedPrefix
0x14000d701  add     rsp, 28h
0x14000d705  retn
0x14000d707  cmp     r9d, 4
0x14000d70b  jnz     short loc_14000D701
0x14000d70d  call    NpDeleteSymlink
0x14000d712  jmp     short loc_14000D701
0x14000d714  mov     rdx, rcx
0x14000d717  mov     rcx, r10
0x14000d71a  call    NpUnlinkFcb
0x14000d71f  jmp     short loc_14000D701
```
