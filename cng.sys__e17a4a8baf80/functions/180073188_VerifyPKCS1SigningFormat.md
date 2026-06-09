# VerifyPKCS1SigningFormat

- ea: `0x180073188`
- end: `0x18007332e`
- name: `VerifyPKCS1SigningFormat`
- size: `422`
- prototype: `__int64 __fastcall(int, int, int, int, void *Buf2, size_t Size, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180072bc4`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180071eec`
- `0x180073188`
- `0x1800a4380`
- `0x1800a4890`

## string_xrefs

- `0x1800731c4`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x18007326a`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x1800732ff`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

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

  v8 = (void *)MSCryptAlloc((unsigned int)Size, a2);
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
0x180073188  mov     [rsp+arg_8], rdx
0x18007318d  push    rbx
0x18007318e  push    rbp
0x18007318f  push    rsi
0x180073190  push    rdi
0x180073191  push    r12
0x180073193  push    r13
0x180073195  push    r14
0x180073197  push    r15
0x180073199  sub     rsp, 48h
0x18007319d  mov     r14d, dword ptr [rsp+88h+Size]
0x1800731a5  mov     r13d, ecx
0x1800731a8  mov     ecx, r14d
0x1800731ab  mov     r15d, r9d
0x1800731ae  mov     r12, r8
0x1800731b1  call    MSCryptAlloc
0x1800731b6  mov     rdi, rax
0x1800731b9  test    rax, rax
0x1800731bc  jnz     short loc_1800731E6
0x1800731be  mov     r9d, 0B8h
0x1800731c4  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800731cb  lea     rdx, aStatus; "Status"
0x1800731d2  mov     ecx, 0C0000017h
0x1800731d7  mov     ebx, 0C0000017h
0x1800731dc  call    DebugTraceError
0x1800731e1  jmp     loc_18007331A
0x1800731e6  cmp     [rsp+88h+arg_30], 0
0x1800731ee  jz      loc_180073298
0x1800731f4  mov     ebx, 0C00000E5h
0x1800731f9  xor     ebp, ebp
0x1800731fb  cmp     ebp, r13d
0x1800731fe  jnb     loc_180073312
0x180073204  mov     r8, r14; Size
0x180073207  xor     edx, edx; Val
0x180073209  mov     rcx, rdi; void *
0x18007320c  call    memset
0x180073211  mov     rax, [rsp+88h+arg_8]
0x180073219  mov     r9d, r15d
0x18007321c  mov     [rsp+88h+var_58], 1; int
0x180073224  mov     r8, r12
0x180073227  mov     ecx, ebp
0x180073229  add     rcx, rcx
0x18007322c  mov     [rsp+88h+var_60], r14d; int
0x180073231  mov     [rsp+88h+var_68], rdi; __int64
0x180073236  mov     edx, [rax+rcx*8]; Size
0x180073239  mov     rcx, [rax+rcx*8+8]; Src
0x18007323e  call    ApplyPKCS1SigningFormat
0x180073243  mov     ebx, eax
0x180073245  test    eax, eax
0x180073247  js      short loc_18007328E
0x180073249  mov     rdx, [rsp+88h+Buf2]; Buf2
0x180073251  mov     r8, r14; Size
0x180073254  mov     rcx, rdi; Buf1
0x180073257  call    memcmp
0x18007325c  test    eax, eax
0x18007325e  jz      loc_1800732EB
0x180073264  mov     r9d, 0DBh
0x18007326a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180073271  lea     rdx, aStatus; "Status"
0x180073278  mov     ecx, 0C000A000h
0x18007327d  mov     ebx, 0C000A000h
0x180073282  call    DebugTraceError
0x180073287  inc     ebp
0x180073289  jmp     loc_1800731FB
0x18007328e  mov     r9d, 0CEh
0x180073294  mov     ecx, eax
0x180073296  jmp     short loc_1800732FF
0x180073298  mov     r8, r14; Size
0x18007329b  xor     edx, edx; Val
0x18007329d  mov     rcx, rdi; void *
0x1800732a0  call    memset
0x1800732a5  mov     [rsp+88h+var_58], 0; int
0x1800732ad  mov     r9d, r15d
0x1800732b0  mov     [rsp+88h+var_60], r14d; int
0x1800732b5  mov     r8, r12
0x1800732b8  xor     edx, edx; Size
0x1800732ba  mov     [rsp+88h+var_68], rdi; __int64
0x1800732bf  xor     ecx, ecx; Src
0x1800732c1  call    ApplyPKCS1SigningFormat
0x1800732c6  mov     ebx, eax
0x1800732c8  test    eax, eax
0x1800732ca  jns     short loc_1800732D4
0x1800732cc  mov     r9d, 0ECh
0x1800732d2  jmp     short loc_180073294
0x1800732d4  mov     rdx, [rsp+88h+Buf2]; Buf2
0x1800732dc  mov     r8, r14; Size
0x1800732df  mov     rcx, rdi; Buf1
0x1800732e2  call    memcmp
0x1800732e7  test    eax, eax
0x1800732e9  jnz     short loc_1800732EF
0x1800732eb  xor     ebx, ebx
0x1800732ed  jmp     short loc_180073312
0x1800732ef  mov     ebx, 0C000A000h
0x1800732f4  mov     r9d, 0F8h
0x1800732fa  mov     ecx, 0C000A000h
0x1800732ff  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180073306  lea     rdx, aStatus; "Status"
0x18007330d  call    DebugTraceError
0x180073312  mov     rcx, rdi; P
0x180073315  call    MSCryptFree
0x18007331a  mov     eax, ebx
0x18007331c  add     rsp, 48h
0x180073320  pop     r15
0x180073322  pop     r14
0x180073324  pop     r13
0x180073326  pop     r12
0x180073328  pop     rdi
0x180073329  pop     rsi
0x18007332a  pop     rbp
0x18007332b  pop     rbx
0x18007332c  retn
```
