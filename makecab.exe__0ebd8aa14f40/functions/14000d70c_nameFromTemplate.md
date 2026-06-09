# nameFromTemplate

- ea: `0x14000d70c`
- end: `0x14000d837`
- name: `nameFromTemplate`
- size: `299`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPSTR pszDest@<rcx>, __int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140006834`
- `0x1400068d8`
- `0x14000b128`
- `0x14000c2bc`
- `0x14000c6d4`

## callees

- `0x140008620`
- `0x140008e64`
- `0x14000d70c`
- `0x14000e450`

## pseudocode

```c
__int64 __fastcall nameFromTemplate(STRSAFE_LPSTR pszDest, int a2, char *a3, __int64 a4, const char *a5, __int64 a6)
{
  char *v6; // rax
  int v7; // r10d
  unsigned int v10; // ebx
  char v11; // cl
  char pszFormat[254]; // [rsp+40h] [rbp-128h] BYREF
  char v14; // [rsp+13Eh] [rbp-2Ah] BYREF
  char v15; // [rsp+13Fh] [rbp-29h] BYREF

  v6 = pszFormat;
  v7 = 0;
  v10 = 1;
  while ( 1 )
  {
    v11 = *a3;
    if ( !*a3 )
      break;
    if ( v11 == 42 )
    {
      if ( v6 >= &v14 )
        break;
      *v6++ = 37;
      ++v7;
      *v6 = 100;
    }
    else
    {
      if ( v6 >= &v15 )
        break;
      *v6 = v11;
    }
    ++a3;
    ++v6;
  }
  *v6 = 0;
  if ( v7 <= 4 )
  {
    if ( StringCbPrintfA(pszDest, a2, pszFormat) < 0 )
    {
      ErrSet(a6, "%1 length exceeded limit (%2): %3", "%s%d%s", a5, a2 - 1, pszFormat);
      return 0;
    }
    return v10;
  }
  else
  {
    ErrSet(a6, "Wildcard (%1) limit (%2) exceeded in %3", "%c%d%s", 42, 4, a5);
    return 0;
  }
}

```

## disassembly

```asm
0x14000d70c  mov     [rsp+arg_10], rbx
0x14000d711  push    rbp
0x14000d712  push    rsi
0x14000d713  push    rdi
0x14000d714  sub     rsp, 150h
0x14000d71b  mov     rax, cs:__security_cookie
0x14000d722  xor     rax, rsp
0x14000d725  mov     [rsp+168h+var_28], rax
0x14000d72d  mov     rdi, [rsp+168h+arg_20]
0x14000d735  lea     rax, [rsp+168h+pszFormat]
0x14000d73a  mov     rsi, [rsp+168h+arg_28]
0x14000d742  xor     r10d, r10d
0x14000d745  movsxd  rbp, edx
0x14000d748  mov     r11, rcx
0x14000d74b  lea     ebx, [r10+1]
0x14000d74f  jmp     short loc_14000D786
0x14000d751  cmp     cl, 2Ah ; '*'
0x14000d754  jnz     short loc_14000D771
0x14000d756  lea     rcx, [rsp+168h+var_2A]
0x14000d75e  cmp     rax, rcx
0x14000d761  jnb     short loc_14000D78D
0x14000d763  mov     byte ptr [rax], 25h ; '%'
0x14000d766  add     rax, rbx
0x14000d769  add     r10d, ebx
0x14000d76c  mov     byte ptr [rax], 64h ; 'd'
0x14000d76f  jmp     short loc_14000D780
0x14000d771  lea     rdx, [rsp+168h+var_29]
0x14000d779  cmp     rax, rdx
0x14000d77c  jnb     short loc_14000D78D
0x14000d77e  mov     [rax], cl
0x14000d780  add     r8, rbx
0x14000d783  add     rax, rbx
0x14000d786  mov     cl, [r8]
0x14000d789  test    cl, cl
0x14000d78b  jnz     short loc_14000D751
0x14000d78d  mov     byte ptr [rax], 0
0x14000d790  cmp     r10d, 4
0x14000d794  jle     short loc_14000D7C3
0x14000d796  mov     [rsp+168h+var_140], rdi
0x14000d79b  lea     r8, aCDS; "%c%d%s"
0x14000d7a2  mov     r9d, 2Ah ; '*'
0x14000d7a8  mov     [rsp+168h+var_148], 4
0x14000d7b0  lea     rdx, aWildcard1Limit; "Wildcard (%1) limit (%2) exceeded in %3"
0x14000d7b7  mov     rcx, rsi
0x14000d7ba  call    ErrSet
0x14000d7bf  xor     eax, eax
0x14000d7c1  jmp     short loc_14000D814
0x14000d7c3  mov     [rsp+168h+var_138], r9d
0x14000d7c8  lea     r8, [rsp+168h+pszFormat]; pszFormat
0x14000d7cd  mov     dword ptr [rsp+168h+var_140], r9d
0x14000d7d2  mov     rdx, rbp; cbDest
0x14000d7d5  mov     rcx, r11; pszDest
0x14000d7d8  mov     [rsp+168h+var_148], r9d
0x14000d7dd  call    StringCbPrintfA
0x14000d7e2  test    eax, eax
0x14000d7e4  jns     short loc_14000D812
0x14000d7e6  lea     rcx, [rsp+168h+pszFormat]
0x14000d7eb  mov     r9, rdi
0x14000d7ee  mov     [rsp+168h+var_140], rcx
0x14000d7f3  lea     eax, [rbp-1]
0x14000d7f6  mov     rcx, rsi
0x14000d7f9  mov     [rsp+168h+var_148], eax
0x14000d7fd  lea     r8, aSDS; "%s%d%s"
0x14000d804  lea     rdx, a1LengthExceede; "%1 length exceeded limit (%2): %3"
0x14000d80b  call    ErrSet
0x14000d810  xor     ebx, ebx
0x14000d812  mov     eax, ebx
0x14000d814  mov     rcx, [rsp+168h+var_28]
0x14000d81c  xor     rcx, rsp; StackCookie
0x14000d81f  call    __security_check_cookie
0x14000d824  mov     rbx, [rsp+168h+arg_10]
0x14000d82c  add     rsp, 150h
0x14000d833  pop     rdi
0x14000d834  pop     rsi
0x14000d835  pop     rbp
0x14000d836  retn
```
