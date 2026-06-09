# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000773c`
- end: `0x180007824`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ce0`

## callees

- `0x180001eae`
- `0x18000773c`
- `0x180007de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000779f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000779f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x18000773c  push    rbx
0x18000773e  push    rbp
0x18000773f  push    rsi
0x180007740  push    rdi
0x180007741  push    r14
0x180007743  push    r15
0x180007745  sub     rsp, 28h
0x180007749  mov     al, [rcx+2]
0x18000774c  xor     ebp, ebp
0x18000774e  mov     r9, [rdx]
0x180007751  mov     rdi, r8
0x180007754  mov     r15, rdx
0x180007757  mov     rsi, rcx
0x18000775a  cmp     al, 1
0x18000775c  jnz     short loc_18000777A
0x18000775e  lea     rbx, [r9+2]
0x180007762  cmp     rbx, r8
0x180007765  ja      loc_1800077F5
0x18000776b  test    r9, r9
0x18000776e  jz      short loc_18000779F
0x180007770  movzx   eax, word ptr [rcx+4]
0x180007774  mov     [r9], ax
0x180007778  jmp     short loc_1800077B5
0x18000777a  cmp     al, 2
0x18000777c  jnz     short loc_1800077B2
0x18000777e  lea     rbx, [r9+4]
0x180007782  cmp     rbx, rdi
0x180007785  ja      short loc_1800077F5
0x180007787  test    r9, r9
0x18000778a  jz      short loc_18000779F
0x18000778c  lea     rax, [rcx+4]
0x180007790  test    rax, rax
0x180007793  jz      short loc_18000779C
0x180007795  mov     eax, [rax]
0x180007797  mov     [r9], eax
0x18000779a  jmp     short loc_1800077B5
0x18000779c  mov     [r9], eax
0x18000779f  call    cs:__imp__o__errno
0x1800077a5  mov     dword ptr [rax], 16h
0x1800077ab  call    _invalid_parameter_noinfo
0x1800077b0  jmp     short loc_1800077B5
0x1800077b2  mov     rbx, r9
0x1800077b5  cmp     [rsi], bp
0x1800077b8  jnz     short loc_1800077E3
0x1800077ba  lea     r14, [rbx+2]
0x1800077be  cmp     r14, rdi
0x1800077c1  ja      short loc_1800077F5
0x1800077c3  lea     rbp, [rsi+8]
0x1800077c7  mov     rdx, rdi
0x1800077ca  sub     rdx, rbx; DestinationSize
0x1800077cd  mov     r8, rbp; Source
0x1800077d0  mov     r9d, 2; SourceSize
0x1800077d6  mov     rcx, rbx; Destination
0x1800077d9  call    memcpy_s
0x1800077de  mov     rbx, r14
0x1800077e1  jmp     short loc_1800077E7
0x1800077e3  lea     rbp, [rsi+8]
0x1800077e7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800077ec  lea     rax, [r9+rbx]
0x1800077f0  cmp     rax, rdi
0x1800077f3  jbe     short loc_1800077F9
0x1800077f5  xor     al, al
0x1800077f7  jmp     short loc_180007817
0x1800077f9  mov     r8, [rsi+18h]; Source
0x1800077fd  sub     rdi, rbx
0x180007800  mov     rdx, rdi; DestinationSize
0x180007803  mov     rcx, rbx; Destination
0x180007806  call    memcpy_s
0x18000780b  movzx   ecx, word ptr [rbp+0]
0x18000780f  mov     al, 1
0x180007811  add     rcx, rbx
0x180007814  mov     [r15], rcx
0x180007817  add     rsp, 28h
0x18000781b  pop     r15
0x18000781d  pop     r14
0x18000781f  pop     rdi
0x180007820  pop     rsi
0x180007821  pop     rbp
0x180007822  pop     rbx
0x180007823  retn
```
