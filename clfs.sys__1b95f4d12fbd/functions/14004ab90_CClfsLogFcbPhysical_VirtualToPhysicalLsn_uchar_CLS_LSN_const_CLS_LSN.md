# CClfsLogFcbPhysical::VirtualToPhysicalLsn(uchar,_CLS_LSN const &,_CLS_LSN &)

- ea: `0x14004ab90`
- end: `0x14004ae0f`
- name: `?VirtualToPhysicalLsn@CClfsLogFcbPhysical@@UEAAJEAEBT_CLS_LSN@@AEAT2@@Z`
- size: `639`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, unsigned __int8, const union _CLS_LSN *, union _CLS_LSN *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003590`
- `0x140005840`
- `0x140005f00`
- `0x1400075b0`
- `0x140008394`
- `0x140008c40`
- `0x14000a8e0`
- `0x14000a920`
- `0x14000ee30`
- `0x140010548`
- `0x140017f20`
- `0x140017f80`
- `0x14004ab90`
- `0x140064378`
- `0x140064dac`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004abe9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004abe9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004ac03`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14004ac03`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::VirtualToPhysicalLsn(
        CClfsLogFcbPhysical *this,
        unsigned __int8 a2,
        const union _CLS_LSN *a3,
        union _CLS_LSN *a4)
{
  const union _CLS_LSN *v5; // rsi
  char v7; // r12
  char *v8; // r15
  BOOLEAN v9; // di
  unsigned int *v10; // r14
  int LsnRegion; // esi
  bool v12; // di
  const CLFS_LSN *v13; // rdx
  const CLFS_LSN *v14; // rcx
  __int64 v15; // r8
  const union _CLS_LSN *v16; // rax
  struct _ERESOURCE *v17; // rbx
  ULONG v18; // edi
  ULONG v19; // ebx
  CLFS_CONTAINER_ID v20; // eax
  BOOLEAN v22; // [rsp+40h] [rbp-58h]
  _BYTE v23[64]; // [rsp+58h] [rbp-40h] BYREF
  union _CLS_LSN v26; // [rsp+B8h] [rbp+20h] BYREF

  v5 = a3;
  v26 = CLFS_LSN_INVALID;
  v7 = 0;
  *a4 = CLFS_LSN_INVALID;
  v8 = (char *)this - 608;
  v9 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this - 408), 1u);
  v22 = v9;
  v10 = (unsigned int *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
  if ( v10 )
  {
    v7 = 1;
    if ( (*((_DWORD *)this - 61) & 0x1000) != 0 )
    {
      LsnRegion = -1072037845;
      CClfsLogFcbCommon::SetInvalidLogTag((CClfsLogFcbCommon *)v8, 0x10u, -1072037845);
      goto LABEL_14;
    }
    v12 = 0;
    if ( (unsigned __int8)operator>=(v5) )
    {
      v12 = ClfsLsnLess(v14, v13 + 1) != 0;
      LOBYTE(v15) = a2;
    }
    if ( v12 )
    {
      v26 = **(union _CLS_LSN **)&CClfsLogFcbPhysical::GetNextRegionLsn(
                                    (CClfsLogFcbPhysical *)v8,
                                    &v26,
                                    (int)this - 104);
      memmove(v10, *((const void **)this + 12), 0x1000u);
    }
    else
    {
      v16 = (const union _CLS_LSN *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, _BYTE *, __int64))(*(_QWORD *)this + 288LL))(
                                      this,
                                      v23,
                                      v15);
      LsnRegion = CClfsLogFcbPhysical::FindLsnRegion(
                    (CClfsLogFcbPhysical *)v8,
                    a2,
                    v5,
                    v16,
                    (unsigned __int8 *)v10,
                    &v26);
      if ( LsnRegion < 0 )
      {
LABEL_13:
        v9 = v22;
        goto LABEL_14;
      }
      v5 = a3;
    }
    v17 = (struct _ERESOURCE *)(v8 + 200);
    ClfsReleaseResourceLite((struct _ERESOURCE *)(v8 + 200));
    v9 = 0;
    v22 = 0;
    LsnRegion = CClfsLogFcbPhysical::MapPhysicalBlockOffset(
                  (CClfsLogFcbPhysical *)v8,
                  a2,
                  v5,
                  &v26,
                  (const struct _CLFS_OWNER_REFERRAL *)((char *)&v10[4 * a2] + v10[12]),
                  (const struct _CLFS_OWNER_ENTRY *const)((char *)v10 + v10[11]),
                  a4);
    if ( LsnRegion < 0 )
      goto LABEL_15;
    v18 = ClfsLsnRecordSequence(a3);
    v19 = ClfsLsnBlockOffset(a4);
    v20 = ClfsLsnContainer(a4);
    *a4 = ClfsLsnCreate(v20, v19, v18);
    goto LABEL_13;
  }
  LsnRegion = -1073741670;
LABEL_14:
  v17 = (struct _ERESOURCE *)(v8 + 200);
LABEL_15:
  if ( v9 )
    ClfsReleaseResourceLite(v17);
  if ( v7 )
    CClfsLogFcbPhysical::FreeOwnerPage((struct CClfsLogFcbPhysical *)v8, (unsigned __int8 *)v10);
  return (unsigned int)LsnRegion;
}

```

## disassembly

```asm
0x14004ab90  mov     r11, rsp
0x14004ab93  mov     [r11+18h], r8
0x14004ab97  mov     [rsp+arg_8], dl
0x14004ab9b  mov     [r11+8], rcx
0x14004ab9f  push    rbx
0x14004aba0  push    rsi
0x14004aba1  push    rdi
0x14004aba2  push    r12
0x14004aba4  push    r13
0x14004aba6  push    r14
0x14004aba8  push    r15
0x14004abaa  sub     rsp, 60h
0x14004abae  mov     r13, r9
0x14004abb1  mov     rsi, r8
0x14004abb4  mov     rbx, rcx
0x14004abb7  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14004abbe  mov     [r11+20h], rax
0x14004abc2  mov     qword ptr [r11-50h], 0
0x14004abca  mov     [rsp+98h+var_58], 0
0x14004abcf  xor     r12b, r12b
0x14004abd2  mov     [r11-57h], r12b
0x14004abd6  mov     [r9], rax
0x14004abd9  lea     r15, [rcx-260h]
0x14004abe0  lea     rcx, [r15+0C8h]; Resource
0x14004abe7  mov     dl, 1; Wait
0x14004abe9  call    cs:__imp_ExAcquireResourceSharedLite
0x14004abf0  nop     dword ptr [rax+rax+00h]
0x14004abf5  mov     dil, al
0x14004abf8  mov     [rsp+98h+var_58], al
0x14004abfc  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004ac03  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14004ac0a  nop     dword ptr [rax+rax+00h]
0x14004ac0f  mov     r14, rax
0x14004ac12  mov     [rsp+98h+var_50], rax
0x14004ac17  test    rax, rax
0x14004ac1a  jnz     short loc_14004AC2A
0x14004ac1c  mov     esi, 0C000009Ah
0x14004ac21  mov     [rsp+98h+var_54], esi
0x14004ac25  jmp     loc_14004ADD8
0x14004ac2a  mov     r12b, 1
0x14004ac2d  mov     [rsp+98h+var_57], r12b
0x14004ac32  mov     eax, [rbx-0F4h]
0x14004ac38  bt      eax, 0Ch
0x14004ac3c  jnb     short loc_14004AC5C
0x14004ac3e  mov     esi, 0C01A002Bh
0x14004ac43  mov     [rsp+98h+var_54], esi
0x14004ac47  mov     r8d, esi; int
0x14004ac4a  mov     edx, 10h; unsigned int
0x14004ac4f  mov     rcx, r15; this
0x14004ac52  call    ?SetInvalidLogTag@CClfsLogFcbCommon@@QEAAXKJ@Z; CClfsLogFcbCommon::SetInvalidLogTag(ulong,long)
0x14004ac57  jmp     loc_14004ADD8
0x14004ac5c  mov     rcx, [r15+2C0h]
0x14004ac63  xor     dil, dil
0x14004ac66  mov     [rsp+98h+var_56], dil
0x14004ac6b  movzx   r8d, [rsp+98h+arg_8]
0x14004ac74  mov     edx, r8d
0x14004ac77  shl     rdx, 4
0x14004ac7b  mov     [rsp+98h+var_48], rdx
0x14004ac80  mov     eax, [rcx+30h]
0x14004ac83  add     rdx, rax
0x14004ac86  add     rdx, rcx
0x14004ac89  mov     rcx, rsi
0x14004ac8c  call    ??P@YAEAEBT_CLS_LSN@@0@Z; operator>=(_CLS_LSN const &,_CLS_LSN const &)
0x14004ac91  test    al, al
0x14004ac93  jz      short loc_14004ACB9
0x14004ac95  add     rdx, 8; plsn2
0x14004ac99  call    ClfsLsnLess
0x14004ac9e  movzx   edi, dil
0x14004aca2  test    al, al
0x14004aca4  mov     eax, 1
0x14004aca9  cmovnz  edi, eax
0x14004acac  mov     [rsp+98h+var_56], dil
0x14004acb1  mov     r8b, [rsp+98h+arg_8]
0x14004acb9  test    dil, dil
0x14004acbc  jz      short loc_14004ACF1
0x14004acbe  lea     r8, [rbx-68h]; unsigned int
0x14004acc2  lea     rdx, [rsp+98h+arg_18]; union _CLS_LSN *
0x14004acca  mov     rcx, r15; this
0x14004accd  call    ?GetNextRegionLsn@CClfsLogFcbPhysical@@AEAA?AT_CLS_LSN@@AEBT2@K@Z; CClfsLogFcbPhysical::GetNextRegionLsn(_CLS_LSN const &,ulong)
0x14004acd2  mov     rcx, [rax]
0x14004acd5  mov     qword ptr [rsp+98h+arg_18], rcx
0x14004acdd  mov     r8d, 1000h; Size
0x14004ace3  mov     rdx, [rbx+60h]; Src
0x14004ace7  mov     rcx, r14; void *
0x14004acea  call    memmove
0x14004acef  jmp     short loc_14004AD45
0x14004acf1  mov     rax, [rbx]
0x14004acf4  mov     rax, [rax+120h]
0x14004acfb  lea     rdx, [rsp+98h+var_40]
0x14004ad00  mov     rcx, rbx
0x14004ad03  call    _guard_dispatch_icall
0x14004ad08  mov     r9, rax; union _CLS_LSN *
0x14004ad0b  lea     rax, [rsp+98h+arg_18]
0x14004ad13  mov     [rsp+98h+var_70], rax; union _CLS_LSN *
0x14004ad18  mov     [rsp+98h+var_78], r14; unsigned __int8 *
0x14004ad1d  mov     r8, rsi; union _CLS_LSN *
0x14004ad20  mov     dl, [rsp+98h+arg_8]; unsigned __int8
0x14004ad27  mov     rcx, r15; this
0x14004ad2a  call    ?FindLsnRegion@CClfsLogFcbPhysical@@QEAAJEAEBT_CLS_LSN@@0PEAEAEAT2@@Z; CClfsLogFcbPhysical::FindLsnRegion(uchar,_CLS_LSN const &,_CLS_LSN const &,uchar *,_CLS_LSN &)
0x14004ad2f  mov     esi, eax
0x14004ad31  mov     [rsp+98h+var_54], eax
0x14004ad35  test    eax, eax
0x14004ad37  js      loc_14004ADD3
0x14004ad3d  mov     rsi, [rsp+98h+plsn]
0x14004ad45  lea     rbx, [r15+0C8h]
0x14004ad4c  mov     rcx, rbx
0x14004ad4f  call    ClfsReleaseResourceLite
0x14004ad54  xor     dil, dil
0x14004ad57  mov     [rsp+98h+var_58], dil
0x14004ad5c  mov     ecx, [r14+2Ch]
0x14004ad60  add     rcx, r14
0x14004ad63  mov     eax, [r14+30h]
0x14004ad67  add     rax, [rsp+98h+var_48]
0x14004ad6c  add     rax, r14
0x14004ad6f  mov     [rsp+98h+var_68], r13; union _CLS_LSN *
0x14004ad74  mov     [rsp+98h+var_70], rcx; struct _CLFS_OWNER_ENTRY *
0x14004ad79  mov     [rsp+98h+var_78], rax; struct _CLFS_OWNER_REFERRAL *
0x14004ad7e  lea     r9, [rsp+98h+arg_18]; union _CLS_LSN *
0x14004ad86  mov     r8, rsi; union _CLS_LSN *
0x14004ad89  mov     dl, [rsp+98h+arg_8]; unsigned __int8
0x14004ad90  mov     rcx, r15; this
0x14004ad93  call    ?MapPhysicalBlockOffset@CClfsLogFcbPhysical@@AEAAJEAEBT_CLS_LSN@@0AEBU_CLFS_OWNER_REFERRAL@@QEBU_CLFS_OWNER_ENTRY@@AEAT2@@Z; CClfsLogFcbPhysical::MapPhysicalBlockOffset(uchar,_CLS_LSN const &,_CLS_LSN const &,_CLFS_OWNER_REFERRAL const &,_CLFS_OWNER_ENTRY const * const,_CLS_LSN &)
0x14004ad98  mov     esi, eax
0x14004ad9a  mov     [rsp+98h+var_54], eax
0x14004ad9e  test    eax, eax
0x14004ada0  js      short loc_14004ADDF
0x14004ada2  mov     rcx, [rsp+98h+plsn]; plsn
0x14004adaa  call    ClfsLsnRecordSequence
0x14004adaf  mov     edi, eax
0x14004adb1  mov     rcx, r13; plsn
0x14004adb4  call    ClfsLsnBlockOffset
0x14004adb9  mov     ebx, eax
0x14004adbb  mov     rcx, r13; plsn
0x14004adbe  call    ClfsLsnContainer
0x14004adc3  mov     r8d, edi; cRecord
0x14004adc6  mov     edx, ebx; offBlock
0x14004adc8  mov     ecx, eax; cidContainer
0x14004adca  call    ClfsLsnCreate
0x14004adcf  mov     [r13+0], rax
0x14004add3  mov     dil, [rsp+98h+var_58]
0x14004add8  lea     rbx, [r15+0C8h]
0x14004addf  test    dil, dil
0x14004ade2  jz      short loc_14004ADEC
0x14004ade4  mov     rcx, rbx
0x14004ade7  call    ClfsReleaseResourceLite
0x14004adec  test    r12b, r12b
0x14004adef  jz      short loc_14004ADFC
0x14004adf1  mov     rdx, r14; unsigned __int8 *
0x14004adf4  mov     rcx, r15; struct CClfsLogFcbPhysical *
0x14004adf7  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x14004adfc  mov     eax, esi
0x14004adfe  add     rsp, 60h
0x14004ae02  pop     r15
0x14004ae04  pop     r14
0x14004ae06  pop     r13
0x14004ae08  pop     r12
0x14004ae0a  pop     rdi
0x14004ae0b  pop     rsi
0x14004ae0c  pop     rbx
0x14004ae0d  retn
0x140080372  push    rbp
0x140080374  sub     rsp, 40h
0x140080378  mov     rbp, rdx
0x14008037b  cmp     byte ptr [rbp+40h], 0
0x14008037f  jz      short loc_140080398
0x140080381  mov     rcx, [rbp+0A0h]
0x140080388  add     rcx, 0FFFFFFFFFFFFFE68h
0x14008038f  call    ClfsReleaseResourceLite
0x140080394  mov     byte ptr [rbp+40h], 0
0x140080398  cmp     byte ptr [rbp+41h], 0
0x14008039c  jz      short loc_1400803BD
0x14008039e  mov     rcx, [rbp+0A0h]
0x1400803a5  add     rcx, 0FFFFFFFFFFFFFDA0h; struct CClfsLogFcbPhysical *
0x1400803ac  mov     rdx, [rbp+48h]; unsigned __int8 *
0x1400803b0  call    ?FreeOwnerPage@CClfsLogFcbPhysical@@CAXPEAV1@PEAE@Z; CClfsLogFcbPhysical::FreeOwnerPage(CClfsLogFcbPhysical *,uchar *)
0x1400803b5  mov     qword ptr [rbp+48h], 0
0x1400803bd  add     rsp, 40h
0x1400803c1  pop     rbp
0x1400803c2  retn
```
