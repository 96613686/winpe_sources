# CreateStorageRequestBlock

- ea: `0x14000f250`
- end: `0x14000f3cd`
- name: `CreateStorageRequestBlock`
- size: `381`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000eee0`
- `0x14005b8b8`

## callees

- `0x14000f250`
- `0x14000f410`
- `0x14003e470`

## pseudocode

```c
__int64 __fastcall CreateStorageRequestBlock(
        __int64 *a1,
        __int16 a2,
        __int64 (__fastcall *a3)(_QWORD, __int64, int *),
        unsigned int *a4,
        unsigned int a5,
        char a6)
{
  unsigned int v9; // edi
  unsigned int v10; // ebx
  int *v11; // r8
  __int64 i; // rdx
  __int64 v13; // rax
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx

  v9 = 0;
  v10 = 128;
  if ( a2 )
  {
    if ( a2 == 1 )
      v10 = 4 * a5 + 128;
    else
      v9 = -1073741811;
  }
  else if ( a5 )
  {
    v10 = 4 * a5 + 124;
  }
  if ( (v10 & 7) != 0 )
    v10 += 8 - (v10 & 7);
  if ( !v9 )
  {
    v10 += 16;
    if ( a2 == 1 )
      v10 += 112;
  }
  v11 = (int *)&a6;
  for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
  {
    if ( v9 )
      return v9;
    v15 = *v11;
    v11 += 2;
    if ( v15 == 64 )
    {
      v10 += 40;
    }
    else if ( v15 == 128 )
    {
      v10 += 32;
    }
    else
    {
      if ( v15 > 65 )
      {
        v16 = v15 - 66;
        if ( !v16 )
        {
          v11 += 2;
          v10 += *(v11 - 2) + 40;
          continue;
        }
        v17 = v16 - 30;
        if ( v17 && (unsigned int)(v17 - 1) >= 2 )
        {
LABEL_44:
          v9 = -1073741811;
          continue;
        }
      }
      else
      {
        if ( v15 == 65 )
        {
          v10 += 56;
          continue;
        }
        if ( v15 != 1 )
        {
          if ( v15 == -536870912 )
          {
            v11 += 2;
            v10 += *(v11 - 2);
            continue;
          }
          if ( v15 == -268435456 || v15 != -268435455 && v15 != -268435454 )
            goto LABEL_44;
        }
      }
      v10 += 24;
    }
  }
  if ( v9 )
    return v9;
  if ( a3 )
  {
    v13 = a3(v10, i, v11);
    *a1 = v13;
    if ( !v13 )
      v9 = -1073741670;
  }
  if ( a4 )
    *a4 = v10;
  if ( !*a1 )
    return v9;
  else
    return pInitializeStorageRequestBlock(*a1);
}

```

## disassembly

```asm
0x14000f250  push    rbx
0x14000f252  push    rbp
0x14000f253  push    rsi
0x14000f254  push    rdi
0x14000f255  push    r14
0x14000f257  sub     rsp, 40h
0x14000f25b  xor     r11d, r11d
0x14000f25e  mov     rsi, r9
0x14000f261  mov     r9d, [rsp+68h+arg_20]
0x14000f269  mov     r10, r8
0x14000f26c  movzx   ebp, dx
0x14000f26f  mov     r14, rcx
0x14000f272  mov     edi, r11d
0x14000f275  mov     ebx, 80h
0x14000f27a  test    dx, dx
0x14000f27d  jnz     loc_14000F35F
0x14000f283  test    r9d, r9d
0x14000f286  jz      short loc_14000F290
0x14000f288  lea     ebx, ds:7Ch[r9*4]
0x14000f290  mov     ecx, ebx
0x14000f292  and     ecx, 7
0x14000f295  jz      short loc_14000F2A0
0x14000f297  mov     eax, 8
0x14000f29c  sub     eax, ecx
0x14000f29e  add     ebx, eax
0x14000f2a0  test    edi, edi
0x14000f2a2  jnz     short loc_14000F2B1
0x14000f2a4  add     ebx, 10h
0x14000f2a7  cmp     bp, 1
0x14000f2ab  jz      loc_14000F376
0x14000f2b1  lea     r8, [rsp+68h+arg_28]
0x14000f2b9  mov     edx, r11d
0x14000f2bc  test    r9d, r9d
0x14000f2bf  jnz     short loc_14000F321
0x14000f2c1  test    edi, edi
0x14000f2c3  jnz     loc_14000F34A
0x14000f2c9  test    r10, r10
0x14000f2cc  jz      short loc_14000F2EE
0x14000f2ce  mov     ecx, ebx
0x14000f2d0  mov     rax, r10
0x14000f2d3  call    _guard_dispatch_icall
0x14000f2d8  mov     r9d, [rsp+68h+arg_20]
0x14000f2e0  test    rax, rax
0x14000f2e3  mov     ecx, 0C000009Ah
0x14000f2e8  mov     [r14], rax
0x14000f2eb  cmovz   edi, ecx
0x14000f2ee  test    rsi, rsi
0x14000f2f1  jz      short loc_14000F2F5
0x14000f2f3  mov     [rsi], ebx
0x14000f2f5  mov     rcx, [r14]
0x14000f2f8  test    rcx, rcx
0x14000f2fb  jz      short loc_14000F34A
0x14000f2fd  lea     rax, [rsp+68h+arg_28]
0x14000f305  mov     r8d, ebx
0x14000f308  movzx   edx, bp
0x14000f30b  mov     [rsp+68h+var_48], rax
0x14000f310  call    pInitializeStorageRequestBlock
0x14000f315  add     rsp, 40h
0x14000f319  pop     r14
0x14000f31b  pop     rdi
0x14000f31c  pop     rsi
0x14000f31d  pop     rbp
0x14000f31e  pop     rbx
0x14000f31f  retn
0x14000f321  test    edi, edi
0x14000f323  jnz     short loc_14000F34A
0x14000f325  mov     ecx, [r8]
0x14000f328  add     r8, 8
0x14000f32c  cmp     ecx, 40h ; '@'
0x14000f32f  jnz     short loc_14000F33D
0x14000f331  add     ebx, 28h ; '('
0x14000f334  inc     edx
0x14000f336  cmp     edx, r9d
0x14000f339  jb      short loc_14000F321
0x14000f33b  jmp     short loc_14000F2C1
0x14000f33d  cmp     ecx, 80h
0x14000f343  jnz     short loc_14000F34E
0x14000f345  add     ebx, 20h ; ' '
0x14000f348  jmp     short loc_14000F334
0x14000f34a  mov     eax, edi
0x14000f34c  jmp     short loc_14000F315
0x14000f34e  cmp     ecx, 41h ; 'A'
0x14000f351  jg      short loc_14000F3B0
0x14000f353  jz      short loc_14000F3AB
0x14000f355  cmp     ecx, 1
0x14000f358  jnz     short loc_14000F37E
0x14000f35a  add     ebx, 18h
0x14000f35d  jmp     short loc_14000F334
0x14000f35f  cmp     bp, 1
0x14000f363  jnz     loc_14003FAEC
0x14000f369  lea     ebx, ds:80h[r9*4]
0x14000f371  jmp     loc_14000F290
0x14000f376  add     ebx, 70h ; 'p'
0x14000f379  jmp     loc_14000F2B1
0x14000f37e  cmp     ecx, 0E0000000h
0x14000f384  jz      loc_14003FAF6
0x14000f38a  cmp     ecx, 0F0000000h
0x14000f390  jz      loc_14003FB03
0x14000f396  cmp     ecx, 0F0000001h
0x14000f39c  jz      short loc_14000F35A
0x14000f39e  cmp     ecx, 0F0000002h
0x14000f3a4  jz      short loc_14000F35A
0x14000f3a6  jmp     loc_14003FB03
0x14000f3ab  add     ebx, 38h ; '8'
0x14000f3ae  jmp     short loc_14000F334
0x14000f3b0  sub     ecx, 42h ; 'B'
0x14000f3b3  jz      loc_14003FB0D
0x14000f3b9  sub     ecx, 1Eh
0x14000f3bc  jz      short loc_14000F35A
0x14000f3be  sub     ecx, 1
0x14000f3c1  jz      short loc_14000F35A
0x14000f3c3  cmp     ecx, 1
0x14000f3c6  jz      short loc_14000F35A
0x14000f3c8  jmp     loc_14003FB03
0x14003faec  mov     edi, 0C000000Dh
0x14003faf1  jmp     loc_14000F290
0x14003faf6  add     r8, 8
0x14003fafa  add     ebx, [r8-8]
0x14003fafe  jmp     loc_14000F334
0x14003fb03  mov     edi, 0C000000Dh
0x14003fb08  jmp     loc_14000F334
0x14003fb0d  add     r8, 8
0x14003fb11  add     ebx, 28h ; '('
0x14003fb14  add     ebx, [r8-8]
0x14003fb18  jmp     loc_14000F334
```
