# RpcGetEnumResult

- ea: `0x18001a160`
- end: `0x18001aa3c`
- name: `RpcGetEnumResult`
- size: `2268`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18000b190`
- `0x18000c700`
- `0x18001a160`
- `0x18001aa50`
- `0x1800271d0`
- `0x18004b460`
- `0x18004bf44`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a8d5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a8d5`
- `ntdll!NtQueryInformationProcess` at `0x18001a8b9`
- `ntdll!NtQueryInformationProcess` at `0x18001a8b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a62b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a9e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a62b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a9e9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001a267`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001a267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a8fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a8fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a301`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a9d3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a1dc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001a1dc`
- `RPCRT4!RpcImpersonateClient` at `0x18001a2be`
- `RPCRT4!RpcImpersonateClient` at `0x18001a2be`
- `RPCRT4!RpcRevertToSelf` at `0x18001a53c`
- `RPCRT4!RpcRevertToSelf` at `0x18001a53c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001a24c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001a24c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a891`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a891`

## string_xrefs

- `0x18001a93f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18001a719`: `%s with Trace ID 0x%x Completed`
- `0x18001a7dc`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001a751`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001a160  mov     [rsp-8+arg_0], rbx
0x18001a165  push    rbp
0x18001a166  push    rsi
0x18001a167  push    rdi
0x18001a168  push    r12
0x18001a16a  push    r13
0x18001a16c  push    r14
0x18001a16e  push    r15
0x18001a170  lea     rbp, [rsp-390h]
0x18001a178  sub     rsp, 490h
0x18001a17f  mov     rax, cs:__security_cookie
0x18001a186  xor     rax, rsp
0x18001a189  mov     [rbp+3C0h+var_40], rax
0x18001a190  mov     r14, r9
0x18001a193  mov     [rsp+4C0h+var_478], r9
0x18001a198  mov     r15d, r8d
0x18001a19b  mov     r13, rdx
0x18001a19e  mov     rdi, rcx
0x18001a1a1  xor     r12d, r12d
0x18001a1a4  mov     [rsp+4C0h+var_488], r12
0x18001a1a9  mov     [rsp+4C0h+var_470], r12
0x18001a1ae  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001a1b5  mov     [rbp+3C0h+var_3F0], rax
0x18001a1b9  mov     [rbp+3C0h+var_3D4], 1
0x18001a1c0  mov     [rbp+3C0h+var_3D0], r12
0x18001a1c4  lea     rbx, aRpcgetenumresu; "RpcGetEnumResult"
0x18001a1cb  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r12d; int CTraceBase::g_bEnabled
0x18001a1d2  jnz     loc_18001A78A
0x18001a1d8  lea     rcx, [rbp+3C0h+pguid]; pguid
0x18001a1dc  call    cs:__imp_CoCreateGuid
0x18001a1e2  mov     eax, 1
0x18001a1e7  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, eax; ulong CTraceBase::g_NextShortActivityID
0x18001a1ef  inc     eax
0x18001a1f1  mov     [rbp+3C0h+var_3D8], eax
0x18001a1f4  mov     [rbp+3C0h+var_3C8], r12d
0x18001a1f8  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001a1ff  mov     [rbp+3C0h+var_3F0], rax
0x18001a203  mov     [rbp+3C0h+var_3C0], rbx
0x18001a207  mov     qword ptr [rbp+3C0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001a20f  mov     [rbp+3C0h+var_3B0], r12d
0x18001a213  xor     edx, edx; Val
0x18001a215  mov     r8d, 208h; Size
0x18001a21b  lea     rcx, [rbp+3C0h+var_3AC]; void *
0x18001a21f  call    memset_0
0x18001a224  cmp     [rbp+3C0h+var_3B0], r12d
0x18001a228  jnz     loc_18001A6D9
0x18001a22e  mov     esi, r12d
0x18001a231  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001a238  jnz     loc_18001A87C
0x18001a23e  mov     qword ptr [rbp+3C0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001a246  lea     rdx, [rbp+3C0h+Pid+4]; Pid
0x18001a24a  xor     ecx, ecx; Binding
0x18001a24c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001a252  mov     ebx, eax
0x18001a254  test    eax, eax
0x18001a256  jg      loc_18001A668
0x18001a25c  test    ebx, ebx
0x18001a25e  js      short loc_18001A275
0x18001a260  lea     rdx, [rbp+3C0h+Pid]; pSessionId
0x18001a264  mov     ecx, [rbp+3C0h+Pid+4]; dwProcessId
0x18001a267  call    cs:__imp_ProcessIdToSessionId
0x18001a26d  test    esi, esi
0x18001a26f  jnz     loc_18001A886
0x18001a275  cmp     [rbp+3C0h+var_3B0], r12d
0x18001a279  jnz     loc_18001A72F
0x18001a27f  test    rdi, rdi
0x18001a282  jz      loc_18001A90E
0x18001a288  mov     rbx, [rdi+638h]
0x18001a28f  test    rbx, rbx
0x18001a292  jz      short loc_18001A2A3
0x18001a294  mov     rax, [rbx]
0x18001a297  mov     rcx, rbx
0x18001a29a  mov     rax, [rax+8]
0x18001a29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2a3  test    r13, r13
0x18001a2a6  jz      loc_18001A64C
0x18001a2ac  test    r14, r14
0x18001a2af  jz      loc_18001A64C
0x18001a2b5  mov     [r13+0], r12
0x18001a2b9  mov     [r14], r12d
0x18001a2bc  xor     ecx, ecx; BindingHandle
0x18001a2be  call    cs:__imp_RpcImpersonateClient
0x18001a2c4  mov     edi, eax
0x18001a2c6  test    eax, eax
0x18001a2c8  jg      loc_18001A676
0x18001a2ce  test    edi, edi
0x18001a2d0  js      loc_18001A935
0x18001a2d6  cmp     r15d, 2
0x18001a2da  ja      loc_18001A955
0x18001a2e0  mov     r14d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x18001a2e7  test    r14d, r14d
0x18001a2ea  jz      loc_18001A644
0x18001a2f0  mov     [rsp+4C0h+var_490], 1
0x18001a2f8  imul    rdx, r14, 68h ; 'h'; uBytes
0x18001a2fc  mov     ecx, 40h ; '@'; uFlags
0x18001a301  call    cs:__imp_LocalAlloc
0x18001a307  mov     r12, rax
0x18001a30a  test    rax, rax
0x18001a30d  jz      loc_18001A960
0x18001a313  mov     rax, [rbx]
0x18001a316  mov     rcx, rbx
0x18001a319  mov     rax, [rax+58h]
0x18001a31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a322  xor     esi, esi
0x18001a324  cmp     esi, r14d
0x18001a327  jnb     loc_18001A525
0x18001a32d  mov     rcx, [rsp+4C0h+var_488]
0x18001a332  mov     [rsp+4C0h+var_488], 0
0x18001a33b  test    rcx, rcx
0x18001a33e  jz      short loc_18001A34C
0x18001a340  mov     rax, [rcx]
0x18001a343  mov     rax, [rax+10h]
0x18001a347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a34c  mov     rax, [rbx]
0x18001a34f  lea     rdx, [rsp+4C0h+var_488]
0x18001a354  mov     rcx, rbx
0x18001a357  mov     rax, [rax+50h]
0x18001a35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a360  mov     edi, eax
0x18001a362  cmp     eax, 80070103h
0x18001a367  jz      loc_18001A523
0x18001a36d  test    eax, eax
0x18001a36f  js      loc_18001A9A5
0x18001a375  mov     rcx, [rsp+4C0h+var_488]
0x18001a37a  mov     rax, [rcx]
0x18001a37d  xor     r8d, r8d
0x18001a380  mov     edx, 1
0x18001a385  mov     rax, [rax+88h]
0x18001a38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a391  test    eax, eax
0x18001a393  js      loc_18001A976
0x18001a399  xorps   xmm0, xmm0
0x18001a39c  xor     eax, eax
0x18001a39e  movups  [rsp+4C0h+var_460], xmm0
0x18001a3a3  movups  [rsp+4C0h+var_450], xmm0
0x18001a3a8  movups  [rbp+3C0h+var_440], xmm0
0x18001a3ac  movups  [rbp+3C0h+var_430], xmm0
0x18001a3b0  movups  [rbp+3C0h+var_420], xmm0
0x18001a3b4  movups  [rbp+3C0h+var_410], xmm0
0x18001a3b8  mov     [rbp+3C0h+var_400], eax
0x18001a3bb  mov     rcx, [rsp+4C0h+var_488]
0x18001a3c0  mov     rax, [rcx]
0x18001a3c3  lea     rdx, [rsp+4C0h+var_460]
0x18001a3c8  mov     rax, [rax+50h]
0x18001a3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3d1  mov     edi, eax
0x18001a3d3  mov     dword ptr [rsp+4C0h+var_480], 0
0x18001a3db  mov     rcx, [rsp+4C0h+var_488]
0x18001a3e0  mov     rax, [rcx]
0x18001a3e3  lea     rdx, [rsp+4C0h+var_480]
0x18001a3e8  mov     rax, [rax+58h]
0x18001a3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3f1  movsxd  rax, dword ptr [rsp+4C0h+var_480]
0x18001a3f6  cmp     eax, 1
0x18001a3f9  jnz     loc_18001A513
0x18001a3ff  mov     eax, 9; jumptable 000000018001A604 case 0
0x18001a404  mov     dword ptr [rsp+4C0h+var_460+4], eax
0x18001a408  xor     eax, eax
0x18001a40a  mov     [rbp+3C0h+var_90], ax
0x18001a411  mov     rcx, [rsp+4C0h+var_488]
0x18001a416  mov     rax, [rcx]
0x18001a419  lea     rdx, [rsp+4C0h+var_470]
0x18001a41e  mov     rax, [rax+68h]
0x18001a422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a427  mov     rcx, [rsp+4C0h+var_470]
0x18001a42c  test    rcx, rcx
0x18001a42f  jz      short loc_18001A49E
0x18001a431  mov     rax, [rcx]
0x18001a434  lea     rdx, [rbp+3C0h+var_90]
0x18001a43b  mov     rax, [rax+68h]
0x18001a43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a444  mov     edi, eax
0x18001a446  test    eax, eax
0x18001a448  js      short loc_18001A49E
0x18001a44a  mov     ecx, 7FFFFFFEh
0x18001a44f  lea     rdx, [rbp+3C0h+var_90]
0x18001a456  mov     r8d, 21h ; '!'
0x18001a45c  lea     r9, [rsp+4C0h+var_460+8]
0x18001a461  test    rcx, rcx
0x18001a464  jz      short loc_18001A483
0x18001a466  movzx   eax, word ptr [rdx]
0x18001a469  test    ax, ax
0x18001a46c  jz      short loc_18001A483
0x18001a46e  add     rdx, 2
0x18001a472  mov     [r9], ax
0x18001a476  add     r9, 2
0x18001a47a  dec     rcx
0x18001a47d  sub     r8, 1
0x18001a481  jnz     short loc_18001A461
0x18001a483  lea     rcx, [r9-2]
0x18001a487  test    r8, r8
0x18001a48a  cmovnz  rcx, r9
0x18001a48e  xor     eax, eax
0x18001a490  mov     [rcx], ax
0x18001a493  mov     edi, 8007007Ah
0x18001a498  test    r8, r8
0x18001a49b  cmovnz  edi, eax
0x18001a49e  mov     dword ptr [rbp+3C0h+var_410], 1
0x18001a4a5  mov     eax, esi
0x18001a4a7  imul    rcx, rax, 68h ; 'h'
0x18001a4ab  mov     [rcx+r12], r15d
0x18001a4af  cmp     r15d, 1
0x18001a4b3  jnz     loc_18001A684
0x18001a4b9  movaps  xmm0, [rsp+4C0h+var_460]
0x18001a4be  movups  xmmword ptr [rcx+r12+4], xmm0
0x18001a4c4  movaps  xmm1, [rsp+4C0h+var_450]
0x18001a4c9  movups  xmmword ptr [rcx+r12+14h], xmm1
0x18001a4cf  movaps  xmm0, [rbp+3C0h+var_440]
0x18001a4d3  movups  xmmword ptr [rcx+r12+24h], xmm0
0x18001a4d9  movaps  xmm1, [rbp+3C0h+var_430]
0x18001a4dd  movups  xmmword ptr [rcx+r12+34h], xmm1
0x18001a4e3  movups  xmm0, [rbp+3C0h+var_430+0Ch]
0x18001a4e7  movups  xmmword ptr [rcx+r12+40h], xmm0
0x18001a4ed  mov     rcx, [rsp+4C0h+var_470]
0x18001a4f2  mov     [rsp+4C0h+var_470], 0
0x18001a4fb  test    rcx, rcx
0x18001a4fe  jz      short loc_18001A50C
0x18001a500  mov     rax, [rcx]
0x18001a503  mov     rax, [rax+10h]
0x18001a507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a50c  inc     esi
0x18001a50e  jmp     loc_18001A324
0x18001a513  cmp     eax, 0Ch
0x18001a516  jnz     loc_18001A5EA
0x18001a51c  xor     eax, eax; jumptable 000000018001A604 case 5
0x18001a51e  jmp     loc_18001A404
0x18001a523  xor     edi, edi
0x18001a525  mov     [r13+0], r12
0x18001a529  mov     r14, [rsp+4C0h+var_478]
0x18001a52e  mov     [r14], esi
0x18001a531  test    edi, edi
0x18001a533  js      loc_18001A9CB
0x18001a539  xor     r12d, r12d
0x18001a53c  call    cs:__imp_RpcRevertToSelf
0x18001a542  test    eax, eax
0x18001a544  jnz     loc_18001A83B
0x18001a54a  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001a551  mov     [rbp+3C0h+var_3F0], rax
0x18001a555  cmp     [rbp+3C0h+var_3B0], 0
0x18001a559  jnz     loc_18001A704
0x18001a55f  lea     rax, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001a566  mov     [rbp+3C0h+var_3F0], rax
0x18001a56a  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18001a571  jnz     loc_18001A610
0x18001a577  mov     [rbp+3C0h+var_3D0], r12
0x18001a57b  test    rbx, rbx
0x18001a57e  jz      short loc_18001A590
0x18001a580  mov     rax, [rbx]
0x18001a583  mov     rcx, rbx
0x18001a586  mov     rax, [rax+10h]
0x18001a58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a58f  nop
0x18001a590  mov     rcx, [rsp+4C0h+var_470]
0x18001a595  test    rcx, rcx
0x18001a598  jz      short loc_18001A5A7
0x18001a59a  mov     rax, [rcx]
0x18001a59d  mov     rax, [rax+10h]
0x18001a5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5a6  nop
0x18001a5a7  mov     rcx, [rsp+4C0h+var_488]
0x18001a5ac  test    rcx, rcx
0x18001a5af  jz      short loc_18001A5BE
0x18001a5b1  mov     rax, [rcx]
0x18001a5b4  mov     rax, [rax+10h]
0x18001a5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5bd  nop
0x18001a5be  mov     eax, edi
0x18001a5c0  mov     rcx, [rbp+3C0h+var_40]
0x18001a5c7  xor     rcx, rsp; StackCookie
0x18001a5ca  call    __security_check_cookie
0x18001a5cf  mov     rbx, [rsp+4C0h+arg_0]
0x18001a5d7  add     rsp, 490h
0x18001a5de  pop     r15
0x18001a5e0  pop     r14
0x18001a5e2  pop     r13
0x18001a5e4  pop     r12
0x18001a5e6  pop     rdi
0x18001a5e7  pop     rsi
0x18001a5e8  pop     rbp
0x18001a5e9  retn
0x18001a5ea  cmp     eax, 0Dh; switch 14 cases
0x18001a5ed  ja      def_18001A604; jumptable 000000018001A604 default case, cases 1,10-12
0x18001a5f3  lea     rdx, __ImageBase
0x18001a5fa  mov     ecx, ds:(jpt_18001A604 - 180000000h)[rdx+rax*4]
0x18001a601  add     rcx, rdx
0x18001a604  jmp     rcx; switch jump
0x18001a606  mov     eax, 4; jumptable 000000018001A604 cases 3,4,13
0x18001a60b  jmp     loc_18001A404
0x18001a610  cmp     [rbp+3C0h+var_3C8], 0
0x18001a614  jnz     loc_18001A577
0x18001a61a  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001a620  cmp     ecx, 0FFFFFFFFh
0x18001a623  jz      loc_18001A577
0x18001a629  xor     edx, edx; lpTlsValue
0x18001a62b  call    cs:__imp_TlsSetValue
0x18001a631  test    eax, eax
0x18001a633  jnz     loc_18001A9E1
0x18001a639  call    cs:__imp_GetLastError
0x18001a63f  jmp     loc_18001A9F7
0x18001a644  mov     edi, r12d
  ... truncated ...
```
