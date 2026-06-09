# LegacyParseInfAndCommitFileQueue(_SETUP_CONTEXT *)

- ea: `0x18000c408`
- end: `0x18000c613`
- name: `?LegacyParseInfAndCommitFileQueue@@YAJPEAU_SETUP_CONTEXT@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(struct _SETUP_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180011c70`

## callees

- `0x18000b200`
- `0x18000c408`
- `0x18000d57c`
- `0x18001bef8`
- `0x18002143c`
- `0x180022dec`
- `0x180034f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5c3`
- `SETUPAPI!SetupScanFileQueueW` at `0x18000c54e`
- `SETUPAPI!SetupScanFileQueueW` at `0x18000c54e`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18000c564`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18000c564`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x18000c554`

## string_xrefs

- `0x18000c5cd`: `SetupCommitFileQueue failed`
- `0x18000c464`: `Error building queue of files to copy: hr: 0x%x`
- `0x18000c46b`: `LegacyParseInfAndCommitFileQueue`
- `0x18000c590`: `LegacyParseInfAndCommitFileQueue`
- `0x18000c5ac`: `LegacyParseInfAndCommitFileQueue`
- `0x18000c491`: `PerformInfInstallActions failed`
- `0x18000c4ab`: `ParseInfAndCommitFileQueue`
- `0x18000c587`: `A file was missing while committing the file queue.`
- `0x18000c5a5`: `Error committing file queue: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall LegacyParseInfAndCommitFileQueue(struct _SETUP_CONTEXT *a1)
{
  char *v1; // rbp
  __int64 v2; // rdi
  void *v3; // r12
  const unsigned __int16 *v4; // r14
  const unsigned __int16 *v5; // r15
  const WCHAR *v6; // rsi
  int v7; // eax
  unsigned int IsInfDriverIsolationEnabledW; // ebx
  DWORD v9; // eax
  const unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rcx
  NCoreLibrary *v12; // rcx
  int LastErrorAsFailHR; // eax
  DWORD LastError; // eax
  DWORD Result; // [rsp+80h] [rbp+8h] BYREF

  v1 = (char *)*((_QWORD *)a1 + 1);
  v2 = *((_QWORD *)a1 + 4);
  v3 = (void *)*((_QWORD *)a1 + 2);
  v4 = (const unsigned __int16 *)*((_QWORD *)a1 + 6);
  v5 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
  v6 = (const WCHAR *)*((_QWORD *)a1 + 8);
  v7 = PerformInfInstallActions(
         *(HDEVINFO *)a1,
         v1,
         *((unsigned __int16 **)a1 + 3),
         v2,
         *((_DWORD *)a1 + 10),
         *((_DWORD *)a1 + 11) & 0x40000000);
  IsInfDriverIsolationEnabledW = v7;
  if ( v7 >= 0 )
  {
    v11 = *(unsigned __int16 **)v2;
    Result = 1;
    IsInfDriverIsolationEnabledW = PSetupIsInfDriverIsolationEnabledW(v11, v6);
    if ( (IsInfDriverIsolationEnabledW & 0x80000000) == 0 )
      IsInfDriverIsolationEnabledW = CheckCoreDriverDependentINFsForSandBox(v6);
    if ( (IsInfDriverIsolationEnabledW & 0x80000000) != 0 )
    {
      *(_DWORD *)(v2 + 176) = 1;
      return IsInfDriverIsolationEnabledW;
    }
    *(_DWORD *)(v2 + 176) = Result;
    Result = 0;
    SetupScanFileQueueW(v1, 0x22u, HWND_MESSAGE|0x2LL, 0, 0, &Result);
    if ( SetupCommitFileQueueW(HWND_MESSAGE|0x2LL, v1, SetupDefaultQueueCallbackW, v3) )
    {
      return 0;
    }
    else
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12);
      IsInfDriverIsolationEnabledW = LastErrorAsFailHR;
      if ( (_WORD)LastErrorAsFailHR == 1223 )
      {
        IsInfDriverIsolationEnabledW = -2147024894;
        ClassInstallerTelemetry::WriteDbgTraceError(
          "LegacyParseInfAndCommitFileQueue",
          L"A file was missing while committing the file queue.");
      }
      else if ( LastErrorAsFailHR >= 0 )
      {
        return IsInfDriverIsolationEnabledW;
      }
      ClassInstallerTelemetry::WriteDbgTraceError(
        "LegacyParseInfAndCommitFileQueue",
        L"Error committing file queue: hr: 0x%x",
        IsInfDriverIsolationEnabledW);
      if ( IsInfDriverIsolationEnabledW == -2147024894 )
        LastError = 2;
      else
        LastError = GetLastError();
      SplLogPrinterSetupEvent(
        &SETUP_PARSEINF_FAILED,
        L"ParseInfAndCommitFileQueue",
        L"SetupCommitFileQueue failed",
        0,
        v4,
        v5,
        *(const unsigned __int16 **)(v2 + 184),
        v6,
        LastError,
        IsInfDriverIsolationEnabledW);
    }
  }
  else
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "LegacyParseInfAndCommitFileQueue",
      L"Error building queue of files to copy: hr: 0x%x",
      (unsigned int)v7);
    v9 = GetLastError();
    v10 = *(const unsigned __int16 **)(v2 + 184);
    if ( !v10 )
      v10 = *(const unsigned __int16 **)(v2 + 16);
    SplLogPrinterSetupEvent(
      &SETUP_PARSEINF_FAILED,
      L"ParseInfAndCommitFileQueue",
      L"PerformInfInstallActions failed",
      0,
      v4,
      v5,
      v10,
      v6,
      v9,
      IsInfDriverIsolationEnabledW);
  }
  return IsInfDriverIsolationEnabledW;
}

```

## disassembly

```asm
0x18000c408  mov     [rsp+arg_8], rbx
0x18000c40d  mov     [rsp+arg_10], rbp
0x18000c412  push    rsi
0x18000c413  push    rdi
0x18000c414  push    r12
0x18000c416  push    r14
0x18000c418  push    r15
0x18000c41a  sub     rsp, 50h
0x18000c41e  mov     eax, [rcx+2Ch]
0x18000c421  mov     rbp, [rcx+8]
0x18000c425  and     eax, 40000000h
0x18000c42a  mov     rdi, [rcx+20h]
0x18000c42e  mov     rdx, rbp
0x18000c431  mov     r12, [rcx+10h]
0x18000c435  mov     r9, rdi
0x18000c438  mov     r14, [rcx+30h]
0x18000c43c  mov     r15, [rcx+38h]
0x18000c440  mov     rsi, [rcx+40h]
0x18000c444  mov     r8, [rcx+18h]
0x18000c448  mov     dword ptr [rsp+78h+Result], eax; int
0x18000c44c  mov     eax, [rcx+28h]
0x18000c44f  mov     rcx, [rcx]; DeviceInfoSet
0x18000c452  mov     dword ptr [rsp+78h+CallbackContext], eax; int
0x18000c456  call    PerformInfInstallActions
0x18000c45b  mov     ebx, eax
0x18000c45d  test    eax, eax
0x18000c45f  jns     short loc_18000C4CB
0x18000c461  mov     r8d, eax
0x18000c464  lea     rdx, aErrorBuildingQ; "Error building queue of files to copy: "...
0x18000c46b  lea     rcx, aLegacyparseinf; "LegacyParseInfAndCommitFileQueue"
0x18000c472  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000c477  call    cs:__imp_GetLastError
0x18000c47d  mov     rcx, [rdi+0B8h]
0x18000c484  test    rcx, rcx
0x18000c487  jnz     short loc_18000C48D
0x18000c489  mov     rcx, [rdi+10h]
0x18000c48d  mov     [rsp+78h+var_30], ebx; unsigned int
0x18000c491  lea     r8, aPerforminfinst; "PerformInfInstallActions failed"
0x18000c498  mov     [rsp+78h+var_38], eax; unsigned int
0x18000c49c  mov     [rsp+78h+var_40], rsi; unsigned __int16 *
0x18000c4a1  mov     [rsp+78h+var_48], rcx; unsigned __int16 *
0x18000c4a6  mov     [rsp+78h+Result], r15; unsigned __int16 *
0x18000c4ab  lea     rdx, aParseinfandcom; "ParseInfAndCommitFileQueue"
0x18000c4b2  xor     r9d, r9d; unsigned __int16 *
0x18000c4b5  mov     [rsp+78h+CallbackContext], r14; unsigned __int16 *
0x18000c4ba  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18000c4c1  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18000c4c6  jmp     loc_18000C5F8
0x18000c4cb  mov     rcx, [rdi]; unsigned __int16 *
0x18000c4ce  lea     r8, [rsp+78h+arg_0]
0x18000c4d6  mov     rdx, rsi; lpString1
0x18000c4d9  mov     [rsp+78h+arg_0], 1
0x18000c4e4  call    PSetupIsInfDriverIsolationEnabledW
0x18000c4e9  mov     ebx, eax
0x18000c4eb  test    eax, eax
0x18000c4ed  js      short loc_18000C508
0x18000c4ef  lea     rdx, [rdi+190h]
0x18000c4f6  mov     rcx, rsi; lpString1
0x18000c4f9  lea     r8, [rsp+78h+arg_0]
0x18000c501  call    CheckCoreDriverDependentINFsForSandBox
0x18000c506  mov     ebx, eax
0x18000c508  test    ebx, ebx
0x18000c50a  js      loc_18000C5EE
0x18000c510  mov     eax, [rsp+78h+arg_0]
0x18000c517  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c51b  mov     [rdi+0B0h], eax
0x18000c521  xor     r9d, r9d; CallbackRoutine
0x18000c524  lea     rax, [rsp+78h+arg_0]
0x18000c52c  mov     [rsp+78h+arg_0], 0
0x18000c537  mov     [rsp+78h+Result], rax; Result
0x18000c53c  mov     r8, rbx; Window
0x18000c53f  lea     edx, [rbx+23h]; Flags
0x18000c542  mov     [rsp+78h+CallbackContext], 0; CallbackContext
0x18000c54b  mov     rcx, rbp; FileQueue
0x18000c54e  call    cs:__imp_SetupScanFileQueueW
0x18000c554  mov     r8, cs:__imp_SetupDefaultQueueCallbackW; MsgHandler
0x18000c55b  mov     r9, r12; Context
0x18000c55e  mov     rdx, rbp; QueueHandle
0x18000c561  mov     rcx, rbx; Owner
0x18000c564  call    cs:__imp_SetupCommitFileQueueW
0x18000c56a  test    eax, eax
0x18000c56c  jz      short loc_18000C575
0x18000c56e  xor     ebx, ebx
0x18000c570  jmp     loc_18000C5F8
0x18000c575  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18000c57a  mov     ebx, eax
0x18000c57c  mov     ebp, 80070002h
0x18000c581  cmp     ax, 4C7h
0x18000c585  jnz     short loc_18000C59E
0x18000c587  lea     rdx, aAFileWasMissin; "A file was missing while committing the"...
0x18000c58e  mov     ebx, ebp
0x18000c590  lea     rcx, aLegacyparseinf; "LegacyParseInfAndCommitFileQueue"
0x18000c597  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000c59c  jmp     short loc_18000C5A2
0x18000c59e  test    eax, eax
0x18000c5a0  jns     short loc_18000C5F8
0x18000c5a2  mov     r8d, ebx
0x18000c5a5  lea     rdx, aErrorCommittin; "Error committing file queue: hr: 0x%x"
0x18000c5ac  lea     rcx, aLegacyparseinf; "LegacyParseInfAndCommitFileQueue"
0x18000c5b3  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000c5b8  cmp     ebx, ebp
0x18000c5ba  jnz     short loc_18000C5C3
0x18000c5bc  mov     eax, 2
0x18000c5c1  jmp     short loc_18000C5C9
0x18000c5c3  call    cs:__imp_GetLastError
0x18000c5c9  mov     [rsp+78h+var_30], ebx
0x18000c5cd  lea     r8, aSetupcommitfil; "SetupCommitFileQueue failed"
0x18000c5d4  mov     [rsp+78h+var_38], eax
0x18000c5d8  mov     rax, [rdi+0B8h]
0x18000c5df  mov     [rsp+78h+var_40], rsi
0x18000c5e4  mov     [rsp+78h+var_48], rax
0x18000c5e9  jmp     loc_18000C4A6
0x18000c5ee  mov     dword ptr [rdi+0B0h], 1
0x18000c5f8  lea     r11, [rsp+78h+var_28]
0x18000c5fd  mov     eax, ebx
0x18000c5ff  mov     rbx, [r11+38h]
0x18000c603  mov     rbp, [r11+40h]
0x18000c607  mov     rsp, r11
0x18000c60a  pop     r15
0x18000c60c  pop     r14
0x18000c60e  pop     r12
0x18000c610  pop     rdi
0x18000c611  pop     rsi
0x18000c612  retn
```
