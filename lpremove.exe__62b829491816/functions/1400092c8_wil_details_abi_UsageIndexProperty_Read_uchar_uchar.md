# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1400092c8`
- end: `0x1400093c0`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006d8c`
- `0x1400099d8`
- `0x140009dac`

## callees

- `0x140002b82`
- `0x1400092c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009305`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009347`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009386`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009305`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009347`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009386`

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
0x1400092c8  push    rbx
0x1400092ca  push    rbp
0x1400092cb  push    rsi
0x1400092cc  push    rdi
0x1400092cd  push    r14
0x1400092cf  push    r15
0x1400092d1  sub     rsp, 28h
0x1400092d5  mov     rax, [rdx]
0x1400092d8  xor     r15d, r15d
0x1400092db  cmp     byte ptr [rcx+2], 1
0x1400092df  mov     rbp, r8
0x1400092e2  mov     r14, rdx
0x1400092e5  mov     rdi, rcx
0x1400092e8  jnz     short loc_140009321
0x1400092ea  lea     rbx, [rax+2]
0x1400092ee  cmp     rbx, r8
0x1400092f1  ja      loc_1400093A6
0x1400092f7  mov     [rcx+10h], rax
0x1400092fb  test    rax, rax
0x1400092fe  jz      short loc_140009305
0x140009300  movzx   ecx, word ptr [rax]
0x140009303  jmp     short loc_140009319
0x140009305  call    cs:__imp__o__errno
0x14000930b  mov     dword ptr [rax], 16h
0x140009311  call    _invalid_parameter_noinfo
0x140009316  mov     ecx, r15d
0x140009319  movzx   eax, cx
0x14000931c  mov     [rdi+4], eax
0x14000931f  jmp     short loc_14000935D
0x140009321  cmp     byte ptr [rcx+2], 2
0x140009325  jnz     short loc_14000935A
0x140009327  lea     rbx, [rax+4]
0x14000932b  cmp     rbx, rbp
0x14000932e  ja      short loc_1400093A6
0x140009330  mov     [rcx+10h], rax
0x140009334  add     rcx, 4
0x140009338  jz      short loc_140009347
0x14000933a  test    rax, rax
0x14000933d  jz      short loc_140009345
0x14000933f  mov     eax, [rax]
0x140009341  mov     [rcx], eax
0x140009343  jmp     short loc_14000935D
0x140009345  mov     [rcx], eax
0x140009347  call    cs:__imp__o__errno
0x14000934d  mov     dword ptr [rax], 16h
0x140009353  call    _invalid_parameter_noinfo
0x140009358  jmp     short loc_14000935D
0x14000935a  mov     rbx, rax
0x14000935d  movzx   eax, word ptr [rdi]
0x140009360  mov     [rdi+8], ax
0x140009364  test    ax, ax
0x140009367  jnz     short loc_14000939A
0x140009369  lea     rsi, [rbx+2]
0x14000936d  cmp     rsi, rbp
0x140009370  ja      short loc_1400093A6
0x140009372  test    rbx, rbx
0x140009375  jz      short loc_140009380
0x140009377  movzx   eax, word ptr [rbx]
0x14000937a  mov     [rdi+8], ax
0x14000937e  jmp     short loc_140009397
0x140009380  xor     eax, eax
0x140009382  mov     [rdi+8], ax
0x140009386  call    cs:__imp__o__errno
0x14000938c  mov     dword ptr [rax], 16h
0x140009392  call    _invalid_parameter_noinfo
0x140009397  mov     rbx, rsi
0x14000939a  movzx   ecx, word ptr [rdi+8]
0x14000939e  add     rcx, rbx
0x1400093a1  cmp     rcx, rbp
0x1400093a4  jbe     short loc_1400093AA
0x1400093a6  xor     al, al
0x1400093a8  jmp     short loc_1400093B3
0x1400093aa  mov     [rdi+18h], rbx
0x1400093ae  mov     al, 1
0x1400093b0  mov     [r14], rcx
0x1400093b3  add     rsp, 28h
0x1400093b7  pop     r15
0x1400093b9  pop     r14
0x1400093bb  pop     rdi
0x1400093bc  pop     rsi
0x1400093bd  pop     rbp
0x1400093be  pop     rbx
0x1400093bf  retn
```
