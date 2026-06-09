# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180004028`
- end: `0x18000412a`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039ac`
- `0x180003c54`
- `0x180003d88`
- `0x180003f40`
- `0x18000dd50`

## callees

- `0x180004028`
- `0x18000be22`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800040e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800040f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004117`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800040e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800040f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004117`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v7; // rbx
  _DWORD *v8; // rcx
  unsigned __int16 v9; // cx
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
      v9 = *v3;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v9 = 0;
    }
    *((_DWORD *)this + 1) = v9;
    goto LABEL_11;
  }
  if ( *((_BYTE *)this + 2) != 2 )
  {
    v7 = (unsigned __int16 *)*a2;
    goto LABEL_11;
  }
  v7 = v3 + 2;
  if ( v3 + 2 > (unsigned __int16 *)a3 )
    return 0;
  *((_QWORD *)this + 2) = v3;
  v8 = (_DWORD *)((char *)this + 4);
  if ( !v8 )
    goto LABEL_21;
  if ( !v3 )
  {
    *v8 = 0;
LABEL_21:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
  *v8 = *(_DWORD *)v3;
LABEL_11:
  v10 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( !v10 )
  {
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
  }
  v11 = (unsigned __int8 *)v7 + *((unsigned __int16 *)this + 4);
  if ( v11 <= a3 )
  {
    *((_QWORD *)this + 3) = v7;
    result = 1;
    *a2 = v11;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180004028  push    rbx
0x18000402a  push    rbp
0x18000402b  push    rsi
0x18000402c  push    rdi
0x18000402d  push    r14
0x18000402f  push    r15
0x180004031  sub     rsp, 28h
0x180004035  mov     rax, [rdx]
0x180004038  xor     r15d, r15d
0x18000403b  cmp     byte ptr [rcx+2], 1
0x18000403f  mov     rbp, r8
0x180004042  mov     r14, rdx
0x180004045  mov     rdi, rcx
0x180004048  jz      short loc_18000407A
0x18000404a  cmp     byte ptr [rcx+2], 2
0x18000404e  jnz     loc_18000410C
0x180004054  lea     rbx, [rax+4]
0x180004058  cmp     rbx, r8
0x18000405b  ja      short loc_1800040C3
0x18000405d  mov     [rcx+10h], rax
0x180004061  add     rcx, 4
0x180004065  jz      loc_1800040F9
0x18000406b  test    rax, rax
0x18000406e  jz      loc_1800040F7
0x180004074  mov     eax, [rax]
0x180004076  mov     [rcx], eax
0x180004078  jmp     short loc_180004095
0x18000407a  lea     rbx, [rax+2]
0x18000407e  cmp     rbx, rbp
0x180004081  ja      short loc_1800040C3
0x180004083  mov     [rcx+10h], rax
0x180004087  test    rax, rax
0x18000408a  jz      short loc_1800040E1
0x18000408c  movzx   ecx, word ptr [rax]
0x18000408f  movzx   eax, cx
0x180004092  mov     [rdi+4], eax
0x180004095  movzx   eax, word ptr [rdi]
0x180004098  mov     [rdi+8], ax
0x18000409c  test    ax, ax
0x18000409f  jz      short loc_1800040C7
0x1800040a1  movzx   ecx, word ptr [rdi+8]
0x1800040a5  add     rcx, rbx
0x1800040a8  cmp     rcx, rbp
0x1800040ab  ja      short loc_1800040C3
0x1800040ad  mov     [rdi+18h], rbx
0x1800040b1  mov     al, 1
0x1800040b3  mov     [r14], rcx
0x1800040b6  add     rsp, 28h
0x1800040ba  pop     r15
0x1800040bc  pop     r14
0x1800040be  pop     rdi
0x1800040bf  pop     rsi
0x1800040c0  pop     rbp
0x1800040c1  pop     rbx
0x1800040c2  retn
0x1800040c3  xor     al, al
0x1800040c5  jmp     short loc_1800040B6
0x1800040c7  lea     rsi, [rbx+2]
0x1800040cb  cmp     rsi, rbp
0x1800040ce  ja      short loc_1800040C3
0x1800040d0  test    rbx, rbx
0x1800040d3  jz      short loc_180004111
0x1800040d5  movzx   eax, word ptr [rbx]
0x1800040d8  mov     [rdi+8], ax
0x1800040dc  mov     rbx, rsi
0x1800040df  jmp     short loc_1800040A1
0x1800040e1  call    cs:__imp__o__errno
0x1800040e7  mov     dword ptr [rax], 16h
0x1800040ed  call    _invalid_parameter_noinfo
0x1800040f2  mov     ecx, r15d
0x1800040f5  jmp     short loc_18000408F
0x1800040f7  mov     [rcx], eax
0x1800040f9  call    cs:__imp__o__errno
0x1800040ff  mov     dword ptr [rax], 16h
0x180004105  call    _invalid_parameter_noinfo
0x18000410a  jmp     short loc_180004095
0x18000410c  mov     rbx, rax
0x18000410f  jmp     short loc_180004095
0x180004111  xor     eax, eax
0x180004113  mov     [rdi+8], ax
0x180004117  call    cs:__imp__o__errno
0x18000411d  mov     dword ptr [rax], 16h
0x180004123  call    _invalid_parameter_noinfo
0x180004128  jmp     short loc_1800040DC
```
