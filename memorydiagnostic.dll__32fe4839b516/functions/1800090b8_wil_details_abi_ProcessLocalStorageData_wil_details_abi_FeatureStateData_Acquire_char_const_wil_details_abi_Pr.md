# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800090b8`
- end: `0x1800094b8`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000adb0`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x1800072e8`
- `0x1800084d8`
- `0x1800090b8`
- `0x18000a490`
- `0x18000c960`
- `0x18000d7a8`
- `0x18000efd0`
- `0x1800113a4`
- `0x180014060`
- `0x1800152b8`
- `0x1800162e8`
- `0x1800188bc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800090ee`
- `KERNEL32!GetCurrentProcessId` at `0x1800090ee`
- `KERNEL32!GetProcessHeap` at `0x1800092e8`
- `KERNEL32!GetProcessHeap` at `0x1800092e8`
- `KERNEL32!CreateMutexExW` at `0x180009135`
- `KERNEL32!CreateMutexExW` at `0x180009135`
- `KERNEL32!CloseHandle` at `0x180009220`
- `KERNEL32!CloseHandle` at `0x180009347`
- `KERNEL32!CloseHandle` at `0x180009406`
- `KERNEL32!CloseHandle` at `0x180009220`
- `KERNEL32!CloseHandle` at `0x180009347`
- `KERNEL32!CloseHandle` at `0x180009406`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000916b`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000916b`
- `KERNEL32!ReleaseMutex` at `0x180009209`
- `KERNEL32!ReleaseMutex` at `0x18000932b`
- `KERNEL32!ReleaseMutex` at `0x1800093ea`
- `KERNEL32!ReleaseMutex` at `0x180009209`
- `KERNEL32!ReleaseMutex` at `0x18000932b`
- `KERNEL32!ReleaseMutex` at `0x1800093ea`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800093b9`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800093b9`
- `KERNEL32!HeapFree` at `0x1800092fc`
- `KERNEL32!HeapFree` at `0x1800092fc`

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
  void *v9; // rdx
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v41 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v41, (bool *)v11);
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
0x1800090b8  mov     [rsp-8+arg_10], rbx
0x1800090bd  push    rbp
0x1800090be  push    rsi
0x1800090bf  push    rdi
0x1800090c0  push    r14
0x1800090c2  push    r15
0x1800090c4  lea     rbp, [rsp-170h]
0x1800090cc  sub     rsp, 270h
0x1800090d3  mov     rax, cs:__security_cookie
0x1800090da  xor     rax, rsp
0x1800090dd  mov     [rbp+190h+var_30], rax
0x1800090e4  and     qword ptr [rdx], 0
0x1800090e8  mov     r15, rdx
0x1800090eb  mov     rbx, rcx
0x1800090ee  call    cs:__imp_GetCurrentProcessId
0x1800090f5  nop     dword ptr [rax+rax+00h]
0x1800090fa  mov     esi, 130h
0x1800090ff  mov     [rsp+290h+var_268], rbx
0x180009104  mov     r9d, eax
0x180009107  mov     [rsp+290h+var_270], esi; int
0x18000910b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009112  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180009117  lea     edx, [rsi-2Ch]; unsigned __int64
0x18000911a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000911f  and     [rsp+290h+hHandle], 0
0x180009125  lea     rdx, [rsp+290h+Name]; lpName
0x18000912a  mov     r9d, 1F0001h; dwDesiredAccess
0x180009130  xor     r8d, r8d; dwFlags
0x180009133  xor     ecx, ecx; lpMutexAttributes
0x180009135  call    cs:__imp_CreateMutexExW
0x18000913c  nop     dword ptr [rax+rax+00h]
0x180009141  mov     rdx, rax
0x180009144  lea     rcx, [rsp+290h+hHandle]
0x180009149  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000914e  mov     rbx, [rsp+290h+hHandle]
0x180009153  test    rbx, rbx
0x180009156  jnz     short loc_180009162
0x180009158  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000915d  jmp     loc_180009418
0x180009162  xor     r8d, r8d; bAlertable
0x180009165  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009168  mov     rcx, rbx; hHandle
0x18000916b  call    cs:__imp_WaitForSingleObjectEx
0x180009172  nop     dword ptr [rax+rax+00h]
0x180009177  cmp     eax, 102h
0x18000917c  jz      short loc_18000918E
0x18000917e  test    eax, 0FFFFFF7Fh
0x180009183  jnz     loc_180009451
0x180009189  mov     r14, rbx
0x18000918c  jmp     short loc_180009191
0x18000918e  xor     r14d, r14d
0x180009191  and     [rsp+290h+var_248], 0
0x180009197  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000919c  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800091a1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800091a6  mov     edi, eax
0x1800091a8  test    eax, eax
0x1800091aa  jns     loc_18000923B
0x1800091b0  mov     rcx, [rbp+198h]; this
0x1800091b7  lea     r8, aWil; "wil"
0x1800091be  mov     r9d, eax; char *
0x1800091c1  mov     edx, 64h ; 'd'; void *
0x1800091c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091cb  mov     rcx, [rbp+198h]; this
0x1800091d2  lea     r8, aWil; "wil"
0x1800091d9  mov     r9d, edi; char *
0x1800091dc  mov     edx, 6Dh ; 'm'; void *
0x1800091e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091e6  mov     rcx, [rbp+198h]; this
0x1800091ed  lea     r8, aWil; "wil"
0x1800091f4  mov     r9d, edi; char *
0x1800091f7  mov     edx, 12Bh; void *
0x1800091fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009201  test    r14, r14
0x180009204  jz      short loc_18000921D
0x180009206  mov     rcx, r14; hMutex
0x180009209  call    cs:__imp_ReleaseMutex
0x180009210  nop     dword ptr [rax+rax+00h]
0x180009215  test    eax, eax
0x180009217  jz      loc_18000945E
0x18000921d  mov     rcx, rbx; hObject
0x180009220  call    cs:__imp_CloseHandle
0x180009227  nop     dword ptr [rax+rax+00h]
0x18000922c  test    eax, eax
0x18000922e  jz      loc_180009470
0x180009234  mov     eax, edi
0x180009236  jmp     loc_180009418
0x18000923b  mov     rax, [rsp+290h+var_248]
0x180009240  lea     rcx, ds:0[rax*4]
0x180009248  test    rcx, rcx
0x18000924b  jz      short loc_180009263
0x18000924d  mov     [r15], rcx
0x180009250  mov     ecx, [rcx]
0x180009252  mov     rax, [r15]
0x180009255  inc     ecx
0x180009257  mov     rbx, [rsp+290h+hHandle]
0x18000925c  mov     [rax], ecx
0x18000925e  jmp     loc_1800093E2
0x180009263  and     qword ptr [r15], 0
0x180009267  mov     rdx, rsi; dwBytes
0x18000926a  mov     ecx, 8; dwFlags
0x18000926f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009274  mov     rdi, rax
0x180009277  test    rax, rax
0x18000927a  jnz     short loc_18000929E
0x18000927c  mov     rcx, [rbp+198h]; this
0x180009283  lea     r8, aWil; "wil"
0x18000928a  mov     esi, 8007000Eh
0x18000928f  mov     edx, 148h; void *
0x180009294  mov     r9d, esi; char *
0x180009297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000929c  jmp     short loc_180009308
0x18000929e  xorps   xmm0, xmm0
0x1800092a1  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800092a6  mov     r8, rdi; void *
0x1800092a9  lea     rcx, [rsp+290h+var_258]; this
0x1800092ae  movdqu  [rsp+290h+var_258], xmm0
0x1800092b4  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800092b9  mov     esi, eax
0x1800092bb  test    eax, eax
0x1800092bd  jns     loc_180009362
0x1800092c3  mov     rcx, [rbp+198h]; this
0x1800092ca  lea     r8, aWil; "wil"
0x1800092d1  mov     r9d, eax; char *
0x1800092d4  mov     edx, 14Bh; void *
0x1800092d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092de  lea     rcx, [rsp+290h+var_258]; this
0x1800092e3  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800092e8  call    cs:__imp_GetProcessHeap
0x1800092ef  nop     dword ptr [rax+rax+00h]
0x1800092f4  mov     r8, rdi; lpMem
0x1800092f7  xor     edx, edx; dwFlags
0x1800092f9  mov     rcx, rax; hHeap
0x1800092fc  call    cs:__imp_HeapFree
0x180009303  nop     dword ptr [rax+rax+00h]
0x180009308  mov     rcx, [rbp+198h]; this
0x18000930f  lea     r8, aWil; "wil"
0x180009316  mov     r9d, esi; char *
0x180009319  mov     edx, 134h; void *
0x18000931e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009323  test    r14, r14
0x180009326  jz      short loc_18000933F
0x180009328  mov     rcx, r14; hMutex
0x18000932b  call    cs:__imp_ReleaseMutex
0x180009332  nop     dword ptr [rax+rax+00h]
0x180009337  test    eax, eax
0x180009339  jz      loc_180009482
0x18000933f  test    rbx, rbx
0x180009342  jz      short loc_18000935B
0x180009344  mov     rcx, rbx; hObject
0x180009347  call    cs:__imp_CloseHandle
0x18000934e  nop     dword ptr [rax+rax+00h]
0x180009353  test    eax, eax
0x180009355  jz      loc_180009494
0x18000935b  mov     eax, esi
0x18000935d  jmp     loc_180009418
0x180009362  mov     rax, qword ptr [rsp+290h+var_258]
0x180009367  lea     rcx, [rdi+28h]; void *
0x18000936b  mov     [rdi+10h], rax
0x18000936f  xor     edx, edx; Val
0x180009371  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180009376  mov     r8d, 108h; Size
0x18000937c  mov     [rdi+8], rbx
0x180009380  xor     ebx, ebx
0x180009382  and     qword ptr [rsp+290h+var_258], rbx
0x180009387  and     qword ptr [rsp+290h+var_258+8], rbx
0x18000938c  mov     [rdi+18h], rax
0x180009390  mov     dword ptr [rdi], 1
0x180009396  call    memset_0
0x18000939b  xor     eax, eax
0x18000939d  lea     rcx, [rdi+28h]; this
0x1800093a1  mov     [rdi+20h], rax
0x1800093a5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800093aa  lea     rsi, [rdi+0E8h]
0x1800093b1  xor     r8d, r8d; Flags
0x1800093b4  mov     rcx, rsi; lpCriticalSection
0x1800093b7  xor     edx, edx; dwSpinCount
0x1800093b9  call    cs:__imp_InitializeCriticalSectionEx
0x1800093c0  nop     dword ptr [rax+rax+00h]
0x1800093c5  and     [rsi+28h], rbx
0x1800093c9  lea     rcx, [rsp+290h+var_258]; this
0x1800093ce  and     [rsi+30h], rbx
0x1800093d2  and     [rsi+38h], rbx
0x1800093d6  and     [rsi+40h], rbx
0x1800093da  mov     [r15], rdi
0x1800093dd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800093e2  test    r14, r14
0x1800093e5  jz      short loc_1800093FE
0x1800093e7  mov     rcx, r14; hMutex
0x1800093ea  call    cs:__imp_ReleaseMutex
0x1800093f1  nop     dword ptr [rax+rax+00h]
0x1800093f6  test    eax, eax
0x1800093f8  jz      loc_1800094A6
0x1800093fe  test    rbx, rbx
0x180009401  jz      short loc_180009416
0x180009403  mov     rcx, rbx; hObject
0x180009406  call    cs:__imp_CloseHandle
0x18000940d  nop     dword ptr [rax+rax+00h]
0x180009412  test    eax, eax
0x180009414  jz      short loc_18000943F
0x180009416  xor     eax, eax
0x180009418  mov     rcx, [rbp+190h+var_30]
0x18000941f  xor     rcx, rsp; StackCookie
0x180009422  call    __security_check_cookie
0x180009427  mov     rbx, [rsp+290h+arg_10]
0x18000942f  add     rsp, 270h
0x180009436  pop     r15
0x180009438  pop     r14
0x18000943a  pop     rdi
0x18000943b  pop     rsi
0x18000943c  pop     rbp
0x18000943d  retn
0x18000943f  mov     rcx, [rbp+198h]; this
0x180009446  mov     edx, 9DDh; void *
0x18000944b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009451  mov     rcx, [rbp+198h]; this
0x180009458  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000945e  mov     rcx, [rbp+198h]; this
0x180009465  mov     edx, 9E7h; void *
0x18000946a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009470  mov     rcx, [rbp+198h]; this
0x180009477  mov     edx, 9DDh; void *
0x18000947c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009482  mov     rcx, [rbp+198h]; this
0x180009489  mov     edx, 9E7h; void *
0x18000948e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009494  mov     rcx, [rbp+198h]; this
0x18000949b  mov     edx, 9DDh; void *
0x1800094a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800094a6  mov     rcx, [rbp+198h]; this
0x1800094ad  mov     edx, 9E7h; void *
0x1800094b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
