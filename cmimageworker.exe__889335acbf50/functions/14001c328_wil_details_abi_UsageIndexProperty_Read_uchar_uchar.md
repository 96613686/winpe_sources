# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14001c328`
- end: `0x14001c437`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `271`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400198b4`
- `0x14001cb74`
- `0x14001cf68`

## callees

- `0x140002a4a`
- `0x14001c328`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c365`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c3b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c3f6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c365`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c3b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001c3f6`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v7; // rbx
  unsigned __int16 v8; // cx
  _DWORD *v9; // rcx
  __int16 v10; // ax
  unsigned __int8 *v11; // rcx
  bool result; // al

  v3 = (unsigned __int16 *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v8 = *v3;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v8 = 0;
    }
    *((_DWORD *)this + 1) = v8;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    v9 = (_DWORD *)((char *)this + 4);
    if ( v9 )
    {
      if ( v3 )
      {
        *v9 = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *v9 = 0;
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = (unsigned __int16 *)*a2;
  }
LABEL_15:
  v10 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v10 )
    goto LABEL_21;
  if ( v7 + 1 > (unsigned __int16 *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)this + 4) = *v7;
  }
  else
  {
    *((_WORD *)this + 4) = 0;
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v11 = (unsigned __int8 *)v7 + *((unsigned __int16 *)this + 4);
  if ( v11 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v11;
  return result;
}

```

## disassembly

```asm
0x14001c328  push    rbx
0x14001c32a  push    rbp
0x14001c32b  push    rsi
0x14001c32c  push    rdi
0x14001c32d  push    r14
0x14001c32f  push    r15
0x14001c331  sub     rsp, 28h
0x14001c335  mov     rax, [rdx]
0x14001c338  xor     r15d, r15d
0x14001c33b  cmp     byte ptr [rcx+2], 1
0x14001c33f  mov     rbp, r8
0x14001c342  mov     r14, rdx
0x14001c345  mov     rdi, rcx
0x14001c348  jnz     short loc_14001C387
0x14001c34a  lea     rbx, [rax+2]
0x14001c34e  cmp     rbx, r8
0x14001c351  ja      loc_14001C41C
0x14001c357  mov     [rcx+10h], rax
0x14001c35b  test    rax, rax
0x14001c35e  jz      short loc_14001C365
0x14001c360  movzx   ecx, word ptr [rax]
0x14001c363  jmp     short loc_14001C37F
0x14001c365  call    cs:__imp__o__errno
0x14001c36c  nop     dword ptr [rax+rax+00h]
0x14001c371  mov     dword ptr [rax], 16h
0x14001c377  call    _invalid_parameter_noinfo
0x14001c37c  mov     ecx, r15d
0x14001c37f  movzx   eax, cx
0x14001c382  mov     [rdi+4], eax
0x14001c385  jmp     short loc_14001C3CD
0x14001c387  cmp     byte ptr [rcx+2], 2
0x14001c38b  jnz     short loc_14001C3CA
0x14001c38d  lea     rbx, [rax+4]
0x14001c391  cmp     rbx, rbp
0x14001c394  ja      loc_14001C41C
0x14001c39a  mov     [rcx+10h], rax
0x14001c39e  add     rcx, 4
0x14001c3a2  jz      short loc_14001C3B1
0x14001c3a4  test    rax, rax
0x14001c3a7  jz      short loc_14001C3AF
0x14001c3a9  mov     eax, [rax]
0x14001c3ab  mov     [rcx], eax
0x14001c3ad  jmp     short loc_14001C3CD
0x14001c3af  mov     [rcx], eax
0x14001c3b1  call    cs:__imp__o__errno
0x14001c3b8  nop     dword ptr [rax+rax+00h]
0x14001c3bd  mov     dword ptr [rax], 16h
0x14001c3c3  call    _invalid_parameter_noinfo
0x14001c3c8  jmp     short loc_14001C3CD
0x14001c3ca  mov     rbx, rax
0x14001c3cd  movzx   eax, word ptr [rdi]
0x14001c3d0  mov     [rdi+8], ax
0x14001c3d4  test    ax, ax
0x14001c3d7  jnz     short loc_14001C410
0x14001c3d9  lea     rsi, [rbx+2]
0x14001c3dd  cmp     rsi, rbp
0x14001c3e0  ja      short loc_14001C41C
0x14001c3e2  test    rbx, rbx
0x14001c3e5  jz      short loc_14001C3F0
0x14001c3e7  movzx   eax, word ptr [rbx]
0x14001c3ea  mov     [rdi+8], ax
0x14001c3ee  jmp     short loc_14001C40D
0x14001c3f0  xor     eax, eax
0x14001c3f2  mov     [rdi+8], ax
0x14001c3f6  call    cs:__imp__o__errno
0x14001c3fd  nop     dword ptr [rax+rax+00h]
0x14001c402  mov     dword ptr [rax], 16h
0x14001c408  call    _invalid_parameter_noinfo
0x14001c40d  mov     rbx, rsi
0x14001c410  movzx   ecx, word ptr [rdi+8]
0x14001c414  add     rcx, rbx
0x14001c417  cmp     rcx, rbp
0x14001c41a  jbe     short loc_14001C420
0x14001c41c  xor     al, al
0x14001c41e  jmp     short loc_14001C429
0x14001c420  mov     [rdi+18h], rbx
0x14001c424  mov     al, 1
0x14001c426  mov     [r14], rcx
0x14001c429  add     rsp, 28h
0x14001c42d  pop     r15
0x14001c42f  pop     r14
0x14001c431  pop     rdi
0x14001c432  pop     rsi
0x14001c433  pop     rbp
0x14001c434  pop     rbx
0x14001c435  retn
```
