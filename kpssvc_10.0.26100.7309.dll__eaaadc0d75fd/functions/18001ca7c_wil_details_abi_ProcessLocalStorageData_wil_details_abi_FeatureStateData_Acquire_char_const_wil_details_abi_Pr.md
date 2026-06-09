# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001ca7c`
- end: `0x18001ce87`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001d064`

## callees

- `0x18001ad2c`
- `0x18001be44`
- `0x18001c400`
- `0x18001ca7c`
- `0x18001ce90`
- `0x18001d2d4`
- `0x18001dd08`
- `0x180023520`
- `0x180024f68`
- `0x180025aac`
- `0x180026398`
- `0x18002667c`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cda7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cda7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001caf9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001caf9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001cb4f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001cb4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001cd76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001cd76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cd04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cdc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cd04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cdc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ccac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ccac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ccc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ccc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cab2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cab2`

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
  unsigned int v7; // edi
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // r9
  void *v13; // r14
  int ValueInternal; // eax
  unsigned __int64 v15; // r8
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  HANDLE v23; // rbx
  char *v24; // rax
  unsigned int v25; // r8d
  char *v26; // rdi
  unsigned int v27; // esi
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hObject = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hObject,
    Mutex);
  v6 = hObject;
  if ( !hObject )
    return (unsigned int)wil::details::GetLastErrorFailHr(v5);
  v9 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v6;
  }
  v46 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, &v46, (bool *)v12);
  v7 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v7, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v7, v42);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v18, v19);
    if ( v6 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v20, v21);
    }
    return v7;
  }
  v22 = (_DWORD *)(4 * v46);
  if ( 4 * v46 )
  {
    *a2 = v22;
    v23 = hObject;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_26;
  }
  *a2 = 0;
  v24 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v15);
  v26 = v24;
  if ( v24 )
  {
    v45 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v45,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      *((_QWORD *)v26 + 2) = v45;
      v36 = *((_QWORD *)&v45 + 1);
      *((_QWORD *)v26 + 1) = v6;
      v23 = 0;
      v45 = 0u;
      *((_QWORD *)v26 + 3) = v36;
      *(_DWORD *)v26 = 1;
      memset_0(v26 + 40, 0, 0x108u);
      *((_QWORD *)v26 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 232), 0, 0);
      *((_QWORD *)v26 + 34) = 0;
      *((_QWORD *)v26 + 35) = 0;
      *((_QWORD *)v26 + 36) = 0;
      *((_QWORD *)v26 + 37) = 0;
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
LABEL_26:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v37, v38);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v43);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x18001ca7c  mov     [rsp-8+arg_10], rbx
0x18001ca81  push    rbp
0x18001ca82  push    rsi
0x18001ca83  push    rdi
0x18001ca84  push    r14
0x18001ca86  push    r15
0x18001ca88  lea     rbp, [rsp-170h]
0x18001ca90  sub     rsp, 270h
0x18001ca97  mov     rax, cs:__security_cookie
0x18001ca9e  xor     rax, rsp
0x18001caa1  mov     [rbp+190h+var_30], rax
0x18001caa8  and     qword ptr [rdx], 0
0x18001caac  mov     r15, rdx
0x18001caaf  mov     rbx, rcx
0x18001cab2  call    cs:__imp_GetCurrentProcessId
0x18001cab9  nop     dword ptr [rax+rax+00h]
0x18001cabe  mov     esi, 130h
0x18001cac3  mov     [rsp+290h+var_268], rbx
0x18001cac8  mov     r9d, eax
0x18001cacb  mov     [rsp+290h+var_270], esi; int
0x18001cacf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001cad6  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001cadb  lea     edx, [rsi-2Ch]; unsigned __int64
0x18001cade  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cae3  and     [rsp+290h+hObject], 0
0x18001cae9  lea     rdx, [rsp+290h+Name]; lpName
0x18001caee  mov     r9d, 1F0001h; dwDesiredAccess
0x18001caf4  xor     r8d, r8d; dwFlags
0x18001caf7  xor     ecx, ecx; lpMutexAttributes
0x18001caf9  call    cs:__imp_CreateMutexExW
0x18001cb00  nop     dword ptr [rax+rax+00h]
0x18001cb05  mov     rdx, rax
0x18001cb08  lea     rcx, [rsp+290h+hObject]
0x18001cb0d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001cb12  mov     rbx, [rsp+290h+hObject]
0x18001cb17  test    rbx, rbx
0x18001cb1a  jnz     short loc_18001CB46
0x18001cb1c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001cb21  mov     edi, eax
0x18001cb23  test    rbx, rbx
0x18001cb26  jz      short loc_18001CB3F
0x18001cb28  mov     rcx, rbx; hObject
0x18001cb2b  call    cs:__imp_CloseHandle
0x18001cb32  nop     dword ptr [rax+rax+00h]
0x18001cb37  test    eax, eax
0x18001cb39  jz      loc_18001CE20
0x18001cb3f  mov     eax, edi
0x18001cb41  jmp     loc_18001CDD5
0x18001cb46  xor     r8d, r8d; bAlertable
0x18001cb49  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001cb4c  mov     rcx, rbx; hHandle
0x18001cb4f  call    cs:__imp_WaitForSingleObjectEx
0x18001cb56  nop     dword ptr [rax+rax+00h]
0x18001cb5b  cmp     eax, 102h
0x18001cb60  jz      short loc_18001CB72
0x18001cb62  test    eax, 0FFFFFF7Fh
0x18001cb67  jnz     loc_18001CE32
0x18001cb6d  mov     r14, rbx
0x18001cb70  jmp     short loc_18001CB75
0x18001cb72  xor     r14d, r14d
0x18001cb75  and     [rsp+290h+var_248], 0
0x18001cb7b  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18001cb80  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001cb85  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001cb8a  mov     edi, eax
0x18001cb8c  test    eax, eax
0x18001cb8e  jns     short loc_18001CC0D
0x18001cb90  mov     rcx, [rbp+198h]; this
0x18001cb97  mov     r9d, eax; char *
0x18001cb9a  mov     edx, 64h ; 'd'; void *
0x18001cb9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cba4  mov     rcx, [rbp+198h]; this
0x18001cbab  mov     r9d, edi; char *
0x18001cbae  mov     edx, 6Dh ; 'm'; void *
0x18001cbb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbb8  mov     rcx, [rbp+198h]; this
0x18001cbbf  mov     r9d, edi; char *
0x18001cbc2  mov     edx, 12Bh; void *
0x18001cbc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbcc  test    r14, r14
0x18001cbcf  jz      short loc_18001CBE8
0x18001cbd1  mov     rcx, r14; hMutex
0x18001cbd4  call    cs:__imp_ReleaseMutex
0x18001cbdb  nop     dword ptr [rax+rax+00h]
0x18001cbe0  test    eax, eax
0x18001cbe2  jz      loc_18001CE3F
0x18001cbe8  test    rbx, rbx
0x18001cbeb  jz      loc_18001CB3F
0x18001cbf1  mov     rcx, rbx; hObject
0x18001cbf4  call    cs:__imp_CloseHandle
0x18001cbfb  nop     dword ptr [rax+rax+00h]
0x18001cc00  test    eax, eax
0x18001cc02  jz      loc_18001CE0E
0x18001cc08  jmp     loc_18001CB3F
0x18001cc0d  mov     rax, [rsp+290h+var_248]
0x18001cc12  lea     rcx, ds:0[rax*4]
0x18001cc1a  test    rcx, rcx
0x18001cc1d  jz      short loc_18001CC35
0x18001cc1f  mov     [r15], rcx
0x18001cc22  mov     ecx, [rcx]
0x18001cc24  mov     rax, [r15]
0x18001cc27  inc     ecx
0x18001cc29  mov     rbx, [rsp+290h+hObject]
0x18001cc2e  mov     [rax], ecx
0x18001cc30  jmp     loc_18001CD9F
0x18001cc35  and     qword ptr [r15], 0
0x18001cc39  mov     rdx, rsi; dwBytes
0x18001cc3c  mov     ecx, 8; dwFlags
0x18001cc41  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001cc46  mov     rdi, rax
0x18001cc49  test    rax, rax
0x18001cc4c  jnz     short loc_18001CC69
0x18001cc4e  mov     rcx, [rbp+198h]; this
0x18001cc55  mov     esi, 8007000Eh
0x18001cc5a  mov     r9d, esi; char *
0x18001cc5d  mov     edx, 148h; void *
0x18001cc62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc67  jmp     short loc_18001CCCC
0x18001cc69  xorps   xmm0, xmm0
0x18001cc6c  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18001cc71  mov     r8, rdi; void *
0x18001cc74  lea     rcx, [rsp+290h+var_258]; this
0x18001cc79  movdqu  [rsp+290h+var_258], xmm0
0x18001cc7f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18001cc84  mov     esi, eax
0x18001cc86  test    eax, eax
0x18001cc88  jns     loc_18001CD1F
0x18001cc8e  mov     rcx, [rbp+198h]; this
0x18001cc95  mov     r9d, eax; char *
0x18001cc98  mov     edx, 14Bh; void *
0x18001cc9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cca2  lea     rcx, [rsp+290h+var_258]; this
0x18001cca7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001ccac  call    cs:__imp_GetProcessHeap
0x18001ccb3  nop     dword ptr [rax+rax+00h]
0x18001ccb8  mov     r8, rdi; lpMem
0x18001ccbb  xor     edx, edx; dwFlags
0x18001ccbd  mov     rcx, rax; hHeap
0x18001ccc0  call    cs:__imp_HeapFree
0x18001ccc7  nop     dword ptr [rax+rax+00h]
0x18001cccc  mov     rcx, [rbp+198h]; this
0x18001ccd3  mov     r9d, esi; char *
0x18001ccd6  mov     edx, 134h; void *
0x18001ccdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cce0  test    r14, r14
0x18001cce3  jz      short loc_18001CCFC
0x18001cce5  mov     rcx, r14; hMutex
0x18001cce8  call    cs:__imp_ReleaseMutex
0x18001ccef  nop     dword ptr [rax+rax+00h]
0x18001ccf4  test    eax, eax
0x18001ccf6  jz      loc_18001CE51
0x18001ccfc  test    rbx, rbx
0x18001ccff  jz      short loc_18001CD18
0x18001cd01  mov     rcx, rbx; hObject
0x18001cd04  call    cs:__imp_CloseHandle
0x18001cd0b  nop     dword ptr [rax+rax+00h]
0x18001cd10  test    eax, eax
0x18001cd12  jz      loc_18001CE63
0x18001cd18  mov     eax, esi
0x18001cd1a  jmp     loc_18001CDD5
0x18001cd1f  mov     rax, qword ptr [rsp+290h+var_258]
0x18001cd24  lea     rcx, [rdi+28h]; void *
0x18001cd28  mov     [rdi+10h], rax
0x18001cd2c  xor     edx, edx; Val
0x18001cd2e  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18001cd33  mov     r8d, 108h; Size
0x18001cd39  mov     [rdi+8], rbx
0x18001cd3d  xor     ebx, ebx
0x18001cd3f  and     qword ptr [rsp+290h+var_258], rbx
0x18001cd44  and     qword ptr [rsp+290h+var_258+8], rbx
0x18001cd49  mov     [rdi+18h], rax
0x18001cd4d  mov     dword ptr [rdi], 1
0x18001cd53  call    memset_0
0x18001cd58  xor     eax, eax
0x18001cd5a  lea     rcx, [rdi+28h]; this
0x18001cd5e  mov     [rdi+20h], rax
0x18001cd62  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001cd67  lea     rsi, [rdi+0E8h]
0x18001cd6e  xor     r8d, r8d; Flags
0x18001cd71  mov     rcx, rsi; lpCriticalSection
0x18001cd74  xor     edx, edx; dwSpinCount
0x18001cd76  call    cs:__imp_InitializeCriticalSectionEx
0x18001cd7d  nop     dword ptr [rax+rax+00h]
0x18001cd82  and     [rsi+28h], rbx
0x18001cd86  lea     rcx, [rsp+290h+var_258]; this
0x18001cd8b  and     [rsi+30h], rbx
0x18001cd8f  and     [rsi+38h], rbx
0x18001cd93  and     [rsi+40h], rbx
0x18001cd97  mov     [r15], rdi
0x18001cd9a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001cd9f  test    r14, r14
0x18001cda2  jz      short loc_18001CDBB
0x18001cda4  mov     rcx, r14; hMutex
0x18001cda7  call    cs:__imp_ReleaseMutex
0x18001cdae  nop     dword ptr [rax+rax+00h]
0x18001cdb3  test    eax, eax
0x18001cdb5  jz      loc_18001CE75
0x18001cdbb  test    rbx, rbx
0x18001cdbe  jz      short loc_18001CDD3
0x18001cdc0  mov     rcx, rbx; hObject
0x18001cdc3  call    cs:__imp_CloseHandle
0x18001cdca  nop     dword ptr [rax+rax+00h]
0x18001cdcf  test    eax, eax
0x18001cdd1  jz      short loc_18001CDFC
0x18001cdd3  xor     eax, eax
0x18001cdd5  mov     rcx, [rbp+190h+var_30]
0x18001cddc  xor     rcx, rsp; StackCookie
0x18001cddf  call    __security_check_cookie
0x18001cde4  mov     rbx, [rsp+290h+arg_10]
0x18001cdec  add     rsp, 270h
0x18001cdf3  pop     r15
0x18001cdf5  pop     r14
0x18001cdf7  pop     rdi
0x18001cdf8  pop     rsi
0x18001cdf9  pop     rbp
0x18001cdfa  retn
0x18001cdfc  mov     rcx, [rbp+198h]; this
0x18001ce03  mov     edx, 9DDh; void *
0x18001ce08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ce0e  mov     rcx, [rbp+198h]; this
0x18001ce15  mov     edx, 9DDh; void *
0x18001ce1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ce20  mov     rcx, [rbp+198h]; this
0x18001ce27  mov     edx, 9DDh; void *
0x18001ce2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ce32  mov     rcx, [rbp+198h]; this
0x18001ce39  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001ce3f  mov     rcx, [rbp+198h]; this
0x18001ce46  mov     edx, 9E7h; void *
0x18001ce4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ce51  mov     rcx, [rbp+198h]; this
0x18001ce58  mov     edx, 9E7h; void *
0x18001ce5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ce63  mov     rcx, [rbp+198h]; this
0x18001ce6a  mov     edx, 9DDh; void *
0x18001ce6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ce75  mov     rcx, [rbp+198h]; this
0x18001ce7c  mov     edx, 9E7h; void *
0x18001ce81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
