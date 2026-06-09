# wcomexecmd_0

- ea: `0x18001b018`
- end: `0x18001b0ca`
- name: `wcomexecmd_0`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ad60`

## callees

- `0x180007f00`
- `0x18001b018`
- `0x18001bf4c`
- `0x18001c4a0`
- `0x18001d300`
- `0x18002f050`

## pseudocode

```c
__int64 __fastcall wcomexecmd_0(unsigned int a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rbx
  void *v8; // [rsp+30h] [rbp-18h] BYREF
  void *Block; // [rsp+58h] [rbp+10h] BYREF

  Block = 0;
  v8 = 0;
  if ( !a2 || !a3 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  if ( (unsigned int)wcenvarg(a3, a4, &Block, &v8, a2) == -1 )
    return -1;
  v7 = wdospawn(a1, a2, (WCHAR *)Block, v8);
  free(Block);
  free(v8);
  return v7;
}

```

## disassembly

```asm
0x18001b018  mov     [rsp+arg_0], rbx
0x18001b01d  push    rdi
0x18001b01e  sub     rsp, 40h
0x18001b022  mov     [rsp+48h+Block], 0
0x18001b02b  mov     r10, r9
0x18001b02e  mov     [rsp+48h+var_18], 0
0x18001b037  mov     rax, r8
0x18001b03a  mov     rbx, rdx
0x18001b03d  mov     edi, ecx
0x18001b03f  test    rdx, rdx
0x18001b042  jnz     short loc_18001B06D
0x18001b044  call    _errno
0x18001b049  xor     r9d, r9d; LineNo
0x18001b04c  mov     [rsp+48h+Reserved], 0; Reserved
0x18001b055  xor     r8d, r8d; FileName
0x18001b058  xor     edx, edx; FunctionName
0x18001b05a  xor     ecx, ecx; Expression
0x18001b05c  mov     dword ptr [rax], 16h
0x18001b062  call    _invalid_parameter
0x18001b067  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b06b  jmp     short loc_18001B0BF
0x18001b06d  test    rax, rax
0x18001b070  jz      short loc_18001B044
0x18001b072  lea     r9, [rsp+48h+var_18]
0x18001b077  mov     [rsp+48h+Reserved], rbx
0x18001b07c  lea     r8, [rsp+48h+Block]
0x18001b081  mov     rdx, r10
0x18001b084  mov     rcx, rax
0x18001b087  call    _wcenvarg
0x18001b08c  cmp     eax, 0FFFFFFFFh
0x18001b08f  jz      short loc_18001B067
0x18001b091  mov     r9, [rsp+48h+var_18]
0x18001b096  mov     rdx, rbx
0x18001b099  mov     r8, [rsp+48h+Block]
0x18001b09e  mov     ecx, edi
0x18001b0a0  call    _wdospawn
0x18001b0a5  mov     rcx, [rsp+48h+Block]; Block
0x18001b0aa  mov     rbx, rax
0x18001b0ad  call    free
0x18001b0b2  mov     rcx, [rsp+48h+var_18]; Block
0x18001b0b7  call    free
0x18001b0bc  mov     rax, rbx
0x18001b0bf  mov     rbx, [rsp+48h+arg_0]
0x18001b0c4  add     rsp, 40h
0x18001b0c8  pop     rdi
0x18001b0c9  retn
```
