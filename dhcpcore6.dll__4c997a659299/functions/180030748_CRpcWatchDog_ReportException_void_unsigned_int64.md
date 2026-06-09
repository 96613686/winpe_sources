# CRpcWatchDog::ReportException(void *,unsigned __int64)

- ea: `0x180030748`
- end: `0x18003087b`
- name: `?ReportException@CRpcWatchDog@@AEAAXPEAX_K@Z`
- size: `307`
- prototype: `void __fastcall(CRpcWatchDog *this, void *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800193a0`

## callees

- `0x180019ad0`
- `0x18001a3ee`
- `0x180030748`
- `0x180033740`
- `0x180033920`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800307c1`
- `ntdll!RtlCaptureContext` at `0x1800307c1`
- `ntdll!RtlReportExceptionEx` at `0x180030822`
- `ntdll!RtlReportExceptionEx` at `0x180030822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800307fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800307fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800307ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800307ec`

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
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
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
  if ( (BYTE1(xmmword_1800423E0) & 0x40) != 0 )
    WPP_SF_qq(1038, 19, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids, a2, a3);
}

```

## disassembly

```asm
0x180030748  mov     [rsp+arg_0], rbx
0x18003074d  mov     [rsp+arg_18], rsi
0x180030752  push    rdi
0x180030753  sub     rsp, 5B0h
0x18003075a  mov     rax, cs:__security_cookie
0x180030761  xor     rax, rsp
0x180030764  mov     [rsp+5B8h+var_18], rax
0x18003076c  mov     rsi, r8
0x18003076f  mov     rdi, rdx
0x180030772  mov     rbx, rcx
0x180030775  xor     edx, edx; Val
0x180030777  mov     r8d, 4D0h; Size
0x18003077d  lea     rcx, [rsp+5B8h+ContextRecord]; void *
0x180030785  call    memset_0
0x18003078a  xor     edx, edx; Val
0x18003078c  lea     rcx, [rsp+5B8h+var_588]; void *
0x180030791  mov     r8d, 98h; Size
0x180030797  call    memset_0
0x18003079c  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x1800307a3  jz      short loc_1800307B9
0x1800307a5  mov     eax, [rbx+58h]
0x1800307a8  mov     r9, rdi
0x1800307ab  mov     [rsp+5B8h+var_590], eax
0x1800307af  mov     [rsp+5B8h+var_598], rsi
0x1800307b4  call    WPP_SF_qqd
0x1800307b9  lea     rcx, [rsp+5B8h+ContextRecord]; ContextRecord
0x1800307c1  call    cs:__imp_RtlCaptureContext
0x1800307c8  nop     dword ptr [rax+rax+00h]
0x1800307cd  mov     eax, 1
0x1800307d2  mov     [rsp+5B8h+var_588], 5B4h
0x1800307da  mov     [rsp+5B8h+var_584], eax
0x1800307de  mov     [rsp+5B8h+var_570], eax
0x1800307e2  mov     [rsp+5B8h+var_578], rdi
0x1800307e7  mov     [rsp+5B8h+var_568], rsi
0x1800307ec  call    cs:__imp_GetCurrentThread
0x1800307f3  nop     dword ptr [rax+rax+00h]
0x1800307f8  mov     rbx, rax
0x1800307fb  call    cs:__imp_GetCurrentProcess
0x180030802  nop     dword ptr [rax+rax+00h]
0x180030807  mov     r8d, 0Eh
0x18003080d  mov     [rsp+5B8h+var_598], rbx
0x180030812  mov     r9, rax
0x180030815  lea     rdx, [rsp+5B8h+ContextRecord]
0x18003081d  lea     rcx, [rsp+5B8h+var_588]
0x180030822  call    cs:__imp_RtlReportExceptionEx
0x180030829  nop     dword ptr [rax+rax+00h]
0x18003082e  test    byte ptr cs:xmmword_1800423E0+1, 40h
0x180030835  jz      short loc_180030855
0x180030837  mov     edx, 13h
0x18003083c  mov     [rsp+5B8h+var_598], rsi
0x180030841  mov     ecx, 40Eh
0x180030846  lea     r8, WPP_4a51b424fa8f37f25afcfa27acbc090e_Traceguids
0x18003084d  mov     r9, rdi
0x180030850  call    WPP_SF_qq
0x180030855  mov     rcx, [rsp+5B8h+var_18]
0x18003085d  xor     rcx, rsp; StackCookie
0x180030860  call    __security_check_cookie
0x180030865  lea     r11, [rsp+5B8h+var_8]
0x18003086d  mov     rbx, [r11+10h]
0x180030871  mov     rsi, [r11+28h]
0x180030875  mov     rsp, r11
0x180030878  pop     rdi
0x180030879  retn
```
