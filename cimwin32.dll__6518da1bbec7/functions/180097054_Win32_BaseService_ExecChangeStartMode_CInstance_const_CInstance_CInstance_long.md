# Win32_BaseService::ExecChangeStartMode(CInstance const &,CInstance *,CInstance *,long)

- ea: `0x180097054`
- end: `0x18009741a`
- name: `?ExecChangeStartMode@Win32_BaseService@@IEAAJAEBVCInstance@@PEAV2@1J@Z`
- size: `966`
- prototype: `int(Win32_BaseService *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180097780`

## callees

- `0x18000ab30`
- `0x180013ae0`
- `0x180044b1c`
- `0x18008bb9c`
- `0x180097054`
- `0x1800981e4`
- `0x180098390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009727f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009727f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18009707c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18009709d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800970f4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18009707c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18009709d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800970f4`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180097157`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180097157`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180097184`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18009719f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800971ba`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800971d5`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800971f0`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180097184`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18009719f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800971ba`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800971d5`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800971f0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180097228`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180097228`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18009732f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180097352`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18009737a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800973bb`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800973d3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18009732f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180097352`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18009737a`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800973bb`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800973d3`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18009716a`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18009716a`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180097120`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x180097120`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180097397`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800973a3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800973df`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800973f9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180097397`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800973a3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800973df`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800973f9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009723a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009723a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180097209`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180097209`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180097271`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800972b7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180097271`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800972b7`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800972f8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800972f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Win32_BaseService::ExecChangeStartMode(
        Win32_BaseService *this,
        const struct CInstance *a2,
        struct CInstance *a3,
        struct CInstance *a4,
        char a5)
{
  Win32_BaseService *v8; // rcx
  int ServiceStatus; // ebx
  DWORD v10; // esi
  Win32_BaseService *v11; // rcx
  SC_HANDLE v12; // rbx
  const WCHAR *v13; // rax
  SC_HANDLE v14; // rax
  Win32_BaseService *v15; // rcx
  SC_HANDLE v16; // r14
  struct _QUERY_SERVICE_CONFIGW *v17; // rbx
  Win32_BaseService *v18; // rcx
  struct _QUERY_SERVICE_CONFIGW *v19; // rax
  unsigned int ServiceErrorCode; // r8d
  unsigned int v21; // eax
  unsigned int v22; // eax
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int16 v25; // [rsp+64h] [rbp-54h] BYREF
  _BYTE v26[8]; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v27[8]; // [rsp+70h] [rbp-48h] BYREF
  BOOL v28; // [rsp+78h] [rbp-40h]
  int pExceptionObject; // [rsp+7Ch] [rbp-3Ch] BYREF
  struct _QUERY_SERVICE_CONFIGW *v30; // [rsp+80h] [rbp-38h]
  _BYTE v31[8]; // [rsp+88h] [rbp-30h] BYREF
  SC_HANDLE v32; // [rsp+90h] [rbp-28h] BYREF
  SC_HANDLE v33; // [rsp+98h] [rbp-20h] BYREF
  Win32_BaseService *v34; // [rsp+C0h] [rbp+8h] BYREF
  bool v35; // [rsp+D0h] [rbp+18h] BYREF

  v34 = this;
  CHString::CHString((CHString *)v31);
  if ( !a3 || !a4 )
  {
    ServiceStatus = -2147217400;
    goto LABEL_42;
  }
  CHString::CHString((CHString *)v27);
  pcbBytesNeeded = 0;
  v35 = 0;
  LOBYTE(v34) = 0;
  ServiceStatus = Win32_BaseService::GetServiceStatus(
                    v8,
                    a2,
                    (struct CHString *)v27,
                    &pcbBytesNeeded,
                    &v35,
                    (bool *)&v34);
  if ( ServiceStatus < 0 )
    goto LABEL_40;
  CHString::CHString((CHString *)v26);
  a5 = 0;
  v25 = 0;
  if ( !CInstance::GetStatus(a3, L"StartMode", (bool *)&a5, &v25) )
  {
    CInstance::SetDWORD(a4, L"ReturnValue", 0x15u);
    CHString::~CHString((CHString *)v26);
LABEL_40:
    ServiceStatus = -2147217404;
    goto LABEL_37;
  }
  if ( a5
    && v25 == 8
    && CInstance::GetCHString(a3, L"StartMode", (struct CHString *)v26)
    && !CHString::IsEmpty((CHString *)v26) )
  {
    if ( !CHString::CompareNoCase((CHString *)v26, L"Boot") )
    {
      v10 = 0;
LABEL_19:
      v12 = OpenSCManagerW(0, 0, 0xAu);
      v33 = v12;
      if ( v12 )
      {
        v13 = (const WCHAR *)CHString::operator unsigned short const *(v27);
        v14 = OpenServiceW(v12, v13, 3u);
        v16 = v14;
        v32 = v14;
        if ( v14 )
        {
          pcbBytesNeeded = 0;
          v17 = 0;
          v30 = 0;
          try
          {
            v28 = QueryServiceConfigW(v14, 0, 0, &pcbBytesNeeded);
            if ( !v28 )
            {
              if ( GetLastError() != 122 )
                goto LABEL_29;
              v19 = (struct _QUERY_SERVICE_CONFIGW *)operator new(pcbBytesNeeded);
              v17 = v19;
              v30 = v19;
              if ( !v19 )
              {
                pExceptionObject = 0;
                throw (CHeap_Exception *)&pExceptionObject;
              }
              v28 = QueryServiceConfigW(v16, v19, pcbBytesNeeded, &pcbBytesNeeded);
              if ( !v28 )
                goto LABEL_29;
            }
            if ( ChangeServiceConfigW(
                   v16,
                   v17->dwServiceType,
                   v10,
                   v17->dwErrorControl,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0,
                   v17->lpDisplayName) )
            {
              ServiceErrorCode = 0;
            }
            else
            {
LABEL_29:
              ServiceErrorCode = Win32_BaseService::GetServiceErrorCode(v18);
            }
            CInstance::SetDWORD(a4, L"ReturnValue", ServiceErrorCode);
          }
          catch ( ... )
          {
            operator delete(v30);
            throw;
          }
          operator delete(v17);
        }
        else
        {
          v21 = Win32_BaseService::GetServiceErrorCode(v15);
          CInstance::SetDWORD(a4, L"ReturnValue", v21);
        }
        SmartCloseServiceHandle::~SmartCloseServiceHandle(&v32);
      }
      else
      {
        v22 = Win32_BaseService::GetServiceErrorCode(v11);
        CInstance::SetDWORD(a4, L"ReturnValue", v22);
      }
      ServiceStatus = 0;
      SmartCloseServiceHandle::~SmartCloseServiceHandle(&v33);
      goto LABEL_36;
    }
    if ( !CHString::CompareNoCase((CHString *)v26, L"System") )
    {
      v10 = 1;
      goto LABEL_19;
    }
    if ( !CHString::CompareNoCase((CHString *)v26, L"Automatic") )
    {
      v10 = 2;
      goto LABEL_19;
    }
    if ( !CHString::CompareNoCase((CHString *)v26, L"Manual") )
    {
      v10 = 3;
      goto LABEL_19;
    }
    if ( !CHString::CompareNoCase((CHString *)v26, L"Disabled") )
    {
      v10 = 4;
      goto LABEL_19;
    }
  }
  CInstance::SetDWORD(a4, L"ReturnValue", 0x15u);
LABEL_36:
  CHString::~CHString((CHString *)v26);
LABEL_37:
  CHString::~CHString((CHString *)v27);
LABEL_42:
  CHString::~CHString((CHString *)v31);
  return (unsigned int)ServiceStatus;
}

```

## disassembly

```asm
0x180097054  mov     rax, rsp
0x180097057  mov     [rax+10h], rbx
0x18009705b  mov     [rax+20h], rsi
0x18009705f  mov     [rax+8], rcx
0x180097063  push    rdi
0x180097064  push    r14
0x180097066  push    r15
0x180097068  sub     rsp, 0A0h
0x18009706f  mov     rdi, r9
0x180097072  mov     rsi, r8
0x180097075  mov     rbx, rdx
0x180097078  lea     rcx, [rax-30h]
0x18009707c  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180097082  nop
0x180097083  xor     r15d, r15d
0x180097086  test    rsi, rsi
0x180097089  jz      loc_1800973EC
0x18009708f  test    rdi, rdi
0x180097092  jz      loc_1800973EC
0x180097098  lea     rcx, [rsp+0B8h+var_48]
0x18009709d  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800970a3  nop
0x1800970a4  mov     [rsp+0B8h+pcbBytesNeeded], r15d
0x1800970a9  mov     [rsp+0B8h+arg_10], r15b
0x1800970b1  mov     byte ptr [rsp+0B8h+arg_0], r15b
0x1800970b9  lea     rax, [rsp+0B8h+arg_0]
0x1800970c1  mov     [rsp+0B8h+lpLoadOrderGroup], rax; bool *
0x1800970c6  lea     rax, [rsp+0B8h+arg_10]
0x1800970ce  mov     [rsp+0B8h+lpBinaryPathName], rax; bool *
0x1800970d3  lea     r9, [rsp+0B8h+pcbBytesNeeded]; unsigned int *
0x1800970d8  lea     r8, [rsp+0B8h+var_48]; struct CHString *
0x1800970dd  mov     rdx, rbx; struct CInstance *
0x1800970e0  call    ?GetServiceStatus@Win32_BaseService@@IEAAJAEBVCInstance@@AEAVCHString@@AEAKAEA_N3@Z; Win32_BaseService::GetServiceStatus(CInstance const &,CHString &,ulong &,bool &,bool &)
0x1800970e5  mov     ebx, eax
0x1800970e7  test    eax, eax
0x1800970e9  js      loc_1800973E5
0x1800970ef  lea     rcx, [rsp+0B8h+var_50]
0x1800970f4  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800970fa  nop
0x1800970fb  mov     byte ptr [rsp+0B8h+arg_20], r15b
0x180097103  mov     [rsp+0B8h+var_54], r15w
0x180097109  lea     r9, [rsp+0B8h+var_54]
0x18009710e  lea     r8, [rsp+0B8h+arg_20]
0x180097116  lea     rdx, aStartmode; "StartMode"
0x18009711d  mov     rcx, rsi
0x180097120  call    cs:__imp_?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z; CInstance::GetStatus(ushort const *,bool &,ushort &)
0x180097126  test    al, al
0x180097128  jz      loc_1800973C3
0x18009712e  cmp     byte ptr [rsp+0B8h+arg_20], r15b
0x180097136  jz      loc_1800973AB
0x18009713c  cmp     [rsp+0B8h+var_54], 8
0x180097142  jnz     loc_1800973AB
0x180097148  lea     r8, [rsp+0B8h+var_50]
0x18009714d  lea     rdx, aStartmode; "StartMode"
0x180097154  mov     rcx, rsi
0x180097157  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x18009715d  test    al, al
0x18009715f  jz      loc_1800973AB
0x180097165  lea     rcx, [rsp+0B8h+var_50]
0x18009716a  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x180097170  test    eax, eax
0x180097172  jnz     loc_1800973AB
0x180097178  lea     rdx, aBoot; "Boot"
0x18009717f  lea     rcx, [rsp+0B8h+var_50]
0x180097184  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x18009718a  test    eax, eax
0x18009718c  jnz     short loc_180097193
0x18009718e  mov     esi, r15d
0x180097191  jmp     short loc_180097201
0x180097193  lea     rdx, aSystem_0; "System"
0x18009719a  lea     rcx, [rsp+0B8h+var_50]
0x18009719f  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800971a5  test    eax, eax
0x1800971a7  jnz     short loc_1800971AE
0x1800971a9  lea     esi, [rax+1]
0x1800971ac  jmp     short loc_180097201
0x1800971ae  lea     rdx, aAutomatic; "Automatic"
0x1800971b5  lea     rcx, [rsp+0B8h+var_50]
0x1800971ba  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800971c0  test    eax, eax
0x1800971c2  jnz     short loc_1800971C9
0x1800971c4  lea     esi, [rax+2]
0x1800971c7  jmp     short loc_180097201
0x1800971c9  lea     rdx, aManual; "Manual"
0x1800971d0  lea     rcx, [rsp+0B8h+var_50]
0x1800971d5  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800971db  test    eax, eax
0x1800971dd  jnz     short loc_1800971E4
0x1800971df  lea     esi, [rax+3]
0x1800971e2  jmp     short loc_180097201
0x1800971e4  lea     rdx, aDisabled; "Disabled"
0x1800971eb  lea     rcx, [rsp+0B8h+var_50]
0x1800971f0  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800971f6  test    eax, eax
0x1800971f8  jnz     loc_1800973AB
0x1800971fe  lea     esi, [rax+4]
0x180097201  xor     edx, edx; lpDatabaseName
0x180097203  xor     ecx, ecx; lpMachineName
0x180097205  lea     r8d, [rdx+0Ah]; dwDesiredAccess
0x180097209  call    cs:__imp_OpenSCManagerW
0x18009720f  mov     rbx, rax
0x180097212  mov     [rsp+0B8h+var_20], rax
0x18009721a  test    rax, rax
0x18009721d  jz      loc_180097368
0x180097223  lea     rcx, [rsp+0B8h+var_48]
0x180097228  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18009722e  mov     r8d, 3; dwDesiredAccess
0x180097234  mov     rdx, rax; lpServiceName
0x180097237  mov     rcx, rbx; hSCManager
0x18009723a  call    cs:__imp_OpenServiceW
0x180097240  mov     r14, rax
0x180097243  mov     [rsp+0B8h+var_28], rax
0x18009724b  test    rax, rax
0x18009724e  jz      loc_180097340
0x180097254  mov     [rsp+0B8h+pcbBytesNeeded], r15d
0x180097259  mov     rbx, r15
0x18009725c  mov     [rsp+0B8h+var_38], rbx
0x180097264  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x180097269  xor     r8d, r8d; cbBufSize
0x18009726c  xor     edx, edx; lpServiceConfig
0x18009726e  mov     rcx, rax; hService
0x180097271  call    cs:__imp_QueryServiceConfigW
0x180097277  mov     [rsp+0B8h+var_40], eax
0x18009727b  test    eax, eax
0x18009727d  jnz     short loc_1800972C5
0x18009727f  call    cs:__imp_GetLastError
0x180097285  cmp     eax, 7Ah ; 'z'
0x180097288  jnz     loc_18009731D
0x18009728e  mov     ecx, [rsp+0B8h+pcbBytesNeeded]; unsigned __int64
0x180097292  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180097297  mov     rbx, rax
0x18009729a  mov     [rsp+0B8h+var_38], rax
0x1800972a2  test    rax, rax
0x1800972a5  jz      short loc_180097307
0x1800972a7  lea     r9, [rsp+0B8h+pcbBytesNeeded]; pcbBytesNeeded
0x1800972ac  mov     r8d, [rsp+0B8h+pcbBytesNeeded]; cbBufSize
0x1800972b1  mov     rdx, rax; lpServiceConfig
0x1800972b4  mov     rcx, r14; hService
0x1800972b7  call    cs:__imp_QueryServiceConfigW
0x1800972bd  mov     [rsp+0B8h+var_40], eax
0x1800972c1  test    eax, eax
0x1800972c3  jz      short loc_18009731D
0x1800972c5  mov     rax, [rbx+38h]
0x1800972c9  mov     [rsp+0B8h+lpDisplayName], rax; lpDisplayName
0x1800972ce  mov     [rsp+0B8h+lpPassword], r15; lpPassword
0x1800972d3  mov     [rsp+0B8h+lpServiceStartName], r15; lpServiceStartName
0x1800972d8  mov     [rsp+0B8h+lpDependencies], r15; lpDependencies
0x1800972dd  mov     [rsp+0B8h+lpdwTagId], r15; lpdwTagId
0x1800972e2  mov     [rsp+0B8h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x1800972e7  mov     [rsp+0B8h+lpBinaryPathName], r15; lpBinaryPathName
0x1800972ec  mov     r9d, [rbx+8]; dwErrorControl
0x1800972f0  mov     r8d, esi; dwStartType
0x1800972f3  mov     edx, [rbx]; dwServiceType
0x1800972f5  mov     rcx, r14; hService
0x1800972f8  call    cs:__imp_ChangeServiceConfigW
0x1800972fe  test    eax, eax
0x180097300  jz      short loc_18009731D
0x180097302  xor     r8d, r8d
0x180097305  jmp     short loc_180097325
0x180097307  mov     [rsp+0B8h+pExceptionObject], r15d
0x18009730c  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x180097313  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180097318  call    _CxxThrowException_0
0x18009731d  call    ?GetServiceErrorCode@Win32_BaseService@@IEAAKXZ; Win32_BaseService::GetServiceErrorCode(void)
0x180097322  mov     r8d, eax
0x180097325  lea     rdx, aReturnvalue; "ReturnValue"
0x18009732c  mov     rcx, rdi
0x18009732f  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180097335  nop
0x180097336  mov     rcx, rbx; void *
0x180097339  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009733e  jmp     short loc_180097359
0x180097340  call    ?GetServiceErrorCode@Win32_BaseService@@IEAAKXZ; Win32_BaseService::GetServiceErrorCode(void)
0x180097345  mov     r8d, eax
0x180097348  lea     rdx, aReturnvalue; "ReturnValue"
0x18009734f  mov     rcx, rdi
0x180097352  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180097358  nop
0x180097359  lea     rcx, [rsp+0B8h+var_28]; this
0x180097361  call    ??1SmartCloseServiceHandle@@QEAA@XZ; SmartCloseServiceHandle::~SmartCloseServiceHandle(void)
0x180097366  jmp     short loc_180097381
0x180097368  call    ?GetServiceErrorCode@Win32_BaseService@@IEAAKXZ; Win32_BaseService::GetServiceErrorCode(void)
0x18009736d  mov     r8d, eax
0x180097370  lea     rdx, aReturnvalue; "ReturnValue"
0x180097377  mov     rcx, rdi
0x18009737a  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180097380  nop
0x180097381  mov     ebx, r15d
0x180097384  lea     rcx, [rsp+0B8h+var_20]; this
0x18009738c  call    ??1SmartCloseServiceHandle@@QEAA@XZ; SmartCloseServiceHandle::~SmartCloseServiceHandle(void)
0x180097391  nop
0x180097392  lea     rcx, [rsp+0B8h+var_50]
0x180097397  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18009739d  nop
0x18009739e  lea     rcx, [rsp+0B8h+var_48]
0x1800973a3  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800973a9  jmp     short loc_1800973F1
0x1800973ab  mov     r8d, 15h
0x1800973b1  lea     rdx, aReturnvalue; "ReturnValue"
0x1800973b8  mov     rcx, rdi
0x1800973bb  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800973c1  jmp     short loc_180097392
0x1800973c3  mov     r8d, 15h
0x1800973c9  lea     rdx, aReturnvalue; "ReturnValue"
0x1800973d0  mov     rcx, rdi
0x1800973d3  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800973d9  nop
0x1800973da  lea     rcx, [rsp+0B8h+var_50]
0x1800973df  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800973e5  mov     ebx, 80041004h
0x1800973ea  jmp     short loc_18009739E
0x1800973ec  mov     ebx, 80041008h
0x1800973f1  lea     rcx, [rsp+0B8h+var_30]
0x1800973f9  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800973ff  mov     eax, ebx
0x180097401  lea     r11, [rsp+0B8h+var_18]
0x180097409  mov     rbx, [r11+28h]
0x18009740d  mov     rsi, [r11+38h]
0x180097411  mov     rsp, r11
0x180097414  pop     r15
0x180097416  pop     r14
0x180097418  pop     rdi
0x180097419  retn
```
