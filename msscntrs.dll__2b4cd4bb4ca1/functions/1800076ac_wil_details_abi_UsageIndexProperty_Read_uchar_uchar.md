# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800076ac`
- end: `0x1800077a4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005de0`
- `0x180007f38`
- `0x18000830c`

## callees

- `0x1800032b2`
- `0x1800076ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800076e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000772b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000776a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800076e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000772b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000776a`

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
0x1800076ac  push    rbx
0x1800076ae  push    rbp
0x1800076af  push    rsi
0x1800076b0  push    rdi
0x1800076b1  push    r14
0x1800076b3  push    r15
0x1800076b5  sub     rsp, 28h
0x1800076b9  mov     rax, [rdx]
0x1800076bc  xor     r15d, r15d
0x1800076bf  cmp     byte ptr [rcx+2], 1
0x1800076c3  mov     rbp, r8
0x1800076c6  mov     r14, rdx
0x1800076c9  mov     rdi, rcx
0x1800076cc  jnz     short loc_180007705
0x1800076ce  lea     rbx, [rax+2]
0x1800076d2  cmp     rbx, r8
0x1800076d5  ja      loc_18000778A
0x1800076db  mov     [rcx+10h], rax
0x1800076df  test    rax, rax
0x1800076e2  jz      short loc_1800076E9
0x1800076e4  movzx   ecx, word ptr [rax]
0x1800076e7  jmp     short loc_1800076FD
0x1800076e9  call    cs:__imp__o__errno
0x1800076ef  mov     dword ptr [rax], 16h
0x1800076f5  call    _invalid_parameter_noinfo
0x1800076fa  mov     ecx, r15d
0x1800076fd  movzx   eax, cx
0x180007700  mov     [rdi+4], eax
0x180007703  jmp     short loc_180007741
0x180007705  cmp     byte ptr [rcx+2], 2
0x180007709  jnz     short loc_18000773E
0x18000770b  lea     rbx, [rax+4]
0x18000770f  cmp     rbx, rbp
0x180007712  ja      short loc_18000778A
0x180007714  mov     [rcx+10h], rax
0x180007718  add     rcx, 4
0x18000771c  jz      short loc_18000772B
0x18000771e  test    rax, rax
0x180007721  jz      short loc_180007729
0x180007723  mov     eax, [rax]
0x180007725  mov     [rcx], eax
0x180007727  jmp     short loc_180007741
0x180007729  mov     [rcx], eax
0x18000772b  call    cs:__imp__o__errno
0x180007731  mov     dword ptr [rax], 16h
0x180007737  call    _invalid_parameter_noinfo
0x18000773c  jmp     short loc_180007741
0x18000773e  mov     rbx, rax
0x180007741  movzx   eax, word ptr [rdi]
0x180007744  mov     [rdi+8], ax
0x180007748  test    ax, ax
0x18000774b  jnz     short loc_18000777E
0x18000774d  lea     rsi, [rbx+2]
0x180007751  cmp     rsi, rbp
0x180007754  ja      short loc_18000778A
0x180007756  test    rbx, rbx
0x180007759  jz      short loc_180007764
0x18000775b  movzx   eax, word ptr [rbx]
0x18000775e  mov     [rdi+8], ax
0x180007762  jmp     short loc_18000777B
0x180007764  xor     eax, eax
0x180007766  mov     [rdi+8], ax
0x18000776a  call    cs:__imp__o__errno
0x180007770  mov     dword ptr [rax], 16h
0x180007776  call    _invalid_parameter_noinfo
0x18000777b  mov     rbx, rsi
0x18000777e  movzx   ecx, word ptr [rdi+8]
0x180007782  add     rcx, rbx
0x180007785  cmp     rcx, rbp
0x180007788  jbe     short loc_18000778E
0x18000778a  xor     al, al
0x18000778c  jmp     short loc_180007797
0x18000778e  mov     [rdi+18h], rbx
0x180007792  mov     al, 1
0x180007794  mov     [r14], rcx
0x180007797  add     rsp, 28h
0x18000779b  pop     r15
0x18000779d  pop     r14
0x18000779f  pop     rdi
0x1800077a0  pop     rsi
0x1800077a1  pop     rbp
0x1800077a2  pop     rbx
0x1800077a3  retn
```
