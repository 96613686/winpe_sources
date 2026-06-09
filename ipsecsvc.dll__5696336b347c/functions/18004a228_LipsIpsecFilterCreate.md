# LipsIpsecFilterCreate

- ea: `0x18004a228`
- end: `0x18004a4bb`
- name: `LipsIpsecFilterCreate`
- size: `659`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180046160`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004a228`
- `0x18004a4c4`
- `0x18004a530`

## string_xrefs

- `0x18004a4a0`: `LipsIpsecFilterCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecFilterCreate(__int64 a1, __int64 a2, _QWORD *a3)
{
  LPVOID v6; // rax
  _QWORD *v7; // rdi
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // r14d
  __int64 v12; // rax
  LPVOID v14; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = IpsecAllocMem(0x30u);
  v14 = v6;
  v7 = v6;
  if ( !v6 )
  {
    v8 = 8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_40;
    v10 = 10;
    goto LABEL_5;
  }
  v11 = *(_DWORD *)(a1 + 192);
  v8 = LipsIpsecFilterLayerCreate(a1, a2, 0, v6);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_40;
    v10 = 11;
    goto LABEL_5;
  }
  v8 = LipsIpsecFilterLayerCreate(a1, a2, 1, v7 + 1);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_40;
    v10 = 12;
    goto LABEL_5;
  }
  v8 = LipsIpsecFilterLayerCreate(a1, a2, 2, v7 + 2);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_40;
    v10 = 13;
    goto LABEL_5;
  }
  if ( v11
    && (v12 = *(_QWORD *)(a1 + 184)) != 0
    && (*(_BYTE *)(v12 + 32) & 4) != 0
    && *(_DWORD *)(a1 + 144) == 3
    && *(_DWORD *)(a1 + 148) == 3
    && *(_DWORD *)(a1 + 156) == 4 )
  {
    v8 = LipsIpsecFilterLayerCreate(a1, 0, 4, v7 + 4);
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_40;
      v10 = 14;
      goto LABEL_5;
    }
    v8 = LipsIpsecFilterLayerCreate(a1, 0, 5, v7 + 5);
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_40;
      v10 = 15;
      goto LABEL_5;
    }
  }
  else
  {
    v8 = LipsIpsecFilterLayerCreate(a1, 0, 3, v7 + 3);
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_40;
      v10 = 16;
LABEL_5:
      WPP_SF_d(v9[2], v10, WPP_6aaaced537c833a4c6f456c9c9a48105_Traceguids, v8);
      goto LABEL_40;
    }
  }
  if ( !v7[1] && !v7[2] )
    v8 = 87;
  *a3 = v7;
  v14 = 0;
LABEL_40:
  LipsIpsecFilterDestroy(&v14);
  if ( v8 )
    return LipsReportError(v8, "LipsIpsecFilterCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004a228  push    rbx
0x18004a22a  push    rbp
0x18004a22b  push    rsi
0x18004a22c  push    rdi
0x18004a22d  push    r14
0x18004a22f  push    r15
0x18004a231  sub     rsp, 28h
0x18004a235  mov     rsi, rcx
0x18004a238  mov     qword ptr [r8], 0
0x18004a23f  mov     ecx, 30h ; '0'
0x18004a244  mov     r15, r8
0x18004a247  mov     rbp, rdx
0x18004a24a  call    IpsecAllocMem
0x18004a24f  mov     [rsp+58h+arg_10], rax
0x18004a254  mov     rdi, rax
0x18004a257  test    rax, rax
0x18004a25a  jnz     short loc_18004A29B
0x18004a25c  lea     ebx, [rax+8]
0x18004a25f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a266  lea     rax, WPP_GLOBAL_Control
0x18004a26d  cmp     rcx, rax
0x18004a270  jz      loc_18004A48E
0x18004a276  test    byte ptr [rcx+1Ch], 10h
0x18004a27a  jz      loc_18004A48E
0x18004a280  lea     edx, [rdi+0Ah]
0x18004a283  mov     rcx, [rcx+10h]
0x18004a287  lea     r8, WPP_6aaaced537c833a4c6f456c9c9a48105_Traceguids
0x18004a28e  mov     r9d, ebx
0x18004a291  call    WPP_SF_d
0x18004a296  jmp     loc_18004A48E
0x18004a29b  mov     r14d, [rsi+0C0h]
0x18004a2a2  mov     r9, rdi
0x18004a2a5  xor     r8d, r8d
0x18004a2a8  mov     rdx, rbp
0x18004a2ab  mov     rcx, rsi
0x18004a2ae  call    LipsIpsecFilterLayerCreate
0x18004a2b3  mov     ebx, eax
0x18004a2b5  test    eax, eax
0x18004a2b7  jz      short loc_18004A2E1
0x18004a2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2c0  lea     rax, WPP_GLOBAL_Control
0x18004a2c7  cmp     rcx, rax
0x18004a2ca  jz      loc_18004A48E
0x18004a2d0  test    byte ptr [rcx+1Ch], 10h
0x18004a2d4  jz      loc_18004A48E
0x18004a2da  mov     edx, 0Bh
0x18004a2df  jmp     short loc_18004A283
0x18004a2e1  lea     r9, [rdi+8]
0x18004a2e5  mov     r8d, 1
0x18004a2eb  mov     rdx, rbp
0x18004a2ee  mov     rcx, rsi
0x18004a2f1  call    LipsIpsecFilterLayerCreate
0x18004a2f6  mov     ebx, eax
0x18004a2f8  test    eax, eax
0x18004a2fa  jz      short loc_18004A327
0x18004a2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a303  lea     rax, WPP_GLOBAL_Control
0x18004a30a  cmp     rcx, rax
0x18004a30d  jz      loc_18004A48E
0x18004a313  test    byte ptr [rcx+1Ch], 10h
0x18004a317  jz      loc_18004A48E
0x18004a31d  mov     edx, 0Ch
0x18004a322  jmp     loc_18004A283
0x18004a327  lea     r9, [rdi+10h]
0x18004a32b  mov     r8d, 2
0x18004a331  mov     rdx, rbp
0x18004a334  mov     rcx, rsi
0x18004a337  call    LipsIpsecFilterLayerCreate
0x18004a33c  mov     ebx, eax
0x18004a33e  test    eax, eax
0x18004a340  jz      short loc_18004A36D
0x18004a342  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a349  lea     rax, WPP_GLOBAL_Control
0x18004a350  cmp     rcx, rax
0x18004a353  jz      loc_18004A48E
0x18004a359  test    byte ptr [rcx+1Ch], 10h
0x18004a35d  jz      loc_18004A48E
0x18004a363  mov     edx, 0Dh
0x18004a368  jmp     loc_18004A283
0x18004a36d  mov     r8d, 3
0x18004a373  test    r14d, r14d
0x18004a376  jz      loc_18004A437
0x18004a37c  mov     rax, [rsi+0B8h]
0x18004a383  test    rax, rax
0x18004a386  jz      loc_18004A437
0x18004a38c  test    byte ptr [rax+20h], 4
0x18004a390  jz      loc_18004A437
0x18004a396  cmp     [rsi+90h], r8d
0x18004a39d  jnz     loc_18004A437
0x18004a3a3  cmp     [rsi+94h], r8d
0x18004a3aa  jnz     loc_18004A437
0x18004a3b0  cmp     dword ptr [rsi+9Ch], 4
0x18004a3b7  jnz     short loc_18004A437
0x18004a3b9  xor     edx, edx
0x18004a3bb  lea     r9, [rdi+20h]
0x18004a3bf  mov     rcx, rsi
0x18004a3c2  lea     r8d, [rdx+4]
0x18004a3c6  call    LipsIpsecFilterLayerCreate
0x18004a3cb  mov     ebx, eax
0x18004a3cd  test    eax, eax
0x18004a3cf  jz      short loc_18004A3FC
0x18004a3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3d8  lea     rax, WPP_GLOBAL_Control
0x18004a3df  cmp     rcx, rax
0x18004a3e2  jz      loc_18004A48E
0x18004a3e8  test    byte ptr [rcx+1Ch], 10h
0x18004a3ec  jz      loc_18004A48E
0x18004a3f2  mov     edx, 0Eh
0x18004a3f7  jmp     loc_18004A283
0x18004a3fc  xor     edx, edx
0x18004a3fe  lea     r9, [rdi+28h]
0x18004a402  mov     rcx, rsi
0x18004a405  lea     r8d, [rdx+5]
0x18004a409  call    LipsIpsecFilterLayerCreate
0x18004a40e  mov     ebx, eax
0x18004a410  test    eax, eax
0x18004a412  jz      short loc_18004A46E
0x18004a414  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a41b  lea     rax, WPP_GLOBAL_Control
0x18004a422  cmp     rcx, rax
0x18004a425  jz      short loc_18004A48E
0x18004a427  test    byte ptr [rcx+1Ch], 10h
0x18004a42b  jz      short loc_18004A48E
0x18004a42d  mov     edx, 0Fh
0x18004a432  jmp     loc_18004A283
0x18004a437  lea     r9, [rdi+18h]
0x18004a43b  xor     edx, edx
0x18004a43d  mov     rcx, rsi
0x18004a440  call    LipsIpsecFilterLayerCreate
0x18004a445  mov     ebx, eax
0x18004a447  test    eax, eax
0x18004a449  jz      short loc_18004A46E
0x18004a44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a452  lea     rax, WPP_GLOBAL_Control
0x18004a459  cmp     rcx, rax
0x18004a45c  jz      short loc_18004A48E
0x18004a45e  test    byte ptr [rcx+1Ch], 10h
0x18004a462  jz      short loc_18004A48E
0x18004a464  mov     edx, 10h
0x18004a469  jmp     loc_18004A283
0x18004a46e  cmp     qword ptr [rdi+8], 0
0x18004a473  jnz     short loc_18004A482
0x18004a475  cmp     qword ptr [rdi+10h], 0
0x18004a47a  mov     eax, 57h ; 'W'
0x18004a47f  cmovz   ebx, eax
0x18004a482  mov     [r15], rdi
0x18004a485  mov     [rsp+58h+arg_10], 0
0x18004a48e  lea     rcx, [rsp+58h+arg_10]
0x18004a493  call    LipsIpsecFilterDestroy
0x18004a498  test    ebx, ebx
0x18004a49a  jnz     short loc_18004A4A0
0x18004a49c  xor     eax, eax
0x18004a49e  jmp     short loc_18004A4AE
0x18004a4a0  lea     rdx, aLipsipsecfilte_0; "LipsIpsecFilterCreate"
0x18004a4a7  mov     ecx, ebx
0x18004a4a9  call    LipsReportError
0x18004a4ae  add     rsp, 28h
0x18004a4b2  pop     r15
0x18004a4b4  pop     r14
0x18004a4b6  pop     rdi
0x18004a4b7  pop     rsi
0x18004a4b8  pop     rbp
0x18004a4b9  pop     rbx
0x18004a4ba  retn
```
