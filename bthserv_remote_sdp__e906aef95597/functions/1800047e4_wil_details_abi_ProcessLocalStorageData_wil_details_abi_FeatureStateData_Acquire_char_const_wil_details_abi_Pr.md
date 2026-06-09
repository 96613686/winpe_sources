# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800047e4`
- end: `0x180004be9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004dd4`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x1800038b4`
- `0x180004014`
- `0x1800047e4`
- `0x180004bf0`
- `0x180005044`
- `0x1800058f8`
- `0x180006764`
- `0x180007fb4`
- `0x180008af8`
- `0x18000902c`
- `0x180009944`
- `0x180009ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004861`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004861`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004935`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b16`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004935`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b16`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004ae5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004ae5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004897`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004897`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000481a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000481a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000494c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000494c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b32`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // r14
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  HANDLE v21; // rbx
  char *v22; // rax
  char *v23; // rdi
  unsigned int v24; // esi
  int v25; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  __int64 v31; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v40; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xC37, v10, v11);
    v12 = v6;
  }
  v41 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v15, v36);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v15, v37);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v41);
  if ( 4 * v41 )
  {
    *a2 = v20;
    v21 = hHandle;
    *(_DWORD *)*a2 = *v20 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v22 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v23 = v22;
  if ( v22 )
  {
    v40 = 0;
    v25 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v40,
            (char *)Name,
            (unsigned __int64)v22);
    v24 = v25;
    if ( v25 >= 0 )
    {
      *((_QWORD *)v23 + 2) = v40;
      v31 = *((_QWORD *)&v40 + 1);
      *((_QWORD *)v23 + 1) = v6;
      v21 = 0;
      v40 = 0u;
      *((_QWORD *)v23 + 3) = v31;
      *(_DWORD *)v23 = 1;
      memset_0(v23 + 40, 0, 0x108u);
      *((_QWORD *)v23 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 232), 0, 0);
      *((_QWORD *)v23 + 34) = 0;
      *((_QWORD *)v23 + 35) = 0;
      *((_QWORD *)v23 + 36) = 0;
      *((_QWORD *)v23 + 37) = 0;
      *a2 = v23;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v40);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v32, v33);
      if ( v21 && !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v40);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)v24, v38);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v27, v28);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v29, v30);
  return v24;
}

```

## disassembly

```asm
0x1800047e4  mov     [rsp-8+arg_10], rbx
0x1800047e9  push    rbp
0x1800047ea  push    rsi
0x1800047eb  push    rdi
0x1800047ec  push    r14
0x1800047ee  push    r15
0x1800047f0  lea     rbp, [rsp-170h]
0x1800047f8  sub     rsp, 270h
0x1800047ff  mov     rax, cs:__security_cookie
0x180004806  xor     rax, rsp
0x180004809  mov     [rbp+190h+var_30], rax
0x180004810  and     qword ptr [rdx], 0
0x180004814  mov     r15, rdx
0x180004817  mov     rbx, rcx
0x18000481a  call    cs:__imp_GetCurrentProcessId
0x180004821  nop     dword ptr [rax+rax+00h]
0x180004826  mov     esi, 130h
0x18000482b  mov     [rsp+290h+var_268], rbx
0x180004830  mov     r9d, eax
0x180004833  mov     [rsp+290h+var_270], esi; int
0x180004837  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000483e  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180004843  lea     edx, [rsi-2Ch]; unsigned __int64
0x180004846  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000484b  and     [rsp+290h+hHandle], 0
0x180004851  lea     rdx, [rsp+290h+Name]; lpName
0x180004856  mov     r9d, 1F0001h; dwDesiredAccess
0x18000485c  xor     r8d, r8d; dwFlags
0x18000485f  xor     ecx, ecx; lpMutexAttributes
0x180004861  call    cs:__imp_CreateMutexExW
0x180004868  nop     dword ptr [rax+rax+00h]
0x18000486d  mov     rdx, rax
0x180004870  lea     rcx, [rsp+290h+hHandle]
0x180004875  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000487a  mov     rbx, [rsp+290h+hHandle]
0x18000487f  test    rbx, rbx
0x180004882  jnz     short loc_18000488E
0x180004884  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004889  jmp     loc_180004B44
0x18000488e  xor     r8d, r8d; bAlertable
0x180004891  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004894  mov     rcx, rbx; hHandle
0x180004897  call    cs:__imp_WaitForSingleObjectEx
0x18000489e  nop     dword ptr [rax+rax+00h]
0x1800048a3  cmp     eax, 102h
0x1800048a8  jz      short loc_1800048BA
0x1800048aa  test    eax, 0FFFFFF7Fh
0x1800048af  jnz     loc_180004B7D
0x1800048b5  mov     r14, rbx
0x1800048b8  jmp     short loc_1800048BD
0x1800048ba  xor     r14d, r14d
0x1800048bd  and     [rsp+290h+var_248], 0
0x1800048c3  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x1800048c8  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800048cd  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800048d2  mov     edi, eax
0x1800048d4  test    eax, eax
0x1800048d6  jns     loc_180004967
0x1800048dc  mov     rcx, [rbp+198h]; this
0x1800048e3  lea     r8, aWil; "wil"
0x1800048ea  mov     r9d, eax; char *
0x1800048ed  mov     edx, 64h ; 'd'; void *
0x1800048f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048f7  mov     rcx, [rbp+198h]; this
0x1800048fe  lea     r8, aWil; "wil"
0x180004905  mov     r9d, edi; char *
0x180004908  mov     edx, 6Dh ; 'm'; void *
0x18000490d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004912  mov     rcx, [rbp+198h]; this
0x180004919  lea     r8, aWil; "wil"
0x180004920  mov     r9d, edi; char *
0x180004923  mov     edx, 12Bh; void *
0x180004928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000492d  test    r14, r14
0x180004930  jz      short loc_180004949
0x180004932  mov     rcx, r14; hMutex
0x180004935  call    cs:__imp_ReleaseMutex
0x18000493c  nop     dword ptr [rax+rax+00h]
0x180004941  test    eax, eax
0x180004943  jz      loc_180004B8F
0x180004949  mov     rcx, rbx; hObject
0x18000494c  call    cs:__imp_CloseHandle
0x180004953  nop     dword ptr [rax+rax+00h]
0x180004958  test    eax, eax
0x18000495a  jz      loc_180004BA1
0x180004960  mov     eax, edi
0x180004962  jmp     loc_180004B44
0x180004967  mov     rax, [rsp+290h+var_248]
0x18000496c  lea     rcx, ds:0[rax*4]
0x180004974  test    rcx, rcx
0x180004977  jz      short loc_18000498F
0x180004979  mov     [r15], rcx
0x18000497c  mov     ecx, [rcx]
0x18000497e  mov     rax, [r15]
0x180004981  inc     ecx
0x180004983  mov     rbx, [rsp+290h+hHandle]
0x180004988  mov     [rax], ecx
0x18000498a  jmp     loc_180004B0E
0x18000498f  and     qword ptr [r15], 0
0x180004993  mov     rdx, rsi; dwBytes
0x180004996  mov     ecx, 8; dwFlags
0x18000499b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800049a0  mov     rdi, rax
0x1800049a3  test    rax, rax
0x1800049a6  jnz     short loc_1800049CA
0x1800049a8  mov     rcx, [rbp+198h]; this
0x1800049af  lea     r8, aWil; "wil"
0x1800049b6  mov     esi, 8007000Eh
0x1800049bb  mov     edx, 148h; void *
0x1800049c0  mov     r9d, esi; char *
0x1800049c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049c8  jmp     short loc_180004A34
0x1800049ca  xorps   xmm0, xmm0
0x1800049cd  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800049d2  mov     r8, rdi; void *
0x1800049d5  lea     rcx, [rsp+290h+var_258]; this
0x1800049da  movdqu  [rsp+290h+var_258], xmm0
0x1800049e0  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800049e5  mov     esi, eax
0x1800049e7  test    eax, eax
0x1800049e9  jns     loc_180004A8E
0x1800049ef  mov     rcx, [rbp+198h]; this
0x1800049f6  lea     r8, aWil; "wil"
0x1800049fd  mov     r9d, eax; char *
0x180004a00  mov     edx, 14Bh; void *
0x180004a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a0a  lea     rcx, [rsp+290h+var_258]; this
0x180004a0f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004a14  call    cs:__imp_GetProcessHeap
0x180004a1b  nop     dword ptr [rax+rax+00h]
0x180004a20  mov     r8, rdi; lpMem
0x180004a23  xor     edx, edx; dwFlags
0x180004a25  mov     rcx, rax; hHeap
0x180004a28  call    cs:__imp_HeapFree
0x180004a2f  nop     dword ptr [rax+rax+00h]
0x180004a34  mov     rcx, [rbp+198h]; this
0x180004a3b  lea     r8, aWil; "wil"
0x180004a42  mov     r9d, esi; char *
0x180004a45  mov     edx, 134h; void *
0x180004a4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a4f  test    r14, r14
0x180004a52  jz      short loc_180004A6B
0x180004a54  mov     rcx, r14; hMutex
0x180004a57  call    cs:__imp_ReleaseMutex
0x180004a5e  nop     dword ptr [rax+rax+00h]
0x180004a63  test    eax, eax
0x180004a65  jz      loc_180004BB3
0x180004a6b  test    rbx, rbx
0x180004a6e  jz      short loc_180004A87
0x180004a70  mov     rcx, rbx; hObject
0x180004a73  call    cs:__imp_CloseHandle
0x180004a7a  nop     dword ptr [rax+rax+00h]
0x180004a7f  test    eax, eax
0x180004a81  jz      loc_180004BC5
0x180004a87  mov     eax, esi
0x180004a89  jmp     loc_180004B44
0x180004a8e  mov     rax, qword ptr [rsp+290h+var_258]
0x180004a93  lea     rcx, [rdi+28h]; void *
0x180004a97  mov     [rdi+10h], rax
0x180004a9b  xor     edx, edx; Val
0x180004a9d  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180004aa2  mov     r8d, 108h; Size
0x180004aa8  mov     [rdi+8], rbx
0x180004aac  xor     ebx, ebx
0x180004aae  and     qword ptr [rsp+290h+var_258], rbx
0x180004ab3  and     qword ptr [rsp+290h+var_258+8], rbx
0x180004ab8  mov     [rdi+18h], rax
0x180004abc  mov     dword ptr [rdi], 1
0x180004ac2  call    memset_0
0x180004ac7  xor     eax, eax
0x180004ac9  lea     rcx, [rdi+28h]; this
0x180004acd  mov     [rdi+20h], rax
0x180004ad1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004ad6  lea     rsi, [rdi+0E8h]
0x180004add  xor     r8d, r8d; Flags
0x180004ae0  mov     rcx, rsi; lpCriticalSection
0x180004ae3  xor     edx, edx; dwSpinCount
0x180004ae5  call    cs:__imp_InitializeCriticalSectionEx
0x180004aec  nop     dword ptr [rax+rax+00h]
0x180004af1  and     [rsi+28h], rbx
0x180004af5  lea     rcx, [rsp+290h+var_258]; this
0x180004afa  and     [rsi+30h], rbx
0x180004afe  and     [rsi+38h], rbx
0x180004b02  and     [rsi+40h], rbx
0x180004b06  mov     [r15], rdi
0x180004b09  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004b0e  test    r14, r14
0x180004b11  jz      short loc_180004B2A
0x180004b13  mov     rcx, r14; hMutex
0x180004b16  call    cs:__imp_ReleaseMutex
0x180004b1d  nop     dword ptr [rax+rax+00h]
0x180004b22  test    eax, eax
0x180004b24  jz      loc_180004BD7
0x180004b2a  test    rbx, rbx
0x180004b2d  jz      short loc_180004B42
0x180004b2f  mov     rcx, rbx; hObject
0x180004b32  call    cs:__imp_CloseHandle
0x180004b39  nop     dword ptr [rax+rax+00h]
0x180004b3e  test    eax, eax
0x180004b40  jz      short loc_180004B6B
0x180004b42  xor     eax, eax
0x180004b44  mov     rcx, [rbp+190h+var_30]
0x180004b4b  xor     rcx, rsp; StackCookie
0x180004b4e  call    __security_check_cookie
0x180004b53  mov     rbx, [rsp+290h+arg_10]
0x180004b5b  add     rsp, 270h
0x180004b62  pop     r15
0x180004b64  pop     r14
0x180004b66  pop     rdi
0x180004b67  pop     rsi
0x180004b68  pop     rbp
0x180004b69  retn
0x180004b6b  mov     rcx, [rbp+198h]; this
0x180004b72  mov     edx, 9DDh; void *
0x180004b77  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b7d  mov     rcx, [rbp+198h]; this
0x180004b84  mov     edx, 0C37h; void *
0x180004b89  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004b8f  mov     rcx, [rbp+198h]; this
0x180004b96  mov     edx, 9E7h; void *
0x180004b9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ba1  mov     rcx, [rbp+198h]; this
0x180004ba8  mov     edx, 9DDh; void *
0x180004bad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004bb3  mov     rcx, [rbp+198h]; this
0x180004bba  mov     edx, 9E7h; void *
0x180004bbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004bc5  mov     rcx, [rbp+198h]; this
0x180004bcc  mov     edx, 9DDh; void *
0x180004bd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004bd7  mov     rcx, [rbp+198h]; this
0x180004bde  mov     edx, 9E7h; void *
0x180004be3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
