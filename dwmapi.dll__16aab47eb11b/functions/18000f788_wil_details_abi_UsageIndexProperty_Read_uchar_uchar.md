# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000f788`
- end: `0x18000f86e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cbec`
- `0x18000ec44`
- `0x18000f330`
- `0x18000f48c`
- `0x18001005c`

## callees

- `0x18000ca48`
- `0x18000f788`

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
0x18000f788  mov     rax, rsp
0x18000f78b  mov     [rax+10h], rbx
0x18000f78f  mov     [rax+18h], rbp
0x18000f793  push    rsi
0x18000f794  push    rdi
0x18000f795  push    r12
0x18000f797  push    r14
0x18000f799  push    r15
0x18000f79b  sub     rsp, 20h
0x18000f79f  xor     r15d, r15d
0x18000f7a2  mov     rsi, r8
0x18000f7a5  cmp     byte ptr [rcx+2], 1
0x18000f7a9  mov     r12, rdx
0x18000f7ac  mov     r8, [rdx]; Source
0x18000f7af  mov     rdi, rcx
0x18000f7b2  jnz     short loc_18000F7E6
0x18000f7b4  lea     rbx, [r8+2]
0x18000f7b8  cmp     rbx, rsi
0x18000f7bb  ja      loc_18000F849
0x18000f7c1  lea     ebp, [r15+2]
0x18000f7c5  mov     [rcx+10h], r8
0x18000f7c9  mov     r9d, ebp; SourceSize
0x18000f7cc  mov     [rax+8], r15w
0x18000f7d1  mov     edx, ebp; DestinationSize
0x18000f7d3  lea     rcx, [rax+8]; Destination
0x18000f7d7  call    memcpy_s
0x18000f7dc  movzx   eax, [rsp+48h+arg_0]
0x18000f7e1  mov     [rdi+4], eax
0x18000f7e4  jmp     short loc_18000F810
0x18000f7e6  mov     ebp, 2
0x18000f7eb  mov     rbx, r8
0x18000f7ee  cmp     [rcx+2], bpl
0x18000f7f2  jnz     short loc_18000F810
0x18000f7f4  lea     rbx, [r8+4]
0x18000f7f8  cmp     rbx, rsi
0x18000f7fb  ja      short loc_18000F849
0x18000f7fd  lea     edx, [rbp+2]; DestinationSize
0x18000f800  mov     [rcx+10h], r8
0x18000f804  mov     r9d, edx; SourceSize
0x18000f807  add     rcx, 4; Destination
0x18000f80b  call    memcpy_s
0x18000f810  movzx   eax, word ptr [rdi]
0x18000f813  lea     r14, [rdi+8]
0x18000f817  mov     [r14], ax
0x18000f81b  test    ax, ax
0x18000f81e  jnz     short loc_18000F83D
0x18000f820  lea     r15, [rbx+2]
0x18000f824  cmp     r15, rsi
0x18000f827  ja      short loc_18000F849
0x18000f829  mov     r9, rbp; SourceSize
0x18000f82c  mov     r8, rbx; Source
0x18000f82f  mov     rdx, rbp; DestinationSize
0x18000f832  mov     rcx, r14; Destination
0x18000f835  call    memcpy_s
0x18000f83a  mov     rbx, r15
0x18000f83d  movzx   ecx, word ptr [r14]
0x18000f841  add     rcx, rbx
0x18000f844  cmp     rcx, rsi
0x18000f847  jbe     short loc_18000F84D
0x18000f849  xor     al, al
0x18000f84b  jmp     short loc_18000F857
0x18000f84d  mov     [rdi+18h], rbx
0x18000f851  mov     al, 1
0x18000f853  mov     [r12], rcx
0x18000f857  mov     rbx, [rsp+48h+arg_8]
0x18000f85c  mov     rbp, [rsp+48h+arg_10]
0x18000f861  add     rsp, 20h
0x18000f865  pop     r15
0x18000f867  pop     r14
0x18000f869  pop     r12
0x18000f86b  pop     rdi
0x18000f86c  pop     rsi
0x18000f86d  retn
```
