# MountMgrQueryPoints

- ea: `0x1400168b0`
- end: `0x140016db0`
- name: `MountMgrQueryPoints`
- size: `1280`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x14000c528`
- `0x1400147a0`
- `0x140018560`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x1400168b0`
- `0x140016dc0`
- `0x140017760`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400169ee`
- `ntoskrnl!ExAllocatePool2` at `0x140016ae3`
- `ntoskrnl!ExAllocatePool2` at `0x140016b6d`
- `ntoskrnl!ExAllocatePool2` at `0x1400169ee`
- `ntoskrnl!ExAllocatePool2` at `0x140016ae3`
- `ntoskrnl!ExAllocatePool2` at `0x140016b6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016a52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016a52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d4c`

## pseudocode

```c
__int64 __fastcall MountMgrQueryPoints(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  unsigned int *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r10
  __int64 v9; // r11
  __int64 v10; // rsi
  __int64 v11; // rbp
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rdx
  PVOID *v14; // rsi
  __int64 v15; // rax
  unsigned __int16 v16; // ax
  WCHAR *v17; // rax
  unsigned int PointsFromMemory; // ebx
  PDEVICE_OBJECT v20; // rcx
  void *v21; // rax
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  _WORD *Pool2; // r14
  PVOID v26[2]; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING P; // [rsp+40h] [rbp-48h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  P = 0;
  *(_OWORD *)v26 = 0;
  if ( *(_DWORD *)(v3 + 16) < 0x18u )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v24 = 209;
LABEL_39:
    WPP_SF_L(v20->AttachedDevice, v24, a3, 3221225485LL);
    return 3221225485LL;
  }
  v6 = *(unsigned int **)(a2 + 24);
  a3 = *((unsigned __int16 *)v6 + 2);
  if ( (_WORD)a3 )
  {
    v7 = *v6;
  }
  else
  {
    *v6 = 0;
    v7 = 0;
  }
  v8 = *((unsigned __int16 *)v6 + 6);
  if ( !(_WORD)v8 )
    v6[2] = 0;
  v9 = *((unsigned __int16 *)v6 + 10);
  if ( !(_WORD)v9 )
    v6[4] = 0;
  if ( (a3 & 1) != 0
    || (v7 & 1) != 0
    || (v10 = v6[2], (v10 & 1) != 0 || (v8 & 1) != 0)
    || (v11 = v6[4], (v11 & 1) != 0 || (v9 & 1) != 0) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v24 = 210;
    goto LABEL_39;
  }
  v12 = v8 + v10;
  v13 = a3 + v7;
  if ( v13 <= v12 )
    v13 = v12;
  if ( v13 <= v9 + v11 )
    v13 = v9 + v11;
  if ( v13 > *(unsigned int *)(v3 + 16) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 211, a3, 3221225485LL);
    return 3221225485LL;
  }
  if ( *(_DWORD *)(v3 + 8) < 0x20u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 212, a3, 3221225485LL);
    return 3221225485LL;
  }
  if ( !(_WORD)a3 )
  {
    v14 = 0;
LABEL_19:
    v15 = *((unsigned __int16 *)v6 + 6);
    if ( (_WORD)v15 )
    {
      Pool2 = (_WORD *)ExAllocatePool2(258, v15 + 2, 1098149453);
      if ( Pool2 )
      {
        *Pool2 = *((_WORD *)v6 + 6);
        memmove(Pool2 + 1, (char *)v6 + v6[2], *((unsigned __int16 *)v6 + 6));
        PointsFromMemory = QueryPointsFromMemory(a1, a2, (int)v14, (int)Pool2, 0);
        ExFreePoolWithTag(Pool2, 0);
        return PointsFromMemory;
      }
      if ( v14 )
        ExFreePoolWithTag(v26[1], 0);
      return 3221225626LL;
    }
    v16 = *((_WORD *)v6 + 10);
    if ( !v16 )
    {
      if ( *((_WORD *)v6 + 2) )
      {
        PointsFromMemory = QueryPointsFromSymbolicLinkName(a1, v14, a2);
        ExFreePoolWithTag(v14[1], 0);
      }
      else
      {
        return (unsigned int)QueryPointsFromMemory(a1, a2, 0, 0, 0);
      }
      return PointsFromMemory;
    }
    if ( v16 <= 0xF000u )
    {
      P.Length = *((_WORD *)v6 + 10);
      P.MaximumLength = v16 + 2;
      v17 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)(v16 + 2), 1098149453);
      P.Buffer = v17;
      if ( v17 )
      {
        memmove(v17, (char *)v6 + v6[4], P.Length);
        P.Buffer[(unsigned __int64)P.Length >> 1] = 0;
        PointsFromMemory = QueryPointsFromMemory(a1, a2, (int)v14, 0, &P);
        ExFreePoolWithTag(P.Buffer, 0);
        return PointsFromMemory;
      }
      if ( v14 )
        ExFreePoolWithTag(v26[1], 0);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        return 3221225626LL;
      v23 = 216;
      goto LABEL_35;
    }
    if ( v14 )
      ExFreePoolWithTag(v26[1], 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 215, a3, 3221225485LL);
    return 3221225485LL;
  }
  if ( (unsigned __int16)a3 > 0xF000u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 213, a3, 3221225485LL);
    return 3221225485LL;
  }
  LOWORD(v26[0]) = a3;
  WORD1(v26[0]) = a3 + 2;
  v21 = (void *)ExAllocatePool2(258, (unsigned __int16)(a3 + 2), 1098149453);
  v26[1] = v21;
  if ( v21 )
  {
    memmove(v21, (char *)v6 + *v6, LOWORD(v26[0]));
    v14 = v26;
    *((_WORD *)v26[1] + ((unsigned __int64)LOWORD(v26[0]) >> 1)) = 0;
    goto LABEL_19;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
    return 3221225626LL;
  v23 = 214;
LABEL_35:
  WPP_SF_(v22->AttachedDevice, v23);
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400168b0  push    rbx
0x1400168b2  push    rbp
0x1400168b3  push    rsi
0x1400168b4  push    rdi
0x1400168b5  push    r12
0x1400168b7  push    r14
0x1400168b9  push    r15
0x1400168bb  sub     rsp, 50h
0x1400168bf  mov     r9, [rdx+0B8h]
0x1400168c6  xorps   xmm0, xmm0
0x1400168c9  xorps   xmm1, xmm1
0x1400168cc  mov     rdi, rdx
0x1400168cf  movups  xmmword ptr [rsp+88h+P.Length], xmm0
0x1400168d4  mov     r15, rcx
0x1400168d7  movups  xmmword ptr [rsp+88h+var_58], xmm1
0x1400168dc  cmp     dword ptr [r9+10h], 18h
0x1400168e1  jb      loc_140016A95
0x1400168e7  mov     rbx, [rdx+18h]
0x1400168eb  xor     r12d, r12d
0x1400168ee  movzx   r8d, word ptr [rbx+4]
0x1400168f3  test    r8w, r8w
0x1400168f7  jnz     loc_140016AB3
0x1400168fd  mov     [rbx], r12d
0x140016900  mov     edx, r12d
0x140016903  movzx   r10d, word ptr [rbx+0Ch]
0x140016908  test    r10w, r10w
0x14001690c  jnz     short loc_140016912
0x14001690e  mov     [rbx+8], r12d
0x140016912  movzx   r11d, word ptr [rbx+14h]
0x140016917  test    r11w, r11w
0x14001691b  jnz     short loc_140016921
0x14001691d  mov     [rbx+10h], r12d
0x140016921  bt      r8w, r12w
0x140016926  setnb   cl
0x140016929  test    dl, 1
0x14001692c  setz    al
0x14001692f  test    al, cl
0x140016931  jz      loc_140016D84
0x140016937  mov     esi, [rbx+8]
0x14001693a  test    sil, 1
0x14001693e  setz    cl
0x140016941  bt      r10w, r12w
0x140016946  setnb   al
0x140016949  test    al, cl
0x14001694b  jz      loc_140016D84
0x140016951  mov     ebp, [rbx+10h]
0x140016954  test    bpl, 1
0x140016958  setz    cl
0x14001695b  bt      r11w, r12w
0x140016960  setnb   al
0x140016963  test    al, cl
0x140016965  jz      loc_140016D84
0x14001696b  add     rsi, r10
0x14001696e  add     rdx, r8
0x140016971  lea     r10, [r11+rbp]
0x140016975  cmp     rdx, rsi
0x140016978  ja      short loc_14001697D
0x14001697a  mov     rdx, rsi
0x14001697d  cmp     rdx, r10
0x140016980  ja      short loc_140016985
0x140016982  mov     rdx, r10
0x140016985  mov     eax, [r9+10h]
0x140016989  cmp     rdx, rax
0x14001698c  ja      loc_140016C39
0x140016992  cmp     dword ptr [r9+8], 20h ; ' '
0x140016997  jb      loc_140016BC3
0x14001699d  mov     ebp, 0F000h
0x1400169a2  test    r8w, r8w
0x1400169a6  jnz     loc_140016ABA
0x1400169ac  mov     rsi, r12
0x1400169af  movzx   eax, word ptr [rbx+0Ch]
0x1400169b3  test    ax, ax
0x1400169b6  jnz     loc_140016B5E
0x1400169bc  movzx   eax, word ptr [rbx+14h]
0x1400169c0  test    ax, ax
0x1400169c3  jz      loc_140016A70
0x1400169c9  cmp     ax, bp
0x1400169cc  ja      loc_140016C74
0x1400169d2  mov     [rsp+88h+P.Length], ax
0x1400169d7  mov     ecx, 102h
0x1400169dc  add     ax, 2
0x1400169e0  mov     r8d, 41746E4Dh
0x1400169e6  movzx   edx, ax
0x1400169e9  mov     [rsp+88h+P.MaximumLength], dx
0x1400169ee  call    cs:__imp_ExAllocatePool2
0x1400169f5  nop     dword ptr [rax+rax+00h]
0x1400169fa  mov     [rsp+88h+P.Buffer], rax
0x1400169ff  test    rax, rax
0x140016a02  jz      loc_140016D40
0x140016a08  mov     edx, [rbx+10h]
0x140016a0b  mov     rcx, rax; void *
0x140016a0e  movzx   r8d, [rsp+88h+P.Length]; Size
0x140016a14  add     rdx, rbx; Src
0x140016a17  call    memmove
0x140016a1c  movzx   edx, [rsp+88h+P.Length]
0x140016a21  xor     r9d, r9d; int
0x140016a24  mov     rax, [rsp+88h+P.Buffer]
0x140016a29  mov     r8, rsi; int
0x140016a2c  shr     rdx, 1
0x140016a2f  mov     rcx, r15; int
0x140016a32  mov     [rax+rdx*2], r12w
0x140016a37  lea     rax, [rsp+88h+P]
0x140016a3c  mov     rdx, rdi; int
0x140016a3f  mov     [rsp+88h+ObjectName], rax; ObjectName
0x140016a44  call    QueryPointsFromMemory
0x140016a49  mov     rcx, [rsp+88h+P.Buffer]; P
0x140016a4e  xor     edx, edx; Tag
0x140016a50  mov     ebx, eax
0x140016a52  call    cs:__imp_ExFreePoolWithTag
0x140016a59  nop     dword ptr [rax+rax+00h]
0x140016a5e  mov     eax, ebx
0x140016a60  add     rsp, 50h
0x140016a64  pop     r15
0x140016a66  pop     r14
0x140016a68  pop     r12
0x140016a6a  pop     rdi
0x140016a6b  pop     rsi
0x140016a6c  pop     rbp
0x140016a6d  pop     rbx
0x140016a6e  retn
0x140016a70  mov     rcx, r15; int
0x140016a73  cmp     [rbx+4], r12w
0x140016a78  jnz     loc_140016B9F
0x140016a7e  xor     r9d, r9d; int
0x140016a81  mov     [rsp+88h+ObjectName], r12; ObjectName
0x140016a86  xor     r8d, r8d; int
0x140016a89  mov     rdx, rdi; int
0x140016a8c  call    QueryPointsFromMemory
0x140016a91  mov     ebx, eax
0x140016a93  jmp     short loc_140016A5E
0x140016a95  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a9c  lea     rax, WPP_GLOBAL_Control
0x140016aa3  cmp     rcx, rax
0x140016aa6  jnz     loc_140016B3A
0x140016aac  mov     eax, 0C000000Dh
0x140016ab1  jmp     short loc_140016A60
0x140016ab3  mov     edx, [rbx]
0x140016ab5  jmp     loc_140016903
0x140016aba  cmp     r8w, bp
0x140016abe  ja      loc_140016BFE
0x140016ac4  mov     word ptr [rsp+88h+var_58], r8w
0x140016aca  mov     ecx, 102h
0x140016acf  add     r8w, 2
0x140016ad4  movzx   edx, r8w
0x140016ad8  mov     r8d, 41746E4Dh
0x140016ade  mov     word ptr [rsp+88h+var_58+2], dx
0x140016ae3  call    cs:__imp_ExAllocatePool2
0x140016aea  nop     dword ptr [rax+rax+00h]
0x140016aef  mov     [rsp+88h+var_58+8], rax
0x140016af4  test    rax, rax
0x140016af7  jnz     loc_140016CC7
0x140016afd  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b04  lea     rax, WPP_GLOBAL_Control
0x140016b0b  cmp     rcx, rax
0x140016b0e  jz      short loc_140016B25
0x140016b10  mov     eax, [rcx+2Ch]
0x140016b13  test    al, 4
0x140016b15  jz      short loc_140016B25
0x140016b17  mov     edx, 0D6h
0x140016b1c  mov     rcx, [rcx+18h]
0x140016b20  call    WPP_SF_
0x140016b25  mov     eax, 0C000009Ah
0x140016b2a  add     rsp, 50h
0x140016b2e  pop     r15
0x140016b30  pop     r14
0x140016b32  pop     r12
0x140016b34  pop     rdi
0x140016b35  pop     rsi
0x140016b36  pop     rbp
0x140016b37  pop     rbx
0x140016b38  retn
0x140016b3a  mov     eax, [rcx+2Ch]
0x140016b3d  test    al, 1
0x140016b3f  jz      loc_140016AAC
0x140016b45  mov     edx, 0D1h
0x140016b4a  mov     rcx, [rcx+18h]
0x140016b4e  mov     r9d, 0C000000Dh
0x140016b54  call    WPP_SF_L
0x140016b59  jmp     loc_140016AAC
0x140016b5e  lea     rdx, [rax+2]
0x140016b62  mov     ecx, 102h
0x140016b67  mov     r8d, 41746E4Dh
0x140016b6d  call    cs:__imp_ExAllocatePool2
0x140016b74  nop     dword ptr [rax+rax+00h]
0x140016b79  mov     r14, rax
0x140016b7c  test    rax, rax
0x140016b7f  jnz     loc_140016CF6
0x140016b85  test    rsi, rsi
0x140016b88  jz      short loc_140016B25
0x140016b8a  mov     rcx, [rsp+88h+var_58+8]; P
0x140016b8f  xor     edx, edx; Tag
0x140016b91  call    cs:__imp_ExFreePoolWithTag
0x140016b98  nop     dword ptr [rax+rax+00h]
0x140016b9d  jmp     short loc_140016B25
0x140016b9f  mov     r8, rdi
0x140016ba2  mov     rdx, rsi
0x140016ba5  call    QueryPointsFromSymbolicLinkName
0x140016baa  mov     rcx, [rsi+8]; P
0x140016bae  xor     edx, edx; Tag
0x140016bb0  mov     ebx, eax
0x140016bb2  call    cs:__imp_ExFreePoolWithTag
0x140016bb9  nop     dword ptr [rax+rax+00h]
0x140016bbe  jmp     loc_140016A5E
0x140016bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140016bca  lea     rax, WPP_GLOBAL_Control
0x140016bd1  cmp     rcx, rax
0x140016bd4  jz      loc_140016AAC
0x140016bda  mov     eax, [rcx+2Ch]
0x140016bdd  test    al, 1
0x140016bdf  jz      loc_140016AAC
0x140016be5  mov     rcx, [rcx+18h]
0x140016be9  mov     edx, 0D4h
0x140016bee  mov     r9d, 0C000000Dh
0x140016bf4  call    WPP_SF_L
0x140016bf9  jmp     loc_140016AAC
0x140016bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c05  lea     rax, WPP_GLOBAL_Control
0x140016c0c  cmp     rcx, rax
0x140016c0f  jz      loc_140016AAC
0x140016c15  mov     eax, [rcx+2Ch]
0x140016c18  test    al, 1
0x140016c1a  jz      loc_140016AAC
0x140016c20  mov     rcx, [rcx+18h]
0x140016c24  mov     edx, 0D5h
0x140016c29  mov     r9d, 0C000000Dh
0x140016c2f  call    WPP_SF_L
0x140016c34  jmp     loc_140016AAC
0x140016c39  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c40  lea     rax, WPP_GLOBAL_Control
0x140016c47  cmp     rcx, rax
0x140016c4a  jz      loc_140016AAC
0x140016c50  mov     eax, [rcx+2Ch]
0x140016c53  test    al, 1
0x140016c55  jz      loc_140016AAC
0x140016c5b  mov     rcx, [rcx+18h]
0x140016c5f  mov     edx, 0D3h
0x140016c64  mov     r9d, 0C000000Dh
0x140016c6a  call    WPP_SF_L
0x140016c6f  jmp     loc_140016AAC
0x140016c74  test    rsi, rsi
0x140016c77  jz      short loc_140016C8C
0x140016c79  mov     rcx, [rsp+88h+var_58+8]; P
0x140016c7e  xor     edx, edx; Tag
0x140016c80  call    cs:__imp_ExFreePoolWithTag
0x140016c87  nop     dword ptr [rax+rax+00h]
0x140016c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c93  lea     rax, WPP_GLOBAL_Control
0x140016c9a  cmp     rcx, rax
0x140016c9d  jz      loc_140016AAC
0x140016ca3  mov     eax, [rcx+2Ch]
0x140016ca6  test    al, 1
0x140016ca8  jz      loc_140016AAC
0x140016cae  mov     rcx, [rcx+18h]
0x140016cb2  mov     edx, 0D7h
0x140016cb7  mov     r9d, 0C000000Dh
0x140016cbd  call    WPP_SF_L
0x140016cc2  jmp     loc_140016AAC
0x140016cc7  mov     edx, [rbx]
0x140016cc9  mov     rcx, rax; void *
0x140016ccc  movzx   r8d, word ptr [rsp+88h+var_58]; Size
0x140016cd2  add     rdx, rbx; Src
0x140016cd5  call    memmove
0x140016cda  movzx   edx, word ptr [rsp+88h+var_58]
0x140016cdf  lea     rsi, [rsp+88h+var_58]
0x140016ce4  mov     rax, [rsp+88h+var_58+8]
0x140016ce9  shr     rdx, 1
0x140016cec  mov     [rax+rdx*2], r12w
0x140016cf1  jmp     loc_1400169AF
0x140016cf6  movzx   eax, word ptr [rbx+0Ch]
0x140016cfa  lea     rcx, [r14+2]; void *
0x140016cfe  mov     [r14], ax
0x140016d02  mov     edx, [rbx+8]
0x140016d05  movzx   r8d, word ptr [rbx+0Ch]; Size
0x140016d0a  add     rdx, rbx; Src
0x140016d0d  call    memmove
0x140016d12  mov     r9, r14; int
0x140016d15  mov     [rsp+88h+ObjectName], r12; ObjectName
0x140016d1a  mov     r8, rsi; int
0x140016d1d  mov     rdx, rdi; int
0x140016d20  mov     rcx, r15; int
0x140016d23  call    QueryPointsFromMemory
0x140016d28  xor     edx, edx; Tag
0x140016d2a  mov     rcx, r14; P
0x140016d2d  mov     ebx, eax
0x140016d2f  call    cs:__imp_ExFreePoolWithTag
0x140016d36  nop     dword ptr [rax+rax+00h]
0x140016d3b  jmp     loc_140016A5E
0x140016d40  test    rsi, rsi
0x140016d43  jz      short loc_140016D58
0x140016d45  mov     rcx, [rsp+88h+var_58+8]; P
0x140016d4a  xor     edx, edx; Tag
0x140016d4c  call    cs:__imp_ExFreePoolWithTag
0x140016d53  nop     dword ptr [rax+rax+00h]
0x140016d58  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d5f  lea     rax, WPP_GLOBAL_Control
0x140016d66  cmp     rcx, rax
0x140016d69  jz      loc_140016B25
0x140016d6f  mov     eax, [rcx+2Ch]
0x140016d72  test    al, 4
0x140016d74  jz      loc_140016B25
  ... truncated ...
```
