# CsrpLogModuleFailureString

- ea: `0x180008ca4`
- end: `0x180008d8d`
- name: `CsrpLogModuleFailureString`
- size: `233`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPCSTR pszSrc@<rcx>, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001540`
- `0x180005180`

## callees

- `0x180008290`
- `0x180008ca4`
- `0x180008d94`
- `0x18000ab61`
- `0x18000ab80`

## pseudocode

```c
__int64 __fastcall CsrpLogModuleFailureString(STRSAFE_LPCSTR pszSrc, __int64 a2, const char *a3, const char *a4)
{
  size_t v7; // rdx
  HRESULT v8; // eax
  int v9; // r11d
  int v10; // r10d
  HRESULT v11; // eax
  int v12; // r11d
  int v13; // r10d
  char v14; // r8
  _BYTE v16[64]; // [rsp+20h] [rbp-F8h] BYREF
  char pszDest[64]; // [rsp+60h] [rbp-B8h] BYREF
  char v18[80]; // [rsp+A0h] [rbp-78h] BYREF

  memset_0(v16, 0, 0xCCu);
  if ( a3 )
  {
    v8 = StringCbCopyA(pszDest, v7, a3);
    if ( ((v8 + v10) & v10) == 0 )
    {
      v7 = (unsigned __int8)pszDest[0];
      if ( v8 != v9 )
        v7 = 0;
      pszDest[0] = v7;
    }
  }
  if ( a4 )
  {
    v11 = StringCbCopyA(v18, v7, a4);
    if ( ((v11 + v13) & v13) == 0 )
    {
      v14 = v18[0];
      if ( v11 != v12 )
        v14 = 0;
      v18[0] = v14;
    }
  }
  return CsrpInternalLogFailure(pszSrc);
}

```

## disassembly

```asm
0x180008ca4  mov     [rsp+arg_8], rbx
0x180008ca9  push    rbp
0x180008caa  push    rsi
0x180008cab  push    rdi
0x180008cac  sub     rsp, 100h
0x180008cb3  mov     rax, cs:__security_cookie
0x180008cba  xor     rax, rsp
0x180008cbd  mov     [rsp+118h+var_28], rax
0x180008cc5  mov     rdi, r8
0x180008cc8  mov     esi, edx
0x180008cca  mov     rbp, rcx
0x180008ccd  xor     edx, edx; Val
0x180008ccf  mov     r8d, 0CCh; Size
0x180008cd5  lea     rcx, [rsp+118h+var_F8]; void *
0x180008cda  mov     rbx, r9
0x180008cdd  call    memset_0
0x180008ce2  mov     r10d, 80000000h
0x180008ce8  mov     r11d, 8007007Ah
0x180008cee  test    rdi, rdi
0x180008cf1  jz      short loc_180008D1A
0x180008cf3  mov     r8, rdi; pszSrc
0x180008cf6  lea     rcx, [rsp+118h+pszDest]; pszDest
0x180008cfb  call    StringCbCopyA
0x180008d00  lea     ecx, [rax+r10]
0x180008d04  test    r10d, ecx
0x180008d07  jnz     short loc_180008D1A
0x180008d09  movzx   edx, [rsp+118h+pszDest]
0x180008d0e  xor     ecx, ecx
0x180008d10  cmp     eax, r11d
0x180008d13  cmovnz  edx, ecx; cbDest
0x180008d16  mov     [rsp+118h+pszDest], dl
0x180008d1a  test    rbx, rbx
0x180008d1d  jz      short loc_180008D52
0x180008d1f  mov     r8, rbx; pszSrc
0x180008d22  lea     rcx, [rsp+118h+var_78]; pszDest
0x180008d2a  call    StringCbCopyA
0x180008d2f  lea     edx, [rax+r10]
0x180008d33  test    r10d, edx
0x180008d36  jnz     short loc_180008D52
0x180008d38  movzx   r8d, [rsp+118h+var_78]
0x180008d41  xor     edx, edx
0x180008d43  cmp     eax, r11d
0x180008d46  cmovnz  r8d, edx
0x180008d4a  mov     [rsp+118h+var_78], r8b
0x180008d52  mov     r8d, [rsp+118h+arg_20]
0x180008d5a  lea     r9, [rsp+118h+var_F8]
0x180008d5f  mov     edx, esi
0x180008d61  mov     rcx, rbp; pszSrc
0x180008d64  call    CsrpInternalLogFailure
0x180008d69  mov     rcx, [rsp+118h+var_28]
0x180008d71  xor     rcx, rsp; StackCookie
0x180008d74  call    __security_check_cookie
0x180008d79  mov     rbx, [rsp+118h+arg_8]
0x180008d81  add     rsp, 100h
0x180008d88  pop     rdi
0x180008d89  pop     rsi
0x180008d8a  pop     rbp
0x180008d8b  retn
```
