# comexecmd

- ea: `0x180018f44`
- end: `0x180018fee`
- name: `comexecmd`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018cc0`

## callees

- `0x180007f00`
- `0x180018f44`
- `0x18001b684`
- `0x18001bba4`
- `0x18001d300`
- `0x18002f050`

## pseudocode

```c
__int64 __fastcall comexecmd(const CHAR *a1, __int64 a2, __int64 a3)
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
  if ( (unsigned int)cenvarg(a2, a3, &Block, &v7, a1) == -1 )
    return -1;
  v5 = dospawn(2u, a1, (CHAR *)Block, v7);
  free(Block);
  free(v7);
  return v5;
}

```

## disassembly

```asm
0x180018f44  push    rbx
0x180018f46  sub     rsp, 30h
0x180018f4a  mov     [rsp+38h+Block], 0
0x180018f53  mov     r10, r8
0x180018f56  mov     [rsp+38h+arg_18], 0
0x180018f5f  mov     rax, rdx
0x180018f62  mov     rbx, rcx
0x180018f65  test    rcx, rcx
0x180018f68  jnz     short loc_180018F93
0x180018f6a  call    _errno
0x180018f6f  xor     r9d, r9d; LineNo
0x180018f72  mov     [rsp+38h+Reserved], 0; Reserved
0x180018f7b  xor     r8d, r8d; FileName
0x180018f7e  xor     edx, edx; FunctionName
0x180018f80  xor     ecx, ecx; Expression
0x180018f82  mov     dword ptr [rax], 16h
0x180018f88  call    _invalid_parameter
0x180018f8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018f91  jmp     short loc_180018FE8
0x180018f93  test    rax, rax
0x180018f96  jz      short loc_180018F6A
0x180018f98  lea     r9, [rsp+38h+arg_18]
0x180018f9d  mov     [rsp+38h+Reserved], rbx
0x180018fa2  lea     r8, [rsp+38h+Block]
0x180018fa7  mov     rdx, r10
0x180018faa  mov     rcx, rax
0x180018fad  call    _cenvarg
0x180018fb2  cmp     eax, 0FFFFFFFFh
0x180018fb5  jz      short loc_180018F8D
0x180018fb7  mov     r9, [rsp+38h+arg_18]
0x180018fbc  mov     rdx, rbx
0x180018fbf  mov     r8, [rsp+38h+Block]
0x180018fc4  mov     ecx, 2
0x180018fc9  call    _dospawn
0x180018fce  mov     rcx, [rsp+38h+Block]; Block
0x180018fd3  mov     rbx, rax
0x180018fd6  call    free
0x180018fdb  mov     rcx, [rsp+38h+arg_18]; Block
0x180018fe0  call    free
0x180018fe5  mov     rax, rbx
0x180018fe8  add     rsp, 30h
0x180018fec  pop     rbx
0x180018fed  retn
```
