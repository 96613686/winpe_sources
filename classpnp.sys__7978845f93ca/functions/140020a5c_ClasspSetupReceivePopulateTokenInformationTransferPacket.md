# ClasspSetupReceivePopulateTokenInformationTransferPacket

- ea: `0x140020a5c`
- end: `0x140020eec`
- name: `ClasspSetupReceivePopulateTokenInformationTransferPacket`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400206f8`

## callees

- `0x140020a5c`
- `0x140022668`
- `0x14003e640`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ClasspSetupReceivePopulateTokenInformationTransferPacket(
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
      21,
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
    v48[5] = a6;
    v48[4] = BYTE1(a6);
    v48[3] = BYTE2(a6);
    v48[2] = HIBYTE(a6);
    v48[12] = BYTE1(a3);
    v48[11] = BYTE2(a3);
    v48[10] = HIBYTE(a3);
  }
  *(_QWORD *)(a2 + 240) = a4;
  *(_QWORD *)(a2 + 344) = ClasspReceivePopulateTokenInformationTransferPacketDone;
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
                                 22,
                                 WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids,
                                 *(_QWORD *)(a2 + 40),
                                 a5);
  }
  return result;
}

```

## disassembly

```asm
0x140020a5c  mov     r11, rsp
0x140020a5f  mov     [r11+8], rbx
0x140020a63  mov     [r11+10h], rbp
0x140020a67  mov     [r11+18h], r8d
0x140020a6b  push    rsi
0x140020a6c  push    rdi
0x140020a6d  push    r12
0x140020a6f  push    r14
0x140020a71  push    r15
0x140020a73  sub     rsp, 30h
0x140020a77  mov     r15, r9
0x140020a7a  mov     ebp, r8d
0x140020a7d  mov     rbx, rdx
0x140020a80  mov     r12, rcx
0x140020a83  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a8a  lea     rax, WPP_GLOBAL_Control
0x140020a91  mov     r14, [rsp+58h+arg_20]
0x140020a99  cmp     rcx, rax
0x140020a9c  jz      short loc_140020AC8
0x140020a9e  mov     eax, [rcx+2Ch]
0x140020aa1  test    al, 10h
0x140020aa3  jz      short loc_140020AC8
0x140020aa5  cmp     byte ptr [rcx+29h], 5
0x140020aa9  jb      short loc_140020AC8
0x140020aab  mov     r9, [rbx+28h]
0x140020aaf  lea     r8, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids
0x140020ab6  mov     rcx, [rcx+18h]
0x140020aba  mov     edx, 15h
0x140020abf  mov     [r11-38h], r14
0x140020ac3  call    WPP_SF_qq
0x140020ac8  mov     rax, [rbx+28h]
0x140020acc  mov     rsi, [rax+40h]
0x140020ad0  mov     rax, [rsi+478h]
0x140020ad7  mov     rdx, [rax+2B0h]; Src
0x140020ade  mov     rax, [rsi+210h]
0x140020ae5  cmp     byte ptr [rax+1Eh], 1
0x140020ae9  jnz     short loc_140020AF0
0x140020aeb  mov     eax, [rdx+10h]
0x140020aee  jmp     short loc_140020AF3
0x140020af0  movzx   eax, word ptr [rdx]
0x140020af3  mov     rcx, [rbx+120h]; void *
0x140020afa  mov     r8d, eax; Size
0x140020afd  call    memmove
0x140020b02  mov     rcx, [rbx+120h]
0x140020b09  cmp     byte ptr [rcx+2], 28h ; '('
0x140020b0d  jnz     short loc_140020B17
0x140020b0f  mov     word ptr [rcx+26h], 20h ; ' '
0x140020b15  jmp     short loc_140020B1B
0x140020b17  mov     byte ptr [rcx+9], 20h ; ' '
0x140020b1b  mov     rdx, [rbx+120h]
0x140020b22  cmp     byte ptr [rdx+2], 28h ; '('
0x140020b26  jnz     short loc_140020BA5
0x140020b28  cmp     dword ptr [rdx+14h], 0
0x140020b2c  jnz     short loc_140020BA9
0x140020b2e  xor     r11b, r11b
0x140020b31  xor     r10d, r10d
0x140020b34  cmp     [rdx+38h], r10d
0x140020b38  jbe     short loc_140020BA9
0x140020b3a  mov     ecx, [rdx+r10*4+78h]
0x140020b3f  cmp     ecx, 80h
0x140020b45  jb      short loc_140020B92
0x140020b47  mov     r9d, [rdx+10h]
0x140020b4b  cmp     ecx, r9d
0x140020b4e  jnb     short loc_140020B92
0x140020b50  mov     r8d, ecx
0x140020b53  mov     ecx, [rcx+rdx]
0x140020b56  sub     ecx, 40h ; '@'
0x140020b59  jz      short loc_140020B84
0x140020b5b  sub     ecx, 1
0x140020b5e  jz      short loc_140020B70
0x140020b60  cmp     ecx, 1
0x140020b63  jnz     short loc_140020B8D
0x140020b65  lea     rcx, [r8+28h]
0x140020b69  cmp     rcx, r9
0x140020b6c  jbe     short loc_140020BA9
0x140020b6e  jmp     short loc_140020B8D
0x140020b70  lea     rcx, [r8+38h]
0x140020b74  cmp     rcx, r9
0x140020b77  ja      short loc_140020B8D
0x140020b79  mov     r11b, 1
0x140020b7c  mov     byte ptr [r8+rdx+0Ah], 10h
0x140020b82  jmp     short loc_140020B8D
0x140020b84  lea     rcx, [r8+28h]
0x140020b88  cmp     rcx, r9
0x140020b8b  jbe     short loc_140020B9D
0x140020b8d  test    r11b, r11b
0x140020b90  jnz     short loc_140020BA9
0x140020b92  inc     r10d
0x140020b95  cmp     r10d, [rdx+38h]
0x140020b99  jb      short loc_140020B3A
0x140020b9b  jmp     short loc_140020BA9
0x140020b9d  mov     byte ptr [r8+rdx+0Ah], 10h
0x140020ba3  jmp     short loc_140020BA9
0x140020ba5  mov     byte ptr [rdx+0Ah], 10h
0x140020ba9  mov     rax, [rbx+120h]
0x140020bb0  mov     rcx, [rbx+20h]
0x140020bb4  cmp     byte ptr [rax+2], 28h ; '('
0x140020bb8  jnz     short loc_140020BC0
0x140020bba  mov     [rax+50h], rcx
0x140020bbe  jmp     short loc_140020BC4
0x140020bc0  mov     [rax+30h], rcx
0x140020bc4  mov     rdx, [rbx+120h]
0x140020bcb  lea     r10, [rbx+108h]
0x140020bd2  cmp     byte ptr [rdx+2], 28h ; '('
0x140020bd6  jnz     loc_140020C5C
0x140020bdc  cmp     dword ptr [rdx+14h], 0
0x140020be0  jnz     short loc_140020C60
0x140020be2  xor     dil, dil
0x140020be5  xor     r11d, r11d
0x140020be8  cmp     [rdx+38h], r11d
0x140020bec  jbe     short loc_140020C60
0x140020bee  mov     ecx, [rdx+r11*4+78h]
0x140020bf3  cmp     ecx, 80h
0x140020bf9  jb      short loc_140020C4A
0x140020bfb  mov     r9d, [rdx+10h]
0x140020bff  cmp     ecx, r9d
0x140020c02  jnb     short loc_140020C4A
0x140020c04  mov     r8d, ecx
0x140020c07  mov     ecx, [rcx+rdx]
0x140020c0a  sub     ecx, 40h ; '@'
0x140020c0d  jz      short loc_140020C3C
0x140020c0f  sub     ecx, 1
0x140020c12  jz      short loc_140020C29
0x140020c14  cmp     ecx, 1
0x140020c17  jnz     short loc_140020C45
0x140020c19  lea     rcx, [r8+28h]
0x140020c1d  cmp     rcx, r9
0x140020c20  ja      short loc_140020C45
0x140020c22  mov     [r8+rdx+18h], r10
0x140020c27  jmp     short loc_140020C60
0x140020c29  lea     rcx, [r8+38h]
0x140020c2d  cmp     rcx, r9
0x140020c30  ja      short loc_140020C45
0x140020c32  mov     dil, 1
0x140020c35  mov     [r8+rdx+10h], r10
0x140020c3a  jmp     short loc_140020C45
0x140020c3c  lea     rcx, [r8+28h]
0x140020c40  cmp     rcx, r9
0x140020c43  jbe     short loc_140020C55
0x140020c45  test    dil, dil
0x140020c48  jnz     short loc_140020C60
0x140020c4a  inc     r11d
0x140020c4d  cmp     r11d, [rdx+38h]
0x140020c51  jb      short loc_140020BEE
0x140020c53  jmp     short loc_140020C60
0x140020c55  mov     [r8+rdx+10h], r10
0x140020c5a  jmp     short loc_140020C60
0x140020c5c  mov     [rdx+20h], r10
0x140020c60  mov     rdx, [rbx+120h]
0x140020c67  cmp     byte ptr [rdx+2], 28h ; '('
0x140020c6b  jnz     short loc_140020CDF
0x140020c6d  cmp     dword ptr [rdx+14h], 0
0x140020c71  jnz     short loc_140020CE3
0x140020c73  xor     r11b, r11b
0x140020c76  xor     r10d, r10d
0x140020c79  cmp     [rdx+38h], r10d
0x140020c7d  jbe     short loc_140020CE3
0x140020c7f  mov     ecx, [rdx+r10*4+78h]
0x140020c84  cmp     ecx, 80h
0x140020c8a  jb      short loc_140020CB8
0x140020c8c  mov     r9d, [rdx+10h]
0x140020c90  cmp     ecx, r9d
0x140020c93  jnb     short loc_140020CB8
0x140020c95  mov     r8d, ecx
0x140020c98  mov     ecx, [rcx+rdx]
0x140020c9b  sub     ecx, 40h ; '@'
0x140020c9e  jz      short loc_140020CAA
0x140020ca0  sub     ecx, 1
0x140020ca3  jz      short loc_140020CC3
0x140020ca5  cmp     ecx, 1
0x140020ca8  jnz     short loc_140020CB3
0x140020caa  lea     rcx, [r8+28h]
0x140020cae  cmp     rcx, r9
0x140020cb1  jbe     short loc_140020CD7
0x140020cb3  test    r11b, r11b
0x140020cb6  jnz     short loc_140020CE3
0x140020cb8  inc     r10d
0x140020cbb  cmp     r10d, [rdx+38h]
0x140020cbf  jb      short loc_140020C7F
0x140020cc1  jmp     short loc_140020CE3
0x140020cc3  lea     rcx, [r8+38h]
0x140020cc7  cmp     rcx, r9
0x140020cca  ja      short loc_140020CB3
0x140020ccc  mov     r11b, 1
0x140020ccf  mov     byte ptr [r8+rdx+9], 12h
0x140020cd5  jmp     short loc_140020CB3
0x140020cd7  mov     byte ptr [r8+rdx+9], 12h
0x140020cdd  jmp     short loc_140020CE3
0x140020cdf  mov     byte ptr [rdx+0Bh], 12h
0x140020ce3  mov     rax, [rbx+120h]
0x140020cea  mov     ecx, [rsi+248h]
0x140020cf0  cmp     byte ptr [rax+2], 28h ; '('
0x140020cf4  jnz     short loc_140020CFB
0x140020cf6  mov     [rax+28h], ecx
0x140020cf9  jmp     short loc_140020CFE
0x140020cfb  mov     [rax+14h], ecx
0x140020cfe  mov     rax, [rbx+120h]
0x140020d05  cmp     byte ptr [rax+2], 28h ; '('
0x140020d09  jnz     short loc_140020D11
0x140020d0b  mov     [rax+40h], r15
0x140020d0f  jmp     short loc_140020D15
0x140020d11  mov     [rax+18h], r15
0x140020d15  mov     rax, [rbx+120h]
0x140020d1c  cmp     byte ptr [rax+2], 28h ; '('
0x140020d20  jnz     short loc_140020D27
0x140020d22  mov     [rax+3Ch], ebp
0x140020d25  jmp     short loc_140020D2A
0x140020d27  mov     [rax+10h], ebp
0x140020d2a  mov     rcx, [rbx+120h]
0x140020d31  mov     eax, [rsi+250h]
0x140020d37  or      eax, 148h
0x140020d3c  cmp     byte ptr [rcx+2], 28h ; '('
0x140020d40  jnz     short loc_140020D47
0x140020d42  mov     [rcx+18h], eax
0x140020d45  jmp     short loc_140020D4A
0x140020d47  mov     [rcx+0Ch], eax
0x140020d4a  mov     rdx, [rbx+120h]
0x140020d51  cmp     byte ptr [rdx+2], 28h ; '('
0x140020d55  jnz     loc_140020E09
0x140020d5b  xor     r8d, r8d
0x140020d5e  cmp     [rdx+14h], r8d
0x140020d62  jnz     loc_140020E0D
0x140020d68  mov     edi, [rdx+38h]
0x140020d6b  test    edi, edi
0x140020d6d  jz      loc_140020E0D
0x140020d73  xor     r11d, r11d
0x140020d76  xor     sil, sil
0x140020d79  mov     ecx, [rdx+r11*4+78h]
0x140020d7e  cmp     ecx, 80h
0x140020d84  jb      short loc_140020DEE
0x140020d86  mov     r10d, [rdx+10h]
0x140020d8a  cmp     ecx, r10d
0x140020d8d  jnb     short loc_140020DEE
0x140020d8f  mov     r9d, ecx
0x140020d92  mov     ecx, [rcx+rdx]
0x140020d95  sub     ecx, 40h ; '@'
0x140020d98  jz      short loc_140020DE0
0x140020d9a  sub     ecx, 1
0x140020d9d  jz      short loc_140020DC3
0x140020d9f  cmp     ecx, 1
0x140020da2  jnz     short loc_140020DE9
0x140020da4  lea     rcx, [r9+28h]
0x140020da8  cmp     rcx, r10
0x140020dab  ja      short loc_140020DE9
0x140020dad  lea     rcx, [rdx+20h]
0x140020db1  add     rcx, r9
0x140020db4  cmp     dword ptr [r9+rdx+0Ch], 0
0x140020dba  cmovz   rcx, r8
0x140020dbe  mov     r8, rcx
0x140020dc1  jmp     short loc_140020E0D
0x140020dc3  lea     rcx, [r9+38h]
0x140020dc7  cmp     rcx, r10
0x140020dca  ja      short loc_140020DE9
0x140020dcc  cmp     byte ptr [r9+rdx+0Ah], 0
0x140020dd2  jbe     short loc_140020E0D
0x140020dd4  lea     r8, [rdx+18h]
0x140020dd8  mov     sil, 1
0x140020ddb  add     r8, r9
0x140020dde  jmp     short loc_140020DE9
0x140020de0  lea     rcx, [r9+28h]
0x140020de4  cmp     rcx, r10
0x140020de7  jbe     short loc_140020DF8
0x140020de9  test    sil, sil
0x140020dec  jnz     short loc_140020E0D
0x140020dee  inc     r11d
0x140020df1  cmp     r11d, edi
0x140020df4  jb      short loc_140020D79
0x140020df6  jmp     short loc_140020E0D
0x140020df8  cmp     byte ptr [r9+rdx+0Ah], 0
0x140020dfe  jbe     short loc_140020E0D
0x140020e00  lea     r8, [rdx+18h]
0x140020e04  add     r8, r9
0x140020e07  jmp     short loc_140020E0D
0x140020e09  lea     r8, [rdx+48h]
0x140020e0d  test    r8, r8
0x140020e10  jz      short loc_140020E6A
0x140020e12  mov     al, [r8+1]
0x140020e16  and     al, 0E7h
0x140020e18  mov     byte ptr [r8], 84h
0x140020e1c  or      al, 7
0x140020e1e  mov     [r8+0Dh], bpl
0x140020e22  mov     [r8+1], al
0x140020e26  mov     al, [rsp+58h+arg_28]
0x140020e2d  mov     [r8+5], al
0x140020e31  mov     al, [rsp+58h+arg_29]
0x140020e38  mov     [r8+4], al
0x140020e3c  mov     al, [rsp+58h+arg_2A]
0x140020e43  mov     [r8+3], al
0x140020e47  mov     al, [rsp+58h+arg_2B]
0x140020e4e  mov     [r8+2], al
0x140020e52  mov     al, [rsp+58h+arg_11]
0x140020e56  mov     [r8+0Ch], al
0x140020e5a  mov     al, [rsp+58h+arg_12]
0x140020e5e  mov     [r8+0Bh], al
0x140020e62  mov     al, [rsp+58h+arg_13]
0x140020e66  mov     [r8+0Ah], al
0x140020e6a  lea     rax, ClasspReceivePopulateTokenInformationTransferPacketDone
0x140020e71  mov     [rbx+0F0h], r15
0x140020e78  mov     [rbx+158h], rax
0x140020e7f  mov     [rbx+0F8h], ebp
  ... truncated ...
```
