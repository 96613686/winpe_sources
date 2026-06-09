# ClasspSetupReceiveWriteUsingTokenInformationTransferPacket

- ea: `0x140021274`
- end: `0x140021704`
- name: `ClasspSetupReceiveWriteUsingTokenInformationTransferPacket`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140020ef4`

## callees

- `0x140021274`
- `0x140022668`
- `0x14003e640`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ClasspSetupReceiveWriteUsingTokenInformationTransferPacket(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  char v15; // r11
  __int64 v16; // r10
  __int64 v17; // rcx
  unsigned __int64 v18; // r9
  __int64 v19; // r8
  int v20; // ecx
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r10
  char v26; // di
  __int64 i; // r11
  __int64 v28; // rcx
  unsigned __int64 v29; // r9
  __int64 v30; // r8
  int v31; // ecx
  int v32; // ecx
  __int64 v33; // rdx
  char v34; // r11
  __int64 v35; // r10
  __int64 v36; // rcx
  unsigned __int64 v37; // r9
  __int64 v38; // r8
  int v39; // ecx
  int v40; // ecx
  __int64 v41; // rax
  int v42; // ecx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rdx
  _BYTE *v48; // r8
  unsigned int v49; // edi
  __int64 v50; // r11
  char v51; // si
  __int64 v52; // rcx
  unsigned __int64 v53; // r10
  __int64 v54; // r9
  int v55; // ecx
  int v56; // ecx
  _BYTE *v57; // rcx
  char v58; // al
  PDEVICE_OBJECT *result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids,
      *(_QWORD *)(a2 + 40),
      a5);
  }
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 64LL);
  v11 = *(_DWORD **)(*(_QWORD *)(v10 + 1144) + 688LL);
  if ( *(_BYTE *)(*(_QWORD *)(v10 + 528) + 30LL) == 1 )
    v12 = v11[4];
  else
    v12 = *(unsigned __int16 *)v11;
  memmove(*(void **)(a2 + 288), v11, v12);
  v13 = *(_QWORD *)(a2 + 288);
  if ( *(_BYTE *)(v13 + 2) == 40 )
    *(_WORD *)(v13 + 38) = 32;
  else
    *(_BYTE *)(v13 + 9) = 32;
  v14 = *(_QWORD *)(a2 + 288);
  if ( *(_BYTE *)(v14 + 2) == 40 )
  {
    if ( *(_DWORD *)(v14 + 20) )
      goto LABEL_29;
    v15 = 0;
    v16 = 0;
    if ( !*(_DWORD *)(v14 + 56) )
      goto LABEL_29;
    while ( 1 )
    {
      v17 = *(unsigned int *)(v14 + 4 * v16 + 120);
      if ( (unsigned int)v17 >= 0x80 )
      {
        v18 = *(unsigned int *)(v14 + 16);
        if ( (unsigned int)v17 < (unsigned int)v18 )
        {
          v19 = (unsigned int)v17;
          v20 = *(_DWORD *)(v17 + v14) - 64;
          if ( v20 )
          {
            v21 = v20 - 1;
            if ( v21 )
            {
              if ( v21 == 1 && v19 + 40 <= v18 )
                goto LABEL_29;
            }
            else if ( v19 + 56 <= v18 )
            {
              v15 = 1;
              *(_BYTE *)(v19 + v14 + 10) = 16;
            }
          }
          else if ( v19 + 40 <= v18 )
          {
            *(_BYTE *)(v19 + v14 + 10) = 16;
            goto LABEL_29;
          }
          if ( v15 )
            goto LABEL_29;
        }
      }
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= *(_DWORD *)(v14 + 56) )
        goto LABEL_29;
    }
  }
  *(_BYTE *)(v14 + 10) = 16;
LABEL_29:
  v22 = *(_QWORD *)(a2 + 288);
  v23 = *(_QWORD *)(a2 + 32);
  if ( *(_BYTE *)(v22 + 2) == 40 )
    *(_QWORD *)(v22 + 80) = v23;
  else
    *(_QWORD *)(v22 + 48) = v23;
  v24 = *(_QWORD *)(a2 + 288);
  v25 = a2 + 264;
  if ( *(_BYTE *)(v24 + 2) == 40 )
  {
    if ( !*(_DWORD *)(v24 + 20) )
    {
      v26 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v24 + 56); i = (unsigned int)(i + 1) )
      {
        v28 = *(unsigned int *)(v24 + 4 * i + 120);
        if ( (unsigned int)v28 >= 0x80 )
        {
          v29 = *(unsigned int *)(v24 + 16);
          if ( (unsigned int)v28 < (unsigned int)v29 )
          {
            v30 = (unsigned int)v28;
            v31 = *(_DWORD *)(v28 + v24) - 64;
            if ( v31 )
            {
              v32 = v31 - 1;
              if ( v32 )
              {
                if ( v32 == 1 && v30 + 40 <= v29 )
                {
                  *(_QWORD *)(v30 + v24 + 24) = v25;
                  break;
                }
              }
              else if ( v30 + 56 <= v29 )
              {
                v26 = 1;
                *(_QWORD *)(v30 + v24 + 16) = v25;
              }
            }
            else if ( v30 + 40 <= v29 )
            {
              *(_QWORD *)(v30 + v24 + 16) = v25;
              break;
            }
            if ( v26 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_QWORD *)(v24 + 32) = v25;
  }
  v33 = *(_QWORD *)(a2 + 288);
  if ( *(_BYTE *)(v33 + 2) == 40 )
  {
    if ( *(_DWORD *)(v33 + 20) )
      goto LABEL_66;
    v34 = 0;
    v35 = 0;
    if ( !*(_DWORD *)(v33 + 56) )
      goto LABEL_66;
    while ( 1 )
    {
      v36 = *(unsigned int *)(v33 + 4 * v35 + 120);
      if ( (unsigned int)v36 >= 0x80 )
      {
        v37 = *(unsigned int *)(v33 + 16);
        if ( (unsigned int)v36 < (unsigned int)v37 )
          break;
      }
LABEL_60:
      v35 = (unsigned int)(v35 + 1);
      if ( (unsigned int)v35 >= *(_DWORD *)(v33 + 56) )
        goto LABEL_66;
    }
    v38 = (unsigned int)v36;
    v39 = *(_DWORD *)(v36 + v33) - 64;
    if ( !v39 )
      goto LABEL_58;
    v40 = v39 - 1;
    if ( v40 )
    {
      if ( v40 == 1 )
      {
LABEL_58:
        if ( v38 + 40 <= v37 )
        {
          *(_BYTE *)(v38 + v33 + 9) = 18;
          goto LABEL_66;
        }
      }
    }
    else if ( v38 + 56 <= v37 )
    {
      v34 = 1;
      *(_BYTE *)(v38 + v33 + 9) = 18;
    }
    if ( v34 )
      goto LABEL_66;
    goto LABEL_60;
  }
  *(_BYTE *)(v33 + 11) = 18;
LABEL_66:
  v41 = *(_QWORD *)(a2 + 288);
  v42 = *(_DWORD *)(v10 + 584);
  if ( *(_BYTE *)(v41 + 2) == 40 )
    *(_DWORD *)(v41 + 40) = v42;
  else
    *(_DWORD *)(v41 + 20) = v42;
  v43 = *(_QWORD *)(a2 + 288);
  if ( *(_BYTE *)(v43 + 2) == 40 )
    *(_QWORD *)(v43 + 64) = a4;
  else
    *(_QWORD *)(v43 + 24) = a4;
  v44 = *(_QWORD *)(a2 + 288);
  if ( *(_BYTE *)(v44 + 2) == 40 )
    *(_DWORD *)(v44 + 60) = a3;
  else
    *(_DWORD *)(v44 + 16) = a3;
  v45 = *(_QWORD *)(a2 + 288);
  v46 = *(_DWORD *)(v10 + 592) | 0x148;
  if ( *(_BYTE *)(v45 + 2) == 40 )
    *(_DWORD *)(v45 + 24) = v46;
  else
    *(_DWORD *)(v45 + 12) = v46;
  v47 = *(_QWORD *)(a2 + 288);
  if ( *(_BYTE *)(v47 + 2) != 40 )
  {
    v48 = (_BYTE *)(v47 + 72);
    goto LABEL_101;
  }
  v48 = 0;
  if ( !*(_DWORD *)(v47 + 20) )
  {
    v49 = *(_DWORD *)(v47 + 56);
    if ( v49 )
    {
      v50 = 0;
      v51 = 0;
      do
      {
        v52 = *(unsigned int *)(v47 + 4 * v50 + 120);
        if ( (unsigned int)v52 >= 0x80 )
        {
          v53 = *(unsigned int *)(v47 + 16);
          if ( (unsigned int)v52 < (unsigned int)v53 )
          {
            v54 = (unsigned int)v52;
            v55 = *(_DWORD *)(v52 + v47) - 64;
            if ( v55 )
            {
              v56 = v55 - 1;
              if ( v56 )
              {
                if ( v56 == 1 && v54 + 40 <= v53 )
                {
                  v57 = (_BYTE *)(v54 + v47 + 32);
                  if ( !*(_DWORD *)(v54 + v47 + 12) )
                    v57 = v48;
                  v48 = v57;
                  break;
                }
              }
              else if ( v54 + 56 <= v53 )
              {
                if ( !*(_BYTE *)(v54 + v47 + 10) )
                  break;
                v51 = 1;
                v48 = (_BYTE *)(v54 + v47 + 24);
              }
            }
            else if ( v54 + 40 <= v53 )
            {
              if ( *(_BYTE *)(v54 + v47 + 10) )
                v48 = (_BYTE *)(v54 + v47 + 24);
              break;
            }
            if ( v51 )
              break;
          }
        }
        v50 = (unsigned int)(v50 + 1);
      }
      while ( (unsigned int)v50 < v49 );
    }
  }
LABEL_101:
  if ( v48 )
  {
    v58 = v48[1] & 0xE7;
    *v48 = -124;
    v48[13] = a3;
    v48[1] = v58 | 7;
    v48[12] = BYTE1(a3);
    v48[11] = BYTE2(a3);
    v48[10] = HIBYTE(a3);
    v48[5] = a6;
    v48[4] = BYTE1(a6);
    v48[3] = BYTE2(a6);
    v48[2] = HIBYTE(a6);
  }
  *(_QWORD *)(a2 + 240) = a4;
  *(_QWORD *)(a2 + 344) = ClasspReceiveWriteUsingTokenInformationTransferPacketDone;
  *(_DWORD *)(a2 + 248) = a3;
  *(_QWORD *)(a2 + 48) = a5;
  *(_WORD *)(a2 + 56) = 512;
  *(_QWORD *)(a2 + 352) = a1;
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return (PDEVICE_OBJECT *)WPP_SF_qq(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 26,
                                 WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids,
                                 *(_QWORD *)(a2 + 40),
                                 a5);
  }
  return result;
}

```

## disassembly

```asm
0x140021274  mov     r11, rsp
0x140021277  mov     [r11+8], rbx
0x14002127b  mov     [r11+10h], rbp
0x14002127f  mov     [r11+18h], r8d
0x140021283  push    rsi
0x140021284  push    rdi
0x140021285  push    r12
0x140021287  push    r14
0x140021289  push    r15
0x14002128b  sub     rsp, 30h
0x14002128f  mov     r15, r9
0x140021292  mov     ebp, r8d
0x140021295  mov     rbx, rdx
0x140021298  mov     r12, rcx
0x14002129b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212a2  lea     rax, WPP_GLOBAL_Control
0x1400212a9  mov     r14, [rsp+58h+arg_20]
0x1400212b1  cmp     rcx, rax
0x1400212b4  jz      short loc_1400212E0
0x1400212b6  mov     eax, [rcx+2Ch]
0x1400212b9  test    al, 10h
0x1400212bb  jz      short loc_1400212E0
0x1400212bd  cmp     byte ptr [rcx+29h], 5
0x1400212c1  jb      short loc_1400212E0
0x1400212c3  mov     r9, [rbx+28h]
0x1400212c7  lea     r8, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids
0x1400212ce  mov     rcx, [rcx+18h]
0x1400212d2  mov     edx, 19h
0x1400212d7  mov     [r11-38h], r14
0x1400212db  call    WPP_SF_qq
0x1400212e0  mov     rax, [rbx+28h]
0x1400212e4  mov     rsi, [rax+40h]
0x1400212e8  mov     rax, [rsi+478h]
0x1400212ef  mov     rdx, [rax+2B0h]; Src
0x1400212f6  mov     rax, [rsi+210h]
0x1400212fd  cmp     byte ptr [rax+1Eh], 1
0x140021301  jnz     short loc_140021308
0x140021303  mov     eax, [rdx+10h]
0x140021306  jmp     short loc_14002130B
0x140021308  movzx   eax, word ptr [rdx]
0x14002130b  mov     rcx, [rbx+120h]; void *
0x140021312  mov     r8d, eax; Size
0x140021315  call    memmove
0x14002131a  mov     rcx, [rbx+120h]
0x140021321  cmp     byte ptr [rcx+2], 28h ; '('
0x140021325  jnz     short loc_14002132F
0x140021327  mov     word ptr [rcx+26h], 20h ; ' '
0x14002132d  jmp     short loc_140021333
0x14002132f  mov     byte ptr [rcx+9], 20h ; ' '
0x140021333  mov     rdx, [rbx+120h]
0x14002133a  cmp     byte ptr [rdx+2], 28h ; '('
0x14002133e  jnz     short loc_1400213BD
0x140021340  cmp     dword ptr [rdx+14h], 0
0x140021344  jnz     short loc_1400213C1
0x140021346  xor     r11b, r11b
0x140021349  xor     r10d, r10d
0x14002134c  cmp     [rdx+38h], r10d
0x140021350  jbe     short loc_1400213C1
0x140021352  mov     ecx, [rdx+r10*4+78h]
0x140021357  cmp     ecx, 80h
0x14002135d  jb      short loc_1400213AA
0x14002135f  mov     r9d, [rdx+10h]
0x140021363  cmp     ecx, r9d
0x140021366  jnb     short loc_1400213AA
0x140021368  mov     r8d, ecx
0x14002136b  mov     ecx, [rcx+rdx]
0x14002136e  sub     ecx, 40h ; '@'
0x140021371  jz      short loc_14002139C
0x140021373  sub     ecx, 1
0x140021376  jz      short loc_140021388
0x140021378  cmp     ecx, 1
0x14002137b  jnz     short loc_1400213A5
0x14002137d  lea     rcx, [r8+28h]
0x140021381  cmp     rcx, r9
0x140021384  jbe     short loc_1400213C1
0x140021386  jmp     short loc_1400213A5
0x140021388  lea     rcx, [r8+38h]
0x14002138c  cmp     rcx, r9
0x14002138f  ja      short loc_1400213A5
0x140021391  mov     r11b, 1
0x140021394  mov     byte ptr [r8+rdx+0Ah], 10h
0x14002139a  jmp     short loc_1400213A5
0x14002139c  lea     rcx, [r8+28h]
0x1400213a0  cmp     rcx, r9
0x1400213a3  jbe     short loc_1400213B5
0x1400213a5  test    r11b, r11b
0x1400213a8  jnz     short loc_1400213C1
0x1400213aa  inc     r10d
0x1400213ad  cmp     r10d, [rdx+38h]
0x1400213b1  jb      short loc_140021352
0x1400213b3  jmp     short loc_1400213C1
0x1400213b5  mov     byte ptr [r8+rdx+0Ah], 10h
0x1400213bb  jmp     short loc_1400213C1
0x1400213bd  mov     byte ptr [rdx+0Ah], 10h
0x1400213c1  mov     rax, [rbx+120h]
0x1400213c8  mov     rcx, [rbx+20h]
0x1400213cc  cmp     byte ptr [rax+2], 28h ; '('
0x1400213d0  jnz     short loc_1400213D8
0x1400213d2  mov     [rax+50h], rcx
0x1400213d6  jmp     short loc_1400213DC
0x1400213d8  mov     [rax+30h], rcx
0x1400213dc  mov     rdx, [rbx+120h]
0x1400213e3  lea     r10, [rbx+108h]
0x1400213ea  cmp     byte ptr [rdx+2], 28h ; '('
0x1400213ee  jnz     loc_140021474
0x1400213f4  cmp     dword ptr [rdx+14h], 0
0x1400213f8  jnz     short loc_140021478
0x1400213fa  xor     dil, dil
0x1400213fd  xor     r11d, r11d
0x140021400  cmp     [rdx+38h], r11d
0x140021404  jbe     short loc_140021478
0x140021406  mov     ecx, [rdx+r11*4+78h]
0x14002140b  cmp     ecx, 80h
0x140021411  jb      short loc_140021462
0x140021413  mov     r9d, [rdx+10h]
0x140021417  cmp     ecx, r9d
0x14002141a  jnb     short loc_140021462
0x14002141c  mov     r8d, ecx
0x14002141f  mov     ecx, [rcx+rdx]
0x140021422  sub     ecx, 40h ; '@'
0x140021425  jz      short loc_140021454
0x140021427  sub     ecx, 1
0x14002142a  jz      short loc_140021441
0x14002142c  cmp     ecx, 1
0x14002142f  jnz     short loc_14002145D
0x140021431  lea     rcx, [r8+28h]
0x140021435  cmp     rcx, r9
0x140021438  ja      short loc_14002145D
0x14002143a  mov     [r8+rdx+18h], r10
0x14002143f  jmp     short loc_140021478
0x140021441  lea     rcx, [r8+38h]
0x140021445  cmp     rcx, r9
0x140021448  ja      short loc_14002145D
0x14002144a  mov     dil, 1
0x14002144d  mov     [r8+rdx+10h], r10
0x140021452  jmp     short loc_14002145D
0x140021454  lea     rcx, [r8+28h]
0x140021458  cmp     rcx, r9
0x14002145b  jbe     short loc_14002146D
0x14002145d  test    dil, dil
0x140021460  jnz     short loc_140021478
0x140021462  inc     r11d
0x140021465  cmp     r11d, [rdx+38h]
0x140021469  jb      short loc_140021406
0x14002146b  jmp     short loc_140021478
0x14002146d  mov     [r8+rdx+10h], r10
0x140021472  jmp     short loc_140021478
0x140021474  mov     [rdx+20h], r10
0x140021478  mov     rdx, [rbx+120h]
0x14002147f  cmp     byte ptr [rdx+2], 28h ; '('
0x140021483  jnz     short loc_1400214F7
0x140021485  cmp     dword ptr [rdx+14h], 0
0x140021489  jnz     short loc_1400214FB
0x14002148b  xor     r11b, r11b
0x14002148e  xor     r10d, r10d
0x140021491  cmp     [rdx+38h], r10d
0x140021495  jbe     short loc_1400214FB
0x140021497  mov     ecx, [rdx+r10*4+78h]
0x14002149c  cmp     ecx, 80h
0x1400214a2  jb      short loc_1400214D0
0x1400214a4  mov     r9d, [rdx+10h]
0x1400214a8  cmp     ecx, r9d
0x1400214ab  jnb     short loc_1400214D0
0x1400214ad  mov     r8d, ecx
0x1400214b0  mov     ecx, [rcx+rdx]
0x1400214b3  sub     ecx, 40h ; '@'
0x1400214b6  jz      short loc_1400214C2
0x1400214b8  sub     ecx, 1
0x1400214bb  jz      short loc_1400214DB
0x1400214bd  cmp     ecx, 1
0x1400214c0  jnz     short loc_1400214CB
0x1400214c2  lea     rcx, [r8+28h]
0x1400214c6  cmp     rcx, r9
0x1400214c9  jbe     short loc_1400214EF
0x1400214cb  test    r11b, r11b
0x1400214ce  jnz     short loc_1400214FB
0x1400214d0  inc     r10d
0x1400214d3  cmp     r10d, [rdx+38h]
0x1400214d7  jb      short loc_140021497
0x1400214d9  jmp     short loc_1400214FB
0x1400214db  lea     rcx, [r8+38h]
0x1400214df  cmp     rcx, r9
0x1400214e2  ja      short loc_1400214CB
0x1400214e4  mov     r11b, 1
0x1400214e7  mov     byte ptr [r8+rdx+9], 12h
0x1400214ed  jmp     short loc_1400214CB
0x1400214ef  mov     byte ptr [r8+rdx+9], 12h
0x1400214f5  jmp     short loc_1400214FB
0x1400214f7  mov     byte ptr [rdx+0Bh], 12h
0x1400214fb  mov     rax, [rbx+120h]
0x140021502  mov     ecx, [rsi+248h]
0x140021508  cmp     byte ptr [rax+2], 28h ; '('
0x14002150c  jnz     short loc_140021513
0x14002150e  mov     [rax+28h], ecx
0x140021511  jmp     short loc_140021516
0x140021513  mov     [rax+14h], ecx
0x140021516  mov     rax, [rbx+120h]
0x14002151d  cmp     byte ptr [rax+2], 28h ; '('
0x140021521  jnz     short loc_140021529
0x140021523  mov     [rax+40h], r15
0x140021527  jmp     short loc_14002152D
0x140021529  mov     [rax+18h], r15
0x14002152d  mov     rax, [rbx+120h]
0x140021534  cmp     byte ptr [rax+2], 28h ; '('
0x140021538  jnz     short loc_14002153F
0x14002153a  mov     [rax+3Ch], ebp
0x14002153d  jmp     short loc_140021542
0x14002153f  mov     [rax+10h], ebp
0x140021542  mov     rcx, [rbx+120h]
0x140021549  mov     eax, [rsi+250h]
0x14002154f  or      eax, 148h
0x140021554  cmp     byte ptr [rcx+2], 28h ; '('
0x140021558  jnz     short loc_14002155F
0x14002155a  mov     [rcx+18h], eax
0x14002155d  jmp     short loc_140021562
0x14002155f  mov     [rcx+0Ch], eax
0x140021562  mov     rdx, [rbx+120h]
0x140021569  cmp     byte ptr [rdx+2], 28h ; '('
0x14002156d  jnz     loc_140021621
0x140021573  xor     r8d, r8d
0x140021576  cmp     [rdx+14h], r8d
0x14002157a  jnz     loc_140021625
0x140021580  mov     edi, [rdx+38h]
0x140021583  test    edi, edi
0x140021585  jz      loc_140021625
0x14002158b  xor     r11d, r11d
0x14002158e  xor     sil, sil
0x140021591  mov     ecx, [rdx+r11*4+78h]
0x140021596  cmp     ecx, 80h
0x14002159c  jb      short loc_140021606
0x14002159e  mov     r10d, [rdx+10h]
0x1400215a2  cmp     ecx, r10d
0x1400215a5  jnb     short loc_140021606
0x1400215a7  mov     r9d, ecx
0x1400215aa  mov     ecx, [rcx+rdx]
0x1400215ad  sub     ecx, 40h ; '@'
0x1400215b0  jz      short loc_1400215F8
0x1400215b2  sub     ecx, 1
0x1400215b5  jz      short loc_1400215DB
0x1400215b7  cmp     ecx, 1
0x1400215ba  jnz     short loc_140021601
0x1400215bc  lea     rcx, [r9+28h]
0x1400215c0  cmp     rcx, r10
0x1400215c3  ja      short loc_140021601
0x1400215c5  lea     rcx, [rdx+20h]
0x1400215c9  add     rcx, r9
0x1400215cc  cmp     dword ptr [r9+rdx+0Ch], 0
0x1400215d2  cmovz   rcx, r8
0x1400215d6  mov     r8, rcx
0x1400215d9  jmp     short loc_140021625
0x1400215db  lea     rcx, [r9+38h]
0x1400215df  cmp     rcx, r10
0x1400215e2  ja      short loc_140021601
0x1400215e4  cmp     byte ptr [r9+rdx+0Ah], 0
0x1400215ea  jbe     short loc_140021625
0x1400215ec  lea     r8, [rdx+18h]
0x1400215f0  mov     sil, 1
0x1400215f3  add     r8, r9
0x1400215f6  jmp     short loc_140021601
0x1400215f8  lea     rcx, [r9+28h]
0x1400215fc  cmp     rcx, r10
0x1400215ff  jbe     short loc_140021610
0x140021601  test    sil, sil
0x140021604  jnz     short loc_140021625
0x140021606  inc     r11d
0x140021609  cmp     r11d, edi
0x14002160c  jb      short loc_140021591
0x14002160e  jmp     short loc_140021625
0x140021610  cmp     byte ptr [r9+rdx+0Ah], 0
0x140021616  jbe     short loc_140021625
0x140021618  lea     r8, [rdx+18h]
0x14002161c  add     r8, r9
0x14002161f  jmp     short loc_140021625
0x140021621  lea     r8, [rdx+48h]
0x140021625  test    r8, r8
0x140021628  jz      short loc_140021682
0x14002162a  mov     al, [r8+1]
0x14002162e  and     al, 0E7h
0x140021630  mov     byte ptr [r8], 84h
0x140021634  or      al, 7
0x140021636  mov     [r8+0Dh], bpl
0x14002163a  mov     [r8+1], al
0x14002163e  mov     al, [rsp+58h+arg_11]
0x140021642  mov     [r8+0Ch], al
0x140021646  mov     al, [rsp+58h+arg_12]
0x14002164a  mov     [r8+0Bh], al
0x14002164e  mov     al, [rsp+58h+arg_13]
0x140021652  mov     [r8+0Ah], al
0x140021656  mov     al, [rsp+58h+arg_28]
0x14002165d  mov     [r8+5], al
0x140021661  mov     al, [rsp+58h+arg_29]
0x140021668  mov     [r8+4], al
0x14002166c  mov     al, [rsp+58h+arg_2A]
0x140021673  mov     [r8+3], al
0x140021677  mov     al, [rsp+58h+arg_2B]
0x14002167e  mov     [r8+2], al
0x140021682  lea     rax, ClasspReceiveWriteUsingTokenInformationTransferPacketDone
0x140021689  mov     [rbx+0F0h], r15
0x140021690  mov     [rbx+158h], rax
0x140021697  mov     [rbx+0F8h], ebp
  ... truncated ...
```
