# split_block

- ea: `0x18000f2a8`
- end: `0x18000f503`
- name: `split_block`
- size: `603`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800111c0`
- `0x180014568`

## callees

- `0x18000f2a8`
- `0x18000fe40`
- `0x180014dc0`

## pseudocode

```c
__int64 __fastcall split_block(__int64 a1, __int64 a2, unsigned int a3, int a4, unsigned int *a5, _DWORD *a6)
{
  unsigned __int8 v8; // bp
  unsigned int v9; // r9d
  __int16 v10; // r11
  __int64 i; // rdx
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // r13d
  unsigned int v16; // r12d
  unsigned int v17; // esi
  unsigned int v18; // r15d
  unsigned int v19; // r14d
  unsigned int v20; // ebx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // [rsp+34h] [rbp-884h]
  _WORD v24[1032]; // [rsp+50h] [rbp-868h]

  *a5 = a3;
  if ( a6 )
    *a6 = a4;
  if ( a3 >= 0x1800 )
  {
    v8 = *(_BYTE *)(a1 + 2224);
    if ( v8 < 4u )
    {
      v9 = 0;
      v10 = 0;
      for ( i = 0; (unsigned int)i < a3 >> 3; i = (unsigned int)(i + 1) )
      {
        if ( (i & 7) == 0 )
        {
          if ( v9 >= 0x408 )
            return 0;
          v12 = (int)v9++;
          v24[v12] = v10;
        }
        v10 += *(unsigned __int8 *)(*(unsigned __int8 *)(i + *(_QWORD *)(a1 + 80)) + a1 + 2225);
      }
      v13 = a3 - 4096;
      v14 = 2048;
      v23 = a3 - 4096;
      while ( v14 < v13 )
      {
        v15 = v14 + 1024;
        if ( (unsigned int)return_difference(
                             a1,
                             v14,
                             v14 + 1024,
                             (unsigned __int16)v24[(unsigned __int64)v14 >> 6],
                             (unsigned __int16)v24[(unsigned __int64)(v14 + 1024) >> 6]) > 0x578
          && (unsigned int)return_difference(
                             a1,
                             v14 - 1024,
                             v14 + 2048,
                             (unsigned __int16)v24[(unsigned __int64)(v14 - 1024) >> 6],
                             (unsigned __int16)v24[(unsigned __int64)(v14 + 2048) >> 6]) > 0x578
          && (unsigned int)return_difference(
                             a1,
                             v14 - 2048,
                             v14 + 3072,
                             (unsigned __int16)v24[(unsigned __int64)(v14 - 2048) >> 6],
                             (unsigned __int16)v24[(unsigned __int64)(v14 + 3072) >> 6]) > 0x578 )
        {
          v16 = 0;
          v17 = 0;
          v18 = v14 + 512;
          if ( v14 + 512 < v14 + 2560 )
          {
            v19 = v14 + 2560;
            do
            {
              v20 = v16;
              v21 = return_difference(
                      a1,
                      v18 - 1024,
                      v18,
                      (unsigned __int16)v24[(unsigned __int64)(v18 - 1024) >> 6],
                      (unsigned __int16)v24[(unsigned __int64)v18 >> 6]);
              v22 = v18;
              if ( v21 > v16 )
                v16 = v21;
              if ( v21 <= v20 )
                v22 = v17;
              v18 += 64;
              v17 = v22;
            }
            while ( v18 < v19 );
            if ( v16 >= 0x6A4 && v22 >= 0x1000 )
            {
              *(_BYTE *)(a1 + 2224) = v8 + 1;
              *a5 = v22;
              if ( a6 )
                *a6 = (unsigned __int16)v24[(unsigned __int64)v22 >> 6];
              return 1;
            }
          }
        }
        v13 = v23;
        v14 = v15;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f2a8  push    rbx
0x18000f2aa  push    rbp
0x18000f2ab  push    rsi
0x18000f2ac  push    rdi
0x18000f2ad  push    r12
0x18000f2af  push    r13
0x18000f2b1  push    r14
0x18000f2b3  push    r15
0x18000f2b5  sub     rsp, 878h
0x18000f2bc  mov     rax, cs:__security_cookie
0x18000f2c3  xor     rax, rsp
0x18000f2c6  mov     [rsp+8B8h+var_58], rax
0x18000f2ce  mov     rax, [rsp+8B8h+arg_20]
0x18000f2d6  mov     rdi, rcx
0x18000f2d9  mov     r14, [rsp+8B8h+arg_28]
0x18000f2e1  mov     [rsp+8B8h+var_878], rax
0x18000f2e6  mov     [rsp+8B8h+var_880], r14
0x18000f2eb  mov     [rax], r8d
0x18000f2ee  test    r14, r14
0x18000f2f1  jnz     loc_18000F3D2
0x18000f2f7  cmp     r8d, 1800h
0x18000f2fe  jnb     short loc_18000F326
0x18000f300  xor     eax, eax
0x18000f302  mov     rcx, [rsp+8B8h+var_58]
0x18000f30a  xor     rcx, rsp; StackCookie
0x18000f30d  call    __security_check_cookie
0x18000f312  add     rsp, 878h
0x18000f319  pop     r15
0x18000f31b  pop     r14
0x18000f31d  pop     r13
0x18000f31f  pop     r12
0x18000f321  pop     rdi
0x18000f322  pop     rsi
0x18000f323  pop     rbp
0x18000f324  pop     rbx
0x18000f325  retn
0x18000f326  mov     bpl, [rcx+8B0h]
0x18000f32d  cmp     bpl, 4
0x18000f331  jnb     short loc_18000F300
0x18000f333  xor     r9d, r9d
0x18000f336  xor     r11d, r11d
0x18000f339  xor     edx, edx
0x18000f33b  mov     r10d, r8d
0x18000f33e  shr     r10d, 3
0x18000f342  cmp     edx, r10d
0x18000f345  jnb     short loc_18000F37A
0x18000f347  test    dl, 7
0x18000f34a  jz      short loc_18000F363
0x18000f34c  mov     rax, [rdi+50h]
0x18000f350  movzx   ecx, byte ptr [rdx+rax]
0x18000f354  movzx   eax, byte ptr [rcx+rdi+8B1h]
0x18000f35c  add     r11d, eax
0x18000f35f  inc     edx
0x18000f361  jmp     short loc_18000F342
0x18000f363  cmp     r9d, 408h
0x18000f36a  jnb     short loc_18000F300
0x18000f36c  movsxd  rax, r9d
0x18000f36f  inc     r9d
0x18000f372  mov     [rsp+rax*2+8B8h+var_868], r11w
0x18000f378  jmp     short loc_18000F34C
0x18000f37a  lea     eax, [r8-1000h]
0x18000f381  mov     ebx, 800h
0x18000f386  mov     [rsp+8B8h+var_884], eax
0x18000f38a  cmp     ebx, eax
0x18000f38c  jnb     loc_18000F300
0x18000f392  lea     r13d, [rbx+400h]
0x18000f399  mov     edx, ebx
0x18000f39b  mov     eax, r13d
0x18000f39e  mov     r8d, r13d
0x18000f3a1  shr     rax, 6
0x18000f3a5  movzx   ecx, [rsp+rax*2+8B8h+var_868]
0x18000f3aa  mov     [rsp+8B8h+var_898], ecx
0x18000f3ae  mov     rcx, rdi
0x18000f3b1  mov     eax, ebx
0x18000f3b3  shr     rax, 6
0x18000f3b7  movzx   r9d, [rsp+rax*2+8B8h+var_868]
0x18000f3bd  call    return_difference
0x18000f3c2  cmp     eax, 578h
0x18000f3c7  ja      short loc_18000F3DA
0x18000f3c9  mov     eax, [rsp+8B8h+var_884]
0x18000f3cd  mov     ebx, r13d
0x18000f3d0  jmp     short loc_18000F38A
0x18000f3d2  mov     [r14], r9d
0x18000f3d5  jmp     loc_18000F2F7
0x18000f3da  lea     r8d, [rbx+800h]
0x18000f3e1  mov     eax, r8d
0x18000f3e4  lea     edx, [rbx-400h]
0x18000f3ea  shr     rax, 6
0x18000f3ee  movzx   ecx, [rsp+rax*2+8B8h+var_868]
0x18000f3f3  mov     eax, edx
0x18000f3f5  shr     rax, 6
0x18000f3f9  mov     [rsp+8B8h+var_898], ecx
0x18000f3fd  mov     rcx, rdi
0x18000f400  movzx   r9d, [rsp+rax*2+8B8h+var_868]
0x18000f406  call    return_difference
0x18000f40b  cmp     eax, 578h
0x18000f410  jbe     short loc_18000F3C9
0x18000f412  lea     r8d, [rbx+0C00h]
0x18000f419  mov     eax, r8d
0x18000f41c  lea     edx, [rbx-800h]
0x18000f422  shr     rax, 6
0x18000f426  movzx   ecx, [rsp+rax*2+8B8h+var_868]
0x18000f42b  mov     eax, edx
0x18000f42d  shr     rax, 6
0x18000f431  mov     [rsp+8B8h+var_898], ecx
0x18000f435  mov     rcx, rdi
0x18000f438  movzx   r9d, [rsp+rax*2+8B8h+var_868]
0x18000f43e  call    return_difference
0x18000f443  cmp     eax, 578h
0x18000f448  jbe     loc_18000F3C9
0x18000f44e  xor     r12d, r12d
0x18000f451  lea     eax, [rbx+0A00h]
0x18000f457  xor     esi, esi
0x18000f459  lea     r15d, [rbx+200h]
0x18000f460  cmp     r15d, eax
0x18000f463  jnb     loc_18000F3C9
0x18000f469  mov     r14d, eax
0x18000f46c  lea     edx, [r15-400h]
0x18000f473  mov     eax, r15d
0x18000f476  shr     rax, 6
0x18000f47a  mov     r8d, r15d
0x18000f47d  mov     ebx, r12d
0x18000f480  movzx   ecx, [rsp+rax*2+8B8h+var_868]
0x18000f485  mov     eax, edx
0x18000f487  shr     rax, 6
0x18000f48b  mov     [rsp+8B8h+var_898], ecx
0x18000f48f  mov     rcx, rdi
0x18000f492  movzx   r9d, [rsp+rax*2+8B8h+var_868]
0x18000f498  call    return_difference
0x18000f49d  cmp     eax, r12d
0x18000f4a0  mov     ecx, r15d
0x18000f4a3  cmova   r12d, eax
0x18000f4a7  cmp     eax, ebx
0x18000f4a9  cmovbe  ecx, esi
0x18000f4ac  add     r15d, 40h ; '@'
0x18000f4b0  mov     esi, ecx
0x18000f4b2  cmp     r15d, r14d
0x18000f4b5  jb      short loc_18000F46C
0x18000f4b7  mov     r14, [rsp+8B8h+var_880]
0x18000f4bc  cmp     r12d, 6A4h
0x18000f4c3  jb      loc_18000F3C9
0x18000f4c9  cmp     esi, 1000h
0x18000f4cf  jb      loc_18000F3C9
0x18000f4d5  mov     rcx, [rsp+8B8h+var_878]
0x18000f4da  inc     bpl
0x18000f4dd  mov     [rdi+8B0h], bpl
0x18000f4e4  mov     [rcx], esi
0x18000f4e6  test    r14, r14
0x18000f4e9  jz      short loc_18000F4F9
0x18000f4eb  mov     ecx, esi
0x18000f4ed  shr     rcx, 6
0x18000f4f1  movzx   ecx, [rsp+rcx*2+8B8h+var_868]
0x18000f4f6  mov     [r14], ecx
0x18000f4f9  mov     eax, 1
0x18000f4fe  jmp     loc_18000F302
```
