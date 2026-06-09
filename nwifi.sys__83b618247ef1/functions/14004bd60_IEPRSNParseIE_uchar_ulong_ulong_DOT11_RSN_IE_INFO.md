# IEPRSNParseIE(uchar *,ulong,ulong *,DOT11_RSN_IE_INFO *)

- ea: `0x14004bd60`
- end: `0x14004c4ee`
- name: `?IEPRSNParseIE@@YAJPEAEKPEAKPEAUDOT11_RSN_IE_INFO@@@Z`
- size: `1934`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, unsigned int *, struct DOT11_RSN_IE_INFO *)`
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14003a5f4`
- `0x140040f40`
- `0x14004113c`
- `0x14004a0bc`
- `0x14004a7fc`
- `0x140051d54`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x14003ff10`
- `0x140047a40`
- `0x14004b9b8`
- `0x14004bacc`
- `0x14004bb20`
- `0x14004bc0c`
- `0x14004bd60`
- `0x14004c4f4`
- `0x14004f63c`
- `0x140052710`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004bf87`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c18c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c3ca`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004bf87`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c18c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004c3ca`
- `ntoskrnl!ExAllocatePool2` at `0x14004bfa2`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1aa`
- `ntoskrnl!ExAllocatePool2` at `0x14004c3e8`
- `ntoskrnl!ExAllocatePool2` at `0x14004bfa2`
- `ntoskrnl!ExAllocatePool2` at `0x14004c1aa`
- `ntoskrnl!ExAllocatePool2` at `0x14004c3e8`

## pseudocode

```c
__int64 __fastcall IEPRSNParseIE(unsigned __int8 *a1, int a2, unsigned int *a3, struct DOT11_RSN_IE_INFO *a4)
{
  struct DOT11_RSN_IE_INFO *v6; // rsi
  _QWORD *v7; // r15
  int v8; // eax
  int v9; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  char v13; // r13
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  PDEVICE_OBJECT v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int16 v19; // bp
  unsigned __int16 v20; // ax
  __int64 v21; // r9
  unsigned int v22; // edi
  unsigned int v23; // r13d
  unsigned int v24; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  char *v27; // r14
  enum RSNA_CIPHER_SUITE *v28; // r12
  int IsEnabledDeviceUsageNoInline; // eax
  int v30; // r10d
  unsigned __int16 v31; // r8
  unsigned int v32; // ebp
  unsigned int v33; // esi
  unsigned int *v34; // rdi
  unsigned int v35; // eax
  enum RSNA_CIPHER_SUITE *v36; // rcx
  __int64 v37; // r12
  unsigned __int16 *v38; // r14
  __int16 v39; // ax
  char v40; // al
  int v41; // eax
  unsigned __int16 valid; // ax
  unsigned __int8 *v43; // rdx
  __int64 v44; // r9
  int v45; // ebp
  struct _NPAGED_LOOKASIDE_LIST *v46; // r10
  _QWORD *v47; // rdi
  unsigned int v48; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *v50; // rax
  char *v51; // r13
  unsigned int v52; // r15d
  unsigned int v53; // esi
  int v54; // r14d
  unsigned int v55; // ebp
  struct DOT11_AUTH_AKM_SUITE *v56; // r12
  int v57; // eax
  int v58; // eax
  PDEVICE_OBJECT v59; // rcx
  __int64 v60; // rdx
  __int16 v61; // r13
  unsigned int v62; // eax
  unsigned int *v63; // r14
  unsigned int v64; // ebp
  unsigned int v65; // eax
  struct _NPAGED_LOOKASIDE_LIST *v66; // rbx
  _DWORD *v67; // rax
  unsigned int v68; // r8d
  __int128 v69; // xmm0
  __int64 v70; // rdx
  char v72; // [rsp+30h] [rbp-78h]
  unsigned __int16 v73; // [rsp+32h] [rbp-76h]
  unsigned int v74; // [rsp+34h] [rbp-74h] BYREF
  enum RSNA_CIPHER_SUITE v75; // [rsp+38h] [rbp-70h]
  unsigned int v76; // [rsp+3Ch] [rbp-6Ch]
  int v77; // [rsp+40h] [rbp-68h]
  int v78; // [rsp+44h] [rbp-64h]
  unsigned __int16 *v79; // [rsp+48h] [rbp-60h]
  unsigned int v80; // [rsp+50h] [rbp-58h]
  unsigned int *v81; // [rsp+58h] [rbp-50h]
  enum RSNA_CIPHER_SUITE *v82; // [rsp+60h] [rbp-48h]
  char v83; // [rsp+B0h] [rbp+8h]

  v83 = (char)a1;
  v74 = 0;
  v6 = a4;
  memset(a4, 0, 0x48u);
  *((_DWORD *)v6 + 8) = 28053248;
  *(_WORD *)v6 = 1;
  v7 = (_QWORD *)((char *)v6 + 16);
  *((_DWORD *)v6 + 1) = 4;
  *((_WORD *)v6 + 4) = 1;
  *((_DWORD *)v6 + 4) = 4;
  *((_WORD *)v6 + 12) = 1;
  *((_DWORD *)v6 + 9) = 6;
  v8 = IEPRSNValidateIEContent(a1, a2, &v74);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v11 = 60;
LABEL_4:
    v12 = (unsigned int)v8;
    goto LABEL_5;
  }
  v8 = *(unsigned __int16 *)a1;
  if ( (_WORD)v8 != 1 )
  {
    v9 = -1073741823;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v11 = 61;
    goto LABEL_4;
  }
  v13 = v74;
  *(_WORD *)v6 = 1;
  if ( (v13 & 1) == 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v15 = 62;
LABEL_120:
    WPP_SF_(v14->AttachedDevice, v15, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    goto LABEL_121;
  }
  v75 = *(_DWORD *)(a1 + 2);
  v9 = IEPConvertCipherSuite(v75, (enum _DOT11_CIPHER_ALGORITHM *)v6 + 1);
  if ( v9 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v17 = *((_DWORD *)v6 + 1);
      v18 = 63;
      goto LABEL_15;
    }
    goto LABEL_121;
  }
  if ( (v13 & 6) != 6 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v15 = 64;
    goto LABEL_120;
  }
  v19 = *((_WORD *)a1 + 3);
  v73 = v19;
  v82 = (enum RSNA_CIPHER_SUITE *)(a1 + 8);
  v20 = IEPCountRSNCipherSuites(v19, (enum RSNA_CIPHER_SUITE *)a1 + 2);
  v22 = v20;
  v23 = 0;
  if ( !v20 )
  {
    v9 = -1073741823;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v15 = 65;
    goto LABEL_120;
  }
  if ( v20 <= 1u )
  {
    v27 = (char *)v6 + 16;
    goto LABEL_37;
  }
  v24 = 4 * v20 + 16;
  *v7 = 0;
  if ( 4 * v22 >= 0xFFFFFFF0 )
  {
LABEL_33:
    v9 = -1073741670;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v11 = 66;
    v12 = v22;
LABEL_5:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_e90d411d816e312466897e39e745b158_Traceguids, v12);
    goto LABEL_121;
  }
  if ( v24 > 0x40 )
  {
    if ( v24 > 0x100 )
    {
      if ( v24 > 0x400 )
      {
        if ( v24 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (_DWORD *)ExAllocatePool2(64, v24, 2053731191, v21);
          goto LABEL_32;
        }
        p_WaitListHead = &stru_1400B0180;
      }
      else
      {
        p_WaitListHead = &Lookaside;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    }
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_32:
  if ( !Pool2 )
    goto LABEL_33;
  Pool2[2] = 2053731191;
  v27 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_WaitListHead;
  v9 = 0;
  *v7 = Pool2 + 4;
LABEL_37:
  *((_WORD *)v6 + 4) = v22;
  v28 = (enum RSNA_CIPHER_SUITE *)(a1 + 8);
  IsEnabledDeviceUsageNoInline = Feature_58744956__private_IsEnabledDeviceUsageNoInline();
  v30 = 0;
  if ( IsEnabledDeviceUsageNoInline )
    v72 = (unsigned int)AreRsnCiphersValidForWpa3Ent(v75, v19, v28) != 0;
  else
    v72 = 0;
  v31 = v19;
  v32 = v30;
  if ( v73 )
  {
    v33 = v22;
    v34 = (unsigned int *)v28;
    do
    {
      if ( v32 >= v33 )
        break;
      v9 = IEPConvertCipherSuite(*v34, (enum _DOT11_CIPHER_ALGORITHM *)&v27[4 * v32]);
      v30 = 0;
      ++v34;
      v35 = v32 + 1;
      ++v23;
      if ( v9 < 0 )
        v35 = v32;
      v32 = v35;
    }
    while ( v23 < v73 );
    v6 = a4;
    v31 = v73;
  }
  if ( (v74 & 0x18) != 0x18 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v15 = 67;
    goto LABEL_120;
  }
  v36 = &v28[v31];
  v37 = *(unsigned __int16 *)v36;
  v81 = (unsigned int *)((char *)v36 + 2);
  v38 = (unsigned __int16 *)&v36[v37] + 1;
  v79 = v38;
  if ( (v74 & 0x20) != 0 )
  {
    v39 = *v38++;
    v79 = v38;
    *((_WORD *)v6 + 20) = v39;
  }
  v40 = *((_BYTE *)v6 + 40);
  if ( v40 < 0 || (v40 & 0x40) != 0 )
  {
    *((_DWORD *)v6 + 17) = 6;
    v41 = 1;
  }
  else
  {
    v41 = v30;
  }
  v77 = v41;
  valid = IEPCountValidAuthAlgorithms(v37, (unsigned __int8 *)v36 + 2, v31, v82, v75, v41);
  v45 = valid;
  v46 = 0;
  if ( !valid )
  {
    v9 = -1073741823;
    goto LABEL_121;
  }
  v47 = (_QWORD *)((char *)v6 + 32);
  v76 = valid;
  if ( valid > 1u )
  {
    v48 = 8 * valid + 16;
    *v47 = 0;
    if ( (unsigned int)(8 * v45) >= 0xFFFFFFF0 )
      goto LABEL_58;
    if ( v48 > 0x40 )
    {
      if ( v48 > 0x100 )
      {
        if ( v48 > 0x400 )
        {
          if ( v48 > 0x800 )
          {
            p_DeviceQueue = 0;
            v50 = (_DWORD *)ExAllocatePool2(64, v48, 2053731191, v44);
            goto LABEL_69;
          }
          p_DeviceQueue = &stru_1400B0180;
        }
        else
        {
          p_DeviceQueue = &Lookaside;
        }
      }
      else
      {
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v50 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_69:
    v46 = 0;
    if ( !v50 )
      goto LABEL_58;
    *(_QWORD *)v50 = p_DeviceQueue;
    v51 = (char *)(v50 + 4);
    v50[2] = 2053731191;
    v9 = 0;
    *v47 = v50 + 4;
    goto LABEL_72;
  }
  v51 = (char *)v6 + 32;
  v76 = valid;
LABEL_72:
  *((_WORD *)v6 + 12) = v45;
  v52 = 0;
  v78 = 0;
  v80 = v37;
  if ( !(_DWORD)v37 )
    goto LABEL_95;
  v53 = v76;
  v54 = v77;
  while ( v52 < v53 )
  {
    v55 = *v81;
    v56 = (struct DOT11_AUTH_AKM_SUITE *)&v51[8 * v52];
    v57 = IEPRSNConvertAuthSuite(*v81, v43, v56);
    v46 = 0;
    v9 = v57;
    if ( v57 >= 0 )
    {
      ++v52;
      v58 = Feature_58744956__private_IsEnabledDeviceUsageNoInline();
      v46 = 0;
      if ( v58 )
      {
        if ( !IsRsnAkmValidForWpa3Ent(v55, v54) || v72 == (_BYTE)v46 )
          goto LABEL_93;
        if ( v52 >= v53 )
        {
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v60 = 69;
            goto LABEL_92;
          }
        }
        else
        {
          *(_DWORD *)&v51[8 * v52] = *(_DWORD *)v56;
          *(_DWORD *)&v51[8 * v52++ + 4] = 11;
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v60 = 68;
            goto LABEL_92;
          }
        }
      }
      else
      {
        if ( v55 != 95162112 || !v54 || !(unsigned int)AreRsnCiphersValidForWpa3Ent(v75, v73, v82) )
          goto LABEL_93;
        if ( v52 >= v53 )
        {
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v60 = 71;
            goto LABEL_92;
          }
        }
        else
        {
          *(_DWORD *)&v51[8 * v52] = *(_DWORD *)v56;
          *(_DWORD *)&v51[8 * v52++ + 4] = 11;
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v60 = (unsigned int)((_DWORD)v46 + 70);
LABEL_92:
            WPP_SF_(v59->AttachedDevice, v60, WPP_e90d411d816e312466897e39e745b158_Traceguids);
            v46 = 0;
          }
        }
      }
    }
LABEL_93:
    ++v81;
    if ( ++v78 >= v80 )
      break;
  }
  v6 = a4;
  v38 = v79;
LABEL_95:
  v61 = v74;
  if ( (v74 & 0x40) == 0 )
    goto LABEL_121;
  *((_BYTE *)v6 + 64) = (_BYTE)v38 - v83;
  v62 = *v38;
  v63 = (unsigned int *)(v38 + 1);
  *((_WORD *)v6 + 21) = v62;
  if ( (v61 & 0x80u) == 0 )
    goto LABEL_112;
  v64 = v62;
  *((_QWORD *)v6 + 6) = v46;
  v65 = 16 * (v62 + 1);
  if ( v65 < 0x10 )
    goto LABEL_58;
  if ( v65 <= 0x40 )
  {
    v66 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    goto LABEL_106;
  }
  if ( v65 <= 0x100 )
  {
    v66 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_106;
  }
  if ( v65 <= 0x400 )
  {
    v66 = &Lookaside;
    goto LABEL_106;
  }
  if ( v65 > 0x800 )
  {
    v66 = v46;
    v67 = (_DWORD *)ExAllocatePool2(64, v65, 2053731191, v44);
  }
  else
  {
    v66 = &stru_1400B0180;
LABEL_106:
    v67 = ExAllocateFromNPagedLookasideList(v66);
  }
  if ( !v67 )
  {
LABEL_58:
    v9 = -1073741670;
    goto LABEL_121;
  }
  *(_QWORD *)v67 = v66;
  v68 = 0;
  v67[2] = 2053731191;
  v9 = 0;
  *((_QWORD *)v6 + 6) = v67 + 4;
  if ( v64 )
  {
    do
    {
      v69 = *(_OWORD *)v63;
      v63 += 4;
      v70 = v68++;
      *(_OWORD *)(*((_QWORD *)v6 + 6) + 16 * v70) = v69;
    }
    while ( v68 < v64 );
    v61 = v74;
  }
LABEL_112:
  if ( (v61 & 0x100) != 0 )
  {
    v9 = IEPConvertCipherSuite(*v63, (enum _DOT11_CIPHER_ALGORITHM *)v6 + 17);
    if ( v9 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v17 = *((_DWORD *)v6 + 17);
        v18 = 72;
LABEL_15:
        WPP_SF_Dd(v16->AttachedDevice, v18, WPP_e90d411d816e312466897e39e745b158_Traceguids, (unsigned int)v9, v17);
      }
    }
  }
LABEL_121:
  if ( a3 )
    *a3 = v74;
  if ( v9 )
    FreeRSNIEContent(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004bd60  mov     rax, rsp
0x14004bd63  mov     [rax+10h], rbx
0x14004bd67  mov     [rax+20h], r9
0x14004bd6b  mov     [rax+18h], r8
0x14004bd6f  mov     [rax+8], rcx
0x14004bd73  push    rbp
0x14004bd74  push    rsi
0x14004bd75  push    rdi
0x14004bd76  push    r12
0x14004bd78  push    r13
0x14004bd7a  push    r14
0x14004bd7c  push    r15
0x14004bd7e  sub     rsp, 70h
0x14004bd82  xor     edi, edi
0x14004bd84  mov     ebx, edx
0x14004bd86  mov     r12, rcx
0x14004bd89  mov     [rax-74h], edi
0x14004bd8c  xor     edx, edx; Val
0x14004bd8e  mov     rcx, r9; void *
0x14004bd91  mov     rsi, r9
0x14004bd94  lea     r8d, [rdi+48h]; Size
0x14004bd98  call    memset
0x14004bd9d  lea     ebp, [rdi+1]
0x14004bda0  mov     dword ptr [rsi+20h], 1AC0F00h
0x14004bda7  lea     r14, [rsi+4]
0x14004bdab  mov     [rsi], bp
0x14004bdae  lea     r15, [rsi+10h]
0x14004bdb2  mov     dword ptr [r14], 4
0x14004bdb9  lea     r8, [rsp+0A8h+var_74]; unsigned int *
0x14004bdbe  mov     [rsi+8], bp
0x14004bdc2  mov     edx, ebx; int
0x14004bdc4  mov     dword ptr [r15], 4
0x14004bdcb  mov     rcx, r12; unsigned __int8 *
0x14004bdce  mov     [rsi+18h], bp
0x14004bdd2  mov     dword ptr [rsi+24h], 6
0x14004bdd9  call    ?IEPRSNValidateIEContent@@YAJPEAEJPEAK@Z; IEPRSNValidateIEContent(uchar *,long,ulong *)
0x14004bdde  mov     ebx, eax
0x14004bde0  test    eax, eax
0x14004bde2  jns     short loc_14004BE16
0x14004bde4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bdeb  lea     rdi, WPP_GLOBAL_Control
0x14004bdf2  cmp     rcx, rdi
0x14004bdf5  jz      loc_14004C4B4
0x14004bdfb  lea     edx, [rbp+3Bh]
0x14004bdfe  mov     r9d, eax
0x14004be01  mov     rcx, [rcx+18h]
0x14004be05  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004be0c  call    WPP_SF_d
0x14004be11  jmp     loc_14004C4B4
0x14004be16  movzx   eax, word ptr [r12]
0x14004be1b  cmp     bp, ax
0x14004be1e  jz      short loc_14004BE43
0x14004be20  mov     ebx, 0C0000001h
0x14004be25  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be2c  lea     rdi, WPP_GLOBAL_Control
0x14004be33  cmp     rcx, rdi
0x14004be36  jz      loc_14004C4B4
0x14004be3c  mov     edx, 3Dh ; '='
0x14004be41  jmp     short loc_14004BDFE
0x14004be43  mov     r13d, [rsp+0A8h+var_74]
0x14004be48  mov     [rsi], ax
0x14004be4b  test    bpl, r13b
0x14004be4e  jnz     short loc_14004BE71
0x14004be50  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be57  lea     rdi, WPP_GLOBAL_Control
0x14004be5e  cmp     rcx, rdi
0x14004be61  jz      loc_14004C4B4
0x14004be67  mov     edx, 3Eh ; '>'
0x14004be6c  jmp     loc_14004C4A4
0x14004be71  mov     eax, [r12+2]
0x14004be76  mov     rdx, r14; enum _DOT11_CIPHER_ALGORITHM *
0x14004be79  mov     ecx, eax; unsigned int
0x14004be7b  mov     [rsp+0A8h+var_70], eax
0x14004be7f  call    ?IEPConvertCipherSuite@@YAJKPEAW4_DOT11_CIPHER_ALGORITHM@@@Z; IEPConvertCipherSuite(ulong,_DOT11_CIPHER_ALGORITHM *)
0x14004be84  mov     ebx, eax
0x14004be86  test    eax, eax
0x14004be88  jns     short loc_14004BEC5
0x14004be8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be91  lea     rdi, WPP_GLOBAL_Control
0x14004be98  cmp     rcx, rdi
0x14004be9b  jz      loc_14004C4B4
0x14004bea1  mov     eax, [r14]
0x14004bea4  mov     edx, 3Fh ; '?'
0x14004bea9  mov     rcx, [rcx+18h]
0x14004bead  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004beb4  mov     r9d, ebx
0x14004beb7  mov     [rsp+0A8h+var_88], eax
0x14004bebb  call    WPP_SF_Dd
0x14004bec0  jmp     loc_14004C4B4
0x14004bec5  mov     eax, r13d
0x14004bec8  and     eax, 6
0x14004becb  cmp     al, 6
0x14004becd  jnz     loc_14004C48C
0x14004bed3  movzx   ebp, word ptr [r12+6]
0x14004bed9  lea     rax, [r12+8]
0x14004bede  mov     rdx, rax; enum RSNA_CIPHER_SUITE *
0x14004bee1  mov     [rsp+0A8h+var_76], bp
0x14004bee6  movzx   ecx, bp; unsigned __int16
0x14004bee9  mov     [rsp+0A8h+var_48], rax
0x14004beee  call    ?IEPCountRSNCipherSuites@@YAGGPEAW4RSNA_CIPHER_SUITE@@@Z; IEPCountRSNCipherSuites(ushort,RSNA_CIPHER_SUITE *)
0x14004bef3  movzx   edi, ax
0x14004bef6  xor     r13d, r13d
0x14004bef9  test    di, di
0x14004befc  jnz     short loc_14004BF23
0x14004befe  mov     ebx, 0C0000001h
0x14004bf03  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bf0a  lea     rdi, WPP_GLOBAL_Control
0x14004bf11  cmp     rcx, rdi
0x14004bf14  jz      loc_14004C4B4
0x14004bf1a  lea     edx, [r13+41h]
0x14004bf1e  jmp     loc_14004C4A4
0x14004bf23  mov     eax, 1
0x14004bf28  mov     r14d, 7A697377h
0x14004bf2e  cmp     di, ax
0x14004bf31  jbe     loc_14004BFF4
0x14004bf37  lea     eax, ds:10h[rdi*4]
0x14004bf3e  mov     [r15], r13
0x14004bf41  mov     ebp, edi
0x14004bf43  cmp     eax, 10h
0x14004bf46  jb      short loc_14004BFB3
0x14004bf48  cmp     eax, 40h ; '@'
0x14004bf4b  ja      short loc_14004BF56
0x14004bf4d  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004bf54  jmp     short loc_14004BF84
0x14004bf56  cmp     eax, 100h
0x14004bf5b  ja      short loc_14004BF66
0x14004bf5d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004bf64  jmp     short loc_14004BF84
0x14004bf66  cmp     eax, 400h
0x14004bf6b  ja      short loc_14004BF76
0x14004bf6d  lea     rbx, Lookaside
0x14004bf74  jmp     short loc_14004BF84
0x14004bf76  cmp     eax, 800h
0x14004bf7b  ja      short loc_14004BF95
0x14004bf7d  lea     rbx, stru_1400B0180
0x14004bf84  mov     rcx, rbx; Lookaside
0x14004bf87  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004bf8e  nop     dword ptr [rax+rax+00h]
0x14004bf93  jmp     short loc_14004BFAE
0x14004bf95  mov     edx, eax
0x14004bf97  mov     r8d, r14d
0x14004bf9a  mov     ecx, 40h ; '@'
0x14004bf9f  mov     rbx, r13
0x14004bfa2  call    cs:__imp_ExAllocatePool2
0x14004bfa9  nop     dword ptr [rax+rax+00h]
0x14004bfae  test    rax, rax
0x14004bfb1  jnz     short loc_14004BFDC
0x14004bfb3  mov     ebx, 0C000009Ah
0x14004bfb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bfbf  lea     rdi, WPP_GLOBAL_Control
0x14004bfc6  cmp     rcx, rdi
0x14004bfc9  jz      loc_14004C4B4
0x14004bfcf  mov     edx, 42h ; 'B'
0x14004bfd4  mov     r9d, ebp
0x14004bfd7  jmp     loc_14004BE01
0x14004bfdc  movzx   ebp, [rsp+0A8h+var_76]
0x14004bfe1  mov     [rax+8], r14d
0x14004bfe5  lea     r14, [rax+10h]
0x14004bfe9  mov     [rax], rbx
0x14004bfec  mov     ebx, r13d
0x14004bfef  mov     [r15], r14
0x14004bff2  jmp     short loc_14004BFF7
0x14004bff4  mov     r14, r15
0x14004bff7  mov     [rsi+8], di
0x14004bffb  add     r12, 8
0x14004bfff  call    Feature_58744956__private_IsEnabledDeviceUsageNoInline
0x14004c004  xor     r10d, r10d
0x14004c007  test    eax, eax
0x14004c009  jnz     short loc_14004C012
0x14004c00b  mov     [rsp+0A8h+var_78], r10b
0x14004c010  jmp     short loc_14004C028
0x14004c012  mov     ecx, [rsp+0A8h+var_70]; enum RSNA_CIPHER_SUITE
0x14004c016  mov     r8, r12; enum RSNA_CIPHER_SUITE *
0x14004c019  movzx   edx, bp; unsigned __int16
0x14004c01c  call    ?AreRsnCiphersValidForWpa3Ent@@YAHW4RSNA_CIPHER_SUITE@@GPEAW41@@Z; AreRsnCiphersValidForWpa3Ent(RSNA_CIPHER_SUITE,ushort,RSNA_CIPHER_SUITE *)
0x14004c021  test    eax, eax
0x14004c023  setnz   [rsp+0A8h+var_78]
0x14004c028  movzx   r8d, [rsp+0A8h+var_76]
0x14004c02e  mov     ebp, r10d
0x14004c031  mov     r15d, r8d
0x14004c034  test    r8d, r8d
0x14004c037  jz      short loc_14004C078
0x14004c039  mov     esi, edi
0x14004c03b  mov     rdi, r12
0x14004c03e  cmp     ebp, esi
0x14004c040  jnb     short loc_14004C06A
0x14004c042  mov     ecx, [rdi]; unsigned int
0x14004c044  mov     eax, ebp
0x14004c046  lea     rdx, [r14+rax*4]; enum _DOT11_CIPHER_ALGORITHM *
0x14004c04a  call    ?IEPConvertCipherSuite@@YAJKPEAW4_DOT11_CIPHER_ALGORITHM@@@Z; IEPConvertCipherSuite(ulong,_DOT11_CIPHER_ALGORITHM *)
0x14004c04f  mov     ebx, eax
0x14004c051  xor     r10d, r10d
0x14004c054  add     rdi, 4
0x14004c058  lea     eax, [rbp+1]
0x14004c05b  inc     r13d
0x14004c05e  test    ebx, ebx
0x14004c060  cmovs   eax, ebp
0x14004c063  mov     ebp, eax
0x14004c065  cmp     r13d, r15d
0x14004c068  jb      short loc_14004C03E
0x14004c06a  mov     rsi, [rsp+0A8h+arg_18]
0x14004c072  movzx   r8d, [rsp+0A8h+var_76]; unsigned __int16
0x14004c078  mov     r13d, [rsp+0A8h+var_74]
0x14004c07d  mov     eax, r13d
0x14004c080  and     eax, 18h
0x14004c083  cmp     al, 18h
0x14004c085  jnz     loc_14004C472
0x14004c08b  movzx   eax, r8w
0x14004c08f  lea     rcx, [r12+rax*4]
0x14004c093  movzx   r12d, word ptr [rcx]
0x14004c097  lea     rdx, [rcx+2]; unsigned __int8 *
0x14004c09b  mov     [rsp+0A8h+var_50], rdx
0x14004c0a0  lea     r14, ds:2[r12*4]
0x14004c0a8  add     r14, rcx
0x14004c0ab  mov     [rsp+0A8h+var_60], r14
0x14004c0b0  test    r13b, 20h
0x14004c0b4  jz      short loc_14004C0C7
0x14004c0b6  movzx   eax, word ptr [r14]
0x14004c0ba  add     r14, 2
0x14004c0be  mov     [rsp+0A8h+var_60], r14
0x14004c0c3  mov     [rsi+28h], ax
0x14004c0c7  mov     al, [rsi+28h]
0x14004c0ca  test    al, al
0x14004c0cc  js      short loc_14004C0DD
0x14004c0ce  test    al, 40h
0x14004c0d0  jnz     short loc_14004C0DD
0x14004c0d2  mov     eax, r10d
0x14004c0d5  mov     r15d, 1
0x14004c0db  jmp     short loc_14004C0ED
0x14004c0dd  mov     r15d, 1
0x14004c0e3  mov     dword ptr [rsi+44h], 6
0x14004c0ea  mov     eax, r15d
0x14004c0ed  mov     r9, [rsp+0A8h+var_48]; enum RSNA_CIPHER_SUITE *
0x14004c0f2  movzx   ecx, r12w; unsigned __int16
0x14004c0f6  mov     [rsp+0A8h+var_80], eax; int
0x14004c0fa  mov     [rsp+0A8h+var_68], eax
0x14004c0fe  mov     eax, [rsp+0A8h+var_70]
0x14004c102  mov     [rsp+0A8h+var_88], eax; enum RSNA_CIPHER_SUITE
0x14004c106  call    ?IEPCountValidAuthAlgorithms@@YAGGPEAEGPEAW4RSNA_CIPHER_SUITE@@W41@H@Z; IEPCountValidAuthAlgorithms(ushort,uchar *,ushort,RSNA_CIPHER_SUITE *,RSNA_CIPHER_SUITE,int)
0x14004c10b  movzx   ebp, ax
0x14004c10e  xor     r10d, r10d
0x14004c111  test    bp, bp
0x14004c114  jnz     short loc_14004C120
0x14004c116  mov     ebx, 0C0000001h
0x14004c11b  jmp     loc_14004C4B4
0x14004c120  lea     rdi, [rsi+20h]
0x14004c124  mov     eax, ebp
0x14004c126  mov     [rsp+0A8h+var_6C], eax
0x14004c12a  cmp     bp, r15w
0x14004c12e  jbe     loc_14004C1D4
0x14004c134  lea     eax, ds:10h[rbp*8]
0x14004c13b  mov     [rdi], r10
0x14004c13e  cmp     eax, 10h
0x14004c141  jnb     short loc_14004C14D
0x14004c143  mov     ebx, 0C000009Ah
0x14004c148  jmp     loc_14004C4B4
0x14004c14d  cmp     eax, 40h ; '@'
0x14004c150  ja      short loc_14004C15B
0x14004c152  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004c159  jmp     short loc_14004C189
0x14004c15b  cmp     eax, 100h
0x14004c160  ja      short loc_14004C16B
0x14004c162  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004c169  jmp     short loc_14004C189
0x14004c16b  cmp     eax, 400h
0x14004c170  ja      short loc_14004C17B
0x14004c172  lea     rbx, Lookaside
0x14004c179  jmp     short loc_14004C189
0x14004c17b  cmp     eax, 800h
0x14004c180  ja      short loc_14004C19A
0x14004c182  lea     rbx, stru_1400B0180
0x14004c189  mov     rcx, rbx; Lookaside
0x14004c18c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004c193  nop     dword ptr [rax+rax+00h]
0x14004c198  jmp     short loc_14004C1B6
0x14004c19a  mov     edx, eax
0x14004c19c  mov     ecx, 40h ; '@'
0x14004c1a1  mov     r8d, 7A697377h
0x14004c1a7  mov     rbx, r10
0x14004c1aa  call    cs:__imp_ExAllocatePool2
0x14004c1b1  nop     dword ptr [rax+rax+00h]
0x14004c1b6  xor     r10d, r10d
0x14004c1b9  test    rax, rax
0x14004c1bc  jz      short loc_14004C143
0x14004c1be  mov     [rax], rbx
0x14004c1c1  lea     r13, [rax+10h]
0x14004c1c5  mov     dword ptr [rax+8], 7A697377h
0x14004c1cc  mov     ebx, r10d
0x14004c1cf  mov     [rdi], r13
0x14004c1d2  jmp     short loc_14004C1DB
0x14004c1d4  mov     r13, rdi
0x14004c1d7  mov     [rsp+0A8h+var_6C], eax
0x14004c1db  mov     [rsi+18h], bp
0x14004c1df  mov     r15d, r10d
0x14004c1e2  mov     [rsp+0A8h+var_64], r10d
0x14004c1e7  lea     rdi, WPP_GLOBAL_Control
0x14004c1ee  mov     [rsp+0A8h+var_58], r12d
0x14004c1f3  test    r12d, r12d
0x14004c1f6  jz      loc_14004C346
0x14004c1fc  mov     esi, [rsp+0A8h+var_6C]
  ... truncated ...
```
