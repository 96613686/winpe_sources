# xGetMonitorInfo

- ea: `0x14002e550`
- end: `0x14002e651`
- name: `xGetMonitorInfo`
- size: `257`
- prototype: `BOOL __stdcall(HMONITOR, LPMONITORINFO)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002ec90`

## callees

- `0x140001020`
- `0x14002e550`
- `0x14002f4d0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14002e5b1`
- `KERNEL32!MultiByteToWideChar` at `0x14002e5b1`
- `USER32!SystemParametersInfoA` at `0x14002e5db`
- `USER32!SystemParametersInfoA` at `0x14002e5db`
- `USER32!GetSystemMetrics` at `0x14002e5ef`
- `USER32!GetSystemMetrics` at `0x14002e5ff`
- `USER32!GetSystemMetrics` at `0x14002e5ef`
- `USER32!GetSystemMetrics` at `0x14002e5ff`

## pseudocode

```c
BOOL __stdcall xGetMonitorInfo(HMONITOR a1, LPMONITORINFO a2)
{
  int MonitorInfo; // edi
  LONG SystemMetrics; // eax
  bool v7; // cf
  RECT v8; // xmm0
  RECT pvParam; // [rsp+30h] [rbp-28h] BYREF

  if ( (unsigned int)InitMultipleMonitorStubs() )
  {
    MonitorInfo = g_pfnGetMonitorInfo(a1, a2);
    if ( MonitorInfo && !g_fMultimonPlatformNT && a2->cbSize >= 0x68 )
      MultiByteToWideChar(0, 0, (LPCCH)&a2[1], -1, (LPWSTR)&a2[1], 32);
    return MonitorInfo;
  }
  if ( a1 == (HMONITOR)305397826 && a2 && a2->cbSize >= 0x28 && SystemParametersInfoA(0x30u, 0, &pvParam, 0) )
  {
    a2->rcMonitor.left = 0;
    a2->rcMonitor.top = 0;
    MonitorInfo = 1;
    a2->rcMonitor.right = GetSystemMetrics(0);
    SystemMetrics = GetSystemMetrics(1);
    v7 = a2->cbSize < 0x68;
    v8 = pvParam;
    a2->rcMonitor.bottom = SystemMetrics;
    a2->dwFlags = 1;
    a2->rcWork = v8;
    if ( !v7 )
      MultiByteToWideChar(0, 0, "DISPLAY", -1, (LPWSTR)&a2[1], 32);
    return MonitorInfo;
  }
  return 0;
}

```

## disassembly

```asm
0x14002e550  mov     [rsp+arg_10], rbx
0x14002e555  push    rdi
0x14002e556  sub     rsp, 50h
0x14002e55a  mov     rax, cs:__security_cookie
0x14002e561  xor     rax, rsp
0x14002e564  mov     [rsp+58h+var_18], rax
0x14002e569  mov     rbx, rdx
0x14002e56c  mov     rdi, rcx
0x14002e56f  call    InitMultipleMonitorStubs
0x14002e574  test    eax, eax
0x14002e576  jz      short loc_14002E5BB
0x14002e578  mov     rdx, rbx
0x14002e57b  mov     rcx, rdi
0x14002e57e  call    cs:g_pfnGetMonitorInfo
0x14002e584  mov     edi, eax
0x14002e586  test    eax, eax
0x14002e588  jz      short loc_14002E5B7
0x14002e58a  cmp     cs:g_fMultimonPlatformNT, 0
0x14002e591  jnz     short loc_14002E5B7
0x14002e593  cmp     dword ptr [rbx], 68h ; 'h'
0x14002e596  jb      short loc_14002E5B7
0x14002e598  lea     r8, [rbx+28h]; lpMultiByteStr
0x14002e59c  mov     [rsp+58h+cchWideChar], 20h ; ' '; cchWideChar
0x14002e5a4  mov     [rsp+58h+lpWideCharStr], r8; lpWideCharStr
0x14002e5a9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14002e5ad  xor     edx, edx; dwFlags
0x14002e5af  xor     ecx, ecx; CodePage
0x14002e5b1  call    cs:__imp_MultiByteToWideChar
0x14002e5b7  mov     eax, edi
0x14002e5b9  jmp     short loc_14002E639
0x14002e5bb  cmp     rdi, 12340042h
0x14002e5c2  jnz     short loc_14002E637
0x14002e5c4  test    rbx, rbx
0x14002e5c7  jz      short loc_14002E637
0x14002e5c9  cmp     dword ptr [rbx], 28h ; '('
0x14002e5cc  jb      short loc_14002E637
0x14002e5ce  xor     edx, edx; uiParam
0x14002e5d0  lea     r8, [rsp+58h+pvParam]; pvParam
0x14002e5d5  xor     r9d, r9d; fWinIni
0x14002e5d8  lea     ecx, [rdx+30h]; uiAction
0x14002e5db  call    cs:__imp_SystemParametersInfoA
0x14002e5e1  test    eax, eax
0x14002e5e3  jz      short loc_14002E637
0x14002e5e5  and     dword ptr [rbx+4], 0
0x14002e5e9  xor     ecx, ecx; nIndex
0x14002e5eb  and     dword ptr [rbx+8], 0
0x14002e5ef  call    cs:__imp_GetSystemMetrics
0x14002e5f5  mov     edi, 1
0x14002e5fa  mov     [rbx+0Ch], eax
0x14002e5fd  mov     ecx, edi; nIndex
0x14002e5ff  call    cs:__imp_GetSystemMetrics
0x14002e605  cmp     dword ptr [rbx], 68h ; 'h'
0x14002e608  movups  xmm0, [rsp+58h+pvParam]
0x14002e60d  mov     [rbx+10h], eax
0x14002e610  mov     [rbx+24h], edi
0x14002e613  movdqu  xmmword ptr [rbx+14h], xmm0
0x14002e618  jb      short loc_14002E5B7
0x14002e61a  lea     rcx, [rbx+28h]
0x14002e61e  mov     [rsp+58h+cchWideChar], 20h ; ' '
0x14002e626  mov     [rsp+58h+lpWideCharStr], rcx
0x14002e62b  lea     r8, aDisplay; "DISPLAY"
0x14002e632  jmp     loc_14002E5A9
0x14002e637  xor     eax, eax
0x14002e639  mov     rcx, [rsp+58h+var_18]
0x14002e63e  xor     rcx, rsp; StackCookie
0x14002e641  call    __security_check_cookie
0x14002e646  mov     rbx, [rsp+58h+arg_10]
0x14002e64b  add     rsp, 50h
0x14002e64f  pop     rdi
0x14002e650  retn
```
