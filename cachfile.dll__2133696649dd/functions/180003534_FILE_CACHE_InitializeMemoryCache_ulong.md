# FILE_CACHE::InitializeMemoryCache(ulong)

- ea: `0x180003534`
- end: `0x1800036b8`
- name: `?InitializeMemoryCache@FILE_CACHE@@AEAAJK@Z`
- size: `388`
- prototype: `__int64 __fastcall(PVOID Parameter, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003230`

## callees

- `0x180003534`
- `0x180003c32`
- `0x180003c70`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800035b1`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800035b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003688`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000356e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000356e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003637`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003625`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180003625`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180003658`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180003658`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003677`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003677`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800035fa`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800035fa`
- `iisutil!IISInitializeCriticalSection` at `0x180003564`
- `iisutil!IISInitializeCriticalSection` at `0x180003564`

## pseudocode

```c
signed int __fastcall FILE_CACHE::InitializeMemoryCache(char *Parameter, int a2)
{
  signed int result; // eax
  DWORDLONG v5; // rax
  signed int v6; // ebx
  DWORDLONG ullTotalVirtual; // rax
  HANDLE *v8; // r14
  signed int LastError; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  void *v12; // rcx
  _MEMORYSTATUSEX Buffer; // [rsp+40h] [rbp-68h] BYREF

  if ( (unsigned int)IISInitializeCriticalSection(Parameter + 72) )
  {
    v5 = *((_QWORD *)Parameter + 6);
    v6 = 0;
    if ( !v5 )
    {
      memset_0(&Buffer, 0, sizeof(Buffer));
      Buffer.dwLength = 64;
      GlobalMemoryStatusEx(&Buffer);
      ullTotalVirtual = Buffer.ullTotalVirtual;
      if ( Buffer.ullAvailPhys < Buffer.ullTotalVirtual )
        ullTotalVirtual = Buffer.ullAvailPhys;
      v5 = ullTotalVirtual >> 1;
    }
    *((_QWORD *)Parameter + 14) = v5;
    v8 = (HANDLE *)(Parameter + 136);
    if ( !CreateTimerQueueTimer(
            (PHANDLE)Parameter + 17,
            0,
            FILE_CACHE::ScavengerAndMemoryCacheAdjustor,
            Parameter,
            1000 * a2,
            1000 * a2,
            0x10u) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_16;
    }
    v10 = HeapCreate(0, 0, 0);
    *((_QWORD *)Parameter + 16) = v10;
    if ( !v10 )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 < 0 )
      {
LABEL_16:
        v12 = (void *)*((_QWORD *)Parameter + 16);
        if ( v12 )
        {
          HeapDestroy(v12);
          *((_QWORD *)Parameter + 16) = 0;
        }
        if ( *v8 )
        {
          DeleteTimerQueueTimer(0, *v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          *v8 = 0;
        }
        DeleteCriticalSection((LPCRITICAL_SECTION)(Parameter + 72));
      }
    }
    return v6;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180003534  mov     [rsp+arg_10], rbx
0x180003539  mov     [rsp+arg_18], rbp
0x18000353e  push    rsi
0x18000353f  push    rdi
0x180003540  push    r14
0x180003542  sub     rsp, 90h
0x180003549  mov     rax, cs:__security_cookie
0x180003550  xor     rax, rsp
0x180003553  mov     [rsp+0A8h+var_28], rax
0x18000355b  mov     rdi, rcx
0x18000355e  mov     esi, edx
0x180003560  add     rcx, 48h ; 'H'
0x180003564  call    cs:__imp_IISInitializeCriticalSection
0x18000356a  test    eax, eax
0x18000356c  jnz     short loc_180003589
0x18000356e  call    cs:__imp_GetLastError
0x180003574  test    eax, eax
0x180003576  jle     loc_180003690
0x18000357c  movzx   eax, ax
0x18000357f  or      eax, 80070000h
0x180003584  jmp     loc_180003690
0x180003589  mov     rax, [rdi+30h]
0x18000358d  xor     ebx, ebx
0x18000358f  test    rax, rax
0x180003592  jnz     short loc_1800035CA
0x180003594  lea     r14d, [rbx+40h]
0x180003598  xor     edx, edx; Val
0x18000359a  mov     r8d, r14d; Size
0x18000359d  lea     rcx, [rsp+0A8h+Buffer]; void *
0x1800035a2  call    memset_0
0x1800035a7  lea     rcx, [rsp+0A8h+Buffer]; lpBuffer
0x1800035ac  mov     [rsp+0A8h+Buffer.dwLength], r14d
0x1800035b1  call    cs:__imp_GlobalMemoryStatusEx
0x1800035b7  mov     rax, [rsp+0A8h+Buffer.ullTotalVirtual]
0x1800035bc  cmp     [rsp+0A8h+Buffer.ullAvailPhys], rax
0x1800035c1  cmovb   rax, [rsp+0A8h+Buffer.ullAvailPhys]
0x1800035c7  shr     rax, 1
0x1800035ca  mov     [rdi+70h], rax
0x1800035ce  lea     r14, [rdi+88h]
0x1800035d5  imul    eax, esi, 3E8h
0x1800035db  lea     r8, ?ScavengerAndMemoryCacheAdjustor@FILE_CACHE@@CAXPEAXE@Z; Callback
0x1800035e2  mov     [rsp+0A8h+Flags], 10h; Flags
0x1800035ea  mov     r9, rdi; Parameter
0x1800035ed  xor     edx, edx; TimerQueue
0x1800035ef  mov     rcx, r14; phNewTimer
0x1800035f2  mov     [rsp+0A8h+Period], eax; Period
0x1800035f6  mov     [rsp+0A8h+DueTime], eax; DueTime
0x1800035fa  call    cs:__imp_CreateTimerQueueTimer
0x180003600  mov     esi, 80070000h
0x180003605  test    eax, eax
0x180003607  jnz     short loc_18000361E
0x180003609  call    cs:__imp_GetLastError
0x18000360f  mov     ebx, eax
0x180003611  test    eax, eax
0x180003613  jle     short loc_18000361A
0x180003615  movzx   ebx, ax
0x180003618  or      ebx, esi
0x18000361a  test    ebx, ebx
0x18000361c  js      short loc_18000364C
0x18000361e  xor     r8d, r8d; dwMaximumSize
0x180003621  xor     edx, edx; dwInitialSize
0x180003623  xor     ecx, ecx; flOptions
0x180003625  call    cs:__imp_HeapCreate
0x18000362b  mov     [rdi+80h], rax
0x180003632  test    rax, rax
0x180003635  jnz     short loc_18000368E
0x180003637  call    cs:__imp_GetLastError
0x18000363d  mov     ebx, eax
0x18000363f  test    eax, eax
0x180003641  jle     short loc_180003648
0x180003643  movzx   ebx, ax
0x180003646  or      ebx, esi
0x180003648  test    ebx, ebx
0x18000364a  jns     short loc_18000368E
0x18000364c  mov     rcx, [rdi+80h]; hHeap
0x180003653  test    rcx, rcx
0x180003656  jz      short loc_180003669
0x180003658  call    cs:__imp_HeapDestroy
0x18000365e  mov     qword ptr [rdi+80h], 0
0x180003669  mov     rdx, [r14]; Timer
0x18000366c  test    rdx, rdx
0x18000366f  jz      short loc_180003684
0x180003671  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180003675  xor     ecx, ecx; TimerQueue
0x180003677  call    cs:__imp_DeleteTimerQueueTimer
0x18000367d  mov     qword ptr [r14], 0
0x180003684  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003688  call    cs:__imp_DeleteCriticalSection
0x18000368e  mov     eax, ebx
0x180003690  mov     rcx, [rsp+0A8h+var_28]
0x180003698  xor     rcx, rsp; StackCookie
0x18000369b  call    __security_check_cookie
0x1800036a0  lea     r11, [rsp+0A8h+var_18]
0x1800036a8  mov     rbx, [r11+30h]
0x1800036ac  mov     rbp, [r11+38h]
0x1800036b0  mov     rsp, r11
0x1800036b3  pop     r14
0x1800036b5  pop     rdi
0x1800036b6  pop     rsi
0x1800036b7  retn
```
