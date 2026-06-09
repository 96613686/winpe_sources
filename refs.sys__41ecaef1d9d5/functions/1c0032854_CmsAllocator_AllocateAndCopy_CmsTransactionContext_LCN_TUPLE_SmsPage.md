# CmsAllocator::AllocateAndCopy(CmsTransactionContext *,_LCN_TUPLE *,SmsPage *)

- ea: `0x1c0032854`
- end: `0x1c0032b2a`
- name: `?AllocateAndCopy@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@PEAUSmsPage@@@Z`
- size: `726`
- prototype: `int(CmsAllocator *__hidden this, struct CmsTransactionContext *, union _LCN_TUPLE *, struct SmsPage *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1c0017350`

## callees

- `0x1c0019730`
- `0x1c001cb20`
- `0x1c0024e28`
- `0x1c0032854`
- `0x1c0032c14`
- `0x1c0032dc0`
- `0x1c00b11a0`
- `0x1c00b5fe8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0032967`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0032967`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00329c5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00329c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0032a50`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0032a97`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0032a50`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0032a97`
- `ntoskrnl!KeSetEvent` at `0x1c00329a7`
- `ntoskrnl!KeSetEvent` at `0x1c00329a7`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1c0032949`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1c0032949`

## pseudocode

```c
__int64 __fastcall CmsAllocator::AllocateAndCopy(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        union _LCN_TUPLE *a3,
        struct SmsPage *a4)
{
  __int64 v4; // rdi
  __int64 v6; // rcx
  CmsVolume *v9; // rcx
  struct SmsUndoRecord *Undo; // r15
  unsigned __int64 v11; // rax
  int v12; // r14d
  struct SmsPage *v13; // rax
  struct CmsTransactionContext *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  struct SmsPage *v17; // rdi
  struct CmsTransactionContext *v19; // rdx
  unsigned int v20; // r8d
  __int128 v21; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h]
  _QWORD v23[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h]
  struct SmsPage *v25; // [rsp+A0h] [rbp+20h] BYREF

  v4 = *((_QWORD *)this + 6);
  v6 = *((_QWORD *)a4 + 15);
  v25 = 0;
  v24 = 0;
  v22 = 0;
  v21 = 0;
  Undo = (struct SmsUndoRecord *)CmsBPlusTable::AllocateUndo(v6, (__int64)a2, 1, (__int64)a4, 0x18u, 0);
  if ( !Undo )
  {
    v12 = -1073741670;
    goto LABEL_22;
  }
  v11 = *((_QWORD *)a4 + 15);
  v21 = v11;
  BYTE4(v22) = 0;
  LODWORD(v22) = *(_DWORD *)(v11 + 116);
  BYTE5(v22) = *((_BYTE *)a4 + 328);
  v12 = CmsVolume::PinSinglePage((CmsVolume *)v4, a2, (struct _SmsView *)&v21, a3, *((_DWORD *)a4 + 80), 7u, 0, 0, &v25);
  if ( v12 < 0 )
  {
LABEL_22:
    CmsVolume::ClearPageCopyingState(v9, a4, 0);
    CmsBPlusTable::FreeUndoRecord(Undo, v19, v20);
    return (unsigned int)v12;
  }
  RtlCopyMemoryNonTemporal(
    (void *)(*((_QWORD *)v25 + 16) + 80LL),
    (const void *)(*((_QWORD *)a4 + 16) + 80LL),
    (unsigned int)(*((_DWORD *)a4 + 80) << *(_DWORD *)(v4 + 64)) - 80LL);
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a4 + 15) + 32LL) + 32LL) + 48LL), 0);
  *((_QWORD *)v25 + 35) = a4;
  v13 = v25;
  ++*((_DWORD *)a4 + 76);
  *((_QWORD *)a4 + 36) = v13;
  _InterlockedXor64((volatile signed __int64 *)a4 + 51, 0x1008u);
  KeSetEvent((PRKEVENT)a4 + 16, 0, 0);
  ExReleasePushLockEx(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a4 + 15) + 32LL) + 32LL) + 48LL), 0);
  v15 = *(_QWORD *)(v4 + 3056);
  if ( v15 )
  {
    if ( *(_BYTE *)(v15 + 16) )
    {
      v16 = *((_QWORD *)a4 + 15);
      if ( (*(_DWORD *)(v16 + 16) & 0x8000000) == 0 && *(_BYTE *)(*(_QWORD *)(v16 + 40) + 84LL) == 4 )
      {
        if ( !*((_QWORD *)a4 + 35) && (*((_QWORD *)a4 + 51) & 0x20000000LL) == 0
          || !*((_BYTE *)a4 + 328)
          && (v14 = (struct CmsTransactionContext *)*(unsigned int *)(*((_QWORD *)a4 + 15) + 16LL),
              ((unsigned int)v14 & 0x2000000) != 0) )
        {
          CmsVolumeContainer::GeneratePageChecksum(*(CmsVolumeContainer **)(v4 + 3048), v14, a4);
        }
      }
    }
  }
  v23[0] = a4;
  LODWORD(v24) = 4;
  _InterlockedIncrement((volatile signed __int32 *)a4 + 81);
  if ( (*((_QWORD *)a4 + 51) & 0x20) == 0 )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)a4 + 4, 0);
    if ( !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)a4 + 15)) )
      ++*((_DWORD *)a2 + 6);
  }
  v17 = v25;
  v23[1] = v25;
  HIDWORD(v24) = 1;
  _InterlockedIncrement((volatile signed __int32 *)v25 + 81);
  if ( (*((_QWORD *)v17 + 51) & 0x20) == 0 )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)v17 + 4, 0);
    if ( !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v17 + 15)) )
      ++*((_DWORD *)a2 + 6);
  }
  CmsBPlusTable::FormatUndoRecord(*((CmsBPlusTable **)a4 + 15), a2, Undo, 0, v23, 0x18u, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1c0032854  mov     [rsp-18h+arg_8], rbx
0x1c0032859  mov     [rsp-18h+arg_10], rsi
0x1c003285e  mov     [rsp-18h+arg_18], rdi
0x1c0032863  push    rbp
0x1c0032864  push    r14
0x1c0032866  push    r15
0x1c0032868  mov     rbp, rsp
0x1c003286b  sub     rsp, 80h
0x1c0032872  mov     rdi, [rcx+30h]
0x1c0032876  xor     eax, eax
0x1c0032878  and     [rsp+80h+var_58], eax
0x1c003287c  mov     r14, r8
0x1c003287f  mov     rcx, [r9+78h]
0x1c0032883  xorps   xmm0, xmm0
0x1c0032886  and     [rbp+arg_0], 0
0x1c003288b  mov     rbx, r9
0x1c003288e  lea     r8d, [rax+1]
0x1c0032892  mov     [rbp+var_8], rax
0x1c0032896  mov     rsi, rdx
0x1c0032899  mov     [rbp+var_20], rax
0x1c003289d  movups  [rbp+var_30], xmm0
0x1c00328a1  mov     dword ptr [rsp+80h+var_60], 18h
0x1c00328a9  call    ?AllocateUndo@CmsBPlusTable@@QEAAPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@W4_MS_UNDO_OPERATION@@EKJKE@Z; CmsBPlusTable::AllocateUndo(CmsTransactionContext *,_MS_UNDO_OPERATION,uchar,ulong,long,ulong,uchar)
0x1c00328ae  mov     r15, rax
0x1c00328b1  test    rax, rax
0x1c00328b4  jz      loc_1C007E6B4
0x1c00328ba  mov     rax, [rbx+78h]
0x1c00328be  lea     r8, [rbp+var_30]; struct _SmsView *
0x1c00328c2  and     qword ptr [rbp+var_30+8], 0
0x1c00328c7  mov     r9, r14; union _LCN_TUPLE *
0x1c00328ca  mov     qword ptr [rbp+var_30], rax
0x1c00328ce  mov     rdx, rsi; struct CmsTransactionContext *
0x1c00328d1  mov     byte ptr [rbp+var_20+4], 0
0x1c00328d5  mov     rcx, rdi; this
0x1c00328d8  mov     eax, [rax+74h]
0x1c00328db  mov     dword ptr [rbp+var_20], eax
0x1c00328de  mov     al, [rbx+148h]
0x1c00328e4  mov     byte ptr [rbp+var_20+5], al
0x1c00328e7  lea     rax, [rbp+arg_0]
0x1c00328eb  mov     [rsp+80h+var_40], rax; struct SmsPage **
0x1c00328f0  and     [rsp+80h+var_48], 0
0x1c00328f6  and     [rsp+80h+var_50], 0
0x1c00328fc  mov     eax, [rbx+140h]
0x1c0032902  mov     [rsp+80h+var_58], 7; unsigned int
0x1c003290a  mov     dword ptr [rsp+80h+var_60], eax; unsigned int
0x1c003290e  call    ?PinSinglePage@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsView@@PEAT_LCN_TUPLE@@KKPEAU_SmsChecksumBlob@@PEAPEAU_SmsPageHeader@@PEAPEAUSmsPage@@@Z; CmsVolume::PinSinglePage(CmsTransactionContext *,_SmsView *,_LCN_TUPLE *,ulong,ulong,_SmsChecksumBlob *,_SmsPageHeader * *,SmsPage * *)
0x1c0032913  mov     r14d, eax
0x1c0032916  test    eax, eax
0x1c0032918  js      loc_1C007E6BA
0x1c003291e  mov     r8d, [rbx+140h]
0x1c0032925  mov     ecx, [rdi+40h]
0x1c0032928  mov     rdx, [rbx+80h]
0x1c003292f  shl     r8d, cl
0x1c0032932  add     rdx, 50h ; 'P'; Source
0x1c0032936  mov     rcx, [rbp+arg_0]
0x1c003293a  sub     r8, 50h ; 'P'; Length
0x1c003293e  mov     rcx, [rcx+80h]
0x1c0032945  add     rcx, 50h ; 'P'; Destination
0x1c0032949  call    cs:__imp_RtlCopyMemoryNonTemporal
0x1c0032950  nop     dword ptr [rax+rax+00h]
0x1c0032955  mov     rax, [rbx+78h]
0x1c0032959  xor     edx, edx
0x1c003295b  mov     rcx, [rax+20h]
0x1c003295f  mov     rcx, [rcx+20h]
0x1c0032963  mov     rcx, [rcx+30h]
0x1c0032967  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c003296e  nop     dword ptr [rax+rax+00h]
0x1c0032973  mov     rax, [rbp+arg_0]
0x1c0032977  mov     [rax+118h], rbx
0x1c003297e  mov     rax, [rbp+arg_0]
0x1c0032982  inc     dword ptr [rbx+130h]
0x1c0032988  mov     [rbx+120h], rax
0x1c003298f  lock xor qword ptr [rbx+198h], 1008h
0x1c003299b  lea     rcx, [rbx+180h]; Event
0x1c00329a2  xor     r8d, r8d; Wait
0x1c00329a5  xor     edx, edx; Increment
0x1c00329a7  call    cs:__imp_KeSetEvent
0x1c00329ae  nop     dword ptr [rax+rax+00h]
0x1c00329b3  mov     rax, [rbx+78h]
0x1c00329b7  xor     edx, edx
0x1c00329b9  mov     rcx, [rax+20h]
0x1c00329bd  mov     rcx, [rcx+20h]
0x1c00329c1  mov     rcx, [rcx+30h]
0x1c00329c5  call    cs:__imp_ExReleasePushLockEx
0x1c00329cc  nop     dword ptr [rax+rax+00h]
0x1c00329d1  mov     rax, [rdi+0BF0h]
0x1c00329d8  test    rax, rax
0x1c00329db  jz      short loc_1C0032A2A
0x1c00329dd  cmp     byte ptr [rax+10h], 0
0x1c00329e1  jz      short loc_1C0032A2A
0x1c00329e3  mov     rcx, [rbx+78h]
0x1c00329e7  mov     eax, [rcx+10h]
0x1c00329ea  bt      rax, 1Bh
0x1c00329ef  jb      short loc_1C0032A2A
0x1c00329f1  mov     rax, [rcx+28h]
0x1c00329f5  cmp     byte ptr [rax+54h], 4
0x1c00329f9  jnz     short loc_1C0032A2A
0x1c00329fb  cmp     qword ptr [rbx+118h], 0
0x1c0032a03  jnz     loc_1C0032B06
0x1c0032a09  mov     rax, [rbx+198h]
0x1c0032a10  bt      rax, 1Dh
0x1c0032a15  jb      loc_1C0032B06
0x1c0032a1b  mov     rcx, [rdi+0BE8h]; this
0x1c0032a22  mov     r8, rbx; struct SmsPage *
0x1c0032a25  call    ?GeneratePageChecksum@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@PEAUSmsPage@@@Z; CmsVolumeContainer::GeneratePageChecksum(CmsTransactionContext *,SmsPage *)
0x1c0032a2a  mov     [rbp+var_18], rbx
0x1c0032a2e  mov     dword ptr [rbp+var_8], 4
0x1c0032a35  lock inc dword ptr [rbx+144h]
0x1c0032a3c  mov     rax, [rbx+198h]
0x1c0032a43  test    al, 20h
0x1c0032a45  jnz     short loc_1C0032A6D
0x1c0032a47  lea     rcx, [rbx+1A0h]; Resource
0x1c0032a4e  xor     edx, edx; Wait
0x1c0032a50  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0032a57  nop     dword ptr [rax+rax+00h]
0x1c0032a5c  mov     rcx, [rbx+78h]; this
0x1c0032a60  call    ?WasUpdateDeferred@CmsBPlusTable@@QEAAEXZ; CmsBPlusTable::WasUpdateDeferred(void)
0x1c0032a65  test    al, al
0x1c0032a67  jz      loc_1C0032AF9
0x1c0032a6d  mov     rdi, [rbp+arg_0]
0x1c0032a71  mov     [rbp+var_10], rdi
0x1c0032a75  mov     dword ptr [rbp+var_8+4], 1
0x1c0032a7c  lock inc dword ptr [rdi+144h]
0x1c0032a83  mov     rax, [rdi+198h]
0x1c0032a8a  test    al, 20h
0x1c0032a8c  jnz     short loc_1C0032AB0
0x1c0032a8e  lea     rcx, [rdi+1A0h]; Resource
0x1c0032a95  xor     edx, edx; Wait
0x1c0032a97  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0032a9e  nop     dword ptr [rax+rax+00h]
0x1c0032aa3  mov     rcx, [rdi+78h]; this
0x1c0032aa7  call    ?WasUpdateDeferred@CmsBPlusTable@@QEAAEXZ; CmsBPlusTable::WasUpdateDeferred(void)
0x1c0032aac  test    al, al
0x1c0032aae  jz      short loc_1C0032B01
0x1c0032ab0  and     dword ptr [rsp+80h+var_50], 0
0x1c0032ab5  lea     rax, [rbp+var_18]
0x1c0032ab9  mov     rcx, [rbx+78h]; this
0x1c0032abd  xor     r9d, r9d; struct _SmsLookupStack *
0x1c0032ac0  mov     [rsp+80h+var_58], 18h; unsigned int
0x1c0032ac8  mov     r8, r15; struct SmsUndoRecord *
0x1c0032acb  mov     rdx, rsi; struct CmsTransactionContext *
0x1c0032ace  mov     [rsp+80h+var_60], rax; void *
0x1c0032ad3  call    ?FormatUndoRecord@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@PEAU_SmsLookupStack@@PEAXKJ@Z; CmsBPlusTable::FormatUndoRecord(CmsTransactionContext *,SmsUndoRecord *,_SmsLookupStack *,void *,ulong,long)
0x1c0032ad8  lea     r11, [rsp+80h+var_s0]
0x1c0032ae0  mov     eax, r14d
0x1c0032ae3  mov     rbx, [r11+28h]
0x1c0032ae7  mov     rsi, [r11+30h]
0x1c0032aeb  mov     rdi, [r11+38h]
0x1c0032aef  mov     rsp, r11
0x1c0032af2  pop     r15
0x1c0032af4  pop     r14
0x1c0032af6  pop     rbp
0x1c0032af7  retn
0x1c0032af9  inc     dword ptr [rsi+18h]
0x1c0032afc  jmp     loc_1C0032A6D
0x1c0032b01  inc     dword ptr [rsi+18h]
0x1c0032b04  jmp     short loc_1C0032AB0
0x1c0032b06  cmp     byte ptr [rbx+148h], 0
0x1c0032b0d  jnz     loc_1C0032A2A
0x1c0032b13  mov     rax, [rbx+78h]
0x1c0032b17  mov     edx, [rax+10h]
0x1c0032b1a  bt      rdx, 19h
0x1c0032b1f  jnb     loc_1C0032A2A
0x1c0032b25  jmp     loc_1C0032A1B
0x1c007e6b4  mov     r14d, 0C000009Ah
0x1c007e6ba  xor     r8d, r8d; unsigned __int8
0x1c007e6bd  mov     rdx, rbx; struct SmsPage *
0x1c007e6c0  call    ?ClearPageCopyingState@CmsVolume@@QEAAXPEAUSmsPage@@E@Z; CmsVolume::ClearPageCopyingState(SmsPage *,uchar)
0x1c007e6c5  mov     rcx, r15; struct SmsUndoRecord *
0x1c007e6c8  call    ?FreeUndoRecord@CmsBPlusTable@@SAXPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@K@Z; CmsBPlusTable::FreeUndoRecord(SmsUndoRecord *,CmsTransactionContext *,ulong)
0x1c007e6cd  nop
0x1c007e6ce  jmp     loc_1C0032AD8
```
