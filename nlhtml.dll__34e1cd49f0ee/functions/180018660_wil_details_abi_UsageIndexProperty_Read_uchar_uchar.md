# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180018660`
- end: `0x180018746`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180016d78`
- `0x1800179cc`
- `0x180017e0c`
- `0x180018cc8`
- `0x180019a40`

## callees

- `0x180018660`
- `0x18001aea4`

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
0x180018660  mov     rax, rsp
0x180018663  mov     [rax+10h], rbx
0x180018667  mov     [rax+18h], rbp
0x18001866b  push    rsi
0x18001866c  push    rdi
0x18001866d  push    r12
0x18001866f  push    r14
0x180018671  push    r15
0x180018673  sub     rsp, 20h
0x180018677  xor     r15d, r15d
0x18001867a  mov     rsi, r8
0x18001867d  cmp     byte ptr [rcx+2], 1
0x180018681  mov     r12, rdx
0x180018684  mov     r8, [rdx]; Source
0x180018687  mov     rdi, rcx
0x18001868a  jnz     short loc_1800186BE
0x18001868c  lea     rbx, [r8+2]
0x180018690  cmp     rbx, rsi
0x180018693  ja      loc_180018721
0x180018699  lea     ebp, [r15+2]
0x18001869d  mov     [rcx+10h], r8
0x1800186a1  mov     r9d, ebp; SourceSize
0x1800186a4  mov     [rax+8], r15w
0x1800186a9  mov     edx, ebp; DestinationSize
0x1800186ab  lea     rcx, [rax+8]; Destination
0x1800186af  call    memcpy_s
0x1800186b4  movzx   eax, [rsp+48h+arg_0]
0x1800186b9  mov     [rdi+4], eax
0x1800186bc  jmp     short loc_1800186E8
0x1800186be  mov     ebp, 2
0x1800186c3  mov     rbx, r8
0x1800186c6  cmp     [rcx+2], bpl
0x1800186ca  jnz     short loc_1800186E8
0x1800186cc  lea     rbx, [r8+4]
0x1800186d0  cmp     rbx, rsi
0x1800186d3  ja      short loc_180018721
0x1800186d5  lea     edx, [rbp+2]; DestinationSize
0x1800186d8  mov     [rcx+10h], r8
0x1800186dc  mov     r9d, edx; SourceSize
0x1800186df  add     rcx, 4; Destination
0x1800186e3  call    memcpy_s
0x1800186e8  movzx   eax, word ptr [rdi]
0x1800186eb  lea     r14, [rdi+8]
0x1800186ef  mov     [r14], ax
0x1800186f3  test    ax, ax
0x1800186f6  jnz     short loc_180018715
0x1800186f8  lea     r15, [rbx+2]
0x1800186fc  cmp     r15, rsi
0x1800186ff  ja      short loc_180018721
0x180018701  mov     r9, rbp; SourceSize
0x180018704  mov     r8, rbx; Source
0x180018707  mov     rdx, rbp; DestinationSize
0x18001870a  mov     rcx, r14; Destination
0x18001870d  call    memcpy_s
0x180018712  mov     rbx, r15
0x180018715  movzx   ecx, word ptr [r14]
0x180018719  add     rcx, rbx
0x18001871c  cmp     rcx, rsi
0x18001871f  jbe     short loc_180018725
0x180018721  xor     al, al
0x180018723  jmp     short loc_18001872F
0x180018725  mov     [rdi+18h], rbx
0x180018729  mov     al, 1
0x18001872b  mov     [r12], rcx
0x18001872f  mov     rbx, [rsp+48h+arg_8]
0x180018734  mov     rbp, [rsp+48h+arg_10]
0x180018739  add     rsp, 20h
0x18001873d  pop     r15
0x18001873f  pop     r14
0x180018741  pop     r12
0x180018743  pop     rdi
0x180018744  pop     rsi
0x180018745  retn
```
