# GetCrashVerticalPaths(void *,void *,void *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong)

- ea: `0x1800419b8`
- end: `0x180041bd5`
- name: `?GetCrashVerticalPaths@@YAJPEAX00PEA_WK1K1K@Z`
- size: `541`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, HANDLE@<rdx>, void *@<r8>, wchar_t *@<r9>, unsigned int, wchar_t *, unsigned int, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d8b4`
- `0x180041bdc`

## callees

- `0x180003617`
- `0x180004ee1`
- `0x180004eed`
- `0x180006684`
- `0x18001bfb0`
- `0x1800419b8`
- `0x1800424dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180041af8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180041b08`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180041af8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180041b08`
- `ntdll!DbgPrintEx` at `0x180041a30`
- `ntdll!DbgPrintEx` at `0x180041ae8`
- `ntdll!DbgPrintEx` at `0x180041bb9`
- `ntdll!DbgPrintEx` at `0x180041a30`
- `ntdll!DbgPrintEx` at `0x180041ae8`
- `ntdll!DbgPrintEx` at `0x180041bb9`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180041a76`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180041a76`

## string_xrefs

- `0x180041bad`: `WER/ReportFault/%u:%u: ERROR GetSystemWindowsDirectory failed or the size was inadequate.\n`

## pseudocode

```c
__int64 __fastcall GetCrashVerticalPaths(
        HANDLE Process,
        HANDLE a2,
        void *a3,
        wchar_t *a4,
        __int16 a5,
        wchar_t *a6,
        unsigned int a7,
        wchar_t *lpBuffer)
{
  int IsProtectedProcess; // eax
  int v13; // r15d
  int LastError; // ebx
  DWORD CurrentProcessId_0; // eax
  wchar_t *v16; // rbx
  UINT SystemWow64Directory2W; // eax
  const wchar_t *v18; // rax
  int v19; // ebx
  DWORD v20; // eax
  DWORD ProcessId; // ebx
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD v26; // eax
  __int64 v27; // [rsp+20h] [rbp-68h]
  __int64 v28; // [rsp+28h] [rbp-60h]

  IsProtectedProcess = WerpIsProtectedProcess(Process);
  a5 = 0;
  v13 = IsProtectedProcess;
  if ( !(unsigned int)IsWow64Process2_0(Process, &a5, 0) )
  {
    LastError = WerpGetLastError();
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING IsWow64Process2 failed: %u.\n",
      CurrentProcessId_0,
      248,
      LastError);
  }
  if ( a5 == 332 || a5 == 452 )
  {
    v16 = lpBuffer;
    SystemWow64Directory2W = GetSystemWow64Directory2W(lpBuffer, 32);
  }
  else
  {
    v16 = lpBuffer;
    SystemWow64Directory2W = GetSystemDirectoryW_0(lpBuffer, 0x20u);
  }
  if ( SystemWow64Directory2W - 1 <= 0x1F && *v16 )
  {
    v18 = L"WerFaultSecure.exe";
    if ( !v13 )
      v18 = L"WerFault.exe";
    v19 = StringCchPrintfW(a4, 0x40u, L"%s\\%s", v16, v18);
    if ( v19 < 0 )
    {
      v20 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/ReportFault/%u:%u: ERROR StringCchPrintf failed: HRESULT %08X.\n", v20, 282, v19);
      return (unsigned int)v19;
    }
    ProcessId = GetProcessId(Process);
    if ( a2 && (v23 = GetProcessId(a2), v23 != ProcessId) && v23 )
    {
      LODWORD(v28) = v23;
      LODWORD(v27) = ProcessId;
      v19 = StringCchPrintfW(a6, 0x80u, L"%s -u -p %d -ip %d -s %I64d", a4, v27, v28, a3);
      if ( v19 < 0 )
      {
        v24 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/ReportFault/%u:%u: ERROR StringCchPrintf failed: HRESULT %08X.\n", v24, 321, v19);
        return (unsigned int)v19;
      }
    }
    else
    {
      LODWORD(v27) = ProcessId;
      v19 = StringCchPrintfW(a6, 0x80u, L"%s -u -p %d -s %I64d", a4, v27, a3);
      if ( v19 < 0 )
      {
        v25 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/ReportFault/%u:%u: ERROR StringCchPrintf failed: HRESULT %08X.\n", v25, 336, v19);
        return (unsigned int)v19;
      }
    }
    return 0;
  }
  else
  {
    v26 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR GetSystemWindowsDirectory failed or the size was inadequate.\n",
      v26,
      264);
    return 2147942561LL;
  }
}

```

## disassembly

```asm
0x1800419b8  push    rbx
0x1800419ba  push    rbp
0x1800419bb  push    rsi
0x1800419bc  push    rdi
0x1800419bd  push    r12
0x1800419bf  push    r13
0x1800419c1  push    r14
0x1800419c3  push    r15
0x1800419c5  sub     rsp, 48h
0x1800419c9  mov     rsi, r9
0x1800419cc  mov     r14, r8
0x1800419cf  mov     rdi, rdx
0x1800419d2  mov     rbp, rcx
0x1800419d5  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x1800419da  xor     r12d, r12d
0x1800419dd  lea     rdx, [rsp+88h+arg_20]
0x1800419e5  xor     r8d, r8d
0x1800419e8  mov     [rsp+88h+arg_20], r12w
0x1800419f1  mov     rcx, rbp
0x1800419f4  mov     r15d, eax
0x1800419f7  call    IsWow64Process2_0
0x1800419fc  mov     r13d, 96h
0x180041a02  test    eax, eax
0x180041a04  jnz     short loc_180041A36
0x180041a06  call    WerpGetLastError
0x180041a0b  mov     ebx, eax
0x180041a0d  call    GetCurrentProcessId_0
0x180041a12  mov     r9d, eax
0x180041a15  mov     dword ptr [rsp+88h+var_60], ebx
0x180041a19  lea     r8, aWerReportfault_8; "WER/ReportFault/%u:%u: WARNING IsWow64P"...
0x180041a20  mov     dword ptr [rsp+88h+var_68], 0F8h
0x180041a28  lea     edx, [r12+1]; Level
0x180041a2d  mov     ecx, r13d; ComponentId
0x180041a30  call    cs:__imp_DbgPrintEx
0x180041a36  movzx   r8d, [rsp+88h+arg_20]
0x180041a3f  mov     ecx, r8d
0x180041a42  sub     ecx, 14Ch
0x180041a48  jz      short loc_180041A66
0x180041a4a  cmp     ecx, 78h ; 'x'
0x180041a4d  jz      short loc_180041A66
0x180041a4f  mov     rbx, [rsp+88h+lpBuffer]
0x180041a57  mov     edx, 20h ; ' '; uSize
0x180041a5c  mov     rcx, rbx; lpBuffer
0x180041a5f  call    GetSystemDirectoryW_0
0x180041a64  jmp     short loc_180041A7C
0x180041a66  mov     rbx, [rsp+88h+lpBuffer]
0x180041a6e  mov     edx, 20h ; ' '
0x180041a73  mov     rcx, rbx
0x180041a76  call    cs:__imp_GetSystemWow64Directory2W
0x180041a7c  dec     eax
0x180041a7e  cmp     eax, 1Fh
0x180041a81  ja      loc_180041B9D
0x180041a87  cmp     [rbx], r12w
0x180041a8b  jz      loc_180041B9D
0x180041a91  lea     rcx, aWerfaultExe; "WerFault.exe"
0x180041a98  test    r15d, r15d
0x180041a9b  lea     rax, aWerfaultsecure; "WerFaultSecure.exe"
0x180041aa2  mov     r9, rbx
0x180041aa5  cmovz   rax, rcx
0x180041aa9  lea     r8, aSS_0; "%s\\%s"
0x180041ab0  mov     rcx, rsi; wchar_t *
0x180041ab3  mov     [rsp+88h+var_68], rax
0x180041ab8  mov     edx, 40h ; '@'; unsigned __int64
0x180041abd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180041ac2  mov     ebx, eax
0x180041ac4  test    eax, eax
0x180041ac6  jns     short loc_180041AF5
0x180041ac8  call    GetCurrentProcessId_0
0x180041acd  mov     dword ptr [rsp+88h+var_60], ebx
0x180041ad1  mov     dword ptr [rsp+88h+var_68], 11Ah
0x180041ad9  mov     r9d, eax
0x180041adc  lea     r8, aWerReportfault_14; "WER/ReportFault/%u:%u: ERROR StringCchP"...
0x180041ae3  xor     edx, edx; Level
0x180041ae5  mov     ecx, r13d; ComponentId
0x180041ae8  call    cs:__imp_DbgPrintEx
0x180041aee  mov     eax, ebx
0x180041af0  jmp     loc_180041BC4
0x180041af5  mov     rcx, rbp; Process
0x180041af8  call    cs:__imp_GetProcessId
0x180041afe  mov     ebx, eax
0x180041b00  test    rdi, rdi
0x180041b03  jz      short loc_180041B58
0x180041b05  mov     rcx, rdi; Process
0x180041b08  call    cs:__imp_GetProcessId
0x180041b0e  cmp     eax, ebx
0x180041b10  jz      short loc_180041B58
0x180041b12  test    eax, eax
0x180041b14  jz      short loc_180041B58
0x180041b16  mov     rcx, [rsp+88h+arg_28]; wchar_t *
0x180041b1e  lea     r8, aSUPDIpDSI64d; "%s -u -p %d -ip %d -s %I64d"
0x180041b25  mov     [rsp+88h+var_58], r14
0x180041b2a  mov     r9, rsi
0x180041b2d  mov     dword ptr [rsp+88h+var_60], eax
0x180041b31  mov     edx, 80h; unsigned __int64
0x180041b36  mov     dword ptr [rsp+88h+var_68], ebx
0x180041b3a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180041b3f  mov     ebx, eax
0x180041b41  test    eax, eax
0x180041b43  jns     short loc_180041B99
0x180041b45  call    GetCurrentProcessId_0
0x180041b4a  mov     dword ptr [rsp+88h+var_60], ebx
0x180041b4e  mov     dword ptr [rsp+88h+var_68], 141h
0x180041b56  jmp     short loc_180041AD9
0x180041b58  mov     rcx, [rsp+88h+arg_28]; wchar_t *
0x180041b60  lea     r8, aSUPDSI64d; "%s -u -p %d -s %I64d"
0x180041b67  mov     [rsp+88h+var_60], r14
0x180041b6c  mov     r9, rsi
0x180041b6f  mov     edx, 80h; unsigned __int64
0x180041b74  mov     dword ptr [rsp+88h+var_68], ebx
0x180041b78  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180041b7d  mov     ebx, eax
0x180041b7f  test    eax, eax
0x180041b81  jns     short loc_180041B99
0x180041b83  call    GetCurrentProcessId_0
0x180041b88  mov     dword ptr [rsp+88h+var_60], ebx
0x180041b8c  mov     dword ptr [rsp+88h+var_68], 150h
0x180041b94  jmp     loc_180041AD9
0x180041b99  xor     eax, eax
0x180041b9b  jmp     short loc_180041BC4
0x180041b9d  call    GetCurrentProcessId_0
0x180041ba2  mov     r9d, eax
0x180041ba5  mov     dword ptr [rsp+88h+var_68], 108h
0x180041bad  lea     r8, aWerReportfault_22; "WER/ReportFault/%u:%u: ERROR GetSystemW"...
0x180041bb4  xor     edx, edx; Level
0x180041bb6  mov     ecx, r13d; ComponentId
0x180041bb9  call    cs:__imp_DbgPrintEx
0x180041bbf  mov     eax, 800700A1h
0x180041bc4  add     rsp, 48h
0x180041bc8  pop     r15
0x180041bca  pop     r14
0x180041bcc  pop     r13
0x180041bce  pop     r12
0x180041bd0  pop     rdi
0x180041bd1  pop     rsi
0x180041bd2  pop     rbp
0x180041bd3  pop     rbx
0x180041bd4  retn
```
