# IEPRSNParseIE(uchar *,ulong,ulong *,DOT11_RSN_IE_INFO *)

- ea: `0x14004cfe8`
- end: `0x14004d776`
- name: `?IEPRSNParseIE@@YAJPEAEKPEAKPEAUDOT11_RSN_IE_INFO@@@Z`
- size: `1934`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int *, struct DOT11_RSN_IE_INFO *)`
- caller_count: `7`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14003a814`
- `0x140040680`
- `0x1400419dc`
- `0x140041bd8`
- `0x14004b344`
- `0x14004ba84`
- `0x14005351c`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x140040130`
- `0x140048cc8`
- `0x14004cc40`
- `0x14004cd54`
- `0x14004cda8`
- `0x14004ce94`
- `0x14004cfe8`
- `0x14004d77c`
- `0x140050e04`
- `0x140053ed8`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d20f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d414`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d652`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d20f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d414`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d652`
- `ntoskrnl!ExAllocatePool2` at `0x14004d22a`
- `ntoskrnl!ExAllocatePool2` at `0x14004d432`
- `ntoskrnl!ExAllocatePool2` at `0x14004d670`
- `ntoskrnl!ExAllocatePool2` at `0x14004d22a`
- `ntoskrnl!ExAllocatePool2` at `0x14004d432`
- `ntoskrnl!ExAllocatePool2` at `0x14004d670`

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
  unsigned int v21; // edi
  unsigned int v22; // r13d
  unsigned int v23; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  char *v26; // r14
  enum RSNA_CIPHER_SUITE *v27; // r12
  int IsEnabledDeviceUsageNoInline; // eax
  int v29; // r10d
  unsigned __int16 v30; // r8
  unsigned int v31; // ebp
  unsigned int v32; // esi
  unsigned int *v33; // rdi
  unsigned int v34; // eax
  enum RSNA_CIPHER_SUITE *v35; // rcx
  __int64 v36; // r12
  unsigned __int16 *v37; // r14
  __int16 v38; // ax
  char v39; // al
  int v40; // eax
  unsigned __int16 valid; // ax
  unsigned __int8 *v42; // rdx
  int v43; // ebp
  struct _NPAGED_LOOKASIDE_LIST *v44; // r10
  _QWORD *v45; // rdi
  unsigned int v46; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *v48; // rax
  char *v49; // r13
  unsigned int v50; // r15d
  unsigned int v51; // esi
  int v52; // r14d
  unsigned int v53; // ebp
  struct DOT11_AUTH_AKM_SUITE *v54; // r12
  int v55; // eax
  int v56; // eax
  PDEVICE_OBJECT v57; // rcx
  __int64 v58; // rdx
  __int16 v59; // r13
  unsigned int v60; // eax
  unsigned int *v61; // r14
  unsigned int v62; // ebp
  unsigned int v63; // eax
  struct _NPAGED_LOOKASIDE_LIST *v64; // rbx
  _DWORD *v65; // rax
  unsigned int v66; // r8d
  __int128 v67; // xmm0
  __int64 v68; // rdx
  char v70; // [rsp+30h] [rbp-78h]
  unsigned __int16 v71; // [rsp+32h] [rbp-76h]
  unsigned int v72; // [rsp+34h] [rbp-74h] BYREF
  enum RSNA_CIPHER_SUITE v73; // [rsp+38h] [rbp-70h]
  unsigned int v74; // [rsp+3Ch] [rbp-6Ch]
  int v75; // [rsp+40h] [rbp-68h]
  int v76; // [rsp+44h] [rbp-64h]
  unsigned __int16 *v77; // [rsp+48h] [rbp-60h]
  unsigned int v78; // [rsp+50h] [rbp-58h]
  unsigned int *v79; // [rsp+58h] [rbp-50h]
  enum RSNA_CIPHER_SUITE *v80; // [rsp+60h] [rbp-48h]
  char v81; // [rsp+B0h] [rbp+8h]

  v81 = (char)a1;
  v72 = 0;
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
  v8 = IEPRSNValidateIEContent(a1, a2, &v72);
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
  v13 = v72;
  *(_WORD *)v6 = 1;
  if ( (v13 & 1) == 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v15 = 62;
LABEL_120:
    WPP_SF_(v14->AttachedDevice, v15, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    goto LABEL_121;
  }
  v73 = *(_DWORD *)(a1 + 2);
  v9 = IEPConvertCipherSuite(v73, (enum _DOT11_CIPHER_ALGORITHM *)v6 + 1);
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
  v71 = v19;
  v80 = (enum RSNA_CIPHER_SUITE *)(a1 + 8);
  v20 = IEPCountRSNCipherSuites(v19, (enum RSNA_CIPHER_SUITE *)a1 + 2);
  v21 = v20;
  v22 = 0;
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
    v26 = (char *)v6 + 16;
    goto LABEL_37;
  }
  v23 = 4 * v20 + 16;
  *v7 = 0;
  if ( 4 * v21 >= 0xFFFFFFF0 )
  {
LABEL_33:
    v9 = -1073741670;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v11 = 66;
    v12 = v21;
LABEL_5:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v12);
    goto LABEL_121;
  }
  if ( v23 > 0x40 )
  {
    if ( v23 > 0x100 )
    {
      if ( v23 > 0x400 )
      {
        if ( v23 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (_DWORD *)ExAllocatePool2(64, v23, 2053731191);
          goto LABEL_32;
        }
        p_WaitListHead = &stru_1400B31C0;
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
  v26 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_WaitListHead;
  v9 = 0;
  *v7 = Pool2 + 4;
LABEL_37:
  *((_WORD *)v6 + 4) = v21;
  v27 = (enum RSNA_CIPHER_SUITE *)(a1 + 8);
  IsEnabledDeviceUsageNoInline = Feature_58744956__private_IsEnabledDeviceUsageNoInline();
  v29 = 0;
  if ( IsEnabledDeviceUsageNoInline )
    v70 = (unsigned int)AreRsnCiphersValidForWpa3Ent(v73, v19, v27) != 0;
  else
    v70 = 0;
  v30 = v19;
  v31 = v29;
  if ( v71 )
  {
    v32 = v21;
    v33 = (unsigned int *)v27;
    do
    {
      if ( v31 >= v32 )
        break;
      v9 = IEPConvertCipherSuite(*v33, (enum _DOT11_CIPHER_ALGORITHM *)&v26[4 * v31]);
      v29 = 0;
      ++v33;
      v34 = v31 + 1;
      ++v22;
      if ( v9 < 0 )
        v34 = v31;
      v31 = v34;
    }
    while ( v22 < v71 );
    v6 = a4;
    v30 = v71;
  }
  if ( (v72 & 0x18) != 0x18 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_121;
    v15 = 67;
    goto LABEL_120;
  }
  v35 = &v27[v30];
  v36 = *(unsigned __int16 *)v35;
  v79 = (unsigned int *)((char *)v35 + 2);
  v37 = (unsigned __int16 *)&v35[v36] + 1;
  v77 = v37;
  if ( (v72 & 0x20) != 0 )
  {
    v38 = *v37++;
    v77 = v37;
    *((_WORD *)v6 + 20) = v38;
  }
  v39 = *((_BYTE *)v6 + 40);
  if ( v39 < 0 || (v39 & 0x40) != 0 )
  {
    *((_DWORD *)v6 + 17) = 6;
    v40 = 1;
  }
  else
  {
    v40 = v29;
  }
  v75 = v40;
  valid = IEPCountValidAuthAlgorithms(v36, (unsigned __int8 *)v35 + 2, v30, v80, v73, v40);
  v43 = valid;
  v44 = 0;
  if ( !valid )
  {
    v9 = -1073741823;
    goto LABEL_121;
  }
  v45 = (_QWORD *)((char *)v6 + 32);
  v74 = valid;
  if ( valid > 1u )
  {
    v46 = 8 * valid + 16;
    *v45 = 0;
    if ( (unsigned int)(8 * v43) >= 0xFFFFFFF0 )
      goto LABEL_58;
    if ( v46 > 0x40 )
    {
      if ( v46 > 0x100 )
      {
        if ( v46 > 0x400 )
        {
          if ( v46 > 0x800 )
          {
            p_DeviceQueue = 0;
            v48 = (_DWORD *)ExAllocatePool2(64, v46, 2053731191);
            goto LABEL_69;
          }
          p_DeviceQueue = &stru_1400B31C0;
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
    v48 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_69:
    v44 = 0;
    if ( !v48 )
      goto LABEL_58;
    *(_QWORD *)v48 = p_DeviceQueue;
    v49 = (char *)(v48 + 4);
    v48[2] = 2053731191;
    v9 = 0;
    *v45 = v48 + 4;
    goto LABEL_72;
  }
  v49 = (char *)v6 + 32;
  v74 = valid;
LABEL_72:
  *((_WORD *)v6 + 12) = v43;
  v50 = 0;
  v76 = 0;
  v78 = v36;
  if ( !(_DWORD)v36 )
    goto LABEL_95;
  v51 = v74;
  v52 = v75;
  while ( v50 < v51 )
  {
    v53 = *v79;
    v54 = (struct DOT11_AUTH_AKM_SUITE *)&v49[8 * v50];
    v55 = IEPRSNConvertAuthSuite(*v79, v42, v54);
    v44 = 0;
    v9 = v55;
    if ( v55 >= 0 )
    {
      ++v50;
      v56 = Feature_58744956__private_IsEnabledDeviceUsageNoInline();
      v44 = 0;
      if ( v56 )
      {
        if ( !IsRsnAkmValidForWpa3Ent(v53, v52) || v70 == (_BYTE)v44 )
          goto LABEL_93;
        if ( v50 >= v51 )
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v58 = 69;
            goto LABEL_92;
          }
        }
        else
        {
          *(_DWORD *)&v49[8 * v50] = *(_DWORD *)v54;
          *(_DWORD *)&v49[8 * v50++ + 4] = 11;
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v58 = 68;
            goto LABEL_92;
          }
        }
      }
      else
      {
        if ( v53 != 95162112 || !v52 || !(unsigned int)AreRsnCiphersValidForWpa3Ent(v73, v71, v80) )
          goto LABEL_93;
        if ( v50 >= v51 )
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v58 = 71;
            goto LABEL_92;
          }
        }
        else
        {
          *(_DWORD *)&v49[8 * v50] = *(_DWORD *)v54;
          *(_DWORD *)&v49[8 * v50++ + 4] = 11;
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v58 = (unsigned int)((_DWORD)v44 + 70);
LABEL_92:
            WPP_SF_(v57->AttachedDevice, v58, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
            v44 = 0;
          }
        }
      }
    }
LABEL_93:
    ++v79;
    if ( ++v76 >= v78 )
      break;
  }
  v6 = a4;
  v37 = v77;
LABEL_95:
  v59 = v72;
  if ( (v72 & 0x40) == 0 )
    goto LABEL_121;
  *((_BYTE *)v6 + 64) = (_BYTE)v37 - v81;
  v60 = *v37;
  v61 = (unsigned int *)(v37 + 1);
  *((_WORD *)v6 + 21) = v60;
  if ( (v59 & 0x80u) == 0 )
    goto LABEL_112;
  v62 = v60;
  *((_QWORD *)v6 + 6) = v44;
  v63 = 16 * (v60 + 1);
  if ( v63 < 0x10 )
    goto LABEL_58;
  if ( v63 <= 0x40 )
  {
    v64 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    goto LABEL_106;
  }
  if ( v63 <= 0x100 )
  {
    v64 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_106;
  }
  if ( v63 <= 0x400 )
  {
    v64 = &Lookaside;
    goto LABEL_106;
  }
  if ( v63 > 0x800 )
  {
    v64 = v44;
    v65 = (_DWORD *)ExAllocatePool2(64, v63, 2053731191);
  }
  else
  {
    v64 = &stru_1400B31C0;
LABEL_106:
    v65 = ExAllocateFromNPagedLookasideList(v64);
  }
  if ( !v65 )
  {
LABEL_58:
    v9 = -1073741670;
    goto LABEL_121;
  }
  *(_QWORD *)v65 = v64;
  v66 = 0;
  v65[2] = 2053731191;
  v9 = 0;
  *((_QWORD *)v6 + 6) = v65 + 4;
  if ( v62 )
  {
    do
    {
      v67 = *(_OWORD *)v61;
      v61 += 4;
      v68 = v66++;
      *(_OWORD *)(*((_QWORD *)v6 + 6) + 16 * v68) = v67;
    }
    while ( v66 < v62 );
    v59 = v72;
  }
LABEL_112:
  if ( (v59 & 0x100) != 0 )
  {
    v9 = IEPConvertCipherSuite(*v61, (enum _DOT11_CIPHER_ALGORITHM *)v6 + 17);
    if ( v9 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v17 = *((_DWORD *)v6 + 17);
        v18 = 72;
LABEL_15:
        WPP_SF_Dd(v16->AttachedDevice, v18, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)v9, v17);
      }
    }
  }
LABEL_121:
  if ( a3 )
    *a3 = v72;
  if ( v9 )
    FreeRSNIEContent(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004cfe8  mov     rax, rsp
0x14004cfeb  mov     [rax+10h], rbx
0x14004cfef  mov     [rax+20h], r9
0x14004cff3  mov     [rax+18h], r8
0x14004cff7  mov     [rax+8], rcx
0x14004cffb  push    rbp
0x14004cffc  push    rsi
0x14004cffd  push    rdi
0x14004cffe  push    r12
0x14004d000  push    r13
0x14004d002  push    r14
0x14004d004  push    r15
0x14004d006  sub     rsp, 70h
0x14004d00a  xor     edi, edi
0x14004d00c  mov     ebx, edx
0x14004d00e  mov     r12, rcx
0x14004d011  mov     [rax-74h], edi
0x14004d014  xor     edx, edx; Val
0x14004d016  mov     rcx, r9; void *
0x14004d019  mov     rsi, r9
0x14004d01c  lea     r8d, [rdi+48h]; Size
0x14004d020  call    memset
0x14004d025  lea     ebp, [rdi+1]
0x14004d028  mov     dword ptr [rsi+20h], 1AC0F00h
0x14004d02f  lea     r14, [rsi+4]
0x14004d033  mov     [rsi], bp
0x14004d036  lea     r15, [rsi+10h]
0x14004d03a  mov     dword ptr [r14], 4
0x14004d041  lea     r8, [rsp+0A8h+var_74]; unsigned int *
0x14004d046  mov     [rsi+8], bp
0x14004d04a  mov     edx, ebx; int
0x14004d04c  mov     dword ptr [r15], 4
0x14004d053  mov     rcx, r12; unsigned __int8 *
0x14004d056  mov     [rsi+18h], bp
0x14004d05a  mov     dword ptr [rsi+24h], 6
0x14004d061  call    ?IEPRSNValidateIEContent@@YAJPEAEJPEAK@Z; IEPRSNValidateIEContent(uchar *,long,ulong *)
0x14004d066  mov     ebx, eax
0x14004d068  test    eax, eax
0x14004d06a  jns     short loc_14004D09E
0x14004d06c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d073  lea     rdi, WPP_GLOBAL_Control
0x14004d07a  cmp     rcx, rdi
0x14004d07d  jz      loc_14004D73C
0x14004d083  lea     edx, [rbp+3Bh]
0x14004d086  mov     r9d, eax
0x14004d089  mov     rcx, [rcx+18h]
0x14004d08d  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004d094  call    WPP_SF_d
0x14004d099  jmp     loc_14004D73C
0x14004d09e  movzx   eax, word ptr [r12]
0x14004d0a3  cmp     bp, ax
0x14004d0a6  jz      short loc_14004D0CB
0x14004d0a8  mov     ebx, 0C0000001h
0x14004d0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d0b4  lea     rdi, WPP_GLOBAL_Control
0x14004d0bb  cmp     rcx, rdi
0x14004d0be  jz      loc_14004D73C
0x14004d0c4  mov     edx, 3Dh ; '='
0x14004d0c9  jmp     short loc_14004D086
0x14004d0cb  mov     r13d, [rsp+0A8h+var_74]
0x14004d0d0  mov     [rsi], ax
0x14004d0d3  test    bpl, r13b
0x14004d0d6  jnz     short loc_14004D0F9
0x14004d0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d0df  lea     rdi, WPP_GLOBAL_Control
0x14004d0e6  cmp     rcx, rdi
0x14004d0e9  jz      loc_14004D73C
0x14004d0ef  mov     edx, 3Eh ; '>'
0x14004d0f4  jmp     loc_14004D72C
0x14004d0f9  mov     eax, [r12+2]
0x14004d0fe  mov     rdx, r14; enum _DOT11_CIPHER_ALGORITHM *
0x14004d101  mov     ecx, eax; unsigned int
0x14004d103  mov     [rsp+0A8h+var_70], eax
0x14004d107  call    ?IEPConvertCipherSuite@@YAJKPEAW4_DOT11_CIPHER_ALGORITHM@@@Z; IEPConvertCipherSuite(ulong,_DOT11_CIPHER_ALGORITHM *)
0x14004d10c  mov     ebx, eax
0x14004d10e  test    eax, eax
0x14004d110  jns     short loc_14004D14D
0x14004d112  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d119  lea     rdi, WPP_GLOBAL_Control
0x14004d120  cmp     rcx, rdi
0x14004d123  jz      loc_14004D73C
0x14004d129  mov     eax, [r14]
0x14004d12c  mov     edx, 3Fh ; '?'
0x14004d131  mov     rcx, [rcx+18h]
0x14004d135  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004d13c  mov     r9d, ebx
0x14004d13f  mov     [rsp+0A8h+var_88], eax
0x14004d143  call    WPP_SF_Dd
0x14004d148  jmp     loc_14004D73C
0x14004d14d  mov     eax, r13d
0x14004d150  and     eax, 6
0x14004d153  cmp     al, 6
0x14004d155  jnz     loc_14004D714
0x14004d15b  movzx   ebp, word ptr [r12+6]
0x14004d161  lea     rax, [r12+8]
0x14004d166  mov     rdx, rax; enum RSNA_CIPHER_SUITE *
0x14004d169  mov     [rsp+0A8h+var_76], bp
0x14004d16e  movzx   ecx, bp; unsigned __int16
0x14004d171  mov     [rsp+0A8h+var_48], rax
0x14004d176  call    ?IEPCountRSNCipherSuites@@YAGGPEAW4RSNA_CIPHER_SUITE@@@Z; IEPCountRSNCipherSuites(ushort,RSNA_CIPHER_SUITE *)
0x14004d17b  movzx   edi, ax
0x14004d17e  xor     r13d, r13d
0x14004d181  test    di, di
0x14004d184  jnz     short loc_14004D1AB
0x14004d186  mov     ebx, 0C0000001h
0x14004d18b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d192  lea     rdi, WPP_GLOBAL_Control
0x14004d199  cmp     rcx, rdi
0x14004d19c  jz      loc_14004D73C
0x14004d1a2  lea     edx, [r13+41h]
0x14004d1a6  jmp     loc_14004D72C
0x14004d1ab  mov     eax, 1
0x14004d1b0  mov     r14d, 7A697377h
0x14004d1b6  cmp     di, ax
0x14004d1b9  jbe     loc_14004D27C
0x14004d1bf  lea     eax, ds:10h[rdi*4]
0x14004d1c6  mov     [r15], r13
0x14004d1c9  mov     ebp, edi
0x14004d1cb  cmp     eax, 10h
0x14004d1ce  jb      short loc_14004D23B
0x14004d1d0  cmp     eax, 40h ; '@'
0x14004d1d3  ja      short loc_14004D1DE
0x14004d1d5  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004d1dc  jmp     short loc_14004D20C
0x14004d1de  cmp     eax, 100h
0x14004d1e3  ja      short loc_14004D1EE
0x14004d1e5  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004d1ec  jmp     short loc_14004D20C
0x14004d1ee  cmp     eax, 400h
0x14004d1f3  ja      short loc_14004D1FE
0x14004d1f5  lea     rbx, Lookaside
0x14004d1fc  jmp     short loc_14004D20C
0x14004d1fe  cmp     eax, 800h
0x14004d203  ja      short loc_14004D21D
0x14004d205  lea     rbx, stru_1400B31C0
0x14004d20c  mov     rcx, rbx; Lookaside
0x14004d20f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004d216  nop     dword ptr [rax+rax+00h]
0x14004d21b  jmp     short loc_14004D236
0x14004d21d  mov     edx, eax
0x14004d21f  mov     r8d, r14d
0x14004d222  mov     ecx, 40h ; '@'
0x14004d227  mov     rbx, r13
0x14004d22a  call    cs:__imp_ExAllocatePool2
0x14004d231  nop     dword ptr [rax+rax+00h]
0x14004d236  test    rax, rax
0x14004d239  jnz     short loc_14004D264
0x14004d23b  mov     ebx, 0C000009Ah
0x14004d240  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d247  lea     rdi, WPP_GLOBAL_Control
0x14004d24e  cmp     rcx, rdi
0x14004d251  jz      loc_14004D73C
0x14004d257  mov     edx, 42h ; 'B'
0x14004d25c  mov     r9d, ebp
0x14004d25f  jmp     loc_14004D089
0x14004d264  movzx   ebp, [rsp+0A8h+var_76]
0x14004d269  mov     [rax+8], r14d
0x14004d26d  lea     r14, [rax+10h]
0x14004d271  mov     [rax], rbx
0x14004d274  mov     ebx, r13d
0x14004d277  mov     [r15], r14
0x14004d27a  jmp     short loc_14004D27F
0x14004d27c  mov     r14, r15
0x14004d27f  mov     [rsi+8], di
0x14004d283  add     r12, 8
0x14004d287  call    Feature_58744956__private_IsEnabledDeviceUsageNoInline
0x14004d28c  xor     r10d, r10d
0x14004d28f  test    eax, eax
0x14004d291  jnz     short loc_14004D29A
0x14004d293  mov     [rsp+0A8h+var_78], r10b
0x14004d298  jmp     short loc_14004D2B0
0x14004d29a  mov     ecx, [rsp+0A8h+var_70]; enum RSNA_CIPHER_SUITE
0x14004d29e  mov     r8, r12; enum RSNA_CIPHER_SUITE *
0x14004d2a1  movzx   edx, bp; unsigned __int16
0x14004d2a4  call    ?AreRsnCiphersValidForWpa3Ent@@YAHW4RSNA_CIPHER_SUITE@@GPEAW41@@Z; AreRsnCiphersValidForWpa3Ent(RSNA_CIPHER_SUITE,ushort,RSNA_CIPHER_SUITE *)
0x14004d2a9  test    eax, eax
0x14004d2ab  setnz   [rsp+0A8h+var_78]
0x14004d2b0  movzx   r8d, [rsp+0A8h+var_76]
0x14004d2b6  mov     ebp, r10d
0x14004d2b9  mov     r15d, r8d
0x14004d2bc  test    r8d, r8d
0x14004d2bf  jz      short loc_14004D300
0x14004d2c1  mov     esi, edi
0x14004d2c3  mov     rdi, r12
0x14004d2c6  cmp     ebp, esi
0x14004d2c8  jnb     short loc_14004D2F2
0x14004d2ca  mov     ecx, [rdi]; unsigned int
0x14004d2cc  mov     eax, ebp
0x14004d2ce  lea     rdx, [r14+rax*4]; enum _DOT11_CIPHER_ALGORITHM *
0x14004d2d2  call    ?IEPConvertCipherSuite@@YAJKPEAW4_DOT11_CIPHER_ALGORITHM@@@Z; IEPConvertCipherSuite(ulong,_DOT11_CIPHER_ALGORITHM *)
0x14004d2d7  mov     ebx, eax
0x14004d2d9  xor     r10d, r10d
0x14004d2dc  add     rdi, 4
0x14004d2e0  lea     eax, [rbp+1]
0x14004d2e3  inc     r13d
0x14004d2e6  test    ebx, ebx
0x14004d2e8  cmovs   eax, ebp
0x14004d2eb  mov     ebp, eax
0x14004d2ed  cmp     r13d, r15d
0x14004d2f0  jb      short loc_14004D2C6
0x14004d2f2  mov     rsi, [rsp+0A8h+arg_18]
0x14004d2fa  movzx   r8d, [rsp+0A8h+var_76]; unsigned __int16
0x14004d300  mov     r13d, [rsp+0A8h+var_74]
0x14004d305  mov     eax, r13d
0x14004d308  and     eax, 18h
0x14004d30b  cmp     al, 18h
0x14004d30d  jnz     loc_14004D6FA
0x14004d313  movzx   eax, r8w
0x14004d317  lea     rcx, [r12+rax*4]
0x14004d31b  movzx   r12d, word ptr [rcx]
0x14004d31f  lea     rdx, [rcx+2]; unsigned __int8 *
0x14004d323  mov     [rsp+0A8h+var_50], rdx
0x14004d328  lea     r14, ds:2[r12*4]
0x14004d330  add     r14, rcx
0x14004d333  mov     [rsp+0A8h+var_60], r14
0x14004d338  test    r13b, 20h
0x14004d33c  jz      short loc_14004D34F
0x14004d33e  movzx   eax, word ptr [r14]
0x14004d342  add     r14, 2
0x14004d346  mov     [rsp+0A8h+var_60], r14
0x14004d34b  mov     [rsi+28h], ax
0x14004d34f  mov     al, [rsi+28h]
0x14004d352  test    al, al
0x14004d354  js      short loc_14004D365
0x14004d356  test    al, 40h
0x14004d358  jnz     short loc_14004D365
0x14004d35a  mov     eax, r10d
0x14004d35d  mov     r15d, 1
0x14004d363  jmp     short loc_14004D375
0x14004d365  mov     r15d, 1
0x14004d36b  mov     dword ptr [rsi+44h], 6
0x14004d372  mov     eax, r15d
0x14004d375  mov     r9, [rsp+0A8h+var_48]; enum RSNA_CIPHER_SUITE *
0x14004d37a  movzx   ecx, r12w; unsigned __int16
0x14004d37e  mov     [rsp+0A8h+var_80], eax; int
0x14004d382  mov     [rsp+0A8h+var_68], eax
0x14004d386  mov     eax, [rsp+0A8h+var_70]
0x14004d38a  mov     [rsp+0A8h+var_88], eax; enum RSNA_CIPHER_SUITE
0x14004d38e  call    ?IEPCountValidAuthAlgorithms@@YAGGPEAEGPEAW4RSNA_CIPHER_SUITE@@W41@H@Z; IEPCountValidAuthAlgorithms(ushort,uchar *,ushort,RSNA_CIPHER_SUITE *,RSNA_CIPHER_SUITE,int)
0x14004d393  movzx   ebp, ax
0x14004d396  xor     r10d, r10d
0x14004d399  test    bp, bp
0x14004d39c  jnz     short loc_14004D3A8
0x14004d39e  mov     ebx, 0C0000001h
0x14004d3a3  jmp     loc_14004D73C
0x14004d3a8  lea     rdi, [rsi+20h]
0x14004d3ac  mov     eax, ebp
0x14004d3ae  mov     [rsp+0A8h+var_6C], eax
0x14004d3b2  cmp     bp, r15w
0x14004d3b6  jbe     loc_14004D45C
0x14004d3bc  lea     eax, ds:10h[rbp*8]
0x14004d3c3  mov     [rdi], r10
0x14004d3c6  cmp     eax, 10h
0x14004d3c9  jnb     short loc_14004D3D5
0x14004d3cb  mov     ebx, 0C000009Ah
0x14004d3d0  jmp     loc_14004D73C
0x14004d3d5  cmp     eax, 40h ; '@'
0x14004d3d8  ja      short loc_14004D3E3
0x14004d3da  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004d3e1  jmp     short loc_14004D411
0x14004d3e3  cmp     eax, 100h
0x14004d3e8  ja      short loc_14004D3F3
0x14004d3ea  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004d3f1  jmp     short loc_14004D411
0x14004d3f3  cmp     eax, 400h
0x14004d3f8  ja      short loc_14004D403
0x14004d3fa  lea     rbx, Lookaside
0x14004d401  jmp     short loc_14004D411
0x14004d403  cmp     eax, 800h
0x14004d408  ja      short loc_14004D422
0x14004d40a  lea     rbx, stru_1400B31C0
0x14004d411  mov     rcx, rbx; Lookaside
0x14004d414  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004d41b  nop     dword ptr [rax+rax+00h]
0x14004d420  jmp     short loc_14004D43E
0x14004d422  mov     edx, eax
0x14004d424  mov     ecx, 40h ; '@'
0x14004d429  mov     r8d, 7A697377h
0x14004d42f  mov     rbx, r10
0x14004d432  call    cs:__imp_ExAllocatePool2
0x14004d439  nop     dword ptr [rax+rax+00h]
0x14004d43e  xor     r10d, r10d
0x14004d441  test    rax, rax
0x14004d444  jz      short loc_14004D3CB
0x14004d446  mov     [rax], rbx
0x14004d449  lea     r13, [rax+10h]
0x14004d44d  mov     dword ptr [rax+8], 7A697377h
0x14004d454  mov     ebx, r10d
0x14004d457  mov     [rdi], r13
0x14004d45a  jmp     short loc_14004D463
0x14004d45c  mov     r13, rdi
0x14004d45f  mov     [rsp+0A8h+var_6C], eax
0x14004d463  mov     [rsi+18h], bp
0x14004d467  mov     r15d, r10d
0x14004d46a  mov     [rsp+0A8h+var_64], r10d
0x14004d46f  lea     rdi, WPP_GLOBAL_Control
0x14004d476  mov     [rsp+0A8h+var_58], r12d
0x14004d47b  test    r12d, r12d
0x14004d47e  jz      loc_14004D5CE
0x14004d484  mov     esi, [rsp+0A8h+var_6C]
  ... truncated ...
```
