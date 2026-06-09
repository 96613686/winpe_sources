# CscDriverpAllocate

- ea: `0x180003650`
- end: `0x1800036a9`
- name: `CscDriverpAllocate`
- size: `89`
- prototype: `__int64 __fastcall(SIZE_T uBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002db0`
- `0x180003920`

## callees

- `0x180003650`
- `0x180008d20`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003660`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180003660`

## pseudocode

```c
HLOCAL __fastcall CscDriverpAllocate(SIZE_T uBytes)
{
  unsigned int v1; // edi
  __int64 v2; // rdx
  HLOCAL v3; // rbx
  __int64 v4; // r8

  v1 = uBytes;
  v3 = LocalAlloc(0, (unsigned int)uBytes);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 7), v2, v4, v1, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  push    rdi
0x180003656  sub     rsp, 30h
0x18000365a  mov     edi, ecx
0x18000365c  mov     edx, ecx; uBytes
0x18000365e  xor     ecx, ecx; uFlags
0x180003660  call    cs:__imp_LocalAlloc
0x180003666  mov     rbx, rax
0x180003669  mov     rcx, cs:WPP_GLOBAL_Control
0x180003670  lea     rax, WPP_GLOBAL_Control
0x180003677  cmp     rcx, rax
0x18000367a  jz      short loc_180003682
0x18000367c  test    byte ptr [rcx+44h], 40h
0x180003680  jnz     short loc_180003690
0x180003682  mov     rax, rbx
0x180003685  mov     rbx, [rsp+38h+arg_0]
0x18000368a  add     rsp, 30h
0x18000368e  pop     rdi
0x18000368f  retn
0x180003690  cmp     byte ptr [rcx+41h], 4
0x180003694  jb      short loc_180003682
0x180003696  mov     rcx, [rcx+38h]
0x18000369a  mov     r9d, edi
0x18000369d  mov     [rsp+38h+var_18], rbx
0x1800036a2  call    WPP_SF_Dq
0x1800036a7  jmp     short loc_180003682
```
