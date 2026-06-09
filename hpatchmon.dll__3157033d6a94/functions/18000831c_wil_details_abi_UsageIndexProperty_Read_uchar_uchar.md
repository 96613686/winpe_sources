# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000831c`
- end: `0x180008414`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ac0`
- `0x180008b68`
- `0x180008f3c`

## callees

- `0x180002b62`
- `0x18000831c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008359`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000839b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008359`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000839b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083da`

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
0x18000831c  push    rbx
0x18000831e  push    rbp
0x18000831f  push    rsi
0x180008320  push    rdi
0x180008321  push    r14
0x180008323  push    r15
0x180008325  sub     rsp, 28h
0x180008329  mov     rax, [rdx]
0x18000832c  xor     r15d, r15d
0x18000832f  cmp     byte ptr [rcx+2], 1
0x180008333  mov     rbp, r8
0x180008336  mov     r14, rdx
0x180008339  mov     rdi, rcx
0x18000833c  jnz     short loc_180008375
0x18000833e  lea     rbx, [rax+2]
0x180008342  cmp     rbx, r8
0x180008345  ja      loc_1800083FA
0x18000834b  mov     [rcx+10h], rax
0x18000834f  test    rax, rax
0x180008352  jz      short loc_180008359
0x180008354  movzx   ecx, word ptr [rax]
0x180008357  jmp     short loc_18000836D
0x180008359  call    cs:__imp__o__errno
0x18000835f  mov     dword ptr [rax], 16h
0x180008365  call    _invalid_parameter_noinfo
0x18000836a  mov     ecx, r15d
0x18000836d  movzx   eax, cx
0x180008370  mov     [rdi+4], eax
0x180008373  jmp     short loc_1800083B1
0x180008375  cmp     byte ptr [rcx+2], 2
0x180008379  jnz     short loc_1800083AE
0x18000837b  lea     rbx, [rax+4]
0x18000837f  cmp     rbx, rbp
0x180008382  ja      short loc_1800083FA
0x180008384  mov     [rcx+10h], rax
0x180008388  add     rcx, 4
0x18000838c  jz      short loc_18000839B
0x18000838e  test    rax, rax
0x180008391  jz      short loc_180008399
0x180008393  mov     eax, [rax]
0x180008395  mov     [rcx], eax
0x180008397  jmp     short loc_1800083B1
0x180008399  mov     [rcx], eax
0x18000839b  call    cs:__imp__o__errno
0x1800083a1  mov     dword ptr [rax], 16h
0x1800083a7  call    _invalid_parameter_noinfo
0x1800083ac  jmp     short loc_1800083B1
0x1800083ae  mov     rbx, rax
0x1800083b1  movzx   eax, word ptr [rdi]
0x1800083b4  mov     [rdi+8], ax
0x1800083b8  test    ax, ax
0x1800083bb  jnz     short loc_1800083EE
0x1800083bd  lea     rsi, [rbx+2]
0x1800083c1  cmp     rsi, rbp
0x1800083c4  ja      short loc_1800083FA
0x1800083c6  test    rbx, rbx
0x1800083c9  jz      short loc_1800083D4
0x1800083cb  movzx   eax, word ptr [rbx]
0x1800083ce  mov     [rdi+8], ax
0x1800083d2  jmp     short loc_1800083EB
0x1800083d4  xor     eax, eax
0x1800083d6  mov     [rdi+8], ax
0x1800083da  call    cs:__imp__o__errno
0x1800083e0  mov     dword ptr [rax], 16h
0x1800083e6  call    _invalid_parameter_noinfo
0x1800083eb  mov     rbx, rsi
0x1800083ee  movzx   ecx, word ptr [rdi+8]
0x1800083f2  add     rcx, rbx
0x1800083f5  cmp     rcx, rbp
0x1800083f8  jbe     short loc_1800083FE
0x1800083fa  xor     al, al
0x1800083fc  jmp     short loc_180008407
0x1800083fe  mov     [rdi+18h], rbx
0x180008402  mov     al, 1
0x180008404  mov     [r14], rcx
0x180008407  add     rsp, 28h
0x18000840b  pop     r15
0x18000840d  pop     r14
0x18000840f  pop     rdi
0x180008410  pop     rsi
0x180008411  pop     rbp
0x180008412  pop     rbx
0x180008413  retn
```
