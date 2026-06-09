# CscDriverpFree

- ea: `0x180003e90`
- end: `0x180003edc`
- name: `CscDriverpFree`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002db0`
- `0x180003920`

## callees

- `0x180003e90`
- `0x180008eb0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003e9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003e9e`

## pseudocode

```c
_UNKNOWN **__fastcall CscDriverpFree(void *a1, __int64 a2, __int64 a3)
{
  _UNKNOWN **result; // rax

  if ( a1 )
    LocalFree(a1);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    return (_UNKNOWN **)WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, a3, a1);
  }
  return result;
}

```

## disassembly

```asm
0x180003e90  push    rbx
0x180003e92  sub     rsp, 20h
0x180003e96  mov     rbx, rcx
0x180003e99  test    rcx, rcx
0x180003e9c  jz      short loc_180003EA4
0x180003e9e  call    cs:__imp_LocalFree
0x180003ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eab  lea     rax, WPP_GLOBAL_Control
0x180003eb2  cmp     rcx, rax
0x180003eb5  jz      short loc_180003EBD
0x180003eb7  test    byte ptr [rcx+44h], 40h
0x180003ebb  jnz     short loc_180003EC3
0x180003ebd  add     rsp, 20h
0x180003ec1  pop     rbx
0x180003ec2  retn
0x180003ec3  cmp     byte ptr [rcx+41h], 4
0x180003ec7  jb      short loc_180003EBD
0x180003ec9  mov     rcx, [rcx+38h]
0x180003ecd  mov     edx, 0Bh
0x180003ed2  mov     r9, rbx
0x180003ed5  call    WPP_SF_q
0x180003eda  jmp     short loc_180003EBD
```
