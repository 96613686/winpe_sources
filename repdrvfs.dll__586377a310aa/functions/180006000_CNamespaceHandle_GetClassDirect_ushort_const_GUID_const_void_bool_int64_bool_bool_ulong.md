# CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)

- ea: `0x180006000`
- end: `0x180006953`
- name: `?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z`
- size: `2387`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, const struct _GUID *, void **, char, __int64 *, bool *, bool *, unsigned int)`
- caller_count: `13`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002350`
- `0x1800040c0`
- `0x180004f30`
- `0x180006d30`
- `0x180007770`
- `0x180014290`
- `0x1800178e0`
- `0x18001e370`
- `0x180022f50`
- `0x180025180`
- `0x1800262cc`
- `0x180031e48`
- `0x180032b24`

## callees

- `0x1800012b8`
- `0x1800013c8`
- `0x180006000`
- `0x180006960`
- `0x1800178e0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800060a1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006349`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800063cc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800060a1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006349`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800063cc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180006126`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800064d2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800064dc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800065f2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800065fc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800066e1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000679e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180006848`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800068aa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800068b4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180006911`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000691b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180006126`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800064d2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800064dc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800065f2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800065fc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800066e1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000679e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180006848`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800068aa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800068b4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180006911`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000691b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180006086`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180006095`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000616f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180006194`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180006086`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180006095`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000616f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180006194`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006131`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006227`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006250`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800062b5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800062c2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006321`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800065d8`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000660e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800066ec`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006131`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006227`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006250`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800062b5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800062c2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180006321`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800065d8`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000660e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800066ec`
- `wbemcomn!GetMemLogObject` at `0x180006529`
- `wbemcomn!GetMemLogObject` at `0x180006646`
- `wbemcomn!GetMemLogObject` at `0x18000674d`
- `wbemcomn!GetMemLogObject` at `0x1800067af`
- `wbemcomn!GetMemLogObject` at `0x1800067fd`
- `wbemcomn!GetMemLogObject` at `0x180006859`
- `wbemcomn!GetMemLogObject` at `0x1800068c5`
- `wbemcomn!GetMemLogObject` at `0x180006529`
- `wbemcomn!GetMemLogObject` at `0x180006646`
- `wbemcomn!GetMemLogObject` at `0x18000674d`
- `wbemcomn!GetMemLogObject` at `0x1800067af`
- `wbemcomn!GetMemLogObject` at `0x1800067fd`
- `wbemcomn!GetMemLogObject` at `0x180006859`
- `wbemcomn!GetMemLogObject` at `0x1800068c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006534`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006651`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000675b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800067bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000680b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800068d0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006534`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006651`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000675b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800067bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000680b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800068d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006200`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006200`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000673a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000673a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CNamespaceHandle::GetClassDirect(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4,
        char a5,
        __int64 *a6,
        bool *a7,
        bool *a8,
        unsigned int a9)
{
  __int64 v13; // rax
  __int64 v14; // r13
  unsigned __int16 *v15; // rax
  char *v16; // rbx
  __int64 *v17; // r10
  __int64 *v18; // r9
  __int64 *v19; // rdi
  char *v20; // rax
  signed __int64 v21; // r8
  int v22; // ecx
  int v23; // edx
  __int64 v24; // rdi
  __int64 *v25; // r14
  bool *v26; // rsi
  char v27; // r15
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rcx
  struct _IWmiObject *v35; // rdi
  unsigned __int16 *v36; // rax
  int v37; // ecx
  int v38; // edx
  unsigned int v39; // ebx
  unsigned __int16 *v41; // rax
  unsigned __int16 *v42; // rbx
  __int64 v43; // rax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rdx
  unsigned __int16 *v46; // rcx
  unsigned __int16 v47; // r9
  unsigned __int16 *v48; // rax
  unsigned __int16 *v49; // rax
  unsigned __int16 *v50; // rdi
  unsigned __int16 *v51; // r8
  unsigned __int16 *v52; // rdx
  unsigned int i; // ecx
  unsigned __int16 v54; // ax
  unsigned int v55; // ecx
  unsigned __int16 *v56; // r8
  unsigned __int16 *v57; // rdx
  unsigned __int16 v58; // ax
  int v59; // esi
  struct _IWmiObject *v60; // rsi
  unsigned int v61; // r14d
  CMemoryLog *v62; // rax
  CVarObjHeap *v63; // rcx
  __int64 v64; // rdx
  CMemoryLog *v65; // rax
  unsigned int v66; // edi
  CMemoryLog *v67; // rax
  CMemoryLog *v68; // rax
  CMemoryLog *v69; // rax
  CMemoryLog *v70; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v72; // rbx
  struct _IWmiObject *v73; // [rsp+40h] [rbp-28h] BYREF
  __int64 v74; // [rsp+48h] [rbp-20h] BYREF
  struct _IWmiObject *v75; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v76[2]; // [rsp+58h] [rbp-10h] BYREF
  _WORD *v78; // [rsp+B8h] [rbp+50h] BYREF
  const struct _GUID *v79; // [rsp+C0h] [rbp+58h]
  void **v80; // [rsp+C8h] [rbp+60h]

  v80 = a4;
  v79 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, a2);
  }
  if ( a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    if ( v13 )
    {
      v73 = 0;
      v14 = *((_QWORD *)this + 11);
      CInCritSec::CInCritSec((CInCritSec *)v76, *(struct _RTL_CRITICAL_SECTION **)(v14 + 16));
      CInCritSec::CInCritSec((CInCritSec *)&v74, *(struct _RTL_CRITICAL_SECTION **)(v14 + 16));
      v15 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x84u);
      v16 = (char *)v15;
      if ( v15 )
      {
        v78 = v15;
        if ( A51Hash(a2, v15) )
        {
          v17 = *(__int64 **)(v14 + 24);
          v18 = (__int64 *)v17[1];
          v19 = v17;
          if ( *((_BYTE *)v18 + 25) )
            goto LABEL_17;
          do
          {
            v20 = (char *)v18[4];
            v21 = v16 - v20;
            do
            {
              v22 = *(unsigned __int16 *)&v20[v21];
              v23 = *(unsigned __int16 *)v20 - v22;
              if ( v23 )
                break;
              v20 += 2;
            }
            while ( v22 );
            if ( v23 >= 0 )
            {
              v19 = v18;
              v18 = (__int64 *)*v18;
            }
            else
            {
              v18 = (__int64 *)v18[2];
            }
          }
          while ( !*((_BYTE *)v18 + 25) );
          if ( v19 == v17 )
            goto LABEL_17;
          v36 = (unsigned __int16 *)v16;
          do
          {
            v37 = *(unsigned __int16 *)((char *)v36 + v19[4] - (_QWORD)v16);
            v38 = *v36 - v37;
            if ( v38 )
              break;
            ++v36;
          }
          while ( v37 );
          if ( v38 < 0 )
LABEL_17:
            v24 = 0;
          else
            v24 = v19[5];
          CWin32DefaultArena::WbemMemFree(v16);
          CInCritSec::~CInCritSec((CInCritSec *)&v74);
          if ( !v24 || a9 == 2 && *(_BYTE *)(v24 + 337) )
            goto LABEL_53;
          v25 = a6;
          if ( a6 )
            *a6 = *(_QWORD *)(v24 + 328);
          v26 = a7;
          if ( a7 )
            *a7 = *(_BYTE *)(v24 + 336);
          CInCritSec::CInCritSec((CInCritSec *)&v78, *(struct _RTL_CRITICAL_SECTION **)(v14 + 16));
          v27 = a5;
          if ( *(_QWORD *)(v24 + 176) )
          {
            v28 = *(_QWORD *)(v14 + 16);
            CInCritSec::CInCritSec((CInCritSec *)&v75, (struct _RTL_CRITICAL_SECTION *)v28);
            v29 = *(_QWORD *)(v24 + 24);
            v30 = *(_QWORD *)(v24 + 16);
            if ( v29 )
              *(_QWORD *)(v29 + 16) = v30;
            if ( v30 )
              *(_QWORD *)(v30 + 24) = v29;
            v31 = *(_QWORD *)(v28 + 56);
            if ( v31 == v24 )
              *(_QWORD *)(v28 + 56) = *(_QWORD *)(v31 + 16);
            v32 = *(_QWORD *)(v28 + 48);
            if ( v32 == v24 )
              *(_QWORD *)(v28 + 48) = *(_QWORD *)(v32 + 24);
            *(_QWORD *)(v24 + 24) = 0;
            *(_QWORD *)(v24 + 16) = 0;
            *(_QWORD *)(v24 + 24) = *(_QWORD *)(v28 + 48);
            v33 = *(_QWORD *)(v28 + 48);
            if ( v33 )
              *(_QWORD *)(v33 + 16) = v24;
            *(_QWORD *)(v28 + 48) = v24;
            if ( !*(_QWORD *)(v28 + 56) )
              *(_QWORD *)(v28 + 56) = v24;
            *(_DWORD *)(v24 + 320) = GetTickCount();
            *(_DWORD *)(v24 + 324) = 4;
            if ( !*(_QWORD *)(v28 + 80) )
              CreateTimerQueueTimer(
                (PHANDLE)(v28 + 80),
                0,
                CForestCache::staticTimerCallback,
                (PVOID)v28,
                *(_DWORD *)(v28 + 68),
                *(_DWORD *)(v28 + 68),
                0x20u);
            CInCritSec::~CInCritSec((CInCritSec *)&v75);
            v34 = *(_QWORD *)(v24 + 176);
            if ( !v27 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
              v35 = *(struct _IWmiObject **)(v24 + 176);
              CInCritSec::~CInCritSec((CInCritSec *)&v78);
LABEL_49:
              CInCritSec::~CInCritSec((CInCritSec *)v76);
              v73 = v35;
              if ( !v35 )
              {
LABEL_54:
                if ( v26 )
                  *v26 = 1;
                v41 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
                v42 = v41;
                v78 = v41;
                if ( v41 )
                {
                  *v41 = 0;
                  v43 = 2147483646;
                  v44 = L"CD_";
                  v45 = 371;
                  v46 = v42;
                  do
                  {
                    if ( !v43 )
                      break;
                    v47 = *v44;
                    if ( !*v44 )
                      break;
                    ++v44;
                    *v46++ = v47;
                    --v43;
                    --v45;
                  }
                  while ( v45 );
                  v48 = v46 - 1;
                  if ( v45 )
                    v48 = v46;
                  *v48 = 0;
                  if ( A51Hash(a2, v42 + 3) )
                  {
                    v49 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
                    v50 = v49;
                    v76[0] = v49;
                    if ( v49 )
                    {
                      *v49 = 0;
                      v51 = (unsigned __int16 *)*((_QWORD *)this + 7);
                      v52 = v49;
                      for ( i = 0; *v51; ++i )
                      {
                        if ( i >= 0x172 )
                          break;
                        v54 = *v51++;
                        *v52++ = v54;
                      }
                      *v52 = 92;
                      v55 = i + 1;
                      v56 = v52 + 1;
                      if ( v55 >= 0x173 )
                        v56 = v52;
                      if ( *v42 )
                      {
                        v57 = v42;
                        do
                        {
                          if ( v55 >= 0x172 )
                            break;
                          v58 = *v57++;
                          *v56++ = v58;
                          ++v55;
                        }
                        while ( *v57 );
                      }
                      *v56 = 0;
                      v59 = CNamespaceHandle::FileToClass(
                              (struct _RTL_CRITICAL_SECTION ***)this,
                              v50,
                              &v73,
                              v27,
                              v25,
                              a8,
                              a9);
                      if ( v59 < 0 )
                      {
                        if ( v59 == -2147217406 )
                        {
                          CWin32DefaultArena::WbemMemFree(v50);
                          CWin32DefaultArena::WbemMemFree(v42);
                          return 2147749890LL;
                        }
                        else
                        {
                          MemLogObject = GetMemLogObject();
                          CMemoryLog::Write(MemLogObject, v59);
                          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              154,
                              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                              (unsigned int)v59);
                          }
                          CWin32DefaultArena::WbemMemFree(v50);
                          CWin32DefaultArena::WbemMemFree(v42);
                          return (unsigned int)v59;
                        }
                      }
                      else
                      {
                        v60 = v73;
                        v75 = v73;
                        v61 = (**(__int64 (__fastcall ***)(struct _IWmiObject *, const struct _GUID *, void **))v73)(
                                v73,
                                v79,
                                v80);
                        if ( v60 )
                          (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v60 + 16LL))(v60);
                        CWin32DefaultArena::WbemMemFree(v50);
                        CWin32DefaultArena::WbemMemFree(v42);
                        return v61;
                      }
                    }
                    else
                    {
                      v70 = GetMemLogObject();
                      CMemoryLog::Write(v70, -2147217402);
                      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          153,
                          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                          2147749894LL);
                      }
                      CWin32DefaultArena::WbemMemFree(0);
                      CWin32DefaultArena::WbemMemFree(v42);
                      return 2147749894LL;
                    }
                  }
                  else
                  {
                    v68 = GetMemLogObject();
                    CMemoryLog::Write(v68, -2147217393);
                    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        534,
                        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                        2147749903LL);
                    }
                    v69 = GetMemLogObject();
                    CMemoryLog::Write(v69, -2147217393);
                    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        152,
                        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                        2147749903LL);
                    }
                    CWin32DefaultArena::WbemMemFree(v42);
                    return 2147749903LL;
                  }
                }
                else
                {
                  v67 = GetMemLogObject();
                  CMemoryLog::Write(v67, -2147217402);
                  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      151,
                      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                      2147749894LL);
                  }
                  CWin32DefaultArena::WbemMemFree(0);
                  return 2147749894LL;
                }
              }
              v78 = v35;
              v39 = (**(__int64 (__fastcall ***)(struct _IWmiObject *, const struct _GUID *, void **))v35)(
                      v35,
                      v79,
                      v80);
              (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v35 + 16LL))(v35);
              return v39;
            }
            v74 = 0;
            if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 96LL))(v34, &v74) >= 0 )
            {
              v75 = 0;
              (**(void (__fastcall ***)(__int64, GUID *, struct _IWmiObject **))v74)(v74, &IID__IWmiObject, &v75);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
              v35 = v75;
              CInCritSec::~CInCritSec((CInCritSec *)&v78);
              goto LABEL_49;
            }
          }
          CInCritSec::~CInCritSec((CInCritSec *)&v78);
          v35 = 0;
          goto LABEL_49;
        }
        CWin32DefaultArena::WbemMemFree(v16);
      }
      CInCritSec::~CInCritSec((CInCritSec *)&v74);
LABEL_53:
      CInCritSec::~CInCritSec((CInCritSec *)v76);
      v73 = 0;
      v26 = a7;
      v25 = a6;
      v27 = a5;
      goto LABEL_54;
    }
  }
  if ( !*((_QWORD *)this + 12) )
  {
    v78 = 0;
    v39 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, _WORD **))g_pWbemCobjFac->lpVtbl->CreateInstance)(
            g_pWbemCobjFac,
            0,
            &IID__IWmiObject,
            &v78);
    if ( (v39 & 0x80000000) != 0 )
    {
      v65 = GetMemLogObject();
      CMemoryLog::Write(v65, v39);
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v39;
      }
      v64 = 149;
LABEL_84:
      WPP_SF_d(*((_QWORD *)v63 + 2), v64, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v39);
      return v39;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 12, (signed __int64)v78, 0) )
      (*(void (__fastcall **)(_WORD *))(*(_QWORD *)v78 + 16LL))(v78);
  }
  v76[0] = 0;
  v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 12) + 96LL))(*((_QWORD *)this + 12), v76);
  if ( (v39 & 0x80000000) != 0 )
  {
    v62 = GetMemLogObject();
    CMemoryLog::Write(v62, v39);
    v63 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v39;
    }
    v64 = 150;
    goto LABEL_84;
  }
  v72 = v76[0];
  v78 = (_WORD *)v76[0];
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  v66 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v72)(v72, a3, a4);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  return v66;
}

```

## disassembly

```asm
0x180006000  mov     [rsp-40h+arg_18], r9
0x180006005  mov     [rsp-40h+arg_10], r8
0x18000600a  mov     [rsp-40h+arg_0], rcx
0x18000600f  push    rbp
0x180006010  push    rbx
0x180006011  push    rsi
0x180006012  push    rdi
0x180006013  push    r12
0x180006015  push    r13
0x180006017  push    r14
0x180006019  push    r15
0x18000601b  mov     rbp, rsp
0x18000601e  sub     rsp, 68h
0x180006022  mov     rsi, r9
0x180006025  mov     r14, r8
0x180006028  mov     r12, rdx
0x18000602b  mov     rdi, rcx
0x18000602e  lea     r15, WPP_GLOBAL_Control
0x180006035  mov     rcx, cs:WPP_GLOBAL_Control
0x18000603c  cmp     rcx, r15
0x18000603f  jz      short loc_18000604B
0x180006041  test    byte ptr [rcx+1Ch], 1
0x180006045  jnz     loc_18000657B
0x18000604b  test    r12, r12
0x18000604e  jz      loc_1800064FA
0x180006054  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000605b  nop     dword ptr [rax+rax+00h]
0x180006060  inc     rax
0x180006063  cmp     word ptr [r12+rax*2], 0
0x180006069  jnz     short loc_180006060
0x18000606b  test    rax, rax
0x18000606e  jz      loc_1800064FA
0x180006074  xor     esi, esi
0x180006076  mov     [rbp+var_28], rsi
0x18000607a  mov     r13, [rdi+58h]
0x18000607e  mov     rdx, [r13+10h]
0x180006082  lea     rcx, [rbp+var_10]
0x180006086  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000608c  nop
0x18000608d  mov     rdx, [r13+10h]
0x180006091  lea     rcx, [rbp+var_20]
0x180006095  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000609b  nop
0x18000609c  mov     ecx, 84h
0x1800060a1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800060a7  mov     rbx, rax
0x1800060aa  test    rax, rax
0x1800060ad  jz      loc_1800066E8
0x1800060b3  mov     [rbp+arg_8], rax
0x1800060b7  mov     rdx, rax; unsigned __int16 *
0x1800060ba  mov     rcx, r12; unsigned __int16 *
0x1800060bd  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x1800060c2  test    al, al
0x1800060c4  jz      loc_1800066DE
0x1800060ca  mov     r10, [r13+18h]
0x1800060ce  mov     r9, [r10+8]
0x1800060d2  mov     rdi, r10
0x1800060d5  cmp     [r9+19h], sil
0x1800060d9  jnz     short loc_180006120
0x1800060db  nop     dword ptr [rax+rax+00h]
0x1800060e0  mov     rax, [r9+20h]
0x1800060e4  mov     r8, rbx
0x1800060e7  sub     r8, rax
0x1800060ea  nop     word ptr [rax+rax+00h]
0x1800060f0  movzx   edx, word ptr [rax]
0x1800060f3  movzx   ecx, word ptr [rax+r8]
0x1800060f8  sub     edx, ecx
0x1800060fa  jnz     short loc_180006104
0x1800060fc  add     rax, 2
0x180006100  test    ecx, ecx
0x180006102  jnz     short loc_1800060F0
0x180006104  test    edx, edx
0x180006106  jns     loc_180006258
0x18000610c  mov     r9, [r9+10h]
0x180006110  cmp     byte ptr [r9+19h], 0
0x180006115  jz      short loc_1800060E0
0x180006117  cmp     rdi, r10
0x18000611a  jnz     loc_180006263
0x180006120  mov     rdi, rsi
0x180006123  mov     rcx, rbx
0x180006126  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000612c  nop
0x18000612d  lea     rcx, [rbp+var_20]
0x180006131  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180006137  test    rdi, rdi
0x18000613a  jz      loc_18000631D
0x180006140  cmp     [rbp+arg_40], 2
0x180006147  jz      loc_180006310
0x18000614d  mov     r14, [rbp+arg_28]
0x180006151  test    r14, r14
0x180006154  jnz     loc_1800064EB
0x18000615a  mov     rsi, [rbp+arg_30]
0x18000615e  test    rsi, rsi
0x180006161  jnz     loc_1800066F7
0x180006167  mov     rdx, [r13+10h]
0x18000616b  lea     rcx, [rbp+arg_8]
0x18000616f  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180006175  nop
0x180006176  movzx   r15d, [rbp+arg_20]
0x18000617b  cmp     qword ptr [rdi+0B0h], 0
0x180006183  jz      loc_18000660A
0x180006189  mov     rbx, [r13+10h]
0x18000618d  mov     rdx, rbx
0x180006190  lea     rcx, [rbp+var_18]
0x180006194  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000619a  mov     rcx, [rdi+18h]
0x18000619e  mov     rax, [rdi+10h]
0x1800061a2  test    rcx, rcx
0x1800061a5  jz      short loc_1800061AB
0x1800061a7  mov     [rcx+10h], rax
0x1800061ab  test    rax, rax
0x1800061ae  jz      short loc_1800061B4
0x1800061b0  mov     [rax+18h], rcx
0x1800061b4  mov     rax, [rbx+38h]
0x1800061b8  cmp     rax, rdi
0x1800061bb  jz      loc_180006705
0x1800061c1  mov     rax, [rbx+30h]
0x1800061c5  cmp     rax, rdi
0x1800061c8  jnz     short loc_1800061D2
0x1800061ca  mov     rax, [rax+18h]
0x1800061ce  mov     [rbx+30h], rax
0x1800061d2  xor     r13d, r13d
0x1800061d5  mov     [rdi+18h], r13
0x1800061d9  mov     [rdi+10h], r13
0x1800061dd  mov     rax, [rbx+30h]
0x1800061e1  mov     [rdi+18h], rax
0x1800061e5  mov     rax, [rbx+30h]
0x1800061e9  test    rax, rax
0x1800061ec  jz      short loc_1800061F2
0x1800061ee  mov     [rax+10h], rdi
0x1800061f2  mov     [rbx+30h], rdi
0x1800061f6  cmp     [rbx+38h], r13
0x1800061fa  jz      loc_180006712
0x180006200  call    cs:__imp_GetTickCount
0x180006206  mov     [rdi+140h], eax
0x18000620c  mov     dword ptr [rdi+144h], 4
0x180006216  lea     rcx, [rbx+50h]; phNewTimer
0x18000621a  cmp     [rcx], r13
0x18000621d  jz      loc_18000671B
0x180006223  lea     rcx, [rbp+var_18]
0x180006227  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000622d  mov     rcx, [rdi+0B0h]
0x180006234  test    r15b, r15b
0x180006237  jnz     short loc_180006295
0x180006239  mov     rax, [rcx]
0x18000623c  mov     rax, [rax+8]
0x180006240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006245  mov     rdi, [rdi+0B0h]
0x18000624c  lea     rcx, [rbp+arg_8]
0x180006250  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180006256  jmp     short loc_1800062BE
0x180006258  mov     rdi, r9
0x18000625b  mov     r9, [r9]
0x18000625e  jmp     loc_180006110
0x180006263  mov     rax, rbx
0x180006266  mov     r8, [rdi+20h]
0x18000626a  sub     r8, rbx
0x18000626d  nop     dword ptr [rax]
0x180006270  movzx   edx, word ptr [rax]
0x180006273  movzx   ecx, word ptr [rax+r8]
0x180006278  sub     edx, ecx
0x18000627a  jnz     short loc_180006284
0x18000627c  add     rax, 2
0x180006280  test    ecx, ecx
0x180006282  jnz     short loc_180006270
0x180006284  test    edx, edx
0x180006286  js      loc_180006120
0x18000628c  mov     rdi, [rdi+28h]
0x180006290  jmp     loc_180006123
0x180006295  mov     [rbp+var_20], r13
0x180006299  mov     rax, [rcx]
0x18000629c  lea     rdx, [rbp+var_20]
0x1800062a0  mov     rax, [rax+60h]
0x1800062a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a9  test    eax, eax
0x1800062ab  jns     loc_1800065A2
0x1800062b1  lea     rcx, [rbp+arg_8]
0x1800062b5  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800062bb  mov     rdi, r13
0x1800062be  lea     rcx, [rbp+var_10]
0x1800062c2  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800062c8  mov     [rbp+var_28], rdi
0x1800062cc  test    rdi, rdi
0x1800062cf  jz      short loc_18000633B
0x1800062d1  mov     [rbp+arg_8], rdi
0x1800062d5  mov     rax, [rdi]
0x1800062d8  mov     r8, [rbp+arg_18]
0x1800062dc  mov     rdx, [rbp+arg_10]
0x1800062e0  mov     rcx, rdi
0x1800062e3  mov     rax, [rax]
0x1800062e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062eb  mov     ebx, eax
0x1800062ed  mov     rdx, [rdi]
0x1800062f0  mov     rcx, rdi
0x1800062f3  mov     rax, [rdx+10h]
0x1800062f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fc  nop
0x1800062fd  mov     eax, ebx
0x1800062ff  add     rsp, 68h
0x180006303  pop     r15
0x180006305  pop     r14
0x180006307  pop     r13
0x180006309  pop     r12
0x18000630b  pop     rdi
0x18000630c  pop     rsi
0x18000630d  pop     rbx
0x18000630e  pop     rbp
0x18000630f  retn
0x180006310  cmp     byte ptr [rdi+151h], 0
0x180006317  jz      loc_18000614D
0x18000631d  lea     rcx, [rbp+var_10]
0x180006321  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180006327  mov     [rbp+var_28], rsi
0x18000632b  mov     rsi, [rbp+arg_30]
0x18000632f  mov     r14, [rbp+arg_28]
0x180006333  movzx   r15d, [rbp+arg_20]
0x180006338  xor     r13d, r13d
0x18000633b  test    rsi, rsi
0x18000633e  jnz     loc_180006745
0x180006344  mov     ecx, 2E6h
0x180006349  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000634f  mov     rbx, rax
0x180006352  mov     [rbp+arg_8], rax
0x180006356  test    rax, rax
0x180006359  jz      short loc_18000635F
0x18000635b  mov     [rax], r13w
0x18000635f  test    rbx, rbx
0x180006362  jz      loc_18000674D
0x180006368  mov     eax, 7FFFFFFEh
0x18000636d  lea     r8, aCd_0; "CD_"
0x180006374  mov     edx, 173h
0x180006379  mov     rcx, rbx
0x18000637c  nop     dword ptr [rax+00h]
0x180006380  test    rax, rax
0x180006383  jz      short loc_1800063A4
0x180006385  movzx   r9d, word ptr [r8]
0x180006389  test    r9w, r9w
0x18000638d  jz      short loc_1800063A4
0x18000638f  add     r8, 2
0x180006393  mov     [rcx], r9w
0x180006397  add     rcx, 2
0x18000639b  dec     rax
0x18000639e  sub     rdx, 1
0x1800063a2  jnz     short loc_180006380
0x1800063a4  lea     rax, [rcx-2]
0x1800063a8  test    rdx, rdx
0x1800063ab  cmovnz  rax, rcx
0x1800063af  mov     [rax], r13w
0x1800063b3  lea     rdx, [rbx+6]; unsigned __int16 *
0x1800063b7  mov     rcx, r12; unsigned __int16 *
0x1800063ba  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x1800063bf  test    al, al
0x1800063c1  jz      loc_1800067AF
0x1800063c7  mov     ecx, 2E6h
0x1800063cc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800063d2  mov     rdi, rax
0x1800063d5  mov     [rbp+var_10], rax
0x1800063d9  test    rax, rax
0x1800063dc  jz      short loc_1800063E2
0x1800063de  mov     [rax], r13w
0x1800063e2  test    rdi, rdi
0x1800063e5  jz      loc_180006859
0x1800063eb  mov     r10, [rbp+arg_0]
0x1800063ef  mov     r8, [r10+38h]
0x1800063f3  mov     rdx, rdi
0x1800063f6  mov     ecx, r13d
0x1800063f9  cmp     word ptr [r8], 0
0x1800063fe  jz      short loc_180006420
0x180006400  cmp     ecx, 172h
0x180006406  jnb     short loc_180006420
0x180006408  movzx   eax, word ptr [r8]
0x18000640c  add     r8, 2
0x180006410  mov     [rdx], ax
0x180006413  add     rdx, 2
0x180006417  inc     ecx
0x180006419  cmp     word ptr [r8], 0
0x18000641e  jnz     short loc_180006400
0x180006420  mov     word ptr [rdx], 5Ch ; '\'
0x180006425  inc     ecx
0x180006427  lea     r8, [rdx+2]
0x18000642b  cmp     ecx, 173h
0x180006431  cmovnb  r8, rdx
0x180006435  cmp     word ptr [rbx], 0
0x180006439  jz      short loc_18000645D
0x18000643b  mov     rdx, rbx
0x18000643e  cmp     ecx, 172h
0x180006444  jnb     short loc_18000645D
0x180006446  movzx   eax, word ptr [rdx]
0x180006449  add     rdx, 2
0x18000644d  mov     [r8], ax
0x180006451  add     r8, 2
0x180006455  inc     ecx
0x180006457  cmp     word ptr [rdx], 0
0x18000645b  jnz     short loc_18000643E
0x18000645d  mov     [r8], r13w
0x180006461  mov     eax, [rbp+arg_40]
0x180006467  mov     [rsp+68h+Flags], eax; unsigned int
0x18000646b  mov     rax, [rbp+arg_38]
0x180006472  mov     qword ptr [rsp+68h+Period], rax; bool *
0x180006477  mov     qword ptr [rsp+68h+DueTime], r14; __int64 *
  ... truncated ...
```
