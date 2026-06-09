# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001c684`
- end: `0x18001ca76`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001dfa4`

## callees

- `0x18001ad2c`
- `0x18001c400`
- `0x18001c684`
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

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c7de`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c8f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c996`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c7de`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c8f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c996`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c703`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c703`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c759`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c7fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c90e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c7fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c90e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c8b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c8b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c8ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c8ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c6ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c6ba`

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
  _QWORD *v24; // rax
  unsigned int v25; // r8d
  _QWORD *v26; // rdi
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
  __int64 v37; // rax
  unsigned int v38; // r8d
  const char *v39; // r9
  unsigned int v40; // r8d
  const char *v41; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
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
  v47 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, &v47, (bool *)v12);
  v7 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v15, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v7, v42);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v7, v43);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v18, v19);
    if ( v6 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v20, v21);
    }
    return v7;
  }
  v22 = (_DWORD *)(4 * v47);
  if ( 4 * v47 )
  {
    *a2 = v22;
    v23 = hObject;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_26;
  }
  *a2 = 0;
  v24 = wil::details::ProcessHeapAlloc(8u, 0x78u, v15);
  v26 = v24;
  if ( v24 )
  {
    v46 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v46,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v36 = v46;
      v26[1] = v6;
      v23 = 0;
      v26[2] = v36;
      v37 = *((_QWORD *)&v46 + 1);
      v46 = 0u;
      *(_DWORD *)v26 = 1;
      hObject = 0;
      v26[3] = v37;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v46);
LABEL_26:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v38, v39);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v40, v41);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v46);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v44);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x18001c684  mov     [rsp-8+arg_10], rbx
0x18001c689  push    rbp
0x18001c68a  push    rsi
0x18001c68b  push    rdi
0x18001c68c  push    r14
0x18001c68e  push    r15
0x18001c690  lea     rbp, [rsp-170h]
0x18001c698  sub     rsp, 270h
0x18001c69f  mov     rax, cs:__security_cookie
0x18001c6a6  xor     rax, rsp
0x18001c6a9  mov     [rbp+190h+var_30], rax
0x18001c6b0  and     qword ptr [rdx], 0
0x18001c6b4  mov     r15, rdx
0x18001c6b7  mov     rbx, rcx
0x18001c6ba  call    cs:__imp_GetCurrentProcessId
0x18001c6c1  nop     dword ptr [rax+rax+00h]
0x18001c6c6  mov     esi, 78h ; 'x'
0x18001c6cb  mov     [rsp+290h+var_268], rbx
0x18001c6d0  mov     r9d, eax
0x18001c6d3  mov     [rsp+290h+var_270], esi; int
0x18001c6d7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001c6de  mov     edx, 104h; unsigned __int64
0x18001c6e3  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001c6e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c6ed  and     [rsp+290h+hObject], 0
0x18001c6f3  lea     rdx, [rsp+290h+Name]; lpName
0x18001c6f8  mov     r9d, 1F0001h; dwDesiredAccess
0x18001c6fe  xor     r8d, r8d; dwFlags
0x18001c701  xor     ecx, ecx; lpMutexAttributes
0x18001c703  call    cs:__imp_CreateMutexExW
0x18001c70a  nop     dword ptr [rax+rax+00h]
0x18001c70f  mov     rdx, rax
0x18001c712  lea     rcx, [rsp+290h+hObject]
0x18001c717  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001c71c  mov     rbx, [rsp+290h+hObject]
0x18001c721  test    rbx, rbx
0x18001c724  jnz     short loc_18001C750
0x18001c726  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c72b  mov     edi, eax
0x18001c72d  test    rbx, rbx
0x18001c730  jz      short loc_18001C749
0x18001c732  mov     rcx, rbx; hObject
0x18001c735  call    cs:__imp_CloseHandle
0x18001c73c  nop     dword ptr [rax+rax+00h]
0x18001c741  test    eax, eax
0x18001c743  jz      loc_18001CA0F
0x18001c749  mov     eax, edi
0x18001c74b  jmp     loc_18001C9C4
0x18001c750  xor     r8d, r8d; bAlertable
0x18001c753  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c756  mov     rcx, rbx; hHandle
0x18001c759  call    cs:__imp_WaitForSingleObjectEx
0x18001c760  nop     dword ptr [rax+rax+00h]
0x18001c765  cmp     eax, 102h
0x18001c76a  jz      short loc_18001C77C
0x18001c76c  test    eax, 0FFFFFF7Fh
0x18001c771  jnz     loc_18001CA21
0x18001c777  mov     r14, rbx
0x18001c77a  jmp     short loc_18001C77F
0x18001c77c  xor     r14d, r14d
0x18001c77f  and     [rsp+290h+var_248], 0
0x18001c785  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18001c78a  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18001c78f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001c794  mov     edi, eax
0x18001c796  test    eax, eax
0x18001c798  jns     short loc_18001C817
0x18001c79a  mov     rcx, [rbp+198h]; this
0x18001c7a1  mov     r9d, eax; char *
0x18001c7a4  mov     edx, 64h ; 'd'; void *
0x18001c7a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7ae  mov     rcx, [rbp+198h]; this
0x18001c7b5  mov     r9d, edi; char *
0x18001c7b8  mov     edx, 6Dh ; 'm'; void *
0x18001c7bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7c2  mov     rcx, [rbp+198h]; this
0x18001c7c9  mov     r9d, edi; char *
0x18001c7cc  mov     edx, 12Bh; void *
0x18001c7d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7d6  test    r14, r14
0x18001c7d9  jz      short loc_18001C7F2
0x18001c7db  mov     rcx, r14; hMutex
0x18001c7de  call    cs:__imp_ReleaseMutex
0x18001c7e5  nop     dword ptr [rax+rax+00h]
0x18001c7ea  test    eax, eax
0x18001c7ec  jz      loc_18001CA2E
0x18001c7f2  test    rbx, rbx
0x18001c7f5  jz      loc_18001C749
0x18001c7fb  mov     rcx, rbx; hObject
0x18001c7fe  call    cs:__imp_CloseHandle
0x18001c805  nop     dword ptr [rax+rax+00h]
0x18001c80a  test    eax, eax
0x18001c80c  jz      loc_18001C9FD
0x18001c812  jmp     loc_18001C749
0x18001c817  mov     rax, [rsp+290h+var_248]
0x18001c81c  lea     rcx, ds:0[rax*4]
0x18001c824  test    rcx, rcx
0x18001c827  jz      short loc_18001C83F
0x18001c829  mov     [r15], rcx
0x18001c82c  mov     ecx, [rcx]
0x18001c82e  mov     rax, [r15]
0x18001c831  inc     ecx
0x18001c833  mov     rbx, [rsp+290h+hObject]
0x18001c838  mov     [rax], ecx
0x18001c83a  jmp     loc_18001C98E
0x18001c83f  and     qword ptr [r15], 0
0x18001c843  mov     rdx, rsi; dwBytes
0x18001c846  mov     ecx, 8; dwFlags
0x18001c84b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001c850  mov     rdi, rax
0x18001c853  test    rax, rax
0x18001c856  jnz     short loc_18001C873
0x18001c858  mov     rcx, [rbp+198h]; this
0x18001c85f  mov     esi, 8007000Eh
0x18001c864  mov     r9d, esi; char *
0x18001c867  mov     edx, 148h; void *
0x18001c86c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c871  jmp     short loc_18001C8D6
0x18001c873  xorps   xmm0, xmm0
0x18001c876  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18001c87b  mov     r8, rdi; void *
0x18001c87e  lea     rcx, [rsp+290h+var_258]; this
0x18001c883  movdqu  [rsp+290h+var_258], xmm0
0x18001c889  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18001c88e  mov     esi, eax
0x18001c890  test    eax, eax
0x18001c892  jns     loc_18001C929
0x18001c898  mov     rcx, [rbp+198h]; this
0x18001c89f  mov     r9d, eax; char *
0x18001c8a2  mov     edx, 14Bh; void *
0x18001c8a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8ac  lea     rcx, [rsp+290h+var_258]; this
0x18001c8b1  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001c8b6  call    cs:__imp_GetProcessHeap
0x18001c8bd  nop     dword ptr [rax+rax+00h]
0x18001c8c2  mov     r8, rdi; lpMem
0x18001c8c5  xor     edx, edx; dwFlags
0x18001c8c7  mov     rcx, rax; hHeap
0x18001c8ca  call    cs:__imp_HeapFree
0x18001c8d1  nop     dword ptr [rax+rax+00h]
0x18001c8d6  mov     rcx, [rbp+198h]; this
0x18001c8dd  mov     r9d, esi; char *
0x18001c8e0  mov     edx, 134h; void *
0x18001c8e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8ea  test    r14, r14
0x18001c8ed  jz      short loc_18001C906
0x18001c8ef  mov     rcx, r14; hMutex
0x18001c8f2  call    cs:__imp_ReleaseMutex
0x18001c8f9  nop     dword ptr [rax+rax+00h]
0x18001c8fe  test    eax, eax
0x18001c900  jz      loc_18001CA40
0x18001c906  test    rbx, rbx
0x18001c909  jz      short loc_18001C922
0x18001c90b  mov     rcx, rbx; hObject
0x18001c90e  call    cs:__imp_CloseHandle
0x18001c915  nop     dword ptr [rax+rax+00h]
0x18001c91a  test    eax, eax
0x18001c91c  jz      loc_18001CA52
0x18001c922  mov     eax, esi
0x18001c924  jmp     loc_18001C9C4
0x18001c929  mov     rax, qword ptr [rsp+290h+var_258]
0x18001c92e  lea     rcx, [rdi+22h]; void *
0x18001c932  mov     [rdi+8], rbx
0x18001c936  xor     edx, edx; Val
0x18001c938  xor     ebx, ebx
0x18001c93a  mov     [rdi+10h], rax
0x18001c93e  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18001c943  and     qword ptr [rsp+290h+var_258], rbx
0x18001c948  and     qword ptr [rsp+290h+var_258+8], rbx
0x18001c94d  lea     r8d, [rbx+56h]; Size
0x18001c951  mov     dword ptr [rdi], 1
0x18001c957  mov     [rsp+290h+hObject], rbx
0x18001c95c  mov     [rdi+18h], rax
0x18001c960  call    memset_0
0x18001c965  mov     word ptr [rdi+20h], 58h ; 'X'
0x18001c96b  lea     rcx, [rdi+28h]; void *
0x18001c96f  xor     edx, edx; Val
0x18001c971  mov     dword ptr [rdi+24h], 1
0x18001c978  lea     r8d, [rbx+50h]; Size
0x18001c97c  call    memset_0
0x18001c981  lea     rcx, [rsp+290h+var_258]; this
0x18001c986  mov     [r15], rdi
0x18001c989  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001c98e  test    r14, r14
0x18001c991  jz      short loc_18001C9AA
0x18001c993  mov     rcx, r14; hMutex
0x18001c996  call    cs:__imp_ReleaseMutex
0x18001c99d  nop     dword ptr [rax+rax+00h]
0x18001c9a2  test    eax, eax
0x18001c9a4  jz      loc_18001CA64
0x18001c9aa  test    rbx, rbx
0x18001c9ad  jz      short loc_18001C9C2
0x18001c9af  mov     rcx, rbx; hObject
0x18001c9b2  call    cs:__imp_CloseHandle
0x18001c9b9  nop     dword ptr [rax+rax+00h]
0x18001c9be  test    eax, eax
0x18001c9c0  jz      short loc_18001C9EB
0x18001c9c2  xor     eax, eax
0x18001c9c4  mov     rcx, [rbp+190h+var_30]
0x18001c9cb  xor     rcx, rsp; StackCookie
0x18001c9ce  call    __security_check_cookie
0x18001c9d3  mov     rbx, [rsp+290h+arg_10]
0x18001c9db  add     rsp, 270h
0x18001c9e2  pop     r15
0x18001c9e4  pop     r14
0x18001c9e6  pop     rdi
0x18001c9e7  pop     rsi
0x18001c9e8  pop     rbp
0x18001c9e9  retn
0x18001c9eb  mov     rcx, [rbp+198h]; this
0x18001c9f2  mov     edx, 9DDh; void *
0x18001c9f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c9fd  mov     rcx, [rbp+198h]; this
0x18001ca04  mov     edx, 9DDh; void *
0x18001ca09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ca0f  mov     rcx, [rbp+198h]; this
0x18001ca16  mov     edx, 9DDh; void *
0x18001ca1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ca21  mov     rcx, [rbp+198h]; this
0x18001ca28  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001ca2e  mov     rcx, [rbp+198h]; this
0x18001ca35  mov     edx, 9E7h; void *
0x18001ca3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ca40  mov     rcx, [rbp+198h]; this
0x18001ca47  mov     edx, 9E7h; void *
0x18001ca4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ca52  mov     rcx, [rbp+198h]; this
0x18001ca59  mov     edx, 9DDh; void *
0x18001ca5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ca64  mov     rcx, [rbp+198h]; this
0x18001ca6b  mov     edx, 9E7h; void *
0x18001ca70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
