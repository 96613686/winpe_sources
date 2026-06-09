# CompactGlyphSet

- ea: `0x140034688`
- end: `0x14003472c`
- name: `CompactGlyphSet`
- size: `164`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400350dc`

## callees

- `0x140034688`
- `0x140038e74`
- `0x140076ef6`

## pseudocode

```c
__int64 __fastcall CompactGlyphSet(char *Src, __int64 a2, int a3, _QWORD *a4)
{
  int v5; // eax
  unsigned int v7; // edi
  __int64 v8; // r15
  char *v9; // rdx
  unsigned int v10; // r14d
  __int64 v11; // rax
  unsigned int *v12; // rdx
  unsigned __int16 v13; // r8

  v5 = a2;
  v7 = 0;
  *a4 = 0;
  if ( Src )
  {
    if ( a2 )
    {
      v8 = a3;
      v9 = &Src[a3];
      v10 = v5 - (_DWORD)v9;
      memmove_0(&Src[*(unsigned int *)Src], v9, (unsigned int)(v5 - (_DWORD)v9));
      if ( *(_DWORD *)Src + v10 >= v10 )
      {
        v11 = ATMrealloc(Src);
        v12 = (unsigned int *)Src;
        if ( v11 )
          v12 = (unsigned int *)v11;
        v13 = 0;
        v7 = 1;
        while ( v13 < v12[3] )
          *(_QWORD *)&v12[4 * v13++ + 6] += (char *)v12 + *v12 - v8 - (_QWORD)Src;
        *v12 += v10;
        *a4 = v12;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140034688  push    rbx
0x14003468a  push    rsi
0x14003468b  push    rdi
0x14003468c  push    r14
0x14003468e  push    r15
0x140034690  sub     rsp, 30h
0x140034694  mov     rsi, r9
0x140034697  mov     rax, rdx
0x14003469a  mov     rbx, rcx
0x14003469d  xor     edi, edi
0x14003469f  mov     [r9], rdi
0x1400346a2  test    rcx, rcx
0x1400346a5  jz      short loc_14003471E
0x1400346a7  test    rax, rax
0x1400346aa  jz      short loc_14003471E
0x1400346ac  movsxd  r15, r8d
0x1400346af  lea     rdx, [r15+rcx]; Src
0x1400346b3  sub     eax, edx
0x1400346b5  mov     r14d, eax
0x1400346b8  mov     r8d, eax; Size
0x1400346bb  mov     ecx, [rcx]
0x1400346bd  add     rcx, rbx; void *
0x1400346c0  call    memmove_0
0x1400346c5  mov     eax, [rbx]
0x1400346c7  lea     ecx, [rax+r14]
0x1400346cb  cmp     ecx, r14d
0x1400346ce  jb      short loc_14003471E
0x1400346d0  mov     edx, ecx
0x1400346d2  mov     rcx, rbx; Src
0x1400346d5  call    ATMrealloc
0x1400346da  mov     rdx, rbx
0x1400346dd  test    rax, rax
0x1400346e0  cmovnz  rdx, rax
0x1400346e4  xor     r8d, r8d
0x1400346e7  lea     edi, [r8+1]
0x1400346eb  mov     [rsp+58h+var_38], r8w
0x1400346f1  movzx   eax, r8w
0x1400346f5  cmp     eax, [rdx+0Ch]
0x1400346f8  jnb     short loc_140034718
0x1400346fa  movzx   ecx, r8w
0x1400346fe  shl     rcx, 4
0x140034702  mov     eax, [rdx]
0x140034704  sub     rax, r15
0x140034707  sub     rax, rbx
0x14003470a  add     rax, rdx
0x14003470d  add     [rcx+rdx+18h], rax
0x140034712  add     r8w, di
0x140034716  jmp     short loc_1400346EB
0x140034718  add     [rdx], r14d
0x14003471b  mov     [rsi], rdx
0x14003471e  mov     eax, edi
0x140034720  add     rsp, 30h
0x140034724  pop     r15
0x140034726  pop     r14
0x140034728  pop     rdi
0x140034729  pop     rsi
0x14003472a  pop     rbx
0x14003472b  retn
0x140096807  push    rbp
0x140096809  sub     rsp, 20h
0x14009680d  mov     rbp, rdx
0x140096810  add     rsp, 20h
0x140096814  pop     rbp
0x140096815  retn
```
