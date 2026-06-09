# StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)

- ea: `0x14000b700`
- end: `0x14000b8da`
- name: `?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z`
- size: `474`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, size_t Size@<rdx>, const char *@<r8>, char **@<r9>, unsigned __int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008c74`
- `0x14000a5d4`

## callees

- `0x140001af3`
- `0x14000b700`

## pseudocode

```c
__int64 __fastcall StringCchCopyExA(
        char *a1,
        size_t Size,
        const BYTE *a3,
        char **a4,
        unsigned __int64 *a5,
        unsigned int a6)
{
  size_t v8; // rdi
  __int64 v9; // rcx
  char *v10; // r15
  unsigned __int64 v11; // rbx
  unsigned int v12; // esi
  char *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rcx
  char *v16; // rax

  v8 = Size;
  v9 = 2147483646;
  if ( (a6 & 0x100) != 0 )
  {
    if ( (a1 || !Size) && Size <= 0x7FFFFFFF )
    {
      v10 = a1;
      v11 = Size;
      if ( !a3 )
        a3 = &byte_140012D60;
      goto LABEL_9;
    }
LABEL_42:
    v12 = -2147024809;
    if ( Size )
      *a1 = 0;
    return v12;
  }
  if ( Size - 1 > 0x7FFFFFFE )
    goto LABEL_42;
  v10 = a1;
  v11 = Size;
LABEL_9:
  if ( (a6 & 0xFFFFE000) != 0 )
  {
    v12 = -2147024809;
    if ( Size )
      *a1 = 0;
  }
  else if ( Size )
  {
    v13 = a1;
    v14 = 0;
    do
    {
      if ( !v9 )
        break;
      if ( !*a3 )
        break;
      *v13++ = *a3++;
      --v9;
      ++v14;
      --Size;
    }
    while ( Size );
    v15 = v14 - 1;
    if ( Size )
      v15 = v14;
    v16 = v13 - 1;
    if ( Size )
      v16 = v13;
    v10 = &a1[v15];
    *v16 = 0;
    v11 = v8 - v15;
    v12 = Size == 0 ? 0x8007007A : 0;
    if ( Size )
    {
      if ( (a6 & 0x200) != 0 && v11 > 1 )
        memset_0(v10 + 1, (unsigned __int8)a6, v11 - 1);
      goto LABEL_38;
    }
  }
  else
  {
    v12 = 0;
    if ( !*a3 )
    {
LABEL_38:
      if ( a4 )
        *a4 = v10;
      if ( a5 )
        *a5 = v11;
      return v12;
    }
    v12 = a1 != 0 ? -2147024774 : -2147024809;
  }
  if ( (a6 & 0x1C00) != 0 && v8 )
  {
    if ( (a6 & 0x1000) != 0 )
    {
      v10 = a1;
      *a1 = 0;
      v11 = v8;
    }
    if ( (a6 & 0x400) != 0 )
    {
      memset_0(a1, (unsigned __int8)a6, v8);
      if ( (_BYTE)a6 )
      {
        v11 = 1;
        v10 = &a1[v8 - 1];
        *v10 = 0;
      }
      else
      {
        v10 = a1;
        v11 = v8;
      }
    }
    if ( (a6 & 0x800) != 0 )
    {
      v10 = a1;
      *a1 = 0;
      v11 = v8;
    }
  }
  if ( v12 == -2147024774 )
    goto LABEL_38;
  return v12;
}

```

## disassembly

```asm
0x14000b700  push    rbx
0x14000b702  push    rbp
0x14000b703  push    rsi
0x14000b704  push    rdi
0x14000b705  push    r12
0x14000b707  push    r14
0x14000b709  push    r15
0x14000b70b  sub     rsp, 20h
0x14000b70f  mov     ebp, [rsp+58h+arg_28]
0x14000b716  mov     r14, rcx
0x14000b719  mov     r12, r9
0x14000b71c  mov     rdi, rdx
0x14000b71f  mov     ecx, 7FFFFFFEh
0x14000b724  bt      ebp, 8
0x14000b728  jnb     short loc_14000B759
0x14000b72a  test    r14, r14
0x14000b72d  jnz     short loc_14000B738
0x14000b72f  test    rdx, rdx
0x14000b732  jnz     loc_14000B8BA
0x14000b738  cmp     rdi, 7FFFFFFFh
0x14000b73f  ja      loc_14000B8BA
0x14000b745  mov     r15, r14
0x14000b748  mov     rbx, rdi
0x14000b74b  test    r8, r8
0x14000b74e  jnz     short loc_14000B76C
0x14000b750  lea     r8, byte_140012D60
0x14000b757  jmp     short loc_14000B76C
0x14000b759  lea     rax, [rdx-1]
0x14000b75d  cmp     rax, rcx
0x14000b760  ja      loc_14000B8BA
0x14000b766  mov     r15, r14
0x14000b769  mov     rbx, rdi
0x14000b76c  test    ebp, 0FFFFE000h
0x14000b772  jz      short loc_14000B7D4
0x14000b774  mov     esi, 80070057h
0x14000b779  test    rdi, rdi
0x14000b77c  jz      short loc_14000B782
0x14000b77e  mov     byte ptr [r14], 0
0x14000b782  test    ebp, 1C00h
0x14000b788  jz      loc_14000B897
0x14000b78e  test    rdi, rdi
0x14000b791  jz      loc_14000B897
0x14000b797  bt      ebp, 0Ch
0x14000b79b  jnb     short loc_14000B7A7
0x14000b79d  mov     r15, r14
0x14000b7a0  mov     byte ptr [r14], 0
0x14000b7a4  mov     rbx, rdi
0x14000b7a7  bt      ebp, 0Ah
0x14000b7ab  jnb     loc_14000B887
0x14000b7b1  movzx   edx, bpl; Val
0x14000b7b5  mov     r8, rdi; Size
0x14000b7b8  mov     rcx, r14; void *
0x14000b7bb  call    memset_0
0x14000b7c0  test    bpl, bpl
0x14000b7c3  jnz     loc_14000B877
0x14000b7c9  mov     r15, r14
0x14000b7cc  mov     rbx, rdi
0x14000b7cf  jmp     loc_14000B887
0x14000b7d4  test    rdi, rdi
0x14000b7d7  jnz     short loc_14000B7F8
0x14000b7d9  xor     esi, esi
0x14000b7db  cmp     [r8], sil
0x14000b7de  jz      loc_14000B89F
0x14000b7e4  mov     rax, r14
0x14000b7e7  mov     esi, 80070057h
0x14000b7ec  neg     rax
0x14000b7ef  sbb     ecx, ecx
0x14000b7f1  and     ecx, 23h
0x14000b7f4  add     esi, ecx
0x14000b7f6  jmp     short loc_14000B782
0x14000b7f8  mov     r9, r14
0x14000b7fb  xor     eax, eax
0x14000b7fd  test    rcx, rcx
0x14000b800  jz      short loc_14000B81F
0x14000b802  mov     r10b, [r8]
0x14000b805  test    r10b, r10b
0x14000b808  jz      short loc_14000B81F
0x14000b80a  mov     [r9], r10b
0x14000b80d  inc     r8
0x14000b810  inc     r9
0x14000b813  dec     rcx
0x14000b816  inc     rax
0x14000b819  sub     rdx, 1
0x14000b81d  jnz     short loc_14000B7FD
0x14000b81f  lea     rcx, [rax-1]
0x14000b823  test    rdx, rdx
0x14000b826  mov     rbx, rdi
0x14000b829  cmovnz  rcx, rax
0x14000b82d  lea     rax, [r9-1]
0x14000b831  cmovnz  rax, r9
0x14000b835  lea     r15, [rcx+r14]
0x14000b839  mov     byte ptr [rax], 0
0x14000b83c  mov     rax, rdx
0x14000b83f  neg     rax
0x14000b842  sbb     esi, esi
0x14000b844  sub     rbx, rcx
0x14000b847  not     esi
0x14000b849  and     esi, 8007007Ah
0x14000b84f  test    rdx, rdx
0x14000b852  jz      loc_14000B782
0x14000b858  bt      ebp, 9
0x14000b85c  jnb     short loc_14000B89F
0x14000b85e  cmp     rbx, 1
0x14000b862  jbe     short loc_14000B89F
0x14000b864  lea     r8, [rbx-1]; Size
0x14000b868  movzx   edx, bpl; Val
0x14000b86c  lea     rcx, [r15+1]; void *
0x14000b870  call    memset_0
0x14000b875  jmp     short loc_14000B89F
0x14000b877  lea     r15, [rdi-1]
0x14000b87b  mov     ebx, 1
0x14000b880  add     r15, r14
0x14000b883  mov     byte ptr [r15], 0
0x14000b887  bt      ebp, 0Bh
0x14000b88b  jnb     short loc_14000B897
0x14000b88d  mov     r15, r14
0x14000b890  mov     byte ptr [r14], 0
0x14000b894  mov     rbx, rdi
0x14000b897  cmp     esi, 8007007Ah
0x14000b89d  jnz     short loc_14000B8C8
0x14000b89f  test    r12, r12
0x14000b8a2  jz      short loc_14000B8A8
0x14000b8a4  mov     [r12], r15
0x14000b8a8  mov     rax, [rsp+58h+arg_20]
0x14000b8b0  test    rax, rax
0x14000b8b3  jz      short loc_14000B8C8
0x14000b8b5  mov     [rax], rbx
0x14000b8b8  jmp     short loc_14000B8C8
0x14000b8ba  mov     esi, 80070057h
0x14000b8bf  test    rdi, rdi
0x14000b8c2  jz      short loc_14000B8C8
0x14000b8c4  mov     byte ptr [r14], 0
0x14000b8c8  mov     eax, esi
0x14000b8ca  add     rsp, 20h
0x14000b8ce  pop     r15
0x14000b8d0  pop     r14
0x14000b8d2  pop     r12
0x14000b8d4  pop     rdi
0x14000b8d5  pop     rsi
0x14000b8d6  pop     rbp
0x14000b8d7  pop     rbx
0x14000b8d8  retn
```
