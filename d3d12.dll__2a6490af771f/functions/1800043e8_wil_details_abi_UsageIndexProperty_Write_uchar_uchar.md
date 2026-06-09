# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800043e8`
- end: `0x1800044c9`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `225`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800039ac`

## callees

- `0x1800043e8`
- `0x18000463c`
- `0x18000be22`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004477`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004477`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  _WORD *v4; // rcx
  char v7; // al
  _WORD *v8; // rbx
  unsigned __int16 *v9; // rbp
  rsize_t v10; // r9
  bool result; // al

  v4 = *a2;
  v7 = *((_BYTE *)this + 2);
  if ( v7 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
    }
  }
  else if ( v7 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
      return 0;
    memcpy_s(v4, 4u, (char *)this + 4, 4u);
  }
  else
  {
    v8 = *a2;
  }
  if ( *(_WORD *)this )
  {
    v9 = (unsigned __int16 *)((char *)this + 8);
  }
  else
  {
    if ( v8 + 1 > (_WORD *)a3 )
      return 0;
    v9 = (unsigned __int16 *)((char *)this + 8);
    memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
    ++v8;
  }
  v10 = *v9;
  if ( (unsigned __int8 *)((char *)v8 + v10) <= a3 )
  {
    memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v10);
    result = 1;
    *a2 = (unsigned __int8 *)v8 + *v9;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x1800043e8  push    rbx
0x1800043ea  push    rbp
0x1800043eb  push    rsi
0x1800043ec  push    rdi
0x1800043ed  push    r14
0x1800043ef  push    r15
0x1800043f1  sub     rsp, 28h
0x1800043f5  mov     rsi, rcx
0x1800043f8  xor     ebp, ebp
0x1800043fa  mov     rcx, [rdx]; Destination
0x1800043fd  mov     rdi, r8
0x180004400  mov     r15, rdx
0x180004403  mov     al, [rsi+2]
0x180004406  cmp     al, 1
0x180004408  jnz     short loc_180004421
0x18000440a  lea     rbx, [rcx+2]
0x18000440e  cmp     rbx, r8
0x180004411  ja      short loc_180004473
0x180004413  test    rcx, rcx
0x180004416  jz      short loc_180004477
0x180004418  movzx   eax, word ptr [rsi+4]
0x18000441c  mov     [rcx], ax
0x18000441f  jmp     short loc_180004428
0x180004421  cmp     al, 2
0x180004423  jz      short loc_18000448A
0x180004425  mov     rbx, rcx
0x180004428  cmp     [rsi], bp
0x18000442b  jz      short loc_18000446A
0x18000442d  lea     rbp, [rsi+8]
0x180004431  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180004436  lea     rax, [r9+rbx]
0x18000443a  cmp     rax, rdi
0x18000443d  ja      short loc_180004473
0x18000443f  mov     r8, [rsi+18h]; Source
0x180004443  sub     rdi, rbx
0x180004446  mov     rdx, rdi; DestinationSize
0x180004449  mov     rcx, rbx; Destination
0x18000444c  call    memcpy_s
0x180004451  movzx   ecx, word ptr [rbp+0]
0x180004455  mov     al, 1
0x180004457  add     rcx, rbx
0x18000445a  mov     [r15], rcx
0x18000445d  add     rsp, 28h
0x180004461  pop     r15
0x180004463  pop     r14
0x180004465  pop     rdi
0x180004466  pop     rsi
0x180004467  pop     rbp
0x180004468  pop     rbx
0x180004469  retn
0x18000446a  lea     r14, [rbx+2]
0x18000446e  cmp     r14, rdi
0x180004471  jbe     short loc_1800044A6
0x180004473  xor     al, al
0x180004475  jmp     short loc_18000445D
0x180004477  call    cs:__imp__o__errno
0x18000447d  mov     dword ptr [rax], 16h
0x180004483  call    _invalid_parameter_noinfo
0x180004488  jmp     short loc_180004428
0x18000448a  lea     rbx, [rcx+4]
0x18000448e  cmp     rbx, rdi
0x180004491  ja      short loc_180004473
0x180004493  mov     edx, 4; DestinationSize
0x180004498  lea     r8, [rsi+4]; Source
0x18000449c  mov     r9d, edx; SourceSize
0x18000449f  call    memcpy_s
0x1800044a4  jmp     short loc_180004428
0x1800044a6  lea     rbp, [rsi+8]
0x1800044aa  mov     rdx, rdi
0x1800044ad  sub     rdx, rbx; DestinationSize
0x1800044b0  mov     r8, rbp; Source
0x1800044b3  mov     r9d, 2; SourceSize
0x1800044b9  mov     rcx, rbx; Destination
0x1800044bc  call    memcpy_s
0x1800044c1  mov     rbx, r14
0x1800044c4  jmp     loc_180004431
```
