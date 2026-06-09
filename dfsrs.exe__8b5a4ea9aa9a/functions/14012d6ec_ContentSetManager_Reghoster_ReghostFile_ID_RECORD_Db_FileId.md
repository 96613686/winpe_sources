# ContentSetManager::Reghoster::ReghostFile(ID_RECORD &,Db *,FileId &)

- ea: `0x14012d6ec`
- end: `0x14012e105`
- name: `?ReghostFile@Reghoster@ContentSetManager@@QEAAPEAVFrsStatus@@AEAVID_RECORD@@PEAVDb@@AEAVFileId@@@Z`
- size: `2585`
- prototype: `struct FrsStatus *(ContentSetManager::Reghoster *__hidden this, struct ID_RECORD *, struct Db *, struct FileId *)`
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x14012d478`
- `0x14012d524`

## callees

- `0x1400036a0`
- `0x14000d980`
- `0x14000dcc0`
- `0x14000e34c`
- `0x140024868`
- `0x140024be4`
- `0x140028fcc`
- `0x14002a6d0`
- `0x14002c1c0`
- `0x14002c548`
- `0x14006d538`
- `0x14006f224`
- `0x1400844fc`
- `0x140085aa0`
- `0x140091bec`
- `0x14009d5e0`
- `0x1400c2ce8`
- `0x1400c3488`
- `0x140110e44`
- `0x14011541c`
- `0x14011788c`
- `0x14012c590`
- `0x14012c808`
- `0x14012c9ac`
- `0x14012d6ec`
- `0x1401af7b0`
- `0x1401b90b4`
- `0x1401b9494`
- `0x1401c9600`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14012d838`
- `KERNEL32!GetCurrentThreadId` at `0x14012d908`
- `KERNEL32!GetCurrentThreadId` at `0x14012dbe4`
- `KERNEL32!GetCurrentThreadId` at `0x14012dc90`
- `KERNEL32!GetCurrentThreadId` at `0x14012dcec`
- `KERNEL32!GetCurrentThreadId` at `0x14012df4f`
- `KERNEL32!GetCurrentThreadId` at `0x14012e062`
- `KERNEL32!GetCurrentThreadId` at `0x14012d838`
- `KERNEL32!GetCurrentThreadId` at `0x14012d908`
- `KERNEL32!GetCurrentThreadId` at `0x14012dbe4`
- `KERNEL32!GetCurrentThreadId` at `0x14012dc90`
- `KERNEL32!GetCurrentThreadId` at `0x14012dcec`
- `KERNEL32!GetCurrentThreadId` at `0x14012df4f`
- `KERNEL32!GetCurrentThreadId` at `0x14012e062`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct FrsStatus *__fastcall ContentSetManager::Reghoster::ReghostFile(
        ContentSetManager::Reghoster *this,
        struct ID_RECORD *a2,
        struct Db *a3,
        struct FileId *a4)
{
  __int64 v7; // rbx
  struct FrsStatus *appended; // rdi
  DWORD v9; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // r8d
  __int64 (__fastcall *v15)(ContentSetManager::Reghoster *, __int64, char *, __int64, int, _DWORD, struct Writer **); // r10
  unsigned int v16; // ecx
  struct Reader *v17; // r12
  struct Writer *v18; // r13
  __int64 v19; // rax
  unsigned int v20; // r9d
  __int64 (__fastcall *v21)(ContentSetManager::Reghoster *, __int64, char *, __int64); // r10
  const struct VolumeId *v22; // rdx
  FrsFilter *v23; // rcx
  const struct FileId *v24; // r8
  union _LARGE_INTEGER *v25; // r9
  __int64 v26; // rax
  int v27; // edx
  __int64 v28; // r8
  _QWORD *v29; // r10
  __int64 v30; // r8
  DWORD v31; // eax
  __int64 v32; // rcx
  DWORD v33; // eax
  __int64 v34; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 (__fastcall *v38)(ContentSetManager::Reghoster *, __int64, __int64 *, __int64); // r10
  __int64 v39; // rax
  __int64 (__fastcall *v40)(ContentSetManager::Reghoster *, __int64, _QWORD *, __int64 *, __int64, __int64 *); // r10
  __int64 v41; // rax
  __int64 (__fastcall *v42)(ContentSetManager::Reghoster *, __int64, __int64 *, __int64 *, __int64, int, _QWORD, int, __int64 *); // r10
  FrsStatus *v43; // rax
  DWORD v44; // eax
  __int64 v45; // rcx
  __int64 v46; // r14
  __int64 v47; // r15
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 (__fastcall *v50)(ContentSetManager::Reghoster *, __int64, char *, __int64); // r10
  DWORD v51; // eax
  __int64 v52; // rcx
  unsigned int v54; // [rsp+20h] [rbp-E0h]
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v56; // [rsp+68h] [rbp-98h] BYREF
  struct FrsStatus *v57; // [rsp+70h] [rbp-90h] BYREF
  struct Reader *v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v60; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+90h] [rbp-70h]
  int v62; // [rsp+94h] [rbp-6Ch]
  const wchar_t *v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+A0h] [rbp-60h] BYREF
  struct Writer *v65; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-48h] BYREF
  struct FrsStatus *v68; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h] BYREF
  void *v70; // [rsp+D0h] [rbp-30h] BYREF
  _FILE_ALLOCATED_RANGE_BUFFER v71; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v72[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v73[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v74[40]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v75[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v76[656]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v77; // [rsp+3E8h] [rbp+2E8h] BYREF
  _QWORD v78[4]; // [rsp+3F0h] [rbp+2F0h] BYREF

  v68 = a4;
  v7 = 0;
  v55 = 0;
  std::wstring::wstring(v73);
  std::wstring::wstring(v74);
  v58 = 0;
  v65 = 0;
  v59 = 0;
  v66 = 0;
  v69 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v75);
  v64 = 0;
  LODWORD(v57) = 0;
  v67 = 0;
  v56 = 0;
  v70 = 0;
  ScopedLock::ScopedLock((ScopedLock *)v72, (struct ScopedCS *)(*((_QWORD *)this + 1) + 1568LL));
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v60 = L"ContentSetManager::Reghoster::ReghostFile";
    v61 = 1458;
    v62 = 4;
    v63 = L"REGH";
    dbgobj::DbgPrint<unsigned short,_GUID,FileId,UID,GVSN,__int64>(
      (unsigned int)&v60,
      (unsigned int)L"REGH",
      *((_QWORD *)this + 1) + 168,
      (_DWORD)a2 + 688,
      (__int64)a2,
      (__int64)a2 + 24,
      (__int64)a2 + 680);
  }
  ContentSetManager::MakeNameFromUpdate(a2, v73);
  appended = ContentSetManager::IsAncestorBeingRenamed(
               *((ContentSetManager **)this + 1),
               (struct ID_RECORD *)((char *)a2 + 688),
               (int *)&v57);
  if ( !appended )
  {
    if ( !(_DWORD)v57
      || (v9 = GetCurrentThreadId(),
          (appended = (struct FrsStatus *)FrsStatusList::PushNewError(
                                            v10,
                                            9062,
                                            0,
                                            3,
                                            "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                            "ContentSetManager::Reghoster::ReghostFile",
                                            1478,
                                            v9,
                                            0)) == 0) )
    {
      appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(ContentSetManager::Reghoster *, __int64, char *, __int64, _QWORD, struct Reader **))(*(_QWORD *)this + 24LL))(
                                       this,
                                       *((_QWORD *)this + 1) + 208LL,
                                       (char *)a2 + 688,
                                       1,
                                       *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 1184LL) + 488LL),
                                       &v58);
      if ( !appended )
      {
        appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Reader *, __int64 *))(*(_QWORD *)v58 + 64LL))(
                                         v58,
                                         &v55);
        if ( !appended )
        {
          if ( v55 == *((_QWORD *)a2 + 85)
            || (v11 = GetCurrentThreadId(),
                (appended = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                  v12,
                                                  9029,
                                                  0,
                                                  3,
                                                  "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                                  "ContentSetManager::Reghoster::ReghostFile",
                                                  1507,
                                                  v11,
                                                  0)) == 0) )
          {
            v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
            appended = (struct FrsStatus *)v15(
                                             this,
                                             *((_QWORD *)this + 1) + 208LL,
                                             (char *)this + 32,
                                             v13,
                                             v14,
                                             0,
                                             &v65);
            if ( !appended )
            {
              v17 = v58;
              v18 = v65;
              appended = Transfer::Run(v16, v58, v65, *((const volatile int **)this + 6));
              if ( !appended )
              {
                (*(void (__fastcall **)(struct Reader *))(*(_QWORD *)v17 + 16LL))(v17);
                appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Writer *))(*(_QWORD *)v18 + 24LL))(v18);
                if ( !appended )
                {
                  appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Writer *, __int64 *))(*(_QWORD *)v65 + 40LL))(
                                                   v65,
                                                   &v59);
                  if ( !appended )
                  {
                    v71.FileOffset.QuadPart = 0;
                    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
                    v54 = v20;
                    appended = (struct FrsStatus *)v21(this, *((_QWORD *)this + 1) + 208LL, (char *)this + 32, v19);
                    if ( !appended )
                    {
                      (*(void (__fastcall **)(struct Reader *, __int64 *))(*(_QWORD *)v58 + 96LL))(v58, &v67);
                      (*(void (__fastcall **)(struct Reader *, unsigned int *))(*(_QWORD *)v58 + 104LL))(v58, &v56);
                      if ( v56 )
                      {
                        v70 = operator_new(saturated_mul(v56, 0x10u));
                        (*(void (__fastcall **)(struct Reader *, void *))(*(_QWORD *)v58 + 112LL))(v58, v70);
                      }
                      appended = FrsFilter::GhostFile(v23, v22, v24, v25, v54, &v71);
                      if ( !appended )
                      {
                        Db::Lock(a3, (const struct FileId *)&v59);
                        appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a3 + 16LL))(
                                                         a3,
                                                         0);
                        if ( appended )
                        {
                          FidLockMan::Unlock((FidLockMan *)(*((_QWORD *)a3 + 1) + 8LL), a3, (const struct FileId *)&v59);
LABEL_53:
                          if ( !appended )
                          {
                            *(_QWORD *)v68 = v59;
                            v46 = *((_QWORD *)this + 1);
                            v47 = v67;
                            ScopedLock::ScopedLock((ScopedLock *)&v60, (struct ScopedCS *)(v46 + 1896));
                            v48 = *(_QWORD *)(v46 + 1952);
                            if ( v48 )
                            {
                              DfsrPerf::IncrementCounter(v48, 35, 1);
                              DfsrPerf::IncrementCounter(*(_QWORD *)(v46 + 1952), 36, v47);
                            }
                            ScopedLock::~ScopedLock((ScopedLock *)&v60);
                          }
                          goto LABEL_57;
                        }
                        v26 = *(_QWORD *)a3;
                        v71.Length.QuadPart = 0;
                        appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, int *, char *, _BYTE *, LARGE_INTEGER *))(v26 + 40))(
                                                         a3,
                                                         &v64,
                                                         (char *)a2 + 688,
                                                         v75,
                                                         &v71.Length);
                        if ( appended )
                        {
LABEL_43:
                          v43 = (FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _QWORD))(*(_QWORD *)a3 + 24LL))(
                                               a3,
                                               0);
                          if ( v43 )
                            appended = FrsStatus::AppendError(v43, appended);
                          goto LABEL_53;
                        }
                        if ( v64 && (unsigned int)ID_RECORD::Alive((ID_RECORD *)v75) )
                        {
                          v29 = (_QWORD *)((char *)a2 + 680);
                          if ( *((_QWORD *)a2 + 86) == v78[0]
                            && *v29 == v77
                            && (unsigned __int8)GVSN::operator==(a2, v75, v28)
                            && (unsigned __int8)GVSN::operator==((char *)a2 + 24, v76, v30) )
                          {
LABEL_28:
                            LODWORD(v57) = 1;
                            if ( (unsigned int)Db::TryLock(
                                                 a3,
                                                 (const struct FileId *)v78,
                                                 (const enum FidLockMan::Type *)&v57)
                              || (v31 = GetCurrentThreadId(),
                                  (appended = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                    v32,
                                                                    9029,
                                                                    0,
                                                                    3,
                                                                    "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                                                    "ContentSetManager::Reghoster::ReghostFile",
                                                                    1666,
                                                                    v31,
                                                                    0)) == 0) )
                            {
                              appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(ContentSetManager::Reghoster *, __int64, _QWORD *, __int64 *, __int64 *, _BYTE *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 208LL))(
                                                               this,
                                                               *((_QWORD *)this + 1) + 208LL,
                                                               v78,
                                                               &v55,
                                                               &v69,
                                                               v74,
                                                               0,
                                                               0,
                                                               0,
                                                               0);
                              if ( !appended )
                              {
                                if ( v55 <= v77
                                  || (v33 = GetCurrentThreadId(),
                                      (appended = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                        v34,
                                                                        9029,
                                                                        0,
                                                                        3,
                                                                        "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                                                        "ContentSetManager::Reghoster::ReghostFile",
                                                                        1701,
                                                                        v33,
                                                                        0)) == 0) )
                                {
                                  v66 = *(_QWORD *)ContentSetManager::GetDeletedFid(*((_QWORD *)this + 1), &v60);
                                  if ( v66
                                    || (CurrentThreadId = GetCurrentThreadId(),
                                        (appended = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                          v36,
                                                                          9051,
                                                                          0,
                                                                          3,
                                                                          "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                                                          "ContentSetManager::Reghoster::ReghostFile",
                                                                          1720,
                                                                          CurrentThreadId,
                                                                          0)) == 0) )
                                  {
                                    v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
                                    v57 = (struct FrsStatus *)v38(this, *((_QWORD *)this + 1) + 208LL, &v66, v37);
                                    CLEAR_ERROR(&v57);
                                    appended = v57;
                                    if ( !v57 )
                                    {
                                      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
                                      appended = (struct FrsStatus *)v40(
                                                                       this,
                                                                       *((_QWORD *)this + 1) + 208LL,
                                                                       v78,
                                                                       &v66,
                                                                       v39,
                                                                       &v55);
                                      if ( !appended )
                                      {
                                        v55 = 0;
                                        v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
                                        appended = (struct FrsStatus *)v42(
                                                                         this,
                                                                         *((_QWORD *)this + 1) + 208LL,
                                                                         &v59,
                                                                         &v69,
                                                                         v41,
                                                                         1,
                                                                         0,
                                                                         1,
                                                                         &v55);
                                        if ( !appended )
                                        {
                                          v78[0] = v59;
                                          v77 = v55;
                                          if ( g_DebugLog
                                            && LODWORD(g_DebugLog[1].LockSemaphore)
                                            && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                                          {
                                            v60 = L"ContentSetManager::Reghoster::ReghostFile";
                                            v61 = 1775;
                                            v62 = 4;
                                            v63 = L"REGH";
                                            dbgobj::DbgPrint<unsigned short,ID_RECORD>(
                                              &v60,
                                              L"LDB Updating ID Record:%?",
                                              v75);
                                          }
                                          appended = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct Db *, _BYTE *, _BYTE *, _QWORD))(*(_QWORD *)a3 + 200LL))(
                                                                           a3,
                                                                           v75,
                                                                           v75,
                                                                           0);
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                            goto LABEL_43;
                          }
                        }
                        else
                        {
                          v29 = (_QWORD *)((char *)a2 + 680);
                        }
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                        {
                          v60 = L"ContentSetManager::Reghoster::ReghostFile";
                          v61 = 1637;
                          v62 = 5;
                          v63 = L"REGH";
                          dbgobj::DbgPrint<unsigned short,FileId,UID,GVSN,__int64,GVSN,__int64>(
                            (unsigned int)&v60,
                            v27,
                            (_DWORD)a2 + 688,
                            (_DWORD)a2,
                            (__int64)a2 + 24,
                            (__int64)v29,
                            (__int64)v76,
                            (__int64)&v77);
                        }
                        v44 = GetCurrentThreadId();
                        appended = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                         v45,
                                                         9029,
                                                         0,
                                                         3,
                                                         "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
                                                         "ContentSetManager::Reghoster::ReghostFile",
                                                         1645,
                                                         v44,
                                                         0);
                        if ( appended )
                          goto LABEL_43;
                        goto LABEL_28;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_57:
  v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
  v68 = (struct FrsStatus *)v50(this, *((_QWORD *)this + 1) + 208LL, (char *)this + 32, v49);
  CLEAR_ERROR(&v68);
  if ( appended )
  {
    v51 = GetCurrentThreadId();
    v7 = FrsStatusList::PushNewError(
           v52,
           *((unsigned int *)appended + 1),
           *((unsigned int *)appended + 2),
           *(unsigned int *)appended,
           "base\\fs\\remotefs\\frs\\src\\sync\\reghost.cpp",
           "ContentSetManager::Reghoster::ReghostFile",
           1832,
           v51,
           appended);
  }
  ScopedLock::~ScopedLock((ScopedLock *)v72);
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v70);
  scoped_any<SimilarityTraitsTableDisk::TraitsDumpStateDisk *,close_delete,null_t,0>::~scoped_any<SimilarityTraitsTableDisk::TraitsDumpStateDisk *,close_delete,null_t,0>(&v65);
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v58);
  std::wstring::~wstring(v74);
  std::wstring::~wstring(v73);
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x14012d6ec  push    rbp
0x14012d6ee  push    rbx
0x14012d6ef  push    rsi
0x14012d6f0  push    rdi
0x14012d6f1  push    r12
0x14012d6f3  push    r13
0x14012d6f5  push    r14
0x14012d6f7  push    r15
0x14012d6f9  lea     rbp, [rsp-328h]
0x14012d701  sub     rsp, 428h
0x14012d708  mov     rax, cs:__security_cookie
0x14012d70f  xor     rax, rsp
0x14012d712  mov     [rbp+360h+var_50], rax
0x14012d719  mov     [rbp+360h+var_3A0], r9
0x14012d71d  mov     r15, r8
0x14012d720  mov     r14, rdx
0x14012d723  mov     rsi, rcx
0x14012d726  xor     ebx, ebx
0x14012d728  mov     [rsp+460h+var_400], rbx
0x14012d72d  lea     rcx, [rbp+360h+var_368]
0x14012d731  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14012d736  nop
0x14012d737  lea     rcx, [rbp+360h+var_348]
0x14012d73b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14012d740  nop
0x14012d741  mov     [rsp+460h+var_3E8], rbx
0x14012d746  mov     [rbp+360h+var_3B8], rbx
0x14012d74a  mov     [rbp+360h+var_3E0], rbx
0x14012d74e  mov     [rbp+360h+var_3B0], rbx
0x14012d752  mov     [rbp+360h+var_398], rbx
0x14012d756  lea     rcx, [rbp+360h+var_320]; this
0x14012d75a  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x14012d75f  mov     [rbp+360h+var_3C0], ebx
0x14012d762  mov     dword ptr [rsp+460h+var_3F0], ebx
0x14012d766  mov     [rbp+360h+var_3A8], rbx
0x14012d76a  mov     [rsp+460h+var_3F8], ebx
0x14012d76e  mov     [rbp+360h+var_390], rbx
0x14012d772  mov     rdx, [rsi+8]
0x14012d776  add     rdx, 620h; struct ScopedCS *
0x14012d77d  lea     rcx, [rbp+360h+var_378]; this
0x14012d781  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14012d786  nop
0x14012d787  lea     rcx, aContentsetmana_2; "ContentSetManager::Reghoster::ReghostFi"...
0x14012d78e  lea     rdx, aRegh; "REGH"
0x14012d795  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14012d79c  test    rax, rax
0x14012d79f  jz      short loc_14012D7F7
0x14012d7a1  cmp     [rax+40h], ebx
0x14012d7a4  jz      short loc_14012D7F7
0x14012d7a6  cmp     dword ptr [rax+38h], 4
0x14012d7aa  jl      short loc_14012D7F7
0x14012d7ac  mov     [rbp+360h+var_3D8], rcx
0x14012d7b0  mov     [rbp+360h+var_3D0], 5B2h
0x14012d7b7  mov     [rbp+360h+var_3CC], 4
0x14012d7be  mov     [rbp+360h+var_3C8], rdx
0x14012d7c2  mov     r8, [rsi+8]
0x14012d7c6  add     r8, 0A8h
0x14012d7cd  lea     rcx, [r14+18h]
0x14012d7d1  lea     r9, [r14+2B0h]
0x14012d7d8  lea     rax, [r14+2A8h]
0x14012d7df  mov     [rsp+460h+var_430], rax
0x14012d7e4  mov     [rsp+460h+var_438], rcx
0x14012d7e9  mov     qword ptr [rsp+460h+var_440], r14
0x14012d7ee  lea     rcx, [rbp+360h+var_3D8]
0x14012d7f2  call    ??$DbgPrint@GU_GUID@@VFileId@@VUID@@VGVSN@@_J@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBVFileId@@AEBVUID@@AEBVGVSN@@AEB_J@Z; dbgobj::DbgPrint<ushort,_GUID,FileId,UID,GVSN,__int64>(ushort const *,_GUID const &,FileId const &,UID const &,GVSN const &,__int64 const &)
0x14012d7f7  lea     rdx, [rbp+360h+var_368]
0x14012d7fb  mov     rcx, r14
0x14012d7fe  call    ?MakeNameFromUpdate@ContentSetManager@@SAXAEBVID_UPDATE@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ContentSetManager::MakeNameFromUpdate(ID_UPDATE const &,std::wstring &)
0x14012d803  lea     r12, [r14+2B0h]
0x14012d80a  lea     r8, [rsp+460h+var_3F0]; int *
0x14012d80f  mov     rdx, r12; struct FileId *
0x14012d812  mov     rcx, [rsi+8]; this
0x14012d816  call    ?IsAncestorBeingRenamed@ContentSetManager@@QEAAPEAVFrsStatus@@AEBVFileId@@AEAH@Z; ContentSetManager::IsAncestorBeingRenamed(FileId const &,int &)
0x14012d81b  mov     rdi, rax
0x14012d81e  lea     r13, aContentsetmana_42; "ContentSetManager::Reghoster::ReghostFi"...
0x14012d825  test    rax, rax
0x14012d828  jnz     loc_14012E023
0x14012d82e  lea     r13d, [rax+3]
0x14012d832  cmp     dword ptr [rsp+460h+var_3F0], ebx
0x14012d836  jz      short loc_14012D889
0x14012d838  call    cs:__imp_GetCurrentThreadId
0x14012d83f  nop     dword ptr [rax+rax+00h]
0x14012d844  mov     [rsp+460h+var_420], rbx
0x14012d849  mov     dword ptr [rsp+460h+var_428], eax
0x14012d84d  mov     dword ptr [rsp+460h+var_430], 5C6h
0x14012d855  lea     rax, aContentsetmana_42; "ContentSetManager::Reghoster::ReghostFi"...
0x14012d85c  mov     [rsp+460h+var_438], rax
0x14012d861  lea     rax, aBaseFsRemotefs_40; "base\\fs\\remotefs\\frs\\src\\sync\\reg"...
0x14012d868  mov     qword ptr [rsp+460h+var_440], rax
0x14012d86d  mov     r9d, r13d
0x14012d870  xor     r8d, r8d
0x14012d873  mov     edx, 2366h
0x14012d878  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012d87d  mov     rdi, rax
0x14012d880  test    rax, rax
0x14012d883  jnz     loc_14012E01C
0x14012d889  mov     rax, [rsi]
0x14012d88c  mov     r10, [rax+18h]
0x14012d890  mov     rcx, [rsi+8]
0x14012d894  mov     rax, [rcx+4A0h]
0x14012d89b  mov     r8, [rax+1E8h]
0x14012d8a2  lea     rdx, [rcx+0D0h]
0x14012d8a9  lea     rax, [rsp+460h+var_3E8]
0x14012d8ae  mov     [rsp+460h+var_438], rax
0x14012d8b3  mov     qword ptr [rsp+460h+var_440], r8
0x14012d8b8  mov     r9d, 1
0x14012d8be  mov     r8, r12
0x14012d8c1  mov     rcx, rsi
0x14012d8c4  mov     rax, r10
0x14012d8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012d8cc  mov     rdi, rax
0x14012d8cf  test    rax, rax
0x14012d8d2  jnz     loc_14012E01C
0x14012d8d8  mov     rcx, [rsp+460h+var_3E8]
0x14012d8dd  mov     rax, [rcx]
0x14012d8e0  lea     rdx, [rsp+460h+var_400]
0x14012d8e5  mov     rax, [rax+40h]
0x14012d8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012d8ee  mov     rdi, rax
0x14012d8f1  test    rax, rax
0x14012d8f4  jnz     loc_14012E01C
0x14012d8fa  mov     rax, [r14+2A8h]
0x14012d901  cmp     [rsp+460h+var_400], rax
0x14012d906  jz      short loc_14012D959
0x14012d908  call    cs:__imp_GetCurrentThreadId
0x14012d90f  nop     dword ptr [rax+rax+00h]
0x14012d914  mov     [rsp+460h+var_420], rbx
0x14012d919  mov     dword ptr [rsp+460h+var_428], eax
0x14012d91d  mov     dword ptr [rsp+460h+var_430], 5E3h
0x14012d925  lea     rax, aContentsetmana_42; "ContentSetManager::Reghoster::ReghostFi"...
0x14012d92c  mov     [rsp+460h+var_438], rax
0x14012d931  lea     rax, aBaseFsRemotefs_40; "base\\fs\\remotefs\\frs\\src\\sync\\reg"...
0x14012d938  mov     qword ptr [rsp+460h+var_440], rax
0x14012d93d  mov     r9d, r13d
0x14012d940  xor     r8d, r8d
0x14012d943  mov     edx, 2345h
0x14012d948  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012d94d  mov     rdi, rax
0x14012d950  test    rax, rax
0x14012d953  jnz     loc_14012E01C
0x14012d959  mov     rax, [rsi]
0x14012d95c  mov     r10, [rax+20h]
0x14012d960  mov     r8d, [r14+94h]
0x14012d967  lea     rcx, [rbp+360h+var_368]
0x14012d96b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14012d970  mov     rdx, [rsi+8]
0x14012d974  add     rdx, 0D0h
0x14012d97b  lea     r9, [rbp+360h+var_3B8]
0x14012d97f  mov     [rsp+460h+var_430], r9
0x14012d984  mov     dword ptr [rsp+460h+var_438], ebx
0x14012d988  mov     [rsp+460h+var_440], r8d
0x14012d98d  mov     r9, rax
0x14012d990  lea     r8, [rsi+20h]
0x14012d994  mov     rcx, rsi
0x14012d997  mov     rax, r10
0x14012d99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012d99f  mov     rdi, rax
0x14012d9a2  test    rax, rax
0x14012d9a5  jnz     loc_14012E01C
0x14012d9ab  mov     r12, [rsp+460h+var_3E8]
0x14012d9b0  mov     r13, [rbp+360h+var_3B8]
0x14012d9b4  mov     r9, [rsi+30h]; volatile int *
0x14012d9b8  mov     r8, r13; struct Writer *
0x14012d9bb  mov     rdx, r12; struct Reader *
0x14012d9be  call    ?Run@Transfer@@SAPEAVFrsStatus@@KPEAVReader@@PEAVWriter@@AEDH@Z; Transfer::Run(ulong,Reader *,Writer *,int const volatile &)
0x14012d9c3  mov     rdi, rax
0x14012d9c6  test    rax, rax
0x14012d9c9  jnz     loc_14012E01C
0x14012d9cf  mov     rax, [r12]
0x14012d9d3  mov     rcx, r12
0x14012d9d6  mov     rax, [rax+10h]
0x14012d9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012d9df  mov     rax, [r13+0]
0x14012d9e3  mov     rcx, r13
0x14012d9e6  mov     rax, [rax+18h]
0x14012d9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012d9ef  mov     rdi, rax
0x14012d9f2  test    rax, rax
0x14012d9f5  jnz     loc_14012E01C
0x14012d9fb  mov     rcx, [rbp+360h+var_3B8]
0x14012d9ff  mov     rax, [rcx]
0x14012da02  lea     rdx, [rbp+360h+var_3E0]
0x14012da06  mov     rax, [rax+28h]
0x14012da0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012da0f  mov     rdi, rax
0x14012da12  test    rax, rax
0x14012da15  jnz     loc_14012E01C
0x14012da1b  mov     qword ptr [rbp+360h+var_388.FileOffset], rbx
0x14012da1f  mov     rax, [rsi]
0x14012da22  mov     r10, [rax+0A0h]
0x14012da29  mov     r9d, [r14+94h]
0x14012da30  lea     rcx, [rbp+360h+var_368]
0x14012da34  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14012da39  mov     rdx, [rsi+8]
0x14012da3d  add     rdx, 0D0h
0x14012da44  lea     rcx, [rbp+360h+var_388]
0x14012da48  mov     [rsp+460h+var_438], rcx; struct _FILE_ALLOCATED_RANGE_BUFFER *
0x14012da4d  mov     [rsp+460h+var_440], r9d; unsigned int
0x14012da52  mov     r9, rax
0x14012da55  lea     r8, [rsi+20h]
0x14012da59  mov     rcx, rsi
0x14012da5c  mov     rax, r10
0x14012da5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012da64  mov     rdi, rax
0x14012da67  test    rax, rax
0x14012da6a  jnz     loc_14012E01C
0x14012da70  mov     rcx, [rsp+460h+var_3E8]
0x14012da75  mov     rax, [rcx]
0x14012da78  lea     rdx, [rbp+360h+var_3A8]
0x14012da7c  mov     rax, [rax+60h]
0x14012da80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012da85  mov     rcx, [rsp+460h+var_3E8]
0x14012da8a  mov     rax, [rcx]
0x14012da8d  lea     rdx, [rsp+460h+var_3F8]
0x14012da92  mov     rax, [rax+68h]
0x14012da96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012da9b  cmp     [rsp+460h+var_3F8], ebx
0x14012da9f  jz      short loc_14012DAD3
0x14012daa1  mov     ecx, [rsp+460h+var_3F8]
0x14012daa5  lea     eax, [rdi+10h]
0x14012daa8  mul     rcx
0x14012daab  lea     rcx, [rdi-1]
0x14012daaf  cmovo   rax, rcx
0x14012dab3  mov     rcx, rax; unsigned __int64
0x14012dab6  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x14012dabb  mov     rdx, rax
0x14012dabe  mov     [rbp+360h+var_390], rax
0x14012dac2  mov     rcx, [rsp+460h+var_3E8]
0x14012dac7  mov     rax, [rcx]
0x14012daca  mov     rax, [rax+70h]
0x14012dace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012dad3  call    ?GhostFile@FrsFilter@@QEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@AEAT_LARGE_INTEGER@@KPEAU_FILE_ALLOCATED_RANGE_BUFFER@@@Z; FrsFilter::GhostFile(VolumeId const &,FileId const &,_LARGE_INTEGER &,ulong,_FILE_ALLOCATED_RANGE_BUFFER *)
0x14012dad8  mov     rdi, rax
0x14012dadb  test    rax, rax
0x14012dade  jnz     loc_14012E01C
0x14012dae4  lea     rdx, [rbp+360h+var_3E0]; struct FileId *
0x14012dae8  mov     rcx, r15; this
0x14012daeb  call    ?Lock@Db@@QEAAXAEBVFileId@@@Z; Db::Lock(FileId const &)
0x14012daf0  mov     rax, [r15]
0x14012daf3  xor     edx, edx
0x14012daf5  mov     rcx, r15
0x14012daf8  mov     rax, [rax+10h]
0x14012dafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012db01  mov     rdi, rax
0x14012db04  test    rax, rax
0x14012db07  jnz     loc_14012DFAB
0x14012db0d  mov     rax, [r15]
0x14012db10  mov     qword ptr [rbp+360h+var_388.Length], rbx
0x14012db14  lea     rcx, [rbp+360h+var_388.Length]
0x14012db18  mov     qword ptr [rsp+460h+var_440], rcx
0x14012db1d  lea     r9, [rbp+360h+var_320]
0x14012db21  lea     r12, [r14+2B0h]
0x14012db28  mov     r8, r12
0x14012db2b  lea     rdx, [rbp+360h+var_3C0]
0x14012db2f  mov     rcx, r15
0x14012db32  mov     rax, [rax+28h]
0x14012db36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012db3b  mov     rdi, rax
0x14012db3e  test    rax, rax
0x14012db41  jnz     loc_14012DEAE
0x14012db47  cmp     [rbp+360h+var_3C0], ebx
0x14012db4a  jz      loc_14012DEDB
0x14012db50  lea     rcx, [rbp+360h+var_320]; this
0x14012db54  call    ?Alive@ID_RECORD@@QEBAHXZ; ID_RECORD::Alive(void)
0x14012db59  test    eax, eax
0x14012db5b  jz      loc_14012DEDB
0x14012db61  mov     rax, [rbp+360h+var_70]
0x14012db68  lea     r10, [r14+2A8h]
0x14012db6f  cmp     [r12], rax
0x14012db73  jnz     loc_14012DEE2
0x14012db79  mov     rax, [rbp+360h+var_78]
0x14012db80  cmp     [r10], rax
0x14012db83  jnz     loc_14012DEE2
0x14012db89  lea     rdx, [rbp+360h+var_320]
0x14012db8d  mov     rcx, r14
0x14012db90  call    ??8GVSN@@QEBA_NAEBV0@@Z; GVSN::operator==(GVSN const &)
0x14012db95  test    al, al
0x14012db97  jz      loc_14012DEE2
0x14012db9d  lea     rcx, [r14+18h]
0x14012dba1  lea     rdx, [rbp+360h+var_308]
0x14012dba5  call    ??8GVSN@@QEBA_NAEBV0@@Z; GVSN::operator==(GVSN const &)
0x14012dbaa  test    al, al
0x14012dbac  jz      loc_14012DEE2
0x14012dbb2  lea     r14d, [rdi+3]
0x14012dbb6  lea     r12, aContentsetmana_42; "ContentSetManager::Reghoster::ReghostFi"...
0x14012dbbd  lea     r13, aBaseFsRemotefs_40; "base\\fs\\remotefs\\frs\\src\\sync\\reg"...
0x14012dbc4  mov     dword ptr [rsp+460h+var_3F0], 1
0x14012dbcc  lea     r8, [rsp+460h+var_3F0]; enum FidLockMan::Type *
0x14012dbd1  lea     rdx, [rbp+360h+var_70]; struct FileId *
0x14012dbd8  mov     rcx, r15; this
0x14012dbdb  call    ?TryLock@Db@@QEAAHAEBVFileId@@AEBW4Type@FidLockMan@@@Z; Db::TryLock(FileId const &,FidLockMan::Type const &)
0x14012dbe0  test    eax, eax
0x14012dbe2  jnz     short loc_14012DC27
0x14012dbe4  call    cs:__imp_GetCurrentThreadId
0x14012dbeb  nop     dword ptr [rax+rax+00h]
0x14012dbf0  mov     [rsp+460h+var_420], rbx
0x14012dbf5  mov     dword ptr [rsp+460h+var_428], eax
0x14012dbf9  mov     dword ptr [rsp+460h+var_430], 682h
0x14012dc01  mov     [rsp+460h+var_438], r12
0x14012dc06  mov     qword ptr [rsp+460h+var_440], r13
  ... truncated ...
```
