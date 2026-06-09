# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006a20`
- end: `0x180006b44`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `292`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005070`
- `0x180007300`
- `0x1800076f4`

## callees

- `0x180002692`
- `0x180006a20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a6c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006ab6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006afd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006a6c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006ab6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006afd`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int16 *v4; // r9
  unsigned __int16 *v8; // rdi
  unsigned __int16 v9; // ax
  _DWORD *v10; // rcx
  __int16 v11; // ax
  unsigned __int16 *v12; // rdi
  unsigned __int16 *v13; // rsi
  unsigned __int8 *v14; // rcx
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = (unsigned __int16 *)*a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v4;
    if ( v4 )
    {
      v9 = *v4;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v9 = 0;
    }
    *((_DWORD *)this + 1) = v9;
    goto LABEL_14;
  }
  if ( v3 != 2 )
    goto LABEL_15;
  v8 = v4 + 2;
  if ( v4 + 2 > (unsigned __int16 *)a3 )
    return 0;
  *((_QWORD *)this + 2) = v4;
  v10 = (_DWORD *)((char *)this + 4);
  if ( !v10 )
    goto LABEL_13;
  if ( !v4 )
  {
    *v10 = 0;
LABEL_13:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_14;
  }
  *v10 = *(_DWORD *)v4;
LABEL_14:
  v4 = v8;
LABEL_15:
  v11 = *(_WORD *)this;
  v12 = (unsigned __int16 *)((char *)this + 8);
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v11 )
    goto LABEL_23;
  v13 = v4 + 1;
  if ( v4 + 1 > (unsigned __int16 *)a3 )
    return 0;
  if ( this == (wil::details_abi::UsageIndexProperty *)-8LL )
  {
LABEL_21:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_22;
  }
  if ( !v4 )
  {
    *v12 = 0;
    goto LABEL_21;
  }
  *v12 = *v4;
LABEL_22:
  v4 = v13;
LABEL_23:
  v14 = (unsigned __int8 *)v4 + *v12;
  if ( v14 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v4;
  result = 1;
  *a2 = v14;
  return result;
}

```

## disassembly

```asm
0x180006a20  mov     [rsp+arg_8], rbx
0x180006a25  mov     [rsp+arg_10], rbp
0x180006a2a  push    rsi
0x180006a2b  push    rdi
0x180006a2c  push    r12
0x180006a2e  push    r14
0x180006a30  push    r15
0x180006a32  sub     rsp, 20h
0x180006a36  mov     al, [rcx+2]
0x180006a39  xor     r15d, r15d
0x180006a3c  mov     r9, [rdx]
0x180006a3f  mov     rbp, r8
0x180006a42  mov     r14, rdx
0x180006a45  mov     rbx, rcx
0x180006a48  lea     r12d, [r15+16h]
0x180006a4c  cmp     al, 1
0x180006a4e  jnz     short loc_180006A8B
0x180006a50  lea     rdi, [r9+2]
0x180006a54  cmp     rdi, r8
0x180006a57  ja      loc_180006B1F
0x180006a5d  mov     [rcx+10h], r9
0x180006a61  test    r9, r9
0x180006a64  jz      short loc_180006A6C
0x180006a66  movzx   eax, word ptr [r9]
0x180006a6a  jmp     short loc_180006A83
0x180006a6c  call    cs:__imp__o__errno
0x180006a73  nop     dword ptr [rax+rax+00h]
0x180006a78  mov     [rax], r12d
0x180006a7b  call    _invalid_parameter_noinfo
0x180006a80  mov     eax, r15d
0x180006a83  movzx   eax, ax
0x180006a86  mov     [rbx+4], eax
0x180006a89  jmp     short loc_180006ACA
0x180006a8b  cmp     al, 2
0x180006a8d  jnz     short loc_180006ACD
0x180006a8f  lea     rdi, [r9+4]
0x180006a93  cmp     rdi, rbp
0x180006a96  ja      loc_180006B1F
0x180006a9c  mov     [rcx+10h], r9
0x180006aa0  add     rcx, 4
0x180006aa4  jz      short loc_180006AB6
0x180006aa6  test    r9, r9
0x180006aa9  jz      short loc_180006AB2
0x180006aab  mov     eax, [r9]
0x180006aae  mov     [rcx], eax
0x180006ab0  jmp     short loc_180006ACA
0x180006ab2  xor     eax, eax
0x180006ab4  mov     [rcx], eax
0x180006ab6  call    cs:__imp__o__errno
0x180006abd  nop     dword ptr [rax+rax+00h]
0x180006ac2  mov     [rax], r12d
0x180006ac5  call    _invalid_parameter_noinfo
0x180006aca  mov     r9, rdi
0x180006acd  movzx   eax, word ptr [rbx]
0x180006ad0  lea     rdi, [rbx+8]
0x180006ad4  mov     [rdi], ax
0x180006ad7  test    ax, ax
0x180006ada  jnz     short loc_180006B14
0x180006adc  lea     rsi, [r9+2]
0x180006ae0  cmp     rsi, rbp
0x180006ae3  ja      short loc_180006B1F
0x180006ae5  test    rdi, rdi
0x180006ae8  jz      short loc_180006AFD
0x180006aea  test    r9, r9
0x180006aed  jz      short loc_180006AF8
0x180006aef  movzx   eax, word ptr [r9]
0x180006af3  mov     [rdi], ax
0x180006af6  jmp     short loc_180006B11
0x180006af8  xor     eax, eax
0x180006afa  mov     [rdi], ax
0x180006afd  call    cs:__imp__o__errno
0x180006b04  nop     dword ptr [rax+rax+00h]
0x180006b09  mov     [rax], r12d
0x180006b0c  call    _invalid_parameter_noinfo
0x180006b11  mov     r9, rsi
0x180006b14  movzx   ecx, word ptr [rdi]
0x180006b17  add     rcx, r9
0x180006b1a  cmp     rcx, rbp
0x180006b1d  jbe     short loc_180006B23
0x180006b1f  xor     al, al
0x180006b21  jmp     short loc_180006B2C
0x180006b23  mov     [rbx+18h], r9
0x180006b27  mov     al, 1
0x180006b29  mov     [r14], rcx
0x180006b2c  mov     rbx, [rsp+48h+arg_8]
0x180006b31  mov     rbp, [rsp+48h+arg_10]
0x180006b36  add     rsp, 20h
0x180006b3a  pop     r15
0x180006b3c  pop     r14
0x180006b3e  pop     r12
0x180006b40  pop     rdi
0x180006b41  pop     rsi
0x180006b42  retn
```
