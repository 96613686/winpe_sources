# CODBCLOG::PrepareParameters(void)

- ea: `0x18000ba58`
- end: `0x18000bc0f`
- name: `?PrepareParameters@CODBCLOG@@QEAAHXZ`
- size: `439`
- prototype: `__int64 __fastcall(void ***this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000afb0`
- `0x18000b120`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000ba58`
- `0x18000d870`
- `0x18000ec62`

## pseudocode

```c
__int64 __fastcall CODBCLOG::PrepareParameters(void ***this)
{
  _QWORD *v2; // rbx
  unsigned int v3; // esi
  unsigned int v4; // edi
  int v5; // ebp
  __int16 v6; // r15
  _WORD *v7; // r10
  __int16 v8; // r9
  __int16 v9; // dx
  __int16 v10; // cx
  int v11; // r8d
  int v12; // r14d
  unsigned int v13; // edi
  size_t v14; // r12
  _QWORD *v15; // r15
  void *v16; // rax
  __int64 i; // rdi
  _QWORD *v18; // r14
  void *v19; // rcx
  __int64 result; // rax
  int v21; // [rsp+70h] [rbp+8h]

  v2 = operator new(0x60u);
  v3 = 0;
  if ( v2 )
  {
    v4 = 0;
    while ( 1 )
    {
      v5 = 12;
      if ( SLODWORD(qword_180017140[5 * v4]) > 0 )
      {
        v6 = qword_180017140[5 * v4];
        v7 = operator new(0x28u);
        if ( v7 )
        {
          v8 = WORD2(qword_180017140[5 * v4 + 3]);
          v9 = WORD2(qword_180017140[5 * v4 + 2]);
          v10 = WORD1(qword_180017140[5 * v4 + 2]);
          v11 = qword_180017140[5 * v4 + 3];
          v7[1] = qword_180017140[5 * v4 + 2];
          v7[2] = v10;
          v7[3] = v9;
          v7[6] = v8;
          *v7 = v6;
          *((_DWORD *)v7 + 2) = v11;
          *((_QWORD *)v7 + 2) = 0;
          *((_QWORD *)v7 + 3) = 0;
          *((_QWORD *)v7 + 4) = 0;
        }
        else
        {
          v7 = 0;
        }
        v2[v3] = v7;
        if ( !v7 )
        {
LABEL_19:
          v3 = 0;
          for ( i = 0; i != 12; ++i )
          {
            v18 = (_QWORD *)v2[i];
            if ( v18 )
            {
              v19 = (void *)v18[2];
              if ( v19 )
                operator delete(v19);
              operator delete(v18);
              v2[i] = 0;
            }
          }
          operator delete(v2);
          v2 = 0;
          break;
        }
        ++v3;
      }
      if ( ++v4 >= 0xE )
      {
        v3 = 1;
        v12 = 0;
        v13 = 0;
        while ( 1 )
        {
          if ( SLODWORD(qword_180017140[5 * v13]) > 0 )
          {
            v14 = SLODWORD(qword_180017140[5 * v13 + 4]);
            v15 = (_QWORD *)v2[v12];
            v21 = HIDWORD(qword_180017140[5 * v13 + 4]);
            v16 = operator new(v14);
            v15[2] = v16;
            if ( v16 )
            {
              memset_0(v16, 0, v14);
              v15[4] = v21;
              v15[3] = v14;
            }
            if ( !v15[2] || !ODBC_STATEMENT::BindParameter(this[114], (struct ODBC_PARAMETER *)v2[v12]) )
              goto LABEL_19;
            ++v12;
          }
          if ( ++v13 >= 0xE )
            goto LABEL_27;
        }
      }
    }
  }
  v5 = 0;
LABEL_27:
  this[115] = (void **)v2;
  result = v3;
  *((_DWORD *)this + 225) = v5;
  return result;
}

```

## disassembly

```asm
0x18000ba58  push    rbx
0x18000ba5a  push    rbp
0x18000ba5b  push    rsi
0x18000ba5c  push    rdi
0x18000ba5d  push    r12
0x18000ba5f  push    r13
0x18000ba61  push    r14
0x18000ba63  push    r15
0x18000ba65  sub     rsp, 28h
0x18000ba69  mov     r13, rcx
0x18000ba6c  mov     ecx, 60h ; '`'; Size
0x18000ba71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba76  xor     r12d, r12d
0x18000ba79  mov     rbx, rax
0x18000ba7c  mov     esi, r12d
0x18000ba7f  test    rax, rax
0x18000ba82  jz      loc_18000BBEB
0x18000ba88  mov     edi, r12d
0x18000ba8b  lea     r11, qword_180017140
0x18000ba92  mov     ecx, edi
0x18000ba94  mov     ebp, 0Ch
0x18000ba99  lea     r14, [rcx+rcx*4]
0x18000ba9d  cmp     [r11+r14*8], r12d
0x18000baa1  jle     short loc_18000BB1A
0x18000baa3  movzx   r15d, word ptr [r11+r14*8]
0x18000baa8  lea     ecx, [rbp+1Ch]; Size
0x18000baab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bab0  lea     r11, qword_180017140
0x18000bab7  mov     r10, rax
0x18000baba  test    rax, rax
0x18000babd  jz      short loc_18000BB06
0x18000babf  movzx   r9d, word ptr [r11+r14*8+1Ch]
0x18000bac5  movzx   edx, word ptr [r11+r14*8+14h]
0x18000bacb  movzx   ecx, word ptr [r11+r14*8+12h]
0x18000bad1  movzx   eax, word ptr [r11+r14*8+10h]
0x18000bad7  mov     r8d, [r11+r14*8+18h]
0x18000badc  mov     [r10+2], ax
0x18000bae1  mov     [r10+4], cx
0x18000bae6  mov     [r10+6], dx
0x18000baeb  mov     [r10+0Ch], r9w
0x18000baf0  mov     [r10], r15w
0x18000baf4  mov     [r10+8], r8d
0x18000baf8  mov     [r10+10h], r12
0x18000bafc  mov     [r10+18h], r12
0x18000bb00  mov     [r10+20h], r12
0x18000bb04  jmp     short loc_18000BB09
0x18000bb06  mov     r10, r12
0x18000bb09  mov     eax, esi
0x18000bb0b  mov     [rbx+rax*8], r10
0x18000bb0f  test    r10, r10
0x18000bb12  jz      loc_18000BBAF
0x18000bb18  inc     esi
0x18000bb1a  inc     edi
0x18000bb1c  cmp     edi, 0Eh
0x18000bb1f  jb      loc_18000BA92
0x18000bb25  mov     esi, 1
0x18000bb2a  mov     r14d, r12d
0x18000bb2d  mov     edi, r12d
0x18000bb30  mov     eax, edi
0x18000bb32  lea     rcx, [rax+rax*4]
0x18000bb36  cmp     [r11+rcx*8], r12d
0x18000bb3a  jle     short loc_18000BBA6
0x18000bb3c  movsxd  r12, dword ptr [r11+rcx*8+20h]
0x18000bb41  mov     eax, r14d
0x18000bb44  mov     r15, [rbx+rax*8]
0x18000bb48  mov     eax, [r11+rcx*8+24h]
0x18000bb4d  mov     rcx, r12; Size
0x18000bb50  mov     [rsp+68h+arg_0], eax
0x18000bb54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb59  mov     [r15+10h], rax
0x18000bb5d  test    rax, rax
0x18000bb60  jz      short loc_18000BB7C
0x18000bb62  mov     r8, r12; Size
0x18000bb65  xor     edx, edx; Val
0x18000bb67  mov     rcx, rax; void *
0x18000bb6a  call    memset_0
0x18000bb6f  movsxd  rax, [rsp+68h+arg_0]
0x18000bb74  mov     [r15+20h], rax
0x18000bb78  mov     [r15+18h], r12
0x18000bb7c  xor     r12d, r12d
0x18000bb7f  cmp     [r15+10h], r12
0x18000bb83  jz      short loc_18000BBAF
0x18000bb85  mov     rcx, [r13+390h]; this
0x18000bb8c  mov     edx, r14d
0x18000bb8f  mov     rdx, [rbx+rdx*8]; struct ODBC_PARAMETER *
0x18000bb93  call    ?BindParameter@ODBC_STATEMENT@@QEAAHPEAVODBC_PARAMETER@@@Z; ODBC_STATEMENT::BindParameter(ODBC_PARAMETER *)
0x18000bb98  test    eax, eax
0x18000bb9a  jz      short loc_18000BBAF
0x18000bb9c  inc     r14d
0x18000bb9f  lea     r11, qword_180017140
0x18000bba6  inc     edi
0x18000bba8  cmp     edi, 0Eh
0x18000bbab  jb      short loc_18000BB30
0x18000bbad  jmp     short loc_18000BBEE
0x18000bbaf  mov     esi, r12d
0x18000bbb2  mov     rdi, r12
0x18000bbb5  mov     r14, [rbx+rdi*8]
0x18000bbb9  test    r14, r14
0x18000bbbc  jz      short loc_18000BBD8
0x18000bbbe  mov     rcx, [r14+10h]; Block
0x18000bbc2  test    rcx, rcx
0x18000bbc5  jz      short loc_18000BBCC
0x18000bbc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bbcc  mov     rcx, r14; Block
0x18000bbcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bbd4  mov     [rbx+rdi*8], r12
0x18000bbd8  inc     rdi
0x18000bbdb  cmp     rdi, rbp
0x18000bbde  jnz     short loc_18000BBB5
0x18000bbe0  mov     rcx, rbx; Block
0x18000bbe3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bbe8  mov     rbx, r12
0x18000bbeb  mov     ebp, r12d
0x18000bbee  mov     [r13+398h], rbx
0x18000bbf5  mov     eax, esi
0x18000bbf7  mov     [r13+384h], ebp
0x18000bbfe  add     rsp, 28h
0x18000bc02  pop     r15
0x18000bc04  pop     r14
0x18000bc06  pop     r13
0x18000bc08  pop     r12
0x18000bc0a  pop     rdi
0x18000bc0b  pop     rsi
0x18000bc0c  pop     rbp
0x18000bc0d  pop     rbx
0x18000bc0e  retn
```
