# copy_and_add_argument_to_buffer_char_

- ea: `0x180019870`
- end: `0x180019980`
- name: `copy_and_add_argument_to_buffer_char_`
- size: `272`
- prototype: `__int64 __fastcall(char *Source, char *, rsize_t MaxCount)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180019664`
- `0x180019980`

## callees

- `0x180019470`
- `0x180019590`
- `0x180019608`
- `0x180019870`
- `0x180019b2c`
- `0x18001be14`

## pseudocode

```c
__int64 __fastcall copy_and_add_argument_to_buffer_char_(char *Source, char *a2, rsize_t MaxCount, __int64 a4)
{
  __int64 v5; // rdi
  rsize_t v9; // rdi
  size_t v11; // r14
  char *v12; // rax
  char *v13; // rbx
  unsigned int v14; // edi

  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  v9 = v5 + 1;
  if ( v9 > -1LL - MaxCount )
    return 12;
  v11 = v9 + MaxCount + 1;
  v12 = (char *)calloc_base(v11, 1u);
  v13 = v12;
  if ( MaxCount && strncpy_s(v12, v11, a2, MaxCount) )
    invoke_watson(0, 0, 0, 0, 0);
  if ( strncpy_s(&v13[MaxCount], v11 - MaxCount, Source, v9) )
    invoke_watson(0, 0, 0, 0, 0);
  v14 = `anonymous namespace'::argument_list<char>::expand_if_necessary(a4);
  if ( v14 )
  {
    free_base(v13);
  }
  else
  {
    **(_QWORD **)(a4 + 8) = v13;
    *(_QWORD *)(a4 + 8) += 8LL;
    v14 = 0;
  }
  free_base(0);
  return v14;
}

```

## disassembly

```asm
0x180019870  mov     rax, rsp
0x180019873  mov     [rax+8], rbx
0x180019877  mov     [rax+10h], rbp
0x18001987b  mov     [rax+18h], rsi
0x18001987f  mov     [rax+20h], rdi
0x180019883  push    r12
0x180019885  push    r14
0x180019887  push    r15
0x180019889  sub     rsp, 30h
0x18001988d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019891  mov     rsi, r9
0x180019894  mov     rdi, rax
0x180019897  mov     rbp, r8
0x18001989a  mov     r12, rdx
0x18001989d  mov     r15, rcx
0x1800198a0  inc     rdi
0x1800198a3  cmp     byte ptr [rcx+rdi], 0
0x1800198a7  jnz     short loc_1800198A0
0x1800198a9  mov     edx, 1; Size
0x1800198ae  sub     rax, r8
0x1800198b1  add     rdi, rdx
0x1800198b4  cmp     rdi, rax
0x1800198b7  jbe     short loc_1800198DB
0x1800198b9  lea     eax, [rdx+0Bh]
0x1800198bc  mov     rbx, [rsp+48h+arg_0]
0x1800198c1  mov     rbp, [rsp+48h+arg_8]
0x1800198c6  mov     rsi, [rsp+48h+arg_10]
0x1800198cb  mov     rdi, [rsp+48h+arg_18]
0x1800198d0  add     rsp, 30h
0x1800198d4  pop     r15
0x1800198d6  pop     r14
0x1800198d8  pop     r12
0x1800198da  retn
0x1800198db  lea     r14, [r8+1]
0x1800198df  add     r14, rdi
0x1800198e2  mov     rcx, r14; Count
0x1800198e5  call    _calloc_base
0x1800198ea  mov     rbx, rax
0x1800198ed  test    rbp, rbp
0x1800198f0  jz      short loc_180019907
0x1800198f2  mov     r9, rbp; MaxCount
0x1800198f5  mov     r8, r12; Source
0x1800198f8  mov     rdx, r14; SizeInBytes
0x1800198fb  mov     rcx, rax; Destination
0x1800198fe  call    strncpy_s
0x180019903  test    eax, eax
0x180019905  jnz     short loc_180019954
0x180019907  sub     r14, rbp
0x18001990a  lea     rcx, [rbx+rbp]; Destination
0x18001990e  mov     rdx, r14; SizeInBytes
0x180019911  mov     r9, rdi; MaxCount
0x180019914  mov     r8, r15; Source
0x180019917  call    strncpy_s
0x18001991c  test    eax, eax
0x18001991e  jnz     short loc_18001996A
0x180019920  mov     rcx, rsi
0x180019923  call    ?expand_if_necessary@?$argument_list@D@?A0xca0879c4@@AEAAHXZ
0x180019928  mov     edi, eax
0x18001992a  test    eax, eax
0x18001992c  jz      short loc_180019938
0x18001992e  mov     rcx, rbx; Block
0x180019931  call    _free_base
0x180019936  jmp     short loc_180019946
0x180019938  mov     rax, [rsi+8]
0x18001993c  mov     [rax], rbx
0x18001993f  add     qword ptr [rsi+8], 8
0x180019944  xor     edi, edi
0x180019946  xor     ecx, ecx; Block
0x180019948  call    _free_base
0x18001994d  mov     eax, edi
0x18001994f  jmp     loc_1800198BC
0x180019954  and     [rsp+48h+var_28], 0
0x18001995a  xor     r9d, r9d; LineNo
0x18001995d  xor     r8d, r8d; FileName
0x180019960  xor     edx, edx; FunctionName
0x180019962  xor     ecx, ecx; Expression
0x180019964  call    _invoke_watson
0x18001996a  and     [rsp+48h+var_28], 0
0x180019970  xor     r9d, r9d; LineNo
0x180019973  xor     r8d, r8d; FileName
0x180019976  xor     edx, edx; FunctionName
0x180019978  xor     ecx, ecx; Expression
0x18001997a  call    _invoke_watson
```
