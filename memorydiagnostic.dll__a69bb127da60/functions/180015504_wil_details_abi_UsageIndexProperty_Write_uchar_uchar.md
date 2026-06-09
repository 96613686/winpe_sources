# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180015504`
- end: `0x1800155ec`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f6d8`

## callees

- `0x1800038c6`
- `0x180015504`
- `0x1800196f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015567`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015567`

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
0x180015504  push    rbx
0x180015506  push    rbp
0x180015507  push    rsi
0x180015508  push    rdi
0x180015509  push    r14
0x18001550b  push    r15
0x18001550d  sub     rsp, 28h
0x180015511  mov     al, [rcx+2]
0x180015514  xor     ebp, ebp
0x180015516  mov     r9, [rdx]
0x180015519  mov     rdi, r8
0x18001551c  mov     r15, rdx
0x18001551f  mov     rsi, rcx
0x180015522  cmp     al, 1
0x180015524  jnz     short loc_180015542
0x180015526  lea     rbx, [r9+2]
0x18001552a  cmp     rbx, r8
0x18001552d  ja      loc_1800155BD
0x180015533  test    r9, r9
0x180015536  jz      short loc_180015567
0x180015538  movzx   eax, word ptr [rcx+4]
0x18001553c  mov     [r9], ax
0x180015540  jmp     short loc_18001557D
0x180015542  cmp     al, 2
0x180015544  jnz     short loc_18001557A
0x180015546  lea     rbx, [r9+4]
0x18001554a  cmp     rbx, rdi
0x18001554d  ja      short loc_1800155BD
0x18001554f  test    r9, r9
0x180015552  jz      short loc_180015567
0x180015554  lea     rax, [rcx+4]
0x180015558  test    rax, rax
0x18001555b  jz      short loc_180015564
0x18001555d  mov     eax, [rax]
0x18001555f  mov     [r9], eax
0x180015562  jmp     short loc_18001557D
0x180015564  mov     [r9], eax
0x180015567  call    cs:__imp__o__errno
0x18001556d  mov     dword ptr [rax], 16h
0x180015573  call    _invalid_parameter_noinfo
0x180015578  jmp     short loc_18001557D
0x18001557a  mov     rbx, r9
0x18001557d  cmp     [rsi], bp
0x180015580  jnz     short loc_1800155AB
0x180015582  lea     r14, [rbx+2]
0x180015586  cmp     r14, rdi
0x180015589  ja      short loc_1800155BD
0x18001558b  lea     rbp, [rsi+8]
0x18001558f  mov     rdx, rdi
0x180015592  sub     rdx, rbx; DestinationSize
0x180015595  mov     r8, rbp; Source
0x180015598  mov     r9d, 2; SourceSize
0x18001559e  mov     rcx, rbx; Destination
0x1800155a1  call    memcpy_s
0x1800155a6  mov     rbx, r14
0x1800155a9  jmp     short loc_1800155AF
0x1800155ab  lea     rbp, [rsi+8]
0x1800155af  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800155b4  lea     rax, [r9+rbx]
0x1800155b8  cmp     rax, rdi
0x1800155bb  jbe     short loc_1800155C1
0x1800155bd  xor     al, al
0x1800155bf  jmp     short loc_1800155DF
0x1800155c1  mov     r8, [rsi+18h]; Source
0x1800155c5  sub     rdi, rbx
0x1800155c8  mov     rdx, rdi; DestinationSize
0x1800155cb  mov     rcx, rbx; Destination
0x1800155ce  call    memcpy_s
0x1800155d3  movzx   ecx, word ptr [rbp+0]
0x1800155d7  mov     al, 1
0x1800155d9  add     rcx, rbx
0x1800155dc  mov     [r15], rcx
0x1800155df  add     rsp, 28h
0x1800155e3  pop     r15
0x1800155e5  pop     r14
0x1800155e7  pop     rdi
0x1800155e8  pop     rsi
0x1800155e9  pop     rbp
0x1800155ea  pop     rbx
0x1800155eb  retn
```
