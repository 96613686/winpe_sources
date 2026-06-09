# comexecmd_0

- ea: `0x180019aa8`
- end: `0x180019b5a`
- name: `comexecmd_0`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019810`

## callees

- `0x180007f00`
- `0x180019aa8`
- `0x18001b684`
- `0x18001bba4`
- `0x18001d300`
- `0x18002f050`

## pseudocode

```c
__int64 __fastcall comexecmd_0(unsigned int a1, const CHAR *a2, __int64 a3, __int64 a4)
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
  if ( (unsigned int)cenvarg(a3, a4, &Block, &v8, a2) == -1 )
    return -1;
  v7 = dospawn(a1, a2, (CHAR *)Block, v8);
  free(Block);
  free(v8);
  return v7;
}

```

## disassembly

```asm
0x180019aa8  mov     [rsp+arg_0], rbx
0x180019aad  push    rdi
0x180019aae  sub     rsp, 40h
0x180019ab2  mov     [rsp+48h+Block], 0
0x180019abb  mov     r10, r9
0x180019abe  mov     [rsp+48h+var_18], 0
0x180019ac7  mov     rax, r8
0x180019aca  mov     rbx, rdx
0x180019acd  mov     edi, ecx
0x180019acf  test    rdx, rdx
0x180019ad2  jnz     short loc_180019AFD
0x180019ad4  call    _errno
0x180019ad9  xor     r9d, r9d; LineNo
0x180019adc  mov     [rsp+48h+Reserved], 0; Reserved
0x180019ae5  xor     r8d, r8d; FileName
0x180019ae8  xor     edx, edx; FunctionName
0x180019aea  xor     ecx, ecx; Expression
0x180019aec  mov     dword ptr [rax], 16h
0x180019af2  call    _invalid_parameter
0x180019af7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019afb  jmp     short loc_180019B4F
0x180019afd  test    rax, rax
0x180019b00  jz      short loc_180019AD4
0x180019b02  lea     r9, [rsp+48h+var_18]
0x180019b07  mov     [rsp+48h+Reserved], rbx
0x180019b0c  lea     r8, [rsp+48h+Block]
0x180019b11  mov     rdx, r10
0x180019b14  mov     rcx, rax
0x180019b17  call    _cenvarg
0x180019b1c  cmp     eax, 0FFFFFFFFh
0x180019b1f  jz      short loc_180019AF7
0x180019b21  mov     r9, [rsp+48h+var_18]
0x180019b26  mov     rdx, rbx
0x180019b29  mov     r8, [rsp+48h+Block]
0x180019b2e  mov     ecx, edi
0x180019b30  call    _dospawn
0x180019b35  mov     rcx, [rsp+48h+Block]; Block
0x180019b3a  mov     rbx, rax
0x180019b3d  call    free
0x180019b42  mov     rcx, [rsp+48h+var_18]; Block
0x180019b47  call    free
0x180019b4c  mov     rax, rbx
0x180019b4f  mov     rbx, [rsp+48h+arg_0]
0x180019b54  add     rsp, 40h
0x180019b58  pop     rdi
0x180019b59  retn
```
