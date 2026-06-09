# RtlCheckTokenMembershipEx

- ea: `0x180013ed0`
- end: `0x18001443c`
- name: `RtlCheckTokenMembershipEx`
- size: `1388`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180012c8c`
- `0x180013310`
- `0x180013820`

## callees

- `0x180012df0`
- `0x180013ed0`
- `0x180015af0`
- `0x180015b30`
- `0x18015eae0`
- `0x18015ecc0`
- `0x18015f0c0`
- `0x18015f0e0`
- `0x18015f320`
- `0x180162810`
- `0x180164280`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlCheckTokenMembershipEx(void *a1, unsigned __int8 *a2, int a3, _BYTE *a4)
{
  char v8; // si
  char v9; // bl
  _BYTE *v10; // rcx
  unsigned int i; // r8d
  __int64 v12; // r9
  char v13; // bl
  _BYTE *v14; // rdx
  unsigned int j; // r8d
  _BYTE *v16; // rcx
  unsigned int v17; // edx
  __int64 v18; // r9
  int v19; // ebx
  _BYTE *v21; // r8
  unsigned int k; // edx
  _BYTE *v23; // rcx
  size_t v24; // r8
  __int64 v25; // r9
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v30; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 *v33; // [rsp+80h] [rbp-80h]
  _BYTE v34[48]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h] BYREF
  int v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v38[232]; // [rsp+D8h] [rbp-28h] BYREF
  char Src; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int8 v40; // [rsp+1C1h] [rbp+C1h]
  _BYTE v41[56]; // [rsp+210h] [rbp+110h] BYREF

  v28 = 0;
  v27 = 0;
  memset_thunk_772440563353939046(&Src, 0, 0x44u);
  memset_thunk_772440563353939046(&v37, 0, 0xECu);
  Handle = 0;
  v26 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v30 = 0;
  *a4 = 0;
  memset(v34, 0, 44);
  v31 = 0;
  v32 = 0;
  if ( (a3 & 0xFFFFFFFC) == 0 )
  {
    v8 = 2;
    if ( a1 )
    {
      Handle = a1;
    }
    else
    {
      v19 = NtOpenThreadTokenEx(-2, 8, 0, 0, &Handle);
      if ( v19 == -1073741700 )
      {
        v19 = NtOpenProcessTokenEx(-1, 10, 0, &v30);
        if ( v19 < 0 )
          goto LABEL_48;
        *(_QWORD *)&v34[40] = &v35;
        *(_DWORD *)v34 = 48;
        memset(&v34[8], 0, 20);
        *(_QWORD *)&v34[32] = 0;
        v35 = 0x20000000CLL;
        LOWORD(v36) = 1;
        v19 = NtDuplicateToken(v30, 12, v34, 0, 2, &Handle);
        NtClose(v30);
      }
      if ( v19 < 0 )
        goto LABEL_48;
    }
    v33 = 0;
    v31 = 1u;
    v32 = 0;
    if ( a2 )
    {
      *((_QWORD *)&v31 + 1) = a2;
      *(_QWORD *)&v32 = a2;
    }
    else
    {
      *(_QWORD *)&v32 = 0;
    }
    WORD1(v31) = 0;
    v37 = 15466498;
    if ( (unsigned __int8)RtlValidSid(a2) && (unsigned __int8)v37 <= 4u )
    {
      v9 = 2;
      if ( (unsigned __int8)v37 > 2u )
        v9 = v37;
      if ( RtlValidAcl((__int64)&v37) )
      {
        v10 = v38;
        for ( i = 0; i < WORD2(v37); ++i )
        {
          if ( v10 >= &v38[WORD1(v37) - 8] )
            goto LABEL_19;
          v10 += *((unsigned __int16 *)v10 + 1);
        }
        if ( v10 <= &v38[WORD1(v37) - 8] )
        {
          if ( v10 )
          {
            v12 = (unsigned __int16)(4 * (a2[1] + 4));
            if ( &v10[v12] <= &v38[WORD1(v37) - 8] )
            {
              *(_WORD *)v10 = 0;
              *((_WORD *)v10 + 1) = v12;
              *((_DWORD *)v10 + 1) = 1;
              memmove(v10 + 8, a2, 4LL * a2[1] + 8);
              ++WORD2(v37);
              LOBYTE(v37) = v9;
            }
          }
        }
      }
    }
LABEL_19:
    if ( (a3 & 3) != 0 )
    {
      RtlInitializeSidEx(&Src, &RtlpAppPackageAuthority, 2, 2, 1);
      if ( (unsigned __int8)RtlValidSid(&Src) )
      {
        if ( (unsigned __int8)v37 <= 4u )
        {
          v13 = 2;
          if ( (unsigned __int8)v37 > 2u )
            v13 = v37;
          if ( RtlValidAcl((__int64)&v37) )
          {
            v14 = v38;
            for ( j = 0; j < WORD2(v37); ++j )
            {
              if ( v14 >= &v38[WORD1(v37) - 8] )
                goto LABEL_34;
              v14 += *((unsigned __int16 *)v14 + 1);
            }
            v16 = 0;
            if ( v14 <= &v38[WORD1(v37) - 8] )
              v16 = v14;
            if ( v16 )
            {
              v17 = 4 * v40 + 8;
              v18 = (unsigned __int16)(4 * v40 + 16);
              if ( &v16[v18] <= &v38[WORD1(v37) - 8] )
              {
                *(_WORD *)v16 = 0;
                *((_WORD *)v16 + 1) = v18;
                *((_DWORD *)v16 + 1) = 1;
                memmove(v16 + 8, &Src, v17);
                ++WORD2(v37);
                LOBYTE(v37) = v13;
              }
            }
          }
        }
      }
    }
LABEL_34:
    if ( (a3 & 2) != 0 )
    {
      RtlInitializeSidEx(&Src, &RtlpAppPackageAuthority, 2, 2, 2);
      if ( (unsigned __int8)RtlValidSid(&Src) )
      {
        if ( (unsigned __int8)v37 <= 4u )
        {
          if ( (unsigned __int8)v37 > 2u )
            v8 = v37;
          if ( RtlValidAcl((__int64)&v37) )
          {
            v21 = v38;
            for ( k = 0; k < WORD2(v37); ++k )
            {
              if ( v21 >= &v38[WORD1(v37) - 8] )
                goto LABEL_35;
              v21 += *((unsigned __int16 *)v21 + 1);
            }
            v23 = 0;
            if ( v21 <= &v38[WORD1(v37) - 8] )
              v23 = v21;
            if ( v23 )
            {
              v24 = 4 * (unsigned int)v40 + 8;
              v25 = (unsigned __int16)(4 * v40 + 16);
              if ( &v23[v25] <= &v38[WORD1(v37) - 8] )
              {
                *(_WORD *)v23 = 0;
                *((_WORD *)v23 + 1) = v25;
                *((_DWORD *)v23 + 1) = 1;
                memmove(v23 + 8, &Src, v24);
                ++WORD2(v37);
                LOBYTE(v37) = v8;
              }
            }
          }
        }
      }
    }
LABEL_35:
    if ( (_BYTE)v31 == 1 && (SWORD1(v31) & 0x8000u) == 0 )
    {
      v33 = &v37;
      WORD1(v31) = WORD1(v31) & 0xFFF3 | 4;
    }
    v26 = 56;
    v19 = ZwAccessCheck(&v31, Handle, 1, RtlpCheckTokenMembershipGenericMapping, v41, &v26, &v28, &v27);
    if ( v19 >= 0 )
    {
      v19 = 0;
      if ( v27 )
      {
        if ( v27 == -1073741790 )
          goto LABEL_42;
        goto LABEL_41;
      }
      if ( v28 != 1 )
      {
LABEL_41:
        v19 = v27;
        goto LABEL_42;
      }
      *a4 = 1;
    }
LABEL_42:
    if ( a1 )
      return (unsigned int)v19;
LABEL_48:
    if ( Handle )
      NtClose(Handle);
    return (unsigned int)v19;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180013ed0  push    rbp
0x180013ed2  push    rbx
0x180013ed3  push    rdi
0x180013ed4  push    r12
0x180013ed6  push    r13
0x180013ed8  push    r14
0x180013eda  push    r15
0x180013edc  lea     rbp, [rsp-150h]
0x180013ee4  sub     rsp, 250h
0x180013eeb  mov     rax, cs:__security_cookie
0x180013ef2  xor     rax, rsp
0x180013ef5  mov     [rbp+180h+var_38], rax
0x180013efc  mov     r15d, r8d
0x180013eff  mov     rdi, rdx
0x180013f02  mov     r14, rcx
0x180013f05  xor     r13d, r13d
0x180013f08  xor     edx, edx; Val
0x180013f0a  mov     [rsp+280h+var_238], r13d
0x180013f0f  mov     r8d, 44h ; 'D'; Size
0x180013f15  mov     [rsp+280h+var_23C], r13d
0x180013f1a  lea     rcx, [rbp+180h+Src]; void *
0x180013f21  mov     r12, r9
0x180013f24  call    memset$thunk$772440563353939046
0x180013f29  xor     edx, edx; Val
0x180013f2b  lea     rcx, [rbp+180h+var_1B0]; void *
0x180013f2f  mov     r8d, 0ECh; Size
0x180013f35  call    memset$thunk$772440563353939046
0x180013f3a  xor     eax, eax
0x180013f3c  mov     [rsp+280h+Handle], r13
0x180013f41  mov     [rsp+280h+var_240], r13d
0x180013f46  xorps   xmm0, xmm0
0x180013f49  mov     [rbp+180h+var_1C8], rax
0x180013f4d  mov     [rbp+180h+var_1C0], eax
0x180013f50  mov     [rbp+180h+var_200], rax
0x180013f54  mov     [rsp+280h+var_228], r13
0x180013f59  mov     [r12], al
0x180013f5d  movups  [rbp+180h+var_1E8], xmm0
0x180013f61  movups  [rbp+180h+var_1E8+0Ch], xmm0
0x180013f65  movups  [rbp+180h+var_1F8], xmm0
0x180013f69  movups  [rsp+280h+var_220], xmm0
0x180013f6e  movups  [rsp+280h+var_210], xmm0
0x180013f73  test    r15d, 0FFFFFFFCh
0x180013f7a  jnz     loc_1800143A1
0x180013f80  mov     [rsp+280h+arg_10], rsi
0x180013f88  mov     esi, 2
0x180013f8d  test    r14, r14
0x180013f90  jz      loc_180014264
0x180013f96  mov     [rsp+280h+Handle], r14
0x180013f9b  xorps   xmm0, xmm0
0x180013f9e  xor     eax, eax
0x180013fa0  mov     [rbp+180h+var_200], rax
0x180013fa4  movups  [rsp+280h+var_220], xmm0
0x180013fa9  mov     byte ptr [rsp+280h+var_220], 1
0x180013fae  mov     qword ptr [rsp+280h+var_220+8], r13
0x180013fb3  movups  [rsp+280h+var_210], xmm0
0x180013fb8  test    rdi, rdi
0x180013fbb  jz      loc_180014432
0x180013fc1  mov     qword ptr [rsp+280h+var_220+8], rdi
0x180013fc6  mov     qword ptr [rsp+280h+var_210], rdi
0x180013fcb  mov     rcx, rdi
0x180013fce  mov     word ptr [rsp+280h+var_220+2], r13w
0x180013fd4  mov     [rbp+180h+var_1B0], 0EC0002h
0x180013fdc  call    RtlValidSid
0x180013fe1  test    al, al
0x180013fe3  jz      loc_180014097
0x180013fe9  movzx   ecx, byte ptr [rbp+180h+var_1B0]
0x180013fed  cmp     cl, 4
0x180013ff0  ja      loc_180014097
0x180013ff6  cmp     cl, sil
0x180013ff9  mov     ebx, esi
0x180013ffb  cmova   ebx, ecx
0x180013ffe  lea     rcx, [rbp+180h+var_1B0]
0x180014002  call    RtlValidAcl
0x180014007  test    al, al
0x180014009  jz      loc_180014097
0x18001400f  movzx   r9d, word ptr [rbp+180h+var_1B0+4]
0x180014014  lea     rcx, [rbp+180h+var_1A8]
0x180014018  movzx   r10d, word ptr [rbp+180h+var_1B0+2]
0x18001401d  mov     r8d, r13d
0x180014020  cmp     r8d, r9d
0x180014023  jnb     short loc_18001403D
0x180014025  lea     rdx, [rbp+180h+var_1B0]
0x180014029  add     rdx, r10
0x18001402c  cmp     rcx, rdx
0x18001402f  jnb     short loc_180014097
0x180014031  movzx   eax, word ptr [rcx+2]
0x180014035  inc     r8d
0x180014038  add     rcx, rax
0x18001403b  jmp     short loc_180014020
0x18001403d  lea     r8, [rbp+180h+var_1B0]
0x180014041  add     r8, r10
0x180014044  cmp     rcx, r8
0x180014047  ja      short loc_180014097
0x180014049  test    rcx, rcx
0x18001404c  jz      short loc_180014097
0x18001404e  movzx   eax, byte ptr [rdi+1]
0x180014052  add     ax, 4
0x180014056  shl     ax, 2
0x18001405a  movzx   r9d, ax
0x18001405e  lea     rax, [rcx+r9]
0x180014062  cmp     rax, r8
0x180014065  ja      short loc_180014097
0x180014067  mov     [rcx], r13w
0x18001406b  mov     rdx, rdi; Src
0x18001406e  mov     [rcx+2], r9w
0x180014073  mov     dword ptr [rcx+4], 1
0x18001407a  add     rcx, 8; void *
0x18001407e  movzx   r8d, byte ptr [rdi+1]
0x180014083  lea     r8, ds:8[r8*4]; Size
0x18001408b  call    memmove
0x180014090  inc     word ptr [rbp+180h+var_1B0+4]
0x180014094  mov     byte ptr [rbp+180h+var_1B0], bl
0x180014097  test    r15b, 3
0x18001409b  jz      loc_180014189
0x1800140a1  mov     r9d, esi
0x1800140a4  mov     dword ptr [rsp+280h+var_260], 1
0x1800140ac  mov     r8d, esi
0x1800140af  lea     rdx, RtlpAppPackageAuthority
0x1800140b6  lea     rcx, [rbp+180h+Src]
0x1800140bd  call    RtlInitializeSidEx
0x1800140c2  lea     rcx, [rbp+180h+Src]
0x1800140c9  call    RtlValidSid
0x1800140ce  test    al, al
0x1800140d0  jz      loc_180014189
0x1800140d6  movzx   ecx, byte ptr [rbp+180h+var_1B0]
0x1800140da  cmp     cl, 4
0x1800140dd  ja      loc_180014189
0x1800140e3  cmp     cl, sil
0x1800140e6  mov     ebx, esi
0x1800140e8  cmova   ebx, ecx
0x1800140eb  lea     rcx, [rbp+180h+var_1B0]
0x1800140ef  call    RtlValidAcl
0x1800140f4  test    al, al
0x1800140f6  jz      loc_180014189
0x1800140fc  movzx   r10d, word ptr [rbp+180h+var_1B0+4]
0x180014101  lea     rdx, [rbp+180h+var_1A8]
0x180014105  movzx   r9d, word ptr [rbp+180h+var_1B0+2]
0x18001410a  mov     r8d, r13d
0x18001410d  cmp     r8d, r10d
0x180014110  jnb     short loc_18001412A
0x180014112  lea     rcx, [rbp+180h+var_1B0]
0x180014116  add     rcx, r9
0x180014119  cmp     rdx, rcx
0x18001411c  jnb     short loc_180014189
0x18001411e  movzx   eax, word ptr [rdx+2]
0x180014122  inc     r8d
0x180014125  add     rdx, rax
0x180014128  jmp     short loc_18001410D
0x18001412a  lea     r8, [rbp+180h+var_1B0]
0x18001412e  mov     rcx, r13
0x180014131  add     r8, r9
0x180014134  cmp     rdx, r8
0x180014137  ja      short loc_18001413C
0x180014139  mov     rcx, rdx
0x18001413c  test    rcx, rcx
0x18001413f  jz      short loc_180014189
0x180014141  movzx   eax, [rbp+180h+var_BF]
0x180014148  lea     edx, ds:8[rax*4]
0x18001414f  lea     eax, [rdx+8]
0x180014152  movzx   r9d, ax
0x180014156  lea     rax, [rcx+r9]
0x18001415a  cmp     rax, r8
0x18001415d  ja      short loc_180014189
0x18001415f  mov     [rcx], r13w
0x180014163  mov     [rcx+2], r9w
0x180014168  mov     dword ptr [rcx+4], 1
0x18001416f  add     rcx, 8; void *
0x180014173  mov     r8d, edx; Size
0x180014176  lea     rdx, [rbp+180h+Src]; Src
0x18001417d  call    memmove
0x180014182  inc     word ptr [rbp+180h+var_1B0+4]
0x180014186  mov     byte ptr [rbp+180h+var_1B0], bl
0x180014189  test    sil, r15b
0x18001418c  jnz     loc_1800142AE
0x180014192  cmp     byte ptr [rsp+280h+var_220], 1
0x180014197  jnz     short loc_1800141BC
0x180014199  movzx   eax, word ptr [rsp+280h+var_220+2]
0x18001419e  test    ax, ax
0x1800141a1  js      short loc_1800141BC
0x1800141a3  lea     rcx, [rbp+180h+var_1B0]
0x1800141a7  mov     [rbp+180h+var_200], rcx
0x1800141ab  mov     ecx, 0FFF7h
0x1800141b0  and     ax, cx
0x1800141b3  or      ax, 4
0x1800141b7  mov     word ptr [rsp+280h+var_220+2], ax
0x1800141bc  mov     rdx, [rsp+280h+Handle]
0x1800141c1  lea     rax, [rsp+280h+var_23C]
0x1800141c6  mov     [rsp+280h+var_248], rax
0x1800141cb  lea     r9, RtlpCheckTokenMembershipGenericMapping
0x1800141d2  lea     rax, [rsp+280h+var_238]
0x1800141d7  mov     [rsp+280h+var_240], 38h ; '8'
0x1800141df  mov     [rsp+280h+var_250], rax
0x1800141e4  lea     rcx, [rsp+280h+var_220]
0x1800141e9  lea     rax, [rsp+280h+var_240]
0x1800141ee  mov     r8d, 1
0x1800141f4  mov     [rsp+280h+var_258], rax
0x1800141f9  lea     rax, [rbp+180h+var_70]
0x180014200  mov     [rsp+280h+var_260], rax
0x180014205  call    ZwAccessCheck
0x18001420a  mov     ebx, eax
0x18001420c  test    eax, eax
0x18001420e  js      short loc_180014224
0x180014210  mov     eax, [rsp+280h+var_23C]
0x180014214  mov     ebx, r13d
0x180014217  test    eax, eax
0x180014219  jz      short loc_180014256
0x18001421b  cmp     eax, 0C0000022h
0x180014220  jz      short loc_180014224
0x180014222  mov     ebx, eax
0x180014224  test    r14, r14
0x180014227  jz      short loc_18001429A
0x180014229  mov     rsi, [rsp+280h+arg_10]
0x180014231  mov     eax, ebx
0x180014233  mov     rcx, [rbp+180h+var_38]
0x18001423a  xor     rcx, rsp; StackCookie
0x18001423d  call    __security_check_cookie
0x180014242  add     rsp, 250h
0x180014249  pop     r15
0x18001424b  pop     r14
0x18001424d  pop     r13
0x18001424f  pop     r12
0x180014251  pop     rdi
0x180014252  pop     rbx
0x180014253  pop     rbp
0x180014254  retn
0x180014256  cmp     [rsp+280h+var_238], 1
0x18001425b  jnz     short loc_180014222
0x18001425d  mov     byte ptr [r12], 1
0x180014262  jmp     short loc_180014224
0x180014264  lea     rax, [rsp+280h+Handle]
0x180014269  xor     r9d, r9d
0x18001426c  xor     r8d, r8d
0x18001426f  mov     [rsp+280h+var_260], rax
0x180014274  mov     edx, 8
0x180014279  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180014280  call    NtOpenThreadTokenEx
0x180014285  mov     ebx, eax
0x180014287  cmp     eax, 0C000007Ch
0x18001428c  jz      loc_1800143AB
0x180014292  test    ebx, ebx
0x180014294  jns     loc_180013F9B
0x18001429a  mov     rcx, [rsp+280h+Handle]; Handle
0x18001429f  test    rcx, rcx
0x1800142a2  jz      short loc_180014229
0x1800142a4  call    NtClose
0x1800142a9  jmp     loc_180014229
0x1800142ae  mov     r9d, esi
0x1800142b1  mov     dword ptr [rsp+280h+var_260], esi
0x1800142b5  mov     r8d, esi
0x1800142b8  lea     rdx, RtlpAppPackageAuthority
0x1800142bf  lea     rcx, [rbp+180h+Src]
0x1800142c6  call    RtlInitializeSidEx
0x1800142cb  lea     rcx, [rbp+180h+Src]
0x1800142d2  call    RtlValidSid
0x1800142d7  test    al, al
0x1800142d9  jz      loc_180014192
0x1800142df  movzx   ecx, byte ptr [rbp+180h+var_1B0]
0x1800142e3  cmp     cl, 4
0x1800142e6  ja      loc_180014192
0x1800142ec  cmp     cl, sil
0x1800142ef  cmova   esi, ecx
0x1800142f2  lea     rcx, [rbp+180h+var_1B0]
0x1800142f6  call    RtlValidAcl
0x1800142fb  test    al, al
0x1800142fd  jz      loc_180014192
0x180014303  movzx   r9d, word ptr [rbp+180h+var_1B0+4]
0x180014308  lea     r8, [rbp+180h+var_1A8]
0x18001430c  movzx   r10d, word ptr [rbp+180h+var_1B0+2]
0x180014311  mov     edx, r13d
0x180014314  cmp     edx, r9d
0x180014317  jnb     short loc_180014335
0x180014319  lea     rcx, [rbp+180h+var_1B0]
0x18001431d  add     rcx, r10
0x180014320  cmp     r8, rcx
0x180014323  jnb     loc_180014192
0x180014329  movzx   eax, word ptr [r8+2]
0x18001432e  inc     edx
0x180014330  add     r8, rax
0x180014333  jmp     short loc_180014314
0x180014335  lea     rdx, [rbp+180h+var_1B0]
0x180014339  mov     rcx, r13
0x18001433c  add     rdx, r10
0x18001433f  cmp     r8, rdx
0x180014342  ja      short loc_180014347
0x180014344  mov     rcx, r8
0x180014347  test    rcx, rcx
0x18001434a  jz      loc_180014192
0x180014350  movzx   eax, [rbp+180h+var_BF]
0x180014357  lea     r8d, ds:8[rax*4]; Size
0x18001435f  lea     eax, [r8+8]
0x180014363  movzx   r9d, ax
0x180014367  lea     rax, [rcx+r9]
0x18001436b  cmp     rax, rdx
0x18001436e  ja      loc_180014192
0x180014374  mov     [rcx], r13w
0x180014378  lea     rdx, [rbp+180h+Src]; Src
0x18001437f  mov     [rcx+2], r9w
0x180014384  mov     dword ptr [rcx+4], 1
0x18001438b  add     rcx, 8; void *
0x18001438f  call    memmove
  ... truncated ...
```
