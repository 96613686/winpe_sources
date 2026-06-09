# xGetMonitorInfo

- ea: `0x18006fce8`
- end: `0x18006fdb9`
- name: `xGetMonitorInfo`
- size: `209`
- prototype: `BOOL __stdcall(HMONITOR, LPMONITORINFO)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18006f6e4`
- `0x18006fb0c`

## callees

- `0x1800095c8`
- `0x18006fba0`
- `0x18006fce8`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!SystemParametersInfoA` at `0x18006fd49`
- `USER32!SystemParametersInfoA` at `0x18006fd49`
- `USER32!GetSystemMetrics` at `0x18006fd5d`
- `USER32!GetSystemMetrics` at `0x18006fd6d`
- `USER32!GetSystemMetrics` at `0x18006fd5d`
- `USER32!GetSystemMetrics` at `0x18006fd6d`

## pseudocode

```c
BOOL __stdcall xGetMonitorInfo(HMONITOR a1, LPMONITORINFO a2)
{
  LONG SystemMetrics; // eax
  bool v6; // cf
  RECT v7; // xmm0
  RECT pvParam; // [rsp+20h] [rbp-28h] BYREF

  pvParam = 0;
  if ( (unsigned int)InitMultipleMonitorStubs() )
    return ((__int64 (__fastcall *)(HMONITOR, LPMONITORINFO))g_pfnGetMonitorInfo)(a1, a2);
  if ( a1 != (HMONITOR)66 || !a2 || a2->cbSize < 0x28 || !SystemParametersInfoA(0x30u, 0, &pvParam, 0) )
    return 0;
  *(_QWORD *)&a2->rcMonitor.left = 0;
  a2->rcMonitor.right = GetSystemMetrics(0);
  SystemMetrics = GetSystemMetrics(1);
  v6 = a2->cbSize < 0x48;
  v7 = pvParam;
  a2->rcMonitor.bottom = SystemMetrics;
  a2->dwFlags = 1;
  a2->rcWork = v7;
  if ( !v6 )
    StringCchCopyA((char *)&a2[1], 0x20u, "DISPLAY");
  return 1;
}

```

## disassembly

```asm
0x18006fce8  mov     [rsp+arg_10], rbx
0x18006fced  push    rdi
0x18006fcee  sub     rsp, 40h
0x18006fcf2  mov     rax, cs:__security_cookie
0x18006fcf9  xor     rax, rsp
0x18006fcfc  mov     [rsp+48h+var_18], rax
0x18006fd01  xorps   xmm0, xmm0
0x18006fd04  mov     rbx, rdx
0x18006fd07  movups  [rsp+48h+pvParam], xmm0
0x18006fd0c  mov     rdi, rcx
0x18006fd0f  call    InitMultipleMonitorStubs
0x18006fd14  test    eax, eax
0x18006fd16  jz      short loc_18006FD2C
0x18006fd18  mov     rax, cs:g_pfnGetMonitorInfo
0x18006fd1f  mov     rdx, rbx
0x18006fd22  mov     rcx, rdi
0x18006fd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd2a  jmp     short loc_18006FDA1
0x18006fd2c  cmp     rdi, 42h ; 'B'
0x18006fd30  jnz     short loc_18006FD9F
0x18006fd32  test    rbx, rbx
0x18006fd35  jz      short loc_18006FD9F
0x18006fd37  cmp     dword ptr [rbx], 28h ; '('
0x18006fd3a  jb      short loc_18006FD9F
0x18006fd3c  xor     r9d, r9d; fWinIni
0x18006fd3f  lea     r8, [rsp+48h+pvParam]; pvParam
0x18006fd44  xor     edx, edx; uiParam
0x18006fd46  lea     ecx, [rdi-12h]; uiAction
0x18006fd49  call    cs:__imp_SystemParametersInfoA
0x18006fd4f  test    eax, eax
0x18006fd51  jz      short loc_18006FD9F
0x18006fd53  xor     ecx, ecx; nIndex
0x18006fd55  mov     qword ptr [rbx+4], 0
0x18006fd5d  call    cs:__imp_GetSystemMetrics
0x18006fd63  mov     edi, 1
0x18006fd68  mov     [rbx+0Ch], eax
0x18006fd6b  mov     ecx, edi; nIndex
0x18006fd6d  call    cs:__imp_GetSystemMetrics
0x18006fd73  cmp     dword ptr [rbx], 48h ; 'H'
0x18006fd76  movups  xmm0, [rsp+48h+pvParam]
0x18006fd7b  mov     [rbx+10h], eax
0x18006fd7e  mov     [rbx+24h], edi
0x18006fd81  movdqu  xmmword ptr [rbx+14h], xmm0
0x18006fd86  jb      short loc_18006FD9B
0x18006fd88  lea     rcx, [rbx+28h]; char *
0x18006fd8c  lea     r8, pszDriver; "DISPLAY"
0x18006fd93  lea     edx, [rdi+1Fh]; unsigned __int64
0x18006fd96  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006fd9b  mov     eax, edi
0x18006fd9d  jmp     short loc_18006FDA1
0x18006fd9f  xor     eax, eax
0x18006fda1  mov     rcx, [rsp+48h+var_18]
0x18006fda6  xor     rcx, rsp; StackCookie
0x18006fda9  call    __security_check_cookie
0x18006fdae  mov     rbx, [rsp+48h+arg_10]
0x18006fdb3  add     rsp, 40h
0x18006fdb7  pop     rdi
0x18006fdb8  retn
```
