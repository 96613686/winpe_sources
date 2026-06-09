# WorkThreadManager::s_QueuePoolTaskUnderLock(void *,Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *,WorkThreadManager::TaskList *,WorkThreadManager::CThread * *,ulong &)

- ea: `0x180032b10`
- end: `0x18003304e`
- name: `?s_QueuePoolTaskUnderLock@WorkThreadManager@@CAJPEAXW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@PEAVTaskList@1@PEAPEAVCThread@1@AEAK@Z`
- size: `1342`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004950`

## callees

- `0x1800046e0`
- `0x180004890`
- `0x180007880`
- `0x180009740`
- `0x18000a0ac`
- `0x18000b018`
- `0x18000bcf4`
- `0x18000bd6c`
- `0x18000c3f4`
- `0x18000c548`
- `0x18000c5f0`
- `0x18000c648`
- `0x18000e044`
- `0x18000e7a8`
- `0x180031730`
- `0x180032b10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180032bb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180032bb8`

## string_xrefs

- `0x180032d15`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180032e42`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180032f8f`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::s_QueuePoolTaskUnderLock(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        WorkThreadManager::TaskList *a6,
        _QWORD *a7,
        PVOID pv)
{
  _QWORD *v8; // r12
  _DWORD *v10; // r14
  unsigned int v11; // r13d
  _QWORD *i; // rdi
  DWORD TickCount; // eax
  char *v15; // rbx
  PVOID *v16; // r12
  int v17; // r10d
  bool v18; // r14
  char *v19; // rdi
  char *v20; // rcx
  __int64 v21; // r9
  char v22; // r11
  WorkThreadManager::TaskList *v23; // r8
  struct WorkThreadManager::TaskData *v24; // rax
  int v25; // ebx
  volatile int *v26; // rdx
  __int64 v27; // rdx
  int v29; // ecx
  unsigned __int64 v30; // rax
  int v31; // edi
  int v32; // eax
  char *v33; // rdi
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // rax
  int started; // eax
  volatile int *v38; // rdx
  __int64 v39; // rax
  int v40; // [rsp+28h] [rbp-D9h]
  int v41; // [rsp+28h] [rbp-D9h]
  int v42; // [rsp+30h] [rbp-D1h]
  int v43; // [rsp+30h] [rbp-D1h]
  __int16 v44; // [rsp+38h] [rbp-C9h]
  DWORD v45; // [rsp+3Ch] [rbp-C5h]
  __int64 v46; // [rsp+40h] [rbp-C1h]
  int v47; // [rsp+44h] [rbp-BDh]
  unsigned __int64 v48; // [rsp+50h] [rbp-B1h]
  __int64 v49; // [rsp+58h] [rbp-A9h]
  __int64 v50; // [rsp+60h] [rbp-A1h]
  char *v51; // [rsp+68h] [rbp-99h]
  _BYTE v52[72]; // [rsp+70h] [rbp-91h] BYREF
  _BYTE v53[128]; // [rsp+B8h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+3Fh]
  __int64 v55; // [rsp+148h] [rbp+47h]
  unsigned int v56; // [rsp+150h] [rbp+4Fh] BYREF
  unsigned int v57; // [rsp+158h] [rbp+57h] BYREF

  v57 = a3;
  v56 = a2;
  v55 = a1;
  v8 = a7;
  v10 = pv;
  v11 = a4;
  *a7 = 0;
  *v10 = 0;
  HIDWORD(v46) = a3 & 2;
  if ( (a3 & 2) != 0 )
  {
    for ( i = WorkThreadManager::s_pThreadList; ; i = (_QWORD *)i[2] )
    {
      if ( !i )
        goto LABEL_11;
      if ( *((_DWORD *)i + 38) == (_DWORD)a4
        && i[24]
        && (a2 == *((_DWORD *)i + 18) || a2 == 3)
        && ((*((_BYTE *)i + 76) ^ (unsigned __int8)a3) & 0xB) == 0
        && (*((_BYTE *)i + 148) & 2) != 0 )
      {
        break;
      }
    }
    if ( (a3 & 0x100) != 0 )
    {
      v23 = (WorkThreadManager::TaskList *)(i + 3);
      while ( *(WorkThreadManager::TaskList **)v23 != v23 )
      {
        v24 = WorkThreadManager::TaskList::RawRemoveHead(v23);
        WorkThreadManager::TaskList::PushBack(a6, v24);
      }
      LODWORD(a1) = v55;
    }
    v41 = a1;
    WorkThreadManager::TaskData::TaskData(v52, a2, a3, a4);
    v25 = WorkThreadManager::TaskList::PushBack((WorkThreadManager::TaskList *)(i + 3));
    WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v52);
    if ( v25 >= 0 )
    {
      if ( *((int *)i + 11) < 0 )
      {
        *v8 = i;
        Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)((char *)i + 12), v26);
      }
      *v10 = *((_DWORD *)i + 20);
      return 0;
    }
    v27 = 1211;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v25,
      v41);
    return (unsigned int)v25;
  }
LABEL_11:
  if ( (a3 & 0x13) != 0 || (LOBYTE(v44) = 1, a1) )
    LOBYTE(v44) = 0;
  TickCount = GetTickCount();
  v15 = (char *)WorkThreadManager::s_pThreadList;
  v16 = &WorkThreadManager::s_pThreadList;
  v17 = dword_1800497CC;
  v45 = TickCount;
  v18 = (a3 & 0x200) != 0;
  v51 = 0;
  if ( WorkThreadManager::s_pThreadList )
  {
    v50 = 0;
    LODWORD(v46) = a3 & 4;
    v48 = 0;
    HIBYTE(v44) = a3 & 1;
    v49 = 0;
    while ( 1 )
    {
      v19 = v15;
      if ( (unsigned __int8)WorkThreadManager::CThread::Eligible(v15, a2, a3) )
      {
        if ( *((_QWORD *)v15 + 24) || v15[88] )
        {
          if ( !v21 || v15[40] )
            v51 = v15;
          if ( *((_DWORD *)v15 + 38) == v11 )
          {
            if ( byte_1800491BC && v17 == *((_DWORD *)v15 + 20) )
            {
              dword_1800497CC = 0;
              v17 = 0;
              if ( *((char **)v15 + 3) == v15 + 24 )
              {
                v29 = v55;
                if ( !v55 && *((int *)v15 + 21) <= 1 )
                {
                  WorkThreadManager::TaskData::TaskData(v52, a2, a3, v11);
                  v31 = WorkThreadManager::TaskList::PushBack((WorkThreadManager::TaskList *)(v15 + 24));
                  WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v52);
                  if ( v31 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x4FC,
                      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
                      (const char *)(unsigned int)v31,
                      0);
                    return (unsigned int)v31;
                  }
                  WorkThreadManager::CThread::CheckForDeadlock(v15);
                  v32 = *((_DWORD *)v15 + 20);
                  goto LABEL_84;
                }
                v19 = v15;
                goto LABEL_51;
              }
              v19 = v20;
            }
            v29 = v55;
LABEL_51:
            if ( v22 )
            {
              v30 = v48;
              if ( v45 - *((_DWORD *)v15 + 54) < 0xBB8 )
                v30 = ++v48;
              if ( (unsigned __int64)++v50 >= 0x64 || v30 >= 8 )
              {
                v41 = v29;
                WorkThreadManager::TaskData::TaskData(v52, a2, a3, v11);
                v25 = WorkThreadManager::TaskList::PushBack((WorkThreadManager::TaskList *)&WorkThreadManager::s_taskFloodingList);
                WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v52);
                if ( v25 < 0 )
                {
                  v27 = 1308;
                  goto LABEL_34;
                }
                WorkThreadManager::s_EnsureFloodingListWatchdogUnderLock();
                return 0;
              }
            }
          }
          v18 = 1;
          goto LABEL_57;
        }
        if ( *((int *)v15 + 21) <= 1 )
          goto LABEL_66;
        if ( *((_DWORD *)v15 + 38) == v11 )
        {
          if ( HIBYTE(v44) && (v15[148] & 1) != 0 )
            goto LABEL_66;
          if ( (a3 & 4) != 0 && (v15[148] & 4) != 0 && ++v49 == 30 )
            goto LABEL_66;
        }
      }
LABEL_57:
      v16 = (PVOID *)(v15 + 16);
      v15 = (char *)*((_QWORD *)v15 + 2);
      if ( !v15 )
        goto LABEL_66;
    }
  }
  v19 = 0;
LABEL_66:
  if ( !*v16 )
  {
    Microsoft::WRL::Details::Make<WorkThreadManager::CThread,enum Windows::Internal::TaskApartment &,enum Windows::Internal::TaskOptions &>(
      &pv,
      &v56,
      &v57);
    v33 = (char *)pv;
    if ( !pv )
    {
      v25 = -2147024882;
      v34 = 1354;
      v35 = 2147942414LL;
LABEL_78:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)v35,
        v40);
      Microsoft::WRL::ComPtr<WorkThreadManager::CDelayedTaskLifetime>::InternalRelease(&pv);
      return (unsigned int)v25;
    }
    v42 = a5;
    v36 = WorkThreadManager::TaskData::TaskData(v53, a2, a3, v11);
    WorkThreadManager::CThread::SetThreadTask(v33, v52, v36, v45, v55, v42, v44, v46);
    WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v52);
    WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v53);
    if ( !v18 || v47 )
    {
      started = WorkThreadManager::CThread::StartThread((WorkThreadManager::CThread *)v33);
      v25 = started;
      if ( started < 0 )
      {
        v34 = 1372;
        goto LABEL_77;
      }
      *a7 = v33;
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v33 + 12), v38);
    }
    else
    {
      if ( v51 )
        v51[40] = 1;
      started = WorkThreadManager::CThread::StartThreadWithFallback((WorkThreadManager::CThread *)v33);
      v25 = started;
      if ( started < 0 )
      {
        v34 = 1368;
LABEL_77:
        v35 = (unsigned int)started;
        goto LABEL_78;
      }
    }
    pv = 0;
    *v16 = v33;
    Microsoft::WRL::ComPtr<WorkThreadManager::CDelayedTaskLifetime>::InternalRelease(&pv);
    return 0;
  }
  if ( v17 == *((_DWORD *)v19 + 20) )
    dword_1800497CC = 0;
  v43 = a5;
  v39 = WorkThreadManager::TaskData::TaskData(v52, a2, a3, v11);
  WorkThreadManager::CThread::SetThreadTask(v19, v53, v39, v45, v55, v43, v44, v46);
  WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v53);
  WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)v52);
  v32 = *((_DWORD *)v19 + 20);
LABEL_84:
  *(_DWORD *)pv = v32;
  return 0;
}

```

## disassembly

```asm
0x180032b10  mov     rax, rsp
0x180032b13  mov     [rax+20h], rbx
0x180032b17  mov     [rax+18h], r8d
0x180032b1b  mov     [rax+10h], edx
0x180032b1e  mov     [rax+8], rcx
0x180032b22  push    rbp
0x180032b23  push    rsi
0x180032b24  push    rdi
0x180032b25  push    r12
0x180032b27  push    r13
0x180032b29  push    r14
0x180032b2b  push    r15
0x180032b2d  lea     rbp, [rax-3Fh]
0x180032b31  sub     rsp, 100h
0x180032b38  mov     r12, [rbp+37h+arg_30]
0x180032b3c  mov     r15d, edx
0x180032b3f  mov     r14, [rbp+37h+pv]
0x180032b43  xor     edx, edx
0x180032b45  mov     eax, r8d
0x180032b48  mov     r13d, r9d
0x180032b4b  and     eax, 2
0x180032b4e  mov     esi, r8d
0x180032b51  mov     [r12], rdx
0x180032b55  mov     [r14], edx
0x180032b58  mov     [rsp+3Ch], eax
0x180032b5c  jz      short loc_180032BA4
0x180032b5e  mov     rdi, cs:?s_pThreadList@WorkThreadManager@@0PEAVCThread@1@EA; WorkThreadManager::CThread * WorkThreadManager::s_pThreadList
0x180032b65  jmp     short loc_180032B9F
0x180032b67  cmp     [rdi+98h], r13d
0x180032b6e  jnz     short loc_180032B9B
0x180032b70  cmp     [rdi+0C0h], rdx
0x180032b77  jz      short loc_180032B9B
0x180032b79  cmp     r15d, [rdi+48h]
0x180032b7d  jz      short loc_180032B85
0x180032b7f  cmp     r15d, 3
0x180032b83  jnz     short loc_180032B9B
0x180032b85  mov     eax, esi
0x180032b87  xor     eax, [rdi+4Ch]
0x180032b8a  test    al, 0Bh
0x180032b8c  jnz     short loc_180032B9B
0x180032b8e  test    byte ptr [rdi+94h], 2
0x180032b95  jnz     loc_180032CA9
0x180032b9b  mov     rdi, [rdi+10h]
0x180032b9f  test    rdi, rdi
0x180032ba2  jnz     short loc_180032B67
0x180032ba4  test    sil, 13h
0x180032ba8  jnz     short loc_180032BB4
0x180032baa  mov     byte ptr [rsp+130h+var_100], 1
0x180032baf  test    rcx, rcx
0x180032bb2  jz      short loc_180032BB8
0x180032bb4  mov     byte ptr [rsp+130h+var_100], dl
0x180032bb8  call    cs:__imp_GetTickCount
0x180032bbe  mov     rbx, cs:?s_pThreadList@WorkThreadManager@@0PEAVCThread@1@EA; WorkThreadManager::CThread * WorkThreadManager::s_pThreadList
0x180032bc5  lea     r12, ?s_pThreadList@WorkThreadManager@@0PEAVCThread@1@EA; WorkThreadManager::CThread * WorkThreadManager::s_pThreadList
0x180032bcc  mov     r10d, cs:dword_1800497CC
0x180032bd3  xor     edx, edx
0x180032bd5  mov     r14d, esi
0x180032bd8  mov     [rsp+130h+var_FC], eax
0x180032bdc  shr     r14d, 9
0x180032be0  mov     r9d, edx
0x180032be3  and     r14b, 1
0x180032be7  mov     [rsp+130h+var_D0], rdx
0x180032bec  test    rbx, rbx
0x180032bef  jz      loc_180032EC1
0x180032bf5  mov     r11b, byte ptr [rsp+130h+var_100]
0x180032bfa  mov     eax, esi
0x180032bfc  and     eax, 4
0x180032bff  mov     [rsp+130h+var_D8], rdx
0x180032c04  mov     [rsp+38h], eax
0x180032c08  mov     al, sil
0x180032c0b  and     al, 1
0x180032c0d  mov     [rsp+130h+var_E8], rdx
0x180032c12  mov     byte ptr [rsp+130h+var_100+1], al
0x180032c16  mov     [rsp+130h+var_E0], rdx
0x180032c1b  mov     r8d, esi
0x180032c1e  mov     edx, r15d
0x180032c21  mov     rcx, rbx
0x180032c24  mov     rdi, rbx
0x180032c27  call    ?Eligible@CThread@WorkThreadManager@@QEBA_NW4TaskApartment@Internal@Windows@@W4TaskOptions@45@@Z; WorkThreadManager::CThread::Eligible(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions)
0x180032c2c  xor     edx, edx
0x180032c2e  test    al, al
0x180032c30  jz      loc_180032DEC
0x180032c36  cmp     [rbx+0C0h], rdx
0x180032c3d  jnz     loc_180032D49
0x180032c43  cmp     [rbx+58h], dl
0x180032c46  jnz     loc_180032D49
0x180032c4c  cmp     dword ptr [rbx+54h], 1
0x180032c50  jle     loc_180032EC4
0x180032c56  cmp     [rbx+98h], r13d
0x180032c5d  jnz     loc_180032DEC
0x180032c63  cmp     byte ptr [rsp+130h+var_100+1], dl
0x180032c67  jz      short loc_180032C76
0x180032c69  test    byte ptr [rbx+94h], 1
0x180032c70  jnz     loc_180032EC4
0x180032c76  cmp     [rsp+38h], edx
0x180032c7a  jz      loc_180032DEC
0x180032c80  test    byte ptr [rbx+94h], 4
0x180032c87  jz      loc_180032DEC
0x180032c8d  mov     rax, [rsp+130h+var_E0]
0x180032c92  inc     rax
0x180032c95  mov     [rsp+130h+var_E0], rax
0x180032c9a  cmp     rax, 1Eh
0x180032c9e  jz      loc_180032EC4
0x180032ca4  jmp     loc_180032DEC
0x180032ca9  bt      esi, 8
0x180032cad  jnb     short loc_180032CD2
0x180032caf  lea     r8, [rdi+18h]
0x180032cb3  cmp     [r8], r8
0x180032cb6  jz      short loc_180032CCE
0x180032cb8  mov     rcx, r8; this
0x180032cbb  call    ?RawRemoveHead@TaskList@WorkThreadManager@@AEAAPEAUTaskData@2@XZ; WorkThreadManager::TaskList::RawRemoveHead(void)
0x180032cc0  mov     rcx, [rbp+37h+arg_28]; this
0x180032cc4  mov     rdx, rax; struct WorkThreadManager::TaskData *
0x180032cc7  call    ?PushBack@TaskList@WorkThreadManager@@QEAAXPEAUTaskData@2@@Z; WorkThreadManager::TaskList::PushBack(WorkThreadManager::TaskData *)
0x180032ccc  jmp     short loc_180032CB3
0x180032cce  mov     rcx, qword ptr [rbp+37h+arg_0]
0x180032cd2  mov     rax, [rbp+37h+arg_20]
0x180032cd6  mov     r8d, esi
0x180032cd9  mov     qword ptr [rsp+130h+var_108], rax
0x180032cde  mov     edx, r15d
0x180032ce1  mov     qword ptr [rsp+130h+var_110], rcx; int
0x180032ce6  lea     rcx, [rsp+130h+var_C8]
0x180032ceb  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x180032cf0  mov     rdx, rax
0x180032cf3  lea     rcx, [rdi+18h]; this
0x180032cf7  call    ?PushBack@TaskList@WorkThreadManager@@QEAAJ$$QEAUTaskData@2@@Z; WorkThreadManager::TaskList::PushBack(WorkThreadManager::TaskData &&)
0x180032cfc  lea     rcx, [rsp+130h+var_C8]; this
0x180032d01  mov     ebx, eax
0x180032d03  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180032d08  test    ebx, ebx
0x180032d0a  jns     short loc_180032D2B
0x180032d0c  mov     edx, 4BBh; void *
0x180032d11  mov     rcx, [rbp+3Fh]; this
0x180032d15  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180032d1c  mov     r9d, ebx; char *
0x180032d1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d24  mov     eax, ebx
0x180032d26  jmp     loc_180033033
0x180032d2b  cmp     dword ptr [rdi+2Ch], 0
0x180032d2f  jge     short loc_180032D3E
0x180032d31  lea     rcx, [rdi+0Ch]; this
0x180032d35  mov     [r12], rdi
0x180032d39  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180032d3e  mov     eax, [rdi+50h]
0x180032d41  mov     [r14], eax
0x180032d44  jmp     loc_180033031
0x180032d49  test    r9, r9
0x180032d4c  jz      short loc_180032D53
0x180032d4e  cmp     [rbx+28h], dl
0x180032d51  jz      short loc_180032D5B
0x180032d53  mov     r9, rbx
0x180032d56  mov     [rsp+130h+var_D0], rbx
0x180032d5b  cmp     [rbx+98h], r13d
0x180032d62  jnz     loc_180032DE9
0x180032d68  cmp     cs:byte_1800491BC, dl
0x180032d6e  jz      short loc_180032D9F
0x180032d70  cmp     r10d, [rbx+50h]
0x180032d74  jnz     short loc_180032D9F
0x180032d76  lea     rdi, [rbx+18h]
0x180032d7a  mov     cs:dword_1800497CC, edx
0x180032d80  mov     r10d, edx
0x180032d83  cmp     [rdi], rdi
0x180032d86  jnz     short loc_180032D9C
0x180032d88  mov     rcx, qword ptr [rbp+37h+arg_0]
0x180032d8c  test    rcx, rcx
0x180032d8f  jnz     short loc_180032D97
0x180032d91  cmp     dword ptr [rbx+54h], 1
0x180032d95  jle     short loc_180032E02
0x180032d97  mov     rdi, rbx
0x180032d9a  jmp     short loc_180032DA3
0x180032d9c  mov     rdi, rcx
0x180032d9f  mov     rcx, qword ptr [rbp+37h+arg_0]
0x180032da3  test    r11b, r11b
0x180032da6  jz      short loc_180032DE9
0x180032da8  mov     eax, [rsp+130h+var_FC]
0x180032dac  sub     eax, [rbx+0D8h]
0x180032db2  cmp     eax, 0BB8h
0x180032db7  mov     rax, [rsp+130h+var_E8]
0x180032dbc  jnb     short loc_180032DC6
0x180032dbe  inc     rax
0x180032dc1  mov     [rsp+130h+var_E8], rax
0x180032dc6  mov     rdx, [rsp+130h+var_D8]
0x180032dcb  inc     rdx
0x180032dce  mov     [rsp+130h+var_D8], rdx
0x180032dd3  cmp     rdx, 64h ; 'd'
0x180032dd7  jnb     loc_180032E6D
0x180032ddd  cmp     rax, 8
0x180032de1  jnb     loc_180032E6D
0x180032de7  xor     edx, edx
0x180032de9  mov     r14b, 1
0x180032dec  lea     r12, [rbx+10h]
0x180032df0  mov     rbx, [r12]
0x180032df4  test    rbx, rbx
0x180032df7  jnz     loc_180032C1B
0x180032dfd  jmp     loc_180032EC4
0x180032e02  mov     rax, [rbp+37h+arg_20]
0x180032e06  lea     rcx, [rsp+130h+var_C8]
0x180032e0b  mov     qword ptr [rsp+130h+var_108], rax
0x180032e10  mov     r9d, r13d
0x180032e13  mov     qword ptr [rsp+130h+var_110], rdx; int
0x180032e18  mov     r8d, esi
0x180032e1b  mov     edx, r15d
0x180032e1e  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x180032e23  mov     rdx, rax
0x180032e26  mov     rcx, rdi; this
0x180032e29  call    ?PushBack@TaskList@WorkThreadManager@@QEAAJ$$QEAUTaskData@2@@Z; WorkThreadManager::TaskList::PushBack(WorkThreadManager::TaskData &&)
0x180032e2e  lea     rcx, [rsp+130h+var_C8]; this
0x180032e33  mov     edi, eax
0x180032e35  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180032e3a  test    edi, edi
0x180032e3c  jns     short loc_180032E5D
0x180032e3e  mov     rcx, [rbp+3Fh]; this
0x180032e42  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180032e49  mov     r9d, edi; char *
0x180032e4c  mov     edx, 4FCh; void *
0x180032e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e56  mov     eax, edi
0x180032e58  jmp     loc_180033033
0x180032e5d  mov     rcx, rbx; pv
0x180032e60  call    ?CheckForDeadlock@CThread@WorkThreadManager@@QEAAXXZ; WorkThreadManager::CThread::CheckForDeadlock(void)
0x180032e65  mov     eax, [rbx+50h]
0x180032e68  jmp     loc_18003302B
0x180032e6d  mov     rax, [rbp+37h+arg_20]
0x180032e71  mov     r9d, r13d
0x180032e74  mov     qword ptr [rsp+130h+var_108], rax
0x180032e79  mov     r8d, esi
0x180032e7c  mov     qword ptr [rsp+130h+var_110], rcx
0x180032e81  mov     edx, r15d
0x180032e84  lea     rcx, [rsp+130h+var_C8]
0x180032e89  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x180032e8e  mov     rdx, rax
0x180032e91  lea     rcx, ?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A; this
0x180032e98  call    ?PushBack@TaskList@WorkThreadManager@@QEAAJ$$QEAUTaskData@2@@Z; WorkThreadManager::TaskList::PushBack(WorkThreadManager::TaskData &&)
0x180032e9d  lea     rcx, [rsp+130h+var_C8]; this
0x180032ea2  mov     ebx, eax
0x180032ea4  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180032ea9  test    ebx, ebx
0x180032eab  jns     short loc_180032EB7
0x180032ead  mov     edx, 51Ch
0x180032eb2  jmp     loc_180032D11
0x180032eb7  call    ?s_EnsureFloodingListWatchdogUnderLock@WorkThreadManager@@CAXXZ; WorkThreadManager::s_EnsureFloodingListWatchdogUnderLock(void)
0x180032ebc  jmp     loc_180033031
0x180032ec1  mov     rdi, rdx
0x180032ec4  cmp     [r12], rdx
0x180032ec8  jnz     loc_180032FD0
0x180032ece  lea     r8, [rbp+37h+arg_10]
0x180032ed2  lea     rdx, [rbp+37h+arg_8]
0x180032ed6  lea     rcx, [rbp+37h+pv]
0x180032eda  call    ??$Make@VCThread@WorkThreadManager@@AEAW4TaskApartment@Internal@Windows@@AEAW4TaskOptions@45@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCThread@WorkThreadManager@@@12@AEAW4TaskApartment@Internal@Windows@@AEAW4TaskOptions@56@@Z; Microsoft::WRL::Details::Make<WorkThreadManager::CThread,Windows::Internal::TaskApartment &,Windows::Internal::TaskOptions &>(Windows::Internal::TaskApartment &,Windows::Internal::TaskOptions &)
0x180032edf  mov     rdi, [rbp+37h+pv]
0x180032ee3  test    rdi, rdi
0x180032ee6  jnz     short loc_180032EFA
0x180032ee8  mov     ebx, 8007000Eh
0x180032eed  mov     edx, 54Ah
0x180032ef2  mov     r9d, ebx
0x180032ef5  jmp     loc_180032F8B
0x180032efa  mov     rax, [rbp+37h+arg_20]
0x180032efe  lea     rcx, [rbp+37h+var_80]
0x180032f02  mov     qword ptr [rsp+130h+var_108], rax
0x180032f07  mov     r9d, r13d
0x180032f0a  mov     rax, qword ptr [rbp+37h+arg_0]
0x180032f0e  mov     r8d, esi
0x180032f11  mov     edx, r15d
0x180032f14  mov     qword ptr [rsp+130h+var_110], rax; int
0x180032f19  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x180032f1e  mov     r9d, [rsp+130h+var_FC]
0x180032f23  lea     rdx, [rsp+130h+var_C8]
0x180032f28  mov     r8, rax
0x180032f2b  mov     rcx, rdi
0x180032f2e  call    ?SetThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@$$QEAU32@K@Z; WorkThreadManager::CThread::SetThreadTask(WorkThreadManager::TaskData &&,ulong)
0x180032f33  lea     rcx, [rsp+130h+var_C8]; this
0x180032f38  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180032f3d  lea     rcx, [rbp+37h+var_80]; this
0x180032f41  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180032f46  test    r14b, r14b
0x180032f49  jz      short loc_180032F75
0x180032f4b  cmp     dword ptr [rsp+3Ch], 0
0x180032f50  jnz     short loc_180032F75
0x180032f52  mov     rax, [rsp+130h+var_D0]
0x180032f57  test    rax, rax
0x180032f5a  jz      short loc_180032F60
0x180032f5c  mov     byte ptr [rax+28h], 1
0x180032f60  mov     rcx, rdi; pv
0x180032f63  call    ?StartThreadWithFallback@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThreadWithFallback(void)
0x180032f68  mov     ebx, eax
0x180032f6a  test    eax, eax
0x180032f6c  jns     short loc_180032FB9
0x180032f6e  mov     edx, 558h
0x180032f73  jmp     short loc_180032F88
0x180032f75  mov     rcx, rdi; this
0x180032f78  call    ?StartThread@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThread(void)
0x180032f7d  mov     ebx, eax
0x180032f7f  test    eax, eax
0x180032f81  jns     short loc_180032FA9
0x180032f83  mov     edx, 55Ch; void *
0x180032f88  mov     r9d, eax; char *
0x180032f8b  mov     rcx, [rbp+3Fh]; this
0x180032f8f  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180032f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032f9b  lea     rcx, [rbp+37h+pv]
  ... truncated ...
```
