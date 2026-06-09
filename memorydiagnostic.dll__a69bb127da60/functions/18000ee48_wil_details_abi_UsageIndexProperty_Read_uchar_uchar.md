# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000ee48`
- end: `0x18000ef40`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c004`
- `0x18000f6d8`
- `0x18000faac`

## callees

- `0x1800038c6`
- `0x18000ee48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee85`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eec7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ef06`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee85`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eec7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ef06`

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
0x18000ee48  push    rbx
0x18000ee4a  push    rbp
0x18000ee4b  push    rsi
0x18000ee4c  push    rdi
0x18000ee4d  push    r14
0x18000ee4f  push    r15
0x18000ee51  sub     rsp, 28h
0x18000ee55  mov     rax, [rdx]
0x18000ee58  xor     r15d, r15d
0x18000ee5b  cmp     byte ptr [rcx+2], 1
0x18000ee5f  mov     rbp, r8
0x18000ee62  mov     r14, rdx
0x18000ee65  mov     rdi, rcx
0x18000ee68  jnz     short loc_18000EEA1
0x18000ee6a  lea     rbx, [rax+2]
0x18000ee6e  cmp     rbx, r8
0x18000ee71  ja      loc_18000EF26
0x18000ee77  mov     [rcx+10h], rax
0x18000ee7b  test    rax, rax
0x18000ee7e  jz      short loc_18000EE85
0x18000ee80  movzx   ecx, word ptr [rax]
0x18000ee83  jmp     short loc_18000EE99
0x18000ee85  call    cs:__imp__o__errno
0x18000ee8b  mov     dword ptr [rax], 16h
0x18000ee91  call    _invalid_parameter_noinfo
0x18000ee96  mov     ecx, r15d
0x18000ee99  movzx   eax, cx
0x18000ee9c  mov     [rdi+4], eax
0x18000ee9f  jmp     short loc_18000EEDD
0x18000eea1  cmp     byte ptr [rcx+2], 2
0x18000eea5  jnz     short loc_18000EEDA
0x18000eea7  lea     rbx, [rax+4]
0x18000eeab  cmp     rbx, rbp
0x18000eeae  ja      short loc_18000EF26
0x18000eeb0  mov     [rcx+10h], rax
0x18000eeb4  add     rcx, 4
0x18000eeb8  jz      short loc_18000EEC7
0x18000eeba  test    rax, rax
0x18000eebd  jz      short loc_18000EEC5
0x18000eebf  mov     eax, [rax]
0x18000eec1  mov     [rcx], eax
0x18000eec3  jmp     short loc_18000EEDD
0x18000eec5  mov     [rcx], eax
0x18000eec7  call    cs:__imp__o__errno
0x18000eecd  mov     dword ptr [rax], 16h
0x18000eed3  call    _invalid_parameter_noinfo
0x18000eed8  jmp     short loc_18000EEDD
0x18000eeda  mov     rbx, rax
0x18000eedd  movzx   eax, word ptr [rdi]
0x18000eee0  mov     [rdi+8], ax
0x18000eee4  test    ax, ax
0x18000eee7  jnz     short loc_18000EF1A
0x18000eee9  lea     rsi, [rbx+2]
0x18000eeed  cmp     rsi, rbp
0x18000eef0  ja      short loc_18000EF26
0x18000eef2  test    rbx, rbx
0x18000eef5  jz      short loc_18000EF00
0x18000eef7  movzx   eax, word ptr [rbx]
0x18000eefa  mov     [rdi+8], ax
0x18000eefe  jmp     short loc_18000EF17
0x18000ef00  xor     eax, eax
0x18000ef02  mov     [rdi+8], ax
0x18000ef06  call    cs:__imp__o__errno
0x18000ef0c  mov     dword ptr [rax], 16h
0x18000ef12  call    _invalid_parameter_noinfo
0x18000ef17  mov     rbx, rsi
0x18000ef1a  movzx   ecx, word ptr [rdi+8]
0x18000ef1e  add     rcx, rbx
0x18000ef21  cmp     rcx, rbp
0x18000ef24  jbe     short loc_18000EF2A
0x18000ef26  xor     al, al
0x18000ef28  jmp     short loc_18000EF33
0x18000ef2a  mov     [rdi+18h], rbx
0x18000ef2e  mov     al, 1
0x18000ef30  mov     [r14], rcx
0x18000ef33  add     rsp, 28h
0x18000ef37  pop     r15
0x18000ef39  pop     r14
0x18000ef3b  pop     rdi
0x18000ef3c  pop     rsi
0x18000ef3d  pop     rbp
0x18000ef3e  pop     rbx
0x18000ef3f  retn
```
