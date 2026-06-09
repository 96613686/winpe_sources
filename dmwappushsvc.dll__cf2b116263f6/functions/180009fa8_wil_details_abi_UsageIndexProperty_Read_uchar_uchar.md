# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180009fa8`
- end: `0x18000a08e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085ec`
- `0x1800092e8`
- `0x180009718`
- `0x18000a8c8`
- `0x18000b418`

## callees

- `0x180006094`
- `0x180009fa8`

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
0x180009fa8  mov     rax, rsp
0x180009fab  mov     [rax+10h], rbx
0x180009faf  mov     [rax+18h], rbp
0x180009fb3  push    rsi
0x180009fb4  push    rdi
0x180009fb5  push    r12
0x180009fb7  push    r14
0x180009fb9  push    r15
0x180009fbb  sub     rsp, 20h
0x180009fbf  xor     r15d, r15d
0x180009fc2  mov     rsi, r8
0x180009fc5  cmp     byte ptr [rcx+2], 1
0x180009fc9  mov     r12, rdx
0x180009fcc  mov     r8, [rdx]; Source
0x180009fcf  mov     rdi, rcx
0x180009fd2  jnz     short loc_18000A006
0x180009fd4  lea     rbx, [r8+2]
0x180009fd8  cmp     rbx, rsi
0x180009fdb  ja      loc_18000A069
0x180009fe1  lea     ebp, [r15+2]
0x180009fe5  mov     [rcx+10h], r8
0x180009fe9  mov     r9d, ebp; SourceSize
0x180009fec  mov     [rax+8], r15w
0x180009ff1  mov     edx, ebp; DestinationSize
0x180009ff3  lea     rcx, [rax+8]; Destination
0x180009ff7  call    memcpy_s
0x180009ffc  movzx   eax, [rsp+48h+arg_0]
0x18000a001  mov     [rdi+4], eax
0x18000a004  jmp     short loc_18000A030
0x18000a006  mov     ebp, 2
0x18000a00b  mov     rbx, r8
0x18000a00e  cmp     [rcx+2], bpl
0x18000a012  jnz     short loc_18000A030
0x18000a014  lea     rbx, [r8+4]
0x18000a018  cmp     rbx, rsi
0x18000a01b  ja      short loc_18000A069
0x18000a01d  lea     edx, [rbp+2]; DestinationSize
0x18000a020  mov     [rcx+10h], r8
0x18000a024  mov     r9d, edx; SourceSize
0x18000a027  add     rcx, 4; Destination
0x18000a02b  call    memcpy_s
0x18000a030  movzx   eax, word ptr [rdi]
0x18000a033  lea     r14, [rdi+8]
0x18000a037  mov     [r14], ax
0x18000a03b  test    ax, ax
0x18000a03e  jnz     short loc_18000A05D
0x18000a040  lea     r15, [rbx+2]
0x18000a044  cmp     r15, rsi
0x18000a047  ja      short loc_18000A069
0x18000a049  mov     r9, rbp; SourceSize
0x18000a04c  mov     r8, rbx; Source
0x18000a04f  mov     rdx, rbp; DestinationSize
0x18000a052  mov     rcx, r14; Destination
0x18000a055  call    memcpy_s
0x18000a05a  mov     rbx, r15
0x18000a05d  movzx   ecx, word ptr [r14]
0x18000a061  add     rcx, rbx
0x18000a064  cmp     rcx, rsi
0x18000a067  jbe     short loc_18000A06D
0x18000a069  xor     al, al
0x18000a06b  jmp     short loc_18000A077
0x18000a06d  mov     [rdi+18h], rbx
0x18000a071  mov     al, 1
0x18000a073  mov     [r12], rcx
0x18000a077  mov     rbx, [rsp+48h+arg_8]
0x18000a07c  mov     rbp, [rsp+48h+arg_10]
0x18000a081  add     rsp, 20h
0x18000a085  pop     r15
0x18000a087  pop     r14
0x18000a089  pop     r12
0x18000a08b  pop     rdi
0x18000a08c  pop     rsi
0x18000a08d  retn
```
