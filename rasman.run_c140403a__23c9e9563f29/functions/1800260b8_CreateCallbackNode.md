# CreateCallbackNode

- ea: `0x1800260b8`
- end: `0x180026154`
- name: `CreateCallbackNode`
- size: `156`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR, STRSAFE_LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002541c`

## callees

- `0x1800246f4`
- `0x180025040`
- `0x180026058`
- `0x1800260b8`

## pseudocode

```c
__int64 __fastcall CreateCallbackNode(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, STRSAFE_LPCWSTR a3, int a4)
{
  __int64 SizedNode; // rax
  __int64 v9; // rdi
  wchar_t **v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // rcx

  SizedNode = DtlCreateSizedNode(32);
  v9 = SizedNode;
  if ( SizedNode )
  {
    v10 = *(wchar_t ***)(SizedNode + 16);
    *v10 = StrDup(pszSrc);
    v10[1] = StrDup(a2);
    v11 = StrDup(a3);
    v12 = *v10;
    v10[2] = v11;
    *((_DWORD *)v10 + 6) = a4;
    if ( v12 && v10[1] && v11 )
      return v9;
    Free0(v12);
    Free0(v10[1]);
    Free0(v10[2]);
    Free0(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800260b8  push    rbx
0x1800260ba  push    rbp
0x1800260bb  push    rsi
0x1800260bc  push    rdi
0x1800260bd  push    r14
0x1800260bf  push    r15
0x1800260c1  sub     rsp, 28h
0x1800260c5  mov     r15, rcx
0x1800260c8  mov     esi, r9d
0x1800260cb  mov     ecx, 20h ; ' '
0x1800260d0  mov     rbp, r8
0x1800260d3  mov     r14, rdx
0x1800260d6  call    DtlCreateSizedNode
0x1800260db  mov     rdi, rax
0x1800260de  test    rax, rax
0x1800260e1  jz      short loc_180026145
0x1800260e3  mov     rbx, [rax+10h]
0x1800260e7  mov     rcx, r15; pszSrc
0x1800260ea  call    StrDup
0x1800260ef  mov     rcx, r14; pszSrc
0x1800260f2  mov     [rbx], rax
0x1800260f5  call    StrDup
0x1800260fa  mov     rcx, rbp; pszSrc
0x1800260fd  mov     [rbx+8], rax
0x180026101  call    StrDup
0x180026106  mov     rcx, [rbx]
0x180026109  mov     [rbx+10h], rax
0x18002610d  mov     [rbx+18h], esi
0x180026110  test    rcx, rcx
0x180026113  jz      short loc_180026126
0x180026115  cmp     qword ptr [rbx+8], 0
0x18002611a  jz      short loc_180026126
0x18002611c  test    rax, rax
0x18002611f  jz      short loc_180026126
0x180026121  mov     rax, rdi
0x180026124  jmp     short loc_180026147
0x180026126  call    Free0
0x18002612b  mov     rcx, [rbx+8]
0x18002612f  call    Free0
0x180026134  mov     rcx, [rbx+10h]
0x180026138  call    Free0
0x18002613d  mov     rcx, rdi
0x180026140  call    Free0
0x180026145  xor     eax, eax
0x180026147  add     rsp, 28h
0x18002614b  pop     r15
0x18002614d  pop     r14
0x18002614f  pop     rdi
0x180026150  pop     rsi
0x180026151  pop     rbp
0x180026152  pop     rbx
0x180026153  retn
```
