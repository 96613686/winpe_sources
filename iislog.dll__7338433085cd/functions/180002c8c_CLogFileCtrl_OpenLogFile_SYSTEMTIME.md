# CLogFileCtrl::OpenLogFile(_SYSTEMTIME *)

- ea: `0x180002c8c`
- end: `0x180002fcb`
- name: `?OpenLogFile@CLogFileCtrl@@AEAAHPEAU_SYSTEMTIME@@@Z`
- size: `831`
- prototype: `__int64 __fastcall(CLogFileCtrl *__hidden this, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180003374`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000216c`
- `0x180002c8c`
- `0x18000d0e0`
- `0x18000d22c`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180002d2c`
- `msvcrt!strcpy_s` at `0x180002d2c`
- `msvcrt!strcat_s` at `0x180002db9`
- `msvcrt!strcat_s` at `0x180002dce`
- `msvcrt!strcat_s` at `0x180002e6f`
- `msvcrt!strcat_s` at `0x180002e84`
- `msvcrt!strcat_s` at `0x180002db9`
- `msvcrt!strcat_s` at `0x180002dce`
- `msvcrt!strcat_s` at `0x180002e6f`
- `msvcrt!strcat_s` at `0x180002e84`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180002ebb`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180002ebb`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180002f3e`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180002f3e`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x180002e55`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x180002f90`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x180002e55`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x180002f90`
- `IisRTL!IISCreateDirectory` at `0x180002d74`
- `IisRTL!IISCreateDirectory` at `0x180002d74`
- `KERNEL32!SetLastError` at `0x180002e09`
- `KERNEL32!SetLastError` at `0x180002f98`
- `KERNEL32!SetLastError` at `0x180002e09`
- `KERNEL32!SetLastError` at `0x180002f98`
- `KERNEL32!GetSystemInfo` at `0x180002ee0`
- `KERNEL32!GetSystemInfo` at `0x180002ee0`
- `KERNEL32!GetLastError` at `0x180002d52`
- `KERNEL32!GetLastError` at `0x180002de0`
- `KERNEL32!GetLastError` at `0x180002e37`
- `KERNEL32!GetLastError` at `0x180002d52`
- `KERNEL32!GetLastError` at `0x180002de0`
- `KERNEL32!GetLastError` at `0x180002e37`
- `KERNEL32!CloseHandle` at `0x180002e00`
- `KERNEL32!CloseHandle` at `0x180002e00`
- `KERNEL32!GetCurrentThread` at `0x180002d32`
- `KERNEL32!GetCurrentThread` at `0x180002d32`
- `USER32!CharPrevA` at `0x180002d9f`
- `USER32!CharPrevA` at `0x180002d9f`
- `ADVAPI32!SetThreadToken` at `0x180002df5`
- `ADVAPI32!SetThreadToken` at `0x180002df5`
- `ADVAPI32!RevertToSelf` at `0x180002d67`
- `ADVAPI32!RevertToSelf` at `0x180002d67`
- `ADVAPI32!OpenThreadToken` at `0x180002d48`
- `ADVAPI32!OpenThreadToken` at `0x180002d48`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::OpenLogFile(CLogFileCtrl *this, struct _SYSTEMTIME *a2)
{
  unsigned int v3; // esi
  __int64 v4; // rax
  unsigned int v5; // edx
  HANDLE CurrentThread; // rax
  int DirectoryForSystemAndAdministrators; // edi
  __int64 v8; // rax
  DWORD LastError; // r14d
  DWORD v10; // eax
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  DWORD dwAllocationGranularity; // eax
  unsigned int v14; // r8d
  BOOL v15; // r9d
  int v16; // eax
  _QWORD *v17; // rdi
  HANDLE TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  char *v20; // [rsp+38h] [rbp-C8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Destination[304]; // [rsp+70h] [rbp-90h] BYREF

  v3 = 1;
  TokenHandle = 0;
  if ( !*((_QWORD *)this + 7) )
  {
    if ( *((_DWORD *)this + 28) || *((_DWORD *)this + 27) )
    {
      v4 = *(_QWORD *)this;
      *((_DWORD *)this + 28) = 0;
      (*(void (__fastcall **)(CLogFileCtrl *, struct _SYSTEMTIME *))(v4 + 96))(this, a2);
    }
    v5 = *((_DWORD *)this + 72);
    if ( v5 + *((_DWORD *)this + 86) < 0x104 && v5 >= 3 )
    {
      strcpy_s(Destination, 0x125u, *((const char **)this + 34));
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xF01FFu, 0, &TokenHandle) )
      {
        RevertToSelf();
      }
      else if ( GetLastError() != 1008 )
      {
        return 0;
      }
      DirectoryForSystemAndAdministrators = IISCreateDirectory(Destination, 1);
      if ( DirectoryForSystemAndAdministrators )
      {
        v8 = -1;
        do
          ++v8;
        while ( Destination[v8] );
        if ( *CharPrevA(Destination, &Destination[v8]) != 92 )
          strcat_s(Destination, 0x125u, "\\");
        strcat_s(Destination, 0x125u, *((const char **)this + 20));
        DirectoryForSystemAndAdministrators = CreateDirectoryForSystemAndAdministrators(Destination);
      }
      LastError = GetLastError();
      if ( TokenHandle )
      {
        SetThreadToken(0, TokenHandle);
        CloseHandle(TokenHandle);
        SetLastError(LastError);
      }
      if ( DirectoryForSystemAndAdministrators )
      {
        strcat_s(Destination, 0x125u, "\\");
        strcat_s(Destination, 0x125u, *((const char **)this + 41));
        v11 = operator new(0x78u);
        v12 = v11;
        if ( v11 )
        {
          *v11 = -1;
          v11[1] = 0;
          *((_DWORD *)v11 + 4) = 0;
          v11[3] = 0;
          *((_DWORD *)v11 + 8) = 0;
          STR::STR((STR *)(v11 + 8));
          v12[5] = 0;
          v12[7] = 0;
          memset(&SystemInfo, 0, sizeof(SystemInfo));
          GetSystemInfo(&SystemInfo);
          dwAllocationGranularity = SystemInfo.dwAllocationGranularity;
          *((_DWORD *)v12 + 5) = SystemInfo.dwAllocationGranularity;
          if ( !dwAllocationGranularity )
            *((_DWORD *)v12 + 5) = 0x10000;
          v14 = *((_DWORD *)this + 26);
          v15 = *((_DWORD *)this + 89) == 0;
          *((_QWORD *)this + 7) = v12;
          v16 = ILOG_FILE::Open((ILOG_FILE *)v12, Destination, v14, v15);
          v17 = (_QWORD *)*((_QWORD *)this + 7);
          if ( v16 )
          {
            *((_QWORD *)this + 12) = v17[5];
            return v3;
          }
          if ( v17 )
          {
            ILOG_FILE::CloseFile(*((ILOG_FILE **)this + 7));
            STR::~STR((STR *)(v17 + 8));
            operator delete(v17);
          }
        }
        *((_QWORD *)this + 7) = 0;
      }
      else if ( g_eventLog && !*((_DWORD *)this + 89) )
      {
        v20 = Destination;
        v10 = GetLastError();
        EVENT_LOG::LogEvent((EVENT_LOG *)g_eventLog, 0xC0000002, 1u, (const char **const)&v20, v10);
      }
      return 0;
    }
    v3 = 0;
    if ( g_eventLog && !*((_DWORD *)this + 89) )
    {
      v20 = Destination;
      EVENT_LOG::LogEvent((EVENT_LOG *)g_eventLog, 0xC0000002, 1u, (const char **const)&v20, 0xA1u);
    }
    SetLastError(0xA1u);
  }
  return v3;
}

```

## disassembly

```asm
0x180002c8c  mov     [rsp-8+arg_10], rbx
0x180002c91  mov     [rsp-8+arg_18], rsi
0x180002c96  push    rbp
0x180002c97  push    rdi
0x180002c98  push    r13
0x180002c9a  push    r14
0x180002c9c  push    r15
0x180002c9e  lea     rbp, [rsp-0B0h]
0x180002ca6  sub     rsp, 1B0h
0x180002cad  mov     rax, cs:__security_cookie
0x180002cb4  xor     rax, rsp
0x180002cb7  mov     [rbp+0D0h+var_30], rax
0x180002cbe  xor     r15d, r15d
0x180002cc1  mov     rbx, rcx
0x180002cc4  mov     esi, 1
0x180002cc9  mov     [rsp+1D0h+TokenHandle], r15
0x180002cce  cmp     [rcx+38h], r15
0x180002cd2  jnz     loc_180002F9E
0x180002cd8  cmp     [rcx+70h], r15d
0x180002cdc  jnz     short loc_180002CE4
0x180002cde  cmp     [rcx+6Ch], r15d
0x180002ce2  jz      short loc_180002CF4
0x180002ce4  mov     rax, [rcx]
0x180002ce7  mov     [rcx+70h], r15d
0x180002ceb  mov     rax, [rax+60h]
0x180002cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf4  mov     ecx, [rbx+158h]
0x180002cfa  mov     edx, [rbx+120h]
0x180002d00  add     ecx, edx
0x180002d02  cmp     ecx, 104h
0x180002d08  jnb     loc_180002F55
0x180002d0e  cmp     edx, 3
0x180002d11  jb      loc_180002F55
0x180002d17  mov     r8, [rbx+110h]; Source
0x180002d1e  lea     rcx, [rsp+1D0h+Destination]; Destination
0x180002d23  mov     r13d, 125h
0x180002d29  mov     edx, r13d; SizeInBytes
0x180002d2c  call    cs:__imp_strcpy_s
0x180002d32  call    cs:__imp_GetCurrentThread
0x180002d38  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x180002d3d  xor     r8d, r8d; OpenAsSelf
0x180002d40  mov     rcx, rax; ThreadHandle
0x180002d43  mov     edx, 0F01FFh; DesiredAccess
0x180002d48  call    cs:__imp_OpenThreadToken
0x180002d4e  test    eax, eax
0x180002d50  jnz     short loc_180002D67
0x180002d52  call    cs:__imp_GetLastError
0x180002d58  cmp     eax, 3F0h
0x180002d5d  jz      short loc_180002D6D
0x180002d5f  mov     esi, r15d
0x180002d62  jmp     loc_180002F9E
0x180002d67  call    cs:__imp_RevertToSelf
0x180002d6d  mov     edx, esi
0x180002d6f  lea     rcx, [rsp+1D0h+Destination]
0x180002d74  call    cs:__imp_?IISCreateDirectory@@YAHPEBDH@Z; IISCreateDirectory(char const *,int)
0x180002d7a  mov     edi, eax
0x180002d7c  test    eax, eax
0x180002d7e  jz      short loc_180002DE0
0x180002d80  lea     rcx, [rsp+1D0h+Destination]
0x180002d85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002d89  inc     rax
0x180002d8c  cmp     [rcx+rax], r15b
0x180002d90  jnz     short loc_180002D89
0x180002d92  lea     rdx, [rsp+1D0h+Destination]
0x180002d97  add     rdx, rax; lpszCurrent
0x180002d9a  lea     rcx, [rsp+1D0h+Destination]; lpszStart
0x180002d9f  call    cs:__imp_CharPrevA
0x180002da5  cmp     byte ptr [rax], 5Ch ; '\'
0x180002da8  jz      short loc_180002DBF
0x180002daa  lea     r8, asc_1800130D0; "\\"
0x180002db1  mov     rdx, r13; SizeInBytes
0x180002db4  lea     rcx, [rsp+1D0h+Destination]; Destination
0x180002db9  call    cs:__imp_strcat_s
0x180002dbf  mov     r8, [rbx+0A0h]; Source
0x180002dc6  lea     rcx, [rsp+1D0h+Destination]; Destination
0x180002dcb  mov     rdx, r13; SizeInBytes
0x180002dce  call    cs:__imp_strcat_s
0x180002dd4  lea     rcx, [rsp+1D0h+Destination]; lpPathName
0x180002dd9  call    ?CreateDirectoryForSystemAndAdministrators@@YAHPEBD@Z; CreateDirectoryForSystemAndAdministrators(char const *)
0x180002dde  mov     edi, eax
0x180002de0  call    cs:__imp_GetLastError
0x180002de6  mov     rdx, [rsp+1D0h+TokenHandle]; Token
0x180002deb  mov     r14d, eax
0x180002dee  test    rdx, rdx
0x180002df1  jz      short loc_180002E0F
0x180002df3  xor     ecx, ecx; Thread
0x180002df5  call    cs:__imp_SetThreadToken
0x180002dfb  mov     rcx, [rsp+1D0h+TokenHandle]; hObject
0x180002e00  call    cs:__imp_CloseHandle
0x180002e06  mov     ecx, r14d; dwErrCode
0x180002e09  call    cs:__imp_SetLastError
0x180002e0f  test    edi, edi
0x180002e11  jnz     short loc_180002E60
0x180002e13  cmp     cs:?g_eventLog@@3PEAVEVENT_LOG@@EA, r15; EVENT_LOG * g_eventLog
0x180002e1a  jz      loc_180002D5F
0x180002e20  cmp     [rbx+164h], r15d
0x180002e27  jnz     loc_180002D5F
0x180002e2d  lea     rax, [rsp+1D0h+Destination]
0x180002e32  mov     [rsp+1D0h+var_198], rax
0x180002e37  call    cs:__imp_GetLastError
0x180002e3d  mov     rcx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x180002e44  lea     r9, [rsp+1D0h+var_198]
0x180002e49  mov     r8d, esi
0x180002e4c  mov     [rsp+1D0h+var_1B0], eax
0x180002e50  mov     edx, 0C0000002h
0x180002e55  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z; EVENT_LOG::LogEvent(ulong,ushort,char const * * const,ulong)
0x180002e5b  jmp     loc_180002D5F
0x180002e60  lea     r8, asc_1800130D0; "\\"
0x180002e67  mov     rdx, r13; SizeInBytes
0x180002e6a  lea     rcx, [rsp+1D0h+Destination]; Destination
0x180002e6f  call    cs:__imp_strcat_s
0x180002e75  mov     r8, [rbx+148h]; Source
0x180002e7c  lea     rcx, [rsp+1D0h+Destination]; Destination
0x180002e81  mov     rdx, r13; SizeInBytes
0x180002e84  call    cs:__imp_strcat_s
0x180002e8a  mov     ecx, 78h ; 'x'; Size
0x180002e8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e94  mov     rdi, rax
0x180002e97  test    rax, rax
0x180002e9a  jz      loc_180002F4C
0x180002ea0  lea     rcx, [rax+40h]
0x180002ea4  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180002eab  mov     [rax+8], r15
0x180002eaf  mov     [rax+10h], r15d
0x180002eb3  mov     [rax+18h], r15
0x180002eb7  mov     [rax+20h], r15d
0x180002ebb  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180002ec1  xorps   xmm0, xmm0
0x180002ec4  mov     [rdi+28h], r15
0x180002ec8  lea     rcx, [rsp+1D0h+SystemInfo]; lpSystemInfo
0x180002ecd  mov     [rdi+38h], r15
0x180002ed1  movups  xmmword ptr [rsp+1D0h+SystemInfo], xmm0
0x180002ed6  movups  xmmword ptr [rsp+1D0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180002edb  movups  xmmword ptr [rsp+1D0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180002ee0  call    cs:__imp_GetSystemInfo
0x180002ee6  mov     eax, [rsp+1D0h+SystemInfo.dwAllocationGranularity]
0x180002eea  mov     [rdi+14h], eax
0x180002eed  test    eax, eax
0x180002eef  jnz     short loc_180002EF8
0x180002ef1  mov     dword ptr [rdi+14h], 10000h
0x180002ef8  cmp     [rbx+164h], r15d
0x180002eff  lea     rdx, [rsp+1D0h+Destination]; lpFileName
0x180002f04  mov     r8d, [rbx+68h]; unsigned int
0x180002f08  mov     r9d, r15d
0x180002f0b  setz    r9b; int
0x180002f0f  mov     [rbx+38h], rdi
0x180002f13  mov     rcx, rdi; this
0x180002f16  call    ?Open@ILOG_FILE@@QEAAHPEBDKH@Z; ILOG_FILE::Open(char const *,ulong,int)
0x180002f1b  mov     rdi, [rbx+38h]
0x180002f1f  test    eax, eax
0x180002f21  jz      short loc_180002F2D
0x180002f23  mov     rax, [rdi+28h]
0x180002f27  mov     [rbx+60h], rax
0x180002f2b  jmp     short loc_180002F9E
0x180002f2d  test    rdi, rdi
0x180002f30  jz      short loc_180002F4C
0x180002f32  mov     rcx, rdi; this
0x180002f35  call    ?CloseFile@ILOG_FILE@@QEAAHXZ; ILOG_FILE::CloseFile(void)
0x180002f3a  lea     rcx, [rdi+40h]
0x180002f3e  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180002f44  mov     rcx, rdi; Block
0x180002f47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f4c  mov     [rbx+38h], r15
0x180002f50  jmp     loc_180002D5F
0x180002f55  mov     rcx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x180002f5c  mov     esi, r15d
0x180002f5f  mov     edi, 0A1h
0x180002f64  test    rcx, rcx
0x180002f67  jz      short loc_180002F96
0x180002f69  cmp     [rbx+164h], r15d
0x180002f70  jnz     short loc_180002F96
0x180002f72  lea     rax, [rsp+1D0h+Destination]
0x180002f77  mov     [rsp+1D0h+var_1B0], edi
0x180002f7b  mov     r8d, 1
0x180002f81  mov     [rsp+1D0h+var_198], rax
0x180002f86  lea     r9, [rsp+1D0h+var_198]
0x180002f8b  mov     edx, 0C0000002h
0x180002f90  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z; EVENT_LOG::LogEvent(ulong,ushort,char const * * const,ulong)
0x180002f96  mov     ecx, edi; dwErrCode
0x180002f98  call    cs:__imp_SetLastError
0x180002f9e  mov     eax, esi
0x180002fa0  mov     rcx, [rbp+0D0h+var_30]
0x180002fa7  xor     rcx, rsp; StackCookie
0x180002faa  call    __security_check_cookie
0x180002faf  lea     r11, [rsp+1D0h+var_20]
0x180002fb7  mov     rbx, [r11+40h]
0x180002fbb  mov     rsi, [r11+48h]
0x180002fbf  mov     rsp, r11
0x180002fc2  pop     r15
0x180002fc4  pop     r14
0x180002fc6  pop     r13
0x180002fc8  pop     rdi
0x180002fc9  pop     rbp
0x180002fca  retn
```
