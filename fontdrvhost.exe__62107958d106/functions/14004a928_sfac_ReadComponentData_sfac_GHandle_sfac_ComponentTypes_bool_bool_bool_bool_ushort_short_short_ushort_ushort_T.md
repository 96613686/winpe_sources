# sfac_ReadComponentData(sfac_GHandle *,sfac_ComponentTypes *,bool *,bool *,bool *,bool *,ushort *,short *,short *,ushort *,ushort *,TransMatrix *,bool *,bool *)

- ea: `0x14004a928`
- end: `0x14004ac1d`
- name: `?sfac_ReadComponentData@@YAHPEAUsfac_GHandle@@PEAW4sfac_ComponentTypes@@PEA_N222PEAGPEAF433PEAUTransMatrix@@22@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct sfac_GHandle *, enum sfac_ComponentTypes *, bool *, bool *, bool *, bool *, unsigned __int16 *, __int16 *, __int16 *, unsigned __int16 *, unsigned __int16 *, struct TransMatrix *, bool *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400197e0`

## callees

- `0x14004a928`

## pseudocode

```c
__int64 __fastcall sfac_ReadComponentData(
        struct sfac_GHandle *a1,
        enum sfac_ComponentTypes *a2,
        bool *a3,
        bool *a4,
        bool *a5,
        bool *a6,
        unsigned __int16 *a7,
        __int16 *a8,
        __int16 *a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        struct TransMatrix *a12,
        bool *a13,
        bool *a14)
{
  __int64 v15; // rbx
  unsigned __int64 v16; // r11
  unsigned __int16 v18; // r9
  unsigned __int8 *v19; // rdx
  unsigned __int8 *v20; // r8
  __int16 v22; // cx
  int v23; // ecx
  int v24; // eax
  unsigned __int8 *v25; // r8
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  unsigned __int8 *v29; // rdx
  int v30; // ecx

  v15 = *((_QWORD *)a1 + 3);
  v16 = *(unsigned int *)a1 + *((_QWORD *)a1 + 1);
  *(_OWORD *)a12 = xmmword_14009B9C0;
  *((_OWORD *)a12 + 1) = xmmword_14009B9D0;
  *((_DWORD *)a12 + 8) = 0x10000;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  *a13 = 0;
  if ( v15 + 2 > v16 )
    return 5133;
  v18 = _byteswap_ushort(*(_WORD *)v15);
  *a6 = HIBYTE(v18) & 1;
  *a4 = (v18 & 0x200) != 0;
  *a3 = (v18 & 4) != 0;
  if ( (v18 & 0x800) != 0 )
    *a5 = 1;
  if ( (v18 & 0x1000) != 0 )
    *a5 = 0;
  v19 = (unsigned __int8 *)(v15 + 4);
  if ( v15 + 4 > v16 )
    return 5133;
  *a7 = _byteswap_ushort(*(_WORD *)(v15 + 2));
  *(_DWORD *)a2 = (v18 & 2) != 0;
  if ( (v18 & 1) != 0 )
  {
    if ( v15 + 8 <= v16 )
    {
      v22 = _byteswap_ushort(*(_WORD *)(v15 + 4));
      if ( (v18 & 2) != 0 )
      {
        *a8 = v22;
        *a9 = _byteswap_ushort(*(_WORD *)(v15 + 6));
      }
      else
      {
        *a10 = v22;
        *a11 = _byteswap_ushort(*(_WORD *)(v15 + 6));
      }
      v20 = (unsigned __int8 *)(v15 + 8);
LABEL_11:
      if ( (v18 & 0xC8) == 0 )
      {
LABEL_12:
        *a14 = (v18 & 0x20) == 0;
        *((_QWORD *)a1 + 3) = v20;
        return v16 < (unsigned __int64)v20 ? 0x140D : 0;
      }
      *a13 = 1;
      if ( (v18 & 0x80u) == 0 )
      {
        v29 = v20 + 2;
        *((_DWORD *)a12 + 1) = 0;
        *((_DWORD *)a12 + 3) = 0;
        if ( (unsigned __int64)(v20 + 2) > v16 )
          return 5133;
        v30 = 4 * (v20[1] | (__int16)(*v20 << 8));
        *(_DWORD *)a12 = v30;
        if ( (v18 & 0x40) == 0 )
        {
          v20 += 2;
          goto LABEL_29;
        }
        v20 += 4;
        if ( (unsigned __int64)(v29 + 2) > v16 )
          return 5133;
      }
      else
      {
        if ( (unsigned __int64)(v20 + 8) > v16 )
          return 5133;
        v23 = (__int16)(*v20 << 8);
        v24 = v20[1];
        v25 = v20 + 2;
        *(_DWORD *)a12 = 4 * (v24 | v23);
        v26 = (__int16)(*v25 << 8);
        v27 = v25[1];
        v25 += 2;
        *((_DWORD *)a12 + 1) = 4 * (v27 | v26);
        v28 = v25[1] | (__int16)(*v25 << 8);
        v29 = v25 + 2;
        v20 = v25 + 4;
        *((_DWORD *)a12 + 3) = 4 * v28;
      }
      v30 = 4 * (v29[1] | (__int16)(*v29 << 8));
LABEL_29:
      *((_DWORD *)a12 + 4) = v30;
      goto LABEL_12;
    }
  }
  else
  {
    v20 = (unsigned __int8 *)(v15 + 6);
    if ( v15 + 6 <= v16 )
    {
      if ( (v18 & 2) != 0 )
      {
        *a8 = (char)*v19;
        *a9 = *(char *)(v15 + 5);
      }
      else
      {
        *a10 = *v19;
        *a11 = *(unsigned __int8 *)(v15 + 5);
      }
      goto LABEL_11;
    }
  }
  return 5133;
}

```

## disassembly

```asm
0x14004a928  mov     [rsp+arg_0], rcx
0x14004a92d  push    rbx
0x14004a92e  push    rbp
0x14004a92f  push    rsi
0x14004a930  push    rdi
0x14004a931  push    r12
0x14004a933  push    r13
0x14004a935  push    r14
0x14004a937  push    r15
0x14004a939  mov     r10d, [rcx]
0x14004a93c  mov     r13, rdx
0x14004a93f  mov     r11, [rcx+8]
0x14004a943  xor     edx, edx
0x14004a945  mov     rbx, [rcx+18h]
0x14004a949  add     r11, r10
0x14004a94c  mov     r10, [rsp+40h+arg_58]
0x14004a954  mov     r12, r8
0x14004a957  mov     eax, cs:dword_14009B9E0
0x14004a95d  mov     rbp, r9
0x14004a960  movups  xmm0, cs:xmmword_14009B9C0
0x14004a967  mov     rdi, [rsp+40h+arg_38]
0x14004a96f  lea     r8, [rbx+2]
0x14004a973  mov     rsi, [rsp+40h+arg_40]
0x14004a97b  mov     r14, [rsp+40h+arg_48]
0x14004a983  mov     r15, [rsp+40h+arg_50]
0x14004a98b  movups  xmm1, cs:xmmword_14009B9D0
0x14004a992  movups  xmmword ptr [r10], xmm0
0x14004a996  movups  xmmword ptr [r10+10h], xmm1
0x14004a99b  mov     [r10+20h], eax
0x14004a99f  mov     rax, [rsp+40h+arg_60]
0x14004a9a7  mov     [rdi], dx
0x14004a9aa  mov     [rsi], dx
0x14004a9ad  mov     [r14], dx
0x14004a9b1  mov     [r15], dx
0x14004a9b5  mov     [rax], dl
0x14004a9b7  cmp     r8, r11
0x14004a9ba  ja      loc_14004AB13
0x14004a9c0  movzx   eax, byte ptr [rbx]
0x14004a9c3  movzx   r9d, byte ptr [rbx+1]
0x14004a9c8  mov     bl, 1
0x14004a9ca  shl     ax, 8
0x14004a9ce  or      r9w, ax
0x14004a9d2  mov     rax, [rsp+40h+arg_28]
0x14004a9d7  movzx   ecx, r9w
0x14004a9db  shr     cx, 8
0x14004a9df  and     cl, bl
0x14004a9e1  mov     [rax], cl
0x14004a9e3  movzx   eax, r9w
0x14004a9e7  shr     ax, 9
0x14004a9eb  and     al, bl
0x14004a9ed  mov     [rbp+0], al
0x14004a9f0  mov     al, r9b
0x14004a9f3  shr     al, 2
0x14004a9f6  and     al, bl
0x14004a9f8  bt      r9w, 0Bh
0x14004a9fe  mov     [r12], al
0x14004aa02  mov     rax, [rsp+40h+arg_20]
0x14004aa07  jb      loc_14004AB3A
0x14004aa0d  bt      r9w, 0Ch
0x14004aa13  jb      loc_14004AB1A
0x14004aa19  lea     rdx, [r8+2]
0x14004aa1d  cmp     rdx, r11
0x14004aa20  ja      loc_14004AB13
0x14004aa26  movzx   eax, byte ptr [r8+1]
0x14004aa2b  mov     r12d, 2
0x14004aa31  movzx   ecx, byte ptr [r8]
0x14004aa35  movzx   ebx, r9w
0x14004aa39  shl     cx, 8
0x14004aa3d  or      cx, ax
0x14004aa40  mov     rax, [rsp+40h+arg_30]
0x14004aa45  and     bx, r12w
0x14004aa49  lea     ebp, [r12-2]
0x14004aa4e  mov     [rax], cx
0x14004aa51  mov     eax, ebp
0x14004aa53  setnz   al
0x14004aa56  mov     [r13+0], eax
0x14004aa5a  test    r9b, 1
0x14004aa5e  jnz     short loc_14004AABF
0x14004aa60  lea     r8, [rdx+2]
0x14004aa64  cmp     r8, r11
0x14004aa67  ja      loc_14004AB13
0x14004aa6d  test    bx, bx
0x14004aa70  jz      loc_14004AB41
0x14004aa76  movsx   eax, byte ptr [rdx]
0x14004aa79  mov     [rdi], ax
0x14004aa7c  movsx   eax, byte ptr [rdx+1]
0x14004aa80  mov     [rsi], ax
0x14004aa83  test    r9b, 0C8h
0x14004aa87  jnz     short loc_14004AAF6
0x14004aa89  mov     rax, [rsp+40h+arg_68]
0x14004aa91  shr     r9b, 5
0x14004aa95  not     r9b
0x14004aa98  and     r9b, 1
0x14004aa9c  mov     [rax], r9b
0x14004aa9f  cmp     r11, r8
0x14004aaa2  mov     rax, [rsp+40h+arg_0]
0x14004aaa7  mov     [rax+18h], r8
0x14004aaab  sbb     eax, eax
0x14004aaad  and     eax, 140Dh
0x14004aab2  pop     r15
0x14004aab4  pop     r14
0x14004aab6  pop     r13
0x14004aab8  pop     r12
0x14004aaba  pop     rdi
0x14004aabb  pop     rsi
0x14004aabc  pop     rbp
0x14004aabd  pop     rbx
0x14004aabe  retn
0x14004aabf  lea     rax, [rdx+4]
0x14004aac3  cmp     rax, r11
0x14004aac6  ja      short loc_14004AB13
0x14004aac8  movzx   ecx, byte ptr [rdx]
0x14004aacb  movzx   eax, byte ptr [rdx+1]
0x14004aacf  shl     cx, 8
0x14004aad3  or      cx, ax
0x14004aad6  test    bx, bx
0x14004aad9  jz      short loc_14004AB21
0x14004aadb  mov     [rdi], cx
0x14004aade  movzx   ecx, byte ptr [rdx+2]
0x14004aae2  movzx   eax, byte ptr [rdx+3]
0x14004aae6  shl     cx, 8
0x14004aaea  or      cx, ax
0x14004aaed  mov     [rsi], cx
0x14004aaf0  lea     r8, [rdx+4]
0x14004aaf4  jmp     short loc_14004AA83
0x14004aaf6  mov     rax, [rsp+40h+arg_60]
0x14004aafe  mov     byte ptr [rax], 1
0x14004ab01  test    r9b, r9b
0x14004ab04  jns     loc_14004ABCF
0x14004ab0a  lea     rax, [r8+8]
0x14004ab0e  cmp     rax, r11
0x14004ab11  jbe     short loc_14004AB55
0x14004ab13  mov     eax, 140Dh
0x14004ab18  jmp     short loc_14004AAB2
0x14004ab1a  mov     [rax], dl
0x14004ab1c  jmp     loc_14004AA19
0x14004ab21  mov     [r14], cx
0x14004ab25  movzx   ecx, byte ptr [rdx+2]
0x14004ab29  movzx   eax, byte ptr [rdx+3]
0x14004ab2d  shl     cx, 8
0x14004ab31  or      cx, ax
0x14004ab34  mov     [r15], cx
0x14004ab38  jmp     short loc_14004AAF0
0x14004ab3a  mov     [rax], bl
0x14004ab3c  jmp     loc_14004AA0D
0x14004ab41  movzx   eax, byte ptr [rdx]
0x14004ab44  mov     [r14], ax
0x14004ab48  movzx   eax, byte ptr [rdx+1]
0x14004ab4c  mov     [r15], ax
0x14004ab50  jmp     loc_14004AA83
0x14004ab55  movzx   eax, byte ptr [r8]
0x14004ab59  shl     ax, 8
0x14004ab5d  movsx   ecx, ax
0x14004ab60  movzx   eax, byte ptr [r8+1]
0x14004ab65  add     r8, r12
0x14004ab68  or      ecx, eax
0x14004ab6a  lea     eax, ds:0[rcx*4]
0x14004ab71  mov     [r10], eax
0x14004ab74  movzx   eax, byte ptr [r8]
0x14004ab78  shl     ax, 8
0x14004ab7c  movsx   ecx, ax
0x14004ab7f  movzx   eax, byte ptr [r8+1]
0x14004ab84  add     r8, r12
0x14004ab87  or      ecx, eax
0x14004ab89  lea     eax, ds:0[rcx*4]
0x14004ab90  mov     [r10+4], eax
0x14004ab94  movzx   eax, byte ptr [r8]
0x14004ab98  shl     ax, 8
0x14004ab9c  movsx   ecx, ax
0x14004ab9f  movzx   eax, byte ptr [r8+1]
0x14004aba4  add     r8, r12
0x14004aba7  or      ecx, eax
0x14004aba9  mov     rdx, r8
0x14004abac  add     r8, r12
0x14004abaf  lea     eax, ds:0[rcx*4]
0x14004abb6  mov     [r10+0Ch], eax
0x14004abba  movzx   eax, byte ptr [rdx]
0x14004abbd  shl     ax, 8
0x14004abc1  movsx   ecx, ax
0x14004abc4  movzx   eax, byte ptr [rdx+1]
0x14004abc8  or      ecx, eax
0x14004abca  shl     ecx, 2
0x14004abcd  jmp     short loc_14004AC14
0x14004abcf  lea     rdx, [r8+2]
0x14004abd3  mov     [r10+4], ebp
0x14004abd7  mov     [r10+0Ch], ebp
0x14004abdb  cmp     rdx, r11
0x14004abde  ja      loc_14004AB13
0x14004abe4  movzx   eax, byte ptr [r8]
0x14004abe8  shl     ax, 8
0x14004abec  movsx   ecx, ax
0x14004abef  movzx   eax, byte ptr [r8+1]
0x14004abf4  or      ecx, eax
0x14004abf6  shl     ecx, 2
0x14004abf9  mov     [r10], ecx
0x14004abfc  test    r9b, 40h
0x14004ac00  jz      short loc_14004AC11
0x14004ac02  lea     r8, [rdx+2]
0x14004ac06  cmp     r8, r11
0x14004ac09  ja      loc_14004AB13
0x14004ac0f  jmp     short loc_14004ABBA
0x14004ac11  mov     r8, rdx
0x14004ac14  mov     [r10+10h], ecx
0x14004ac18  jmp     loc_14004AA89
```
