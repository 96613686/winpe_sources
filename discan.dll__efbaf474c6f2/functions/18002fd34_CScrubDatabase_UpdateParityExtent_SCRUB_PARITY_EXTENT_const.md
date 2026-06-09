# CScrubDatabase::UpdateParityExtent(_SCRUB_PARITY_EXTENT const *)

- ea: `0x18002fd34`
- end: `0x180030613`
- name: `?UpdateParityExtent@CScrubDatabase@@QEAAJPEBU_SCRUB_PARITY_EXTENT@@@Z`
- size: `2271`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this, const struct _SCRUB_PARITY_EXTENT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18003061c`

## callees

- `0x1800032f8`
- `0x180006470`
- `0x180006498`
- `0x180006688`
- `0x18002e820`
- `0x18002eda8`
- `0x18002f9e0`
- `0x18002fd34`
- `0x1800309c8`
- `0x180037620`

## import_xrefs

- `ESENT!JetMove` at `0x18002ff4f`
- `ESENT!JetMove` at `0x18003024a`
- `ESENT!JetMove` at `0x18003042d`
- `ESENT!JetMove` at `0x18002ff4f`
- `ESENT!JetMove` at `0x18003024a`
- `ESENT!JetMove` at `0x18003042d`
- `ESENT!JetMakeKey` at `0x18002fe64`
- `ESENT!JetMakeKey` at `0x18002fe64`
- `ESENT!JetSeek` at `0x18002feb4`
- `ESENT!JetSeek` at `0x18002feb4`
- `ESENT!JetDelete` at `0x1800303e4`
- `ESENT!JetDelete` at `0x18003051d`
- `ESENT!JetDelete` at `0x1800303e4`
- `ESENT!JetDelete` at `0x18003051d`

## string_xrefs

- `0x18002fd67`: `CScrubDatabase::UpdateParityExtent`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::UpdateParityExtent(CScrubDatabase *this, const struct _SCRUB_PARITY_EXTENT *a2)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v5; // rdx
  USHORT Length; // cx
  USHORT v7; // r8
  USHORT v8; // ax
  PVOID *v9; // r8
  JET_TABLEID v10; // rdx
  JET_SESID v11; // rcx
  JET_ERR Key; // r15d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  const struct _SCRUB_PARITY_EXTENT *v20; // rdx
  unsigned int v21; // ebx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  PVOID *v25; // r10
  __int64 v26; // r11
  __int64 v27; // r8
  __int64 v28; // rbx
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // r9
  int v32; // eax
  unsigned int v33; // r8d
  JET_ERR v34; // eax
  unsigned int v35; // r8d
  int v36; // eax
  __int64 v37; // r8
  PVOID *v38; // rcx
  int v39; // eax
  const char *v41; // [rsp+30h] [rbp-50h] BYREF
  int ColumnData; // [rsp+38h] [rbp-48h]
  __int64 pvData; // [rsp+40h] [rbp-40h] BYREF
  __int128 v44; // [rsp+48h] [rbp-38h] BYREF
  __int128 v45; // [rsp+58h] [rbp-28h] BYREF
  __int128 v46; // [rsp+68h] [rbp-18h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v41 = "CScrubDatabase::UpdateParityExtent";
  v5 = ThreadLocalStoragePointer[tls_index];
  Length = GlobalIndentString.Length;
  v7 = ++*(_WORD *)(v5 + 8);
  *(_QWORD *)(v5 + 16) = "CScrubDatabase::UpdateParityExtent";
  v8 = Length;
  if ( v7 < Length )
  {
    v8 = v7;
    Length = v7;
  }
  LOWORD(v45) = v8;
  DWORD1(v45) = 0;
  *((_QWORD *)&v45 + 1) = off_180047060;
  WORD1(v45) = Length;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::UpdateParityExtent");
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_iii(v9[2], 31);
  }
  v10 = *((_QWORD *)this + 3);
  v11 = *((_QWORD *)this + 1);
  pvData = *(_QWORD *)a2;
  Key = JetMakeKey(v11, v10, &pvData, 8u, 1u);
  if ( Key )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_147;
    }
    v14 = 32;
    goto LABEL_146;
  }
  v15 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 4u);
  Key = v15;
  if ( v15 != -1601 && v15 != 1039 && v15 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_147;
    }
    v14 = 33;
    goto LABEL_146;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v15);
  }
  v44 = 0;
  if ( Key == -1601 )
  {
    Key = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    if ( Key == -1603 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_34;
      }
      v19 = 35;
LABEL_33:
      WPP_SF_(v18[2], v19, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids);
LABEL_34:
      v20 = a2;
LABEL_35:
      v21 = CScrubDatabase::AddParityExtentRow(this, v20);
      ColumnData = v21;
      goto LABEL_153;
    }
    if ( Key )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_147;
      }
      v14 = 36;
      goto LABEL_146;
    }
    ColumnData = CScrubDatabase::RetrieveColumnData(this, (struct _SCRUB_PARITY_EXTENT *)&v44, v17);
    v21 = ColumnData;
    if ( ColumnData < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_153;
      }
      v23 = 37;
LABEL_46:
      v24 = v21;
LABEL_47:
      WPP_SF_d(v22[2], v23, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v24);
      goto LABEL_153;
    }
    if ( !DoesScrubParityExtentOverlap((const struct _SCRUB_PARITY_EXTENT *)&v44, a2) )
      goto LABEL_35;
LABEL_49:
    v25 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_50;
  }
  v32 = CScrubDatabase::RetrieveColumnData(this, (struct _SCRUB_PARITY_EXTENT *)&v44, v16);
  ColumnData = v32;
  v21 = v32;
  if ( !Key )
  {
    if ( v32 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_153;
      }
      v23 = 38;
      goto LABEL_46;
    }
    goto LABEL_49;
  }
  if ( v32 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_153;
    }
    v23 = 39;
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_iii(*((_QWORD *)WPP_GLOBAL_Control + 2), 40);
  }
  if ( !DoesScrubParityExtentOverlap((const struct _SCRUB_PARITY_EXTENT *)&v44, a2) )
  {
    Key = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    if ( Key == -1603 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_34;
      }
      v19 = 41;
      goto LABEL_33;
    }
    if ( Key )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_147;
      }
      v14 = 42;
      goto LABEL_146;
    }
    ColumnData = CScrubDatabase::RetrieveColumnData(this, (struct _SCRUB_PARITY_EXTENT *)&v44, v33);
    v21 = ColumnData;
    if ( ColumnData < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_153;
      }
      v23 = 43;
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_iii(*((_QWORD *)WPP_GLOBAL_Control + 2), 44);
    }
    if ( !DoesScrubParityExtentOverlap((const struct _SCRUB_PARITY_EXTENT *)&v44, a2) )
    {
      if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
        WPP_SF_iii(v25[2], 45);
      goto LABEL_34;
    }
  }
LABEL_50:
  if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
  {
    WPP_SF_iii(v25[2], 46);
    v25 = (PVOID *)WPP_GLOBAL_Control;
  }
  v26 = v44;
  v27 = *(_QWORD *)a2;
  v28 = *((_QWORD *)&v44 + 1);
  v29 = *(_QWORD *)a2 + *((_QWORD *)a2 + 1);
  v46 = 0;
  v30 = v44 + *((_QWORD *)&v44 + 1);
  if ( v29 > (_QWORD)v44 + *((_QWORD *)&v44 + 1) )
    v30 = v29;
  if ( (__int64)v44 < v27 )
    v27 = v44;
  v31 = v30 - v27;
  *(_QWORD *)&v46 = v27;
  *((_QWORD *)&v46 + 1) = v31;
  if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
  {
    WPP_SF_iii(v25[2], 47);
    v26 = v44;
    v25 = (PVOID *)WPP_GLOBAL_Control;
    v31 = *((_QWORD *)&v46 + 1);
    v27 = v46;
    v28 = *((_QWORD *)&v44 + 1);
  }
  if ( v27 == v26 && v31 == v28 )
  {
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
      WPP_SF_(v25[2], 48, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids);
    ColumnData = 0;
    v21 = 0;
    goto LABEL_153;
  }
  if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
    WPP_SF_iii(v25[2], 49);
  Key = JetDelete(*((_QWORD *)this + 1), *((_QWORD *)this + 3));
  if ( !Key )
  {
    while ( 1 )
    {
      v34 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
      Key = v34;
      if ( v34 == -1603 )
      {
LABEL_151:
        v21 = CScrubDatabase::AddParityExtentRow(this, (const struct _SCRUB_PARITY_EXTENT *)&v46);
        goto LABEL_152;
      }
      if ( v34 )
        break;
      v45 = 0;
      v36 = CScrubDatabase::RetrieveColumnData(this, (struct _SCRUB_PARITY_EXTENT *)&v45, v35);
      ColumnData = v36;
      v21 = v36;
      if ( v36 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = 52;
          v24 = (unsigned int)v36;
          goto LABEL_47;
        }
        goto LABEL_153;
      }
      if ( !DoesScrubParityExtentOverlap(
              (const struct _SCRUB_PARITY_EXTENT *)&v45,
              (const struct _SCRUB_PARITY_EXTENT *)&v46) )
        goto LABEL_151;
      v37 = *((_QWORD *)&v45 + 1) + v45;
      if ( (_QWORD)v46 + *((_QWORD *)&v46 + 1) > *((_QWORD *)&v45 + 1) + (_QWORD)v45 )
        v37 = v46 + *((_QWORD *)&v46 + 1);
      *((_QWORD *)&v46 + 1) = v37 - v46;
      v38 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_iii(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)(Key + 53));
          v38 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 1) != 0 && *((_BYTE *)v38 + 25) >= 4u )
          WPP_SF_iii(v38[2], 54);
      }
      Key = JetDelete(*((_QWORD *)this + 1), *((_QWORD *)this + 3));
      if ( Key )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 55;
          goto LABEL_146;
        }
        goto LABEL_147;
      }
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 51;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 50;
LABEL_146:
    WPP_SF_d(v13[2], v14, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, (unsigned int)Key);
  }
LABEL_147:
  if ( Key == -1011 )
  {
    v21 = -2147024882;
  }
  else
  {
    v39 = -Key;
    if ( Key > 0 )
      LOWORD(v39) = Key;
    v21 = Key & 0x8E5E0000 | (unsigned __int16)v39 | 0xE5E0000;
  }
LABEL_152:
  ColumnData = v21;
LABEL_153:
  CHResultImp::~CHResultImp((CHResultImp *)&v41);
  return v21;
}

```

## disassembly

```asm
0x18002fd34  mov     [rsp-28h+arg_10], rbx
0x18002fd39  mov     [rsp-28h+arg_18], rsi
0x18002fd3e  push    rbp
0x18002fd3f  push    rdi
0x18002fd40  push    r12
0x18002fd42  push    r13
0x18002fd44  push    r15
0x18002fd46  mov     rbp, rsp
0x18002fd49  sub     rsp, 80h
0x18002fd50  mov     rax, cs:__security_cookie
0x18002fd57  xor     rax, rsp
0x18002fd5a  mov     [rbp+var_8], rax
0x18002fd5e  mov     rax, gs:58h
0x18002fd67  lea     r9, aCscrubdatabase_3; "CScrubDatabase::UpdateParityExtent"
0x18002fd6e  mov     rdi, rcx
0x18002fd71  mov     r8d, 8
0x18002fd77  mov     ecx, cs:_tls_index
0x18002fd7d  mov     r12, rdx
0x18002fd80  mov     r13d, 1
0x18002fd86  mov     [rbp+var_50], r9
0x18002fd8a  mov     rdx, [rax+rcx*8]
0x18002fd8e  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002fd95  mov     eax, 10h
0x18002fd9a  add     [r8+rdx], r13w
0x18002fd9f  movzx   r8d, word ptr [r8+rdx]
0x18002fda4  mov     [rax+rdx], r9
0x18002fda8  cmp     r8w, cx
0x18002fdac  movzx   eax, cx
0x18002fdaf  cmovb   ax, r8w
0x18002fdb4  cmovb   cx, r8w
0x18002fdb9  mov     word ptr [rbp+var_28], ax
0x18002fdbd  xor     eax, eax
0x18002fdbf  mov     dword ptr [rbp+var_28+4], eax
0x18002fdc2  mov     rax, cs:off_180047060; "                                       "...
0x18002fdc9  mov     qword ptr [rbp+var_28+8], rax
0x18002fdcd  mov     word ptr [rbp+var_28+2], cx
0x18002fdd1  mov     r8, cs:WPP_GLOBAL_Control
0x18002fdd8  lea     rbx, WPP_GLOBAL_Control
0x18002fddf  cmp     r8, rbx
0x18002fde2  jz      short loc_18002FE45
0x18002fde4  test    [r8+1Ch], r13b
0x18002fde8  jz      short loc_18002FE0E
0x18002fdea  cmp     byte ptr [r8+19h], 5
0x18002fdef  jb      short loc_18002FE0E
0x18002fdf1  mov     rcx, [r8+10h]; LoggerHandle
0x18002fdf5  lea     edx, [r13+0Ch]
0x18002fdf9  mov     qword ptr [rsp+80h+grbit], r9; __int64
0x18002fdfe  lea     r9, [rbp+var_28]
0x18002fe02  call    WPP_SF_aZs
0x18002fe07  mov     r8, cs:WPP_GLOBAL_Control
0x18002fe0e  cmp     r8, rbx
0x18002fe11  jz      short loc_18002FE45
0x18002fe13  test    [r8+1Ch], r13b
0x18002fe17  jz      short loc_18002FE45
0x18002fe19  cmp     byte ptr [r8+19h], 4
0x18002fe1e  jb      short loc_18002FE45
0x18002fe20  mov     rcx, [r12+8]
0x18002fe25  mov     edx, 1Fh
0x18002fe2a  mov     r9, [r12]
0x18002fe2e  mov     [rsp+80h+var_58], rcx
0x18002fe33  lea     rax, [r9+rcx]
0x18002fe37  mov     rcx, [r8+10h]
0x18002fe3b  mov     qword ptr [rsp+80h+grbit], rax
0x18002fe40  call    WPP_SF_iii
0x18002fe45  mov     rax, [r12]
0x18002fe49  lea     r8, [rbp+pvData]; pvData
0x18002fe4d  mov     rdx, [rdi+18h]; tableid
0x18002fe51  mov     r9d, 8; cbData
0x18002fe57  mov     rcx, [rdi+8]; sesid
0x18002fe5b  mov     [rbp+pvData], rax
0x18002fe5f  mov     [rsp+80h+grbit], r13d; grbit
0x18002fe64  call    cs:__imp_JetMakeKey
0x18002fe6a  mov     r15d, eax
0x18002fe6d  test    eax, eax
0x18002fe6f  jz      short loc_18002FEA6
0x18002fe71  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe78  cmp     rcx, rbx
0x18002fe7b  jz      loc_1800305A8
0x18002fe81  test    [rcx+1Ch], r13b
0x18002fe85  jz      loc_1800305A8
0x18002fe8b  cmp     byte ptr [rcx+19h], 2
0x18002fe8f  jb      loc_1800305A8
0x18002fe95  mov     edx, 20h ; ' '
0x18002fe9a  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002fea1  jmp     loc_18003059C
0x18002fea6  mov     rdx, [rdi+18h]; tableid
0x18002feaa  mov     r8d, 4; grbit
0x18002feb0  mov     rcx, [rdi+8]; sesid
0x18002feb4  call    cs:__imp_JetSeek
0x18002feba  mov     r15d, eax
0x18002febd  cmp     eax, 0FFFFF9BFh
0x18002fec2  jz      short loc_18002FEFA
0x18002fec4  cmp     eax, 40Fh
0x18002fec9  jz      short loc_18002FEFA
0x18002fecb  test    eax, eax
0x18002fecd  jz      short loc_18002FEFA
0x18002fecf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fed6  cmp     rcx, rbx
0x18002fed9  jz      loc_1800305A8
0x18002fedf  test    [rcx+1Ch], r13b
0x18002fee3  jz      loc_1800305A8
0x18002fee9  cmp     byte ptr [rcx+19h], 2
0x18002feed  jb      loc_1800305A8
0x18002fef3  mov     edx, 21h ; '!'
0x18002fef8  jmp     short loc_18002FE9A
0x18002fefa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff01  lea     rsi, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002ff08  cmp     rcx, rbx
0x18002ff0b  jz      short loc_18002FF2D
0x18002ff0d  test    [rcx+1Ch], r13b
0x18002ff11  jz      short loc_18002FF2D
0x18002ff13  cmp     byte ptr [rcx+19h], 2
0x18002ff17  jb      short loc_18002FF2D
0x18002ff19  mov     rcx, [rcx+10h]
0x18002ff1d  mov     edx, 22h ; '"'
0x18002ff22  mov     r9d, r15d
0x18002ff25  mov     r8, rsi
0x18002ff28  call    WPP_SF_d
0x18002ff2d  xorps   xmm0, xmm0
0x18002ff30  movups  [rbp+var_38], xmm0
0x18002ff34  cmp     r15d, 0FFFFF9BFh
0x18002ff3b  jnz     loc_180030152
0x18002ff41  mov     rdx, [rdi+18h]; tableid
0x18002ff45  xor     r9d, r9d; grbit
0x18002ff48  mov     rcx, [rdi+8]; sesid
0x18002ff4c  mov     r8d, r13d; cRow
0x18002ff4f  call    cs:__imp_JetMove
0x18002ff55  mov     r15d, eax
0x18002ff58  cmp     eax, 0FFFFF9BDh
0x18002ff5d  jnz     short loc_18002FF9D
0x18002ff5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff66  cmp     rcx, rbx
0x18002ff69  jz      short loc_18002FF88
0x18002ff6b  test    [rcx+1Ch], r13b
0x18002ff6f  jz      short loc_18002FF88
0x18002ff71  cmp     byte ptr [rcx+19h], 4
0x18002ff75  jb      short loc_18002FF88
0x18002ff77  mov     edx, 23h ; '#'
0x18002ff7c  mov     rcx, [rcx+10h]
0x18002ff80  mov     r8, rsi
0x18002ff83  call    WPP_SF_
0x18002ff88  mov     rdx, r12; struct _SCRUB_PARITY_EXTENT *
0x18002ff8b  mov     rcx, rdi; this
0x18002ff8e  call    ?AddParityExtentRow@CScrubDatabase@@AEAAJPEBU_SCRUB_PARITY_EXTENT@@@Z; CScrubDatabase::AddParityExtentRow(_SCRUB_PARITY_EXTENT const *)
0x18002ff93  mov     ebx, eax
0x18002ff95  mov     [rbp+var_48], eax
0x18002ff98  jmp     loc_1800305E0
0x18002ff9d  test    r15d, r15d
0x18002ffa0  jz      short loc_18002FFD0
0x18002ffa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffa9  cmp     rcx, rbx
0x18002ffac  jz      loc_1800305A8
0x18002ffb2  test    [rcx+1Ch], r13b
0x18002ffb6  jz      loc_1800305A8
0x18002ffbc  cmp     byte ptr [rcx+19h], 2
0x18002ffc0  jb      loc_1800305A8
0x18002ffc6  mov     edx, 24h ; '$'
0x18002ffcb  jmp     loc_180030599
0x18002ffd0  lea     rdx, [rbp+var_38]; struct _SCRUB_PARITY_EXTENT *
0x18002ffd4  mov     rcx, rdi; this
0x18002ffd7  call    ?RetrieveColumnData@CScrubDatabase@@AEAAJPEAU_SCRUB_PARITY_EXTENT@@K@Z; CScrubDatabase::RetrieveColumnData(_SCRUB_PARITY_EXTENT *,ulong)
0x18002ffdc  mov     [rbp+var_48], eax
0x18002ffdf  mov     ebx, eax
0x18002ffe1  test    eax, eax
0x18002ffe3  jns     short loc_180030029
0x18002ffe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffec  lea     rax, WPP_GLOBAL_Control
0x18002fff3  cmp     rcx, rax
0x18002fff6  jz      loc_1800305E0
0x18002fffc  test    [rcx+1Ch], r13b
0x180030000  jz      loc_1800305E0
0x180030006  cmp     byte ptr [rcx+19h], 2
0x18003000a  jb      loc_1800305E0
0x180030010  mov     edx, 25h ; '%'
0x180030015  mov     r9d, ebx
0x180030018  mov     rcx, [rcx+10h]
0x18003001c  mov     r8, rsi
0x18003001f  call    WPP_SF_d
0x180030024  jmp     loc_1800305E0
0x180030029  mov     rdx, r12; struct _SCRUB_PARITY_EXTENT *
0x18003002c  lea     rcx, [rbp+var_38]; struct _SCRUB_PARITY_EXTENT *
0x180030030  call    ?DoesScrubParityExtentOverlap@@YA_NPEBU_SCRUB_PARITY_EXTENT@@0@Z; DoesScrubParityExtentOverlap(_SCRUB_PARITY_EXTENT const *,_SCRUB_PARITY_EXTENT const *)
0x180030035  test    al, al
0x180030037  jz      loc_18002FF8B
0x18003003d  mov     r10, cs:WPP_GLOBAL_Control
0x180030044  lea     rbx, WPP_GLOBAL_Control
0x18003004b  cmp     r10, rbx
0x18003004e  jz      short loc_180030088
0x180030050  test    [r10+1Ch], r13b
0x180030054  jz      short loc_180030088
0x180030056  cmp     byte ptr [r10+19h], 4
0x18003005b  jb      short loc_180030088
0x18003005d  mov     rax, qword ptr [rbp+var_38+8]
0x180030061  mov     edx, 2Eh ; '.'
0x180030066  mov     r9, qword ptr [rbp+var_38]
0x18003006a  mov     [rsp+80h+var_58], rax
0x18003006f  lea     rcx, [r9+rax]
0x180030073  mov     qword ptr [rsp+80h+grbit], rcx
0x180030078  mov     rcx, [r10+10h]
0x18003007c  call    WPP_SF_iii
0x180030081  mov     r10, cs:WPP_GLOBAL_Control
0x180030088  mov     r11, qword ptr [rbp+var_38]
0x18003008c  xorps   xmm0, xmm0
0x18003008f  mov     r8, [r12]
0x180030093  mov     rbx, qword ptr [rbp+var_38+8]
0x180030097  mov     rcx, [r12+8]
0x18003009c  add     rcx, r8
0x18003009f  movups  [rbp+var_18], xmm0
0x1800300a3  lea     r9, [r11+rbx]
0x1800300a7  cmp     rcx, r9
0x1800300aa  cmova   r9, rcx
0x1800300ae  cmp     r11, r8
0x1800300b1  cmovl   r8, r11
0x1800300b5  sub     r9, r8
0x1800300b8  mov     qword ptr [rbp+var_18], r8
0x1800300bc  mov     qword ptr [rbp+var_18+8], r9
0x1800300c0  lea     r12, WPP_GLOBAL_Control
0x1800300c7  cmp     r10, r12
0x1800300ca  jz      short loc_18003010F
0x1800300cc  test    [r10+1Ch], r13b
0x1800300d0  jz      short loc_18003010F
0x1800300d2  cmp     byte ptr [r10+19h], 4
0x1800300d7  jb      short loc_18003010F
0x1800300d9  mov     rcx, [r10+10h]
0x1800300dd  lea     rax, [r9+r8]
0x1800300e1  mov     [rsp+80h+var_58], r9
0x1800300e6  mov     edx, 2Fh ; '/'
0x1800300eb  mov     r9, r8
0x1800300ee  mov     qword ptr [rsp+80h+grbit], rax
0x1800300f3  call    WPP_SF_iii
0x1800300f8  mov     r11, qword ptr [rbp+var_38]
0x1800300fc  mov     r10, cs:WPP_GLOBAL_Control
0x180030103  mov     r9, qword ptr [rbp+var_18+8]
0x180030107  mov     r8, qword ptr [rbp+var_18]
0x18003010b  mov     rbx, qword ptr [rbp+var_38+8]
0x18003010f  cmp     r8, r11
0x180030112  jnz     loc_1800303AB
0x180030118  cmp     r9, rbx
0x18003011b  jnz     loc_1800303AB
0x180030121  cmp     r10, r12
0x180030124  jz      short loc_180030144
0x180030126  test    [r10+1Ch], r13b
0x18003012a  jz      short loc_180030144
0x18003012c  cmp     byte ptr [r10+19h], 4
0x180030131  jb      short loc_180030144
0x180030133  mov     rcx, [r10+10h]
0x180030137  mov     edx, 30h ; '0'
0x18003013c  mov     r8, rsi
0x18003013f  call    WPP_SF_
0x180030144  mov     [rbp+var_48], 0
0x18003014b  xor     ebx, ebx
0x18003014d  jmp     loc_1800305E0
0x180030152  lea     rdx, [rbp+var_38]; struct _SCRUB_PARITY_EXTENT *
0x180030156  mov     rcx, rdi; this
0x180030159  call    ?RetrieveColumnData@CScrubDatabase@@AEAAJPEAU_SCRUB_PARITY_EXTENT@@K@Z; CScrubDatabase::RetrieveColumnData(_SCRUB_PARITY_EXTENT *,ulong)
0x18003015e  mov     [rbp+var_48], eax
0x180030161  mov     ebx, eax
0x180030163  test    r15d, r15d
0x180030166  jnz     short loc_1800301A4
0x180030168  test    eax, eax
0x18003016a  jns     loc_18003003D
0x180030170  mov     rcx, cs:WPP_GLOBAL_Control
0x180030177  lea     rax, WPP_GLOBAL_Control
0x18003017e  cmp     rcx, rax
0x180030181  jz      loc_1800305E0
0x180030187  test    [rcx+1Ch], r13b
0x18003018b  jz      loc_1800305E0
0x180030191  cmp     byte ptr [rcx+19h], 2
0x180030195  jb      loc_1800305E0
0x18003019b  lea     edx, [r15+26h]
0x18003019f  jmp     loc_180030015
0x1800301a4  test    eax, eax
0x1800301a6  jns     short loc_1800301DD
0x1800301a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800301af  lea     rax, WPP_GLOBAL_Control
0x1800301b6  cmp     rcx, rax
0x1800301b9  jz      loc_1800305E0
0x1800301bf  test    [rcx+1Ch], r13b
0x1800301c3  jz      loc_1800305E0
0x1800301c9  cmp     byte ptr [rcx+19h], 2
0x1800301cd  jb      loc_1800305E0
0x1800301d3  mov     edx, 27h ; '''
0x1800301d8  jmp     loc_180030015
0x1800301dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800301e4  lea     rbx, WPP_GLOBAL_Control
0x1800301eb  cmp     r10, rbx
0x1800301ee  jz      short loc_180030228
0x1800301f0  test    [r10+1Ch], r13b
0x1800301f4  jz      short loc_180030228
0x1800301f6  cmp     byte ptr [r10+19h], 4
0x1800301fb  jb      short loc_180030228
0x1800301fd  mov     rax, qword ptr [rbp+var_38+8]
0x180030201  mov     edx, 28h ; '('
0x180030206  mov     r9, qword ptr [rbp+var_38]
0x18003020a  mov     rcx, [r10+10h]
0x18003020e  mov     [rsp+80h+var_58], rax
0x180030213  lea     r8, [r9+rax]
0x180030217  mov     qword ptr [rsp+80h+grbit], r8
0x18003021c  call    WPP_SF_iii
0x180030221  mov     r10, cs:WPP_GLOBAL_Control
  ... truncated ...
```
