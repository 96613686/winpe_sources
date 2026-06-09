# CalculateAppPoolHash(ushort const *,APP_POOL_HASH * *)

- ea: `0x180008c90`
- end: `0x180008e4e`
- name: `?CalculateAppPoolHash@@YAJPEBGPEAPEAUAPP_POOL_HASH@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct APP_POOL_HASH **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008e54`

## callees

- `0x180005460`
- `0x1800054a0`
- `0x180005f46`
- `0x180005f90`
- `0x180008c90`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x180008d40`
- `msvcrt!_wcslwr_s` at `0x180008d40`
- `bcrypt!BCryptFinishHash` at `0x180008de3`
- `bcrypt!BCryptFinishHash` at `0x180008de3`
- `bcrypt!BCryptDestroyHash` at `0x180008df9`
- `bcrypt!BCryptDestroyHash` at `0x180008df9`
- `bcrypt!BCryptHashData` at `0x180008dbf`
- `bcrypt!BCryptHashData` at `0x180008dbf`
- `bcrypt!BCryptCreateHash` at `0x180008d9f`
- `bcrypt!BCryptCreateHash` at `0x180008d9f`

## pseudocode

```c
__int64 __fastcall CalculateAppPoolHash(const unsigned __int16 *Src, struct APP_POOL_HASH **a2)
{
  unsigned __int64 v3; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rsi
  struct APP_POOL_HASH *v8; // rbx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-58h] BYREF
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-50h] BYREF
  int v11; // [rsp+58h] [rbp-40h]

  phHash = 0;
  v3 = -1;
  *a2 = 0;
  do
    ++v3;
  while ( Src[v3] );
  if ( v3 >= 0xFFFFFFFF )
    return 2147942487LL;
  v6 = operator new(saturated_mul(v3 + 1, 2u));
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  memcpy_0(v6, Src, 2 * v3);
  v7[v3] = 0;
  if ( _wcslwr_s(v7, v3 + 1) )
  {
    operator delete(v7);
    return 2147942487LL;
  }
  else
  {
    v8 = (struct APP_POOL_HASH *)operator new(0x14u);
    if ( v8 )
    {
      if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
        __fastfail(7u);
      if ( BCryptHashData(phHash, (PUCHAR)v7, 2 * v3, 0) < 0 )
        __fastfail(7u);
      if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash);
      phHash = 0;
      *(_OWORD *)v8 = *(_OWORD *)pbOutput;
      *((_DWORD *)v8 + 4) = v11;
      *a2 = v8;
      operator delete(v7);
      return 0;
    }
    else
    {
      operator delete(v7);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180008c90  push    rbp
0x180008c92  push    rdi
0x180008c93  push    r12
0x180008c95  push    r15
0x180008c97  sub     rsp, 78h
0x180008c9b  mov     rax, cs:__security_cookie
0x180008ca2  xor     rax, rsp
0x180008ca5  mov     [rsp+98h+var_38], rax
0x180008caa  xor     r12d, r12d
0x180008cad  mov     rbp, rcx
0x180008cb0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008cb7  mov     [rsp+98h+phHash], r12
0x180008cbc  mov     rdi, rcx
0x180008cbf  mov     [rdx], r12
0x180008cc2  mov     r15, rdx
0x180008cc5  inc     rdi
0x180008cc8  cmp     [rbp+rdi*2+0], r12w
0x180008cce  jnz     short loc_180008CC5
0x180008cd0  mov     eax, 0FFFFFFFFh
0x180008cd5  cmp     rdi, rax
0x180008cd8  jb      short loc_180008CE4
0x180008cda  mov     eax, 80070057h
0x180008cdf  jmp     loc_180008E36
0x180008ce4  mov     [rsp+98h+arg_18], rsi
0x180008cec  mov     eax, 2
0x180008cf1  mov     [rsp+98h+var_28], r14
0x180008cf6  lea     r14, [rdi+1]
0x180008cfa  mul     r14
0x180008cfd  cmovb   rax, rcx
0x180008d01  mov     rcx, rax; Size
0x180008d04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008d09  mov     rsi, rax
0x180008d0c  test    rax, rax
0x180008d0f  jnz     short loc_180008D1B
0x180008d11  mov     eax, 8007000Eh
0x180008d16  jmp     loc_180008E29
0x180008d1b  mov     [rsp+98h+arg_10], rbx
0x180008d23  mov     rdx, rbp; Src
0x180008d26  lea     rbx, [rdi+rdi]
0x180008d2a  mov     rcx, rsi; void *
0x180008d2d  mov     r8, rbx; Size
0x180008d30  call    memcpy_0
0x180008d35  mov     rdx, r14; SizeInWords
0x180008d38  mov     [rbx+rsi], r12w
0x180008d3d  mov     rcx, rsi; String
0x180008d40  call    cs:__imp__wcslwr_s
0x180008d46  test    eax, eax
0x180008d48  jz      short loc_180008D5C
0x180008d4a  mov     rcx, rsi; Block
0x180008d4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008d52  mov     eax, 80070057h
0x180008d57  jmp     loc_180008E21
0x180008d5c  mov     ecx, 14h; Size
0x180008d61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008d66  mov     rbx, rax
0x180008d69  test    rax, rax
0x180008d6c  jnz     short loc_180008D80
0x180008d6e  mov     rcx, rsi; Block
0x180008d71  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008d76  mov     eax, 8007000Eh
0x180008d7b  jmp     loc_180008E21
0x180008d80  mov     [rsp+98h+dwFlags], r12d; dwFlags
0x180008d85  lea     rdx, [rsp+98h+phHash]; phHash
0x180008d8a  mov     [rsp+98h+cbSecret], r12d; cbSecret
0x180008d8f  xor     r9d, r9d; cbHashObject
0x180008d92  xor     r8d, r8d; pbHashObject
0x180008d95  mov     [rsp+98h+pbSecret], r12; pbSecret
0x180008d9a  mov     ecx, 31h ; '1'; hAlgorithm
0x180008d9f  call    cs:__imp_BCryptCreateHash
0x180008da5  test    eax, eax
0x180008da7  jns     short loc_180008DB0
0x180008da9  mov     ecx, 7
0x180008dae  int     29h; Win8: RtlFailFast(ecx)
0x180008db0  mov     rcx, [rsp+98h+phHash]; hHash
0x180008db5  lea     r8d, [rdi+rdi]; cbInput
0x180008db9  xor     r9d, r9d; dwFlags
0x180008dbc  mov     rdx, rsi; pbInput
0x180008dbf  call    cs:__imp_BCryptHashData
0x180008dc5  test    eax, eax
0x180008dc7  jns     short loc_180008DD0
0x180008dc9  mov     ecx, 7
0x180008dce  int     29h; Win8: RtlFailFast(ecx)
0x180008dd0  mov     rcx, [rsp+98h+phHash]; hHash
0x180008dd5  lea     rdx, [rsp+98h+pbOutput]; pbOutput
0x180008dda  xor     r9d, r9d; dwFlags
0x180008ddd  mov     r8d, 14h; cbOutput
0x180008de3  call    cs:__imp_BCryptFinishHash
0x180008de9  test    eax, eax
0x180008deb  jns     short loc_180008DF4
0x180008ded  mov     ecx, 7
0x180008df2  int     29h; Win8: RtlFailFast(ecx)
0x180008df4  mov     rcx, [rsp+98h+phHash]; hHash
0x180008df9  call    cs:__imp_BCryptDestroyHash
0x180008dff  movups  xmm0, xmmword ptr [rsp+98h+pbOutput]
0x180008e04  mov     [rsp+98h+phHash], r12
0x180008e09  movups  xmmword ptr [rbx], xmm0
0x180008e0c  mov     ecx, [rsp+98h+var_40]
0x180008e10  mov     [rbx+10h], ecx
0x180008e13  mov     rcx, rsi; Block
0x180008e16  mov     [r15], rbx
0x180008e19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008e1e  mov     eax, r12d
0x180008e21  mov     rbx, [rsp+98h+arg_10]
0x180008e29  mov     rsi, [rsp+98h+arg_18]
0x180008e31  mov     r14, [rsp+98h+var_28]
0x180008e36  mov     rcx, [rsp+98h+var_38]
0x180008e3b  xor     rcx, rsp; StackCookie
0x180008e3e  call    __security_check_cookie
0x180008e43  add     rsp, 78h
0x180008e47  pop     r15
0x180008e49  pop     r12
0x180008e4b  pop     rdi
0x180008e4c  pop     rbp
0x180008e4d  retn
```
