# CManagerThread::HandleDeviceEvent(unsigned __int64,void *)

- ea: `0x18000ac48`
- end: `0x18000b1c6`
- name: `?HandleDeviceEvent@CManagerThread@@QEAAX_KPEAX@Z`
- size: `1406`
- prototype: `void __fastcall(CManagerThread *this, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x180008180`

## callees

- `0x1800011b0`
- `0x180004e30`
- `0x180007300`
- `0x1800076d0`
- `0x180008640`
- `0x1800092f0`
- `0x180009660`
- `0x18000ac48`
- `0x18000b1cc`
- `0x18000b1e8`
- `0x18000b5b4`
- `0x18000b5f8`
- `0x18000bc98`
- `0x18000d910`
- `0x18000f448`
- `0x18000f6b8`
- `0x18000f8cc`
- `0x18001034c`
- `0x1800103d4`
- `0x1800105f0`
- `0x1800106a8`
- `0x180010964`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ac72`
- `KERNEL32!EnterCriticalSection` at `0x18000b07e`
- `KERNEL32!EnterCriticalSection` at `0x18000ac72`
- `KERNEL32!EnterCriticalSection` at `0x18000b07e`
- `KERNEL32!LeaveCriticalSection` at `0x18000b069`
- `KERNEL32!LeaveCriticalSection` at `0x18000b11c`
- `KERNEL32!LeaveCriticalSection` at `0x18000b1a1`
- `KERNEL32!LeaveCriticalSection` at `0x18000b069`
- `KERNEL32!LeaveCriticalSection` at `0x18000b11c`
- `KERNEL32!LeaveCriticalSection` at `0x18000b1a1`

## pseudocode

```c
void __fastcall CManagerThread::HandleDeviceEvent(CManagerThread *this, __int64 a2, unsigned int *a3)
{
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned __int64 *v7; // rax
  int v8; // edx
  int v9; // r8d
  int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rax
  CManagerThread *v13; // rbx
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned __int16 ***v23; // rbx
  _QWORD *v24; // rax
  unsigned __int64 *v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 *ValueAt; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rax
  __int64 v32; // rsi
  _QWORD *v33; // rax
  CManagerThread *v34; // [rsp+50h] [rbp+20h] BYREF
  __int64 v35; // [rsp+60h] [rbp+30h] BYREF

  v34 = this;
  SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(&v34);
  EnterCriticalSection(&stru_1800199F0);
  v6 = a3[1];
  if ( (_DWORD)v6 != 6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_id(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v5, a2, a3[1]);
    goto LABEL_86;
  }
  v7 = ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
         (unsigned __int64 **)&xmmword_180019A40 + 1,
         *((_QWORD *)a3 + 3));
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_q_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, *((_QWORD *)a3 + 3), (__int64)(a3 + 8));
LABEL_86:
    LeaveCriticalSection(&stru_1800199F0);
    v13 = v34;
    goto LABEL_87;
  }
  SmartPtr<CVolumeTrackingDescriptor>::operator=((__int64 *)&v34, (__int64 *)v7 + 1);
  v10 = 0;
  switch ( a2 )
  {
    case 32774LL:
      v11 = a3 + 8;
      v12 = *((_QWORD *)a3 + 4) - *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1;
      if ( !v12 )
        v12 = *((_QWORD *)a3 + 5) - *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4;
      if ( !v12 )
      {
        v13 = v34;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            138,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            **(_QWORD **)v34);
        v10 = 1;
        goto LABEL_27;
      }
      v14 = *v11 - *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1;
      if ( *v11 == *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1 )
        v14 = *((_QWORD *)a3 + 5) - *(_QWORD *)GUID_IO_VOLUME_LOCK_FAILED.Data4;
      if ( !v14 )
      {
        v13 = v34;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_27;
        v16 = 139;
LABEL_26:
        WPP_SF_S(v15[2], v16, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, **(_QWORD **)v13);
LABEL_27:
        *(_DWORD *)(*(_QWORD *)v13 + 16LL) = v10;
        goto LABEL_72;
      }
      v17 = *v11 - *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1;
      if ( *v11 == *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1 )
        v17 = *((_QWORD *)a3 + 5) - *(_QWORD *)GUID_IO_VOLUME_UNLOCK.Data4;
      if ( !v17 )
      {
        v13 = v34;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_27;
        v16 = 140;
        goto LABEL_26;
      }
      v18 = *v11 - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1;
      if ( *v11 == *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1 )
        v18 = *((_QWORD *)a3 + 5) - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4;
      if ( !v18 )
      {
        v13 = v34;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            141,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            **(_QWORD **)v34);
        v10 = 1;
        goto LABEL_48;
      }
      v19 = *v11 - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1;
      if ( *v11 == *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1 )
        v19 = *((_QWORD *)a3 + 5) - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT_FAILED.Data4;
      if ( !v19 )
      {
        v13 = v34;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_48;
        v21 = 142;
LABEL_47:
        WPP_SF_S(v20[2], v21, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, **(_QWORD **)v13);
LABEL_48:
        *(_DWORD *)(*(_QWORD *)v13 + 20LL) = v10;
        goto LABEL_72;
      }
      v22 = *v11 - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
      if ( *v11 == *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1 )
        v22 = *((_QWORD *)a3 + 5) - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
      if ( !v22 )
      {
        v13 = v34;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_48;
        v21 = 143;
        goto LABEL_47;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = v34;
        WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v11);
        goto LABEL_72;
      }
      goto LABEL_71;
    case 32769LL:
      v13 = v34;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          145,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          **(_QWORD **)v34);
      v10 = 1;
LABEL_61:
      *(_DWORD *)(*(_QWORD *)v13 + 24LL) = v10;
      goto LABEL_72;
    case 32770LL:
      v13 = v34;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          146,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          **(_QWORD **)v34);
      goto LABEL_61;
    case 32772LL:
      v23 = (unsigned __int16 ***)v34;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          147,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          **(_QWORD **)v34);
      v24 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
              (__int64)&qword_180019A18,
              **v23);
      if ( v24 )
        ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(
          &qword_180019A18,
          v24);
      v25 = ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
              (unsigned __int64 **)&xmmword_180019A40 + 1,
              (unsigned __int64)(*v23)[1]);
      if ( v25 )
        ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(
          (char *)&xmmword_180019A40 + 8,
          v25);
      SmartPtr<CVolumeTrackingDescriptor>::operator=(&v34, 0);
      goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
  {
LABEL_71:
    v13 = v34;
    goto LABEL_72;
  }
  v13 = v34;
  WPP_SF_Si(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    148,
    (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
    **(_QWORD **)v34,
    a2);
LABEL_72:
  LeaveCriticalSection(&stru_1800199F0);
  if ( v10 )
  {
    EnterCriticalSection(&CriticalSection);
    v26 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
            &xmmword_1800198F0,
            xmmword_1800198F0);
    while ( v26 )
    {
      SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v34);
      ValueAt = (__int64 *)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::GetValueAt(
                             v27,
                             v26);
      SmartPtr<CConfigDescriptor>::operator=((__int64 *)&v34, ValueAt);
      v31 = *(__int64 **)(*(_QWORD *)v34 + 136LL);
      if ( v31 )
      {
        if ( *v31 )
        {
          v32 = *v31;
          if ( !*(_DWORD *)(*v31 + 48) )
          {
            v33 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                    &v35,
                    *(_QWORD **)v13);
            CWorkerThread::ReportVolumeUnavailability(v32, v33);
          }
        }
      }
      v26 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(
              &xmmword_1800198F0,
              v26,
              v29,
              v30);
      SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v34);
    }
    LeaveCriticalSection(&CriticalSection);
  }
LABEL_87:
  if ( v13 )
    SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(v13);
}

```

## disassembly

```asm
0x18000ac48  mov     [rsp-18h+arg_8], rbx
0x18000ac4d  mov     [rsp-18h+arg_0], rcx
0x18000ac52  push    rbp
0x18000ac53  push    rsi
0x18000ac54  push    rdi
0x18000ac55  mov     rbp, rsp
0x18000ac58  sub     rsp, 30h
0x18000ac5c  mov     rbx, r8
0x18000ac5f  mov     rsi, rdx
0x18000ac62  lea     rcx, [rbp+arg_0]
0x18000ac66  call    ??0?$SmartPtr@VCWorkerThread@@@@QEAA@PEAVCWorkerThread@@@Z; SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(CWorkerThread *)
0x18000ac6b  lea     rcx, stru_1800199F0; lpCriticalSection
0x18000ac72  call    cs:__imp_EnterCriticalSection
0x18000ac78  mov     edx, [rbx+4]
0x18000ac7b  cmp     edx, 6
0x18000ac7e  jnz     loc_18000B171
0x18000ac84  mov     rdx, [rbx+18h]
0x18000ac88  lea     rcx, xmmword_180019A40+8
0x18000ac8f  call    ?Find@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@IEBAPEAVCNode@12@PEAX@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(void *)
0x18000ac94  test    rax, rax
0x18000ac97  jnz     short loc_18000ACD5
0x18000ac99  lea     rax, WPP_GLOBAL_Control
0x18000aca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aca7  cmp     rcx, rax
0x18000acaa  jz      loc_18000B19A
0x18000acb0  test    byte ptr [rcx+1Ch], 2
0x18000acb4  jz      loc_18000B19A
0x18000acba  lea     rax, [rbx+20h]
0x18000acbe  mov     [rsp+30h+var_10], rax
0x18000acc3  mov     r9, [rbx+18h]
0x18000acc7  mov     rcx, [rcx+10h]
0x18000accb  call    WPP_SF_q_guid_
0x18000acd0  jmp     loc_18000B19A
0x18000acd5  lea     rdx, [rax+8]
0x18000acd9  lea     rcx, [rbp+arg_0]
0x18000acdd  call    ??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CVolumeTrackingDescriptor>::operator=(SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000ace2  xor     edi, edi
0x18000ace4  cmp     rsi, 8006h
0x18000aceb  jnz     loc_18000AF2D
0x18000acf1  lea     rcx, [rbx+20h]
0x18000acf5  mov     rax, [rcx]
0x18000acf8  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data1
0x18000acff  jnz     short loc_18000AD0C
0x18000ad01  mov     rax, [rcx+8]
0x18000ad05  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data4
0x18000ad0c  test    rax, rax
0x18000ad0f  jnz     short loc_18000AD53
0x18000ad11  lea     rax, WPP_GLOBAL_Control
0x18000ad18  mov     rbx, [rbp+arg_0]
0x18000ad1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad23  cmp     rcx, rax
0x18000ad26  jz      short loc_18000AD49
0x18000ad28  test    byte ptr [rcx+1Ch], 8
0x18000ad2c  jz      short loc_18000AD49
0x18000ad2e  mov     r9, [rbx]
0x18000ad31  mov     edx, 8Ah
0x18000ad36  mov     r9, [r9]
0x18000ad39  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000ad40  mov     rcx, [rcx+10h]
0x18000ad44  call    WPP_SF_S
0x18000ad49  mov     edi, 1
0x18000ad4e  jmp     loc_18000ADE7
0x18000ad53  mov     rax, [rcx]
0x18000ad56  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data1
0x18000ad5d  jnz     short loc_18000AD6A
0x18000ad5f  mov     rax, [rcx+8]
0x18000ad63  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data4
0x18000ad6a  test    rax, rax
0x18000ad6d  jnz     short loc_18000AD93
0x18000ad6f  lea     rax, WPP_GLOBAL_Control
0x18000ad76  mov     rbx, [rbp+arg_0]
0x18000ad7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad81  cmp     rcx, rax
0x18000ad84  jz      short loc_18000ADE7
0x18000ad86  test    byte ptr [rcx+1Ch], 8
0x18000ad8a  jz      short loc_18000ADE7
0x18000ad8c  mov     edx, 8Bh
0x18000ad91  jmp     short loc_18000ADD1
0x18000ad93  mov     rax, [rcx]
0x18000ad96  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data1
0x18000ad9d  jnz     short loc_18000ADAA
0x18000ad9f  mov     rax, [rcx+8]
0x18000ada3  sub     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data4
0x18000adaa  test    rax, rax
0x18000adad  jnz     short loc_18000ADF2
0x18000adaf  lea     rax, WPP_GLOBAL_Control
0x18000adb6  mov     rbx, [rbp+arg_0]
0x18000adba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adc1  cmp     rcx, rax
0x18000adc4  jz      short loc_18000ADE7
0x18000adc6  test    byte ptr [rcx+1Ch], 8
0x18000adca  jz      short loc_18000ADE7
0x18000adcc  mov     edx, 8Ch
0x18000add1  mov     r9, [rbx]
0x18000add4  mov     r9, [r9]
0x18000add7  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000adde  mov     rcx, [rcx+10h]
0x18000ade2  call    WPP_SF_S
0x18000ade7  mov     rax, [rbx]
0x18000adea  mov     [rax+10h], edi
0x18000aded  jmp     loc_18000B062
0x18000adf2  mov     rax, [rcx]
0x18000adf5  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x18000adfc  jnz     short loc_18000AE09
0x18000adfe  mov     rax, [rcx+8]
0x18000ae02  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x18000ae09  test    rax, rax
0x18000ae0c  jnz     short loc_18000AE50
0x18000ae0e  lea     rax, WPP_GLOBAL_Control
0x18000ae15  mov     rbx, [rbp+arg_0]
0x18000ae19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae20  cmp     rcx, rax
0x18000ae23  jz      short loc_18000AE46
0x18000ae25  test    byte ptr [rcx+1Ch], 8
0x18000ae29  jz      short loc_18000AE46
0x18000ae2b  mov     r9, [rbx]
0x18000ae2e  mov     edx, 8Dh
0x18000ae33  mov     r9, [r9]
0x18000ae36  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000ae3d  mov     rcx, [rcx+10h]
0x18000ae41  call    WPP_SF_S
0x18000ae46  mov     edi, 1
0x18000ae4b  jmp     loc_18000AEE4
0x18000ae50  mov     rax, [rcx]
0x18000ae53  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data1
0x18000ae5a  jnz     short loc_18000AE67
0x18000ae5c  mov     rax, [rcx+8]
0x18000ae60  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT_FAILED.Data4
0x18000ae67  test    rax, rax
0x18000ae6a  jnz     short loc_18000AE90
0x18000ae6c  lea     rax, WPP_GLOBAL_Control
0x18000ae73  mov     rbx, [rbp+arg_0]
0x18000ae77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae7e  cmp     rcx, rax
0x18000ae81  jz      short loc_18000AEE4
0x18000ae83  test    byte ptr [rcx+1Ch], 8
0x18000ae87  jz      short loc_18000AEE4
0x18000ae89  mov     edx, 8Eh
0x18000ae8e  jmp     short loc_18000AECE
0x18000ae90  mov     rax, [rcx]
0x18000ae93  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x18000ae9a  jnz     short loc_18000AEA7
0x18000ae9c  mov     rax, [rcx+8]
0x18000aea0  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x18000aea7  test    rax, rax
0x18000aeaa  jnz     short loc_18000AEEF
0x18000aeac  lea     rax, WPP_GLOBAL_Control
0x18000aeb3  mov     rbx, [rbp+arg_0]
0x18000aeb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aebe  cmp     rcx, rax
0x18000aec1  jz      short loc_18000AEE4
0x18000aec3  test    byte ptr [rcx+1Ch], 8
0x18000aec7  jz      short loc_18000AEE4
0x18000aec9  mov     edx, 8Fh
0x18000aece  mov     r9, [rbx]
0x18000aed1  mov     r9, [r9]
0x18000aed4  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000aedb  mov     rcx, [rcx+10h]
0x18000aedf  call    WPP_SF_S
0x18000aee4  mov     rax, [rbx]
0x18000aee7  mov     [rax+14h], edi
0x18000aeea  jmp     loc_18000B062
0x18000aeef  lea     rax, WPP_GLOBAL_Control
0x18000aef6  mov     rdx, cs:WPP_GLOBAL_Control
0x18000aefd  cmp     rdx, rax
0x18000af00  jz      loc_18000B05E
0x18000af06  test    byte ptr [rdx+1Ch], 10h
0x18000af0a  jz      loc_18000B05E
0x18000af10  mov     rbx, [rbp+arg_0]
0x18000af14  mov     r9, [rbx]
0x18000af17  mov     [rsp+30h+var_10], rcx; __int64
0x18000af1c  mov     r9, [r9]
0x18000af1f  mov     rcx, [rdx+10h]; LoggerHandle
0x18000af23  call    WPP_SF_S_guid_
0x18000af28  jmp     loc_18000B062
0x18000af2d  cmp     rsi, 8001h
0x18000af34  jnz     short loc_18000AF75
0x18000af36  lea     rax, WPP_GLOBAL_Control
0x18000af3d  mov     rbx, [rbp+arg_0]
0x18000af41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af48  cmp     rcx, rax
0x18000af4b  jz      short loc_18000AF6E
0x18000af4d  test    byte ptr [rcx+1Ch], 8
0x18000af51  jz      short loc_18000AF6E
0x18000af53  mov     r9, [rbx]
0x18000af56  mov     edx, 91h
0x18000af5b  mov     r9, [r9]
0x18000af5e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000af65  mov     rcx, [rcx+10h]
0x18000af69  call    WPP_SF_S
0x18000af6e  mov     edi, 1
0x18000af73  jmp     short loc_18000AFB6
0x18000af75  cmp     rsi, 8002h
0x18000af7c  jnz     short loc_18000AFC1
0x18000af7e  lea     rax, WPP_GLOBAL_Control
0x18000af85  mov     rbx, [rbp+arg_0]
0x18000af89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af90  cmp     rcx, rax
0x18000af93  jz      short loc_18000AFB6
0x18000af95  test    byte ptr [rcx+1Ch], 8
0x18000af99  jz      short loc_18000AFB6
0x18000af9b  mov     r9, [rbx]
0x18000af9e  mov     edx, 92h
0x18000afa3  mov     r9, [r9]
0x18000afa6  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000afad  mov     rcx, [rcx+10h]
0x18000afb1  call    WPP_SF_S
0x18000afb6  mov     rax, [rbx]
0x18000afb9  mov     [rax+18h], edi
0x18000afbc  jmp     loc_18000B062
0x18000afc1  cmp     rsi, 8004h
0x18000afc8  jnz     loc_18000B127
0x18000afce  lea     rax, WPP_GLOBAL_Control
0x18000afd5  mov     rbx, [rbp+arg_0]
0x18000afd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afe0  cmp     rcx, rax
0x18000afe3  jz      short loc_18000B006
0x18000afe5  test    byte ptr [rcx+1Ch], 8
0x18000afe9  jz      short loc_18000B006
0x18000afeb  mov     r9, [rbx]
0x18000afee  mov     edx, 93h
0x18000aff3  mov     r9, [r9]
0x18000aff6  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000affd  mov     rcx, [rcx+10h]
0x18000b001  call    WPP_SF_S
0x18000b006  mov     rdx, [rbx]
0x18000b009  mov     rdx, [rdx]
0x18000b00c  lea     rcx, qword_180019A18
0x18000b013  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(ushort const *)
0x18000b018  test    rax, rax
0x18000b01b  jz      short loc_18000B02C
0x18000b01d  mov     rdx, rax
0x18000b020  lea     rcx, qword_180019A18
0x18000b027  call    ?RBDelete@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAA_NPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000b02c  mov     rdx, [rbx]
0x18000b02f  mov     rdx, [rdx+8]
0x18000b033  lea     rcx, xmmword_180019A40+8
0x18000b03a  call    ?Find@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@IEBAPEAVCNode@12@PEAX@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(void *)
0x18000b03f  test    rax, rax
0x18000b042  jz      short loc_18000B053
0x18000b044  mov     rdx, rax
0x18000b047  lea     rcx, xmmword_180019A40+8
0x18000b04e  call    ?RBDelete@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAA_NPEAVCNode@12@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RBDelete(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x18000b053  xor     edx, edx
0x18000b055  lea     rcx, [rbp+arg_0]
0x18000b059  call    ??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@PEAVCVolumeTrackingDescriptor@@@Z; SmartPtr<CVolumeTrackingDescriptor>::operator=(CVolumeTrackingDescriptor *)
0x18000b05e  mov     rbx, [rbp+arg_0]
0x18000b062  lea     rcx, stru_1800199F0; lpCriticalSection
0x18000b069  call    cs:__imp_LeaveCriticalSection
0x18000b06f  test    edi, edi
0x18000b071  jz      loc_18000B1AB
0x18000b077  lea     rcx, CriticalSection; lpCriticalSection
0x18000b07e  call    cs:__imp_EnterCriticalSection
0x18000b084  mov     rdx, qword ptr cs:xmmword_1800198F0
0x18000b08b  lea     rcx, xmmword_1800198F0
0x18000b092  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b097  mov     rdi, rax
0x18000b09a  test    rax, rax
0x18000b09d  jz      short loc_18000B115
0x18000b09f  lea     rcx, [rbp+arg_0]
0x18000b0a3  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000b0a8  mov     rdx, rdi
0x18000b0ab  call    ?GetValueAt@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@QEAAAEAV?$SmartPtr@VCConfigDescriptor@@@@PEAU__POSITION@@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::GetValueAt(__POSITION *)
0x18000b0b0  mov     rdx, rax
0x18000b0b3  lea     rcx, [rbp+arg_0]
0x18000b0b7  call    ??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@AEBV0@@Z; SmartPtr<CConfigDescriptor>::operator=(SmartPtr<CConfigDescriptor> const &)
0x18000b0bc  mov     rcx, [rbp+arg_0]
0x18000b0c0  mov     rdx, [rcx]
0x18000b0c3  mov     rax, [rdx+88h]
0x18000b0ca  test    rax, rax
0x18000b0cd  jz      short loc_18000B0F5
0x18000b0cf  cmp     qword ptr [rax], 0
0x18000b0d3  jz      short loc_18000B0F5
0x18000b0d5  mov     rsi, [rax]
0x18000b0d8  cmp     dword ptr [rsi+30h], 0
0x18000b0dc  jnz     short loc_18000B0F5
0x18000b0de  mov     rdx, [rbx]
0x18000b0e1  lea     rcx, [rbp+arg_10]
0x18000b0e5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000b0ea  mov     rdx, rax
0x18000b0ed  mov     rcx, rsi
0x18000b0f0  call    ?ReportVolumeUnavailability@CWorkerThread@@QEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CWorkerThread::ReportVolumeUnavailability(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000b0f5  mov     rdx, rdi
0x18000b0f8  lea     rcx, xmmword_1800198F0
0x18000b0ff  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b104  mov     rdi, rax
0x18000b107  lea     rcx, [rbp+arg_0]
0x18000b10b  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000b110  test    rdi, rdi
0x18000b113  jnz     short loc_18000B09F
0x18000b115  lea     rcx, CriticalSection; lpCriticalSection
0x18000b11c  call    cs:__imp_LeaveCriticalSection
0x18000b122  jmp     loc_18000B1AB
0x18000b127  lea     rax, WPP_GLOBAL_Control
0x18000b12e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b135  cmp     rcx, rax
0x18000b138  jz      loc_18000B05E
0x18000b13e  test    byte ptr [rcx+1Ch], 10h
0x18000b142  jz      loc_18000B05E
0x18000b148  mov     rbx, [rbp+arg_0]
  ... truncated ...
```
