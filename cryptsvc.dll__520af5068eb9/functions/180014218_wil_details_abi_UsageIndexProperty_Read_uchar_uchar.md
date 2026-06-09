# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180014218`
- end: `0x1800142fe`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc00`
- `0x18001278c`
- `0x180013a14`
- `0x180013ed4`
- `0x180014cf0`

## callees

- `0x18000ec1c`
- `0x180014218`

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
0x180014218  mov     rax, rsp
0x18001421b  mov     [rax+10h], rbx
0x18001421f  mov     [rax+18h], rbp
0x180014223  push    rsi
0x180014224  push    rdi
0x180014225  push    r12
0x180014227  push    r14
0x180014229  push    r15
0x18001422b  sub     rsp, 20h
0x18001422f  xor     r15d, r15d
0x180014232  mov     rsi, r8
0x180014235  cmp     byte ptr [rcx+2], 1
0x180014239  mov     r12, rdx
0x18001423c  mov     r8, [rdx]; Source
0x18001423f  mov     rdi, rcx
0x180014242  jnz     short loc_180014276
0x180014244  lea     rbx, [r8+2]
0x180014248  cmp     rbx, rsi
0x18001424b  ja      loc_1800142D9
0x180014251  lea     ebp, [r15+2]
0x180014255  mov     [rcx+10h], r8
0x180014259  mov     r9d, ebp; SourceSize
0x18001425c  mov     [rax+8], r15w
0x180014261  mov     edx, ebp; DestinationSize
0x180014263  lea     rcx, [rax+8]; Destination
0x180014267  call    memcpy_s
0x18001426c  movzx   eax, [rsp+48h+arg_0]
0x180014271  mov     [rdi+4], eax
0x180014274  jmp     short loc_1800142A0
0x180014276  mov     ebp, 2
0x18001427b  mov     rbx, r8
0x18001427e  cmp     [rcx+2], bpl
0x180014282  jnz     short loc_1800142A0
0x180014284  lea     rbx, [r8+4]
0x180014288  cmp     rbx, rsi
0x18001428b  ja      short loc_1800142D9
0x18001428d  lea     edx, [rbp+2]; DestinationSize
0x180014290  mov     [rcx+10h], r8
0x180014294  mov     r9d, edx; SourceSize
0x180014297  add     rcx, 4; Destination
0x18001429b  call    memcpy_s
0x1800142a0  movzx   eax, word ptr [rdi]
0x1800142a3  lea     r14, [rdi+8]
0x1800142a7  mov     [r14], ax
0x1800142ab  test    ax, ax
0x1800142ae  jnz     short loc_1800142CD
0x1800142b0  lea     r15, [rbx+2]
0x1800142b4  cmp     r15, rsi
0x1800142b7  ja      short loc_1800142D9
0x1800142b9  mov     r9, rbp; SourceSize
0x1800142bc  mov     r8, rbx; Source
0x1800142bf  mov     rdx, rbp; DestinationSize
0x1800142c2  mov     rcx, r14; Destination
0x1800142c5  call    memcpy_s
0x1800142ca  mov     rbx, r15
0x1800142cd  movzx   ecx, word ptr [r14]
0x1800142d1  add     rcx, rbx
0x1800142d4  cmp     rcx, rsi
0x1800142d7  jbe     short loc_1800142DD
0x1800142d9  xor     al, al
0x1800142db  jmp     short loc_1800142E7
0x1800142dd  mov     [rdi+18h], rbx
0x1800142e1  mov     al, 1
0x1800142e3  mov     [r12], rcx
0x1800142e7  mov     rbx, [rsp+48h+arg_8]
0x1800142ec  mov     rbp, [rsp+48h+arg_10]
0x1800142f1  add     rsp, 20h
0x1800142f5  pop     r15
0x1800142f7  pop     r14
0x1800142f9  pop     r12
0x1800142fb  pop     rdi
0x1800142fc  pop     rsi
0x1800142fd  retn
```
