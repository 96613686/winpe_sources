# ServiceMain

- ea: `0x180001f60`
- end: `0x180002107`
- name: `ServiceMain`
- size: `423`
- prototype: `int __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001f60`
- `0x180002110`
- `0x1800021d0`
- `0x180002200`
- `0x180003448`
- `0x180005020`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002015`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002015`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800020cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800020cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001fa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001fa5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800020bf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800020bf`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000208e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000208e`

## string_xrefs

- `0x180001f9e`: `CreateDOService`

## pseudocode

```c
int __fastcall ServiceMain(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  signed int v6; // ebx
  FARPROC ProcAddress; // rdi
  SERVICE_STATUS_HANDLE v8; // rax
  bool v9; // di
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-88h] BYREF
  __int64 v14; // [rsp+28h] [rbp-80h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, __int64); // [rsp+30h] [rbp-78h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-70h]
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-68h] BYREF

  v6 = -2147467259;
  DllForwarder::DllForwarder((DllForwarder *)&v15, a2, a3, a4);
  if ( !hModule )
    goto LABEL_12;
  ProcAddress = GetProcAddress(hModule, "CreateDOService");
  if ( !ProcAddress )
    goto LABEL_12;
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(&v14);
  v13 = 0;
  Microsoft::WRL::ComPtr<IDOService>::InternalRelease(&v13);
  LODWORD(v8) = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))ProcAddress)(*(_QWORD *)a2, v14, &v13);
  v6 = (int)v8;
  if ( (int)v8 >= 0 )
  {
    v9 = 0;
    if ( a1 >= 2 )
      v9 = (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 1), L"TriggerStarted") == 0;
    LODWORD(v8) = (*(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v13 + 24LL))(v13, v9);
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    LODWORD(v8) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v14;
  if ( v14 )
  {
    v14 = 0;
    LODWORD(v8) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v6 < 0 )
  {
LABEL_12:
    v8 = RegisterServiceCtrlHandlerExW(*(LPCWSTR *)a2, DummySvcCtrlHandler, 0);
    if ( v8 )
    {
      ServiceStatus.dwServiceType = 0;
      *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      ServiceStatus.dwWin32ExitCode = 1066;
      ServiceStatus.dwServiceSpecificExitCode = v6;
      LODWORD(v8) = SetServiceStatus(v8, &ServiceStatus);
    }
  }
  if ( hModule )
    LODWORD(v8) = FreeLibrary(hModule);
  if ( v15 )
    LODWORD(v8) = (**v15)(v15, 1);
  return (int)v8;
}

```

## disassembly

```asm
0x180001f60  push    rbx
0x180001f62  push    rbp
0x180001f63  push    rsi
0x180001f64  push    rdi
0x180001f65  push    r14
0x180001f67  push    r15
0x180001f69  sub     rsp, 78h
0x180001f6d  mov     rax, cs:__security_cookie
0x180001f74  xor     rax, rsp
0x180001f77  mov     [rsp+0A8h+var_48], rax
0x180001f7c  mov     r14, rdx
0x180001f7f  mov     esi, ecx
0x180001f81  mov     ebx, 80004005h
0x180001f86  lea     rcx, [rsp+0A8h+var_78]; this
0x180001f8b  call    ??0DllForwarder@@QEAA@PEBG00@Z; DllForwarder::DllForwarder(ushort const *,ushort const *,ushort const *)
0x180001f90  mov     rcx, [rsp+0A8h+hModule]; hModule
0x180001f95  test    rcx, rcx
0x180001f98  jz      loc_180002079
0x180001f9e  lea     rdx, aCreatedoservic; "CreateDOService"
0x180001fa5  call    cs:__imp_GetProcAddress
0x180001fab  mov     rdi, rax
0x180001fae  test    rax, rax
0x180001fb1  jz      loc_180002079
0x180001fb7  xor     ebp, ebp
0x180001fb9  mov     [rsp+0A8h+var_80], rbp
0x180001fbe  lea     rcx, [rsp+0A8h+var_80]
0x180001fc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180001fc8  lea     rcx, [rsp+0A8h+var_80]
0x180001fcd  call    ??$MakeAndInitialize@VCServiceCallback@@UIDOServiceCallback@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIDOServiceCallback@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(IDOServiceCallback * *)
0x180001fd2  mov     [rsp+0A8h+var_88], rbp
0x180001fd7  lea     rcx, [rsp+0A8h+var_88]
0x180001fdc  call    ?InternalRelease@?$ComPtr@UIDOService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDOService>::InternalRelease(void)
0x180001fe1  lea     r8, [rsp+0A8h+var_88]
0x180001fe6  mov     rdx, [rsp+0A8h+var_80]
0x180001feb  mov     rcx, [r14]
0x180001fee  mov     rax, rdi
0x180001ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff6  mov     ebx, eax
0x180001ff8  mov     r15d, 1
0x180001ffe  test    eax, eax
0x180002000  js      short loc_18000203B
0x180002002  xor     dil, dil
0x180002005  cmp     esi, 2
0x180002008  jb      short loc_180002025
0x18000200a  lea     rdx, aTriggerstarted; "TriggerStarted"
0x180002011  mov     rcx, [r14+8]
0x180002015  call    cs:__imp__o__wcsicmp
0x18000201b  movzx   edi, dil
0x18000201f  test    eax, eax
0x180002021  cmovz   edi, r15d
0x180002025  mov     rcx, [rsp+0A8h+var_88]
0x18000202a  mov     rax, [rcx]
0x18000202d  movzx   edx, dil
0x180002031  mov     rax, [rax+18h]
0x180002035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203a  nop
0x18000203b  mov     rcx, [rsp+0A8h+var_88]
0x180002040  test    rcx, rcx
0x180002043  jz      short loc_180002057
0x180002045  mov     [rsp+0A8h+var_88], rbp
0x18000204a  mov     rax, [rcx]
0x18000204d  mov     rax, [rax+10h]
0x180002051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002056  nop
0x180002057  mov     rcx, [rsp+0A8h+var_80]
0x18000205c  test    rcx, rcx
0x18000205f  jz      short loc_180002073
0x180002061  mov     [rsp+0A8h+var_80], rbp
0x180002066  mov     rax, [rcx]
0x180002069  mov     rax, [rax+10h]
0x18000206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002072  nop
0x180002073  test    ebx, ebx
0x180002075  js      short loc_180002081
0x180002077  jmp     short loc_1800020C5
0x180002079  xor     ebp, ebp
0x18000207b  mov     r15d, 1
0x180002081  xor     r8d, r8d; lpContext
0x180002084  lea     rdx, DummySvcCtrlHandler; lpHandlerProc
0x18000208b  mov     rcx, [r14]; lpServiceName
0x18000208e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002094  test    rax, rax
0x180002097  jz      short loc_1800020C5
0x180002099  mov     [rsp+0A8h+ServiceStatus.dwServiceType], ebp
0x18000209d  mov     qword ptr [rsp+0A8h+ServiceStatus.dwCurrentState], 1
0x1800020a6  mov     qword ptr [rsp+0A8h+ServiceStatus.dwCheckPoint], rbp
0x1800020ab  mov     [rsp+0A8h+ServiceStatus.dwWin32ExitCode], 42Ah
0x1800020b3  mov     [rsp+0A8h+ServiceStatus.dwServiceSpecificExitCode], ebx
0x1800020b7  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800020bc  mov     rcx, rax; hServiceStatus
0x1800020bf  call    cs:__imp_SetServiceStatus
0x1800020c5  mov     rcx, [rsp+0A8h+hModule]; hLibModule
0x1800020ca  test    rcx, rcx
0x1800020cd  jz      short loc_1800020D5
0x1800020cf  call    cs:__imp_FreeLibrary
0x1800020d5  mov     rcx, [rsp+0A8h+var_78]
0x1800020da  test    rcx, rcx
0x1800020dd  jz      short loc_1800020ED
0x1800020df  mov     rax, [rcx]
0x1800020e2  mov     edx, r15d
0x1800020e5  mov     rax, [rax]
0x1800020e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ed  mov     rcx, [rsp+0A8h+var_48]
0x1800020f2  xor     rcx, rsp; StackCookie
0x1800020f5  call    __security_check_cookie
0x1800020fa  add     rsp, 78h
0x1800020fe  pop     r15
0x180002100  pop     r14
0x180002102  pop     rdi
0x180002103  pop     rsi
0x180002104  pop     rbp
0x180002105  pop     rbx
0x180002106  retn
```
