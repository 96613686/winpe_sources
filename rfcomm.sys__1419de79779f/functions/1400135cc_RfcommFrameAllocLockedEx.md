# RfcommFrameAllocLockedEx

- ea: `0x1400135cc`
- end: `0x140013ab4`
- name: `RfcommFrameAllocLockedEx`
- size: `1256`
- prototype: `__int64 __fastcall(__int64, __int64 *, char, char, char, int, unsigned int *, __int64, char)`
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fe48`
- `0x1400149b4`
- `0x140014b10`
- `0x140014c64`
- `0x140014eb4`
- `0x14001513c`
- `0x1400152ec`
- `0x14001552c`
- `0x140015688`
- `0x1400162d0`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004a68`
- `0x140004e58`
- `0x1400135cc`
- `0x14001e74c`
- `0x14001e8f4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400136c9`
- `ntoskrnl!ExAllocatePool2` at `0x140013855`
- `ntoskrnl!ExAllocatePool2` at `0x1400138ff`
- `ntoskrnl!ExAllocatePool2` at `0x1400136c9`
- `ntoskrnl!ExAllocatePool2` at `0x140013855`
- `ntoskrnl!ExAllocatePool2` at `0x1400138ff`

## string_xrefs

- `0x1400139a7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommFrameAllocLockedEx(
        __int64 a1,
        __int64 *a2,
        char a3,
        char a4,
        char a5,
        int a6,
        unsigned int *a7,
        __int64 a8,
        char a9)
{
  __int64 *v10; // r15
  __int64 v12; // rbx
  unsigned int v13; // edi
  char v14; // r13
  int v15; // eax
  unsigned int v16; // esi
  __int64 v17; // rax
  int v18; // edx
  unsigned int v19; // ecx
  _BYTE *v20; // rdx
  unsigned int v21; // r9d
  char v22; // r8
  char v23; // al
  char v24; // r12
  char v25; // al
  _BYTE *v26; // r11
  unsigned __int8 v27; // al
  unsigned __int64 v28; // rcx
  __int64 Pool2; // rax
  unsigned __int8 *v30; // rdx
  char v31; // cl
  char v32; // r8
  unsigned __int8 *v33; // r11
  unsigned __int8 v34; // al
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  char v37; // cl
  unsigned __int8 v38; // al
  char v39; // cl
  char v40; // r8
  unsigned __int8 *v41; // r11
  unsigned __int64 v42; // rcx

  v10 = a2;
  v12 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      45,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  if ( *(_DWORD *)(a1 + 48) == 6 || v10 && *((_DWORD *)v10 + 12) == 9 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v12;
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      46,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1,
      (char)v10);
    goto LABEL_52;
  }
  switch ( a3 )
  {
    case 15:
      goto LABEL_39;
    case 47:
    case 67:
      Pool2 = ExAllocatePool2(64, 156, 1380345426);
      v12 = Pool2;
      if ( !Pool2 )
        break;
      *(_DWORD *)(Pool2 + 136) = 1;
      v30 = (unsigned __int8 *)(Pool2 + 152);
      *(_BYTE *)(Pool2 + 140) = -1;
      v21 = 4;
      *(_DWORD *)(Pool2 + 52) = 4;
      *(_DWORD *)(Pool2 + 48) = 156;
      *(_DWORD *)(Pool2 + 16) = 1296126534;
      *(_BYTE *)(Pool2 + 152) |= 1u;
      v31 = *(_BYTE *)(Pool2 + 152);
      if ( *(_BYTE *)(a1 + 272) )
        v31 |= 2u;
      v32 = 3;
      *(_BYTE *)(Pool2 + 154) = 1;
      *v30 = v31 | (4 * a5);
      *(_BYTE *)(Pool2 + 153) = a3 | 0x10;
      v33 = (unsigned __int8 *)(Pool2 + 152);
      v34 = -1;
      do
      {
        v35 = *v33++;
        v34 = *((_BYTE *)crctable + (v34 ^ v35));
        --v32;
      }
      while ( v32 );
      goto LABEL_46;
    case 99:
LABEL_39:
      v36 = ExAllocatePool2(64, 156, 1380345426);
      v12 = v36;
      if ( !v36 )
        break;
      *(_DWORD *)(v36 + 48) = 156;
      v30 = (unsigned __int8 *)(v36 + 152);
      *(_DWORD *)(v36 + 16) = 1296126534;
      *(_DWORD *)(v36 + 136) = 2;
      v21 = 4;
      *(_DWORD *)(v36 + 52) = 4;
      *(_BYTE *)(v36 + 152) |= 1u;
      v37 = *(_BYTE *)(v36 + 152);
      if ( !*(_BYTE *)(a1 + 272) )
        v37 |= 2u;
      v38 = v37 | (4 * a5);
      v39 = 16;
      *v30 = v38;
      if ( a3 != 99 )
        v39 = a9 != 0 ? 0x10 : 0;
      v30[2] = 1;
      v30[1] = a3 | v39;
      v40 = 3;
      v41 = v30;
      v34 = -1;
      do
      {
        v42 = *v41++;
        v34 = *((_BYTE *)crctable + (v34 ^ v42));
        --v40;
      }
      while ( v40 );
LABEL_46:
      v30[3] = ~v34;
LABEL_47:
      *a7 = v21;
      RefObj_AddRefEx(a1 + 24, 1296126534, 2278, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      *(_QWORD *)(v12 + 72) = a1;
      if ( v10 )
      {
        RefObj_AddRefEx(v10 + 3, 1296126534, 2283, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
        *(_QWORD *)(v12 + 72) = v10;
      }
      RefObj_InitEx(
        v12 + 24,
        (unsigned int)FrameFree,
        541803329,
        2295,
        (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      a2 = *(__int64 **)(a8 + 8);
      if ( *a2 != a8 )
        __fastfail(3u);
      *(_QWORD *)v12 = a8;
      *(_QWORD *)(v12 + 8) = a2;
      *a2 = v12;
      *(_QWORD *)(a8 + 8) = v12;
      break;
    case -17:
      v13 = *a7;
      v14 = 0;
      v15 = 157 - (*a7 < 0x80);
      if ( a5 && *(_BYTE *)(a1 + 465) )
      {
        v14 = 1;
        ++v15;
      }
      if ( v13 > 0x7FFF )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v12;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          47,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          *a7);
        break;
      }
      v16 = v13 + v15;
      v17 = ExAllocatePool2(64, v13 + v15, 1380345426);
      v12 = v17;
      if ( v17 )
      {
        if ( a5 )
        {
          *(_DWORD *)(v17 + 136) = 3;
        }
        else
        {
          *(_DWORD *)(v17 + 136) = 5 - (a6 != 1);
          *(_BYTE *)(v17 + 140) = a4;
        }
        v19 = *a7;
        v20 = (_BYTE *)(v17 + 152);
        *(_DWORD *)(v17 + 48) = v16;
        v21 = v16 - 152;
        *(_DWORD *)(v17 + 16) = 1296126534;
        *(_DWORD *)(v17 + 52) = v16 - 152;
        *(_DWORD *)(v17 + 56) = v19;
        v22 = 2;
        *(_QWORD *)(v17 + 144) = v17 + 156LL - (v13 < 0x80);
        *(_BYTE *)(v17 + 152) |= 1u;
        v23 = *(_BYTE *)(v17 + 152);
        if ( *(_BYTE *)(a1 + 272) )
          v23 |= 2u;
        v24 = v23 | (4 * a5);
        *(_BYTE *)(v12 + 153) = -17;
        v25 = 2 * *(_BYTE *)a7;
        *v20 = v24;
        *(_BYTE *)(v12 + 154) = v25;
        if ( v13 >= 0x80 )
          *(_BYTE *)(v12 + 155) = v19 >> 7;
        else
          *(_BYTE *)(v12 + 154) = v25 | 1;
        v26 = &v20[v21];
        if ( v14 )
        {
          ++*(_QWORD *)(v12 + 144);
          *(_BYTE *)(v12 + 153) |= 0x10u;
        }
        v27 = -1;
        do
        {
          v28 = (unsigned __int8)*v20++;
          v27 = *((_BYTE *)crctable + (v27 ^ v28));
          --v22;
        }
        while ( v22 );
        *(v26 - 1) = ~v27;
        goto LABEL_47;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        1,
        48,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        v16);
      break;
  }
LABEL_52:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      49,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v12);
  return v12;
}

```

## disassembly

```asm
0x1400135cc  mov     [rsp+arg_18], r9b
0x1400135d1  push    rbx
0x1400135d2  push    rbp
0x1400135d3  push    rsi
0x1400135d4  push    rdi
0x1400135d5  push    r12
0x1400135d7  push    r13
0x1400135d9  push    r14
0x1400135db  push    r15
0x1400135dd  sub     rsp, 48h
0x1400135e1  mov     dil, r8b
0x1400135e4  mov     r15, rdx
0x1400135e7  mov     rbp, rcx
0x1400135ea  xor     ebx, ebx
0x1400135ec  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400135f3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400135fa  lea     rsi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013601  jz      short loc_140013627
0x140013603  mov     rcx, cs:WPP_GLOBAL_Control
0x14001360a  lea     r9d, [rbx+2Dh]
0x14001360e  lea     r8d, [rbx+3]
0x140013612  mov     [rsp+88h+var_68], rsi
0x140013617  mov     rcx, [rcx+40h]
0x14001361b  call    WPP_RECORDER_SF_
0x140013620  lea     rcx, WPP_RECORDER_INITIALIZED
0x140013627  cmp     dword ptr [rbp+30h], 6
0x14001362b  jz      loc_140013A80
0x140013631  test    r15, r15
0x140013634  jz      short loc_140013641
0x140013636  cmp     dword ptr [r15+30h], 9
0x14001363b  jz      loc_140013A80
0x140013641  mov     r14, [rsp+88h+arg_30]
0x140013649  cmp     dil, 0Fh
0x14001364d  jz      loc_1400138EF
0x140013653  mov     r9d, 2Fh ; '/'
0x140013659  cmp     dil, r9b
0x14001365c  jz      loc_140013845
0x140013662  cmp     dil, 43h ; 'C'
0x140013666  jz      loc_140013845
0x14001366c  cmp     dil, 63h ; 'c'
0x140013670  jz      loc_1400138EF
0x140013676  cmp     dil, 0EFh
0x14001367a  jnz     loc_140013A37
0x140013680  mov     edi, [r14]
0x140013683  xor     r13b, r13b
0x140013686  mov     r12b, [rsp+88h+arg_20]
0x14001368e  cmp     edi, 80h
0x140013694  sbb     eax, eax
0x140013696  add     eax, 9Dh
0x14001369b  test    r12b, r12b
0x14001369e  jz      short loc_1400136AD
0x1400136a0  cmp     [rbp+1D1h], bl
0x1400136a6  jz      short loc_1400136AD
0x1400136a8  mov     r13b, 1
0x1400136ab  inc     eax
0x1400136ad  cmp     edi, 7FFFh
0x1400136b3  ja      loc_140013814
0x1400136b9  lea     esi, [rdi+rax]
0x1400136bc  mov     ecx, 40h ; '@'
0x1400136c1  mov     edx, esi
0x1400136c3  mov     r8d, 52466652h
0x1400136c9  call    cs:__imp_ExAllocatePool2
0x1400136d0  nop     dword ptr [rax+rax+00h]
0x1400136d5  mov     rbx, rax
0x1400136d8  test    rax, rax
0x1400136db  jz      loc_1400137D1
0x1400136e1  test    r12b, r12b
0x1400136e4  jnz     short loc_14001370B
0x1400136e6  mov     ecx, [rsp+88h+arg_28]
0x1400136ed  dec     ecx
0x1400136ef  neg     ecx
0x1400136f1  sbb     eax, eax
0x1400136f3  add     eax, 5
0x1400136f6  mov     [rbx+88h], eax
0x1400136fc  mov     al, [rsp+88h+arg_18]
0x140013703  mov     [rbx+8Ch], al
0x140013709  jmp     short loc_140013715
0x14001370b  mov     dword ptr [rax+88h], 3
0x140013715  mov     ecx, [r14]
0x140013718  lea     rdx, [rbx+98h]
0x14001371f  mov     [rbx+30h], esi
0x140013722  lea     r9d, [rsi-98h]
0x140013729  mov     dword ptr [rbx+10h], 4D415246h
0x140013730  mov     r10d, 80h
0x140013736  mov     [rbx+34h], r9d
0x14001373a  cmp     edi, r10d
0x14001373d  mov     [rbx+38h], ecx
0x140013740  sbb     rax, rax
0x140013743  add     rax, 9Ch
0x140013749  lea     r8d, [r10-7Eh]
0x14001374d  add     rax, rbx
0x140013750  mov     [rbx+90h], rax
0x140013757  or      byte ptr [rdx], 1
0x14001375a  cmp     byte ptr [rbp+110h], 0
0x140013761  mov     al, [rdx]
0x140013763  jz      short loc_140013768
0x140013765  or      al, r8b
0x140013768  shl     r12b, 2
0x14001376c  or      r12b, al
0x14001376f  mov     byte ptr [rdx+1], 0EFh
0x140013773  mov     al, [r14]
0x140013776  add     al, al
0x140013778  mov     [rdx], r12b
0x14001377b  mov     [rdx+2], al
0x14001377e  cmp     edi, r10d
0x140013781  jnb     short loc_14001378A
0x140013783  or      al, 1
0x140013785  mov     [rdx+2], al
0x140013788  jmp     short loc_140013790
0x14001378a  shr     ecx, 7
0x14001378d  mov     [rdx+3], cl
0x140013790  mov     r11d, r9d
0x140013793  add     r11, rdx
0x140013796  test    r13b, r13b
0x140013799  jz      short loc_1400137A7
0x14001379b  inc     qword ptr [rbx+90h]
0x1400137a2  mov     cl, 10h
0x1400137a4  or      [rdx+1], cl
0x1400137a7  mov     al, 0FFh
0x1400137a9  lea     r10, crctable
0x1400137b0  movzx   ecx, byte ptr [rdx]
0x1400137b3  inc     rdx
0x1400137b6  movzx   eax, al
0x1400137b9  xor     rcx, rax
0x1400137bc  mov     al, [rcx+r10]
0x1400137c0  add     r8b, 0FFh
0x1400137c4  jnz     short loc_1400137B0
0x1400137c6  not     al
0x1400137c8  mov     [r11-1], al
0x1400137cc  jmp     loc_1400139A4
0x1400137d1  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400137d8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400137df  jz      loc_140013A6B
0x1400137e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137ec  mov     r9d, 30h ; '0'
0x1400137f2  mov     dword ptr [rsp+88h+var_60], esi
0x1400137f6  lea     rsi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400137fd  mov     [rsp+88h+var_68], rsi
0x140013802  mov     rcx, [rcx+40h]
0x140013806  lea     r8d, [r9-2Fh]
0x14001380a  call    WPP_RECORDER_SF_d
0x14001380f  jmp     loc_140013A3E
0x140013814  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001381b  jz      loc_140013A6B
0x140013821  mov     rcx, cs:WPP_GLOBAL_Control
0x140013828  mov     r8d, 1
0x14001382e  mov     dword ptr [rsp+88h+var_60], edi
0x140013832  mov     [rsp+88h+var_68], rsi
0x140013837  mov     rcx, [rcx+40h]
0x14001383b  call    WPP_RECORDER_SF_d
0x140013840  jmp     loc_140013A37
0x140013845  mov     esi, 9Ch
0x14001384a  mov     r8d, 52466652h
0x140013850  mov     edx, esi
0x140013852  lea     ecx, [rsi-5Ch]
0x140013855  call    cs:__imp_ExAllocatePool2
0x14001385c  nop     dword ptr [rax+rax+00h]
0x140013861  mov     rbx, rax
0x140013864  test    rax, rax
0x140013867  jz      loc_140013A30
0x14001386d  mov     dword ptr [rax+88h], 1
0x140013877  lea     rdx, [rax+98h]
0x14001387e  mov     byte ptr [rax+8Ch], 0FFh
0x140013885  mov     r9d, 4
0x14001388b  mov     [rax+34h], r9d
0x14001388f  mov     [rax+30h], esi
0x140013892  mov     dword ptr [rax+10h], 4D415246h
0x140013899  or      byte ptr [rdx], 1
0x14001389c  cmp     byte ptr [rbp+110h], 0
0x1400138a3  mov     cl, [rdx]
0x1400138a5  jz      short loc_1400138AA
0x1400138a7  or      cl, 2
0x1400138aa  mov     al, [rsp+88h+arg_20]
0x1400138b1  lea     r10, crctable
0x1400138b8  shl     al, 2
0x1400138bb  mov     r8b, 3
0x1400138be  or      al, cl
0x1400138c0  mov     byte ptr [rdx+2], 1
0x1400138c4  or      dil, 10h
0x1400138c8  mov     [rdx], al
0x1400138ca  mov     [rdx+1], dil
0x1400138ce  mov     r11, rdx
0x1400138d1  mov     al, 0FFh
0x1400138d3  movzx   ecx, byte ptr [r11]
0x1400138d7  inc     r11
0x1400138da  movzx   eax, al
0x1400138dd  xor     rcx, rax
0x1400138e0  mov     al, [rcx+r10]
0x1400138e4  add     r8b, 0FFh
0x1400138e8  jnz     short loc_1400138D3
0x1400138ea  jmp     loc_14001399F
0x1400138ef  mov     esi, 9Ch
0x1400138f4  mov     r8d, 52466652h
0x1400138fa  mov     edx, esi
0x1400138fc  lea     ecx, [rsi-5Ch]
0x1400138ff  call    cs:__imp_ExAllocatePool2
0x140013906  nop     dword ptr [rax+rax+00h]
0x14001390b  mov     rbx, rax
0x14001390e  test    rax, rax
0x140013911  jz      loc_140013A30
0x140013917  mov     [rax+30h], esi
0x14001391a  lea     rdx, [rax+98h]
0x140013921  mov     dword ptr [rax+10h], 4D415246h
0x140013928  mov     r8d, 2
0x14001392e  mov     [rax+88h], r8d
0x140013935  lea     r9d, [r8+2]
0x140013939  mov     [rax+34h], r9d
0x14001393d  or      byte ptr [rdx], 1
0x140013940  cmp     byte ptr [rbp+110h], 0
0x140013947  mov     cl, [rdx]
0x140013949  jnz     short loc_14001394E
0x14001394b  or      cl, r8b
0x14001394e  mov     al, [rsp+88h+arg_20]
0x140013955  shl     al, 2
0x140013958  or      al, cl
0x14001395a  mov     cl, 10h
0x14001395c  mov     [rdx], al
0x14001395e  cmp     dil, 63h ; 'c'
0x140013962  jz      short loc_14001396F
0x140013964  neg     [rsp+88h+arg_40]
0x14001396b  sbb     al, al
0x14001396d  and     cl, al
0x14001396f  or      cl, dil
0x140013972  mov     byte ptr [rdx+2], 1
0x140013976  mov     [rdx+1], cl
0x140013979  lea     r10, crctable
0x140013980  mov     r8b, 3
0x140013983  mov     r11, rdx
0x140013986  mov     al, 0FFh
0x140013988  movzx   ecx, byte ptr [r11]
0x14001398c  inc     r11
0x14001398f  movzx   eax, al
0x140013992  xor     rcx, rax
0x140013995  mov     al, [rcx+r10]
0x140013999  add     r8b, 0FFh
0x14001399d  jnz     short loc_140013988
0x14001399f  not     al
0x1400139a1  mov     [rdx+3], al
0x1400139a4  mov     [r14], r9d
0x1400139a7  lea     rdi, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400139ae  mov     r9, rdi
0x1400139b1  lea     rcx, [rbp+18h]
0x1400139b5  mov     edx, 4D415246h
0x1400139ba  mov     r8d, 8E6h
0x1400139c0  call    RefObj_AddRefEx
0x1400139c5  mov     [rbx+48h], rbp
0x1400139c9  test    r15, r15
0x1400139cc  jz      short loc_1400139E9
0x1400139ce  lea     rcx, [r15+18h]
0x1400139d2  mov     r9, rdi
0x1400139d5  mov     edx, 4D415246h
0x1400139da  mov     r8d, 8EBh
0x1400139e0  call    RefObj_AddRefEx
0x1400139e5  mov     [rbx+48h], r15
0x1400139e9  lea     rcx, [rbx+18h]
0x1400139ed  mov     [rsp+88h+var_68], rdi
0x1400139f2  mov     r9d, 8F7h
0x1400139f8  lea     rdx, FrameFree
0x1400139ff  mov     r8d, 204B4341h
0x140013a05  call    RefObj_InitEx
0x140013a0a  mov     rax, [rsp+88h+arg_38]
0x140013a12  mov     rdx, [rax+8]
0x140013a16  cmp     [rdx], rax
0x140013a19  jz      short loc_140013A22
0x140013a1b  mov     ecx, 3
0x140013a20  int     29h; Win8: RtlFailFast(ecx)
0x140013a22  mov     [rbx], rax
0x140013a25  mov     [rbx+8], rdx
0x140013a29  mov     [rdx], rbx
0x140013a2c  mov     [rax+8], rbx
0x140013a30  lea     rsi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013a37  lea     rdi, WPP_RECORDER_INITIALIZED
0x140013a3e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140013a45  jz      short loc_140013A6B
0x140013a47  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a4e  mov     r9d, 31h ; '1'
0x140013a54  mov     [rsp+88h+var_60], rbx
0x140013a59  mov     [rsp+88h+var_68], rsi
0x140013a5e  mov     rcx, [rcx+40h]
0x140013a62  lea     r8d, [r9-2Eh]
0x140013a66  call    WPP_RECORDER_SF_q
0x140013a6b  mov     rax, rbx
0x140013a6e  add     rsp, 48h
0x140013a72  pop     r15
0x140013a74  pop     r14
0x140013a76  pop     r13
0x140013a78  pop     r12
0x140013a7a  pop     rdi
0x140013a7b  pop     rsi
0x140013a7c  pop     rbp
0x140013a7d  pop     rbx
0x140013a7e  retn
0x140013a80  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140013a87  jz      short loc_140013A6B
0x140013a89  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a90  mov     r9d, 2Eh ; '.'
0x140013a96  mov     [rsp+88h+var_58], r15
0x140013a9b  mov     [rsp+88h+var_60], rbp
0x140013aa0  mov     [rsp+88h+var_68], rsi
0x140013aa5  mov     rcx, [rcx+40h]
  ... truncated ...
```
