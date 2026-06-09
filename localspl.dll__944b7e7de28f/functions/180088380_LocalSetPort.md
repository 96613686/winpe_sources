# LocalSetPort

- ea: `0x180088380`
- end: `0x18008884e`
- name: `LocalSetPort`
- size: `1230`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800051f0`
- `0x180007e94`
- `0x1800080bc`
- `0x1800080f8`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x180009630`
- `0x180011f00`
- `0x180024a58`
- `0x180026584`
- `0x18003ea2c`
- `0x18004486c`
- `0x180046650`
- `0x180054638`
- `0x180061dd8`
- `0x180065dd4`
- `0x180088380`
- `0x1800e2e08`
- `0x1800e2f78`
- `0x1800e3004`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800884bf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800884bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180088702`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008870f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180088702`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008870f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180088808`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180088808`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180088817`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180088817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800885fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800885fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180088489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180088692`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180088489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180088692`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008847c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008847c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800887ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800887ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180088737`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800887e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180088737`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800887e7`
- `SPOOLSS!DllFreeSplStr` at `0x1800885b8`
- `SPOOLSS!DllFreeSplStr` at `0x1800885d0`
- `SPOOLSS!DllFreeSplStr` at `0x18008861e`
- `SPOOLSS!DllFreeSplStr` at `0x1800885b8`
- `SPOOLSS!DllFreeSplStr` at `0x1800885d0`
- `SPOOLSS!DllFreeSplStr` at `0x18008861e`
- `SPOOLSS!AllocSplStr` at `0x1800885ec`
- `SPOOLSS!AllocSplStr` at `0x180088628`
- `SPOOLSS!AllocSplStr` at `0x1800885ec`
- `SPOOLSS!AllocSplStr` at `0x180088628`

## pseudocode

```c
__int64 __fastcall LocalSetPort(LPCWSTR lpString1, unsigned __int16 *a2, int a3, __int64 a4)
{
  int v5; // r14d
  const WCHAR *v7; // rdi
  __int64 SpoolerByNameIncRef; // rbp
  void *v9; // rdx
  SecurityHelper *v10; // rcx
  void *v11; // rdx
  SecurityHelper *v12; // rcx
  void *v13; // rdx
  SecurityHelper *v14; // rcx
  DWORD LastError; // ebx
  int v16; // r12d
  int v17; // eax
  wchar_t *v18; // rax
  __int64 IniKey; // rax
  __int64 v20; // rdi
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ebx
  __int64 v25; // rdx
  int v26; // r14d
  int v27; // r15d
  __int64 v28; // rax
  __int64 v29; // r9
  unsigned __int16 *v30; // rax
  __int64 v31; // rdx
  int v32; // ecx
  int v33; // r8d
  _WORD *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v39; // ebx
  void *v40; // rcx
  HANDLE v41; // rcx
  int v42; // ebx
  __int64 v43; // rcx
  __int64 v44; // rax
  void *v45; // rcx
  DWORD TickCount; // eax
  void *v47; // rcx
  __int64 v48; // [rsp+20h] [rbp-298h]
  __int64 v49; // [rsp+28h] [rbp-290h]
  wchar_t Str[272]; // [rsp+40h] [rbp-278h] BYREF

  v5 = a3;
  v7 = lpString1;
  SpoolerByNameIncRef = FindSpoolerByNameIncRef(lpString1);
  if ( (unsigned int)IsWindowsProtectedPrintEnabled()
    && !(unsigned int)SecurityHelper::IsLocalSystem(v10, v9)
    && !(unsigned int)SecurityHelper::IsRestrictedSpoolerWorker(v12, v11)
    && !SecurityHelper::IsInAdministratorGroup(v14, v13) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "LocalSetPort",
      L"LocalSetPort failed: only LocalSystem or an Administrator is allowed to set a port in Windows Protected Print mode.");
    LastError = 50;
    if ( SpoolerByNameIncRef )
    {
      v16 = 0;
      goto LABEL_54;
    }
LABEL_57:
    LODWORD(v49) = LastError;
    LODWORD(v48) = v5;
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "LocalSetPort",
      L"Failed for '%ws', port '%ws', level %d.  Error %d",
      v7,
      a2,
      v48,
      v49);
    SetLastError(LastError);
    return 0;
  }
  if ( !SpoolerByNameIncRef )
  {
    LastError = 123;
    goto LABEL_57;
  }
  v16 = 0;
  if ( !(unsigned int)MyName(v7) )
  {
    LastError = GetLastError();
    goto LABEL_54;
  }
  v17 = IsCallViaRPC();
  if ( !(unsigned int)ValidateObjectAccess(0, 2 - (unsigned int)(v17 != 0), 0, 0, SpoolerByNameIncRef, 1) )
  {
    LastError = GetLastError();
    if ( LastError != 5 || TlsGetValue(gdwTlsSetPortIndex) )
    {
      SetLastError(LastError);
      goto LABEL_54;
    }
  }
  if ( !a2 )
  {
    LastError = 1796;
    goto LABEL_54;
  }
  StringCchCopyW(Str, 0x10Du, a2);
  v18 = wcschr(Str, 0x2Cu);
  if ( v18 )
    *v18 = 0;
  v16 = 1;
  EnterSplSem(0);
  IniKey = FindIniKey(*(_QWORD *)(SpoolerByNameIncRef + 64), Str, SpoolerByNameIncRef + 33160);
  v20 = IniKey;
  if ( IniKey )
  {
    if ( v5 != 3 )
    {
      LastError = 124;
      goto LABEL_53;
    }
    if ( a4 )
    {
      v21 = *(_DWORD *)(a4 + 16);
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            if ( v23 != 1 )
              goto LABEL_52;
            v24 = 0x80000;
          }
          else
          {
            v24 = 0x40000;
          }
        }
        else
        {
          v24 = 0x20000;
        }
      }
      else
      {
        if ( *(_DWORD *)a4 || *(_QWORD *)(a4 + 8) )
          goto LABEL_52;
        v24 = 0;
      }
      v25 = *(_QWORD *)(IniKey + 56);
      *(_DWORD *)(IniKey + 52) = 0;
      v26 = 0;
      v27 = *(_DWORD *)(IniKey + 48);
      *(_DWORD *)(IniKey + 48) = v27 & 0xFFF1FFFF;
      if ( v25 )
      {
        v28 = *(_QWORD *)(IniKey + 72);
        if ( v28 )
        {
          v29 = *(_QWORD *)(v28 + 192);
          if ( v29 )
          {
            v30 = *(unsigned __int16 **)(v28 + 192);
            v31 = v25 - v29;
            do
            {
              v32 = *(unsigned __int16 *)((char *)v30 + v31);
              v33 = *v30 - v32;
              if ( v33 )
                break;
              ++v30;
            }
            while ( v32 );
            if ( !v33 )
            {
              DllFreeSplStr(v29);
              *(_QWORD *)(*(_QWORD *)(v20 + 72) + 192LL) = 0;
              v26 = 1;
            }
          }
        }
        DllFreeSplStr(*(_QWORD *)(v20 + 56));
        *(_QWORD *)(v20 + 56) = 0;
      }
      v34 = *(_WORD **)(a4 + 8);
      if ( v34 && *v34 )
      {
        v35 = AllocSplStr(v34);
        *(_QWORD *)(v20 + 56) = v35;
        if ( !v35 )
        {
          LastError = GetLastError();
LABEL_47:
          v5 = a3;
          goto LABEL_53;
        }
        v36 = *(_QWORD *)(v20 + 72);
        if ( v36 )
        {
          DllFreeSplStr(*(_QWORD *)(v36 + 192));
          v26 = 1;
          *(_QWORD *)(*(_QWORD *)(v20 + 72) + 192LL) = AllocSplStr(*(_QWORD *)(v20 + 56));
        }
LABEL_59:
        if ( v26 )
          SetPrinterChange(
            *(_QWORD *)(*(_QWORD *)(v20 + 72) + 88LL),
            *(_QWORD *)(v20 + 72),
            (unsigned int)NVJobStatusString,
            512,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 72) + 88LL) + 280LL));
        *(_DWORD *)(v20 + 48) |= v24;
        UpdatePortStatusForAllPrinters((struct _INIPORT *)v20);
        v39 = v24 & 0x20000;
        if ( (v27 & 0x20000) == 0 )
        {
          if ( v39 )
          {
            if ( *(_DWORD *)(v20 + 80)
              && *(_DWORD *)(SpoolerByNameIncRef + 288)
              && ((unsigned int)(*(_DWORD *)a4 - 1) <= 2 || (unsigned int)(*(_DWORD *)a4 - 5) <= 2)
              && !*(_DWORD *)(v20 + 196) )
            {
              TickCount = GetTickCount();
              v47 = *(void **)(v20 + 200);
              *(_DWORD *)(v20 + 196) = TickCount;
              if ( v47 )
                ResetEvent(v47);
              else
                *(_QWORD *)(v20 + 200) = CreateEventW(0, 1, 0, 0);
            }
          }
          else
          {
            v45 = *(void **)(v20 + 200);
            if ( v45 )
            {
              CloseHandle(v45);
              *(_QWORD *)(v20 + 200) = 0;
            }
          }
          goto LABEL_87;
        }
        if ( v39 )
        {
          if ( !*(_DWORD *)(v20 + 80) )
            goto LABEL_87;
          if ( !*(_QWORD *)(v20 + 200) )
            goto LABEL_87;
          v42 = *(_DWORD *)(v20 + 196);
          if ( GetTickCount() - v42 <= 1000 * *(_DWORD *)(SpoolerByNameIncRef + 284) )
            goto LABEL_87;
          v43 = *(_QWORD *)(v20 + 72);
          if ( !v43 )
            goto LABEL_87;
          v44 = *(_QWORD *)(v43 + 88);
          if ( !v44 || *(_DWORD *)(v44 + 308) <= 1u )
            goto LABEL_87;
          if ( (*(_DWORD *)(v43 + 32) & 0x820) == 0 )
          {
            ClearJobError(v43);
            RestartJob(*(INIJOB **)(v20 + 72));
          }
          v41 = *(HANDLE *)(v20 + 200);
        }
        else
        {
          v40 = *(void **)(v20 + 200);
          *(_DWORD *)(v20 + 196) = 0;
          if ( v40 )
            SetEvent(v40);
          v41 = SchedulerSignal;
        }
        SetEvent(v41);
LABEL_87:
        LastError = 0;
        goto LABEL_47;
      }
      if ( *(_DWORD *)a4 < 0xDu )
      {
        *(_DWORD *)(v20 + 52) = *(_DWORD *)a4;
        goto LABEL_59;
      }
      v5 = a3;
    }
LABEL_52:
    LastError = 87;
    goto LABEL_53;
  }
  LastError = 1796;
LABEL_53:
  v7 = lpString1;
LABEL_54:
  FindSpoolerByNameDecRef(SpoolerByNameIncRef);
  if ( v16 )
    LeaveSplSem(v37);
  if ( LastError )
    goto LABEL_57;
  return 1;
}

```

## disassembly

```asm
0x180088380  push    rbx
0x180088382  push    rbp
0x180088383  push    rsi
0x180088384  push    rdi
0x180088385  push    r12
0x180088387  push    r13
0x180088389  push    r14
0x18008838b  push    r15
0x18008838d  sub     rsp, 278h
0x180088394  mov     rax, cs:__security_cookie
0x18008839b  xor     rax, rsp
0x18008839e  mov     [rsp+2B8h+var_58], rax
0x1800883a6  mov     rsi, r9
0x1800883a9  mov     [rsp+2B8h+var_280], r8d
0x1800883ae  mov     r14d, r8d
0x1800883b1  mov     [rsp+2B8h+var_288], rcx
0x1800883b6  mov     r13, rdx
0x1800883b9  mov     rdi, rcx
0x1800883bc  call    FindSpoolerByNameIncRef
0x1800883c1  mov     rbp, rax
0x1800883c4  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1800883c9  xor     r15d, r15d
0x1800883cc  test    eax, eax
0x1800883ce  jz      short loc_180088413
0x1800883d0  call    ?IsLocalSystem@SecurityHelper@@YAHPEAX@Z; SecurityHelper::IsLocalSystem(void *)
0x1800883d5  test    eax, eax
0x1800883d7  jnz     short loc_180088413
0x1800883d9  call    ?IsRestrictedSpoolerWorker@SecurityHelper@@YAHPEAX@Z; SecurityHelper::IsRestrictedSpoolerWorker(void *)
0x1800883de  test    eax, eax
0x1800883e0  jnz     short loc_180088413
0x1800883e2  call    ?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z; SecurityHelper::IsInAdministratorGroup(void *)
0x1800883e7  test    eax, eax
0x1800883e9  jnz     short loc_180088413
0x1800883eb  lea     rdx, aLocalsetportFa; "LocalSetPort failed: only LocalSystem o"...
0x1800883f2  lea     rcx, aLocalsetport; "LocalSetPort"
0x1800883f9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800883fe  lea     ebx, [r15+32h]
0x180088402  test    rbp, rbp
0x180088405  jz      loc_18008866E
0x18008840b  mov     r12d, r15d
0x18008840e  jmp     loc_180088654
0x180088413  test    rbp, rbp
0x180088416  jnz     short loc_180088420
0x180088418  lea     ebx, [rbp+7Bh]
0x18008841b  jmp     loc_18008866E
0x180088420  mov     rdx, rbp
0x180088423  mov     rcx, rdi; lpString1
0x180088426  mov     r12d, r15d
0x180088429  call    MyName
0x18008842e  test    eax, eax
0x180088430  jnz     short loc_18008843F
0x180088432  call    cs:__imp_GetLastError
0x180088438  mov     ebx, eax
0x18008843a  jmp     loc_180088654
0x18008843f  call    IsCallViaRPC
0x180088444  neg     eax
0x180088446  mov     dword ptr [rsp+2B8h+var_290], 1
0x18008844e  mov     [rsp+2B8h+var_298], rbp
0x180088453  sbb     edx, edx
0x180088455  xor     r9d, r9d
0x180088458  add     edx, 2
0x18008845b  xor     r8d, r8d
0x18008845e  xor     ecx, ecx
0x180088460  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180088465  test    eax, eax
0x180088467  jnz     short loc_180088494
0x180088469  call    cs:__imp_GetLastError
0x18008846f  mov     ebx, eax
0x180088471  cmp     eax, 5
0x180088474  jnz     short loc_180088487
0x180088476  mov     ecx, cs:gdwTlsSetPortIndex; dwTlsIndex
0x18008847c  call    cs:__imp_TlsGetValue
0x180088482  test    rax, rax
0x180088485  jz      short loc_180088494
0x180088487  mov     ecx, ebx; dwErrCode
0x180088489  call    cs:__imp_SetLastError
0x18008848f  jmp     loc_180088654
0x180088494  test    r13, r13
0x180088497  jnz     short loc_1800884A3
0x180088499  mov     ebx, 704h
0x18008849e  jmp     loc_180088654
0x1800884a3  mov     r8, r13; unsigned __int16 *
0x1800884a6  lea     rcx, [rsp+2B8h+Str]; unsigned __int16 *
0x1800884ab  mov     edx, 10Dh; unsigned __int64
0x1800884b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800884b5  mov     edx, 2Ch ; ','; Ch
0x1800884ba  lea     rcx, [rsp+2B8h+Str]; Str
0x1800884bf  call    cs:__imp_wcschr
0x1800884c5  test    rax, rax
0x1800884c8  jz      short loc_1800884CE
0x1800884ca  mov     [rax], r15w
0x1800884ce  xor     ecx, ecx
0x1800884d0  lea     r12d, [rcx+1]
0x1800884d4  call    EnterSplSem
0x1800884d9  mov     rcx, [rbp+40h]
0x1800884dd  lea     r8, [rbp+8188h]
0x1800884e4  lea     rdx, [rsp+2B8h+Str]
0x1800884e9  call    FindIniKey
0x1800884ee  mov     rdi, rax
0x1800884f1  test    rax, rax
0x1800884f4  jnz     short loc_180088500
0x1800884f6  mov     ebx, 704h
0x1800884fb  jmp     loc_18008864F
0x180088500  cmp     r14d, 3
0x180088504  jz      short loc_180088510
0x180088506  mov     ebx, 7Ch ; '|'
0x18008850b  jmp     loc_18008864F
0x180088510  test    rsi, rsi
0x180088513  jz      loc_18008864A
0x180088519  mov     ecx, [rsi+10h]
0x18008851c  test    ecx, ecx
0x18008851e  jz      short loc_180088548
0x180088520  sub     ecx, r12d
0x180088523  jz      short loc_180088541
0x180088525  sub     ecx, r12d
0x180088528  jz      short loc_18008853A
0x18008852a  cmp     ecx, r12d
0x18008852d  jnz     loc_18008864A
0x180088533  mov     ebx, 80000h
0x180088538  jmp     short loc_18008855E
0x18008853a  mov     ebx, 40000h
0x18008853f  jmp     short loc_18008855E
0x180088541  mov     ebx, 20000h
0x180088546  jmp     short loc_18008855E
0x180088548  cmp     [rsi], r15d
0x18008854b  jnz     loc_18008864A
0x180088551  cmp     [rsi+8], r15
0x180088555  jnz     loc_18008864A
0x18008855b  mov     ebx, r15d
0x18008855e  mov     rdx, [rdi+38h]
0x180088562  xor     r10d, r10d
0x180088565  mov     [rax+34h], r10d
0x180088569  mov     r14d, r15d
0x18008856c  mov     r15d, [rax+30h]
0x180088570  mov     eax, r15d
0x180088573  and     eax, 0FFF1FFFFh
0x180088578  mov     [rdi+30h], eax
0x18008857b  test    rdx, rdx
0x18008857e  jz      short loc_1800885DD
0x180088580  mov     rax, [rdi+48h]
0x180088584  test    rax, rax
0x180088587  jz      short loc_1800885CC
0x180088589  mov     r9, [rax+0C0h]
0x180088590  test    r9, r9
0x180088593  jz      short loc_1800885CC
0x180088595  mov     rax, r9
0x180088598  sub     rdx, r9
0x18008859b  movzx   r8d, word ptr [rax]
0x18008859f  movzx   ecx, word ptr [rax+rdx]
0x1800885a3  sub     r8d, ecx
0x1800885a6  jnz     short loc_1800885B0
0x1800885a8  add     rax, 2
0x1800885ac  test    ecx, ecx
0x1800885ae  jnz     short loc_18008859B
0x1800885b0  test    r8d, r8d
0x1800885b3  jnz     short loc_1800885CC
0x1800885b5  mov     rcx, r9
0x1800885b8  call    cs:__imp_DllFreeSplStr
0x1800885be  mov     rax, [rdi+48h]
0x1800885c2  mov     [rax+0C0h], r14
0x1800885c9  mov     r14d, r12d
0x1800885cc  mov     rcx, [rdi+38h]
0x1800885d0  call    cs:__imp_DllFreeSplStr
0x1800885d6  xor     r10d, r10d
0x1800885d9  mov     [rdi+38h], r10
0x1800885dd  mov     rcx, [rsi+8]
0x1800885e1  test    rcx, rcx
0x1800885e4  jz      short loc_18008863E
0x1800885e6  cmp     [rcx], r10w
0x1800885ea  jz      short loc_18008863E
0x1800885ec  call    cs:__imp_AllocSplStr
0x1800885f2  mov     [rdi+38h], rax
0x1800885f6  test    rax, rax
0x1800885f9  jnz     short loc_18008860A
0x1800885fb  call    cs:__imp_GetLastError
0x180088601  mov     ebx, eax
0x180088603  mov     r14d, [rsp+2B8h+var_280]
0x180088608  jmp     short loc_18008864F
0x18008860a  mov     rcx, [rdi+48h]
0x18008860e  test    rcx, rcx
0x180088611  jz      loc_1800886A2
0x180088617  mov     rcx, [rcx+0C0h]
0x18008861e  call    cs:__imp_DllFreeSplStr
0x180088624  mov     rcx, [rdi+38h]
0x180088628  call    cs:__imp_AllocSplStr
0x18008862e  mov     rcx, [rdi+48h]
0x180088632  mov     r14d, r12d
0x180088635  mov     [rcx+0C0h], rax
0x18008863c  jmp     short loc_1800886A2
0x18008863e  mov     eax, [rsi]
0x180088640  cmp     eax, 0Dh
0x180088643  jb      short loc_18008869F
0x180088645  mov     r14d, [rsp+2B8h+var_280]
0x18008864a  mov     ebx, 57h ; 'W'
0x18008864f  mov     rdi, [rsp+2B8h+var_288]
0x180088654  mov     rcx, rbp
0x180088657  call    FindSpoolerByNameDecRef
0x18008865c  test    r12d, r12d
0x18008865f  jz      short loc_180088666
0x180088661  call    LeaveSplSem
0x180088666  test    ebx, ebx
0x180088668  jz      loc_180088825
0x18008866e  mov     dword ptr [rsp+2B8h+var_290], ebx
0x180088672  lea     rdx, aFailedForWsPor; "Failed for '%ws', port '%ws', level %d."...
0x180088679  mov     r9, r13
0x18008867c  mov     dword ptr [rsp+2B8h+var_298], r14d
0x180088681  mov     r8, rdi
0x180088684  lea     rcx, aLocalsetport; "LocalSetPort"
0x18008868b  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180088690  mov     ecx, ebx; dwErrCode
0x180088692  call    cs:__imp_SetLastError
0x180088698  xor     eax, eax
0x18008869a  jmp     loc_18008882A
0x18008869f  mov     [rdi+34h], eax
0x1800886a2  test    r14d, r14d
0x1800886a5  jz      short loc_1800886CD
0x1800886a7  mov     rdx, [rdi+48h]
0x1800886ab  lea     r8, NVJobStatusString
0x1800886b2  mov     r9d, 200h
0x1800886b8  mov     rcx, [rdx+58h]
0x1800886bc  mov     rax, [rcx+118h]
0x1800886c3  mov     [rsp+2B8h+var_298], rax
0x1800886c8  call    SetPrinterChange
0x1800886cd  or      [rdi+30h], ebx
0x1800886d0  mov     rcx, rdi; struct _INIPORT *
0x1800886d3  call    ?UpdatePortStatusForAllPrinters@@YAXPEAU_INIPORT@@@Z; UpdatePortStatusForAllPrinters(_INIPORT *)
0x1800886d8  mov     eax, 20000h
0x1800886dd  and     ebx, eax
0x1800886df  test    eax, r15d
0x1800886e2  jz      loc_18008879B
0x1800886e8  xor     r15d, r15d
0x1800886eb  test    ebx, ebx
0x1800886ed  jnz     short loc_18008871A
0x1800886ef  mov     rcx, [rdi+0C8h]; hEvent
0x1800886f6  mov     [rdi+0C4h], r15d
0x1800886fd  test    rcx, rcx
0x180088700  jz      short loc_180088708
0x180088702  call    cs:__imp_SetEvent
0x180088708  mov     rcx, cs:SchedulerSignal; hEvent
0x18008870f  call    cs:__imp_SetEvent
0x180088715  jmp     loc_18008881D
0x18008871a  cmp     [rdi+50h], r15d
0x18008871e  jz      loc_18008881D
0x180088724  cmp     [rdi+0C8h], r15
0x18008872b  jz      loc_18008881D
0x180088731  mov     ebx, [rdi+0C4h]
0x180088737  call    cs:__imp_GetTickCount
0x18008873d  imul    ecx, [rbp+11Ch], 3E8h
0x180088747  sub     eax, ebx
0x180088749  cmp     eax, ecx
0x18008874b  jbe     loc_18008881D
0x180088751  mov     rcx, [rdi+48h]
0x180088755  test    rcx, rcx
0x180088758  jz      loc_18008881D
0x18008875e  mov     rax, [rcx+58h]
0x180088762  test    rax, rax
0x180088765  jz      loc_18008881D
0x18008876b  cmp     [rax+134h], r12d
0x180088772  jbe     loc_18008881D
0x180088778  test    dword ptr [rcx+20h], 820h
0x18008877f  jnz     short loc_18008878F
0x180088781  call    ClearJobError
0x180088786  mov     rcx, [rdi+48h]; this
0x18008878a  call    RestartJob
0x18008878f  mov     rcx, [rdi+0C8h]
0x180088796  jmp     loc_18008870F
0x18008879b  xor     r15d, r15d
0x18008879e  test    ebx, ebx
0x1800887a0  jnz     short loc_1800887BD
0x1800887a2  mov     rcx, [rdi+0C8h]; hObject
0x1800887a9  test    rcx, rcx
0x1800887ac  jz      short loc_18008881D
0x1800887ae  call    cs:__imp_CloseHandle
0x1800887b4  mov     [rdi+0C8h], r15
0x1800887bb  jmp     short loc_18008881D
0x1800887bd  cmp     [rdi+50h], r15d
0x1800887c1  jz      short loc_18008881D
0x1800887c3  cmp     [rbp+120h], r15d
0x1800887ca  jz      short loc_18008881D
0x1800887cc  mov     ecx, [rsi]
0x1800887ce  lea     eax, [rcx-1]
0x1800887d1  cmp     eax, 2
0x1800887d4  jbe     short loc_1800887DE
0x1800887d6  lea     eax, [rcx-5]
0x1800887d9  cmp     eax, 2
0x1800887dc  ja      short loc_18008881D
0x1800887de  cmp     [rdi+0C4h], r15d
0x1800887e5  jnz     short loc_18008881D
0x1800887e7  call    cs:__imp_GetTickCount
0x1800887ed  mov     rcx, [rdi+0C8h]; hEvent
0x1800887f4  mov     [rdi+0C4h], eax
0x1800887fa  test    rcx, rcx
0x1800887fd  jnz     short loc_180088817
0x1800887ff  xor     r9d, r9d; lpName
0x180088802  xor     r8d, r8d; bInitialState
0x180088805  mov     edx, r12d; bManualReset
0x180088808  call    cs:__imp_CreateEventW
0x18008880e  mov     [rdi+0C8h], rax
0x180088815  jmp     short loc_18008881D
0x180088817  call    cs:__imp_ResetEvent
  ... truncated ...
```
