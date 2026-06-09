# ClasspQueryCommandDurationLimitModePage

- ea: `0x140033110`
- end: `0x140033777`
- name: `ClasspQueryCommandDurationLimitModePage`
- size: `1639`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT, _BYTE *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400316d4`
- `0x140033924`
- `0x140035128`

## callees

- `0x14001fbf4`
- `0x14001feac`
- `0x14001fedc`
- `0x140030ecc`
- `0x140031148`
- `0x140033110`
- `0x14003b8c8`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400331ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400331ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033759`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033759`

## pseudocode

```c
__int64 __fastcall ClasspQueryCommandDurationLimitModePage(PDEVICE_OBJECT a1, _BYTE *a2)
{
  bool v3; // zf
  PDEVICE_OBJECT v4; // r13
  void *Pool2; // r15
  int ModeSubPage; // ebx
  unsigned int v7; // esi
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r10
  __int64 v14; // r9
  __int64 v15; // r8
  _BYTE *v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int8 v20; // r9
  __int64 v21; // r10
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  char v27; // r9
  __int64 v28; // rdx
  __int64 v30; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 v32; // [rsp+98h] [rbp+48h] BYREF
  __int16 v33; // [rsp+A0h] [rbp+50h]
  __int16 v34; // [rsp+A8h] [rbp+58h]

  v3 = (*a2 & 1) == 0;
  v4 = a1;
  Pool2 = 0;
  v31 = 0;
  LOBYTE(v32) = 0;
  if ( v3 )
  {
LABEL_2:
    ModeSubPage = -1073741637;
    goto LABEL_92;
  }
  if ( a2[9] )
  {
    memset(a2 + 12, 0, 0xA0u);
    a2[9] = 0;
  }
  if ( !(unsigned __int8)ClasspGetCommandDurationLimitModePage(a2, &v32) )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        171,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        (*(unsigned __int16 *)a2 >> 4) & 3);
    }
    goto LABEL_91;
  }
  v7 = (unsigned __int8)v32;
  if ( (unsigned __int8)(v32 - 7) > 1u )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        170,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        (unsigned __int8)v32);
    }
    goto LABEL_2;
  }
  LODWORD(v30) = 255;
  Pool2 = (void *)ExAllocatePool2(64, 255, 1867277139);
  if ( Pool2 )
  {
    LOBYTE(v10) = 1;
    LOBYTE(v9) = v7;
    if ( (int)ClasspGetModeSubPage((int)v4->DriverObject, v8, v9, v10, Pool2, (__int64)&v30, (__int64)&v31) < 0 )
    {
      a1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_23;
      }
      v11 = 166;
LABEL_22:
      WPP_SF_d(a1->AttachedDevice, v11, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, v7);
LABEL_23:
      ModeSubPage = -1073741275;
      goto LABEL_92;
    }
    v12 = v31;
    if ( (*(_BYTE *)v31 & 0x3F) != 0xA || *(_BYTE *)(v31 + 1) != (_BYTE)v7 )
    {
      a1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_91;
      }
      v26 = *(unsigned __int8 *)(v31 + 1);
      v27 = *(_BYTE *)v31;
      v28 = 167;
      goto LABEL_82;
    }
    LODWORD(a1) = *(_BYTE *)v31 >> 7;
    LOWORD(a1) = *(_WORD *)a2 & 0xFFBF | ((_WORD)a1 << 6);
    *(_WORD *)a2 = (_WORD)a1;
    HIBYTE(v32) = *(_BYTE *)(v12 + 2);
    LOBYTE(v32) = *(_BYTE *)(v12 + 3);
    if ( (_BYTE)v7 == 7 )
    {
      if ( v32 < 0xE4u )
        goto LABEL_91;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      do
      {
        if ( (*(_BYTE *)(v12 + v14 + 8) & 0xF) != 0 )
          *(_DWORD *)&a2[v15 + 16] |= 1u;
        HIBYTE(v32) = *(_BYTE *)(v12 + v14 + 10);
        LOBYTE(v32) = *(_BYTE *)(v12 + v14 + 11);
        HIBYTE(v33) = *(_BYTE *)(v12 + v14 + 12);
        LOBYTE(v33) = *(_BYTE *)(v12 + v14 + 13);
        HIBYTE(v34) = *(_BYTE *)(v12 + v14 + 18);
        LOBYTE(v34) = *(_BYTE *)(v12 + v14 + 19);
        if ( v32 )
          *(_DWORD *)&a2[v15 + 16] |= 2u;
        v16 = &a2[v15];
        if ( v33 )
          *((_DWORD *)v16 + 4) |= 4u;
        if ( v34 )
          *((_DWORD *)v16 + 4) |= 8u;
        if ( (*(_BYTE *)(v12 + v14 + 14) & 0xF0) != 0 )
          *((_DWORD *)v16 + 4) |= 0x10u;
        if ( (*(_BYTE *)(v12 + v14 + 14) & 0xF) != 0 )
          *((_DWORD *)v16 + 4) |= 0x20u;
        if ( (*(_BYTE *)(v12 + v14 + 22) & 0xF) != 0 )
          *(_DWORD *)&a2[v15 + 16] = *((_DWORD *)v16 + 4) | 0x40;
        if ( *(_DWORD *)&a2[v15 + 16] )
          ++a2[9];
        ++v13;
        v14 += 32;
        v15 += 20;
      }
      while ( v13 != 7 );
    }
    else
    {
      if ( v32 < 0xE4u )
        goto LABEL_91;
      v17 = 0;
      v15 = 0;
      v18 = 0;
      do
      {
        if ( (*(_BYTE *)(v15 + v12 + 8) & 0xF) != 0 )
          *(_DWORD *)&a2[v18 + 16] |= 1u;
        HIBYTE(v32) = *(_BYTE *)(v15 + v12 + 10);
        LOBYTE(v32) = *(_BYTE *)(v15 + v12 + 11);
        HIBYTE(v33) = *(_BYTE *)(v15 + v12 + 12);
        LOBYTE(v33) = *(_BYTE *)(v15 + v12 + 13);
        HIBYTE(v34) = *(_BYTE *)(v15 + v12 + 18);
        LOBYTE(v34) = *(_BYTE *)(v15 + v12 + 19);
        if ( v32 )
          *(_DWORD *)&a2[v18 + 16] |= 2u;
        if ( v33 )
          *(_DWORD *)&a2[v18 + 16] |= 4u;
        if ( v34 )
          *(_DWORD *)&a2[v18 + 16] |= 8u;
        if ( (*(_BYTE *)(v15 + v12 + 14) & 0xF0) != 0 )
          *(_DWORD *)&a2[v18 + 16] |= 0x10u;
        if ( (*(_BYTE *)(v15 + v12 + 14) & 0xF) != 0 )
          *(_DWORD *)&a2[v18 + 16] |= 0x20u;
        if ( (*(_BYTE *)(v15 + v12 + 22) & 0xF) != 0 )
          *(_DWORD *)&a2[v18 + 16] |= 0x40u;
        if ( *(_DWORD *)&a2[v18 + 16] )
          ++a2[9];
        ++v17;
        v15 += 32;
        v18 += 20;
      }
      while ( v17 != 7 );
    }
    LOBYTE(v15) = v7;
    ModeSubPage = ClasspGetModeSubPage((int)v4->DriverObject, v12, v15, 0, Pool2, (__int64)&v30, (__int64)&v31);
    if ( ModeSubPage < 0 )
    {
      a1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_23;
      }
      v11 = 168;
      goto LABEL_22;
    }
    v19 = v31;
    if ( (*(_BYTE *)v31 & 0x3F) == 0xA && *(_BYTE *)(v31 + 1) == (_BYTE)v7 )
    {
      v20 = 0;
      v21 = 0;
      if ( (_BYTE)v7 == 7 )
      {
        do
        {
          v22 = 5 * v21;
          v23 = 32 * v21;
          ++v20;
          ++v21;
          HIBYTE(v32) = *(_BYTE *)(v23 + v19 + 10);
          LOBYTE(v32) = *(_BYTE *)(v23 + v19 + 11);
          HIBYTE(v33) = *(_BYTE *)(v23 + v19 + 12);
          LOBYTE(v33) = *(_BYTE *)(v23 + v19 + 13);
          HIBYTE(v34) = *(_BYTE *)(v23 + v19 + 18);
          LOBYTE(v34) = *(_BYTE *)(v23 + v19 + 19);
          a2[4 * v22 + 12] = v20;
          a2[4 * v22 + 20] = *(_BYTE *)(v23 + v19 + 8) & 0xF;
          *(_WORD *)&a2[4 * v22 + 24] = v32;
          *(_WORD *)&a2[4 * v22 + 26] = v33;
          *(_WORD *)&a2[4 * v22 + 28] = v34;
          a2[4 * v22 + 21] = *(_BYTE *)(v23 + v19 + 14) >> 4;
          a2[4 * v22 + 22] = *(_BYTE *)(v23 + v19 + 14) & 0xF;
          a2[4 * v22 + 23] = *(_BYTE *)(v23 + v19 + 22) & 0xF;
        }
        while ( v20 < 7u );
      }
      else
      {
        do
        {
          v24 = 5 * v21;
          v25 = 32 * v21;
          ++v20;
          ++v21;
          HIBYTE(v32) = *(_BYTE *)(v25 + v19 + 10);
          LOBYTE(v32) = *(_BYTE *)(v25 + v19 + 11);
          HIBYTE(v33) = *(_BYTE *)(v25 + v19 + 12);
          LOBYTE(v33) = *(_BYTE *)(v25 + v19 + 13);
          HIBYTE(v34) = *(_BYTE *)(v25 + v19 + 18);
          LOBYTE(v34) = *(_BYTE *)(v25 + v19 + 19);
          a2[4 * v24 + 12] = v20;
          a2[4 * v24 + 20] = *(_BYTE *)(v25 + v19 + 8) & 0xF;
          *(_WORD *)&a2[4 * v24 + 24] = v32;
          *(_WORD *)&a2[4 * v24 + 26] = v33;
          *(_WORD *)&a2[4 * v24 + 28] = v34;
          a2[4 * v24 + 21] = *(_BYTE *)(v25 + v19 + 14) >> 4;
          a2[4 * v24 + 22] = *(_BYTE *)(v25 + v19 + 14) & 0xF;
          a2[4 * v24 + 23] = *(_BYTE *)(v25 + v19 + 22) & 0xF;
        }
        while ( v20 < 7u );
      }
LABEL_95:
      ExFreePoolWithTag(Pool2, 0);
      return (unsigned int)ModeSubPage;
    }
    a1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v26 = *(unsigned __int8 *)(v31 + 1);
      v27 = *(_BYTE *)v31;
      v28 = 169;
LABEL_82:
      WPP_SF_DD(a1->AttachedDevice, v28, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, v27 & 0x3F, v26);
    }
LABEL_91:
    ModeSubPage = -1073741811;
    goto LABEL_92;
  }
  LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 165, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
  }
  ModeSubPage = -1073741670;
LABEL_92:
  if ( ClassPnPETWEnabled )
  {
    LOBYTE(a1) = (*(_WORD *)a2 & 8) != 0;
    ClasspCDLModePageOperationFailureEvent(
      (_DWORD)a1,
      v4->DriverObject,
      ModeSubPage,
      1,
      *a2 & 1,
      (*(_WORD *)a2 & 0x40) != 0,
      (char)a1,
      ((unsigned __int8)*(_WORD *)a2 >> 4) & 3);
  }
  if ( Pool2 )
    goto LABEL_95;
  return (unsigned int)ModeSubPage;
}

```

## disassembly

```asm
0x140033110  push    rbp
0x140033112  push    rbx
0x140033113  push    rsi
0x140033114  push    rdi
0x140033115  push    r12
0x140033117  push    r13
0x140033119  push    r15
0x14003311b  mov     rbp, rsp
0x14003311e  sub     rsp, 50h
0x140033122  xor     r12d, r12d
0x140033125  mov     rdi, rdx
0x140033128  test    byte ptr [rdx], 1
0x14003312b  mov     r13, rcx
0x14003312e  mov     r15d, r12d
0x140033131  mov     [rbp+var_8], r12
0x140033135  mov     byte ptr [rbp+arg_8], r12b
0x140033139  jnz     short loc_140033145
0x14003313b  mov     ebx, 0C00000BBh
0x140033140  jmp     loc_140033704
0x140033145  cmp     [rdx+9], r12b
0x140033149  jbe     short loc_140033160
0x14003314b  lea     rcx, [rdx+0Ch]; void *
0x14003314f  mov     r8d, 0A0h; Size
0x140033155  xor     edx, edx; Val
0x140033157  call    memset
0x14003315c  mov     [rdi+9], r12b
0x140033160  lea     rdx, [rbp+arg_8]
0x140033164  mov     rcx, rdi
0x140033167  call    ClasspGetCommandDurationLimitModePage
0x14003316c  test    al, al
0x14003316e  jz      loc_1400336BC
0x140033174  movzx   esi, byte ptr [rbp+arg_8]
0x140033178  lea     eax, [rsi-7]
0x14003317b  cmp     al, 1
0x14003317d  jbe     short loc_1400331BB
0x14003317f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033186  lea     rax, WPP_GLOBAL_Control
0x14003318d  cmp     rcx, rax
0x140033190  jz      short loc_14003313B
0x140033192  test    dword ptr [rcx+2Ch], 20000h
0x140033199  jz      short loc_14003313B
0x14003319b  cmp     byte ptr [rcx+29h], 3
0x14003319f  jb      short loc_14003313B
0x1400331a1  mov     rcx, [rcx+18h]
0x1400331a5  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400331ac  mov     r9d, esi
0x1400331af  mov     edx, 0AAh
0x1400331b4  call    WPP_SF_d
0x1400331b9  jmp     short loc_14003313B
0x1400331bb  mov     edx, 0FFh
0x1400331c0  mov     ecx, 40h ; '@'
0x1400331c5  mov     r8d, 6F4C6353h
0x1400331cb  mov     dword ptr [rbp+var_10], edx
0x1400331ce  call    cs:__imp_ExAllocatePool2
0x1400331d5  nop     dword ptr [rax+rax+00h]
0x1400331da  mov     r15, rax
0x1400331dd  test    rax, rax
0x1400331e0  jnz     short loc_140033223
0x1400331e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331e9  lea     rax, WPP_GLOBAL_Control
0x1400331f0  cmp     rcx, rax
0x1400331f3  jz      short loc_140033219
0x1400331f5  test    dword ptr [rcx+2Ch], 20000h
0x1400331fc  jz      short loc_140033219
0x1400331fe  cmp     byte ptr [rcx+29h], 2
0x140033202  jb      short loc_140033219
0x140033204  mov     rcx, [rcx+18h]
0x140033208  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003320f  mov     edx, 0A5h
0x140033214  call    WPP_SF_
0x140033219  mov     ebx, 0C000009Ah
0x14003321e  jmp     loc_140033704
0x140033223  mov     rcx, [r13+8]; int
0x140033227  lea     rax, [rbp+var_8]
0x14003322b  mov     [rsp+50h+var_20], rax; __int64
0x140033230  mov     r9b, 1; int
0x140033233  lea     rax, [rbp+var_10]
0x140033237  mov     r8b, sil; int
0x14003323a  mov     [rsp+50h+var_28], rax; __int64
0x14003323f  mov     [rsp+50h+var_30], r15; void *
0x140033244  call    ClasspGetModeSubPage
0x140033249  test    eax, eax
0x14003324b  jns     short loc_140033291
0x14003324d  mov     rcx, cs:WPP_GLOBAL_Control
0x140033254  lea     rax, WPP_GLOBAL_Control
0x14003325b  cmp     rcx, rax
0x14003325e  jz      short loc_140033287
0x140033260  test    dword ptr [rcx+2Ch], 20000h
0x140033267  jz      short loc_140033287
0x140033269  cmp     byte ptr [rcx+29h], 4
0x14003326d  jb      short loc_140033287
0x14003326f  mov     edx, 0A6h
0x140033274  mov     rcx, [rcx+18h]
0x140033278  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003327f  mov     r9d, esi
0x140033282  call    WPP_SF_d
0x140033287  mov     ebx, 0C0000225h
0x14003328c  jmp     loc_140033704
0x140033291  mov     rdx, [rbp+var_8]; int
0x140033295  movzx   r8d, byte ptr [rdx]
0x140033299  mov     al, r8b
0x14003329c  and     al, 3Fh
0x14003329e  cmp     al, 0Ah
0x1400332a0  jnz     loc_14003368C
0x1400332a6  cmp     [rdx+1], sil
0x1400332aa  jnz     loc_14003368C
0x1400332b0  movzx   eax, word ptr [rdi]
0x1400332b3  shr     r8b, 7
0x1400332b7  movzx   ecx, r8b
0x1400332bb  mov     r8d, 0FFBFh
0x1400332c1  and     ax, r8w
0x1400332c5  shl     cx, 6
0x1400332c9  or      cx, ax
0x1400332cc  mov     [rdi], cx
0x1400332cf  mov     al, [rdx+2]
0x1400332d2  mov     byte ptr [rbp+arg_8+1], al
0x1400332d5  mov     al, [rdx+3]
0x1400332d8  mov     byte ptr [rbp+arg_8], al
0x1400332db  mov     eax, 0E4h
0x1400332e0  cmp     sil, 7
0x1400332e4  jnz     loc_1400333B1
0x1400332ea  cmp     [rbp+arg_8], ax
0x1400332ee  jb      loc_1400336FF
0x1400332f4  mov     r10, r12
0x1400332f7  mov     r9, r12
0x1400332fa  mov     r8, r12
0x1400332fd  test    byte ptr [rdx+r9+8], 0Fh
0x140033303  jz      short loc_14003330B
0x140033305  or      dword ptr [r8+rdi+10h], 1
0x14003330b  mov     al, [rdx+r9+0Ah]
0x140033310  mov     byte ptr [rbp+arg_8+1], al
0x140033313  mov     al, [rdx+r9+0Bh]
0x140033318  mov     byte ptr [rbp+arg_8], al
0x14003331b  mov     al, [rdx+r9+0Ch]
0x140033320  mov     byte ptr [rbp+arg_10+1], al
0x140033323  mov     al, [rdx+r9+0Dh]
0x140033328  mov     byte ptr [rbp+arg_10], al
0x14003332b  mov     al, [rdx+r9+12h]
0x140033330  mov     byte ptr [rbp+arg_18+1], al
0x140033333  mov     al, [rdx+r9+13h]
0x140033338  mov     byte ptr [rbp+arg_18], al
0x14003333b  cmp     [rbp+arg_8], r12w
0x140033340  jz      short loc_140033348
0x140033342  or      dword ptr [r8+rdi+10h], 2
0x140033348  lea     rcx, [r8+rdi]
0x14003334c  cmp     [rbp+arg_10], r12w
0x140033351  jz      short loc_140033357
0x140033353  or      dword ptr [rcx+10h], 4
0x140033357  cmp     [rbp+arg_18], r12w
0x14003335c  jz      short loc_140033362
0x14003335e  or      dword ptr [rcx+10h], 8
0x140033362  test    byte ptr [rdx+r9+0Eh], 0F0h
0x140033368  jz      short loc_14003336E
0x14003336a  or      dword ptr [rcx+10h], 10h
0x14003336e  test    byte ptr [rdx+r9+0Eh], 0Fh
0x140033374  jz      short loc_14003337A
0x140033376  or      dword ptr [rcx+10h], 20h
0x14003337a  test    byte ptr [rdx+r9+16h], 0Fh
0x140033380  jz      short loc_14003338D
0x140033382  mov     eax, [rcx+10h]
0x140033385  or      eax, 40h
0x140033388  mov     [r8+rdi+10h], eax
0x14003338d  cmp     [r8+rdi+10h], r12d
0x140033392  jz      short loc_140033397
0x140033394  inc     byte ptr [rdi+9]
0x140033397  inc     r10
0x14003339a  add     r9, 20h ; ' '
0x14003339e  add     r8, 14h
0x1400333a2  cmp     r10, 7
0x1400333a6  jnz     loc_1400332FD
0x1400333ac  jmp     loc_14003346B
0x1400333b1  cmp     [rbp+arg_8], ax
0x1400333b5  jb      loc_1400336FF
0x1400333bb  mov     r9, r12
0x1400333be  mov     r8, r12
0x1400333c1  mov     rcx, r12
0x1400333c4  test    byte ptr [r8+rdx+8], 0Fh
0x1400333ca  jz      short loc_1400333D1
0x1400333cc  or      dword ptr [rcx+rdi+10h], 1
0x1400333d1  mov     al, [r8+rdx+0Ah]
0x1400333d6  mov     byte ptr [rbp+arg_8+1], al
0x1400333d9  mov     al, [r8+rdx+0Bh]
0x1400333de  mov     byte ptr [rbp+arg_8], al
0x1400333e1  mov     al, [r8+rdx+0Ch]
0x1400333e6  mov     byte ptr [rbp+arg_10+1], al
0x1400333e9  mov     al, [r8+rdx+0Dh]
0x1400333ee  mov     byte ptr [rbp+arg_10], al
0x1400333f1  mov     al, [r8+rdx+12h]
0x1400333f6  mov     byte ptr [rbp+arg_18+1], al
0x1400333f9  mov     al, [r8+rdx+13h]
0x1400333fe  mov     byte ptr [rbp+arg_18], al
0x140033401  cmp     [rbp+arg_8], r12w
0x140033406  jz      short loc_14003340D
0x140033408  or      dword ptr [rcx+rdi+10h], 2
0x14003340d  cmp     [rbp+arg_10], r12w
0x140033412  jz      short loc_140033419
0x140033414  or      dword ptr [rcx+rdi+10h], 4
0x140033419  cmp     [rbp+arg_18], r12w
0x14003341e  jz      short loc_140033425
0x140033420  or      dword ptr [rcx+rdi+10h], 8
0x140033425  test    byte ptr [r8+rdx+0Eh], 0F0h
0x14003342b  jz      short loc_140033432
0x14003342d  or      dword ptr [rcx+rdi+10h], 10h
0x140033432  test    byte ptr [r8+rdx+0Eh], 0Fh
0x140033438  jz      short loc_14003343F
0x14003343a  or      dword ptr [rcx+rdi+10h], 20h
0x14003343f  test    byte ptr [r8+rdx+16h], 0Fh
0x140033445  jz      short loc_14003344C
0x140033447  or      dword ptr [rcx+rdi+10h], 40h
0x14003344c  cmp     [rcx+rdi+10h], r12d
0x140033451  jz      short loc_140033456
0x140033453  inc     byte ptr [rdi+9]
0x140033456  inc     r9
0x140033459  add     r8, 20h ; ' '
0x14003345d  add     rcx, 14h
0x140033461  cmp     r9, 7
0x140033465  jnz     loc_1400333C4
0x14003346b  mov     rcx, [r13+8]; int
0x14003346f  lea     rax, [rbp+var_8]
0x140033473  mov     [rsp+50h+var_20], rax; __int64
0x140033478  xor     r9d, r9d; int
0x14003347b  lea     rax, [rbp+var_10]
0x14003347f  mov     r8b, sil; int
0x140033482  mov     [rsp+50h+var_28], rax; __int64
0x140033487  mov     [rsp+50h+var_30], r15; void *
0x14003348c  call    ClasspGetModeSubPage
0x140033491  mov     ebx, eax
0x140033493  test    eax, eax
0x140033495  jns     short loc_1400334CF
0x140033497  mov     rcx, cs:WPP_GLOBAL_Control
0x14003349e  lea     rax, WPP_GLOBAL_Control
0x1400334a5  cmp     rcx, rax
0x1400334a8  jz      loc_140033287
0x1400334ae  test    dword ptr [rcx+2Ch], 20000h
0x1400334b5  jz      loc_140033287
0x1400334bb  cmp     byte ptr [rcx+29h], 4
0x1400334bf  jb      loc_140033287
0x1400334c5  mov     edx, 0A8h
0x1400334ca  jmp     loc_140033274
0x1400334cf  mov     r8, [rbp+var_8]
0x1400334d3  movzx   edx, byte ptr [r8]
0x1400334d7  mov     al, dl
0x1400334d9  and     al, 3Fh
0x1400334db  cmp     al, 0Ah
0x1400334dd  jnz     loc_140033637
0x1400334e3  cmp     [r8+1], sil
0x1400334e7  jnz     loc_140033637
0x1400334ed  mov     r9b, r12b
0x1400334f0  mov     r10, r12
0x1400334f3  cmp     sil, 7
0x1400334f7  jnz     loc_14003359A
0x1400334fd  lea     rcx, [r10+r10*4]
0x140033501  mov     rdx, r10
0x140033504  shl     rdx, 5
0x140033508  inc     r9b
0x14003350b  inc     r10
0x14003350e  mov     al, [rdx+r8+0Ah]
0x140033513  mov     byte ptr [rbp+arg_8+1], al
0x140033516  mov     al, [rdx+r8+0Bh]
0x14003351b  mov     byte ptr [rbp+arg_8], al
0x14003351e  mov     al, [rdx+r8+0Ch]
0x140033523  mov     byte ptr [rbp+arg_10+1], al
0x140033526  mov     al, [rdx+r8+0Dh]
0x14003352b  mov     byte ptr [rbp+arg_10], al
0x14003352e  mov     al, [rdx+r8+12h]
0x140033533  mov     byte ptr [rbp+arg_18+1], al
0x140033536  mov     al, [rdx+r8+13h]
0x14003353b  mov     byte ptr [rbp+arg_18], al
0x14003353e  mov     [rdi+rcx*4+0Ch], r9b
0x140033543  mov     al, [rdx+r8+8]
0x140033548  and     al, 0Fh
0x14003354a  mov     [rdi+rcx*4+14h], al
0x14003354e  movzx   eax, [rbp+arg_8]
0x140033552  mov     [rdi+rcx*4+18h], ax
0x140033557  movzx   eax, [rbp+arg_10]
0x14003355b  mov     [rdi+rcx*4+1Ah], ax
0x140033560  movzx   eax, [rbp+arg_18]
0x140033564  mov     [rdi+rcx*4+1Ch], ax
0x140033569  mov     al, [rdx+r8+0Eh]
0x14003356e  shr     al, 4
0x140033571  mov     [rdi+rcx*4+15h], al
0x140033575  mov     al, [rdx+r8+0Eh]
0x14003357a  and     al, 0Fh
0x14003357c  mov     [rdi+rcx*4+16h], al
0x140033580  mov     al, [rdx+r8+16h]
0x140033585  and     al, 0Fh
0x140033587  mov     [rdi+rcx*4+17h], al
0x14003358b  cmp     r9b, 7
0x14003358f  jb      loc_1400334FD
0x140033595  jmp     loc_140033754
0x14003359a  lea     rcx, [r10+r10*4]
0x14003359e  mov     rdx, r10
0x1400335a1  shl     rdx, 5
0x1400335a5  inc     r9b
0x1400335a8  inc     r10
0x1400335ab  mov     al, [rdx+r8+0Ah]
0x1400335b0  mov     byte ptr [rbp+arg_8+1], al
0x1400335b3  mov     al, [rdx+r8+0Bh]
0x1400335b8  mov     byte ptr [rbp+arg_8], al
0x1400335bb  mov     al, [rdx+r8+0Ch]
  ... truncated ...
```
