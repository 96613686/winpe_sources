# DfscGetRefCacheSizeLocked

- ea: `0x140016f74`
- end: `0x1400170a0`
- name: `DfscGetRefCacheSizeLocked`
- size: `300`
- prototype: `__int64 __fastcall(PUNICODE_PREFIX_TABLE PrefixTable, unsigned int *, char, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400158f0`

## callees

- `0x140016f74`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140016f97`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x14001702f`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140016f97`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x14001702f`

## pseudocode

```c
__int64 __fastcall DfscGetRefCacheSizeLocked(PUNICODE_PREFIX_TABLE PrefixTable, unsigned int *a2, char a3, int a4)
{
  int v8; // edi
  int v9; // ebx
  __int64 result; // rax
  __int64 i; // r10
  unsigned int v12; // r8d
  unsigned int v13; // edx
  int v14; // r9d
  int v15; // r11d
  __int64 v16; // rax
  unsigned int v17; // ecx
  int v18; // ebx

  v8 = 0;
  v9 = 0;
  result = (__int64)RtlNextUnicodePrefix(PrefixTable, 1u);
  for ( i = result; result; i = result )
  {
    if ( (*(_BYTE *)(i - 60) & 1) != 0 )
    {
      v12 = *(unsigned __int16 *)(i - 48);
      v8 += ((*(unsigned __int16 *)(i + 72) + 5) & 0xFFFFFFFC) + v12 * (a3 != 0 ? 4 : 8);
      if ( (_WORD)v12 )
      {
        v13 = 0;
        v14 = -4;
        if ( a4 != 393536 )
          v14 = -2;
        v15 = 11;
        if ( a4 != 393536 )
          v15 = 5;
        do
        {
          v16 = v13++;
          v8 += v14 & (v15 + *(unsigned __int16 *)(112 * v16 + i + 184));
        }
        while ( v13 < v12 );
      }
      ++v9;
    }
    result = (__int64)RtlNextUnicodePrefix(PrefixTable, 0);
  }
  if ( a3 )
  {
    v17 = v8 + 48 * v9 + 4;
    if ( (((_BYTE)v8 + 48 * (_BYTE)v9 + 4) & 3) != 0 )
      v17 = (v17 + 4) & 0xFFFFFFFC;
    if ( v17 < 0x34 )
      v17 = 52;
  }
  else
  {
    v18 = v9 << 6;
    v17 = v8 + v18 + 8;
    if ( (((_BYTE)v8 + (_BYTE)v18 + 8) & 7) != 0 )
      v17 = (v17 + 8) & 0xFFFFFFF8;
    result = 72;
    if ( v17 < 0x48 )
      v17 = 72;
  }
  *a2 = v17;
  return result;
}

```

## disassembly

```asm
0x140016f74  push    rbx
0x140016f76  push    rbp
0x140016f77  push    rsi
0x140016f78  push    rdi
0x140016f79  push    r12
0x140016f7b  push    r13
0x140016f7d  push    r14
0x140016f7f  push    r15
0x140016f81  sub     rsp, 28h
0x140016f85  mov     r14, rdx
0x140016f88  mov     r15d, r9d
0x140016f8b  mov     dl, 1; Restart
0x140016f8d  mov     sil, r8b
0x140016f90  mov     rbp, rcx
0x140016f93  xor     edi, edi
0x140016f95  xor     ebx, ebx
0x140016f97  call    cs:__imp_RtlNextUnicodePrefix
0x140016f9e  nop     dword ptr [rax+rax+00h]
0x140016fa3  mov     r10, rax
0x140016fa6  mov     r12d, 0FFFFFFFCh
0x140016fac  test    rax, rax
0x140016faf  jz      loc_140017047
0x140016fb5  lea     r13d, [rdi+5]
0x140016fb9  test    byte ptr [r10-3Ch], 1
0x140016fbe  jz      short loc_14001702A
0x140016fc0  movzx   r8d, word ptr [r10-30h]
0x140016fc5  mov     al, sil
0x140016fc8  movzx   ecx, word ptr [r10+48h]
0x140016fcd  neg     al
0x140016fcf  sbb     edx, edx
0x140016fd1  add     ecx, r13d
0x140016fd4  and     edx, r12d
0x140016fd7  and     ecx, r12d
0x140016fda  add     edx, 8
0x140016fdd  xor     eax, eax
0x140016fdf  imul    edx, r8d
0x140016fe3  add     edi, edx
0x140016fe5  add     edi, ecx
0x140016fe7  cmp     ax, r8w
0x140016feb  jnb     short loc_140017028
0x140016fed  xor     edx, edx
0x140016fef  mov     r9d, r12d
0x140016ff2  cmp     r15d, 60140h
0x140016ff9  mov     eax, 0FFFFFFFEh
0x140016ffe  cmovnz  r9d, eax
0x140017002  lea     r11d, [rdx+0Bh]
0x140017006  cmovnz  r11d, r13d
0x14001700a  mov     eax, edx
0x14001700c  inc     edx
0x14001700e  imul    rcx, rax, 70h ; 'p'
0x140017012  movzx   eax, word ptr [rcx+r10+0B8h]
0x14001701b  add     eax, r11d
0x14001701e  and     eax, r9d
0x140017021  add     edi, eax
0x140017023  cmp     edx, r8d
0x140017026  jb      short loc_14001700A
0x140017028  inc     ebx
0x14001702a  xor     edx, edx; Restart
0x14001702c  mov     rcx, rbp; PrefixTable
0x14001702f  call    cs:__imp_RtlNextUnicodePrefix
0x140017036  nop     dword ptr [rax+rax+00h]
0x14001703b  mov     r10, rax
0x14001703e  test    rax, rax
0x140017041  jnz     loc_140016FB9
0x140017047  test    sil, sil
0x14001704a  jz      short loc_14001706E
0x14001704c  lea     ecx, [rbx+rbx*2]
0x14001704f  shl     ecx, 4
0x140017052  add     ecx, 4
0x140017055  add     ecx, edi
0x140017057  test    cl, 3
0x14001705a  jz      short loc_140017062
0x14001705c  add     ecx, 4
0x14001705f  and     ecx, r12d
0x140017062  cmp     ecx, 34h ; '4'
0x140017065  jnb     short loc_14001708B
0x140017067  mov     ecx, 34h ; '4'
0x14001706c  jmp     short loc_14001708B
0x14001706e  shl     ebx, 6
0x140017071  lea     ecx, [rbx+8]
0x140017074  add     ecx, edi
0x140017076  test    cl, 7
0x140017079  jz      short loc_140017081
0x14001707b  add     ecx, 8
0x14001707e  and     ecx, 0FFFFFFF8h
0x140017081  mov     eax, 48h ; 'H'
0x140017086  cmp     ecx, eax
0x140017088  cmovb   ecx, eax
0x14001708b  mov     [r14], ecx
0x14001708e  add     rsp, 28h
0x140017092  pop     r15
0x140017094  pop     r14
0x140017096  pop     r13
0x140017098  pop     r12
0x14001709a  pop     rdi
0x14001709b  pop     rsi
0x14001709c  pop     rbp
0x14001709d  pop     rbx
0x14001709e  retn
```
