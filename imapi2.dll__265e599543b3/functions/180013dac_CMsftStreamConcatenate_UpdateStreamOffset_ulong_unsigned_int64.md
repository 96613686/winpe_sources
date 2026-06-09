# CMsftStreamConcatenate::UpdateStreamOffset(ulong,unsigned __int64)

- ea: `0x180013dac`
- end: `0x1800140cb`
- name: `?UpdateStreamOffset@CMsftStreamConcatenate@@AEAAJK_K@Z`
- size: `799`
- prototype: `__int64 __fastcall(CMsftStreamConcatenate *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000d084`

## callees

- `0x180013dac`
- `0x180014134`
- `0x1800142d4`
- `0x180014354`
- `0x180049880`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftStreamConcatenate::UpdateStreamOffset(
        CMsftStreamConcatenate *this,
        unsigned int a2,
        unsigned __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // r15
  int v7; // ebx
  unsigned __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v12; // r14
  unsigned int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int v16[4]; // [rsp+50h] [rbp-848h] BYREF
  _BYTE v17[2048]; // [rsp+60h] [rbp-838h] BYREF

  v3 = *((unsigned int *)this + 16);
  v5 = a2;
  if ( a2 >= (unsigned int)v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 62), 24, &WPP_47ba174de9f13fae433aca4eb423b804_Traceguids, v3, a2);
    }
    return (unsigned int)-2147024809;
  }
  v7 = 0;
  v8 = *(_QWORD *)(*((_QWORD *)this + 11) + 8LL * a2);
  if ( a3 == v8 )
    return (unsigned int)v7;
  if ( *((_BYTE *)this + 48) )
  {
    *(_QWORD *)v16 = ~a3;
    v9 = *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * a2);
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, unsigned int *))(*(_QWORD *)v9 + 40LL))(
           v9,
           a3,
           0,
           v16);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
      {
        WPP_SF_iidii(
          *((_QWORD *)WPP_GLOBAL_Control + 62),
          25,
          WPP_GLOBAL_Control,
          a3,
          a3,
          v5,
          *(_QWORD *)v16,
          *(_QWORD *)v16);
      }
      return (unsigned int)v7;
    }
    v10 = *(_QWORD *)v16;
    if ( a3 == *(_QWORD *)v16 )
    {
      *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v5) = *(_QWORD *)v16;
      return (unsigned int)v7;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
    {
      WPP_SF_iidii(
        *((_QWORD *)WPP_GLOBAL_Control + 62),
        26,
        WPP_GLOBAL_Control,
        a3,
        a3,
        v5,
        *(_QWORD *)v16,
        *(_QWORD *)v16);
      v10 = *(_QWORD *)v16;
    }
    *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v5) = v10;
    return (unsigned int)-2147467259;
  }
  if ( a3 <= v8 )
    return (unsigned int)-2147467259;
  v12 = v8 - a3;
  if ( v12 )
  {
    while ( 1 )
    {
      v13 = 2048;
      if ( v12 <= 0x800 )
        v13 = v12;
      v16[0] = ~v13;
      v14 = *(_QWORD *)(*((_QWORD *)this + 9) + 8 * v5);
      v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, unsigned int *))(*(_QWORD *)v14 + 24LL))(
             v14,
             v17,
             v13,
             v16);
      if ( v7 < 0 )
        break;
      v15 = v16[0];
      if ( v13 != v16[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
        {
          WPP_SF_iidiiii(*((_QWORD *)WPP_GLOBAL_Control + 62), 28);
          v15 = v16[0];
        }
        *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v5) += v15;
        return (unsigned int)-2147467259;
      }
      *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v5) += v16[0];
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
    {
      WPP_SF_iidiiii(*((_QWORD *)WPP_GLOBAL_Control + 62), 27);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013dac  mov     [rsp+arg_18], rbx
0x180013db1  push    rbp
0x180013db2  push    rsi
0x180013db3  push    rdi
0x180013db4  push    r14
0x180013db6  push    r15
0x180013db8  sub     rsp, 870h
0x180013dbf  mov     rax, cs:__security_cookie
0x180013dc6  xor     rax, rsp
0x180013dc9  mov     [rsp+898h+var_38], rax
0x180013dd1  mov     r9d, [rcx+40h]
0x180013dd5  mov     rdi, r8
0x180013dd8  mov     r15d, edx
0x180013ddb  mov     rsi, rcx
0x180013dde  cmp     edx, r9d
0x180013de1  jb      short loc_180013E2F
0x180013de3  mov     rax, cs:WPP_GLOBAL_Control
0x180013dea  lea     rcx, WPP_GLOBAL_Control
0x180013df1  cmp     rax, rcx
0x180013df4  jz      short loc_180013E25
0x180013df6  test    byte ptr [rax+1FCh], 4
0x180013dfd  jz      short loc_180013E25
0x180013dff  cmp     byte ptr [rax+1F9h], 3
0x180013e06  jb      short loc_180013E25
0x180013e08  mov     rcx, [rax+1F0h]
0x180013e0f  lea     r8, WPP_47ba174de9f13fae433aca4eb423b804_Traceguids
0x180013e16  mov     edx, 18h
0x180013e1b  mov     dword ptr [rsp+898h+var_878], r15d
0x180013e20  call    WPP_SF_Dd
0x180013e25  mov     ebx, 80070057h
0x180013e2a  jmp     loc_180013F4C
0x180013e2f  mov     rax, [rcx+58h]
0x180013e33  xor     ebx, ebx
0x180013e35  mov     r14, [rax+r15*8]
0x180013e39  cmp     rdi, r14
0x180013e3c  jz      loc_180013F4C
0x180013e42  cmp     [rcx+30h], bl
0x180013e45  jz      loc_180013F7F
0x180013e4b  mov     rax, rdi
0x180013e4e  lea     r9, [rsp+898h+var_848]
0x180013e53  not     rax
0x180013e56  xor     r8d, r8d
0x180013e59  mov     qword ptr [rsp+898h+var_848], rax
0x180013e5e  mov     rdx, rdi
0x180013e61  mov     rax, [rcx+48h]
0x180013e65  mov     rcx, [rax+r15*8]
0x180013e69  mov     rax, [rcx]
0x180013e6c  mov     rax, [rax+28h]
0x180013e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e75  mov     ebx, eax
0x180013e77  test    eax, eax
0x180013e79  jns     short loc_180013EDD
0x180013e7b  mov     r8, cs:WPP_GLOBAL_Control
0x180013e82  lea     rcx, WPP_GLOBAL_Control
0x180013e89  cmp     r8, rcx
0x180013e8c  jz      loc_180013F4C
0x180013e92  test    byte ptr [r8+1FCh], 4
0x180013e9a  jz      loc_180013F4C
0x180013ea0  cmp     byte ptr [r8+1F9h], 3
0x180013ea8  jb      loc_180013F4C
0x180013eae  mov     rax, qword ptr [rsp+898h+var_848]
0x180013eb3  mov     edx, 19h
0x180013eb8  mov     rcx, [r8+1F0h]
0x180013ebf  mov     r9, rdi
0x180013ec2  mov     [rsp+898h+var_860], rax
0x180013ec7  mov     [rsp+898h+var_868], rax
0x180013ecc  mov     [rsp+898h+var_870], r15d
0x180013ed1  mov     [rsp+898h+var_878], rdi
0x180013ed6  call    WPP_SF_iidii
0x180013edb  jmp     short loc_180013F4C
0x180013edd  mov     rax, qword ptr [rsp+898h+var_848]
0x180013ee2  cmp     rdi, rax
0x180013ee5  jz      loc_180013F75
0x180013eeb  mov     r8, cs:WPP_GLOBAL_Control
0x180013ef2  lea     rcx, WPP_GLOBAL_Control
0x180013ef9  cmp     r8, rcx
0x180013efc  jz      short loc_180013F3F
0x180013efe  test    byte ptr [r8+1FCh], 4
0x180013f06  jz      short loc_180013F3F
0x180013f08  cmp     byte ptr [r8+1F9h], 3
0x180013f10  jb      short loc_180013F3F
0x180013f12  mov     rcx, [r8+1F0h]
0x180013f19  mov     edx, 1Ah
0x180013f1e  mov     [rsp+898h+var_860], rax
0x180013f23  mov     r9, rdi
0x180013f26  mov     [rsp+898h+var_868], rax
0x180013f2b  mov     [rsp+898h+var_870], r15d
0x180013f30  mov     [rsp+898h+var_878], rdi
0x180013f35  call    WPP_SF_iidii
0x180013f3a  mov     rax, qword ptr [rsp+898h+var_848]
0x180013f3f  mov     rcx, [rsi+58h]
0x180013f43  mov     [rcx+r15*8], rax
0x180013f47  mov     ebx, 80004005h
0x180013f4c  mov     eax, ebx
0x180013f4e  mov     rcx, [rsp+898h+var_38]
0x180013f56  xor     rcx, rsp; StackCookie
0x180013f59  call    __security_check_cookie
0x180013f5e  mov     rbx, [rsp+898h+arg_18]
0x180013f66  add     rsp, 870h
0x180013f6d  pop     r15
0x180013f6f  pop     r14
0x180013f71  pop     rdi
0x180013f72  pop     rsi
0x180013f73  pop     rbp
0x180013f74  retn
0x180013f75  mov     rcx, [rsi+58h]
0x180013f79  mov     [rcx+r15*8], rax
0x180013f7d  jmp     short loc_180013F4C
0x180013f7f  cmp     rdi, r14
0x180013f82  jbe     short loc_180013F47
0x180013f84  sub     r14, rdi
0x180013f87  jz      short loc_180013F4C
0x180013f89  mov     edi, 800h
0x180013f8e  cmp     r14, 800h
0x180013f95  ja      short loc_180013F9A
0x180013f97  mov     edi, r14d
0x180013f9a  mov     eax, edi
0x180013f9c  lea     r9, [rsp+898h+var_848]
0x180013fa1  not     eax
0x180013fa3  lea     rdx, [rsp+898h+var_838]
0x180013fa8  mov     [rsp+898h+var_848], eax
0x180013fac  mov     r8d, edi
0x180013faf  mov     rax, [rsi+48h]
0x180013fb3  mov     rcx, [rax+r15*8]
0x180013fb7  mov     rax, [rcx]
0x180013fba  mov     rax, [rax+18h]
0x180013fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc3  mov     ebx, eax
0x180013fc5  test    eax, eax
0x180013fc7  js      loc_180014054
0x180013fcd  mov     eax, [rsp+898h+var_848]
0x180013fd1  cmp     edi, eax
0x180013fd3  jnz     short loc_180013FDF
0x180013fd5  mov     rcx, [rsi+58h]
0x180013fd9  add     [rcx+r15*8], rax
0x180013fdd  jmp     short loc_180013F89
0x180013fdf  mov     r11, cs:WPP_GLOBAL_Control
0x180013fe6  lea     rcx, WPP_GLOBAL_Control
0x180013fed  cmp     r11, rcx
0x180013ff0  jz      short loc_180014047
0x180013ff2  test    byte ptr [r11+1FCh], 4
0x180013ffa  jz      short loc_180014047
0x180013ffc  cmp     byte ptr [r11+1F9h], 3
0x180014004  jb      short loc_180014047
0x180014006  mov     rcx, [r11+1F0h]
0x18001400d  mov     r8, rax
0x180014010  mov     rax, [rsi+58h]
0x180014014  mov     edx, 1Ch
0x180014019  mov     [rsp+898h+var_850], r8
0x18001401e  mov     [rsp+898h+var_858], r8
0x180014023  mov     r9d, edi
0x180014026  mov     r10, [rax+r15*8]
0x18001402a  mov     [rsp+898h+var_860], r10
0x18001402f  mov     [rsp+898h+var_868], r10
0x180014034  mov     [rsp+898h+var_870], r15d
0x180014039  mov     [rsp+898h+var_878], r9
0x18001403e  call    WPP_SF_iidiiii
0x180014043  mov     eax, [rsp+898h+var_848]
0x180014047  mov     rcx, [rsi+58h]
0x18001404b  add     [rcx+r15*8], rax
0x18001404f  jmp     loc_180013F47
0x180014054  mov     r11, cs:WPP_GLOBAL_Control
0x18001405b  lea     rcx, WPP_GLOBAL_Control
0x180014062  cmp     r11, rcx
0x180014065  jz      loc_180013F4C
0x18001406b  test    byte ptr [r11+1FCh], 4
0x180014073  jz      loc_180013F4C
0x180014079  cmp     byte ptr [r11+1F9h], 3
0x180014081  jb      loc_180013F4C
0x180014087  mov     r8d, [rsp+898h+var_848]
0x18001408c  mov     edx, 1Bh
0x180014091  mov     rax, [rsi+58h]
0x180014095  mov     rcx, [r11+1F0h]
0x18001409c  mov     [rsp+898h+var_850], r8
0x1800140a1  mov     [rsp+898h+var_858], r8
0x1800140a6  mov     r10, [rax+r15*8]
0x1800140aa  mov     [rsp+898h+var_860], r10
0x1800140af  mov     [rsp+898h+var_868], r10
0x1800140b4  mov     r9d, edi
0x1800140b7  mov     [rsp+898h+var_870], r15d
0x1800140bc  mov     [rsp+898h+var_878], r9
0x1800140c1  call    WPP_SF_iidiiii
0x1800140c6  jmp     loc_180013F4C
```
