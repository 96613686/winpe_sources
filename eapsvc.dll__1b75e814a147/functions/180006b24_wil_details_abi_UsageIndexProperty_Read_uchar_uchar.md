# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006b24`
- end: `0x180006c1c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051d0`
- `0x1800073b8`
- `0x18000778c`

## callees

- `0x18000288a`
- `0x180006b24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006b61`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006ba3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006be2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006b61`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006ba3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006be2`

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
0x180006b24  push    rbx
0x180006b26  push    rbp
0x180006b27  push    rsi
0x180006b28  push    rdi
0x180006b29  push    r14
0x180006b2b  push    r15
0x180006b2d  sub     rsp, 28h
0x180006b31  mov     rax, [rdx]
0x180006b34  xor     r15d, r15d
0x180006b37  cmp     byte ptr [rcx+2], 1
0x180006b3b  mov     rbp, r8
0x180006b3e  mov     r14, rdx
0x180006b41  mov     rdi, rcx
0x180006b44  jnz     short loc_180006B7D
0x180006b46  lea     rbx, [rax+2]
0x180006b4a  cmp     rbx, r8
0x180006b4d  ja      loc_180006C02
0x180006b53  mov     [rcx+10h], rax
0x180006b57  test    rax, rax
0x180006b5a  jz      short loc_180006B61
0x180006b5c  movzx   ecx, word ptr [rax]
0x180006b5f  jmp     short loc_180006B75
0x180006b61  call    cs:__imp__o__errno
0x180006b67  mov     dword ptr [rax], 16h
0x180006b6d  call    _invalid_parameter_noinfo
0x180006b72  mov     ecx, r15d
0x180006b75  movzx   eax, cx
0x180006b78  mov     [rdi+4], eax
0x180006b7b  jmp     short loc_180006BB9
0x180006b7d  cmp     byte ptr [rcx+2], 2
0x180006b81  jnz     short loc_180006BB6
0x180006b83  lea     rbx, [rax+4]
0x180006b87  cmp     rbx, rbp
0x180006b8a  ja      short loc_180006C02
0x180006b8c  mov     [rcx+10h], rax
0x180006b90  add     rcx, 4
0x180006b94  jz      short loc_180006BA3
0x180006b96  test    rax, rax
0x180006b99  jz      short loc_180006BA1
0x180006b9b  mov     eax, [rax]
0x180006b9d  mov     [rcx], eax
0x180006b9f  jmp     short loc_180006BB9
0x180006ba1  mov     [rcx], eax
0x180006ba3  call    cs:__imp__o__errno
0x180006ba9  mov     dword ptr [rax], 16h
0x180006baf  call    _invalid_parameter_noinfo
0x180006bb4  jmp     short loc_180006BB9
0x180006bb6  mov     rbx, rax
0x180006bb9  movzx   eax, word ptr [rdi]
0x180006bbc  mov     [rdi+8], ax
0x180006bc0  test    ax, ax
0x180006bc3  jnz     short loc_180006BF6
0x180006bc5  lea     rsi, [rbx+2]
0x180006bc9  cmp     rsi, rbp
0x180006bcc  ja      short loc_180006C02
0x180006bce  test    rbx, rbx
0x180006bd1  jz      short loc_180006BDC
0x180006bd3  movzx   eax, word ptr [rbx]
0x180006bd6  mov     [rdi+8], ax
0x180006bda  jmp     short loc_180006BF3
0x180006bdc  xor     eax, eax
0x180006bde  mov     [rdi+8], ax
0x180006be2  call    cs:__imp__o__errno
0x180006be8  mov     dword ptr [rax], 16h
0x180006bee  call    _invalid_parameter_noinfo
0x180006bf3  mov     rbx, rsi
0x180006bf6  movzx   ecx, word ptr [rdi+8]
0x180006bfa  add     rcx, rbx
0x180006bfd  cmp     rcx, rbp
0x180006c00  jbe     short loc_180006C06
0x180006c02  xor     al, al
0x180006c04  jmp     short loc_180006C0F
0x180006c06  mov     [rdi+18h], rbx
0x180006c0a  mov     al, 1
0x180006c0c  mov     [r14], rcx
0x180006c0f  add     rsp, 28h
0x180006c13  pop     r15
0x180006c15  pop     r14
0x180006c17  pop     rdi
0x180006c18  pop     rsi
0x180006c19  pop     rbp
0x180006c1a  pop     rbx
0x180006c1b  retn
```
