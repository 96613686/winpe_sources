# FveEnableEAS::InitializeWithSupportLevel(DeviceEncryptionSupportLevel const &,bool,bool,bool,bool)

- ea: `0x180027a3c`
- end: `0x18002834e`
- name: `?InitializeWithSupportLevel@FveEnableEAS@@QEAAJAEBVDeviceEncryptionSupportLevel@@_N111@Z`
- size: `2322`
- prototype: `__int64 __fastcall(FveEnableEAS *this, const struct DeviceEncryptionSupportLevel *, char, bool, int, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180027800`

## callees

- `0x180001248`
- `0x180001478`
- `0x1800037a0`
- `0x18000e354`
- `0x180015624`
- `0x180017c9c`
- `0x180023828`
- `0x18002386c`
- `0x1800238e0`
- `0x180023954`
- `0x1800239c8`
- `0x180023a40`
- `0x180027a3c`
- `0x180028648`
- `0x180028f2c`
- `0x1800291e4`

## string_xrefs

- `0x180027d03`: `AdBackupCache->Initialize`

## pseudocode

```c
__int64 __fastcall FveEnableEAS::InitializeWithSupportLevel(
        FveEnableEAS *this,
        const struct DeviceEncryptionSupportLevel *a2,
        char a3,
        bool a4,
        int a5,
        bool a6)
{
  _BYTE *v10; // r12
  char v11; // cl
  int v12; // ebx
  PVOID *v13; // rcx
  __int64 v14; // rdx
  PVOID *v15; // r10
  const char *v16; // rax
  __int64 v17; // rdx
  bool v18; // r15
  unsigned int SharedNo; // eax
  const char *v20; // rax
  __int64 v21; // rdx
  FveAdBackupStatusCache *v22; // r14
  unsigned int v23; // eax
  std::_Ref_count_base *v24; // rcx
  unsigned int v25; // eax
  _QWORD *v26; // r14
  const char *v27; // rax
  __int64 v28; // rdx
  std::_Ref_count_base *v29; // rcx
  std::_Ref_count_base *v30; // rcx
  __int64 *v31; // rcx
  char *v32; // r9
  unsigned int v33; // eax
  const char *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  unsigned int v41; // eax
  char *v43; // [rsp+28h] [rbp-58h]
  int v44; // [rsp+60h] [rbp-20h] BYREF
  FveAdBackupStatusCache *v45[2]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v47; // [rsp+C0h] [rbp+40h] BYREF
  int v48; // [rsp+C8h] [rbp+48h] BYREF
  int v49; // [rsp+D0h] [rbp+50h] BYREF
  int v50; // [rsp+D8h] [rbp+58h] BYREF

  LOBYTE(v49) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
  *(_DWORD *)this = *(_DWORD *)a2;
  *((_BYTE *)this + 4) = *((_BYTE *)a2 + 4);
  v10 = (char *)this + 5;
  *((_BYTE *)this + 5) = a3;
  *((_BYTE *)this + 6) = a4;
  v11 = a5;
  *((_BYTE *)this + 7) = a5;
  if ( *((_BYTE *)this + 1) )
  {
    if ( !*((_BYTE *)this + 3) )
    {
      v12 = -2144272176;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xB9,
        (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
        (const char *)0x803100D0LL,
        (int)"_SupportLevel.SupportsDeviceEncryption",
        v43);
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v12;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_125;
      v14 = 17;
      goto LABEL_8;
    }
    v12 = FveEasUtil::CheckDEBackupRecoveryPasswordToAAD(v11, a4, (bool *)&v49);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        (unsigned int)v12);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 < 0 )
    {
      v16 = "InitializeWithSupportLevel";
      v17 = 191;
LABEL_19:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v17,
        (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
        (const char *)(unsigned int)v12,
        (int)v16,
        v43);
LABEL_124:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_125;
    }
    v18 = a6;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
      WPP_SF_DDDDD(
        v15[2],
        *((unsigned __int8 *)this + 7),
        *((unsigned __int8 *)this + 6),
        (unsigned __int8)*v10,
        *((unsigned __int8 *)this + 6),
        *((unsigned __int8 *)this + 7),
        a6,
        (unsigned __int8)v49);
    if ( *v10 )
    {
      *(_OWORD *)v45 = 0;
      SharedNo = MakeSharedNoThrow<FveAdBackupStatusCache>(v45);
      v12 = SharedNo;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, SharedNo);
      if ( v12 >= 0 )
      {
        v22 = v45[0];
        v23 = FveAdBackupStatusCache::Initialize(v45[0]);
        v12 = v23;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v23);
        if ( v12 >= 0 )
        {
          *((_QWORD *)this + 6) = v22;
          v24 = (std::_Ref_count_base *)*((_QWORD *)this + 7);
          *((FveAdBackupStatusCache **)this + 7) = v45[1];
          if ( v24 )
            std::_Ref_count_base::_Decref(v24);
          a5 = 0;
          v25 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,enum ProvisionSingleBackupStatusCache,bool &>(
                  (__int64 *)this + 1,
                  (__int64)this + 48,
                  &a5,
                  (char *)this + 5);
          v12 = v25;
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v25);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v12 >= 0 )
          {
            if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
            {
              WPP_SF_(v13[2], 23, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
              v13 = (PVOID *)WPP_GLOBAL_Control;
            }
            goto LABEL_125;
          }
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xCE,
            (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
            (const char *)(unsigned int)v12,
            (int)"MakeUniqueNoThrow2",
            v43);
          goto LABEL_9;
        }
        v20 = "AdBackupCache->Initialize";
        v21 = 199;
      }
      else
      {
        v20 = "MakeUniqueNoThrow1";
        v21 = 198;
      }
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v21,
        (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
        (const char *)(unsigned int)v12,
        (int)v20,
        v43);
      if ( v45[1] )
        std::_Ref_count_base::_Decref(v45[1]);
LABEL_9:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_125;
    }
    if ( *((_BYTE *)this + 6) )
    {
      if ( (_BYTE)v49 )
      {
        *(_OWORD *)v45 = 0;
        v12 = MakeSharedNoThrow<FveCloudStatusCache>(v45);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)v12);
        if ( v12 < 0 )
        {
          v27 = "MakeSharedNoThrow3";
          v28 = 214;
          goto LABEL_56;
        }
        v26 = (_QWORD *)((char *)this + 16);
        *((FveAdBackupStatusCache **)this + 2) = v45[0];
        v30 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
        *((FveAdBackupStatusCache **)this + 3) = v45[1];
        if ( v30 )
          std::_Ref_count_base::_Decref(v30);
        if ( !v18 )
          goto LABEL_68;
        goto LABEL_61;
      }
      if ( v18 )
      {
        v26 = (_QWORD *)((char *)this + 16);
LABEL_61:
        *(_OWORD *)v45 = 0;
        v12 = MakeSharedNoThrow<FveSkyStatusCache>(v45);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)v12);
        if ( v12 < 0 )
        {
          v27 = "MakeSharedNoThrow4";
          v28 = 221;
          goto LABEL_56;
        }
        std::shared_ptr<IBackupStatusCache>::operator=<FveSkyStatusCache,0>((_QWORD *)this + 4, (__int64 *)v45);
        if ( v45[1] )
          std::_Ref_count_base::_Decref(v45[1]);
LABEL_68:
        if ( *v26 )
        {
          v31 = (__int64 *)((char *)this + 8);
          v32 = (char *)this + 5;
          if ( *((_QWORD *)this + 4) )
          {
            v33 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,std::shared_ptr<IBackupStatusCache> &,bool &>(
                    v31,
                    (__int64)v26,
                    (__int64)this + 32,
                    v32);
            v12 = v33;
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v33);
              v13 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v12 < 0 )
            {
              v34 = "MakeSharedNoThrow5";
              v35 = 230;
LABEL_75:
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)v35,
                (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
                (const char *)(unsigned int)v12,
                (int)v34,
                v43);
              goto LABEL_9;
            }
            if ( v13 == &WPP_GLOBAL_Control )
              return (unsigned int)v12;
            if ( (*((_BYTE *)v13 + 28) & 8) == 0 )
              goto LABEL_125;
            v36 = 27;
          }
          else
          {
            a5 = 1;
            v37 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,enum ProvisionSingleBackupStatusCache,bool &>(
                    v31,
                    (__int64)v26,
                    &a5,
                    v32);
            v12 = v37;
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v37);
              v13 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v12 < 0 )
            {
              v34 = "MakeSharedNoThrow6";
              v35 = 237;
              goto LABEL_75;
            }
            if ( v13 == &WPP_GLOBAL_Control )
              return (unsigned int)v12;
            if ( (*((_BYTE *)v13 + 28) & 8) == 0 )
              goto LABEL_125;
            v36 = 29;
          }
        }
        else
        {
          if ( *((_BYTE *)this + 7) && !v18 )
          {
            v12 = -2144272145;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
                2150695151LL);
            if ( (unsigned int)dword_18003D5C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003D5C8) )
            {
              v45[0] = (FveAdBackupStatusCache *)0x1000000;
              a5 = -2144272145;
              v49 = (unsigned __int8)v49;
              v50 = 0;
              v47 = *((unsigned __int8 *)this + 7);
              v48 = *((unsigned __int8 *)this + 6);
              v44 = (unsigned __int8)*v10;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                v38,
                (__int64)&word_18003745E,
                v39,
                v40,
                (__int64)&v44,
                (__int64)&v48,
                (__int64)&v47,
                (__int64)&v50,
                (__int64)&v49,
                (__int64)&a5,
                (__int64)v45);
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
                2150695151LL);
            v16 = "FVE_E_NO_BACKUP_ACCOUNT";
            v17 = 268;
            goto LABEL_19;
          }
          a5 = 2;
          v41 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,enum ProvisionSingleBackupStatusCache,bool &>(
                  (__int64 *)this + 1,
                  (__int64)this + 32,
                  &a5,
                  (char *)this + 5);
          v12 = v41;
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v41);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v12 < 0 )
          {
            v34 = "MakeSharedNoThrow7";
            v35 = 274;
            goto LABEL_75;
          }
          if ( v13 == &WPP_GLOBAL_Control )
            return (unsigned int)v12;
          if ( (*((_BYTE *)v13 + 28) & 8) == 0 )
            goto LABEL_125;
          v36 = 33;
        }
        WPP_SF_(v13[2], v36, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
        goto LABEL_9;
      }
    }
    *(_OWORD *)v45 = 0;
    v12 = MakeSharedNoThrow<FveSkyStatusCache>(v45);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        (unsigned int)v12);
    if ( v12 >= 0 )
    {
      std::shared_ptr<IBackupStatusCache>::operator=<FveSkyStatusCache,0>((_QWORD *)this + 4, (__int64 *)v45);
      a5 = 2;
      v12 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,enum ProvisionSingleBackupStatusCache,bool &>(
              (__int64 *)this + 1,
              (__int64)this + 32,
              &a5,
              (char *)this + 5);
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          (unsigned int)v12);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 >= 0 )
      {
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
        {
          WPP_SF_(v13[2], 36, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v45[1] )
          goto LABEL_125;
        v29 = v45[1];
LABEL_123:
        std::_Ref_count_base::_Decref(v29);
        goto LABEL_124;
      }
      v27 = "MakeSharedNoThrow9";
      v28 = 286;
    }
    else
    {
      v27 = "MakeSharedNoThrow8";
      v28 = 280;
    }
LABEL_56:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v28,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)v12,
      (int)v27,
      v43);
    v29 = v45[1];
    if ( !v45[1] )
      goto LABEL_9;
    goto LABEL_123;
  }
  v12 = -2144272294;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0xB6,
    (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
    (const char *)0x8031005ALL,
    (int)"LicensedForDeviceEncryption",
    v43);
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v14 = 16;
LABEL_8:
    WPP_SF_d(v13[2], v14, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)v12);
    goto LABEL_9;
  }
LABEL_125:
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_d(v13[2], 37, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027a3c  push    rbp
0x180027a3e  push    rbx
0x180027a3f  push    rsi
0x180027a40  push    rdi
0x180027a41  push    r12
0x180027a43  push    r14
0x180027a45  push    r15
0x180027a47  mov     rbp, rsp
0x180027a4a  sub     rsp, 80h
0x180027a51  mov     sil, r9b
0x180027a54  mov     r14b, r8b
0x180027a57  mov     rbx, rdx
0x180027a5a  mov     rdi, rcx
0x180027a5d  mov     byte ptr [rbp+arg_10], 0
0x180027a61  lea     rax, WPP_GLOBAL_Control
0x180027a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a6f  cmp     rcx, rax
0x180027a72  jz      short loc_180027A8F
0x180027a74  test    byte ptr [rcx+1Ch], 20h
0x180027a78  jz      short loc_180027A8F
0x180027a7a  mov     edx, 0Fh
0x180027a7f  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027a86  mov     rcx, [rcx+10h]
0x180027a8a  call    WPP_SF_
0x180027a8f  mov     eax, [rbx]
0x180027a91  mov     [rdi], eax
0x180027a93  mov     al, [rbx+4]
0x180027a96  mov     [rdi+4], al
0x180027a99  lea     r12, [rdi+5]
0x180027a9d  mov     [r12], r14b
0x180027aa1  mov     [rdi+6], sil
0x180027aa5  mov     cl, byte ptr [rbp+arg_20]; bool
0x180027aa8  mov     [rdi+7], cl
0x180027aab  xor     r14d, r14d
0x180027aae  cmp     [rdi+1], r14b
0x180027ab2  jnz     short loc_180027B24
0x180027ab4  mov     ebx, 8031005Ah
0x180027ab9  mov     rcx, [rbp+38h]; this
0x180027abd  lea     rax, aLicensedfordev; "LicensedForDeviceEncryption"
0x180027ac4  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027ac9  mov     r9d, ebx; char *
0x180027acc  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180027ad3  mov     edx, 0B6h; void *
0x180027ad8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027add  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ae4  lea     r15, WPP_GLOBAL_Control
0x180027aeb  cmp     rcx, r15
0x180027aee  jz      loc_18002833A
0x180027af4  mov     sil, 40h ; '@'
0x180027af7  test    [rcx+1Ch], sil
0x180027afb  jz      loc_180028317
0x180027b01  lea     edx, [r14+10h]
0x180027b05  mov     r9d, ebx
0x180027b08  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027b0f  mov     rcx, [rcx+10h]
0x180027b13  call    WPP_SF_d
0x180027b18  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b1f  jmp     loc_180028317
0x180027b24  cmp     [rdi+3], r14b
0x180027b28  jnz     short loc_180027B7E
0x180027b2a  mov     ebx, 803100D0h
0x180027b2f  mov     rcx, [rbp+38h]; this
0x180027b33  lea     rax, aSupportlevelSu; "_SupportLevel.SupportsDeviceEncryption"
0x180027b3a  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027b3f  mov     r9d, ebx; char *
0x180027b42  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180027b49  mov     edx, 0B9h; void *
0x180027b4e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b5a  lea     r15, WPP_GLOBAL_Control
0x180027b61  cmp     rcx, r15
0x180027b64  jz      loc_18002833A
0x180027b6a  mov     sil, 40h ; '@'
0x180027b6d  test    [rcx+1Ch], sil
0x180027b71  jz      loc_180028317
0x180027b77  mov     edx, 11h
0x180027b7c  jmp     short loc_180027B05
0x180027b7e  lea     r8, [rbp+arg_10]; bool *
0x180027b82  mov     dl, sil; bool
0x180027b85  call    ?CheckDEBackupRecoveryPasswordToAAD@FveEasUtil@@SAJ_N0PEA_N@Z; FveEasUtil::CheckDEBackupRecoveryPasswordToAAD(bool,bool,bool *)
0x180027b8a  mov     ebx, eax
0x180027b8c  mov     sil, 40h ; '@'
0x180027b8f  mov     r10, cs:WPP_GLOBAL_Control
0x180027b96  lea     rax, WPP_GLOBAL_Control
0x180027b9d  cmp     r10, rax
0x180027ba0  jz      short loc_180027BCE
0x180027ba2  test    [r10+1Ch], sil
0x180027ba6  jz      short loc_180027BCE
0x180027ba8  mov     edx, 12h
0x180027bad  mov     r9d, ebx
0x180027bb0  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027bb7  mov     rcx, [r10+10h]
0x180027bbb  call    WPP_SF_d
0x180027bc0  mov     r10, cs:WPP_GLOBAL_Control
0x180027bc7  lea     rax, WPP_GLOBAL_Control
0x180027bce  test    ebx, ebx
0x180027bd0  jns     short loc_180027BFB
0x180027bd2  lea     rax, aInitializewith; "InitializeWithSupportLevel"
0x180027bd9  mov     edx, 0BFh; void *
0x180027bde  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180027be5  mov     r9d, ebx; char *
0x180027be8  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027bed  mov     rcx, [rbp+38h]; this
0x180027bf1  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027bf6  jmp     loc_180028309
0x180027bfb  movzx   r15d, [rbp+arg_28]
0x180027c00  cmp     r10, rax
0x180027c03  jz      short loc_180027C39
0x180027c05  test    byte ptr [r10+1Ch], 8
0x180027c0a  jz      short loc_180027C39
0x180027c0c  movzx   eax, byte ptr [rbp+arg_10]
0x180027c10  movzx   edx, byte ptr [rdi+7]
0x180027c14  movzx   r8d, byte ptr [rdi+6]
0x180027c19  movzx   r9d, byte ptr [r12]
0x180027c1e  mov     dword ptr [rsp+80h+var_48], eax
0x180027c22  mov     dword ptr [rsp+80h+var_50], r15d
0x180027c27  mov     dword ptr [rsp+80h+var_58], edx; char *
0x180027c2b  mov     [rsp+80h+var_60], r8d
0x180027c30  mov     rcx, [r10+10h]
0x180027c34  call    WPP_SF_DDDDD
0x180027c39  cmp     [r12], r14b
0x180027c3d  jz      loc_180027DD3
0x180027c43  xorps   xmm0, xmm0
0x180027c46  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180027c4b  lea     rcx, [rbp+var_18]
0x180027c4f  call    ??$MakeSharedNoThrow@VFveAdBackupStatusCache@@@@YAJAEAV?$shared_ptr@VFveAdBackupStatusCache@@@std@@@Z; MakeSharedNoThrow<FveAdBackupStatusCache>(std::shared_ptr<FveAdBackupStatusCache> &)
0x180027c54  mov     ebx, eax
0x180027c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c5d  lea     r15, WPP_GLOBAL_Control
0x180027c64  cmp     rcx, r15
0x180027c67  jz      short loc_180027C87
0x180027c69  test    [rcx+1Ch], sil
0x180027c6d  jz      short loc_180027C87
0x180027c6f  mov     edx, 14h
0x180027c74  mov     r9d, eax
0x180027c77  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027c7e  mov     rcx, [rcx+10h]
0x180027c82  call    WPP_SF_d
0x180027c87  test    ebx, ebx
0x180027c89  jns     short loc_180027CC7
0x180027c8b  lea     rax, aMakeuniquenoth_0; "MakeUniqueNoThrow1"
0x180027c92  mov     edx, 0C6h; void *
0x180027c97  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180027c9e  mov     r9d, ebx; char *
0x180027ca1  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027ca6  mov     rcx, [rbp+38h]; this
0x180027caa  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027caf  nop
0x180027cb0  mov     rcx, [rbp+var_18+8]; this
0x180027cb4  test    rcx, rcx
0x180027cb7  jz      loc_180027B18
0x180027cbd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027cc2  jmp     loc_180027B18
0x180027cc7  mov     r14, [rbp+var_18]
0x180027ccb  mov     rcx, r14; this
0x180027cce  call    ?Initialize@FveAdBackupStatusCache@@QEAAJXZ; FveAdBackupStatusCache::Initialize(void)
0x180027cd3  mov     ebx, eax
0x180027cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cdc  cmp     rcx, r15
0x180027cdf  jz      short loc_180027CFF
0x180027ce1  test    [rcx+1Ch], sil
0x180027ce5  jz      short loc_180027CFF
0x180027ce7  mov     edx, 15h
0x180027cec  mov     r9d, eax
0x180027cef  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027cf6  mov     rcx, [rcx+10h]
0x180027cfa  call    WPP_SF_d
0x180027cff  test    ebx, ebx
0x180027d01  jns     short loc_180027D11
0x180027d03  lea     rax, aAdbackupcacheI; "AdBackupCache->Initialize"
0x180027d0a  mov     edx, 0C7h
0x180027d0f  jmp     short loc_180027C97
0x180027d11  mov     [rdi+30h], r14
0x180027d15  mov     rcx, [rdi+38h]; this
0x180027d19  mov     rax, [rbp+var_18+8]
0x180027d1d  mov     [rdi+38h], rax
0x180027d21  test    rcx, rcx
0x180027d24  jz      short loc_180027D2B
0x180027d26  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027d2b  mov     [rbp+arg_20], 0
0x180027d32  lea     rcx, [rdi+8]
0x180027d36  mov     r9, r12
0x180027d39  lea     r8, [rbp+arg_20]
0x180027d3d  lea     rdx, [rdi+30h]
0x180027d41  call    ??$MakeUniqueNoThrow@VFveEasUtil@@AEAV?$shared_ptr@VIBackupStatusCache@@@std@@W4ProvisionSingleBackupStatusCache@@AEA_N@@YAJAEAV?$unique_ptr@VFveEasUtil@@U?$default_delete@VFveEasUtil@@@std@@@std@@AEAV?$shared_ptr@VIBackupStatusCache@@@1@$$QEAW4ProvisionSingleBackupStatusCache@@AEA_N@Z; MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,ProvisionSingleBackupStatusCache,bool &>(std::unique_ptr<FveEasUtil> &,std::shared_ptr<IBackupStatusCache> &,ProvisionSingleBackupStatusCache &&,bool &)
0x180027d46  mov     ebx, eax
0x180027d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d4f  cmp     rcx, r15
0x180027d52  jz      short loc_180027D79
0x180027d54  test    [rcx+1Ch], sil
0x180027d58  jz      short loc_180027D79
0x180027d5a  mov     edx, 16h
0x180027d5f  mov     r9d, eax
0x180027d62  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027d69  mov     rcx, [rcx+10h]
0x180027d6d  call    WPP_SF_d
0x180027d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d79  test    ebx, ebx
0x180027d7b  jns     short loc_180027DA7
0x180027d7d  mov     rcx, [rbp+38h]; this
0x180027d81  lea     rax, aMakeuniquenoth; "MakeUniqueNoThrow2"
0x180027d88  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027d8d  mov     r9d, ebx; char *
0x180027d90  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180027d97  mov     edx, 0CEh; void *
0x180027d9c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027da1  nop
0x180027da2  jmp     loc_180027B18
0x180027da7  cmp     rcx, r15
0x180027daa  jz      short loc_180027DCE
0x180027dac  test    byte ptr [rcx+1Ch], 8
0x180027db0  jz      short loc_180027DCE
0x180027db2  mov     edx, 17h
0x180027db7  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027dbe  mov     rcx, [rcx+10h]
0x180027dc2  call    WPP_SF_
0x180027dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180027dce  jmp     loc_180028317
0x180027dd3  cmp     [rdi+6], r14b
0x180027dd7  jz      loc_1800281FA
0x180027ddd  cmp     byte ptr [rbp+arg_10], r14b
0x180027de1  jnz     short loc_180027DF5
0x180027de3  test    r15b, r15b
0x180027de6  jz      loc_1800281FA
0x180027dec  lea     r14, [rdi+10h]
0x180027df0  jmp     loc_180027EA0
0x180027df5  xorps   xmm0, xmm0
0x180027df8  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180027dfd  lea     rcx, [rbp+var_18]
0x180027e01  call    ??$MakeSharedNoThrow@VFveCloudStatusCache@@@@YAJAEAV?$shared_ptr@VFveCloudStatusCache@@@std@@@Z; MakeSharedNoThrow<FveCloudStatusCache>(std::shared_ptr<FveCloudStatusCache> &)
0x180027e06  mov     ebx, eax
0x180027e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e0f  lea     rax, WPP_GLOBAL_Control
0x180027e16  cmp     rcx, rax
0x180027e19  jz      short loc_180027E39
0x180027e1b  test    [rcx+1Ch], sil
0x180027e1f  jz      short loc_180027E39
0x180027e21  mov     edx, 18h
0x180027e26  mov     r9d, ebx
0x180027e29  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027e30  mov     rcx, [rcx+10h]
0x180027e34  call    WPP_SF_d
0x180027e39  test    ebx, ebx
0x180027e3b  jns     short loc_180027E7A
0x180027e3d  lea     rax, aMakesharednoth_4; "MakeSharedNoThrow3"
0x180027e44  mov     edx, 0D6h; void *
0x180027e49  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180027e50  mov     r9d, ebx; char *
0x180027e53  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027e58  mov     rcx, [rbp+38h]; this
0x180027e5c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027e61  mov     rcx, [rbp+var_18+8]
0x180027e65  test    rcx, rcx
0x180027e68  jnz     loc_180028304
0x180027e6e  lea     r15, WPP_GLOBAL_Control
0x180027e75  jmp     loc_180027B18
0x180027e7a  lea     r14, [rdi+10h]
0x180027e7e  mov     rax, [rbp+var_18]
0x180027e82  mov     [r14], rax
0x180027e85  mov     rcx, [r14+8]; this
0x180027e89  mov     rax, [rbp+var_18+8]
0x180027e8d  mov     [r14+8], rax
0x180027e91  test    rcx, rcx
0x180027e94  jz      short loc_180027E9B
0x180027e96  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027e9b  test    r15b, r15b
0x180027e9e  jz      short loc_180027F14
0x180027ea0  xorps   xmm0, xmm0
0x180027ea3  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180027ea8  lea     rcx, [rbp+var_18]
0x180027eac  call    ??$MakeSharedNoThrow@VFveSkyStatusCache@@@@YAJAEAV?$shared_ptr@VFveSkyStatusCache@@@std@@@Z; MakeSharedNoThrow<FveSkyStatusCache>(std::shared_ptr<FveSkyStatusCache> &)
0x180027eb1  mov     ebx, eax
0x180027eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027eba  lea     rax, WPP_GLOBAL_Control
0x180027ec1  cmp     rcx, rax
0x180027ec4  jz      short loc_180027EE4
0x180027ec6  test    [rcx+1Ch], sil
0x180027eca  jz      short loc_180027EE4
0x180027ecc  mov     edx, 19h
0x180027ed1  mov     r9d, ebx
0x180027ed4  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180027edb  mov     rcx, [rcx+10h]
0x180027edf  call    WPP_SF_d
0x180027ee4  test    ebx, ebx
0x180027ee6  jns     short loc_180027EF9
0x180027ee8  lea     rax, aMakesharednoth_5; "MakeSharedNoThrow4"
0x180027eef  mov     edx, 0DDh
0x180027ef4  jmp     loc_180027E49
0x180027ef9  lea     rcx, [rdi+20h]
0x180027efd  lea     rdx, [rbp+var_18]
0x180027f01  call    ??$?4VFveSkyStatusCache@@$0A@@?$shared_ptr@VIBackupStatusCache@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@VFveSkyStatusCache@@@1@@Z; std::shared_ptr<IBackupStatusCache>::operator=<FveSkyStatusCache,0>(std::shared_ptr<FveSkyStatusCache> &&)
0x180027f06  mov     rcx, [rbp+var_18+8]; this
0x180027f0a  test    rcx, rcx
0x180027f0d  jz      short loc_180027F14
0x180027f0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027f14  cmp     qword ptr [r14], 0
0x180027f18  jz      loc_18002803B
0x180027f1e  lea     r8, [rdi+20h]
0x180027f22  lea     rcx, [rdi+8]
0x180027f26  mov     r9, r12
  ... truncated ...
```
