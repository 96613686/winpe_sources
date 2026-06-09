# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006b9c`
- end: `0x180006c94`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005160`
- `0x1800073e8`
- `0x1800077bc`

## callees

- `0x180002666`
- `0x180006b9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006bd9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006c1b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006c5a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006bd9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006c1b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006c5a`

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
0x180006b9c  push    rbx
0x180006b9e  push    rbp
0x180006b9f  push    rsi
0x180006ba0  push    rdi
0x180006ba1  push    r14
0x180006ba3  push    r15
0x180006ba5  sub     rsp, 28h
0x180006ba9  mov     rax, [rdx]
0x180006bac  xor     r15d, r15d
0x180006baf  cmp     byte ptr [rcx+2], 1
0x180006bb3  mov     rbp, r8
0x180006bb6  mov     r14, rdx
0x180006bb9  mov     rdi, rcx
0x180006bbc  jnz     short loc_180006BF5
0x180006bbe  lea     rbx, [rax+2]
0x180006bc2  cmp     rbx, r8
0x180006bc5  ja      loc_180006C7A
0x180006bcb  mov     [rcx+10h], rax
0x180006bcf  test    rax, rax
0x180006bd2  jz      short loc_180006BD9
0x180006bd4  movzx   ecx, word ptr [rax]
0x180006bd7  jmp     short loc_180006BED
0x180006bd9  call    cs:__imp__o__errno
0x180006bdf  mov     dword ptr [rax], 16h
0x180006be5  call    _invalid_parameter_noinfo
0x180006bea  mov     ecx, r15d
0x180006bed  movzx   eax, cx
0x180006bf0  mov     [rdi+4], eax
0x180006bf3  jmp     short loc_180006C31
0x180006bf5  cmp     byte ptr [rcx+2], 2
0x180006bf9  jnz     short loc_180006C2E
0x180006bfb  lea     rbx, [rax+4]
0x180006bff  cmp     rbx, rbp
0x180006c02  ja      short loc_180006C7A
0x180006c04  mov     [rcx+10h], rax
0x180006c08  add     rcx, 4
0x180006c0c  jz      short loc_180006C1B
0x180006c0e  test    rax, rax
0x180006c11  jz      short loc_180006C19
0x180006c13  mov     eax, [rax]
0x180006c15  mov     [rcx], eax
0x180006c17  jmp     short loc_180006C31
0x180006c19  mov     [rcx], eax
0x180006c1b  call    cs:__imp__o__errno
0x180006c21  mov     dword ptr [rax], 16h
0x180006c27  call    _invalid_parameter_noinfo
0x180006c2c  jmp     short loc_180006C31
0x180006c2e  mov     rbx, rax
0x180006c31  movzx   eax, word ptr [rdi]
0x180006c34  mov     [rdi+8], ax
0x180006c38  test    ax, ax
0x180006c3b  jnz     short loc_180006C6E
0x180006c3d  lea     rsi, [rbx+2]
0x180006c41  cmp     rsi, rbp
0x180006c44  ja      short loc_180006C7A
0x180006c46  test    rbx, rbx
0x180006c49  jz      short loc_180006C54
0x180006c4b  movzx   eax, word ptr [rbx]
0x180006c4e  mov     [rdi+8], ax
0x180006c52  jmp     short loc_180006C6B
0x180006c54  xor     eax, eax
0x180006c56  mov     [rdi+8], ax
0x180006c5a  call    cs:__imp__o__errno
0x180006c60  mov     dword ptr [rax], 16h
0x180006c66  call    _invalid_parameter_noinfo
0x180006c6b  mov     rbx, rsi
0x180006c6e  movzx   ecx, word ptr [rdi+8]
0x180006c72  add     rcx, rbx
0x180006c75  cmp     rcx, rbp
0x180006c78  jbe     short loc_180006C7E
0x180006c7a  xor     al, al
0x180006c7c  jmp     short loc_180006C87
0x180006c7e  mov     [rdi+18h], rbx
0x180006c82  mov     al, 1
0x180006c84  mov     [r14], rcx
0x180006c87  add     rsp, 28h
0x180006c8b  pop     r15
0x180006c8d  pop     r14
0x180006c8f  pop     rdi
0x180006c90  pop     rsi
0x180006c91  pop     rbp
0x180006c92  pop     rbx
0x180006c93  retn
```
