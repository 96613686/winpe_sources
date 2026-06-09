# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140079d98`
- end: `0x140079e7e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140075778`
- `0x14007863c`
- `0x140079478`
- `0x140079914`
- `0x14007ac0c`

## callees

- `0x140079d98`
- `0x14007bed8`

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
0x140079d98  mov     rax, rsp
0x140079d9b  mov     [rax+10h], rbx
0x140079d9f  mov     [rax+18h], rbp
0x140079da3  push    rsi
0x140079da4  push    rdi
0x140079da5  push    r12
0x140079da7  push    r14
0x140079da9  push    r15
0x140079dab  sub     rsp, 20h
0x140079daf  xor     r15d, r15d
0x140079db2  mov     rsi, r8
0x140079db5  cmp     byte ptr [rcx+2], 1
0x140079db9  mov     r12, rdx
0x140079dbc  mov     r8, [rdx]; Source
0x140079dbf  mov     rdi, rcx
0x140079dc2  jnz     short loc_140079DF6
0x140079dc4  lea     rbx, [r8+2]
0x140079dc8  cmp     rbx, rsi
0x140079dcb  ja      loc_140079E59
0x140079dd1  lea     ebp, [r15+2]
0x140079dd5  mov     [rcx+10h], r8
0x140079dd9  mov     r9d, ebp; SourceSize
0x140079ddc  mov     [rax+8], r15w
0x140079de1  mov     edx, ebp; DestinationSize
0x140079de3  lea     rcx, [rax+8]; Destination
0x140079de7  call    memcpy_s
0x140079dec  movzx   eax, [rsp+48h+arg_0]
0x140079df1  mov     [rdi+4], eax
0x140079df4  jmp     short loc_140079E20
0x140079df6  mov     ebp, 2
0x140079dfb  mov     rbx, r8
0x140079dfe  cmp     [rcx+2], bpl
0x140079e02  jnz     short loc_140079E20
0x140079e04  lea     rbx, [r8+4]
0x140079e08  cmp     rbx, rsi
0x140079e0b  ja      short loc_140079E59
0x140079e0d  lea     edx, [rbp+2]; DestinationSize
0x140079e10  mov     [rcx+10h], r8
0x140079e14  mov     r9d, edx; SourceSize
0x140079e17  add     rcx, 4; Destination
0x140079e1b  call    memcpy_s
0x140079e20  movzx   eax, word ptr [rdi]
0x140079e23  lea     r14, [rdi+8]
0x140079e27  mov     [r14], ax
0x140079e2b  test    ax, ax
0x140079e2e  jnz     short loc_140079E4D
0x140079e30  lea     r15, [rbx+2]
0x140079e34  cmp     r15, rsi
0x140079e37  ja      short loc_140079E59
0x140079e39  mov     r9, rbp; SourceSize
0x140079e3c  mov     r8, rbx; Source
0x140079e3f  mov     rdx, rbp; DestinationSize
0x140079e42  mov     rcx, r14; Destination
0x140079e45  call    memcpy_s
0x140079e4a  mov     rbx, r15
0x140079e4d  movzx   ecx, word ptr [r14]
0x140079e51  add     rcx, rbx
0x140079e54  cmp     rcx, rsi
0x140079e57  jbe     short loc_140079E5D
0x140079e59  xor     al, al
0x140079e5b  jmp     short loc_140079E67
0x140079e5d  mov     [rdi+18h], rbx
0x140079e61  mov     al, 1
0x140079e63  mov     [r12], rcx
0x140079e67  mov     rbx, [rsp+48h+arg_8]
0x140079e6c  mov     rbp, [rsp+48h+arg_10]
0x140079e71  add     rsp, 20h
0x140079e75  pop     r15
0x140079e77  pop     r14
0x140079e79  pop     r12
0x140079e7b  pop     rdi
0x140079e7c  pop     rsi
0x140079e7d  retn
```
