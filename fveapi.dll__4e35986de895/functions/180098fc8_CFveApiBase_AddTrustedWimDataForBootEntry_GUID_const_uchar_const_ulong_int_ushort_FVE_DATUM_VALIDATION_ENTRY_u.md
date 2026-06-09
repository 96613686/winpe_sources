# CFveApiBase::AddTrustedWimDataForBootEntry(_GUID const *,uchar const *,ulong,int,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)

- ea: `0x180098fc8`
- end: `0x180099a50`
- name: `?AddTrustedWimDataForBootEntry@CFveApiBase@@QEAAJPEBU_GUID@@PEBEKHGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z`
- size: `2696`
- prototype: `__int64 __fastcall(CFveApiBase *this, const struct _GUID *, unsigned __int8 *, int, int, unsigned __int16, struct _FVE_DATUM_VALIDATION_ENTRY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18009eca8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x180044da4`
- `0x1800476f0`
- `0x180071210`
- `0x180098fc8`
- `0x18009e740`
- `0x18011efc2`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseStore` at `0x1800999d5`
- `bcd!BcdCloseStore` at `0x18012463f`
- `bcd!BcdCloseStore` at `0x1800999d5`
- `bcd!BcdCloseStore` at `0x18012463f`
- `bcd!BcdOpenSystemStore` at `0x1800998ab`
- `bcd!BcdOpenSystemStore` at `0x1800998ab`

## pseudocode

```c
__int64 __fastcall CFveApiBase::AddTrustedWimDataForBootEntry(
        CFveApiBase *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        int a4,
        int a5,
        unsigned __int16 a6,
        struct _FVE_DATUM_VALIDATION_ENTRY *a7,
        unsigned __int16 *a8)
{
  unsigned __int8 *v8; // rax
  CFveApiBase *v9; // r10
  unsigned __int64 v10; // rdx
  __int64 v11; // rdi
  unsigned __int16 v12; // r12
  PVOID *v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r9
  int First; // eax
  int v18; // eax
  unsigned __int16 v19; // r8
  int DataSegment; // eax
  unsigned __int16 v21; // ax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int16 v26; // ax
  unsigned __int16 v27; // r12
  int v28; // r9d
  unsigned __int16 v29; // r8
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  _OWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  _OWORD *v45; // rax
  int v46; // eax
  int v47; // r13d
  unsigned __int16 v49[2]; // [rsp+50h] [rbp-A8h] BYREF
  int v50; // [rsp+54h] [rbp-A4h]
  unsigned __int16 v51; // [rsp+58h] [rbp-A0h]
  int v52; // [rsp+5Ch] [rbp-9Ch]
  char v53; // [rsp+60h] [rbp-98h]
  int v54; // [rsp+64h] [rbp-94h]
  __int64 v55; // [rsp+68h] [rbp-90h] BYREF
  void *v56; // [rsp+70h] [rbp-88h]
  __int64 v57; // [rsp+78h] [rbp-80h] BYREF
  __int64 v58; // [rsp+80h] [rbp-78h]
  int v59; // [rsp+88h] [rbp-70h]
  const struct _GUID *v60; // [rsp+90h] [rbp-68h]
  __int64 v61; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v62[32]; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-38h]

  v59 = a4;
  v8 = a3;
  v56 = a3;
  v60 = a2;
  v9 = this;
  v58 = (__int64)this;
  v10 = 0;
  v57 = 0;
  v11 = 0;
  v55 = 0;
  v52 = 0;
  v49[0] = 0;
  v61 = 0;
  memset(v62, 0, sizeof(v62));
  v63 = 0;
  v12 = 0;
  LOBYTE(v54) = 0;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v8 = (unsigned __int8 *)v56;
    v9 = (CFveApiBase *)v58;
  }
  if ( !v8 )
  {
    v14 = -2147024809;
    v50 = -2147024809;
    if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 2) == 0 )
      goto LABEL_114;
    v15 = 171;
    v16 = 2147942487LL;
    goto LABEL_8;
  }
  First = FveDatasetGetFirst(*((_QWORD *)v9 + 146), 17, 7, &v57);
  v18 = FromNtStatus(First);
  v14 = v18;
  v50 = v18;
  v10 = 0;
  if ( v18 >= 0 )
  {
    DataSegment = FveDatumGetDataSegment(v57, &v55, v49);
    v18 = FromNtStatus(DataSegment);
    v14 = v18;
    v50 = v18;
    if ( v18 < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_114;
      v15 = 174;
      goto LABEL_15;
    }
    v11 = v55;
    if ( !v55 )
    {
      v18 = -2147024883;
      v14 = -2147024883;
      v50 = -2147024883;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_114;
      v15 = 175;
      goto LABEL_15;
    }
    v10 = v49[0] / 0x28uLL;
    v19 = v10;
    v52 = (unsigned __int16)v10;
    v49[0] /= 0x28u;
    if ( (unsigned __int16)v10 > 0x179u )
    {
      v14 = -2147024883;
      v50 = -2147024883;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_114;
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        176,
        &WPP_1559182127783aab3882fe828952d989_Traceguids,
        (unsigned __int16)v10,
        377,
        -2147024883);
LABEL_9:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_114;
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        &WPP_1559182127783aab3882fe828952d989_Traceguids,
        (unsigned __int16)v10);
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v19 = v52;
    }
  }
  else
  {
    if ( v18 != -805305819 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_114;
      v15 = 172;
LABEL_15:
      v16 = (unsigned int)v18;
LABEL_8:
      WPP_SF_d(v13[2], v15, &WPP_1559182127783aab3882fe828952d989_Traceguids, v16);
      goto LABEL_9;
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_1559182127783aab3882fe828952d989_Traceguids);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v14 = 0;
    v50 = 0;
    v19 = v52;
  }
  v21 = *a8;
  if ( *a8 )
  {
LABEL_78:
    v10 = (unsigned __int64)&WPP_GLOBAL_Control;
LABEL_79:
    if ( a5 )
    {
      if ( *a8 >= 0x179u )
      {
        v18 = -2147024883;
        v14 = -2147024883;
        v50 = -2147024883;
        if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 2) == 0 )
          goto LABEL_114;
        v15 = 184;
        goto LABEL_15;
      }
      v42 = FveDatumValidationInfoDataEntry(0, v60, 16, (char *)a7 + 40 * *a8);
      v43 = FromNtStatus(v42);
      v14 = v43;
      v50 = v43;
      v10 = 0;
      if ( v43 < 0 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_114;
        v39 = 185;
        goto LABEL_88;
      }
      *((_WORD *)a7 + 20 * *a8) = 4;
      *((_WORD *)a7 + 20 * (*a8)++ + 1) = 2;
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v10 = 0;
    }
    if ( *a8 >= 0x179u )
    {
      v43 = -2147024883;
      v14 = -2147024883;
      v50 = -2147024883;
      if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 2) == 0 )
        goto LABEL_114;
      v39 = 186;
      goto LABEL_88;
    }
    *((_WORD *)a7 + 20 * *a8) = 3;
    *((_WORD *)a7 + 20 * *a8 + 1) = 0;
    if ( v59 == 32 )
    {
      v44 = 5LL * *a8;
      v45 = v56;
      *(_OWORD *)((char *)a7 + 8 * v44 + 8) = *(_OWORD *)v56;
      *(_OWORD *)((char *)a7 + 8 * v44 + 24) = v45[1];
      ++*a8;
      if ( a5 )
      {
        v46 = BcdOpenSystemStore(&v61, 0);
        v43 = FromNtStatus(v46);
        v14 = v43;
        v50 = v43;
        v10 = 0;
        if ( v43 >= 0 )
        {
          v47 = *a8;
          v43 = CFveApiBase::StoreValidationDataForAppEx(v58, v61, v60, 4, 377, a7, a8, 0, 0);
          v14 = v43;
          v50 = v43;
          if ( v43 >= 0 )
          {
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_114;
            v38 = (unsigned int)*a8 - v47;
            v39 = 190;
            goto LABEL_69;
          }
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_114;
          v39 = 189;
        }
        else
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_114;
          v39 = 188;
        }
LABEL_88:
        v38 = (unsigned int)v43;
LABEL_69:
        WPP_SF_d(v13[2], v39, &WPP_1559182127783aab3882fe828952d989_Traceguids, v38);
        goto LABEL_70;
      }
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_114;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    }
    else
    {
      v14 = -2147024883;
      v50 = -2147024883;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_114;
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        187,
        &WPP_1559182127783aab3882fe828952d989_Traceguids,
        32,
        v59,
        -2147024883);
    }
LABEL_70:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_114;
  }
  if ( !a5 )
  {
    while ( v21 < v19 )
    {
      *((_WORD *)a7 + 20 * v21) = *(_WORD *)(v11 + 40LL * v21);
      *((_WORD *)a7 + 20 * *a8 + 1) = *(_WORD *)(v11 + 40LL * *a8 + 2);
      *((_DWORD *)a7 + 10 * *a8 + 1) = *(_DWORD *)(v11 + 40LL * *a8 + 4);
      v41 = 5LL * *a8;
      *(_OWORD *)((char *)a7 + 8 * v41 + 8) = *(_OWORD *)(v11 + 40LL * *a8 + 8);
      *(_OWORD *)((char *)a7 + 8 * v41 + 24) = *(_OWORD *)(v11 + 8 * v41 + 24);
      v21 = ++*a8;
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_78;
  }
  v22 = FveDatumValidationInfoDataEntry(0, v60, 16, v62);
  v18 = FromNtStatus(v22);
  v14 = v18;
  v50 = v18;
  if ( v18 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_114;
    v15 = 178;
    goto LABEL_15;
  }
  while ( 1 )
  {
    if ( v12 >= (unsigned __int16)v52 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v10 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v13 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_78;
      }
      goto LABEL_79;
    }
    v23 = 5LL * v12;
    v55 = v23;
    if ( *(_WORD *)(v11 + 40LL * v12) == 4 )
      break;
LABEL_72:
    v40 = 5LL * *a8;
    *(_OWORD *)((char *)a7 + 8 * v40) = *(_OWORD *)(v11 + 8 * v23);
    *(_OWORD *)((char *)a7 + 8 * v40 + 16) = *(_OWORD *)(v11 + 8 * v23 + 16);
    *((_QWORD *)a7 + v40 + 4) = *(_QWORD *)(v11 + 8 * v23 + 32);
    ++*a8;
    v51 = ++v12;
  }
  if ( memcmp_0((const void *)(v11 + 8 * (v23 + 1)), &v62[8], 0x20u) )
  {
    v23 = v55;
    goto LABEL_72;
  }
  v24 = 5LL * *a8;
  v25 = v55;
  *(_OWORD *)((char *)a7 + 8 * v24) = *(_OWORD *)(v11 + 8 * v55);
  *(_OWORD *)((char *)a7 + 8 * v24 + 16) = *(_OWORD *)(v11 + 8 * v25 + 16);
  *((_QWORD *)a7 + v24 + 4) = *(_QWORD *)(v11 + 8 * v25 + 32);
  v26 = ++*a8;
  v49[0] = *a8;
  v27 = v12 + 1;
  v51 = v27;
  LOBYTE(v28) = v54;
  while ( 1 )
  {
    v10 = 3;
    v29 = v52;
    if ( v27 >= (unsigned __int16)v52 )
      break;
    v30 = 5LL * v27;
    v58 = v30;
    if ( *(_WORD *)(v11 + 40LL * v27) != 3 )
    {
      v26 = v49[0];
      break;
    }
    v31 = memcmp_0((const void *)(v11 + 8 * (v30 + 1)), v56, 0x20u);
    v28 = (unsigned __int8)v54;
    if ( !v31 )
      v28 = 1;
    v54 = v28;
    v53 = v28;
    v32 = 5LL * v49[0];
    v33 = v58;
    *(_OWORD *)((char *)a7 + 8 * v32) = *(_OWORD *)(v11 + 8 * v58);
    *(_OWORD *)((char *)a7 + 8 * v32 + 16) = *(_OWORD *)(v11 + 8 * v33 + 16);
    *((_QWORD *)a7 + v32 + 4) = *(_QWORD *)(v11 + 8 * v33 + 32);
    v26 = ++*a8;
    v49[0] = *a8;
    v51 = ++v27;
  }
  if ( (_BYTE)v28 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_64;
    v36 = 181;
  }
  else
  {
    if ( v26 >= 0x179u )
    {
      v18 = -2147024883;
      v14 = -2147024883;
      v50 = -2147024883;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v10 = (unsigned __int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 179;
        goto LABEL_15;
      }
      goto LABEL_114;
    }
    *((_WORD *)a7 + 20 * v26) = 3;
    *((_WORD *)a7 + 20 * *a8 + 1) = 0;
    v34 = 5LL * *a8;
    v35 = v56;
    *(_OWORD *)((char *)a7 + 8 * v34 + 8) = *(_OWORD *)v56;
    *(_OWORD *)((char *)a7 + 8 * v34 + 24) = v35[1];
    ++*a8;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_64;
    v36 = 180;
  }
  WPP_SF_(v13[2], v36, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  v29 = v52;
  while ( 1 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
    if ( v27 >= v29 )
      break;
    v10 = 5LL * v27;
    v37 = 5LL * *a8;
    *(_OWORD *)((char *)a7 + 8 * v37) = *(_OWORD *)(v11 + 40LL * v27);
    *(_OWORD *)((char *)a7 + 8 * v37 + 16) = *(_OWORD *)(v11 + 40LL * v27 + 16);
    *((_QWORD *)a7 + v37 + 4) = *(_QWORD *)(v11 + 40LL * v27 + 32);
    ++*a8;
    v51 = ++v27;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
  {
    v38 = *a8;
    v39 = 182;
    goto LABEL_69;
  }
LABEL_114:
  if ( v61 )
  {
    BcdCloseStore(v61, v10);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v57 )
  {
    FveDatumFree(v57);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_d(v13[2], 192, &WPP_1559182127783aab3882fe828952d989_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180098fc8  mov     r11, rsp
0x180098fcb  mov     [r11+18h], rbx
0x180098fcf  mov     [r11+20h], rsi
0x180098fd3  push    rdi
0x180098fd4  push    r12
0x180098fd6  push    r13
0x180098fd8  push    r14
0x180098fda  push    r15
0x180098fdc  sub     rsp, 0D0h
0x180098fe3  mov     rax, cs:__security_cookie
0x180098fea  xor     rax, rsp
0x180098fed  mov     [rsp+0F8h+var_30], rax
0x180098ff5  mov     [rsp+0F8h+var_70], r9d
0x180098ffd  mov     rax, r8
0x180099000  mov     [rsp+0F8h+var_88], rax
0x180099005  mov     [rsp+0F8h+var_68], rdx
0x18009900d  mov     r10, rcx
0x180099010  mov     [rsp+0F8h+var_78], rcx
0x180099018  mov     r15, [rsp+0F8h+arg_30]
0x180099020  mov     r14, [rsp+0F8h+arg_38]
0x180099028  xor     edx, edx
0x18009902a  mov     [r11-80h], rdx
0x18009902e  mov     edi, edx
0x180099030  mov     [rsp+0F8h+var_90], rdx
0x180099035  mov     [rsp+0F8h+var_9C], edx
0x180099039  mov     [rsp+0F8h+var_A8], dx
0x18009903e  mov     [r11-60h], rdx
0x180099042  xorps   xmm0, xmm0
0x180099045  xor     ecx, ecx
0x180099047  movups  xmmword ptr [r11-58h], xmm0
0x18009904c  movups  xmmword ptr [r11-48h], xmm0
0x180099051  mov     [r11-38h], rcx
0x180099055  mov     r12d, edx
0x180099058  mov     byte ptr [rsp+0F8h+var_94], dl
0x18009905c  lea     r13, WPP_GLOBAL_Control
0x180099063  mov     rcx, cs:WPP_GLOBAL_Control
0x18009906a  lea     rsi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x180099071  cmp     rcx, r13
0x180099074  jz      short loc_1800990A1
0x180099076  test    byte ptr [rcx+1Ch], 20h
0x18009907a  jz      short loc_1800990A1
0x18009907c  mov     edx, 0AAh
0x180099081  mov     r8, rsi
0x180099084  mov     rcx, [rcx+10h]
0x180099088  call    WPP_SF_
0x18009908d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099094  mov     rax, [rsp+0F8h+var_88]
0x180099099  mov     r10, [rsp+0F8h+var_78]
0x1800990a1  test    rax, rax
0x1800990a4  jnz     short loc_1800990E5
0x1800990a6  mov     ebx, 80070057h
0x1800990ab  mov     [rsp+0F8h+var_A4], ebx
0x1800990af  cmp     rcx, r13
0x1800990b2  jz      loc_1800999BE
0x1800990b8  lea     edi, [rax+2]
0x1800990bb  test    [rcx+1Ch], dil
0x1800990bf  jz      loc_1800999BE
0x1800990c5  mov     edx, 0ABh
0x1800990ca  mov     r9d, ebx
0x1800990cd  mov     r8, rsi
0x1800990d0  mov     rcx, [rcx+10h]
0x1800990d4  call    WPP_SF_d
0x1800990d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800990e0  jmp     loc_1800999BE
0x1800990e5  mov     edx, 11h
0x1800990ea  lea     r8d, [rdx-0Ah]
0x1800990ee  lea     r9, [rsp+0F8h+var_80]
0x1800990f3  mov     rcx, [r10+490h]
0x1800990fa  call    FveDatasetGetFirst
0x1800990ff  mov     ecx, eax; int
0x180099101  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099106  mov     ebx, eax
0x180099108  mov     [rsp+0F8h+var_A4], eax
0x18009910c  xor     edx, edx
0x18009910e  test    eax, eax
0x180099110  jns     short loc_18009917C
0x180099112  cmp     eax, 0D0000225h
0x180099117  jz      short loc_180099140
0x180099119  mov     rcx, cs:WPP_GLOBAL_Control
0x180099120  cmp     rcx, r13
0x180099123  jz      loc_1800999BE
0x180099129  lea     edi, [rdx+2]
0x18009912c  test    [rcx+1Ch], dil
0x180099130  jz      loc_1800999BE
0x180099136  mov     edx, 0ACh
0x18009913b  mov     r9d, eax
0x18009913e  jmp     short loc_1800990CD
0x180099140  mov     rcx, cs:WPP_GLOBAL_Control
0x180099147  cmp     rcx, r13
0x18009914a  jz      short loc_18009916C
0x18009914c  test    byte ptr [rcx+1Ch], 8
0x180099150  jz      short loc_18009916C
0x180099152  mov     edx, 0ADh
0x180099157  mov     r8, rsi
0x18009915a  mov     rcx, [rcx+10h]
0x18009915e  call    WPP_SF_
0x180099163  mov     rcx, cs:WPP_GLOBAL_Control
0x18009916a  xor     edx, edx
0x18009916c  mov     ebx, edx
0x18009916e  mov     [rsp+0F8h+var_A4], edx
0x180099172  mov     r8d, [rsp+0F8h+var_9C]
0x180099177  jmp     loc_1800992BA
0x18009917c  lea     r8, [rsp+0F8h+var_A8]
0x180099181  lea     rdx, [rsp+0F8h+var_90]
0x180099186  mov     rcx, [rsp+0F8h+var_80]
0x18009918b  call    FveDatumGetDataSegment
0x180099190  mov     ecx, eax; int
0x180099192  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099197  mov     ebx, eax
0x180099199  mov     [rsp+0F8h+var_A4], eax
0x18009919d  test    eax, eax
0x18009919f  jns     short loc_1800991CA
0x1800991a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991a8  cmp     rcx, r13
0x1800991ab  jz      loc_1800999BE
0x1800991b1  mov     edi, 2
0x1800991b6  test    [rcx+1Ch], dil
0x1800991ba  jz      loc_1800999BE
0x1800991c0  mov     edx, 0AEh
0x1800991c5  jmp     loc_18009913B
0x1800991ca  mov     rdi, [rsp+0F8h+var_90]
0x1800991cf  test    rdi, rdi
0x1800991d2  jnz     short loc_180099208
0x1800991d4  mov     eax, 8007000Dh
0x1800991d9  mov     ebx, eax
0x1800991db  mov     [rsp+0F8h+var_A4], eax
0x1800991df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991e6  cmp     rcx, r13
0x1800991e9  jz      loc_1800999BE
0x1800991ef  mov     edi, 2
0x1800991f4  test    [rcx+1Ch], dil
0x1800991f8  jz      loc_1800999BE
0x1800991fe  mov     edx, 0AFh
0x180099203  jmp     loc_18009913B
0x180099208  movzx   ecx, [rsp+0F8h+var_A8]
0x18009920d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180099217  mul     rcx
0x18009921a  shr     rdx, 5
0x18009921e  movzx   r8d, dx
0x180099222  mov     [rsp+0F8h+var_9C], r8d
0x180099227  mov     [rsp+0F8h+var_A8], dx
0x18009922c  mov     r10d, 179h
0x180099232  cmp     dx, r10w
0x180099236  jbe     short loc_180099285
0x180099238  mov     eax, 8007000Dh
0x18009923d  mov     ebx, eax
0x18009923f  mov     [rsp+0F8h+var_A4], eax
0x180099243  mov     rcx, cs:WPP_GLOBAL_Control
0x18009924a  cmp     rcx, r13
0x18009924d  jz      loc_1800999BE
0x180099253  mov     edi, 2
0x180099258  test    [rcx+1Ch], dil
0x18009925c  jz      loc_1800999BE
0x180099262  movzx   r9d, dx
0x180099266  mov     edx, 0B0h
0x18009926b  mov     dword ptr [rsp+0F8h+var_D0], eax
0x18009926f  mov     [rsp+0F8h+var_D8], r10d
0x180099274  mov     r8, rsi
0x180099277  mov     rcx, [rcx+10h]
0x18009927b  call    WPP_SF_DDD
0x180099280  jmp     loc_1800990D9
0x180099285  mov     rcx, cs:WPP_GLOBAL_Control
0x18009928c  cmp     rcx, r13
0x18009928f  jz      short loc_1800992B8
0x180099291  test    byte ptr [rcx+1Ch], 8
0x180099295  jz      short loc_1800992B8
0x180099297  movzx   r9d, dx
0x18009929b  mov     edx, 0B1h
0x1800992a0  mov     r8, rsi
0x1800992a3  mov     rcx, [rcx+10h]
0x1800992a7  call    WPP_SF_d
0x1800992ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800992b3  mov     r8d, [rsp+0F8h+var_9C]
0x1800992b8  xor     edx, edx
0x1800992ba  movzx   eax, word ptr [r14]
0x1800992be  test    ax, ax
0x1800992c1  jnz     loc_1800996C9
0x1800992c7  cmp     [rsp+0F8h+arg_20], edx
0x1800992ce  jz      loc_18009965A
0x1800992d4  lea     r9, [rsp+0F8h+var_58]
0x1800992dc  mov     r8d, 10h
0x1800992e2  mov     rdx, [rsp+0F8h+var_68]
0x1800992ea  xor     ecx, ecx
0x1800992ec  call    FveDatumValidationInfoDataEntry
0x1800992f1  mov     ecx, eax; int
0x1800992f3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800992f8  mov     ebx, eax
0x1800992fa  mov     [rsp+0F8h+var_A4], eax
0x1800992fe  test    eax, eax
0x180099300  jns     short loc_18009932B
0x180099302  mov     rcx, cs:WPP_GLOBAL_Control
0x180099309  cmp     rcx, r13
0x18009930c  jz      loc_1800999BE
0x180099312  mov     edi, 2
0x180099317  test    [rcx+1Ch], dil
0x18009931b  jz      loc_1800999BE
0x180099321  mov     edx, 0B2h
0x180099326  jmp     loc_18009913B
0x18009932b  mov     r8d, 4
0x180099331  lea     r13d, [r8-3]
0x180099335  cmp     r12w, word ptr [rsp+0F8h+var_9C]
0x18009933b  jnb     loc_18009961F
0x180099341  movzx   eax, r12w
0x180099345  lea     rdx, [rax+rax*4]
0x180099349  mov     [rsp+0F8h+var_90], rdx
0x18009934e  cmp     [rdi+rdx*8], r8w
0x180099353  jnz     loc_1800995E3
0x180099359  inc     rdx
0x18009935c  lea     rcx, [rdi+rdx*8]; Buf1
0x180099360  mov     r8d, 20h ; ' '; Size
0x180099366  lea     rdx, [rsp+0F8h+Buf2]; Buf2
0x18009936e  call    memcmp_0
0x180099373  test    eax, eax
0x180099375  jnz     loc_1800995D8
0x18009937b  movzx   eax, word ptr [r14]
0x18009937f  lea     rcx, [rax+rax*4]
0x180099383  mov     rax, [rsp+0F8h+var_90]
0x180099388  movups  xmm0, xmmword ptr [rdi+rax*8]
0x18009938c  movups  xmmword ptr [r15+rcx*8], xmm0
0x180099391  movups  xmm1, xmmword ptr [rdi+rax*8+10h]
0x180099396  movups  xmmword ptr [r15+rcx*8+10h], xmm1
0x18009939c  movsd   xmm0, qword ptr [rdi+rax*8+20h]
0x1800993a2  movsd   qword ptr [r15+rcx*8+20h], xmm0
0x1800993a9  add     [r14], r13w
0x1800993ad  movzx   eax, word ptr [r14]
0x1800993b1  mov     [rsp+0F8h+var_A8], ax
0x1800993b6  add     r12w, r13w
0x1800993ba  mov     [rsp+0F8h+var_A0], r12w
0x1800993c0  mov     r9d, [rsp+0F8h+var_94]
0x1800993c5  mov     edx, 3
0x1800993ca  mov     r8d, [rsp+0F8h+var_9C]
0x1800993cf  cmp     r12w, r8w
0x1800993d3  jnb     loc_180099470
0x1800993d9  movzx   eax, r12w
0x1800993dd  lea     rax, [rax+rax*4]
0x1800993e1  mov     [rsp+0F8h+var_78], rax
0x1800993e9  cmp     [rdi+rax*8], dx
0x1800993ed  jnz     short loc_18009946B
0x1800993ef  inc     rax
0x1800993f2  lea     rcx, [rdi+rax*8]; Buf1
0x1800993f6  lea     r8d, [rdx+1Dh]; Size
0x1800993fa  mov     rdx, [rsp+0F8h+var_88]; Buf2
0x1800993ff  call    memcmp_0
0x180099404  mov     r9d, [rsp+0F8h+var_94]
0x180099409  movzx   r9d, r9b
0x18009940d  test    eax, eax
0x18009940f  cmovz   r9d, r13d
0x180099413  mov     [rsp+0F8h+var_94], r9d
0x180099418  mov     [rsp+0F8h+var_98], r9b
0x18009941d  movzx   eax, [rsp+0F8h+var_A8]
0x180099422  lea     rcx, [rax+rax*4]
0x180099426  mov     rax, [rsp+0F8h+var_78]
0x18009942e  movups  xmm0, xmmword ptr [rdi+rax*8]
0x180099432  movups  xmmword ptr [r15+rcx*8], xmm0
0x180099437  movups  xmm1, xmmword ptr [rdi+rax*8+10h]
0x18009943c  movups  xmmword ptr [r15+rcx*8+10h], xmm1
0x180099442  movsd   xmm0, qword ptr [rdi+rax*8+20h]
0x180099448  movsd   qword ptr [r15+rcx*8+20h], xmm0
0x18009944f  add     [r14], r13w
0x180099453  movzx   eax, word ptr [r14]
0x180099457  mov     [rsp+0F8h+var_A8], ax
0x18009945c  add     r12w, r13w
0x180099460  mov     [rsp+0F8h+var_A0], r12w
0x180099466  jmp     loc_1800993C5
0x18009946b  movzx   eax, [rsp+0F8h+var_A8]
0x180099470  test    r9b, r9b
0x180099473  jnz     loc_180099520
0x180099479  mov     r9d, 179h
0x18009947f  cmp     ax, r9w
0x180099483  jb      short loc_1800994C0
0x180099485  mov     eax, 8007000Dh
0x18009948a  mov     ebx, eax
0x18009948c  mov     [rsp+0F8h+var_A4], eax
0x180099490  mov     rcx, cs:WPP_GLOBAL_Control
0x180099497  lea     rdx, WPP_GLOBAL_Control
0x18009949e  cmp     rcx, rdx
0x1800994a1  jz      loc_1800999BE
0x1800994a7  mov     edi, 2
0x1800994ac  test    [rcx+1Ch], dil
0x1800994b0  jz      loc_1800999BE
0x1800994b6  mov     edx, 0B3h
0x1800994bb  jmp     loc_18009913B
0x1800994c0  movzx   eax, ax
0x1800994c3  lea     rcx, [rax+rax*4]
0x1800994c7  mov     [r15+rcx*8], dx
0x1800994cc  movzx   eax, word ptr [r14]
0x1800994d0  lea     rcx, [rax+rax*4]
0x1800994d4  xor     eax, eax
0x1800994d6  mov     [r15+rcx*8+2], ax
0x1800994dc  movzx   eax, word ptr [r14]
0x1800994e0  lea     rcx, [rax+rax*4]
0x1800994e4  mov     rax, [rsp+0F8h+var_88]
0x1800994e9  movups  xmm0, xmmword ptr [rax]
0x1800994ec  movups  xmmword ptr [r15+rcx*8+8], xmm0
0x1800994f2  movups  xmm1, xmmword ptr [rax+10h]
0x1800994f6  movups  xmmword ptr [r15+rcx*8+18h], xmm1
0x1800994fc  add     [r14], r13w
0x180099500  mov     rcx, cs:WPP_GLOBAL_Control
0x180099507  lea     rax, WPP_GLOBAL_Control
0x18009950e  cmp     rcx, rax
  ... truncated ...
```
