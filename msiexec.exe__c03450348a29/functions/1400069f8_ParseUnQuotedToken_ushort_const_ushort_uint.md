# ParseUnQuotedToken(ushort const * &,ushort * &,uint)

- ea: `0x1400069f8`
- end: `0x140006a89`
- name: `?ParseUnQuotedToken@@YA_NAEAPEBGAEAPEAGI@Z`
- size: `145`
- prototype: `bool __fastcall(const unsigned __int16 **, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006a90`

## callees

- `0x1400069f8`
- `0x1400097f2`

## pseudocode

```c
bool __fastcall ParseUnQuotedToken(unsigned __int16 **a1, unsigned __int16 **a2, unsigned int a3)
{
  __int64 v4; // r10
  unsigned __int16 *v5; // rdx
  unsigned __int16 v6; // r9
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r8
  __int64 v9; // r8
  char *v10; // rbx
  size_t v11; // rdi
  bool result; // al

  v4 = a3;
  v5 = *a1;
  v6 = **a1;
  if ( v6 )
  {
    v7 = *a1;
    do
    {
      v8 = (unsigned __int16 *)v7;
      if ( v6 == 32 )
        break;
      if ( v6 == 9 )
        break;
      *a1 = (unsigned __int16 *)++v7;
      v8 = (unsigned __int16 *)v7;
      v6 = *v7;
    }
    while ( *v7 );
  }
  else
  {
    v8 = *a1;
  }
  v9 = v8 - v5;
  if ( v9 >= v4 || v9 < 0 )
    return 0;
  if ( (_DWORD)v9 )
  {
    v10 = (char *)*a2;
    v11 = 2LL * (unsigned int)v9;
    memcpy_0(*a2, v5, v11);
    *a2 = (unsigned __int16 *)&v10[v11];
  }
  result = 1;
  **a2 = 0;
  return result;
}

```

## disassembly

```asm
0x1400069f8  push    rbx
0x1400069fa  push    rbp
0x1400069fb  push    rsi
0x1400069fc  push    rdi
0x1400069fd  sub     rsp, 28h
0x140006a01  mov     rsi, rdx
0x140006a04  mov     r10d, r8d
0x140006a07  mov     rdx, [rcx]; Src
0x140006a0a  xor     ebp, ebp
0x140006a0c  movzx   r9d, word ptr [rdx]
0x140006a10  test    r9w, r9w
0x140006a14  jz      short loc_140006A40
0x140006a16  mov     rax, rdx
0x140006a19  mov     r8, rax
0x140006a1c  cmp     r9w, 20h ; ' '
0x140006a21  jz      short loc_140006A43
0x140006a23  cmp     r9w, 9
0x140006a28  jz      short loc_140006A43
0x140006a2a  add     rax, 2
0x140006a2e  mov     [rcx], rax
0x140006a31  mov     r8, rax
0x140006a34  movzx   r9d, word ptr [rax]
0x140006a38  test    r9w, r9w
0x140006a3c  jnz     short loc_140006A19
0x140006a3e  jmp     short loc_140006A43
0x140006a40  mov     r8, rdx
0x140006a43  sub     r8, rdx
0x140006a46  sar     r8, 1
0x140006a49  cmp     r8, r10
0x140006a4c  jge     short loc_140006A7E
0x140006a4e  test    r8, r8
0x140006a51  js      short loc_140006A7E
0x140006a53  test    r8d, r8d
0x140006a56  jz      short loc_140006A74
0x140006a58  mov     rbx, [rsi]
0x140006a5b  mov     eax, r8d
0x140006a5e  mov     rcx, rbx; void *
0x140006a61  lea     rdi, [rax+rax]
0x140006a65  mov     r8, rdi; Size
0x140006a68  call    memcpy_0
0x140006a6d  lea     rax, [rdi+rbx]
0x140006a71  mov     [rsi], rax
0x140006a74  mov     rcx, [rsi]
0x140006a77  mov     al, 1
0x140006a79  mov     [rcx], bp
0x140006a7c  jmp     short loc_140006A80
0x140006a7e  xor     al, al
0x140006a80  add     rsp, 28h
0x140006a84  pop     rdi
0x140006a85  pop     rsi
0x140006a86  pop     rbp
0x140006a87  pop     rbx
0x140006a88  retn
```
