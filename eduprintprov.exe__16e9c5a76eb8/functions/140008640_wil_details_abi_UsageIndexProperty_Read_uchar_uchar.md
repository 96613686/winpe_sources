# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140008640`
- end: `0x140008738`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006ae8`
- `0x140008c88`
- `0x14000905c`

## callees

- `0x1400030aa`
- `0x140008640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000867d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400086bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400086fe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000867d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400086bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400086fe`

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
0x140008640  push    rbx
0x140008642  push    rbp
0x140008643  push    rsi
0x140008644  push    rdi
0x140008645  push    r14
0x140008647  push    r15
0x140008649  sub     rsp, 28h
0x14000864d  mov     rax, [rdx]
0x140008650  xor     r15d, r15d
0x140008653  cmp     byte ptr [rcx+2], 1
0x140008657  mov     rbp, r8
0x14000865a  mov     r14, rdx
0x14000865d  mov     rdi, rcx
0x140008660  jnz     short loc_140008699
0x140008662  lea     rbx, [rax+2]
0x140008666  cmp     rbx, r8
0x140008669  ja      loc_14000871E
0x14000866f  mov     [rcx+10h], rax
0x140008673  test    rax, rax
0x140008676  jz      short loc_14000867D
0x140008678  movzx   ecx, word ptr [rax]
0x14000867b  jmp     short loc_140008691
0x14000867d  call    cs:__imp__o__errno
0x140008683  mov     dword ptr [rax], 16h
0x140008689  call    _invalid_parameter_noinfo
0x14000868e  mov     ecx, r15d
0x140008691  movzx   eax, cx
0x140008694  mov     [rdi+4], eax
0x140008697  jmp     short loc_1400086D5
0x140008699  cmp     byte ptr [rcx+2], 2
0x14000869d  jnz     short loc_1400086D2
0x14000869f  lea     rbx, [rax+4]
0x1400086a3  cmp     rbx, rbp
0x1400086a6  ja      short loc_14000871E
0x1400086a8  mov     [rcx+10h], rax
0x1400086ac  add     rcx, 4
0x1400086b0  jz      short loc_1400086BF
0x1400086b2  test    rax, rax
0x1400086b5  jz      short loc_1400086BD
0x1400086b7  mov     eax, [rax]
0x1400086b9  mov     [rcx], eax
0x1400086bb  jmp     short loc_1400086D5
0x1400086bd  mov     [rcx], eax
0x1400086bf  call    cs:__imp__o__errno
0x1400086c5  mov     dword ptr [rax], 16h
0x1400086cb  call    _invalid_parameter_noinfo
0x1400086d0  jmp     short loc_1400086D5
0x1400086d2  mov     rbx, rax
0x1400086d5  movzx   eax, word ptr [rdi]
0x1400086d8  mov     [rdi+8], ax
0x1400086dc  test    ax, ax
0x1400086df  jnz     short loc_140008712
0x1400086e1  lea     rsi, [rbx+2]
0x1400086e5  cmp     rsi, rbp
0x1400086e8  ja      short loc_14000871E
0x1400086ea  test    rbx, rbx
0x1400086ed  jz      short loc_1400086F8
0x1400086ef  movzx   eax, word ptr [rbx]
0x1400086f2  mov     [rdi+8], ax
0x1400086f6  jmp     short loc_14000870F
0x1400086f8  xor     eax, eax
0x1400086fa  mov     [rdi+8], ax
0x1400086fe  call    cs:__imp__o__errno
0x140008704  mov     dword ptr [rax], 16h
0x14000870a  call    _invalid_parameter_noinfo
0x14000870f  mov     rbx, rsi
0x140008712  movzx   ecx, word ptr [rdi+8]
0x140008716  add     rcx, rbx
0x140008719  cmp     rcx, rbp
0x14000871c  jbe     short loc_140008722
0x14000871e  xor     al, al
0x140008720  jmp     short loc_14000872B
0x140008722  mov     [rdi+18h], rbx
0x140008726  mov     al, 1
0x140008728  mov     [r14], rcx
0x14000872b  add     rsp, 28h
0x14000872f  pop     r15
0x140008731  pop     r14
0x140008733  pop     rdi
0x140008734  pop     rsi
0x140008735  pop     rbp
0x140008736  pop     rbx
0x140008737  retn
```
