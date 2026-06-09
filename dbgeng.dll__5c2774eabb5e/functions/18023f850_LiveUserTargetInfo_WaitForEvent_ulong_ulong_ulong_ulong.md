# LiveUserTargetInfo::WaitForEvent(ulong,ulong,ulong,ulong *)

- ea: `0x18023f850`
- end: `0x18023fe29`
- name: `?WaitForEvent@LiveUserTargetInfo@@UEAAJKKKPEAK@Z`
- size: `1497`
- prototype: `__int64 __usercall@<rax>(LiveUserTargetInfo *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180071a60`
- `0x1800727b8`
- `0x1800793cc`
- `0x1800797ec`
- `0x18007ac6c`
- `0x18009a324`
- `0x1800b6358`
- `0x1800b94c4`
- `0x1800c12b8`
- `0x1800cca3c`
- `0x1800d9dd8`
- `0x1800f0f40`
- `0x1801e282c`
- `0x1801e40b4`
- `0x1801e4150`
- `0x1801e86c4`
- `0x18023823c`
- `0x1802393f4`
- `0x18023f850`
- `0x1802bef18`
- `0x1802c87ac`
- `0x180413788`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18023fb5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18023fb5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18023fb02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18023fb02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18023fdb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18023fdb2`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x18023fb49`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x18023fb49`

## string_xrefs

- `0x18023fad0`: `WARNING: Break-in timed out without an available thread.  Rewaiting.\n`
- `0x18023fa5a`: `         This is usually caused by another thread holding the loader lock\n`

## pseudocode

```c
__int64 __fastcall LiveUserTargetInfo::WaitForEvent(
        struct IUserDebugServices **this,
        __int64 a2,
        int a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // r14d
  __int64 result; // rax
  int v13; // edi
  struct IUserDebugServices *i; // rax
  struct IUserDebugServices *j; // rbx
  unsigned int v16; // r9d
  unsigned int v17; // r8d
  unsigned int v18; // edx
  struct IUserDebugServices *v19; // rcx
  unsigned int v20; // r15d
  unsigned int v21; // r13d
  TargetInfo *v22; // rax
  char v23; // r9
  struct IUserDebugServices *v24; // rax
  struct IUserDebugServices *v25; // rcx
  unsigned int v26; // ebx
  unsigned int v27; // edi
  char v28; // al
  unsigned int v29; // edi
  unsigned int v30; // ebx
  bool v31; // r8
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r9
  unsigned int v35; // edx
  unsigned int v36; // edx
  LiveUserTargetInfo *v37; // rcx
  struct _PENDING_PROCESS *PendingProcessById; // rbx
  PENDING_PLM_PACKAGE *PendingPlmPackageById; // rax
  PENDING_PLM_PACKAGE *v40; // rcx
  PENDING_PLM_PACKAGE *v41; // rdx
  struct IUserDebugServices *v42; // rcx
  struct IUserDebugServices *v43; // rax
  unsigned int v44; // eax
  LiveUserTargetInfo *v45; // rcx
  struct ProcessInfo *ProcessBySystemId; // rbx
  int v47; // [rsp+30h] [rbp-D0h] BYREF
  int v48; // [rsp+34h] [rbp-CCh]
  unsigned __int16 *v49; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v50; // [rsp+40h] [rbp-C0h]
  _OWORD v51[6]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v52[11]; // [rsp+B0h] [rbp-50h] BYREF

  LODWORD(v49) = a3;
  v50 = a5;
  memset(v52, 0, sizeof(v52));
  v11 = 0;
  v47 = 0;
  v48 = 0;
  if ( !*((_BYTE *)this + 44) )
  {
    result = LiveUserTargetInfo::InitFromServices((LiveUserTargetInfo *)this);
    if ( (_DWORD)result )
      return result;
    v48 = 1;
  }
  if ( !*((_BYTE *)this + 29) || (result = TargetInfo::AddBasicServices((TargetInfo *)this, 1), !(_DWORD)result) )
  {
    v13 = (_DWORD)this[557] & 5;
    if ( v13 || (g_EngStatus & 0x180) != 0 )
    {
      ++a4;
      if ( !*((_DWORD *)this + 6) )
      {
        *((_DWORD *)this + 6) = a4;
        a4 = 0;
      }
      EventOut(L">>> User elapsed time %d\n", a4);
      if ( v13 && a4 >= 0xEA60 )
      {
        for ( i = this[555]; i; i = (struct IUserDebugServices *)*((_QWORD *)i + 4) )
        {
          v8 = *((unsigned int *)i + 6);
          if ( (v8 & 1) != 0 )
          {
            v8 = (unsigned int)v8 | 4;
            *((_DWORD *)i + 6) = v8;
            *((_DWORD *)this + 1114) |= 4u;
          }
        }
      }
    }
    if ( ((_BYTE)this[557] & 0xC) != 0 )
    {
      for ( j = this[555]; ; j = (struct IUserDebugServices *)*((_QWORD *)j + 4) )
      {
        if ( !j )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
          return 2147549183LL;
        }
        if ( (*((_BYTE *)j + 24) & 0xC) != 0 )
          break;
      }
      v16 = *((_DWORD *)j + 7);
      v17 = *((_DWORD *)j + 6);
      v18 = *((_DWORD *)j + 4);
      v19 = this[528];
      g_EventTarget = (TargetInfo *)this;
      result = ExamineActiveProcess(v19, v18, v17, v16, (struct _DEBUG_EVENT64 *)v52);
      if ( (_DWORD)result )
      {
        g_EventTarget = 0;
        return result;
      }
      v20 = *((_DWORD *)j + 4);
      v11 = *((_DWORD *)j + 6);
      v21 = *((_DWORD *)j + 7);
      LiveUserTargetInfo::RemovePendingProcess((LiveUserTargetInfo *)this, j);
      v22 = g_EventTarget;
      v23 = 0;
      goto LABEL_34;
    }
    v20 = 0;
    v21 = 2;
    if ( (g_EngStatus & 0x180) != 0 )
    {
      if ( !*((_BYTE *)this + 4468) && a4 >= 0xBB8 )
      {
        dprintf(L"Break-in sent, waiting %d seconds...\n", g_PendingBreakInTimeoutLimit);
        *((_BYTE *)this + 4468) = 1;
      }
      if ( a4 >= 1000 * g_PendingBreakInTimeoutLimit )
      {
        v24 = this[7];
        if ( v24 && *((_QWORD *)v24 + 46) )
        {
          WarnOut(L"WARNING: Break-in timed out, suspending.\n");
          WarnOut(L"         This is usually caused by another thread holding the loader lock\n");
          v25 = this[7];
          v26 = *((_DWORD *)v25 + 97);
          v27 = *(_DWORD *)(*((_QWORD *)v25 + 46) + 36LL);
          memset(v52, 0, sizeof(v52));
          g_EngStatus &= 0xFFFFFE7F;
          v22 = (TargetInfo *)this;
          g_EventTarget = (TargetInfo *)this;
          v23 = 1;
          LODWORD(v52[0]) = 1;
          *(_QWORD *)((char *)v52 + 4) = __PAIR64__(v27, v26);
          LODWORD(v52[1]) = -2147483641;
          DWORD2(v52[10]) = 1;
LABEL_34:
          g_Target = v22;
          v28 = 0;
          v47 = 176;
          goto LABEL_51;
        }
        WarnOut(L"WARNING: Break-in timed out without an available thread.  Rewaiting.\n");
        *((_DWORD *)this + 6) = 0;
      }
    }
    if ( (g_EngStatus & 0x800) != 0 )
      return 2147483658LL;
    FlushCallbacks();
    LeaveCriticalSection(&g_EngineLock);
    v29 = (unsigned int)v49;
    while ( 1 )
    {
      v30 = (*(__int64 (__fastcall **)(struct IUserDebugServices *, _QWORD, _OWORD *, __int64, int *))(*(_QWORD *)this[528] + 392LL))(
              this[528],
              v29,
              v52,
              176,
              &v47);
      if ( v30 != -2147024882 )
        break;
      Sleep(0x32u);
    }
    EnterCriticalSection(&g_EngineLock);
    if ( v30 == 1 )
      return 1;
    if ( v30 )
    {
      CatastrophicLiveUserError(L"WaitForEvent", v30);
      return v30;
    }
    g_EventTarget = (TargetInfo *)this;
    if ( v47 == 96 )
    {
      v51[0] = v52[0];
      v51[1] = v52[1];
      v51[2] = v52[2];
      v51[3] = v52[3];
      v51[4] = v52[4];
      v51[5] = v52[5];
      DbsDebugEvent32To64((struct _DEBUG_EVENT32 *)v51, (struct _DEBUG_EVENT64 *)v52, v31);
    }
    else
    {
      if ( v47 != 176 )
      {
        ErrOut(L"Event data corrupt\n");
        return 2147500037LL;
      }
      v23 = 0;
    }
    g_Target = (TargetInfo *)this;
    v28 = 1;
LABEL_51:
    v32 = DWORD1(v52[0]);
    v33 = LODWORD(v52[0]);
    *((_BYTE *)this + 41) = v23;
    v34 = DWORD2(v52[0]);
    *((_BYTE *)this + 40) = v28;
    EventOut(L">>> Debug event %u for %X.%X\n", v33, v32, v34);
    v35 = DWORD1(v52[0]);
    g_EventThreadSysId = DWORD2(v52[0]);
    g_EventProcessSysId = DWORD1(v52[0]);
    if ( LODWORD(v52[0]) == 3 )
      goto LABEL_55;
    if ( LODWORD(v52[0]) != 2 )
    {
      FindEventProcessThread();
      v35 = g_EventProcessSysId;
    }
    if ( LODWORD(v52[0]) == 3 )
    {
LABEL_55:
      PendingProcessById = LiveUserTargetInfo::FindPendingProcessById((LiveUserTargetInfo *)this, v35);
      if ( PendingProcessById
        || ((_BYTE)this[557] & 0x10) != 0
        && (PendingProcessById = LiveUserTargetInfo::FindPendingProcessById(v37, 0xFFFFFFFF)) != 0 )
      {
        v11 = *((_DWORD *)PendingProcessById + 6);
        v21 = *((_DWORD *)PendingProcessById + 7);
        if ( (v11 & 1) != 0 )
        {
          VerbOut(L"*** attach succeeded\n");
          v11 &= ~4u;
          if ( (v11 & 0x40) == 0 )
            g_EngStatus |= 0x100u;
          if ( (v11 & 0x80u) != 0 )
            v20 = *((_DWORD *)PendingProcessById + 4);
        }
        LiveUserTargetInfo::RemovePendingProcess((LiveUserTargetInfo *)this, PendingProcessById);
      }
      else
      {
        PendingPlmPackageById = LiveUserTargetInfo::FindPendingPlmPackageById((LiveUserTargetInfo *)this, v36);
        if ( PendingPlmPackageById )
        {
          v40 = this[556];
          v41 = 0;
          while ( v40 )
          {
            if ( v40 == PendingPlmPackageById )
            {
              v42 = (struct IUserDebugServices *)*((_QWORD *)v40 + 3);
              if ( v41 )
                *((_QWORD *)v41 + 3) = v42;
              else
                this[556] = v42;
              PENDING_PLM_PACKAGE::`scalar deleting destructor'(PendingPlmPackageById, (unsigned int)v41);
              break;
            }
            v41 = v40;
            v40 = (PENDING_PLM_PACKAGE *)*((_QWORD *)v40 + 3);
          }
          v11 = 2;
LABEL_77:
          if ( v48 )
            NotifyDebuggeeActivation();
          if ( (unsigned int)(LODWORD(v52[0]) - 2) <= 1 && ((_BYTE)this[529] & 2) != 0 )
            v11 |= 0x80000000;
          v43 = *this;
          g_EngStatus |= 8u;
          v44 = (*((__int64 (__fastcall **)(struct IUserDebugServices **, _OWORD *, _QWORD, _QWORD))v43 + 193))(
                  this,
                  v52,
                  v11,
                  v21);
          *v50 = v44;
          if ( !v20 )
            return 0;
          ProcessBySystemId = TargetInfo::FindProcessBySystemId((TargetInfo *)this, v20);
          if ( !ProcessBySystemId )
            return 0;
          if ( (v11 & 0x20) != 0 )
          {
            if ( v20 == GetCurrentProcessId() )
              return 0;
            (*((void (__fastcall **)(struct IUserDebugServices **, struct ProcessInfo *, _QWORD, __int64))*this + 82))(
              this,
              ProcessBySystemId,
              0,
              1);
            v45 = (LiveUserTargetInfo *)this;
          }
          (*((void (__fastcall **)(LiveUserTargetInfo *, struct ProcessInfo *, _QWORD, __int64))*this + 83))(
            v45,
            ProcessBySystemId,
            0,
            1);
          return 0;
        }
      }
    }
    if ( (v11 & 0xC) != 0 )
    {
      v49 = 0;
      TargetInfo::Reload((TargetInfo *)this, g_EventThread, (wchar_t *)L"-s -P", &v49);
    }
    goto LABEL_77;
  }
  return result;
}

```

## disassembly

```asm
0x18023f850  mov     [rsp-8+arg_8], rbx
0x18023f855  push    rbp
0x18023f856  push    rsi
0x18023f857  push    rdi
0x18023f858  push    r12
0x18023f85a  push    r13
0x18023f85c  push    r14
0x18023f85e  push    r15
0x18023f860  lea     rbp, [rsp-70h]
0x18023f865  sub     rsp, 170h
0x18023f86c  mov     rax, cs:__security_cookie
0x18023f873  xor     rax, rsp
0x18023f876  mov     [rbp+0A0h+var_40], rax
0x18023f87a  mov     rax, [rbp+0A0h+arg_20]
0x18023f881  mov     rsi, rcx
0x18023f884  mov     dword ptr [rsp+1A0h+var_168], r8d
0x18023f889  lea     rcx, [rbp+0A0h+var_F0]; void *
0x18023f88d  mov     r12d, 0B0h
0x18023f893  mov     [rsp+1A0h+var_160], rax
0x18023f898  mov     r8d, r12d; Size
0x18023f89b  xor     edx, edx; Val
0x18023f89d  mov     ebx, r9d
0x18023f8a0  call    memset
0x18023f8a5  xor     r14d, r14d
0x18023f8a8  mov     [rsp+1A0h+var_170], r14d
0x18023f8ad  mov     [rsp+1A0h+var_16C], r14d
0x18023f8b2  cmp     [rsi+2Ch], r14b
0x18023f8b6  jnz     short loc_18023F8D0
0x18023f8b8  mov     rcx, rsi; this
0x18023f8bb  call    ?InitFromServices@LiveUserTargetInfo@@QEAAJXZ; LiveUserTargetInfo::InitFromServices(void)
0x18023f8c0  test    eax, eax
0x18023f8c2  jnz     loc_18023FE01
0x18023f8c8  mov     [rsp+1A0h+var_16C], 1
0x18023f8d0  cmp     [rsi+1Dh], r14b
0x18023f8d4  jz      short loc_18023F8E8
0x18023f8d6  mov     dl, 1; bool
0x18023f8d8  mov     rcx, rsi; this
0x18023f8db  call    ?AddBasicServices@TargetInfo@@QEAAJ_N@Z; TargetInfo::AddBasicServices(bool)
0x18023f8e0  test    eax, eax
0x18023f8e2  jnz     loc_18023FE01
0x18023f8e8  mov     edi, [rsi+1168h]
0x18023f8ee  and     edi, 5
0x18023f8f1  jnz     short loc_18023F8FF
0x18023f8f3  test    cs:?g_EngStatus@@3KA, 180h; ulong g_EngStatus
0x18023f8fd  jz      short loc_18023F94E
0x18023f8ff  inc     ebx
0x18023f901  cmp     [rsi+18h], r14d
0x18023f905  jnz     short loc_18023F90D
0x18023f907  mov     [rsi+18h], ebx
0x18023f90a  mov     ebx, r14d
0x18023f90d  mov     edx, ebx
0x18023f90f  lea     rcx, aUserElapsedTim; ">>> User elapsed time %d\n"
0x18023f916  call    ?EventOut@@YAXPEBGZZ; EventOut(ushort const *,...)
0x18023f91b  test    edi, edi
0x18023f91d  jz      short loc_18023F94E
0x18023f91f  cmp     ebx, 0EA60h
0x18023f925  jb      short loc_18023F94E
0x18023f927  mov     rax, [rsi+1158h]
0x18023f92e  jmp     short loc_18023F949
0x18023f930  mov     ecx, [rax+18h]
0x18023f933  test    cl, 1
0x18023f936  jz      short loc_18023F945
0x18023f938  or      ecx, 4
0x18023f93b  mov     [rax+18h], ecx
0x18023f93e  or      dword ptr [rsi+1168h], 4
0x18023f945  mov     rax, [rax+20h]
0x18023f949  test    rax, rax
0x18023f94c  jnz     short loc_18023F930
0x18023f94e  test    byte ptr [rsi+1168h], 0Ch
0x18023f955  jz      loc_18023F9DF
0x18023f95b  mov     rbx, [rsi+1158h]
0x18023f962  test    rbx, rbx
0x18023f965  jz      short loc_18023F9D0
0x18023f967  test    byte ptr [rbx+18h], 0Ch
0x18023f96b  jnz     short loc_18023F973
0x18023f96d  mov     rbx, [rbx+20h]
0x18023f971  jmp     short loc_18023F962
0x18023f973  mov     r9d, [rbx+1Ch]; unsigned int
0x18023f977  lea     rax, [rbp+0A0h+var_F0]
0x18023f97b  mov     r8d, [rbx+18h]; unsigned int
0x18023f97f  mov     edx, [rbx+10h]; unsigned int
0x18023f982  mov     rcx, [rsi+1080h]; struct IUserDebugServices *
0x18023f989  mov     [rsp+1A0h+var_180], rax; struct _DEBUG_EVENT64 *
0x18023f98e  mov     cs:?g_EventTarget@@3PEAVTargetInfo@@EA, rsi; TargetInfo * g_EventTarget
0x18023f995  call    ?ExamineActiveProcess@@YAJPEAUIUserDebugServices@@KKKPEAU_DEBUG_EVENT64@@@Z; ExamineActiveProcess(IUserDebugServices *,ulong,ulong,ulong,_DEBUG_EVENT64 *)
0x18023f99a  test    eax, eax
0x18023f99c  jz      short loc_18023F9AA
0x18023f99e  mov     cs:?g_EventTarget@@3PEAVTargetInfo@@EA, r14; TargetInfo * g_EventTarget
0x18023f9a5  jmp     loc_18023FE01
0x18023f9aa  mov     r15d, [rbx+10h]
0x18023f9ae  mov     rdx, rbx; struct _PENDING_PROCESS *
0x18023f9b1  mov     r14d, [rbx+18h]
0x18023f9b5  mov     rcx, rsi; this
0x18023f9b8  mov     r13d, [rbx+1Ch]
0x18023f9bc  call    ?RemovePendingProcess@LiveUserTargetInfo@@QEAAXPEAU_PENDING_PROCESS@@@Z; LiveUserTargetInfo::RemovePendingProcess(_PENDING_PROCESS *)
0x18023f9c1  mov     rax, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; TargetInfo * g_EventTarget
0x18023f9c8  xor     r9d, r9d
0x18023f9cb  jmp     loc_18023FABD
0x18023f9d0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18023f9d5  mov     eax, 8000FFFFh
0x18023f9da  jmp     loc_18023FE01
0x18023f9df  xor     r15d, r15d
0x18023f9e2  mov     r13d, 2
0x18023f9e8  test    cs:?g_EngStatus@@3KA, 180h; ulong g_EngStatus
0x18023f9f2  jz      loc_18023FAE0
0x18023f9f8  cmp     [rsi+1174h], r14b
0x18023f9ff  jnz     short loc_18023FA22
0x18023fa01  cmp     ebx, 0BB8h
0x18023fa07  jb      short loc_18023FA22
0x18023fa09  mov     edx, cs:?g_PendingBreakInTimeoutLimit@@3KA; ulong g_PendingBreakInTimeoutLimit
0x18023fa0f  lea     rcx, aBreakInSentWai; "Break-in sent, waiting %d seconds...\n"
0x18023fa16  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18023fa1b  mov     byte ptr [rsi+1174h], 1
0x18023fa22  imul    eax, cs:?g_PendingBreakInTimeoutLimit@@3KA, 3E8h; ulong g_PendingBreakInTimeoutLimit
0x18023fa2c  cmp     ebx, eax
0x18023fa2e  jb      loc_18023FAE0
0x18023fa34  mov     rax, [rsi+38h]
0x18023fa38  test    rax, rax
0x18023fa3b  jz      loc_18023FAD0
0x18023fa41  cmp     [rax+170h], r14
0x18023fa48  jz      loc_18023FAD0
0x18023fa4e  lea     rcx, aWarningBreakIn; "WARNING: Break-in timed out, suspending"...
0x18023fa55  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x18023fa5a  lea     rcx, aThisIsUsuallyC; "         This is usually caused by anot"...
0x18023fa61  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x18023fa66  mov     rcx, [rsi+38h]
0x18023fa6a  mov     r8, r12; Size
0x18023fa6d  xor     edx, edx; Val
0x18023fa6f  mov     rax, [rcx+170h]
0x18023fa76  mov     ebx, [rcx+184h]
0x18023fa7c  lea     rcx, [rbp+0A0h+var_F0]; void *
0x18023fa80  mov     edi, [rax+24h]
0x18023fa83  call    memset
0x18023fa88  and     cs:?g_EngStatus@@3KA, 0FFFFFE7Fh; ulong g_EngStatus
0x18023fa92  mov     rax, rsi
0x18023fa95  mov     cs:?g_EventTarget@@3PEAVTargetInfo@@EA, rax; TargetInfo * g_EventTarget
0x18023fa9c  mov     r9d, 1
0x18023faa2  mov     dword ptr [rbp+0A0h+var_F0], 1
0x18023faa9  mov     dword ptr [rbp+0A0h+var_F0+4], ebx
0x18023faac  mov     dword ptr [rbp+0A0h+var_F0+8], edi
0x18023faaf  mov     dword ptr [rbp+0A0h+var_E0], 80000007h
0x18023fab6  mov     [rbp+0A0h+var_48], 1
0x18023fabd  mov     cs:?g_Target@@3PEAVTargetInfo@@EA, rax; TargetInfo * g_Target
0x18023fac4  xor     eax, eax
0x18023fac6  mov     [rsp+1A0h+var_170], r12d
0x18023facb  jmp     loc_18023FC0C
0x18023fad0  lea     rcx, aWarningBreakIn_0; "WARNING: Break-in timed out without an "...
0x18023fad7  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x18023fadc  mov     [rsi+18h], r14d
0x18023fae0  test    cs:?g_EngStatus@@3KA, 800h; ulong g_EngStatus
0x18023faea  jz      short loc_18023FAF6
0x18023faec  mov     eax, 8000000Ah
0x18023faf1  jmp     loc_18023FE01
0x18023faf6  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x18023fafb  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18023fb02  call    cs:__imp_LeaveCriticalSection
0x18023fb09  nop     dword ptr [rax+rax+00h]
0x18023fb0e  mov     edi, dword ptr [rsp+1A0h+var_168]
0x18023fb12  mov     rcx, [rsi+1080h]
0x18023fb19  lea     rdx, [rsp+1A0h+var_170]
0x18023fb1e  mov     [rsp+1A0h+var_180], rdx
0x18023fb23  lea     r8, [rbp+0A0h+var_F0]
0x18023fb27  mov     r9d, r12d
0x18023fb2a  mov     edx, edi
0x18023fb2c  mov     rax, [rcx]
0x18023fb2f  mov     rax, [rax+188h]
0x18023fb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18023fb3b  mov     ebx, eax
0x18023fb3d  cmp     eax, 8007000Eh
0x18023fb42  jnz     short loc_18023FB57
0x18023fb44  mov     ecx, 32h ; '2'; dwMilliseconds
0x18023fb49  call    cs:__imp_Sleep
0x18023fb50  nop     dword ptr [rax+rax+00h]
0x18023fb55  jmp     short loc_18023FB12
0x18023fb57  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18023fb5e  call    cs:__imp_EnterCriticalSection
0x18023fb65  nop     dword ptr [rax+rax+00h]
0x18023fb6a  cmp     ebx, 1
0x18023fb6d  jnz     short loc_18023FB76
0x18023fb6f  mov     eax, ebx
0x18023fb71  jmp     loc_18023FE01
0x18023fb76  test    ebx, ebx
0x18023fb78  jz      short loc_18023FB8F
0x18023fb7a  mov     edx, ebx; int
0x18023fb7c  lea     rcx, aWaitforevent; "WaitForEvent"
0x18023fb83  call    ?CatastrophicLiveUserError@@YAXPEBGJ@Z; CatastrophicLiveUserError(ushort const *,long)
0x18023fb88  mov     eax, ebx
0x18023fb8a  jmp     loc_18023FE01
0x18023fb8f  mov     cs:?g_EventTarget@@3PEAVTargetInfo@@EA, rsi; TargetInfo * g_EventTarget
0x18023fb96  cmp     [rsp+1A0h+var_170], 60h ; '`'
0x18023fb9b  jnz     short loc_18023FBE3
0x18023fb9d  movaps  xmm0, [rbp+0A0h+var_F0]
0x18023fba1  lea     rdx, [rbp+0A0h+var_F0]; struct _DEBUG_EVENT64 *
0x18023fba5  movaps  xmm1, [rbp+0A0h+var_E0]
0x18023fba9  lea     rcx, [rsp+1A0h+var_150]; struct _DEBUG_EVENT32 *
0x18023fbae  movaps  [rsp+1A0h+var_150], xmm0
0x18023fbb3  xor     r9d, r9d
0x18023fbb6  movaps  xmm0, [rbp+0A0h+var_D0]
0x18023fbba  movaps  [rsp+1A0h+var_140], xmm1
0x18023fbbf  movaps  xmm1, [rbp+0A0h+var_C0]
0x18023fbc3  movaps  [rsp+1A0h+var_130], xmm0
0x18023fbc8  movaps  xmm0, [rbp+0A0h+var_B0]
0x18023fbcc  movaps  [rbp+0A0h+var_120], xmm1
0x18023fbd0  movaps  xmm1, [rbp+0A0h+var_A0]
0x18023fbd4  movaps  [rbp+0A0h+var_110], xmm0
0x18023fbd8  movaps  [rbp+0A0h+var_100], xmm1
0x18023fbdc  call    ?DbsDebugEvent32To64@@YAXPEAU_DEBUG_EVENT32@@PEAU_DEBUG_EVENT64@@_N@Z; DbsDebugEvent32To64(_DEBUG_EVENT32 *,_DEBUG_EVENT64 *,bool)
0x18023fbe1  jmp     short loc_18023FC03
0x18023fbe3  cmp     [rsp+1A0h+var_170], r12d
0x18023fbe8  jz      short loc_18023FC00
0x18023fbea  lea     rcx, aEventDataCorru; "Event data corrupt\n"
0x18023fbf1  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18023fbf6  mov     eax, 80004005h
0x18023fbfb  jmp     loc_18023FE01
0x18023fc00  xor     r9d, r9d
0x18023fc03  mov     cs:?g_Target@@3PEAVTargetInfo@@EA, rsi; TargetInfo * g_Target
0x18023fc0a  mov     al, 1
0x18023fc0c  mov     r8d, dword ptr [rbp+0A0h+var_F0+4]
0x18023fc10  lea     rcx, aDebugEventUFor; ">>> Debug event %u for %X.%X\n"
0x18023fc17  mov     edx, dword ptr [rbp+0A0h+var_F0]
0x18023fc1a  mov     [rsi+29h], r9b
0x18023fc1e  mov     r9d, dword ptr [rbp+0A0h+var_F0+8]
0x18023fc22  mov     [rsi+28h], al
0x18023fc25  call    ?EventOut@@YAXPEBGZZ; EventOut(ushort const *,...)
0x18023fc2a  cmp     dword ptr [rbp+0A0h+var_F0], 3
0x18023fc2e  mov     edx, dword ptr [rbp+0A0h+var_F0+4]
0x18023fc31  mov     eax, dword ptr [rbp+0A0h+var_F0+8]
0x18023fc34  mov     cs:?g_EventProcessSysId@@3KA, edx; ulong g_EventProcessSysId
0x18023fc3a  mov     cs:?g_EventThreadSysId@@3KA, eax; ulong g_EventThreadSysId
0x18023fc40  jz      short loc_18023FC5D
0x18023fc42  cmp     dword ptr [rbp+0A0h+var_F0], 2
0x18023fc46  jz      short loc_18023FC53
0x18023fc48  call    ?FindEventProcessThread@@YAXXZ; FindEventProcessThread(void)
0x18023fc4d  mov     edx, cs:?g_EventProcessSysId@@3KA; unsigned int
0x18023fc53  cmp     dword ptr [rbp+0A0h+var_F0], 3
0x18023fc57  jnz     loc_18023FD1B
0x18023fc5d  mov     rcx, rsi; this
0x18023fc60  call    ?FindPendingProcessById@LiveUserTargetInfo@@QEAAPEAU_PENDING_PROCESS@@K@Z; LiveUserTargetInfo::FindPendingProcessById(ulong)
0x18023fc65  mov     rbx, rax
0x18023fc68  test    rax, rax
0x18023fc6b  jnz     short loc_18023FCDB
0x18023fc6d  test    byte ptr [rsi+1168h], 10h
0x18023fc74  jz      short loc_18023FC86
0x18023fc76  or      edx, 0FFFFFFFFh; unsigned int
0x18023fc79  call    ?FindPendingProcessById@LiveUserTargetInfo@@QEAAPEAU_PENDING_PROCESS@@K@Z; LiveUserTargetInfo::FindPendingProcessById(ulong)
0x18023fc7e  mov     rbx, rax
0x18023fc81  test    rax, rax
0x18023fc84  jnz     short loc_18023FCDB
0x18023fc86  mov     rcx, rsi; this
0x18023fc89  call    ?FindPendingPlmPackageById@LiveUserTargetInfo@@QEAAPEAUPENDING_PLM_PACKAGE@@K@Z; LiveUserTargetInfo::FindPendingPlmPackageById(ulong)
0x18023fc8e  test    rax, rax
0x18023fc91  jz      loc_18023FD1B
0x18023fc97  mov     rcx, [rsi+1160h]
0x18023fc9e  xor     edx, edx
0x18023fca0  jmp     short loc_18023FCAE
0x18023fca2  cmp     rcx, rax
0x18023fca5  jz      short loc_18023FCB5
0x18023fca7  mov     rdx, rcx; unsigned int
0x18023fcaa  mov     rcx, [rcx+18h]
0x18023fcae  test    rcx, rcx
0x18023fcb1  jnz     short loc_18023FCA2
0x18023fcb3  jmp     short loc_18023FCD3
0x18023fcb5  mov     rcx, [rcx+18h]
0x18023fcb9  test    rdx, rdx
0x18023fcbc  jnz     short loc_18023FCC7
0x18023fcbe  mov     [rsi+1160h], rcx
0x18023fcc5  jmp     short loc_18023FCCB
0x18023fcc7  mov     [rdx+18h], rcx
0x18023fccb  mov     rcx, rax; this
0x18023fcce  call    ??_GPENDING_PLM_PACKAGE@@QEAAPEAXI@Z; PENDING_PLM_PACKAGE::`scalar deleting destructor'(uint)
0x18023fcd3  mov     r14d, 2
0x18023fcd9  jmp     short loc_18023FD45
0x18023fcdb  mov     r14d, [rbx+18h]
0x18023fcdf  mov     r13d, [rbx+1Ch]
0x18023fce3  test    r14b, 1
0x18023fce7  jz      short loc_18023FD10
0x18023fce9  lea     rcx, aAttachSucceede; "*** attach succeeded\n"
0x18023fcf0  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x18023fcf5  and     r14d, 0FFFFFFFBh
0x18023fcf9  test    r14b, 40h
0x18023fcfd  jnz     short loc_18023FD07
0x18023fcff  bts     cs:?g_EngStatus@@3KA, 8; ulong g_EngStatus
0x18023fd07  test    r14b, r14b
0x18023fd0a  jns     short loc_18023FD10
0x18023fd0c  mov     r15d, [rbx+10h]
0x18023fd10  mov     rdx, rbx; struct _PENDING_PROCESS *
0x18023fd13  mov     rcx, rsi; this
0x18023fd16  call    ?RemovePendingProcess@LiveUserTargetInfo@@QEAAXPEAU_PENDING_PROCESS@@@Z; LiveUserTargetInfo::RemovePendingProcess(_PENDING_PROCESS *)
0x18023fd1b  test    r14b, 0Ch
0x18023fd1f  jz      short loc_18023FD45
0x18023fd21  mov     rdx, cs:?g_EventThread@@3PEAVThreadInfo@@EA; struct ThreadInfo *
0x18023fd28  lea     r9, [rsp+1A0h+var_168]; unsigned __int16 **
0x18023fd2d  lea     r8, aSP; "-s -P"
0x18023fd34  mov     [rsp+1A0h+var_168], 0
0x18023fd3d  mov     rcx, rsi; this
0x18023fd40  call    ?Reload@TargetInfo@@QEAAJPEAVThreadInfo@@PEBGPEAPEBG@Z; TargetInfo::Reload(ThreadInfo *,ushort const *,ushort const * *)
0x18023fd45  cmp     [rsp+1A0h+var_16C], 0
0x18023fd4a  jz      short loc_18023FD51
0x18023fd4c  call    ?NotifyDebuggeeActivation@@YAXXZ; NotifyDebuggeeActivation(void)
0x18023fd51  mov     eax, dword ptr [rbp+0A0h+var_F0]
  ... truncated ...
```
