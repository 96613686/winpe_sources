# DevAuthPesudoRandomFunction

- ea: `0x180002888`
- end: `0x1800029ed`
- name: `DevAuthPesudoRandomFunction`
- size: `357`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *, size_t Size)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180001d38`
- `0x180001e04`
- `0x180002348`
- `0x180002444`
- `0x180003d00`
- `0x180003e20`
- `0x180004368`
- `0x1800049c4`

## callees

- `0x180002740`
- `0x180002888`
- `0x1800067e0`
- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall DevAuthPesudoRandomFunction(__int64 a1, int a2, int a3, __int64 a4, int a5, _OWORD *a6, size_t Size)
{
  __int64 v9; // rax
  unsigned int v11; // ebx
  unsigned int v12; // esi
  int v14; // [rsp+40h] [rbp-51h] BYREF
  _DWORD v15[3]; // [rsp+44h] [rbp-4Dh] BYREF
  _BYTE *v16; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v17[2]; // [rsp+58h] [rbp-39h] BYREF
  _OWORD Src[2]; // [rsp+68h] [rbp-29h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp-9h] BYREF

  v16 = v19;
  v9 = -1;
  v14 = 32;
  v17[0] = a1;
  do
    ++v9;
  while ( *(_BYTE *)(a1 + v9) );
  v15[0] = v9;
  v15[1] = a5;
  v17[1] = a4;
  if ( !(unsigned int)DevAuthGetHashAllInOne(a2, a3, (unsigned int)v17, (unsigned int)v15, 2, (__int64)v19)
    || !(unsigned int)DevAuthGetHashAllInOne(a2, a3, (unsigned int)&v16, (unsigned int)&v14, 3, (__int64)Src) )
  {
    return 0;
  }
  v11 = Size;
  v12 = 0;
  while ( v11 > 0x20 )
  {
    *a6 = Src[0];
    a6[1] = Src[1];
    if ( !(unsigned int)DevAuthGetHashAllInOne(a2, a3, (unsigned int)&v16, (unsigned int)&v14, 1, (__int64)v19)
      || !(unsigned int)DevAuthGetHashAllInOne(a2, a3, (unsigned int)&v16, (unsigned int)&v14, 3, (__int64)Src) )
    {
      return v12;
    }
    a6 += 2;
    v11 -= 32;
  }
  memmove(a6, Src, v11);
  return 1;
}

```

## disassembly

```asm
0x180002888  mov     [rsp-8+arg_0], rbx
0x18000288d  push    rbp
0x18000288e  push    rsi
0x18000288f  push    rdi
0x180002890  push    r14
0x180002892  push    r15
0x180002894  lea     rbp, [rsp-1Fh]
0x180002899  sub     rsp, 0B0h
0x1800028a0  mov     rax, cs:__security_cookie
0x1800028a7  xor     rax, rsp
0x1800028aa  mov     [rbp+3Fh+var_28], rax
0x1800028ae  mov     rdi, [rbp+3Fh+arg_28]
0x1800028b2  lea     rax, [rbp+3Fh+var_48]
0x1800028b6  mov     [rbp+3Fh+var_80], rax
0x1800028ba  mov     r15d, r8d
0x1800028bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800028c1  mov     [rbp+3Fh+var_90], 20h ; ' '
0x1800028c8  mov     r14, rdx
0x1800028cb  mov     [rbp+3Fh+var_78], rcx
0x1800028cf  inc     rax
0x1800028d2  cmp     byte ptr [rcx+rax], 0
0x1800028d6  jnz     short loc_1800028CF
0x1800028d8  mov     [rbp+3Fh+var_8C], eax
0x1800028db  lea     r8, [rbp+3Fh+var_78]
0x1800028df  mov     eax, [rbp+3Fh+arg_20]
0x1800028e2  mov     edx, r15d
0x1800028e5  mov     [rbp+3Fh+var_88], eax
0x1800028e8  mov     rcx, r14
0x1800028eb  lea     rax, [rbp+3Fh+var_48]
0x1800028ef  mov     [rbp+3Fh+var_70], r9
0x1800028f3  mov     [rsp+0D0h+var_A8], rax
0x1800028f8  lea     r9, [rbp+3Fh+var_8C]
0x1800028fc  mov     [rsp+0D0h+var_B0], 2
0x180002904  call    DevAuthGetHashAllInOne
0x180002909  test    eax, eax
0x18000290b  jz      loc_1800029C7
0x180002911  lea     rax, [rbp+3Fh+Src]
0x180002915  mov     edx, r15d
0x180002918  mov     [rsp+0D0h+var_A8], rax
0x18000291d  lea     r9, [rbp+3Fh+var_90]
0x180002921  lea     r8, [rbp+3Fh+var_80]
0x180002925  mov     [rsp+0D0h+var_B0], 3
0x18000292d  mov     rcx, r14
0x180002930  call    DevAuthGetHashAllInOne
0x180002935  test    eax, eax
0x180002937  jz      loc_1800029C7
0x18000293d  mov     ebx, dword ptr [rbp+3Fh+Size]
0x180002940  xor     esi, esi
0x180002942  cmp     ebx, 20h ; ' '
0x180002945  jbe     short loc_1800029AF
0x180002947  movups  xmm0, [rbp+3Fh+Src]
0x18000294b  lea     rax, [rbp+3Fh+var_48]
0x18000294f  mov     edx, r15d
0x180002952  mov     [rsp+0D0h+var_A8], rax
0x180002957  lea     r9, [rbp+3Fh+var_90]
0x18000295b  movups  xmmword ptr [rdi], xmm0
0x18000295e  lea     r8, [rbp+3Fh+var_80]
0x180002962  mov     rcx, r14
0x180002965  movups  xmm1, [rbp+3Fh+var_58]
0x180002969  mov     [rsp+0D0h+var_B0], 1
0x180002971  movups  xmmword ptr [rdi+10h], xmm1
0x180002975  call    DevAuthGetHashAllInOne
0x18000297a  test    eax, eax
0x18000297c  jz      short loc_1800029C3
0x18000297e  lea     rax, [rbp+3Fh+Src]
0x180002982  mov     edx, r15d
0x180002985  mov     [rsp+0D0h+var_A8], rax
0x18000298a  lea     r9, [rbp+3Fh+var_90]
0x18000298e  lea     r8, [rbp+3Fh+var_80]
0x180002992  mov     [rsp+0D0h+var_B0], 3
0x18000299a  mov     rcx, r14
0x18000299d  call    DevAuthGetHashAllInOne
0x1800029a2  test    eax, eax
0x1800029a4  jz      short loc_1800029C3
0x1800029a6  add     rdi, 20h ; ' '
0x1800029aa  add     ebx, 0FFFFFFE0h
0x1800029ad  jmp     short loc_180002942
0x1800029af  mov     r8d, ebx; Size
0x1800029b2  lea     rdx, [rbp+3Fh+Src]; Src
0x1800029b6  mov     rcx, rdi; void *
0x1800029b9  call    memmove
0x1800029be  mov     esi, 1
0x1800029c3  mov     eax, esi
0x1800029c5  jmp     short loc_1800029C9
0x1800029c7  xor     eax, eax
0x1800029c9  mov     rcx, [rbp+3Fh+var_28]
0x1800029cd  xor     rcx, rsp; StackCookie
0x1800029d0  call    __security_check_cookie
0x1800029d5  mov     rbx, [rsp+0D0h+arg_0]
0x1800029dd  add     rsp, 0B0h
0x1800029e4  pop     r15
0x1800029e6  pop     r14
0x1800029e8  pop     rdi
0x1800029e9  pop     rsi
0x1800029ea  pop     rbp
0x1800029eb  retn
```
