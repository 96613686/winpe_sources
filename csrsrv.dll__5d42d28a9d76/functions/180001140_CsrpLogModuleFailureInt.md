# CsrpLogModuleFailureInt

- ea: `0x180001140`
- end: `0x1800011f1`
- name: `CsrpLogModuleFailureInt`
- size: `177`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPCSTR pszSrc@<rcx>, int)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180001010`
- `0x180001540`
- `0x180001c50`
- `0x180004a20`
- `0x180008df0`
- `0x180009190`
- `0x1800097f0`

## callees

- `0x180001140`
- `0x180008290`
- `0x180008d94`
- `0x18000ab61`
- `0x18000ab80`

## pseudocode

```c
__int64 __fastcall CsrpLogModuleFailureInt(STRSAFE_LPCSTR pszSrc, __int64 a2, const char *a3, int a4)
{
  size_t v7; // rdx
  HRESULT v8; // eax
  char v9; // cl
  _BYTE v11[64]; // [rsp+20h] [rbp-F8h] BYREF
  char pszDest[132]; // [rsp+60h] [rbp-B8h] BYREF
  int v13; // [rsp+E4h] [rbp-34h]

  memset_0(v11, 0, 0xCCu);
  v13 = a4;
  if ( a3 )
  {
    v8 = StringCbCopyA(pszDest, v7, a3);
    if ( (int)(v8 + 0x80000000) >= 0 )
    {
      v9 = pszDest[0];
      if ( v8 != -2147024774 )
        v9 = 0;
      pszDest[0] = v9;
    }
  }
  return CsrpInternalLogFailure(pszSrc);
}

```

## disassembly

```asm
0x180001140  mov     [rsp+arg_8], rbx
0x180001145  push    rbp
0x180001146  push    rsi
0x180001147  push    rdi
0x180001148  sub     rsp, 100h
0x18000114f  mov     rax, cs:__security_cookie
0x180001156  xor     rax, rsp
0x180001159  mov     [rsp+118h+var_28], rax
0x180001161  mov     rbp, r8
0x180001164  mov     esi, edx
0x180001166  mov     rbx, rcx
0x180001169  xor     edx, edx; Val
0x18000116b  mov     r8d, 0CCh; Size
0x180001171  lea     rcx, [rsp+118h+var_F8]; void *
0x180001176  mov     edi, r9d
0x180001179  call    memset_0
0x18000117e  mov     [rsp+118h+var_34], edi
0x180001185  test    rbp, rbp
0x180001188  jz      short loc_1800011B6
0x18000118a  mov     r8, rbp; pszSrc
0x18000118d  lea     rcx, [rsp+118h+pszDest]; pszDest
0x180001192  call    StringCbCopyA
0x180001197  mov     edx, 80000000h
0x18000119c  lea     ecx, [rax+rdx]
0x18000119f  test    edx, ecx
0x1800011a1  jnz     short loc_1800011B6
0x1800011a3  movzx   ecx, [rsp+118h+pszDest]
0x1800011a8  xor     edx, edx
0x1800011aa  cmp     eax, 8007007Ah
0x1800011af  cmovnz  ecx, edx
0x1800011b2  mov     [rsp+118h+pszDest], cl
0x1800011b6  mov     r8d, [rsp+118h+arg_20]
0x1800011be  lea     r9, [rsp+118h+var_F8]
0x1800011c3  mov     edx, esi
0x1800011c5  mov     rcx, rbx; pszSrc
0x1800011c8  call    CsrpInternalLogFailure
0x1800011cd  mov     rcx, [rsp+118h+var_28]
0x1800011d5  xor     rcx, rsp; StackCookie
0x1800011d8  call    __security_check_cookie
0x1800011dd  mov     rbx, [rsp+118h+arg_8]
0x1800011e5  add     rsp, 100h
0x1800011ec  pop     rdi
0x1800011ed  pop     rsi
0x1800011ee  pop     rbp
0x1800011ef  retn
```
