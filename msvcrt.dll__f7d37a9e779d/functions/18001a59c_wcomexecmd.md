# wcomexecmd

- ea: `0x18001a59c`
- end: `0x18001a646`
- name: `wcomexecmd`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a300`

## callees

- `0x180007f00`
- `0x18001a59c`
- `0x18001bf4c`
- `0x18001c4a0`
- `0x18001d300`
- `0x18002f050`

## pseudocode

```c
__int64 __fastcall wcomexecmd(const WCHAR *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  void *Block; // [rsp+40h] [rbp+8h] BYREF
  void *v7; // [rsp+58h] [rbp+20h] BYREF

  Block = 0;
  v7 = 0;
  if ( !a1 || !a2 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  if ( (unsigned int)wcenvarg(a2, a3, &Block, &v7, a1) == -1 )
    return -1;
  v5 = wdospawn(2u, a1, (WCHAR *)Block, v7);
  free(Block);
  free(v7);
  return v5;
}

```

## disassembly

```asm
0x18001a59c  push    rbx
0x18001a59e  sub     rsp, 30h
0x18001a5a2  mov     [rsp+38h+Block], 0
0x18001a5ab  mov     r10, r8
0x18001a5ae  mov     [rsp+38h+arg_18], 0
0x18001a5b7  mov     rax, rdx
0x18001a5ba  mov     rbx, rcx
0x18001a5bd  test    rcx, rcx
0x18001a5c0  jnz     short loc_18001A5EB
0x18001a5c2  call    _errno
0x18001a5c7  xor     r9d, r9d; LineNo
0x18001a5ca  mov     [rsp+38h+Reserved], 0; Reserved
0x18001a5d3  xor     r8d, r8d; FileName
0x18001a5d6  xor     edx, edx; FunctionName
0x18001a5d8  xor     ecx, ecx; Expression
0x18001a5da  mov     dword ptr [rax], 16h
0x18001a5e0  call    _invalid_parameter
0x18001a5e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a5e9  jmp     short loc_18001A640
0x18001a5eb  test    rax, rax
0x18001a5ee  jz      short loc_18001A5C2
0x18001a5f0  lea     r9, [rsp+38h+arg_18]
0x18001a5f5  mov     [rsp+38h+Reserved], rbx
0x18001a5fa  lea     r8, [rsp+38h+Block]
0x18001a5ff  mov     rdx, r10
0x18001a602  mov     rcx, rax
0x18001a605  call    _wcenvarg
0x18001a60a  cmp     eax, 0FFFFFFFFh
0x18001a60d  jz      short loc_18001A5E5
0x18001a60f  mov     r9, [rsp+38h+arg_18]
0x18001a614  mov     rdx, rbx
0x18001a617  mov     r8, [rsp+38h+Block]
0x18001a61c  mov     ecx, 2
0x18001a621  call    _wdospawn
0x18001a626  mov     rcx, [rsp+38h+Block]; Block
0x18001a62b  mov     rbx, rax
0x18001a62e  call    free
0x18001a633  mov     rcx, [rsp+38h+arg_18]; Block
0x18001a638  call    free
0x18001a63d  mov     rax, rbx
0x18001a640  add     rsp, 30h
0x18001a644  pop     rbx
0x18001a645  retn
```
