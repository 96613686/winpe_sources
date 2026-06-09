# GetNumber

- ea: `0x180001a98`
- end: `0x180001bfe`
- name: `GetNumber`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002500`

## callees

- `0x180001a98`
- `0x1800026b6`
- `0x1800026e0`

## import_xrefs

- `msvcrt!wcstoul` at `0x180001bab`
- `msvcrt!wcstoul` at `0x180001bab`
- `msvcrt!iswspace` at `0x180001adf`
- `msvcrt!iswspace` at `0x180001b09`
- `msvcrt!iswspace` at `0x180001adf`
- `msvcrt!iswspace` at `0x180001b09`

## pseudocode

```c
__int64 __fastcall GetNumber(wint_t **a1, _DWORD *a2)
{
  wint_t v4; // cx
  wint_t *v5; // rdi
  wint_t i; // ax
  unsigned __int64 v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  wchar_t *p_String; // r8
  wchar_t *v11; // rcx
  unsigned int v12; // eax
  wchar_t *EndPtr; // [rsp+20h] [rbp-248h] BYREF
  wchar_t String; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v16[526]; // [rsp+32h] [rbp-236h] BYREF

  EndPtr = 0;
  String = 0;
  memset_0(v16, 0, 0x206u);
  while ( 1 )
  {
    v4 = **a1;
    if ( !v4 || !iswspace(v4) )
      break;
    ++*a1;
  }
  v5 = *a1;
  for ( i = **a1; i && !iswspace(i); i = **a1 )
    ++*a1;
  if ( *a1 == v5 )
    return (unsigned int)-2147467259;
  v7 = *a1 - v5;
  if ( v7 > 0x7FFFFFFE )
    return (unsigned int)-2147024809;
  v9 = 260;
  p_String = &String;
  do
  {
    if ( !v7 )
      break;
    if ( !*v5 )
      break;
    *p_String++ = *v5++;
    --v7;
    --v9;
  }
  while ( v9 );
  v11 = p_String - 1;
  if ( v9 )
    v11 = p_String;
  v8 = v9 == 0 ? 0x8007007A : 0;
  *v11 = 0;
  if ( v9 )
  {
    v12 = wcstoul(&String, &EndPtr, 10);
    if ( v12 != -1 && !*EndPtr )
    {
      *a2 = 1;
      a2[1] = v12;
      return v8;
    }
    *a2 = 0;
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x180001a98  mov     [rsp+arg_10], rbx
0x180001a9d  push    rbp
0x180001a9e  push    rsi
0x180001a9f  push    rdi
0x180001aa0  sub     rsp, 250h
0x180001aa7  mov     rax, cs:__security_cookie
0x180001aae  xor     rax, rsp
0x180001ab1  mov     [rsp+268h+var_28], rax
0x180001ab9  xor     ebp, ebp
0x180001abb  mov     rsi, rdx
0x180001abe  mov     rbx, rcx
0x180001ac1  mov     [rsp+268h+EndPtr], rbp
0x180001ac6  xor     edx, edx; Val
0x180001ac8  mov     [rsp+268h+String], bp
0x180001acd  lea     rcx, [rsp+268h+var_236]; void *
0x180001ad2  mov     r8d, 206h; Size
0x180001ad8  call    memset_0
0x180001add  jmp     short loc_180001AF3
0x180001adf  call    cs:__imp_iswspace
0x180001ae6  nop     dword ptr [rax+rax+00h]
0x180001aeb  test    eax, eax
0x180001aed  jz      short loc_180001AFE
0x180001aef  add     qword ptr [rbx], 2
0x180001af3  mov     rax, [rbx]
0x180001af6  movzx   ecx, word ptr [rax]; C
0x180001af9  test    cx, cx
0x180001afc  jnz     short loc_180001ADF
0x180001afe  mov     rdi, [rbx]
0x180001b01  movzx   eax, word ptr [rdi]
0x180001b04  jmp     short loc_180001B23
0x180001b06  movzx   ecx, ax; C
0x180001b09  call    cs:__imp_iswspace
0x180001b10  nop     dword ptr [rax+rax+00h]
0x180001b15  test    eax, eax
0x180001b17  jnz     short loc_180001B28
0x180001b19  add     qword ptr [rbx], 2
0x180001b1d  mov     rax, [rbx]
0x180001b20  movzx   eax, word ptr [rax]
0x180001b23  test    ax, ax
0x180001b26  jnz     short loc_180001B06
0x180001b28  mov     rax, [rbx]
0x180001b2b  cmp     rax, rdi
0x180001b2e  jz      loc_180001BD3
0x180001b34  sub     rax, rdi
0x180001b37  sar     rax, 1
0x180001b3a  cmp     rax, 7FFFFFFEh
0x180001b40  jbe     short loc_180001B4C
0x180001b42  mov     ebx, 80070057h
0x180001b47  jmp     loc_180001BD8
0x180001b4c  mov     edx, 104h
0x180001b51  lea     r8, [rsp+268h+String]
0x180001b56  test    rax, rax
0x180001b59  jz      short loc_180001B78
0x180001b5b  movzx   ecx, word ptr [rdi]
0x180001b5e  test    cx, cx
0x180001b61  jz      short loc_180001B78
0x180001b63  mov     [r8], cx
0x180001b67  add     rdi, 2
0x180001b6b  add     r8, 2
0x180001b6f  dec     rax
0x180001b72  sub     rdx, 1
0x180001b76  jnz     short loc_180001B56
0x180001b78  test    rdx, rdx
0x180001b7b  lea     rcx, [r8-2]
0x180001b7f  mov     rax, rdx
0x180001b82  cmovnz  rcx, r8
0x180001b86  neg     rax
0x180001b89  sbb     ebx, ebx
0x180001b8b  not     ebx
0x180001b8d  and     ebx, 8007007Ah
0x180001b93  mov     [rcx], bp
0x180001b96  test    rdx, rdx
0x180001b99  jz      short loc_180001BD8
0x180001b9b  mov     r8d, 0Ah; Radix
0x180001ba1  lea     rdx, [rsp+268h+EndPtr]; EndPtr
0x180001ba6  lea     rcx, [rsp+268h+String]; String
0x180001bab  call    cs:__imp_wcstoul
0x180001bb2  nop     dword ptr [rax+rax+00h]
0x180001bb7  cmp     eax, 0FFFFFFFFh
0x180001bba  jz      short loc_180001BD1
0x180001bbc  mov     rcx, [rsp+268h+EndPtr]
0x180001bc1  cmp     [rcx], bp
0x180001bc4  jnz     short loc_180001BD1
0x180001bc6  mov     dword ptr [rsi], 1
0x180001bcc  mov     [rsi+4], eax
0x180001bcf  jmp     short loc_180001BD8
0x180001bd1  mov     [rsi], ebp
0x180001bd3  mov     ebx, 80004005h
0x180001bd8  mov     eax, ebx
0x180001bda  mov     rcx, [rsp+268h+var_28]
0x180001be2  xor     rcx, rsp; StackCookie
0x180001be5  call    __security_check_cookie
0x180001bea  mov     rbx, [rsp+268h+arg_10]
0x180001bf2  add     rsp, 250h
0x180001bf9  pop     rdi
0x180001bfa  pop     rsi
0x180001bfb  pop     rbp
0x180001bfc  retn
```
