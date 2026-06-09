# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140005a80`
- end: `0x140005b78`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000463c`
- `0x1400060f8`
- `0x1400064cc`

## callees

- `0x14000202e`
- `0x140005a80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005abd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005aff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005b3e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005abd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005aff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005b3e`

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
0x140005a80  push    rbx
0x140005a82  push    rbp
0x140005a83  push    rsi
0x140005a84  push    rdi
0x140005a85  push    r14
0x140005a87  push    r15
0x140005a89  sub     rsp, 28h
0x140005a8d  mov     rax, [rdx]
0x140005a90  xor     r15d, r15d
0x140005a93  cmp     byte ptr [rcx+2], 1
0x140005a97  mov     rbp, r8
0x140005a9a  mov     r14, rdx
0x140005a9d  mov     rdi, rcx
0x140005aa0  jnz     short loc_140005AD9
0x140005aa2  lea     rbx, [rax+2]
0x140005aa6  cmp     rbx, r8
0x140005aa9  ja      loc_140005B5E
0x140005aaf  mov     [rcx+10h], rax
0x140005ab3  test    rax, rax
0x140005ab6  jz      short loc_140005ABD
0x140005ab8  movzx   ecx, word ptr [rax]
0x140005abb  jmp     short loc_140005AD1
0x140005abd  call    cs:__imp__o__errno
0x140005ac3  mov     dword ptr [rax], 16h
0x140005ac9  call    _invalid_parameter_noinfo
0x140005ace  mov     ecx, r15d
0x140005ad1  movzx   eax, cx
0x140005ad4  mov     [rdi+4], eax
0x140005ad7  jmp     short loc_140005B15
0x140005ad9  cmp     byte ptr [rcx+2], 2
0x140005add  jnz     short loc_140005B12
0x140005adf  lea     rbx, [rax+4]
0x140005ae3  cmp     rbx, rbp
0x140005ae6  ja      short loc_140005B5E
0x140005ae8  mov     [rcx+10h], rax
0x140005aec  add     rcx, 4
0x140005af0  jz      short loc_140005AFF
0x140005af2  test    rax, rax
0x140005af5  jz      short loc_140005AFD
0x140005af7  mov     eax, [rax]
0x140005af9  mov     [rcx], eax
0x140005afb  jmp     short loc_140005B15
0x140005afd  mov     [rcx], eax
0x140005aff  call    cs:__imp__o__errno
0x140005b05  mov     dword ptr [rax], 16h
0x140005b0b  call    _invalid_parameter_noinfo
0x140005b10  jmp     short loc_140005B15
0x140005b12  mov     rbx, rax
0x140005b15  movzx   eax, word ptr [rdi]
0x140005b18  mov     [rdi+8], ax
0x140005b1c  test    ax, ax
0x140005b1f  jnz     short loc_140005B52
0x140005b21  lea     rsi, [rbx+2]
0x140005b25  cmp     rsi, rbp
0x140005b28  ja      short loc_140005B5E
0x140005b2a  test    rbx, rbx
0x140005b2d  jz      short loc_140005B38
0x140005b2f  movzx   eax, word ptr [rbx]
0x140005b32  mov     [rdi+8], ax
0x140005b36  jmp     short loc_140005B4F
0x140005b38  xor     eax, eax
0x140005b3a  mov     [rdi+8], ax
0x140005b3e  call    cs:__imp__o__errno
0x140005b44  mov     dword ptr [rax], 16h
0x140005b4a  call    _invalid_parameter_noinfo
0x140005b4f  mov     rbx, rsi
0x140005b52  movzx   ecx, word ptr [rdi+8]
0x140005b56  add     rcx, rbx
0x140005b59  cmp     rcx, rbp
0x140005b5c  jbe     short loc_140005B62
0x140005b5e  xor     al, al
0x140005b60  jmp     short loc_140005B6B
0x140005b62  mov     [rdi+18h], rbx
0x140005b66  mov     al, 1
0x140005b68  mov     [r14], rcx
0x140005b6b  add     rsp, 28h
0x140005b6f  pop     r15
0x140005b71  pop     r14
0x140005b73  pop     rdi
0x140005b74  pop     rsi
0x140005b75  pop     rbp
0x140005b76  pop     rbx
0x140005b77  retn
```
