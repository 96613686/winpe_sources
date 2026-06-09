# CFveApiBase::AddValidationInfoForBootApp(_GUID const *,int,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)

- ea: `0x180099a58`
- end: `0x18009a2d8`
- name: `?AddValidationInfoForBootApp@CFveApiBase@@QEAAJPEBU_GUID@@HGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z`
- size: `2176`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const struct _GUID *, int, unsigned __int16, struct _FVE_DATUM_VALIDATION_ENTRY *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18005019c`
- `0x18009d858`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x1800476f0`
- `0x180071210`
- `0x180099a58`
- `0x18009e740`
- `0x18009f384`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18009a250`
- `bcd!BcdCloseObject` at `0x18012468c`
- `bcd!BcdCloseObject` at `0x18009a250`
- `bcd!BcdCloseObject` at `0x18012468c`
- `bcd!BcdGetElementData` at `0x180099f86`
- `bcd!BcdGetElementData` at `0x180099f86`
- `bcd!BcdOpenObject` at `0x180099e59`
- `bcd!BcdOpenObject` at `0x180099e59`
- `bcd!BcdCloseStore` at `0x18009a267`
- `bcd!BcdCloseStore` at `0x18012469f`
- `bcd!BcdCloseStore` at `0x18009a267`
- `bcd!BcdCloseStore` at `0x18012469f`
- `bcd!BcdOpenSystemStore` at `0x180099cb7`
- `bcd!BcdOpenSystemStore` at `0x180099cb7`

## pseudocode

```c
__int64 __fastcall CFveApiBase::AddValidationInfoForBootApp(
        CFveApiBase *this,
        const struct _GUID *a2,
        int a3,
        unsigned __int16 a4,
        struct _FVE_DATUM_VALIDATION_ENTRY *a5,
        unsigned __int16 *a6)
{
  int v6; // r15d
  CFveApiBase *v7; // r10
  int First; // eax
  unsigned __int128 v9; // rax
  int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int DataSegment; // eax
  __int64 v15; // r13
  unsigned __int16 v16; // si
  int v17; // eax
  unsigned __int16 v18; // ax
  unsigned __int16 v19; // r13
  struct _FVE_DATUM_VALIDATION_ENTRY *v20; // rdx
  __int64 v21; // rcx
  const struct _GUID *v22; // rsi
  int v23; // eax
  int v24; // esi
  int ElementData; // eax
  int v26; // esi
  int v27; // esi
  __int64 v28; // rdx
  int v30; // [rsp+20h] [rbp-D8h]
  int v31; // [rsp+20h] [rbp-D8h]
  int v32; // [rsp+38h] [rbp-C0h]
  int v33; // [rsp+38h] [rbp-C0h]
  int v34; // [rsp+40h] [rbp-B8h]
  int v35; // [rsp+40h] [rbp-B8h]
  unsigned __int16 v36; // [rsp+54h] [rbp-A4h] BYREF
  unsigned __int16 v37; // [rsp+58h] [rbp-A0h]
  struct _FVE_DATUM_VALIDATION_ENTRY *v38; // [rsp+60h] [rbp-98h]
  CFveApiBase *v39; // [rsp+68h] [rbp-90h]
  __int64 v40; // [rsp+70h] [rbp-88h] BYREF
  int v41; // [rsp+78h] [rbp-80h]
  __int64 v42; // [rsp+80h] [rbp-78h] BYREF
  const struct _GUID *v43; // [rsp+88h] [rbp-70h]
  __int64 v44; // [rsp+90h] [rbp-68h] BYREF
  __int64 v45; // [rsp+98h] [rbp-60h] BYREF
  int v46; // [rsp+A0h] [rbp-58h] BYREF
  __int128 v47; // [rsp+A8h] [rbp-50h] BYREF

  v6 = a4;
  v37 = a4;
  v41 = a3;
  v43 = a2;
  v7 = this;
  v39 = this;
  v38 = a5;
  v42 = 0;
  v47 = 0;
  v46 = 0;
  v40 = 0;
  v36 = 0;
  v44 = 0;
  v45 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    v7 = v39;
  }
  First = FveDatasetGetFirst(*((_QWORD *)v7 + 146), 4, 7, &v40);
  LODWORD(v9) = FromNtStatus(First);
  v10 = v9;
  if ( (v9 & 0x80000000) != 0LL )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 98;
LABEL_8:
      v13 = (unsigned int)v9;
LABEL_9:
      WPP_SF_d(v11[2], v12, &WPP_1559182127783aab3882fe828952d989_Traceguids, v13);
LABEL_10:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_91;
    }
    goto LABEL_91;
  }
  DataSegment = FveDatumGetDataSegment(v40, &v42, &v36);
  LODWORD(v9) = FromNtStatus(DataSegment);
  v10 = v9;
  if ( (v9 & 0x80000000) == 0LL )
  {
    v15 = v42;
    if ( !v42 )
    {
      v10 = -2147024883;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = (unsigned int)(v42 + 100);
        v13 = 2147942413LL;
        goto LABEL_9;
      }
      goto LABEL_91;
    }
    v9 = v36 * (unsigned __int128)0xCCCCCCCCCCCCCCCDuLL;
    v16 = v36 / 0x28u;
    v36 = v16;
    if ( v16 > (unsigned __int16)v6 )
    {
      v10 = -2147024883;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_91;
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        &WPP_1559182127783aab3882fe828952d989_Traceguids,
        v16,
        v6,
        -2147024883);
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_1559182127783aab3882fe828952d989_Traceguids, v16);
    v17 = BcdOpenSystemStore(&v44, *((_QWORD *)&v9 + 1));
    LODWORD(v9) = FromNtStatus(v17);
    v10 = v9;
    if ( (v9 & 0x80000000) != 0LL )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 103;
        goto LABEL_8;
      }
      goto LABEL_91;
    }
    v18 = *a6;
    if ( !*a6 )
    {
      if ( !v16 )
      {
        v19 = v37;
        LODWORD(v9) = CFveApiBase::StoreValidationDataForAppEx(v39, v44, 0, 0, v37, v38, a6, 1, 0);
        v10 = v9;
        if ( (v9 & 0x80000000) != 0LL )
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 104;
            goto LABEL_8;
          }
          goto LABEL_91;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_1559182127783aab3882fe828952d989_Traceguids, *a6);
LABEL_44:
        v22 = v43;
        v23 = BcdOpenObject(v44, v43, &v45);
        v10 = FromNtStatus(v23);
        if ( v10 < 0 )
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_91;
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            &WPP_1559182127783aab3882fe828952d989_Traceguids,
            v22,
            v10);
          goto LABEL_23;
        }
        v24 = *a6;
        LOBYTE(v34) = 1;
        LOBYTE(v32) = 1;
        LOWORD(v30) = v19;
        LODWORD(v9) = CFveApiBase::StoreValidationDataForAppEx(v39, v44, v43, 1, v30, v38, a6, v32, v34);
        v10 = v9;
        if ( (v9 & 0x80000000) != 0LL )
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 107;
            goto LABEL_8;
          }
          goto LABEL_91;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            108,
            &WPP_1559182127783aab3882fe828952d989_Traceguids,
            (unsigned int)*a6 - v24 - 2);
        v46 = 16;
        ElementData = BcdGetElementData(v45, 587202563, &v47, &v46);
        LODWORD(v9) = FromNtStatus(ElementData);
        v10 = v9;
        if ( (_DWORD)v9 == -2147023728 )
        {
          v10 = 0;
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_70;
          v28 = 113;
        }
        else
        {
          if ( (v9 & 0x80000000) != 0LL )
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 109;
              goto LABEL_8;
            }
            goto LABEL_91;
          }
          v26 = *a6;
          LOBYTE(v35) = 1;
          LOBYTE(v33) = 1;
          LOWORD(v31) = v19;
          LODWORD(v9) = CFveApiBase::StoreValidationDataForAppEx(v39, v44, &v47, 2, v31, v38, a6, v33, v35);
          v10 = v9;
          if ( (v9 & 0x80000000) == 0LL )
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                111,
                &WPP_1559182127783aab3882fe828952d989_Traceguids,
                (unsigned int)*a6 - v26 - 2);
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            goto LABEL_70;
          }
          if ( (_DWORD)v9 != -2147023728 && (_DWORD)v9 != -2147024894 )
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 110;
              goto LABEL_8;
            }
            goto LABEL_91;
          }
          v10 = 0;
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_70;
          v28 = 112;
        }
        WPP_SF_(v11[2], v28, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_70:
        if ( !v41 )
          goto LABEL_91;
        v27 = *a6;
        LOBYTE(v35) = 0;
        LOBYTE(v33) = 1;
        LOWORD(v31) = v19;
        LODWORD(v9) = CFveApiBase::StoreValidationDataForAppEx(
                        v39,
                        v44,
                        &GUID_WINDOWS_MEMORY_TESTER,
                        3,
                        v31,
                        v38,
                        a6,
                        v33,
                        v35);
        v10 = v9;
        if ( (v9 & 0x80000000) != 0LL )
        {
          if ( (_DWORD)v9 == -2147023728 || (_DWORD)v9 == -2147024894 )
          {
            v10 = 0;
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_1559182127783aab3882fe828952d989_Traceguids);
              goto LABEL_10;
            }
          }
          else
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 114;
              goto LABEL_8;
            }
          }
          goto LABEL_91;
        }
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_91;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          115,
          &WPP_1559182127783aab3882fe828952d989_Traceguids,
          (unsigned int)*a6 - v27 - 2);
LABEL_23:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_91;
      }
      v20 = v38;
      while ( v18 < v16 )
      {
        *((_WORD *)v20 + 20 * v18) = *(_WORD *)(v15 + 40LL * v18);
        *((_WORD *)v20 + 20 * *a6 + 1) = *(_WORD *)(v15 + 40LL * *a6 + 2);
        *((_DWORD *)v20 + 10 * *a6 + 1) = *(_DWORD *)(v15 + 40LL * *a6 + 4);
        v21 = 5LL * *a6;
        *(_OWORD *)((char *)v20 + 8 * v21 + 8) = *(_OWORD *)(v15 + 40LL * *a6 + 8);
        *(_OWORD *)((char *)v20 + 8 * v21 + 24) = *(_OWORD *)(v15 + 8 * v21 + 24);
        v18 = ++*a6;
      }
    }
    v19 = v37;
    goto LABEL_44;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 99;
    goto LABEL_8;
  }
LABEL_91:
  *(_QWORD *)&v9 = v44;
  if ( v44 )
  {
    if ( v45 )
    {
      BcdCloseObject();
      *(_QWORD *)&v9 = v44;
    }
    BcdCloseStore(v9, *((_QWORD *)&v9 + 1));
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 )
  {
    FveDatumFree(v40);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 )
    WPP_SF_d(v11[2], 117, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180099a58  mov     r11, rsp
0x180099a5b  push    rbx
0x180099a5c  push    rsi
0x180099a5d  push    rdi
0x180099a5e  push    r12
0x180099a60  push    r13
0x180099a62  push    r14
0x180099a64  push    r15
0x180099a66  sub     rsp, 0C0h
0x180099a6d  mov     rax, cs:__security_cookie
0x180099a74  xor     rax, rsp
0x180099a77  mov     [rsp+0F8h+var_40], rax
0x180099a7f  movzx   r15d, r9w
0x180099a83  mov     [rsp+0F8h+var_A0], r15w
0x180099a89  mov     [rsp+0F8h+var_80], r8d
0x180099a8e  mov     [rsp+0F8h+var_70], rdx
0x180099a96  mov     r10, rcx
0x180099a99  mov     [rsp+0F8h+var_90], rcx
0x180099a9e  mov     rax, [rsp+0F8h+arg_20]
0x180099aa6  mov     [rsp+0F8h+var_98], rax
0x180099aab  mov     r14, [rsp+0F8h+arg_28]
0x180099ab3  xor     r12d, r12d
0x180099ab6  mov     [r11-78h], r12
0x180099aba  xorps   xmm0, xmm0
0x180099abd  movups  xmmword ptr [r11-50h], xmm0
0x180099ac2  mov     [r11-58h], r12d
0x180099ac6  mov     [rsp+0F8h+var_88], r12
0x180099acb  mov     eax, r12d
0x180099ace  mov     [rsp+0F8h+var_A4], ax
0x180099ad3  mov     [r11-68h], r12
0x180099ad7  mov     [r11-60h], r12
0x180099adb  lea     rsi, WPP_GLOBAL_Control
0x180099ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x180099ae9  lea     rdi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x180099af0  cmp     rcx, rsi
0x180099af3  jz      short loc_180099B11
0x180099af5  test    byte ptr [rcx+1Ch], 20h
0x180099af9  jz      short loc_180099B11
0x180099afb  lea     edx, [r12+61h]
0x180099b00  mov     r8, rdi
0x180099b03  mov     rcx, [rcx+10h]
0x180099b07  call    WPP_SF_
0x180099b0c  mov     r10, [rsp+0F8h+var_90]
0x180099b11  mov     edx, 4
0x180099b16  lea     r8d, [rdx+3]
0x180099b1a  lea     r9, [rsp+0F8h+var_88]
0x180099b1f  mov     rcx, [r10+490h]
0x180099b26  call    FveDatasetGetFirst
0x180099b2b  mov     ecx, eax; int
0x180099b2d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099b32  mov     ebx, eax
0x180099b34  mov     [rsp+0F8h+var_A8], eax
0x180099b38  test    eax, eax
0x180099b3a  jns     short loc_180099B76
0x180099b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180099b43  cmp     rcx, rsi
0x180099b46  jz      loc_18009A236
0x180099b4c  test    byte ptr [rcx+1Ch], 2
0x180099b50  jz      loc_18009A236
0x180099b56  mov     edx, 62h ; 'b'
0x180099b5b  mov     r9d, eax
0x180099b5e  mov     r8, rdi
0x180099b61  mov     rcx, [rcx+10h]
0x180099b65  call    WPP_SF_d
0x180099b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180099b71  jmp     loc_18009A236
0x180099b76  lea     r8, [rsp+0F8h+var_A4]
0x180099b7b  lea     rdx, [rsp+0F8h+var_78]
0x180099b83  mov     rcx, [rsp+0F8h+var_88]
0x180099b88  call    FveDatumGetDataSegment
0x180099b8d  mov     ecx, eax; int
0x180099b8f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099b94  mov     ebx, eax
0x180099b96  mov     [rsp+0F8h+var_A8], eax
0x180099b9a  test    eax, eax
0x180099b9c  jns     short loc_180099BBF
0x180099b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099ba5  cmp     rcx, rsi
0x180099ba8  jz      loc_18009A236
0x180099bae  test    byte ptr [rcx+1Ch], 2
0x180099bb2  jz      loc_18009A236
0x180099bb8  mov     edx, 63h ; 'c'
0x180099bbd  jmp     short loc_180099B5B
0x180099bbf  mov     r13, [rsp+0F8h+var_78]
0x180099bc7  test    r13, r13
0x180099bca  jnz     short loc_180099BFF
0x180099bcc  mov     r8d, 8007000Dh
0x180099bd2  mov     ebx, r8d
0x180099bd5  mov     [rsp+0F8h+var_A8], ebx
0x180099bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180099be0  cmp     rcx, rsi
0x180099be3  jz      loc_18009A236
0x180099be9  test    byte ptr [rcx+1Ch], 2
0x180099bed  jz      loc_18009A236
0x180099bf3  lea     edx, [r13+64h]
0x180099bf7  mov     r9d, r8d
0x180099bfa  jmp     loc_180099B5E
0x180099bff  movzx   ecx, [rsp+0F8h+var_A4]
0x180099c04  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180099c0e  mul     rcx
0x180099c11  mov     rsi, rdx
0x180099c14  shr     rsi, 5
0x180099c18  mov     [rsp+0F8h+var_A4], si
0x180099c1d  cmp     si, r15w
0x180099c21  jbe     short loc_180099C7E
0x180099c23  mov     r8d, 8007000Dh
0x180099c29  mov     ebx, r8d
0x180099c2c  mov     [rsp+0F8h+var_A8], ebx
0x180099c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c37  lea     rax, WPP_GLOBAL_Control
0x180099c3e  cmp     rcx, rax
0x180099c41  jz      loc_18009A22F
0x180099c47  test    byte ptr [rcx+1Ch], 2
0x180099c4b  jz      loc_18009A22F
0x180099c51  mov     eax, r15d
0x180099c54  movzx   r9d, si
0x180099c58  mov     edx, 65h ; 'e'
0x180099c5d  mov     dword ptr [rsp+0F8h+var_D0], r8d
0x180099c62  mov     [rsp+0F8h+var_D8], eax
0x180099c66  mov     r8, rdi
0x180099c69  mov     rcx, [rcx+10h]
0x180099c6d  call    WPP_SF_DDD
0x180099c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c79  jmp     loc_18009A22F
0x180099c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c85  lea     rax, WPP_GLOBAL_Control
0x180099c8c  mov     r15b, 8
0x180099c8f  cmp     rcx, rax
0x180099c92  jz      short loc_180099CAF
0x180099c94  test    [rcx+1Ch], r15b
0x180099c98  jz      short loc_180099CAF
0x180099c9a  movzx   r9d, si
0x180099c9e  mov     edx, 66h ; 'f'
0x180099ca3  mov     r8, rdi
0x180099ca6  mov     rcx, [rcx+10h]
0x180099caa  call    WPP_SF_d
0x180099caf  lea     rcx, [rsp+0F8h+var_68]
0x180099cb7  call    cs:__imp_BcdOpenSystemStore
0x180099cbe  nop     dword ptr [rax+rax+00h]
0x180099cc3  mov     ecx, eax; int
0x180099cc5  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099cca  mov     ebx, eax
0x180099ccc  mov     [rsp+0F8h+var_A8], eax
0x180099cd0  test    eax, eax
0x180099cd2  jns     short loc_180099CFF
0x180099cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180099cdb  lea     rsi, WPP_GLOBAL_Control
0x180099ce2  cmp     rcx, rsi
0x180099ce5  jz      loc_18009A236
0x180099ceb  test    byte ptr [rcx+1Ch], 2
0x180099cef  jz      loc_18009A236
0x180099cf5  mov     edx, 67h ; 'g'
0x180099cfa  jmp     loc_180099B5B
0x180099cff  movzx   eax, word ptr [r14]
0x180099d03  test    ax, ax
0x180099d06  jnz     loc_180099E32
0x180099d0c  test    si, si
0x180099d0f  jnz     loc_180099DC5
0x180099d15  mov     byte ptr [rsp+0F8h+var_B8], r12b
0x180099d1a  mov     r12d, 1
0x180099d20  mov     [rsp+0F8h+var_C0], r12b
0x180099d25  mov     [rsp+0F8h+var_C8], r14
0x180099d2a  mov     rax, [rsp+0F8h+var_98]
0x180099d2f  mov     [rsp+0F8h+var_D0], rax
0x180099d34  movzx   r13d, [rsp+0F8h+var_A0]
0x180099d3a  mov     word ptr [rsp+0F8h+var_D8], r13w
0x180099d40  xor     r9d, r9d
0x180099d43  xor     r8d, r8d
0x180099d46  mov     rdx, [rsp+0F8h+var_68]
0x180099d4e  mov     rcx, [rsp+0F8h+var_90]
0x180099d53  call    ?StoreValidationDataForAppEx@CFveApiBase@@QEAAJPEAXPEBU_GUID@@W4eFveBootApplicationPolicy@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG_N5@Z; CFveApiBase::StoreValidationDataForAppEx(void *,_GUID const *,eFveBootApplicationPolicy,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *,bool,bool)
0x180099d58  mov     ebx, eax
0x180099d5a  mov     [rsp+0F8h+var_A8], eax
0x180099d5e  test    eax, eax
0x180099d60  jns     short loc_180099D8D
0x180099d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d69  lea     rsi, WPP_GLOBAL_Control
0x180099d70  cmp     rcx, rsi
0x180099d73  jz      loc_18009A236
0x180099d79  test    byte ptr [rcx+1Ch], 2
0x180099d7d  jz      loc_18009A236
0x180099d83  lea     edx, [r12+67h]
0x180099d88  jmp     loc_180099B5B
0x180099d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d94  lea     rax, WPP_GLOBAL_Control
0x180099d9b  cmp     rcx, rax
0x180099d9e  jz      loc_180099E3E
0x180099da4  test    [rcx+1Ch], r15b
0x180099da8  jz      loc_180099E3E
0x180099dae  movzx   r9d, word ptr [r14]
0x180099db2  mov     edx, 69h ; 'i'
0x180099db7  mov     r8, rdi
0x180099dba  mov     rcx, [rcx+10h]
0x180099dbe  call    WPP_SF_d
0x180099dc3  jmp     short loc_180099E3E
0x180099dc5  mov     r12d, 1
0x180099dcb  mov     rdx, [rsp+0F8h+var_98]
0x180099dd0  cmp     ax, si
0x180099dd3  jnb     short loc_180099E38
0x180099dd5  movzx   eax, ax
0x180099dd8  lea     rcx, [rax+rax*4]
0x180099ddc  movzx   eax, word ptr [r13+rcx*8+0]
0x180099de2  mov     [rdx+rcx*8], ax
0x180099de6  movzx   eax, word ptr [r14]
0x180099dea  lea     rcx, [rax+rax*4]
0x180099dee  movzx   eax, word ptr [r13+rcx*8+2]
0x180099df4  mov     [rdx+rcx*8+2], ax
0x180099df9  movzx   eax, word ptr [r14]
0x180099dfd  lea     rcx, [rax+rax*4]
0x180099e01  mov     eax, [r13+rcx*8+4]
0x180099e06  mov     [rdx+rcx*8+4], eax
0x180099e0a  movzx   eax, word ptr [r14]
0x180099e0e  lea     rcx, [rax+rax*4]
0x180099e12  movups  xmm0, xmmword ptr [r13+rcx*8+8]
0x180099e18  movups  xmmword ptr [rdx+rcx*8+8], xmm0
0x180099e1d  movups  xmm1, xmmword ptr [r13+rcx*8+18h]
0x180099e23  movups  xmmword ptr [rdx+rcx*8+18h], xmm1
0x180099e28  add     [r14], r12w
0x180099e2c  movzx   eax, word ptr [r14]
0x180099e30  jmp     short loc_180099DD0
0x180099e32  mov     r12d, 1
0x180099e38  movzx   r13d, [rsp+0F8h+var_A0]
0x180099e3e  lea     r8, [rsp+0F8h+var_60]
0x180099e46  mov     rsi, [rsp+0F8h+var_70]
0x180099e4e  mov     rdx, rsi
0x180099e51  mov     rcx, [rsp+0F8h+var_68]
0x180099e59  call    cs:__imp_BcdOpenObject
0x180099e60  nop     dword ptr [rax+rax+00h]
0x180099e65  mov     ecx, eax; int
0x180099e67  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099e6c  mov     ebx, eax
0x180099e6e  mov     [rsp+0F8h+var_A8], eax
0x180099e72  test    eax, eax
0x180099e74  jns     short loc_180099EB4
0x180099e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180099e7d  lea     rax, WPP_GLOBAL_Control
0x180099e84  cmp     rcx, rax
0x180099e87  jz      loc_18009A22F
0x180099e8d  test    byte ptr [rcx+1Ch], 2
0x180099e91  jz      loc_18009A22F
0x180099e97  mov     edx, 6Ah ; 'j'
0x180099e9c  mov     [rsp+0F8h+var_D8], ebx
0x180099ea0  mov     r9, rsi
0x180099ea3  mov     r8, rdi
0x180099ea6  mov     rcx, [rcx+10h]
0x180099eaa  call    WPP_SF__guid_D
0x180099eaf  jmp     loc_180099C72
0x180099eb4  movzx   esi, word ptr [r14]
0x180099eb8  mov     byte ptr [rsp+0F8h+var_B8], r12b
0x180099ebd  mov     [rsp+0F8h+var_C0], r12b
0x180099ec2  mov     [rsp+0F8h+var_C8], r14
0x180099ec7  mov     rax, [rsp+0F8h+var_98]
0x180099ecc  mov     [rsp+0F8h+var_D0], rax
0x180099ed1  mov     word ptr [rsp+0F8h+var_D8], r13w
0x180099ed7  mov     r9d, r12d
0x180099eda  mov     r8, [rsp+0F8h+var_70]
0x180099ee2  mov     rdx, [rsp+0F8h+var_68]
0x180099eea  mov     rcx, [rsp+0F8h+var_90]
0x180099eef  call    ?StoreValidationDataForAppEx@CFveApiBase@@QEAAJPEAXPEBU_GUID@@W4eFveBootApplicationPolicy@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG_N5@Z; CFveApiBase::StoreValidationDataForAppEx(void *,_GUID const *,eFveBootApplicationPolicy,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *,bool,bool)
0x180099ef4  mov     ebx, eax
0x180099ef6  mov     [rsp+0F8h+var_A8], eax
0x180099efa  test    eax, eax
0x180099efc  jns     short loc_180099F29
0x180099efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f05  lea     rsi, WPP_GLOBAL_Control
0x180099f0c  cmp     rcx, rsi
0x180099f0f  jz      loc_18009A236
0x180099f15  test    byte ptr [rcx+1Ch], 2
0x180099f19  jz      loc_18009A236
0x180099f1f  mov     edx, 6Bh ; 'k'
0x180099f24  jmp     loc_180099B5B
0x180099f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f30  lea     rax, WPP_GLOBAL_Control
0x180099f37  cmp     rcx, rax
0x180099f3a  jz      short loc_180099F5E
0x180099f3c  test    [rcx+1Ch], r15b
0x180099f40  jz      short loc_180099F5E
0x180099f42  movzx   r9d, word ptr [r14]
0x180099f46  sub     r9d, esi
0x180099f49  sub     r9d, 2
0x180099f4d  mov     edx, 6Ch ; 'l'
0x180099f52  mov     r8, rdi
0x180099f55  mov     rcx, [rcx+10h]
0x180099f59  call    WPP_SF_d
0x180099f5e  mov     [rsp+0F8h+var_58], 10h
0x180099f69  lea     r9, [rsp+0F8h+var_58]
0x180099f71  lea     r8, [rsp+0F8h+var_50]
0x180099f79  mov     edx, 23000003h
0x180099f7e  mov     rcx, [rsp+0F8h+var_60]
0x180099f86  call    cs:__imp_BcdGetElementData
0x180099f8d  nop     dword ptr [rax+rax+00h]
0x180099f92  mov     ecx, eax; int
0x180099f94  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180099f99  mov     ebx, eax
0x180099f9b  mov     [rsp+0F8h+var_A8], eax
0x180099f9f  cmp     eax, 80070490h
0x180099fa4  jz      loc_18009A18D
0x180099faa  test    eax, eax
0x180099fac  jns     short loc_180099FD9
0x180099fae  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
