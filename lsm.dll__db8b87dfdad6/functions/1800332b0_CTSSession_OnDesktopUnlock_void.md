# CTSSession::OnDesktopUnlock(void)

- ea: `0x1800332b0`
- end: `0x180033920`
- name: `?OnDesktopUnlock@CTSSession@@UEAAJXZ`
- size: `1648`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b80`
- `0x1800074c0`
- `0x180008f04`
- `0x1800092a4`
- `0x180009420`
- `0x180009810`
- `0x180009a68`
- `0x18000aad4`
- `0x180010fb0`
- `0x1800186a0`
- `0x18001ce00`
- `0x18001f27c`
- `0x180025600`
- `0x180025890`
- `0x180028bbc`
- `0x18002bf6c`
- `0x18002f624`
- `0x1800332b0`
- `0x180034644`
- `0x18004b460`
- `0x18006caec`
- `0x18006f140`
- `0x18006f3a4`
- `0x180097010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800333bb`
- `ntdll!NtQuerySystemTime` at `0x1800333bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033500`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033528`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033500`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180033528`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800333cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800333cb`

## string_xrefs

- `0x18003354b`: `ptrTerminal->LoggedOnCompleted() took this long`
- `0x1800335a7`: `ptrTerminal->LoggedOnCompleted() called while not connected`
- `0x180033613`: `ptrTerminal->LoggedOnCompleted() failed`
- `0x1800336ca`: `Failed to dispatch OnLogonCompleted event`
- `0x180033768`: `unable to write LastRemoteLogonTime to registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTSSession::OnDesktopUnlock(CTSSession *this)
{
  int v2; // eax
  int v3; // ebx
  unsigned int *v4; // rsi
  int v5; // eax
  unsigned int v6; // r12d
  unsigned int v7; // esi
  const unsigned __int16 *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int IsLocalGlassTerminal; // r15d
  ULONGLONG TickCount64; // r14
  ULONGLONG v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  CTSSession *v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // r9
  const char *v28; // [rsp+70h] [rbp-90h] BYREF
  ULONGLONG v29; // [rsp+78h] [rbp-88h] BYREF
  const char *v30; // [rsp+80h] [rbp-80h] BYREF
  const char *v31; // [rsp+88h] [rbp-78h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+90h] [rbp-70h] BYREF
  LONGLONG v33; // [rsp+98h] [rbp-68h] BYREF
  LONGLONG v34; // [rsp+A0h] [rbp-60h] BYREF
  union _LARGE_INTEGER v35; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v38[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v39; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v40[4]; // [rsp+E0h] [rbp-20h]
  __int128 v41; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v42; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v43[24]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v44[192]; // [rsp+120h] [rbp+20h] BYREF

  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v38, (struct _RTL_RESOURCE *)((char *)this + 1856));
  v39 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v43, (struct _GUID *)((char *)this + 3208));
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v44, "CTSSession::OnDesktopUnlock", this);
  *(_QWORD *)&v39 = 0;
  v2 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)&v39);
  v3 = v2;
  if ( v2 < 0 )
  {
    _DbgPrintMessage(8, "InitializeNotifyInfo failed: 0x%x in %s", v2, "CTSSession::OnDesktopUnlock");
    goto LABEL_34;
  }
  v4 = (unsigned int *)((char *)this + 3256);
  v5 = CTSSession::CState::CheckState((char *)this + 3256, 14);
  v3 = v5;
  if ( v5 < 0 )
  {
    CTSSession::LogFailedTransition(this, 14, (unsigned int)v5);
    goto LABEL_34;
  }
  v6 = *v4;
  CTSSession::CState::ChangeState((char *)this + 3256, 14, (char *)&v41 + 8, &v42, 2022);
  v7 = *v4;
  SystemTime.QuadPart = 0;
  NtQuerySystemTime(&SystemTime);
  GetSystemTime((LPSYSTEMTIME)this + 128);
  if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
  {
    v28 = "Unlock";
    v8 = (const unsigned __int16 *)*((_QWORD *)this + 247);
    v33 = (SystemTime.QuadPart - (__int64)v8) / 10000000;
    v34 = SystemTime.QuadPart - (_QWORD)v8;
    v35 = SystemTime;
    v36 = (__int64)this + 3208;
    v37 = (__int64)this + 2048;
    v31 = (char *)this + 2016;
    v30 = (const char *)v8;
    v29 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      SystemTime.QuadPart - (_QWORD)v8,
      (int)byte_1800C4E11,
      SystemTime.QuadPart,
      (__int64)v8,
      (__int64)&v29,
      (__int64)&v30,
      (__int64 *)&v31,
      &v37,
      &v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (const unsigned __int16 **)&v28);
  }
  CAutoLock::Unlock((CAutoLock *)v38);
  if ( v7 != 5 || !*((_DWORD *)this + 527) )
  {
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      LODWORD(v28) = v7;
      v29 = (ULONGLONG)"Unlocked called, but diff new state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned __int8 *)byte_1800C4C91,
        v10,
        v11,
        (const unsigned __int16 **)&v29,
        (__int64)&v28);
    }
    goto LABEL_29;
  }
  IsLocalGlassTerminal = CGlassTerminal::IsLocalGlassTerminal(*((struct ITerminal **)this + 227));
  TickCount64 = GetTickCount64();
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 227) + 72LL))(
         *((_QWORD *)this + 227),
         *((_QWORD *)this + 741));
  v14 = GetTickCount64();
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v29 = v14 - TickCount64;
    LODWORD(v28) = *((_DWORD *)this + 436);
    v30 = "ptrTerminal->LoggedOnCompleted() took this long";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)dword_1800DA020,
      (unsigned __int8 *)byte_1800C4DBB,
      v15,
      v16,
      (const unsigned __int16 **)&v30,
      (__int64)&v28,
      (__int64)&v29);
  }
  if ( v3 == -2147022646 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v29 = (ULONGLONG)"OnDesktopUnlock";
      LODWORD(v28) = -2147022646;
      v30 = "ptrTerminal->LoggedOnCompleted() called while not connected";
      v31 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        2147944650LL,
        (int)word_1800C4D7A,
        v15,
        v16,
        (const unsigned __int16 **)&v31,
        (const unsigned __int16 **)&v30,
        (__int64)&v28,
        (const unsigned __int16 **)&v29);
    }
    goto LABEL_34;
  }
  if ( v3 < 0 && (unsigned int)dword_1800DA020 > 3 )
  {
    v29 = (ULONGLONG)"OnDesktopUnlock";
    LODWORD(v28) = v3;
    v30 = "ptrTerminal->LoggedOnCompleted() failed";
    v31 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      2147944650LL,
      (int)byte_1800C4D39,
      v15,
      v16,
      (const unsigned __int16 **)&v31,
      (const unsigned __int16 **)&v30,
      (__int64)&v28,
      (const unsigned __int16 **)&v29);
  }
  *((_DWORD *)this + 527) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LogonCompletedNotif>::GetImpl'::`2'::impl) )
  {
    if ( v3 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228)
                                                                                        + 1832LL)
                                                                            + 192LL))(
              *((_QWORD *)this + 228) + 1832LL,
              &v39,
              5,
              v6);
      if ( v18 < 0 )
      {
        v17 = (CTSSession *)(unsigned int)dword_1800DA020;
        if ( (unsigned int)dword_1800DA020 > 3 )
        {
          v29 = (ULONGLONG)"OnDesktopUnlock";
          LODWORD(v28) = v18;
          v30 = "Failed to dispatch OnLogonCompleted event";
          v31 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)dword_1800DA020,
            (int)&unk_1800C4CF8,
            v19,
            v20,
            (const unsigned __int16 **)&v31,
            (const unsigned __int16 **)&v30,
            (__int64)&v28,
            (const unsigned __int16 **)&v29);
        }
      }
      goto LABEL_23;
    }
  }
  else if ( v3 >= 0 )
  {
LABEL_23:
    if ( !IsLocalGlassTerminal )
    {
      v21 = CTSSession::WriteLastRemoteLogonTime(v17);
      if ( v21 < 0 && (unsigned int)dword_1800DA020 > 3 )
      {
        v29 = (ULONGLONG)"OnDesktopUnlock";
        LODWORD(v28) = v21;
        v30 = "unable to write LastRemoteLogonTime to registry";
        v31 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)dword_1800DA020,
          (int)word_1800C4CC2,
          v22,
          v23,
          (const unsigned __int16 **)&v31,
          (const unsigned __int16 **)&v30,
          (__int64)&v28,
          (const unsigned __int16 **)&v29);
      }
    }
  }
LABEL_29:
  v24 = CTSSession::SetTimeZone(this);
  if ( v24 < 0 && (unsigned int)dword_1800DA020 > 3 )
  {
    v29 = (ULONGLONG)"OnDesktopUnlock";
    LODWORD(v28) = v24;
    v30 = "Failed to set timezone";
    v31 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_1800DA020,
      (int)&unk_1800C4C50,
      v25,
      v26,
      (const unsigned __int16 **)&v31,
      (const unsigned __int16 **)&v30,
      (__int64)&v28,
      (const unsigned __int16 **)&v29);
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                      + 80LL))(
         *((_QWORD *)this + 228) + 1832LL,
         &v39,
         v7,
         v6);
  CTSSession::PublishWNFNotification(this, 8u, v40[2]);
LABEL_34:
  if ( (_QWORD)v39 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v39 + 16LL))(v39);
    *(_QWORD *)&v39 = 0;
  }
  if ( (_QWORD)v41 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v41 + 16LL))(v41);
    *(_QWORD *)&v41 = 0;
  }
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v44);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v43);
  CAutoLock::Unlock((CAutoLock *)v38);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800332b0  mov     [rsp-8+arg_8], rbx
0x1800332b5  mov     [rsp-8+arg_10], rsi
0x1800332ba  push    rbp
0x1800332bb  push    rdi
0x1800332bc  push    r12
0x1800332be  push    r14
0x1800332c0  push    r15
0x1800332c2  lea     rbp, [rsp-0F0h]
0x1800332ca  sub     rsp, 1F0h
0x1800332d1  mov     rax, cs:__security_cookie
0x1800332d8  xor     rax, rsp
0x1800332db  mov     [rbp+110h+var_30], rax
0x1800332e2  mov     rdi, rcx
0x1800332e5  lea     rdx, [rcx+740h]; struct CResource *
0x1800332ec  lea     rcx, [rbp+110h+var_150]; this
0x1800332f0  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800332f5  nop
0x1800332f6  xorps   xmm0, xmm0
0x1800332f9  xor     eax, eax
0x1800332fb  movups  [rbp+110h+var_140], xmm0
0x1800332ff  movups  xmmword ptr [rbp+110h+var_130], xmm0
0x180033303  movups  [rbp+110h+var_120], xmm0
0x180033307  mov     [rbp+110h+var_110], rax
0x18003330b  lea     r14, [rdi+0C88h]
0x180033312  mov     rdx, r14; struct _GUID *
0x180033315  lea     rcx, [rbp+110h+var_108]; this
0x180033319  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18003331e  nop
0x18003331f  mov     r8, rdi; struct ITSSession *
0x180033322  lea     rdx, aCtssessionOnde_0; "CTSSession::OnDesktopUnlock"
0x180033329  lea     rcx, [rbp+110h+var_F0]; this
0x18003332d  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x180033332  nop
0x180033333  mov     qword ptr [rbp+110h+var_140], 0
0x18003333b  lea     rdx, [rbp+110h+var_140]; struct __PTSSessInfo *
0x18003333f  mov     rcx, rdi; this
0x180033342  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x180033347  mov     ebx, eax
0x180033349  test    eax, eax
0x18003334b  jns     short loc_18003336D
0x18003334d  lea     r9, aCtssessionOnde_0; "CTSSession::OnDesktopUnlock"
0x180033354  mov     r8d, eax
0x180033357  lea     rdx, aInitializenoti_0; "InitializeNotifyInfo failed: 0x%x in %s"
0x18003335e  mov     ecx, 8; int
0x180033363  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033368  jmp     loc_18003389B
0x18003336d  lea     rsi, [rdi+0CB8h]
0x180033374  mov     r15d, 0Eh
0x18003337a  mov     edx, r15d
0x18003337d  mov     rcx, rsi
0x180033380  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x180033385  mov     ebx, eax
0x180033387  mov     edx, r15d
0x18003338a  test    eax, eax
0x18003338c  js      loc_180033890
0x180033392  mov     r12d, [rsi]
0x180033395  mov     dword ptr [rsp+210h+var_1F0], 7E6h
0x18003339d  lea     r9, [rbp+110h+var_110]
0x1800333a1  lea     r8, [rbp+110h+var_120+8]
0x1800333a5  mov     rcx, rsi
0x1800333a8  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x1800333ad  mov     esi, [rsi]
0x1800333af  mov     qword ptr [rbp+110h+SystemTime], 0
0x1800333b7  lea     rcx, [rbp+110h+SystemTime]; SystemTime
0x1800333bb  call    cs:__imp_NtQuerySystemTime
0x1800333c1  lea     rbx, [rdi+800h]
0x1800333c8  mov     rcx, rbx; lpSystemTime
0x1800333cb  call    cs:__imp_GetSystemTime
0x1800333d1  mov     eax, cs:dword_1800DA020
0x1800333d7  cmp     eax, 5
0x1800333da  jbe     loc_1800334C4
0x1800333e0  mov     rdx, 400000000000h
0x1800333ea  lea     rcx, dword_1800DA020
0x1800333f1  call    _tlgKeywordOn
0x1800333f6  test    al, al
0x1800333f8  jz      loc_1800334C4
0x1800333fe  lea     rax, aUnlock; "Unlock"
0x180033405  mov     [rsp+210h+var_1A0], rax
0x18003340a  mov     r9, [rdi+7B8h]
0x180033411  mov     r8, qword ptr [rbp+110h+SystemTime]
0x180033415  mov     rcx, r8
0x180033418  sub     rcx, r9
0x18003341b  mov     rax, 0D6BF94D5E57A42BDh
0x180033425  imul    rcx
0x180033428  add     rdx, rcx
0x18003342b  sar     rdx, 17h
0x18003342f  mov     rax, rdx
0x180033432  shr     rax, 3Fh
0x180033436  add     rdx, rax
0x180033439  mov     [rbp+110h+var_178], rdx
0x18003343d  mov     [rbp+110h+var_170], rcx
0x180033441  mov     [rbp+110h+var_168], r8
0x180033445  mov     [rbp+110h+var_160], r14
0x180033449  mov     [rbp+110h+var_158], rbx
0x18003344d  lea     rax, [rdi+7E0h]
0x180033454  mov     [rbp+110h+var_188], rax
0x180033458  mov     [rbp+110h+var_190], r9
0x18003345c  mov     [rsp+210h+var_198], 2000000h
0x180033465  lea     rax, [rsp+210h+var_1A0]
0x18003346a  mov     [rsp+210h+var_1B0], rax
0x18003346f  lea     rax, [rbp+110h+var_178]
0x180033473  mov     [rsp+210h+var_1B8], rax
0x180033478  lea     rax, [rbp+110h+var_170]
0x18003347c  mov     [rsp+210h+var_1C0], rax
0x180033481  lea     rax, [rbp+110h+var_168]
0x180033485  mov     [rsp+210h+var_1C8], rax
0x18003348a  lea     rax, [rbp+110h+var_160]
0x18003348e  mov     [rsp+210h+var_1D0], rax
0x180033493  lea     rax, [rbp+110h+var_158]
0x180033497  mov     [rsp+210h+var_1D8], rax
0x18003349c  lea     rax, [rbp+110h+var_188]
0x1800334a0  mov     [rsp+210h+var_1E0], rax
0x1800334a5  lea     rax, [rbp+110h+var_190]
0x1800334a9  mov     [rsp+210h+var_1E8], rax
0x1800334ae  lea     rax, [rsp+210h+var_198]
0x1800334b3  mov     [rsp+210h+var_1F0], rax
0x1800334b8  lea     rdx, byte_1800C4E11
0x1800334bf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U1@U1@U1@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@44333AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800334c4  lea     rcx, [rbp+110h+var_150]; this
0x1800334c8  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800334cd  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x1800334d4  lea     r14, aHresultFailedB; "HResult failed but continue"
0x1800334db  cmp     esi, 5
0x1800334de  jnz     loc_1800337AB
0x1800334e4  cmp     dword ptr [rdi+83Ch], 0
0x1800334eb  jz      loc_1800337AB
0x1800334f1  mov     rcx, [rdi+718h]; struct ITerminal *
0x1800334f8  call    ?IsLocalGlassTerminal@CGlassTerminal@@SAHPEAUITerminal@@@Z; CGlassTerminal::IsLocalGlassTerminal(ITerminal *)
0x1800334fd  mov     r15d, eax
0x180033500  call    cs:__imp_GetTickCount64
0x180033506  mov     r14, rax
0x180033509  mov     r8, [rdi+718h]
0x180033510  mov     rcx, [r8]
0x180033513  mov     rax, [rcx+48h]
0x180033517  mov     rdx, [rdi+1728h]
0x18003351e  mov     rcx, r8
0x180033521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033526  mov     ebx, eax
0x180033528  call    cs:__imp_GetTickCount64
0x18003352e  mov     ecx, cs:dword_1800DA020
0x180033534  cmp     ecx, 4
0x180033537  jbe     short loc_18003357F
0x180033539  sub     rax, r14
0x18003353c  mov     [rsp+210h+var_198], rax
0x180033541  mov     eax, [rdi+6D0h]
0x180033547  mov     dword ptr [rsp+210h+var_1A0], eax
0x18003354b  lea     rax, aPtrterminalLog_1; "ptrTerminal->LoggedOnCompleted() took t"...
0x180033552  mov     [rbp+110h+var_190], rax
0x180033556  lea     rax, [rsp+210h+var_198]
0x18003355b  mov     [rsp+210h+var_1E0], rax
0x180033560  lea     rax, [rsp+210h+var_1A0]
0x180033565  mov     [rsp+210h+var_1E8], rax
0x18003356a  lea     rax, [rbp+110h+var_190]
0x18003356e  mov     [rsp+210h+var_1F0], rax
0x180033573  lea     rdx, byte_1800C4DBB
0x18003357a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003357f  mov     ecx, 800708CAh
0x180033584  cmp     ebx, ecx
0x180033586  jnz     short loc_1800335F4
0x180033588  mov     eax, cs:dword_1800DA020
0x18003358e  cmp     eax, 3
0x180033591  jbe     loc_18003389B
0x180033597  lea     rax, aOndesktopunloc_0; "OnDesktopUnlock"
0x18003359e  mov     [rsp+210h+var_198], rax
0x1800335a3  mov     dword ptr [rsp+210h+var_1A0], ecx
0x1800335a7  lea     rax, aPtrterminalLog_2; "ptrTerminal->LoggedOnCompleted() called"...
0x1800335ae  mov     [rbp+110h+var_190], rax
0x1800335b2  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800335b9  mov     [rbp+110h+var_188], rax
0x1800335bd  lea     rax, [rsp+210h+var_198]
0x1800335c2  mov     [rsp+210h+var_1D8], rax
0x1800335c7  lea     rax, [rsp+210h+var_1A0]
0x1800335cc  mov     [rsp+210h+var_1E0], rax
0x1800335d1  lea     rax, [rbp+110h+var_190]
0x1800335d5  mov     [rsp+210h+var_1E8], rax
0x1800335da  lea     rax, [rbp+110h+var_188]
0x1800335de  mov     [rsp+210h+var_1F0], rax
0x1800335e3  lea     rdx, word_1800C4D7A
0x1800335ea  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800335ef  jmp     loc_18003389B
0x1800335f4  test    ebx, ebx
0x1800335f6  jns     short loc_18003365B
0x1800335f8  mov     eax, cs:dword_1800DA020
0x1800335fe  cmp     eax, 3
0x180033601  jbe     short loc_18003365B
0x180033603  lea     rax, aOndesktopunloc_0; "OnDesktopUnlock"
0x18003360a  mov     [rsp+210h+var_198], rax
0x18003360f  mov     dword ptr [rsp+210h+var_1A0], ebx
0x180033613  lea     rax, aPtrterminalLog_0; "ptrTerminal->LoggedOnCompleted() failed"
0x18003361a  mov     [rbp+110h+var_190], rax
0x18003361e  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180033625  mov     [rbp+110h+var_188], rax
0x180033629  lea     rax, [rsp+210h+var_198]
0x18003362e  mov     [rsp+210h+var_1D8], rax
0x180033633  lea     rax, [rsp+210h+var_1A0]
0x180033638  mov     [rsp+210h+var_1E0], rax
0x18003363d  lea     rax, [rbp+110h+var_190]
0x180033641  mov     [rsp+210h+var_1E8], rax
0x180033646  lea     rax, [rbp+110h+var_188]
0x18003364a  mov     [rsp+210h+var_1F0], rax
0x18003364f  lea     rdx, byte_1800C4D39
0x180033656  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003365b  mov     dword ptr [rdi+83Ch], 0
0x180033665  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif> `wil::Feature<__WilFeatureTraits_Feature_LogonCompletedNotif>::GetImpl(void)'::`2'::impl
0x18003366c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif>::__private_IsEnabled(void)
0x180033671  test    al, al
0x180033673  jz      loc_180033714
0x180033679  test    ebx, ebx
0x18003367b  js      loc_1800337E8
0x180033681  mov     rcx, [rdi+720h]
0x180033688  add     rcx, 728h
0x18003368f  mov     rax, [rcx]
0x180033692  mov     r9d, r12d
0x180033695  mov     r8d, 5
0x18003369b  lea     rdx, [rbp+110h+var_140]
0x18003369f  mov     rax, [rax+0C0h]
0x1800336a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336ab  test    eax, eax
0x1800336ad  jns     short loc_18003372C
0x1800336af  mov     ecx, cs:dword_1800DA020
0x1800336b5  cmp     ecx, 3
0x1800336b8  jbe     short loc_18003372C
0x1800336ba  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x1800336c1  mov     [rsp+210h+var_198], rbx
0x1800336c6  mov     dword ptr [rsp+210h+var_1A0], eax
0x1800336ca  lea     rax, aFailedToDispat; "Failed to dispatch OnLogonCompleted eve"...
0x1800336d1  mov     [rbp+110h+var_190], rax
0x1800336d5  lea     r14, aHresultFailedB; "HResult failed but continue"
0x1800336dc  mov     [rbp+110h+var_188], r14
0x1800336e0  lea     rax, [rsp+210h+var_198]
0x1800336e5  mov     [rsp+210h+var_1D8], rax
0x1800336ea  lea     rax, [rsp+210h+var_1A0]
0x1800336ef  mov     [rsp+210h+var_1E0], rax
0x1800336f4  lea     rax, [rbp+110h+var_190]
0x1800336f8  mov     [rsp+210h+var_1E8], rax
0x1800336fd  lea     rax, [rbp+110h+var_188]
0x180033701  mov     [rsp+210h+var_1F0], rax
0x180033706  lea     rdx, unk_1800C4CF8
0x18003370d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033712  jmp     short loc_18003373A
0x180033714  lea     r14, aHresultFailedB; "HResult failed but continue"
0x18003371b  test    ebx, ebx
0x18003371d  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x180033724  js      loc_1800337F6
0x18003372a  jmp     short loc_18003373A
0x18003372c  lea     r14, aHresultFailedB; "HResult failed but continue"
0x180033733  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x18003373a  test    r15d, r15d
0x18003373d  jnz     loc_1800337F6
0x180033743  call    ?WriteLastRemoteLogonTime@CTSSession@@AEAAJXZ; CTSSession::WriteLastRemoteLogonTime(void)
0x180033748  test    eax, eax
0x18003374a  jns     loc_1800337F6
0x180033750  mov     ecx, cs:dword_1800DA020
0x180033756  cmp     ecx, 3
0x180033759  jbe     loc_1800337F6
0x18003375f  mov     [rsp+210h+var_198], rbx
0x180033764  mov     dword ptr [rsp+210h+var_1A0], eax
0x180033768  lea     rax, aUnableToWriteL; "unable to write LastRemoteLogonTime to "...
0x18003376f  mov     [rbp+110h+var_190], rax
0x180033773  mov     [rbp+110h+var_188], r14
0x180033777  lea     rax, [rsp+210h+var_198]
0x18003377c  mov     [rsp+210h+var_1D8], rax
0x180033781  lea     rax, [rsp+210h+var_1A0]
0x180033786  mov     [rsp+210h+var_1E0], rax
0x18003378b  lea     rax, [rbp+110h+var_190]
0x18003378f  mov     [rsp+210h+var_1E8], rax
0x180033794  lea     rax, [rbp+110h+var_188]
0x180033798  mov     [rsp+210h+var_1F0], rax
0x18003379d  lea     rdx, word_1800C4CC2
0x1800337a4  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800337a9  jmp     short loc_1800337F6
0x1800337ab  mov     eax, cs:dword_1800DA020
0x1800337b1  cmp     eax, 5
0x1800337b4  jbe     short loc_1800337F6
0x1800337b6  mov     dword ptr [rsp+210h+var_1A0], esi
0x1800337ba  lea     rax, aUnlockedCalled; "Unlocked called, but diff new state"
0x1800337c1  mov     [rsp+210h+var_198], rax
0x1800337c6  lea     rax, [rsp+210h+var_1A0]
0x1800337cb  mov     [rsp+210h+var_1E8], rax
0x1800337d0  lea     rax, [rsp+210h+var_198]
0x1800337d5  mov     [rsp+210h+var_1F0], rax
0x1800337da  lea     rdx, byte_1800C4C91
0x1800337e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800337e6  jmp     short loc_1800337F6
0x1800337e8  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x1800337ef  lea     r14, aHresultFailedB; "HResult failed but continue"
0x1800337f6  mov     rcx, rdi; this
0x1800337f9  call    ?SetTimeZone@CTSSession@@AEAAJXZ; CTSSession::SetTimeZone(void)
0x1800337fe  test    eax, eax
0x180033800  jns     short loc_180033857
0x180033802  mov     ecx, cs:dword_1800DA020
0x180033808  cmp     ecx, 3
0x18003380b  jbe     short loc_180033857
0x18003380d  mov     [rsp+210h+var_198], rbx
0x180033812  mov     dword ptr [rsp+210h+var_1A0], eax
0x180033816  lea     rax, aFailedToSetTim; "Failed to set timezone"
0x18003381d  mov     [rbp+110h+var_190], rax
0x180033821  mov     [rbp+110h+var_188], r14
0x180033825  lea     rax, [rsp+210h+var_198]
0x18003382a  mov     [rsp+210h+var_1D8], rax
  ... truncated ...
```
