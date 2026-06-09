# TransferPacketRetryTimerDpc

- ea: `0x140004300`
- end: `0x140004947`
- name: `TransferPacketRetryTimerDpc`
- size: `1607`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140004300`
- `0x140004950`
- `0x1400050a0`
- `0x14001f450`
- `0x14001fc38`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x140004406`
- `ntoskrnl!IoClearActivityIdThread` at `0x140004406`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140004367`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140004367`

## pseudocode

```c
void __fastcall TransferPacketRetryTimerDpc(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // rax
  __int64 v6; // rcx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v7; // r14
  bool v8; // di
  __int64 v9; // rdx
  __int64 v10; // rax
  char v11; // r8
  int v12; // ecx
  __int64 v13; // r8
  char v14; // r12
  char v15; // r13
  char v16; // r10
  unsigned __int8 v17; // r9
  unsigned int v18; // ebp
  __int64 v19; // r11
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // r15
  __int64 v23; // r14
  int v24; // ecx
  unsigned __int64 v25; // rcx
  unsigned int v26; // r15d
  __int64 v27; // rbp
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  __int64 v30; // r14
  __int64 v31; // r11
  int v32; // ecx
  unsigned __int64 v33; // rcx
  char v34; // r15
  _BYTE *v35; // rdx
  _BYTE *v36; // rcx
  _BYTE *v37; // rax
  unsigned int v38; // eax
  bool v39; // cc
  char *v40; // r9
  unsigned __int64 v41; // rcx
  char v42; // r9
  unsigned int v43; // r11d
  __int64 v44; // rbp
  __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  __int64 v47; // r14
  __int64 v48; // r10
  int v49; // ecx
  unsigned __int64 v50; // rcx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  _SENSE_DATA *v54; // r8
  unsigned int v55; // ebp
  __int64 v56; // rsi
  __int64 v57; // rcx
  unsigned __int64 v58; // r9
  int v59; // r10d
  __int64 v60; // r11
  unsigned __int64 v61; // rcx
  __int64 v62; // rdx
  char *v63; // r9
  unsigned int v64; // ebp
  __int64 i; // r10
  __int64 v66; // rcx
  unsigned __int64 v67; // r11
  __int64 v68; // r8
  __int64 v69; // rsi
  int v70; // ecx
  unsigned __int64 v71; // rcx
  int v72; // r10d
  int v73; // ecx
  __int64 v74; // rdx
  unsigned int v75; // esi
  __int64 v76; // r8
  __int64 v77; // rcx
  unsigned __int64 v78; // r9
  __int64 v79; // r11
  __int64 v80; // r10
  int v81; // ecx
  int v82; // ecx
  unsigned __int64 v83; // rcx
  __int128 *v84; // [rsp+60h] [rbp-58h] BYREF
  struct _FUNCTIONAL_DEVICE_EXTENSION *v85; // [rsp+68h] [rbp-50h]
  __int128 v86; // [rsp+70h] [rbp-48h] BYREF

  v4 = *((_QWORD *)DeferredContext + 5);
  v84 = 0;
  v6 = *((_QWORD *)DeferredContext + 4);
  v86 = 0;
  v7 = *(struct _FUNCTIONAL_DEVICE_EXTENSION **)(v4 + 64);
  v84 = &v86;
  v85 = v7;
  v8 = (int)IoPropagateActivityIdToThread(v6, DeferredContext + 328, &v84) >= 0;
  if ( ClassPnPETWEnabled )
  {
    v13 = *((_QWORD *)DeferredContext + 36);
    v14 = 0;
    v15 = 0;
    v16 = *(_BYTE *)(v13 + 2);
    if ( v16 == 40 )
    {
      v17 = 0;
      if ( !*(_DWORD *)(v13 + 20) )
      {
        v18 = *(_DWORD *)(v13 + 56);
        if ( v18 )
        {
          v19 = 0;
          while ( 1 )
          {
            v20 = *(unsigned int *)(v13 + 4 * v19 + 120);
            if ( (unsigned int)v20 < 0x80 )
              goto LABEL_18;
            v21 = *(unsigned int *)(v13 + 16);
            if ( (unsigned int)v20 >= (unsigned int)v21 )
              goto LABEL_18;
            v22 = v20 + v13;
            v23 = (unsigned int)v20;
            v24 = *(_DWORD *)(v20 + v13);
            if ( v24 == 64 )
              goto LABEL_16;
            v51 = v24 - 65;
            if ( v51 )
              break;
            v25 = v23 + 56;
LABEL_17:
            if ( v25 <= v21 )
            {
              v17 = *(_BYTE *)(v22 + 9);
              goto LABEL_19;
            }
LABEL_18:
            v19 = (unsigned int)(v19 + 1);
            if ( (unsigned int)v19 >= v18 )
              goto LABEL_19;
          }
          if ( v51 != 1 )
            goto LABEL_18;
LABEL_16:
          v25 = v23 + 40;
          goto LABEL_17;
        }
LABEL_19:
        if ( !*(_DWORD *)(v13 + 20) )
        {
          v26 = *(_DWORD *)(v13 + 56);
          if ( v26 )
          {
            v27 = 0;
            do
            {
              v28 = *(unsigned int *)(v13 + 4 * v27 + 120);
              if ( (unsigned int)v28 < 0x80 )
                goto LABEL_27;
              v29 = *(unsigned int *)(v13 + 16);
              if ( (unsigned int)v28 >= (unsigned int)v29 )
                goto LABEL_27;
              v30 = v28 + v13;
              v31 = (unsigned int)v28;
              v32 = *(_DWORD *)(v28 + v13);
              if ( v32 == 64 )
              {
                v33 = v31 + 40;
              }
              else
              {
                v52 = v32 - 65;
                if ( v52 )
                {
                  if ( v52 == 1 && v31 + 40 <= v29 )
                  {
                    v35 = *(_BYTE **)(v30 + 24);
                    goto LABEL_30;
                  }
                  goto LABEL_27;
                }
                v33 = v31 + 56;
              }
              if ( v33 <= v29 )
              {
                v35 = *(_BYTE **)(v30 + 16);
                goto LABEL_30;
              }
LABEL_27:
              v27 = (unsigned int)(v27 + 1);
            }
            while ( (unsigned int)v27 < v26 );
          }
        }
      }
    }
    else
    {
      v35 = *(_BYTE **)(v13 + 32);
      v17 = *(_BYTE *)(v13 + 11);
LABEL_30:
      if ( v35 && v17 )
      {
        v36 = &v35[v17];
        v37 = v35 + 8;
        if ( (unsigned __int8)((*v35 & 0x7F) - 114) <= 1u )
        {
          if ( v37 <= v36 )
          {
            v34 = v35[2];
            v15 = v35[1] & 0xF;
            v14 = v35[3];
            goto LABEL_40;
          }
        }
        else if ( v37 <= v36 )
        {
          v38 = v17;
          v15 = v35[2] & 0xF;
          v39 = (unsigned int)(unsigned __int8)v35[7] + 8 <= v17;
          v40 = v35 + 13;
          if ( v39 )
            v38 = (unsigned __int8)v35[7] + 8;
          v41 = (unsigned __int64)&v35[v38];
          if ( (unsigned __int64)v40 <= v41 )
            v34 = v35[12];
          else
            v34 = 0;
          if ( (unsigned __int64)(v35 + 14) <= v41 )
            v14 = *v40;
          goto LABEL_40;
        }
      }
    }
    v34 = 0;
LABEL_40:
    if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) == 0 )
    {
      v7 = v85;
      goto LABEL_2;
    }
    if ( v16 != 40 )
    {
      v42 = *(_BYTE *)(v13 + 4);
      goto LABEL_43;
    }
    v42 = 0;
    if ( *(_DWORD *)(v13 + 20) || (v43 = *(_DWORD *)(v13 + 56)) == 0 )
    {
LABEL_43:
      v7 = v85;
      McTemplateK0qpqduuuuu_EtwWriteTransfer(
        v85->PrivateFdoData->MaxNumberOfIoRetries - (unsigned __int8)DeferredContext[57],
        *((_QWORD *)DeferredContext + 4),
        (_DWORD)DeferredContext + 328,
        v85->DeviceNumber,
        *((_QWORD *)DeferredContext + 4),
        v85->PrivateFdoData->MaxNumberOfIoRetries - DeferredContext[57],
        *(_DWORD *)(*((_QWORD *)DeferredContext + 4) + 48LL),
        *(_BYTE *)(v13 + 3),
        v42,
        v15,
        v34,
        v14);
      goto LABEL_2;
    }
    v44 = 0;
    while ( 1 )
    {
      v45 = *(unsigned int *)(v13 + 4 * v44 + 120);
      if ( (unsigned int)v45 < 0x80 )
        goto LABEL_52;
      v46 = *(unsigned int *)(v13 + 16);
      if ( (unsigned int)v45 >= (unsigned int)v46 )
        goto LABEL_52;
      v47 = v13 + v45;
      v48 = (unsigned int)v45;
      v49 = *(_DWORD *)(v13 + v45);
      if ( v49 == 64 )
        goto LABEL_50;
      v53 = v49 - 65;
      if ( v53 )
        break;
      v50 = v48 + 56;
LABEL_51:
      if ( v50 <= v46 )
      {
        v42 = *(_BYTE *)(v47 + 8);
        goto LABEL_43;
      }
LABEL_52:
      v44 = (unsigned int)(v44 + 1);
      if ( (unsigned int)v44 >= v43 )
        goto LABEL_43;
    }
    if ( v53 != 1 )
      goto LABEL_52;
LABEL_50:
    v50 = v48 + 40;
    goto LABEL_51;
  }
LABEL_2:
  v9 = *((_QWORD *)DeferredContext + 36);
  v10 = 24;
  v11 = *(_BYTE *)(v9 + 2);
  if ( v11 != 40 )
    v10 = 12;
  v12 = *(_DWORD *)(v10 + v9);
  if ( (v12 & 0x200000) != 0 && (v12 & 0x400) != 0 )
  {
    if ( v11 != 40 )
    {
      v54 = *(_SENSE_DATA **)(v9 + 32);
      goto LABEL_85;
    }
    v54 = 0;
    if ( !*(_DWORD *)(v9 + 20) )
    {
      v55 = *(_DWORD *)(v9 + 56);
      if ( v55 )
      {
        v56 = 0;
        do
        {
          v57 = *(unsigned int *)(v9 + 4 * v56 + 120);
          if ( (unsigned int)v57 < 0x80 )
            goto LABEL_81;
          v58 = *(unsigned int *)(v9 + 16);
          if ( (unsigned int)v57 >= (unsigned int)v58 )
            goto LABEL_81;
          v59 = *(_DWORD *)(v9 + v57);
          v60 = v9 + v57;
          if ( v59 == 64 )
          {
            v61 = v57 + 40;
          }
          else
          {
            v72 = v59 - 65;
            if ( v72 )
            {
              if ( v72 == 1 && v57 + 40 <= v58 )
              {
                v54 = *(_SENSE_DATA **)(v60 + 24);
                break;
              }
              goto LABEL_81;
            }
            v61 = v57 + 56;
          }
          if ( v61 <= v58 )
          {
            v54 = *(_SENSE_DATA **)(v60 + 16);
            break;
          }
LABEL_81:
          v56 = (unsigned int)(v56 + 1);
        }
        while ( (unsigned int)v56 < v55 );
      }
    }
LABEL_85:
    if ( v54 == v7->SenseData )
      goto LABEL_6;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_b5ce07307f52390d5b0d6953034364b3_Traceguids, DeferredContext);
    }
    FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(v7);
    v62 = *((_QWORD *)DeferredContext + 36);
    v63 = DeferredContext + 264;
    if ( *(_BYTE *)(v62 + 2) != 40 )
    {
      *(_QWORD *)(v62 + 32) = v63;
      goto LABEL_108;
    }
    if ( !*(_DWORD *)(v62 + 20) )
    {
      v64 = *(_DWORD *)(v62 + 56);
      for ( i = 0; (unsigned int)i < v64; i = (unsigned int)(i + 1) )
      {
        v66 = *(unsigned int *)(v62 + 4 * i + 120);
        if ( (unsigned int)v66 < 0x80 )
          continue;
        v67 = *(unsigned int *)(v62 + 16);
        if ( (unsigned int)v66 >= (unsigned int)v67 )
          continue;
        v68 = v62 + v66;
        v69 = (unsigned int)v66;
        v70 = *(_DWORD *)(v62 + v66);
        if ( v70 == 64 )
        {
          v71 = v69 + 40;
        }
        else
        {
          v73 = v70 - 65;
          if ( v73 )
          {
            if ( v73 == 1 && v69 + 40 <= v67 )
            {
              *(_QWORD *)(v68 + 24) = v63;
              break;
            }
            continue;
          }
          v71 = v69 + 56;
        }
        if ( v71 <= v67 )
        {
          *(_QWORD *)(v68 + 16) = v63;
          break;
        }
      }
    }
LABEL_108:
    v74 = *((_QWORD *)DeferredContext + 36);
    if ( *(_BYTE *)(v74 + 2) != 40 )
    {
      *(_BYTE *)(v74 + 11) = 18;
      goto LABEL_6;
    }
    if ( *(_DWORD *)(v74 + 20) )
      goto LABEL_6;
    v75 = *(_DWORD *)(v74 + 56);
    v76 = 0;
    if ( !v75 )
      goto LABEL_6;
    while ( 1 )
    {
      v77 = *(unsigned int *)(v74 + 4 * v76 + 120);
      if ( (unsigned int)v77 < 0x80 )
        goto LABEL_124;
      v78 = *(unsigned int *)(v74 + 16);
      if ( (unsigned int)v77 >= (unsigned int)v78 )
        goto LABEL_124;
      v79 = v74 + v77;
      v80 = (unsigned int)v77;
      v81 = *(_DWORD *)(v74 + v77);
      if ( v81 == 64 )
        break;
      v82 = v81 - 65;
      if ( !v82 )
      {
        v83 = v80 + 56;
        goto LABEL_123;
      }
      if ( v82 == 1 && v80 + 40 <= v78 )
      {
LABEL_117:
        *(_BYTE *)(v79 + 9) = 18;
        goto LABEL_6;
      }
LABEL_124:
      v76 = (unsigned int)(v76 + 1);
      if ( (unsigned int)v76 >= v75 )
        goto LABEL_6;
    }
    v83 = v80 + 40;
LABEL_123:
    if ( v83 <= v78 )
      goto LABEL_117;
    goto LABEL_124;
  }
LABEL_6:
  *(_OWORD *)(DeferredContext + 264) = 0;
  *((_WORD *)DeferredContext + 140) = 0;
  SubmitTransferPacket(DeferredContext);
  if ( v8 )
    IoClearActivityIdThread(v84);
}

```

## disassembly

```asm
0x140004300  mov     r11, rsp
0x140004303  sub     rsp, 0B8h
0x14000430a  mov     rax, cs:__security_cookie
0x140004311  xor     rax, rsp
0x140004314  mov     [rsp+0B8h+var_38], rax
0x14000431c  mov     rax, [rdx+28h]
0x140004320  lea     r8, [r11-58h]
0x140004324  mov     [r11+8], rbx
0x140004328  xorps   xmm0, xmm0
0x14000432b  mov     [r11+18h], rbp
0x14000432f  mov     rbx, rdx
0x140004332  mov     [r11+20h], rsi
0x140004336  add     rdx, 148h
0x14000433d  mov     qword ptr [r11-58h], 0
0x140004345  mov     [r11-8], rdi
0x140004349  mov     rcx, [rbx+20h]
0x14000434d  mov     [r11-20h], r14
0x140004351  movups  [rsp+0B8h+var_48], xmm0
0x140004356  mov     r14, [rax+40h]
0x14000435a  lea     rax, [r11-48h]
0x14000435e  mov     [r11-58h], rax
0x140004362  mov     [rsp+0B8h+var_50], r14
0x140004367  call    cs:__imp_IoPropagateActivityIdToThread
0x14000436e  nop     dword ptr [rax+rax+00h]
0x140004373  mov     edi, eax
0x140004375  shr     edi, 1Fh
0x140004378  xor     dil, 1
0x14000437c  cmp     cs:ClassPnPETWEnabled, 0
0x140004383  jnz     loc_14000442B
0x140004389  mov     rdx, [rbx+120h]
0x140004390  mov     ecx, 0Ch
0x140004395  mov     eax, 18h
0x14000439a  movzx   r8d, byte ptr [rdx+2]
0x14000439f  cmp     r8b, 28h ; '('
0x1400043a3  cmovnz  eax, ecx
0x1400043a6  mov     ecx, [rax+rdx]
0x1400043a9  bt      ecx, 15h
0x1400043ad  jnb     short loc_1400043B9
0x1400043af  bt      ecx, 0Ah
0x1400043b3  jb      loc_140004710
0x1400043b9  mov     eax, 108h
0x1400043be  xorps   xmm0, xmm0
0x1400043c1  xor     edx, edx
0x1400043c3  mov     rcx, rbx
0x1400043c6  movups  xmmword ptr [rbx+rax], xmm0
0x1400043ca  mov     [rbx+rax+10h], dx
0x1400043cf  call    SubmitTransferPacket
0x1400043d4  mov     r14, [rsp+0B8h+var_20]
0x1400043dc  test    dil, dil
0x1400043df  mov     rdi, [rsp+0B8h+var_8]
0x1400043e7  mov     rsi, [rsp+0B8h+arg_18]
0x1400043ef  mov     rbp, [rsp+0B8h+arg_10]
0x1400043f7  mov     rbx, [rsp+0B8h+arg_0]
0x1400043ff  jz      short loc_140004412
0x140004401  mov     rcx, [rsp+0B8h+var_58]
0x140004406  call    cs:__imp_IoClearActivityIdThread
0x14000440d  nop     dword ptr [rax+rax+00h]
0x140004412  mov     rcx, [rsp+0B8h+var_38]
0x14000441a  xor     rcx, rsp; StackCookie
0x14000441d  call    __security_check_cookie
0x140004422  add     rsp, 0B8h
0x140004429  retn
0x14000442b  mov     r8, [rbx+120h]
0x140004432  mov     [rsp+0B8h+var_10], r12
0x14000443a  xor     r12b, r12b
0x14000443d  mov     [rsp+0B8h+var_18], r13
0x140004445  xor     r13b, r13b
0x140004448  mov     [rsp+0B8h+var_28], r15
0x140004450  movzx   r10d, byte ptr [r8+2]
0x140004455  cmp     r10b, 28h ; '('
0x140004459  jnz     loc_140004508
0x14000445f  xor     r9b, r9b
0x140004462  cmp     dword ptr [r8+14h], 0
0x140004467  jnz     loc_140004503
0x14000446d  mov     ebp, [r8+38h]
0x140004471  test    ebp, ebp
0x140004473  jz      short loc_1400044B5
0x140004475  xor     r11d, r11d
0x140004478  mov     ecx, [r8+r11*4+78h]
0x14000447d  cmp     ecx, 80h
0x140004483  jb      short loc_1400044AD
0x140004485  mov     edx, [r8+10h]
0x140004489  cmp     ecx, edx
0x14000448b  jnb     short loc_1400044AD
0x14000448d  lea     r15, [rcx+r8]
0x140004491  mov     r14d, ecx
0x140004494  mov     ecx, [r15]
0x140004497  cmp     ecx, 40h ; '@'
0x14000449a  jnz     loc_14000465E
0x1400044a0  lea     rcx, [r14+28h]
0x1400044a4  cmp     rcx, rdx
0x1400044a7  jbe     loc_1400046AD
0x1400044ad  inc     r11d
0x1400044b0  cmp     r11d, ebp
0x1400044b3  jb      short loc_140004478
0x1400044b5  cmp     dword ptr [r8+14h], 0
0x1400044ba  jnz     short loc_140004503
0x1400044bc  mov     r15d, [r8+38h]
0x1400044c0  test    r15d, r15d
0x1400044c3  jz      short loc_140004503
0x1400044c5  xor     ebp, ebp
0x1400044c7  mov     ecx, [r8+rbp*4+78h]
0x1400044cc  cmp     ecx, 80h
0x1400044d2  jb      short loc_1400044FC
0x1400044d4  mov     edx, [r8+10h]
0x1400044d8  cmp     ecx, edx
0x1400044da  jnb     short loc_1400044FC
0x1400044dc  lea     r14, [rcx+r8]
0x1400044e0  mov     r11d, ecx
0x1400044e3  mov     ecx, [r14]
0x1400044e6  cmp     ecx, 40h ; '@'
0x1400044e9  jnz     loc_140004675
0x1400044ef  lea     rcx, [r11+28h]
0x1400044f3  cmp     rcx, rdx
0x1400044f6  jbe     loc_1400046B7
0x1400044fc  inc     ebp
0x1400044fe  cmp     ebp, r15d
0x140004501  jb      short loc_1400044C7
0x140004503  xor     r15b, r15b
0x140004506  jmp     short loc_140004575
0x140004508  mov     rdx, [r8+20h]
0x14000450c  movzx   r9d, byte ptr [r8+0Bh]
0x140004511  test    rdx, rdx
0x140004514  jz      short loc_140004503
0x140004516  test    r9b, r9b
0x140004519  jz      short loc_140004503
0x14000451b  movzx   eax, byte ptr [rdx]
0x14000451e  and     al, 7Fh
0x140004520  movzx   ecx, r9b
0x140004524  sub     al, 72h ; 'r'
0x140004526  add     rcx, rdx
0x140004529  cmp     al, 1
0x14000452b  lea     rax, [rdx+8]
0x14000452f  jbe     loc_1400046CA
0x140004535  cmp     rax, rcx
0x140004538  ja      short loc_140004503
0x14000453a  movzx   ecx, byte ptr [rdx+7]
0x14000453e  movzx   r13d, byte ptr [rdx+2]
0x140004543  add     ecx, 8
0x140004546  movzx   eax, r9b
0x14000454a  and     r13b, 0Fh
0x14000454e  cmp     ecx, eax
0x140004550  lea     r9, [rdx+0Dh]
0x140004554  cmovbe  eax, ecx
0x140004557  mov     ecx, eax
0x140004559  add     rcx, rdx
0x14000455c  cmp     r9, rcx
0x14000455f  jbe     loc_1400046EB
0x140004565  xor     r15b, r15b
0x140004568  lea     rax, [rdx+0Eh]
0x14000456c  cmp     rax, rcx
0x14000456f  jbe     loc_1400046F5
0x140004575  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 40h
0x14000457c  jz      loc_140004859
0x140004582  cmp     r10b, 28h ; '('
0x140004586  jz      short loc_140004607
0x140004588  movzx   r9d, byte ptr [r8+4]
0x14000458d  mov     rdx, [rbx+20h]
0x140004591  mov     r14, [rsp+0B8h+var_50]
0x140004596  mov     [rsp+0B8h+var_60], r12b
0x14000459b  mov     [rsp+0B8h+var_68], r15b
0x1400045a0  mov     [rsp+0B8h+var_70], r13b
0x1400045a5  mov     rax, [r14+478h]
0x1400045ac  mov     [rsp+0B8h+var_78], r9b
0x1400045b1  mov     r9d, [r14+24Ch]
0x1400045b8  movzx   ecx, byte ptr [rax+294h]
0x1400045bf  movzx   eax, byte ptr [rbx+39h]
0x1400045c3  sub     ecx, eax
0x1400045c5  movzx   eax, byte ptr [r8+3]
0x1400045ca  mov     [rsp+0B8h+var_80], al
0x1400045ce  lea     r8, [rbx+148h]
0x1400045d5  mov     eax, [rdx+30h]
0x1400045d8  mov     [rsp+0B8h+var_88], eax
0x1400045dc  mov     [rsp+0B8h+var_90], ecx
0x1400045e0  mov     [rsp+0B8h+var_98], rdx
0x1400045e5  call    McTemplateK0qpqduuuuu_EtwWriteTransfer
0x1400045ea  mov     r15, [rsp+0B8h+var_28]
0x1400045f2  mov     r12, [rsp+0B8h+var_10]
0x1400045fa  mov     r13, [rsp+0B8h+var_18]
0x140004602  jmp     loc_140004389
0x140004607  xor     r9b, r9b
0x14000460a  cmp     dword ptr [r8+14h], 0
0x14000460f  jnz     loc_14000458D
0x140004615  mov     r11d, [r8+38h]
0x140004619  test    r11d, r11d
0x14000461c  jz      loc_14000458D
0x140004622  xor     ebp, ebp
0x140004624  mov     ecx, [r8+rbp*4+78h]
0x140004629  cmp     ecx, 80h
0x14000462f  jb      short loc_140004651
0x140004631  mov     edx, [r8+10h]
0x140004635  cmp     ecx, edx
0x140004637  jnb     short loc_140004651
0x140004639  lea     r14, [r8+rcx]
0x14000463d  mov     r10d, ecx
0x140004640  mov     ecx, [r14]
0x140004643  cmp     ecx, 40h ; '@'
0x140004646  jnz     short loc_14000469D
0x140004648  lea     rcx, [r10+28h]
0x14000464c  cmp     rcx, rdx
0x14000464f  jbe     short loc_1400046C0
0x140004651  inc     ebp
0x140004653  cmp     ebp, r11d
0x140004656  jnb     loc_14000458D
0x14000465c  jmp     short loc_140004624
0x14000465e  sub     ecx, 41h ; 'A'
0x140004661  jz      loc_1400046FE
0x140004667  cmp     ecx, 1
0x14000466a  jnz     loc_1400044AD
0x140004670  jmp     loc_1400044A0
0x140004675  sub     ecx, 41h ; 'A'
0x140004678  jz      loc_140004707
0x14000467e  cmp     ecx, 1
0x140004681  jnz     loc_1400044FC
0x140004687  lea     rcx, [r11+28h]
0x14000468b  cmp     rcx, rdx
0x14000468e  ja      loc_1400044FC
0x140004694  mov     rdx, [r14+18h]
0x140004698  jmp     loc_140004511
0x14000469d  sub     ecx, 41h ; 'A'
0x1400046a0  jz      loc_140004764
0x1400046a6  cmp     ecx, 1
0x1400046a9  jnz     short loc_140004651
0x1400046ab  jmp     short loc_140004648
0x1400046ad  movzx   r9d, byte ptr [r15+9]
0x1400046b2  jmp     loc_1400044B5
0x1400046b7  mov     rdx, [r14+10h]
0x1400046bb  jmp     loc_140004511
0x1400046c0  movzx   r9d, byte ptr [r14+8]
0x1400046c5  jmp     loc_14000458D
0x1400046ca  cmp     rax, rcx
0x1400046cd  ja      loc_140004503
0x1400046d3  movzx   r13d, byte ptr [rdx+1]
0x1400046d8  movzx   r15d, byte ptr [rdx+2]
0x1400046dd  and     r13b, 0Fh
0x1400046e1  movzx   r12d, byte ptr [rdx+3]
0x1400046e6  jmp     loc_140004575
0x1400046eb  movzx   r15d, byte ptr [rdx+0Ch]
0x1400046f0  jmp     loc_140004568
0x1400046f5  movzx   r12d, byte ptr [r9]
0x1400046f9  jmp     loc_140004575
0x1400046fe  lea     rcx, [r14+38h]
0x140004702  jmp     loc_1400044A4
0x140004707  lea     rcx, [r11+38h]
0x14000470b  jmp     loc_1400044F3
0x140004710  cmp     r8b, 28h ; '('
0x140004714  jnz     short loc_14000476D
0x140004716  xor     r8d, r8d
0x140004719  cmp     [rdx+14h], r8d
0x14000471d  jnz     short loc_140004771
0x14000471f  mov     ebp, [rdx+38h]
0x140004722  test    ebp, ebp
0x140004724  jz      short loc_140004771
0x140004726  xor     esi, esi
0x140004728  mov     ecx, [rdx+rsi*4+78h]
0x14000472c  cmp     ecx, 80h
0x140004732  jb      short loc_14000475C
0x140004734  mov     r9d, [rdx+10h]
0x140004738  cmp     ecx, r9d
0x14000473b  jnb     short loc_14000475C
0x14000473d  mov     r10d, [rdx+rcx]
0x140004741  lea     r11, [rdx+rcx]
0x140004745  cmp     r10d, 40h ; '@'
0x140004749  jnz     loc_14000482A
0x14000474f  add     rcx, 28h ; '('
0x140004753  cmp     rcx, r9
0x140004756  jbe     loc_140004850
0x14000475c  inc     esi
0x14000475e  cmp     esi, ebp
0x140004760  jb      short loc_140004728
0x140004762  jmp     short loc_140004771
0x140004764  lea     rcx, [r10+38h]
0x140004768  jmp     loc_14000464C
0x14000476d  mov     r8, [rdx+20h]
0x140004771  cmp     r8, [r14+240h]
0x140004778  jz      loc_1400043B9
0x14000477e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004785  lea     rax, WPP_GLOBAL_Control
0x14000478c  cmp     rcx, rax
0x14000478f  jz      short loc_1400047B6
0x140004791  mov     eax, [rcx+2Ch]
0x140004794  test    al, 8
0x140004796  jz      short loc_1400047B6
0x140004798  cmp     byte ptr [rcx+29h], 4
0x14000479c  jb      short loc_1400047B6
0x14000479e  mov     rcx, [rcx+18h]
0x1400047a2  lea     r8, WPP_b5ce07307f52390d5b0d6953034364b3_Traceguids
0x1400047a9  mov     edx, 0Dh
0x1400047ae  mov     r9, rbx
0x1400047b1  call    WPP_SF_q
0x1400047b6  mov     rdx, [rbx+120h]
0x1400047bd  mov     rcx, r14; FdoExtension
0x1400047c0  call    FREE_PORT_ALLOCATED_SENSE_BUFFER_EX
0x1400047c5  mov     rdx, [rbx+120h]
0x1400047cc  lea     r9, [rbx+108h]
0x1400047d3  cmp     byte ptr [rdx+2], 28h ; '('
0x1400047d7  jnz     loc_140004935
0x1400047dd  cmp     dword ptr [rdx+14h], 0
0x1400047e1  jnz     loc_14000488B
0x1400047e7  mov     ebp, [rdx+38h]
  ... truncated ...
```
