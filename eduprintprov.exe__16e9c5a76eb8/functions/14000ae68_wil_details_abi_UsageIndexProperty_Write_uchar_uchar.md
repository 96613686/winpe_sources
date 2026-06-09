# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000ae68`
- end: `0x14000af50`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008c88`

## callees

- `0x1400030aa`
- `0x14000ae68`
- `0x14000c160`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000aecb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000aecb`

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
0x14000ae68  push    rbx
0x14000ae6a  push    rbp
0x14000ae6b  push    rsi
0x14000ae6c  push    rdi
0x14000ae6d  push    r14
0x14000ae6f  push    r15
0x14000ae71  sub     rsp, 28h
0x14000ae75  mov     al, [rcx+2]
0x14000ae78  xor     ebp, ebp
0x14000ae7a  mov     r9, [rdx]
0x14000ae7d  mov     rdi, r8
0x14000ae80  mov     r15, rdx
0x14000ae83  mov     rsi, rcx
0x14000ae86  cmp     al, 1
0x14000ae88  jnz     short loc_14000AEA6
0x14000ae8a  lea     rbx, [r9+2]
0x14000ae8e  cmp     rbx, r8
0x14000ae91  ja      loc_14000AF21
0x14000ae97  test    r9, r9
0x14000ae9a  jz      short loc_14000AECB
0x14000ae9c  movzx   eax, word ptr [rcx+4]
0x14000aea0  mov     [r9], ax
0x14000aea4  jmp     short loc_14000AEE1
0x14000aea6  cmp     al, 2
0x14000aea8  jnz     short loc_14000AEDE
0x14000aeaa  lea     rbx, [r9+4]
0x14000aeae  cmp     rbx, rdi
0x14000aeb1  ja      short loc_14000AF21
0x14000aeb3  test    r9, r9
0x14000aeb6  jz      short loc_14000AECB
0x14000aeb8  lea     rax, [rcx+4]
0x14000aebc  test    rax, rax
0x14000aebf  jz      short loc_14000AEC8
0x14000aec1  mov     eax, [rax]
0x14000aec3  mov     [r9], eax
0x14000aec6  jmp     short loc_14000AEE1
0x14000aec8  mov     [r9], eax
0x14000aecb  call    cs:__imp__o__errno
0x14000aed1  mov     dword ptr [rax], 16h
0x14000aed7  call    _invalid_parameter_noinfo
0x14000aedc  jmp     short loc_14000AEE1
0x14000aede  mov     rbx, r9
0x14000aee1  cmp     [rsi], bp
0x14000aee4  jnz     short loc_14000AF0F
0x14000aee6  lea     r14, [rbx+2]
0x14000aeea  cmp     r14, rdi
0x14000aeed  ja      short loc_14000AF21
0x14000aeef  lea     rbp, [rsi+8]
0x14000aef3  mov     rdx, rdi
0x14000aef6  sub     rdx, rbx; DestinationSize
0x14000aef9  mov     r8, rbp; Source
0x14000aefc  mov     r9d, 2; SourceSize
0x14000af02  mov     rcx, rbx; Destination
0x14000af05  call    memcpy_s
0x14000af0a  mov     rbx, r14
0x14000af0d  jmp     short loc_14000AF13
0x14000af0f  lea     rbp, [rsi+8]
0x14000af13  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000af18  lea     rax, [r9+rbx]
0x14000af1c  cmp     rax, rdi
0x14000af1f  jbe     short loc_14000AF25
0x14000af21  xor     al, al
0x14000af23  jmp     short loc_14000AF43
0x14000af25  mov     r8, [rsi+18h]; Source
0x14000af29  sub     rdi, rbx
0x14000af2c  mov     rdx, rdi; DestinationSize
0x14000af2f  mov     rcx, rbx; Destination
0x14000af32  call    memcpy_s
0x14000af37  movzx   ecx, word ptr [rbp+0]
0x14000af3b  mov     al, 1
0x14000af3d  add     rcx, rbx
0x14000af40  mov     [r15], rcx
0x14000af43  add     rsp, 28h
0x14000af47  pop     r15
0x14000af49  pop     r14
0x14000af4b  pop     rdi
0x14000af4c  pop     rsi
0x14000af4d  pop     rbp
0x14000af4e  pop     rbx
0x14000af4f  retn
```
