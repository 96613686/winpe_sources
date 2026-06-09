# CTSSession::OnDesktopUnlock(void)

- ea: `0x1800353d0`
- end: `0x180035a59`
- name: `?OnDesktopUnlock@CTSSession@@UEAAJXZ`
- size: `1673`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x1800077a0`
- `0x18000c6b0`
- `0x1800118f4`
- `0x180011a78`
- `0x180011e6c`
- `0x1800120d0`
- `0x180012194`
- `0x18001266c`
- `0x1800129d0`
- `0x180014b20`
- `0x18002167c`
- `0x180027610`
- `0x18002772c`
- `0x18002ae18`
- `0x18002dfb0`
- `0x180031650`
- `0x1800353d0`
- `0x1800367c0`
- `0x18004e850`
- `0x1800709ac`
- `0x180073110`
- `0x180073390`
- `0x18009c010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800354db`
- `ntdll!NtQuerySystemTime` at `0x1800354db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003562c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003565a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003562c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003565a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800354f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800354f1`

## string_xrefs

- `0x180035683`: `ptrTerminal->LoggedOnCompleted() took this long`
- `0x1800356df`: `ptrTerminal->LoggedOnCompleted() called while not connected`
- `0x18003574b`: `ptrTerminal->LoggedOnCompleted() failed`
- `0x180035802`: `Failed to dispatch OnLogonCompleted event`
- `0x1800358a0`: `unable to write LastRemoteLogonTime to registry`

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
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  const char *v28; // [rsp+70h] [rbp-90h] BYREF
  ULONGLONG v29; // [rsp+78h] [rbp-88h] BYREF
  const char *v30; // [rsp+80h] [rbp-80h] BYREF
  const char *v31; // [rsp+88h] [rbp-78h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+90h] [rbp-70h] BYREF
  LONGLONG v33; // [rsp+98h] [rbp-68h] BYREF
  LONGLONG v34; // [rsp+A0h] [rbp-60h] BYREF
  union _LARGE_INTEGER v35; // [rsp+A8h] [rbp-58h] BYREF
  char *v36; // [rsp+B0h] [rbp-50h] BYREF
  char *v37; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v38[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v39; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v40[4]; // [rsp+E0h] [rbp-20h]
  __int128 v41; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v42; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v43[24]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v44[192]; // [rsp+120h] [rbp+20h] BYREF

  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v38, (CTSSession *)((char *)this + 1856));
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
  if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
  {
    v28 = "Unlock";
    v8 = (const unsigned __int16 *)*((_QWORD *)this + 247);
    v33 = (SystemTime.QuadPart - (__int64)v8) / 10000000;
    v34 = SystemTime.QuadPart - (_QWORD)v8;
    v35 = SystemTime;
    v36 = (char *)this + 3208;
    v37 = (char *)this + 2048;
    v31 = (char *)this + 2016;
    v30 = (const char *)v8;
    v29 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      SystemTime.LowPart - (_DWORD)v8,
      (unsigned int)byte_1800C9F99,
      SystemTime.LowPart,
      (_DWORD)v8,
      (__int64)&v29,
      (__int64)&v30,
      (__int64)&v31,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v28);
  }
  CAutoLock::Unlock((CAutoLock *)v38);
  if ( v7 != 5 || !*((_DWORD *)this + 527) )
  {
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      LODWORD(v28) = v7;
      v29 = (ULONGLONG)"Unlocked called, but diff new state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned __int8 *)byte_1800C9E19,
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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v29 = v14 - TickCount64;
    LODWORD(v28) = *((_DWORD *)this + 436);
    v30 = "ptrTerminal->LoggedOnCompleted() took this long";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)dword_1800DF020,
      (unsigned __int8 *)byte_1800C9F43,
      v15,
      v16,
      (const unsigned __int16 **)&v30,
      (__int64)&v28,
      (__int64)&v29);
  }
  if ( v3 == -2147022646 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v29 = (ULONGLONG)"OnDesktopUnlock";
      LODWORD(v28) = -2147022646;
      v30 = "ptrTerminal->LoggedOnCompleted() called while not connected";
      v31 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147022646,
        (unsigned int)word_1800C9F02,
        v15,
        v16,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v28,
        (__int64)&v29);
    }
    goto LABEL_34;
  }
  if ( v3 < 0 && (unsigned int)dword_1800DF020 > 3 )
  {
    v29 = (ULONGLONG)"OnDesktopUnlock";
    LODWORD(v28) = v3;
    v30 = "ptrTerminal->LoggedOnCompleted() failed";
    v31 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      -2147022646,
      (unsigned int)byte_1800C9EC1,
      v15,
      v16,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v28,
      (__int64)&v29);
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
        v17 = (CTSSession *)(unsigned int)dword_1800DF020;
        if ( (unsigned int)dword_1800DF020 > 3 )
        {
          v29 = (ULONGLONG)"OnDesktopUnlock";
          LODWORD(v28) = v18;
          v30 = "Failed to dispatch OnLogonCompleted event";
          v31 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            dword_1800DF020,
            (unsigned int)&unk_1800C9E80,
            v19,
            v20,
            (__int64)&v31,
            (__int64)&v30,
            (__int64)&v28,
            (__int64)&v29);
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
      if ( v21 < 0 && (unsigned int)dword_1800DF020 > 3 )
      {
        v29 = (ULONGLONG)"OnDesktopUnlock";
        LODWORD(v28) = v21;
        v30 = "unable to write LastRemoteLogonTime to registry";
        v31 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1800DF020,
          (unsigned int)word_1800C9E4A,
          v22,
          v23,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v28,
          (__int64)&v29);
      }
    }
  }
LABEL_29:
  v24 = CTSSession::SetTimeZone(this);
  if ( v24 < 0 && (unsigned int)dword_1800DF020 > 3 )
  {
    v29 = (ULONGLONG)"OnDesktopUnlock";
    LODWORD(v28) = v24;
    v30 = "Failed to set timezone";
    v31 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1800DF020,
      (unsigned int)&unk_1800C9DD8,
      v25,
      v26,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v28,
      (__int64)&v29);
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
0x1800353d0  mov     [rsp-8+arg_8], rbx
0x1800353d5  mov     [rsp-8+arg_10], rsi
0x1800353da  push    rbp
0x1800353db  push    rdi
0x1800353dc  push    r12
0x1800353de  push    r14
0x1800353e0  push    r15
0x1800353e2  lea     rbp, [rsp-0F0h]
0x1800353ea  sub     rsp, 1F0h
0x1800353f1  mov     rax, cs:__security_cookie
0x1800353f8  xor     rax, rsp
0x1800353fb  mov     [rbp+110h+var_30], rax
0x180035402  mov     rdi, rcx
0x180035405  lea     rdx, [rcx+740h]; struct CResource *
0x18003540c  lea     rcx, [rbp+110h+var_150]; this
0x180035410  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180035415  nop
0x180035416  xorps   xmm0, xmm0
0x180035419  xor     eax, eax
0x18003541b  movups  [rbp+110h+var_140], xmm0
0x18003541f  movups  xmmword ptr [rbp+110h+var_130], xmm0
0x180035423  movups  [rbp+110h+var_120], xmm0
0x180035427  mov     [rbp+110h+var_110], rax
0x18003542b  lea     r14, [rdi+0C88h]
0x180035432  mov     rdx, r14; struct _GUID *
0x180035435  lea     rcx, [rbp+110h+var_108]; this
0x180035439  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18003543e  nop
0x18003543f  mov     r8, rdi; struct ITSSession *
0x180035442  lea     rdx, aCtssessionOnde_0; "CTSSession::OnDesktopUnlock"
0x180035449  lea     rcx, [rbp+110h+var_F0]; this
0x18003544d  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x180035452  nop
0x180035453  mov     qword ptr [rbp+110h+var_140], 0
0x18003545b  lea     rdx, [rbp+110h+var_140]; struct __PTSSessInfo *
0x18003545f  mov     rcx, rdi; this
0x180035462  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x180035467  mov     ebx, eax
0x180035469  test    eax, eax
0x18003546b  jns     short loc_18003548D
0x18003546d  lea     r9, aCtssessionOnde_0; "CTSSession::OnDesktopUnlock"
0x180035474  mov     r8d, eax
0x180035477  lea     rdx, aInitializenoti_0; "InitializeNotifyInfo failed: 0x%x in %s"
0x18003547e  mov     ecx, 8; int
0x180035483  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180035488  jmp     loc_1800359D3
0x18003548d  lea     rsi, [rdi+0CB8h]
0x180035494  mov     r15d, 0Eh
0x18003549a  mov     edx, r15d
0x18003549d  mov     rcx, rsi
0x1800354a0  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x1800354a5  mov     ebx, eax
0x1800354a7  mov     edx, r15d
0x1800354aa  test    eax, eax
0x1800354ac  js      loc_1800359C8
0x1800354b2  mov     r12d, [rsi]
0x1800354b5  mov     dword ptr [rsp+210h+var_1F0], 7E6h
0x1800354bd  lea     r9, [rbp+110h+var_110]
0x1800354c1  lea     r8, [rbp+110h+var_120+8]
0x1800354c5  mov     rcx, rsi
0x1800354c8  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x1800354cd  mov     esi, [rsi]
0x1800354cf  mov     qword ptr [rbp+110h+SystemTime], 0
0x1800354d7  lea     rcx, [rbp+110h+SystemTime]; SystemTime
0x1800354db  call    cs:__imp_NtQuerySystemTime
0x1800354e2  nop     dword ptr [rax+rax+00h]
0x1800354e7  lea     rbx, [rdi+800h]
0x1800354ee  mov     rcx, rbx; lpSystemTime
0x1800354f1  call    cs:__imp_GetSystemTime
0x1800354f8  nop     dword ptr [rax+rax+00h]
0x1800354fd  mov     eax, cs:dword_1800DF020
0x180035503  cmp     eax, 5
0x180035506  jbe     loc_1800355F0
0x18003550c  mov     rdx, 400000000000h
0x180035516  lea     rcx, dword_1800DF020
0x18003551d  call    _tlgKeywordOn
0x180035522  test    al, al
0x180035524  jz      loc_1800355F0
0x18003552a  lea     rax, aUnlock; "Unlock"
0x180035531  mov     [rsp+210h+var_1A0], rax
0x180035536  mov     r9, [rdi+7B8h]
0x18003553d  mov     r8, qword ptr [rbp+110h+SystemTime]
0x180035541  mov     rcx, r8
0x180035544  sub     rcx, r9
0x180035547  mov     rax, 0D6BF94D5E57A42BDh
0x180035551  imul    rcx
0x180035554  add     rdx, rcx
0x180035557  sar     rdx, 17h
0x18003555b  mov     rax, rdx
0x18003555e  shr     rax, 3Fh
0x180035562  add     rdx, rax
0x180035565  mov     [rbp+110h+var_178], rdx
0x180035569  mov     [rbp+110h+var_170], rcx
0x18003556d  mov     [rbp+110h+var_168], r8
0x180035571  mov     [rbp+110h+var_160], r14
0x180035575  mov     [rbp+110h+var_158], rbx
0x180035579  lea     rax, [rdi+7E0h]
0x180035580  mov     [rbp+110h+var_188], rax
0x180035584  mov     [rbp+110h+var_190], r9
0x180035588  mov     [rsp+210h+var_198], 2000000h
0x180035591  lea     rax, [rsp+210h+var_1A0]
0x180035596  mov     [rsp+210h+var_1B0], rax
0x18003559b  lea     rax, [rbp+110h+var_178]
0x18003559f  mov     [rsp+210h+var_1B8], rax
0x1800355a4  lea     rax, [rbp+110h+var_170]
0x1800355a8  mov     [rsp+210h+var_1C0], rax
0x1800355ad  lea     rax, [rbp+110h+var_168]
0x1800355b1  mov     [rsp+210h+var_1C8], rax
0x1800355b6  lea     rax, [rbp+110h+var_160]
0x1800355ba  mov     [rsp+210h+var_1D0], rax
0x1800355bf  lea     rax, [rbp+110h+var_158]
0x1800355c3  mov     [rsp+210h+var_1D8], rax
0x1800355c8  lea     rax, [rbp+110h+var_188]
0x1800355cc  mov     [rsp+210h+var_1E0], rax
0x1800355d1  lea     rax, [rbp+110h+var_190]
0x1800355d5  mov     [rsp+210h+var_1E8], rax
0x1800355da  lea     rax, [rsp+210h+var_198]
0x1800355df  mov     [rsp+210h+var_1F0], rax
0x1800355e4  lea     rdx, byte_1800C9F99
0x1800355eb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U1@U1@U1@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@44333AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800355f0  lea     rcx, [rbp+110h+var_150]; this
0x1800355f4  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800355f9  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x180035600  lea     r14, aHresultFailedB; "HResult failed but continue"
0x180035607  cmp     esi, 5
0x18003560a  jnz     loc_1800358E3
0x180035610  cmp     dword ptr [rdi+83Ch], 0
0x180035617  jz      loc_1800358E3
0x18003561d  mov     rcx, [rdi+718h]; struct ITerminal *
0x180035624  call    ?IsLocalGlassTerminal@CGlassTerminal@@SAHPEAUITerminal@@@Z; CGlassTerminal::IsLocalGlassTerminal(ITerminal *)
0x180035629  mov     r15d, eax
0x18003562c  call    cs:__imp_GetTickCount64
0x180035633  nop     dword ptr [rax+rax+00h]
0x180035638  mov     r14, rax
0x18003563b  mov     r8, [rdi+718h]
0x180035642  mov     rcx, [r8]
0x180035645  mov     rax, [rcx+48h]
0x180035649  mov     rdx, [rdi+1728h]
0x180035650  mov     rcx, r8
0x180035653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035658  mov     ebx, eax
0x18003565a  call    cs:__imp_GetTickCount64
0x180035661  nop     dword ptr [rax+rax+00h]
0x180035666  mov     ecx, cs:dword_1800DF020
0x18003566c  cmp     ecx, 4
0x18003566f  jbe     short loc_1800356B7
0x180035671  sub     rax, r14
0x180035674  mov     [rsp+210h+var_198], rax
0x180035679  mov     eax, [rdi+6D0h]
0x18003567f  mov     dword ptr [rsp+210h+var_1A0], eax
0x180035683  lea     rax, aPtrterminalLog_1; "ptrTerminal->LoggedOnCompleted() took t"...
0x18003568a  mov     [rbp+110h+var_190], rax
0x18003568e  lea     rax, [rsp+210h+var_198]
0x180035693  mov     [rsp+210h+var_1E0], rax
0x180035698  lea     rax, [rsp+210h+var_1A0]
0x18003569d  mov     [rsp+210h+var_1E8], rax
0x1800356a2  lea     rax, [rbp+110h+var_190]
0x1800356a6  mov     [rsp+210h+var_1F0], rax
0x1800356ab  lea     rdx, byte_1800C9F43
0x1800356b2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800356b7  mov     ecx, 800708CAh
0x1800356bc  cmp     ebx, ecx
0x1800356be  jnz     short loc_18003572C
0x1800356c0  mov     eax, cs:dword_1800DF020
0x1800356c6  cmp     eax, 3
0x1800356c9  jbe     loc_1800359D3
0x1800356cf  lea     rax, aOndesktopunloc_0; "OnDesktopUnlock"
0x1800356d6  mov     [rsp+210h+var_198], rax
0x1800356db  mov     dword ptr [rsp+210h+var_1A0], ecx
0x1800356df  lea     rax, aPtrterminalLog_2; "ptrTerminal->LoggedOnCompleted() called"...
0x1800356e6  mov     [rbp+110h+var_190], rax
0x1800356ea  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800356f1  mov     [rbp+110h+var_188], rax
0x1800356f5  lea     rax, [rsp+210h+var_198]
0x1800356fa  mov     [rsp+210h+var_1D8], rax
0x1800356ff  lea     rax, [rsp+210h+var_1A0]
0x180035704  mov     [rsp+210h+var_1E0], rax
0x180035709  lea     rax, [rbp+110h+var_190]
0x18003570d  mov     [rsp+210h+var_1E8], rax
0x180035712  lea     rax, [rbp+110h+var_188]
0x180035716  mov     [rsp+210h+var_1F0], rax
0x18003571b  lea     rdx, word_1800C9F02
0x180035722  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180035727  jmp     loc_1800359D3
0x18003572c  test    ebx, ebx
0x18003572e  jns     short loc_180035793
0x180035730  mov     eax, cs:dword_1800DF020
0x180035736  cmp     eax, 3
0x180035739  jbe     short loc_180035793
0x18003573b  lea     rax, aOndesktopunloc_0; "OnDesktopUnlock"
0x180035742  mov     [rsp+210h+var_198], rax
0x180035747  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18003574b  lea     rax, aPtrterminalLog_0; "ptrTerminal->LoggedOnCompleted() failed"
0x180035752  mov     [rbp+110h+var_190], rax
0x180035756  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18003575d  mov     [rbp+110h+var_188], rax
0x180035761  lea     rax, [rsp+210h+var_198]
0x180035766  mov     [rsp+210h+var_1D8], rax
0x18003576b  lea     rax, [rsp+210h+var_1A0]
0x180035770  mov     [rsp+210h+var_1E0], rax
0x180035775  lea     rax, [rbp+110h+var_190]
0x180035779  mov     [rsp+210h+var_1E8], rax
0x18003577e  lea     rax, [rbp+110h+var_188]
0x180035782  mov     [rsp+210h+var_1F0], rax
0x180035787  lea     rdx, byte_1800C9EC1
0x18003578e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180035793  mov     dword ptr [rdi+83Ch], 0
0x18003579d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif> `wil::Feature<__WilFeatureTraits_Feature_LogonCompletedNotif>::GetImpl(void)'::`2'::impl
0x1800357a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif>::__private_IsEnabled(void)
0x1800357a9  test    al, al
0x1800357ab  jz      loc_18003584C
0x1800357b1  test    ebx, ebx
0x1800357b3  js      loc_180035920
0x1800357b9  mov     rcx, [rdi+720h]
0x1800357c0  add     rcx, 728h
0x1800357c7  mov     rax, [rcx]
0x1800357ca  mov     r9d, r12d
0x1800357cd  mov     r8d, 5
0x1800357d3  lea     rdx, [rbp+110h+var_140]
0x1800357d7  mov     rax, [rax+0C0h]
0x1800357de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357e3  test    eax, eax
0x1800357e5  jns     short loc_180035864
0x1800357e7  mov     ecx, cs:dword_1800DF020
0x1800357ed  cmp     ecx, 3
0x1800357f0  jbe     short loc_180035864
0x1800357f2  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x1800357f9  mov     [rsp+210h+var_198], rbx
0x1800357fe  mov     dword ptr [rsp+210h+var_1A0], eax
0x180035802  lea     rax, aFailedToDispat; "Failed to dispatch OnLogonCompleted eve"...
0x180035809  mov     [rbp+110h+var_190], rax
0x18003580d  lea     r14, aHresultFailedB; "HResult failed but continue"
0x180035814  mov     [rbp+110h+var_188], r14
0x180035818  lea     rax, [rsp+210h+var_198]
0x18003581d  mov     [rsp+210h+var_1D8], rax
0x180035822  lea     rax, [rsp+210h+var_1A0]
0x180035827  mov     [rsp+210h+var_1E0], rax
0x18003582c  lea     rax, [rbp+110h+var_190]
0x180035830  mov     [rsp+210h+var_1E8], rax
0x180035835  lea     rax, [rbp+110h+var_188]
0x180035839  mov     [rsp+210h+var_1F0], rax
0x18003583e  lea     rdx, unk_1800C9E80
0x180035845  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003584a  jmp     short loc_180035872
0x18003584c  lea     r14, aHresultFailedB; "HResult failed but continue"
0x180035853  test    ebx, ebx
0x180035855  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x18003585c  js      loc_18003592E
0x180035862  jmp     short loc_180035872
0x180035864  lea     r14, aHresultFailedB; "HResult failed but continue"
0x18003586b  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x180035872  test    r15d, r15d
0x180035875  jnz     loc_18003592E
0x18003587b  call    ?WriteLastRemoteLogonTime@CTSSession@@AEAAJXZ; CTSSession::WriteLastRemoteLogonTime(void)
0x180035880  test    eax, eax
0x180035882  jns     loc_18003592E
0x180035888  mov     ecx, cs:dword_1800DF020
0x18003588e  cmp     ecx, 3
0x180035891  jbe     loc_18003592E
0x180035897  mov     [rsp+210h+var_198], rbx
0x18003589c  mov     dword ptr [rsp+210h+var_1A0], eax
0x1800358a0  lea     rax, aUnableToWriteL; "unable to write LastRemoteLogonTime to "...
0x1800358a7  mov     [rbp+110h+var_190], rax
0x1800358ab  mov     [rbp+110h+var_188], r14
0x1800358af  lea     rax, [rsp+210h+var_198]
0x1800358b4  mov     [rsp+210h+var_1D8], rax
0x1800358b9  lea     rax, [rsp+210h+var_1A0]
0x1800358be  mov     [rsp+210h+var_1E0], rax
0x1800358c3  lea     rax, [rbp+110h+var_190]
0x1800358c7  mov     [rsp+210h+var_1E8], rax
0x1800358cc  lea     rax, [rbp+110h+var_188]
0x1800358d0  mov     [rsp+210h+var_1F0], rax
0x1800358d5  lea     rdx, word_1800C9E4A
0x1800358dc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800358e1  jmp     short loc_18003592E
0x1800358e3  mov     eax, cs:dword_1800DF020
0x1800358e9  cmp     eax, 5
0x1800358ec  jbe     short loc_18003592E
0x1800358ee  mov     dword ptr [rsp+210h+var_1A0], esi
0x1800358f2  lea     rax, aUnlockedCalled; "Unlocked called, but diff new state"
0x1800358f9  mov     [rsp+210h+var_198], rax
0x1800358fe  lea     rax, [rsp+210h+var_1A0]
0x180035903  mov     [rsp+210h+var_1E8], rax
0x180035908  lea     rax, [rsp+210h+var_198]
0x18003590d  mov     [rsp+210h+var_1F0], rax
0x180035912  lea     rdx, byte_1800C9E19
0x180035919  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003591e  jmp     short loc_18003592E
0x180035920  lea     rbx, aOndesktopunloc_0; "OnDesktopUnlock"
0x180035927  lea     r14, aHresultFailedB; "HResult failed but continue"
0x18003592e  mov     rcx, rdi; this
0x180035931  call    ?SetTimeZone@CTSSession@@AEAAJXZ; CTSSession::SetTimeZone(void)
0x180035936  test    eax, eax
0x180035938  jns     short loc_18003598F
0x18003593a  mov     ecx, cs:dword_1800DF020
0x180035940  cmp     ecx, 3
0x180035943  jbe     short loc_18003598F
0x180035945  mov     [rsp+210h+var_198], rbx
0x18003594a  mov     dword ptr [rsp+210h+var_1A0], eax
0x18003594e  lea     rax, aFailedToSetTim; "Failed to set timezone"
  ... truncated ...
```
