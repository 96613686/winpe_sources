# XMLParser::ReportUnclosedTags(int)

- ea: `0x1800341fc`
- end: `0x180034325`
- name: `?ReportUnclosedTags@XMLParser@@AEAAJH@Z`
- size: `297`
- prototype: `__int64 __fastcall(XMLParser *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800343d0`

## callees

- `0x180003740`
- `0x180003840`
- `0x1800341fc`
- `0x180041ec0`

## pseudocode

```c
__int64 __fastcall XMLParser::ReportUnclosedTags(XMLParser *this, int a2)
{
  char *v3; // rdi
  int v4; // ecx
  unsigned int v5; // r12d
  __int64 v6; // rbx
  int v7; // esi
  unsigned int v8; // r15d
  __int64 v9; // r14
  int v10; // eax
  __int64 v11; // rbp
  int v12; // ecx
  unsigned __int128 v13; // rax
  char *v14; // rax
  char *v15; // r12
  __int64 v16; // rbx
  signed int v18; // [rsp+60h] [rbp+8h]
  int v20; // [rsp+70h] [rbp+18h]

  v3 = 0;
  v4 = *((_DWORD *)this + 32);
  v5 = 0;
  v20 = v4;
  v6 = 0;
  v7 = a2;
  v8 = -1072896685;
  while ( v7 < v4 )
  {
    v9 = *((_QWORD *)this + 15);
    v10 = *((_DWORD *)this + 28) * v7;
    v11 = v10;
    if ( *(_DWORD *)(v9 + v10 + 4) == 2 )
      break;
    v12 = *(_DWORD *)(v9 + v10 + 24);
    if ( (int)v6 + v12 + 3 > v5 )
    {
      v18 = v6 + v12 + 500;
      v13 = (unsigned __int64)v18 * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v18, 2u) )
        *(_QWORD *)&v13 = -1;
      v14 = (char *)operator new(v13, *((const struct NoThrow **)&v13 + 1));
      v15 = v14;
      if ( !v14 )
      {
        v8 = -2147024882;
        break;
      }
      if ( v3 )
      {
        memmove(v14, v3, (unsigned int)v6);
        operator delete(v3);
      }
      v3 = v15;
      v5 = v18;
    }
    if ( v7 > a2 )
    {
      *(_WORD *)&v3[2 * v6] = 44;
      v16 = (unsigned int)(v6 + 1);
      *(_WORD *)&v3[2 * v16] = 32;
      v6 = (unsigned int)(v16 + 1);
    }
    memmove(&v3[2 * v6], *(const void **)(v9 + v11 + 16), 2LL * *(unsigned int *)(v9 + v11 + 24));
    v6 = (unsigned int)(*(_DWORD *)(v9 + v11 + 24) + v6);
    v4 = v20;
    ++v7;
    *(_WORD *)&v3[2 * v6] = 0;
  }
  operator delete(v3);
  operator delete(0);
  return v8;
}

```

## disassembly

```asm
0x1800341fc  mov     [rsp+arg_18], rbx
0x180034201  mov     [rsp+arg_8], edx
0x180034205  push    rbp
0x180034206  push    rsi
0x180034207  push    rdi
0x180034208  push    r12
0x18003420a  push    r13
0x18003420c  push    r14
0x18003420e  push    r15
0x180034210  sub     rsp, 20h
0x180034214  mov     r13, rcx
0x180034217  xor     edi, edi
0x180034219  mov     ecx, [rcx+80h]
0x18003421f  xor     r12d, r12d
0x180034222  mov     [rsp+58h+arg_10], ecx
0x180034226  xor     ebx, ebx
0x180034228  mov     esi, edx
0x18003422a  mov     r15d, 0C00CE553h
0x180034230  cmp     esi, ecx
0x180034232  jge     loc_1800342FE
0x180034238  mov     r14, [r13+78h]
0x18003423c  mov     eax, esi
0x18003423e  imul    eax, [r13+70h]
0x180034243  movsxd  rbp, eax
0x180034246  cmp     dword ptr [r14+rbp+4], 2
0x18003424c  jz      loc_1800342FE
0x180034252  mov     ecx, [r14+rbp+18h]
0x180034257  lea     eax, [rcx+3]
0x18003425a  add     eax, ebx
0x18003425c  cmp     eax, r12d
0x18003425f  jbe     short loc_1800342B6
0x180034261  lea     eax, [rcx+1F4h]
0x180034267  add     eax, ebx
0x180034269  movsxd  rcx, eax
0x18003426c  mov     [rsp+58h+arg_0], eax
0x180034270  mov     eax, 2
0x180034275  mul     rcx
0x180034278  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003427f  cmovb   rax, rcx
0x180034283  mov     rcx, rax; unsigned __int64
0x180034286  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003428b  mov     r12, rax
0x18003428e  test    rax, rax
0x180034291  jz      short loc_1800342F8
0x180034293  test    rdi, rdi
0x180034296  jz      short loc_1800342AE
0x180034298  mov     r8d, ebx; Size
0x18003429b  mov     rdx, rdi; Src
0x18003429e  mov     rcx, rax; void *
0x1800342a1  call    memmove
0x1800342a6  mov     rcx, rdi; void *
0x1800342a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800342ae  mov     rdi, r12
0x1800342b1  mov     r12d, [rsp+58h+arg_0]
0x1800342b6  cmp     esi, [rsp+58h+arg_8]
0x1800342ba  jle     short loc_1800342CC
0x1800342bc  mov     word ptr [rdi+rbx*2], 2Ch ; ','
0x1800342c2  inc     ebx
0x1800342c4  mov     word ptr [rdi+rbx*2], 20h ; ' '
0x1800342ca  inc     ebx
0x1800342cc  mov     r8d, [r14+rbp+18h]
0x1800342d1  lea     rcx, [rdi+rbx*2]; void *
0x1800342d5  mov     rdx, [r14+rbp+10h]; Src
0x1800342da  add     r8, r8; Size
0x1800342dd  call    memmove
0x1800342e2  add     ebx, [r14+rbp+18h]
0x1800342e7  xor     eax, eax
0x1800342e9  mov     ecx, [rsp+58h+arg_10]
0x1800342ed  inc     esi
0x1800342ef  mov     [rdi+rbx*2], ax
0x1800342f3  jmp     loc_180034230
0x1800342f8  mov     r15d, 8007000Eh
0x1800342fe  mov     rcx, rdi; void *
0x180034301  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034306  xor     ecx, ecx; void *
0x180034308  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003430d  mov     rbx, [rsp+58h+arg_18]
0x180034312  mov     eax, r15d
0x180034315  add     rsp, 20h
0x180034319  pop     r15
0x18003431b  pop     r14
0x18003431d  pop     r13
0x18003431f  pop     r12
0x180034321  pop     rdi
0x180034322  pop     rsi
0x180034323  pop     rbp
0x180034324  retn
```
