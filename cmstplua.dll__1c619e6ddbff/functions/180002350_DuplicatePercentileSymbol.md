# DuplicatePercentileSymbol

- ea: `0x180002350`
- end: `0x18000243c`
- name: `DuplicatePercentileSymbol`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002444`

## callees

- `0x180002350`
- `0x1800026e0`

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
0x180002350  sub     rsp, 618h
0x180002357  mov     rax, cs:__security_cookie
0x18000235e  xor     rax, rsp
0x180002361  mov     [rsp+618h+var_18], rax
0x180002369  mov     r9d, 600h
0x18000236f  mov     r8, rcx
0x180002372  cmp     edx, r9d
0x180002375  ja      loc_180002424
0x18000237b  test    rcx, rcx
0x18000237e  jz      loc_180002424
0x180002384  mov     r10, rcx
0x180002387  lea     eax, [rdx-1]
0x18000238a  mov     byte ptr [rax+rcx], 0
0x18000238e  lea     r11, [rsp+618h+var_618]
0x180002392  xor     ecx, ecx
0x180002394  cmp     [r10], cl
0x180002397  jz      short loc_1800023D1
0x180002399  cmp     r9d, 1
0x18000239d  jbe     short loc_1800023D1
0x18000239f  mov     al, [r10]
0x1800023a2  dec     r9d
0x1800023a5  mov     [r11], al
0x1800023a8  inc     r11
0x1800023ab  cmp     al, 25h ; '%'
0x1800023ad  jnz     short loc_1800023C8
0x1800023af  mov     [r11], al
0x1800023b2  dec     r9d
0x1800023b5  inc     r11
0x1800023b8  cmp     [r10+1], al
0x1800023bc  jnz     short loc_1800023C3
0x1800023be  inc     r10
0x1800023c1  jmp     short loc_1800023C8
0x1800023c3  mov     ecx, 1
0x1800023c8  inc     r10
0x1800023cb  cmp     byte ptr [r10], 0
0x1800023cf  jnz     short loc_180002399
0x1800023d1  mov     byte ptr [r11], 0
0x1800023d5  test    ecx, ecx
0x1800023d7  jz      short loc_180002424
0x1800023d9  mov     ecx, edx
0x1800023db  test    edx, edx
0x1800023dd  jz      short loc_180002424
0x1800023df  cmp     rcx, 7FFFFFFFh
0x1800023e6  ja      short loc_180002420
0x1800023e8  mov     eax, 7FFFFFFEh
0x1800023ed  lea     rdx, [rsp+618h+var_618]
0x1800023f1  test    rax, rax
0x1800023f4  jz      short loc_180002410
0x1800023f6  mov     r9b, [rdx]
0x1800023f9  test    r9b, r9b
0x1800023fc  jz      short loc_180002410
0x1800023fe  mov     [r8], r9b
0x180002401  inc     rdx
0x180002404  inc     r8
0x180002407  dec     rax
0x18000240a  sub     rcx, 1
0x18000240e  jnz     short loc_1800023F1
0x180002410  test    rcx, rcx
0x180002413  lea     rax, [r8-1]
0x180002417  cmovnz  rax, r8
0x18000241b  mov     byte ptr [rax], 0
0x18000241e  jmp     short loc_180002424
0x180002420  mov     byte ptr [r8], 0
0x180002424  mov     rcx, [rsp+618h+var_18]
0x18000242c  xor     rcx, rsp; StackCookie
0x18000242f  call    __security_check_cookie
0x180002434  add     rsp, 618h
0x18000243b  retn
```
