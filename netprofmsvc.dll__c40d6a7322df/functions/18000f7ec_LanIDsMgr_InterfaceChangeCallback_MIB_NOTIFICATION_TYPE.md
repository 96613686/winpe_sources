# LanIDsMgr::InterfaceChangeCallback(_MIB_NOTIFICATION_TYPE)

- ea: `0x18000f7ec`
- end: `0x18000fa9b`
- name: `?InterfaceChangeCallback@LanIDsMgr@@AEAAXW4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `687`
- prototype: `void __fastcall(LanIDsMgr *__hidden this, enum _MIB_NOTIFICATION_TYPE)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f750`

## callees

- `0x18000f7ec`
- `0x18000fab0`
- `0x1800102bc`
- `0x1800a88a0`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f865`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f865`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f8ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f901`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f8ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f901`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f90b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f90b`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18000f919`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18000f919`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000f927`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000f927`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanIDsMgr::InterfaceChangeCallback(LanIDsMgr *this, unsigned int a2)
{
  unsigned int v4; // ebx
  int wYear; // [rsp+20h] [rbp-49h]
  int wMonth; // [rsp+28h] [rbp-41h]
  int wDay; // [rsp+30h] [rbp-39h]
  int wHour; // [rsp+38h] [rbp-31h]
  int wMinute; // [rsp+40h] [rbp-29h]
  int wSecond; // [rsp+48h] [rbp-21h]
  int wMilliseconds; // [rsp+50h] [rbp-19h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-1h] BYREF
  struct _FILETIME pftDueTime; // [rsp+78h] [rbp+Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+17h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+88h] [rbp+1Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  SystemTimeAsFileTime = 0;
  LocalFileTime = 0;
  SystemTime = 0;
  pftDueTime = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  ++*((_QWORD *)this + 19);
  *((_BYTE *)this + 169) = 0;
  if ( *((_BYTE *)this + 168) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 20), 0, 0, 0);
    if ( *((_QWORD *)this + 12) || !*((_DWORD *)this + 16) )
      v4 = 5;
    else
      v4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 88);
    pftDueTime = (struct _FILETIME)(-10000000LL * v4);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 20), &pftDueTime, 0, 0);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  FileTimeToLocalFileTime(&SystemTimeAsFileTime, &LocalFileTime);
  FileTimeToSystemTime(&LocalFileTime, &SystemTime);
  wMilliseconds = SystemTime.wMilliseconds;
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  wDay = SystemTime.wDay;
  wMonth = SystemTime.wMonth;
  wYear = SystemTime.wYear;
  (***((void (****)(_QWORD, const char *, ...))this + 98))(
    *((_QWORD *)this + 98),
    "[LanIDsMgr::InterfaceChangeCallback] Notification %I64u type %u @ %04hu/%02hu/%02hu:%02hu:%02hu:%02hu.%03hu",
    *((_QWORD *)this + 19),
    a2,
    wYear,
    wMonth,
    wDay,
    wHour,
    wMinute,
    wSecond,
    wMilliseconds);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  if ( this != (LanIDsMgr *)-8LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000f7ec  mov     [rsp-8+arg_10], rbx
0x18000f7f1  mov     [rsp-8+arg_18], rsi
0x18000f7f6  push    rbp
0x18000f7f7  push    rdi
0x18000f7f8  push    r12
0x18000f7fa  push    r14
0x18000f7fc  push    r15
0x18000f7fe  lea     rbp, [rsp-37h]
0x18000f803  sub     rsp, 0A0h
0x18000f80a  mov     rax, cs:__security_cookie
0x18000f811  xor     rax, rsp
0x18000f814  mov     [rbp+57h+var_30], rax
0x18000f818  mov     r12d, edx
0x18000f81b  mov     r14, rcx
0x18000f81e  lea     rsi, WPP_GLOBAL_Control
0x18000f825  mov     dil, 4
0x18000f828  lea     rbx, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x18000f82f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f836  cmp     rcx, rsi
0x18000f839  jnz     loc_18000F9F7
0x18000f83f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000f847  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], 0
0x18000f84f  xorps   xmm0, xmm0
0x18000f852  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000f856  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0
0x18000f85e  lea     r15, [r14+8]
0x18000f862  mov     rcx, r15; lpCriticalSection
0x18000f865  call    cs:__imp_EnterCriticalSection
0x18000f86b  mov     [rbp+57h+var_60], r15
0x18000f86f  inc     qword ptr [r14+98h]
0x18000f876  mov     byte ptr [r14+0A9h], 0
0x18000f87e  cmp     byte ptr [r14+0A8h], 0
0x18000f886  jnz     loc_18000FA60
0x18000f88c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f893  cmp     rcx, rsi
0x18000f896  jnz     loc_18000F9D7
0x18000f89c  xor     r9d, r9d; msWindowLength
0x18000f89f  xor     r8d, r8d; msPeriod
0x18000f8a2  xor     edx, edx; pftDueTime
0x18000f8a4  mov     rcx, [r14+0A0h]; pti
0x18000f8ab  call    cs:__imp_SetThreadpoolTimer
0x18000f8b1  mov     r9, [r14+60h]
0x18000f8b5  test    r9, r9
0x18000f8b8  jnz     loc_18000FA90
0x18000f8be  cmp     [r14+40h], r9d
0x18000f8c2  jbe     loc_18000FA90
0x18000f8c8  xor     ebx, ebx
0x18000f8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8d1  cmp     rcx, rsi
0x18000f8d4  jnz     loc_18000FA37
0x18000f8da  mov     eax, ebx
0x18000f8dc  imul    rax, 0FFFFFFFFFF676980h
0x18000f8e3  mov     rcx, rax
0x18000f8e6  shr     rcx, 20h
0x18000f8ea  mov     [rbp+57h+pftDueTime.dwHighDateTime], ecx
0x18000f8ed  mov     [rbp+57h+pftDueTime.dwLowDateTime], eax
0x18000f8f0  xor     r9d, r9d; msWindowLength
0x18000f8f3  xor     r8d, r8d; msPeriod
0x18000f8f6  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18000f8fa  mov     rcx, [r14+0A0h]; pti
0x18000f901  call    cs:__imp_SetThreadpoolTimer
0x18000f907  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000f90b  call    cs:__imp_GetSystemTimeAsFileTime
0x18000f911  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x18000f915  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime
0x18000f919  call    cs:__imp_FileTimeToLocalFileTime
0x18000f91f  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x18000f923  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x18000f927  call    cs:__imp_FileTimeToSystemTime
0x18000f92d  mov     rcx, [r14+310h]
0x18000f934  mov     rax, [rcx]
0x18000f937  movzx   edx, [rbp+57h+SystemTime.wMilliseconds]
0x18000f93b  movzx   r8d, [rbp+57h+SystemTime.wSecond]
0x18000f940  movzx   r10d, [rbp+57h+SystemTime.wMinute]
0x18000f945  movzx   r11d, [rbp+57h+SystemTime.wHour]
0x18000f94a  movzx   ebx, [rbp+57h+SystemTime.wDay]
0x18000f94e  movzx   edi, [rbp+57h+SystemTime.wMonth]
0x18000f952  movzx   esi, [rbp+57h+SystemTime.wYear]
0x18000f956  mov     [rsp+0C0h+var_70], edx
0x18000f95a  mov     [rsp+0C0h+var_78], r8d
0x18000f95f  mov     [rsp+0C0h+var_80], r10d
0x18000f964  mov     [rsp+0C0h+var_88], r11d
0x18000f969  mov     [rsp+0C0h+var_90], ebx
0x18000f96d  mov     [rsp+0C0h+var_98], edi
0x18000f971  mov     [rsp+0C0h+var_A0], esi
0x18000f975  mov     r9d, r12d
0x18000f978  mov     r8, [r14+98h]
0x18000f97f  lea     rdx, aLanidsmgrInter; "[LanIDsMgr::InterfaceChangeCallback] No"...
0x18000f986  mov     rax, [rax]
0x18000f989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f98e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f995  lea     rax, WPP_GLOBAL_Control
0x18000f99c  cmp     rcx, rax
0x18000f99f  jnz     short loc_18000FA17
0x18000f9a1  test    r15, r15
0x18000f9a4  jz      short loc_18000F9AF
0x18000f9a6  mov     rcx, r15; lpCriticalSection
0x18000f9a9  call    cs:__imp_LeaveCriticalSection
0x18000f9af  mov     rcx, [rbp+57h+var_30]
0x18000f9b3  xor     rcx, rsp; StackCookie
0x18000f9b6  call    __security_check_cookie
0x18000f9bb  lea     r11, [rsp+0C0h+var_20]
0x18000f9c3  mov     rbx, [r11+40h]
0x18000f9c7  mov     rsi, [r11+48h]
0x18000f9cb  mov     rsp, r11
0x18000f9ce  pop     r15
0x18000f9d0  pop     r14
0x18000f9d2  pop     r12
0x18000f9d4  pop     rdi
0x18000f9d5  pop     rbp
0x18000f9d6  retn
0x18000f9d7  test    [rcx+1Ch], dil
0x18000f9db  jz      loc_18000F89C
0x18000f9e1  mov     edx, 57h ; 'W'
0x18000f9e6  mov     r8, rbx
0x18000f9e9  mov     rcx, [rcx+10h]
0x18000f9ed  call    WPP_SF_
0x18000f9f2  jmp     loc_18000F89C
0x18000f9f7  test    [rcx+1Ch], dil
0x18000f9fb  jz      loc_18000F83F
0x18000fa01  mov     edx, 56h ; 'V'
0x18000fa06  mov     r8, rbx
0x18000fa09  mov     rcx, [rcx+10h]
0x18000fa0d  call    WPP_SF_
0x18000fa12  jmp     loc_18000F83F
0x18000fa17  test    byte ptr [rcx+1Ch], 4
0x18000fa1b  jz      short loc_18000F9A1
0x18000fa1d  mov     edx, 5Ah ; 'Z'
0x18000fa22  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x18000fa29  mov     rcx, [rcx+10h]
0x18000fa2d  call    WPP_SF_
0x18000fa32  jmp     loc_18000F9A1
0x18000fa37  test    [rcx+1Ch], dil
0x18000fa3b  jz      loc_18000F8DA
0x18000fa41  mov     edx, 58h ; 'X'
0x18000fa46  mov     [rsp+0C0h+var_98], ebx
0x18000fa4a  mov     eax, [r14+40h]
0x18000fa4e  mov     [rsp+0C0h+var_A0], eax
0x18000fa52  mov     rcx, [rcx+10h]
0x18000fa56  call    WPP_SF_qDD
0x18000fa5b  jmp     loc_18000F8DA
0x18000fa60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa67  cmp     rcx, rsi
0x18000fa6a  jz      loc_18000F907
0x18000fa70  test    [rcx+1Ch], dil
0x18000fa74  jz      loc_18000F907
0x18000fa7a  mov     edx, 59h ; 'Y'
0x18000fa7f  mov     r8, rbx
0x18000fa82  mov     rcx, [rcx+10h]
0x18000fa86  call    WPP_SF_
0x18000fa8b  jmp     loc_18000F907
0x18000fa90  mov     ebx, 5
0x18000fa95  jmp     loc_18000F8CA
```
