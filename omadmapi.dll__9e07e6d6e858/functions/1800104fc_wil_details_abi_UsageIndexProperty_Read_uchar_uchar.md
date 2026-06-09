# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800104fc`
- end: `0x18001060b`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `271`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c374`
- `0x180010d9c`
- `0x180011190`

## callees

- `0x180003d26`
- `0x1800104fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010539`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010585`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800105ca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010539`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010585`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800105ca`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v7; // rbx
  unsigned __int16 v8; // cx
  _DWORD *v9; // rcx
  __int16 v10; // ax
  unsigned __int8 *v11; // rcx
  bool result; // al

  v3 = (unsigned __int16 *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v8 = *v3;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v8 = 0;
    }
    *((_DWORD *)this + 1) = v8;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    v9 = (_DWORD *)((char *)this + 4);
    if ( v9 )
    {
      if ( v3 )
      {
        *v9 = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *v9 = 0;
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = (unsigned __int16 *)*a2;
  }
LABEL_15:
  v10 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v10 )
    goto LABEL_21;
  if ( v7 + 1 > (unsigned __int16 *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)this + 4) = *v7;
  }
  else
  {
    *((_WORD *)this + 4) = 0;
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v11 = (unsigned __int8 *)v7 + *((unsigned __int16 *)this + 4);
  if ( v11 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v11;
  return result;
}

```

## disassembly

```asm
0x1800104fc  push    rbx
0x1800104fe  push    rbp
0x1800104ff  push    rsi
0x180010500  push    rdi
0x180010501  push    r14
0x180010503  push    r15
0x180010505  sub     rsp, 28h
0x180010509  mov     rax, [rdx]
0x18001050c  xor     r15d, r15d
0x18001050f  cmp     byte ptr [rcx+2], 1
0x180010513  mov     rbp, r8
0x180010516  mov     r14, rdx
0x180010519  mov     rdi, rcx
0x18001051c  jnz     short loc_18001055B
0x18001051e  lea     rbx, [rax+2]
0x180010522  cmp     rbx, r8
0x180010525  ja      loc_1800105F0
0x18001052b  mov     [rcx+10h], rax
0x18001052f  test    rax, rax
0x180010532  jz      short loc_180010539
0x180010534  movzx   ecx, word ptr [rax]
0x180010537  jmp     short loc_180010553
0x180010539  call    cs:__imp__o__errno
0x180010540  nop     dword ptr [rax+rax+00h]
0x180010545  mov     dword ptr [rax], 16h
0x18001054b  call    _invalid_parameter_noinfo
0x180010550  mov     ecx, r15d
0x180010553  movzx   eax, cx
0x180010556  mov     [rdi+4], eax
0x180010559  jmp     short loc_1800105A1
0x18001055b  cmp     byte ptr [rcx+2], 2
0x18001055f  jnz     short loc_18001059E
0x180010561  lea     rbx, [rax+4]
0x180010565  cmp     rbx, rbp
0x180010568  ja      loc_1800105F0
0x18001056e  mov     [rcx+10h], rax
0x180010572  add     rcx, 4
0x180010576  jz      short loc_180010585
0x180010578  test    rax, rax
0x18001057b  jz      short loc_180010583
0x18001057d  mov     eax, [rax]
0x18001057f  mov     [rcx], eax
0x180010581  jmp     short loc_1800105A1
0x180010583  mov     [rcx], eax
0x180010585  call    cs:__imp__o__errno
0x18001058c  nop     dword ptr [rax+rax+00h]
0x180010591  mov     dword ptr [rax], 16h
0x180010597  call    _invalid_parameter_noinfo
0x18001059c  jmp     short loc_1800105A1
0x18001059e  mov     rbx, rax
0x1800105a1  movzx   eax, word ptr [rdi]
0x1800105a4  mov     [rdi+8], ax
0x1800105a8  test    ax, ax
0x1800105ab  jnz     short loc_1800105E4
0x1800105ad  lea     rsi, [rbx+2]
0x1800105b1  cmp     rsi, rbp
0x1800105b4  ja      short loc_1800105F0
0x1800105b6  test    rbx, rbx
0x1800105b9  jz      short loc_1800105C4
0x1800105bb  movzx   eax, word ptr [rbx]
0x1800105be  mov     [rdi+8], ax
0x1800105c2  jmp     short loc_1800105E1
0x1800105c4  xor     eax, eax
0x1800105c6  mov     [rdi+8], ax
0x1800105ca  call    cs:__imp__o__errno
0x1800105d1  nop     dword ptr [rax+rax+00h]
0x1800105d6  mov     dword ptr [rax], 16h
0x1800105dc  call    _invalid_parameter_noinfo
0x1800105e1  mov     rbx, rsi
0x1800105e4  movzx   ecx, word ptr [rdi+8]
0x1800105e8  add     rcx, rbx
0x1800105eb  cmp     rcx, rbp
0x1800105ee  jbe     short loc_1800105F4
0x1800105f0  xor     al, al
0x1800105f2  jmp     short loc_1800105FD
0x1800105f4  mov     [rdi+18h], rbx
0x1800105f8  mov     al, 1
0x1800105fa  mov     [r14], rcx
0x1800105fd  add     rsp, 28h
0x180010601  pop     r15
0x180010603  pop     r14
0x180010605  pop     rdi
0x180010606  pop     rsi
0x180010607  pop     rbp
0x180010608  pop     rbx
0x180010609  retn
```
