# LaunchDeviceEnrollerForToast(ushort const *)

- ea: `0x1800665d4`
- end: `0x180066902`
- name: `?LaunchDeviceEnrollerForToast@@YAJPEBG@Z`
- size: `814`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800661c0`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000bef4`
- `0x18000d4d4`
- `0x18000db4c`
- `0x180025a78`
- `0x180025cec`
- `0x18002dc38`
- `0x18004568c`
- `0x180048624`
- `0x1800665d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800666d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800666d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800666bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800666bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180066755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180066755`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180066841`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180066841`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180066772`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180066772`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066624`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066624`
- `DMCmnUtils!DmImpersonate` at `0x18006668d`
- `DMCmnUtils!DmImpersonate` at `0x18006668d`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006666f`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18006666f`
- `DMCmnUtils!DmRevertToSelf` at `0x18006672c`
- `DMCmnUtils!DmRevertToSelf` at `0x1800667b5`
- `DMCmnUtils!DmRevertToSelf` at `0x18006688e`
- `DMCmnUtils!DmRevertToSelf` at `0x1800668c2`
- `DMCmnUtils!DmRevertToSelf` at `0x18006672c`
- `DMCmnUtils!DmRevertToSelf` at `0x1800667b5`
- `DMCmnUtils!DmRevertToSelf` at `0x18006688e`
- `DMCmnUtils!DmRevertToSelf` at `0x1800668c2`

## string_xrefs

- `0x18006661d`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall LaunchDeviceEnrollerForToast(const unsigned __int16 *a1)
{
  signed int result; // eax
  int ActiveUserSid; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  HANDLE CurrentThread; // rax
  signed int v11; // eax
  struct _PROCESS_INFORMATION *v12; // rdx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION *v14; // rdx
  int lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Dst[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
  {
    v17 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v17,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v17);
    v4 = ActiveUserSid;
    if ( ActiveUserSid >= 0 )
    {
      ActiveUserSid = DmImpersonate(v17);
      v4 = ActiveUserSid;
      if ( ActiveUserSid >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x7Eu);
        v8 = StringCchPrintfW(v7, 0x3Fu, L"-RemoteFindToastLaunch -o %s", a1);
        v9 = v8;
        if ( v8 >= 0 )
        {
          TokenHandle = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &TokenHandle,
            0);
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0xBu, 1, &TokenHandle) )
          {
            memset(&ProcessInformation, 0, sizeof(ProcessInformation));
            memset_0(&StartupInfo, 0, sizeof(StartupInfo));
            StartupInfo.cb = 104;
            StartupInfo.lpDesktop = L"WinSta0\\Default";
            if ( CreateProcessAsUserW(
                   TokenHandle,
                   Dst,
                   v7,
                   0,
                   0,
                   0,
                   0x1000000u,
                   0,
                   0,
                   &StartupInfo,
                   &ProcessInformation) )
            {
              wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v12);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
              if ( v7 )
                MemoryFree(v7);
              DmRevertToSelf();
              v4 = 0;
              goto LABEL_29;
            }
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
            wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v14);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            if ( v7 )
              MemoryFree(v7);
          }
          else
          {
            v11 = GetLastError();
            v9 = v11;
            if ( v11 > 0 )
              v9 = (unsigned __int16)v11 | 0x80070000;
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            if ( v7 )
              MemoryFree(v7);
          }
          DmRevertToSelf();
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x33,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\remotefind\\getvalue.cpp",
            (const char *)(unsigned int)v8,
            lpThreadAttributes);
          if ( v7 )
            MemoryFree(v7);
          DmRevertToSelf();
        }
        v4 = v9;
LABEL_29:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
        return v4;
      }
      v5 = 43;
    }
    else
    {
      v5 = 42;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\remotefind\\getvalue.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      lpThreadAttributes);
    goto LABEL_29;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800665d4  mov     [rsp-8+arg_8], rbx
0x1800665d9  mov     [rsp-8+arg_10], rdi
0x1800665de  push    rbp
0x1800665df  lea     rbp, [rsp-220h]
0x1800665e7  sub     rsp, 320h
0x1800665ee  mov     rax, cs:__security_cookie
0x1800665f5  xor     rax, rsp
0x1800665f8  mov     [rbp+220h+var_10], rax
0x1800665ff  mov     rdi, rcx
0x180066602  xor     edx, edx; Val
0x180066604  mov     r8d, 208h; Size
0x18006660a  lea     rcx, [rbp+220h+Dst]; void *
0x18006660e  call    memset_0
0x180066613  mov     r8d, 104h; nSize
0x180066619  lea     rdx, [rbp+220h+Dst]; lpDst
0x18006661d  lea     rcx, Src; "%windir%\\system32\\deviceenroller.exe"
0x180066624  call    cs:__imp_ExpandEnvironmentStringsW
0x18006662b  nop     dword ptr [rax+rax+00h]
0x180066630  test    eax, eax
0x180066632  jnz     short loc_180066655
0x180066634  call    cs:__imp_GetLastError
0x18006663b  nop     dword ptr [rax+rax+00h]
0x180066640  test    eax, eax
0x180066642  jle     loc_1800668DD
0x180066648  movzx   eax, ax
0x18006664b  or      eax, 80070000h
0x180066650  jmp     loc_1800668DD
0x180066655  mov     [rsp+320h+var_2B8], 0
0x18006665e  xor     edx, edx
0x180066660  lea     rcx, [rsp+320h+var_2B8]
0x180066665  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006666a  lea     rcx, [rsp+320h+var_2B8]
0x18006666f  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180066676  nop     dword ptr [rax+rax+00h]
0x18006667b  mov     ebx, eax
0x18006667d  test    eax, eax
0x18006667f  jns     short loc_180066688
0x180066681  mov     edx, 2Ah ; '*'
0x180066686  jmp     short loc_1800666A4
0x180066688  mov     rcx, [rsp+320h+var_2B8]
0x18006668d  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180066694  nop     dword ptr [rax+rax+00h]
0x180066699  mov     ebx, eax
0x18006669b  test    eax, eax
0x18006669d  jns     short loc_1800666BF
0x18006669f  mov     edx, 2Bh ; '+'; void *
0x1800666a4  lea     r8, aOnecoreuapAdmi_101; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800666ab  mov     r9d, eax; char *
0x1800666ae  mov     rcx, [rbp+228h]; this
0x1800666b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800666ba  jmp     loc_1800668D1
0x1800666bf  call    cs:__imp_GetProcessHeap
0x1800666c6  nop     dword ptr [rax+rax+00h]
0x1800666cb  mov     rcx, rax; hHeap
0x1800666ce  mov     edx, 8; dwFlags
0x1800666d3  lea     r8d, [rdx+76h]; dwBytes
0x1800666d7  call    cs:__imp_HeapAlloc
0x1800666de  nop     dword ptr [rax+rax+00h]
0x1800666e3  mov     rbx, rax
0x1800666e6  mov     r9, rdi
0x1800666e9  lea     r8, aRemotefindtoas; "-RemoteFindToastLaunch -o %s"
0x1800666f0  mov     edx, 3Fh ; '?'; unsigned __int64
0x1800666f5  mov     rcx, rax; unsigned __int16 *
0x1800666f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800666fd  mov     edi, eax
0x1800666ff  test    eax, eax
0x180066701  jns     short loc_180066740
0x180066703  mov     rcx, [rbp+228h]; this
0x18006670a  mov     r9d, eax; char *
0x18006670d  lea     r8, aOnecoreuapAdmi_101; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180066714  mov     edx, 33h ; '3'; void *
0x180066719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006671e  test    rbx, rbx
0x180066721  jz      short loc_18006672C
0x180066723  mov     rcx, rbx; void *
0x180066726  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006672b  nop
0x18006672c  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180066733  nop     dword ptr [rax+rax+00h]
0x180066738  nop
0x180066739  mov     ebx, edi
0x18006673b  jmp     loc_1800668D1
0x180066740  mov     [rsp+320h+TokenHandle], 0
0x180066749  xor     edx, edx
0x18006674b  lea     rcx, [rsp+320h+TokenHandle]
0x180066750  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180066755  call    cs:__imp_GetCurrentThread
0x18006675c  nop     dword ptr [rax+rax+00h]
0x180066761  lea     r9, [rsp+320h+TokenHandle]; TokenHandle
0x180066766  mov     edx, 0Bh; DesiredAccess
0x18006676b  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x18006676f  mov     rcx, rax; ThreadHandle
0x180066772  call    cs:__imp_OpenThreadToken
0x180066779  nop     dword ptr [rax+rax+00h]
0x18006677e  test    eax, eax
0x180066780  jnz     short loc_1800667C7
0x180066782  call    cs:__imp_GetLastError
0x180066789  nop     dword ptr [rax+rax+00h]
0x18006678e  mov     edi, eax
0x180066790  test    eax, eax
0x180066792  jle     short loc_18006679D
0x180066794  movzx   edi, ax
0x180066797  or      edi, 80070000h
0x18006679d  lea     rcx, [rsp+320h+TokenHandle]
0x1800667a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800667a7  test    rbx, rbx
0x1800667aa  jz      short loc_1800667B5
0x1800667ac  mov     rcx, rbx; void *
0x1800667af  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800667b4  nop
0x1800667b5  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800667bc  nop     dword ptr [rax+rax+00h]
0x1800667c1  nop
0x1800667c2  jmp     loc_180066739
0x1800667c7  xorps   xmm0, xmm0
0x1800667ca  xor     eax, eax
0x1800667cc  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x1800667d1  mov     qword ptr [rbp+220h+ProcessInformation.dwProcessId], rax
0x1800667d5  lea     edi, [rax+68h]
0x1800667d8  mov     r8d, edi; Size
0x1800667db  xor     edx, edx; Val
0x1800667dd  lea     rcx, [rbp+220h+StartupInfo]; void *
0x1800667e1  call    memset_0
0x1800667e6  mov     [rbp+220h+StartupInfo.cb], edi
0x1800667e9  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x1800667f0  mov     [rbp+220h+StartupInfo.lpDesktop], rax
0x1800667f4  lea     rax, [rsp+320h+ProcessInformation]
0x1800667f9  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x1800667fe  lea     rax, [rbp+220h+StartupInfo]
0x180066802  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x180066807  mov     [rsp+320h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180066810  mov     [rsp+320h+lpEnvironment], 0; lpEnvironment
0x180066819  mov     [rsp+320h+dwCreationFlags], 1000000h; dwCreationFlags
0x180066821  mov     [rsp+320h+bInheritHandles], 0; bInheritHandles
0x180066829  mov     [rsp+320h+lpThreadAttributes], 0; lpThreadAttributes
0x180066832  xor     r9d, r9d; lpProcessAttributes
0x180066835  mov     r8, rbx; lpCommandLine
0x180066838  lea     rdx, [rbp+220h+Dst]; lpApplicationName
0x18006683c  mov     rcx, [rsp+320h+TokenHandle]; hToken
0x180066841  call    cs:__imp_CreateProcessAsUserW
0x180066848  nop     dword ptr [rax+rax+00h]
0x18006684d  test    eax, eax
0x18006684f  jnz     short loc_1800668A0
0x180066851  call    cs:__imp_GetLastError
0x180066858  nop     dword ptr [rax+rax+00h]
0x18006685d  mov     edi, eax
0x18006685f  test    eax, eax
0x180066861  jle     short loc_18006686C
0x180066863  movzx   edi, ax
0x180066866  or      edi, 80070000h
0x18006686c  lea     rcx, [rsp+320h+ProcessInformation]; this
0x180066871  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180066876  lea     rcx, [rsp+320h+TokenHandle]
0x18006687b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180066880  test    rbx, rbx
0x180066883  jz      short loc_18006688E
0x180066885  mov     rcx, rbx; void *
0x180066888  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006688d  nop
0x18006688e  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180066895  nop     dword ptr [rax+rax+00h]
0x18006689a  nop
0x18006689b  jmp     loc_180066739
0x1800668a0  lea     rcx, [rsp+320h+ProcessInformation]; this
0x1800668a5  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1800668aa  lea     rcx, [rsp+320h+TokenHandle]
0x1800668af  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800668b4  test    rbx, rbx
0x1800668b7  jz      short loc_1800668C2
0x1800668b9  mov     rcx, rbx; void *
0x1800668bc  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800668c1  nop
0x1800668c2  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800668c9  nop     dword ptr [rax+rax+00h]
0x1800668ce  nop
0x1800668cf  xor     ebx, ebx
0x1800668d1  lea     rcx, [rsp+320h+var_2B8]
0x1800668d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800668db  mov     eax, ebx
0x1800668dd  mov     rcx, [rbp+220h+var_10]
0x1800668e4  xor     rcx, rsp; StackCookie
0x1800668e7  call    __security_check_cookie
0x1800668ec  lea     r11, [rsp+320h+var_s0]
0x1800668f4  mov     rbx, [r11+18h]
0x1800668f8  mov     rdi, [r11+20h]
0x1800668fc  mov     rsp, r11
0x1800668ff  pop     rbp
0x180066900  retn
```
