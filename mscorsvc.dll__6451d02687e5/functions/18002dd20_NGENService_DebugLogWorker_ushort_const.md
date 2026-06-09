# NGENService::DebugLogWorker(ushort const *)

- ea: `0x18002dd20`
- end: `0x18002de54`
- name: `?DebugLogWorker@NGENService@@YAXPEBG@Z`
- size: `308`
- prototype: `void __fastcall(NGENService *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002de54`
- `0x18002e1d0`

## callees

- `0x180001e8c`
- `0x180002f0c`
- `0x18002dd20`
- `0x180030d84`
- `0x180032440`
- `0x180032874`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x18002dd8f`
- `KERNEL32!GetLocalTime` at `0x18002dd8f`
- `KERNEL32!GetCurrentThreadId` at `0x18002ddbb`
- `KERNEL32!GetCurrentThreadId` at `0x18002ddbb`
- `KERNEL32!OutputDebugStringW` at `0x18002ddf1`
- `KERNEL32!OutputDebugStringW` at `0x18002ddf1`
- `KERNEL32!HeapFree` at `0x18002de2a`
- `KERNEL32!HeapFree` at `0x18002de2a`
- `KERNEL32!GetProcessHeap` at `0x18002de15`
- `KERNEL32!GetProcessHeap` at `0x18002de15`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NGENService::DebugLogWorker(NGENService *this, const unsigned __int16 *a2)
{
  DWORD CurrentThreadId; // eax
  WCHAR *v4; // rbx
  HANDLE ProcessHeap; // rax
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-D0h] BYREF
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+44h] [rbp-BCh]
  LPCWSTR lpOutputString; // [rsp+50h] [rbp-B0h]
  __int16 v10; // [rsp+58h] [rbp-A8h] BYREF

  if ( NGENService::ConfigDebugLog(this, (bool)a2) )
  {
    v8 = 512;
    lpOutputString = (LPCWSTR)&v10;
    v7 = 2;
    v10 = 0;
    GetLocalTime(&SystemTime);
    SString::Printf((SString *)&v7, "%02hu:%02hu:%02hu: ", SystemTime.wHour, SystemTime.wMinute, SystemTime.wSecond);
    CurrentThreadId = GetCurrentThreadId();
    SString::AppendPrintf((SString *)&v7, "(%03x): ", CurrentThreadId);
    SString::Append((SString *)&v7, (unsigned __int16 *)this);
    SString::ConvertToUnicode((SString *)&v7);
    OutputDebugStringW(lpOutputString);
    if ( (v8 & 0x800000000LL) != 0 )
    {
      v4 = (WCHAR *)lpOutputString;
      if ( lpOutputString )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v4);
      }
    }
  }
}

```

## disassembly

```asm
0x18002dd20  mov     [rsp-8+arg_8], rbx
0x18002dd25  mov     [rsp-8+arg_10], rdi
0x18002dd2a  push    rbp
0x18002dd2b  lea     rbp, [rsp-170h]
0x18002dd33  sub     rsp, 270h
0x18002dd3a  mov     rax, cs:__security_cookie
0x18002dd41  xor     rax, rsp
0x18002dd44  mov     [rbp+170h+var_10], rax
0x18002dd4b  mov     rbx, rcx
0x18002dd4e  call    ?ConfigDebugLog@NGENService@@YAKXZ; NGENService::ConfigDebugLog(void)
0x18002dd53  xor     edi, edi
0x18002dd55  test    eax, eax
0x18002dd57  jz      loc_18002DE30
0x18002dd5d  mov     [rsp+270h+var_230], rdi
0x18002dd62  mov     [rsp+270h+var_230+4], 200h
0x18002dd6b  mov     [rsp+270h+lpOutputString], rdi
0x18002dd70  lea     rax, [rsp+270h+var_218]
0x18002dd75  mov     [rsp+270h+lpOutputString], rax
0x18002dd7a  mov     dword ptr [rsp+270h+var_230], 2
0x18002dd82  mov     rax, [rsp+270h+lpOutputString]
0x18002dd87  mov     [rax], di
0x18002dd8a  lea     rcx, [rsp+270h+SystemTime]; lpSystemTime
0x18002dd8f  call    cs:__imp_GetLocalTime
0x18002dd95  movzx   eax, [rsp+270h+SystemTime.wSecond]
0x18002dd9a  movzx   r9d, [rsp+270h+SystemTime.wMinute]
0x18002dda0  movzx   r8d, [rsp+270h+SystemTime.wHour]
0x18002dda6  mov     [rsp+270h+var_250], eax
0x18002ddaa  lea     rdx, a02hu02hu02hu; "%02hu:%02hu:%02hu: "
0x18002ddb1  lea     rcx, [rsp+270h+var_230]; this
0x18002ddb6  call    ?Printf@SString@@QEAAXPEBDZZ; SString::Printf(char const *,...)
0x18002ddbb  call    cs:__imp_GetCurrentThreadId
0x18002ddc1  mov     r8d, eax
0x18002ddc4  lea     rdx, a03x; "(%03x): "
0x18002ddcb  lea     rcx, [rsp+270h+var_230]; this
0x18002ddd0  call    ?AppendPrintf@SString@@QEAAXPEBDZZ; SString::AppendPrintf(char const *,...)
0x18002ddd5  mov     rdx, rbx; unsigned __int16 *
0x18002ddd8  lea     rcx, [rsp+270h+var_230]; this
0x18002dddd  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002dde2  lea     rcx, [rsp+270h+var_230]; this
0x18002dde7  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002ddec  mov     rcx, [rsp+270h+lpOutputString]; lpOutputString
0x18002ddf1  call    cs:__imp_OutputDebugStringW
0x18002ddf7  nop
0x18002ddf8  test    [rsp+270h+var_228], 8
0x18002ddfd  jz      short loc_18002DE30
0x18002ddff  mov     rbx, [rsp+270h+lpOutputString]
0x18002de04  test    rbx, rbx
0x18002de07  jz      short loc_18002DE30
0x18002de09  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002de10  test    rax, rax
0x18002de13  jnz     short loc_18002DE22
0x18002de15  call    cs:__imp_GetProcessHeap
0x18002de1b  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002de22  mov     r8, rbx; lpMem
0x18002de25  xor     edx, edx; dwFlags
0x18002de27  mov     rcx, rax; hHeap
0x18002de2a  call    cs:__imp_HeapFree
0x18002de30  mov     rcx, [rbp+170h+var_10]
0x18002de37  xor     rcx, rsp; StackCookie
0x18002de3a  call    __security_check_cookie
0x18002de3f  lea     r11, [rsp+270h+var_s0]
0x18002de47  mov     rbx, [r11+18h]
0x18002de4b  mov     rdi, [r11+20h]
0x18002de4f  mov     rsp, r11
0x18002de52  pop     rbp
0x18002de53  retn
```
