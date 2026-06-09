# MRxSmb2CompleteBufferingStateChangeRequest

- ea: `0x140013fa0`
- end: `0x1400144b9`
- name: `MRxSmb2CompleteBufferingStateChangeRequest`
- size: `1305`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x14000ab50`
- `0x140013fa0`
- `0x140014650`
- `0x140014a00`
- `0x140017960`
- `0x1400297fc`
- `0x140029840`
- `0x140029cb0`
- `0x14002a1dc`
- `0x14002a9ac`
- `0x14002c8a0`
- `0x14002ce1c`
- `0x14002d3d0`
- `0x14002d518`
- `0x14002d630`
- `0x14002d694`
- `0x14002d71c`

## import_xrefs

- `rdbss!RxOrphanSrvOpen` at `0x14003b160`
- `rdbss!RxOrphanSrvOpen` at `0x14003b160`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003af8b`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003af8b`

## pseudocode

```c
__int64 __fastcall MRxSmb2CompleteBufferingStateChangeRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned __int8 v4; // r9
  int v5; // r13d
  __int64 v6; // rbp
  char v7; // r14
  __int64 v8; // rax
  _DWORD *v10; // r15
  _QWORD *v11; // rdx
  int v12; // esi
  int v13; // r14d
  int v14; // edi
  int v15; // esi
  __int64 v16; // rdi
  int v17; // r8d
  unsigned __int8 v18; // di
  __int64 v19; // rbp
  __int32 v20; // esi
  __int64 v21; // rax
  __int64 v22; // r15
  __int64 v23; // rbp
  __int64 result; // rax
  __int64 v25; // rax
  int v26; // r8d
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // rsi
  __int64 v32; // rax
  int v33; // ecx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rdi
  _QWORD *v38; // rax
  int v39; // eax
  int v40; // ebp
  _QWORD *v41; // rbp
  _QWORD *v42; // rcx
  int v43; // r9d
  _QWORD *v44; // rsi
  int v45; // r8d
  __int64 v46; // rax
  int v47; // ecx
  _QWORD *v48; // rax
  _QWORD *v49; // rcx
  int v50; // r8d
  unsigned int v51; // ebx
  char v52; // [rsp+48h] [rbp-70h]
  __int64 v53; // [rsp+60h] [rbp-58h]
  __int64 v54; // [rsp+68h] [rbp-50h]
  char v55; // [rsp+C0h] [rbp+8h]
  __int64 v56; // [rsp+C8h] [rbp+10h] BYREF
  int v57; // [rsp+D0h] [rbp+18h]
  __int64 v58; // [rsp+D8h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 56);
  v4 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 72);
  v7 = *(_BYTE *)(a1 + 464) & 4;
  v8 = *(_QWORD *)(a1 + 64);
  v10 = *(_DWORD **)(v3 + 136);
  v11 = (_QWORD *)*(unsigned int *)(a1 + 448);
  v58 = v3;
  v53 = v6;
  v54 = v8;
  v55 = 0;
  LOBYTE(v56) = v7;
  if ( v7 )
  {
    v12 = v10[16];
    v13 = v10[17];
    v14 = (unsigned __int8)v11 & 0x1F;
    v57 = v12;
    if ( (int)v11 >= 0 )
    {
      v11 = (_QWORD *)((unsigned int)v11 >> 5);
      v40 = (unsigned __int16)v11;
    }
    else
    {
      v14 = 0;
      v40 = -1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qdddd(WPP_GLOBAL_Control->AttachedDevice, 11, a3, v58, v12, v14, v13, v40);
      v4 = 0;
    }
    if ( (*(_BYTE *)(a1 + 464) & 8) != 0 )
    {
      v4 = 1;
      v40 = v13 + 1;
      v55 = 1;
      v14 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdd(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids,
          v58,
          v13 + 1,
          v13);
        v4 = 1;
      }
    }
    v15 = v14 & v12;
    if ( v13 == -1 || v40 == -1 || (unsigned __int16)(v40 - v13) <= 0x7FFFu && (_WORD)v40 != (_WORD)v13 )
    {
      v10[16] = v15;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v16 = v58;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v58);
          v4 = v55;
        }
      }
      else
      {
        v16 = v58;
      }
      if ( v13 != -1 )
      {
        v10[17] = v40;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v16);
          v4 = v55;
        }
      }
    }
    v17 = *(unsigned __int8 *)(a1 + 464);
    LOBYTE(v17) = v17 & 1;
    v18 = v17;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = v58;
    }
    else
    {
      v52 = v15;
      v3 = v58;
      WPP_SF_ddqDDDDdZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        v17,
        (unsigned __int8)v17,
        v4,
        v58,
        *(_DWORD *)(a1 + 456),
        *(_DWORD *)(a1 + 460),
        v57,
        v52,
        v40,
        *(_QWORD *)(a1 + 56) + 360LL);
      v4 = v55;
    }
    v6 = v53;
    v7 = v56;
  }
  else
  {
    v25 = *(_QWORD *)(v6 + 48);
    v26 = *(_DWORD *)(v25 + 24);
    *(_DWORD *)(v25 + 24) = (_DWORD)v11;
    v10[15] = (_DWORD)v11;
    v18 = *(_BYTE *)(a1 + 464) & 1;
    if ( v18 )
    {
      v39 = *(_DWORD *)(a1 + 456);
      if ( (v39 & 2) == 0 && (v39 & 0x10) == 0 && (v39 & 0x20) == 0 )
        v18 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dqDDDDZ(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v11,
        v26,
        v18,
        v3,
        *(_DWORD *)(a1 + 456),
        *(_DWORD *)(a1 + 460),
        v26,
        (char)v11,
        *(_QWORD *)(a1 + 56) + 360LL);
      v4 = 0;
    }
  }
  if ( !*(_DWORD *)(a1 + 460) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v3, v6);
    }
    v19 = *(_QWORD *)(*(_QWORD *)(v3 + 120) + 40LL);
    Smb2InvalidateFileInfoCacheEntry(a1, (struct _NAME_CACHE_CONTROL_ *)(v19 + 376));
    if ( v7 )
    {
      if ( *(_WORD *)v3 == 0xEC21 )
      {
        Smb2InvalidateDirInfoCacheEx(a1, 0, (struct _NAME_CACHE_CONTROL_ *)(v19 + 1112), 0, 1);
        Smb2InvalidateFileNotFoundCacheEx(a1, (struct _NAME_CACHE_CONTROL_ *)(v19 + 560), 0, 1);
        goto LABEL_28;
      }
      v20 = 0;
      v28 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 288LL);
      if ( v28 )
      {
        v29 = *(_QWORD *)(v28 + 136);
        if ( v29 )
          v20 = *(_DWORD *)(v29 + 88);
      }
    }
    else
    {
      v20 = 0;
      v21 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 288LL);
      if ( v21 )
      {
        v27 = *(_QWORD *)(v21 + 136);
        if ( v27 )
          v20 = *(_DWORD *)(v27 + 88);
      }
    }
    Smb2InvalidateSingleFileInDirInfoCache((_QWORD *)a1, (struct _NAME_CACHE_CONTROL_ *)(v19 + 1112));
    _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL) + 84LL), v20);
LABEL_28:
    v4 = v55;
  }
  if ( (*(_BYTE *)(a1 + 464) & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
    {
      v22 = v58;
    }
    else
    {
      v22 = v58;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v58);
    }
    v41 = (_QWORD *)(v22 + 264);
    v30 = (_QWORD *)(v22 + 264);
    do
    {
      v30 = (_QWORD *)*v30;
      if ( v30 == v41 )
        goto LABEL_52;
      v31 = v30 - 17;
    }
    while ( *((_WORD *)v30 - 68) == 0xEBAA );
    while ( 1 )
    {
LABEL_45:
      if ( !v31 )
      {
LABEL_111:
        v23 = v53;
        v4 = v55;
        *(_QWORD *)(a1 + 72) = v53;
        *(_QWORD *)(a1 + 64) = v54;
        goto LABEL_31;
      }
      if ( v7 )
      {
        if ( (v31[9] & 0x604) != 0 )
          goto LABEL_106;
        v32 = v31[6];
        if ( !v32 )
          goto LABEL_106;
        v33 = *(_DWORD *)(v32 + 4);
        if ( v33 == 3 || v33 >= 6 )
          goto LABEL_106;
        v34 = v31 + 23;
        *(_QWORD *)(a1 + 72) = v31;
        v11 = v31 + 23;
        while ( 1 )
        {
          v34 = (_QWORD *)*v34;
          if ( v34 == v11 )
            break;
          v42 = v34 - 14;
          if ( *((_WORD *)v34 - 56) != 0xEBAA )
            goto LABEL_97;
        }
        v42 = 0;
LABEL_97:
        *(_QWORD *)(a1 + 64) = v42;
      }
      v56 = 0;
      v43 = Smb2InitiateFlushLocks(a1, v11, &v56);
      if ( v43 == 259 )
        v43 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v56, 0, 0, 0);
      if ( v43 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqDZ(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          *(_QWORD *)(a1 + 72),
          v22,
          *(_QWORD *)(a1 + 72),
          v43,
          *(_QWORD *)(*(_QWORD *)(a1 + 72) + 80LL));
      }
      if ( !v7 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids);
        }
        goto LABEL_111;
      }
LABEL_106:
      v35 = v31 + 17;
      while ( 1 )
      {
        v35 = (_QWORD *)*v35;
        if ( v35 == v41 )
          break;
        v31 = v35 - 17;
        if ( *((_WORD *)v35 - 68) != 0xEBAA )
          goto LABEL_45;
      }
LABEL_52:
      v31 = 0;
    }
  }
  v22 = v58;
  v23 = v53;
LABEL_31:
  if ( !v18 && !v4 )
    return (unsigned int)v5;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids);
      v4 = v55;
    }
    v44 = (_QWORD *)(v22 + 264);
    v36 = (_QWORD *)(v22 + 264);
    do
    {
      v36 = (_QWORD *)*v36;
      if ( v36 == v44 )
        goto LABEL_59;
      v37 = v36 - 17;
    }
    while ( *((_WORD *)v36 - 68) == 0xEBAA );
    while ( 1 )
    {
LABEL_118:
      if ( !v37 )
      {
LABEL_153:
        *(_QWORD *)(a1 + 64) = v54;
        *(_QWORD *)(a1 + 72) = v23;
        return (unsigned int)v5;
      }
      v45 = *((_DWORD *)v37 + 18);
      if ( (v45 & 0x604) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v37, v45);
LABEL_147:
          v4 = v55;
        }
      }
      else
      {
        v46 = v37[6];
        if ( v46 )
        {
          v47 = *(_DWORD *)(v46 + 4);
          if ( v47 != 3 && v47 < 6 )
          {
            if ( v4 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v37);
              }
              RxOrphanSrvOpen(v37);
            }
            else
            {
              v48 = v37 + 23;
              *(_QWORD *)(a1 + 72) = v37;
              while ( 1 )
              {
                v48 = (_QWORD *)*v48;
                if ( v48 == v37 + 23 )
                  break;
                v49 = v48 - 14;
                if ( *((_WORD *)v48 - 56) != 0xEBAA )
                  goto LABEL_138;
              }
              v49 = 0;
LABEL_138:
              *(_QWORD *)(a1 + 64) = v49;
              v5 = AcknowledgeBreak(a1, 1);
              if ( v5 >= 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    24,
                    (unsigned int)WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids,
                    v22,
                    (char)v37,
                    v37[10]);
                }
                goto LABEL_153;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qqDZ(WPP_GLOBAL_Control->AttachedDevice, 25, v50, v22, (char)v37, v5, v37[10]);
              }
            }
            goto LABEL_147;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids);
          goto LABEL_147;
        }
      }
      v38 = v37 + 17;
      while ( 1 )
      {
        v38 = (_QWORD *)*v38;
        if ( v38 == v44 )
          break;
        v37 = v38 - 17;
        if ( *((_WORD *)v38 - 68) != 0xEBAA )
          goto LABEL_118;
      }
LABEL_59:
      v37 = 0;
    }
  }
  result = AcknowledgeBreak(a1, 0);
  v51 = result;
  if ( (int)result >= 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids, v22);
    return v51;
  }
  return result;
}

```

## disassembly

```asm
0x140013fa0  push    rbx
0x140013fa2  push    rbp
0x140013fa3  push    rsi
0x140013fa4  push    rdi
0x140013fa5  push    r12
0x140013fa7  push    r13
0x140013fa9  push    r14
0x140013fab  push    r15
0x140013fad  sub     rsp, 78h
0x140013fb1  mov     rsi, [rcx+38h]
0x140013fb5  xor     r9b, r9b
0x140013fb8  movzx   r14d, byte ptr [rcx+1D0h]
0x140013fc0  xor     r13d, r13d
0x140013fc3  mov     rbp, [rcx+48h]
0x140013fc7  and     r14b, 4
0x140013fcb  mov     rax, [rcx+40h]
0x140013fcf  mov     rbx, rcx
0x140013fd2  mov     r15, [rsi+88h]
0x140013fd9  mov     edx, [rcx+1C0h]
0x140013fdf  mov     [rsp+0B8h+arg_18], rsi
0x140013fe7  mov     [rsp+0B8h+var_58], rbp
0x140013fec  mov     [rsp+0B8h+var_50], rax
0x140013ff1  mov     [rsp+0B8h+arg_0], r9b
0x140013ff9  mov     byte ptr [rsp+0B8h+arg_8], r14b
0x140014001  jz      loc_1400141CB
0x140014007  mov     esi, [r15+40h]
0x14001400b  xor     eax, eax
0x14001400d  mov     r14d, [r15+44h]
0x140014011  mov     edi, edx
0x140014013  and     edi, 1Fh
0x140014016  mov     [rsp+0B8h+arg_10], esi
0x14001401d  test    edx, edx
0x14001401f  cmovs   edi, eax
0x140014022  js      loc_14001434F
0x140014028  shr     edx, 5
0x14001402b  movzx   ebp, dx
0x14001402e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014035  lea     r12, WPP_GLOBAL_Control
0x14001403c  cmp     rcx, r12
0x14001403f  jz      short loc_14001404E
0x140014041  test    dword ptr [rcx+2Ch], 200h
0x140014048  jnz     loc_140014359
0x14001404e  test    byte ptr [rbx+1D0h], 8
0x140014055  jnz     loc_14003AE4B
0x14001405b  and     esi, edi
0x14001405d  cmp     r14d, 0FFFFFFFFh
0x140014061  jz      short loc_14001407F
0x140014063  cmp     ebp, 0FFFFFFFFh
0x140014066  jz      short loc_14001407F
0x140014068  movzx   eax, bp
0x14001406b  mov     ecx, 7FFFh
0x140014070  sub     ax, r14w
0x140014074  cmp     ax, cx
0x140014077  ja      short loc_1400140C7
0x140014079  cmp     bp, r14w
0x14001407d  jz      short loc_1400140C7
0x14001407f  mov     [r15+40h], esi
0x140014083  mov     rcx, cs:WPP_GLOBAL_Control
0x14001408a  cmp     rcx, r12
0x14001408d  jz      short loc_14001409C
0x14001408f  test    dword ptr [rcx+2Ch], 200h
0x140014096  jnz     loc_140014392
0x14001409c  mov     rdi, [rsp+0B8h+arg_18]
0x1400140a4  cmp     r14d, 0FFFFFFFFh
0x1400140a8  jz      short loc_1400140C7
0x1400140aa  mov     [r15+44h], ebp
0x1400140ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140b5  cmp     rcx, r12
0x1400140b8  jz      short loc_1400140C7
0x1400140ba  test    dword ptr [rcx+2Ch], 200h
0x1400140c1  jnz     loc_1400143CA
0x1400140c7  movzx   r8d, byte ptr [rbx+1D0h]
0x1400140cf  and     r8b, 1
0x1400140d3  movzx   edi, r8b
0x1400140d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140de  cmp     rcx, r12
0x1400140e1  jz      short loc_1400140F0
0x1400140e3  test    dword ptr [rcx+2Ch], 200h
0x1400140ea  jnz     loc_14003AEB7
0x1400140f0  mov     rsi, [rsp+0B8h+arg_18]
0x1400140f8  mov     rbp, [rsp+0B8h+var_58]
0x1400140fd  movzx   r14d, byte ptr [rsp+0B8h+arg_8]
0x140014106  cmp     [rbx+1CCh], r13d
0x14001410d  jnz     short loc_140014184
0x14001410f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014116  cmp     rcx, r12
0x140014119  jz      short loc_140014128
0x14001411b  test    dword ptr [rcx+2Ch], 200h
0x140014122  jnz     loc_1400143FA
0x140014128  mov     rax, [rsi+78h]
0x14001412c  mov     rcx, rbx
0x14001412f  mov     rbp, [rax+28h]
0x140014133  lea     rdx, [rbp+178h]
0x14001413a  call    Smb2InvalidateFileInfoCacheEntry
0x14001413f  test    r14b, r14b
0x140014142  jnz     loc_140014426
0x140014148  mov     rcx, [rbx+38h]
0x14001414c  xor     esi, esi
0x14001414e  mov     rax, [rcx+120h]
0x140014155  test    rax, rax
0x140014158  jnz     loc_140014207
0x14001415e  lea     rdx, [rbp+458h]
0x140014165  mov     rcx, rbx
0x140014168  call    Smb2InvalidateSingleFileInDirInfoCache
0x14001416d  mov     rax, [rbx+38h]
0x140014171  mov     rcx, [rax+88h]
0x140014178  xchg    esi, [rcx+54h]
0x14001417b  movzx   r9d, [rsp+0B8h+arg_0]
0x140014184  test    byte ptr [rbx+1D0h], 2
0x14001418b  mov     r10d, 0EBAAh
0x140014191  jnz     loc_140014467
0x140014197  mov     r15, [rsp+0B8h+arg_18]
0x14001419f  mov     rbp, [rsp+0B8h+var_58]
0x1400141a4  test    dil, dil
0x1400141a7  jnz     loc_14003B04D
0x1400141ad  test    r9b, r9b
0x1400141b0  jnz     loc_14003B04D
0x1400141b6  mov     eax, r13d
0x1400141b9  add     rsp, 78h
0x1400141bd  pop     r15
0x1400141bf  pop     r14
0x1400141c1  pop     r13
0x1400141c3  pop     r12
0x1400141c5  pop     rdi
0x1400141c6  pop     rsi
0x1400141c7  pop     rbp
0x1400141c8  pop     rbx
0x1400141c9  retn
0x1400141cb  mov     rax, [rbp+30h]
0x1400141cf  mov     r8d, [rax+18h]
0x1400141d3  mov     [rax+18h], edx
0x1400141d6  mov     [r15+3Ch], edx
0x1400141da  movzx   edi, byte ptr [rcx+1D0h]
0x1400141e1  and     dil, 1
0x1400141e5  jnz     loc_140014328
0x1400141eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141f2  lea     r12, WPP_GLOBAL_Control
0x1400141f9  cmp     rcx, r12
0x1400141fc  jz      loc_140014106
0x140014202  jmp     loc_14003ADEE
0x140014207  mov     rdx, [rax+88h]
0x14001420e  test    rdx, rdx
0x140014211  jz      loc_14001415E
0x140014217  mov     rax, [rcx+88h]
0x14001421e  nop
0x14001421f  mov     esi, [rdx+58h]
0x140014222  nop
0x140014223  nop
0x140014224  mov     eax, [rax+54h]
0x140014227  nop
0x140014228  jmp     loc_14001415E
0x14001422d  mov     rdx, [rbx+38h]
0x140014231  xor     esi, esi
0x140014233  mov     rax, [rdx+120h]
0x14001423a  test    rax, rax
0x14001423d  jz      loc_14001415E
0x140014243  mov     rcx, [rax+88h]
0x14001424a  test    rcx, rcx
0x14001424d  jz      loc_14001415E
0x140014253  mov     rax, [rdx+88h]
0x14001425a  nop
0x14001425b  mov     esi, [rcx+58h]
0x14001425e  nop
0x14001425f  nop
0x140014260  mov     eax, [rax+54h]
0x140014263  nop
0x140014264  jmp     loc_14001415E
0x140014269  mov     rax, [rax]
0x14001426c  cmp     rax, rbp
0x14001426f  jz      short loc_1400142D2
0x140014271  lea     rsi, [rax-88h]
0x140014278  cmp     [rsi], r10w
0x14001427c  jz      short loc_140014269
0x14001427e  test    rsi, rsi
0x140014281  jz      loc_14003B02D
0x140014287  test    r14b, r14b
0x14001428a  jz      loc_14003AF59
0x140014290  test    dword ptr [rsi+48h], 604h
0x140014297  jnz     loc_14003AFEB
0x14001429d  mov     rax, [rsi+30h]
0x1400142a1  test    rax, rax
0x1400142a4  jz      loc_14003AFEB
0x1400142aa  mov     ecx, [rax+4]
0x1400142ad  cmp     ecx, 3
0x1400142b0  jz      loc_14003AFEB
0x1400142b6  cmp     ecx, 6
0x1400142b9  jge     loc_14003AFEB
0x1400142bf  lea     rax, [rsi+0B8h]
0x1400142c6  mov     [rbx+48h], rsi
0x1400142ca  mov     rdx, rax
0x1400142cd  jmp     loc_14003AF3E
0x1400142d2  xor     esi, esi
0x1400142d4  jmp     short loc_14001427E
0x1400142d6  mov     rax, [rax]
0x1400142d9  cmp     rax, rbp
0x1400142dc  jz      short loc_1400142D2
0x1400142de  lea     rsi, [rax-88h]
0x1400142e5  cmp     [rsi], r10w
0x1400142e9  jz      short loc_1400142D6
0x1400142eb  jmp     short loc_14001427E
0x1400142ed  mov     rax, [rax]
0x1400142f0  cmp     rax, rsi
0x1400142f3  jz      short loc_140014307
0x1400142f5  lea     rdi, [rax-88h]
0x1400142fc  cmp     [rdi], r10w
0x140014300  jz      short loc_1400142ED
0x140014302  jmp     loc_14003B0A4
0x140014307  xor     edi, edi
0x140014309  jmp     loc_14003B0A4
0x14001430e  mov     rax, [rax]
0x140014311  cmp     rax, rsi
0x140014314  jz      short loc_140014307
0x140014316  lea     rdi, [rax-88h]
0x14001431d  cmp     [rdi], r10w
0x140014321  jz      short loc_14001430E
0x140014323  jmp     loc_14003B0A4
0x140014328  mov     eax, [rcx+1C8h]
0x14001432e  test    al, 2
0x140014330  jnz     loc_1400141EB
0x140014336  test    al, 10h
0x140014338  jnz     loc_1400141EB
0x14001433e  test    al, 20h
0x140014340  movzx   edi, dil
0x140014344  mov     eax, r13d
0x140014347  cmovz   edi, eax
0x14001434a  jmp     loc_1400141EB
0x14001434f  mov     ebp, 0FFFFFFFFh
0x140014354  jmp     loc_14001402E
0x140014359  cmp     byte ptr [rcx+29h], 2
0x14001435d  jb      loc_14001404E
0x140014363  mov     r9, [rsp+0B8h+arg_18]
0x14001436b  mov     edx, 0Bh
0x140014370  mov     rcx, [rcx+18h]
0x140014374  mov     [rsp+0B8h+var_80], ebp
0x140014378  mov     dword ptr [rsp+0B8h+var_88], r14d
0x14001437d  mov     dword ptr [rsp+0B8h+var_90], edi
0x140014381  mov     dword ptr [rsp+0B8h+var_98], esi
0x140014385  call    WPP_SF_qdddd
0x14001438a  xor     r9b, r9b
0x14001438d  jmp     loc_14001404E
0x140014392  cmp     byte ptr [rcx+29h], 2
0x140014396  mov     rdi, [rsp+0B8h+arg_18]
0x14001439e  jb      loc_1400140A4
0x1400143a4  mov     rcx, [rcx+18h]
0x1400143a8  lea     r8, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids
0x1400143af  mov     edx, 0Dh
0x1400143b4  mov     r9, rdi
0x1400143b7  call    WPP_SF_q
0x1400143bc  movzx   r9d, [rsp+0B8h+arg_0]
0x1400143c5  jmp     loc_1400140A4
0x1400143ca  cmp     byte ptr [rcx+29h], 2
0x1400143ce  jb      loc_1400140C7
0x1400143d4  mov     rcx, [rcx+18h]
0x1400143d8  lea     r8, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids
0x1400143df  mov     edx, 0Eh
0x1400143e4  mov     r9, rdi
0x1400143e7  call    WPP_SF_q
0x1400143ec  movzx   r9d, [rsp+0B8h+arg_0]
0x1400143f5  jmp     loc_1400140C7
0x1400143fa  cmp     byte ptr [rcx+29h], 2
0x1400143fe  jb      loc_140014128
0x140014404  mov     rcx, [rcx+18h]
0x140014408  lea     r8, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids
0x14001440f  mov     edx, 10h
0x140014414  mov     [rsp+0B8h+var_98], rbp
0x140014419  mov     r9, rsi
0x14001441c  call    WPP_SF_qq
0x140014421  jmp     loc_140014128
0x140014426  mov     eax, 0EC21h
0x14001442b  cmp     [rsi], ax
0x14001442e  jnz     loc_14001422D
0x140014434  lea     r8, [rbp+458h]
0x14001443b  mov     byte ptr [rsp+0B8h+var_98], 1
0x140014440  xor     r9d, r9d
0x140014443  xor     edx, edx
0x140014445  mov     rcx, rbx
0x140014448  call    Smb2InvalidateDirInfoCacheEx
0x14001444d  lea     rdx, [rbp+230h]
0x140014454  mov     r9b, 1
0x140014457  xor     r8d, r8d
0x14001445a  mov     rcx, rbx
0x14001445d  call    Smb2InvalidateFileNotFoundCacheEx
0x140014462  jmp     loc_14001417B
0x140014467  mov     rcx, cs:WPP_GLOBAL_Control
0x14001446e  cmp     rcx, r12
0x140014471  jz      loc_14003AF27
0x140014477  test    dword ptr [rcx+2Ch], 200h
0x14001447e  jz      loc_14003AF27
0x140014484  cmp     byte ptr [rcx+29h], 2
0x140014488  mov     r15, [rsp+0B8h+arg_18]
0x140014490  jb      loc_14003AF2F
0x140014496  mov     rcx, [rcx+18h]
0x14001449a  lea     r8, WPP_5cd873fdf56f33ebee83fa79adc44f16_Traceguids
0x1400144a1  mov     edx, 11h
0x1400144a6  mov     r9, r15
0x1400144a9  call    WPP_SF_q
0x1400144ae  mov     r10d, 0EBAAh
0x1400144b4  jmp     loc_14003AF2F
0x14003adee  test    dword ptr [rcx+2Ch], 200h
0x14003adf5  jz      loc_140014106
  ... truncated ...
```
