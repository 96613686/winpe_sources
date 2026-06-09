# RpcGetEnumResult

- ea: `0x1800183a0`
- end: `0x180018cdc`
- name: `RpcGetEnumResult`
- size: `2364`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int, volatile unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x1800183a0`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180018b56`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180018b56`
- `ntdll!NtQueryInformationProcess` at `0x180018b34`
- `ntdll!NtQueryInformationProcess` at `0x180018b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c90`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180018894`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180018c7c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180018894`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180018c7c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800184b3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800184b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018b85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018b85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018559`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018559`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c60`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001841c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001841c`
- `RPCRT4!RpcImpersonateClient` at `0x180018510`
- `RPCRT4!RpcImpersonateClient` at `0x180018510`
- `RPCRT4!RpcRevertToSelf` at `0x18001879a`
- `RPCRT4!RpcRevertToSelf` at `0x18001879a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180018492`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180018492`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180018b06`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180018b06`

## string_xrefs

- `0x180018bcc`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18001898e`: `%s with Trace ID 0x%x Completed`
- `0x180018a51`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x1800189c6`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
__int64 __fastcall RpcGetEnumResult(__int64 a1, _QWORD *a2, unsigned int a3, volatile unsigned int *a4)
{
  volatile unsigned int *v4; // r14
  unsigned int v8; // esi
  RPC_STATUS v9; // eax
  int v10; // ebx
  __int64 v11; // rbx
  RPC_STATUS v12; // eax
  signed int v13; // edi
  volatile unsigned int v14; // r14d
  char *v15; // r12
  volatile unsigned int v16; // esi
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int16 *v21; // rdx
  __int64 v22; // r8
  _WORD *v23; // r9
  __int16 v24; // ax
  _WORD *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  int v30; // esi
  HANDLE v31; // rax
  void *v32; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v34; // rax
  wchar_t *v35; // rax
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  struct CTraceBase *v37; // [rsp+40h] [rbp-C0h] BYREF
  volatile unsigned int *v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h]
  __int128 v42; // [rsp+80h] [rbp-80h]
  __m256i v43; // [rsp+90h] [rbp-70h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-50h]
  int v45; // [rsp+C0h] [rbp-40h]
  void **v46; // [rsp+D0h] [rbp-30h] BYREF
  GUID pguid; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v48[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct CTraceBase *v49; // [rsp+F0h] [rbp-10h] BYREF
  int v50; // [rsp+F8h] [rbp-8h]
  const char *v51; // [rsp+100h] [rbp+0h]
  unsigned int Pid[2]; // [rsp+108h] [rbp+8h] BYREF
  int v53; // [rsp+110h] [rbp+10h]
  unsigned __int16 v54[262]; // [rsp+114h] [rbp+14h] BYREF
  char ProcessInformation[8]; // [rsp+320h] [rbp+220h] BYREF
  wchar_t *Str; // [rsp+328h] [rbp+228h]
  _WORD v57[40]; // [rsp+430h] [rbp+330h] BYREF

  v4 = a4;
  v38 = a4;
  v36 = 0;
  v39 = 0;
  v46 = &CTraceBase::`vftable';
  v48[1] = 1;
  v49 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v46, 1, "RpcGetEnumResult");
    v37 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v37) >= 0 && v37 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v49) >= 0 && v49 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v49 + 32LL))(v49, &pguid);
      v48[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v49 + 24LL))(v49);
      v50 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v46, "RpcGetEnumResult");
    CTraceBase::GenerateTraceID(&pguid, v48);
  }
  else
  {
    CoCreateGuid(&pguid);
    v48[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v50 = 0;
LABEL_4:
  v46 = &CRpcCallTrace::`vftable';
  v51 = "RpcGetEnumResult";
  *(_QWORD *)Pid = -1;
  v53 = 0;
  memset_0(v54, 0, 0x208u);
  if ( v53 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v51, v48[0]);
  v8 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v8 = 260;
  *(_QWORD *)Pid = -1;
  v9 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v8 )
    {
      v31 = OpenProcess(0x400u, 0, Pid[1]);
      v32 = v31;
      if ( v31 )
      {
        InformationProcess = NtQueryInformationProcess(v31, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v10 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v34 = wcsrchr(Str, 0x5Cu);
          if ( v34 )
            v35 = v34 + 1;
          else
            v35 = Str;
          StringCchCopyW(v54, v8, v35);
        }
        CloseHandle(v32);
      }
      v4 = v38;
    }
  }
  if ( v53 )
  {
    if ( v10 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v54);
    }
  }
  if ( !a1 )
  {
    v11 = 0;
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hEnum", "RpcGetEnumResult");
LABEL_69:
    v13 = -2147024809;
LABEL_70:
    v30 = 0;
    goto LABEL_71;
  }
  v11 = *(_QWORD *)(a1 + 1592);
  if ( v11 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11 + 8LL))(*(_QWORD *)(a1 + 1592));
  if ( !a2 || !v4 )
    goto LABEL_69;
  *a2 = 0;
  *v4 = 0;
  v12 = RpcImpersonateClient(0);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v13, "RpcGetEnumResult");
    goto LABEL_70;
  }
  if ( a3 > 2 )
    a3 = 2;
  v14 = CTSPerfProvider::TotalSessions;
  if ( CTSPerfProvider::TotalSessions )
  {
    v15 = (char *)LocalAlloc(0x40u, 104LL * (unsigned int)CTSPerfProvider::TotalSessions);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 88LL))(v11);
      v16 = 0;
      while ( v16 < v14 )
      {
        v17 = v36;
        v36 = 0;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 80LL))(v11, &v36);
        v13 = v18;
        if ( v18 == -2147024637 )
        {
          v13 = 0;
          break;
        }
        if ( v18 < 0 )
        {
          _DbgPrintMessage(8, "Enum failed: 0x%x in %s", v18, "RpcGetEnumResult");
          v4 = v38;
          v30 = 1;
          goto LABEL_115;
        }
        if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v36 + 136LL))(v36, 1, 0) < 0 )
        {
          v13 = 0;
        }
        else
        {
          v40 = 0;
          v41 = 0;
          v42 = 0;
          memset(&v43, 0, sizeof(v43));
          v44 = 0;
          v45 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v36 + 80LL))(v36, &v40);
          LODWORD(v37) = 0;
          (*(void (__fastcall **)(__int64, struct CTraceBase **))(*(_QWORD *)v36 + 88LL))(v36, &v37);
          if ( (_DWORD)v37 == 1 )
          {
LABEL_32:
            v19 = 9;
          }
          else if ( (_DWORD)v37 == 12 )
          {
LABEL_49:
            v19 = 0;
          }
          else
          {
            switch ( (int)v37 )
            {
              case 0:
                goto LABEL_32;
              case 2:
              case 6:
                v19 = 1;
                break;
              case 3:
              case 4:
              case 13:
                v19 = 4;
                break;
              case 5:
                goto LABEL_49;
              case 7:
                v19 = 3;
                break;
              case 8:
              case 9:
                v19 = 2;
                break;
              default:
                v19 = 8;
                break;
            }
          }
          DWORD1(v40) = v19;
          v57[0] = 0;
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 104LL))(v36, &v39);
          if ( v39 )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v39 + 104LL))(v39, v57);
            if ( v13 >= 0 )
            {
              v20 = 2147483646;
              v21 = v57;
              v22 = 33;
              v23 = (_WORD *)&v40 + 4;
              do
              {
                if ( !v20 )
                  break;
                v24 = *v21;
                if ( !*v21 )
                  break;
                ++v21;
                *v23++ = v24;
                --v20;
                --v22;
              }
              while ( v22 );
              v25 = v23 - 1;
              if ( v22 )
                v25 = v23;
              *v25 = 0;
              v13 = -2147024774;
              if ( v22 )
                v13 = 0;
            }
          }
          LODWORD(v44) = 1;
          v26 = 104LL * v16;
          *(_DWORD *)&v15[v26] = a3;
          if ( a3 == 1 )
          {
            *(_OWORD *)&v15[v26 + 4] = v40;
            *(_OWORD *)&v15[v26 + 20] = v41;
            *(_OWORD *)&v15[v26 + 36] = v42;
            *(_OWORD *)&v15[v26 + 52] = *(_OWORD *)v43.m256i_i8;
            *(_OWORD *)&v15[v26 + 64] = *(_OWORD *)((char *)&v43.m256i_u64[1] + 4);
          }
          else if ( a3 == 2 )
          {
            *(_OWORD *)&v15[v26 + 4] = v40;
            *(_OWORD *)&v15[v26 + 20] = v41;
            *(_OWORD *)&v15[v26 + 36] = v42;
            *(__m256i *)&v15[v26 + 52] = v43;
            *(_OWORD *)&v15[v26 + 84] = v44;
            *(_DWORD *)&v15[v26 + 100] = v45;
          }
          v27 = v39;
          v39 = 0;
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          ++v16;
        }
      }
      *a2 = v15;
      v4 = v38;
      *v38 = v16;
      if ( v13 >= 0 )
        goto LABEL_52;
      v30 = 1;
LABEL_115:
      LocalFree(v15);
    }
    else
    {
      v13 = -2147024882;
      v4 = v38;
      v30 = 1;
    }
LABEL_71:
    *a2 = 0;
    *v4 = 0;
    if ( !v30 )
      goto LABEL_53;
    goto LABEL_52;
  }
  v13 = 0;
LABEL_52:
  v28 = RpcRevertToSelf();
  if ( v28 )
  {
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v28);
  }
LABEL_53:
  v46 = &CRpcCallTrace::`vftable';
  if ( v53 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v51, v48[0]);
  v46 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v50 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_55;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_55:
  v49 = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800183a0  mov     [rsp-8+arg_0], rbx
0x1800183a5  push    rbp
0x1800183a6  push    rsi
0x1800183a7  push    rdi
0x1800183a8  push    r12
0x1800183aa  push    r13
0x1800183ac  push    r14
0x1800183ae  push    r15
0x1800183b0  lea     rbp, [rsp-390h]
0x1800183b8  sub     rsp, 490h
0x1800183bf  mov     rax, cs:__security_cookie
0x1800183c6  xor     rax, rsp
0x1800183c9  mov     [rbp+3C0h+var_40], rax
0x1800183d0  mov     r14, r9
0x1800183d3  mov     [rsp+4C0h+var_478], r9
0x1800183d8  mov     r15d, r8d
0x1800183db  mov     r13, rdx
0x1800183de  mov     rdi, rcx
0x1800183e1  xor     r12d, r12d
0x1800183e4  mov     [rsp+4C0h+var_488], r12
0x1800183e9  mov     [rsp+4C0h+var_470], r12
0x1800183ee  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800183f5  mov     [rbp+3C0h+var_3F0], rax
0x1800183f9  mov     [rbp+3C0h+var_3D4], 1
0x180018400  mov     [rbp+3C0h+var_3D0], r12
0x180018404  lea     rbx, aRpcgetenumresu; "RpcGetEnumResult"
0x18001840b  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x180018412  jnz     loc_1800189FF
0x180018418  lea     rcx, [rbp+3C0h+pguid]; pguid
0x18001841c  call    cs:__imp_CoCreateGuid
0x180018423  nop     dword ptr [rax+rax+00h]
0x180018428  mov     eax, 1
0x18001842d  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x180018435  inc     eax
0x180018437  mov     [rbp+3C0h+var_3D8], eax
0x18001843a  mov     [rbp+3C0h+var_3C8], r12d
0x18001843e  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180018445  mov     [rbp+3C0h+var_3F0], rax
0x180018449  mov     [rbp+3C0h+var_3C0], rbx
0x18001844d  mov     qword ptr [rbp+3C0h+Pid], 0FFFFFFFFFFFFFFFFh
0x180018455  mov     [rbp+3C0h+var_3B0], r12d
0x180018459  xor     edx, edx; Val
0x18001845b  mov     r8d, 208h; Size
0x180018461  lea     rcx, [rbp+3C0h+var_3AC]; void *
0x180018465  call    memset_0
0x18001846a  cmp     [rbp+3C0h+var_3B0], r12d
0x18001846e  jnz     loc_18001894E
0x180018474  mov     esi, r12d
0x180018477  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001847e  jnz     loc_180018AF1
0x180018484  mov     qword ptr [rbp+3C0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001848c  lea     rdx, [rbp+3C0h+Pid+4]; Pid
0x180018490  xor     ecx, ecx; Binding
0x180018492  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180018499  nop     dword ptr [rax+rax+00h]
0x18001849e  mov     ebx, eax
0x1800184a0  test    eax, eax
0x1800184a2  jg      loc_1800188DD
0x1800184a8  test    ebx, ebx
0x1800184aa  js      short loc_1800184C7
0x1800184ac  lea     rdx, [rbp+3C0h+Pid]; pSessionId
0x1800184b0  mov     ecx, [rbp+3C0h+Pid+4]; dwProcessId
0x1800184b3  call    cs:__imp_ProcessIdToSessionId
0x1800184ba  nop     dword ptr [rax+rax+00h]
0x1800184bf  test    esi, esi
0x1800184c1  jnz     loc_180018AFB
0x1800184c7  cmp     [rbp+3C0h+var_3B0], r12d
0x1800184cb  jnz     loc_1800189A4
0x1800184d1  test    rdi, rdi
0x1800184d4  jz      loc_180018B9B
0x1800184da  mov     rbx, [rdi+638h]
0x1800184e1  test    rbx, rbx
0x1800184e4  jz      short loc_1800184F5
0x1800184e6  mov     rax, [rbx]
0x1800184e9  mov     rcx, rbx
0x1800184ec  mov     rax, [rax+8]
0x1800184f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184f5  test    r13, r13
0x1800184f8  jz      loc_1800188C1
0x1800184fe  test    r14, r14
0x180018501  jz      loc_1800188C1
0x180018507  mov     [r13+0], r12
0x18001850b  mov     [r14], r12d
0x18001850e  xor     ecx, ecx; BindingHandle
0x180018510  call    cs:__imp_RpcImpersonateClient
0x180018517  nop     dword ptr [rax+rax+00h]
0x18001851c  mov     edi, eax
0x18001851e  test    eax, eax
0x180018520  jg      loc_1800188EB
0x180018526  test    edi, edi
0x180018528  js      loc_180018BC2
0x18001852e  cmp     r15d, 2
0x180018532  ja      loc_180018BE2
0x180018538  mov     r14d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x18001853f  test    r14d, r14d
0x180018542  jz      loc_1800188B9
0x180018548  mov     [rsp+4C0h+var_490], 1
0x180018550  imul    rdx, r14, 68h ; 'h'; uBytes
0x180018554  mov     ecx, 40h ; '@'; uFlags
0x180018559  call    cs:__imp_LocalAlloc
0x180018560  nop     dword ptr [rax+rax+00h]
0x180018565  mov     r12, rax
0x180018568  test    rax, rax
0x18001856b  jz      loc_180018BED
0x180018571  mov     rax, [rbx]
0x180018574  mov     rcx, rbx
0x180018577  mov     rax, [rax+58h]
0x18001857b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018580  xor     esi, esi
0x180018582  cmp     esi, r14d
0x180018585  jnb     loc_180018783
0x18001858b  mov     rcx, [rsp+4C0h+var_488]
0x180018590  mov     [rsp+4C0h+var_488], 0
0x180018599  test    rcx, rcx
0x18001859c  jz      short loc_1800185AA
0x18001859e  mov     rax, [rcx]
0x1800185a1  mov     rax, [rax+10h]
0x1800185a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185aa  mov     rax, [rbx]
0x1800185ad  lea     rdx, [rsp+4C0h+var_488]
0x1800185b2  mov     rcx, rbx
0x1800185b5  mov     rax, [rax+50h]
0x1800185b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185be  mov     edi, eax
0x1800185c0  cmp     eax, 80070103h
0x1800185c5  jz      loc_180018781
0x1800185cb  test    eax, eax
0x1800185cd  js      loc_180018C32
0x1800185d3  mov     rcx, [rsp+4C0h+var_488]
0x1800185d8  mov     rax, [rcx]
0x1800185db  xor     r8d, r8d
0x1800185de  mov     edx, 1
0x1800185e3  mov     rax, [rax+88h]
0x1800185ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185ef  test    eax, eax
0x1800185f1  js      loc_180018C03
0x1800185f7  xorps   xmm0, xmm0
0x1800185fa  xor     eax, eax
0x1800185fc  movups  [rsp+4C0h+var_460], xmm0
0x180018601  movups  [rsp+4C0h+var_450], xmm0
0x180018606  movups  [rbp+3C0h+var_440], xmm0
0x18001860a  movups  [rbp+3C0h+var_430], xmm0
0x18001860e  movups  [rbp+3C0h+var_420], xmm0
0x180018612  movups  [rbp+3C0h+var_410], xmm0
0x180018616  mov     [rbp+3C0h+var_400], eax
0x180018619  mov     rcx, [rsp+4C0h+var_488]
0x18001861e  mov     rax, [rcx]
0x180018621  lea     rdx, [rsp+4C0h+var_460]
0x180018626  mov     rax, [rax+50h]
0x18001862a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001862f  mov     edi, eax
0x180018631  mov     dword ptr [rsp+4C0h+var_480], 0
0x180018639  mov     rcx, [rsp+4C0h+var_488]
0x18001863e  mov     rax, [rcx]
0x180018641  lea     rdx, [rsp+4C0h+var_480]
0x180018646  mov     rax, [rax+58h]
0x18001864a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001864f  movsxd  rax, dword ptr [rsp+4C0h+var_480]
0x180018654  cmp     eax, 1
0x180018657  jnz     loc_180018771
0x18001865d  mov     eax, 9; jumptable 0000000180018869 case 0
0x180018662  mov     dword ptr [rsp+4C0h+var_460+4], eax
0x180018666  xor     eax, eax
0x180018668  mov     [rbp+3C0h+var_90], ax
0x18001866f  mov     rcx, [rsp+4C0h+var_488]
0x180018674  mov     rax, [rcx]
0x180018677  lea     rdx, [rsp+4C0h+var_470]
0x18001867c  mov     rax, [rax+68h]
0x180018680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018685  mov     rcx, [rsp+4C0h+var_470]
0x18001868a  test    rcx, rcx
0x18001868d  jz      short loc_1800186FC
0x18001868f  mov     rax, [rcx]
0x180018692  lea     rdx, [rbp+3C0h+var_90]
0x180018699  mov     rax, [rax+68h]
0x18001869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a2  mov     edi, eax
0x1800186a4  test    eax, eax
0x1800186a6  js      short loc_1800186FC
0x1800186a8  mov     ecx, 7FFFFFFEh
0x1800186ad  lea     rdx, [rbp+3C0h+var_90]
0x1800186b4  mov     r8d, 21h ; '!'
0x1800186ba  lea     r9, [rsp+4C0h+var_460+8]
0x1800186bf  test    rcx, rcx
0x1800186c2  jz      short loc_1800186E1
0x1800186c4  movzx   eax, word ptr [rdx]
0x1800186c7  test    ax, ax
0x1800186ca  jz      short loc_1800186E1
0x1800186cc  add     rdx, 2
0x1800186d0  mov     [r9], ax
0x1800186d4  add     r9, 2
0x1800186d8  dec     rcx
0x1800186db  sub     r8, 1
0x1800186df  jnz     short loc_1800186BF
0x1800186e1  lea     rcx, [r9-2]
0x1800186e5  test    r8, r8
0x1800186e8  cmovnz  rcx, r9
0x1800186ec  xor     eax, eax
0x1800186ee  mov     [rcx], ax
0x1800186f1  mov     edi, 8007007Ah
0x1800186f6  test    r8, r8
0x1800186f9  cmovnz  edi, eax
0x1800186fc  mov     dword ptr [rbp+3C0h+var_410], 1
0x180018703  mov     eax, esi
0x180018705  imul    rcx, rax, 68h ; 'h'
0x180018709  mov     [rcx+r12], r15d
0x18001870d  cmp     r15d, 1
0x180018711  jnz     loc_1800188F9
0x180018717  movaps  xmm0, [rsp+4C0h+var_460]
0x18001871c  movups  xmmword ptr [rcx+r12+4], xmm0
0x180018722  movaps  xmm1, [rsp+4C0h+var_450]
0x180018727  movups  xmmword ptr [rcx+r12+14h], xmm1
0x18001872d  movaps  xmm0, [rbp+3C0h+var_440]
0x180018731  movups  xmmword ptr [rcx+r12+24h], xmm0
0x180018737  movaps  xmm1, [rbp+3C0h+var_430]
0x18001873b  movups  xmmword ptr [rcx+r12+34h], xmm1
0x180018741  movups  xmm0, [rbp+3C0h+var_430+0Ch]
0x180018745  movups  xmmword ptr [rcx+r12+40h], xmm0
0x18001874b  mov     rcx, [rsp+4C0h+var_470]
0x180018750  mov     [rsp+4C0h+var_470], 0
0x180018759  test    rcx, rcx
0x18001875c  jz      short loc_18001876A
0x18001875e  mov     rax, [rcx]
0x180018761  mov     rax, [rax+10h]
0x180018765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001876a  inc     esi
0x18001876c  jmp     loc_180018582
0x180018771  cmp     eax, 0Ch
0x180018774  jnz     loc_18001884F
0x18001877a  xor     eax, eax; jumptable 0000000180018869 case 5
0x18001877c  jmp     loc_180018662
0x180018781  xor     edi, edi
0x180018783  mov     [r13+0], r12
0x180018787  mov     r14, [rsp+4C0h+var_478]
0x18001878c  mov     [r14], esi
0x18001878f  test    edi, edi
0x180018791  js      loc_180018C58
0x180018797  xor     r12d, r12d
0x18001879a  call    cs:__imp_RpcRevertToSelf
0x1800187a1  nop     dword ptr [rax+rax+00h]
0x1800187a6  test    eax, eax
0x1800187a8  jnz     loc_180018AB0
0x1800187ae  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x1800187b5  mov     [rbp+3C0h+var_3F0], rax
0x1800187b9  cmp     [rbp+3C0h+var_3B0], 0
0x1800187bd  jnz     loc_180018979
0x1800187c3  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x1800187ca  mov     [rbp+3C0h+var_3F0], rax
0x1800187ce  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x1800187d5  jnz     loc_180018879
0x1800187db  mov     [rbp+3C0h+var_3D0], r12
0x1800187df  test    rbx, rbx
0x1800187e2  jz      short loc_1800187F4
0x1800187e4  mov     rax, [rbx]
0x1800187e7  mov     rcx, rbx
0x1800187ea  mov     rax, [rax+10h]
0x1800187ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187f3  nop
0x1800187f4  mov     rcx, [rsp+4C0h+var_470]
0x1800187f9  test    rcx, rcx
0x1800187fc  jz      short loc_18001880B
0x1800187fe  mov     rax, [rcx]
0x180018801  mov     rax, [rax+10h]
0x180018805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001880a  nop
0x18001880b  mov     rcx, [rsp+4C0h+var_488]
0x180018810  test    rcx, rcx
0x180018813  jz      short loc_180018822
0x180018815  mov     rax, [rcx]
0x180018818  mov     rax, [rax+10h]
0x18001881c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018821  nop
0x180018822  mov     eax, edi
0x180018824  mov     rcx, [rbp+3C0h+var_40]
0x18001882b  xor     rcx, rsp; StackCookie
0x18001882e  call    __security_check_cookie
0x180018833  mov     rbx, [rsp+4C0h+arg_0]
0x18001883b  add     rsp, 490h
0x180018842  pop     r15
0x180018844  pop     r14
0x180018846  pop     r13
0x180018848  pop     r12
0x18001884a  pop     rdi
0x18001884b  pop     rsi
0x18001884c  pop     rbp
0x18001884d  retn
0x18001884f  cmp     eax, 0Dh; switch 14 cases
0x180018852  ja      def_180018869; jumptable 0000000180018869 default case, cases 1,10-12
0x180018858  lea     rdx, __ImageBase
0x18001885f  mov     ecx, ds:(jpt_180018869 - 180000000h)[rdx+rax*4]
0x180018866  add     rcx, rdx
0x180018869  jmp     rcx; switch jump
0x18001886f  mov     eax, 4; jumptable 0000000180018869 cases 3,4,13
0x180018874  jmp     loc_180018662
0x180018879  cmp     [rbp+3C0h+var_3C8], 0
0x18001887d  jnz     loc_1800187DB
0x180018883  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x180018889  cmp     ecx, 0FFFFFFFFh
0x18001888c  jz      loc_1800187DB
0x180018892  xor     edx, edx; lpTlsValue
  ... truncated ...
```
