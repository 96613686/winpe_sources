# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180017d34`
- end: `0x180017e2c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180017284`
- `0x180018304`
- `0x1800186d8`

## callees

- `0x180002c36`
- `0x180017d34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017d71`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017db3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017df2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017d71`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017db3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017df2`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int8 *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  unsigned __int8 *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this, a2, a3) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 4;
    if ( v3 + 4 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = *a2;
  }
LABEL_15:
  v8 = *(_WORD *)v6;
  *((_WORD *)v6 + 4) = *(_WORD *)v6;
  if ( v8 )
    goto LABEL_21;
  if ( v7 + 2 > a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *(_WORD *)v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  v7 += 2;
LABEL_21:
  v9 = &v7[*((unsigned __int16 *)v6 + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)v6 + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180017d34  push    rbx
0x180017d36  push    rbp
0x180017d37  push    rsi
0x180017d38  push    rdi
0x180017d39  push    r14
0x180017d3b  push    r15
0x180017d3d  sub     rsp, 28h
0x180017d41  mov     rax, [rdx]
0x180017d44  xor     r15d, r15d
0x180017d47  cmp     byte ptr [rcx+2], 1
0x180017d4b  mov     rbp, r8
0x180017d4e  mov     r14, rdx
0x180017d51  mov     rdi, rcx
0x180017d54  jnz     short loc_180017D8D
0x180017d56  lea     rbx, [rax+2]
0x180017d5a  cmp     rbx, r8
0x180017d5d  ja      loc_180017E12
0x180017d63  mov     [rcx+10h], rax
0x180017d67  test    rax, rax
0x180017d6a  jz      short loc_180017D71
0x180017d6c  movzx   ecx, word ptr [rax]
0x180017d6f  jmp     short loc_180017D85
0x180017d71  call    cs:__imp__o__errno
0x180017d77  mov     dword ptr [rax], 16h
0x180017d7d  call    _invalid_parameter_noinfo
0x180017d82  mov     ecx, r15d
0x180017d85  movzx   eax, cx
0x180017d88  mov     [rdi+4], eax
0x180017d8b  jmp     short loc_180017DC9
0x180017d8d  cmp     byte ptr [rcx+2], 2
0x180017d91  jnz     short loc_180017DC6
0x180017d93  lea     rbx, [rax+4]
0x180017d97  cmp     rbx, rbp
0x180017d9a  ja      short loc_180017E12
0x180017d9c  mov     [rcx+10h], rax
0x180017da0  add     rcx, 4
0x180017da4  jz      short loc_180017DB3
0x180017da6  test    rax, rax
0x180017da9  jz      short loc_180017DB1
0x180017dab  mov     eax, [rax]
0x180017dad  mov     [rcx], eax
0x180017daf  jmp     short loc_180017DC9
0x180017db1  mov     [rcx], eax
0x180017db3  call    cs:__imp__o__errno
0x180017db9  mov     dword ptr [rax], 16h
0x180017dbf  call    _invalid_parameter_noinfo
0x180017dc4  jmp     short loc_180017DC9
0x180017dc6  mov     rbx, rax
0x180017dc9  movzx   eax, word ptr [rdi]
0x180017dcc  mov     [rdi+8], ax
0x180017dd0  test    ax, ax
0x180017dd3  jnz     short loc_180017E06
0x180017dd5  lea     rsi, [rbx+2]
0x180017dd9  cmp     rsi, rbp
0x180017ddc  ja      short loc_180017E12
0x180017dde  test    rbx, rbx
0x180017de1  jz      short loc_180017DEC
0x180017de3  movzx   eax, word ptr [rbx]
0x180017de6  mov     [rdi+8], ax
0x180017dea  jmp     short loc_180017E03
0x180017dec  xor     eax, eax
0x180017dee  mov     [rdi+8], ax
0x180017df2  call    cs:__imp__o__errno
0x180017df8  mov     dword ptr [rax], 16h
0x180017dfe  call    _invalid_parameter_noinfo
0x180017e03  mov     rbx, rsi
0x180017e06  movzx   ecx, word ptr [rdi+8]
0x180017e0a  add     rcx, rbx
0x180017e0d  cmp     rcx, rbp
0x180017e10  jbe     short loc_180017E16
0x180017e12  xor     al, al
0x180017e14  jmp     short loc_180017E1F
0x180017e16  mov     [rdi+18h], rbx
0x180017e1a  mov     al, 1
0x180017e1c  mov     [r14], rcx
0x180017e1f  add     rsp, 28h
0x180017e23  pop     r15
0x180017e25  pop     r14
0x180017e27  pop     rdi
0x180017e28  pop     rsi
0x180017e29  pop     rbp
0x180017e2a  pop     rbx
0x180017e2b  retn
```
