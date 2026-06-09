# _FindAndUnlinkFrame

- ea: `0x18000d83c`
- end: `0x18000d8a2`
- name: `_FindAndUnlinkFrame`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c4c0`
- `0x1800166c0`

## callees

- `0x18000b3f0`
- `0x18000d83c`
- `0x18003e048`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rbx

  result = getptd();
  if ( a1 != *(_QWORD *)(result + 288) )
    goto LABEL_11;
  if ( !result )
    result = getptd();
  v3 = *(_QWORD *)(result + 288);
  if ( !v3 )
LABEL_11:
    _inconsistency();
  while ( 1 )
  {
    v4 = *(_QWORD *)(v3 + 8);
    if ( a1 == v3 )
      break;
    v3 = *(_QWORD *)(v3 + 8);
    if ( !v4 )
      goto LABEL_11;
  }
  if ( !result )
    result = getptd();
  *(_QWORD *)(result + 288) = v4;
  return result;
}

```

## disassembly

```asm
0x18000d83c  mov     [rsp+arg_0], rbx
0x18000d841  push    rdi
0x18000d842  sub     rsp, 20h
0x18000d846  mov     rdi, rcx
0x18000d849  call    _getptd
0x18000d84e  cmp     rdi, [rax+120h]
0x18000d855  jnz     short loc_18000D89C
0x18000d857  test    rax, rax
0x18000d85a  jnz     short loc_18000D861
0x18000d85c  call    _getptd
0x18000d861  mov     rcx, [rax+120h]
0x18000d868  test    rcx, rcx
0x18000d86b  jz      short loc_18000D89C
0x18000d86d  mov     rbx, [rcx+8]
0x18000d871  cmp     rdi, rcx
0x18000d874  jz      short loc_18000D880
0x18000d876  mov     rcx, rbx
0x18000d879  test    rbx, rbx
0x18000d87c  jz      short loc_18000D89C
0x18000d87e  jmp     short loc_18000D86D
0x18000d880  test    rax, rax
0x18000d883  jnz     short loc_18000D88A
0x18000d885  call    _getptd
0x18000d88a  mov     [rax+120h], rbx
0x18000d891  mov     rbx, [rsp+28h+arg_0]
0x18000d896  add     rsp, 20h
0x18000d89a  pop     rdi
0x18000d89b  retn
0x18000d89c  call    ?_inconsistency@@YAXXZ; _inconsistency(void)
```
