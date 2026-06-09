# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c48c`
- end: `0x18000c574`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008b68`

## callees

- `0x180002b62`
- `0x18000c48c`
- `0x18000cdd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4ef`

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
0x18000c48c  push    rbx
0x18000c48e  push    rbp
0x18000c48f  push    rsi
0x18000c490  push    rdi
0x18000c491  push    r14
0x18000c493  push    r15
0x18000c495  sub     rsp, 28h
0x18000c499  mov     al, [rcx+2]
0x18000c49c  xor     ebp, ebp
0x18000c49e  mov     r9, [rdx]
0x18000c4a1  mov     rdi, r8
0x18000c4a4  mov     r15, rdx
0x18000c4a7  mov     rsi, rcx
0x18000c4aa  cmp     al, 1
0x18000c4ac  jnz     short loc_18000C4CA
0x18000c4ae  lea     rbx, [r9+2]
0x18000c4b2  cmp     rbx, r8
0x18000c4b5  ja      loc_18000C545
0x18000c4bb  test    r9, r9
0x18000c4be  jz      short loc_18000C4EF
0x18000c4c0  movzx   eax, word ptr [rcx+4]
0x18000c4c4  mov     [r9], ax
0x18000c4c8  jmp     short loc_18000C505
0x18000c4ca  cmp     al, 2
0x18000c4cc  jnz     short loc_18000C502
0x18000c4ce  lea     rbx, [r9+4]
0x18000c4d2  cmp     rbx, rdi
0x18000c4d5  ja      short loc_18000C545
0x18000c4d7  test    r9, r9
0x18000c4da  jz      short loc_18000C4EF
0x18000c4dc  lea     rax, [rcx+4]
0x18000c4e0  test    rax, rax
0x18000c4e3  jz      short loc_18000C4EC
0x18000c4e5  mov     eax, [rax]
0x18000c4e7  mov     [r9], eax
0x18000c4ea  jmp     short loc_18000C505
0x18000c4ec  mov     [r9], eax
0x18000c4ef  call    cs:__imp__o__errno
0x18000c4f5  mov     dword ptr [rax], 16h
0x18000c4fb  call    _invalid_parameter_noinfo
0x18000c500  jmp     short loc_18000C505
0x18000c502  mov     rbx, r9
0x18000c505  cmp     [rsi], bp
0x18000c508  jnz     short loc_18000C533
0x18000c50a  lea     r14, [rbx+2]
0x18000c50e  cmp     r14, rdi
0x18000c511  ja      short loc_18000C545
0x18000c513  lea     rbp, [rsi+8]
0x18000c517  mov     rdx, rdi
0x18000c51a  sub     rdx, rbx; DestinationSize
0x18000c51d  mov     r8, rbp; Source
0x18000c520  mov     r9d, 2; SourceSize
0x18000c526  mov     rcx, rbx; Destination
0x18000c529  call    memcpy_s
0x18000c52e  mov     rbx, r14
0x18000c531  jmp     short loc_18000C537
0x18000c533  lea     rbp, [rsi+8]
0x18000c537  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000c53c  lea     rax, [r9+rbx]
0x18000c540  cmp     rax, rdi
0x18000c543  jbe     short loc_18000C549
0x18000c545  xor     al, al
0x18000c547  jmp     short loc_18000C567
0x18000c549  mov     r8, [rsi+18h]; Source
0x18000c54d  sub     rdi, rbx
0x18000c550  mov     rdx, rdi; DestinationSize
0x18000c553  mov     rcx, rbx; Destination
0x18000c556  call    memcpy_s
0x18000c55b  movzx   ecx, word ptr [rbp+0]
0x18000c55f  mov     al, 1
0x18000c561  add     rcx, rbx
0x18000c564  mov     [r15], rcx
0x18000c567  add     rsp, 28h
0x18000c56b  pop     r15
0x18000c56d  pop     r14
0x18000c56f  pop     rdi
0x18000c570  pop     rsi
0x18000c571  pop     rbp
0x18000c572  pop     rbx
0x18000c573  retn
```
