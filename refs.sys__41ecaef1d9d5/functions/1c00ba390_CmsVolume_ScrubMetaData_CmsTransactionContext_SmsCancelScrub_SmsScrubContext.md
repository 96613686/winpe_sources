# CmsVolume::ScrubMetaData(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)

- ea: `0x1c00ba390`
- end: `0x1c00badb2`
- name: `?ScrubMetaData@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z`
- size: `2594`
- prototype: `__int64 __fastcall(CmsVolume *__hidden this, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1c00b32c0`

## callees

- `0x1c006ac80`
- `0x1c00b3140`
- `0x1c00ba390`
- `0x1c00badb8`
- `0x1c00bae78`
- `0x1c00baf18`
- `0x1c00cf378`
- `0x1c00dc5cc`
- `0x1c00e64f0`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba488`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba533`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba5f3`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba6bc`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba785`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba84e`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba917`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba9c2`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00baa8f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00bab3f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00babef`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00bacc9`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba488`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba533`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba5f3`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba6bc`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba785`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba84e`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba917`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00ba9c2`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00baa8f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00bab3f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00babef`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c00bacc9`

## pseudocode

```c
__int64 __fastcall CmsVolume::ScrubMetaData(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        struct _SmsCancelScrub *a3,
        struct _SmsScrubContext *a4)
{
  unsigned __int8 v4; // al
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  CmsObjectTable *v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  CmsVolumeContainer *v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // eax

  v4 = *((_BYTE *)a4 + 4);
  v9 = 0;
  if ( v4 <= 9u )
  {
    if ( v4 == 9 )
    {
LABEL_71:
      if ( *((_QWORD *)this + 384) )
      {
        *((_BYTE *)a4 + 689) = 9;
        v9 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(**(_QWORD **)(*((_QWORD *)this + 384) + 8LL) + 72LL))(
               *(_QWORD *)(*((_QWORD *)this + 384) + 8LL),
               a2,
               a3,
               a4);
        *((_BYTE *)a4 + 689) = 0;
      }
      if ( v9 < 0 )
        return (unsigned int)v9;
      if ( *((int *)a4 + 2) <= 0
        || **(_BYTE **)a3
        || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(a4)
        || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
      {
        return (unsigned int)-2147483643;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 10;
      *((_OWORD *)a4 + 6) = 0;
      v18 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 152) = v18;
      *((_DWORD *)a4 + 156) = v18;
      goto LABEL_81;
    }
    if ( !v4 || v4 == 2 )
    {
      if ( (*((_DWORD *)a4 + 160) & 1) == 0 )
      {
        *((_BYTE *)a4 + 689) = 2;
        v9 = CmsVolume::ScrubSuperblock(this, a2, a3, a4);
        *((_BYTE *)a4 + 689) = 0;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 3;
      *((_OWORD *)a4 + 6) = 0;
      v10 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 152) = v10;
      *((_DWORD *)a4 + 156) = v10;
      if ( v9 < 0 )
        return (unsigned int)v9;
      if ( *((int *)a4 + 2) <= 0
        || **(_BYTE **)a3
        || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(a4)
        || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
      {
        return (unsigned int)-2147483643;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 3;
      *((_OWORD *)a4 + 6) = 0;
      v11 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 152) = v11;
      *((_DWORD *)a4 + 156) = v11;
    }
    else
    {
      if ( v4 <= 2u )
        return (unsigned int)v9;
      if ( v4 > 4u )
      {
        if ( v4 != 5 )
        {
          if ( v4 != 6 )
          {
            if ( v4 != 7 )
            {
LABEL_61:
              if ( *((_QWORD *)this + 380) )
              {
                *((_BYTE *)a4 + 689) = 8;
                v9 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(**(_QWORD **)(*((_QWORD *)this + 380) + 16LL) + 72LL))(
                       *(_QWORD *)(*((_QWORD *)this + 380) + 16LL),
                       a2,
                       a3,
                       a4);
                *((_BYTE *)a4 + 689) = 0;
              }
              if ( v9 < 0 )
                return (unsigned int)v9;
              if ( *((int *)a4 + 2) <= 0
                || **(_BYTE **)a3
                || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(a4)
                || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
              {
                return (unsigned int)-2147483643;
              }
              *((_DWORD *)a4 + 3) = 16;
              *((_WORD *)a4 + 2) = 9;
              *((_OWORD *)a4 + 6) = 0;
              v17 = *((_DWORD *)a4 + 3);
              *((_DWORD *)a4 + 152) = v17;
              *((_DWORD *)a4 + 156) = v17;
              goto LABEL_71;
            }
LABEL_51:
            if ( *((_QWORD *)this + 379) )
            {
              *((_BYTE *)a4 + 689) = 7;
              v9 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(**(_QWORD **)(*((_QWORD *)this + 379) + 16LL) + 72LL))(
                     *(_QWORD *)(*((_QWORD *)this + 379) + 16LL),
                     a2,
                     a3,
                     a4);
              *((_BYTE *)a4 + 689) = 0;
            }
            if ( v9 < 0 )
              return (unsigned int)v9;
            if ( *((int *)a4 + 2) <= 0
              || **(_BYTE **)a3
              || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
              || PsIsThreadTerminating(KeGetCurrentThread())
              || (unsigned __int8)MsScrubContextFoundError(a4)
              || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
            {
              return (unsigned int)-2147483643;
            }
            *((_DWORD *)a4 + 3) = 16;
            *((_WORD *)a4 + 2) = 8;
            *((_OWORD *)a4 + 6) = 0;
            v16 = *((_DWORD *)a4 + 3);
            *((_DWORD *)a4 + 152) = v16;
            *((_DWORD *)a4 + 156) = v16;
            goto LABEL_61;
          }
LABEL_41:
          if ( *((_QWORD *)this + 378) )
          {
            *((_BYTE *)a4 + 689) = 6;
            v9 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(**(_QWORD **)(*((_QWORD *)this + 378) + 16LL) + 72LL))(
                   *(_QWORD *)(*((_QWORD *)this + 378) + 16LL),
                   a2,
                   a3,
                   a4);
            *((_BYTE *)a4 + 689) = 0;
          }
          if ( v9 < 0 )
            return (unsigned int)v9;
          if ( *((int *)a4 + 2) <= 0
            || **(_BYTE **)a3
            || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(a4)
            || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
          {
            return (unsigned int)-2147483643;
          }
          *((_DWORD *)a4 + 3) = 16;
          *((_WORD *)a4 + 2) = 7;
          *((_OWORD *)a4 + 6) = 0;
          v15 = *((_DWORD *)a4 + 3);
          *((_DWORD *)a4 + 152) = v15;
          *((_DWORD *)a4 + 156) = v15;
          goto LABEL_51;
        }
LABEL_31:
        if ( *((_QWORD *)this + 388) )
        {
          *((_BYTE *)a4 + 689) = 5;
          v9 = CmsFailoverBPlusTable::ScrubTable(**((CmsFailoverBPlusTable ***)this + 388), a2, a3, a4);
          *((_BYTE *)a4 + 689) = 0;
        }
        if ( v9 < 0 )
          return (unsigned int)v9;
        if ( *((int *)a4 + 2) <= 0
          || **(_BYTE **)a3
          || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
          || PsIsThreadTerminating(KeGetCurrentThread())
          || (unsigned __int8)MsScrubContextFoundError(a4)
          || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
        {
          return (unsigned int)-2147483643;
        }
        *((_DWORD *)a4 + 3) = 16;
        *((_WORD *)a4 + 2) = 6;
        *((_OWORD *)a4 + 6) = 0;
        v14 = *((_DWORD *)a4 + 3);
        *((_DWORD *)a4 + 152) = v14;
        *((_DWORD *)a4 + 156) = v14;
        goto LABEL_41;
      }
    }
    v12 = (CmsObjectTable *)*((_QWORD *)this + 387);
    if ( v12 )
      v9 = CmsObjectTable::Scrub(v12, a2, a3, a4);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 5;
    *((_OWORD *)a4 + 6) = 0;
    v13 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 152) = v13;
    *((_DWORD *)a4 + 156) = v13;
    goto LABEL_31;
  }
  if ( v4 <= 0xBu )
  {
LABEL_81:
    v19 = (CmsVolumeContainer *)*((_QWORD *)this + 381);
    if ( v19 )
      v9 = CmsVolumeContainer::Scrub(v19, a2, a3, a4);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 12;
    *((_OWORD *)a4 + 6) = 0;
    v20 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 152) = v20;
    *((_DWORD *)a4 + 156) = v20;
    goto LABEL_91;
  }
  if ( v4 == 12 )
  {
LABEL_91:
    if ( *((_QWORD *)this + 382) )
    {
      *((_BYTE *)a4 + 689) = 12;
      v21 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 382) + 8LL) + 16LL);
      v9 = (*(__int64 (__fastcall **)(__int64, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(*(_QWORD *)v21 + 72LL))(
             v21,
             a2,
             a3,
             a4);
      *((_BYTE *)a4 + 689) = 0;
    }
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 13;
    *((_OWORD *)a4 + 6) = 0;
    v22 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 152) = v22;
    *((_DWORD *)a4 + 156) = v22;
    goto LABEL_101;
  }
  if ( v4 == 13 )
  {
LABEL_101:
    *((_BYTE *)a4 + 689) = 13;
    v23 = CmsVolume::ScrubVolumeRedoLog(this, a2, a3, a4);
    *((_BYTE *)a4 + 689) = 0;
    v9 = v23;
    if ( v23 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 14;
    *((_OWORD *)a4 + 6) = 0;
    v24 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 152) = v24;
    *((_DWORD *)a4 + 156) = v24;
    goto LABEL_109;
  }
  if ( v4 != 14 )
  {
    if ( v4 != 15 )
    {
      if ( v4 != 16 )
        return (unsigned int)v9;
      goto LABEL_130;
    }
    goto LABEL_117;
  }
LABEL_109:
  *((_BYTE *)a4 + 689) = 14;
  v25 = CmsVolume::ScrubUpcaseTable(this, a2, a3, a4);
  *((_BYTE *)a4 + 689) = 0;
  v9 = v25;
  if ( v25 < 0 )
    return (unsigned int)v9;
  if ( *((int *)a4 + 2) <= 0
    || **(_BYTE **)a3
    || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
    || PsIsThreadTerminating(KeGetCurrentThread())
    || (unsigned __int8)MsScrubContextFoundError(a4)
    || *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
  {
    return (unsigned int)-2147483643;
  }
  *((_DWORD *)a4 + 3) = 16;
  *((_WORD *)a4 + 2) = 15;
  *((_OWORD *)a4 + 6) = 0;
  v26 = *((_DWORD *)a4 + 3);
  *((_DWORD *)a4 + 152) = v26;
  *((_DWORD *)a4 + 156) = v26;
LABEL_117:
  if ( *((_QWORD *)this + 325) )
  {
    *((_BYTE *)a4 + 689) = 15;
    v9 = 0;
    v27 = *((_QWORD *)this + 325);
    v28 = *(_QWORD *)(v27 + 40);
    if ( v28 && *(_BYTE *)(v27 + 437) )
      v9 = (*(__int64 (__fastcall **)(__int64, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(*(_QWORD *)v28 + 72LL))(
             v28,
             a2,
             a3,
             a4);
    *((_BYTE *)a4 + 689) = 0;
  }
  if ( v9 >= 0 )
  {
    if ( *((int *)a4 + 2) > 0
      && !**(_BYTE **)a3
      && (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) == 0
      && !PsIsThreadTerminating(KeGetCurrentThread())
      && !(unsigned __int8)MsScrubContextFoundError(a4)
      && *(_WORD *)(*((_QWORD *)a4 + 88) + 4LL) < *(_WORD *)(*((_QWORD *)a4 + 88) + 6LL) )
    {
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 16;
      *((_OWORD *)a4 + 6) = 0;
      v29 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 152) = v29;
      *((_DWORD *)a4 + 156) = v29;
LABEL_130:
      if ( *((_QWORD *)this + 392) )
      {
        *((_BYTE *)a4 + 689) = 16;
        v9 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *))(***((_QWORD ***)this + 392) + 72LL))(
               **((_QWORD **)this + 392),
               a2,
               a3,
               a4);
        *((_BYTE *)a4 + 689) = 0;
      }
      return (unsigned int)v9;
    }
    return (unsigned int)-2147483643;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c00ba390  mov     rax, rsp
0x1c00ba393  mov     [rax+8], rbx
0x1c00ba397  mov     [rax+10h], rbp
0x1c00ba39b  mov     [rax+18h], rsi
0x1c00ba39f  mov     [rax+20h], rdi
0x1c00ba3a3  push    r12
0x1c00ba3a5  push    r14
0x1c00ba3a7  push    r15
0x1c00ba3a9  sub     rsp, 30h
0x1c00ba3ad  mov     al, [r9+4]
0x1c00ba3b1  xor     r12d, r12d
0x1c00ba3b4  mov     rdi, r9
0x1c00ba3b7  mov     rsi, r8
0x1c00ba3ba  mov     r15, rdx
0x1c00ba3bd  mov     rbp, rcx
0x1c00ba3c0  mov     ebx, r12d
0x1c00ba3c3  lea     r14d, [r12+10h]
0x1c00ba3c8  cmp     al, 9
0x1c00ba3ca  ja      loc_1C00BAD5C
0x1c00ba3d0  jz      loc_1C00BA8A7
0x1c00ba3d6  test    al, al
0x1c00ba3d8  jz      short loc_1C00BA411
0x1c00ba3da  cmp     al, 2
0x1c00ba3dc  jz      short loc_1C00BA411
0x1c00ba3de  jbe     loc_1C00BAD90
0x1c00ba3e4  cmp     al, 4
0x1c00ba3e6  jbe     loc_1C00BA4E1
0x1c00ba3ec  cmp     al, 5
0x1c00ba3ee  jz      loc_1C00BA58C
0x1c00ba3f4  cmp     al, 6
0x1c00ba3f6  jz      loc_1C00BA64C
0x1c00ba3fc  cmp     al, 7
0x1c00ba3fe  jz      loc_1C00BA715
0x1c00ba404  cmp     al, 8
0x1c00ba406  jz      loc_1C00BA7DE
0x1c00ba40c  jmp     loc_1C00BAD90
0x1c00ba411  mov     eax, [r9+280h]
0x1c00ba418  test    al, 1
0x1c00ba41a  jnz     short loc_1C00BA432
0x1c00ba41c  mov     byte ptr [r9+2B1h], 2
0x1c00ba424  call    ?ScrubSuperblock@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsVolume::ScrubSuperblock(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1c00ba429  mov     ebx, eax
0x1c00ba42b  mov     [rdi+2B1h], r12b
0x1c00ba432  mov     [rdi+0Ch], r14d
0x1c00ba436  xorps   xmm0, xmm0
0x1c00ba439  mov     word ptr [rdi+4], 3
0x1c00ba43f  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba443  mov     eax, [rdi+0Ch]
0x1c00ba446  mov     [rdi+260h], eax
0x1c00ba44c  mov     [rdi+270h], eax
0x1c00ba452  test    ebx, ebx
0x1c00ba454  js      loc_1C00BAD90
0x1c00ba45a  cmp     [rdi+8], r12d
0x1c00ba45e  jle     loc_1C00BAD8B
0x1c00ba464  mov     rax, [rsi]
0x1c00ba467  cmp     [rax], r12b
0x1c00ba46a  jnz     loc_1C00BAD8B
0x1c00ba470  mov     rax, [rsi+8]
0x1c00ba474  mov     ecx, [rax]
0x1c00ba476  test    [rsi+10h], ecx
0x1c00ba479  jnz     loc_1C00BAD8B
0x1c00ba47f  mov     rcx, gs:188h; Thread
0x1c00ba488  call    cs:__imp_PsIsThreadTerminating
0x1c00ba48f  nop     dword ptr [rax+rax+00h]
0x1c00ba494  test    al, al
0x1c00ba496  jnz     loc_1C00BAD8B
0x1c00ba49c  mov     rcx, rdi
0x1c00ba49f  call    MsScrubContextFoundError
0x1c00ba4a4  test    al, al
0x1c00ba4a6  jnz     loc_1C00BAD8B
0x1c00ba4ac  mov     rcx, [rdi+2C0h]
0x1c00ba4b3  movzx   eax, word ptr [rcx+6]
0x1c00ba4b7  cmp     [rcx+4], ax
0x1c00ba4bb  jnb     loc_1C00BAD8B
0x1c00ba4c1  mov     [rdi+0Ch], r14d
0x1c00ba4c5  xorps   xmm0, xmm0
0x1c00ba4c8  mov     word ptr [rdi+4], 3
0x1c00ba4ce  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba4d2  mov     eax, [rdi+0Ch]
0x1c00ba4d5  mov     [rdi+260h], eax
0x1c00ba4db  mov     [rdi+270h], eax
0x1c00ba4e1  mov     rcx, [rbp+0C18h]; this
0x1c00ba4e8  test    rcx, rcx
0x1c00ba4eb  jz      short loc_1C00BA4FD
0x1c00ba4ed  mov     r9, rdi; struct _SmsScrubContext *
0x1c00ba4f0  mov     r8, rsi; struct _SmsCancelScrub *
0x1c00ba4f3  mov     rdx, r15; struct CmsTransactionContext *
0x1c00ba4f6  call    ?Scrub@CmsObjectTable@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsObjectTable::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1c00ba4fb  mov     ebx, eax
0x1c00ba4fd  test    ebx, ebx
0x1c00ba4ff  js      loc_1C00BAD90
0x1c00ba505  cmp     [rdi+8], r12d
0x1c00ba509  jle     loc_1C00BAD8B
0x1c00ba50f  mov     rax, [rsi]
0x1c00ba512  cmp     [rax], r12b
0x1c00ba515  jnz     loc_1C00BAD8B
0x1c00ba51b  mov     rax, [rsi+8]
0x1c00ba51f  mov     ecx, [rax]
0x1c00ba521  test    [rsi+10h], ecx
0x1c00ba524  jnz     loc_1C00BAD8B
0x1c00ba52a  mov     rcx, gs:188h; Thread
0x1c00ba533  call    cs:__imp_PsIsThreadTerminating
0x1c00ba53a  nop     dword ptr [rax+rax+00h]
0x1c00ba53f  test    al, al
0x1c00ba541  jnz     loc_1C00BAD8B
0x1c00ba547  mov     rcx, rdi
0x1c00ba54a  call    MsScrubContextFoundError
0x1c00ba54f  test    al, al
0x1c00ba551  jnz     loc_1C00BAD8B
0x1c00ba557  mov     rcx, [rdi+2C0h]
0x1c00ba55e  movzx   eax, word ptr [rcx+6]
0x1c00ba562  cmp     [rcx+4], ax
0x1c00ba566  jnb     loc_1C00BAD8B
0x1c00ba56c  mov     [rdi+0Ch], r14d
0x1c00ba570  xorps   xmm0, xmm0
0x1c00ba573  mov     word ptr [rdi+4], 5
0x1c00ba579  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba57d  mov     eax, [rdi+0Ch]
0x1c00ba580  mov     [rdi+260h], eax
0x1c00ba586  mov     [rdi+270h], eax
0x1c00ba58c  cmp     [rbp+0C20h], r12
0x1c00ba593  jz      short loc_1C00BA5BD
0x1c00ba595  mov     byte ptr [rdi+2B1h], 5
0x1c00ba59c  mov     r9, rdi; struct _SmsScrubContext *
0x1c00ba59f  mov     rax, [rbp+0C20h]
0x1c00ba5a6  mov     r8, rsi; struct _SmsCancelScrub *
0x1c00ba5a9  mov     rdx, r15; struct CmsTransactionContext *
0x1c00ba5ac  mov     rcx, [rax]; this
0x1c00ba5af  call    ?ScrubTable@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsFailoverBPlusTable::ScrubTable(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1c00ba5b4  mov     ebx, eax
0x1c00ba5b6  mov     [rdi+2B1h], r12b
0x1c00ba5bd  test    ebx, ebx
0x1c00ba5bf  js      loc_1C00BAD90
0x1c00ba5c5  cmp     [rdi+8], r12d
0x1c00ba5c9  jle     loc_1C00BAD8B
0x1c00ba5cf  mov     rax, [rsi]
0x1c00ba5d2  cmp     [rax], r12b
0x1c00ba5d5  jnz     loc_1C00BAD8B
0x1c00ba5db  mov     rax, [rsi+8]
0x1c00ba5df  mov     ecx, [rax]
0x1c00ba5e1  test    [rsi+10h], ecx
0x1c00ba5e4  jnz     loc_1C00BAD8B
0x1c00ba5ea  mov     rcx, gs:188h; Thread
0x1c00ba5f3  call    cs:__imp_PsIsThreadTerminating
0x1c00ba5fa  nop     dword ptr [rax+rax+00h]
0x1c00ba5ff  test    al, al
0x1c00ba601  jnz     loc_1C00BAD8B
0x1c00ba607  mov     rcx, rdi
0x1c00ba60a  call    MsScrubContextFoundError
0x1c00ba60f  test    al, al
0x1c00ba611  jnz     loc_1C00BAD8B
0x1c00ba617  mov     rcx, [rdi+2C0h]
0x1c00ba61e  movzx   eax, word ptr [rcx+6]
0x1c00ba622  cmp     [rcx+4], ax
0x1c00ba626  jnb     loc_1C00BAD8B
0x1c00ba62c  mov     [rdi+0Ch], r14d
0x1c00ba630  xorps   xmm0, xmm0
0x1c00ba633  mov     word ptr [rdi+4], 6
0x1c00ba639  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba63d  mov     eax, [rdi+0Ch]
0x1c00ba640  mov     [rdi+260h], eax
0x1c00ba646  mov     [rdi+270h], eax
0x1c00ba64c  cmp     [rbp+0BD0h], r12
0x1c00ba653  jz      short loc_1C00BA686
0x1c00ba655  mov     byte ptr [rdi+2B1h], 6
0x1c00ba65c  mov     r9, rdi
0x1c00ba65f  mov     rax, [rbp+0BD0h]
0x1c00ba666  mov     r8, rsi
0x1c00ba669  mov     rdx, r15
0x1c00ba66c  mov     rcx, [rax+10h]
0x1c00ba670  mov     rax, [rcx]
0x1c00ba673  mov     rax, [rax+48h]
0x1c00ba677  call    cs:__guard_dispatch_icall_fptr
0x1c00ba67d  mov     ebx, eax
0x1c00ba67f  mov     [rdi+2B1h], r12b
0x1c00ba686  test    ebx, ebx
0x1c00ba688  js      loc_1C00BAD90
0x1c00ba68e  cmp     [rdi+8], r12d
0x1c00ba692  jle     loc_1C00BAD8B
0x1c00ba698  mov     rax, [rsi]
0x1c00ba69b  cmp     [rax], r12b
0x1c00ba69e  jnz     loc_1C00BAD8B
0x1c00ba6a4  mov     rax, [rsi+8]
0x1c00ba6a8  mov     ecx, [rax]
0x1c00ba6aa  test    [rsi+10h], ecx
0x1c00ba6ad  jnz     loc_1C00BAD8B
0x1c00ba6b3  mov     rcx, gs:188h; Thread
0x1c00ba6bc  call    cs:__imp_PsIsThreadTerminating
0x1c00ba6c3  nop     dword ptr [rax+rax+00h]
0x1c00ba6c8  test    al, al
0x1c00ba6ca  jnz     loc_1C00BAD8B
0x1c00ba6d0  mov     rcx, rdi
0x1c00ba6d3  call    MsScrubContextFoundError
0x1c00ba6d8  test    al, al
0x1c00ba6da  jnz     loc_1C00BAD8B
0x1c00ba6e0  mov     rcx, [rdi+2C0h]
0x1c00ba6e7  movzx   eax, word ptr [rcx+6]
0x1c00ba6eb  cmp     [rcx+4], ax
0x1c00ba6ef  jnb     loc_1C00BAD8B
0x1c00ba6f5  mov     [rdi+0Ch], r14d
0x1c00ba6f9  xorps   xmm0, xmm0
0x1c00ba6fc  mov     word ptr [rdi+4], 7
0x1c00ba702  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba706  mov     eax, [rdi+0Ch]
0x1c00ba709  mov     [rdi+260h], eax
0x1c00ba70f  mov     [rdi+270h], eax
0x1c00ba715  cmp     [rbp+0BD8h], r12
0x1c00ba71c  jz      short loc_1C00BA74F
0x1c00ba71e  mov     byte ptr [rdi+2B1h], 7
0x1c00ba725  mov     r9, rdi
0x1c00ba728  mov     rax, [rbp+0BD8h]
0x1c00ba72f  mov     r8, rsi
0x1c00ba732  mov     rdx, r15
0x1c00ba735  mov     rcx, [rax+10h]
0x1c00ba739  mov     rax, [rcx]
0x1c00ba73c  mov     rax, [rax+48h]
0x1c00ba740  call    cs:__guard_dispatch_icall_fptr
0x1c00ba746  mov     ebx, eax
0x1c00ba748  mov     [rdi+2B1h], r12b
0x1c00ba74f  test    ebx, ebx
0x1c00ba751  js      loc_1C00BAD90
0x1c00ba757  cmp     [rdi+8], r12d
0x1c00ba75b  jle     loc_1C00BAD8B
0x1c00ba761  mov     rax, [rsi]
0x1c00ba764  cmp     [rax], r12b
0x1c00ba767  jnz     loc_1C00BAD8B
0x1c00ba76d  mov     rax, [rsi+8]
0x1c00ba771  mov     ecx, [rax]
0x1c00ba773  test    [rsi+10h], ecx
0x1c00ba776  jnz     loc_1C00BAD8B
0x1c00ba77c  mov     rcx, gs:188h; Thread
0x1c00ba785  call    cs:__imp_PsIsThreadTerminating
0x1c00ba78c  nop     dword ptr [rax+rax+00h]
0x1c00ba791  test    al, al
0x1c00ba793  jnz     loc_1C00BAD8B
0x1c00ba799  mov     rcx, rdi
0x1c00ba79c  call    MsScrubContextFoundError
0x1c00ba7a1  test    al, al
0x1c00ba7a3  jnz     loc_1C00BAD8B
0x1c00ba7a9  mov     rcx, [rdi+2C0h]
0x1c00ba7b0  movzx   eax, word ptr [rcx+6]
0x1c00ba7b4  cmp     [rcx+4], ax
0x1c00ba7b8  jnb     loc_1C00BAD8B
0x1c00ba7be  mov     [rdi+0Ch], r14d
0x1c00ba7c2  xorps   xmm0, xmm0
0x1c00ba7c5  mov     word ptr [rdi+4], 8
0x1c00ba7cb  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba7cf  mov     eax, [rdi+0Ch]
0x1c00ba7d2  mov     [rdi+260h], eax
0x1c00ba7d8  mov     [rdi+270h], eax
0x1c00ba7de  cmp     [rbp+0BE0h], r12
0x1c00ba7e5  jz      short loc_1C00BA818
0x1c00ba7e7  mov     byte ptr [rdi+2B1h], 8
0x1c00ba7ee  mov     r9, rdi
0x1c00ba7f1  mov     rax, [rbp+0BE0h]
0x1c00ba7f8  mov     r8, rsi
0x1c00ba7fb  mov     rdx, r15
0x1c00ba7fe  mov     rcx, [rax+10h]
0x1c00ba802  mov     rax, [rcx]
0x1c00ba805  mov     rax, [rax+48h]
0x1c00ba809  call    cs:__guard_dispatch_icall_fptr
0x1c00ba80f  mov     ebx, eax
0x1c00ba811  mov     [rdi+2B1h], r12b
0x1c00ba818  test    ebx, ebx
0x1c00ba81a  js      loc_1C00BAD90
0x1c00ba820  cmp     [rdi+8], r12d
0x1c00ba824  jle     loc_1C00BAD8B
0x1c00ba82a  mov     rax, [rsi]
0x1c00ba82d  cmp     [rax], r12b
0x1c00ba830  jnz     loc_1C00BAD8B
0x1c00ba836  mov     rax, [rsi+8]
0x1c00ba83a  mov     ecx, [rax]
0x1c00ba83c  test    [rsi+10h], ecx
0x1c00ba83f  jnz     loc_1C00BAD8B
0x1c00ba845  mov     rcx, gs:188h; Thread
0x1c00ba84e  call    cs:__imp_PsIsThreadTerminating
0x1c00ba855  nop     dword ptr [rax+rax+00h]
0x1c00ba85a  test    al, al
0x1c00ba85c  jnz     loc_1C00BAD8B
0x1c00ba862  mov     rcx, rdi
0x1c00ba865  call    MsScrubContextFoundError
0x1c00ba86a  test    al, al
0x1c00ba86c  jnz     loc_1C00BAD8B
0x1c00ba872  mov     rcx, [rdi+2C0h]
0x1c00ba879  movzx   eax, word ptr [rcx+6]
0x1c00ba87d  cmp     [rcx+4], ax
0x1c00ba881  jnb     loc_1C00BAD8B
0x1c00ba887  mov     [rdi+0Ch], r14d
0x1c00ba88b  xorps   xmm0, xmm0
0x1c00ba88e  mov     word ptr [rdi+4], 9
0x1c00ba894  movups  xmmword ptr [rdi+60h], xmm0
0x1c00ba898  mov     eax, [rdi+0Ch]
0x1c00ba89b  mov     [rdi+260h], eax
0x1c00ba8a1  mov     [rdi+270h], eax
0x1c00ba8a7  cmp     [rbp+0C00h], r12
0x1c00ba8ae  jz      short loc_1C00BA8E1
0x1c00ba8b0  mov     byte ptr [rdi+2B1h], 9
0x1c00ba8b7  mov     r9, rdi
0x1c00ba8ba  mov     rax, [rbp+0C00h]
0x1c00ba8c1  mov     r8, rsi
  ... truncated ...
```
