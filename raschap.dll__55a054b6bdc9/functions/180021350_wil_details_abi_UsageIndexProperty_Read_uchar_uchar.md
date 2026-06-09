# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180021350`
- end: `0x180021436`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180011d74`
- `0x18001fc70`
- `0x180020810`
- `0x180020ca8`
- `0x18002217c`

## callees

- `0x1800118a4`
- `0x180021350`

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
0x180021350  mov     rax, rsp
0x180021353  mov     [rax+10h], rbx
0x180021357  mov     [rax+18h], rbp
0x18002135b  push    rsi
0x18002135c  push    rdi
0x18002135d  push    r12
0x18002135f  push    r14
0x180021361  push    r15
0x180021363  sub     rsp, 20h
0x180021367  xor     r15d, r15d
0x18002136a  mov     rsi, r8
0x18002136d  cmp     byte ptr [rcx+2], 1
0x180021371  mov     r12, rdx
0x180021374  mov     r8, [rdx]; Source
0x180021377  mov     rdi, rcx
0x18002137a  jnz     short loc_1800213AE
0x18002137c  lea     rbx, [r8+2]
0x180021380  cmp     rbx, rsi
0x180021383  ja      loc_180021411
0x180021389  lea     ebp, [r15+2]
0x18002138d  mov     [rcx+10h], r8
0x180021391  mov     r9d, ebp; SourceSize
0x180021394  mov     [rax+8], r15w
0x180021399  mov     edx, ebp; DestinationSize
0x18002139b  lea     rcx, [rax+8]; Destination
0x18002139f  call    memcpy_s
0x1800213a4  movzx   eax, [rsp+48h+arg_0]
0x1800213a9  mov     [rdi+4], eax
0x1800213ac  jmp     short loc_1800213D8
0x1800213ae  mov     ebp, 2
0x1800213b3  mov     rbx, r8
0x1800213b6  cmp     [rcx+2], bpl
0x1800213ba  jnz     short loc_1800213D8
0x1800213bc  lea     rbx, [r8+4]
0x1800213c0  cmp     rbx, rsi
0x1800213c3  ja      short loc_180021411
0x1800213c5  lea     edx, [rbp+2]; DestinationSize
0x1800213c8  mov     [rcx+10h], r8
0x1800213cc  mov     r9d, edx; SourceSize
0x1800213cf  add     rcx, 4; Destination
0x1800213d3  call    memcpy_s
0x1800213d8  movzx   eax, word ptr [rdi]
0x1800213db  lea     r14, [rdi+8]
0x1800213df  mov     [r14], ax
0x1800213e3  test    ax, ax
0x1800213e6  jnz     short loc_180021405
0x1800213e8  lea     r15, [rbx+2]
0x1800213ec  cmp     r15, rsi
0x1800213ef  ja      short loc_180021411
0x1800213f1  mov     r9, rbp; SourceSize
0x1800213f4  mov     r8, rbx; Source
0x1800213f7  mov     rdx, rbp; DestinationSize
0x1800213fa  mov     rcx, r14; Destination
0x1800213fd  call    memcpy_s
0x180021402  mov     rbx, r15
0x180021405  movzx   ecx, word ptr [r14]
0x180021409  add     rcx, rbx
0x18002140c  cmp     rcx, rsi
0x18002140f  jbe     short loc_180021415
0x180021411  xor     al, al
0x180021413  jmp     short loc_18002141F
0x180021415  mov     [rdi+18h], rbx
0x180021419  mov     al, 1
0x18002141b  mov     [r12], rcx
0x18002141f  mov     rbx, [rsp+48h+arg_8]
0x180021424  mov     rbp, [rsp+48h+arg_10]
0x180021429  add     rsp, 20h
0x18002142d  pop     r15
0x18002142f  pop     r14
0x180021431  pop     r12
0x180021433  pop     rdi
0x180021434  pop     rsi
0x180021435  retn
```
