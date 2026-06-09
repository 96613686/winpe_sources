# CreateCbsLogMonitorProvider

- ea: `0x140012b60`
- end: `0x140012b82`
- name: `CreateCbsLogMonitorProvider`
- size: `34`
- prototype: `_QWORD *()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001fe4`
- `0x140012b60`

## pseudocode

```c
_QWORD *CreateCbsLogMonitorProvider()
{
  _QWORD *result; // rax

  result = operator new(8u);
  if ( result )
    *result = &CCbsLogMonitorProvider::`vftable';
  return result;
}

```

## disassembly

```asm
0x140012b60  sub     rsp, 28h
0x140012b64  mov     ecx, 8; Size
0x140012b69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012b6e  test    rax, rax
0x140012b71  jz      short loc_140012B7D
0x140012b73  lea     rcx, ??_7CCbsLogMonitorProvider@@6B@; const CCbsLogMonitorProvider::`vftable'
0x140012b7a  mov     [rax], rcx
0x140012b7d  add     rsp, 28h
0x140012b81  retn
```
