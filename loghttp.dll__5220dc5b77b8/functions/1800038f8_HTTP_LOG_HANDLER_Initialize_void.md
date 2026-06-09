# HTTP_LOG_HANDLER::Initialize(void)

- ea: `0x1800038f8`
- end: `0x180003a09`
- name: `?Initialize@HTTP_LOG_HANDLER@@SAJXZ`
- size: `273`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800038f8`
- `0x1800051c8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000391a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000391a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ed`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800039e3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800039e3`
- `iisutil!IISInitializeCriticalSection` at `0x180003997`
- `iisutil!IISInitializeCriticalSection` at `0x180003997`

## pseudocode

```c
signed int HTTP_LOG_HANDLER::Initialize(void)
{
  __int64 v0; // rax
  const char *v1; // rcx
  __int64 v2; // rdx
  CHAR *v3; // r8
  CHAR *v4; // rcx
  signed int result; // eax
  __int64 v6; // rax
  LOG_PIPE_SERVER *v7; // rcx
  DWORD nSize; // [rsp+50h] [rbp+8h] BYREF

  nSize = 16;
  if ( GetComputerNameExA(ComputerNameDnsHostname, HTTP_LOG_HANDLER::sm_achComputerName, &nSize) )
    goto LABEL_9;
  v0 = 2147483646;
  v1 = "<Server>";
  v2 = 16;
  v3 = HTTP_LOG_HANDLER::sm_achComputerName;
  do
  {
    if ( !v0 )
      break;
    if ( !*v1 )
      break;
    *v3++ = *v1++;
    --v0;
    --v2;
  }
  while ( v2 );
  v4 = v3 - 1;
  result = v2 == 0 ? 0x8007007A : 0;
  if ( v2 )
    v4 = v3;
  *v4 = 0;
  if ( v2 )
  {
LABEL_9:
    v6 = -1;
    do
      ++v6;
    while ( HTTP_LOG_HANDLER::sm_achComputerName[v6] );
    HTTP_LOG_HANDLER::sm_cchComputerName = (unsigned __int16)v6;
    IISInitializeCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
    qword_18000B730 = (__int64)&HTTP_LOG_HANDLER::sm_LogDataListHead;
    HTTP_LOG_HANDLER::sm_LogDataListHead.Flink = &HTTP_LOG_HANDLER::sm_LogDataListHead;
    result = LOG_PIPE_SERVER::Initialize(v7);
    if ( result >= 0 )
    {
      if ( CreateTimerQueueTimer(
             &HTTP_LOG_HANDLER::sm_hTimer,
             0,
             HTTP_LOG_HANDLER::LogDataScavenger,
             0,
             0x493E0u,
             0x493E0u,
             0x10u) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800038f8  push    rbx
0x1800038fa  sub     rsp, 40h
0x1800038fe  lea     rbx, ?sm_achComputerName@HTTP_LOG_HANDLER@@0PADA; char near * HTTP_LOG_HANDLER::sm_achComputerName
0x180003905  mov     [rsp+48h+nSize], 10h
0x18000390d  mov     rdx, rbx; lpBuffer
0x180003910  lea     r8, [rsp+48h+nSize]; nSize
0x180003915  mov     ecx, 1; NameType
0x18000391a  call    cs:__imp_GetComputerNameExA
0x180003920  test    eax, eax
0x180003922  jnz     short loc_18000397A
0x180003924  mov     eax, 7FFFFFFEh
0x180003929  lea     rcx, aServer; "<Server>"
0x180003930  mov     edx, 10h
0x180003935  mov     r8, rbx
0x180003938  test    rax, rax
0x18000393b  jz      short loc_180003957
0x18000393d  mov     r9b, [rcx]
0x180003940  test    r9b, r9b
0x180003943  jz      short loc_180003957
0x180003945  mov     [r8], r9b
0x180003948  inc     rcx
0x18000394b  inc     r8
0x18000394e  dec     rax
0x180003951  sub     rdx, 1
0x180003955  jnz     short loc_180003938
0x180003957  mov     rax, rdx
0x18000395a  lea     rcx, [r8-1]
0x18000395e  neg     rax
0x180003961  sbb     eax, eax
0x180003963  not     eax
0x180003965  and     eax, 8007007Ah
0x18000396a  test    rdx, rdx
0x18000396d  cmovnz  rcx, r8
0x180003971  mov     byte ptr [rcx], 0
0x180003974  jz      loc_180003A03
0x18000397a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000397e  inc     rax
0x180003981  cmp     byte ptr [rbx+rax], 0
0x180003985  jnz     short loc_18000397E
0x180003987  movzx   eax, ax
0x18000398a  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION HTTP_LOG_HANDLER::sm_csLogDataListLock
0x180003991  mov     cs:?sm_cchComputerName@HTTP_LOG_HANDLER@@0KA, eax; ulong HTTP_LOG_HANDLER::sm_cchComputerName
0x180003997  call    cs:__imp_IISInitializeCriticalSection
0x18000399d  lea     rax, ?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x1800039a4  mov     cs:qword_18000B730, rax
0x1800039ab  mov     cs:?sm_LogDataListHead@HTTP_LOG_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY HTTP_LOG_HANDLER::sm_LogDataListHead
0x1800039b2  call    ?Initialize@LOG_PIPE_SERVER@@QEAAJXZ; LOG_PIPE_SERVER::Initialize(void)
0x1800039b7  test    eax, eax
0x1800039b9  js      short loc_180003A03
0x1800039bb  mov     eax, 493E0h
0x1800039c0  mov     [rsp+48h+Flags], 10h; Flags
0x1800039c8  mov     [rsp+48h+Period], eax; Period
0x1800039cc  lea     r8, ?LogDataScavenger@HTTP_LOG_HANDLER@@SAXPEAXE@Z; Callback
0x1800039d3  xor     r9d, r9d; Parameter
0x1800039d6  mov     [rsp+48h+DueTime], eax; DueTime
0x1800039da  xor     edx, edx; TimerQueue
0x1800039dc  lea     rcx, ?sm_hTimer@HTTP_LOG_HANDLER@@0PEAXEA; phNewTimer
0x1800039e3  call    cs:__imp_CreateTimerQueueTimer
0x1800039e9  test    eax, eax
0x1800039eb  jnz     short loc_180003A01
0x1800039ed  call    cs:__imp_GetLastError
0x1800039f3  test    eax, eax
0x1800039f5  jle     short loc_180003A03
0x1800039f7  movzx   eax, ax
0x1800039fa  or      eax, 80070000h
0x1800039ff  jmp     short loc_180003A03
0x180003a01  xor     eax, eax
0x180003a03  add     rsp, 40h
0x180003a07  pop     rbx
0x180003a08  retn
```
