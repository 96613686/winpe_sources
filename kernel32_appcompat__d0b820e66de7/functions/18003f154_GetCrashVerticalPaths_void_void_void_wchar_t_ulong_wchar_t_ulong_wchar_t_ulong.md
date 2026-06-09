# GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)

- ea: `0x18003f154`
- end: `0x18003f328`
- name: `?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z`
- size: `468`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, void *@<rdx>, void *@<r8>, wchar_t *@<r9>, unsigned int, wchar_t *, unsigned int, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005216c`

## callees

- `0x180033c1c`
- `0x18003f154`
- `0x18003fcbc`
- `0x1800529d0`
- `0x180052b0c`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18003f1c7`
- `ntdll!DbgPrintEx` at `0x18003f28e`
- `ntdll!DbgPrintEx` at `0x18003f309`
- `ntdll!DbgPrintEx` at `0x18003f1c7`
- `ntdll!DbgPrintEx` at `0x18003f28e`
- `ntdll!DbgPrintEx` at `0x18003f309`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003f2a1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003f2a1`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18003f213`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18003f213`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18003f18c`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18003f18c`

## string_xrefs

- `0x18003f2f3`: `WER/ReportFault/%u:%u: ERROR GetSystemWindowsDirectory failed or the size was inadequate.\n`

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
0x18003f154  push    rbx
0x18003f156  push    rbp
0x18003f157  push    rsi
0x18003f158  push    rdi
0x18003f159  push    r12
0x18003f15b  push    r14
0x18003f15d  sub     rsp, 38h
0x18003f161  mov     rdi, r9
0x18003f164  mov     rbp, r8
0x18003f167  mov     rsi, rcx
0x18003f16a  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x18003f16f  xor     r12d, r12d
0x18003f172  lea     rdx, [rsp+68h+arg_20]
0x18003f17a  xor     r8d, r8d
0x18003f17d  mov     [rsp+68h+arg_20], r12w
0x18003f186  mov     rcx, rsi
0x18003f189  mov     r14d, eax
0x18003f18c  call    cs:__imp_IsWow64Process2
0x18003f193  nop     dword ptr [rax+rax+00h]
0x18003f198  test    eax, eax
0x18003f19a  jnz     short loc_18003F1D3
0x18003f19c  call    WerpGetLastError
0x18003f1a1  mov     r9, gs:40h
0x18003f1aa  lea     r8, aWerReportfault_8; "WER/ReportFault/%u:%u: WARNING IsWow64P"...
0x18003f1b1  mov     [rsp+68h+var_40], eax
0x18003f1b5  lea     edx, [r12+1]; Level
0x18003f1ba  mov     ecx, 96h; ComponentId
0x18003f1bf  mov     dword ptr [rsp+68h+var_48], 0F8h
0x18003f1c7  call    cs:__imp_DbgPrintEx
0x18003f1ce  nop     dword ptr [rax+rax+00h]
0x18003f1d3  movzx   r8d, [rsp+68h+arg_20]
0x18003f1dc  mov     ecx, r8d
0x18003f1df  sub     ecx, 14Ch
0x18003f1e5  jz      short loc_18003F203
0x18003f1e7  cmp     ecx, 78h ; 'x'
0x18003f1ea  jz      short loc_18003F203
0x18003f1ec  mov     rbx, [rsp+68h+lpBuffer]
0x18003f1f4  mov     edx, 20h ; ' '; uSize
0x18003f1f9  mov     rcx, rbx; lpBuffer
0x18003f1fc  call    GetSystemDirectoryW
0x18003f201  jmp     short loc_18003F21F
0x18003f203  mov     rbx, [rsp+68h+lpBuffer]
0x18003f20b  mov     edx, 20h ; ' '
0x18003f210  mov     rcx, rbx
0x18003f213  call    cs:__imp_GetSystemWow64Directory2W
0x18003f21a  nop     dword ptr [rax+rax+00h]
0x18003f21f  dec     eax
0x18003f221  cmp     eax, 1Fh
0x18003f224  ja      loc_18003F2EA
0x18003f22a  cmp     [rbx], r12w
0x18003f22e  jz      loc_18003F2EA
0x18003f234  lea     rcx, aWerfaultExe; "WerFault.exe"
0x18003f23b  test    r14d, r14d
0x18003f23e  lea     rax, aWerfaultsecure; "WerFaultSecure.exe"
0x18003f245  mov     r9, rbx
0x18003f248  cmovz   rax, rcx
0x18003f24c  lea     r8, aSS; "%s\\%s"
0x18003f253  mov     rcx, rdi; unsigned __int16 *
0x18003f256  mov     [rsp+68h+var_48], rax
0x18003f25b  mov     edx, 40h ; '@'; unsigned __int64
0x18003f260  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f265  mov     ebx, eax
0x18003f267  test    eax, eax
0x18003f269  jns     short loc_18003F29E
0x18003f26b  mov     [rsp+68h+var_40], eax
0x18003f26f  mov     dword ptr [rsp+68h+var_48], 11Ah
0x18003f277  mov     r9, gs:40h
0x18003f280  lea     r8, aWerReportfault_14; "WER/ReportFault/%u:%u: ERROR StringCchP"...
0x18003f287  xor     edx, edx; Level
0x18003f289  mov     ecx, 96h; ComponentId
0x18003f28e  call    cs:__imp_DbgPrintEx
0x18003f295  nop     dword ptr [rax+rax+00h]
0x18003f29a  mov     eax, ebx
0x18003f29c  jmp     short loc_18003F31A
0x18003f29e  mov     rcx, rsi; Process
0x18003f2a1  call    cs:__imp_GetProcessId
0x18003f2a8  nop     dword ptr [rax+rax+00h]
0x18003f2ad  mov     rcx, [rsp+68h+arg_28]; unsigned __int16 *
0x18003f2b5  lea     r8, aSUPDSI64d; "%s -u -p %d -s %I64d"
0x18003f2bc  mov     r9, rdi
0x18003f2bf  mov     qword ptr [rsp+68h+var_40], rbp
0x18003f2c4  mov     edx, 80h; unsigned __int64
0x18003f2c9  mov     dword ptr [rsp+68h+var_48], eax
0x18003f2cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f2d2  mov     ebx, eax
0x18003f2d4  test    eax, eax
0x18003f2d6  jns     short loc_18003F2E6
0x18003f2d8  mov     [rsp+68h+var_40], eax
0x18003f2dc  mov     dword ptr [rsp+68h+var_48], 150h
0x18003f2e4  jmp     short loc_18003F277
0x18003f2e6  xor     eax, eax
0x18003f2e8  jmp     short loc_18003F31A
0x18003f2ea  mov     r9, gs:40h
0x18003f2f3  lea     r8, aWerReportfault_22; "WER/ReportFault/%u:%u: ERROR GetSystemW"...
0x18003f2fa  xor     edx, edx; Level
0x18003f2fc  mov     dword ptr [rsp+68h+var_48], 108h
0x18003f304  mov     ecx, 96h; ComponentId
0x18003f309  call    cs:__imp_DbgPrintEx
0x18003f310  nop     dword ptr [rax+rax+00h]
0x18003f315  mov     eax, 800700A1h
0x18003f31a  add     rsp, 38h
0x18003f31e  pop     r14
0x18003f320  pop     r12
0x18003f322  pop     rdi
0x18003f323  pop     rsi
0x18003f324  pop     rbp
0x18003f325  pop     rbx
0x18003f326  retn
```
