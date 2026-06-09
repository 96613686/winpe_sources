# common_expand_argv_wildcards_char_

- ea: `0x180019664`
- end: `0x18001986d`
- name: `common_expand_argv_wildcards_char_`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180019bf4`

## callees

- `0x180017970`
- `0x180019450`
- `0x180019470`
- `0x180019570`
- `0x180019608`
- `0x180019664`
- `0x180019870`
- `0x180019980`
- `0x18001be14`
- `0x18001bee8`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards_char_(const char **a1, __int64 *a2)
{
  const char **v2; // rbx
  bool i; // zf
  const char *v5; // rcx
  char *v6; // rax
  char *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // r14d
  __int64 buffer_for_argv; // rax
  __int64 v11; // rdx
  __int64 Control; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+58h]

  v2 = a1;
  if ( a2 )
  {
    *a2 = 0;
    for ( i = *a1 == 0; !i; i = *v2 == 0 )
    {
      v5 = *v2;
      strcpy((char *)&Control, "*?");
      v6 = strpbrk(v5, (const char *)&Control);
      v7 = (char *)*v2;
      if ( v6 )
        v8 = expand_argument_wildcards_char_(v7);
      else
        v8 = copy_and_add_argument_to_buffer_char_(v7, 0, 0);
      v9 = v8;
      if ( v8 )
        goto LABEL_14;
      ++v2;
    }
    Control = 0;
    v9 = -1;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(1, 0, 1);
    if ( buffer_for_argv )
    {
      v11 = buffer_for_argv + 8;
      v14 = v11;
      v9 = 0;
      *a2 = buffer_for_argv;
    }
    free_base(0);
LABEL_14:
    free_base(0);
    return v9;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x180019664  mov     [rsp-38h+arg_0], rbx
0x180019669  mov     [rsp-38h+arg_8], rdx
0x18001966e  push    rbp
0x18001966f  push    rsi
0x180019670  push    rdi
0x180019671  push    r12
0x180019673  push    r13
0x180019675  push    r14
0x180019677  push    r15
0x180019679  mov     rbp, rsp
0x18001967c  sub     rsp, 60h
0x180019680  xor     edi, edi
0x180019682  mov     rbx, rcx
0x180019685  test    rdx, rdx
0x180019688  jnz     short loc_1800196A0
0x18001968a  call    _errno
0x18001968f  lea     ebx, [rdi+16h]
0x180019692  mov     [rax], ebx
0x180019694  call    _invalid_parameter_noinfo
0x180019699  mov     eax, ebx
0x18001969b  jmp     loc_180019840
0x1800196a0  xorps   xmm0, xmm0
0x1800196a3  mov     [rdx], rdi
0x1800196a6  cmp     [rcx], rdi
0x1800196a9  movdqu  xmmword ptr [rbp+Block], xmm0
0x1800196ae  mov     [rbp+var_10], rdi
0x1800196b2  jz      short loc_18001970B
0x1800196b4  mov     rcx, [rbx]; Str
0x1800196b7  lea     rdx, [rbp+Control]; Control
0x1800196bb  mov     word ptr [rbp+Control], 3F2Ah
0x1800196c1  mov     byte ptr [rbp+Control+2], dil
0x1800196c5  call    strpbrk
0x1800196ca  mov     rcx, [rbx]; char *
0x1800196cd  test    rax, rax
0x1800196d0  jnz     short loc_1800196E2
0x1800196d2  lea     r9, [rbp+Block]
0x1800196d6  xor     r8d, r8d; MaxCount
0x1800196d9  xor     edx, edx; char *
0x1800196db  call    copy_and_add_argument_to_buffer_char_
0x1800196e0  jmp     short loc_1800196EE
0x1800196e2  lea     r8, [rbp+Block]
0x1800196e6  mov     rdx, rax
0x1800196e9  call    expand_argument_wildcards_char_
0x1800196ee  mov     r14d, eax
0x1800196f1  test    eax, eax
0x1800196f3  jnz     short loc_1800196FE
0x1800196f5  add     rbx, 8
0x1800196f9  cmp     [rbx], rdi
0x1800196fc  jmp     short loc_1800196B2
0x1800196fe  mov     r12, [rbp+Block+8]
0x180019702  mov     rsi, [rbp+Block]
0x180019706  jmp     loc_180019804
0x18001970b  mov     rsi, [rbp+Block]
0x18001970f  mov     r9, rdi
0x180019712  mov     r12, [rbp+Block+8]
0x180019716  mov     rdx, rsi
0x180019719  mov     rax, r12
0x18001971c  mov     [rbp+Control], rdi
0x180019720  sub     rax, rsi
0x180019723  mov     r8, rdi
0x180019726  mov     r15, rax
0x180019729  sar     r15, 3
0x18001972d  inc     r15
0x180019730  lea     rcx, [rax+7]
0x180019734  shr     rcx, 3
0x180019738  cmp     rsi, r12
0x18001973b  cmova   rcx, rdi
0x18001973f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180019743  test    rcx, rcx
0x180019746  jz      short loc_18001976D
0x180019748  mov     r10, [rdx]
0x18001974b  mov     rax, r14
0x18001974e  inc     rax
0x180019751  cmp     [r10+rax], dil
0x180019755  jnz     short loc_18001974E
0x180019757  inc     r9
0x18001975a  add     rdx, 8
0x18001975e  add     r9, rax
0x180019761  inc     r8
0x180019764  cmp     r8, rcx
0x180019767  jnz     short loc_180019748
0x180019769  mov     [rbp+Control], r9
0x18001976d  mov     r8d, 1
0x180019773  mov     rdx, r9
0x180019776  mov     rcx, r15
0x180019779  call    __acrt_allocate_buffer_for_argv
0x18001977e  mov     rbx, rax
0x180019781  test    rax, rax
0x180019784  jz      short loc_1800197FD
0x180019786  lea     rdx, [rax+r15*8]
0x18001978a  mov     r15, rsi
0x18001978d  mov     [rbp+var_28], rdx
0x180019791  mov     rax, rdx
0x180019794  mov     [rbp+arg_18], rdx
0x180019798  cmp     rsi, r12
0x18001979b  jz      short loc_1800197F3
0x18001979d  mov     rcx, rbx
0x1800197a0  sub     rcx, rsi
0x1800197a3  mov     [rbp+var_30], rcx
0x1800197a7  mov     r8, [r15]; Source
0x1800197aa  mov     r13, r14
0x1800197ad  inc     r13
0x1800197b0  cmp     [r8+r13], dil
0x1800197b4  jnz     short loc_1800197AD
0x1800197b6  sub     rdx, rax
0x1800197b9  inc     r13
0x1800197bc  add     rdx, [rbp+Control]; SizeInBytes
0x1800197c0  mov     r9, r13; MaxCount
0x1800197c3  mov     rcx, rax; Destination
0x1800197c6  call    strncpy_s
0x1800197cb  test    eax, eax
0x1800197cd  jnz     loc_180019858
0x1800197d3  mov     rax, [rbp+arg_18]
0x1800197d7  mov     rcx, [rbp+var_30]
0x1800197db  mov     rdx, [rbp+var_28]
0x1800197df  mov     [rcx+r15], rax
0x1800197e3  add     rax, r13
0x1800197e6  add     r15, 8
0x1800197ea  mov     [rbp+arg_18], rax
0x1800197ee  cmp     r15, r12
0x1800197f1  jnz     short loc_1800197A7
0x1800197f3  mov     rax, [rbp+arg_8]
0x1800197f7  mov     r14d, edi
0x1800197fa  mov     [rax], rbx
0x1800197fd  xor     ecx, ecx; Block
0x1800197ff  call    _free_base
0x180019804  mov     rbx, r12
0x180019807  mov     r15, rsi
0x18001980a  sub     rbx, rsi
0x18001980d  add     rbx, 7
0x180019811  shr     rbx, 3
0x180019815  cmp     rsi, r12
0x180019818  cmova   rbx, rdi
0x18001981c  test    rbx, rbx
0x18001981f  jz      short loc_180019835
0x180019821  mov     rcx, [r15]; Block
0x180019824  call    _free_base
0x180019829  inc     rdi
0x18001982c  lea     r15, [r15+8]
0x180019830  cmp     rdi, rbx
0x180019833  jnz     short loc_180019821
0x180019835  mov     rcx, rsi; Block
0x180019838  call    _free_base
0x18001983d  mov     eax, r14d
0x180019840  mov     rbx, [rsp+60h+arg_0]
0x180019848  add     rsp, 60h
0x18001984c  pop     r15
0x18001984e  pop     r14
0x180019850  pop     r13
0x180019852  pop     r12
0x180019854  pop     rdi
0x180019855  pop     rsi
0x180019856  pop     rbp
0x180019857  retn
0x180019858  xor     r9d, r9d; LineNo
0x18001985b  mov     [rsp+60h+Reserved], rdi; Reserved
0x180019860  xor     r8d, r8d; FileName
0x180019863  xor     edx, edx; FunctionName
0x180019865  xor     ecx, ecx; Expression
0x180019867  call    _invoke_watson
```
