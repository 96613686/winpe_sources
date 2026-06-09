# PathReplaceGreedy

- ea: `0x18001d87c`
- end: `0x18001dae2`
- name: `PathReplaceGreedy`
- size: `614`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001dea8`

## callees

- `0x180007740`
- `0x18001d87c`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18001d90b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18001d91f`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18001d90b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18001d91f`

## pseudocode

```c
__int64 __fastcall PathReplaceGreedy(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int16 v4; // cx
  int v6; // r9d
  unsigned __int16 *v7; // r13
  unsigned __int16 v8; // r14
  unsigned __int16 v9; // si
  unsigned int v10; // ecx
  WCHAR v11; // bx
  __int64 v12; // rdx
  unsigned __int16 *v13; // r11
  unsigned int v14; // r8d
  int v15; // ecx
  int v17; // r9d
  int i; // r8d
  unsigned __int16 v19; // dx
  unsigned __int16 v20; // r10
  unsigned __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // r9d
  int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // rcx
  _WORD v29[4]; // [rsp+10h] [rbp-10h] BYREF
  unsigned __int16 *v30; // [rsp+18h] [rbp-8h]
  int v31; // [rsp+20h] [rbp+0h]
  unsigned __int16 *v32; // [rsp+28h] [rbp+8h]

  v32 = a2;
  v4 = *a3;
  if ( *a3 >= *a1 )
  {
    v6 = 0;
    v31 = 0;
    v7 = 0;
    v8 = 0;
    if ( (v4 & 0xFFFE) != 0 )
    {
      do
      {
        v9 = 0;
        if ( (*a1 & 0xFFFE) != 0 )
        {
          do
          {
            v10 = v8 + v9;
            if ( v10 >= *a3 >> 1 )
              break;
            v11 = RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * v10));
            if ( v11 != RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v9)) )
              break;
            ++v9;
          }
          while ( v9 < (unsigned __int16)(*a1 >> 1) );
          v6 = v31;
        }
        if ( v9 == *a1 >> 1 )
        {
          v12 = v8 + (unsigned int)v9;
          if ( (_DWORD)v12 == *a3 >> 1 || *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v12) == 92 )
          {
            v30 = v7;
            LOWORD(v6) = v6 + 1;
            v29[0] = v8;
            v31 = v6;
            v7 = v29;
            v29[1] = v8 + v9;
          }
        }
        ++v8;
      }
      while ( v8 < (unsigned __int16)(*a3 >> 1) );
      if ( v7 )
      {
        v13 = v32;
        v14 = *a3;
        v15 = *v32;
        if ( (unsigned __int16)v15 > *a1 && v14 + (unsigned __int16)v6 * (v15 - *a1) > a3[1] )
          return 2147483653LL;
        v17 = (a3[1] >> 1) - 1;
        for ( i = (v14 >> 1) - 1; i >= 0; --i )
        {
          if ( v7 && i < v7[1] )
          {
            v19 = *v13;
            if ( (*v13 & 0xFFFE) != 0 )
            {
              v20 = 0;
              do
              {
                v21 = v19;
                v22 = v20++;
                v23 = v17--;
                *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v23) = *(_WORD *)(*((_QWORD *)v13 + 1) + 2 * ((v21 >> 1) - v22) - 2);
                v19 = *v13;
              }
              while ( v20 < (unsigned __int16)(*v13 >> 1) );
            }
            i = *v7;
            v7 = (unsigned __int16 *)*((_QWORD *)v7 + 1);
          }
          else
          {
            v24 = v17--;
            *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v24) = *(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * i);
          }
        }
        v25 = v17 + 1;
        v26 = 0;
        while ( v25 < a3[1] >> 1 )
        {
          v27 = v25++;
          v28 = v26++;
          *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v28) = *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v27);
        }
        *a3 = 2 * v26;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001d87c  push    rbp
0x18001d87e  push    rbx
0x18001d87f  push    rsi
0x18001d880  push    rdi
0x18001d881  push    r12
0x18001d883  push    r13
0x18001d885  push    r14
0x18001d887  push    r15
0x18001d889  sub     rsp, 48h
0x18001d88d  lea     rbp, [rsp+20h]
0x18001d892  mov     rax, cs:__security_cookie
0x18001d899  xor     rax, rbp
0x18001d89c  mov     [rbp+60h+var_50], rax
0x18001d8a0  mov     r15, rcx
0x18001d8a3  mov     [rbp+60h+var_58], rdx
0x18001d8a7  movzx   ecx, word ptr [r8]
0x18001d8ab  mov     rdi, r8
0x18001d8ae  cmp     cx, [r15]
0x18001d8b2  jb      loc_18001DAC3
0x18001d8b8  xor     r9d, r9d
0x18001d8bb  mov     r10d, 0FFFEh
0x18001d8c1  and     cx, r10w
0x18001d8c5  mov     [rbp+60h+var_60], r9d
0x18001d8c9  xor     r13d, r13d
0x18001d8cc  xor     r14d, r14d
0x18001d8cf  xor     eax, eax
0x18001d8d1  cmp     ax, cx
0x18001d8d4  jnb     loc_18001DAC3
0x18001d8da  lea     ebx, [rax+1]
0x18001d8dd  movzx   ecx, word ptr [r15]
0x18001d8e1  xor     esi, esi
0x18001d8e3  and     cx, r10w
0x18001d8e7  xor     eax, eax
0x18001d8e9  cmp     ax, cx
0x18001d8ec  jnb     short loc_18001D948
0x18001d8ee  movzx   r12d, r14w
0x18001d8f2  movzx   eax, word ptr [rdi]
0x18001d8f5  movzx   ecx, si
0x18001d8f8  add     ecx, r12d
0x18001d8fb  shr     eax, 1
0x18001d8fd  cmp     ecx, eax
0x18001d8ff  jnb     short loc_18001D93E
0x18001d901  mov     eax, ecx
0x18001d903  mov     rcx, [rdi+8]
0x18001d907  movzx   ecx, word ptr [rcx+rax*2]; Source
0x18001d90b  call    cs:__imp_RtlUpcaseUnicodeChar
0x18001d911  mov     rcx, [r15+8]
0x18001d915  movzx   ebx, ax
0x18001d918  movzx   edx, si
0x18001d91b  movzx   ecx, word ptr [rcx+rdx*2]; Source
0x18001d91f  call    cs:__imp_RtlUpcaseUnicodeChar
0x18001d925  cmp     bx, ax
0x18001d928  mov     ebx, 1
0x18001d92d  jnz     short loc_18001D93E
0x18001d92f  movzx   eax, word ptr [r15]
0x18001d933  add     si, bx
0x18001d936  shr     ax, 1
0x18001d939  cmp     si, ax
0x18001d93c  jb      short loc_18001D8F2
0x18001d93e  mov     r9d, [rbp+60h+var_60]
0x18001d942  mov     r10d, 0FFFEh
0x18001d948  movzx   eax, word ptr [r15]
0x18001d94c  shr     ax, 1
0x18001d94f  cmp     si, ax
0x18001d952  jnz     short loc_18001D99A
0x18001d954  movzx   eax, r14w
0x18001d958  movzx   edx, si
0x18001d95b  add     edx, eax
0x18001d95d  movzx   eax, word ptr [rdi]
0x18001d960  shr     eax, 1
0x18001d962  cmp     edx, eax
0x18001d964  jz      short loc_18001D971
0x18001d966  mov     rax, [rdi+8]
0x18001d96a  cmp     word ptr [rax+rdx*2], 5Ch ; '\'
0x18001d96f  jnz     short loc_18001D99A
0x18001d971  mov     eax, [rsp+80h+var_80]
0x18001d974  sub     rsp, 10h
0x18001d978  lea     rcx, [rsp+90h+var_70]
0x18001d97d  mov     eax, [rcx]
0x18001d97f  add     si, r14w
0x18001d983  mov     [rcx+8], r13
0x18001d987  add     r9w, bx
0x18001d98b  mov     [rcx], r14w
0x18001d98f  mov     [rbp+60h+var_60], r9d
0x18001d993  mov     r13, rcx
0x18001d996  mov     [rcx+2], si
0x18001d99a  movzx   eax, word ptr [rdi]
0x18001d99d  add     r14w, bx
0x18001d9a1  shr     ax, 1
0x18001d9a4  cmp     r14w, ax
0x18001d9a8  jb      loc_18001D8DD
0x18001d9ae  test    r13, r13
0x18001d9b1  jz      loc_18001DAC3
0x18001d9b7  mov     r11, [rbp+60h+var_58]
0x18001d9bb  movzx   r8d, word ptr [rdi]
0x18001d9bf  movzx   ecx, word ptr [r11]
0x18001d9c3  cmp     cx, [r15]
0x18001d9c7  jbe     short loc_18001D9EB
0x18001d9c9  movzx   eax, word ptr [r15]
0x18001d9cd  sub     ecx, eax
0x18001d9cf  movzx   eax, r9w
0x18001d9d3  imul    ecx, eax
0x18001d9d6  movzx   eax, word ptr [rdi+2]
0x18001d9da  add     ecx, r8d
0x18001d9dd  cmp     ecx, eax
0x18001d9df  jbe     short loc_18001D9EB
0x18001d9e1  mov     eax, 80000005h
0x18001d9e6  jmp     loc_18001DAC5
0x18001d9eb  movzx   r9d, word ptr [rdi+2]
0x18001d9f0  shr     r9d, 1
0x18001d9f3  sub     r9d, ebx
0x18001d9f6  shr     r8d, 1
0x18001d9f9  sub     r8d, ebx
0x18001d9fc  js      loc_18001DA90
0x18001da02  test    r13, r13
0x18001da05  jz      short loc_18001DA71
0x18001da07  movzx   eax, word ptr [r13+2]
0x18001da0c  cmp     r8d, eax
0x18001da0f  jge     short loc_18001DA71
0x18001da11  movzx   edx, word ptr [r11]
0x18001da15  xor     eax, eax
0x18001da17  movzx   ecx, dx
0x18001da1a  and     cx, r10w
0x18001da1e  cmp     ax, cx
0x18001da21  jnb     short loc_18001DA66
0x18001da23  xor     r10d, r10d
0x18001da26  mov     rcx, [rdi+8]
0x18001da2a  movzx   r8d, dx
0x18001da2e  movzx   eax, r10w
0x18001da32  add     r10w, bx
0x18001da36  movsxd  rdx, r9d
0x18001da39  sub     r9d, ebx
0x18001da3c  shr     r8, 1
0x18001da3f  sub     r8, rax
0x18001da42  mov     rax, [r11+8]
0x18001da46  movzx   eax, word ptr [rax+r8*2-2]
0x18001da4c  mov     [rcx+rdx*2], ax
0x18001da50  movzx   edx, word ptr [r11]
0x18001da54  movzx   eax, dx
0x18001da57  shr     ax, 1
0x18001da5a  cmp     r10w, ax
0x18001da5e  jb      short loc_18001DA26
0x18001da60  mov     r10d, 0FFFEh
0x18001da66  movzx   r8d, word ptr [r13+0]
0x18001da6b  mov     r13, [r13+8]
0x18001da6f  jmp     short loc_18001DA86
0x18001da71  mov     rdx, [rdi+8]
0x18001da75  movsxd  rcx, r9d
0x18001da78  sub     r9d, ebx
0x18001da7b  movsxd  rax, r8d
0x18001da7e  movzx   eax, word ptr [rdx+rax*2]
0x18001da82  mov     [rdx+rcx*2], ax
0x18001da86  sub     r8d, 1
0x18001da8a  jns     loc_18001DA02
0x18001da90  inc     r9d
0x18001da93  xor     r8d, r8d
0x18001da96  jmp     short loc_18001DAB0
0x18001da98  mov     rdx, [rdi+8]
0x18001da9c  movsxd  rax, r9d
0x18001da9f  add     r9d, ebx
0x18001daa2  movsxd  rcx, r8d
0x18001daa5  add     r8d, ebx
0x18001daa8  movzx   eax, word ptr [rdx+rax*2]
0x18001daac  mov     [rdx+rcx*2], ax
0x18001dab0  movzx   eax, word ptr [rdi+2]
0x18001dab4  shr     eax, 1
0x18001dab6  cmp     r9d, eax
0x18001dab9  jl      short loc_18001DA98
0x18001dabb  add     r8w, r8w
0x18001dabf  mov     [rdi], r8w
0x18001dac3  xor     eax, eax
0x18001dac5  mov     rcx, [rbp+60h+var_50]
0x18001dac9  xor     rcx, rbp; StackCookie
0x18001dacc  call    __security_check_cookie
0x18001dad1  lea     rsp, [rbp+28h]
0x18001dad5  pop     r15
0x18001dad7  pop     r14
0x18001dad9  pop     r13
0x18001dadb  pop     r12
0x18001dadd  pop     rdi
0x18001dade  pop     rsi
0x18001dadf  pop     rbx
0x18001dae0  pop     rbp
0x18001dae1  retn
```
