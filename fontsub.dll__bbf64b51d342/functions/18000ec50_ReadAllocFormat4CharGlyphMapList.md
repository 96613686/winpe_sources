# ReadAllocFormat4CharGlyphMapList

- ea: `0x18000ec50`
- end: `0x18000ef17`
- name: `ReadAllocFormat4CharGlyphMapList`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800118bc`

## callees

- `0x18000dda0`
- `0x18000e4c8`
- `0x18000ec50`
- `0x18000f2c4`
- `0x180011538`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall ReadAllocFormat4CharGlyphMapList(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned __int16 a5,
        __int64 *a6,
        unsigned __int16 *a7)
{
  unsigned __int16 *v7; // r15
  __int64 result; // rax
  __int64 v10; // rbx
  unsigned __int16 v11; // di
  unsigned __int16 v12; // r14
  unsigned __int16 i; // cx
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // ax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int16 v21; // r10
  __int64 v22; // rdi
  unsigned __int16 v23; // r11
  __int64 v24; // r8
  unsigned __int16 v25; // r9
  unsigned int v26; // eax
  unsigned __int16 v27; // dx
  int v28; // edx
  unsigned __int16 v29; // dx
  __int64 v30; // rcx
  unsigned __int16 v31[2]; // [rsp+40h] [rbp-40h] BYREF
  __int16 v32; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v35; // [rsp+58h] [rbp-28h]
  __int64 v36; // [rsp+60h] [rbp-20h] BYREF
  int v37; // [rsp+68h] [rbp-18h]
  __int16 v38; // [rsp+6Ch] [rbp-14h]

  v7 = a7;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  *a6 = 0;
  v35 = a7;
  v34 = 0;
  v33 = 0;
  v31[0] = 0;
  v32 = 0;
  *a7 = 0;
  result = ReadAllocCmapFormat4(
             a1,
             a2,
             a3,
             (unsigned int)&v32,
             (__int64)&v36,
             (__int64)&v34,
             (__int64)&v33,
             (__int64)v31);
  if ( !(_WORD)result )
  {
    v10 = v34;
    v11 = 0;
    v12 = HIWORD(v36) >> 1;
    for ( i = 0; i < v12; ++i )
    {
      v14 = *(_WORD *)(v34 + 8LL * i);
      if ( v14 != 0xFFFF && v14 >= *(_WORD *)(v34 + 8LL * i + 2) )
      {
        v15 = v11 + v14 - *(_WORD *)(v34 + 8LL * i + 2) + 1;
        if ( v15 < v11 )
        {
          FreeCmapFormat4(v34, v33, 1);
          return 1006;
        }
        v11 = v15;
      }
    }
    if ( !v11 )
    {
      v16 = Mem_Alloc(4u);
      v18 = v33;
      v19 = v10;
      *a6 = v16;
      if ( !v16 )
      {
LABEL_12:
        FreeCmapFormat4(v19, v18, v17);
        return 1005;
      }
      FreeCmapFormat4(v10, v18, v17);
      *(_WORD *)*a6 = 0;
      *(_WORD *)(*a6 + 2) = 0;
      *a7 = 1;
      return 0;
    }
    v20 = Mem_Alloc(4LL * v11);
    *a6 = v20;
    if ( !v20 )
    {
      v18 = v33;
      v19 = v10;
      goto LABEL_12;
    }
    *a7 = v11;
    v21 = 0;
    v22 = v33;
    v23 = 0;
    if ( !v12 )
      goto LABEL_32;
    v24 = 0;
    do
    {
      if ( *(_WORD *)(v10 + 8 * v24) != 0xFFFF )
      {
        v25 = *(_WORD *)(v10 + 8 * v24 + 2);
        if ( *(_WORD *)(v10 + 8 * v24) >= v25 )
        {
          while ( 1 )
          {
            v26 = *(unsigned __int16 *)(v10 + 8 * v24 + 6);
            if ( !(_WORD)v26 )
              break;
            v28 = v23 + v25 + (v26 >> 1) - v12 - *(unsigned __int16 *)(v10 + 8 * v24 + 2);
            if ( v28 >= 0 && v28 < v31[0] )
            {
              _mm_lfence();
              v27 = *(_WORD *)(v22 + 2LL * v28);
              if ( v27 )
                goto LABEL_25;
            }
LABEL_29:
            if ( ++v25 > *(_WORD *)(v10 + 8 * v24) )
              goto LABEL_30;
          }
          v27 = v25;
LABEL_25:
          v29 = *(_WORD *)(v10 + 8 * v24 + 4) + v27;
          if ( (unsigned __int16)(v29 - 1) <= 0xFFFDu && v29 < a5 && *(_BYTE *)(v29 + a4) )
          {
            v30 = v21++;
            *(_WORD *)(*a6 + 4 * v30) = v25;
            *(_WORD *)(*a6 + 4 * v30 + 2) = v29;
          }
          goto LABEL_29;
        }
      }
LABEL_30:
      ++v23;
      ++v24;
    }
    while ( v23 < v12 );
    v7 = v35;
    if ( !v21 )
    {
LABEL_32:
      v21 = 1;
      *(_WORD *)*a6 = 0;
      v24 = *a6;
      *(_WORD *)(*a6 + 2) = 0;
    }
    *v7 = v21;
    FreeCmapFormat4(v10, v22, v24);
    SortCodeList(*a6, v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ec50  mov     [rsp-38h+arg_18], rbx
0x18000ec55  push    rbp
0x18000ec56  push    rsi
0x18000ec57  push    rdi
0x18000ec58  push    r12
0x18000ec5a  push    r13
0x18000ec5c  push    r14
0x18000ec5e  push    r15
0x18000ec60  mov     rbp, rsp
0x18000ec63  sub     rsp, 80h
0x18000ec6a  mov     rax, cs:__security_cookie
0x18000ec71  xor     rax, rsp
0x18000ec74  mov     [rbp+var_10], rax
0x18000ec78  mov     r15, [rbp+arg_30]
0x18000ec7c  xor     eax, eax
0x18000ec7e  mov     rsi, [rbp+arg_28]
0x18000ec82  xor     r13d, r13d
0x18000ec85  mov     [rbp+var_20], rax
0x18000ec89  mov     r12, r9
0x18000ec8c  mov     [rbp+var_18], eax
0x18000ec8f  lea     r9, [rbp+var_3C]
0x18000ec93  mov     [rbp+var_14], ax
0x18000ec97  lea     rax, [rbp+var_40]
0x18000ec9b  mov     [rsp+80h+var_48], rax
0x18000eca0  lea     rax, [rbp+var_38]
0x18000eca4  mov     [rsp+80h+var_50], rax
0x18000eca9  lea     rax, [rbp+var_30]
0x18000ecad  mov     [rsp+80h+var_58], rax
0x18000ecb2  lea     rax, [rbp+var_20]
0x18000ecb6  mov     [rsi], r13
0x18000ecb9  mov     [rsp+80h+var_60], rax
0x18000ecbe  mov     [rbp+var_28], r15
0x18000ecc2  mov     [rbp+var_30], r13
0x18000ecc6  mov     [rbp+var_38], r13
0x18000ecca  mov     [rbp+var_40], r13w
0x18000eccf  mov     [rbp+var_3C], r13w
0x18000ecd4  mov     [r15], r13w
0x18000ecd8  call    ReadAllocCmapFormat4
0x18000ecdd  test    ax, ax
0x18000ece0  jnz     loc_18000EEF0
0x18000ece6  movzx   r14d, word ptr [rbp+var_20+6]
0x18000eceb  lea     r8d, [r13+1]
0x18000ecef  mov     rbx, [rbp+var_30]
0x18000ecf3  mov     edi, r13d
0x18000ecf6  shr     r14w, 1
0x18000ecfa  mov     ecx, r13d
0x18000ecfd  mov     r9d, 0FFFFh
0x18000ed03  cmp     cx, r14w
0x18000ed07  jnb     short loc_18000ED4D
0x18000ed09  movzx   edx, cx
0x18000ed0c  movzx   eax, word ptr [rbx+rdx*8]
0x18000ed10  cmp     ax, r9w
0x18000ed14  jz      short loc_18000ED31
0x18000ed16  cmp     ax, [rbx+rdx*8+2]
0x18000ed1b  jb      short loc_18000ED31
0x18000ed1d  sub     ax, [rbx+rdx*8+2]
0x18000ed22  add     ax, di
0x18000ed25  add     ax, r8w
0x18000ed29  cmp     ax, di
0x18000ed2c  jb      short loc_18000ED37
0x18000ed2e  movzx   edi, ax
0x18000ed31  add     cx, r8w
0x18000ed35  jmp     short loc_18000ED03
0x18000ed37  mov     rdx, [rbp+var_38]
0x18000ed3b  mov     rcx, rbx
0x18000ed3e  call    FreeCmapFormat4
0x18000ed43  mov     eax, 3EEh
0x18000ed48  jmp     loc_18000EEF0
0x18000ed4d  test    di, di
0x18000ed50  jnz     short loc_18000ED99
0x18000ed52  mov     ecx, 4; Size
0x18000ed57  call    Mem_Alloc
0x18000ed5c  mov     rdx, [rbp+var_38]
0x18000ed60  mov     rcx, rbx
0x18000ed63  mov     [rsi], rax
0x18000ed66  test    rax, rax
0x18000ed69  jnz     short loc_18000ED7A
0x18000ed6b  call    FreeCmapFormat4
0x18000ed70  mov     eax, 3EDh
0x18000ed75  jmp     loc_18000EEF0
0x18000ed7a  call    FreeCmapFormat4
0x18000ed7f  mov     rcx, [rsi]
0x18000ed82  mov     [rcx], r13w
0x18000ed86  mov     rcx, [rsi]
0x18000ed89  mov     [rcx+2], r13w
0x18000ed8e  mov     word ptr [r15], 1
0x18000ed94  jmp     loc_18000EEED
0x18000ed99  movzx   ecx, di
0x18000ed9c  shl     rcx, 2; Size
0x18000eda0  call    Mem_Alloc
0x18000eda5  mov     [rsi], rax
0x18000eda8  test    rax, rax
0x18000edab  jnz     short loc_18000EDB6
0x18000edad  mov     rdx, [rbp+var_38]
0x18000edb1  mov     rcx, rbx
0x18000edb4  jmp     short loc_18000ED6B
0x18000edb6  mov     [r15], di
0x18000edba  mov     r10d, r13d
0x18000edbd  mov     rdi, [rbp+var_38]
0x18000edc1  mov     r11d, r13d
0x18000edc4  cmp     r13w, r14w
0x18000edc8  jnb     loc_18000EEBE
0x18000edce  mov     r8, r13
0x18000edd1  mov     eax, 0FFFFh
0x18000edd6  mov     r9d, 1
0x18000eddc  cmp     [rbx+r8*8], ax
0x18000ede1  jz      loc_18000EEA3
0x18000ede7  movzx   r9d, word ptr [rbx+r8*8+2]
0x18000eded  cmp     [rbx+r8*8], r9w
0x18000edf2  jb      loc_18000EE9D
0x18000edf8  mov     r15d, 1
0x18000edfe  movzx   eax, word ptr [rbx+r8*8+6]
0x18000ee04  test    ax, ax
0x18000ee07  jnz     short loc_18000EE0F
0x18000ee09  movzx   edx, r9w
0x18000ee0d  jmp     short loc_18000EE46
0x18000ee0f  mov     edx, eax
0x18000ee11  movzx   eax, r14w
0x18000ee15  shr     edx, 1
0x18000ee17  sub     edx, eax
0x18000ee19  movzx   eax, word ptr [rbx+r8*8+2]
0x18000ee1f  sub     edx, eax
0x18000ee21  movzx   eax, r9w
0x18000ee25  add     edx, eax
0x18000ee27  movzx   eax, r11w
0x18000ee2b  add     edx, eax
0x18000ee2d  js      short loc_18000EE84
0x18000ee2f  movzx   eax, [rbp+var_40]
0x18000ee33  cmp     edx, eax
0x18000ee35  jge     short loc_18000EE84
0x18000ee37  lfence
0x18000ee3a  movsxd  rax, edx
0x18000ee3d  movzx   edx, word ptr [rdi+rax*2]
0x18000ee41  test    dx, dx
0x18000ee44  jz      short loc_18000EE84
0x18000ee46  add     dx, [rbx+r8*8+4]
0x18000ee4c  mov     ecx, 0FFFDh
0x18000ee51  movzx   eax, dx
0x18000ee54  sub     ax, r15w
0x18000ee58  cmp     ax, cx
0x18000ee5b  ja      short loc_18000EE84
0x18000ee5d  cmp     dx, [rbp+arg_20]
0x18000ee61  jnb     short loc_18000EE84
0x18000ee63  movzx   eax, dx
0x18000ee66  cmp     [rax+r12], r13b
0x18000ee6a  jz      short loc_18000EE84
0x18000ee6c  mov     rax, [rsi]
0x18000ee6f  movzx   ecx, r10w
0x18000ee73  add     r10w, r15w
0x18000ee77  mov     [rax+rcx*4], r9w
0x18000ee7c  mov     rax, [rsi]
0x18000ee7f  mov     [rax+rcx*4+2], dx
0x18000ee84  add     r9w, r15w
0x18000ee88  cmp     r9w, [rbx+r8*8]
0x18000ee8d  jbe     loc_18000EDFE
0x18000ee93  mov     eax, 0FFFFh
0x18000ee98  mov     r9d, r15d
0x18000ee9b  jmp     short loc_18000EEA3
0x18000ee9d  mov     r9d, 1
0x18000eea3  add     r11w, r9w
0x18000eea7  inc     r8
0x18000eeaa  cmp     r11w, r14w
0x18000eeae  jb      loc_18000EDDC
0x18000eeb4  mov     r15, [rbp+var_28]
0x18000eeb8  test    r10w, r10w
0x18000eebc  jnz     short loc_18000EED3
0x18000eebe  mov     r8, [rsi]
0x18000eec1  mov     r10d, 1
0x18000eec7  mov     [r8], r13w
0x18000eecb  mov     r8, [rsi]
0x18000eece  mov     [r8+2], r13w
0x18000eed3  mov     rdx, rdi
0x18000eed6  mov     [r15], r10w
0x18000eeda  mov     rcx, rbx
0x18000eedd  call    FreeCmapFormat4
0x18000eee2  mov     rcx, [rsi]
0x18000eee5  mov     rdx, r15
0x18000eee8  call    SortCodeList
0x18000eeed  mov     eax, r13d
0x18000eef0  mov     rcx, [rbp+var_10]
0x18000eef4  xor     rcx, rsp; StackCookie
0x18000eef7  call    __security_check_cookie
0x18000eefc  mov     rbx, [rsp+80h+arg_18]
0x18000ef04  add     rsp, 80h
0x18000ef0b  pop     r15
0x18000ef0d  pop     r14
0x18000ef0f  pop     r13
0x18000ef11  pop     r12
0x18000ef13  pop     rdi
0x18000ef14  pop     rsi
0x18000ef15  pop     rbp
0x18000ef16  retn
```
