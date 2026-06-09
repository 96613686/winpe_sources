# DoVJDecompression

- ea: `0x14002cf98`
- end: `0x14002d167`
- name: `DoVJDecompression`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d730`
- `0x140032cd0`

## callees

- `0x14000a290`
- `0x14002cf98`
- `0x14002eed4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002d042`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002d042`

## pseudocode

```c
char __fastcall DoVJDecompression(__int64 a1, __int64 a2)
{
  int v2; // r8d
  int *v3; // r14
  int v6; // r9d
  char *v7; // r10
  char v8; // al
  char v9; // di
  bool v10; // bp
  int v11; // r13d
  PVOID v12; // rax
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  int *v15; // r15
  int v16; // ecx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx

  v2 = *(_DWORD *)(a1 + 72);
  v3 = (int *)(a2 + 72);
  if ( (v2 & 0x1000) != 0 )
  {
    v6 = *v3;
    if ( *v3 <= 2 )
      goto LABEL_33;
    v7 = *(char **)(a2 + 64);
    v8 = *v7 & 0xF0;
    if ( v8 == 64 )
      goto LABEL_33;
    if ( *v7 >= 0 )
    {
      v9 = *v7 & 0xF0;
      if ( v8 == 112 )
        *v7 &= 0x4Fu;
    }
    else
    {
      v9 = 0x80;
    }
    v10 = (v2 & 0x4000) != 0 && v9 == 112 && v6 > 39;
    if ( (v2 & 0x2000) == 0 && !v10 )
      goto LABEL_33;
  }
  else
  {
    v9 = 0x80;
    v10 = 0;
    if ( *(_WORD *)(a2 + 56) != 45 )
      v9 = 112;
  }
  v11 = *v3;
  v12 = ExAllocateFromNPagedLookasideList(&RecvHeaderLookaside);
  *(_QWORD *)(a2 + 80) = v12;
  if ( !v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 0;
    }
    v14 = 72;
LABEL_28:
    WPP_SF_(v13->AttachedDevice, v14, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
    return 0;
  }
  v15 = (int *)(a2 + 92);
  v16 = sl_uncompress_tcp(a2 + 64, v3, v12, a2 + 92, v9, *(_QWORD *)(a1 + 400));
  if ( !v16 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 0;
    }
    v14 = 73;
    goto LABEL_28;
  }
  if ( v10 )
  {
    *(_DWORD *)(a1 + 72) |= 0x2000u;
    *(_DWORD *)(a1 + 68) |= 0x2000u;
  }
  v18 = *(unsigned int *)(a1 + 1664);
  v19 = v18 + ((unsigned __int64)*(unsigned int *)(a1 + 1748) << 32) + v11 + *v15 - v16;
  *(_DWORD *)(a1 + 1664) = v18 + v11 + *v15 - v16;
  *(_DWORD *)(a1 + 1748) = HIDWORD(v19);
  v20 = *(unsigned int *)(a1 + 1656);
  v21 = v20 + *v15 + ((unsigned __int64)*(unsigned int *)(a1 + 1740) << 32);
  *(_DWORD *)(a1 + 1656) = v20 + *v15;
  *(_DWORD *)(a1 + 1740) = HIDWORD(v21);
LABEL_33:
  *(_WORD *)(a2 + 56) = 33;
  return 1;
}

```

## disassembly

```asm
0x14002cf98  push    rbx
0x14002cf9a  push    rbp
0x14002cf9b  push    rsi
0x14002cf9c  push    rdi
0x14002cf9d  push    r12
0x14002cf9f  push    r13
0x14002cfa1  push    r14
0x14002cfa3  push    r15
0x14002cfa5  sub     rsp, 38h
0x14002cfa9  mov     r8d, [rcx+48h]
0x14002cfad  lea     r14, [rdx+48h]
0x14002cfb1  mov     rsi, rdx
0x14002cfb4  mov     rbx, rcx
0x14002cfb7  bt      r8d, 0Ch
0x14002cfbc  jnb     short loc_14002D025
0x14002cfbe  mov     r9d, [r14]
0x14002cfc1  cmp     r9d, 2
0x14002cfc5  jle     loc_14002D14D
0x14002cfcb  mov     r10, [rdx+40h]
0x14002cfcf  mov     dl, [r10]
0x14002cfd2  mov     al, dl
0x14002cfd4  and     al, 0F0h
0x14002cfd6  cmp     al, 40h ; '@'
0x14002cfd8  jz      loc_14002D14D
0x14002cfde  mov     ecx, 70h ; 'p'
0x14002cfe3  test    al, al
0x14002cfe5  jns     short loc_14002CFEC
0x14002cfe7  lea     edi, [rcx+10h]
0x14002cfea  jmp     short loc_14002CFF9
0x14002cfec  mov     dil, al
0x14002cfef  cmp     al, cl
0x14002cff1  jnz     short loc_14002CFF9
0x14002cff3  and     dl, 4Fh
0x14002cff6  mov     [r10], dl
0x14002cff9  bt      r8d, 0Eh
0x14002cffe  jnb     short loc_14002D010
0x14002d000  cmp     dil, cl
0x14002d003  jnz     short loc_14002D010
0x14002d005  cmp     r9d, 27h ; '''
0x14002d009  jle     short loc_14002D010
0x14002d00b  mov     bpl, 1
0x14002d00e  jmp     short loc_14002D013
0x14002d010  xor     bpl, bpl
0x14002d013  bt      r8d, 0Dh
0x14002d018  jb      short loc_14002D038
0x14002d01a  test    bpl, bpl
0x14002d01d  jz      loc_14002D14D
0x14002d023  jmp     short loc_14002D038
0x14002d025  mov     edi, 80h
0x14002d02a  xor     bpl, bpl
0x14002d02d  cmp     word ptr [rdx+38h], 2Dh ; '-'
0x14002d032  lea     ecx, [rdi-10h]
0x14002d035  cmovnz  edi, ecx
0x14002d038  mov     r13d, [r14]
0x14002d03b  lea     rcx, RecvHeaderLookaside; Lookaside
0x14002d042  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002d049  nop     dword ptr [rax+rax+00h]
0x14002d04e  mov     [rsi+50h], rax
0x14002d052  mov     r8, rax
0x14002d055  test    rax, rax
0x14002d058  jnz     short loc_14002D080
0x14002d05a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d061  lea     rax, WPP_GLOBAL_Control
0x14002d068  cmp     rcx, rax
0x14002d06b  jz      short loc_14002D0DF
0x14002d06d  mov     eax, [rcx+2Ch]
0x14002d070  test    al, 10h
0x14002d072  jz      short loc_14002D0DF
0x14002d074  cmp     byte ptr [rcx+29h], 3
0x14002d078  jb      short loc_14002D0DF
0x14002d07a  lea     edx, [r8+48h]
0x14002d07e  jmp     short loc_14002D0CF
0x14002d080  mov     rax, [rbx+190h]
0x14002d087  lea     r15, [rsi+5Ch]
0x14002d08b  mov     [rsp+78h+var_50], rax
0x14002d090  lea     rcx, [rsi+40h]
0x14002d094  mov     r9, r15
0x14002d097  mov     [rsp+78h+var_58], dil
0x14002d09c  mov     rdx, r14
0x14002d09f  call    sl_uncompress_tcp
0x14002d0a4  mov     ecx, eax
0x14002d0a6  test    eax, eax
0x14002d0a8  jnz     short loc_14002D0E3
0x14002d0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d0b1  lea     rax, WPP_GLOBAL_Control
0x14002d0b8  cmp     rcx, rax
0x14002d0bb  jz      short loc_14002D0DF
0x14002d0bd  mov     eax, [rcx+2Ch]
0x14002d0c0  test    al, 10h
0x14002d0c2  jz      short loc_14002D0DF
0x14002d0c4  cmp     byte ptr [rcx+29h], 3
0x14002d0c8  jb      short loc_14002D0DF
0x14002d0ca  mov     edx, 49h ; 'I'
0x14002d0cf  mov     rcx, [rcx+18h]
0x14002d0d3  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14002d0da  call    WPP_SF_
0x14002d0df  xor     al, al
0x14002d0e1  jmp     short loc_14002D155
0x14002d0e3  test    bpl, bpl
0x14002d0e6  jz      short loc_14002D0F3
0x14002d0e8  mov     eax, 2000h
0x14002d0ed  or      [rbx+48h], eax
0x14002d0f0  or      [rbx+44h], eax
0x14002d0f3  mov     eax, [r15]
0x14002d0f6  sub     eax, ecx
0x14002d0f8  add     eax, r13d
0x14002d0fb  movsxd  rdx, eax
0x14002d0fe  mov     eax, [rbx+6D4h]
0x14002d104  shl     rax, 20h
0x14002d108  add     rdx, rax
0x14002d10b  mov     eax, [rbx+680h]
0x14002d111  add     rdx, rax
0x14002d114  mov     [rbx+680h], edx
0x14002d11a  shr     rdx, 20h
0x14002d11e  mov     [rbx+6D4h], edx
0x14002d124  movsxd  rcx, dword ptr [r15]
0x14002d127  mov     edx, [rbx+6CCh]
0x14002d12d  shl     rdx, 20h
0x14002d131  add     rdx, rcx
0x14002d134  mov     ecx, [rbx+678h]
0x14002d13a  add     rdx, rcx
0x14002d13d  mov     [rbx+678h], edx
0x14002d143  shr     rdx, 20h
0x14002d147  mov     [rbx+6CCh], edx
0x14002d14d  mov     word ptr [rsi+38h], 21h ; '!'
0x14002d153  mov     al, 1
0x14002d155  add     rsp, 38h
0x14002d159  pop     r15
0x14002d15b  pop     r14
0x14002d15d  pop     r13
0x14002d15f  pop     r12
0x14002d161  pop     rdi
0x14002d162  pop     rsi
0x14002d163  pop     rbp
0x14002d164  pop     rbx
0x14002d165  retn
```
