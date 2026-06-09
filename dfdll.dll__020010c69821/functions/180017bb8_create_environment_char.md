# create_environment_char_

- ea: `0x180017bb8`
- end: `0x180017cb1`
- name: `create_environment_char_`
- size: `249`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017b4c`

## callees

- `0x180017bb8`
- `0x180017cb4`
- `0x18001845c`
- `0x180019470`
- `0x180019590`
- `0x180019608`

## pseudocode

```c
void *__fastcall create_environment_char_(char *Source)
{
  void *v1; // rsi
  const char *v2; // r14
  __int64 v3; // rdx
  __int64 v4; // rax
  void *v5; // rax
  void *v6; // rbx
  char **v7; // r15
  __int64 v8; // rbp
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi

  v1 = 0;
  v2 = Source;
  v3 = 0;
  while ( *Source )
  {
    if ( *Source != 61 )
      ++v3;
    v4 = -1;
    do
      ++v4;
    while ( Source[v4] );
    Source += v4 + 1;
  }
  v5 = calloc_base(v3 + 1, 8u);
  v6 = v5;
  if ( v5 )
  {
    v7 = (char **)v5;
    while ( *v2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v2[v8] );
      v9 = v8 + 1;
      if ( *v2 != 61 )
      {
        v10 = (char *)calloc_base(v9, 1u);
        v11 = v10;
        if ( !v10 )
        {
          free_environment_wchar_t_(v6);
          free_base(0);
          goto LABEL_20;
        }
        if ( strcpy_s(v10, v9, v2) )
          invoke_watson(0, 0, 0, 0, 0);
        *v7++ = v11;
        free_base(0);
      }
      v2 += v9;
    }
    v1 = v6;
  }
LABEL_20:
  free_base(0);
  return v1;
}

```

## disassembly

```asm
0x180017bb8  mov     [rsp+arg_0], rbx
0x180017bbd  mov     [rsp+arg_8], rbp
0x180017bc2  mov     [rsp+arg_10], rsi
0x180017bc7  push    rdi
0x180017bc8  push    r14
0x180017bca  push    r15
0x180017bcc  sub     rsp, 30h
0x180017bd0  xor     esi, esi
0x180017bd2  mov     r14, rcx
0x180017bd5  mov     edx, esi
0x180017bd7  jmp     short loc_180017BF3
0x180017bd9  cmp     al, 3Dh ; '='
0x180017bdb  jz      short loc_180017BE0
0x180017bdd  inc     rdx
0x180017be0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017be4  inc     rax
0x180017be7  cmp     [rcx+rax], sil
0x180017beb  jnz     short loc_180017BE4
0x180017bed  inc     rcx
0x180017bf0  add     rcx, rax
0x180017bf3  mov     al, [rcx]
0x180017bf5  test    al, al
0x180017bf7  jnz     short loc_180017BD9
0x180017bf9  lea     rcx, [rdx+1]; Count
0x180017bfd  mov     edx, 8; Size
0x180017c02  call    _calloc_base
0x180017c07  mov     rbx, rax
0x180017c0a  test    rax, rax
0x180017c0d  jz      short loc_180017C7B
0x180017c0f  mov     r15, rax
0x180017c12  cmp     [r14], sil
0x180017c15  jz      short loc_180017C78
0x180017c17  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180017c1b  inc     rbp
0x180017c1e  cmp     [r14+rbp], sil
0x180017c22  jnz     short loc_180017C1B
0x180017c24  inc     rbp
0x180017c27  cmp     byte ptr [r14], 3Dh ; '='
0x180017c2b  jz      short loc_180017C62
0x180017c2d  mov     edx, 1; Size
0x180017c32  mov     rcx, rbp; Count
0x180017c35  call    _calloc_base
0x180017c3a  mov     rdi, rax
0x180017c3d  test    rax, rax
0x180017c40  jz      short loc_180017C67
0x180017c42  mov     r8, r14; Source
0x180017c45  mov     rdx, rbp; SizeInBytes
0x180017c48  mov     rcx, rax; Destination
0x180017c4b  call    strcpy_s
0x180017c50  xor     ecx, ecx; Expression
0x180017c52  test    eax, eax
0x180017c54  jnz     short loc_180017C9E
0x180017c56  mov     [r15], rdi
0x180017c59  add     r15, 8
0x180017c5d  call    _free_base
0x180017c62  add     r14, rbp
0x180017c65  jmp     short loc_180017C12
0x180017c67  mov     rcx, rbx; Block
0x180017c6a  call    free_environment_wchar_t_
0x180017c6f  xor     ecx, ecx; Block
0x180017c71  call    _free_base
0x180017c76  jmp     short loc_180017C7B
0x180017c78  mov     rsi, rbx
0x180017c7b  xor     ecx, ecx; Block
0x180017c7d  call    _free_base
0x180017c82  mov     rbx, [rsp+48h+arg_0]
0x180017c87  mov     rax, rsi
0x180017c8a  mov     rsi, [rsp+48h+arg_10]
0x180017c8f  mov     rbp, [rsp+48h+arg_8]
0x180017c94  add     rsp, 30h
0x180017c98  pop     r15
0x180017c9a  pop     r14
0x180017c9c  pop     rdi
0x180017c9d  retn
0x180017c9e  xor     r9d, r9d; LineNo
0x180017ca1  mov     [rsp+48h+Reserved], rsi; Reserved
0x180017ca6  xor     r8d, r8d; FileName
0x180017ca9  xor     edx, edx; FunctionName
0x180017cab  call    _invoke_watson
```
