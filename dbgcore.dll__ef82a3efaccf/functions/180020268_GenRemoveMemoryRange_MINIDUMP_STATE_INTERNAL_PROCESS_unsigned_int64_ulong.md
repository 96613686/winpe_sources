# GenRemoveMemoryRange(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,unsigned __int64,ulong)

- ea: `0x180020268`
- end: `0x1800203c5`
- name: `?GenRemoveMemoryRange@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@_KK@Z`
- size: `349`
- prototype: `void __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058d0`
- `0x18000670c`

## callees

- `0x18001fbd0`
- `0x18001febc`
- `0x180020268`

## pseudocode

```c
void __fastcall GenRemoveMemoryRange(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r14
  unsigned __int64 v8; // r10
  unsigned int v9; // edi
  __int64 i; // rcx
  unsigned __int64 *v11; // r8
  unsigned __int64 v12; // rbp
  int v13; // r13d
  unsigned __int64 v14; // [rsp+40h] [rbp-58h]

  if ( a4 )
  {
    v4 = a3;
    v5 = a3 + a4;
    if ( v5 >= a3 )
    {
      v8 = v5 - 1;
      v9 = (a4 + *((_DWORD *)a1 + 47) + (*((_DWORD *)a1 + 47) & (unsigned int)a3)) >> *((_DWORD *)a1 + 46);
      while ( v9 )
      {
        --v9;
LABEL_5:
        for ( i = *((_QWORD *)a2 + (v4 >> *((_DWORD *)a1 + 46)) % 0x397 + 22); i; i = *(_QWORD *)(i + 8) )
        {
          v11 = *(unsigned __int64 **)i;
          v12 = **(_QWORD **)i;
          if ( v12 <= v8 )
          {
            v13 = *((_DWORD *)v11 + 4);
            v14 = v12 + *((unsigned int *)v11 + 2);
            if ( v14 - 1 >= v4 )
            {
              GenFreeMemoryBlock(a1, a2, (struct _VA_RANGE *)v11, 1u);
              if ( v12 < v4 )
                GenAddOrExtendMemoryRange((__int64)a1, (__int64)a2, 0, v12, v4, v13, 0);
              v8 = v5 - 1;
              if ( v14 - 1 > v5 - 1 )
              {
                GenAddOrExtendMemoryRange((__int64)a1, (__int64)a2, 0, v5, v14, v13, 0);
                v8 = v5 - 1;
              }
              goto LABEL_5;
            }
          }
        }
        v4 += *((unsigned int *)a1 + 47) + 1LL;
      }
    }
  }
}

```

## disassembly

```asm
0x180020268  test    r9d, r9d
0x18002026b  jz      locret_1800203C4
0x180020271  push    rbx
0x180020272  push    rbp
0x180020273  push    rsi
0x180020274  push    rdi
0x180020275  push    r12
0x180020277  push    r13
0x180020279  push    r14
0x18002027b  push    r15
0x18002027d  sub     rsp, 58h
0x180020281  mov     rbx, r8
0x180020284  mov     r14d, r9d
0x180020287  add     r14, rbx
0x18002028a  mov     r15, rdx
0x18002028d  mov     rsi, rcx
0x180020290  cmp     r14, rbx
0x180020293  jb      loc_1800203B4
0x180020299  mov     eax, [rcx+0BCh]
0x18002029f  lea     r10, [r14-1]
0x1800202a3  mov     ecx, [rcx+0B8h]
0x1800202a9  mov     edi, ebx
0x1800202ab  and     edi, eax
0x1800202ad  add     edi, eax
0x1800202af  add     edi, r9d
0x1800202b2  shr     edi, cl
0x1800202b4  jmp     loc_1800203AC
0x1800202b9  dec     edi
0x1800202bb  mov     ecx, [rsi+0B8h]
0x1800202c1  mov     r8, rbx
0x1800202c4  shr     r8, cl
0x1800202c7  mov     rax, 1D3FCA840A073E1Fh
0x1800202d1  mul     r8
0x1800202d4  mov     rax, r8
0x1800202d7  sub     rax, rdx
0x1800202da  shr     rax, 1
0x1800202dd  add     rax, rdx
0x1800202e0  shr     rax, 9
0x1800202e4  imul    rax, 397h
0x1800202eb  sub     r8, rax
0x1800202ee  mov     eax, r8d
0x1800202f1  mov     rcx, [r15+rax*8+0B0h]
0x1800202f9  test    rcx, rcx
0x1800202fc  jz      loc_1800203A0
0x180020302  mov     r8, [rcx]; struct _VA_RANGE *
0x180020305  mov     rbp, [r8]
0x180020308  cmp     rbp, r10
0x18002030b  ja      short loc_180020326
0x18002030d  mov     eax, [r8+8]
0x180020311  mov     r13d, [r8+10h]
0x180020315  add     rax, rbp
0x180020318  mov     [rsp+98h+var_58], rax
0x18002031d  lea     r12, [rax-1]
0x180020321  cmp     r12, rbx
0x180020324  jnb     short loc_18002032C
0x180020326  mov     rcx, [rcx+8]
0x18002032a  jmp     short loc_1800202F9
0x18002032c  mov     r9b, 1; unsigned __int8
0x18002032f  mov     rdx, r15; struct _INTERNAL_PROCESS *
0x180020332  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180020335  call    ?GenFreeMemoryBlock@@YAPEAU_VA_RANGE_REF@@PEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@E@Z; GenFreeMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,uchar)
0x18002033a  cmp     rbp, rbx
0x18002033d  jnb     short loc_180020362
0x18002033f  mov     [rsp+98h+var_68], 0
0x180020347  mov     r9, rbp
0x18002034a  mov     [rsp+98h+var_70], r13d
0x18002034f  xor     r8d, r8d
0x180020352  mov     rdx, r15
0x180020355  mov     [rsp+98h+var_78], rbx
0x18002035a  mov     rcx, rsi
0x18002035d  call    ?GenAddOrExtendMemoryRange@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@_K3W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@@Z; GenAddOrExtendMemoryRange(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,unsigned __int64,unsigned __int64,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE)
0x180020362  lea     r10, [r14-1]
0x180020366  cmp     r12, r10
0x180020369  jbe     loc_1800202BB
0x18002036f  mov     rax, [rsp+98h+var_58]
0x180020374  mov     r9, r14
0x180020377  mov     [rsp+98h+var_68], 0
0x18002037f  xor     r8d, r8d
0x180020382  mov     [rsp+98h+var_70], r13d
0x180020387  mov     rdx, r15
0x18002038a  mov     rcx, rsi
0x18002038d  mov     [rsp+98h+var_78], rax
0x180020392  call    ?GenAddOrExtendMemoryRange@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_VA_RANGE@@_K3W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@@Z; GenAddOrExtendMemoryRange(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_VA_RANGE *,unsigned __int64,unsigned __int64,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE)
0x180020397  lea     r10, [r14-1]
0x18002039b  jmp     loc_1800202BB
0x1800203a0  mov     eax, [rsi+0BCh]
0x1800203a6  inc     rax
0x1800203a9  add     rbx, rax
0x1800203ac  test    edi, edi
0x1800203ae  jnz     loc_1800202B9
0x1800203b4  add     rsp, 58h
0x1800203b8  pop     r15
0x1800203ba  pop     r14
0x1800203bc  pop     r13
0x1800203be  pop     r12
0x1800203c0  pop     rdi
0x1800203c1  pop     rsi
0x1800203c2  pop     rbp
0x1800203c3  pop     rbx
0x1800203c4  retn
```
