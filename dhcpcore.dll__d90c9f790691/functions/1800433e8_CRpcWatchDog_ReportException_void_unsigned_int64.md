# CRpcWatchDog::ReportException(void *,unsigned __int64)

- ea: `0x1800433e8`
- end: `0x180043502`
- name: `?ReportException@CRpcWatchDog@@AEAAXPEAX_K@Z`
- size: `282`
- prototype: `void __fastcall(CRpcWatchDog *this, void *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c46c`

## callees

- `0x18001cef0`
- `0x18001d826`
- `0x1800433e8`
- `0x18004ca1c`
- `0x18004e160`

## import_xrefs

- `ntdll!RtlReportExceptionEx` at `0x1800434b0`
- `ntdll!RtlReportExceptionEx` at `0x1800434b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004348f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004348f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180043486`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180043486`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180043461`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180043461`

## pseudocode

```c
void __fastcall CRpcWatchDog::ReportException(CRpcWatchDog *this, void *a2, __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  HANDLE CurrentThread; // rbx
  HANDLE CurrentProcess; // rax
  int v11; // [rsp+28h] [rbp-590h]
  _DWORD v12[4]; // [rsp+30h] [rbp-588h] BYREF
  void *v13; // [rsp+40h] [rbp-578h]
  int v14; // [rsp+48h] [rbp-570h]
  __int64 v15; // [rsp+50h] [rbp-568h]
  CONTEXT ContextRecord; // [rsp+D0h] [rbp-4E8h] BYREF

  memset_0(&ContextRecord, 0, sizeof(ContextRecord));
  memset_0(v12, 0, 0x98u);
  if ( (BYTE1(xmmword_1800616A0) & 0x40) != 0 )
  {
    v11 = *((_DWORD *)this + 22);
    WPP_SF_qqd(v7, v6, v8, (_DWORD)a2, a3);
  }
  RtlCaptureContext(&ContextRecord);
  v12[0] = 1460;
  v12[1] = 1;
  v14 = 1;
  v13 = a2;
  v15 = a3;
  CurrentThread = GetCurrentThread();
  CurrentProcess = GetCurrentProcess();
  RtlReportExceptionEx(v12, &ContextRecord, 14, CurrentProcess, CurrentThread, v11);
  if ( (BYTE1(xmmword_1800616A0) & 0x40) != 0 )
    WPP_SF_qq(1038, 19, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, a3);
}

```

## disassembly

```asm
0x1800433e8  mov     [rsp+arg_0], rbx
0x1800433ed  mov     [rsp+arg_18], rsi
0x1800433f2  push    rdi
0x1800433f3  sub     rsp, 5B0h
0x1800433fa  mov     rax, cs:__security_cookie
0x180043401  xor     rax, rsp
0x180043404  mov     [rsp+5B8h+var_18], rax
0x18004340c  mov     rsi, r8
0x18004340f  mov     rdi, rdx
0x180043412  mov     rbx, rcx
0x180043415  xor     edx, edx; Val
0x180043417  mov     r8d, 4D0h; Size
0x18004341d  lea     rcx, [rsp+5B8h+ContextRecord]; void *
0x180043425  call    memset_0
0x18004342a  xor     edx, edx; Val
0x18004342c  lea     rcx, [rsp+5B8h+var_588]; void *
0x180043431  mov     r8d, 98h; Size
0x180043437  call    memset_0
0x18004343c  test    byte ptr cs:xmmword_1800616A0+1, 40h
0x180043443  jz      short loc_180043459
0x180043445  mov     eax, [rbx+58h]
0x180043448  mov     r9, rdi
0x18004344b  mov     [rsp+5B8h+var_590], eax
0x18004344f  mov     [rsp+5B8h+var_598], rsi
0x180043454  call    WPP_SF_qqd
0x180043459  lea     rcx, [rsp+5B8h+ContextRecord]; ContextRecord
0x180043461  call    cs:__imp_RtlCaptureContext
0x180043467  mov     eax, 1
0x18004346c  mov     [rsp+5B8h+var_588], 5B4h
0x180043474  mov     [rsp+5B8h+var_584], eax
0x180043478  mov     [rsp+5B8h+var_570], eax
0x18004347c  mov     [rsp+5B8h+var_578], rdi
0x180043481  mov     [rsp+5B8h+var_568], rsi
0x180043486  call    cs:__imp_GetCurrentThread
0x18004348c  mov     rbx, rax
0x18004348f  call    cs:__imp_GetCurrentProcess
0x180043495  mov     r8d, 0Eh
0x18004349b  mov     [rsp+5B8h+var_598], rbx
0x1800434a0  mov     r9, rax
0x1800434a3  lea     rdx, [rsp+5B8h+ContextRecord]
0x1800434ab  lea     rcx, [rsp+5B8h+var_588]
0x1800434b0  call    cs:__imp_RtlReportExceptionEx
0x1800434b6  test    byte ptr cs:xmmword_1800616A0+1, 40h
0x1800434bd  jz      short loc_1800434DD
0x1800434bf  mov     edx, 13h
0x1800434c4  mov     [rsp+5B8h+var_598], rsi
0x1800434c9  mov     ecx, 40Eh
0x1800434ce  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x1800434d5  mov     r9, rdi
0x1800434d8  call    WPP_SF_qq
0x1800434dd  mov     rcx, [rsp+5B8h+var_18]
0x1800434e5  xor     rcx, rsp; StackCookie
0x1800434e8  call    __security_check_cookie
0x1800434ed  lea     r11, [rsp+5B8h+var_8]
0x1800434f5  mov     rbx, [r11+10h]
0x1800434f9  mov     rsi, [r11+28h]
0x1800434fd  mov     rsp, r11
0x180043500  pop     rdi
0x180043501  retn
```
