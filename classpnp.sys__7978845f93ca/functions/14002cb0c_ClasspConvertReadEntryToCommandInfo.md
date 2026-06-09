# ClasspConvertReadEntryToCommandInfo

- ea: `0x14002cb0c`
- end: `0x14002ccd5`
- name: `ClasspConvertReadEntryToCommandInfo`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140035128`

## callees

- `0x14002c6c0`
- `0x14002cb0c`
- `0x140030f70`

## pseudocode

```c
__int64 __fastcall ClasspConvertReadEntryToCommandInfo(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // r12d
  unsigned __int8 v5; // r13
  __int64 result; // rax
  __int64 v8; // r15
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // r14d
  __int16 v16[2]; // [rsp+40h] [rbp-10h] BYREF
  __int16 v17; // [rsp+44h] [rbp-Ch] BYREF
  __int16 v18; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+48h]
  char v20; // [rsp+A8h] [rbp+58h] BYREF

  v19 = a2;
  v3 = 0;
  v5 = 0;
  result = 3221225473LL;
  while ( v3 < a2 && v5 < 7u )
  {
    if ( *(_DWORD *)(v3 + a1) != 56 )
      return 3221225485LL;
    v8 = 5LL * v5;
    v9 = *(_DWORD *)(a3 + 20LL * v5 + 16);
    v10 = v9 ^ ((unsigned __int8)v9 ^ (unsigned __int8)(2 * *(_DWORD *)(v3 + a1 + 8))) & 2;
    *(_DWORD *)(a3 + 4 * v8 + 16) = v10;
    v11 = v10 ^ ((unsigned __int8)v10 ^ (unsigned __int8)(2 * *(_DWORD *)(v3 + a1 + 8))) & 4;
    *(_DWORD *)(a3 + 4 * v8 + 16) = v11;
    v12 = v11 ^ ((unsigned __int8)v11 ^ (unsigned __int8)(2 * *(_DWORD *)(v3 + a1 + 8))) & 8;
    *(_DWORD *)(a3 + 4 * v8 + 16) = v12;
    v13 = v12 ^ ((unsigned __int8)v12 ^ (unsigned __int8)(2 * *(_DWORD *)(v3 + a1 + 8))) & 0x10;
    *(_DWORD *)(a3 + 4 * v8 + 16) = v13;
    v14 = v13 ^ ((unsigned __int8)v13 ^ (unsigned __int8)(2 * *(_DWORD *)(v3 + a1 + 8))) & 0x20;
    *(_DWORD *)(a3 + 4 * v8 + 16) = v14;
    v15 = v14 ^ ((unsigned __int8)v14 ^ (unsigned __int8)(2 * *(_DWORD *)(v3 + a1 + 8))) & 0x40;
    *(_DWORD *)(a3 + 4 * v8 + 16) = v15;
    if ( (v15 & 0xE) != 0 )
    {
      v20 = 0;
      v16[0] = 0;
      v17 = 0;
      v15 |= 1u;
      v18 = 0;
      *(_DWORD *)(a3 + 20LL * v5 + 16) = v15;
      result = ClasspConvertCommandLimitDurationToT2Unit(
                 *(_QWORD *)(v3 + a1 + 16),
                 *(_QWORD *)(v3 + a1 + 24),
                 *(_QWORD *)(v3 + a1 + 32),
                 (unsigned int)&v20,
                 (__int64)v16,
                 (__int64)&v17,
                 (__int64)&v18);
      if ( (int)result < 0 )
        return result;
      *(_BYTE *)(a3 + 20LL * v5 + 20) = v20;
      *(_WORD *)(a3 + 20LL * v5 + 24) = v16[0];
      *(_WORD *)(a3 + 20LL * v5 + 26) = v17;
      *(_WORD *)(a3 + 20LL * v5 + 28) = v18;
    }
    if ( (v15 & 0x10) != 0 )
      *(_BYTE *)(a3 + 20LL * v5 + 21) = ClasspGetCommandDurationLimitT2Policy(*(unsigned int *)(v3 + a1 + 40));
    if ( (v15 & 0x20) != 0 )
      *(_BYTE *)(a3 + 20LL * v5 + 22) = ClasspGetCommandDurationLimitT2Policy(*(unsigned int *)(v3 + a1 + 44));
    if ( (v15 & 0x40) != 0 )
      *(_BYTE *)(a3 + 20LL * v5 + 23) = ClasspGetCommandDurationLimitT2Policy(*(unsigned int *)(v3 + a1 + 48));
    if ( v3 + *(_DWORD *)(v3 + a1 + 4) < v3 )
      return 3221225621LL;
    a2 = v19;
    ++v5;
    result = 0;
    v3 += *(_DWORD *)(v3 + a1 + 4);
  }
  return result;
}

```

## disassembly

```asm
0x14002cb0c  mov     [rsp-38h+arg_0], rbx
0x14002cb11  mov     [rsp-38h+arg_8], edx
0x14002cb15  push    rbp
0x14002cb16  push    rsi
0x14002cb17  push    rdi
0x14002cb18  push    r12
0x14002cb1a  push    r13
0x14002cb1c  push    r14
0x14002cb1e  push    r15
0x14002cb20  mov     rbp, rsp
0x14002cb23  sub     rsp, 50h
0x14002cb27  xor     r12d, r12d
0x14002cb2a  mov     rbx, r8
0x14002cb2d  xor     r13b, r13b
0x14002cb30  mov     rsi, rcx
0x14002cb33  mov     eax, 0C0000001h
0x14002cb38  cmp     r12d, edx
0x14002cb3b  jnb     loc_14002CCBC
0x14002cb41  cmp     r13b, 7
0x14002cb45  jnb     loc_14002CCBC
0x14002cb4b  mov     edi, r12d
0x14002cb4e  cmp     dword ptr [rdi+rsi], 38h ; '8'
0x14002cb52  jnz     loc_14002CCB7
0x14002cb58  mov     ecx, [rdi+rsi+8]
0x14002cb5c  add     ecx, ecx
0x14002cb5e  movzx   eax, r13b
0x14002cb62  lea     r15, [rax+rax*4]
0x14002cb66  mov     eax, [rbx+r15*4+10h]
0x14002cb6b  xor     ecx, eax
0x14002cb6d  and     ecx, 2
0x14002cb70  xor     ecx, eax
0x14002cb72  mov     [rbx+r15*4+10h], ecx
0x14002cb77  mov     eax, [rdi+rsi+8]
0x14002cb7b  add     eax, eax
0x14002cb7d  xor     eax, ecx
0x14002cb7f  and     eax, 4
0x14002cb82  xor     eax, ecx
0x14002cb84  mov     [rbx+r15*4+10h], eax
0x14002cb89  mov     ecx, [rdi+rsi+8]
0x14002cb8d  add     ecx, ecx
0x14002cb8f  xor     ecx, eax
0x14002cb91  and     ecx, 8
0x14002cb94  xor     ecx, eax
0x14002cb96  mov     [rbx+r15*4+10h], ecx
0x14002cb9b  mov     eax, [rdi+rsi+8]
0x14002cb9f  add     eax, eax
0x14002cba1  xor     eax, ecx
0x14002cba3  and     eax, 10h
0x14002cba6  xor     eax, ecx
0x14002cba8  mov     [rbx+r15*4+10h], eax
0x14002cbad  mov     ecx, [rdi+rsi+8]
0x14002cbb1  add     ecx, ecx
0x14002cbb3  xor     ecx, eax
0x14002cbb5  and     ecx, 20h
0x14002cbb8  xor     ecx, eax
0x14002cbba  mov     [rbx+r15*4+10h], ecx
0x14002cbbf  mov     r14d, [rdi+rsi+8]
0x14002cbc4  add     r14d, r14d
0x14002cbc7  xor     r14d, ecx
0x14002cbca  and     r14d, 40h
0x14002cbce  xor     r14d, ecx
0x14002cbd1  mov     [rbx+r15*4+10h], r14d
0x14002cbd6  test    r14b, 0Eh
0x14002cbda  jz      short loc_14002CC58
0x14002cbdc  xor     eax, eax
0x14002cbde  mov     [rbp+arg_18], 0
0x14002cbe2  mov     [rbp+var_10], ax
0x14002cbe6  lea     r9, [rbp+arg_18]
0x14002cbea  mov     [rbp+var_C], ax
0x14002cbee  or      r14d, 1
0x14002cbf2  mov     [rbp+var_8], ax
0x14002cbf6  lea     rax, [rbp+var_8]
0x14002cbfa  mov     [rsp+50h+var_20], rax
0x14002cbff  lea     rax, [rbp+var_C]
0x14002cc03  mov     [rsp+50h+var_28], rax
0x14002cc08  lea     rax, [rbp+var_10]
0x14002cc0c  mov     [rbx+r15*4+10h], r14d
0x14002cc11  mov     r8, [rdi+rsi+20h]
0x14002cc16  mov     rdx, [rdi+rsi+18h]
0x14002cc1b  mov     rcx, [rdi+rsi+10h]
0x14002cc20  mov     [rsp+50h+var_30], rax
0x14002cc25  call    ClasspConvertCommandLimitDurationToT2Unit
0x14002cc2a  test    eax, eax
0x14002cc2c  js      loc_14002CCBC
0x14002cc32  mov     al, [rbp+arg_18]
0x14002cc35  mov     [rbx+r15*4+14h], al
0x14002cc3a  movzx   eax, [rbp+var_10]
0x14002cc3e  mov     [rbx+r15*4+18h], ax
0x14002cc44  movzx   eax, [rbp+var_C]
0x14002cc48  mov     [rbx+r15*4+1Ah], ax
0x14002cc4e  movzx   eax, [rbp+var_8]
0x14002cc52  mov     [rbx+r15*4+1Ch], ax
0x14002cc58  test    r14b, 10h
0x14002cc5c  jz      short loc_14002CC6C
0x14002cc5e  mov     ecx, [rdi+rsi+28h]
0x14002cc62  call    ClasspGetCommandDurationLimitT2Policy
0x14002cc67  mov     [rbx+r15*4+15h], al
0x14002cc6c  test    r14b, 20h
0x14002cc70  jz      short loc_14002CC80
0x14002cc72  mov     ecx, [rdi+rsi+2Ch]
0x14002cc76  call    ClasspGetCommandDurationLimitT2Policy
0x14002cc7b  mov     [rbx+r15*4+16h], al
0x14002cc80  test    r14b, 40h
0x14002cc84  jz      short loc_14002CC94
0x14002cc86  mov     ecx, [rdi+rsi+30h]
0x14002cc8a  call    ClasspGetCommandDurationLimitT2Policy
0x14002cc8f  mov     [rbx+r15*4+17h], al
0x14002cc94  mov     ecx, [rdi+rsi+4]
0x14002cc98  add     ecx, r12d
0x14002cc9b  cmp     ecx, r12d
0x14002cc9e  jb      short loc_14002CCB0
0x14002cca0  mov     edx, [rbp+arg_8]
0x14002cca3  inc     r13b
0x14002cca6  xor     eax, eax
0x14002cca8  mov     r12d, ecx
0x14002ccab  jmp     loc_14002CB38
0x14002ccb0  mov     eax, 0C0000095h
0x14002ccb5  jmp     short loc_14002CCBC
0x14002ccb7  mov     eax, 0C000000Dh
0x14002ccbc  mov     rbx, [rsp+50h+arg_0]
0x14002ccc4  add     rsp, 50h
0x14002ccc8  pop     r15
0x14002ccca  pop     r14
0x14002cccc  pop     r13
0x14002ccce  pop     r12
0x14002ccd0  pop     rdi
0x14002ccd1  pop     rsi
0x14002ccd2  pop     rbp
0x14002ccd3  retn
```
