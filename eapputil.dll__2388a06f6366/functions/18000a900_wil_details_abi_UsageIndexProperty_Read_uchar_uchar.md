# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a900`
- end: `0x18000a9f8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a0a0`
- `0x18000b0d8`
- `0x18000b4ac`

## callees

- `0x180002b1a`
- `0x18000a900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a93d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a97f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a9be`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a93d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a97f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a9be`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  _DWORD *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  _WORD *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = (_WORD *)v3 + 1;
    if ( (unsigned __int8 *)((char *)v3 + 2) > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (_DWORD *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this) = 22;
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
  if ( v7 + 1 > (_WORD *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this) = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v9 = (unsigned __int8 *)v7 + *((unsigned __int16 *)v6 + 4);
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
0x18000a900  push    rbx
0x18000a902  push    rbp
0x18000a903  push    rsi
0x18000a904  push    rdi
0x18000a905  push    r14
0x18000a907  push    r15
0x18000a909  sub     rsp, 28h
0x18000a90d  mov     rax, [rdx]
0x18000a910  xor     r15d, r15d
0x18000a913  cmp     byte ptr [rcx+2], 1
0x18000a917  mov     rbp, r8
0x18000a91a  mov     r14, rdx
0x18000a91d  mov     rdi, rcx
0x18000a920  jnz     short loc_18000A959
0x18000a922  lea     rbx, [rax+2]
0x18000a926  cmp     rbx, r8
0x18000a929  ja      loc_18000A9DE
0x18000a92f  mov     [rcx+10h], rax
0x18000a933  test    rax, rax
0x18000a936  jz      short loc_18000A93D
0x18000a938  movzx   ecx, word ptr [rax]
0x18000a93b  jmp     short loc_18000A951
0x18000a93d  call    cs:__imp__o__errno
0x18000a943  mov     dword ptr [rax], 16h
0x18000a949  call    _invalid_parameter_noinfo
0x18000a94e  mov     ecx, r15d
0x18000a951  movzx   eax, cx
0x18000a954  mov     [rdi+4], eax
0x18000a957  jmp     short loc_18000A995
0x18000a959  cmp     byte ptr [rcx+2], 2
0x18000a95d  jnz     short loc_18000A992
0x18000a95f  lea     rbx, [rax+4]
0x18000a963  cmp     rbx, rbp
0x18000a966  ja      short loc_18000A9DE
0x18000a968  mov     [rcx+10h], rax
0x18000a96c  add     rcx, 4
0x18000a970  jz      short loc_18000A97F
0x18000a972  test    rax, rax
0x18000a975  jz      short loc_18000A97D
0x18000a977  mov     eax, [rax]
0x18000a979  mov     [rcx], eax
0x18000a97b  jmp     short loc_18000A995
0x18000a97d  mov     [rcx], eax
0x18000a97f  call    cs:__imp__o__errno
0x18000a985  mov     dword ptr [rax], 16h
0x18000a98b  call    _invalid_parameter_noinfo
0x18000a990  jmp     short loc_18000A995
0x18000a992  mov     rbx, rax
0x18000a995  movzx   eax, word ptr [rdi]
0x18000a998  mov     [rdi+8], ax
0x18000a99c  test    ax, ax
0x18000a99f  jnz     short loc_18000A9D2
0x18000a9a1  lea     rsi, [rbx+2]
0x18000a9a5  cmp     rsi, rbp
0x18000a9a8  ja      short loc_18000A9DE
0x18000a9aa  test    rbx, rbx
0x18000a9ad  jz      short loc_18000A9B8
0x18000a9af  movzx   eax, word ptr [rbx]
0x18000a9b2  mov     [rdi+8], ax
0x18000a9b6  jmp     short loc_18000A9CF
0x18000a9b8  xor     eax, eax
0x18000a9ba  mov     [rdi+8], ax
0x18000a9be  call    cs:__imp__o__errno
0x18000a9c4  mov     dword ptr [rax], 16h
0x18000a9ca  call    _invalid_parameter_noinfo
0x18000a9cf  mov     rbx, rsi
0x18000a9d2  movzx   ecx, word ptr [rdi+8]
0x18000a9d6  add     rcx, rbx
0x18000a9d9  cmp     rcx, rbp
0x18000a9dc  jbe     short loc_18000A9E2
0x18000a9de  xor     al, al
0x18000a9e0  jmp     short loc_18000A9EB
0x18000a9e2  mov     [rdi+18h], rbx
0x18000a9e6  mov     al, 1
0x18000a9e8  mov     [r14], rcx
0x18000a9eb  add     rsp, 28h
0x18000a9ef  pop     r15
0x18000a9f1  pop     r14
0x18000a9f3  pop     rdi
0x18000a9f4  pop     rsi
0x18000a9f5  pop     rbp
0x18000a9f6  pop     rbx
0x18000a9f7  retn
```
