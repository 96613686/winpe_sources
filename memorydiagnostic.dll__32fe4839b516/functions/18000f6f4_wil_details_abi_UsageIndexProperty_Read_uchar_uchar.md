# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000f6f4`
- end: `0x18000f818`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `292`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c988`
- `0x18000ffd0`
- `0x1800103c4`

## callees

- `0x180003306`
- `0x18000f6f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f740`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f78a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f7d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f740`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f78a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f7d1`

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
0x18000f6f4  mov     [rsp+arg_8], rbx
0x18000f6f9  mov     [rsp+arg_10], rbp
0x18000f6fe  push    rsi
0x18000f6ff  push    rdi
0x18000f700  push    r12
0x18000f702  push    r14
0x18000f704  push    r15
0x18000f706  sub     rsp, 20h
0x18000f70a  mov     al, [rcx+2]
0x18000f70d  xor     r15d, r15d
0x18000f710  mov     r9, [rdx]
0x18000f713  mov     rbp, r8
0x18000f716  mov     r14, rdx
0x18000f719  mov     rbx, rcx
0x18000f71c  lea     r12d, [r15+16h]
0x18000f720  cmp     al, 1
0x18000f722  jnz     short loc_18000F75F
0x18000f724  lea     rdi, [r9+2]
0x18000f728  cmp     rdi, r8
0x18000f72b  ja      loc_18000F7F3
0x18000f731  mov     [rcx+10h], r9
0x18000f735  test    r9, r9
0x18000f738  jz      short loc_18000F740
0x18000f73a  movzx   eax, word ptr [r9]
0x18000f73e  jmp     short loc_18000F757
0x18000f740  call    cs:__imp__o__errno
0x18000f747  nop     dword ptr [rax+rax+00h]
0x18000f74c  mov     [rax], r12d
0x18000f74f  call    _invalid_parameter_noinfo
0x18000f754  mov     eax, r15d
0x18000f757  movzx   eax, ax
0x18000f75a  mov     [rbx+4], eax
0x18000f75d  jmp     short loc_18000F79E
0x18000f75f  cmp     al, 2
0x18000f761  jnz     short loc_18000F7A1
0x18000f763  lea     rdi, [r9+4]
0x18000f767  cmp     rdi, rbp
0x18000f76a  ja      loc_18000F7F3
0x18000f770  mov     [rcx+10h], r9
0x18000f774  add     rcx, 4
0x18000f778  jz      short loc_18000F78A
0x18000f77a  test    r9, r9
0x18000f77d  jz      short loc_18000F786
0x18000f77f  mov     eax, [r9]
0x18000f782  mov     [rcx], eax
0x18000f784  jmp     short loc_18000F79E
0x18000f786  xor     eax, eax
0x18000f788  mov     [rcx], eax
0x18000f78a  call    cs:__imp__o__errno
0x18000f791  nop     dword ptr [rax+rax+00h]
0x18000f796  mov     [rax], r12d
0x18000f799  call    _invalid_parameter_noinfo
0x18000f79e  mov     r9, rdi
0x18000f7a1  movzx   eax, word ptr [rbx]
0x18000f7a4  lea     rdi, [rbx+8]
0x18000f7a8  mov     [rdi], ax
0x18000f7ab  test    ax, ax
0x18000f7ae  jnz     short loc_18000F7E8
0x18000f7b0  lea     rsi, [r9+2]
0x18000f7b4  cmp     rsi, rbp
0x18000f7b7  ja      short loc_18000F7F3
0x18000f7b9  test    rdi, rdi
0x18000f7bc  jz      short loc_18000F7D1
0x18000f7be  test    r9, r9
0x18000f7c1  jz      short loc_18000F7CC
0x18000f7c3  movzx   eax, word ptr [r9]
0x18000f7c7  mov     [rdi], ax
0x18000f7ca  jmp     short loc_18000F7E5
0x18000f7cc  xor     eax, eax
0x18000f7ce  mov     [rdi], ax
0x18000f7d1  call    cs:__imp__o__errno
0x18000f7d8  nop     dword ptr [rax+rax+00h]
0x18000f7dd  mov     [rax], r12d
0x18000f7e0  call    _invalid_parameter_noinfo
0x18000f7e5  mov     r9, rsi
0x18000f7e8  movzx   ecx, word ptr [rdi]
0x18000f7eb  add     rcx, r9
0x18000f7ee  cmp     rcx, rbp
0x18000f7f1  jbe     short loc_18000F7F7
0x18000f7f3  xor     al, al
0x18000f7f5  jmp     short loc_18000F800
0x18000f7f7  mov     [rbx+18h], r9
0x18000f7fb  mov     al, 1
0x18000f7fd  mov     [r14], rcx
0x18000f800  mov     rbx, [rsp+48h+arg_8]
0x18000f805  mov     rbp, [rsp+48h+arg_10]
0x18000f80a  add     rsp, 20h
0x18000f80e  pop     r15
0x18000f810  pop     r14
0x18000f812  pop     r12
0x18000f814  pop     rdi
0x18000f815  pop     rsi
0x18000f816  retn
```
