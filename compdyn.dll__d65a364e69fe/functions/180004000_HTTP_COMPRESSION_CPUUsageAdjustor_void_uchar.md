# HTTP_COMPRESSION::CPUUsageAdjustor(void *,uchar)

- ea: `0x180004000`
- end: `0x180004120`
- name: `?CPUUsageAdjustor@HTTP_COMPRESSION@@CAXPEAXE@Z`
- size: `288`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x18000403b`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x18000403b`

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
0x180004000  mov     r11, rsp
0x180004003  mov     [r11+8], rbx
0x180004007  push    rdi
0x180004008  sub     rsp, 30h
0x18000400c  xor     ebx, ebx
0x18000400e  mov     edi, 1
0x180004013  mov     [r11-18h], rbx
0x180004017  xor     eax, eax
0x180004019  mov     [r11+20h], rbx
0x18000401d  mov     [r11+18h], rbx
0x180004021  lock cmpxchg cs:?sm_fCPUUsageFired@HTTP_COMPRESSION@@0HA, edi; int HTTP_COMPRESSION::sm_fCPUUsageFired
0x180004029  jnz     loc_1800040F5
0x18000402f  lea     r8, [r11+18h]; lpUserTime
0x180004033  lea     rdx, [r11+20h]; lpKernelTime
0x180004037  lea     rcx, [r11-18h]; lpIdleTime
0x18000403b  call    cs:__imp_GetSystemTimes
0x180004041  test    eax, eax
0x180004043  jz      loc_1800040EF
0x180004049  mov     r9, [rsp+38h+arg_10]
0x18000404e  mov     r10d, dword ptr [rsp+38h+arg_10+4]
0x180004053  mov     r8, [rsp+38h+arg_18]
0x180004058  mov     edx, dword ptr [rsp+38h+arg_18+4]
0x18000405c  mov     rcx, qword ptr [rsp+38h+var_18]
0x180004061  shl     r10, 20h
0x180004065  mov     eax, r9d
0x180004068  or      r10, rax
0x18000406b  shl     rdx, 20h
0x18000406f  mov     eax, r8d
0x180004072  or      rdx, rax
0x180004075  add     r10, rdx
0x180004078  sub     r10, cs:?sm_ulUserTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulUserTime
0x18000407f  sub     r10, cs:?sm_ulKernelTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulKernelTime
0x180004086  jz      short loc_1800040EF
0x180004088  mov     edx, dword ptr [rsp+38h+var_18+4]
0x18000408c  shl     rdx, 20h
0x180004090  mov     eax, ecx
0x180004092  or      rdx, rax
0x180004095  mov     rax, r10
0x180004098  sub     rax, rdx
0x18000409b  xor     edx, edx
0x18000409d  add     rax, cs:?sm_ulIdleTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulIdleTime
0x1800040a4  imul    rax, 64h ; 'd'
0x1800040a8  div     r10
0x1800040ab  cmp     cs:?sm_fStaticCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu
0x1800040b1  mov     r10, rax
0x1800040b4  jnz     loc_1800059DE
0x1800040ba  mov     eax, cs:?sm_dwStaticCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark
0x1800040c0  cmp     eax, 64h ; 'd'
0x1800040c3  jl      loc_1800059F6
0x1800040c9  cmp     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x1800040cf  jz      short loc_180004100
0x1800040d1  cmp     r10d, cs:?sm_dwDynamicCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionLowWaterMark
0x1800040d8  jl      short loc_180004118
0x1800040da  mov     cs:?sm_ulIdleTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rcx; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulIdleTime
0x1800040e1  mov     cs:?sm_ulKernelTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, r8; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulKernelTime
0x1800040e8  mov     cs:?sm_ulUserTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, r9; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulUserTime
0x1800040ef  mov     cs:?sm_fCPUUsageFired@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fCPUUsageFired
0x1800040f5  mov     rbx, [rsp+38h+arg_0]
0x1800040fa  add     rsp, 30h
0x1800040fe  pop     rdi
0x1800040ff  retn
0x180004100  mov     eax, cs:?sm_dwDynamicCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark
0x180004106  cmp     r10d, eax
0x180004109  jl      short loc_1800040DA
0x18000410b  cmp     eax, 64h ; 'd'
0x18000410e  jge     short loc_1800040DA
0x180004110  mov     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, edi; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x180004116  jmp     short loc_1800040DA
0x180004118  mov     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x18000411e  jmp     short loc_1800040DA
0x1800059de  cmp     r10d, cs:?sm_dwStaticCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionLowWaterMark
0x1800059e5  jge     loc_1800040C9
0x1800059eb  mov     cs:?sm_fStaticCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, ebx; int HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu
0x1800059f1  jmp     loc_1800040C9
0x1800059f6  cmp     r10d, eax
0x1800059f9  jl      loc_1800040C9
0x1800059ff  mov     cs:?sm_fStaticCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, edi; int HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu
0x180005a05  jmp     loc_1800040C9
```
