# CRpcWatchDog::ReportException(void *,unsigned __int64)

- ea: `0x180078358`
- end: `0x180078483`
- name: `?ReportException@CRpcWatchDog@@AEAAXPEAX_K@Z`
- size: `299`
- prototype: `void __fastcall(CRpcWatchDog *this, void *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180042e54`

## callees

- `0x180046ec0`
- `0x180047818`
- `0x180078358`
- `0x18007b150`
- `0x180086f78`

## import_xrefs

- `ntdll!RtlReportExceptionEx` at `0x180078431`
- `ntdll!RtlReportExceptionEx` at `0x180078431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078410`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078410`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800783e2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800783e2`

## pseudocode

```c
void __fastcall CRpcWatchDog::ReportException(CRpcWatchDog *this, void *a2, __int64 a3)
{
  HANDLE CurrentThread; // rbx
  HANDLE CurrentProcess; // rax
  int v8; // [rsp+28h] [rbp-590h]
  _DWORD v9[4]; // [rsp+30h] [rbp-588h] BYREF
  void *v10; // [rsp+40h] [rbp-578h]
  int v11; // [rsp+48h] [rbp-570h]
  __int64 v12; // [rsp+50h] [rbp-568h]
  CONTEXT ContextRecord; // [rsp+D0h] [rbp-4E8h] BYREF

  memset_0(&ContextRecord, 0, sizeof(ContextRecord));
  memset_0(v9, 0, 0x98u);
  if ( (BYTE1(xmmword_1800AB5A0) & 0x40) != 0 )
  {
    v8 = *((_DWORD *)this + 22);
    WPP_SF_qqd(1038, 18, (unsigned int)WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, (_DWORD)a2, a3);
  }
  RtlCaptureContext(&ContextRecord);
  v9[0] = 1460;
  v9[1] = 1;
  v11 = 1;
  v10 = a2;
  v12 = a3;
  CurrentThread = GetCurrentThread();
  CurrentProcess = GetCurrentProcess();
  RtlReportExceptionEx(v9, &ContextRecord, 14, CurrentProcess, CurrentThread, v8);
  if ( (BYTE1(xmmword_1800AB5A0) & 0x40) != 0 )
    WPP_SF_qq(1038, 19, (unsigned int)WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x180078358  mov     [rsp+arg_0], rbx
0x18007835d  mov     [rsp+arg_18], rsi
0x180078362  push    rdi
0x180078363  sub     rsp, 5B0h
0x18007836a  mov     rax, cs:__security_cookie
0x180078371  xor     rax, rsp
0x180078374  mov     [rsp+5B8h+var_18], rax
0x18007837c  mov     rsi, r8
0x18007837f  mov     rdi, rdx
0x180078382  mov     rbx, rcx
0x180078385  xor     edx, edx; Val
0x180078387  mov     r8d, 4D0h; Size
0x18007838d  lea     rcx, [rsp+5B8h+ContextRecord]; void *
0x180078395  call    memset_0
0x18007839a  xor     edx, edx; Val
0x18007839c  lea     rcx, [rsp+5B8h+var_588]; void *
0x1800783a1  mov     r8d, 98h; Size
0x1800783a7  call    memset_0
0x1800783ac  test    byte ptr cs:xmmword_1800AB5A0+1, 40h
0x1800783b3  jz      short loc_1800783DA
0x1800783b5  mov     eax, [rbx+58h]
0x1800783b8  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x1800783bf  mov     [rsp+5B8h+var_590], eax
0x1800783c3  mov     edx, 12h
0x1800783c8  mov     ecx, 40Eh
0x1800783cd  mov     [rsp+5B8h+var_598], rsi
0x1800783d2  mov     r9, rdi
0x1800783d5  call    WPP_SF_qqd
0x1800783da  lea     rcx, [rsp+5B8h+ContextRecord]; ContextRecord
0x1800783e2  call    cs:__imp_RtlCaptureContext
0x1800783e8  mov     eax, 1
0x1800783ed  mov     [rsp+5B8h+var_588], 5B4h
0x1800783f5  mov     [rsp+5B8h+var_584], eax
0x1800783f9  mov     [rsp+5B8h+var_570], eax
0x1800783fd  mov     [rsp+5B8h+var_578], rdi
0x180078402  mov     [rsp+5B8h+var_568], rsi
0x180078407  call    cs:__imp_GetCurrentThread
0x18007840d  mov     rbx, rax
0x180078410  call    cs:__imp_GetCurrentProcess
0x180078416  mov     r8d, 0Eh
0x18007841c  mov     [rsp+5B8h+var_598], rbx
0x180078421  mov     r9, rax
0x180078424  lea     rdx, [rsp+5B8h+ContextRecord]
0x18007842c  lea     rcx, [rsp+5B8h+var_588]
0x180078431  call    cs:__imp_RtlReportExceptionEx
0x180078437  test    byte ptr cs:xmmword_1800AB5A0+1, 40h
0x18007843e  jz      short loc_18007845E
0x180078440  mov     edx, 13h
0x180078445  mov     [rsp+5B8h+var_598], rsi
0x18007844a  mov     ecx, 40Eh
0x18007844f  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x180078456  mov     r9, rdi
0x180078459  call    WPP_SF_qq
0x18007845e  mov     rcx, [rsp+5B8h+var_18]
0x180078466  xor     rcx, rsp; StackCookie
0x180078469  call    __security_check_cookie
0x18007846e  lea     r11, [rsp+5B8h+var_8]
0x180078476  mov     rbx, [r11+10h]
0x18007847a  mov     rsi, [r11+28h]
0x18007847e  mov     rsp, r11
0x180078481  pop     rdi
0x180078482  retn
```
