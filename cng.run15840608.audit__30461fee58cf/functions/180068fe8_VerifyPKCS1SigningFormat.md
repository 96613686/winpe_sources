# VerifyPKCS1SigningFormat

- ea: `0x180068fe8`
- end: `0x18006918e`
- name: `VerifyPKCS1SigningFormat`
- size: `422`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, __int64, void *Buf2, size_t Size, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180068a24`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180067d4c`
- `0x180068fe8`
- `0x18009d920`
- `0x18009dd40`

## string_xrefs

- `0x180069024`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800690ca`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x18006915f`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

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

  v8 = (void *)MSCryptAlloc((unsigned int)Size);
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
0x180068fe8  mov     [rsp+arg_8], rdx
0x180068fed  push    rbx
0x180068fee  push    rbp
0x180068fef  push    rsi
0x180068ff0  push    rdi
0x180068ff1  push    r12
0x180068ff3  push    r13
0x180068ff5  push    r14
0x180068ff7  push    r15
0x180068ff9  sub     rsp, 48h
0x180068ffd  mov     r14d, dword ptr [rsp+88h+Size]
0x180069005  mov     r13d, ecx
0x180069008  mov     ecx, r14d
0x18006900b  mov     r15d, r9d
0x18006900e  mov     r12, r8
0x180069011  call    MSCryptAlloc
0x180069016  mov     rdi, rax
0x180069019  test    rax, rax
0x18006901c  jnz     short loc_180069046
0x18006901e  mov     r9d, 0B8h
0x180069024  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006902b  lea     rdx, aStatus; "Status"
0x180069032  mov     ecx, 0C0000017h
0x180069037  mov     ebx, 0C0000017h
0x18006903c  call    DebugTraceError
0x180069041  jmp     loc_18006917A
0x180069046  cmp     [rsp+88h+arg_30], 0
0x18006904e  jz      loc_1800690F8
0x180069054  mov     ebx, 0C00000E5h
0x180069059  xor     ebp, ebp
0x18006905b  cmp     ebp, r13d
0x18006905e  jnb     loc_180069172
0x180069064  mov     r8, r14; Size
0x180069067  xor     edx, edx; Val
0x180069069  mov     rcx, rdi; void *
0x18006906c  call    memset
0x180069071  mov     rax, [rsp+88h+arg_8]
0x180069079  mov     r9d, r15d
0x18006907c  mov     [rsp+88h+var_58], 1; int
0x180069084  mov     r8, r12
0x180069087  mov     ecx, ebp
0x180069089  add     rcx, rcx
0x18006908c  mov     [rsp+88h+var_60], r14d; int
0x180069091  mov     [rsp+88h+var_68], rdi; __int64
0x180069096  mov     edx, [rax+rcx*8]; Size
0x180069099  mov     rcx, [rax+rcx*8+8]; Src
0x18006909e  call    ApplyPKCS1SigningFormat
0x1800690a3  mov     ebx, eax
0x1800690a5  test    eax, eax
0x1800690a7  js      short loc_1800690EE
0x1800690a9  mov     rdx, [rsp+88h+Buf2]; Buf2
0x1800690b1  mov     r8, r14; Size
0x1800690b4  mov     rcx, rdi; Buf1
0x1800690b7  call    memcmp
0x1800690bc  test    eax, eax
0x1800690be  jz      loc_18006914B
0x1800690c4  mov     r9d, 0DBh
0x1800690ca  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800690d1  lea     rdx, aStatus; "Status"
0x1800690d8  mov     ecx, 0C000A000h
0x1800690dd  mov     ebx, 0C000A000h
0x1800690e2  call    DebugTraceError
0x1800690e7  inc     ebp
0x1800690e9  jmp     loc_18006905B
0x1800690ee  mov     r9d, 0CEh
0x1800690f4  mov     ecx, eax
0x1800690f6  jmp     short loc_18006915F
0x1800690f8  mov     r8, r14; Size
0x1800690fb  xor     edx, edx; Val
0x1800690fd  mov     rcx, rdi; void *
0x180069100  call    memset
0x180069105  mov     [rsp+88h+var_58], 0; int
0x18006910d  mov     r9d, r15d
0x180069110  mov     [rsp+88h+var_60], r14d; int
0x180069115  mov     r8, r12
0x180069118  xor     edx, edx; Size
0x18006911a  mov     [rsp+88h+var_68], rdi; __int64
0x18006911f  xor     ecx, ecx; Src
0x180069121  call    ApplyPKCS1SigningFormat
0x180069126  mov     ebx, eax
0x180069128  test    eax, eax
0x18006912a  jns     short loc_180069134
0x18006912c  mov     r9d, 0ECh
0x180069132  jmp     short loc_1800690F4
0x180069134  mov     rdx, [rsp+88h+Buf2]; Buf2
0x18006913c  mov     r8, r14; Size
0x18006913f  mov     rcx, rdi; Buf1
0x180069142  call    memcmp
0x180069147  test    eax, eax
0x180069149  jnz     short loc_18006914F
0x18006914b  xor     ebx, ebx
0x18006914d  jmp     short loc_180069172
0x18006914f  mov     ebx, 0C000A000h
0x180069154  mov     r9d, 0F8h
0x18006915a  mov     ecx, 0C000A000h
0x18006915f  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069166  lea     rdx, aStatus; "Status"
0x18006916d  call    DebugTraceError
0x180069172  mov     rcx, rdi; P
0x180069175  call    MSCryptFree
0x18006917a  mov     eax, ebx
0x18006917c  add     rsp, 48h
0x180069180  pop     r15
0x180069182  pop     r14
0x180069184  pop     r13
0x180069186  pop     r12
0x180069188  pop     rdi
0x180069189  pop     rsi
0x18006918a  pop     rbp
0x18006918b  pop     rbx
0x18006918c  retn
```
