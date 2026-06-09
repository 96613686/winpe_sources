# ClasspSetupWriteUsingTokenTransferPacket

- ea: `0x14002971c`
- end: `0x140029bac`
- name: `ClasspSetupWriteUsingTokenTransferPacket`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140024070`

## callees

- `0x140022668`
- `0x14002971c`
- `0x14003e640`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ClasspSetupWriteUsingTokenTransferPacket(
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
      23,
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
    v58 = v48[1] & 0xF1;
    *v48 = -125;
    v48[13] = a3;
    v48[1] = v58 | 0x11;
    v48[12] = BYTE1(a3);
    v48[11] = BYTE2(a3);
    v48[10] = HIBYTE(a3);
    v48[9] = a6;
    v48[8] = BYTE1(a6);
    v48[7] = BYTE2(a6);
    v48[6] = HIBYTE(a6);
  }
  *(_QWORD *)(a2 + 240) = a4;
  *(_QWORD *)(a2 + 344) = ClasspWriteUsingTokenTransferPacketDone;
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
                                 24,
                                 WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids,
                                 *(_QWORD *)(a2 + 40),
                                 a5);
  }
  return result;
}

```

## disassembly

```asm
0x14002971c  mov     r11, rsp
0x14002971f  mov     [r11+8], rbx
0x140029723  mov     [r11+10h], rbp
0x140029727  mov     [r11+18h], r8d
0x14002972b  push    rsi
0x14002972c  push    rdi
0x14002972d  push    r12
0x14002972f  push    r14
0x140029731  push    r15
0x140029733  sub     rsp, 30h
0x140029737  mov     r15, r9
0x14002973a  mov     ebp, r8d
0x14002973d  mov     rbx, rdx
0x140029740  mov     r12, rcx
0x140029743  mov     rcx, cs:WPP_GLOBAL_Control
0x14002974a  lea     rax, WPP_GLOBAL_Control
0x140029751  mov     r14, [rsp+58h+arg_20]
0x140029759  cmp     rcx, rax
0x14002975c  jz      short loc_140029788
0x14002975e  mov     eax, [rcx+2Ch]
0x140029761  test    al, 10h
0x140029763  jz      short loc_140029788
0x140029765  cmp     byte ptr [rcx+29h], 5
0x140029769  jb      short loc_140029788
0x14002976b  mov     r9, [rbx+28h]
0x14002976f  lea     r8, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids
0x140029776  mov     rcx, [rcx+18h]
0x14002977a  mov     edx, 17h
0x14002977f  mov     [r11-38h], r14
0x140029783  call    WPP_SF_qq
0x140029788  mov     rax, [rbx+28h]
0x14002978c  mov     rsi, [rax+40h]
0x140029790  mov     rax, [rsi+478h]
0x140029797  mov     rdx, [rax+2B0h]; Src
0x14002979e  mov     rax, [rsi+210h]
0x1400297a5  cmp     byte ptr [rax+1Eh], 1
0x1400297a9  jnz     short loc_1400297B0
0x1400297ab  mov     eax, [rdx+10h]
0x1400297ae  jmp     short loc_1400297B3
0x1400297b0  movzx   eax, word ptr [rdx]
0x1400297b3  mov     rcx, [rbx+120h]; void *
0x1400297ba  mov     r8d, eax; Size
0x1400297bd  call    memmove
0x1400297c2  mov     rcx, [rbx+120h]
0x1400297c9  cmp     byte ptr [rcx+2], 28h ; '('
0x1400297cd  jnz     short loc_1400297D7
0x1400297cf  mov     word ptr [rcx+26h], 20h ; ' '
0x1400297d5  jmp     short loc_1400297DB
0x1400297d7  mov     byte ptr [rcx+9], 20h ; ' '
0x1400297db  mov     rdx, [rbx+120h]
0x1400297e2  cmp     byte ptr [rdx+2], 28h ; '('
0x1400297e6  jnz     short loc_140029865
0x1400297e8  cmp     dword ptr [rdx+14h], 0
0x1400297ec  jnz     short loc_140029869
0x1400297ee  xor     r11b, r11b
0x1400297f1  xor     r10d, r10d
0x1400297f4  cmp     [rdx+38h], r10d
0x1400297f8  jbe     short loc_140029869
0x1400297fa  mov     ecx, [rdx+r10*4+78h]
0x1400297ff  cmp     ecx, 80h
0x140029805  jb      short loc_140029852
0x140029807  mov     r9d, [rdx+10h]
0x14002980b  cmp     ecx, r9d
0x14002980e  jnb     short loc_140029852
0x140029810  mov     r8d, ecx
0x140029813  mov     ecx, [rcx+rdx]
0x140029816  sub     ecx, 40h ; '@'
0x140029819  jz      short loc_140029844
0x14002981b  sub     ecx, 1
0x14002981e  jz      short loc_140029830
0x140029820  cmp     ecx, 1
0x140029823  jnz     short loc_14002984D
0x140029825  lea     rcx, [r8+28h]
0x140029829  cmp     rcx, r9
0x14002982c  jbe     short loc_140029869
0x14002982e  jmp     short loc_14002984D
0x140029830  lea     rcx, [r8+38h]
0x140029834  cmp     rcx, r9
0x140029837  ja      short loc_14002984D
0x140029839  mov     r11b, 1
0x14002983c  mov     byte ptr [r8+rdx+0Ah], 10h
0x140029842  jmp     short loc_14002984D
0x140029844  lea     rcx, [r8+28h]
0x140029848  cmp     rcx, r9
0x14002984b  jbe     short loc_14002985D
0x14002984d  test    r11b, r11b
0x140029850  jnz     short loc_140029869
0x140029852  inc     r10d
0x140029855  cmp     r10d, [rdx+38h]
0x140029859  jb      short loc_1400297FA
0x14002985b  jmp     short loc_140029869
0x14002985d  mov     byte ptr [r8+rdx+0Ah], 10h
0x140029863  jmp     short loc_140029869
0x140029865  mov     byte ptr [rdx+0Ah], 10h
0x140029869  mov     rax, [rbx+120h]
0x140029870  mov     rcx, [rbx+20h]
0x140029874  cmp     byte ptr [rax+2], 28h ; '('
0x140029878  jnz     short loc_140029880
0x14002987a  mov     [rax+50h], rcx
0x14002987e  jmp     short loc_140029884
0x140029880  mov     [rax+30h], rcx
0x140029884  mov     rdx, [rbx+120h]
0x14002988b  lea     r10, [rbx+108h]
0x140029892  cmp     byte ptr [rdx+2], 28h ; '('
0x140029896  jnz     loc_14002991C
0x14002989c  cmp     dword ptr [rdx+14h], 0
0x1400298a0  jnz     short loc_140029920
0x1400298a2  xor     dil, dil
0x1400298a5  xor     r11d, r11d
0x1400298a8  cmp     [rdx+38h], r11d
0x1400298ac  jbe     short loc_140029920
0x1400298ae  mov     ecx, [rdx+r11*4+78h]
0x1400298b3  cmp     ecx, 80h
0x1400298b9  jb      short loc_14002990A
0x1400298bb  mov     r9d, [rdx+10h]
0x1400298bf  cmp     ecx, r9d
0x1400298c2  jnb     short loc_14002990A
0x1400298c4  mov     r8d, ecx
0x1400298c7  mov     ecx, [rcx+rdx]
0x1400298ca  sub     ecx, 40h ; '@'
0x1400298cd  jz      short loc_1400298FC
0x1400298cf  sub     ecx, 1
0x1400298d2  jz      short loc_1400298E9
0x1400298d4  cmp     ecx, 1
0x1400298d7  jnz     short loc_140029905
0x1400298d9  lea     rcx, [r8+28h]
0x1400298dd  cmp     rcx, r9
0x1400298e0  ja      short loc_140029905
0x1400298e2  mov     [r8+rdx+18h], r10
0x1400298e7  jmp     short loc_140029920
0x1400298e9  lea     rcx, [r8+38h]
0x1400298ed  cmp     rcx, r9
0x1400298f0  ja      short loc_140029905
0x1400298f2  mov     dil, 1
0x1400298f5  mov     [r8+rdx+10h], r10
0x1400298fa  jmp     short loc_140029905
0x1400298fc  lea     rcx, [r8+28h]
0x140029900  cmp     rcx, r9
0x140029903  jbe     short loc_140029915
0x140029905  test    dil, dil
0x140029908  jnz     short loc_140029920
0x14002990a  inc     r11d
0x14002990d  cmp     r11d, [rdx+38h]
0x140029911  jb      short loc_1400298AE
0x140029913  jmp     short loc_140029920
0x140029915  mov     [r8+rdx+10h], r10
0x14002991a  jmp     short loc_140029920
0x14002991c  mov     [rdx+20h], r10
0x140029920  mov     rdx, [rbx+120h]
0x140029927  cmp     byte ptr [rdx+2], 28h ; '('
0x14002992b  jnz     short loc_14002999F
0x14002992d  cmp     dword ptr [rdx+14h], 0
0x140029931  jnz     short loc_1400299A3
0x140029933  xor     r11b, r11b
0x140029936  xor     r10d, r10d
0x140029939  cmp     [rdx+38h], r10d
0x14002993d  jbe     short loc_1400299A3
0x14002993f  mov     ecx, [rdx+r10*4+78h]
0x140029944  cmp     ecx, 80h
0x14002994a  jb      short loc_140029978
0x14002994c  mov     r9d, [rdx+10h]
0x140029950  cmp     ecx, r9d
0x140029953  jnb     short loc_140029978
0x140029955  mov     r8d, ecx
0x140029958  mov     ecx, [rcx+rdx]
0x14002995b  sub     ecx, 40h ; '@'
0x14002995e  jz      short loc_14002996A
0x140029960  sub     ecx, 1
0x140029963  jz      short loc_140029983
0x140029965  cmp     ecx, 1
0x140029968  jnz     short loc_140029973
0x14002996a  lea     rcx, [r8+28h]
0x14002996e  cmp     rcx, r9
0x140029971  jbe     short loc_140029997
0x140029973  test    r11b, r11b
0x140029976  jnz     short loc_1400299A3
0x140029978  inc     r10d
0x14002997b  cmp     r10d, [rdx+38h]
0x14002997f  jb      short loc_14002993F
0x140029981  jmp     short loc_1400299A3
0x140029983  lea     rcx, [r8+38h]
0x140029987  cmp     rcx, r9
0x14002998a  ja      short loc_140029973
0x14002998c  mov     r11b, 1
0x14002998f  mov     byte ptr [r8+rdx+9], 12h
0x140029995  jmp     short loc_140029973
0x140029997  mov     byte ptr [r8+rdx+9], 12h
0x14002999d  jmp     short loc_1400299A3
0x14002999f  mov     byte ptr [rdx+0Bh], 12h
0x1400299a3  mov     rax, [rbx+120h]
0x1400299aa  mov     ecx, [rsi+248h]
0x1400299b0  cmp     byte ptr [rax+2], 28h ; '('
0x1400299b4  jnz     short loc_1400299BB
0x1400299b6  mov     [rax+28h], ecx
0x1400299b9  jmp     short loc_1400299BE
0x1400299bb  mov     [rax+14h], ecx
0x1400299be  mov     rax, [rbx+120h]
0x1400299c5  cmp     byte ptr [rax+2], 28h ; '('
0x1400299c9  jnz     short loc_1400299D1
0x1400299cb  mov     [rax+40h], r15
0x1400299cf  jmp     short loc_1400299D5
0x1400299d1  mov     [rax+18h], r15
0x1400299d5  mov     rax, [rbx+120h]
0x1400299dc  cmp     byte ptr [rax+2], 28h ; '('
0x1400299e0  jnz     short loc_1400299E7
0x1400299e2  mov     [rax+3Ch], ebp
0x1400299e5  jmp     short loc_1400299EA
0x1400299e7  mov     [rax+10h], ebp
0x1400299ea  mov     rcx, [rbx+120h]
0x1400299f1  mov     eax, [rsi+250h]
0x1400299f7  or      eax, 188h
0x1400299fc  cmp     byte ptr [rcx+2], 28h ; '('
0x140029a00  jnz     short loc_140029A07
0x140029a02  mov     [rcx+18h], eax
0x140029a05  jmp     short loc_140029A0A
0x140029a07  mov     [rcx+0Ch], eax
0x140029a0a  mov     rdx, [rbx+120h]
0x140029a11  cmp     byte ptr [rdx+2], 28h ; '('
0x140029a15  jnz     loc_140029AC9
0x140029a1b  xor     r8d, r8d
0x140029a1e  cmp     [rdx+14h], r8d
0x140029a22  jnz     loc_140029ACD
0x140029a28  mov     edi, [rdx+38h]
0x140029a2b  test    edi, edi
0x140029a2d  jz      loc_140029ACD
0x140029a33  xor     r11d, r11d
0x140029a36  xor     sil, sil
0x140029a39  mov     ecx, [rdx+r11*4+78h]
0x140029a3e  cmp     ecx, 80h
0x140029a44  jb      short loc_140029AAE
0x140029a46  mov     r10d, [rdx+10h]
0x140029a4a  cmp     ecx, r10d
0x140029a4d  jnb     short loc_140029AAE
0x140029a4f  mov     r9d, ecx
0x140029a52  mov     ecx, [rcx+rdx]
0x140029a55  sub     ecx, 40h ; '@'
0x140029a58  jz      short loc_140029AA0
0x140029a5a  sub     ecx, 1
0x140029a5d  jz      short loc_140029A83
0x140029a5f  cmp     ecx, 1
0x140029a62  jnz     short loc_140029AA9
0x140029a64  lea     rcx, [r9+28h]
0x140029a68  cmp     rcx, r10
0x140029a6b  ja      short loc_140029AA9
0x140029a6d  lea     rcx, [rdx+20h]
0x140029a71  add     rcx, r9
0x140029a74  cmp     dword ptr [r9+rdx+0Ch], 0
0x140029a7a  cmovz   rcx, r8
0x140029a7e  mov     r8, rcx
0x140029a81  jmp     short loc_140029ACD
0x140029a83  lea     rcx, [r9+38h]
0x140029a87  cmp     rcx, r10
0x140029a8a  ja      short loc_140029AA9
0x140029a8c  cmp     byte ptr [r9+rdx+0Ah], 0
0x140029a92  jbe     short loc_140029ACD
0x140029a94  lea     r8, [rdx+18h]
0x140029a98  mov     sil, 1
0x140029a9b  add     r8, r9
0x140029a9e  jmp     short loc_140029AA9
0x140029aa0  lea     rcx, [r9+28h]
0x140029aa4  cmp     rcx, r10
0x140029aa7  jbe     short loc_140029AB8
0x140029aa9  test    sil, sil
0x140029aac  jnz     short loc_140029ACD
0x140029aae  inc     r11d
0x140029ab1  cmp     r11d, edi
0x140029ab4  jb      short loc_140029A39
0x140029ab6  jmp     short loc_140029ACD
0x140029ab8  cmp     byte ptr [r9+rdx+0Ah], 0
0x140029abe  jbe     short loc_140029ACD
0x140029ac0  lea     r8, [rdx+18h]
0x140029ac4  add     r8, r9
0x140029ac7  jmp     short loc_140029ACD
0x140029ac9  lea     r8, [rdx+48h]
0x140029acd  test    r8, r8
0x140029ad0  jz      short loc_140029B2A
0x140029ad2  mov     al, [r8+1]
0x140029ad6  and     al, 0F1h
0x140029ad8  mov     byte ptr [r8], 83h
0x140029adc  or      al, 11h
0x140029ade  mov     [r8+0Dh], bpl
0x140029ae2  mov     [r8+1], al
0x140029ae6  mov     al, [rsp+58h+arg_11]
0x140029aea  mov     [r8+0Ch], al
0x140029aee  mov     al, [rsp+58h+arg_12]
0x140029af2  mov     [r8+0Bh], al
0x140029af6  mov     al, [rsp+58h+arg_13]
0x140029afa  mov     [r8+0Ah], al
0x140029afe  mov     al, [rsp+58h+arg_28]
0x140029b05  mov     [r8+9], al
0x140029b09  mov     al, [rsp+58h+arg_29]
0x140029b10  mov     [r8+8], al
0x140029b14  mov     al, [rsp+58h+arg_2A]
0x140029b1b  mov     [r8+7], al
0x140029b1f  mov     al, [rsp+58h+arg_2B]
0x140029b26  mov     [r8+6], al
0x140029b2a  lea     rax, ClasspWriteUsingTokenTransferPacketDone
0x140029b31  mov     [rbx+0F0h], r15
0x140029b38  mov     [rbx+158h], rax
0x140029b3f  mov     [rbx+0F8h], ebp
  ... truncated ...
```
