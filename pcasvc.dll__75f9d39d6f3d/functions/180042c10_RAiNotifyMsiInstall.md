# RAiNotifyMsiInstall

- ea: `0x180042c10`
- end: `0x180042f93`
- name: `RAiNotifyMsiInstall`
- size: `899`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, DWORD dwProcessId, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x18000dd7c`
- `0x180012920`
- `0x180012960`
- `0x180012b78`
- `0x180013654`
- `0x18001b320`
- `0x18001d23c`
- `0x180033e58`
- `0x180042c10`
- `0x18008c884`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180042dd4`
- `msvcrt!wcsrchr` at `0x180042dd4`
- `msvcrt!wcscpy_s` at `0x180042dc4`
- `msvcrt!wcscpy_s` at `0x180042dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180042e5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180042e5b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042d3a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042d3a`

## string_xrefs

- `0x180042d14`: `Service`
- `0x180042f37`: `Service`
- `0x180042cd1`: `Bad flags passed to RaiNotifyMsiInstall [%d]`
- `0x180042eec`: `Bad Msi Package or Product code recieved from msiecex.exe: [%d]`
- `0x180042c51`: `RAiNotifyMsiInstall`
- `0x180042c5e`: `RAiNotifyMsiInstall`
- `0x180042d5c`: `RAiNotifyMsiInstall`
- `0x180042da5`: `RAiNotifyMsiInstall`
- `0x180042f07`: `RAiNotifyMsiInstall`
- `0x180042de7`: `Bad ExecutablePath [%d]`
- `0x180042d94`: `Failed to read name of process %d - %d`
- `0x180042d55`: `OpenProcess failed for client ProcessId %d | %d`
- `0x180042d08`: `RAiNotifyMsiInstall, Installer chain already exists for ClientProcessId: %d | %ws | %ws`
- `0x180042f27`: `RAiNotifyMsiInstall, ClientProcessId: %d ParentProcessId: %d | %ws | %ws`
- `0x180042eac`: `Failed to add Msi package and product coded to chain [%d]`
- `0x180042e68`: `MsiInstaller`

## pseudocode

```c
__int64 __fastcall RAiNotifyMsiInstall(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        DWORD dwProcessId,
        unsigned int a6)
{
  void *v8; // r13
  unsigned __int64 v9; // r12
  unsigned int v10; // ebx
  const char *v11; // r9
  int v12; // r8d
  __int64 v13; // rdi
  HANDLE v14; // rax
  wchar_t *v15; // rax
  unsigned int started; // eax
  ULONGLONG TickCount64; // rax
  unsigned int v18; // eax
  char *v20; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Source[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+260h] [rbp+160h] BYREF

  AslLogCallPrintf(3, (unsigned int)"RAiNotifyMsiInstall", 344, (unsigned int)"RAiNotifyMsiInstall");
  v22 = 0;
  v8 = 0;
  v9 = 0;
  if ( dwProcessId )
  {
    if ( a3 && a4 && *(_WORD *)a3 && *(_WORD *)a4 && *(_WORD *)(a3 + 74) && *(_WORD *)(a4 + 74) )
    {
      if ( (a6 & 0xFFFFFFFC) == 0 )
      {
        if ( PcaChainManagerFindMsiInstaller(
               (unsigned __int64)xmmword_1801585C8,
               (const unsigned __int16 *)a3,
               (const unsigned __int16 *)a4) )
        {
          v13 = a2;
          PcaTracePrintf(
            "Service",
            0,
            0,
            "RAiNotifyMsiInstall, Installer chain already exists for ClientProcessId: %d | %ws | %ws",
            dwProcessId,
            Source,
            a2);
          v10 = 0;
          goto LABEL_32;
        }
        v14 = OpenProcess(0x1FFFFFu, 0, dwProcessId);
        v8 = v14;
        if ( !v14 )
        {
          v10 = 6;
          AslLogCallPrintf(
            1,
            (unsigned int)"RAiNotifyMsiInstall",
            395,
            (unsigned int)"OpenProcess failed for client ProcessId %d | %d");
          goto LABEL_31;
        }
        if ( PcaUtilityGetProcessImageName(Source, v14, 0, 0) )
          AslLogCallPrintf(
            1,
            (unsigned int)"RAiNotifyMsiInstall",
            404,
            (unsigned int)"Failed to read name of process %d - %d");
        wcscpy_s(Destination, 0x104u, Source);
        v15 = wcsrchr(Source, 0x5Cu);
        if ( v15 )
        {
          *v15 = 0;
          started = PcaServiceStartTracking(
                      (__int64)&g_Service,
                      v8,
                      1u,
                      Destination,
                      (unsigned __int16 *)&sourceString,
                      (__int64)Source,
                      a6);
          v10 = started;
          if ( started )
          {
            if ( started == 1816 )
              goto LABEL_31;
            v11 = "Failed to start tracking [%d]";
            v12 = 433;
          }
          else
          {
            TickCount64 = GetTickCount64();
            v18 = PcaChainManagerLockChain(
                    &v22,
                    (unsigned __int64)xmmword_1801585C8,
                    dwProcessId,
                    TickCount64,
                    "MsiInstaller");
            v9 = v22;
            v10 = v18;
            if ( v18 || !v22 )
            {
              v11 = "Failed to get chain handle [%d]";
              v12 = 448;
            }
            else
            {
              v10 = PcaChainManagerAddMsiCodes(v22, (const unsigned __int16 *)a3, (const unsigned __int16 *)a4);
              if ( !v10 )
              {
                PcaEventTriagerExecute(*(&g_Service + 1), 19, dwProcessId);
                v10 = 0;
                goto LABEL_31;
              }
              v11 = "Failed to add Msi package and product coded to chain [%d]";
              v12 = 460;
            }
          }
        }
        else
        {
          v10 = 1359;
          v11 = "Bad ExecutablePath [%d]";
          v12 = 415;
        }
LABEL_30:
        AslLogCallPrintf(1, (unsigned int)"RAiNotifyMsiInstall", v12, (_DWORD)v11);
        goto LABEL_31;
      }
      v11 = "Bad flags passed to RaiNotifyMsiInstall [%d]";
      v12 = 371;
    }
    else
    {
      v11 = "Bad Msi Package or Product code recieved from msiecex.exe: [%d]";
      v12 = 365;
    }
    v10 = 87;
    goto LABEL_30;
  }
  v10 = 0;
LABEL_31:
  v13 = a2;
LABEL_32:
  LODWORD(v20) = dwProcessId;
  PcaTracePrintf(
    "Service",
    0,
    0,
    "RAiNotifyMsiInstall, ClientProcessId: %d ParentProcessId: %d | %ws | %ws",
    v20,
    0,
    Source,
    v13);
  if ( v8 )
    CloseHandle(v8);
  if ( v9 )
    PcaChainUnlock(v9);
  return v10;
}

```

## disassembly

```asm
0x180042c10  mov     [rsp-8+arg_0], rbx
0x180042c15  push    rbp
0x180042c16  push    rsi
0x180042c17  push    rdi
0x180042c18  push    r12
0x180042c1a  push    r13
0x180042c1c  push    r14
0x180042c1e  push    r15
0x180042c20  lea     rbp, [rsp-380h]
0x180042c28  sub     rsp, 480h
0x180042c2f  mov     rax, cs:__security_cookie
0x180042c36  xor     rax, rsp
0x180042c39  mov     [rbp+3B0h+var_40], rax
0x180042c40  mov     esi, [rbp+3B0h+dwProcessId]
0x180042c46  mov     r15, r9
0x180042c49  mov     r14, r8
0x180042c4c  mov     [rsp+4B0h+var_470], rdx
0x180042c51  lea     r9, aRainotifymsiin_1; "RAiNotifyMsiInstall"
0x180042c58  mov     r8d, 158h
0x180042c5e  lea     rdx, aRainotifymsiin_1; "RAiNotifyMsiInstall"
0x180042c65  mov     ecx, 3
0x180042c6a  call    AslLogCallPrintf
0x180042c6f  xor     edi, edi
0x180042c71  mov     [rsp+4B0h+var_468], rdi
0x180042c76  mov     r13d, edi
0x180042c79  mov     r12d, edi
0x180042c7c  test    esi, esi
0x180042c7e  jnz     short loc_180042C87
0x180042c80  mov     ebx, edi
0x180042c82  jmp     loc_180042F13
0x180042c87  test    r14, r14
0x180042c8a  jz      loc_180042EEC
0x180042c90  test    r15, r15
0x180042c93  jz      loc_180042EEC
0x180042c99  cmp     [r14], di
0x180042c9d  jz      loc_180042EEC
0x180042ca3  cmp     [r15], di
0x180042ca7  jz      loc_180042EEC
0x180042cad  cmp     [r14+4Ah], di
0x180042cb2  jz      loc_180042EEC
0x180042cb8  cmp     [r15+4Ah], di
0x180042cbd  jz      loc_180042EEC
0x180042cc3  mov     ebx, [rbp+3B0h+arg_28]
0x180042cc9  test    ebx, 0FFFFFFFCh
0x180042ccf  jz      short loc_180042CE3
0x180042cd1  lea     r9, aBadFlagsPassed; "Bad flags passed to RaiNotifyMsiInstall"...
0x180042cd8  mov     r8d, 173h
0x180042cde  jmp     loc_180042EF9
0x180042ce3  mov     rcx, qword ptr cs:xmmword_1801585C8; unsigned __int64
0x180042cea  mov     r8, r15; unsigned __int16 *
0x180042ced  mov     rdx, r14; unsigned __int16 *
0x180042cf0  call    ?PcaChainManagerFindMsiInstaller@@YAH_KPEBG1@Z; PcaChainManagerFindMsiInstaller(unsigned __int64,ushort const *,ushort const *)
0x180042cf5  test    eax, eax
0x180042cf7  jz      short loc_180042D30
0x180042cf9  mov     rdi, [rsp+4B0h+var_470]
0x180042cfe  lea     rax, [rsp+4B0h+Source]
0x180042d03  mov     [rsp+4B0h+var_480], rdi
0x180042d08  lea     r9, aRainotifymsiin_0; "RAiNotifyMsiInstall, Installer chain al"...
0x180042d0f  mov     [rsp+4B0h+var_488], rax
0x180042d14  lea     rcx, aService; "Service"
0x180042d1b  xor     r8d, r8d; unsigned int
0x180042d1e  mov     dword ptr [rsp+4B0h+var_490], esi
0x180042d22  xor     edx, edx; unsigned int
0x180042d24  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180042d29  xor     ebx, ebx
0x180042d2b  jmp     loc_180042F18
0x180042d30  mov     r8d, esi; dwProcessId
0x180042d33  xor     edx, edx; bInheritHandle
0x180042d35  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180042d3a  call    cs:__imp_OpenProcess
0x180042d40  mov     r13, rax
0x180042d43  test    rax, rax
0x180042d46  jnz     short loc_180042D74
0x180042d48  lea     ebx, [rax+6]
0x180042d4b  mov     r8d, 18Bh
0x180042d51  mov     dword ptr [rsp+4B0h+var_488], ebx
0x180042d55  lea     r9, aOpenprocessFai; "OpenProcess failed for client ProcessId"...
0x180042d5c  lea     rdx, aRainotifymsiin_1; "RAiNotifyMsiInstall"
0x180042d63  mov     dword ptr [rsp+4B0h+var_490], esi
0x180042d67  lea     ecx, [rax+1]
0x180042d6a  call    AslLogCallPrintf
0x180042d6f  jmp     loc_180042F13
0x180042d74  xor     r9d, r9d; unsigned __int16 *
0x180042d77  lea     rcx, [rsp+4B0h+Source]; unsigned __int16 *
0x180042d7c  xor     r8d, r8d; unsigned __int16 *
0x180042d7f  mov     rdx, r13; hProcess
0x180042d82  call    ?PcaUtilityGetProcessImageName@@YAKPEAGPEAXPEBG2@Z; PcaUtilityGetProcessImageName(ushort *,void *,ushort const *,ushort const *)
0x180042d87  mov     edi, 1
0x180042d8c  test    eax, eax
0x180042d8e  jz      short loc_180042DB3
0x180042d90  mov     dword ptr [rsp+4B0h+var_488], eax
0x180042d94  lea     r9, aFailedToReadNa_0; "Failed to read name of process %d - %d"
0x180042d9b  mov     r8d, 194h
0x180042da1  mov     dword ptr [rsp+4B0h+var_490], esi
0x180042da5  lea     rdx, aRainotifymsiin_1; "RAiNotifyMsiInstall"
0x180042dac  mov     ecx, edi
0x180042dae  call    AslLogCallPrintf
0x180042db3  lea     r8, [rsp+4B0h+Source]; Source
0x180042db8  mov     edx, 104h; SizeInWords
0x180042dbd  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180042dc4  call    cs:__imp_wcscpy_s
0x180042dca  mov     edx, 5Ch ; '\'; Ch
0x180042dcf  lea     rcx, [rsp+4B0h+Source]; Str
0x180042dd4  call    cs:__imp_wcsrchr
0x180042dda  mov     rcx, rax
0x180042ddd  test    rax, rax
0x180042de0  jnz     short loc_180042DFF
0x180042de2  mov     ebx, 54Fh
0x180042de7  lea     r9, aBadExecutablep; "Bad ExecutablePath [%d]"
0x180042dee  mov     dword ptr [rsp+4B0h+var_490], ebx
0x180042df2  mov     r8d, 19Fh
0x180042df8  mov     ecx, edi
0x180042dfa  jmp     loc_180042F07
0x180042dff  xor     eax, eax
0x180042e01  mov     dword ptr [rsp+4B0h+var_480], ebx
0x180042e05  mov     [rcx], ax
0x180042e08  lea     r9, [rbp+3B0h+Destination]
0x180042e0f  lea     rax, [rsp+4B0h+Source]
0x180042e14  mov     r8d, edi
0x180042e17  mov     [rsp+4B0h+var_488], rax
0x180042e1c  lea     rcx, ?g_Service@@3U_PCA_SERVICE@@A; _PCA_SERVICE g_Service
0x180042e23  lea     rax, sourceString
0x180042e2a  mov     rdx, r13
0x180042e2d  mov     [rsp+4B0h+var_490], rax
0x180042e32  call    ?PcaServiceStartTracking@@YAKPEAU_PCA_SERVICE@@PEAXW4PCA_PROCESS_TYPE@@PEBG33I@Z; PcaServiceStartTracking(_PCA_SERVICE *,void *,PCA_PROCESS_TYPE,ushort const *,ushort const *,ushort const *,uint)
0x180042e37  mov     ebx, eax
0x180042e39  test    eax, eax
0x180042e3b  jz      short loc_180042E5B
0x180042e3d  cmp     eax, 718h
0x180042e42  jz      loc_180042F13
0x180042e48  mov     dword ptr [rsp+4B0h+var_490], eax
0x180042e4c  lea     r9, aFailedToStartT_3; "Failed to start tracking [%d]"
0x180042e53  mov     r8d, 1B1h
0x180042e59  jmp     short loc_180042DF8
0x180042e5b  call    cs:__imp_GetTickCount64
0x180042e61  mov     rdx, qword ptr cs:xmmword_1801585C8; unsigned __int64
0x180042e68  lea     rcx, aMsiinstaller; "MsiInstaller"
0x180042e6f  mov     [rsp+4B0h+var_490], rcx; char *
0x180042e74  mov     r9, rax; unsigned __int64
0x180042e77  lea     rcx, [rsp+4B0h+var_468]; unsigned __int64 *
0x180042e7c  mov     r8d, esi; unsigned int
0x180042e7f  call    ?PcaChainManagerLockChain@@YAKPEA_K_KK1PEBD@Z; PcaChainManagerLockChain(unsigned __int64 *,unsigned __int64,ulong,unsigned __int64,char const *)
0x180042e84  mov     r12, [rsp+4B0h+var_468]
0x180042e89  mov     ebx, eax
0x180042e8b  test    eax, eax
0x180042e8d  jnz     short loc_180042ED6
0x180042e8f  test    r12, r12
0x180042e92  jz      short loc_180042ED6
0x180042e94  mov     r8, r15; unsigned __int16 *
0x180042e97  mov     rdx, r14; unsigned __int16 *
0x180042e9a  mov     rcx, r12; unsigned __int64
0x180042e9d  call    ?PcaChainManagerAddMsiCodes@@YAK_KPEBG1@Z; PcaChainManagerAddMsiCodes(unsigned __int64,ushort const *,ushort const *)
0x180042ea2  mov     ebx, eax
0x180042ea4  test    eax, eax
0x180042ea6  jz      short loc_180042EBE
0x180042ea8  mov     dword ptr [rsp+4B0h+var_490], eax
0x180042eac  lea     r9, aFailedToAddMsi_0; "Failed to add Msi package and product c"...
0x180042eb3  mov     r8d, 1CCh
0x180042eb9  jmp     loc_180042DF8
0x180042ebe  mov     rcx, qword ptr cs:?g_Service@@3U_PCA_SERVICE@@A+8; _PCA_SERVICE g_Service
0x180042ec5  mov     r8, rsi
0x180042ec8  mov     edx, 13h
0x180042ecd  call    ?PcaEventTriagerExecute@@YAX_KW4_PCA_EVENT_TYPE@@PEAX@Z; PcaEventTriagerExecute(unsigned __int64,_PCA_EVENT_TYPE,void *)
0x180042ed2  xor     ebx, ebx
0x180042ed4  jmp     short loc_180042F13
0x180042ed6  mov     dword ptr [rsp+4B0h+var_490], eax
0x180042eda  lea     r9, aFailedToGetCha; "Failed to get chain handle [%d]"
0x180042ee1  mov     r8d, 1C0h
0x180042ee7  jmp     loc_180042DF8
0x180042eec  lea     r9, aBadMsiPackageO; "Bad Msi Package or Product code recieve"...
0x180042ef3  mov     r8d, 16Dh
0x180042ef9  mov     eax, 57h ; 'W'
0x180042efe  mov     ebx, eax
0x180042f00  mov     dword ptr [rsp+4B0h+var_490], eax
0x180042f04  lea     ecx, [rax-56h]
0x180042f07  lea     rdx, aRainotifymsiin_1; "RAiNotifyMsiInstall"
0x180042f0e  call    AslLogCallPrintf
0x180042f13  mov     rdi, [rsp+4B0h+var_470]
0x180042f18  mov     [rsp+4B0h+var_478], rdi
0x180042f1d  lea     rax, [rsp+4B0h+Source]
0x180042f22  mov     [rsp+4B0h+var_480], rax
0x180042f27  lea     r9, aRainotifymsiin; "RAiNotifyMsiInstall, ClientProcessId: %"...
0x180042f2e  mov     [rsp+4B0h+var_488], 0
0x180042f37  lea     rcx, aService; "Service"
0x180042f3e  xor     r8d, r8d; unsigned int
0x180042f41  mov     dword ptr [rsp+4B0h+var_490], esi
0x180042f45  xor     edx, edx; unsigned int
0x180042f47  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180042f4c  test    r13, r13
0x180042f4f  jz      short loc_180042F5A
0x180042f51  mov     rcx, r13; hObject
0x180042f54  call    cs:__imp_CloseHandle
0x180042f5a  test    r12, r12
0x180042f5d  jz      short loc_180042F67
0x180042f5f  mov     rcx, r12; unsigned __int64
0x180042f62  call    ?PcaChainUnlock@@YAX_K@Z; PcaChainUnlock(unsigned __int64)
0x180042f67  mov     eax, ebx
0x180042f69  mov     rcx, [rbp+3B0h+var_40]
0x180042f70  xor     rcx, rsp; StackCookie
0x180042f73  call    __security_check_cookie
0x180042f78  mov     rbx, [rsp+4B0h+arg_0]
0x180042f80  add     rsp, 480h
0x180042f87  pop     r15
0x180042f89  pop     r14
0x180042f8b  pop     r13
0x180042f8d  pop     r12
0x180042f8f  pop     rdi
0x180042f90  pop     rsi
0x180042f91  pop     rbp
0x180042f92  retn
```
