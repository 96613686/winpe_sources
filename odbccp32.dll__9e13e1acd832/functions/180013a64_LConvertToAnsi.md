# LConvertToAnsi

- ea: `0x180013a64`
- end: `0x180013c23`
- name: `LConvertToAnsi`
- size: `447`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int, CHAR **, int, int *, char)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c0c`
- `0x1800085c8`
- `0x180013c2c`

## callees

- `0x180013a64`

## import_xrefs

- `msvcrt!malloc` at `0x180013b2a`
- `msvcrt!malloc` at `0x180013b2a`
- `KERNEL32!WideCharToMultiByte` at `0x180013bcc`
- `KERNEL32!WideCharToMultiByte` at `0x180013bcc`

## pseudocode

```c
__int64 __fastcall LConvertToAnsi(__int64 a1, const WCHAR *a2, int a3, CHAR **a4, int a5, int *a6, char a7)
{
  int *v7; // r14
  int v8; // ebx
  int v11; // r12d
  __int64 v12; // rax
  int cbMultiByte; // edi
  CHAR *v14; // rax
  CHAR *lpMultiByteStr; // rdx
  int v17; // r8d
  int v18; // eax
  int v19; // eax
  __int16 v20; // ax
  int v21; // ecx
  int v22; // eax
  int v23; // ebx
  unsigned __int64 v24; // r9
  int v25; // ecx
  int v26; // [rsp+40h] [rbp-58h] BYREF

  v7 = &v26;
  v8 = a3;
  v26 = 0;
  v11 = (a7 & 2) == 0 ? 2 : 0;
  if ( a6 )
    v7 = a6;
  if ( a3 == -3 && a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v8 = v12 + 1;
    if ( (a7 & 8) == 0 && v12 != -1 )
      v8 = 2 * v12 + 2;
    *v7 = -3;
  }
  else
  {
    *v7 = a3;
    if ( !a2 )
      goto LABEL_45;
  }
  cbMultiByte = a5;
  if ( !a5 && (a7 & 4) == 0 )
  {
LABEL_45:
    if ( a4 )
      *a4 = 0;
    return 0;
  }
  if ( (a7 & 8) != 0 && v8 > 0 )
    v8 *= 2;
  if ( (a7 & 4) != 0 )
  {
    v14 = (CHAR *)malloc(v8 + 1);
    *a4 = v14;
    lpMultiByteStr = v14;
    if ( !v14 )
      return -1;
    v17 = v8;
    cbMultiByte = v8;
    goto LABEL_29;
  }
  lpMultiByteStr = *a4;
  if ( *a4 )
  {
    v18 = 2 * a5;
    if ( a5 <= 0 )
      v18 = a5;
    if ( v8 >= v18 )
    {
      v19 = 2 * a5;
      if ( a5 <= 0 )
        v19 = a5;
    }
    else
    {
      v19 = v8;
    }
    v17 = v11 + v19;
LABEL_29:
    if ( (a7 & 2) != 0 )
      goto LABEL_33;
    v20 = 2 * cbMultiByte;
    if ( cbMultiByte <= 0 )
      v20 = cbMultiByte;
    v21 = v20;
    v22 = v11 + v8;
    v23 = 1;
    if ( v22 <= v21 )
LABEL_33:
      v23 = 0;
    if ( v17 )
    {
      v24 = (unsigned __int64)v17 >> 1;
      if ( v17 <= 0 )
        LODWORD(v24) = v17;
      v25 = WideCharToMultiByte(0, 0x400u, a2, v24, lpMultiByteStr, cbMultiByte, 0, 0);
      if ( v25 )
      {
        if ( *v7 != -3 && !v23 )
          *v7 = (__PAIR64__(v25, a7 & 2) - 1) >> 32;
      }
      else if ( (a7 & 2) == 0 && cbMultiByte >= 1 )
      {
        (*a4)[cbMultiByte - 1] = 0;
      }
    }
    else
    {
      *lpMultiByteStr = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013a64  push    rbx
0x180013a66  push    rbp
0x180013a67  push    rsi
0x180013a68  push    rdi
0x180013a69  push    r12
0x180013a6b  push    r13
0x180013a6d  push    r14
0x180013a6f  push    r15
0x180013a71  sub     rsp, 58h
0x180013a75  mov     ecx, [rsp+98h+arg_30]
0x180013a7c  lea     r14, [rsp+98h+var_58]
0x180013a81  xor     r13d, r13d
0x180013a84  mov     ebx, r8d
0x180013a87  mov     ebp, ecx
0x180013a89  mov     [rsp+98h+var_58], r13d
0x180013a8e  and     ebp, 2
0x180013a91  mov     r8d, ecx
0x180013a94  and     r8d, 8
0x180013a98  mov     eax, ebp
0x180013a9a  neg     eax
0x180013a9c  mov     rsi, r9
0x180013a9f  mov     rax, [rsp+98h+arg_28]
0x180013aa7  mov     r15, rdx
0x180013aaa  sbb     r12d, r12d
0x180013aad  not     r12d
0x180013ab0  and     r12d, 2
0x180013ab4  test    rax, rax
0x180013ab7  cmovnz  r14, rax
0x180013abb  cmp     ebx, 0FFFFFFFDh
0x180013abe  jnz     short loc_180013AF2
0x180013ac0  test    rdx, rdx
0x180013ac3  jz      short loc_180013AF2
0x180013ac5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013ac9  inc     rax
0x180013acc  cmp     [rdx+rax*2], r13w
0x180013ad1  jnz     short loc_180013AC9
0x180013ad3  lea     rbx, [rax+1]
0x180013ad7  test    r8d, r8d
0x180013ada  jnz     short loc_180013AE9
0x180013adc  test    rbx, rbx
0x180013adf  jz      short loc_180013AE9
0x180013ae1  lea     rbx, ds:2[rax*2]
0x180013ae9  mov     dword ptr [r14], 0FFFFFFFDh
0x180013af0  jmp     short loc_180013AFE
0x180013af2  mov     [r14], ebx
0x180013af5  test    r15, r15
0x180013af8  jz      loc_180013C07
0x180013afe  movsxd  rdi, [rsp+98h+arg_20]
0x180013b06  and     ecx, 4
0x180013b09  test    edi, edi
0x180013b0b  jnz     short loc_180013B15
0x180013b0d  test    ecx, ecx
0x180013b0f  jz      loc_180013C07
0x180013b15  test    r8d, r8d
0x180013b18  jz      short loc_180013B20
0x180013b1a  test    ebx, ebx
0x180013b1c  jle     short loc_180013B20
0x180013b1e  add     ebx, ebx
0x180013b20  test    ecx, ecx
0x180013b22  jz      short loc_180013B4B
0x180013b24  lea     ecx, [rbx+1]
0x180013b27  movsxd  rcx, ecx; Size
0x180013b2a  call    cs:__imp_malloc
0x180013b30  mov     [rsi], rax
0x180013b33  mov     rdx, rax
0x180013b36  test    rax, rax
0x180013b39  jnz     short loc_180013B44
0x180013b3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013b3f  jmp     loc_180013C12
0x180013b44  mov     r8d, ebx
0x180013b47  mov     edi, ebx
0x180013b49  jmp     short loc_180013B74
0x180013b4b  mov     rdx, [r9]
0x180013b4e  test    rdx, rdx
0x180013b51  jz      loc_180013C0F
0x180013b57  test    edi, edi
0x180013b59  lea     eax, [rdi+rdi]
0x180013b5c  cmovle  eax, edi
0x180013b5f  cmp     ebx, eax
0x180013b61  jge     short loc_180013B67
0x180013b63  mov     eax, ebx
0x180013b65  jmp     short loc_180013B70
0x180013b67  lea     eax, [rdi+rdi]
0x180013b6a  test    edi, edi
0x180013b6c  jg      short loc_180013B70
0x180013b6e  mov     eax, edi
0x180013b70  lea     r8d, [r12+rax]
0x180013b74  test    ebp, ebp
0x180013b76  jnz     short loc_180013B92
0x180013b78  movzx   eax, di
0x180013b7b  add     ax, ax
0x180013b7e  test    edi, edi
0x180013b80  cmovle  ax, di
0x180013b84  movsx   ecx, ax
0x180013b87  lea     eax, [r12+rbx]
0x180013b8b  lea     ebx, [rbp+1]
0x180013b8e  cmp     eax, ecx
0x180013b90  jg      short loc_180013B95
0x180013b92  mov     ebx, r13d
0x180013b95  test    r8d, r8d
0x180013b98  jnz     short loc_180013B9F
0x180013b9a  mov     [rdx], r13b
0x180013b9d  jmp     short loc_180013C0F
0x180013b9f  movsxd  rax, r8d
0x180013ba2  mov     [rsp+98h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180013ba7  mov     r9, rax
0x180013baa  shr     r9, 1
0x180013bad  test    r8d, r8d
0x180013bb0  mov     [rsp+98h+lpDefaultChar], r13; lpDefaultChar
0x180013bb5  mov     [rsp+98h+cbMultiByte], edi; cbMultiByte
0x180013bb9  mov     r8, r15; lpWideCharStr
0x180013bbc  cmovle  r9d, eax; cchWideChar
0x180013bc0  mov     [rsp+98h+lpMultiByteStr], rdx; lpMultiByteStr
0x180013bc5  xor     ecx, ecx; CodePage
0x180013bc7  mov     edx, 400h; dwFlags
0x180013bcc  call    cs:__imp_WideCharToMultiByte
0x180013bd2  mov     ecx, eax
0x180013bd4  test    eax, eax
0x180013bd6  jnz     short loc_180013BEE
0x180013bd8  test    ebp, ebp
0x180013bda  jnz     short loc_180013C0F
0x180013bdc  cmp     edi, 1
0x180013bdf  jl      short loc_180013C0F
0x180013be1  mov     rax, [rsi]
0x180013be4  movsxd  rcx, edi
0x180013be7  mov     [rcx+rax-1], r13b
0x180013bec  jmp     short loc_180013C0F
0x180013bee  cmp     dword ptr [r14], 0FFFFFFFDh
0x180013bf2  jz      short loc_180013C0F
0x180013bf4  test    ebx, ebx
0x180013bf6  jnz     short loc_180013C0F
0x180013bf8  test    ebp, ebp
0x180013bfa  mov     eax, r13d
0x180013bfd  setz    al
0x180013c00  sub     ecx, eax
0x180013c02  mov     [r14], ecx
0x180013c05  jmp     short loc_180013C0F
0x180013c07  test    rsi, rsi
0x180013c0a  jz      short loc_180013C0F
0x180013c0c  mov     [r9], r13
0x180013c0f  mov     eax, r13d
0x180013c12  add     rsp, 58h
0x180013c16  pop     r15
0x180013c18  pop     r14
0x180013c1a  pop     r13
0x180013c1c  pop     r12
0x180013c1e  pop     rdi
0x180013c1f  pop     rsi
0x180013c20  pop     rbp
0x180013c21  pop     rbx
0x180013c22  retn
```
