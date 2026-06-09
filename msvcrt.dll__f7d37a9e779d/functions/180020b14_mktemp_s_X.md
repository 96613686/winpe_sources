# _mktemp_s_X

- ea: `0x180020b14`
- end: `0x180020c5d`
- name: `_mktemp_s_X`
- size: `329`
- prototype: `__int64 __fastcall(unsigned __int8 *String)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180020aa0`
- `0x180020b00`

## callees

- `0x180007f00`
- `0x1800080a0`
- `0x180020b14`
- `0x180025820`
- `0x18002f050`
- `0x18003de70`
- `0x1800610b0`

## pseudocode

```c
__int64 __fastcall mktemp_s_X(const char *String, size_t a2, int a3)
{
  size_t v6; // rbp
  unsigned int v7; // r15d
  unsigned __int64 v8; // r14
  unsigned __int8 *i; // rdi
  int v10; // ebp
  int v11; // r14d

  if ( !String || !a2 )
    goto LABEL_24;
  v6 = strnlen(String, a2);
  if ( v6 >= a2 )
    goto LABEL_22;
  v7 = _threadid();
  if ( v6 < 6 )
    goto LABEL_22;
  v8 = 0;
  for ( i = (unsigned __int8 *)&String[v6 - 1];
        i >= (unsigned __int8 *)String && !ismbstrail((const unsigned __int8 *)String, i);
        --i )
  {
    if ( *i != 88 )
      goto LABEL_22;
    if ( v8 >= 5 )
      break;
    ++v8;
    *i = v7 % 0xA + 48;
    v7 /= 0xAu;
  }
  if ( *i != 88 || v8 < 5 )
  {
LABEL_22:
    if ( a3 )
      *String = 0;
LABEL_24:
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  *i = 97;
  v10 = 98;
  v11 = *errno();
  while ( 1 )
  {
    *errno() = 0;
    if ( access_s(String, 0) && *errno() != 13 )
    {
      *errno() = v11;
      return 0;
    }
    if ( v10 == 123 )
      break;
    *i = v10++;
  }
  if ( a3 )
    *String = 0;
  *errno() = 17;
  return 17;
}

```

## disassembly

```asm
0x180020b14  push    rbx
0x180020b16  push    rbp
0x180020b17  push    rsi
0x180020b18  push    rdi
0x180020b19  push    r14
0x180020b1b  push    r15
0x180020b1d  sub     rsp, 38h
0x180020b21  mov     esi, r8d
0x180020b24  mov     rdi, rdx
0x180020b27  mov     rbx, rcx
0x180020b2a  test    rcx, rcx
0x180020b2d  jz      loc_180020C2A
0x180020b33  test    rdx, rdx
0x180020b36  jz      loc_180020C2A
0x180020b3c  call    strnlen
0x180020b41  mov     rbp, rax
0x180020b44  cmp     rax, rdi
0x180020b47  jnb     loc_180020C23
0x180020b4d  call    __threadid
0x180020b52  mov     r15d, eax
0x180020b55  cmp     rbp, 6
0x180020b59  jb      loc_180020C23
0x180020b5f  xor     r14d, r14d
0x180020b62  lea     rdi, [rbx-1]
0x180020b66  add     rdi, rbp
0x180020b69  jmp     short loc_180020BB1
0x180020b6b  mov     rdx, rdi; Pos
0x180020b6e  mov     rcx, rbx; String
0x180020b71  call    _ismbstrail
0x180020b76  test    eax, eax
0x180020b78  jnz     short loc_180020BB6
0x180020b7a  cmp     byte ptr [rdi], 58h ; 'X'
0x180020b7d  jnz     loc_180020C23
0x180020b83  cmp     r14, 5
0x180020b87  jnb     short loc_180020BB6
0x180020b89  mov     eax, 0CCCCCCCDh
0x180020b8e  inc     r14
0x180020b91  mul     r15d
0x180020b94  shr     edx, 3
0x180020b97  mov     al, dl
0x180020b99  shl     al, 2
0x180020b9c  lea     ecx, [rax+rdx]
0x180020b9f  add     cl, cl
0x180020ba1  sub     r15b, cl
0x180020ba4  add     r15b, 30h ; '0'
0x180020ba8  mov     [rdi], r15b
0x180020bab  mov     r15d, edx
0x180020bae  dec     rdi
0x180020bb1  cmp     rdi, rbx
0x180020bb4  jnb     short loc_180020B6B
0x180020bb6  cmp     byte ptr [rdi], 58h ; 'X'
0x180020bb9  jnz     short loc_180020C23
0x180020bbb  cmp     r14, 5
0x180020bbf  jb      short loc_180020C23
0x180020bc1  mov     byte ptr [rdi], 61h ; 'a'
0x180020bc4  mov     ebp, 62h ; 'b'
0x180020bc9  call    _errno
0x180020bce  mov     r14d, [rax]
0x180020bd1  call    _errno
0x180020bd6  xor     edx, edx; AccessMode
0x180020bd8  mov     rcx, rbx; FileName
0x180020bdb  mov     dword ptr [rax], 0
0x180020be1  call    _access_s
0x180020be6  test    eax, eax
0x180020be8  jz      short loc_180020BF4
0x180020bea  call    _errno
0x180020bef  cmp     dword ptr [rax], 0Dh
0x180020bf2  jnz     short loc_180020C00
0x180020bf4  cmp     ebp, 7Bh ; '{'
0x180020bf7  jz      short loc_180020C0C
0x180020bf9  mov     [rdi], bpl
0x180020bfc  inc     ebp
0x180020bfe  jmp     short loc_180020BD1
0x180020c00  call    _errno
0x180020c05  mov     [rax], r14d
0x180020c08  xor     eax, eax
0x180020c0a  jmp     short loc_180020C50
0x180020c0c  test    esi, esi
0x180020c0e  jz      short loc_180020C13
0x180020c10  mov     byte ptr [rbx], 0
0x180020c13  call    _errno
0x180020c18  mov     ecx, 11h
0x180020c1d  mov     [rax], ecx
0x180020c1f  mov     eax, ecx
0x180020c21  jmp     short loc_180020C50
0x180020c23  test    esi, esi
0x180020c25  jz      short loc_180020C2A
0x180020c27  mov     byte ptr [rbx], 0
0x180020c2a  call    _errno
0x180020c2f  mov     ebx, 16h
0x180020c34  mov     [rsp+68h+Reserved], 0; Reserved
0x180020c3d  xor     r9d, r9d; LineNo
0x180020c40  xor     r8d, r8d; FileName
0x180020c43  xor     edx, edx; FunctionName
0x180020c45  xor     ecx, ecx; Expression
0x180020c47  mov     [rax], ebx
0x180020c49  call    _invalid_parameter
0x180020c4e  mov     eax, ebx
0x180020c50  add     rsp, 38h
0x180020c54  pop     r15
0x180020c56  pop     r14
0x180020c58  pop     rdi
0x180020c59  pop     rsi
0x180020c5a  pop     rbp
0x180020c5b  pop     rbx
0x180020c5c  retn
```
