# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800161cc`
- end: `0x1800162cf`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `259`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ffd0`

## callees

- `0x180003306`
- `0x1800161cc`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016238`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016238`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _DWORD *v4; // rbx
  _DWORD *v8; // rbp
  unsigned __int16 *v9; // rbp
  rsize_t v10; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 != 1 )
  {
    if ( v3 != 2 )
      goto LABEL_13;
    v8 = v4 + 1;
    if ( v4 + 1 > (_DWORD *)a3 )
      return 0;
    if ( v4 )
    {
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *v4 = *((_DWORD *)this + 1);
        goto LABEL_12;
      }
      *v4 = 0;
    }
LABEL_11:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
  v8 = (_DWORD *)((char *)v4 + 2);
  if ( (unsigned __int8 *)((char *)v4 + 2) > a3 )
    return 0;
  if ( !v4 )
    goto LABEL_11;
  *(_WORD *)v4 = *((_WORD *)this + 2);
LABEL_12:
  v4 = v8;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( (unsigned __int8 *)((char *)v4 + 2) <= a3 )
    {
      v9 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v4, a3 - (unsigned __int8 *)v4, (char *)this + 8, 2u);
      v4 = (_DWORD *)((char *)v4 + 2);
      goto LABEL_17;
    }
    return 0;
  }
  v9 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v10 = *v9;
  if ( (unsigned __int8 *)((char *)v4 + v10) > a3 )
    return 0;
  memcpy_s(v4, a3 - (unsigned __int8 *)v4, *((const void *const *)this + 3), v10);
  result = 1;
  *a2 = (unsigned __int8 *)v4 + *v9;
  return result;
}

```

## disassembly

```asm
0x1800161cc  mov     [rsp+arg_0], rbx
0x1800161d1  mov     [rsp+arg_8], rbp
0x1800161d6  mov     [rsp+arg_10], rsi
0x1800161db  push    rdi
0x1800161dc  push    r14
0x1800161de  push    r15
0x1800161e0  sub     rsp, 20h
0x1800161e4  mov     al, [rcx+2]
0x1800161e7  xor     r14d, r14d
0x1800161ea  mov     rbx, [rdx]
0x1800161ed  mov     rdi, r8
0x1800161f0  mov     r15, rdx
0x1800161f3  mov     rsi, rcx
0x1800161f6  cmp     al, 1
0x1800161f8  jnz     short loc_180016215
0x1800161fa  lea     rbp, [rbx+2]
0x1800161fe  cmp     rbp, r8
0x180016201  ja      loc_180016293
0x180016207  movzx   eax, word ptr [rcx+4]
0x18001620b  test    rbx, rbx
0x18001620e  jz      short loc_180016238
0x180016210  mov     [rbx], ax
0x180016213  jmp     short loc_18001624F
0x180016215  cmp     al, 2
0x180016217  jnz     short loc_180016252
0x180016219  lea     rbp, [rbx+4]
0x18001621d  cmp     rbp, rdi
0x180016220  ja      short loc_180016293
0x180016222  lea     rax, [rcx+4]
0x180016226  test    rbx, rbx
0x180016229  jz      short loc_180016238
0x18001622b  test    rax, rax
0x18001622e  jz      short loc_180016236
0x180016230  mov     eax, [rax]
0x180016232  mov     [rbx], eax
0x180016234  jmp     short loc_18001624F
0x180016236  mov     [rbx], eax
0x180016238  call    cs:__imp__o__errno
0x18001623f  nop     dword ptr [rax+rax+00h]
0x180016244  mov     dword ptr [rax], 16h
0x18001624a  call    _invalid_parameter_noinfo
0x18001624f  mov     rbx, rbp
0x180016252  cmp     [rsi], r14w
0x180016256  jnz     short loc_180016281
0x180016258  lea     r14, [rbx+2]
0x18001625c  cmp     r14, rdi
0x18001625f  ja      short loc_180016293
0x180016261  lea     rbp, [rsi+8]
0x180016265  mov     rdx, rdi
0x180016268  sub     rdx, rbx; DestinationSize
0x18001626b  mov     r8, rbp; Source
0x18001626e  mov     r9d, 2; SourceSize
0x180016274  mov     rcx, rbx; Destination
0x180016277  call    memcpy_s
0x18001627c  mov     rbx, r14
0x18001627f  jmp     short loc_180016285
0x180016281  lea     rbp, [rsi+8]
0x180016285  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18001628a  lea     rax, [r9+rbx]
0x18001628e  cmp     rax, rdi
0x180016291  jbe     short loc_180016297
0x180016293  xor     al, al
0x180016295  jmp     short loc_1800162B5
0x180016297  mov     r8, [rsi+18h]; Source
0x18001629b  sub     rdi, rbx
0x18001629e  mov     rdx, rdi; DestinationSize
0x1800162a1  mov     rcx, rbx; Destination
0x1800162a4  call    memcpy_s
0x1800162a9  movzx   ecx, word ptr [rbp+0]
0x1800162ad  mov     al, 1
0x1800162af  add     rcx, rbx
0x1800162b2  mov     [r15], rcx
0x1800162b5  mov     rbx, [rsp+38h+arg_0]
0x1800162ba  mov     rbp, [rsp+38h+arg_8]
0x1800162bf  mov     rsi, [rsp+38h+arg_10]
0x1800162c4  add     rsp, 20h
0x1800162c8  pop     r15
0x1800162ca  pop     r14
0x1800162cc  pop     rdi
0x1800162cd  retn
```
