# EnterpriseDataProtection::CreateEDPCleanupProcess(ActivityContext *,ushort const *,ushort const *,ulong,_PROCESS_INFORMATION *)

- ea: `0x18001796c`
- end: `0x180017bf6`
- name: `?CreateEDPCleanupProcess@EnterpriseDataProtection@@AEAAJPEAVActivityContext@@PEBG1KPEAU_PROCESS_INFORMATION@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(EnterpriseDataProtection *this, struct ActivityContext *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006d4bc`
- `0x18006de08`

## callees

- `0x1800067a0`
- `0x180006950`
- `0x18000de50`
- `0x18000fb40`
- `0x18001796c`
- `0x180017de4`
- `0x180017fdc`
- `0x18001a86c`
- `0x18001ab40`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18006da50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017a40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017a51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180017b40`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180017b40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall EnterpriseDataProtection::CreateEDPCleanupProcess(
        EnterpriseDataProtection *this,
        struct ActivityContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct _PROCESS_INFORMATION *a6)
{
  int KeyAsString; // ebx
  __int64 v11; // rax
  unsigned int v12; // eax
  unsigned __int64 v13; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // rax
  WCHAR *v16; // rbx
  signed int EnrollmentType; // edi
  struct _GUID v18; // xmm6
  EnterpriseDataProtection *v19; // rcx
  DWORD dwCreationFlags; // eax
  signed int LastError; // eax
  CEnrollmentLogger *Logger; // rax
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v25; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v27; // [rsp+90h] [rbp-70h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v29[40]; // [rsp+110h] [rbp+10h] BYREF

  v24 = 63;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  if ( !a2 || !a3 || !a4 || a5 && a5 != 3 )
    return 2147942487LL;
  KeyAsString = ActivityContext::get_KeyAsString(a2, v29);
  if ( KeyAsString >= 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11;
    if ( v12 + 86 >= v12 )
    {
      v13 = v12 + 86;
      ProcessHeap = GetProcessHeap();
      v15 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v13);
      v16 = v15;
      v25 = v15;
      if ( v15 )
      {
        EnrollmentType = StringCchPrintfW(v15, v13 >> 1, L" %d %s", a5, a4);
        if ( EnrollmentType >= 0 )
        {
          v18 = *(struct _GUID *)((char *)a2 + 8);
          v27 = v18;
          EnrollmentType = EEDBManager::GetEnrollmentType(&v27, (enum EnrollmentEnrollType *)&v24);
          if ( EnrollmentType >= 0 )
          {
            hToken = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &hToken,
              0);
            EnrollmentType = EnterpriseDataProtection::GetTargetUserToken(v19, a2, &hToken);
            if ( EnrollmentType >= 0 )
            {
              dwCreationFlags = 0;
              StartupInfo.cb = 104;
              if ( v24 == 12 )
              {
                StartupInfo.lpDesktop = aWinsta0Default;
                dwCreationFlags = 0x1000000;
              }
              if ( CreateProcessAsUserW(
                     hToken,
                     a3,
                     v16,
                     0,
                     0,
                     0,
                     dwCreationFlags,
                     0,
                     0,
                     &StartupInfo,
                     &ProcessInformation) )
              {
                if ( a6 )
                {
                  *a6 = ProcessInformation;
                }
                else
                {
                  CloseHandle(ProcessInformation.hProcess);
                  CloseHandle(ProcessInformation.hThread);
                }
              }
              else
              {
                LastError = GetLastError();
                EnrollmentType = LastError;
                if ( LastError > 0 )
                  EnrollmentType = (unsigned __int16)LastError | 0x80070000;
                Logger = CEnrollmentLogger::GetLogger();
                v27 = v18;
                CEnrollmentLogger::LogEnterpriseDataProtectionCreateProcessAsUserFail(Logger, EnrollmentType, &v27, a5);
              }
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
          }
        }
      }
      else
      {
        EnrollmentType = -2147024882;
      }
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v25);
      return (unsigned int)EnrollmentType;
    }
    else
    {
      return 2147942934LL;
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return (unsigned int)KeyAsString;
  }
}

```

## disassembly

```asm
0x18001796c  mov     rax, rsp
0x18001796f  push    rbp
0x180017970  push    rbx
0x180017971  push    rdi
0x180017972  push    r12
0x180017974  push    r13
0x180017976  push    r14
0x180017978  push    r15
0x18001797a  lea     rbp, [rsp-80h]
0x18001797f  sub     rsp, 180h
0x180017986  movaps  xmmword ptr [rax-48h], xmm6
0x18001798a  mov     rax, cs:__security_cookie
0x180017991  xor     rax, rsp
0x180017994  mov     [rbp+0B0h+var_50], rax
0x180017998  mov     r12, r9
0x18001799b  mov     r13, r8
0x18001799e  mov     r15, rdx
0x1800179a1  mov     r14, [rbp+0B0h+arg_28]
0x1800179a8  mov     [rsp+1B0h+var_148], 3Fh ; '?'
0x1800179b0  xorps   xmm0, xmm0
0x1800179b3  xor     eax, eax
0x1800179b5  movups  xmmword ptr [rsp+1B0h+ProcessInformation.hProcess], xmm0
0x1800179ba  mov     qword ptr [rbp+0B0h+ProcessInformation.dwProcessId], rax
0x1800179be  xor     edx, edx; Val
0x1800179c0  lea     r8d, [rax+68h]; Size
0x1800179c4  lea     rcx, [rbp+0B0h+StartupInfo]; void *
0x1800179c8  call    memset_0
0x1800179cd  xor     edi, edi
0x1800179cf  test    r15, r15
0x1800179d2  jz      loc_180017BCA
0x1800179d8  test    r13, r13
0x1800179db  jz      loc_180017BCA
0x1800179e1  test    r12, r12
0x1800179e4  jz      loc_180017BCA
0x1800179ea  cmp     [rbp+0B0h+arg_20], edi
0x1800179f0  jz      short loc_1800179FF
0x1800179f2  cmp     [rbp+0B0h+arg_20], 3
0x1800179f9  jnz     loc_180017BCA
0x1800179ff  lea     rdx, [rbp+0B0h+var_A0]; unsigned __int16 *
0x180017a03  mov     rcx, r15; this
0x180017a06  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180017a0b  mov     ebx, eax
0x180017a0d  test    eax, eax
0x180017a0f  jns     short loc_180017A1D
0x180017a11  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x180017a16  mov     eax, ebx
0x180017a18  jmp     loc_180017BCF
0x180017a1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017a21  inc     rax
0x180017a24  cmp     [r12+rax*2], di
0x180017a29  jnz     short loc_180017A21
0x180017a2b  add     eax, eax
0x180017a2d  lea     ecx, [rax+56h]
0x180017a30  cmp     ecx, eax
0x180017a32  jnb     short loc_180017A3E
0x180017a34  mov     eax, 80070216h
0x180017a39  jmp     loc_180017BCF
0x180017a3e  mov     edi, ecx
0x180017a40  call    cs:__imp_GetProcessHeap
0x180017a46  mov     r8d, edi; dwBytes
0x180017a49  mov     edx, 8; dwFlags
0x180017a4e  mov     rcx, rax; hHeap
0x180017a51  call    cs:__imp_HeapAlloc
0x180017a57  mov     rbx, rax
0x180017a5a  mov     [rsp+1B0h+var_140], rax
0x180017a5f  test    rax, rax
0x180017a62  jnz     short loc_180017A6E
0x180017a64  mov     edi, 8007000Eh
0x180017a69  jmp     loc_180017B8A
0x180017a6e  shr     rdi, 1
0x180017a71  mov     [rsp+1B0h+lpThreadAttributes], r12
0x180017a76  mov     r9d, [rbp+0B0h+arg_20]
0x180017a7d  lea     r8, aDS; " %d %s"
0x180017a84  mov     rdx, rdi; unsigned __int64
0x180017a87  mov     rcx, rbx; unsigned __int16 *
0x180017a8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017a8f  mov     edi, eax
0x180017a91  xor     r12d, r12d
0x180017a94  test    eax, eax
0x180017a96  js      loc_180017B8A
0x180017a9c  movups  xmm6, xmmword ptr [r15+8]
0x180017aa1  movdqu  xmmword ptr [rbp+0B0h+var_120.Data1], xmm6
0x180017aa6  lea     rdx, [rsp+1B0h+var_148]; enum EnrollmentEnrollType *
0x180017aab  lea     rcx, [rbp+0B0h+var_120]; struct _GUID
0x180017aaf  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x180017ab4  mov     edi, eax
0x180017ab6  test    eax, eax
0x180017ab8  js      loc_180017B8A
0x180017abe  mov     [rsp+1B0h+hToken], r12
0x180017ac3  xor     edx, edx
0x180017ac5  lea     rcx, [rsp+1B0h+hToken]
0x180017aca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180017acf  lea     r8, [rsp+1B0h+hToken]; void **
0x180017ad4  mov     rdx, r15; struct ActivityContext *
0x180017ad7  call    ?GetTargetUserToken@EnterpriseDataProtection@@AEAAJPEAVActivityContext@@PEAPEAX@Z; EnterpriseDataProtection::GetTargetUserToken(ActivityContext *,void * *)
0x180017adc  mov     edi, eax
0x180017ade  test    eax, eax
0x180017ae0  js      loc_180017B7F
0x180017ae6  mov     eax, r12d
0x180017ae9  mov     [rbp+0B0h+StartupInfo.cb], 68h ; 'h'
0x180017af0  cmp     [rsp+1B0h+var_148], 0Ch
0x180017af5  jnz     short loc_180017B07
0x180017af7  lea     rax, aWinsta0Default; "winsta0\\default"
0x180017afe  mov     [rbp+0B0h+StartupInfo.lpDesktop], rax
0x180017b02  mov     eax, 1000000h
0x180017b07  lea     rcx, [rsp+1B0h+ProcessInformation]
0x180017b0c  mov     [rsp+1B0h+lpProcessInformation], rcx; lpProcessInformation
0x180017b11  lea     rcx, [rbp+0B0h+StartupInfo]
0x180017b15  mov     [rsp+1B0h+lpStartupInfo], rcx; lpStartupInfo
0x180017b1a  mov     [rsp+1B0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180017b1f  mov     [rsp+1B0h+lpEnvironment], r12; lpEnvironment
0x180017b24  mov     [rsp+1B0h+dwCreationFlags], eax; dwCreationFlags
0x180017b28  mov     [rsp+1B0h+bInheritHandles], r12d; bInheritHandles
0x180017b2d  mov     [rsp+1B0h+lpThreadAttributes], r12; lpThreadAttributes
0x180017b32  xor     r9d, r9d; lpProcessAttributes
0x180017b35  mov     r8, rbx; lpCommandLine
0x180017b38  mov     rdx, r13; lpApplicationName
0x180017b3b  mov     rcx, [rsp+1B0h+hToken]; hToken
0x180017b40  call    cs:__imp_CreateProcessAsUserW
0x180017b46  test    eax, eax
0x180017b48  jnz     short loc_180017B98
0x180017b4a  call    cs:__imp_GetLastError
0x180017b50  mov     edi, eax
0x180017b52  test    eax, eax
0x180017b54  jle     short loc_180017B5F
0x180017b56  movzx   edi, ax
0x180017b59  or      edi, 80070000h
0x180017b5f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180017b64  movdqa  xmmword ptr [rbp+0B0h+var_120.Data1], xmm6
0x180017b69  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x180017b70  lea     r8, [rbp+0B0h+var_120]; struct _GUID
0x180017b74  mov     edx, edi; int
0x180017b76  mov     rcx, rax; this
0x180017b79  call    ?LogEnterpriseDataProtectionCreateProcessAsUserFail@CEnrollmentLogger@@QEAAXJU_GUID@@K@Z; CEnrollmentLogger::LogEnterpriseDataProtectionCreateProcessAsUserFail(long,_GUID,ulong)
0x180017b7e  nop
0x180017b7f  lea     rcx, [rsp+1B0h+hToken]
0x180017b84  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017b89  nop
0x180017b8a  lea     rcx, [rsp+1B0h+var_140]
0x180017b8f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180017b94  mov     eax, edi
0x180017b96  jmp     short loc_180017BCF
0x180017b98  test    r14, r14
0x180017b9b  jz      short loc_180017BB3
0x180017b9d  movups  xmm0, xmmword ptr [rsp+1B0h+ProcessInformation.hProcess]
0x180017ba2  movups  xmmword ptr [r14], xmm0
0x180017ba6  movsd   xmm1, qword ptr [rbp+0B0h+ProcessInformation.dwProcessId]
0x180017bab  movsd   qword ptr [r14+10h], xmm1
0x180017bb1  jmp     short loc_180017B7F
0x180017bb3  mov     rcx, [rsp+1B0h+ProcessInformation.hProcess]; hObject
0x180017bb8  call    cs:__imp_CloseHandle
0x180017bbe  mov     rcx, [rbp+0B0h+ProcessInformation.hThread]; hObject
0x180017bc2  call    cs:__imp_CloseHandle
0x180017bc8  jmp     short loc_180017B7F
0x180017bca  mov     eax, 80070057h
0x180017bcf  mov     rcx, [rbp+0B0h+var_50]
0x180017bd3  xor     rcx, rsp; StackCookie
0x180017bd6  call    __security_check_cookie
0x180017bdb  movaps  xmm6, [rsp+1B0h+var_40]
0x180017be3  add     rsp, 180h
0x180017bea  pop     r15
0x180017bec  pop     r14
0x180017bee  pop     r13
0x180017bf0  pop     r12
0x180017bf2  pop     rdi
0x180017bf3  pop     rbx
0x180017bf4  pop     rbp
0x180017bf5  retn
```
