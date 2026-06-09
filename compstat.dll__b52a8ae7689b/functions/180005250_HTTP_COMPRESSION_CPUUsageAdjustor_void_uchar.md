# HTTP_COMPRESSION::CPUUsageAdjustor(void *,uchar)

- ea: `0x180005250`
- end: `0x180005370`
- name: `?CPUUsageAdjustor@HTTP_COMPRESSION@@CAXPEAXE@Z`
- size: `288`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x18000528b`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x18000528b`

## pseudocode

```c
void __fastcall HTTP_COMPRESSION::CPUUsageAdjustor(PVOID a1)
{
  ULONGLONG v1; // r10
  ULONGLONG v2; // r10
  union _ULARGE_INTEGER v3; // [rsp+20h] [rbp-18h] BYREF
  union _ULARGE_INTEGER v4; // [rsp+50h] [rbp+18h] BYREF
  union _ULARGE_INTEGER v5; // [rsp+58h] [rbp+20h] BYREF

  v3.QuadPart = 0;
  v5.QuadPart = 0;
  v4.QuadPart = 0;
  if ( !_InterlockedCompareExchange(&HTTP_COMPRESSION::sm_fCPUUsageFired, 1, 0) )
  {
    if ( GetSystemTimes((PFILETIME)&v3, (PFILETIME)&v5, (PFILETIME)&v4) )
    {
      v1 = v5.QuadPart
         + v4.QuadPart
         - HTTP_COMPRESSION::sm_ulUserTime.QuadPart
         - HTTP_COMPRESSION::sm_ulKernelTime.QuadPart;
      if ( v1 )
      {
        v2 = 100
           * (HTTP_COMPRESSION::sm_ulIdleTime.QuadPart + v1 - (v3.LowPart | ((unsigned __int64)v3.HighPart << 32)))
           / v1;
        if ( HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu )
        {
          if ( (int)v2 < HTTP_COMPRESSION::sm_dwStaticCompressionLowWaterMark )
            HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu = 0;
        }
        else if ( HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark < 100 )
        {
          HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu = (int)v2 >= HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark;
        }
        if ( HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu )
        {
          if ( (int)v2 < HTTP_COMPRESSION::sm_dwDynamicCompressionLowWaterMark )
            HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu = 0;
        }
        else if ( (int)v2 >= HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark )
        {
          HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu = HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark < 100;
        }
        HTTP_COMPRESSION::sm_ulIdleTime = v3;
        HTTP_COMPRESSION::sm_ulKernelTime = v5;
        HTTP_COMPRESSION::sm_ulUserTime = v4;
      }
    }
    HTTP_COMPRESSION::sm_fCPUUsageFired = 0;
  }
}

```

## disassembly

```asm
0x180005250  mov     r11, rsp
0x180005253  mov     [r11+8], rbx
0x180005257  push    rdi
0x180005258  sub     rsp, 30h
0x18000525c  xor     ebx, ebx
0x18000525e  mov     edi, 1
0x180005263  mov     [r11-18h], rbx
0x180005267  xor     eax, eax
0x180005269  mov     [r11+20h], rbx
0x18000526d  mov     [r11+18h], rbx
0x180005271  lock cmpxchg cs:?sm_fCPUUsageFired@HTTP_COMPRESSION@@0HA, edi; int HTTP_COMPRESSION::sm_fCPUUsageFired
0x180005279  jnz     loc_180005345
0x18000527f  lea     r8, [r11+18h]; lpUserTime
0x180005283  lea     rdx, [r11+20h]; lpKernelTime
0x180005287  lea     rcx, [r11-18h]; lpIdleTime
0x18000528b  call    cs:__imp_GetSystemTimes
0x180005291  test    eax, eax
0x180005293  jz      loc_18000533F
0x180005299  mov     r9, [rsp+38h+arg_10]
0x18000529e  mov     r10d, dword ptr [rsp+38h+arg_10+4]
0x1800052a3  mov     r8, [rsp+38h+arg_18]
0x1800052a8  mov     edx, dword ptr [rsp+38h+arg_18+4]
0x1800052ac  mov     rcx, qword ptr [rsp+38h+var_18]
0x1800052b1  shl     r10, 20h
0x1800052b5  mov     eax, r9d
0x1800052b8  or      r10, rax
0x1800052bb  shl     rdx, 20h
0x1800052bf  mov     eax, r8d
0x1800052c2  or      rdx, rax
0x1800052c5  add     r10, rdx
0x1800052c8  sub     r10, cs:?sm_ulUserTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulUserTime
0x1800052cf  sub     r10, cs:?sm_ulKernelTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulKernelTime
0x1800052d6  jz      short loc_18000533F
0x1800052d8  mov     edx, dword ptr [rsp+38h+var_18+4]
0x1800052dc  shl     rdx, 20h
0x1800052e0  mov     eax, ecx
0x1800052e2  or      rdx, rax
0x1800052e5  mov     rax, r10
0x1800052e8  sub     rax, rdx
0x1800052eb  xor     edx, edx
0x1800052ed  add     rax, cs:?sm_ulIdleTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulIdleTime
0x1800052f4  imul    rax, 64h ; 'd'
0x1800052f8  div     r10
0x1800052fb  cmp     cs:?sm_fStaticCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu
0x180005301  mov     r10, rax
0x180005304  jnz     loc_180007518
0x18000530a  mov     eax, cs:?sm_dwStaticCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark
0x180005310  cmp     eax, 64h ; 'd'
0x180005313  jl      loc_180007530
0x180005319  cmp     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x18000531f  jz      short loc_180005350
0x180005321  cmp     r10d, cs:?sm_dwDynamicCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionLowWaterMark
0x180005328  jl      short loc_180005368
0x18000532a  mov     cs:?sm_ulIdleTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rcx; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulIdleTime
0x180005331  mov     cs:?sm_ulKernelTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, r8; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulKernelTime
0x180005338  mov     cs:?sm_ulUserTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, r9; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulUserTime
0x18000533f  mov     cs:?sm_fCPUUsageFired@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fCPUUsageFired
0x180005345  mov     rbx, [rsp+38h+arg_0]
0x18000534a  add     rsp, 30h
0x18000534e  pop     rdi
0x18000534f  retn
0x180005350  mov     eax, cs:?sm_dwDynamicCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark
0x180005356  cmp     r10d, eax
0x180005359  jl      short loc_18000532A
0x18000535b  cmp     eax, 64h ; 'd'
0x18000535e  jge     short loc_18000532A
0x180005360  mov     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, edi; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x180005366  jmp     short loc_18000532A
0x180005368  mov     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x18000536e  jmp     short loc_18000532A
0x180007518  cmp     r10d, cs:?sm_dwStaticCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionLowWaterMark
0x18000751f  jge     loc_180005319
0x180007525  mov     cs:?sm_fStaticCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu
0x18000752b  jmp     loc_180005319
0x180007530  cmp     r10d, eax
0x180007533  jl      loc_180005319
0x180007539  mov     cs:?sm_fStaticCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, edi; int HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu
0x18000753f  jmp     loc_180005319
```
