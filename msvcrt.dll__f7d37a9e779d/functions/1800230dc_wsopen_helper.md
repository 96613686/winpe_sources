# _wsopen_helper

- ea: `0x1800230dc`
- end: `0x1800231be`
- name: `_wsopen_helper`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800230a0`
- `0x1800231d0`

## callees

- `0x180007f00`
- `0x18002026c`
- `0x1800227c0`
- `0x1800230dc`
- `0x18002f050`

## pseudocode

```c
__int64 __fastcall wsopen_helper(const WCHAR *a1, unsigned int a2, int a3, int a4, int *a5, int a6)
{
  unsigned int v6; // edi
  __int64 v7; // rax
  int v9; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-14h]

  v9 = 0;
  if ( !a5 || (*a5 = -1, !a1) || (v10 = 0, a6) && (a4 & 0xFFFFFE7F) != 0 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v6 = tsopen_nolock_0(&v9, a5, a1, a2, a3, a4);
  v10 = v6;
  if ( v9 )
  {
    if ( v6 )
    {
      v7 = _pioinfo[(__int64)*a5 >> 5];
      *(_BYTE *)(v7 + 56LL * (*a5 & 0x1F) + 8) &= ~1u;
    }
    unlock_fhandle((unsigned int)*a5);
  }
  if ( v6 )
    *a5 = -1;
  return v6;
}

```

## disassembly

```asm
0x1800230dc  mov     [rsp+arg_0], rbx
0x1800230e1  push    rdi
0x1800230e2  sub     rsp, 50h
0x1800230e6  mov     [rsp+58h+var_18], 0
0x1800230ee  mov     rbx, [rsp+58h+arg_20]
0x1800230f6  test    rbx, rbx
0x1800230f9  jnz     short loc_18002312C
0x1800230fb  call    _errno
0x180023100  mov     ebx, 16h
0x180023105  mov     [rax], ebx
0x180023107  mov     [rsp+58h+Reserved], 0; Reserved
0x180023110  xor     r9d, r9d; LineNo
0x180023113  xor     r8d, r8d; FileName
0x180023116  xor     edx, edx; FunctionName
0x180023118  xor     ecx, ecx; Expression
0x18002311a  call    _invalid_parameter
0x18002311f  mov     eax, ebx
0x180023121  mov     rbx, [rsp+58h+arg_0]
0x180023126  add     rsp, 50h
0x18002312a  pop     rdi
0x18002312b  retn
0x18002312c  mov     dword ptr [rbx], 0FFFFFFFFh
0x180023132  test    rcx, rcx
0x180023135  jz      short loc_1800230FB
0x180023137  mov     [rsp+58h+var_14], 0
0x18002313f  mov     eax, [rsp+58h+arg_28]
0x180023146  test    eax, eax
0x180023148  jz      short loc_180023153
0x18002314a  test    r9d, 0FFFFFE7Fh
0x180023151  jnz     short loc_1800230FB
0x180023153  mov     [rsp+58h+var_28], eax
0x180023157  mov     [rsp+58h+var_30], r9d
0x18002315c  mov     dword ptr [rsp+58h+Reserved], r8d
0x180023161  mov     r9d, edx
0x180023164  mov     r8, rcx
0x180023167  mov     rdx, rbx
0x18002316a  lea     rcx, [rsp+58h+var_18]
0x18002316f  call    _tsopen_nolock_0
0x180023174  mov     edi, eax
0x180023176  mov     [rsp+58h+var_14], eax
0x18002317a  cmp     [rsp+58h+var_18], 0
0x18002317f  jz      short loc_1800231AD
0x180023181  test    edi, edi
0x180023183  jz      short loc_1800231A6
0x180023185  movsxd  rcx, dword ptr [rbx]
0x180023188  mov     rax, rcx
0x18002318b  sar     rax, 5
0x18002318f  lea     rdx, __pioinfo
0x180023196  and     ecx, 1Fh
0x180023199  imul    rcx, 38h ; '8'
0x18002319d  mov     rax, [rdx+rax*8]
0x1800231a1  and     byte ptr [rax+rcx+8], 0FEh
0x1800231a6  mov     ecx, [rbx]
0x1800231a8  call    _unlock_fhandle
0x1800231ad  test    edi, edi
0x1800231af  jz      short loc_1800231B7
0x1800231b1  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800231b7  mov     eax, edi
0x1800231b9  jmp     loc_180023121
0x18007ba9b  push    rbp
0x18007ba9d  sub     rsp, 40h
0x18007baa1  mov     rbp, rdx
0x18007baa4  cmp     dword ptr [rbp+40h], 0
0x18007baa8  jz      short loc_18007BB0C
0x18007baaa  cmp     dword ptr [rbp+44h], 0
0x18007baae  jz      short loc_18007BAFD
0x18007bab0  mov     r9, [rbp+80h]
0x18007bab7  movsxd  rdx, dword ptr [r9]
0x18007baba  sar     rdx, 5
0x18007babe  lea     r8, __pioinfo
0x18007bac5  mov     eax, [r9]
0x18007bac8  and     eax, 1Fh
0x18007bacb  imul    rcx, rax, 38h ; '8'
0x18007bacf  mov     rax, [r8+rdx*8]
0x18007bad3  mov     r8b, [rax+rcx+8]
0x18007bad8  and     r8b, 0FEh
0x18007badc  movsxd  rdx, dword ptr [r9]
0x18007badf  sar     rdx, 5
0x18007bae3  lea     r10, __pioinfo
0x18007baea  mov     eax, [r9]
0x18007baed  and     eax, 1Fh
0x18007baf0  imul    rcx, rax, 38h ; '8'
0x18007baf4  mov     rax, [r10+rdx*8]
0x18007baf8  mov     [rax+rcx+8], r8b
0x18007bafd  mov     rcx, [rbp+80h]
0x18007bb04  mov     ecx, [rcx]
0x18007bb06  call    _unlock_fhandle
0x18007bb0b  nop
0x18007bb0c  add     rsp, 40h
0x18007bb10  pop     rbp
0x18007bb11  retn
```
