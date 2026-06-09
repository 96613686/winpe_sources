# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000642c`
- end: `0x180006515`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d0c`
- `0x180006a60`
- `0x180006de8`

## callees

- `0x18000642c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000647b`
- `msvcrt!memcpy_s` at `0x1800064b0`
- `msvcrt!memcpy_s` at `0x1800064db`
- `msvcrt!memcpy_s` at `0x18000647b`
- `msvcrt!memcpy_s` at `0x1800064b0`
- `msvcrt!memcpy_s` at `0x1800064db`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x18000642c  mov     rax, rsp
0x18000642f  mov     [rax+10h], rbx
0x180006433  mov     [rax+18h], rbp
0x180006437  push    rsi
0x180006438  push    rdi
0x180006439  push    r12
0x18000643b  push    r14
0x18000643d  push    r15
0x18000643f  sub     rsp, 20h
0x180006443  xor     r15d, r15d
0x180006446  mov     rsi, r8
0x180006449  cmp     byte ptr [rcx+2], 1
0x18000644d  mov     r12, rdx
0x180006450  mov     r8, [rdx]; Source
0x180006453  mov     rdi, rcx
0x180006456  jnz     short loc_18000648B
0x180006458  lea     rbx, [r8+2]
0x18000645c  cmp     rbx, rsi
0x18000645f  ja      loc_1800064F0
0x180006465  lea     ebp, [r15+2]
0x180006469  mov     [rcx+10h], r8
0x18000646d  mov     r9d, ebp; SourceSize
0x180006470  mov     [rax+8], r15w
0x180006475  mov     edx, ebp; DestinationSize
0x180006477  lea     rcx, [rax+8]; Destination
0x18000647b  call    cs:__imp_memcpy_s
0x180006481  movzx   eax, [rsp+48h+arg_0]
0x180006486  mov     [rdi+4], eax
0x180006489  jmp     short loc_1800064B6
0x18000648b  mov     ebp, 2
0x180006490  mov     rbx, r8
0x180006493  cmp     [rcx+2], bpl
0x180006497  jnz     short loc_1800064B6
0x180006499  lea     rbx, [r8+4]
0x18000649d  cmp     rbx, rsi
0x1800064a0  ja      short loc_1800064F0
0x1800064a2  lea     edx, [rbp+2]; DestinationSize
0x1800064a5  mov     [rcx+10h], r8
0x1800064a9  mov     r9d, edx; SourceSize
0x1800064ac  add     rcx, 4; Destination
0x1800064b0  call    cs:__imp_memcpy_s
0x1800064b6  movzx   eax, word ptr [rdi]
0x1800064b9  lea     r14, [rdi+8]
0x1800064bd  mov     [r14], ax
0x1800064c1  test    ax, ax
0x1800064c4  jnz     short loc_1800064E4
0x1800064c6  lea     r15, [rbx+2]
0x1800064ca  cmp     r15, rsi
0x1800064cd  ja      short loc_1800064F0
0x1800064cf  mov     r9, rbp; SourceSize
0x1800064d2  mov     r8, rbx; Source
0x1800064d5  mov     rdx, rbp; DestinationSize
0x1800064d8  mov     rcx, r14; Destination
0x1800064db  call    cs:__imp_memcpy_s
0x1800064e1  mov     rbx, r15
0x1800064e4  movzx   ecx, word ptr [r14]
0x1800064e8  add     rcx, rbx
0x1800064eb  cmp     rcx, rsi
0x1800064ee  jbe     short loc_1800064F4
0x1800064f0  xor     al, al
0x1800064f2  jmp     short loc_1800064FE
0x1800064f4  mov     [rdi+18h], rbx
0x1800064f8  mov     al, 1
0x1800064fa  mov     [r12], rcx
0x1800064fe  mov     rbx, [rsp+48h+arg_8]
0x180006503  mov     rbp, [rsp+48h+arg_10]
0x180006508  add     rsp, 20h
0x18000650c  pop     r15
0x18000650e  pop     r14
0x180006510  pop     r12
0x180006512  pop     rdi
0x180006513  pop     rsi
0x180006514  retn
```
