# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800056a0`
- end: `0x180005798`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003eec`
- `0x180005ce0`
- `0x1800060b4`

## callees

- `0x180001eae`
- `0x1800056a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800056dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000571f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000575e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800056dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000571f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000575e`

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
0x1800056a0  push    rbx
0x1800056a2  push    rbp
0x1800056a3  push    rsi
0x1800056a4  push    rdi
0x1800056a5  push    r14
0x1800056a7  push    r15
0x1800056a9  sub     rsp, 28h
0x1800056ad  mov     rax, [rdx]
0x1800056b0  xor     r15d, r15d
0x1800056b3  cmp     byte ptr [rcx+2], 1
0x1800056b7  mov     rbp, r8
0x1800056ba  mov     r14, rdx
0x1800056bd  mov     rdi, rcx
0x1800056c0  jnz     short loc_1800056F9
0x1800056c2  lea     rbx, [rax+2]
0x1800056c6  cmp     rbx, r8
0x1800056c9  ja      loc_18000577E
0x1800056cf  mov     [rcx+10h], rax
0x1800056d3  test    rax, rax
0x1800056d6  jz      short loc_1800056DD
0x1800056d8  movzx   ecx, word ptr [rax]
0x1800056db  jmp     short loc_1800056F1
0x1800056dd  call    cs:__imp__o__errno
0x1800056e3  mov     dword ptr [rax], 16h
0x1800056e9  call    _invalid_parameter_noinfo
0x1800056ee  mov     ecx, r15d
0x1800056f1  movzx   eax, cx
0x1800056f4  mov     [rdi+4], eax
0x1800056f7  jmp     short loc_180005735
0x1800056f9  cmp     byte ptr [rcx+2], 2
0x1800056fd  jnz     short loc_180005732
0x1800056ff  lea     rbx, [rax+4]
0x180005703  cmp     rbx, rbp
0x180005706  ja      short loc_18000577E
0x180005708  mov     [rcx+10h], rax
0x18000570c  add     rcx, 4
0x180005710  jz      short loc_18000571F
0x180005712  test    rax, rax
0x180005715  jz      short loc_18000571D
0x180005717  mov     eax, [rax]
0x180005719  mov     [rcx], eax
0x18000571b  jmp     short loc_180005735
0x18000571d  mov     [rcx], eax
0x18000571f  call    cs:__imp__o__errno
0x180005725  mov     dword ptr [rax], 16h
0x18000572b  call    _invalid_parameter_noinfo
0x180005730  jmp     short loc_180005735
0x180005732  mov     rbx, rax
0x180005735  movzx   eax, word ptr [rdi]
0x180005738  mov     [rdi+8], ax
0x18000573c  test    ax, ax
0x18000573f  jnz     short loc_180005772
0x180005741  lea     rsi, [rbx+2]
0x180005745  cmp     rsi, rbp
0x180005748  ja      short loc_18000577E
0x18000574a  test    rbx, rbx
0x18000574d  jz      short loc_180005758
0x18000574f  movzx   eax, word ptr [rbx]
0x180005752  mov     [rdi+8], ax
0x180005756  jmp     short loc_18000576F
0x180005758  xor     eax, eax
0x18000575a  mov     [rdi+8], ax
0x18000575e  call    cs:__imp__o__errno
0x180005764  mov     dword ptr [rax], 16h
0x18000576a  call    _invalid_parameter_noinfo
0x18000576f  mov     rbx, rsi
0x180005772  movzx   ecx, word ptr [rdi+8]
0x180005776  add     rcx, rbx
0x180005779  cmp     rcx, rbp
0x18000577c  jbe     short loc_180005782
0x18000577e  xor     al, al
0x180005780  jmp     short loc_18000578B
0x180005782  mov     [rdi+18h], rbx
0x180005786  mov     al, 1
0x180005788  mov     [r14], rcx
0x18000578b  add     rsp, 28h
0x18000578f  pop     r15
0x180005791  pop     r14
0x180005793  pop     rdi
0x180005794  pop     rsi
0x180005795  pop     rbp
0x180005796  pop     rbx
0x180005797  retn
```
