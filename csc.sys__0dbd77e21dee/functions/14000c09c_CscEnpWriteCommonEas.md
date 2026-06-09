# CscEnpWriteCommonEas

- ea: `0x14000c09c`
- end: `0x14000c3d5`
- name: `CscEnpWriteCommonEas`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140083298`

## callees

- `0x14000c09c`
- `0x14000c3dc`
- `0x14000d744`
- `0x1400190ec`
- `0x14002f010`
- `0x14002f140`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c1fa`
- `ntoskrnl!ExAllocatePool2` at `0x14000c1fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c2d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c2d1`

## string_xrefs

- `0x14000c137`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx`
- `0x14000c18a`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx_1`
- `0x14000c0de`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common`

## pseudocode

```c
__int64 __fastcall CscEnpWriteCommonEas(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  int v4; // edi
  unsigned int v8; // edx
  unsigned __int64 v9; // r8
  unsigned __int64 *v10; // rax
  unsigned __int64 v11; // r8
  unsigned __int64 *v12; // rax
  void *v13; // rbx
  unsigned int v14; // r8d
  _QWORD *v15; // rdx
  int v16; // r14d
  int v17; // eax
  unsigned int v18; // r14d
  char *Pool2; // rax
  _QWORD *v20; // rsi
  char *v21; // rdi
  __int64 v22; // rcx
  int v23; // ecx
  bool v24; // zf
  unsigned int v25; // edx
  int v26; // esi
  unsigned __int64 **v28; // rcx
  unsigned __int64 **v29; // rcx
  void *v30; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v31[5]; // [rsp+40h] [rbp-79h] BYREF
  __int16 v32; // [rsp+68h] [rbp-51h]

  v4 = 0;
  if ( !a2 && !a3 && !a4 )
  {
    v26 = 5476;
    goto LABEL_26;
  }
  v8 = 0;
  if ( a2 )
  {
    v31[4] = a2;
    v31[3] = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common";
    v31[2] = 3145775;
    v31[1] = v31;
    v8 = 1;
    v32 = 152;
    v31[0] = v31;
  }
  if ( a3 )
  {
    v9 = (unsigned __int64)v31 & -(__int64)(v8 != 0);
    v10 = &v31[6 * v8];
    v10[2] = 3276849;
    v10[3] = (unsigned __int64)"c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx";
    if ( v9 )
    {
      v28 = *(unsigned __int64 ***)(((unsigned __int64)v31 & -(__int64)(v8 != 0)) + 8);
      if ( *v28 != (unsigned __int64 *)v9 )
        goto LABEL_40;
      *v10 = v9;
      v10[1] = (unsigned __int64)v28;
      *v28 = v10;
      *(_QWORD *)(((unsigned __int64)v31 & -(__int64)(v8 != 0)) + 8) = v10;
    }
    else
    {
      v10[1] = (unsigned __int64)v10;
      *v10 = (unsigned __int64)v10;
    }
    v10[4] = a3;
    ++v8;
    *((_WORD *)v10 + 20) = 96;
  }
  if ( a4 )
  {
    v11 = (unsigned __int64)v31 & -(__int64)(v8 != 0);
    v12 = &v31[6 * v8];
    v12[2] = 3407923;
    v12[3] = (unsigned __int64)"c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx_1";
    if ( !v11 )
    {
      v12[1] = (unsigned __int64)v12;
      *v12 = (unsigned __int64)v12;
LABEL_11:
      v12[4] = a4;
      ++v8;
      *((_WORD *)v12 + 20) = 176;
      goto LABEL_12;
    }
    v29 = *(unsigned __int64 ***)(((unsigned __int64)v31 & -(__int64)(v8 != 0)) + 8);
    if ( *v29 == (unsigned __int64 *)v11 )
    {
      *v12 = v11;
      v12[1] = (unsigned __int64)v29;
      *v29 = v12;
      *(_QWORD *)(((unsigned __int64)v31 & -(__int64)(v8 != 0)) + 8) = v12;
      goto LABEL_11;
    }
LABEL_40:
    __fastfail(3u);
  }
LABEL_12:
  v13 = 0;
  if ( !v8 )
    goto LABEL_21;
  v14 = 0;
  v15 = v31;
  while ( 1 )
  {
    v16 = *((unsigned __int16 *)v15 + 20);
    v17 = *((unsigned __int16 *)v15 + 8) + 9;
    v15 = (_QWORD *)*v15;
    v18 = v14 + v17 + v16;
    if ( v15 == v31 )
      break;
    v14 = (v18 + 3) & 0xFFFFFFFC;
  }
  Pool2 = (char *)ExAllocatePool2(258, v18, 624980803);
  v30 = Pool2;
  v13 = Pool2;
  if ( !Pool2 )
  {
    v4 = -1073741670;
LABEL_23:
    CscEaFreeFullEaBuffer(&v30);
    v13 = v30;
    v26 = 5521;
    goto LABEL_24;
  }
  v20 = v31;
  v21 = Pool2;
  while ( 1 )
  {
    *(_DWORD *)v21 = 0;
    if ( *((_WORD *)v20 + 8) >= 0xFFu )
    {
      v4 = -1073741811;
      goto LABEL_23;
    }
    v21[5] = *((_BYTE *)v20 + 16);
    memmove(v21 + 8, (const void *)v20[3], *((unsigned __int16 *)v20 + 8));
    v21[(unsigned __int8)v21[5] + 8] = 0;
    v22 = (unsigned __int8)v21[5];
    v21[4] = 0;
    *((_WORD *)v21 + 3) = *((_WORD *)v20 + 20);
    memmove(&v21[v22 + 9], (const void *)v20[4], *((unsigned __int16 *)v20 + 20));
    v20 = (_QWORD *)*v20;
    if ( v20 == v31 )
      break;
    v23 = *((unsigned __int16 *)v21 + 3);
    v24 = ((v23 + (unsigned __int8)v21[5] + 12) & 0xFFFFFFFC) == 0;
    v25 = (v23 + (unsigned __int8)v21[5] + 12) & 0xFFFFFFFC;
    *(_DWORD *)v21 = v25;
    if ( v24 )
      v21 = 0;
    else
      v21 += v25;
  }
  v4 = CscStorepLowIoSetEaFilePoster(a1, v13, v18);
  if ( v4 < 0 )
    v26 = 5527;
  else
LABEL_21:
    v26 = 0;
LABEL_24:
  if ( v13 )
    ExFreePoolWithTag(v13, 0x25407343u);
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
      (unsigned int)v4,
      v26);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000c09c  push    rbp
0x14000c09e  push    rbx
0x14000c09f  push    rsi
0x14000c0a0  push    rdi
0x14000c0a1  push    r14
0x14000c0a3  push    r15
0x14000c0a5  lea     rbp, [rsp-2Fh]
0x14000c0aa  sub     rsp, 0E8h
0x14000c0b1  mov     rax, cs:__security_cookie
0x14000c0b8  xor     rax, rsp
0x14000c0bb  mov     [rbp+57h+var_40], rax
0x14000c0bf  xor     edi, edi
0x14000c0c1  mov     r10, r8
0x14000c0c4  mov     rax, rdx
0x14000c0c7  mov     r15, rcx
0x14000c0ca  lea     r8d, [rdi+2Fh]
0x14000c0ce  test    rdx, rdx
0x14000c0d1  jz      loc_14000C37F
0x14000c0d7  xor     edx, edx
0x14000c0d9  test    rax, rax
0x14000c0dc  jz      short loc_14000C113
0x14000c0de  lea     rcx, aC8a05bc03fa849; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x14000c0e5  mov     [rbp+57h+var_B0], rax
0x14000c0e9  mov     [rbp+57h+var_B8], rcx
0x14000c0ed  mov     eax, 98h
0x14000c0f2  lea     rcx, [rbp+57h+var_D0]
0x14000c0f6  mov     [rbp+57h+var_C0], 30002Fh
0x14000c0fe  mov     [rbp+57h+var_C8], rcx
0x14000c102  mov     edx, 1
0x14000c107  lea     rcx, [rbp+57h+var_D0]
0x14000c10b  mov     [rbp+57h+var_A8], ax
0x14000c10f  mov     [rbp+57h+var_D0], rcx
0x14000c113  test    r10, r10
0x14000c116  jz      short loc_14000C166
0x14000c118  mov     eax, edx
0x14000c11a  neg     eax
0x14000c11c  lea     rax, [rbp+57h+var_D0]
0x14000c120  sbb     r8, r8
0x14000c123  and     r8, rax
0x14000c126  mov     eax, edx
0x14000c128  lea     rcx, [rax+rax*2]
0x14000c12c  shl     rcx, 4
0x14000c130  lea     rax, [rbp+57h+var_D0]
0x14000c134  add     rax, rcx
0x14000c137  lea     rcx, aC8a05bc03fa849_3; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x14000c13e  mov     qword ptr [rax+10h], 320031h
0x14000c146  mov     [rax+18h], rcx
0x14000c14a  test    r8, r8
0x14000c14d  jnz     loc_14000C33A
0x14000c153  mov     [rax+8], rax
0x14000c157  mov     [rax], rax
0x14000c15a  mov     [rax+20h], r10
0x14000c15e  inc     edx
0x14000c160  mov     word ptr [rax+28h], 60h ; '`'
0x14000c166  test    r9, r9
0x14000c169  jz      short loc_14000C1B9
0x14000c16b  mov     eax, edx
0x14000c16d  neg     eax
0x14000c16f  lea     rax, [rbp+57h+var_D0]
0x14000c173  sbb     r8, r8
0x14000c176  and     r8, rax
0x14000c179  mov     eax, edx
0x14000c17b  lea     rcx, [rax+rax*2]
0x14000c17f  shl     rcx, 4
0x14000c183  lea     rax, [rbp+57h+var_D0]
0x14000c187  add     rax, rcx
0x14000c18a  lea     rcx, aC8a05bc03fa849_4; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x14000c191  mov     qword ptr [rax+10h], 340033h
0x14000c199  mov     [rax+18h], rcx
0x14000c19d  test    r8, r8
0x14000c1a0  jnz     loc_14000C356
0x14000c1a6  mov     [rax+8], rax
0x14000c1aa  mov     [rax], rax
0x14000c1ad  mov     [rax+20h], r9
0x14000c1b1  inc     edx
0x14000c1b3  mov     word ptr [rax+28h], 0B0h
0x14000c1b9  xor     ebx, ebx
0x14000c1bb  test    edx, edx
0x14000c1bd  jz      loc_14000C2A7
0x14000c1c3  xor     r8d, r8d
0x14000c1c6  lea     rdx, [rbp+57h+var_D0]
0x14000c1ca  movzx   eax, word ptr [rdx+10h]
0x14000c1ce  movzx   r14d, word ptr [rdx+28h]
0x14000c1d3  add     eax, 9
0x14000c1d6  mov     rdx, [rdx]
0x14000c1d9  add     eax, r8d
0x14000c1dc  add     r14d, eax
0x14000c1df  lea     rax, [rbp+57h+var_D0]
0x14000c1e3  cmp     rdx, rax
0x14000c1e6  jnz     loc_14000C372
0x14000c1ec  mov     edx, r14d
0x14000c1ef  mov     ecx, 102h
0x14000c1f4  mov     r8d, 25407343h
0x14000c1fa  call    cs:__imp_ExAllocatePool2
0x14000c201  nop     dword ptr [rax+rax+00h]
0x14000c206  mov     [rsp+110h+var_E0], rax
0x14000c20b  mov     rbx, rax
0x14000c20e  test    rax, rax
0x14000c211  jz      loc_14000C3C4
0x14000c217  lea     rsi, [rbp+57h+var_D0]
0x14000c21b  mov     rdi, rax
0x14000c21e  mov     eax, 0FFh
0x14000c223  mov     dword ptr [rdi], 0
0x14000c229  cmp     [rsi+10h], ax
0x14000c22d  jnb     short loc_14000C2AB
0x14000c22f  mov     al, [rsi+10h]
0x14000c232  lea     rcx, [rdi+8]; void *
0x14000c236  mov     [rdi+5], al
0x14000c239  movzx   r8d, word ptr [rsi+10h]; Size
0x14000c23e  mov     rdx, [rsi+18h]; Src
0x14000c242  call    memmove
0x14000c247  movzx   eax, byte ptr [rdi+5]
0x14000c24b  mov     byte ptr [rax+rdi+8], 0
0x14000c250  movzx   ecx, byte ptr [rdi+5]
0x14000c254  mov     byte ptr [rdi+4], 0
0x14000c258  add     rcx, 9
0x14000c25c  movzx   eax, word ptr [rsi+28h]
0x14000c260  add     rcx, rdi; void *
0x14000c263  mov     [rdi+6], ax
0x14000c267  movzx   r8d, word ptr [rsi+28h]; Size
0x14000c26c  mov     rdx, [rsi+20h]; Src
0x14000c270  call    memmove
0x14000c275  mov     rsi, [rsi]
0x14000c278  lea     rax, [rbp+57h+var_D0]
0x14000c27c  cmp     rsi, rax
0x14000c27f  jz      loc_14000C39B
0x14000c285  movzx   edx, byte ptr [rdi+5]
0x14000c289  movzx   ecx, word ptr [rdi+6]
0x14000c28d  add     edx, 0Ch
0x14000c290  add     edx, ecx
0x14000c292  and     edx, 0FFFFFFFCh
0x14000c295  mov     [rdi], edx
0x14000c297  jz      loc_14000C3CE
0x14000c29d  mov     eax, edx
0x14000c29f  add     rdi, rax
0x14000c2a2  jmp     loc_14000C21E
0x14000c2a7  xor     esi, esi
0x14000c2a9  jmp     short loc_14000C2C4
0x14000c2ab  mov     edi, 0C000000Dh
0x14000c2b0  lea     rcx, [rsp+110h+var_E0]
0x14000c2b5  call    CscEaFreeFullEaBuffer
0x14000c2ba  mov     rbx, [rsp+110h+var_E0]
0x14000c2bf  mov     esi, 1591h
0x14000c2c4  test    rbx, rbx
0x14000c2c7  jz      short loc_14000C2DD
0x14000c2c9  mov     edx, 25407343h; Tag
0x14000c2ce  mov     rcx, rbx; P
0x14000c2d1  call    cs:__imp_ExFreePoolWithTag
0x14000c2d8  nop     dword ptr [rax+rax+00h]
0x14000c2dd  mov     r8d, 2Fh ; '/'
0x14000c2e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c2ea  lea     rax, WPP_GLOBAL_Control
0x14000c2f1  cmp     rcx, rax
0x14000c2f4  jnz     short loc_14000C315
0x14000c2f6  mov     eax, edi
0x14000c2f8  mov     rcx, [rbp+57h+var_40]
0x14000c2fc  xor     rcx, rsp; StackCookie
0x14000c2ff  call    __security_check_cookie
0x14000c304  add     rsp, 0E8h
0x14000c30b  pop     r15
0x14000c30d  pop     r14
0x14000c30f  pop     rdi
0x14000c310  pop     rsi
0x14000c311  pop     rbx
0x14000c312  pop     rbp
0x14000c313  retn
0x14000c315  test    dword ptr [rcx+2Ch], 40000h
0x14000c31c  jz      short loc_14000C2F6
0x14000c31e  mov     rcx, [rcx+18h]
0x14000c322  mov     edx, r8d
0x14000c325  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000c32c  mov     [rsp+110h+var_F0], esi
0x14000c330  mov     r9d, edi
0x14000c333  call    WPP_SF_Dd
0x14000c338  jmp     short loc_14000C2F6
0x14000c33a  mov     rcx, [r8+8]
0x14000c33e  cmp     [rcx], r8
0x14000c341  jnz     short loc_14000C3BD
0x14000c343  mov     [rax], r8
0x14000c346  mov     [rax+8], rcx
0x14000c34a  mov     [rcx], rax
0x14000c34d  mov     [r8+8], rax
0x14000c351  jmp     loc_14000C15A
0x14000c356  mov     rcx, [r8+8]
0x14000c35a  cmp     [rcx], r8
0x14000c35d  jnz     short loc_14000C3BD
0x14000c35f  mov     [rax], r8
0x14000c362  mov     [rax+8], rcx
0x14000c366  mov     [rcx], rax
0x14000c369  mov     [r8+8], rax
0x14000c36d  jmp     loc_14000C1AD
0x14000c372  lea     r8d, [r14+3]
0x14000c376  and     r8d, 0FFFFFFFCh
0x14000c37a  jmp     loc_14000C1CA
0x14000c37f  test    r10, r10
0x14000c382  jnz     loc_14000C0D7
0x14000c388  test    r9, r9
0x14000c38b  jnz     loc_14000C0D7
0x14000c391  mov     esi, 1564h
0x14000c396  jmp     loc_14000C2E3
0x14000c39b  mov     r8d, r14d
0x14000c39e  mov     rdx, rbx
0x14000c3a1  mov     rcx, r15
0x14000c3a4  call    CscStorepLowIoSetEaFilePoster
0x14000c3a9  mov     edi, eax
0x14000c3ab  test    eax, eax
0x14000c3ad  jns     loc_14000C2A7
0x14000c3b3  mov     esi, 1597h
0x14000c3b8  jmp     loc_14000C2C4
0x14000c3bd  mov     ecx, 3
0x14000c3c2  int     29h; Win8: RtlFailFast(ecx)
0x14000c3c4  mov     edi, 0C000009Ah
0x14000c3c9  jmp     loc_14000C2B0
0x14000c3ce  xor     edi, edi
0x14000c3d0  jmp     loc_14000C21E
```
