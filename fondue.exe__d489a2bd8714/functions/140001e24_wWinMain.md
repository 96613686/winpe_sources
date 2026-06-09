# wWinMain

- ea: `0x140001e24`
- end: `0x140002084`
- name: `wWinMain`
- size: `608`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001220`

## callees

- `0x1400017bf`
- `0x140001be4`
- `0x140001d5c`
- `0x140001e24`
- `0x140004cd0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001e7c`
- `KERNEL32!GetCurrentThreadId` at `0x140001e7c`
- `KERNEL32!GetVersionExW` at `0x140002003`
- `KERNEL32!GetVersionExW` at `0x140002003`
- `KERNEL32!ProcessIdToSessionId` at `0x140001f39`
- `KERNEL32!ProcessIdToSessionId` at `0x140001f39`
- `KERNEL32!GetLastError` at `0x140001e92`
- `KERNEL32!GetLastError` at `0x140001eda`
- `KERNEL32!GetLastError` at `0x140001e92`
- `KERNEL32!GetLastError` at `0x140001eda`
- `KERNEL32!LoadLibraryW` at `0x140001fab`
- `KERNEL32!LoadLibraryW` at `0x140001fab`
- `KERNEL32!HeapSetInformation` at `0x140001f1e`
- `KERNEL32!HeapSetInformation` at `0x140001f1e`
- `KERNEL32!GetProcAddress` at `0x140001fc0`
- `KERNEL32!GetProcAddress` at `0x140001fc0`
- `KERNEL32!GetCurrentProcessId` at `0x140001f2c`
- `KERNEL32!GetCurrentProcessId` at `0x140001f2c`
- `USER32!CreateDesktopW` at `0x140001ecc`
- `USER32!CreateDesktopW` at `0x140001ecc`
- `USER32!CloseDesktop` at `0x140002043`
- `USER32!CloseDesktop` at `0x140002043`
- `USER32!GetThreadDesktop` at `0x140001e84`
- `USER32!GetThreadDesktop` at `0x140001e84`
- `USER32!SetThreadDesktop` at `0x140001efb`
- `USER32!SetThreadDesktop` at `0x140002035`
- `USER32!SetThreadDesktop` at `0x140001efb`
- `USER32!SetThreadDesktop` at `0x140002035`
- `USER32!SwitchDesktop` at `0x140001f08`
- `USER32!SwitchDesktop` at `0x14000202c`
- `USER32!SwitchDesktop` at `0x140001f08`
- `USER32!SwitchDesktop` at `0x14000202c`
- `msvcrt!wcsstr` at `0x140001e60`
- `msvcrt!wcsstr` at `0x140001e60`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000201e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000201e`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140001f98`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140001f98`
- `ole32!CoInitialize` at `0x140001f56`
- `ole32!CoInitialize` at `0x140001f56`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  HDESK ThreadDesktop; // rsi
  HDESK v8; // rdi
  DWORD CurrentThreadId; // eax
  signed int LastError; // eax
  int v11; // ebx
  HDESK DesktopW; // rax
  signed int v13; // eax
  DWORD CurrentProcessId; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int result; // eax
  DWORD pSessionId[4]; // [rsp+50h] [rbp-168h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-158h] BYREF
  char v20; // [rsp+17Ah] [rbp-3Eh]

  ThreadDesktop = 0;
  v8 = 0;
  if ( !wcsstr(lpCmdLine, L"/top-most") || !(unsigned int)IsRudeAppPresent() )
    goto LABEL_11;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( !ThreadDesktop )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  DesktopW = CreateDesktopW(L"FondueDesktop", 0, 0, 0, 0x10000000u, 0);
  v8 = DesktopW;
  if ( DesktopW && SetThreadDesktop(DesktopW) && SwitchDesktop(v8) )
  {
LABEL_11:
    HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
    pSessionId[0] = -1;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, pSessionId) || pSessionId[0] )
    {
      v11 = CoInitialize(0);
      if ( v11 >= 0 )
      {
        v11 = CoInitializeSecurity(0, -1, 0, 0, 3u, 3u, 0, 0, 0);
        if ( v11 >= 0 )
        {
          LibraryW = LoadLibraryW(L"APPWIZ.CPL");
          if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "RunFODW")) != 0 )
          {
            v11 = ((__int64 (__fastcall *)(_QWORD, HINSTANCE, LPWSTR, _QWORD))ProcAddress)(
                    0,
                    hInstance,
                    lpCmdLine,
                    (unsigned int)nShowCmd);
          }
          else
          {
            v11 = -2147024846;
            memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
            VersionInformation.dwOSVersionInfoSize = 284;
            GetVersionExW(&VersionInformation);
            if ( (unsigned __int8)(v20 - 2) <= 1u )
              ShowServerMessage(lpCmdLine);
          }
        }
        CoUninitialize();
      }
    }
    else
    {
      v11 = -2147467259;
    }
    if ( !ThreadDesktop )
      goto LABEL_24;
  }
  else
  {
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
  }
  SwitchDesktop(ThreadDesktop);
  SetThreadDesktop(ThreadDesktop);
LABEL_24:
  if ( v8 )
    CloseDesktop(v8);
LABEL_26:
  result = (unsigned __int16)v11;
  if ( (v11 & 0x1FFF0000) != 0x70000 )
    return v11;
  return result;
}

```

## disassembly

```asm
0x140001e24  mov     [rsp+arg_8], rbx
0x140001e29  push    rbp
0x140001e2a  push    rsi
0x140001e2b  push    rdi
0x140001e2c  push    r14
0x140001e2e  push    r15
0x140001e30  sub     rsp, 190h
0x140001e37  mov     rax, cs:__security_cookie
0x140001e3e  xor     rax, rsp
0x140001e41  mov     [rsp+1B8h+var_38], rax
0x140001e49  mov     r14, rcx
0x140001e4c  lea     rdx, aTopMost; "/top-most"
0x140001e53  mov     rcx, r8; Str
0x140001e56  mov     r15d, r9d
0x140001e59  mov     rbp, r8
0x140001e5c  xor     esi, esi
0x140001e5e  xor     edi, edi
0x140001e60  call    cs:__imp_wcsstr
0x140001e66  test    rax, rax
0x140001e69  jz      loc_140001F12
0x140001e6f  call    ?IsRudeAppPresent@@YAHXZ; IsRudeAppPresent(void)
0x140001e74  test    eax, eax
0x140001e76  jz      loc_140001F12
0x140001e7c  call    cs:__imp_GetCurrentThreadId
0x140001e82  mov     ecx, eax; dwThreadId
0x140001e84  call    cs:__imp_GetThreadDesktop
0x140001e8a  mov     rsi, rax
0x140001e8d  test    rax, rax
0x140001e90  jnz     short loc_140001EB0
0x140001e92  call    cs:__imp_GetLastError
0x140001e98  mov     ebx, eax
0x140001e9a  test    eax, eax
0x140001e9c  jle     loc_140002049
0x140001ea2  movzx   ebx, ax
0x140001ea5  or      ebx, 80070000h
0x140001eab  jmp     loc_140002049
0x140001eb0  mov     [rsp+1B8h+lpsa], rdi; lpsa
0x140001eb5  lea     rcx, szDesktop; "FondueDesktop"
0x140001ebc  xor     r9d, r9d; dwFlags
0x140001ebf  mov     [rsp+1B8h+dwDesiredAccess], 10000000h; dwDesiredAccess
0x140001ec7  xor     r8d, r8d; pDevmode
0x140001eca  xor     edx, edx; lpszDevice
0x140001ecc  call    cs:__imp_CreateDesktopW
0x140001ed2  mov     rdi, rax
0x140001ed5  test    rax, rax
0x140001ed8  jnz     short loc_140001EF8
0x140001eda  call    cs:__imp_GetLastError
0x140001ee0  mov     ebx, eax
0x140001ee2  test    eax, eax
0x140001ee4  jle     loc_140002029
0x140001eea  movzx   ebx, ax
0x140001eed  or      ebx, 80070000h
0x140001ef3  jmp     loc_140002029
0x140001ef8  mov     rcx, rdi; hDesktop
0x140001efb  call    cs:__imp_SetThreadDesktop
0x140001f01  test    eax, eax
0x140001f03  jz      short loc_140001EDA
0x140001f05  mov     rcx, rdi; hDesktop
0x140001f08  call    cs:__imp_SwitchDesktop
0x140001f0e  test    eax, eax
0x140001f10  jz      short loc_140001EDA
0x140001f12  xor     r9d, r9d; HeapInformationLength
0x140001f15  xor     r8d, r8d; HeapInformation
0x140001f18  xor     ecx, ecx; HeapHandle
0x140001f1a  lea     edx, [r9+1]; HeapInformationClass
0x140001f1e  call    cs:__imp_HeapSetInformation
0x140001f24  mov     [rsp+1B8h+pSessionId], 0FFFFFFFFh
0x140001f2c  call    cs:__imp_GetCurrentProcessId
0x140001f32  mov     ecx, eax; dwProcessId
0x140001f34  lea     rdx, [rsp+1B8h+pSessionId]; pSessionId
0x140001f39  call    cs:__imp_ProcessIdToSessionId
0x140001f3f  test    eax, eax
0x140001f41  jz      short loc_140001F54
0x140001f43  cmp     [rsp+1B8h+pSessionId], 0
0x140001f48  jnz     short loc_140001F54
0x140001f4a  mov     ebx, 80004005h
0x140001f4f  jmp     loc_140002024
0x140001f54  xor     ecx, ecx; pvReserved
0x140001f56  call    cs:__imp_CoInitialize
0x140001f5c  mov     ebx, eax
0x140001f5e  test    eax, eax
0x140001f60  js      loc_140002024
0x140001f66  mov     [rsp+1B8h+pReserved3], 0; pReserved3
0x140001f6f  mov     eax, 3
0x140001f74  mov     [rsp+1B8h+dwCapabilities], 0; dwCapabilities
0x140001f7c  xor     r9d, r9d; pReserved1
0x140001f7f  mov     [rsp+1B8h+pAuthList], 0; pAuthList
0x140001f88  xor     r8d, r8d; asAuthSvc
0x140001f8b  mov     dword ptr [rsp+1B8h+lpsa], eax; dwImpLevel
0x140001f8f  or      edx, 0FFFFFFFFh; cAuthSvc
0x140001f92  xor     ecx, ecx; pSecDesc
0x140001f94  mov     [rsp+1B8h+dwDesiredAccess], eax; dwAuthnLevel
0x140001f98  call    cs:__imp_CoInitializeSecurity
0x140001f9e  mov     ebx, eax
0x140001fa0  test    eax, eax
0x140001fa2  js      short loc_14000201E
0x140001fa4  lea     rcx, LibFileName; "APPWIZ.CPL"
0x140001fab  call    cs:__imp_LoadLibraryW
0x140001fb1  test    rax, rax
0x140001fb4  jz      short loc_140001FDF
0x140001fb6  lea     rdx, ProcName; "RunFODW"
0x140001fbd  mov     rcx, rax; hModule
0x140001fc0  call    cs:__imp_GetProcAddress
0x140001fc6  test    rax, rax
0x140001fc9  jz      short loc_140001FDF
0x140001fcb  mov     r9d, r15d
0x140001fce  mov     r8, rbp
0x140001fd1  mov     rdx, r14
0x140001fd4  xor     ecx, ecx
0x140001fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fdb  mov     ebx, eax
0x140001fdd  jmp     short loc_14000201E
0x140001fdf  xor     edx, edx; Val
0x140001fe1  lea     rcx, [rsp+1B8h+VersionInformation.dwMajorVersion]; void *
0x140001fe6  mov     r8d, 118h; Size
0x140001fec  mov     ebx, 80070032h
0x140001ff1  call    memset_0
0x140001ff6  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x140001ffb  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140002003  call    cs:__imp_GetVersionExW
0x140002009  mov     al, [rsp+1B8h+var_3E]
0x140002010  sub     al, 2
0x140002012  cmp     al, 1
0x140002014  ja      short loc_14000201E
0x140002016  mov     rcx, rbp; unsigned __int16 *
0x140002019  call    ?ShowServerMessage@@YAXPEAG@Z; ShowServerMessage(ushort *)
0x14000201e  call    cs:__imp_CoUninitialize
0x140002024  test    rsi, rsi
0x140002027  jz      short loc_14000203B
0x140002029  mov     rcx, rsi; hDesktop
0x14000202c  call    cs:__imp_SwitchDesktop
0x140002032  mov     rcx, rsi; hDesktop
0x140002035  call    cs:__imp_SetThreadDesktop
0x14000203b  test    rdi, rdi
0x14000203e  jz      short loc_140002049
0x140002040  mov     rcx, rdi; hDesktop
0x140002043  call    cs:__imp_CloseDesktop
0x140002049  mov     ecx, ebx
0x14000204b  movzx   eax, bx
0x14000204e  and     ecx, 1FFF0000h
0x140002054  cmp     ecx, 70000h
0x14000205a  cmovnz  eax, ebx
0x14000205d  mov     rcx, [rsp+1B8h+var_38]
0x140002065  xor     rcx, rsp; StackCookie
0x140002068  call    __security_check_cookie
0x14000206d  mov     rbx, [rsp+1B8h+arg_8]
0x140002075  add     rsp, 190h
0x14000207c  pop     r15
0x14000207e  pop     r14
0x140002080  pop     rdi
0x140002081  pop     rsi
0x140002082  pop     rbp
0x140002083  retn
```
