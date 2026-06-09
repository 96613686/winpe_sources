# VerifyPKCS1SigningFormat

- ea: `0x1800699e8`
- end: `0x180069b8e`
- name: `VerifyPKCS1SigningFormat`
- size: `422`
- prototype: `__int64 __fastcall(int, int, int, int, void *Buf2, size_t Size, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180069424`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18006874c`
- `0x1800699e8`
- `0x18009fa80`
- `0x18009ffa0`

## string_xrefs

- `0x180069a24`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180069aca`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180069b5f`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall VerifyPKCS1SigningFormat(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *Buf2,
        size_t Size,
        int a7)
{
  void *v8; // rax
  void *v9; // rdi
  unsigned int v10; // ebx
  unsigned int i; // ebp
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rcx

  v8 = (void *)MSCryptAlloc((unsigned int)Size, a2, a3, a4);
  v9 = v8;
  if ( v8 )
  {
    if ( a7 )
    {
      v10 = -1073741595;
      for ( i = 0; i < a1; ++i )
      {
        memset(v9, 0, (unsigned int)Size);
        v12 = ApplyPKCS1SigningFormat(
                *(void **)(a2 + 16LL * i + 8),
                *(unsigned int *)(a2 + 16LL * i),
                (__int64)v9,
                Size,
                1);
        v10 = v12;
        if ( v12 < 0 )
        {
          v13 = 206;
          goto LABEL_10;
        }
        if ( !memcmp(v9, Buf2, (unsigned int)Size) )
          goto LABEL_14;
        v10 = -1073700864;
        DebugTraceError(3221266432LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", 219);
      }
      goto LABEL_17;
    }
    memset(v8, 0, (unsigned int)Size);
    v12 = ApplyPKCS1SigningFormat(0, 0, (__int64)v9, Size, 0);
    v10 = v12;
    if ( v12 >= 0 )
    {
      if ( !memcmp(v9, Buf2, (unsigned int)Size) )
      {
LABEL_14:
        v10 = 0;
LABEL_17:
        MSCryptFree(v9);
        return v10;
      }
      v10 = -1073700864;
      v13 = 248;
      v14 = 3221266432LL;
    }
    else
    {
      v13 = 236;
LABEL_10:
      v14 = (unsigned int)v12;
    }
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v13);
    goto LABEL_17;
  }
  v10 = -1073741801;
  DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", 184);
  return v10;
}

```

## disassembly

```asm
0x1800699e8  mov     [rsp+arg_8], rdx
0x1800699ed  push    rbx
0x1800699ee  push    rbp
0x1800699ef  push    rsi
0x1800699f0  push    rdi
0x1800699f1  push    r12
0x1800699f3  push    r13
0x1800699f5  push    r14
0x1800699f7  push    r15
0x1800699f9  sub     rsp, 48h
0x1800699fd  mov     r14d, dword ptr [rsp+88h+Size]
0x180069a05  mov     r13d, ecx
0x180069a08  mov     ecx, r14d
0x180069a0b  mov     r15d, r9d
0x180069a0e  mov     r12, r8
0x180069a11  call    MSCryptAlloc
0x180069a16  mov     rdi, rax
0x180069a19  test    rax, rax
0x180069a1c  jnz     short loc_180069A46
0x180069a1e  mov     r9d, 0B8h
0x180069a24  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069a2b  lea     rdx, aStatus; "Status"
0x180069a32  mov     ecx, 0C0000017h
0x180069a37  mov     ebx, 0C0000017h
0x180069a3c  call    DebugTraceError
0x180069a41  jmp     loc_180069B7A
0x180069a46  cmp     [rsp+88h+arg_30], 0
0x180069a4e  jz      loc_180069AF8
0x180069a54  mov     ebx, 0C00000E5h
0x180069a59  xor     ebp, ebp
0x180069a5b  cmp     ebp, r13d
0x180069a5e  jnb     loc_180069B72
0x180069a64  mov     r8, r14; Size
0x180069a67  xor     edx, edx; Val
0x180069a69  mov     rcx, rdi; void *
0x180069a6c  call    memset
0x180069a71  mov     rax, [rsp+88h+arg_8]
0x180069a79  mov     r9d, r15d
0x180069a7c  mov     [rsp+88h+var_58], 1; int
0x180069a84  mov     r8, r12
0x180069a87  mov     ecx, ebp
0x180069a89  add     rcx, rcx
0x180069a8c  mov     [rsp+88h+var_60], r14d; int
0x180069a91  mov     [rsp+88h+var_68], rdi; __int64
0x180069a96  mov     edx, [rax+rcx*8]; Size
0x180069a99  mov     rcx, [rax+rcx*8+8]; Src
0x180069a9e  call    ApplyPKCS1SigningFormat
0x180069aa3  mov     ebx, eax
0x180069aa5  test    eax, eax
0x180069aa7  js      short loc_180069AEE
0x180069aa9  mov     rdx, [rsp+88h+Buf2]; Buf2
0x180069ab1  mov     r8, r14; Size
0x180069ab4  mov     rcx, rdi; Buf1
0x180069ab7  call    memcmp
0x180069abc  test    eax, eax
0x180069abe  jz      loc_180069B4B
0x180069ac4  mov     r9d, 0DBh
0x180069aca  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069ad1  lea     rdx, aStatus; "Status"
0x180069ad8  mov     ecx, 0C000A000h
0x180069add  mov     ebx, 0C000A000h
0x180069ae2  call    DebugTraceError
0x180069ae7  inc     ebp
0x180069ae9  jmp     loc_180069A5B
0x180069aee  mov     r9d, 0CEh
0x180069af4  mov     ecx, eax
0x180069af6  jmp     short loc_180069B5F
0x180069af8  mov     r8, r14; Size
0x180069afb  xor     edx, edx; Val
0x180069afd  mov     rcx, rdi; void *
0x180069b00  call    memset
0x180069b05  mov     [rsp+88h+var_58], 0; int
0x180069b0d  mov     r9d, r15d
0x180069b10  mov     [rsp+88h+var_60], r14d; int
0x180069b15  mov     r8, r12
0x180069b18  xor     edx, edx; Size
0x180069b1a  mov     [rsp+88h+var_68], rdi; __int64
0x180069b1f  xor     ecx, ecx; Src
0x180069b21  call    ApplyPKCS1SigningFormat
0x180069b26  mov     ebx, eax
0x180069b28  test    eax, eax
0x180069b2a  jns     short loc_180069B34
0x180069b2c  mov     r9d, 0ECh
0x180069b32  jmp     short loc_180069AF4
0x180069b34  mov     rdx, [rsp+88h+Buf2]; Buf2
0x180069b3c  mov     r8, r14; Size
0x180069b3f  mov     rcx, rdi; Buf1
0x180069b42  call    memcmp
0x180069b47  test    eax, eax
0x180069b49  jnz     short loc_180069B4F
0x180069b4b  xor     ebx, ebx
0x180069b4d  jmp     short loc_180069B72
0x180069b4f  mov     ebx, 0C000A000h
0x180069b54  mov     r9d, 0F8h
0x180069b5a  mov     ecx, 0C000A000h
0x180069b5f  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069b66  lea     rdx, aStatus; "Status"
0x180069b6d  call    DebugTraceError
0x180069b72  mov     rcx, rdi; P
0x180069b75  call    MSCryptFree
0x180069b7a  mov     eax, ebx
0x180069b7c  add     rsp, 48h
0x180069b80  pop     r15
0x180069b82  pop     r14
0x180069b84  pop     r13
0x180069b86  pop     r12
0x180069b88  pop     rdi
0x180069b89  pop     rsi
0x180069b8a  pop     rbp
0x180069b8b  pop     rbx
0x180069b8c  retn
```
