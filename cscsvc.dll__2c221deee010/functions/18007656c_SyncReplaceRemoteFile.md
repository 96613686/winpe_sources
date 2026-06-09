# SyncReplaceRemoteFile

- ea: `0x18007656c`
- end: `0x180076918`
- name: `SyncReplaceRemoteFile`
- size: `940`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18007d2b0`

## callees

- `0x180004c40`
- `0x1800068b0`
- `0x180020ef0`
- `0x1800223c0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c488`
- `0x18003e928`
- `0x180069038`
- `0x18006f0c8`
- `0x18007656c`
- `0x180076920`

## import_xrefs

- `ntdll!RtlGetLastNtStatus` at `0x1800766b8`
- `ntdll!RtlGetLastNtStatus` at `0x1800766f6`
- `ntdll!RtlGetLastNtStatus` at `0x180076742`
- `ntdll!RtlGetLastNtStatus` at `0x1800766b8`
- `ntdll!RtlGetLastNtStatus` at `0x1800766f6`
- `ntdll!RtlGetLastNtStatus` at `0x180076742`
- `ntdll!RtlInitUnicodeString` at `0x1800767b7`
- `ntdll!RtlInitUnicodeString` at `0x1800767b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800766c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800766fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007672b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007677f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800766c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800766fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007672b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007677f`
- `KERNEL32!ReplaceFileW` at `0x180076683`
- `KERNEL32!ReplaceFileW` at `0x180076683`

## string_xrefs

- `0x1800766cf`: `ReplaceFile with failed error = %u: status = 0x%08x, IgnoreAcls = %c`
- `0x180076768`: `ReplaceFile failed with error = %u`
- `0x180076854`: `File open for delete failed with 0x%08x`

## pseudocode

```c
__int64 __fastcall SyncReplaceRemoteFile(unsigned __int16 *a1, __int64 a2, __int64 a3, char a4)
{
  LPCWSTR v4; // r15
  __int64 v7; // rcx
  DWORD v8; // edi
  NTSTATUS RemoteBypassPath; // ebx
  unsigned int v12; // edi
  int FullChildName; // eax
  const WCHAR *v14; // r14
  unsigned int LastNtStatus; // ebx
  DWORD LastError; // eax
  __int64 v17; // rsi
  NTSTATUS v18; // ebx
  DWORD v19; // eax
  DWORD v20; // eax
  __int64 v21; // rbx
  DWORD v22; // eax
  int v23; // edi
  int lpReserved; // [rsp+28h] [rbp-38h]
  LPCWSTR lpReplacementFileName[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v27; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpReplacedFileName; // [rsp+90h] [rbp+30h] BYREF
  int v29; // [rsp+A8h] [rbp+48h] BYREF

  v4 = 0;
  v29 = 0;
  lpReplacementFileName[0] = 0;
  lpReplacedFileName = 0;
  v7 = *a1;
  v8 = a4 != 0 ? 4 : 0;
  v27 = 0;
  if ( (unsigned __int64)(v7 + 16) <= 0xFFFF )
  {
    WORD1(v27) = v7 + 16;
    *((_QWORD *)&v27 + 1) = SyncAlloc();
    if ( *((_QWORD *)&v27 + 1) )
    {
      RemoteBypassPath = CscDriverGetRemoteBypassPath(a1, &v27, &v29);
      if ( RemoteBypassPath >= 0 )
      {
        FullChildName = SyncReplacepGetFullChildName(&v27, a2, lpReplacementFileName);
        v14 = lpReplacementFileName[0];
        RemoteBypassPath = FullChildName;
        if ( FullChildName >= 0 )
        {
          RemoteBypassPath = SyncReplacepGetFullChildName(&v27, a3, &lpReplacedFileName);
          if ( RemoteBypassPath >= 0 )
          {
            v4 = lpReplacedFileName;
            if ( ReplaceFileW(lpReplacedFileName, v14, 0, v8, 0, 0) )
            {
              v12 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                LastNtStatus = RtlGetLastNtStatus();
                LastError = GetLastError();
                SyncTraceOutputInternal(
                  L"ReplaceFile with failed error = %u: status = 0x%08x, IgnoreAcls = %c",
                  LastError,
                  LastNtStatus,
                  a4 != 0 ? 89 : 78);
                v17 = *((_QWORD *)WPP_GLOBAL_Control + 12);
                v18 = RtlGetLastNtStatus();
                v19 = GetLastError();
                LOBYTE(lpReserved) = a4 != 0 ? 89 : 78;
                WPP_SF_DDc(v17, 67, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v19, v18, lpReserved);
              }
              if ( GetLastError() == 87 && a4 )
              {
                RemoteBypassPath = -1073741790;
              }
              else
              {
                RemoteBypassPath = RtlGetLastNtStatus();
                if ( RemoteBypassPath >= 0 )
                {
                  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                  {
                    v20 = GetLastError();
                    SyncTraceOutputInternal(L"ReplaceFile failed with error = %u", v20);
                    v21 = *((_QWORD *)WPP_GLOBAL_Control + 12);
                    v22 = GetLastError();
                    WPP_SF_d(v21, 68, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v22);
                  }
                  RemoteBypassPath = -1073741823;
                }
              }
              lpReplacedFileName = 0;
              *(_OWORD *)lpReplacementFileName = 0;
              RtlInitUnicodeString((PUNICODE_STRING)lpReplacementFileName, v14);
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                SyncTraceOutputInternal(L"Deleting SourceFile <%ws> on failure", v14);
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 69, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v14);
              }
              v23 = CscDriverOpenItemWithDispositionEx((PHANDLE)&lpReplacedFileName, 1114112, 7u, 1u, 4128);
              if ( v23 < 0 )
              {
                if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                {
                  SyncTraceOutputInternal(L"File open for delete failed with 0x%08x", (unsigned int)v23);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 12),
                    70,
                    WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
                    (unsigned int)v23);
                }
              }
              else
              {
                SyncCloseFile((HANDLE)lpReplacedFileName);
              }
              v12 = 1121;
            }
          }
          else
          {
            v4 = lpReplacedFileName;
            v12 = 1051;
          }
        }
        else
        {
          v12 = 1046;
        }
        if ( v14 )
          SyncFree(v14);
        if ( v4 )
          SyncFree(v4);
      }
      else
      {
        v12 = 1041;
      }
    }
    else
    {
      RemoteBypassPath = -1073741670;
      v12 = 1035;
    }
  }
  else
  {
    RemoteBypassPath = -1073741675;
    v12 = 1026;
  }
  if ( *((_QWORD *)&v27 + 1) )
    SyncFree(*((_QWORD *)&v27 + 1));
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"Status = 0x%08x ( EE = %u )", (unsigned int)RemoteBypassPath, v12);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      71,
      WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
      (unsigned int)RemoteBypassPath,
      v12);
  }
  return (unsigned int)RemoteBypassPath;
}

```

## disassembly

```asm
0x18007656c  mov     [rsp-28h+arg_8], rbx
0x180076571  mov     [rsp-28h+arg_10], rsi
0x180076576  push    rbp
0x180076577  push    rdi
0x180076578  push    r12
0x18007657a  push    r14
0x18007657c  push    r15
0x18007657e  mov     rbp, rsp
0x180076581  sub     rsp, 60h
0x180076585  xor     r15d, r15d
0x180076588  mov     [rbp+arg_18], 0
0x18007658f  mov     al, r9b
0x180076592  mov     [rbp+lpReplacementFileName], 0
0x18007659a  neg     al
0x18007659c  mov     [rbp+lpReplacedFileName], r15
0x1800765a0  mov     rbx, rcx
0x1800765a3  mov     r14, rdx
0x1800765a6  movzx   ecx, word ptr [rcx]
0x1800765a9  lea     edx, [r15+10h]
0x1800765ad  sbb     edi, edi
0x1800765af  xorps   xmm0, xmm0
0x1800765b2  and     edi, 4
0x1800765b5  mov     r12b, r9b
0x1800765b8  mov     rsi, r8
0x1800765bb  lea     rax, [rdx+rcx]
0x1800765bf  movups  [rbp+var_10], xmm0
0x1800765c3  cmp     rax, 0FFFFh
0x1800765c9  jbe     short loc_1800765DA
0x1800765cb  mov     ebx, 0C0000095h
0x1800765d0  mov     edi, 402h
0x1800765d5  jmp     loc_1800768A2
0x1800765da  add     cx, dx
0x1800765dd  movzx   ecx, cx
0x1800765e0  mov     word ptr [rbp+var_10+2], cx
0x1800765e4  call    SyncAlloc
0x1800765e9  mov     qword ptr [rbp+var_10+8], rax
0x1800765ed  test    rax, rax
0x1800765f0  jnz     short loc_180076601
0x1800765f2  mov     ebx, 0C000009Ah
0x1800765f7  mov     edi, 40Bh
0x1800765fc  jmp     loc_1800768A2
0x180076601  lea     r8, [rbp+arg_18]
0x180076605  mov     rcx, rbx
0x180076608  lea     rdx, [rbp+var_10]
0x18007660c  call    CscDriverGetRemoteBypassPath
0x180076611  mov     ebx, eax
0x180076613  test    eax, eax
0x180076615  jns     short loc_180076621
0x180076617  mov     edi, 411h
0x18007661c  jmp     loc_1800768A2
0x180076621  lea     r8, [rbp+lpReplacementFileName]
0x180076625  mov     rdx, r14
0x180076628  lea     rcx, [rbp+var_10]
0x18007662c  call    SyncReplacepGetFullChildName
0x180076631  mov     r14, [rbp+lpReplacementFileName]
0x180076635  mov     ebx, eax
0x180076637  test    eax, eax
0x180076639  jns     short loc_180076645
0x18007663b  mov     edi, 416h
0x180076640  jmp     loc_180076888
0x180076645  lea     r8, [rbp+lpReplacedFileName]
0x180076649  mov     rdx, rsi
0x18007664c  lea     rcx, [rbp+var_10]
0x180076650  call    SyncReplacepGetFullChildName
0x180076655  mov     ebx, eax
0x180076657  test    eax, eax
0x180076659  jns     short loc_180076669
0x18007665b  mov     r15, [rbp+lpReplacedFileName]
0x18007665f  mov     edi, 41Bh
0x180076664  jmp     loc_180076888
0x180076669  mov     [rsp+60h+lpReserved], r15; lpReserved
0x18007666e  mov     r9d, edi; dwReplaceFlags
0x180076671  mov     [rsp+60h+lpExclude], r15; lpExclude
0x180076676  xor     r8d, r8d; lpBackupFileName
0x180076679  mov     r15, [rbp+lpReplacedFileName]
0x18007667d  mov     rdx, r14; lpReplacementFileName
0x180076680  mov     rcx, r15; lpReplacedFileName
0x180076683  call    cs:__imp_ReplaceFileW
0x180076689  test    eax, eax
0x18007668b  jnz     loc_180076886
0x180076691  mov     rax, cs:WPP_GLOBAL_Control
0x180076698  lea     rsi, WPP_GLOBAL_Control
0x18007669f  cmp     rax, rsi
0x1800766a2  jz      loc_18007672B
0x1800766a8  test    byte ptr [rax+6Ch], 1
0x1800766ac  jz      short loc_18007672B
0x1800766ae  mov     al, r12b
0x1800766b1  neg     al
0x1800766b3  sbb     edi, edi
0x1800766b5  and     edi, 0Bh
0x1800766b8  call    cs:__imp_RtlGetLastNtStatus
0x1800766be  mov     ebx, eax
0x1800766c0  call    cs:__imp_GetLastError
0x1800766c6  lea     r9d, [rdi+4Eh]
0x1800766ca  mov     r8d, ebx
0x1800766cd  mov     edx, eax
0x1800766cf  lea     rcx, aReplacefileWit; "ReplaceFile with failed error = %u: sta"...
0x1800766d6  call    SyncTraceOutputInternal
0x1800766db  mov     rax, cs:WPP_GLOBAL_Control
0x1800766e2  mov     rsi, [rax+60h]
0x1800766e6  mov     al, r12b
0x1800766e9  neg     al
0x1800766eb  sbb     dil, dil
0x1800766ee  and     dil, 0Bh
0x1800766f2  add     dil, 4Eh ; 'N'
0x1800766f6  call    cs:__imp_RtlGetLastNtStatus
0x1800766fc  mov     ebx, eax
0x1800766fe  call    cs:__imp_GetLastError
0x180076704  mov     edx, 43h ; 'C'
0x180076709  mov     byte ptr [rsp+60h+lpReserved], dil
0x18007670e  mov     r9d, eax
0x180076711  mov     dword ptr [rsp+60h+lpExclude], ebx
0x180076715  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18007671c  mov     rcx, rsi
0x18007671f  call    WPP_SF_DDc
0x180076724  lea     rsi, WPP_GLOBAL_Control
0x18007672b  call    cs:__imp_GetLastError
0x180076731  cmp     eax, 57h ; 'W'
0x180076734  jnz     short loc_180076742
0x180076736  test    r12b, r12b
0x180076739  jz      short loc_180076742
0x18007673b  mov     ebx, 0C0000022h
0x180076740  jmp     short loc_1800767A1
0x180076742  call    cs:__imp_RtlGetLastNtStatus
0x180076748  mov     ebx, eax
0x18007674a  test    eax, eax
0x18007674c  js      short loc_1800767A1
0x18007674e  mov     rax, cs:WPP_GLOBAL_Control
0x180076755  cmp     rax, rsi
0x180076758  jz      short loc_18007679C
0x18007675a  test    byte ptr [rax+6Ch], 1
0x18007675e  jz      short loc_18007679C
0x180076760  call    cs:__imp_GetLastError
0x180076766  mov     edx, eax
0x180076768  lea     rcx, aReplacefileFai; "ReplaceFile failed with error = %u"
0x18007676f  call    SyncTraceOutputInternal
0x180076774  mov     rax, cs:WPP_GLOBAL_Control
0x18007677b  mov     rbx, [rax+60h]
0x18007677f  call    cs:__imp_GetLastError
0x180076785  mov     edx, 44h ; 'D'
0x18007678a  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180076791  mov     r9d, eax
0x180076794  mov     rcx, rbx
0x180076797  call    WPP_SF_d
0x18007679c  mov     ebx, 0C0000001h
0x1800767a1  xorps   xmm0, xmm0
0x1800767a4  mov     [rbp+lpReplacedFileName], 0
0x1800767ac  mov     rdx, r14; SourceString
0x1800767af  lea     rcx, [rbp+lpReplacementFileName]; DestinationString
0x1800767b3  movups  xmmword ptr [rbp+lpReplacementFileName], xmm0
0x1800767b7  call    cs:__imp_RtlInitUnicodeString
0x1800767bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800767c4  cmp     rax, rsi
0x1800767c7  jz      short loc_1800767FD
0x1800767c9  test    byte ptr [rax+6Ch], 1
0x1800767cd  jz      short loc_1800767FD
0x1800767cf  mov     rdx, r14
0x1800767d2  lea     rcx, aDeletingSource; "Deleting SourceFile <%ws> on failure"
0x1800767d9  call    SyncTraceOutputInternal
0x1800767de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800767e5  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x1800767ec  mov     edx, 45h ; 'E'
0x1800767f1  mov     r9, r14
0x1800767f4  mov     rcx, [rcx+60h]
0x1800767f8  call    WPP_SF_S
0x1800767fd  mov     [rsp+60h+var_28], 1020h; int
0x180076805  lea     r8, [rbp+lpReplacementFileName]
0x180076809  mov     [rsp+60h+var_30], 1; ULONG
0x180076811  lea     rcx, [rbp+lpReplacedFileName]; FileHandle
0x180076815  mov     dword ptr [rsp+60h+lpReserved], 7; ULONG
0x18007681d  xor     r9d, r9d
0x180076820  xor     edx, edx
0x180076822  mov     dword ptr [rsp+60h+lpExclude], 110000h; int
0x18007682a  call    CscDriverOpenItemWithDispositionEx
0x18007682f  mov     edi, eax
0x180076831  test    eax, eax
0x180076833  js      short loc_180076840
0x180076835  mov     rcx, [rbp+lpReplacedFileName]; Handle
0x180076839  call    SyncCloseFile
0x18007683e  jmp     short loc_18007687F
0x180076840  mov     rax, cs:WPP_GLOBAL_Control
0x180076847  cmp     rax, rsi
0x18007684a  jz      short loc_18007687F
0x18007684c  test    byte ptr [rax+6Ch], 1
0x180076850  jz      short loc_18007687F
0x180076852  mov     edx, edi
0x180076854  lea     rcx, aFileOpenForDel; "File open for delete failed with 0x%08x"
0x18007685b  call    SyncTraceOutputInternal
0x180076860  mov     rcx, cs:WPP_GLOBAL_Control
0x180076867  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18007686e  mov     edx, 46h ; 'F'
0x180076873  mov     r9d, edi
0x180076876  mov     rcx, [rcx+60h]
0x18007687a  call    WPP_SF_d
0x18007687f  mov     edi, 461h
0x180076884  jmp     short loc_180076888
0x180076886  xor     edi, edi
0x180076888  test    r14, r14
0x18007688b  jz      short loc_180076895
0x18007688d  mov     rcx, r14
0x180076890  call    SyncFree
0x180076895  test    r15, r15
0x180076898  jz      short loc_1800768A2
0x18007689a  mov     rcx, r15
0x18007689d  call    SyncFree
0x1800768a2  mov     rcx, qword ptr [rbp+var_10+8]
0x1800768a6  test    rcx, rcx
0x1800768a9  jz      short loc_1800768B0
0x1800768ab  call    SyncFree
0x1800768b0  mov     rax, cs:WPP_GLOBAL_Control
0x1800768b7  lea     rcx, WPP_GLOBAL_Control
0x1800768be  cmp     rax, rcx
0x1800768c1  jz      short loc_1800768FD
0x1800768c3  test    byte ptr [rax+6Ch], 8
0x1800768c7  jz      short loc_1800768FD
0x1800768c9  mov     r8d, edi
0x1800768cc  lea     rcx, aStatus0x08xEeU; "Status = 0x%08x ( EE = %u )"
0x1800768d3  mov     edx, ebx
0x1800768d5  call    SyncTraceOutputInternal
0x1800768da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800768e1  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x1800768e8  mov     edx, 47h ; 'G'
0x1800768ed  mov     dword ptr [rsp+60h+lpExclude], edi
0x1800768f1  mov     r9d, ebx
0x1800768f4  mov     rcx, [rcx+60h]
0x1800768f8  call    WPP_SF_dd
0x1800768fd  lea     r11, [rsp+60h+var_s0]
0x180076902  mov     eax, ebx
0x180076904  mov     rbx, [r11+38h]
0x180076908  mov     rsi, [r11+40h]
0x18007690c  mov     rsp, r11
0x18007690f  pop     r15
0x180076911  pop     r14
0x180076913  pop     r12
0x180076915  pop     rdi
0x180076916  pop     rbp
0x180076917  retn
```
