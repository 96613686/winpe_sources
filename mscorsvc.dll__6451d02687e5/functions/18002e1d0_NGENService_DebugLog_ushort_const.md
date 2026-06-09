# NGENService::DebugLog(ushort const *,...)

- ea: `0x18002e1d0`
- end: `0x18002e307`
- name: `?DebugLog@NGENService@@YAXPEBGZZ`
- size: `311`
- prototype: `void(NGENService *__hidden this, const unsigned __int16 *, ...)`
- caller_count: `25`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180002f44`
- `0x180003270`
- `0x18000352c`
- `0x1800039ac`
- `0x180003c90`
- `0x1800040e8`
- `0x180004170`
- `0x1800046c4`
- `0x180004af4`
- `0x180004c5c`
- `0x180004cac`
- `0x1800050b4`
- `0x1800053a0`
- `0x180005688`
- `0x180007130`
- `0x180007518`
- `0x18000765c`
- `0x18001a880`
- `0x18001a990`
- `0x18001a9d8`
- `0x18001afbc`
- `0x18001b038`
- `0x18001b1e4`
- `0x18001b340`
- `0x18001bf08`

## callees

- `0x180002f0c`
- `0x18002dd20`
- `0x18002de54`
- `0x18002e1d0`
- `0x180030d84`
- `0x180032678`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002e21c`
- `KERNEL32!EnterCriticalSection` at `0x18002e21c`
- `KERNEL32!LeaveCriticalSection` at `0x18002e2e6`
- `KERNEL32!LeaveCriticalSection` at `0x18002e2e6`
- `KERNEL32!HeapFree` at `0x18002e2dc`
- `KERNEL32!HeapFree` at `0x18002e2dc`
- `KERNEL32!GetProcessHeap` at `0x18002e2c7`
- `KERNEL32!GetProcessHeap` at `0x18002e2c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void NGENService::DebugLog(NGENService *this, const unsigned __int16 *a2, ...)
{
  bool v2; // dl
  NGENService *v3; // rcx
  bool v4; // dl
  NGENService *v5; // rcx
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rdx
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  int v10; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+3Ch] [rbp-CCh]
  LPVOID lpMem; // [rsp+48h] [rbp-C0h]
  __int16 v13; // [rsp+50h] [rbp-B8h] BYREF
  const unsigned __int16 *v15; // [rsp+2A0h] [rbp+198h] BYREF

  v15 = a2;
  EnterCriticalSection(&NGENService::g_LoggingCS);
  v11 = 512;
  lpMem = &v13;
  v10 = 2;
  v13 = 0;
  SString::VPrintf((SString *)&v10, (const unsigned __int16 *)this, (char *)&v15);
  if ( NGENService::ConfigDebugLog(v3, v2) <= 1 )
  {
    if ( NGENService::ConfigDebugLog(v5, v4) )
    {
      SString::ConvertToUnicode((SString *)&v10);
      NGENService::DebugLogWorker((NGENService *)lpMem, v7);
    }
  }
  else
  {
    SString::ConvertToUnicode((SString *)&v10);
    NGENService::LogWorker((NGENService *)lpMem, v6);
  }
  if ( (v11 & 0x800000000LL) != 0 )
  {
    v8 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v8);
    }
  }
  LeaveCriticalSection(&NGENService::g_LoggingCS);
}

```

## disassembly

```asm
0x18002e1d0  mov     rax, rsp
0x18002e1d3  mov     [rax+8], rcx
0x18002e1d7  mov     [rax+10h], rdx
0x18002e1db  mov     [rax+18h], r8
0x18002e1df  mov     [rax+20h], r9
0x18002e1e3  push    rbp
0x18002e1e4  push    rbx
0x18002e1e5  push    rsi
0x18002e1e6  push    rdi
0x18002e1e7  lea     rbp, [rax-188h]
0x18002e1ee  sub     rsp, 268h
0x18002e1f5  mov     rax, cs:__security_cookie
0x18002e1fc  xor     rax, rsp
0x18002e1ff  mov     [rbp+180h+var_30], rax
0x18002e206  lea     rsi, ?g_LoggingCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_LoggingCS
0x18002e20d  mov     qword ptr [rsp+280h+var_260], rsi
0x18002e212  xor     edi, edi
0x18002e214  mov     byte ptr [rsp+280h+var_258], dil
0x18002e219  mov     rcx, rsi; lpCriticalSection
0x18002e21c  call    cs:__imp_EnterCriticalSection
0x18002e222  mov     byte ptr [rsp+280h+var_258], 1
0x18002e227  mov     qword ptr [rsp+280h+var_250], rdi
0x18002e22c  mov     qword ptr [rsp+34h], 200h
0x18002e235  mov     [rsp+280h+lpMem], rdi
0x18002e23a  lea     rax, [rsp+280h+var_238]
0x18002e23f  mov     [rsp+280h+lpMem], rax
0x18002e244  mov     [rsp+280h+var_250], 2
0x18002e24c  mov     rax, [rsp+280h+lpMem]
0x18002e251  mov     [rax], di
0x18002e254  lea     r8, [rbp+180h+arg_8]; char *
0x18002e25b  mov     rdx, [rbp+180h+arg_0]; unsigned __int16 *
0x18002e262  lea     rcx, [rsp+280h+var_250]; this
0x18002e267  call    ?VPrintf@SString@@QEAAXPEBGPEAD@Z; SString::VPrintf(ushort const *,char *)
0x18002e26c  call    ?ConfigDebugLog@NGENService@@YAKXZ; NGENService::ConfigDebugLog(void)
0x18002e271  cmp     eax, 1
0x18002e274  jbe     short loc_18002E28C
0x18002e276  lea     rcx, [rsp+280h+var_250]; this
0x18002e27b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002e280  mov     rcx, [rsp+280h+lpMem]; this
0x18002e285  call    ?LogWorker@NGENService@@YAXPEBG@Z; NGENService::LogWorker(ushort const *)
0x18002e28a  jmp     short loc_18002E2AA
0x18002e28c  call    ?ConfigDebugLog@NGENService@@YAKXZ; NGENService::ConfigDebugLog(void)
0x18002e291  test    eax, eax
0x18002e293  jz      short loc_18002E2AA
0x18002e295  lea     rcx, [rsp+280h+var_250]; this
0x18002e29a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002e29f  mov     rcx, [rsp+280h+lpMem]; this
0x18002e2a4  call    ?DebugLogWorker@NGENService@@YAXPEBG@Z; NGENService::DebugLogWorker(ushort const *)
0x18002e2a9  nop
0x18002e2aa  test    byte ptr [rsp+280h+var_248], 8
0x18002e2af  jz      short loc_18002E2E3
0x18002e2b1  mov     rbx, [rsp+280h+lpMem]
0x18002e2b6  test    rbx, rbx
0x18002e2b9  jz      short loc_18002E2E3
0x18002e2bb  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002e2c2  test    rax, rax
0x18002e2c5  jnz     short loc_18002E2D4
0x18002e2c7  call    cs:__imp_GetProcessHeap
0x18002e2cd  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002e2d4  mov     r8, rbx; lpMem
0x18002e2d7  xor     edx, edx; dwFlags
0x18002e2d9  mov     rcx, rax; hHeap
0x18002e2dc  call    cs:__imp_HeapFree
0x18002e2e2  nop
0x18002e2e3  mov     rcx, rsi; lpCriticalSection
0x18002e2e6  call    cs:__imp_LeaveCriticalSection
0x18002e2ec  mov     rcx, [rbp+180h+var_30]
0x18002e2f3  xor     rcx, rsp; StackCookie
0x18002e2f6  call    __security_check_cookie
0x18002e2fb  add     rsp, 268h
0x18002e302  pop     rdi
0x18002e303  pop     rsi
0x18002e304  pop     rbx
0x18002e305  pop     rbp
0x18002e306  retn
```
