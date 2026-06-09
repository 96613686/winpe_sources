# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800063a8`
- end: `0x1800064a0`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004800`
- `0x180006be8`
- `0x180006fbc`

## callees

- `0x18000214a`
- `0x1800063a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006427`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006466`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006427`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006466`

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
0x1800063a8  push    rbx
0x1800063aa  push    rbp
0x1800063ab  push    rsi
0x1800063ac  push    rdi
0x1800063ad  push    r14
0x1800063af  push    r15
0x1800063b1  sub     rsp, 28h
0x1800063b5  mov     rax, [rdx]
0x1800063b8  xor     r15d, r15d
0x1800063bb  cmp     byte ptr [rcx+2], 1
0x1800063bf  mov     rbp, r8
0x1800063c2  mov     r14, rdx
0x1800063c5  mov     rdi, rcx
0x1800063c8  jnz     short loc_180006401
0x1800063ca  lea     rbx, [rax+2]
0x1800063ce  cmp     rbx, r8
0x1800063d1  ja      loc_180006486
0x1800063d7  mov     [rcx+10h], rax
0x1800063db  test    rax, rax
0x1800063de  jz      short loc_1800063E5
0x1800063e0  movzx   ecx, word ptr [rax]
0x1800063e3  jmp     short loc_1800063F9
0x1800063e5  call    cs:__imp__o__errno
0x1800063eb  mov     dword ptr [rax], 16h
0x1800063f1  call    _invalid_parameter_noinfo
0x1800063f6  mov     ecx, r15d
0x1800063f9  movzx   eax, cx
0x1800063fc  mov     [rdi+4], eax
0x1800063ff  jmp     short loc_18000643D
0x180006401  cmp     byte ptr [rcx+2], 2
0x180006405  jnz     short loc_18000643A
0x180006407  lea     rbx, [rax+4]
0x18000640b  cmp     rbx, rbp
0x18000640e  ja      short loc_180006486
0x180006410  mov     [rcx+10h], rax
0x180006414  add     rcx, 4
0x180006418  jz      short loc_180006427
0x18000641a  test    rax, rax
0x18000641d  jz      short loc_180006425
0x18000641f  mov     eax, [rax]
0x180006421  mov     [rcx], eax
0x180006423  jmp     short loc_18000643D
0x180006425  mov     [rcx], eax
0x180006427  call    cs:__imp__o__errno
0x18000642d  mov     dword ptr [rax], 16h
0x180006433  call    _invalid_parameter_noinfo
0x180006438  jmp     short loc_18000643D
0x18000643a  mov     rbx, rax
0x18000643d  movzx   eax, word ptr [rdi]
0x180006440  mov     [rdi+8], ax
0x180006444  test    ax, ax
0x180006447  jnz     short loc_18000647A
0x180006449  lea     rsi, [rbx+2]
0x18000644d  cmp     rsi, rbp
0x180006450  ja      short loc_180006486
0x180006452  test    rbx, rbx
0x180006455  jz      short loc_180006460
0x180006457  movzx   eax, word ptr [rbx]
0x18000645a  mov     [rdi+8], ax
0x18000645e  jmp     short loc_180006477
0x180006460  xor     eax, eax
0x180006462  mov     [rdi+8], ax
0x180006466  call    cs:__imp__o__errno
0x18000646c  mov     dword ptr [rax], 16h
0x180006472  call    _invalid_parameter_noinfo
0x180006477  mov     rbx, rsi
0x18000647a  movzx   ecx, word ptr [rdi+8]
0x18000647e  add     rcx, rbx
0x180006481  cmp     rcx, rbp
0x180006484  jbe     short loc_18000648A
0x180006486  xor     al, al
0x180006488  jmp     short loc_180006493
0x18000648a  mov     [rdi+18h], rbx
0x18000648e  mov     al, 1
0x180006490  mov     [r14], rcx
0x180006493  add     rsp, 28h
0x180006497  pop     r15
0x180006499  pop     r14
0x18000649b  pop     rdi
0x18000649c  pop     rsi
0x18000649d  pop     rbp
0x18000649e  pop     rbx
0x18000649f  retn
```
