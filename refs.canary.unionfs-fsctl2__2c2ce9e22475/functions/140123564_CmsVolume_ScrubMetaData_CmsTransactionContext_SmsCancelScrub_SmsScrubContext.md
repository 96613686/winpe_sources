# CmsVolume::ScrubMetaData(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)

- ea: `0x140123564`
- end: `0x140123fa0`
- name: `?ScrubMetaData@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z`
- size: `2620`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, struct _SmsCancelScrub *, struct _SmsScrubContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1401158ac`

## callees

- `0x140087ea0`
- `0x1400c96a8`
- `0x1400d06a0`
- `0x1401157bc`
- `0x140123564`
- `0x140131060`
- `0x140131d90`
- `0x140138b74`
- `0x14013b190`
- `0x14013c6a8`
- `0x14013e334`
- `0x14015f03c`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x140123667`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123712`
- `ntoskrnl!PsIsThreadTerminating` at `0x1401237d2`
- `ntoskrnl!PsIsThreadTerminating` at `0x14012388f`
- `ntoskrnl!PsIsThreadTerminating` at `0x14012394c`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123a09`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123ac6`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123b71`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123c32`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123d2e`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123e2d`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123eba`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123667`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123712`
- `ntoskrnl!PsIsThreadTerminating` at `0x1401237d2`
- `ntoskrnl!PsIsThreadTerminating` at `0x14012388f`
- `ntoskrnl!PsIsThreadTerminating` at `0x14012394c`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123a09`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123ac6`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123b71`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123c32`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123d2e`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123e2d`
- `ntoskrnl!PsIsThreadTerminating` at `0x140123eba`

## pseudocode

```c
__int64 __fastcall CmsVolume::ScrubMetaData(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        struct _SmsCancelScrub *a3,
        struct _SmsScrubContext *a4)
{
  unsigned int v5; // r9d
  int v9; // ebx
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  unsigned int v15; // r9d
  int v16; // ecx
  int v17; // eax
  CmsObjectTable *v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  CmsVolumeContainer *v30; // rcx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  unsigned int v37; // r9d
  unsigned int v38; // r9d
  unsigned int v39; // r9d
  unsigned int v40; // r9d
  unsigned int v41; // r9d
  unsigned int v42; // r9d
  int v44; // [rsp+A8h] [rbp+60h] BYREF
  int v45; // [rsp+ACh] [rbp+64h]

  v5 = *((unsigned __int8 *)a4 + 4);
  v9 = 0;
  if ( v5 <= 9 )
  {
    if ( v5 == 9 )
    {
LABEL_68:
      if ( *((_QWORD *)this + 421) )
      {
        *((_BYTE *)a4 + 841) = 9;
        v28 = CmsBlockRefcount::Scrub(*((CmsBlockRefcount **)this + 421), a2, a3, a4);
        *((_BYTE *)a4 + 841) = 0;
        v9 = v28;
        if ( v28 < 0 )
          return (unsigned int)v9;
      }
      if ( *((int *)a4 + 2) <= 0
        || **(_BYTE **)a3
        || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(a4)
        || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
      {
        return (unsigned int)-2147483643;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 10;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v29 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v29;
      *((_DWORD *)a4 + 194) = v29;
      goto LABEL_77;
    }
    if ( v5 && (v10 = v5 - 2) != 0 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                if ( v15 != 1 )
                  return (unsigned int)v9;
LABEL_59:
                if ( *((_QWORD *)this + 415) )
                {
                  *((_BYTE *)a4 + 841) = 8;
                  v26 = CmsAllocator::Scrub(*((CmsAllocator **)this + 415), a2, a3, a4);
                  *((_BYTE *)a4 + 841) = 0;
                  v9 = v26;
                  if ( v26 < 0 )
                    return (unsigned int)v9;
                }
                if ( *((int *)a4 + 2) <= 0
                  || **(_BYTE **)a3
                  || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
                  || PsIsThreadTerminating(KeGetCurrentThread())
                  || (unsigned __int8)MsScrubContextFoundError(a4)
                  || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
                {
                  return (unsigned int)-2147483643;
                }
                *((_DWORD *)a4 + 3) = 16;
                *((_WORD *)a4 + 2) = 9;
                *(_OWORD *)((char *)a4 + 104) = 0;
                v27 = *((_DWORD *)a4 + 3);
                *((_DWORD *)a4 + 190) = v27;
                *((_DWORD *)a4 + 194) = v27;
                goto LABEL_68;
              }
LABEL_50:
              if ( *((_QWORD *)this + 416) )
              {
                *((_BYTE *)a4 + 841) = 7;
                v24 = CmsAllocator::Scrub(*((CmsAllocator **)this + 416), a2, a3, a4);
                *((_BYTE *)a4 + 841) = 0;
                v9 = v24;
                if ( v24 < 0 )
                  return (unsigned int)v9;
              }
              if ( *((int *)a4 + 2) <= 0
                || **(_BYTE **)a3
                || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(a4)
                || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
              {
                return (unsigned int)-2147483643;
              }
              *((_DWORD *)a4 + 3) = 16;
              *((_WORD *)a4 + 2) = 8;
              *(_OWORD *)((char *)a4 + 104) = 0;
              v25 = *((_DWORD *)a4 + 3);
              *((_DWORD *)a4 + 190) = v25;
              *((_DWORD *)a4 + 194) = v25;
              goto LABEL_59;
            }
LABEL_41:
            if ( *((_QWORD *)this + 414) )
            {
              *((_BYTE *)a4 + 841) = 6;
              v22 = CmsAllocator::Scrub(*((CmsAllocator **)this + 414), a2, a3, a4);
              *((_BYTE *)a4 + 841) = 0;
              v9 = v22;
              if ( v22 < 0 )
                return (unsigned int)v9;
            }
            if ( *((int *)a4 + 2) <= 0
              || **(_BYTE **)a3
              || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
              || PsIsThreadTerminating(KeGetCurrentThread())
              || (unsigned __int8)MsScrubContextFoundError(a4)
              || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
            {
              return (unsigned int)-2147483643;
            }
            *((_DWORD *)a4 + 3) = 16;
            *((_WORD *)a4 + 2) = 7;
            *(_OWORD *)((char *)a4 + 104) = 0;
            v23 = *((_DWORD *)a4 + 3);
            *((_DWORD *)a4 + 190) = v23;
            *((_DWORD *)a4 + 194) = v23;
            goto LABEL_50;
          }
LABEL_32:
          if ( *((_QWORD *)this + 431) )
          {
            *((_BYTE *)a4 + 841) = 5;
            v20 = CmsFailoverBPlusTable::ScrubTable(**((CmsFailoverBPlusTable ***)this + 431), a2, a3, a4);
            *((_BYTE *)a4 + 841) = 0;
            v9 = v20;
            if ( v20 < 0 )
              return (unsigned int)v9;
          }
          if ( *((int *)a4 + 2) <= 0
            || **(_BYTE **)a3
            || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(a4)
            || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
          {
            return (unsigned int)-2147483643;
          }
          *((_DWORD *)a4 + 3) = 16;
          *((_WORD *)a4 + 2) = 6;
          *(_OWORD *)((char *)a4 + 104) = 0;
          v21 = *((_DWORD *)a4 + 3);
          *((_DWORD *)a4 + 190) = v21;
          *((_DWORD *)a4 + 194) = v21;
          goto LABEL_41;
        }
      }
    }
    else
    {
      if ( (*((_DWORD *)a4 + 198) & 1) == 0 )
      {
        *((_BYTE *)a4 + 841) = 2;
        v9 = CmsVolume::ScrubSuperblock(this, a2, a3, a4);
        *((_BYTE *)a4 + 841) = 0;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 3;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v16 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v16;
      *((_DWORD *)a4 + 194) = v16;
      if ( v9 < 0 )
        return (unsigned int)v9;
      if ( *((int *)a4 + 2) <= 0
        || **(_BYTE **)a3
        || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(a4)
        || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
      {
        return (unsigned int)-2147483643;
      }
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 3;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v17 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v17;
      *((_DWORD *)a4 + 194) = v17;
    }
    v18 = (CmsObjectTable *)*((_QWORD *)this + 426);
    if ( v18 )
      v9 = CmsObjectTable::Scrub(v18, a2, a3, a4);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 5;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v19 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v19;
    *((_DWORD *)a4 + 194) = v19;
    goto LABEL_32;
  }
  v37 = v5 - 10;
  if ( !v37 || (v38 = v37 - 1) == 0 )
  {
LABEL_77:
    v30 = (CmsVolumeContainer *)*((_QWORD *)this + 417);
    if ( v30 )
      v9 = CmsVolumeContainer::Scrub(v30, a2, a3, a4);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 12;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v31 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v31;
    *((_DWORD *)a4 + 194) = v31;
    goto LABEL_87;
  }
  v39 = v38 - 1;
  if ( !v39 )
  {
LABEL_87:
    if ( *((_QWORD *)this + 418) )
    {
      *((_BYTE *)a4 + 841) = 12;
      v32 = CmsAllocator::Scrub(*(CmsAllocator **)(*((_QWORD *)this + 418) + 8LL), a2, a3, a4);
      *((_BYTE *)a4 + 841) = 0;
      v9 = v32;
      if ( v32 < 0 )
        return (unsigned int)v9;
    }
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 13;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v33 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v33;
    *((_DWORD *)a4 + 194) = v33;
    goto LABEL_96;
  }
  v40 = v39 - 1;
  if ( !v40 )
  {
LABEL_96:
    *((_BYTE *)a4 + 841) = 13;
    v44 = 10;
    v45 = 9;
    v9 = CmsVolume::InitializeFailoverMetadataTable(this, a2, &v44);
    if ( v9 >= 0 )
      v9 = CmsFailoverBPlusTable::ScrubTable(0, a2, a3, a4);
    *((_BYTE *)a4 + 841) = 0;
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_DWORD *)a4 + 3) = 16;
    *((_WORD *)a4 + 2) = 14;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v34 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v34;
    *((_DWORD *)a4 + 194) = v34;
    goto LABEL_106;
  }
  v41 = v40 - 1;
  if ( v41 )
  {
    v42 = v41 - 1;
    if ( v42 )
    {
      if ( v42 != 1 )
        return (unsigned int)v9;
      goto LABEL_123;
    }
LABEL_116:
    if ( *((int *)a4 + 2) > 0
      && !**(_BYTE **)a3
      && (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) == 0
      && !PsIsThreadTerminating(KeGetCurrentThread())
      && !(unsigned __int8)MsScrubContextFoundError(a4)
      && *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) < *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      *((_DWORD *)a4 + 3) = 16;
      *((_WORD *)a4 + 2) = 16;
      *(_OWORD *)((char *)a4 + 104) = 0;
      v36 = *((_DWORD *)a4 + 3);
      *((_DWORD *)a4 + 190) = v36;
      *((_DWORD *)a4 + 194) = v36;
LABEL_123:
      if ( *((_QWORD *)this + 434) )
      {
        *((_BYTE *)a4 + 841) = 16;
        v9 = CmsTrashTable::Scrub(*((CmsTrashTable **)this + 434), a2, a3, a4);
        *((_BYTE *)a4 + 841) = 0;
      }
      return (unsigned int)v9;
    }
    return (unsigned int)-2147483643;
  }
LABEL_106:
  *((_BYTE *)a4 + 841) = 14;
  v44 = 8;
  v45 = 7;
  v9 = CmsVolume::InitializeFailoverMetadataTable(this, a2, &v44);
  if ( v9 >= 0 )
    v9 = CmsFailoverBPlusTable::ScrubTable(0, a2, a3, a4);
  *((_BYTE *)a4 + 841) = 0;
  if ( v9 >= 0 )
  {
    if ( *((int *)a4 + 2) <= 0
      || **(_BYTE **)a3
      || (**((_DWORD **)a3 + 1) & *((_DWORD *)a3 + 4)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(a4)
      || *(_WORD *)(*((_QWORD *)a4 + 107) + 4LL) >= *(_WORD *)(*((_QWORD *)a4 + 107) + 6LL) )
    {
      return (unsigned int)-2147483643;
    }
    *((_WORD *)a4 + 2) = 15;
    *((_DWORD *)a4 + 3) = 16;
    *(_OWORD *)((char *)a4 + 104) = 0;
    v35 = *((_DWORD *)a4 + 3);
    *((_DWORD *)a4 + 190) = v35;
    *((_DWORD *)a4 + 194) = v35;
    goto LABEL_116;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140123564  push    rbp
0x140123566  push    rbx
0x140123567  push    rsi
0x140123568  push    rdi
0x140123569  push    r12
0x14012356b  push    r13
0x14012356d  push    r14
0x14012356f  push    r15
0x140123571  mov     rbp, rsp
0x140123574  sub     rsp, 48h
0x140123578  xor     r13d, r13d
0x14012357b  mov     rdi, r9
0x14012357e  movzx   r9d, byte ptr [r9+4]
0x140123583  mov     rsi, r8
0x140123586  mov     r12, rdx
0x140123589  mov     r15, rcx
0x14012358c  mov     ebx, r13d
0x14012358f  lea     r14d, [r13+10h]
0x140123593  cmp     r9d, 9
0x140123597  ja      loc_140123F43
0x14012359d  jz      loc_140123A62
0x1401235a3  test    r9d, r9d
0x1401235a6  jz      short loc_1401235EF
0x1401235a8  sub     r9d, 2
0x1401235ac  jz      short loc_1401235EF
0x1401235ae  sub     r9d, 1
0x1401235b2  jz      loc_1401236C0
0x1401235b8  sub     r9d, 1
0x1401235bc  jz      loc_1401236C0
0x1401235c2  sub     r9d, 1
0x1401235c6  jz      loc_14012376B
0x1401235cc  sub     r9d, 1
0x1401235d0  jz      loc_14012382B
0x1401235d6  sub     r9d, 1
0x1401235da  jz      loc_1401238E8
0x1401235e0  cmp     r9d, 1
0x1401235e4  jz      loc_1401239A5
0x1401235ea  jmp     loc_140123F8C
0x1401235ef  mov     eax, [rdi+318h]
0x1401235f5  test    al, 1
0x1401235f7  jnz     short loc_140123611
0x1401235f9  mov     r9, rdi; struct _SmsScrubContext *
0x1401235fc  mov     byte ptr [rdi+349h], 2
0x140123603  call    ?ScrubSuperblock@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsVolume::ScrubSuperblock(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140123608  mov     ebx, eax
0x14012360a  mov     [rdi+349h], r13b
0x140123611  mov     [rdi+0Ch], r14d
0x140123615  xorps   xmm0, xmm0
0x140123618  mov     word ptr [rdi+4], 3
0x14012361e  movups  xmmword ptr [rdi+68h], xmm0
0x140123622  mov     ecx, [rdi+0Ch]
0x140123625  mov     [rdi+2F8h], ecx
0x14012362b  mov     [rdi+308h], ecx
0x140123631  test    ebx, ebx
0x140123633  js      loc_140123F8C
0x140123639  cmp     [rdi+8], r13d
0x14012363d  jle     loc_140123F87
0x140123643  mov     rax, [rsi]
0x140123646  cmp     [rax], r13b
0x140123649  jnz     loc_140123F87
0x14012364f  mov     rax, [rsi+8]
0x140123653  mov     ecx, [rax]
0x140123655  test    [rsi+10h], ecx
0x140123658  jnz     loc_140123F87
0x14012365e  mov     rcx, gs:188h; Thread
0x140123667  call    cs:__imp_PsIsThreadTerminating
0x14012366e  nop     dword ptr [rax+rax+00h]
0x140123673  test    al, al
0x140123675  jnz     loc_140123F87
0x14012367b  mov     rcx, rdi
0x14012367e  call    MsScrubContextFoundError
0x140123683  test    al, al
0x140123685  jnz     loc_140123F87
0x14012368b  mov     rcx, [rdi+358h]
0x140123692  movzx   eax, word ptr [rcx+6]
0x140123696  cmp     [rcx+4], ax
0x14012369a  jnb     loc_140123F87
0x1401236a0  mov     [rdi+0Ch], r14d
0x1401236a4  xorps   xmm0, xmm0
0x1401236a7  mov     word ptr [rdi+4], 3
0x1401236ad  movups  xmmword ptr [rdi+68h], xmm0
0x1401236b1  mov     eax, [rdi+0Ch]
0x1401236b4  mov     [rdi+2F8h], eax
0x1401236ba  mov     [rdi+308h], eax
0x1401236c0  mov     rcx, [r15+0D50h]; this
0x1401236c7  test    rcx, rcx
0x1401236ca  jz      short loc_1401236DC
0x1401236cc  mov     r9, rdi; struct _SmsScrubContext *
0x1401236cf  mov     r8, rsi; struct _SmsCancelScrub *
0x1401236d2  mov     rdx, r12; struct CmsTransactionContext *
0x1401236d5  call    ?Scrub@CmsObjectTable@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsObjectTable::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1401236da  mov     ebx, eax
0x1401236dc  test    ebx, ebx
0x1401236de  js      loc_140123F8C
0x1401236e4  cmp     [rdi+8], r13d
0x1401236e8  jle     loc_140123F87
0x1401236ee  mov     rax, [rsi]
0x1401236f1  cmp     [rax], r13b
0x1401236f4  jnz     loc_140123F87
0x1401236fa  mov     rax, [rsi+8]
0x1401236fe  mov     ecx, [rax]
0x140123700  test    [rsi+10h], ecx
0x140123703  jnz     loc_140123F87
0x140123709  mov     rcx, gs:188h; Thread
0x140123712  call    cs:__imp_PsIsThreadTerminating
0x140123719  nop     dword ptr [rax+rax+00h]
0x14012371e  test    al, al
0x140123720  jnz     loc_140123F87
0x140123726  mov     rcx, rdi
0x140123729  call    MsScrubContextFoundError
0x14012372e  test    al, al
0x140123730  jnz     loc_140123F87
0x140123736  mov     rcx, [rdi+358h]
0x14012373d  movzx   eax, word ptr [rcx+6]
0x140123741  cmp     [rcx+4], ax
0x140123745  jnb     loc_140123F87
0x14012374b  mov     [rdi+0Ch], r14d
0x14012374f  xorps   xmm0, xmm0
0x140123752  mov     word ptr [rdi+4], 5
0x140123758  movups  xmmword ptr [rdi+68h], xmm0
0x14012375c  mov     eax, [rdi+0Ch]
0x14012375f  mov     [rdi+2F8h], eax
0x140123765  mov     [rdi+308h], eax
0x14012376b  cmp     [r15+0D78h], r13
0x140123772  jz      short loc_1401237A4
0x140123774  mov     byte ptr [rdi+349h], 5
0x14012377b  mov     r9, rdi; struct _SmsScrubContext *
0x14012377e  mov     rcx, [r15+0D78h]
0x140123785  mov     r8, rsi; struct _SmsCancelScrub *
0x140123788  mov     rdx, r12; struct CmsTransactionContext *
0x14012378b  mov     rcx, [rcx]; this
0x14012378e  call    ?ScrubTable@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsFailoverBPlusTable::ScrubTable(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140123793  mov     [rdi+349h], r13b
0x14012379a  mov     ebx, eax
0x14012379c  test    eax, eax
0x14012379e  js      loc_140123F8C
0x1401237a4  cmp     [rdi+8], r13d
0x1401237a8  jle     loc_140123F87
0x1401237ae  mov     rax, [rsi]
0x1401237b1  cmp     [rax], r13b
0x1401237b4  jnz     loc_140123F87
0x1401237ba  mov     rax, [rsi+8]
0x1401237be  mov     ecx, [rax]
0x1401237c0  test    [rsi+10h], ecx
0x1401237c3  jnz     loc_140123F87
0x1401237c9  mov     rcx, gs:188h; Thread
0x1401237d2  call    cs:__imp_PsIsThreadTerminating
0x1401237d9  nop     dword ptr [rax+rax+00h]
0x1401237de  test    al, al
0x1401237e0  jnz     loc_140123F87
0x1401237e6  mov     rcx, rdi
0x1401237e9  call    MsScrubContextFoundError
0x1401237ee  test    al, al
0x1401237f0  jnz     loc_140123F87
0x1401237f6  mov     rcx, [rdi+358h]
0x1401237fd  movzx   eax, word ptr [rcx+6]
0x140123801  cmp     [rcx+4], ax
0x140123805  jnb     loc_140123F87
0x14012380b  mov     [rdi+0Ch], r14d
0x14012380f  xorps   xmm0, xmm0
0x140123812  mov     word ptr [rdi+4], 6
0x140123818  movups  xmmword ptr [rdi+68h], xmm0
0x14012381c  mov     eax, [rdi+0Ch]
0x14012381f  mov     [rdi+2F8h], eax
0x140123825  mov     [rdi+308h], eax
0x14012382b  cmp     [r15+0CF0h], r13
0x140123832  jz      short loc_140123861
0x140123834  mov     byte ptr [rdi+349h], 6
0x14012383b  mov     r9, rdi; struct _SmsScrubContext *
0x14012383e  mov     rcx, [r15+0CF0h]; this
0x140123845  mov     r8, rsi; struct _SmsCancelScrub *
0x140123848  mov     rdx, r12; struct CmsTransactionContext *
0x14012384b  call    ?Scrub@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsAllocator::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140123850  mov     [rdi+349h], r13b
0x140123857  mov     ebx, eax
0x140123859  test    eax, eax
0x14012385b  js      loc_140123F8C
0x140123861  cmp     [rdi+8], r13d
0x140123865  jle     loc_140123F87
0x14012386b  mov     rax, [rsi]
0x14012386e  cmp     [rax], r13b
0x140123871  jnz     loc_140123F87
0x140123877  mov     rax, [rsi+8]
0x14012387b  mov     ecx, [rax]
0x14012387d  test    [rsi+10h], ecx
0x140123880  jnz     loc_140123F87
0x140123886  mov     rcx, gs:188h; Thread
0x14012388f  call    cs:__imp_PsIsThreadTerminating
0x140123896  nop     dword ptr [rax+rax+00h]
0x14012389b  test    al, al
0x14012389d  jnz     loc_140123F87
0x1401238a3  mov     rcx, rdi
0x1401238a6  call    MsScrubContextFoundError
0x1401238ab  test    al, al
0x1401238ad  jnz     loc_140123F87
0x1401238b3  mov     rcx, [rdi+358h]
0x1401238ba  movzx   eax, word ptr [rcx+6]
0x1401238be  cmp     [rcx+4], ax
0x1401238c2  jnb     loc_140123F87
0x1401238c8  mov     [rdi+0Ch], r14d
0x1401238cc  xorps   xmm0, xmm0
0x1401238cf  mov     word ptr [rdi+4], 7
0x1401238d5  movups  xmmword ptr [rdi+68h], xmm0
0x1401238d9  mov     eax, [rdi+0Ch]
0x1401238dc  mov     [rdi+2F8h], eax
0x1401238e2  mov     [rdi+308h], eax
0x1401238e8  cmp     [r15+0D00h], r13
0x1401238ef  jz      short loc_14012391E
0x1401238f1  mov     byte ptr [rdi+349h], 7
0x1401238f8  mov     r9, rdi; struct _SmsScrubContext *
0x1401238fb  mov     rcx, [r15+0D00h]; this
0x140123902  mov     r8, rsi; struct _SmsCancelScrub *
0x140123905  mov     rdx, r12; struct CmsTransactionContext *
0x140123908  call    ?Scrub@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsAllocator::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x14012390d  mov     [rdi+349h], r13b
0x140123914  mov     ebx, eax
0x140123916  test    eax, eax
0x140123918  js      loc_140123F8C
0x14012391e  cmp     [rdi+8], r13d
0x140123922  jle     loc_140123F87
0x140123928  mov     rax, [rsi]
0x14012392b  cmp     [rax], r13b
0x14012392e  jnz     loc_140123F87
0x140123934  mov     rax, [rsi+8]
0x140123938  mov     ecx, [rax]
0x14012393a  test    [rsi+10h], ecx
0x14012393d  jnz     loc_140123F87
0x140123943  mov     rcx, gs:188h; Thread
0x14012394c  call    cs:__imp_PsIsThreadTerminating
0x140123953  nop     dword ptr [rax+rax+00h]
0x140123958  test    al, al
0x14012395a  jnz     loc_140123F87
0x140123960  mov     rcx, rdi
0x140123963  call    MsScrubContextFoundError
0x140123968  test    al, al
0x14012396a  jnz     loc_140123F87
0x140123970  mov     rcx, [rdi+358h]
0x140123977  movzx   eax, word ptr [rcx+6]
0x14012397b  cmp     [rcx+4], ax
0x14012397f  jnb     loc_140123F87
0x140123985  mov     [rdi+0Ch], r14d
0x140123989  xorps   xmm0, xmm0
0x14012398c  mov     word ptr [rdi+4], 8
0x140123992  movups  xmmword ptr [rdi+68h], xmm0
0x140123996  mov     eax, [rdi+0Ch]
0x140123999  mov     [rdi+2F8h], eax
0x14012399f  mov     [rdi+308h], eax
0x1401239a5  cmp     [r15+0CF8h], r13
0x1401239ac  jz      short loc_1401239DB
0x1401239ae  mov     byte ptr [rdi+349h], 8
0x1401239b5  mov     r9, rdi; struct _SmsScrubContext *
0x1401239b8  mov     rcx, [r15+0CF8h]; this
0x1401239bf  mov     r8, rsi; struct _SmsCancelScrub *
0x1401239c2  mov     rdx, r12; struct CmsTransactionContext *
0x1401239c5  call    ?Scrub@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsAllocator::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x1401239ca  mov     [rdi+349h], r13b
0x1401239d1  mov     ebx, eax
0x1401239d3  test    eax, eax
0x1401239d5  js      loc_140123F8C
0x1401239db  cmp     [rdi+8], r13d
0x1401239df  jle     loc_140123F87
0x1401239e5  mov     rax, [rsi]
0x1401239e8  cmp     [rax], r13b
0x1401239eb  jnz     loc_140123F87
0x1401239f1  mov     rax, [rsi+8]
0x1401239f5  mov     ecx, [rax]
0x1401239f7  test    [rsi+10h], ecx
0x1401239fa  jnz     loc_140123F87
0x140123a00  mov     rcx, gs:188h; Thread
0x140123a09  call    cs:__imp_PsIsThreadTerminating
0x140123a10  nop     dword ptr [rax+rax+00h]
0x140123a15  test    al, al
0x140123a17  jnz     loc_140123F87
0x140123a1d  mov     rcx, rdi
0x140123a20  call    MsScrubContextFoundError
0x140123a25  test    al, al
0x140123a27  jnz     loc_140123F87
0x140123a2d  mov     rcx, [rdi+358h]
0x140123a34  movzx   eax, word ptr [rcx+6]
0x140123a38  cmp     [rcx+4], ax
0x140123a3c  jnb     loc_140123F87
0x140123a42  mov     [rdi+0Ch], r14d
0x140123a46  xorps   xmm0, xmm0
0x140123a49  mov     word ptr [rdi+4], 9
0x140123a4f  movups  xmmword ptr [rdi+68h], xmm0
0x140123a53  mov     eax, [rdi+0Ch]
0x140123a56  mov     [rdi+2F8h], eax
0x140123a5c  mov     [rdi+308h], eax
0x140123a62  cmp     [r15+0D28h], r13
0x140123a69  jz      short loc_140123A98
0x140123a6b  mov     byte ptr [rdi+349h], 9
0x140123a72  mov     r9, rdi; struct _SmsScrubContext *
0x140123a75  mov     rcx, [r15+0D28h]; this
0x140123a7c  mov     r8, rsi; struct _SmsCancelScrub *
0x140123a7f  mov     rdx, r12; struct CmsTransactionContext *
0x140123a82  call    ?Scrub@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsCancelScrub@@PEAU_SmsScrubContext@@@Z; CmsBlockRefcount::Scrub(CmsTransactionContext *,_SmsCancelScrub *,_SmsScrubContext *)
0x140123a87  mov     [rdi+349h], r13b
0x140123a8e  mov     ebx, eax
0x140123a90  test    eax, eax
0x140123a92  js      loc_140123F8C
  ... truncated ...
```
