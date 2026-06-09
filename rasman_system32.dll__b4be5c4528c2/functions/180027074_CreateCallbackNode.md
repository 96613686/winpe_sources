# CreateCallbackNode

- ea: `0x180027074`
- end: `0x180027111`
- name: `CreateCallbackNode`
- size: `157`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR, STRSAFE_LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800262d0`

## callees

- `0x1800254c4`
- `0x180025ed0`
- `0x18002700c`
- `0x180027074`

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
0x180027074  push    rbx
0x180027076  push    rbp
0x180027077  push    rsi
0x180027078  push    rdi
0x180027079  push    r14
0x18002707b  push    r15
0x18002707d  sub     rsp, 28h
0x180027081  mov     r15, rcx
0x180027084  mov     esi, r9d
0x180027087  mov     ecx, 20h ; ' '
0x18002708c  mov     rbp, r8
0x18002708f  mov     r14, rdx
0x180027092  call    DtlCreateSizedNode
0x180027097  mov     rdi, rax
0x18002709a  test    rax, rax
0x18002709d  jz      short loc_180027101
0x18002709f  mov     rbx, [rax+10h]
0x1800270a3  mov     rcx, r15; pszSrc
0x1800270a6  call    StrDup
0x1800270ab  mov     rcx, r14; pszSrc
0x1800270ae  mov     [rbx], rax
0x1800270b1  call    StrDup
0x1800270b6  mov     rcx, rbp; pszSrc
0x1800270b9  mov     [rbx+8], rax
0x1800270bd  call    StrDup
0x1800270c2  mov     rcx, [rbx]
0x1800270c5  mov     [rbx+10h], rax
0x1800270c9  mov     [rbx+18h], esi
0x1800270cc  test    rcx, rcx
0x1800270cf  jz      short loc_1800270E2
0x1800270d1  cmp     qword ptr [rbx+8], 0
0x1800270d6  jz      short loc_1800270E2
0x1800270d8  test    rax, rax
0x1800270db  jz      short loc_1800270E2
0x1800270dd  mov     rax, rdi
0x1800270e0  jmp     short loc_180027103
0x1800270e2  call    Free0
0x1800270e7  mov     rcx, [rbx+8]
0x1800270eb  call    Free0
0x1800270f0  mov     rcx, [rbx+10h]
0x1800270f4  call    Free0
0x1800270f9  mov     rcx, rdi
0x1800270fc  call    Free0
0x180027101  xor     eax, eax
0x180027103  add     rsp, 28h
0x180027107  pop     r15
0x180027109  pop     r14
0x18002710b  pop     rdi
0x18002710c  pop     rsi
0x18002710d  pop     rbp
0x18002710e  pop     rbx
0x18002710f  retn
```
