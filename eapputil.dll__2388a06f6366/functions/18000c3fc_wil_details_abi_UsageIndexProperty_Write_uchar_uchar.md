# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c3fc`
- end: `0x18000c4e4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b0d8`

## callees

- `0x180002b1a`
- `0x180007eac`
- `0x18000c3fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c45f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c45f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
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
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x18000c3fc  push    rbx
0x18000c3fe  push    rbp
0x18000c3ff  push    rsi
0x18000c400  push    rdi
0x18000c401  push    r14
0x18000c403  push    r15
0x18000c405  sub     rsp, 28h
0x18000c409  mov     al, [rcx+2]
0x18000c40c  xor     ebp, ebp
0x18000c40e  mov     r9, [rdx]
0x18000c411  mov     rdi, r8
0x18000c414  mov     r15, rdx
0x18000c417  mov     rsi, rcx
0x18000c41a  cmp     al, 1
0x18000c41c  jnz     short loc_18000C43A
0x18000c41e  lea     rbx, [r9+2]
0x18000c422  cmp     rbx, r8
0x18000c425  ja      loc_18000C4B5
0x18000c42b  test    r9, r9
0x18000c42e  jz      short loc_18000C45F
0x18000c430  movzx   eax, word ptr [rcx+4]
0x18000c434  mov     [r9], ax
0x18000c438  jmp     short loc_18000C475
0x18000c43a  cmp     al, 2
0x18000c43c  jnz     short loc_18000C472
0x18000c43e  lea     rbx, [r9+4]
0x18000c442  cmp     rbx, rdi
0x18000c445  ja      short loc_18000C4B5
0x18000c447  test    r9, r9
0x18000c44a  jz      short loc_18000C45F
0x18000c44c  lea     rax, [rcx+4]
0x18000c450  test    rax, rax
0x18000c453  jz      short loc_18000C45C
0x18000c455  mov     eax, [rax]
0x18000c457  mov     [r9], eax
0x18000c45a  jmp     short loc_18000C475
0x18000c45c  mov     [r9], eax
0x18000c45f  call    cs:__imp__o__errno
0x18000c465  mov     dword ptr [rax], 16h
0x18000c46b  call    _invalid_parameter_noinfo
0x18000c470  jmp     short loc_18000C475
0x18000c472  mov     rbx, r9
0x18000c475  cmp     [rsi], bp
0x18000c478  jnz     short loc_18000C4A3
0x18000c47a  lea     r14, [rbx+2]
0x18000c47e  cmp     r14, rdi
0x18000c481  ja      short loc_18000C4B5
0x18000c483  lea     rbp, [rsi+8]
0x18000c487  mov     rdx, rdi
0x18000c48a  sub     rdx, rbx; DestinationSize
0x18000c48d  mov     r8, rbp; Source
0x18000c490  mov     r9d, 2; SourceSize
0x18000c496  mov     rcx, rbx; Destination
0x18000c499  call    memcpy_s
0x18000c49e  mov     rbx, r14
0x18000c4a1  jmp     short loc_18000C4A7
0x18000c4a3  lea     rbp, [rsi+8]
0x18000c4a7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000c4ac  lea     rax, [r9+rbx]
0x18000c4b0  cmp     rax, rdi
0x18000c4b3  jbe     short loc_18000C4B9
0x18000c4b5  xor     al, al
0x18000c4b7  jmp     short loc_18000C4D7
0x18000c4b9  mov     r8, [rsi+18h]; Source
0x18000c4bd  sub     rdi, rbx
0x18000c4c0  mov     rdx, rdi; DestinationSize
0x18000c4c3  mov     rcx, rbx; Destination
0x18000c4c6  call    memcpy_s
0x18000c4cb  movzx   ecx, word ptr [rbp+0]
0x18000c4cf  mov     al, 1
0x18000c4d1  add     rcx, rbx
0x18000c4d4  mov     [r15], rcx
0x18000c4d7  add     rsp, 28h
0x18000c4db  pop     r15
0x18000c4dd  pop     r14
0x18000c4df  pop     rdi
0x18000c4e0  pop     rsi
0x18000c4e1  pop     rbp
0x18000c4e2  pop     rbx
0x18000c4e3  retn
```
