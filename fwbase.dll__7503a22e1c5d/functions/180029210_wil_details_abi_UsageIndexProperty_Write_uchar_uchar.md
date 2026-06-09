# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180029210`
- end: `0x180029303`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `243`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026b70`

## callees

- `0x18001eae6`
- `0x180029210`
- `0x180029fd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029272`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029272`

## pseudocode

```c
char __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v5; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9

  v3 = *((_BYTE *)this + 2);
  v5 = *a2;
  if ( v3 == 1 )
  {
    v8 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    if ( v5 )
    {
      *(_WORD *)v5 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    if ( v5 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v5 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v5 = (_DWORD)v9;
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
  *a2 = &v8[*v10];
  return 1;
}

```

## disassembly

```asm
0x180029210  push    rbx
0x180029212  push    rbp
0x180029213  push    rsi
0x180029214  push    rdi
0x180029215  push    r14
0x180029217  push    r15
0x180029219  sub     rsp, 28h
0x18002921d  movzx   eax, byte ptr [rcx+2]
0x180029221  mov     rdi, r8
0x180029224  mov     r9, [rdx]
0x180029227  mov     r15, rdx
0x18002922a  mov     rsi, rcx
0x18002922d  cmp     al, 1
0x18002922f  jnz     short loc_18002924D
0x180029231  lea     rbx, [r9+2]
0x180029235  cmp     rbx, r8
0x180029238  ja      loc_1800292C9
0x18002923e  test    r9, r9
0x180029241  jz      short loc_180029272
0x180029243  movzx   eax, word ptr [rcx+4]
0x180029247  mov     [r9], ax
0x18002924b  jmp     short loc_180029288
0x18002924d  cmp     al, 2
0x18002924f  jnz     short loc_180029285
0x180029251  lea     rbx, [r9+4]
0x180029255  cmp     rbx, rdi
0x180029258  ja      short loc_1800292C9
0x18002925a  test    r9, r9
0x18002925d  jz      short loc_180029272
0x18002925f  lea     rax, [rcx+4]
0x180029263  test    rax, rax
0x180029266  jz      short loc_18002926F
0x180029268  mov     eax, [rax]
0x18002926a  mov     [r9], eax
0x18002926d  jmp     short loc_180029288
0x18002926f  mov     [r9], eax
0x180029272  call    cs:__imp__o__errno
0x180029278  mov     dword ptr [rax], 16h
0x18002927e  call    _invalid_parameter_noinfo
0x180029283  jmp     short loc_180029288
0x180029285  mov     rbx, r9
0x180029288  cmp     word ptr [rsi], 0
0x18002928c  jnz     short loc_1800292B7
0x18002928e  lea     r14, [rbx+2]
0x180029292  cmp     r14, rdi
0x180029295  ja      short loc_1800292C9
0x180029297  lea     rbp, [rsi+8]
0x18002929b  mov     rdx, rdi
0x18002929e  sub     rdx, rbx; DestinationSize
0x1800292a1  mov     r8, rbp; Source
0x1800292a4  mov     r9d, 2; SourceSize
0x1800292aa  mov     rcx, rbx; Destination
0x1800292ad  call    memcpy_s
0x1800292b2  mov     rbx, r14
0x1800292b5  jmp     short loc_1800292BB
0x1800292b7  lea     rbp, [rsi+8]
0x1800292bb  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800292c0  lea     rax, [r9+rbx]
0x1800292c4  cmp     rax, rdi
0x1800292c7  jbe     short loc_1800292D8
0x1800292c9  xor     al, al
0x1800292cb  add     rsp, 28h
0x1800292cf  pop     r15
0x1800292d1  pop     r14
0x1800292d3  pop     rdi
0x1800292d4  pop     rsi
0x1800292d5  pop     rbp
0x1800292d6  pop     rbx
0x1800292d7  retn
0x1800292d8  mov     r8, [rsi+18h]; Source
0x1800292dc  sub     rdi, rbx
0x1800292df  mov     rdx, rdi; DestinationSize
0x1800292e2  mov     rcx, rbx; Destination
0x1800292e5  call    memcpy_s
0x1800292ea  movzx   eax, word ptr [rbp+0]
0x1800292ee  add     rax, rbx
0x1800292f1  mov     [r15], rax
0x1800292f4  mov     al, 1
0x1800292f6  add     rsp, 28h
0x1800292fa  pop     r15
0x1800292fc  pop     r14
0x1800292fe  pop     rdi
0x1800292ff  pop     rsi
0x180029300  pop     rbp
0x180029301  pop     rbx
0x180029302  retn
```
