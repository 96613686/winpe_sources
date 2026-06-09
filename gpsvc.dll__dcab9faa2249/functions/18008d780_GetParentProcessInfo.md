# GetParentProcessInfo

- ea: `0x18008d780`
- end: `0x18008db4c`
- name: `GetParentProcessInfo`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18008edac`

## callees

- `0x180003770`
- `0x18000a52c`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x18007dec4`
- `0x18008d780`
- `0x18008e434`
- `0x18008f6f8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d958`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d9ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d958`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d9ff`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008d7de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008d910`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008d9ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008dad6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008d7de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008d910`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008d9ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008dad6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008d936`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008d936`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008d890`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008d890`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008d8d7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008d8d7`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008d7e9`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18008d7e9`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18008d83d`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18008d87a`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18008d83d`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18008d87a`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18008d826`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18008d860`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18008d826`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x18008d860`

## string_xrefs

- `0x18008da87`: `RPC Attribution: Service enumeration failed for svchost.exe PID %lu`
- `0x18008daaf`: `RPC Attribution: Service enumeration failed for svchost.exe PID %lu`
- `0x18008dac9`: `Access Denied (svchost.exe - service unknown)`
- `0x18008dade`: `Access Denied (%ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall GetParentProcessInfo(int a1, unsigned int *a2)
{
  unsigned __int16 *v4; // rsi
  char *Toolhelp32Snapshot; // rbx
  BOOL i; // eax
  BOOL j; // eax
  HANDLE v8; // rbx
  __int64 v9; // rax
  wchar_t *v10; // rax
  WCHAR *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r8
  const wchar_t *v14; // r8
  bool v15; // bl
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  void *v18; // [rsp+38h] [rbp-C8h] BYREF
  void *v19; // [rsp+40h] [rbp-C0h] BYREF
  PROCESSENTRY32W pe; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t ExeName[264]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v22[528]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v23[1024]; // [rsp+6B0h] [rbp+5B0h] BYREF

  if ( !a2 )
    return 0;
  *a2 = 0;
  v4 = (unsigned __int16 *)(a2 + 1);
  _o_wcscpy_s(a2 + 1, 1300, L"Unknown");
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  v18 = Toolhelp32Snapshot;
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    XHandle::~XHandle(&v18);
    return 0;
  }
  memset_0(&pe.cntUsage, 0, 0x234u);
  pe.dwSize = 568;
  for ( i = Process32FirstW(Toolhelp32Snapshot, &pe); i; i = Process32NextW(Toolhelp32Snapshot, &pe) )
  {
    if ( pe.th32ProcessID == a1 )
    {
      *a2 = pe.th32ParentProcessID;
      break;
    }
  }
  if ( *a2 )
  {
    for ( j = Process32FirstW(Toolhelp32Snapshot, &pe); ; j = Process32NextW(Toolhelp32Snapshot, &pe) )
    {
      if ( !j )
        goto LABEL_46;
      if ( pe.th32ProcessID == *a2 )
        break;
    }
    v8 = OpenProcess(0x1000u, 0, *a2);
    v19 = v8;
    if ( v8 )
    {
      memset_0(ExeName, 0, 0x208u);
      dwSize = 260;
      if ( !QueryFullProcessImageNameW(v8, 0, ExeName, &dwSize) )
        goto LABEL_28;
      v9 = -1;
      do
        ++v9;
      while ( ExeName[v9] );
      if ( v9 )
      {
        _o_wcscpy_s(v4, 1300, ExeName);
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::GetImpl'::`2'::impl) )
        {
          v10 = wcsrchr(ExeName, 0x5Cu);
          if ( v10 )
            v11 = v10 + 1;
          else
            v11 = ExeName;
          if ( !(unsigned int)_o__wcsicmp(v11, L"svchost.exe") )
          {
            memset_0(v23, 0, sizeof(v23));
            if ( (unsigned int)GetServicesInProcess(*a2, v23, v12) )
            {
              if ( v23[0] )
              {
                _o_wcscpy_s(v22, 260, v4);
                StringCchPrintfW(v4, 0x514u, L"%ws [%ws]", v22, v23);
              }
            }
          }
        }
      }
      else
      {
LABEL_28:
        if ( pe.szExeFile[0] )
          swprintf_s(v4, 0x514u, L"Unknown (%ws)", pe.szExeFile);
      }
      goto LABEL_45;
    }
    if ( (unsigned int)_o__wcsicmp(pe.szExeFile, L"svchost.exe") )
    {
      swprintf_s(v4, 0x514u, L"Access Denied (%ws)", pe.szExeFile);
      goto LABEL_45;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::GetImpl'::`2'::impl) )
    {
      memset_0(v23, 0, sizeof(v23));
      if ( (unsigned int)GetServicesInProcess(*a2, v23, v13) && v23[0] )
      {
        StringCchPrintfW(v4, 0x514u, L"svchost.exe [%ws]", v23);
LABEL_45:
        XHandle::~XHandle(&v19);
        goto LABEL_46;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"RPC Attribution: Service enumeration failed for svchost.exe PID %lu", *a2);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"RPC Attribution: Service enumeration failed for svchost.exe PID %lu", *a2);
        }
      }
      v14 = L"svchost.exe";
    }
    else
    {
      v14 = L"Access Denied (svchost.exe - service unknown)";
    }
    _o_wcscpy_s(v4, 1300, v14);
    goto LABEL_45;
  }
LABEL_46:
  v15 = *a2 != 0;
  XHandle::~XHandle(&v18);
  return v15;
}

```

## disassembly

```asm
0x18008d780  mov     [rsp-8+arg_0], rbx
0x18008d785  mov     [rsp-8+arg_10], rsi
0x18008d78a  push    rbp
0x18008d78b  push    rdi
0x18008d78c  push    r12
0x18008d78e  push    r14
0x18008d790  push    r15
0x18008d792  lea     rbp, [rsp-0DC0h]
0x18008d79a  sub     rsp, 0EC0h
0x18008d7a1  mov     rax, cs:__security_cookie
0x18008d7a8  xor     rax, rsp
0x18008d7ab  mov     [rbp+0DE0h+var_30], rax
0x18008d7b2  mov     rdi, rdx
0x18008d7b5  mov     r14d, ecx
0x18008d7b8  xor     r15d, r15d
0x18008d7bb  test    rdx, rdx
0x18008d7be  jz      loc_18008DB1F
0x18008d7c4  mov     [rdx], r15d
0x18008d7c7  lea     rsi, [rdx+4]
0x18008d7cb  lea     r8, aUnknown_0; "Unknown"
0x18008d7d2  mov     r12d, 514h
0x18008d7d8  mov     edx, r12d
0x18008d7db  mov     rcx, rsi
0x18008d7de  call    cs:__imp__o_wcscpy_s
0x18008d7e4  xor     edx, edx; th32ProcessID
0x18008d7e6  lea     ecx, [rdx+2]; dwFlags
0x18008d7e9  call    cs:__imp_CreateToolhelp32Snapshot
0x18008d7ef  mov     rbx, rax
0x18008d7f2  mov     [rsp+0EE0h+var_EA8], rax
0x18008d7f7  dec     rax
0x18008d7fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008d7fe  ja      loc_18008DB15
0x18008d804  xor     edx, edx; Val
0x18008d806  mov     r8d, 234h; Size
0x18008d80c  lea     rcx, [rsp+0EE0h+pe.cntUsage]; void *
0x18008d811  call    memset_0
0x18008d816  mov     [rsp+0EE0h+pe.dwSize], 238h
0x18008d81e  lea     rdx, [rsp+0EE0h+pe]; lppe
0x18008d823  mov     rcx, rbx; hSnapshot
0x18008d826  call    cs:__imp_Process32FirstW
0x18008d82c  jmp     short loc_18008D843
0x18008d82e  cmp     [rsp+0EE0h+pe.th32ProcessID], r14d
0x18008d833  jz      short loc_18008D849
0x18008d835  lea     rdx, [rsp+0EE0h+pe]; lppe
0x18008d83a  mov     rcx, rbx; hSnapshot
0x18008d83d  call    cs:__imp_Process32NextW
0x18008d843  test    eax, eax
0x18008d845  jnz     short loc_18008D82E
0x18008d847  jmp     short loc_18008D84F
0x18008d849  mov     eax, [rsp+0EE0h+pe.th32ParentProcessID]
0x18008d84d  mov     [rdi], eax
0x18008d84f  cmp     [rdi], r15d
0x18008d852  jz      loc_18008DB01
0x18008d858  lea     rdx, [rsp+0EE0h+pe]; lppe
0x18008d85d  mov     rcx, rbx; hSnapshot
0x18008d860  call    cs:__imp_Process32FirstW
0x18008d866  jmp     short loc_18008D880
0x18008d868  mov     r8d, [rdi]; dwProcessId
0x18008d86b  cmp     [rsp+0EE0h+pe.th32ProcessID], r8d
0x18008d870  jz      short loc_18008D889
0x18008d872  lea     rdx, [rsp+0EE0h+pe]; lppe
0x18008d877  mov     rcx, rbx; hSnapshot
0x18008d87a  call    cs:__imp_Process32NextW
0x18008d880  test    eax, eax
0x18008d882  jnz     short loc_18008D868
0x18008d884  jmp     loc_18008DB01
0x18008d889  xor     edx, edx; bInheritHandle
0x18008d88b  mov     ecx, 1000h; dwDesiredAccess
0x18008d890  call    cs:__imp_OpenProcess
0x18008d896  mov     rbx, rax
0x18008d899  mov     [rsp+0EE0h+var_EA0], rax
0x18008d89e  test    rax, rax
0x18008d8a1  jz      loc_18008D9F3
0x18008d8a7  xor     edx, edx; Val
0x18008d8a9  mov     r8d, 208h; Size
0x18008d8af  lea     rcx, [rbp+0DE0h+ExeName]; void *
0x18008d8b6  call    memset_0
0x18008d8bb  mov     r14d, 104h
0x18008d8c1  mov     [rsp+0EE0h+dwSize], r14d
0x18008d8c6  lea     r9, [rsp+0EE0h+dwSize]; lpdwSize
0x18008d8cb  lea     r8, [rbp+0DE0h+ExeName]; lpExeName
0x18008d8d2  xor     edx, edx; dwFlags
0x18008d8d4  mov     rcx, rbx; hProcess
0x18008d8d7  call    cs:__imp_QueryFullProcessImageNameW
0x18008d8dd  test    eax, eax
0x18008d8df  jz      loc_18008D9DB
0x18008d8e5  lea     rcx, [rbp+0DE0h+ExeName]
0x18008d8ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008d8f0  inc     rax
0x18008d8f3  cmp     [rcx+rax*2], r15w
0x18008d8f8  jnz     short loc_18008D8F0
0x18008d8fa  test    rax, rax
0x18008d8fd  jz      loc_18008D9DB
0x18008d903  lea     r8, [rbp+0DE0h+ExeName]
0x18008d90a  mov     rdx, r12
0x18008d90d  mov     rcx, rsi
0x18008d910  call    cs:__imp__o_wcscpy_s
0x18008d916  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::GetImpl(void)'::`2'::impl
0x18008d91d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::__private_IsEnabled(void)
0x18008d922  test    al, al
0x18008d924  jz      loc_18008DAF6
0x18008d92a  mov     edx, 5Ch ; '\'; Ch
0x18008d92f  lea     rcx, [rbp+0DE0h+ExeName]; Str
0x18008d936  call    cs:__imp_wcsrchr
0x18008d93c  test    rax, rax
0x18008d93f  jz      short loc_18008D947
0x18008d941  add     rax, 2
0x18008d945  jmp     short loc_18008D94E
0x18008d947  lea     rax, [rbp+0DE0h+ExeName]
0x18008d94e  lea     rdx, aSvchostExe; "svchost.exe"
0x18008d955  mov     rcx, rax
0x18008d958  call    cs:__imp__o__wcsicmp
0x18008d95e  test    eax, eax
0x18008d960  jnz     loc_18008DAF6
0x18008d966  xor     edx, edx; Val
0x18008d968  mov     r8d, 800h; Size
0x18008d96e  lea     rcx, [rbp+0DE0h+var_830]; void *
0x18008d975  call    memset_0
0x18008d97a  lea     rdx, [rbp+0DE0h+var_830]
0x18008d981  mov     ecx, [rdi]
0x18008d983  call    GetServicesInProcess
0x18008d988  test    eax, eax
0x18008d98a  jz      loc_18008DAF6
0x18008d990  cmp     [rbp+0DE0h+var_830], r15w
0x18008d998  jz      loc_18008DAF6
0x18008d99e  mov     r8, rsi
0x18008d9a1  mov     rdx, r14
0x18008d9a4  lea     rcx, [rbp+0DE0h+var_A40]
0x18008d9ab  call    cs:__imp__o_wcscpy_s
0x18008d9b1  lea     rax, [rbp+0DE0h+var_830]
0x18008d9b8  mov     [rsp+0EE0h+var_EC0], rax
0x18008d9bd  lea     r9, [rbp+0DE0h+var_A40]
0x18008d9c4  lea     r8, aWsWs; "%ws [%ws]"
0x18008d9cb  mov     rdx, r12; unsigned __int64
0x18008d9ce  mov     rcx, rsi; unsigned __int16 *
0x18008d9d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008d9d6  jmp     loc_18008DAF6
0x18008d9db  cmp     [rsp+0EE0h+pe.szExeFile], r15w
0x18008d9e1  jz      loc_18008DAF6
0x18008d9e7  lea     r8, aUnknownWs; "Unknown (%ws)"
0x18008d9ee  jmp     loc_18008DAE5
0x18008d9f3  lea     rdx, aSvchostExe; "svchost.exe"
0x18008d9fa  lea     rcx, [rsp+0EE0h+pe.szExeFile]
0x18008d9ff  call    cs:__imp__o__wcsicmp
0x18008da05  test    eax, eax
0x18008da07  jnz     loc_18008DADE
0x18008da0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::GetImpl(void)'::`2'::impl
0x18008da14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPUpdateSvchostDetails>::__private_IsEnabled(void)
0x18008da19  test    al, al
0x18008da1b  jz      loc_18008DAC9
0x18008da21  xor     edx, edx; Val
0x18008da23  mov     r8d, 800h; Size
0x18008da29  lea     rcx, [rbp+0DE0h+var_830]; void *
0x18008da30  call    memset_0
0x18008da35  lea     rdx, [rbp+0DE0h+var_830]
0x18008da3c  mov     ecx, [rdi]
0x18008da3e  call    GetServicesInProcess
0x18008da43  test    eax, eax
0x18008da45  jz      short loc_18008DA6F
0x18008da47  cmp     [rbp+0DE0h+var_830], r15w
0x18008da4f  jz      short loc_18008DA6F
0x18008da51  lea     r9, [rbp+0DE0h+var_830]
0x18008da58  lea     r8, aSvchostExeWs; "svchost.exe [%ws]"
0x18008da5f  mov     rdx, r12; unsigned __int64
0x18008da62  mov     rcx, rsi; unsigned __int16 *
0x18008da65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008da6a  jmp     loc_18008DAF6
0x18008da6f  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18008da76  jz      short loc_18008DAC0
0x18008da78  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008da7f  test    rax, rax
0x18008da82  jz      short loc_18008DA9A
0x18008da84  mov     r8d, [rdi]
0x18008da87  lea     rdx, aRpcAttribution_1; "RPC Attribution: Service enumeration fa"...
0x18008da8e  mov     ecx, 2
0x18008da93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008da98  jmp     short loc_18008DAC0
0x18008da9a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18008daa1  jz      short loc_18008DAC0
0x18008daa3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008daaa  jz      short loc_18008DAC0
0x18008daac  mov     r8d, [rdi]
0x18008daaf  lea     rdx, aRpcAttribution_1; "RPC Attribution: Service enumeration fa"...
0x18008dab6  mov     ecx, 2; unsigned int
0x18008dabb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008dac0  lea     r8, aSvchostExe; "svchost.exe"
0x18008dac7  jmp     short loc_18008DAD0
0x18008dac9  lea     r8, aAccessDeniedSv; "Access Denied (svchost.exe - service un"...
0x18008dad0  mov     rdx, r12
0x18008dad3  mov     rcx, rsi
0x18008dad6  call    cs:__imp__o_wcscpy_s
0x18008dadc  jmp     short loc_18008DAF6
0x18008dade  lea     r8, aAccessDeniedWs; "Access Denied (%ws)"
0x18008dae5  lea     r9, [rsp+0EE0h+pe.szExeFile]
0x18008daea  mov     rdx, r12; BufferCount
0x18008daed  mov     rcx, rsi; Buffer
0x18008daf0  call    swprintf_s
0x18008daf5  nop
0x18008daf6  lea     rcx, [rsp+0EE0h+var_EA0]; this
0x18008dafb  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18008db00  nop
0x18008db01  cmp     [rdi], r15d
0x18008db04  setnz   bl
0x18008db07  lea     rcx, [rsp+0EE0h+var_EA8]; this
0x18008db0c  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18008db11  mov     al, bl
0x18008db13  jmp     short loc_18008DB21
0x18008db15  lea     rcx, [rsp+0EE0h+var_EA8]; this
0x18008db1a  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18008db1f  xor     al, al
0x18008db21  mov     rcx, [rbp+0DE0h+var_30]
0x18008db28  xor     rcx, rsp; StackCookie
0x18008db2b  call    __security_check_cookie
0x18008db30  lea     r11, [rsp+0EE0h+var_20]
0x18008db38  mov     rbx, [r11+30h]
0x18008db3c  mov     rsi, [r11+40h]
0x18008db40  mov     rsp, r11
0x18008db43  pop     r15
0x18008db45  pop     r14
0x18008db47  pop     r12
0x18008db49  pop     rdi
0x18008db4a  pop     rbp
0x18008db4b  retn
```
