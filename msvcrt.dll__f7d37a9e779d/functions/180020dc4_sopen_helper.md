# _sopen_helper

- ea: `0x180020dc4`
- end: `0x180020ea6`
- name: `_sopen_helper`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180020d70`
- `0x180020eb0`

## callees

- `0x180007f00`
- `0x18002026c`
- `0x180020dc4`
- `0x180020ee8`
- `0x1800230dc`
- `0x18002f050`

## pseudocode

```c
__int64 __fastcall sopen_helper(const CHAR *a1, unsigned int a2, int a3, int a4, int *a5, int a6)
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
  v6 = tsopen_nolock(&v9, a5, a1, a2, a3, a4);
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
0x180020dc4  mov     [rsp+arg_0], rbx
0x180020dc9  push    rdi
0x180020dca  sub     rsp, 50h
0x180020dce  mov     [rsp+58h+var_18], 0
0x180020dd6  mov     rbx, [rsp+58h+arg_20]
0x180020dde  test    rbx, rbx
0x180020de1  jnz     short loc_180020E14
0x180020de3  call    _errno
0x180020de8  mov     ebx, 16h
0x180020ded  mov     [rax], ebx
0x180020def  mov     [rsp+58h+Reserved], 0; Reserved
0x180020df8  xor     r9d, r9d; LineNo
0x180020dfb  xor     r8d, r8d; FileName
0x180020dfe  xor     edx, edx; FunctionName
0x180020e00  xor     ecx, ecx; Expression
0x180020e02  call    _invalid_parameter
0x180020e07  mov     eax, ebx
0x180020e09  mov     rbx, [rsp+58h+arg_0]
0x180020e0e  add     rsp, 50h
0x180020e12  pop     rdi
0x180020e13  retn
0x180020e14  mov     dword ptr [rbx], 0FFFFFFFFh
0x180020e1a  test    rcx, rcx
0x180020e1d  jz      short loc_180020DE3
0x180020e1f  mov     [rsp+58h+var_14], 0
0x180020e27  mov     eax, [rsp+58h+arg_28]
0x180020e2e  test    eax, eax
0x180020e30  jz      short loc_180020E3B
0x180020e32  test    r9d, 0FFFFFE7Fh
0x180020e39  jnz     short loc_180020DE3
0x180020e3b  mov     [rsp+58h+var_28], eax
0x180020e3f  mov     [rsp+58h+var_30], r9d
0x180020e44  mov     dword ptr [rsp+58h+Reserved], r8d
0x180020e49  mov     r9d, edx
0x180020e4c  mov     r8, rcx
0x180020e4f  mov     rdx, rbx
0x180020e52  lea     rcx, [rsp+58h+var_18]
0x180020e57  call    _tsopen_nolock
0x180020e5c  mov     edi, eax
0x180020e5e  mov     [rsp+58h+var_14], eax
0x180020e62  cmp     [rsp+58h+var_18], 0
0x180020e67  jz      short loc_180020E95
0x180020e69  test    edi, edi
0x180020e6b  jz      short loc_180020E8E
0x180020e6d  movsxd  rcx, dword ptr [rbx]
0x180020e70  mov     rax, rcx
0x180020e73  sar     rax, 5
0x180020e77  lea     rdx, __pioinfo
0x180020e7e  and     ecx, 1Fh
0x180020e81  imul    rcx, 38h ; '8'
0x180020e85  mov     rax, [rdx+rax*8]
0x180020e89  and     byte ptr [rax+rcx+8], 0FEh
0x180020e8e  mov     ecx, [rbx]
0x180020e90  call    _unlock_fhandle
0x180020e95  test    edi, edi
0x180020e97  jz      short loc_180020E9F
0x180020e99  mov     dword ptr [rbx], 0FFFFFFFFh
0x180020e9f  mov     eax, edi
0x180020ea1  jmp     loc_180020E09
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
