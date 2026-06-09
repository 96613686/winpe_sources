# Imapi2Utility::GetStreamSizeAndSeekAbility(IStream *,unsigned __int64 *,uchar *)

- ea: `0x1800443a8`
- end: `0x1800445a8`
- name: `?GetStreamSizeAndSeekAbility@Imapi2Utility@@YAJPEAUIStream@@PEA_KPEAE@Z`
- size: `512`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IStream *, unsigned __int64 *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180012100`
- `0x180014ab0`
- `0x180040d54`

## callees

- `0x1800140f4`
- `0x1800443a8`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetStreamSizeAndSeekAbility(
        Imapi2Utility *this,
        struct IStream *a2,
        unsigned __int64 *a3,
        unsigned __int8 *a4)
{
  unsigned int v4; // edi
  __int64 v6; // rax
  int v9; // eax
  __int64 v10; // r9
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  _QWORD v17[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v18[16]; // [rsp+40h] [rbp-88h] BYREF
  __int64 v19; // [rsp+50h] [rbp-78h]

  v4 = 0;
  *(_QWORD *)a2 = 0;
  *(_BYTE *)a3 = 0;
  v6 = *(_QWORD *)this;
  v17[0] = 0;
  v9 = (*(__int64 (__fastcall **)(Imapi2Utility *, _QWORD, __int64, _QWORD *))(v6 + 40))(this, 0, 2, v17);
  if ( v9 < 0 )
  {
    *(_QWORD *)a2 = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
LABEL_7:
      memset_0(v18, 0, 0x50u);
      if ( (*(int (__fastcall **)(Imapi2Utility *, _BYTE *, __int64))(*(_QWORD *)this + 96LL))(this, v18, 1) >= 0 )
      {
        v15 = v19;
        if ( v19 )
        {
          *(_BYTE *)a3 = 0;
          *(_QWORD *)a2 = v15;
          return v4;
        }
        v10 = 2147942487LL;
        v4 = -2147024809;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v12 = (unsigned int)(v19 + 88);
          goto LABEL_27;
        }
      }
      else
      {
        v10 = 2147942487LL;
        v4 = -2147024809;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v12 = 87;
LABEL_27:
          WPP_SF_d(v11[2], v12, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v10);
          return v4;
        }
      }
      return v4;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
      (unsigned int)v9);
LABEL_6:
    if ( *(_QWORD *)a2 )
      return v4;
    goto LABEL_7;
  }
  v13 = v17[0];
  if ( v17[0] )
  {
    *(_BYTE *)a3 = 1;
    *(_QWORD *)a2 = v13;
    v14 = (*(__int64 (__fastcall **)(Imapi2Utility *, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)this + 40LL))(
            this,
            0,
            0,
            v17);
    if ( v14 < 0 )
    {
      v4 = v14;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v12 = 86;
        v10 = (unsigned int)v14;
        goto LABEL_27;
      }
      return v4;
    }
    goto LABEL_6;
  }
  v10 = 2147942487LL;
  v4 = -2147024809;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v12 = (unsigned int)(LODWORD(v17[0]) + 85);
    goto LABEL_27;
  }
  return v4;
}

```

## disassembly

```asm
0x1800443a8  mov     [rsp+arg_18], rbx
0x1800443ad  push    rsi
0x1800443ae  push    rdi
0x1800443af  push    r13
0x1800443b1  push    r14
0x1800443b3  push    r15
0x1800443b5  sub     rsp, 0A0h
0x1800443bc  mov     rax, cs:__security_cookie
0x1800443c3  xor     rax, rsp
0x1800443c6  mov     [rsp+0C8h+var_38], rax
0x1800443ce  xor     edi, edi
0x1800443d0  lea     r9, [rsp+0C8h+var_98]
0x1800443d5  mov     [rdx], rdi
0x1800443d8  xor     ebx, ebx
0x1800443da  mov     [r8], dil
0x1800443dd  mov     r15, r8
0x1800443e0  mov     rax, [rcx]
0x1800443e3  mov     rsi, rdx
0x1800443e6  lea     r8d, [rdi+2]
0x1800443ea  mov     [rsp+0C8h+var_98], rbx
0x1800443ef  mov     edx, ebx
0x1800443f1  mov     r14, rcx
0x1800443f4  mov     rax, [rax+28h]
0x1800443f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443fd  lea     r13, WPP_GLOBAL_Control
0x180044404  test    eax, eax
0x180044406  jns     loc_1800444AF
0x18004440c  mov     [rsi], rbx
0x18004440f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044416  cmp     rcx, r13
0x180044419  jz      short loc_180044446
0x18004441b  test    byte ptr [rcx+1Ch], 4
0x18004441f  jz      short loc_180044446
0x180044421  cmp     byte ptr [rcx+19h], 4
0x180044425  jb      short loc_180044446
0x180044427  mov     rcx, [rcx+10h]
0x18004442b  lea     edx, [rdi+54h]
0x18004442e  mov     r9d, eax
0x180044431  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044438  call    WPP_SF_d
0x18004443d  cmp     [rsi], rbx
0x180044440  jnz     loc_18004457E
0x180044446  xor     edx, edx; Val
0x180044448  lea     rcx, [rsp+0C8h+var_88]; void *
0x18004444d  lea     r8d, [rdx+50h]; Size
0x180044451  call    memset_0
0x180044456  mov     rax, [r14]
0x180044459  lea     rdx, [rsp+0C8h+var_88]
0x18004445e  mov     r8d, 1
0x180044464  mov     rcx, r14
0x180044467  mov     rax, [rax+60h]
0x18004446b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044470  test    eax, eax
0x180044472  jns     loc_180044538
0x180044478  mov     r9d, 80070057h
0x18004447e  mov     edi, r9d
0x180044481  mov     rcx, cs:WPP_GLOBAL_Control
0x180044488  cmp     rcx, r13
0x18004448b  jz      loc_18004457E
0x180044491  test    byte ptr [rcx+1Ch], 4
0x180044495  jz      loc_18004457E
0x18004449b  cmp     byte ptr [rcx+19h], 3
0x18004449f  jb      loc_18004457E
0x1800444a5  mov     edx, 57h ; 'W'
0x1800444aa  jmp     loc_180044566
0x1800444af  mov     rax, [rsp+0C8h+var_98]
0x1800444b4  test    rax, rax
0x1800444b7  jnz     short loc_1800444EB
0x1800444b9  mov     r9d, 80070057h
0x1800444bf  mov     edi, r9d
0x1800444c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800444c9  cmp     rcx, r13
0x1800444cc  jz      loc_18004457E
0x1800444d2  test    byte ptr [rcx+1Ch], 4
0x1800444d6  jz      loc_18004457E
0x1800444dc  cmp     byte ptr [rcx+19h], 3
0x1800444e0  jb      loc_18004457E
0x1800444e6  lea     edx, [rax+55h]
0x1800444e9  jmp     short loc_180044566
0x1800444eb  mov     byte ptr [r15], 1
0x1800444ef  lea     r9, [rsp+0C8h+var_98]
0x1800444f4  mov     [rsi], rax
0x1800444f7  xor     r8d, r8d
0x1800444fa  mov     rax, [r14]
0x1800444fd  mov     rdx, rbx
0x180044500  mov     rcx, r14
0x180044503  mov     rax, [rax+28h]
0x180044507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004450c  test    eax, eax
0x18004450e  jns     loc_18004443D
0x180044514  mov     edi, eax
0x180044516  mov     rcx, cs:WPP_GLOBAL_Control
0x18004451d  cmp     rcx, r13
0x180044520  jz      short loc_18004457E
0x180044522  test    byte ptr [rcx+1Ch], 4
0x180044526  jz      short loc_18004457E
0x180044528  cmp     byte ptr [rcx+19h], 3
0x18004452c  jb      short loc_18004457E
0x18004452e  mov     edx, 56h ; 'V'
0x180044533  mov     r9d, eax
0x180044536  jmp     short loc_180044566
0x180044538  mov     rax, [rsp+0C8h+var_78]
0x18004453d  test    rax, rax
0x180044540  jnz     short loc_180044578
0x180044542  mov     r9d, 80070057h
0x180044548  mov     edi, r9d
0x18004454b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044552  cmp     rcx, r13
0x180044555  jz      short loc_18004457E
0x180044557  test    byte ptr [rcx+1Ch], 4
0x18004455b  jz      short loc_18004457E
0x18004455d  cmp     byte ptr [rcx+19h], 3
0x180044561  jb      short loc_18004457E
0x180044563  lea     edx, [rax+58h]
0x180044566  mov     rcx, [rcx+10h]
0x18004456a  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044571  call    WPP_SF_d
0x180044576  jmp     short loc_18004457E
0x180044578  mov     [r15], bl
0x18004457b  mov     [rsi], rax
0x18004457e  mov     eax, edi
0x180044580  mov     rcx, [rsp+0C8h+var_38]
0x180044588  xor     rcx, rsp; StackCookie
0x18004458b  call    __security_check_cookie
0x180044590  mov     rbx, [rsp+0C8h+arg_18]
0x180044598  add     rsp, 0A0h
0x18004459f  pop     r15
0x1800445a1  pop     r14
0x1800445a3  pop     r13
0x1800445a5  pop     rdi
0x1800445a6  pop     rsi
0x1800445a7  retn
```
