# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000cc58`
- end: `0x14000cd40`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400099d8`

## callees

- `0x140002b82`
- `0x14000cc58`
- `0x14000d778`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ccbb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ccbb`

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
0x14000cc58  push    rbx
0x14000cc5a  push    rbp
0x14000cc5b  push    rsi
0x14000cc5c  push    rdi
0x14000cc5d  push    r14
0x14000cc5f  push    r15
0x14000cc61  sub     rsp, 28h
0x14000cc65  mov     al, [rcx+2]
0x14000cc68  xor     ebp, ebp
0x14000cc6a  mov     r9, [rdx]
0x14000cc6d  mov     rdi, r8
0x14000cc70  mov     r15, rdx
0x14000cc73  mov     rsi, rcx
0x14000cc76  cmp     al, 1
0x14000cc78  jnz     short loc_14000CC96
0x14000cc7a  lea     rbx, [r9+2]
0x14000cc7e  cmp     rbx, r8
0x14000cc81  ja      loc_14000CD11
0x14000cc87  test    r9, r9
0x14000cc8a  jz      short loc_14000CCBB
0x14000cc8c  movzx   eax, word ptr [rcx+4]
0x14000cc90  mov     [r9], ax
0x14000cc94  jmp     short loc_14000CCD1
0x14000cc96  cmp     al, 2
0x14000cc98  jnz     short loc_14000CCCE
0x14000cc9a  lea     rbx, [r9+4]
0x14000cc9e  cmp     rbx, rdi
0x14000cca1  ja      short loc_14000CD11
0x14000cca3  test    r9, r9
0x14000cca6  jz      short loc_14000CCBB
0x14000cca8  lea     rax, [rcx+4]
0x14000ccac  test    rax, rax
0x14000ccaf  jz      short loc_14000CCB8
0x14000ccb1  mov     eax, [rax]
0x14000ccb3  mov     [r9], eax
0x14000ccb6  jmp     short loc_14000CCD1
0x14000ccb8  mov     [r9], eax
0x14000ccbb  call    cs:__imp__o__errno
0x14000ccc1  mov     dword ptr [rax], 16h
0x14000ccc7  call    _invalid_parameter_noinfo
0x14000cccc  jmp     short loc_14000CCD1
0x14000ccce  mov     rbx, r9
0x14000ccd1  cmp     [rsi], bp
0x14000ccd4  jnz     short loc_14000CCFF
0x14000ccd6  lea     r14, [rbx+2]
0x14000ccda  cmp     r14, rdi
0x14000ccdd  ja      short loc_14000CD11
0x14000ccdf  lea     rbp, [rsi+8]
0x14000cce3  mov     rdx, rdi
0x14000cce6  sub     rdx, rbx; DestinationSize
0x14000cce9  mov     r8, rbp; Source
0x14000ccec  mov     r9d, 2; SourceSize
0x14000ccf2  mov     rcx, rbx; Destination
0x14000ccf5  call    memcpy_s
0x14000ccfa  mov     rbx, r14
0x14000ccfd  jmp     short loc_14000CD03
0x14000ccff  lea     rbp, [rsi+8]
0x14000cd03  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000cd08  lea     rax, [r9+rbx]
0x14000cd0c  cmp     rax, rdi
0x14000cd0f  jbe     short loc_14000CD15
0x14000cd11  xor     al, al
0x14000cd13  jmp     short loc_14000CD33
0x14000cd15  mov     r8, [rsi+18h]; Source
0x14000cd19  sub     rdi, rbx
0x14000cd1c  mov     rdx, rdi; DestinationSize
0x14000cd1f  mov     rcx, rbx; Destination
0x14000cd22  call    memcpy_s
0x14000cd27  movzx   ecx, word ptr [rbp+0]
0x14000cd2b  mov     al, 1
0x14000cd2d  add     rcx, rbx
0x14000cd30  mov     [r15], rcx
0x14000cd33  add     rsp, 28h
0x14000cd37  pop     r15
0x14000cd39  pop     r14
0x14000cd3b  pop     rdi
0x14000cd3c  pop     rsi
0x14000cd3d  pop     rbp
0x14000cd3e  pop     rbx
0x14000cd3f  retn
```
