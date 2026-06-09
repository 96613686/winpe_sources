# GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)

- ea: `0x18003b7e0`
- end: `0x18003b98f`
- name: `?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z`
- size: `431`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, void *@<rdx>, void *@<r8>, wchar_t *@<r9>, unsigned int, wchar_t *, unsigned int, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004e470`

## callees

- `0x180031b8c`
- `0x18003b7e0`
- `0x18003c2f4`
- `0x18004ec94`
- `0x18004ed20`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18003b84d`
- `ntdll!DbgPrintEx` at `0x18003b908`
- `ntdll!DbgPrintEx` at `0x18003b977`
- `ntdll!DbgPrintEx` at `0x18003b84d`
- `ntdll!DbgPrintEx` at `0x18003b908`
- `ntdll!DbgPrintEx` at `0x18003b977`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003b915`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003b915`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18003b893`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18003b893`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18003b818`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18003b818`

## string_xrefs

- `0x18003b961`: `WER/ReportFault/%u:%u: ERROR GetSystemWindowsDirectory failed or the size was inadequate.\n`

## pseudocode

```c
__int64 __fastcall GetCrashVerticalPaths(
        HANDLE Process,
        void *a2,
        void *a3,
        wchar_t *a4,
        __int16 a5,
        wchar_t *a6,
        unsigned int a7,
        wchar_t *lpBuffer)
{
  int IsProtectedProcess; // eax
  int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int LastError; // eax
  wchar_t *v18; // rbx
  UINT SystemWow64Directory2W; // eax
  const wchar_t *v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  int v24; // eax
  __int64 v25; // [rsp+20h] [rbp-48h]
  int v26; // [rsp+20h] [rbp-48h]
  int v27; // [rsp+28h] [rbp-40h]

  IsProtectedProcess = WerpIsProtectedProcess(Process);
  a5 = 0;
  v12 = IsProtectedProcess;
  if ( !(unsigned int)IsWow64Process2(Process, &a5, 0) )
  {
    LastError = WerpGetLastError(v14, v13, v15, v16);
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING IsWow64Process2 failed: %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      248,
      LastError);
  }
  if ( a5 == 332 || a5 == 452 )
  {
    v18 = lpBuffer;
    SystemWow64Directory2W = GetSystemWow64Directory2W(lpBuffer, 32);
  }
  else
  {
    v18 = lpBuffer;
    SystemWow64Directory2W = GetSystemDirectoryW(lpBuffer, 0x20u);
  }
  if ( SystemWow64Directory2W - 1 <= 0x1F && *v18 )
  {
    v20 = L"WerFaultSecure.exe";
    if ( !v12 )
      v20 = L"WerFault.exe";
    v21 = StringCchPrintfW(a4, 0x40u, L"%s\\%s", v18, v20);
    v22 = v21;
    if ( v21 < 0 )
    {
      v27 = v21;
      v26 = 282;
LABEL_13:
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR StringCchPrintf failed: HRESULT %08X.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        v26,
        v27);
      return v22;
    }
    LODWORD(v25) = GetProcessId(Process);
    v24 = StringCchPrintfW(a6, 0x80u, L"%s -u -p %d -s %I64d", a4, v25, a3);
    v22 = v24;
    if ( v24 < 0 )
    {
      v27 = v24;
      v26 = 336;
      goto LABEL_13;
    }
    return 0;
  }
  else
  {
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR GetSystemWindowsDirectory failed or the size was inadequate.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      264);
    return 2147942561LL;
  }
}

```

## disassembly

```asm
0x18003b7e0  push    rbx
0x18003b7e2  push    rbp
0x18003b7e3  push    rsi
0x18003b7e4  push    rdi
0x18003b7e5  push    r12
0x18003b7e7  push    r14
0x18003b7e9  sub     rsp, 38h
0x18003b7ed  mov     rdi, r9
0x18003b7f0  mov     rbp, r8
0x18003b7f3  mov     rsi, rcx
0x18003b7f6  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x18003b7fb  xor     r12d, r12d
0x18003b7fe  lea     rdx, [rsp+68h+arg_20]
0x18003b806  xor     r8d, r8d
0x18003b809  mov     [rsp+68h+arg_20], r12w
0x18003b812  mov     rcx, rsi
0x18003b815  mov     r14d, eax
0x18003b818  call    cs:__imp_IsWow64Process2
0x18003b81e  test    eax, eax
0x18003b820  jnz     short loc_18003B853
0x18003b822  call    WerpGetLastError
0x18003b827  mov     r9, gs:40h
0x18003b830  lea     r8, aWerReportfault_8; "WER/ReportFault/%u:%u: WARNING IsWow64P"...
0x18003b837  mov     [rsp+68h+var_40], eax
0x18003b83b  lea     edx, [r12+1]; Level
0x18003b840  mov     ecx, 96h; ComponentId
0x18003b845  mov     dword ptr [rsp+68h+var_48], 0F8h
0x18003b84d  call    cs:__imp_DbgPrintEx
0x18003b853  movzx   r8d, [rsp+68h+arg_20]
0x18003b85c  mov     ecx, r8d
0x18003b85f  sub     ecx, 14Ch
0x18003b865  jz      short loc_18003B883
0x18003b867  cmp     ecx, 78h ; 'x'
0x18003b86a  jz      short loc_18003B883
0x18003b86c  mov     rbx, [rsp+68h+lpBuffer]
0x18003b874  mov     edx, 20h ; ' '; uSize
0x18003b879  mov     rcx, rbx; lpBuffer
0x18003b87c  call    GetSystemDirectoryW
0x18003b881  jmp     short loc_18003B899
0x18003b883  mov     rbx, [rsp+68h+lpBuffer]
0x18003b88b  mov     edx, 20h ; ' '
0x18003b890  mov     rcx, rbx
0x18003b893  call    cs:__imp_GetSystemWow64Directory2W
0x18003b899  dec     eax
0x18003b89b  cmp     eax, 1Fh
0x18003b89e  ja      loc_18003B958
0x18003b8a4  cmp     [rbx], r12w
0x18003b8a8  jz      loc_18003B958
0x18003b8ae  lea     rcx, aWerfaultExe; "WerFault.exe"
0x18003b8b5  test    r14d, r14d
0x18003b8b8  lea     rax, aWerfaultsecure; "WerFaultSecure.exe"
0x18003b8bf  mov     r9, rbx
0x18003b8c2  cmovz   rax, rcx
0x18003b8c6  lea     r8, aSS; "%s\\%s"
0x18003b8cd  mov     rcx, rdi; unsigned __int16 *
0x18003b8d0  mov     [rsp+68h+var_48], rax
0x18003b8d5  mov     edx, 40h ; '@'; unsigned __int64
0x18003b8da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b8df  mov     ebx, eax
0x18003b8e1  test    eax, eax
0x18003b8e3  jns     short loc_18003B912
0x18003b8e5  mov     [rsp+68h+var_40], eax
0x18003b8e9  mov     dword ptr [rsp+68h+var_48], 11Ah
0x18003b8f1  mov     r9, gs:40h
0x18003b8fa  lea     r8, aWerReportfault_14; "WER/ReportFault/%u:%u: ERROR StringCchP"...
0x18003b901  xor     edx, edx; Level
0x18003b903  mov     ecx, 96h; ComponentId
0x18003b908  call    cs:__imp_DbgPrintEx
0x18003b90e  mov     eax, ebx
0x18003b910  jmp     short loc_18003B982
0x18003b912  mov     rcx, rsi; Process
0x18003b915  call    cs:__imp_GetProcessId
0x18003b91b  mov     rcx, [rsp+68h+arg_28]; unsigned __int16 *
0x18003b923  lea     r8, aSUPDSI64d; "%s -u -p %d -s %I64d"
0x18003b92a  mov     r9, rdi
0x18003b92d  mov     qword ptr [rsp+68h+var_40], rbp
0x18003b932  mov     edx, 80h; unsigned __int64
0x18003b937  mov     dword ptr [rsp+68h+var_48], eax
0x18003b93b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b940  mov     ebx, eax
0x18003b942  test    eax, eax
0x18003b944  jns     short loc_18003B954
0x18003b946  mov     [rsp+68h+var_40], eax
0x18003b94a  mov     dword ptr [rsp+68h+var_48], 150h
0x18003b952  jmp     short loc_18003B8F1
0x18003b954  xor     eax, eax
0x18003b956  jmp     short loc_18003B982
0x18003b958  mov     r9, gs:40h
0x18003b961  lea     r8, aWerReportfault_22; "WER/ReportFault/%u:%u: ERROR GetSystemW"...
0x18003b968  xor     edx, edx; Level
0x18003b96a  mov     dword ptr [rsp+68h+var_48], 108h
0x18003b972  mov     ecx, 96h; ComponentId
0x18003b977  call    cs:__imp_DbgPrintEx
0x18003b97d  mov     eax, 800700A1h
0x18003b982  add     rsp, 38h
0x18003b986  pop     r14
0x18003b988  pop     r12
0x18003b98a  pop     rdi
0x18003b98b  pop     rsi
0x18003b98c  pop     rbp
0x18003b98d  pop     rbx
0x18003b98e  retn
```
