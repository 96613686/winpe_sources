# DuplicatePercentileSymbol

- ea: `0x180004c60`
- end: `0x180004d4c`
- name: `DuplicatePercentileSymbol`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d54`
- `0x180004e1c`

## callees

- `0x180004c60`
- `0x1800054b0`

## pseudocode

```c
void __fastcall DuplicatePercentileSymbol(_BYTE *a1, unsigned int a2)
{
  unsigned int v2; // r9d
  _BYTE *v3; // r8
  char *v4; // r10
  char *v5; // r11
  int i; // ecx
  char v7; // al
  __int64 v8; // rcx
  __int64 v9; // rax
  _BYTE *v10; // rdx
  _BYTE *v11; // rax
  _BYTE v12[1536]; // [rsp+0h] [rbp-618h] BYREF

  v2 = 1536;
  v3 = a1;
  if ( a2 <= 0x600 && a1 )
  {
    v4 = a1;
    a1[a2 - 1] = 0;
    v5 = v12;
    for ( i = 0; *v4; ++v4 )
    {
      if ( v2 <= 1 )
        break;
      v7 = *v4;
      --v2;
      *v5++ = *v4;
      if ( v7 == 37 )
      {
        *v5 = 37;
        --v2;
        ++v5;
        if ( v4[1] == 37 )
          ++v4;
        else
          i = 1;
      }
    }
    *v5 = 0;
    if ( i )
    {
      v8 = a2;
      if ( a2 )
      {
        if ( a2 > 0x7FFFFFFFuLL )
        {
          *v3 = 0;
        }
        else
        {
          v9 = 2147483646;
          v10 = v12;
          do
          {
            if ( !v9 )
              break;
            if ( !*v10 )
              break;
            *v3++ = *v10++;
            --v9;
            --v8;
          }
          while ( v8 );
          v11 = v3 - 1;
          if ( v8 )
            v11 = v3;
          *v11 = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180004c60  sub     rsp, 618h
0x180004c67  mov     rax, cs:__security_cookie
0x180004c6e  xor     rax, rsp
0x180004c71  mov     [rsp+618h+var_18], rax
0x180004c79  mov     r9d, 600h
0x180004c7f  mov     r8, rcx
0x180004c82  cmp     edx, r9d
0x180004c85  ja      loc_180004D34
0x180004c8b  test    rcx, rcx
0x180004c8e  jz      loc_180004D34
0x180004c94  mov     r10, rcx
0x180004c97  lea     eax, [rdx-1]
0x180004c9a  mov     byte ptr [rax+rcx], 0
0x180004c9e  lea     r11, [rsp+618h+var_618]
0x180004ca2  xor     ecx, ecx
0x180004ca4  cmp     [r10], cl
0x180004ca7  jz      short loc_180004CE1
0x180004ca9  cmp     r9d, 1
0x180004cad  jbe     short loc_180004CE1
0x180004caf  mov     al, [r10]
0x180004cb2  dec     r9d
0x180004cb5  mov     [r11], al
0x180004cb8  inc     r11
0x180004cbb  cmp     al, 25h ; '%'
0x180004cbd  jnz     short loc_180004CD8
0x180004cbf  mov     [r11], al
0x180004cc2  dec     r9d
0x180004cc5  inc     r11
0x180004cc8  cmp     [r10+1], al
0x180004ccc  jnz     short loc_180004CD3
0x180004cce  inc     r10
0x180004cd1  jmp     short loc_180004CD8
0x180004cd3  mov     ecx, 1
0x180004cd8  inc     r10
0x180004cdb  cmp     byte ptr [r10], 0
0x180004cdf  jnz     short loc_180004CA9
0x180004ce1  mov     byte ptr [r11], 0
0x180004ce5  test    ecx, ecx
0x180004ce7  jz      short loc_180004D34
0x180004ce9  mov     ecx, edx
0x180004ceb  test    edx, edx
0x180004ced  jz      short loc_180004D34
0x180004cef  cmp     rcx, 7FFFFFFFh
0x180004cf6  ja      short loc_180004D30
0x180004cf8  mov     eax, 7FFFFFFEh
0x180004cfd  lea     rdx, [rsp+618h+var_618]
0x180004d01  test    rax, rax
0x180004d04  jz      short loc_180004D20
0x180004d06  mov     r9b, [rdx]
0x180004d09  test    r9b, r9b
0x180004d0c  jz      short loc_180004D20
0x180004d0e  mov     [r8], r9b
0x180004d11  inc     rdx
0x180004d14  inc     r8
0x180004d17  dec     rax
0x180004d1a  sub     rcx, 1
0x180004d1e  jnz     short loc_180004D01
0x180004d20  test    rcx, rcx
0x180004d23  lea     rax, [r8-1]
0x180004d27  cmovnz  rax, r8
0x180004d2b  mov     byte ptr [rax], 0
0x180004d2e  jmp     short loc_180004D34
0x180004d30  mov     byte ptr [r8], 0
0x180004d34  mov     rcx, [rsp+618h+var_18]
0x180004d3c  xor     rcx, rsp; StackCookie
0x180004d3f  call    __security_check_cookie
0x180004d44  add     rsp, 618h
0x180004d4b  retn
```
