# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180008274`
- end: `0x180008376`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800035a4`
- `0x180006954`
- `0x180007528`
- `0x180007bcc`
- `0x180009200`

## callees

- `0x180003404`
- `0x180004310`
- `0x180008274`

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
  unsigned __int16 v11; // [rsp+20h] [rbp-38h] BYREF

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
0x180008274  mov     r11, rsp
0x180008277  mov     [r11+18h], rbx
0x18000827b  mov     [r11+20h], rbp
0x18000827f  push    rsi
0x180008280  push    rdi
0x180008281  push    r12
0x180008283  push    r14
0x180008285  push    r15
0x180008287  sub     rsp, 30h
0x18000828b  mov     rax, cs:__security_cookie
0x180008292  xor     rax, rsp
0x180008295  mov     [rsp+58h+var_30], rax
0x18000829a  xor     r15d, r15d
0x18000829d  mov     rsi, r8
0x1800082a0  cmp     byte ptr [rcx+2], 1
0x1800082a4  mov     r12, rdx
0x1800082a7  mov     r8, [rdx]; Source
0x1800082aa  mov     rdi, rcx
0x1800082ad  jnz     short loc_1800082E1
0x1800082af  lea     rbx, [r8+2]
0x1800082b3  cmp     rbx, rsi
0x1800082b6  ja      loc_180008344
0x1800082bc  lea     ebp, [r15+2]
0x1800082c0  mov     [rcx+10h], r8
0x1800082c4  mov     r9d, ebp; SourceSize
0x1800082c7  mov     [r11-38h], r15w
0x1800082cc  mov     edx, ebp; DestinationSize
0x1800082ce  lea     rcx, [r11-38h]; Destination
0x1800082d2  call    memcpy_s
0x1800082d7  movzx   eax, [rsp+58h+var_38]
0x1800082dc  mov     [rdi+4], eax
0x1800082df  jmp     short loc_18000830B
0x1800082e1  mov     ebp, 2
0x1800082e6  mov     rbx, r8
0x1800082e9  cmp     [rcx+2], bpl
0x1800082ed  jnz     short loc_18000830B
0x1800082ef  lea     rbx, [r8+4]
0x1800082f3  cmp     rbx, rsi
0x1800082f6  ja      short loc_180008344
0x1800082f8  lea     edx, [rbp+2]; DestinationSize
0x1800082fb  mov     [rcx+10h], r8
0x1800082ff  mov     r9d, edx; SourceSize
0x180008302  add     rcx, 4; Destination
0x180008306  call    memcpy_s
0x18000830b  movzx   eax, word ptr [rdi]
0x18000830e  lea     r14, [rdi+8]
0x180008312  mov     [r14], ax
0x180008316  test    ax, ax
0x180008319  jnz     short loc_180008338
0x18000831b  lea     r15, [rbx+2]
0x18000831f  cmp     r15, rsi
0x180008322  ja      short loc_180008344
0x180008324  mov     r9, rbp; SourceSize
0x180008327  mov     r8, rbx; Source
0x18000832a  mov     rdx, rbp; DestinationSize
0x18000832d  mov     rcx, r14; Destination
0x180008330  call    memcpy_s
0x180008335  mov     rbx, r15
0x180008338  movzx   ecx, word ptr [r14]
0x18000833c  add     rcx, rbx
0x18000833f  cmp     rcx, rsi
0x180008342  jbe     short loc_180008348
0x180008344  xor     al, al
0x180008346  jmp     short loc_180008352
0x180008348  mov     [rdi+18h], rbx
0x18000834c  mov     al, 1
0x18000834e  mov     [r12], rcx
0x180008352  mov     rcx, [rsp+58h+var_30]
0x180008357  xor     rcx, rsp; StackCookie
0x18000835a  call    __security_check_cookie
0x18000835f  mov     rbx, [rsp+58h+arg_10]
0x180008364  mov     rbp, [rsp+58h+arg_18]
0x180008369  add     rsp, 30h
0x18000836d  pop     r15
0x18000836f  pop     r14
0x180008371  pop     r12
0x180008373  pop     rdi
0x180008374  pop     rsi
0x180008375  retn
```
