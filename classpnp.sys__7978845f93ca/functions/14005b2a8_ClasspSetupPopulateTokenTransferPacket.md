# ClasspSetupPopulateTokenTransferPacket

- ea: `0x14005b2a8`
- end: `0x14005b738`
- name: `ClasspSetupPopulateTokenTransferPacket`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140059cb4`

## callees

- `0x140022668`
- `0x14003e640`
- `0x14005b2a8`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ClasspSetupPopulateTokenTransferPacket(
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
      19,
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
  v46 = *(_DWORD *)(v10 + 592) | 0x188;
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
    v58 = v48[1] & 0xF0;
    *v48 = -125;
    v48[13] = a3;
    v48[1] = v58 | 0x10;
    v48[9] = a6;
    v48[8] = BYTE1(a6);
    v48[7] = BYTE2(a6);
    v48[6] = HIBYTE(a6);
    v48[12] = BYTE1(a3);
    v48[11] = BYTE2(a3);
    v48[10] = HIBYTE(a3);
  }
  *(_QWORD *)(a2 + 240) = a4;
  *(_QWORD *)(a2 + 344) = ClasspPopulateTokenTransferPacketDone;
  *(_DWORD *)(a2 + 248) = a3;
  *(_QWORD *)(a2 + 48) = a5;
  *(_WORD *)(a2 + 56) = 256;
  *(_QWORD *)(a2 + 352) = a1;
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return (PDEVICE_OBJECT *)WPP_SF_qq(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 20,
                                 WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids,
                                 *(_QWORD *)(a2 + 40),
                                 a5);
  }
  return result;
}

```

## disassembly

```asm
0x14005b2a8  mov     r11, rsp
0x14005b2ab  mov     [r11+8], rbx
0x14005b2af  mov     [r11+10h], rbp
0x14005b2b3  mov     [r11+18h], r8d
0x14005b2b7  push    rsi
0x14005b2b8  push    rdi
0x14005b2b9  push    r12
0x14005b2bb  push    r14
0x14005b2bd  push    r15
0x14005b2bf  sub     rsp, 30h
0x14005b2c3  mov     r15, r9
0x14005b2c6  mov     ebp, r8d
0x14005b2c9  mov     rbx, rdx
0x14005b2cc  mov     r12, rcx
0x14005b2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b2d6  lea     rax, WPP_GLOBAL_Control
0x14005b2dd  mov     r14, [rsp+58h+arg_20]
0x14005b2e5  cmp     rcx, rax
0x14005b2e8  jz      short loc_14005B314
0x14005b2ea  mov     eax, [rcx+2Ch]
0x14005b2ed  test    al, 10h
0x14005b2ef  jz      short loc_14005B314
0x14005b2f1  cmp     byte ptr [rcx+29h], 5
0x14005b2f5  jb      short loc_14005B314
0x14005b2f7  mov     r9, [rbx+28h]
0x14005b2fb  lea     r8, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids
0x14005b302  mov     rcx, [rcx+18h]
0x14005b306  mov     edx, 13h
0x14005b30b  mov     [r11-38h], r14
0x14005b30f  call    WPP_SF_qq
0x14005b314  mov     rax, [rbx+28h]
0x14005b318  mov     rsi, [rax+40h]
0x14005b31c  mov     rax, [rsi+478h]
0x14005b323  mov     rdx, [rax+2B0h]; Src
0x14005b32a  mov     rax, [rsi+210h]
0x14005b331  cmp     byte ptr [rax+1Eh], 1
0x14005b335  jnz     short loc_14005B33C
0x14005b337  mov     eax, [rdx+10h]
0x14005b33a  jmp     short loc_14005B33F
0x14005b33c  movzx   eax, word ptr [rdx]
0x14005b33f  mov     rcx, [rbx+120h]; void *
0x14005b346  mov     r8d, eax; Size
0x14005b349  call    memmove
0x14005b34e  mov     rcx, [rbx+120h]
0x14005b355  cmp     byte ptr [rcx+2], 28h ; '('
0x14005b359  jnz     short loc_14005B363
0x14005b35b  mov     word ptr [rcx+26h], 20h ; ' '
0x14005b361  jmp     short loc_14005B367
0x14005b363  mov     byte ptr [rcx+9], 20h ; ' '
0x14005b367  mov     rdx, [rbx+120h]
0x14005b36e  cmp     byte ptr [rdx+2], 28h ; '('
0x14005b372  jnz     short loc_14005B3F1
0x14005b374  cmp     dword ptr [rdx+14h], 0
0x14005b378  jnz     short loc_14005B3F5
0x14005b37a  xor     r11b, r11b
0x14005b37d  xor     r10d, r10d
0x14005b380  cmp     [rdx+38h], r10d
0x14005b384  jbe     short loc_14005B3F5
0x14005b386  mov     ecx, [rdx+r10*4+78h]
0x14005b38b  cmp     ecx, 80h
0x14005b391  jb      short loc_14005B3DE
0x14005b393  mov     r9d, [rdx+10h]
0x14005b397  cmp     ecx, r9d
0x14005b39a  jnb     short loc_14005B3DE
0x14005b39c  mov     r8d, ecx
0x14005b39f  mov     ecx, [rcx+rdx]
0x14005b3a2  sub     ecx, 40h ; '@'
0x14005b3a5  jz      short loc_14005B3D0
0x14005b3a7  sub     ecx, 1
0x14005b3aa  jz      short loc_14005B3BC
0x14005b3ac  cmp     ecx, 1
0x14005b3af  jnz     short loc_14005B3D9
0x14005b3b1  lea     rcx, [r8+28h]
0x14005b3b5  cmp     rcx, r9
0x14005b3b8  jbe     short loc_14005B3F5
0x14005b3ba  jmp     short loc_14005B3D9
0x14005b3bc  lea     rcx, [r8+38h]
0x14005b3c0  cmp     rcx, r9
0x14005b3c3  ja      short loc_14005B3D9
0x14005b3c5  mov     r11b, 1
0x14005b3c8  mov     byte ptr [r8+rdx+0Ah], 10h
0x14005b3ce  jmp     short loc_14005B3D9
0x14005b3d0  lea     rcx, [r8+28h]
0x14005b3d4  cmp     rcx, r9
0x14005b3d7  jbe     short loc_14005B3E9
0x14005b3d9  test    r11b, r11b
0x14005b3dc  jnz     short loc_14005B3F5
0x14005b3de  inc     r10d
0x14005b3e1  cmp     r10d, [rdx+38h]
0x14005b3e5  jb      short loc_14005B386
0x14005b3e7  jmp     short loc_14005B3F5
0x14005b3e9  mov     byte ptr [r8+rdx+0Ah], 10h
0x14005b3ef  jmp     short loc_14005B3F5
0x14005b3f1  mov     byte ptr [rdx+0Ah], 10h
0x14005b3f5  mov     rax, [rbx+120h]
0x14005b3fc  mov     rcx, [rbx+20h]
0x14005b400  cmp     byte ptr [rax+2], 28h ; '('
0x14005b404  jnz     short loc_14005B40C
0x14005b406  mov     [rax+50h], rcx
0x14005b40a  jmp     short loc_14005B410
0x14005b40c  mov     [rax+30h], rcx
0x14005b410  mov     rdx, [rbx+120h]
0x14005b417  lea     r10, [rbx+108h]
0x14005b41e  cmp     byte ptr [rdx+2], 28h ; '('
0x14005b422  jnz     loc_14005B4A8
0x14005b428  cmp     dword ptr [rdx+14h], 0
0x14005b42c  jnz     short loc_14005B4AC
0x14005b42e  xor     dil, dil
0x14005b431  xor     r11d, r11d
0x14005b434  cmp     [rdx+38h], r11d
0x14005b438  jbe     short loc_14005B4AC
0x14005b43a  mov     ecx, [rdx+r11*4+78h]
0x14005b43f  cmp     ecx, 80h
0x14005b445  jb      short loc_14005B496
0x14005b447  mov     r9d, [rdx+10h]
0x14005b44b  cmp     ecx, r9d
0x14005b44e  jnb     short loc_14005B496
0x14005b450  mov     r8d, ecx
0x14005b453  mov     ecx, [rcx+rdx]
0x14005b456  sub     ecx, 40h ; '@'
0x14005b459  jz      short loc_14005B488
0x14005b45b  sub     ecx, 1
0x14005b45e  jz      short loc_14005B475
0x14005b460  cmp     ecx, 1
0x14005b463  jnz     short loc_14005B491
0x14005b465  lea     rcx, [r8+28h]
0x14005b469  cmp     rcx, r9
0x14005b46c  ja      short loc_14005B491
0x14005b46e  mov     [r8+rdx+18h], r10
0x14005b473  jmp     short loc_14005B4AC
0x14005b475  lea     rcx, [r8+38h]
0x14005b479  cmp     rcx, r9
0x14005b47c  ja      short loc_14005B491
0x14005b47e  mov     dil, 1
0x14005b481  mov     [r8+rdx+10h], r10
0x14005b486  jmp     short loc_14005B491
0x14005b488  lea     rcx, [r8+28h]
0x14005b48c  cmp     rcx, r9
0x14005b48f  jbe     short loc_14005B4A1
0x14005b491  test    dil, dil
0x14005b494  jnz     short loc_14005B4AC
0x14005b496  inc     r11d
0x14005b499  cmp     r11d, [rdx+38h]
0x14005b49d  jb      short loc_14005B43A
0x14005b49f  jmp     short loc_14005B4AC
0x14005b4a1  mov     [r8+rdx+10h], r10
0x14005b4a6  jmp     short loc_14005B4AC
0x14005b4a8  mov     [rdx+20h], r10
0x14005b4ac  mov     rdx, [rbx+120h]
0x14005b4b3  cmp     byte ptr [rdx+2], 28h ; '('
0x14005b4b7  jnz     short loc_14005B52B
0x14005b4b9  cmp     dword ptr [rdx+14h], 0
0x14005b4bd  jnz     short loc_14005B52F
0x14005b4bf  xor     r11b, r11b
0x14005b4c2  xor     r10d, r10d
0x14005b4c5  cmp     [rdx+38h], r10d
0x14005b4c9  jbe     short loc_14005B52F
0x14005b4cb  mov     ecx, [rdx+r10*4+78h]
0x14005b4d0  cmp     ecx, 80h
0x14005b4d6  jb      short loc_14005B504
0x14005b4d8  mov     r9d, [rdx+10h]
0x14005b4dc  cmp     ecx, r9d
0x14005b4df  jnb     short loc_14005B504
0x14005b4e1  mov     r8d, ecx
0x14005b4e4  mov     ecx, [rcx+rdx]
0x14005b4e7  sub     ecx, 40h ; '@'
0x14005b4ea  jz      short loc_14005B4F6
0x14005b4ec  sub     ecx, 1
0x14005b4ef  jz      short loc_14005B50F
0x14005b4f1  cmp     ecx, 1
0x14005b4f4  jnz     short loc_14005B4FF
0x14005b4f6  lea     rcx, [r8+28h]
0x14005b4fa  cmp     rcx, r9
0x14005b4fd  jbe     short loc_14005B523
0x14005b4ff  test    r11b, r11b
0x14005b502  jnz     short loc_14005B52F
0x14005b504  inc     r10d
0x14005b507  cmp     r10d, [rdx+38h]
0x14005b50b  jb      short loc_14005B4CB
0x14005b50d  jmp     short loc_14005B52F
0x14005b50f  lea     rcx, [r8+38h]
0x14005b513  cmp     rcx, r9
0x14005b516  ja      short loc_14005B4FF
0x14005b518  mov     r11b, 1
0x14005b51b  mov     byte ptr [r8+rdx+9], 12h
0x14005b521  jmp     short loc_14005B4FF
0x14005b523  mov     byte ptr [r8+rdx+9], 12h
0x14005b529  jmp     short loc_14005B52F
0x14005b52b  mov     byte ptr [rdx+0Bh], 12h
0x14005b52f  mov     rax, [rbx+120h]
0x14005b536  mov     ecx, [rsi+248h]
0x14005b53c  cmp     byte ptr [rax+2], 28h ; '('
0x14005b540  jnz     short loc_14005B547
0x14005b542  mov     [rax+28h], ecx
0x14005b545  jmp     short loc_14005B54A
0x14005b547  mov     [rax+14h], ecx
0x14005b54a  mov     rax, [rbx+120h]
0x14005b551  cmp     byte ptr [rax+2], 28h ; '('
0x14005b555  jnz     short loc_14005B55D
0x14005b557  mov     [rax+40h], r15
0x14005b55b  jmp     short loc_14005B561
0x14005b55d  mov     [rax+18h], r15
0x14005b561  mov     rax, [rbx+120h]
0x14005b568  cmp     byte ptr [rax+2], 28h ; '('
0x14005b56c  jnz     short loc_14005B573
0x14005b56e  mov     [rax+3Ch], ebp
0x14005b571  jmp     short loc_14005B576
0x14005b573  mov     [rax+10h], ebp
0x14005b576  mov     rcx, [rbx+120h]
0x14005b57d  mov     eax, [rsi+250h]
0x14005b583  or      eax, 188h
0x14005b588  cmp     byte ptr [rcx+2], 28h ; '('
0x14005b58c  jnz     short loc_14005B593
0x14005b58e  mov     [rcx+18h], eax
0x14005b591  jmp     short loc_14005B596
0x14005b593  mov     [rcx+0Ch], eax
0x14005b596  mov     rdx, [rbx+120h]
0x14005b59d  cmp     byte ptr [rdx+2], 28h ; '('
0x14005b5a1  jnz     loc_14005B655
0x14005b5a7  xor     r8d, r8d
0x14005b5aa  cmp     [rdx+14h], r8d
0x14005b5ae  jnz     loc_14005B659
0x14005b5b4  mov     edi, [rdx+38h]
0x14005b5b7  test    edi, edi
0x14005b5b9  jz      loc_14005B659
0x14005b5bf  xor     r11d, r11d
0x14005b5c2  xor     sil, sil
0x14005b5c5  mov     ecx, [rdx+r11*4+78h]
0x14005b5ca  cmp     ecx, 80h
0x14005b5d0  jb      short loc_14005B63A
0x14005b5d2  mov     r10d, [rdx+10h]
0x14005b5d6  cmp     ecx, r10d
0x14005b5d9  jnb     short loc_14005B63A
0x14005b5db  mov     r9d, ecx
0x14005b5de  mov     ecx, [rcx+rdx]
0x14005b5e1  sub     ecx, 40h ; '@'
0x14005b5e4  jz      short loc_14005B62C
0x14005b5e6  sub     ecx, 1
0x14005b5e9  jz      short loc_14005B60F
0x14005b5eb  cmp     ecx, 1
0x14005b5ee  jnz     short loc_14005B635
0x14005b5f0  lea     rcx, [r9+28h]
0x14005b5f4  cmp     rcx, r10
0x14005b5f7  ja      short loc_14005B635
0x14005b5f9  lea     rcx, [rdx+20h]
0x14005b5fd  add     rcx, r9
0x14005b600  cmp     dword ptr [r9+rdx+0Ch], 0
0x14005b606  cmovz   rcx, r8
0x14005b60a  mov     r8, rcx
0x14005b60d  jmp     short loc_14005B659
0x14005b60f  lea     rcx, [r9+38h]
0x14005b613  cmp     rcx, r10
0x14005b616  ja      short loc_14005B635
0x14005b618  cmp     byte ptr [r9+rdx+0Ah], 0
0x14005b61e  jbe     short loc_14005B659
0x14005b620  lea     r8, [rdx+18h]
0x14005b624  mov     sil, 1
0x14005b627  add     r8, r9
0x14005b62a  jmp     short loc_14005B635
0x14005b62c  lea     rcx, [r9+28h]
0x14005b630  cmp     rcx, r10
0x14005b633  jbe     short loc_14005B644
0x14005b635  test    sil, sil
0x14005b638  jnz     short loc_14005B659
0x14005b63a  inc     r11d
0x14005b63d  cmp     r11d, edi
0x14005b640  jb      short loc_14005B5C5
0x14005b642  jmp     short loc_14005B659
0x14005b644  cmp     byte ptr [r9+rdx+0Ah], 0
0x14005b64a  jbe     short loc_14005B659
0x14005b64c  lea     r8, [rdx+18h]
0x14005b650  add     r8, r9
0x14005b653  jmp     short loc_14005B659
0x14005b655  lea     r8, [rdx+48h]
0x14005b659  test    r8, r8
0x14005b65c  jz      short loc_14005B6B6
0x14005b65e  mov     al, [r8+1]
0x14005b662  and     al, 0F0h
0x14005b664  mov     byte ptr [r8], 83h
0x14005b668  or      al, 10h
0x14005b66a  mov     [r8+0Dh], bpl
0x14005b66e  mov     [r8+1], al
0x14005b672  mov     al, [rsp+58h+arg_28]
0x14005b679  mov     [r8+9], al
0x14005b67d  mov     al, [rsp+58h+arg_29]
0x14005b684  mov     [r8+8], al
0x14005b688  mov     al, [rsp+58h+arg_2A]
0x14005b68f  mov     [r8+7], al
0x14005b693  mov     al, [rsp+58h+arg_2B]
0x14005b69a  mov     [r8+6], al
0x14005b69e  mov     al, [rsp+58h+arg_11]
0x14005b6a2  mov     [r8+0Ch], al
0x14005b6a6  mov     al, [rsp+58h+arg_12]
0x14005b6aa  mov     [r8+0Bh], al
0x14005b6ae  mov     al, [rsp+58h+arg_13]
0x14005b6b2  mov     [r8+0Ah], al
0x14005b6b6  lea     rax, ClasspPopulateTokenTransferPacketDone
0x14005b6bd  mov     [rbx+0F0h], r15
0x14005b6c4  mov     [rbx+158h], rax
0x14005b6cb  mov     [rbx+0F8h], ebp
  ... truncated ...
```
