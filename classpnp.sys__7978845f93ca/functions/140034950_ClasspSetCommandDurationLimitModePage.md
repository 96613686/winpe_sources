# ClasspSetCommandDurationLimitModePage

- ea: `0x140034950`
- end: `0x140034e01`
- name: `ClasspSetCommandDurationLimitModePage`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140035128`

## callees

- `0x14001fbf4`
- `0x14001feac`
- `0x14001fedc`
- `0x140025134`
- `0x140030ecc`
- `0x140031148`
- `0x140034950`
- `0x14003b8c8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400349fb`
- `ntoskrnl!ExAllocatePool2` at `0x1400349fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034ddf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034ddf`

## pseudocode

```c
__int64 __fastcall ClasspSetCommandDurationLimitModePage(__int64 a1, __int16 *a2)
{
  __int16 v2; // r9
  _BYTE *Pool2; // rsi
  char v4; // bp
  __int64 v6; // r14
  int v7; // ebx
  unsigned int v8; // r9d
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rdx
  unsigned __int8 v13; // r8
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // r10
  _BYTE *v17; // r9
  __int64 v18; // r10
  char v19; // dl
  __int64 v21; // [rsp+68h] [rbp+10h] BYREF
  __int64 v22; // [rsp+70h] [rbp+18h] BYREF

  v2 = *a2;
  Pool2 = 0;
  v4 = 0;
  v22 = 0;
  LOBYTE(v21) = 0;
  v6 = a1;
  if ( (v2 & 1) == 0 )
  {
LABEL_2:
    v7 = -1073741637;
    goto LABEL_68;
  }
  if ( !(unsigned __int8)ClasspGetCommandDurationLimitModePage(a2, &v21) )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 200, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, (v8 >> 4) & 3);
    }
    goto LABEL_67;
  }
  v9 = (unsigned __int8)v21;
  if ( (unsigned __int8)(v21 - 7) > 1u )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        199,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        (unsigned __int8)v21);
    }
    goto LABEL_2;
  }
  LODWORD(v21) = 255;
  Pool2 = (_BYTE *)ExAllocatePool2(64, 255, 1867277139);
  if ( !Pool2 )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
    }
    v7 = -1073741670;
    goto LABEL_68;
  }
  LOBYTE(v11) = v9;
  if ( (int)ClasspGetModeSubPage(*(_QWORD *)(v6 + 8), v10, v11, 0, Pool2, (__int64)&v21, (__int64)&v22) < 0 )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, v9);
    }
    v7 = -1073741275;
    goto LABEL_68;
  }
  v12 = v22;
  v13 = *(_BYTE *)v22;
  if ( (*(_BYTE *)v22 & 0x3F) != 0xA || *(_BYTE *)(v22 + 1) != (_BYTE)v9 )
  {
    LODWORD(a1) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        198,
        WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
        v13 & 0x3F,
        *(unsigned __int8 *)(v22 + 1));
    }
LABEL_67:
    v7 = -1073741811;
    goto LABEL_68;
  }
  *Pool2 = 0;
  v4 = v13 >> 7;
  *(_BYTE *)(v12 + 7) &= 0xFu;
  v14 = 0;
  if ( (_BYTE)v9 == 7 )
  {
    v15 = 0;
    *(_DWORD *)v12 = -469760182;
    v16 = 0;
    do
    {
      v17 = (_BYTE *)(v12 + v16);
      if ( (*(_DWORD *)&a2[v14 + 8] & 0xE) != 0 )
        v17[8] ^= (LOBYTE(a2[v14 + 10]) ^ v17[8]) & 0xF;
      if ( (*(_DWORD *)&a2[v14 + 8] & 2) != 0 )
      {
        v17 = (_BYTE *)(v16 + v12);
        v17[11] = a2[v14 + 12];
        v17[10] = HIBYTE(a2[v14 + 12]);
      }
      if ( (*(_DWORD *)&a2[v14 + 8] & 4) != 0 )
      {
        v17 = (_BYTE *)(v16 + v12);
        v17[13] = a2[v14 + 13];
        v17[12] = HIBYTE(a2[v14 + 13]);
      }
      if ( (*(_DWORD *)&a2[v14 + 8] & 8) != 0 )
      {
        v17[19] = a2[v14 + 14];
        v17[18] = HIBYTE(a2[v14 + 14]);
      }
      if ( (*(_DWORD *)&a2[v14 + 8] & 0x10) != 0 )
        v17[14] = v17[14] & 0xF | (16 * HIBYTE(a2[v14 + 10]));
      if ( (*(_DWORD *)&a2[v14 + 8] & 0x20) != 0 )
        v17[14] ^= (LOBYTE(a2[v14 + 11]) ^ v17[14]) & 0xF;
      if ( (*(_DWORD *)&a2[v14 + 8] & 0x40) != 0 )
        v17[22] ^= (HIBYTE(a2[v14 + 11]) ^ v17[22]) & 0xF;
      ++v15;
      v14 += 10;
      v16 += 32;
    }
    while ( v15 != 7 );
  }
  else
  {
    v18 = 0;
    *(_DWORD *)v12 = -469759926;
    v17 = 0;
    do
    {
      if ( (*(_DWORD *)&a2[v14 + 8] & 0xE) != 0 )
        v17[v12 + 8] ^= (LOBYTE(a2[v14 + 10]) ^ v17[v12 + 8]) & 0xF;
      if ( (*(_DWORD *)&a2[v14 + 8] & 2) != 0 )
      {
        v17[v12 + 11] = a2[v14 + 12];
        v17[v12 + 10] = HIBYTE(a2[v14 + 12]);
      }
      if ( (*(_DWORD *)&a2[v14 + 8] & 4) != 0 )
      {
        v17[v12 + 13] = a2[v14 + 13];
        v17[v12 + 12] = HIBYTE(a2[v14 + 13]);
      }
      if ( (*(_DWORD *)&a2[v14 + 8] & 8) != 0 )
      {
        v17[v12 + 19] = a2[v14 + 14];
        v17[v12 + 18] = HIBYTE(a2[v14 + 14]);
      }
      if ( (*(_DWORD *)&a2[v14 + 8] & 0x10) != 0 )
        v17[v12 + 14] = v17[v12 + 14] & 0xF | (16 * HIBYTE(a2[v14 + 10]));
      if ( (*(_DWORD *)&a2[v14 + 8] & 0x20) != 0 )
        v17[v12 + 14] ^= (LOBYTE(a2[v14 + 11]) ^ v17[v12 + 14]) & 0xF;
      if ( (*(_DWORD *)&a2[v14 + 8] & 0x40) != 0 )
        v17[v12 + 22] ^= (HIBYTE(a2[v14 + 11]) ^ v17[v12 + 22]) & 0xF;
      ++v18;
      v14 += 10;
      v17 += 32;
    }
    while ( v18 != 7 );
  }
  LOBYTE(v17) = v4;
  v7 = ClasspModeSelect(*(_QWORD *)(v6 + 8), Pool2, (unsigned int)v21, v17);
  if ( v7 >= 0 )
    goto LABEL_71;
LABEL_68:
  if ( ClassPnPETWEnabled )
  {
    LOBYTE(a1) = *a2;
    v19 = (a1 & 8) != 0;
    LOBYTE(a1) = ((unsigned __int8)a1 >> 4) & 3;
    ClasspCDLModePageOperationFailureEvent(a1, *(_QWORD *)(v6 + 8), v7, 0, *(_BYTE *)a2 & 1, v4, v19, a1);
  }
  if ( Pool2 )
LABEL_71:
    ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140034950  mov     rax, rsp
0x140034953  mov     [rax+8], rbx
0x140034957  mov     [rax+20h], rbp
0x14003495b  push    rsi
0x14003495c  push    rdi
0x14003495d  push    r14
0x14003495f  sub     rsp, 40h
0x140034963  movzx   r9d, word ptr [rdx]
0x140034967  xor     esi, esi
0x140034969  xor     bpl, bpl
0x14003496c  mov     [rax+18h], rsi
0x140034970  mov     [rax+10h], sil
0x140034974  mov     rdi, rdx
0x140034977  mov     r14, rcx
0x14003497a  test    r9b, 1
0x14003497e  jnz     short loc_14003498A
0x140034980  mov     ebx, 0C00000BBh
0x140034985  jmp     loc_140034D97
0x14003498a  lea     rdx, [rsp+58h+arg_8]
0x14003498f  mov     rcx, rdi
0x140034992  call    ClasspGetCommandDurationLimitModePage
0x140034997  test    al, al
0x140034999  jz      loc_140034D53
0x14003499f  movzx   ebx, byte ptr [rsp+58h+arg_8]
0x1400349a4  lea     eax, [rbx-7]
0x1400349a7  cmp     al, 1
0x1400349a9  jbe     short loc_1400349E7
0x1400349ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400349b2  lea     rax, WPP_GLOBAL_Control
0x1400349b9  cmp     rcx, rax
0x1400349bc  jz      short loc_140034980
0x1400349be  test    dword ptr [rcx+2Ch], 20000h
0x1400349c5  jz      short loc_140034980
0x1400349c7  cmp     byte ptr [rcx+29h], 3
0x1400349cb  jb      short loc_140034980
0x1400349cd  mov     rcx, [rcx+18h]
0x1400349d1  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400349d8  mov     r9d, ebx
0x1400349db  mov     edx, 0C7h
0x1400349e0  call    WPP_SF_d
0x1400349e5  jmp     short loc_140034980
0x1400349e7  mov     edx, 0FFh
0x1400349ec  mov     ecx, 40h ; '@'
0x1400349f1  mov     r8d, 6F4C6353h
0x1400349f7  mov     dword ptr [rsp+58h+arg_8], edx
0x1400349fb  call    cs:__imp_ExAllocatePool2
0x140034a02  nop     dword ptr [rax+rax+00h]
0x140034a07  mov     rsi, rax
0x140034a0a  test    rax, rax
0x140034a0d  jnz     short loc_140034A50
0x140034a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a16  lea     rax, WPP_GLOBAL_Control
0x140034a1d  cmp     rcx, rax
0x140034a20  jz      short loc_140034A46
0x140034a22  test    dword ptr [rcx+2Ch], 20000h
0x140034a29  jz      short loc_140034A46
0x140034a2b  cmp     byte ptr [rcx+29h], 2
0x140034a2f  jb      short loc_140034A46
0x140034a31  mov     rcx, [rcx+18h]
0x140034a35  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034a3c  mov     edx, 0C4h
0x140034a41  call    WPP_SF_
0x140034a46  mov     ebx, 0C000009Ah
0x140034a4b  jmp     loc_140034D97
0x140034a50  mov     rcx, [r14+8]; int
0x140034a54  lea     rax, [rsp+58h+arg_10]
0x140034a59  mov     [rsp+58h+var_28], rax; __int64
0x140034a5e  xor     r9d, r9d; int
0x140034a61  lea     rax, [rsp+58h+arg_8]
0x140034a66  mov     r8b, bl; int
0x140034a69  mov     [rsp+58h+var_30], rax; __int64
0x140034a6e  mov     [rsp+58h+var_38], rsi; void *
0x140034a73  call    ClasspGetModeSubPage
0x140034a78  test    eax, eax
0x140034a7a  jns     short loc_140034AC0
0x140034a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a83  lea     rax, WPP_GLOBAL_Control
0x140034a8a  cmp     rcx, rax
0x140034a8d  jz      short loc_140034AB6
0x140034a8f  test    dword ptr [rcx+2Ch], 20000h
0x140034a96  jz      short loc_140034AB6
0x140034a98  cmp     byte ptr [rcx+29h], 4
0x140034a9c  jb      short loc_140034AB6
0x140034a9e  mov     rcx, [rcx+18h]
0x140034aa2  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034aa9  mov     r9d, ebx
0x140034aac  mov     edx, 0C5h
0x140034ab1  call    WPP_SF_d
0x140034ab6  mov     ebx, 0C0000225h
0x140034abb  jmp     loc_140034D97
0x140034ac0  mov     rdx, [rsp+58h+arg_10]
0x140034ac5  movzx   r8d, byte ptr [rdx]
0x140034ac9  mov     al, r8b
0x140034acc  and     al, 3Fh
0x140034ace  cmp     al, 0Ah
0x140034ad0  jnz     loc_140034D0B
0x140034ad6  cmp     [rdx+1], bl
0x140034ad9  jnz     loc_140034D0B
0x140034adf  mov     bpl, r8b
0x140034ae2  mov     byte ptr [rsi], 0
0x140034ae5  mov     r11b, 0Fh
0x140034ae8  shr     bpl, 7
0x140034aec  and     [rdx+7], r11b
0x140034af0  xor     r8d, r8d
0x140034af3  cmp     bl, 7
0x140034af6  jnz     loc_140034BF3
0x140034afc  xor     ebx, ebx
0x140034afe  mov     dword ptr [rdx], 0E400074Ah
0x140034b04  xor     r10d, r10d
0x140034b07  mov     eax, [r8+rdi+10h]
0x140034b0c  lea     r9, [rdx+r10]
0x140034b10  test    al, 0Eh
0x140034b12  jz      short loc_140034B28
0x140034b14  mov     al, [r9+8]
0x140034b18  mov     cl, al
0x140034b1a  xor     cl, [r8+rdi+14h]
0x140034b1f  and     cl, r11b
0x140034b22  xor     cl, al
0x140034b24  mov     [r9+8], cl
0x140034b28  mov     eax, [r8+rdi+10h]
0x140034b2d  test    al, 2
0x140034b2f  jz      short loc_140034B47
0x140034b31  mov     al, [r8+rdi+18h]
0x140034b36  lea     r9, [r10+rdx]
0x140034b3a  mov     [r9+0Bh], al
0x140034b3e  mov     al, [r8+rdi+19h]
0x140034b43  mov     [r9+0Ah], al
0x140034b47  mov     eax, [r8+rdi+10h]
0x140034b4c  test    al, 4
0x140034b4e  jz      short loc_140034B66
0x140034b50  mov     al, [r8+rdi+1Ah]
0x140034b55  lea     r9, [r10+rdx]
0x140034b59  mov     [r9+0Dh], al
0x140034b5d  mov     al, [r8+rdi+1Bh]
0x140034b62  mov     [r9+0Ch], al
0x140034b66  mov     eax, [r8+rdi+10h]
0x140034b6b  test    al, 8
0x140034b6d  jz      short loc_140034B81
0x140034b6f  mov     al, [r8+rdi+1Ch]
0x140034b74  mov     [r9+13h], al
0x140034b78  mov     al, [r8+rdi+1Dh]
0x140034b7d  mov     [r9+12h], al
0x140034b81  mov     eax, [r8+rdi+10h]
0x140034b86  test    al, 10h
0x140034b88  jz      short loc_140034B9F
0x140034b8a  mov     cl, [r8+rdi+15h]
0x140034b8f  mov     al, [r9+0Eh]
0x140034b93  shl     cl, 4
0x140034b96  and     al, r11b
0x140034b99  or      cl, al
0x140034b9b  mov     [r9+0Eh], cl
0x140034b9f  mov     eax, [r8+rdi+10h]
0x140034ba4  test    al, 20h
0x140034ba6  jz      short loc_140034BBC
0x140034ba8  mov     al, [r9+0Eh]
0x140034bac  mov     cl, al
0x140034bae  xor     cl, [r8+rdi+16h]
0x140034bb3  and     cl, r11b
0x140034bb6  xor     cl, al
0x140034bb8  mov     [r9+0Eh], cl
0x140034bbc  mov     eax, [r8+rdi+10h]
0x140034bc1  test    al, 40h
0x140034bc3  jz      short loc_140034BD9
0x140034bc5  mov     al, [r9+16h]
0x140034bc9  mov     cl, al
0x140034bcb  xor     cl, [r8+rdi+17h]
0x140034bd0  and     cl, r11b
0x140034bd3  xor     cl, al
0x140034bd5  mov     [r9+16h], cl
0x140034bd9  inc     rbx
0x140034bdc  add     r8, 14h
0x140034be0  add     r10, 20h ; ' '
0x140034be4  cmp     rbx, 7
0x140034be8  jnz     loc_140034B07
0x140034bee  jmp     loc_140034CE8
0x140034bf3  xor     r10d, r10d
0x140034bf6  mov     dword ptr [rdx], 0E400084Ah
0x140034bfc  xor     r9d, r9d
0x140034bff  mov     eax, [r8+rdi+10h]
0x140034c04  test    al, 0Eh
0x140034c06  jz      short loc_140034C1E
0x140034c08  mov     al, [r9+rdx+8]
0x140034c0d  mov     cl, al
0x140034c0f  xor     cl, [r8+rdi+14h]
0x140034c14  and     cl, r11b
0x140034c17  xor     cl, al
0x140034c19  mov     [r9+rdx+8], cl
0x140034c1e  mov     eax, [r8+rdi+10h]
0x140034c23  test    al, 2
0x140034c25  jz      short loc_140034C3B
0x140034c27  mov     al, [r8+rdi+18h]
0x140034c2c  mov     [r9+rdx+0Bh], al
0x140034c31  mov     al, [r8+rdi+19h]
0x140034c36  mov     [r9+rdx+0Ah], al
0x140034c3b  mov     eax, [r8+rdi+10h]
0x140034c40  test    al, 4
0x140034c42  jz      short loc_140034C58
0x140034c44  mov     al, [r8+rdi+1Ah]
0x140034c49  mov     [r9+rdx+0Dh], al
0x140034c4e  mov     al, [r8+rdi+1Bh]
0x140034c53  mov     [r9+rdx+0Ch], al
0x140034c58  mov     eax, [r8+rdi+10h]
0x140034c5d  test    al, 8
0x140034c5f  jz      short loc_140034C75
0x140034c61  mov     al, [r8+rdi+1Ch]
0x140034c66  mov     [r9+rdx+13h], al
0x140034c6b  mov     al, [r8+rdi+1Dh]
0x140034c70  mov     [r9+rdx+12h], al
0x140034c75  mov     eax, [r8+rdi+10h]
0x140034c7a  test    al, 10h
0x140034c7c  jz      short loc_140034C95
0x140034c7e  mov     cl, [r8+rdi+15h]
0x140034c83  mov     al, [r9+rdx+0Eh]
0x140034c88  shl     cl, 4
0x140034c8b  and     al, r11b
0x140034c8e  or      cl, al
0x140034c90  mov     [r9+rdx+0Eh], cl
0x140034c95  mov     eax, [r8+rdi+10h]
0x140034c9a  test    al, 20h
0x140034c9c  jz      short loc_140034CB4
0x140034c9e  mov     al, [r9+rdx+0Eh]
0x140034ca3  mov     cl, al
0x140034ca5  xor     cl, [r8+rdi+16h]
0x140034caa  and     cl, r11b
0x140034cad  xor     cl, al
0x140034caf  mov     [r9+rdx+0Eh], cl
0x140034cb4  mov     eax, [r8+rdi+10h]
0x140034cb9  test    al, 40h
0x140034cbb  jz      short loc_140034CD3
0x140034cbd  mov     al, [r9+rdx+16h]
0x140034cc2  mov     cl, al
0x140034cc4  xor     cl, [r8+rdi+17h]
0x140034cc9  and     cl, r11b
0x140034ccc  xor     cl, al
0x140034cce  mov     [r9+rdx+16h], cl
0x140034cd3  inc     r10
0x140034cd6  add     r8, 14h
0x140034cda  add     r9, 20h ; ' '
0x140034cde  cmp     r10, 7
0x140034ce2  jnz     loc_140034BFF
0x140034ce8  mov     r8d, dword ptr [rsp+58h+arg_8]
0x140034ced  mov     r9b, bpl
0x140034cf0  mov     rcx, [r14+8]
0x140034cf4  mov     rdx, rsi
0x140034cf7  call    ClasspModeSelect
0x140034cfc  mov     ebx, eax
0x140034cfe  test    eax, eax
0x140034d00  jns     loc_140034DDA
0x140034d06  jmp     loc_140034D97
0x140034d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d12  lea     rax, WPP_GLOBAL_Control
0x140034d19  cmp     rcx, rax
0x140034d1c  jz      short loc_140034D92
0x140034d1e  test    dword ptr [rcx+2Ch], 20000h
0x140034d25  jz      short loc_140034D92
0x140034d27  cmp     byte ptr [rcx+29h], 2
0x140034d2b  jb      short loc_140034D92
0x140034d2d  movzx   eax, byte ptr [rdx+1]
0x140034d31  mov     r9d, r8d
0x140034d34  mov     rcx, [rcx+18h]
0x140034d38  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034d3f  and     r9d, 3Fh
0x140034d43  mov     dword ptr [rsp+58h+var_38], eax
0x140034d47  mov     edx, 0C6h
0x140034d4c  call    WPP_SF_DD
0x140034d51  jmp     short loc_140034D92
0x140034d53  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d5a  lea     rax, WPP_GLOBAL_Control
0x140034d61  cmp     rcx, rax
0x140034d64  jz      short loc_140034D92
0x140034d66  test    dword ptr [rcx+2Ch], 20000h
0x140034d6d  jz      short loc_140034D92
0x140034d6f  cmp     byte ptr [rcx+29h], 2
0x140034d73  jb      short loc_140034D92
0x140034d75  mov     rcx, [rcx+18h]
0x140034d79  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x140034d80  shr     r9d, 4
0x140034d84  mov     edx, 0C8h
0x140034d89  and     r9d, 3
0x140034d8d  call    WPP_SF_d
0x140034d92  mov     ebx, 0C000000Dh
0x140034d97  cmp     cs:ClassPnPETWEnabled, 0
0x140034d9e  jz      short loc_140034DD5
0x140034da0  movzx   edx, word ptr [rdi]
0x140034da3  xor     r9d, r9d
0x140034da6  mov     al, [rdi]
0x140034da8  mov     cl, dl
0x140034daa  shr     dl, 3
0x140034dad  and     al, 1
0x140034daf  and     dl, 1
0x140034db2  shr     cl, 4
0x140034db5  and     cl, 3
0x140034db8  mov     r8d, ebx
0x140034dbb  mov     [rsp+58h+var_20], cl
0x140034dbf  mov     byte ptr [rsp+58h+var_28], dl
0x140034dc3  mov     rdx, [r14+8]
0x140034dc7  mov     byte ptr [rsp+58h+var_30], bpl
0x140034dcc  mov     byte ptr [rsp+58h+var_38], al
0x140034dd0  call    ClasspCDLModePageOperationFailureEvent
0x140034dd5  test    rsi, rsi
  ... truncated ...
```
