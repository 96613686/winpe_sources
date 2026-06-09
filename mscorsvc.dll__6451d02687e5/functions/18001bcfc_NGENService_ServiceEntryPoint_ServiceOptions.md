# NGENService::ServiceEntryPoint(_ServiceOptions *)

- ea: `0x18001bcfc`
- end: `0x18001bf05`
- name: `?ServiceEntryPoint@NGENService@@YAJPEAU_ServiceOptions@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(NGENService *__hidden this, struct _ServiceOptions *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800085b0`

## callees

- `0x180006680`
- `0x18000798c`
- `0x18001a3a0`
- `0x18001b340`
- `0x18001b57c`
- `0x18001bcfc`
- `0x180030d84`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18001bef0`
- `KERNEL32!TerminateProcess` at `0x18001bef0`
- `KERNEL32!GetCurrentProcess` at `0x18001bee5`
- `KERNEL32!GetCurrentProcess` at `0x18001bee5`
- `KERNEL32!SetEnvironmentVariableW` at `0x18001bdca`
- `KERNEL32!SetEnvironmentVariableW` at `0x18001bdef`
- `KERNEL32!SetEnvironmentVariableW` at `0x18001bdca`
- `KERNEL32!SetEnvironmentVariableW` at `0x18001bdef`
- `KERNEL32!GetLastError` at `0x18001be6d`
- `KERNEL32!GetLastError` at `0x18001be6d`
- `KERNEL32!HeapFree` at `0x18001be30`
- `KERNEL32!HeapFree` at `0x18001beb6`
- `KERNEL32!HeapFree` at `0x18001be30`
- `KERNEL32!HeapFree` at `0x18001beb6`
- `KERNEL32!GetProcessHeap` at `0x18001be1b`
- `KERNEL32!GetProcessHeap` at `0x18001bea1`
- `KERNEL32!GetProcessHeap` at `0x18001be1b`
- `KERNEL32!GetProcessHeap` at `0x18001bea1`

## string_xrefs

- `0x18001bdc3`: `COMPLUS_DEFAULTVERSION`
- `0x18001bde8`: `COMPLUS_VERSION`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NGENService::ServiceEntryPoint(NGENService *this, struct _ServiceOptions *a2, bool a3)
{
  NGENService *v3; // rcx
  WCHAR *v4; // rbx
  HANDLE v5; // rax
  unsigned __int16 **v6; // r8
  signed int LastError; // ecx
  __int64 result; // rax
  WCHAR *v9; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE CurrentProcess; // rax
  _SERVICE_TABLE_ENTRYW v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+38h] [rbp-C8h]
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+44h] [rbp-BCh]
  LPCWSTR lpValue; // [rsp+50h] [rbp-B0h]
  __int16 v18; // [rsp+58h] [rbp-A8h] BYREF

  v12.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)NGENService::ServiceMain;
  v13 = 0;
  v14 = 0;
  NGENService::g_Options = *(_QWORD *)this;
  dword_18006FC10 = *((_DWORD *)this + 2);
  NGENService::g_bProcessNGENService = 1;
  if ( (int)NGENService::GenerateServiceName((NGENService *)&NGENService::g_sServiceName, 0, a3) < 0 )
    return 2147500037LL;
  if ( !*(&NGENService::g_Options + 1) )
    goto LABEL_10;
  v16 = 512;
  lpValue = (LPCWSTR)&v18;
  v15 = 2;
  v18 = 0;
  Helpers::GetVersionDirectoryFromCurrentModulePath((struct SString *)&v15);
  SString::ConvertToUnicode((SString *)&v15);
  if ( !SetEnvironmentVariableW(L"COMPLUS_DEFAULTVERSION", lpValue)
    || (SString::ConvertToUnicode((SString *)&v15), !SetEnvironmentVariableW(L"COMPLUS_VERSION", lpValue)) )
  {
    if ( (v16 & 0x800000000LL) != 0 )
    {
      v9 = (WCHAR *)lpValue;
      if ( lpValue )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v9);
      }
    }
    return 2147500037LL;
  }
  if ( (v16 & 0x800000000LL) != 0 )
  {
    v4 = (WCHAR *)lpValue;
    if ( lpValue )
    {
      v5 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v5 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v5;
      }
      HeapFree(v5, 0, v4);
    }
  }
LABEL_10:
  NGENService::ServiceExtraInstallSteps(v3);
  SString::ConvertToUnicode((SString *)&NGENService::g_sServiceName);
  v12.lpServiceName = lpMem;
  if ( !NGENService::g_Options )
  {
    NGENService::ServiceMain(0, 0, v6);
    return 0;
  }
  if ( (unsigned int)CLRStartServiceCtrlDispatcher(&v12) )
  {
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 0);
    return 0;
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x18001bcfc  mov     [rsp-8+arg_0], rbx
0x18001bd01  mov     [rsp-8+arg_8], rdi
0x18001bd06  push    rbp
0x18001bd07  lea     rbp, [rsp-170h]
0x18001bd0f  sub     rsp, 270h
0x18001bd16  mov     rax, cs:__security_cookie
0x18001bd1d  xor     rax, rsp
0x18001bd20  mov     [rbp+170h+var_10], rax
0x18001bd27  lea     rax, ?ServiceMain@NGENService@@YAXKPEAPEAG@Z; NGENService::ServiceMain(ulong,ushort * *)
0x18001bd2e  mov     [rsp+270h+var_250.lpServiceProc], rax
0x18001bd33  xor     edi, edi
0x18001bd35  mov     [rsp+270h+var_240], rdi
0x18001bd3a  mov     [rsp+270h+var_238], rdi
0x18001bd3f  movsd   xmm0, qword ptr [rcx]
0x18001bd43  movsd   cs:?g_Options@NGENService@@3U_ServiceOptions@@A, xmm0; _ServiceOptions NGENService::g_Options
0x18001bd4b  mov     eax, [rcx+8]
0x18001bd4e  mov     cs:dword_18006FC10, eax
0x18001bd54  mov     cs:?g_bProcessNGENService@NGENService@@3_NA, 1; bool NGENService::g_bProcessNGENService
0x18001bd5b  xor     edx, edx; struct SString *
0x18001bd5d  lea     rcx, ?g_sServiceName@NGENService@@3VSString@@A; this
0x18001bd64  call    ?GenerateServiceName@NGENService@@YAJAEAVSString@@_N@Z; NGENService::GenerateServiceName(SString &,bool)
0x18001bd69  test    eax, eax
0x18001bd6b  js      loc_18001BEBC
0x18001bd71  cmp     dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A+4, edi; _ServiceOptions NGENService::g_Options
0x18001bd77  jz      loc_18001BE36
0x18001bd7d  mov     [rsp+270h+var_230], rdi
0x18001bd82  mov     [rsp+270h+var_230+4], 200h
0x18001bd8b  mov     [rsp+270h+lpValue], rdi
0x18001bd90  lea     rax, [rsp+270h+var_218]
0x18001bd95  mov     [rsp+270h+lpValue], rax
0x18001bd9a  mov     dword ptr [rsp+270h+var_230], 2
0x18001bda2  mov     rax, [rsp+270h+lpValue]
0x18001bda7  mov     [rax], di
0x18001bdaa  lea     rcx, [rsp+270h+var_230]; this
0x18001bdaf  call    ?GetVersionDirectoryFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryFromCurrentModulePath(SString &)
0x18001bdb4  lea     rcx, [rsp+270h+var_230]; this
0x18001bdb9  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001bdbe  mov     rdx, [rsp+270h+lpValue]; lpValue
0x18001bdc3  lea     rcx, Name; "COMPLUS_DEFAULTVERSION"
0x18001bdca  call    cs:__imp_SetEnvironmentVariableW
0x18001bdd0  cmp     eax, 1
0x18001bdd3  jnz     loc_18001BE84
0x18001bdd9  lea     rcx, [rsp+270h+var_230]; this
0x18001bdde  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001bde3  mov     rdx, [rsp+270h+lpValue]; lpValue
0x18001bde8  lea     rcx, aComplusVersion; "COMPLUS_VERSION"
0x18001bdef  call    cs:__imp_SetEnvironmentVariableW
0x18001bdf5  cmp     eax, 1
0x18001bdf8  jnz     loc_18001BE84
0x18001bdfe  test    [rsp+270h+var_228], 8
0x18001be03  jz      short loc_18001BE36
0x18001be05  mov     rbx, [rsp+270h+lpValue]
0x18001be0a  test    rbx, rbx
0x18001be0d  jz      short loc_18001BE36
0x18001be0f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001be16  test    rax, rax
0x18001be19  jnz     short loc_18001BE28
0x18001be1b  call    cs:__imp_GetProcessHeap
0x18001be21  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001be28  mov     r8, rbx; lpMem
0x18001be2b  xor     edx, edx; dwFlags
0x18001be2d  mov     rcx, rax; hHeap
0x18001be30  call    cs:__imp_HeapFree
0x18001be36  call    ?ServiceExtraInstallSteps@NGENService@@YAJXZ; NGENService::ServiceExtraInstallSteps(void)
0x18001be3b  lea     rcx, ?g_sServiceName@NGENService@@3VSString@@A; this
0x18001be42  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001be47  mov     rax, cs:lpMem
0x18001be4e  mov     [rsp+270h+var_250.lpServiceName], rax
0x18001be53  cmp     dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A, edi; _ServiceOptions NGENService::g_Options
0x18001be59  jz      loc_18001BEF8
0x18001be5f  lea     rcx, [rsp+270h+var_250]; struct _SERVICE_TABLE_ENTRYW *
0x18001be64  call    ?CLRStartServiceCtrlDispatcher@@YAHQEAU_SERVICE_TABLE_ENTRYW@@@Z; CLRStartServiceCtrlDispatcher(_SERVICE_TABLE_ENTRYW * const)
0x18001be69  test    eax, eax
0x18001be6b  jnz     short loc_18001BEE5
0x18001be6d  call    cs:__imp_GetLastError
0x18001be73  mov     ecx, eax
0x18001be75  movzx   eax, ax
0x18001be78  or      eax, 80070000h
0x18001be7d  test    ecx, ecx
0x18001be7f  cmovle  eax, ecx
0x18001be82  jmp     short loc_18001BEC1
0x18001be84  test    [rsp+270h+var_228], 8
0x18001be89  jz      short loc_18001BEBC
0x18001be8b  mov     rbx, [rsp+270h+lpValue]
0x18001be90  test    rbx, rbx
0x18001be93  jz      short loc_18001BEBC
0x18001be95  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001be9c  test    rax, rax
0x18001be9f  jnz     short loc_18001BEAE
0x18001bea1  call    cs:__imp_GetProcessHeap
0x18001bea7  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001beae  mov     r8, rbx; lpMem
0x18001beb1  xor     edx, edx; dwFlags
0x18001beb3  mov     rcx, rax; hHeap
0x18001beb6  call    cs:__imp_HeapFree
0x18001bebc  mov     eax, 80004005h
0x18001bec1  mov     rcx, [rbp+170h+var_10]
0x18001bec8  xor     rcx, rsp; StackCookie
0x18001becb  call    __security_check_cookie
0x18001bed0  lea     r11, [rsp+270h+var_s0]
0x18001bed8  mov     rbx, [r11+10h]
0x18001bedc  mov     rdi, [r11+18h]
0x18001bee0  mov     rsp, r11
0x18001bee3  pop     rbp
0x18001bee4  retn
0x18001bee5  call    cs:__imp_GetCurrentProcess
0x18001beeb  mov     rcx, rax; hProcess
0x18001beee  xor     edx, edx; uExitCode
0x18001bef0  call    cs:__imp_TerminateProcess
0x18001bef6  jmp     short loc_18001BF01
0x18001bef8  xor     edx, edx; unsigned int
0x18001befa  xor     ecx, ecx; this
0x18001befc  call    ?ServiceMain@NGENService@@YAXKPEAPEAG@Z; NGENService::ServiceMain(ulong,ushort * *)
0x18001bf01  xor     eax, eax
0x18001bf03  jmp     short loc_18001BEC1
```
