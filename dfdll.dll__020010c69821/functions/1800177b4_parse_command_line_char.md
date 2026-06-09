# parse_command_line_char_

- ea: `0x1800177b4`
- end: `0x180017970`
- name: `parse_command_line_char_`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800179d4`

## callees

- `0x1800177b4`
- `0x18001a708`

## pseudocode

```c
char __fastcall parse_command_line_char_(char *a1, _QWORD *a2, _BYTE *a3, _QWORD *a4, _QWORD *a5)
{
  _UNKNOWN **v5; // rax
  _BYTE *v7; // rdi
  _QWORD *v8; // r14
  bool v10; // bp
  unsigned int v11; // esi
  bool v12; // si
  int v13; // edx
  unsigned int v14; // eax
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h] BYREF

  v5 = &retaddr;
  v7 = a3;
  v8 = a2;
  *a5 = 0;
  *a4 = 1;
  if ( a2 )
  {
    *a2 = a3;
    v8 = a2 + 1;
  }
  v10 = 0;
  do
  {
    if ( *a1 == 34 )
    {
      LOBYTE(v11) = 34;
      v10 = !v10;
      ++a1;
    }
    else
    {
      ++*a5;
      if ( v7 )
        *v7++ = *a1;
      v11 = *a1++;
      LODWORD(v5) = ismbblead(v11);
      if ( (_DWORD)v5 )
      {
        ++*a5;
        if ( v7 )
        {
          LOBYTE(v5) = *a1;
          *v7++ = *a1;
        }
        ++a1;
      }
      if ( !(_BYTE)v11 )
      {
        --a1;
        goto LABEL_19;
      }
    }
  }
  while ( v10 || (_BYTE)v11 != 32 && (_BYTE)v11 != 9 );
  if ( v7 )
    *(v7 - 1) = 0;
LABEL_19:
  v12 = 0;
  while ( *a1 )
  {
    while ( *a1 == 32 || *a1 == 9 )
      ++a1;
    if ( !*a1 )
      break;
    if ( v8 )
      *v8++ = v7;
    ++*a4;
    while ( 1 )
    {
      v13 = 1;
      v14 = 0;
      while ( *a1 == 92 )
      {
        ++a1;
        ++v14;
      }
      if ( *a1 == 34 )
      {
        if ( (v14 & 1) == 0 )
        {
          if ( v12 && a1[1] == 34 )
          {
            ++a1;
          }
          else
          {
            v13 = 0;
            v12 = !v12;
          }
        }
        v14 >>= 1;
      }
      while ( v14 )
      {
        --v14;
        if ( v7 )
          *v7++ = 92;
        ++*a5;
      }
      LOBYTE(v5) = *a1;
      if ( !*a1 || !v12 && ((_BYTE)v5 == 32 || (_BYTE)v5 == 9) )
        break;
      if ( v13 )
      {
        if ( v7 )
          *v7++ = (_BYTE)v5;
        if ( ismbblead(*a1) )
        {
          ++*a5;
          ++a1;
          if ( v7 )
            *v7++ = *a1;
        }
        ++*a5;
      }
      ++a1;
    }
    if ( v7 )
      *v7++ = 0;
    ++*a5;
  }
  if ( v8 )
    *v8 = 0;
  ++*a4;
  return (char)v5;
}

```

## disassembly

```asm
0x1800177b4  mov     rax, rsp
0x1800177b7  mov     [rax+8], rbx
0x1800177bb  mov     [rax+10h], rbp
0x1800177bf  mov     [rax+18h], rsi
0x1800177c3  mov     [rax+20h], rdi
0x1800177c7  push    r12
0x1800177c9  push    r14
0x1800177cb  push    r15
0x1800177cd  sub     rsp, 20h
0x1800177d1  mov     r15, [rsp+38h+arg_20]
0x1800177d6  mov     r12, r9
0x1800177d9  mov     rdi, r8
0x1800177dc  mov     r14, rdx
0x1800177df  mov     rbx, rcx
0x1800177e2  and     qword ptr [r15], 0
0x1800177e6  mov     qword ptr [r9], 1
0x1800177ed  test    rdx, rdx
0x1800177f0  jz      short loc_1800177F9
0x1800177f2  mov     [rdx], r8
0x1800177f5  add     r14, 8
0x1800177f9  xor     bpl, bpl
0x1800177fc  cmp     byte ptr [rbx], 22h ; '"'
0x1800177ff  jnz     short loc_180017810
0x180017801  test    bpl, bpl
0x180017804  mov     sil, 22h ; '"'
0x180017807  setz    bpl
0x18001780b  inc     rbx
0x18001780e  jmp     short loc_180017847
0x180017810  inc     qword ptr [r15]
0x180017813  test    rdi, rdi
0x180017816  jz      short loc_18001781F
0x180017818  mov     al, [rbx]
0x18001781a  mov     [rdi], al
0x18001781c  inc     rdi
0x18001781f  movsx   esi, byte ptr [rbx]
0x180017822  inc     rbx
0x180017825  mov     ecx, esi; Ch
0x180017827  call    _ismbblead
0x18001782c  test    eax, eax
0x18001782e  jz      short loc_180017842
0x180017830  inc     qword ptr [r15]
0x180017833  test    rdi, rdi
0x180017836  jz      short loc_18001783F
0x180017838  mov     al, [rbx]
0x18001783a  mov     [rdi], al
0x18001783c  inc     rdi
0x18001783f  inc     rbx
0x180017842  test    sil, sil
0x180017845  jz      short loc_180017863
0x180017847  test    bpl, bpl
0x18001784a  jnz     short loc_1800177FC
0x18001784c  cmp     sil, 20h ; ' '
0x180017850  jz      short loc_180017858
0x180017852  cmp     sil, 9
0x180017856  jnz     short loc_1800177FC
0x180017858  test    rdi, rdi
0x18001785b  jz      short loc_180017866
0x18001785d  mov     byte ptr [rdi-1], 0
0x180017861  jmp     short loc_180017866
0x180017863  dec     rbx
0x180017866  xor     sil, sil
0x180017869  cmp     byte ptr [rbx], 0
0x18001786c  jz      loc_180017944
0x180017872  cmp     byte ptr [rbx], 20h ; ' '
0x180017875  jz      short loc_18001787C
0x180017877  cmp     byte ptr [rbx], 9
0x18001787a  jnz     short loc_180017881
0x18001787c  inc     rbx
0x18001787f  jmp     short loc_180017872
0x180017881  cmp     byte ptr [rbx], 0
0x180017884  jz      loc_180017944
0x18001788a  test    r14, r14
0x18001788d  jz      short loc_180017896
0x18001788f  mov     [r14], rdi
0x180017892  add     r14, 8
0x180017896  inc     qword ptr [r12]
0x18001789a  mov     edx, 1
0x18001789f  xor     eax, eax
0x1800178a1  jmp     short loc_1800178A8
0x1800178a3  inc     rbx
0x1800178a6  inc     eax
0x1800178a8  cmp     byte ptr [rbx], 5Ch ; '\'
0x1800178ab  jz      short loc_1800178A3
0x1800178ad  cmp     byte ptr [rbx], 22h ; '"'
0x1800178b0  jnz     short loc_1800178E3
0x1800178b2  test    dl, al
0x1800178b4  jnz     short loc_1800178CF
0x1800178b6  test    sil, sil
0x1800178b9  jz      short loc_1800178C6
0x1800178bb  cmp     byte ptr [rbx+1], 22h ; '"'
0x1800178bf  jnz     short loc_1800178C6
0x1800178c1  inc     rbx
0x1800178c4  jmp     short loc_1800178CF
0x1800178c6  xor     edx, edx
0x1800178c8  test    sil, sil
0x1800178cb  setz    sil
0x1800178cf  shr     eax, 1
0x1800178d1  jmp     short loc_1800178E3
0x1800178d3  dec     eax
0x1800178d5  test    rdi, rdi
0x1800178d8  jz      short loc_1800178E0
0x1800178da  mov     byte ptr [rdi], 5Ch ; '\'
0x1800178dd  inc     rdi
0x1800178e0  inc     qword ptr [r15]
0x1800178e3  test    eax, eax
0x1800178e5  jnz     short loc_1800178D3
0x1800178e7  mov     al, [rbx]
0x1800178e9  test    al, al
0x1800178eb  jz      short loc_180017931
0x1800178ed  test    sil, sil
0x1800178f0  jnz     short loc_1800178FA
0x1800178f2  cmp     al, 20h ; ' '
0x1800178f4  jz      short loc_180017931
0x1800178f6  cmp     al, 9
0x1800178f8  jz      short loc_180017931
0x1800178fa  test    edx, edx
0x1800178fc  jz      short loc_180017929
0x1800178fe  test    rdi, rdi
0x180017901  jz      short loc_180017908
0x180017903  mov     [rdi], al
0x180017905  inc     rdi
0x180017908  movsx   ecx, byte ptr [rbx]; Ch
0x18001790b  call    _ismbblead
0x180017910  test    eax, eax
0x180017912  jz      short loc_180017926
0x180017914  inc     qword ptr [r15]
0x180017917  inc     rbx
0x18001791a  test    rdi, rdi
0x18001791d  jz      short loc_180017926
0x18001791f  mov     al, [rbx]
0x180017921  mov     [rdi], al
0x180017923  inc     rdi
0x180017926  inc     qword ptr [r15]
0x180017929  inc     rbx
0x18001792c  jmp     loc_18001789A
0x180017931  test    rdi, rdi
0x180017934  jz      short loc_18001793C
0x180017936  mov     byte ptr [rdi], 0
0x180017939  inc     rdi
0x18001793c  inc     qword ptr [r15]
0x18001793f  jmp     loc_180017869
0x180017944  test    r14, r14
0x180017947  jz      short loc_18001794D
0x180017949  and     qword ptr [r14], 0
0x18001794d  inc     qword ptr [r12]
0x180017951  mov     rbx, [rsp+38h+arg_0]
0x180017956  mov     rbp, [rsp+38h+arg_8]
0x18001795b  mov     rsi, [rsp+38h+arg_10]
0x180017960  mov     rdi, [rsp+38h+arg_18]
0x180017965  add     rsp, 20h
0x180017969  pop     r15
0x18001796b  pop     r14
0x18001796d  pop     r12
0x18001796f  retn
```
