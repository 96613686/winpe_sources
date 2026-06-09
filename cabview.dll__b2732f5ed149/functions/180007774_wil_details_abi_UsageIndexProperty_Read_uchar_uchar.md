# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180007774`
- end: `0x180007876`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180005898`
- `0x1800068b0`
- `0x180006d90`
- `0x180007ddc`
- `0x180008994`

## callees

- `0x180002620`
- `0x180007774`
- `0x18000a310`

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
0x180007774  mov     r11, rsp
0x180007777  mov     [r11+18h], rbx
0x18000777b  mov     [r11+20h], rbp
0x18000777f  push    rsi
0x180007780  push    rdi
0x180007781  push    r12
0x180007783  push    r14
0x180007785  push    r15
0x180007787  sub     rsp, 30h
0x18000778b  mov     rax, cs:__security_cookie
0x180007792  xor     rax, rsp
0x180007795  mov     [rsp+58h+var_30], rax
0x18000779a  xor     r15d, r15d
0x18000779d  mov     rsi, r8
0x1800077a0  cmp     byte ptr [rcx+2], 1
0x1800077a4  mov     r12, rdx
0x1800077a7  mov     r8, [rdx]; Source
0x1800077aa  mov     rdi, rcx
0x1800077ad  jnz     short loc_1800077E1
0x1800077af  lea     rbx, [r8+2]
0x1800077b3  cmp     rbx, rsi
0x1800077b6  ja      loc_180007844
0x1800077bc  lea     ebp, [r15+2]
0x1800077c0  mov     [rcx+10h], r8
0x1800077c4  mov     r9d, ebp; SourceSize
0x1800077c7  mov     [r11-38h], r15w
0x1800077cc  mov     edx, ebp; DestinationSize
0x1800077ce  lea     rcx, [r11-38h]; Destination
0x1800077d2  call    memcpy_s
0x1800077d7  movzx   eax, [rsp+58h+var_38]
0x1800077dc  mov     [rdi+4], eax
0x1800077df  jmp     short loc_18000780B
0x1800077e1  mov     ebp, 2
0x1800077e6  mov     rbx, r8
0x1800077e9  cmp     [rcx+2], bpl
0x1800077ed  jnz     short loc_18000780B
0x1800077ef  lea     rbx, [r8+4]
0x1800077f3  cmp     rbx, rsi
0x1800077f6  ja      short loc_180007844
0x1800077f8  lea     edx, [rbp+2]; DestinationSize
0x1800077fb  mov     [rcx+10h], r8
0x1800077ff  mov     r9d, edx; SourceSize
0x180007802  add     rcx, 4; Destination
0x180007806  call    memcpy_s
0x18000780b  movzx   eax, word ptr [rdi]
0x18000780e  lea     r14, [rdi+8]
0x180007812  mov     [r14], ax
0x180007816  test    ax, ax
0x180007819  jnz     short loc_180007838
0x18000781b  lea     r15, [rbx+2]
0x18000781f  cmp     r15, rsi
0x180007822  ja      short loc_180007844
0x180007824  mov     r9, rbp; SourceSize
0x180007827  mov     r8, rbx; Source
0x18000782a  mov     rdx, rbp; DestinationSize
0x18000782d  mov     rcx, r14; Destination
0x180007830  call    memcpy_s
0x180007835  mov     rbx, r15
0x180007838  movzx   ecx, word ptr [r14]
0x18000783c  add     rcx, rbx
0x18000783f  cmp     rcx, rsi
0x180007842  jbe     short loc_180007848
0x180007844  xor     al, al
0x180007846  jmp     short loc_180007852
0x180007848  mov     [rdi+18h], rbx
0x18000784c  mov     al, 1
0x18000784e  mov     [r12], rcx
0x180007852  mov     rcx, [rsp+58h+var_30]
0x180007857  xor     rcx, rsp; StackCookie
0x18000785a  call    __security_check_cookie
0x18000785f  mov     rbx, [rsp+58h+arg_10]
0x180007864  mov     rbp, [rsp+58h+arg_18]
0x180007869  add     rsp, 30h
0x18000786d  pop     r15
0x18000786f  pop     r14
0x180007871  pop     r12
0x180007873  pop     rdi
0x180007874  pop     rsi
0x180007875  retn
```
