# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c93c`
- end: `0x18000cd56`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d85c`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000c6f4`
- `0x18000c93c`
- `0x18000cd5c`
- `0x18000cf44`
- `0x18000d508`
- `0x18000de20`
- `0x18000e234`
- `0x18000ec7c`
- `0x18000ed4c`
- `0x18000f1c8`
- `0x18000f2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c9bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c9bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c9f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c9f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ca90`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cbb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cc59`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ca90`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cbb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cc59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c972`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc75`

## string_xrefs

- `0x18000ccb5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cce0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ccf9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cd12`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cd2b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000cd44`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  HANDLE v19; // rbx
  _QWORD *v20; // rax
  _QWORD *v21; // rdi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  __int64 v27; // rax
  __int64 v28; // rax
  const char *v29; // r9
  const char *v30; // r9
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v35; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
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
  v36 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v15, v31);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v15, v32);
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
  v18 = (_DWORD *)(4 * v36);
  if ( 4 * v36 )
  {
    *a2 = v18;
    v19 = hHandle;
    *(_DWORD *)*a2 = *v18 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v20 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v21 = v20;
  if ( v20 )
  {
    v35 = 0;
    v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)&v35, Name, v20);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v27 = v35;
      v21[1] = v6;
      v19 = 0;
      v21[2] = v27;
      v28 = *((_QWORD *)&v35 + 1);
      v35 = 0u;
      *(_DWORD *)v21 = 1;
      hHandle = 0;
      v21[3] = v28;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v35);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9E7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      if ( v19 && !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9DD,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v30);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v35);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)v22, v33);
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
0x18000c93c  mov     [rsp-8+arg_10], rbx
0x18000c941  push    rbp
0x18000c942  push    rsi
0x18000c943  push    rdi
0x18000c944  push    r14
0x18000c946  push    r15
0x18000c948  lea     rbp, [rsp-170h]
0x18000c950  sub     rsp, 270h
0x18000c957  mov     rax, cs:__security_cookie
0x18000c95e  xor     rax, rsp
0x18000c961  mov     [rbp+190h+var_30], rax
0x18000c968  and     qword ptr [rdx], 0
0x18000c96c  mov     r15, rdx
0x18000c96f  mov     rbx, rcx
0x18000c972  call    cs:__imp_GetCurrentProcessId
0x18000c979  nop     dword ptr [rax+rax+00h]
0x18000c97e  mov     r14d, 78h ; 'x'
0x18000c984  mov     [rsp+290h+var_268], rbx
0x18000c989  mov     r9d, eax
0x18000c98c  mov     [rsp+290h+var_270], r14d; int
0x18000c991  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c998  mov     edx, 104h; unsigned __int64
0x18000c99d  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000c9a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c9a7  and     [rsp+290h+hHandle], 0
0x18000c9ad  lea     rdx, [rsp+290h+Name]; lpName
0x18000c9b2  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c9b8  xor     r8d, r8d; dwFlags
0x18000c9bb  xor     ecx, ecx; lpMutexAttributes
0x18000c9bd  call    cs:__imp_CreateMutexExW
0x18000c9c4  nop     dword ptr [rax+rax+00h]
0x18000c9c9  mov     rdx, rax
0x18000c9cc  lea     rcx, [rsp+290h+hHandle]
0x18000c9d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c9d6  mov     rbx, [rsp+290h+hHandle]
0x18000c9db  test    rbx, rbx
0x18000c9de  jnz     short loc_18000C9EA
0x18000c9e0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c9e5  jmp     loc_18000CC87
0x18000c9ea  xor     r8d, r8d; bAlertable
0x18000c9ed  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c9f0  mov     rcx, rbx; hHandle
0x18000c9f3  call    cs:__imp_WaitForSingleObjectEx
0x18000c9fa  nop     dword ptr [rax+rax+00h]
0x18000c9ff  cmp     eax, 102h
0x18000ca04  jz      short loc_18000CA16
0x18000ca06  test    eax, 0FFFFFF7Fh
0x18000ca0b  jnz     loc_18000CCC7
0x18000ca11  mov     rsi, rbx
0x18000ca14  jmp     short loc_18000CA18
0x18000ca16  xor     esi, esi
0x18000ca18  and     [rsp+290h+var_248], 0
0x18000ca1e  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000ca23  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000ca28  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000ca2d  mov     edi, eax
0x18000ca2f  test    eax, eax
0x18000ca31  jns     loc_18000CAC2
0x18000ca37  mov     rcx, [rbp+198h]; this
0x18000ca3e  lea     r8, aWil; "wil"
0x18000ca45  mov     r9d, eax; char *
0x18000ca48  mov     edx, 64h ; 'd'; void *
0x18000ca4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca52  mov     rcx, [rbp+198h]; this
0x18000ca59  lea     r8, aWil; "wil"
0x18000ca60  mov     r9d, edi; char *
0x18000ca63  mov     edx, 6Dh ; 'm'; void *
0x18000ca68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca6d  mov     rcx, [rbp+198h]; this
0x18000ca74  lea     r8, aWil; "wil"
0x18000ca7b  mov     r9d, edi; char *
0x18000ca7e  mov     edx, 12Bh; void *
0x18000ca83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca88  test    rsi, rsi
0x18000ca8b  jz      short loc_18000CAA4
0x18000ca8d  mov     rcx, rsi; hMutex
0x18000ca90  call    cs:__imp_ReleaseMutex
0x18000ca97  nop     dword ptr [rax+rax+00h]
0x18000ca9c  test    eax, eax
0x18000ca9e  jz      loc_18000CCD9
0x18000caa4  mov     rcx, rbx; hObject
0x18000caa7  call    cs:__imp_CloseHandle
0x18000caae  nop     dword ptr [rax+rax+00h]
0x18000cab3  test    eax, eax
0x18000cab5  jz      loc_18000CCF2
0x18000cabb  mov     eax, edi
0x18000cabd  jmp     loc_18000CC87
0x18000cac2  mov     rax, [rsp+290h+var_248]
0x18000cac7  lea     rcx, ds:0[rax*4]
0x18000cacf  test    rcx, rcx
0x18000cad2  jz      short loc_18000CAEA
0x18000cad4  mov     [r15], rcx
0x18000cad7  mov     ecx, [rcx]
0x18000cad9  mov     rax, [r15]
0x18000cadc  inc     ecx
0x18000cade  mov     rbx, [rsp+290h+hHandle]
0x18000cae3  mov     [rax], ecx
0x18000cae5  jmp     loc_18000CC51
0x18000caea  and     qword ptr [r15], 0
0x18000caee  mov     rdx, r14; dwBytes
0x18000caf1  mov     ecx, 8; dwFlags
0x18000caf6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000cafb  mov     rdi, rax
0x18000cafe  test    rax, rax
0x18000cb01  jnz     short loc_18000CB26
0x18000cb03  mov     rcx, [rbp+198h]; this
0x18000cb0a  lea     r8, aWil; "wil"
0x18000cb11  mov     r14d, 8007000Eh
0x18000cb17  mov     edx, 148h; void *
0x18000cb1c  mov     r9d, r14d; char *
0x18000cb1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb24  jmp     short loc_18000CB91
0x18000cb26  xorps   xmm0, xmm0
0x18000cb29  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000cb2e  mov     r8, rdi; void *
0x18000cb31  lea     rcx, [rsp+290h+var_258]; this
0x18000cb36  movdqu  [rsp+290h+var_258], xmm0
0x18000cb3c  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000cb41  mov     r14d, eax
0x18000cb44  test    eax, eax
0x18000cb46  jns     loc_18000CBEC
0x18000cb4c  mov     rcx, [rbp+198h]; this
0x18000cb53  lea     r8, aWil; "wil"
0x18000cb5a  mov     r9d, eax; char *
0x18000cb5d  mov     edx, 14Bh; void *
0x18000cb62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb67  lea     rcx, [rsp+290h+var_258]; this
0x18000cb6c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000cb71  call    cs:__imp_GetProcessHeap
0x18000cb78  nop     dword ptr [rax+rax+00h]
0x18000cb7d  mov     r8, rdi; lpMem
0x18000cb80  xor     edx, edx; dwFlags
0x18000cb82  mov     rcx, rax; hHeap
0x18000cb85  call    cs:__imp_HeapFree
0x18000cb8c  nop     dword ptr [rax+rax+00h]
0x18000cb91  mov     rcx, [rbp+198h]; this
0x18000cb98  lea     r8, aWil; "wil"
0x18000cb9f  mov     r9d, r14d; char *
0x18000cba2  mov     edx, 134h; void *
0x18000cba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbac  test    rsi, rsi
0x18000cbaf  jz      short loc_18000CBC8
0x18000cbb1  mov     rcx, rsi; hMutex
0x18000cbb4  call    cs:__imp_ReleaseMutex
0x18000cbbb  nop     dword ptr [rax+rax+00h]
0x18000cbc0  test    eax, eax
0x18000cbc2  jz      loc_18000CD0B
0x18000cbc8  test    rbx, rbx
0x18000cbcb  jz      short loc_18000CBE4
0x18000cbcd  mov     rcx, rbx; hObject
0x18000cbd0  call    cs:__imp_CloseHandle
0x18000cbd7  nop     dword ptr [rax+rax+00h]
0x18000cbdc  test    eax, eax
0x18000cbde  jz      loc_18000CD24
0x18000cbe4  mov     eax, r14d
0x18000cbe7  jmp     loc_18000CC87
0x18000cbec  mov     rax, qword ptr [rsp+290h+var_258]
0x18000cbf1  lea     rcx, [rdi+22h]; void *
0x18000cbf5  mov     [rdi+8], rbx
0x18000cbf9  xor     edx, edx; Val
0x18000cbfb  xor     ebx, ebx
0x18000cbfd  mov     [rdi+10h], rax
0x18000cc01  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18000cc06  and     qword ptr [rsp+290h+var_258], rbx
0x18000cc0b  and     qword ptr [rsp+290h+var_258+8], rbx
0x18000cc10  lea     r8d, [rbx+56h]; Size
0x18000cc14  mov     dword ptr [rdi], 1
0x18000cc1a  mov     [rsp+290h+hHandle], rbx
0x18000cc1f  mov     [rdi+18h], rax
0x18000cc23  call    memset_0
0x18000cc28  mov     word ptr [rdi+20h], 58h ; 'X'
0x18000cc2e  lea     rcx, [rdi+28h]; void *
0x18000cc32  xor     edx, edx; Val
0x18000cc34  mov     dword ptr [rdi+24h], 1
0x18000cc3b  lea     r8d, [rbx+50h]; Size
0x18000cc3f  call    memset_0
0x18000cc44  lea     rcx, [rsp+290h+var_258]; this
0x18000cc49  mov     [r15], rdi
0x18000cc4c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000cc51  test    rsi, rsi
0x18000cc54  jz      short loc_18000CC6D
0x18000cc56  mov     rcx, rsi; hMutex
0x18000cc59  call    cs:__imp_ReleaseMutex
0x18000cc60  nop     dword ptr [rax+rax+00h]
0x18000cc65  test    eax, eax
0x18000cc67  jz      loc_18000CD3D
0x18000cc6d  test    rbx, rbx
0x18000cc70  jz      short loc_18000CC85
0x18000cc72  mov     rcx, rbx; hObject
0x18000cc75  call    cs:__imp_CloseHandle
0x18000cc7c  nop     dword ptr [rax+rax+00h]
0x18000cc81  test    eax, eax
0x18000cc83  jz      short loc_18000CCAE
0x18000cc85  xor     eax, eax
0x18000cc87  mov     rcx, [rbp+190h+var_30]
0x18000cc8e  xor     rcx, rsp; StackCookie
0x18000cc91  call    __security_check_cookie
0x18000cc96  mov     rbx, [rsp+290h+arg_10]
0x18000cc9e  add     rsp, 270h
0x18000cca5  pop     r15
0x18000cca7  pop     r14
0x18000cca9  pop     rdi
0x18000ccaa  pop     rsi
0x18000ccab  pop     rbp
0x18000ccac  retn
0x18000ccae  mov     rcx, [rbp+198h]; this
0x18000ccb5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ccbc  mov     edx, 9DDh; void *
0x18000ccc1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ccc7  mov     rcx, [rbp+198h]; this
0x18000ccce  mov     edx, 0C37h; void *
0x18000ccd3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000ccd9  mov     rcx, [rbp+198h]; this
0x18000cce0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cce7  mov     edx, 9E7h; void *
0x18000ccec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ccf2  mov     rcx, [rbp+198h]; this
0x18000ccf9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd00  mov     edx, 9DDh; void *
0x18000cd05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd0b  mov     rcx, [rbp+198h]; this
0x18000cd12  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd19  mov     edx, 9E7h; void *
0x18000cd1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd24  mov     rcx, [rbp+198h]; this
0x18000cd2b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd32  mov     edx, 9DDh; void *
0x18000cd37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd3d  mov     rcx, [rbp+198h]; this
0x18000cd44  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cd4b  mov     edx, 9E7h; void *
0x18000cd50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
