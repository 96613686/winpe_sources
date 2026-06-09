# AD_LOOKUP_MANAGER::Initialize(void)

- ea: `0x1800252dc`
- end: `0x1800254a6`
- name: `?Initialize@AD_LOOKUP_MANAGER@@QEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(AD_LOOKUP_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800029fc`

## callees

- `0x180001210`
- `0x1800252dc`
- `0x180025a58`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18002533a`
- `KERNEL32!CreateEventW` at `0x180025357`
- `KERNEL32!CreateEventW` at `0x18002533a`
- `KERNEL32!CreateEventW` at `0x180025357`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025307`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025307`
- `KERNEL32!CreateThread` at `0x1800253dc`
- `KERNEL32!CreateThread` at `0x1800253dc`
- `KERNEL32!GetLastError` at `0x18002542d`
- `KERNEL32!GetLastError` at `0x18002542d`
- `KERNEL32!GetSystemInfo` at `0x18002536f`
- `KERNEL32!GetSystemInfo` at `0x18002536f`
- `iisutil!PuDbgPrintError` at `0x180025484`
- `iisutil!PuDbgPrintError` at `0x180025484`

## pseudocode

```c
__int64 __fastcall AD_LOOKUP_MANAGER::Initialize(AD_LOOKUP_MANAGER *this)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax
  DWORD dwNumberOfProcessors; // ebx
  void *v5; // rax
  __int64 v6; // rsi
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  signed int LastError; // eax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8), 0x800003E8) )
    goto LABEL_15;
  *((_DWORD *)this + 12) = 1;
  *((_QWORD *)this + 8) = (char *)this + 56;
  *((_QWORD *)this + 7) = (char *)this + 56;
  *((_DWORD *)this + 24) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 9) = EventW;
  if ( !EventW )
    goto LABEL_15;
  v3 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = v3;
  if ( !v3 )
    goto LABEL_15;
  GetSystemInfo(&SystemInfo);
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  if ( SystemInfo.dwNumberOfProcessors > 4 )
    dwNumberOfProcessors = (SystemInfo.dwNumberOfProcessors >> 1) + 2;
  if ( dwNumberOfProcessors > 0x19 )
    dwNumberOfProcessors = 25;
  v5 = operator new(saturated_mul(dwNumberOfProcessors, 8u));
  *((_QWORD *)this + 11) = v5;
  if ( !v5 )
  {
LABEL_20:
    v7 = -2147024888;
LABEL_21:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ad_lookup_manager.cxx",
        878,
        "AD_LOOKUP_MANAGER::Initialize",
        v7,
        " AD_LOOKUP_MANAGER initialization failed.\n",
        *(_QWORD *)&SystemInfo.dwOemId,
        SystemInfo.lpMinimumApplicationAddress,
        SystemInfo.lpMaximumApplicationAddress,
        SystemInfo.dwActiveProcessorMask);
    AD_LOOKUP_MANAGER::Terminate(this);
    return v7;
  }
  v6 = 0;
  if ( !dwNumberOfProcessors )
  {
LABEL_12:
    v7 = 0;
    if ( *(_QWORD *)this )
      return v7;
    v8 = operator new(0x18u);
    if ( v8 )
    {
      v8[4] = 0;
      v8[5] = 0;
      *((_QWORD *)v8 + 1) = v8;
      *(_QWORD *)v8 = v8;
      *(_QWORD *)this = v8;
      return v7;
    }
    *(_QWORD *)this = 0;
    goto LABEL_20;
  }
  while ( 1 )
  {
    *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v6) = CreateThread(0, 0, AD_LOOKUP_MANAGER::WorkerThread, this, 0, 0);
    if ( !*(_QWORD *)(*((_QWORD *)this + 11) + 8 * v6) )
      break;
    ++*((_DWORD *)this + 24);
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= dwNumberOfProcessors )
      goto LABEL_12;
  }
LABEL_15:
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_21;
  return v7;
}

```

## disassembly

```asm
0x1800252dc  mov     rax, rsp
0x1800252df  mov     [rax+10h], rbx
0x1800252e3  mov     [rax+18h], rsi
0x1800252e7  push    rdi
0x1800252e8  sub     rsp, 60h
0x1800252ec  xorps   xmm0, xmm0
0x1800252ef  mov     rdi, rcx
0x1800252f2  add     rcx, 8; lpCriticalSection
0x1800252f6  mov     edx, 800003E8h; dwSpinCount
0x1800252fb  movups  xmmword ptr [rax-38h], xmm0
0x1800252ff  movups  xmmword ptr [rax-28h], xmm0
0x180025303  movups  xmmword ptr [rax-18h], xmm0
0x180025307  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002530d  test    eax, eax
0x18002530f  jz      loc_18002542D
0x180025315  lea     rax, [rdi+38h]
0x180025319  mov     dword ptr [rdi+30h], 1
0x180025320  xor     r9d, r9d; lpName
0x180025323  mov     [rax+8], rax
0x180025327  mov     [rax], rax
0x18002532a  xor     r8d, r8d; bInitialState
0x18002532d  xor     ecx, ecx; lpEventAttributes
0x18002532f  mov     dword ptr [rdi+60h], 0
0x180025336  lea     edx, [r9+1]; bManualReset
0x18002533a  call    cs:__imp_CreateEventW
0x180025340  mov     [rdi+48h], rax
0x180025344  test    rax, rax
0x180025347  jz      loc_18002542D
0x18002534d  xor     r9d, r9d; lpName
0x180025350  xor     r8d, r8d; bInitialState
0x180025353  xor     edx, edx; bManualReset
0x180025355  xor     ecx, ecx; lpEventAttributes
0x180025357  call    cs:__imp_CreateEventW
0x18002535d  mov     [rdi+50h], rax
0x180025361  test    rax, rax
0x180025364  jz      loc_18002542D
0x18002536a  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x18002536f  call    cs:__imp_GetSystemInfo
0x180025375  mov     ebx, [rsp+68h+SystemInfo.dwNumberOfProcessors]
0x180025379  cmp     ebx, 4
0x18002537c  jbe     short loc_180025383
0x18002537e  shr     ebx, 1
0x180025380  add     ebx, 2
0x180025383  mov     eax, 19h
0x180025388  cmp     ebx, eax
0x18002538a  cmova   ebx, eax
0x18002538d  mov     eax, 8
0x180025392  mov     ecx, ebx
0x180025394  mul     rcx
0x180025397  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002539e  cmovb   rax, rcx
0x1800253a2  mov     rcx, rax; Size
0x1800253a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800253aa  mov     [rdi+58h], rax
0x1800253ae  test    rax, rax
0x1800253b1  jz      loc_18002544B
0x1800253b7  xor     esi, esi
0x1800253b9  test    ebx, ebx
0x1800253bb  jz      short loc_1800253FE
0x1800253bd  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1800253c6  lea     r8, ?WorkerThread@AD_LOOKUP_MANAGER@@CAKPEAX@Z; lpStartAddress
0x1800253cd  mov     r9, rdi; lpParameter
0x1800253d0  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800253d8  xor     edx, edx; dwStackSize
0x1800253da  xor     ecx, ecx; lpThreadAttributes
0x1800253dc  call    cs:__imp_CreateThread
0x1800253e2  mov     rcx, [rdi+58h]
0x1800253e6  mov     [rcx+rsi*8], rax
0x1800253ea  mov     rax, [rdi+58h]
0x1800253ee  cmp     qword ptr [rax+rsi*8], 0
0x1800253f3  jz      short loc_18002542D
0x1800253f5  inc     dword ptr [rdi+60h]
0x1800253f8  inc     esi
0x1800253fa  cmp     esi, ebx
0x1800253fc  jb      short loc_1800253BD
0x1800253fe  xor     ebx, ebx
0x180025400  cmp     [rdi], rbx
0x180025403  jnz     loc_180025492
0x180025409  lea     ecx, [rbx+18h]; Size
0x18002540c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025411  mov     [rsp+68h+arg_0], rax
0x180025416  test    rax, rax
0x180025419  jz      short loc_180025448
0x18002541b  mov     [rax+10h], ebx
0x18002541e  mov     [rax+14h], ebx
0x180025421  mov     [rax+8], rax
0x180025425  mov     [rax], rax
0x180025428  mov     [rdi], rax
0x18002542b  jmp     short loc_180025492
0x18002542d  call    cs:__imp_GetLastError
0x180025433  mov     ebx, eax
0x180025435  test    eax, eax
0x180025437  jle     short loc_180025442
0x180025439  movzx   ebx, ax
0x18002543c  or      ebx, 80070000h
0x180025442  test    ebx, ebx
0x180025444  jns     short loc_180025492
0x180025446  jmp     short loc_180025450
0x180025448  mov     [rdi], rbx
0x18002544b  mov     ebx, 80070008h
0x180025450  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025457  jz      short loc_18002548A
0x180025459  mov     rcx, cs:g_pDebug
0x180025460  lea     rax, aAdLookupManage; " AD_LOOKUP_MANAGER initialization faile"...
0x180025467  mov     [rsp+68h+lpThreadId], rax
0x18002546c  lea     r9, aAdLookupManage_0; "AD_LOOKUP_MANAGER::Initialize"
0x180025473  mov     r8d, 36Eh
0x180025479  mov     [rsp+68h+dwCreationFlags], ebx
0x18002547d  lea     rdx, aInetsrvIisIisr_3; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180025484  call    cs:__imp_PuDbgPrintError
0x18002548a  mov     rcx, rdi; this
0x18002548d  call    ?Terminate@AD_LOOKUP_MANAGER@@QEAAXXZ; AD_LOOKUP_MANAGER::Terminate(void)
0x180025492  lea     r11, [rsp+68h+var_8]
0x180025497  mov     eax, ebx
0x180025499  mov     rbx, [r11+18h]
0x18002549d  mov     rsi, [r11+20h]
0x1800254a1  mov     rsp, r11
0x1800254a4  pop     rdi
0x1800254a5  retn
```
