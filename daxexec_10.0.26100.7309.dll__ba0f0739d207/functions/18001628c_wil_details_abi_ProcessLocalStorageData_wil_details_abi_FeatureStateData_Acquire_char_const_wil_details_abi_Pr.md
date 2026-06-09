# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001628c`
- end: `0x1800166bb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800179e0`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000c6f4`
- `0x18000cd5c`
- `0x18000cf44`
- `0x18000d508`
- `0x18000de20`
- `0x18000e234`
- `0x18000ec7c`
- `0x18000ed4c`
- `0x18000f1c8`
- `0x18000f2e0`
- `0x180014d00`
- `0x18001628c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016309`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016309`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001633f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001633f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800163dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800164ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800165be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800163dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800164ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800165be`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001658d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001658d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800164d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800164d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800164bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800164bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800162c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800162c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001651b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800165da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001651b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800165da`

## string_xrefs

- `0x18001661a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180016645`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001665e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180016677`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180016690`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800166a9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  HANDLE v19; // rbx
  char *v20; // rax
  char *v21; // rdi
  unsigned int v22; // esi
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
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
  v35 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v35, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v15, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v15, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9E7,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DD,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v35);
  if ( 4 * v35 )
  {
    *a2 = v18;
    v19 = hHandle;
    *(_DWORD *)*a2 = *v18 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v20 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v21 = v20;
  if ( v20 )
  {
    v34 = 0;
    v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)&v34, Name, v20);
    v22 = v23;
    if ( v23 >= 0 )
    {
      *((_QWORD *)v21 + 2) = v34;
      v27 = *((_QWORD *)&v34 + 1);
      *((_QWORD *)v21 + 1) = v6;
      v19 = 0;
      v34 = 0u;
      *((_QWORD *)v21 + 3) = v27;
      *(_DWORD *)v21 = 1;
      memset_0(v21 + 40, 0, 0x108u);
      *((_QWORD *)v21 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 232), 0, 0);
      *((_QWORD *)v21 + 34) = 0;
      *((_QWORD *)v21 + 35) = 0;
      *((_QWORD *)v21 + 36) = 0;
      *((_QWORD *)v21 + 37) = 0;
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v34);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9E7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v19 && !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9DD,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)v22, v32);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9E7,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9DD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return v22;
}

```

## disassembly

```asm
0x18001628c  mov     [rsp-8+arg_10], rbx
0x180016291  push    rbp
0x180016292  push    rsi
0x180016293  push    rdi
0x180016294  push    r14
0x180016296  push    r15
0x180016298  lea     rbp, [rsp-170h]
0x1800162a0  sub     rsp, 270h
0x1800162a7  mov     rax, cs:__security_cookie
0x1800162ae  xor     rax, rsp
0x1800162b1  mov     [rbp+190h+var_30], rax
0x1800162b8  and     qword ptr [rdx], 0
0x1800162bc  mov     r15, rdx
0x1800162bf  mov     rbx, rcx
0x1800162c2  call    cs:__imp_GetCurrentProcessId
0x1800162c9  nop     dword ptr [rax+rax+00h]
0x1800162ce  mov     esi, 130h
0x1800162d3  mov     [rsp+290h+var_268], rbx
0x1800162d8  mov     r9d, eax
0x1800162db  mov     [rsp+290h+var_270], esi; int
0x1800162df  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800162e6  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800162eb  lea     edx, [rsi-2Ch]; unsigned __int64
0x1800162ee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800162f3  and     [rsp+290h+hHandle], 0
0x1800162f9  lea     rdx, [rsp+290h+Name]; lpName
0x1800162fe  mov     r9d, 1F0001h; dwDesiredAccess
0x180016304  xor     r8d, r8d; dwFlags
0x180016307  xor     ecx, ecx; lpMutexAttributes
0x180016309  call    cs:__imp_CreateMutexExW
0x180016310  nop     dword ptr [rax+rax+00h]
0x180016315  mov     rdx, rax
0x180016318  lea     rcx, [rsp+290h+hHandle]
0x18001631d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016322  mov     rbx, [rsp+290h+hHandle]
0x180016327  test    rbx, rbx
0x18001632a  jnz     short loc_180016336
0x18001632c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016331  jmp     loc_1800165EC
0x180016336  xor     r8d, r8d; bAlertable
0x180016339  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001633c  mov     rcx, rbx; hHandle
0x18001633f  call    cs:__imp_WaitForSingleObjectEx
0x180016346  nop     dword ptr [rax+rax+00h]
0x18001634b  cmp     eax, 102h
0x180016350  jz      short loc_180016362
0x180016352  test    eax, 0FFFFFF7Fh
0x180016357  jnz     loc_18001662C
0x18001635d  mov     r14, rbx
0x180016360  jmp     short loc_180016365
0x180016362  xor     r14d, r14d
0x180016365  and     [rsp+290h+var_248], 0
0x18001636b  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180016370  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180016375  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001637a  mov     edi, eax
0x18001637c  test    eax, eax
0x18001637e  jns     loc_18001640F
0x180016384  mov     rcx, [rbp+198h]; this
0x18001638b  lea     r8, aWil; "wil"
0x180016392  mov     r9d, eax; char *
0x180016395  mov     edx, 64h ; 'd'; void *
0x18001639a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001639f  mov     rcx, [rbp+198h]; this
0x1800163a6  lea     r8, aWil; "wil"
0x1800163ad  mov     r9d, edi; char *
0x1800163b0  mov     edx, 6Dh ; 'm'; void *
0x1800163b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163ba  mov     rcx, [rbp+198h]; this
0x1800163c1  lea     r8, aWil; "wil"
0x1800163c8  mov     r9d, edi; char *
0x1800163cb  mov     edx, 12Bh; void *
0x1800163d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163d5  test    r14, r14
0x1800163d8  jz      short loc_1800163F1
0x1800163da  mov     rcx, r14; hMutex
0x1800163dd  call    cs:__imp_ReleaseMutex
0x1800163e4  nop     dword ptr [rax+rax+00h]
0x1800163e9  test    eax, eax
0x1800163eb  jz      loc_18001663E
0x1800163f1  mov     rcx, rbx; hObject
0x1800163f4  call    cs:__imp_CloseHandle
0x1800163fb  nop     dword ptr [rax+rax+00h]
0x180016400  test    eax, eax
0x180016402  jz      loc_180016657
0x180016408  mov     eax, edi
0x18001640a  jmp     loc_1800165EC
0x18001640f  mov     rax, [rsp+290h+var_248]
0x180016414  lea     rcx, ds:0[rax*4]
0x18001641c  test    rcx, rcx
0x18001641f  jz      short loc_180016437
0x180016421  mov     [r15], rcx
0x180016424  mov     ecx, [rcx]
0x180016426  mov     rax, [r15]
0x180016429  inc     ecx
0x18001642b  mov     rbx, [rsp+290h+hHandle]
0x180016430  mov     [rax], ecx
0x180016432  jmp     loc_1800165B6
0x180016437  and     qword ptr [r15], 0
0x18001643b  mov     rdx, rsi; dwBytes
0x18001643e  mov     ecx, 8; dwFlags
0x180016443  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180016448  mov     rdi, rax
0x18001644b  test    rax, rax
0x18001644e  jnz     short loc_180016472
0x180016450  mov     rcx, [rbp+198h]; this
0x180016457  lea     r8, aWil; "wil"
0x18001645e  mov     esi, 8007000Eh
0x180016463  mov     edx, 148h; void *
0x180016468  mov     r9d, esi; char *
0x18001646b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016470  jmp     short loc_1800164DC
0x180016472  xorps   xmm0, xmm0
0x180016475  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18001647a  mov     r8, rdi; void *
0x18001647d  lea     rcx, [rsp+290h+var_258]; this
0x180016482  movdqu  [rsp+290h+var_258], xmm0
0x180016488  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18001648d  mov     esi, eax
0x18001648f  test    eax, eax
0x180016491  jns     loc_180016536
0x180016497  mov     rcx, [rbp+198h]; this
0x18001649e  lea     r8, aWil; "wil"
0x1800164a5  mov     r9d, eax; char *
0x1800164a8  mov     edx, 14Bh; void *
0x1800164ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164b2  lea     rcx, [rsp+290h+var_258]; this
0x1800164b7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800164bc  call    cs:__imp_GetProcessHeap
0x1800164c3  nop     dword ptr [rax+rax+00h]
0x1800164c8  mov     r8, rdi; lpMem
0x1800164cb  xor     edx, edx; dwFlags
0x1800164cd  mov     rcx, rax; hHeap
0x1800164d0  call    cs:__imp_HeapFree
0x1800164d7  nop     dword ptr [rax+rax+00h]
0x1800164dc  mov     rcx, [rbp+198h]; this
0x1800164e3  lea     r8, aWil; "wil"
0x1800164ea  mov     r9d, esi; char *
0x1800164ed  mov     edx, 134h; void *
0x1800164f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164f7  test    r14, r14
0x1800164fa  jz      short loc_180016513
0x1800164fc  mov     rcx, r14; hMutex
0x1800164ff  call    cs:__imp_ReleaseMutex
0x180016506  nop     dword ptr [rax+rax+00h]
0x18001650b  test    eax, eax
0x18001650d  jz      loc_180016670
0x180016513  test    rbx, rbx
0x180016516  jz      short loc_18001652F
0x180016518  mov     rcx, rbx; hObject
0x18001651b  call    cs:__imp_CloseHandle
0x180016522  nop     dword ptr [rax+rax+00h]
0x180016527  test    eax, eax
0x180016529  jz      loc_180016689
0x18001652f  mov     eax, esi
0x180016531  jmp     loc_1800165EC
0x180016536  mov     rax, qword ptr [rsp+290h+var_258]
0x18001653b  lea     rcx, [rdi+28h]; void *
0x18001653f  mov     [rdi+10h], rax
0x180016543  xor     edx, edx; Val
0x180016545  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18001654a  mov     r8d, 108h; Size
0x180016550  mov     [rdi+8], rbx
0x180016554  xor     ebx, ebx
0x180016556  and     qword ptr [rsp+290h+var_258], rbx
0x18001655b  and     qword ptr [rsp+290h+var_258+8], rbx
0x180016560  mov     [rdi+18h], rax
0x180016564  mov     dword ptr [rdi], 1
0x18001656a  call    memset_0
0x18001656f  xor     eax, eax
0x180016571  lea     rcx, [rdi+28h]; this
0x180016575  mov     [rdi+20h], rax
0x180016579  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001657e  lea     rsi, [rdi+0E8h]
0x180016585  xor     r8d, r8d; Flags
0x180016588  mov     rcx, rsi; lpCriticalSection
0x18001658b  xor     edx, edx; dwSpinCount
0x18001658d  call    cs:__imp_InitializeCriticalSectionEx
0x180016594  nop     dword ptr [rax+rax+00h]
0x180016599  and     [rsi+28h], rbx
0x18001659d  lea     rcx, [rsp+290h+var_258]; this
0x1800165a2  and     [rsi+30h], rbx
0x1800165a6  and     [rsi+38h], rbx
0x1800165aa  and     [rsi+40h], rbx
0x1800165ae  mov     [r15], rdi
0x1800165b1  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800165b6  test    r14, r14
0x1800165b9  jz      short loc_1800165D2
0x1800165bb  mov     rcx, r14; hMutex
0x1800165be  call    cs:__imp_ReleaseMutex
0x1800165c5  nop     dword ptr [rax+rax+00h]
0x1800165ca  test    eax, eax
0x1800165cc  jz      loc_1800166A2
0x1800165d2  test    rbx, rbx
0x1800165d5  jz      short loc_1800165EA
0x1800165d7  mov     rcx, rbx; hObject
0x1800165da  call    cs:__imp_CloseHandle
0x1800165e1  nop     dword ptr [rax+rax+00h]
0x1800165e6  test    eax, eax
0x1800165e8  jz      short loc_180016613
0x1800165ea  xor     eax, eax
0x1800165ec  mov     rcx, [rbp+190h+var_30]
0x1800165f3  xor     rcx, rsp; StackCookie
0x1800165f6  call    __security_check_cookie
0x1800165fb  mov     rbx, [rsp+290h+arg_10]
0x180016603  add     rsp, 270h
0x18001660a  pop     r15
0x18001660c  pop     r14
0x18001660e  pop     rdi
0x18001660f  pop     rsi
0x180016610  pop     rbp
0x180016611  retn
0x180016613  mov     rcx, [rbp+198h]; this
0x18001661a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016621  mov     edx, 9DDh; void *
0x180016626  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001662c  mov     rcx, [rbp+198h]; this
0x180016633  mov     edx, 0C37h; void *
0x180016638  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001663e  mov     rcx, [rbp+198h]; this
0x180016645  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001664c  mov     edx, 9E7h; void *
0x180016651  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016657  mov     rcx, [rbp+198h]; this
0x18001665e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016665  mov     edx, 9DDh; void *
0x18001666a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016670  mov     rcx, [rbp+198h]; this
0x180016677  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001667e  mov     edx, 9E7h; void *
0x180016683  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180016689  mov     rcx, [rbp+198h]; this
0x180016690  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016697  mov     edx, 9DDh; void *
0x18001669c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800166a2  mov     rcx, [rbp+198h]; this
0x1800166a9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800166b0  mov     edx, 9E7h; void *
0x1800166b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
