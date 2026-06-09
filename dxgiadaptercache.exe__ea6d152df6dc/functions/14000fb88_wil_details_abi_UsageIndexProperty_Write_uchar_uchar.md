# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000fb88`
- end: `0x14000fc70`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b708`

## callees

- `0x140002ca2`
- `0x14000fb88`
- `0x140010f78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000fbeb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000fbeb`

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
0x14000fb88  push    rbx
0x14000fb8a  push    rbp
0x14000fb8b  push    rsi
0x14000fb8c  push    rdi
0x14000fb8d  push    r14
0x14000fb8f  push    r15
0x14000fb91  sub     rsp, 28h
0x14000fb95  mov     al, [rcx+2]
0x14000fb98  xor     ebp, ebp
0x14000fb9a  mov     r9, [rdx]
0x14000fb9d  mov     rdi, r8
0x14000fba0  mov     r15, rdx
0x14000fba3  mov     rsi, rcx
0x14000fba6  cmp     al, 1
0x14000fba8  jnz     short loc_14000FBC6
0x14000fbaa  lea     rbx, [r9+2]
0x14000fbae  cmp     rbx, r8
0x14000fbb1  ja      loc_14000FC41
0x14000fbb7  test    r9, r9
0x14000fbba  jz      short loc_14000FBEB
0x14000fbbc  movzx   eax, word ptr [rcx+4]
0x14000fbc0  mov     [r9], ax
0x14000fbc4  jmp     short loc_14000FC01
0x14000fbc6  cmp     al, 2
0x14000fbc8  jnz     short loc_14000FBFE
0x14000fbca  lea     rbx, [r9+4]
0x14000fbce  cmp     rbx, rdi
0x14000fbd1  ja      short loc_14000FC41
0x14000fbd3  test    r9, r9
0x14000fbd6  jz      short loc_14000FBEB
0x14000fbd8  lea     rax, [rcx+4]
0x14000fbdc  test    rax, rax
0x14000fbdf  jz      short loc_14000FBE8
0x14000fbe1  mov     eax, [rax]
0x14000fbe3  mov     [r9], eax
0x14000fbe6  jmp     short loc_14000FC01
0x14000fbe8  mov     [r9], eax
0x14000fbeb  call    cs:__imp__o__errno
0x14000fbf1  mov     dword ptr [rax], 16h
0x14000fbf7  call    _invalid_parameter_noinfo
0x14000fbfc  jmp     short loc_14000FC01
0x14000fbfe  mov     rbx, r9
0x14000fc01  cmp     [rsi], bp
0x14000fc04  jnz     short loc_14000FC2F
0x14000fc06  lea     r14, [rbx+2]
0x14000fc0a  cmp     r14, rdi
0x14000fc0d  ja      short loc_14000FC41
0x14000fc0f  lea     rbp, [rsi+8]
0x14000fc13  mov     rdx, rdi
0x14000fc16  sub     rdx, rbx; DestinationSize
0x14000fc19  mov     r8, rbp; Source
0x14000fc1c  mov     r9d, 2; SourceSize
0x14000fc22  mov     rcx, rbx; Destination
0x14000fc25  call    memcpy_s
0x14000fc2a  mov     rbx, r14
0x14000fc2d  jmp     short loc_14000FC33
0x14000fc2f  lea     rbp, [rsi+8]
0x14000fc33  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000fc38  lea     rax, [r9+rbx]
0x14000fc3c  cmp     rax, rdi
0x14000fc3f  jbe     short loc_14000FC45
0x14000fc41  xor     al, al
0x14000fc43  jmp     short loc_14000FC63
0x14000fc45  mov     r8, [rsi+18h]; Source
0x14000fc49  sub     rdi, rbx
0x14000fc4c  mov     rdx, rdi; DestinationSize
0x14000fc4f  mov     rcx, rbx; Destination
0x14000fc52  call    memcpy_s
0x14000fc57  movzx   ecx, word ptr [rbp+0]
0x14000fc5b  mov     al, 1
0x14000fc5d  add     rcx, rbx
0x14000fc60  mov     [r15], rcx
0x14000fc63  add     rsp, 28h
0x14000fc67  pop     r15
0x14000fc69  pop     r14
0x14000fc6b  pop     rdi
0x14000fc6c  pop     rsi
0x14000fc6d  pop     rbp
0x14000fc6e  pop     rbx
0x14000fc6f  retn
```
