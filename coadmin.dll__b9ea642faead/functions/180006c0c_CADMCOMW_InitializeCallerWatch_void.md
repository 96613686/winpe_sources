# CADMCOMW::InitializeCallerWatch(void)

- ea: `0x180006c0c`
- end: `0x180006e3b`
- name: `?InitializeCallerWatch@CADMCOMW@@AEAAJXZ`
- size: `559`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800068d4`
- `0x180007ee0`
- `0x180008240`

## callees

- `0x180005514`
- `0x180006c0c`
- `0x18000fb50`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x180006d88`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180006d88`
- `KERNEL32!CloseHandle` at `0x180006d17`
- `KERNEL32!CloseHandle` at `0x180006d17`
- `KERNEL32!LeaveCriticalSection` at `0x180006c9b`
- `KERNEL32!LeaveCriticalSection` at `0x180006c9b`
- `KERNEL32!EnterCriticalSection` at `0x180006c4d`
- `KERNEL32!EnterCriticalSection` at `0x180006c4d`
- `KERNEL32!GetLastError` at `0x180006cb8`
- `KERNEL32!GetLastError` at `0x180006d92`
- `KERNEL32!GetLastError` at `0x180006cb8`
- `KERNEL32!GetLastError` at `0x180006d92`
- `KERNEL32!UnregisterWaitEx` at `0x180006cae`
- `KERNEL32!UnregisterWaitEx` at `0x180006cae`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180006d21`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180006d21`
- `IisRTL!PuDbgPrint` at `0x180006d01`
- `IisRTL!PuDbgPrint` at `0x180006ddf`
- `IisRTL!PuDbgPrint` at `0x180006d01`
- `IisRTL!PuDbgPrint` at `0x180006ddf`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x180006c43`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x180006c43`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180006df5`
- `IisRTL!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180006df5`

## string_xrefs

- `0x180006cfa`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180006dd8`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180006ce8`: `CADMCOMW::InitializeCallerWatch`
- `0x180006dc6`: `CADMCOMW::InitializeCallerWatch`

## pseudocode

```c
__int64 __fastcall CADMCOMW::InitializeCallerWatch(char *Context)
{
  HANDLE v1; // rdi
  CADMCOMW *v3; // rcx
  int CallerPIDAndProcessName; // ebx
  unsigned int v5; // r14d
  signed int v6; // eax
  signed int LastError; // eax
  HANDLE v9; // rax
  HANDLE hObject; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-31h] BYREF
  HANDLE WaitHandle; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v13[56]; // [rsp+48h] [rbp-21h] BYREF

  v1 = 0;
  hObject = 0;
  WaitHandle = 0;
  v11 = 0;
  STRU::STRU((STRU *)v13);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 104));
  if ( *((_DWORD *)Context + 42) )
    goto LABEL_2;
  CallerPIDAndProcessName = CADMCOMW::GetCallerPIDAndProcessName(
                              v3,
                              &v11,
                              (struct STRU *)v13,
                              &hObject,
                              *((_DWORD *)Context + 224));
  if ( CallerPIDAndProcessName < 0 )
    goto LABEL_6;
  v5 = v11;
  if ( v11 == CADMCOMW::sm_dwProcessIdRpcSs )
  {
    CallerPIDAndProcessName = 0;
LABEL_6:
    v1 = hObject;
    goto LABEL_7;
  }
  if ( v11 == CADMCOMW::sm_dwProcessIdThis )
  {
    *((_DWORD *)Context + 42) = CADMCOMW::sm_dwProcessIdThis;
    goto LABEL_6;
  }
  v1 = hObject;
  if ( v11 == -1 )
  {
LABEL_2:
    CallerPIDAndProcessName = 0;
    goto LABEL_7;
  }
  if ( RegisterWaitForSingleObject(
         &WaitHandle,
         hObject,
         CADMCOMW::CallerWatchWaitOrTimerCallback,
         Context,
         0xFFFFFFFF,
         8u) )
  {
    if ( (int)STRU::Copy((STRU *)(Context + 200), (const struct STRU *)v13) >= 0 )
    {
      if ( !*((_QWORD *)Context + 22) )
      {
        v9 = WaitHandle;
        *((_QWORD *)Context + 22) = v1;
        v1 = 0;
        WaitHandle = 0;
        *((_QWORD *)Context + 23) = v9;
        *((_DWORD *)Context + 42) = v5;
      }
      goto LABEL_2;
    }
    CallerPIDAndProcessName = -2147024882;
  }
  else
  {
    LastError = GetLastError();
    CallerPIDAndProcessName = LastError;
    if ( LastError > 0 )
      CallerPIDAndProcessName = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        7112,
        "CADMCOMW::InitializeCallerWatch",
        "RegisterWaitForSingleObject() failed in InitializeCallerWatch hr=0x%08x.\n",
        CallerPIDAndProcessName);
  }
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 104));
  if ( WaitHandle )
  {
    if ( !UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v6 = GetLastError();
      CallerPIDAndProcessName = v6;
      if ( v6 > 0 )
        CallerPIDAndProcessName = (unsigned __int16)v6 | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          7150,
          "CADMCOMW::InitializeCallerWatch",
          "UnregisterWaitEx() failed hr=0x%08x.\n",
          CallerPIDAndProcessName);
    }
    WaitHandle = 0;
  }
  if ( v1 )
    CloseHandle(v1);
  STRU::~STRU((STRU *)v13);
  return (unsigned int)CallerPIDAndProcessName;
}

```

## disassembly

```asm
0x180006c0c  push    rbp
0x180006c0e  push    rbx
0x180006c0f  push    rsi
0x180006c10  push    rdi
0x180006c11  push    r14
0x180006c13  push    r15
0x180006c15  lea     rbp, [rsp-2Fh]
0x180006c1a  sub     rsp, 98h
0x180006c21  mov     rax, cs:__security_cookie
0x180006c28  xor     rax, rsp
0x180006c2b  mov     [rbp+57h+var_40], rax
0x180006c2f  xor     edi, edi
0x180006c31  mov     rsi, rcx
0x180006c34  lea     rcx, [rbp+57h+var_78]
0x180006c38  mov     [rbp+57h+hObject], rdi
0x180006c3c  mov     [rbp+57h+WaitHandle], rdi
0x180006c40  mov     [rbp+57h+var_88], edi
0x180006c43  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006c49  lea     rcx, [rsi+68h]; lpCriticalSection
0x180006c4d  call    cs:__imp_EnterCriticalSection
0x180006c53  cmp     [rsi+0A8h], edi
0x180006c59  jz      short loc_180006C5F
0x180006c5b  xor     ebx, ebx
0x180006c5d  jmp     short loc_180006C97
0x180006c5f  mov     eax, [rsi+380h]
0x180006c65  lea     r9, [rbp+57h+hObject]; void **
0x180006c69  lea     r8, [rbp+57h+var_78]; struct STRU *
0x180006c6d  mov     [rsp+0C0h+dwMilliseconds], eax; int
0x180006c71  lea     rdx, [rbp+57h+var_88]; unsigned int *
0x180006c75  call    ?GetCallerPIDAndProcessName@CADMCOMW@@AEAAJPEAKPEAVSTRU@@PEAPEAXH@Z; CADMCOMW::GetCallerPIDAndProcessName(ulong *,STRU *,void * *,int)
0x180006c7a  mov     ebx, eax
0x180006c7c  test    eax, eax
0x180006c7e  js      short loc_180006C93
0x180006c80  mov     r14d, [rbp+57h+var_88]
0x180006c84  cmp     r14d, cs:?sm_dwProcessIdRpcSs@CADMCOMW@@2KA; ulong CADMCOMW::sm_dwProcessIdRpcSs
0x180006c8b  jnz     loc_180006D45
0x180006c91  xor     ebx, ebx
0x180006c93  mov     rdi, [rbp+57h+hObject]
0x180006c97  lea     rcx, [rsi+68h]; lpCriticalSection
0x180006c9b  call    cs:__imp_LeaveCriticalSection
0x180006ca1  mov     rcx, [rbp+57h+WaitHandle]; WaitHandle
0x180006ca5  test    rcx, rcx
0x180006ca8  jz      short loc_180006D0F
0x180006caa  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006cae  call    cs:__imp_UnregisterWaitEx
0x180006cb4  test    eax, eax
0x180006cb6  jnz     short loc_180006D07
0x180006cb8  call    cs:__imp_GetLastError
0x180006cbe  mov     ebx, eax
0x180006cc0  test    eax, eax
0x180006cc2  jle     short loc_180006CCD
0x180006cc4  movzx   ebx, ax
0x180006cc7  or      ebx, 80070000h
0x180006ccd  test    byte ptr cs:g_dwDebugFlags, 3
0x180006cd4  jz      short loc_180006D07
0x180006cd6  mov     rcx, cs:g_pDebug
0x180006cdd  lea     rax, aUnregisterwait; "UnregisterWaitEx() failed hr=0x%08x.\n"
0x180006ce4  mov     [rsp+0C0h+dwFlags], ebx
0x180006ce8  lea     r9, aCadmcomwInitia; "CADMCOMW::InitializeCallerWatch"
0x180006cef  mov     r8d, 1BEEh
0x180006cf5  mov     qword ptr [rsp+0C0h+dwMilliseconds], rax
0x180006cfa  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180006d01  call    cs:__imp_PuDbgPrint
0x180006d07  mov     [rbp+57h+WaitHandle], 0
0x180006d0f  test    rdi, rdi
0x180006d12  jz      short loc_180006D1D
0x180006d14  mov     rcx, rdi; hObject
0x180006d17  call    cs:__imp_CloseHandle
0x180006d1d  lea     rcx, [rbp+57h+var_78]
0x180006d21  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006d27  mov     eax, ebx
0x180006d29  mov     rcx, [rbp+57h+var_40]
0x180006d2d  xor     rcx, rsp; StackCookie
0x180006d30  call    __security_check_cookie
0x180006d35  add     rsp, 98h
0x180006d3c  pop     r15
0x180006d3e  pop     r14
0x180006d40  pop     rdi
0x180006d41  pop     rsi
0x180006d42  pop     rbx
0x180006d43  pop     rbp
0x180006d44  retn
0x180006d45  mov     eax, cs:?sm_dwProcessIdThis@CADMCOMW@@2KA; ulong CADMCOMW::sm_dwProcessIdThis
0x180006d4b  cmp     r14d, eax
0x180006d4e  jnz     short loc_180006D5B
0x180006d50  mov     [rsi+0A8h], eax
0x180006d56  jmp     loc_180006C93
0x180006d5b  mov     rdi, [rbp+57h+hObject]
0x180006d5f  or      eax, 0FFFFFFFFh
0x180006d62  cmp     r14d, eax
0x180006d65  jz      loc_180006C5B
0x180006d6b  mov     [rsp+0C0h+dwFlags], 8; dwFlags
0x180006d73  lea     r8, ?CallerWatchWaitOrTimerCallback@CADMCOMW@@CAXPEAXE@Z; Callback
0x180006d7a  mov     r9, rsi; Context
0x180006d7d  mov     [rsp+0C0h+dwMilliseconds], eax; dwMilliseconds
0x180006d81  mov     rdx, rdi; hObject
0x180006d84  lea     rcx, [rbp+57h+WaitHandle]; phNewWaitObject
0x180006d88  call    cs:__imp_RegisterWaitForSingleObject
0x180006d8e  test    eax, eax
0x180006d90  jnz     short loc_180006DEA
0x180006d92  call    cs:__imp_GetLastError
0x180006d98  mov     ebx, eax
0x180006d9a  test    eax, eax
0x180006d9c  jle     short loc_180006DA7
0x180006d9e  movzx   ebx, ax
0x180006da1  or      ebx, 80070000h
0x180006da7  test    byte ptr cs:g_dwDebugFlags, 3
0x180006dae  jz      loc_180006C97
0x180006db4  mov     rcx, cs:g_pDebug
0x180006dbb  lea     rax, aRegisterwaitfo; "RegisterWaitForSingleObject() failed in"...
0x180006dc2  mov     [rsp+0C0h+dwFlags], ebx
0x180006dc6  lea     r9, aCadmcomwInitia; "CADMCOMW::InitializeCallerWatch"
0x180006dcd  mov     r8d, 1BC8h
0x180006dd3  mov     qword ptr [rsp+0C0h+dwMilliseconds], rax
0x180006dd8  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180006ddf  call    cs:__imp_PuDbgPrint
0x180006de5  jmp     loc_180006C97
0x180006dea  lea     rcx, [rsi+0C8h]
0x180006df1  lea     rdx, [rbp+57h+var_78]
0x180006df5  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180006dfb  test    eax, eax
0x180006dfd  jns     short loc_180006E09
0x180006dff  mov     ebx, 8007000Eh
0x180006e04  jmp     loc_180006C97
0x180006e09  cmp     qword ptr [rsi+0B0h], 0
0x180006e11  jnz     loc_180006C5B
0x180006e17  mov     rax, [rbp+57h+WaitHandle]
0x180006e1b  mov     [rsi+0B0h], rdi
0x180006e22  xor     edi, edi
0x180006e24  mov     [rbp+57h+WaitHandle], rdi
0x180006e28  mov     [rsi+0B8h], rax
0x180006e2f  mov     [rsi+0A8h], r14d
0x180006e36  jmp     loc_180006C5B
```
