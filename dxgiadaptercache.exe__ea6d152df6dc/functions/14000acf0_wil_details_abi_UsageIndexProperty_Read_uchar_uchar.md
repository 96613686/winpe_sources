# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000acf0`
- end: `0x14000ade8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008584`
- `0x14000b708`
- `0x14000badc`

## callees

- `0x140002ca2`
- `0x14000acf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000adae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000adae`

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
0x14000acf0  push    rbx
0x14000acf2  push    rbp
0x14000acf3  push    rsi
0x14000acf4  push    rdi
0x14000acf5  push    r14
0x14000acf7  push    r15
0x14000acf9  sub     rsp, 28h
0x14000acfd  mov     rax, [rdx]
0x14000ad00  xor     r15d, r15d
0x14000ad03  cmp     byte ptr [rcx+2], 1
0x14000ad07  mov     rbp, r8
0x14000ad0a  mov     r14, rdx
0x14000ad0d  mov     rdi, rcx
0x14000ad10  jnz     short loc_14000AD49
0x14000ad12  lea     rbx, [rax+2]
0x14000ad16  cmp     rbx, r8
0x14000ad19  ja      loc_14000ADCE
0x14000ad1f  mov     [rcx+10h], rax
0x14000ad23  test    rax, rax
0x14000ad26  jz      short loc_14000AD2D
0x14000ad28  movzx   ecx, word ptr [rax]
0x14000ad2b  jmp     short loc_14000AD41
0x14000ad2d  call    cs:__imp__o__errno
0x14000ad33  mov     dword ptr [rax], 16h
0x14000ad39  call    _invalid_parameter_noinfo
0x14000ad3e  mov     ecx, r15d
0x14000ad41  movzx   eax, cx
0x14000ad44  mov     [rdi+4], eax
0x14000ad47  jmp     short loc_14000AD85
0x14000ad49  cmp     byte ptr [rcx+2], 2
0x14000ad4d  jnz     short loc_14000AD82
0x14000ad4f  lea     rbx, [rax+4]
0x14000ad53  cmp     rbx, rbp
0x14000ad56  ja      short loc_14000ADCE
0x14000ad58  mov     [rcx+10h], rax
0x14000ad5c  add     rcx, 4
0x14000ad60  jz      short loc_14000AD6F
0x14000ad62  test    rax, rax
0x14000ad65  jz      short loc_14000AD6D
0x14000ad67  mov     eax, [rax]
0x14000ad69  mov     [rcx], eax
0x14000ad6b  jmp     short loc_14000AD85
0x14000ad6d  mov     [rcx], eax
0x14000ad6f  call    cs:__imp__o__errno
0x14000ad75  mov     dword ptr [rax], 16h
0x14000ad7b  call    _invalid_parameter_noinfo
0x14000ad80  jmp     short loc_14000AD85
0x14000ad82  mov     rbx, rax
0x14000ad85  movzx   eax, word ptr [rdi]
0x14000ad88  mov     [rdi+8], ax
0x14000ad8c  test    ax, ax
0x14000ad8f  jnz     short loc_14000ADC2
0x14000ad91  lea     rsi, [rbx+2]
0x14000ad95  cmp     rsi, rbp
0x14000ad98  ja      short loc_14000ADCE
0x14000ad9a  test    rbx, rbx
0x14000ad9d  jz      short loc_14000ADA8
0x14000ad9f  movzx   eax, word ptr [rbx]
0x14000ada2  mov     [rdi+8], ax
0x14000ada6  jmp     short loc_14000ADBF
0x14000ada8  xor     eax, eax
0x14000adaa  mov     [rdi+8], ax
0x14000adae  call    cs:__imp__o__errno
0x14000adb4  mov     dword ptr [rax], 16h
0x14000adba  call    _invalid_parameter_noinfo
0x14000adbf  mov     rbx, rsi
0x14000adc2  movzx   ecx, word ptr [rdi+8]
0x14000adc6  add     rcx, rbx
0x14000adc9  cmp     rcx, rbp
0x14000adcc  jbe     short loc_14000ADD2
0x14000adce  xor     al, al
0x14000add0  jmp     short loc_14000ADDB
0x14000add2  mov     [rdi+18h], rbx
0x14000add6  mov     al, 1
0x14000add8  mov     [r14], rcx
0x14000addb  add     rsp, 28h
0x14000addf  pop     r15
0x14000ade1  pop     r14
0x14000ade3  pop     rdi
0x14000ade4  pop     rsi
0x14000ade5  pop     rbp
0x14000ade6  pop     rbx
0x14000ade7  retn
```
