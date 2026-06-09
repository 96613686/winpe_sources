# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180026190`
- end: `0x18002629a`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `266`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023aa0`

## callees

- `0x18001eae6`
- `0x180026190`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800261d8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002621b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002625a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800261d8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002621b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002625a`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int8 *v3; // rax
  _DWORD *v5; // rcx
  unsigned __int8 *v8; // rbx
  __int16 v9; // ax
  unsigned __int8 *v10; // rcx
  bool result; // al

  v3 = *a2;
  v5 = (_DWORD *)*((unsigned __int8 *)this + 2);
  if ( (_BYTE)v5 == 1 )
  {
    v8 = v3 + 2;
    if ( v3 + 2 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v5 = (_DWORD *)*(unsigned __int16 *)v3;
      *((_DWORD *)this + 1) = (unsigned __int16)v5;
    }
    else
    {
      *(_DWORD *)_o__errno(v5, a2, a3) = 22;
      invalid_parameter_noinfo();
      v5 = 0;
      *((_DWORD *)this + 1) = 0;
    }
  }
  else if ( (_BYTE)v5 == 2 )
  {
    v8 = v3 + 4;
    if ( v3 + 4 > a3 )
      return 0;
    v5 = (_DWORD *)((char *)this + 4);
    *((_QWORD *)this + 2) = v3;
    if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
    {
      if ( v3 )
      {
        *v5 = *(_DWORD *)v3;
        goto LABEL_14;
      }
      *v5 = 0;
    }
    *(_DWORD *)_o__errno(v5, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v8 = *a2;
  }
LABEL_14:
  v9 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v9 )
    goto LABEL_20;
  if ( v8 + 2 > a3 )
    return 0;
  if ( v8 )
  {
    *((_WORD *)this + 4) = *(_WORD *)v8;
  }
  else
  {
    *((_WORD *)this + 4) = 0;
    *(_DWORD *)_o__errno(v5, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  v8 += 2;
LABEL_20:
  v10 = &v8[*((unsigned __int16 *)this + 4)];
  if ( v10 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v8;
  result = 1;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x180026190  mov     [rsp+arg_10], rbx
0x180026195  mov     [rsp+arg_18], rbp
0x18002619a  push    rsi
0x18002619b  push    rdi
0x18002619c  push    r14
0x18002619e  sub     rsp, 20h
0x1800261a2  mov     rax, [rdx]
0x1800261a5  mov     rdi, rcx
0x1800261a8  movzx   ecx, byte ptr [rcx+2]
0x1800261ac  mov     rbp, r8
0x1800261af  mov     r14, rdx
0x1800261b2  cmp     cl, 1
0x1800261b5  jnz     short loc_1800261F3
0x1800261b7  lea     rbx, [rax+2]
0x1800261bb  cmp     rbx, r8
0x1800261be  ja      loc_18002627A
0x1800261c4  mov     [rdi+10h], rax
0x1800261c8  test    rax, rax
0x1800261cb  jz      short loc_1800261D8
0x1800261cd  movzx   ecx, word ptr [rax]
0x1800261d0  movzx   eax, cx
0x1800261d3  mov     [rdi+4], eax
0x1800261d6  jmp     short loc_180026231
0x1800261d8  call    cs:__imp__o__errno
0x1800261de  mov     dword ptr [rax], 16h
0x1800261e4  call    _invalid_parameter_noinfo
0x1800261e9  xor     ecx, ecx
0x1800261eb  movzx   eax, cx
0x1800261ee  mov     [rdi+4], eax
0x1800261f1  jmp     short loc_180026231
0x1800261f3  cmp     cl, 2
0x1800261f6  jnz     short loc_18002622E
0x1800261f8  lea     rbx, [rax+4]
0x1800261fc  cmp     rbx, rbp
0x1800261ff  ja      short loc_18002627A
0x180026201  lea     rcx, [rdi+4]
0x180026205  mov     [rdi+10h], rax
0x180026209  test    rcx, rcx
0x18002620c  jz      short loc_18002621B
0x18002620e  test    rax, rax
0x180026211  jz      short loc_180026219
0x180026213  mov     eax, [rax]
0x180026215  mov     [rcx], eax
0x180026217  jmp     short loc_180026231
0x180026219  mov     [rcx], eax
0x18002621b  call    cs:__imp__o__errno
0x180026221  mov     dword ptr [rax], 16h
0x180026227  call    _invalid_parameter_noinfo
0x18002622c  jmp     short loc_180026231
0x18002622e  mov     rbx, rax
0x180026231  movzx   eax, word ptr [rdi]
0x180026234  mov     [rdi+8], ax
0x180026238  test    ax, ax
0x18002623b  jnz     short loc_18002626E
0x18002623d  lea     rsi, [rbx+2]
0x180026241  cmp     rsi, rbp
0x180026244  ja      short loc_18002627A
0x180026246  test    rbx, rbx
0x180026249  jz      short loc_180026254
0x18002624b  movzx   eax, word ptr [rbx]
0x18002624e  mov     [rdi+8], ax
0x180026252  jmp     short loc_18002626B
0x180026254  xor     eax, eax
0x180026256  mov     [rdi+8], ax
0x18002625a  call    cs:__imp__o__errno
0x180026260  mov     dword ptr [rax], 16h
0x180026266  call    _invalid_parameter_noinfo
0x18002626b  mov     rbx, rsi
0x18002626e  movzx   ecx, word ptr [rdi+8]
0x180026272  add     rcx, rbx
0x180026275  cmp     rcx, rbp
0x180026278  jbe     short loc_18002627E
0x18002627a  xor     al, al
0x18002627c  jmp     short loc_180026287
0x18002627e  mov     [rdi+18h], rbx
0x180026282  mov     al, 1
0x180026284  mov     [r14], rcx
0x180026287  mov     rbx, [rsp+38h+arg_10]
0x18002628c  mov     rbp, [rsp+38h+arg_18]
0x180026291  add     rsp, 20h
0x180026295  pop     r14
0x180026297  pop     rdi
0x180026298  pop     rsi
0x180026299  retn
```
