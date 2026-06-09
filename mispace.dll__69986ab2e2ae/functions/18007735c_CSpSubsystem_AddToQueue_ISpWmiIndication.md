# CSpSubsystem::_AddToQueue(ISpWmiIndication *)

- ea: `0x18007735c`
- end: `0x18007762e`
- name: `?_AddToQueue@CSpSubsystem@@IEAA?AW4_MI_Result@@PEAVISpWmiIndication@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(CSpSubsystem *this, struct ISpWmiIndication *, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180078cac`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x1800063ac`
- `0x18000c644`
- `0x18000d0e4`
- `0x180013bf8`
- `0x1800195fc`
- `0x180028a20`
- `0x1800293c0`
- `0x18006f21c`
- `0x18007735c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800773d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800773d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077465`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007743b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007743b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800775bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800775bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180077586`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800775a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180077586`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800775a3`

## pseudocode

```c
__int64 __fastcall CSpSubsystem::_AddToQueue(CSpSubsystem *this, struct ISpWmiIndication *a2, int a3, int a4)
{
  struct _FILETIME v6; // rbx
  CSpSubsystem::_SP_INDICATION_INFO *v7; // rdi
  int v8; // ecx
  DWORD LastError; // ebx
  int v10; // r8d
  int v11; // r9d
  char *v12; // rdx
  enum _MI_Result v13; // esi
  CSpSubsystem::_SP_INDICATION_INFO *v14; // rbx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  DWORD v17; // eax
  unsigned int v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-19h] BYREF
  const char *v24; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v25[3]; // [rsp+50h] [rbp-9h] BYREF
  int v26; // [rsp+68h] [rbp+Fh]
  _BYTE v27[8]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v28; // [rsp+78h] [rbp+1Fh]
  __int64 v29; // [rsp+80h] [rbp+27h]
  int v30; // [rsp+88h] [rbp+2Fh]
  __int64 v31; // [rsp+D0h] [rbp+77h] BYREF
  const char *v32; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v31) = 1322;
    v32 = "CSpSubsystem::_AddToQueue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CSpSubsystem::_AddToQueue",
      (unsigned int)&word_1803177F6,
      a3,
      a4,
      (__int64)&v32,
      (__int64)&v31);
  }
  SystemTimeAsFileTime = 0;
  v25[0] = &CSmLinkedListIterator<CSpSubsystem::_SP_INDICATION_INFO *>::`vftable';
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = SystemTimeAsFileTime;
  v7 = (CSpSubsystem::_SP_INDICATION_INFO *)operator new(0x18u);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *(_QWORD *)v7 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v7);
  *(_QWORD *)v7 = 0;
  CSmRefPtrBase<CSpWmiAssociation::LocalDataSource<CSpStorageEnclosure::LocalDataSource,CSpPhysicalDisk::LocalDataSource>>::_Assign(
    v7,
    a2);
  *((_QWORD *)v7 + 1) = MISpaceHandle::GetTime(MISpaceHandle::g_MISpaceHandle);
  *((struct _FILETIME *)v7 + 2) = v6;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( !(*(unsigned __int8 (__fastcall **)(char *, CSpSubsystem::_SP_INDICATION_INFO *))(*((_QWORD *)this + 7) + 8LL))(
          (char *)this + 56,
          v7) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError != 122 )
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_13;
        LODWORD(v31) = LastError;
        v12 = byte_1803197F5;
        goto LABEL_10;
      }
      if ( (unsigned int)dword_18039EB68 > 3 )
      {
        LODWORD(v31) = 122;
        v12 = &byte_180319097;
        goto LABEL_10;
      }
    }
    else
    {
      v8 = dword_18039EB68;
      if ( (unsigned int)dword_18039EB68 > 4 )
      {
        LODWORD(v31) = 0;
        v12 = byte_180317B89;
LABEL_10:
        LODWORD(v32) = 1356;
        v24 = "CSpSubsystem::_AddToQueue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (_DWORD)v12,
          v10,
          v11,
          (__int64)&v24,
          (__int64)&v32,
          (__int64)&v31);
      }
    }
LABEL_13:
    v13 = MI_FROM_WIN32(LastError);
    v14 = v7;
    goto LABEL_22;
  }
  v13 = MI_RESULT_OK;
  v31 = 0;
  CSmLinkedListIterator<unsigned short *>::CSmLinkedListIterator<unsigned short *>(v27, (char *)this + 56);
  v25[1] = v28;
  v25[2] = v29;
  v26 = v30;
  if ( (unsigned __int8)CSmLinkedListIterator<_SU_TP_CONTEXT *>::GetNext(v25, &v31) )
  {
    v15 = *(_QWORD *)&v6 + 50000000LL;
    v16 = *(_QWORD *)(v31 + 16) + 300000000LL;
    if ( v15 >= v16 )
    {
      v31 = *(_QWORD *)(v31 + 16) + 300000000LL;
      v17 = v16;
    }
    else
    {
      v31 = v15;
      v17 = v15;
    }
    SystemTimeAsFileTime.dwLowDateTime = v17;
    if ( v15 >= v16 )
      HIDWORD(v15) = HIDWORD(v16);
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v15);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 16), 0, 0, 0);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 16), &SystemTimeAsFileTime, 0, 0);
  }
  v7 = 0;
  v14 = 0;
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v7 && v14 )
    CSpSubsystem::_SP_INDICATION_INFO::`scalar deleting destructor'(v14, v18);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v31) = 1408;
    v32 = "CSpSubsystem::_AddToQueue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_180314FA9,
      v20,
      v21,
      (__int64)&v32,
      (__int64)&v31);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18007735c  mov     [rsp-8+arg_0], rbx
0x180077361  mov     [rsp-8+arg_8], rsi
0x180077366  push    rbp
0x180077367  push    rdi
0x180077368  push    r12
0x18007736a  push    r14
0x18007736c  push    r15
0x18007736e  lea     rbp, [rsp-37h]
0x180077373  sub     rsp, 90h
0x18007737a  mov     rsi, rdx
0x18007737d  mov     r14, rcx
0x180077380  mov     eax, cs:dword_18039EB68
0x180077386  lea     rcx, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x18007738d  cmp     eax, 5
0x180077390  jbe     short loc_1800773BB
0x180077392  mov     dword ptr [rbp+57h+arg_10], 52Ah
0x180077399  mov     [rbp+57h+arg_18], rcx
0x18007739d  lea     rax, [rbp+57h+arg_10]
0x1800773a1  mov     [rsp+0B0h+var_88], rax
0x1800773a6  lea     rax, [rbp+57h+arg_18]
0x1800773aa  mov     [rsp+0B0h+var_90], rax
0x1800773af  lea     rdx, word_1803177F6
0x1800773b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800773bb  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800773c3  lea     rax, ??_7?$CSmLinkedListIterator@PEAU_SP_INDICATION_INFO@CSpSubsystem@@@@6B@; const CSmLinkedListIterator<CSpSubsystem::_SP_INDICATION_INFO *>::`vftable'
0x1800773ca  mov     [rbp+57h+var_60], rax
0x1800773ce  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800773d2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800773d9  nop     dword ptr [rax+rax+00h]
0x1800773de  mov     rbx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800773e2  mov     ecx, 18h; Size
0x1800773e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800773ec  mov     rdi, rax
0x1800773ef  mov     qword ptr [rax+8], 0
0x1800773f7  mov     qword ptr [rax+10h], 0
0x1800773ff  mov     qword ptr [rax], 0
0x180077406  mov     rcx, rax
0x180077409  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18007740e  mov     qword ptr [rdi], 0
0x180077415  mov     rdx, rsi
0x180077418  mov     rcx, rdi
0x18007741b  call    ?_Assign@?$CSmRefPtrBase@V?$LocalDataSource@V0CSpStorageEnclosure@@V0CSpPhysicalDisk@@@CSpWmiAssociation@@@@IEAAXPEAV?$LocalDataSource@V0CSpStorageEnclosure@@V0CSpPhysicalDisk@@@CSpWmiAssociation@@@Z; CSmRefPtrBase<CSpWmiAssociation::LocalDataSource<CSpStorageEnclosure::LocalDataSource,CSpPhysicalDisk::LocalDataSource>>::_Assign(CSpWmiAssociation::LocalDataSource<CSpStorageEnclosure::LocalDataSource,CSpPhysicalDisk::LocalDataSource> *)
0x180077420  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180077427  call    ?GetTime@MISpaceHandle@@QEAA_KXZ; MISpaceHandle::GetTime(void)
0x18007742c  mov     [rdi+8], rax
0x180077430  mov     [rdi+10h], rbx
0x180077434  lea     r12, [r14+58h]
0x180077438  mov     rcx, r12; lpCriticalSection
0x18007743b  call    cs:__imp_EnterCriticalSection
0x180077442  nop     dword ptr [rax+rax+00h]
0x180077447  lea     r15, [r14+38h]
0x18007744b  mov     rax, [r15]
0x18007744e  mov     rdx, rdi
0x180077451  mov     rcx, r15
0x180077454  mov     rax, [rax+8]
0x180077458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007745d  test    al, al
0x18007745f  jnz     loc_180077505
0x180077465  call    cs:__imp_GetLastError
0x18007746c  nop     dword ptr [rax+rax+00h]
0x180077471  mov     ebx, eax
0x180077473  test    eax, eax
0x180077475  jnz     short loc_18007748E
0x180077477  mov     ecx, cs:dword_18039EB68
0x18007747d  cmp     ecx, 4
0x180077480  jbe     short loc_1800774ED
0x180077482  mov     dword ptr [rbp+57h+arg_10], eax
0x180077485  lea     rdx, byte_180317B89
0x18007748c  jmp     short loc_1800774A8
0x18007748e  mov     eax, cs:dword_18039EB68
0x180077494  cmp     ebx, 7Ah ; 'z'
0x180077497  jnz     short loc_1800774DC
0x180077499  cmp     eax, 3
0x18007749c  jbe     short loc_1800774ED
0x18007749e  mov     dword ptr [rbp+57h+arg_10], ebx
0x1800774a1  lea     rdx, byte_180319097
0x1800774a8  lea     rax, [rbp+57h+arg_10]
0x1800774ac  mov     [rsp+0B0h+var_80], rax
0x1800774b1  lea     rax, [rbp+57h+arg_18]
0x1800774b5  mov     [rsp+0B0h+var_88], rax
0x1800774ba  lea     r14, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x1800774c1  lea     rax, [rbp+57h+var_68]
0x1800774c5  mov     dword ptr [rbp+57h+arg_18], 54Ch
0x1800774cc  mov     [rbp+57h+var_68], r14
0x1800774d0  mov     [rsp+0B0h+var_90], rax
0x1800774d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800774da  jmp     short loc_1800774F4
0x1800774dc  cmp     eax, 2
0x1800774df  jbe     short loc_1800774ED
0x1800774e1  mov     dword ptr [rbp+57h+arg_10], ebx
0x1800774e4  lea     rdx, byte_1803197F5
0x1800774eb  jmp     short loc_1800774A8
0x1800774ed  lea     r14, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x1800774f4  mov     ecx, ebx; unsigned int
0x1800774f6  call    ?MI_FROM_WIN32@@YA?AW4_MI_Result@@K@Z; MI_FROM_WIN32(ulong)
0x1800774fb  mov     esi, eax
0x1800774fd  mov     rbx, rdi
0x180077500  jmp     loc_1800775BA
0x180077505  xor     esi, esi
0x180077507  mov     [rbp+57h+arg_10], rsi
0x18007750b  mov     rdx, r15
0x18007750e  lea     rcx, [rbp+57h+var_40]
0x180077512  call    ??0?$CSmLinkedListIterator@PEAG@@QEAA@PEAV?$CSmLinkedList@PEAG@@@Z; CSmLinkedListIterator<ushort *>::CSmLinkedListIterator<ushort *>(CSmLinkedList<ushort *> *)
0x180077517  mov     rcx, [rbp+57h+var_38]
0x18007751b  mov     [rbp+57h+var_58], rcx
0x18007751f  mov     rax, [rbp+57h+var_30]
0x180077523  mov     [rbp+57h+var_50], rax
0x180077527  mov     eax, [rbp+57h+var_28]
0x18007752a  mov     [rbp+57h+var_48], eax
0x18007752d  lea     rdx, [rbp+57h+arg_10]
0x180077531  lea     rcx, [rbp+57h+var_60]
0x180077535  call    ?GetNext@?$CSmLinkedListIterator@PEAU_SU_TP_CONTEXT@@@@UEAA_NPEAPEAU_SU_TP_CONTEXT@@@Z; CSmLinkedListIterator<_SU_TP_CONTEXT *>::GetNext(_SU_TP_CONTEXT * *)
0x18007753a  test    al, al
0x18007753c  jz      short loc_1800775AF
0x18007753e  add     rbx, 2FAF080h
0x180077545  mov     rax, [rbp+57h+arg_10]
0x180077549  mov     rcx, [rax+10h]
0x18007754d  add     rcx, 11E1A300h
0x180077554  cmp     rbx, rcx
0x180077557  jnb     short loc_180077562
0x180077559  mov     [rbp+57h+arg_10], rbx
0x18007755d  mov     rax, rbx
0x180077560  jmp     short loc_180077569
0x180077562  mov     [rbp+57h+arg_10], rcx
0x180077566  mov     rax, rcx
0x180077569  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18007756c  cmovnb  rbx, rcx
0x180077570  shr     rbx, 20h
0x180077574  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], ebx
0x180077577  xor     r9d, r9d; msWindowLength
0x18007757a  xor     r8d, r8d; msPeriod
0x18007757d  xor     edx, edx; pftDueTime
0x18007757f  mov     rcx, [r14+80h]; pti
0x180077586  call    cs:__imp_SetThreadpoolTimer
0x18007758d  nop     dword ptr [rax+rax+00h]
0x180077592  xor     r9d, r9d; msWindowLength
0x180077595  xor     r8d, r8d; msPeriod
0x180077598  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; pftDueTime
0x18007759c  mov     rcx, [r14+80h]; pti
0x1800775a3  call    cs:__imp_SetThreadpoolTimer
0x1800775aa  nop     dword ptr [rax+rax+00h]
0x1800775af  xor     edi, edi
0x1800775b1  xor     ebx, ebx
0x1800775b3  lea     r14, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x1800775ba  mov     rcx, r12; lpCriticalSection
0x1800775bd  call    cs:__imp_LeaveCriticalSection
0x1800775c4  nop     dword ptr [rax+rax+00h]
0x1800775c9  test    rdi, rdi
0x1800775cc  jz      short loc_1800775DB
0x1800775ce  test    rbx, rbx
0x1800775d1  jz      short loc_1800775DB
0x1800775d3  mov     rcx, rbx; this
0x1800775d6  call    ??_G_SP_INDICATION_INFO@CSpSubsystem@@QEAAPEAXI@Z; CSpSubsystem::_SP_INDICATION_INFO::`scalar deleting destructor'(uint)
0x1800775db  mov     eax, cs:dword_18039EB68
0x1800775e1  cmp     eax, 5
0x1800775e4  jbe     short loc_18007760F
0x1800775e6  mov     dword ptr [rbp+57h+arg_10], 580h
0x1800775ed  mov     [rbp+57h+arg_18], r14
0x1800775f1  lea     rax, [rbp+57h+arg_10]
0x1800775f5  mov     [rsp+0B0h+var_88], rax
0x1800775fa  lea     rax, [rbp+57h+arg_18]
0x1800775fe  mov     [rsp+0B0h+var_90], rax
0x180077603  lea     rdx, byte_180314FA9
0x18007760a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007760f  mov     eax, esi
0x180077611  lea     r11, [rsp+0B0h+var_20]
0x180077619  mov     rbx, [r11+30h]
0x18007761d  mov     rsi, [r11+38h]
0x180077621  mov     rsp, r11
0x180077624  pop     r15
0x180077626  pop     r14
0x180077628  pop     r12
0x18007762a  pop     rdi
0x18007762b  pop     rbp
0x18007762c  retn
```
