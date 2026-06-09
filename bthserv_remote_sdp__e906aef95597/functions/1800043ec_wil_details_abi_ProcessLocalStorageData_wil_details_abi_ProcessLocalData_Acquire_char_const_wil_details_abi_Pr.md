# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800043ec`
- end: `0x1800047dc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1008`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005b90`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180004014`
- `0x1800043ec`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000446d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000446d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004540`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004664`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004709`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004540`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004664`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004709`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800044a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004621`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004621`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004635`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004725`

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
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  HANDLE v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  unsigned int v24; // r14d
  int v25; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v41; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
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
  v42 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)v15, v37);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, (unsigned int)"wil", (const char *)v15, v38);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v42);
  if ( 4 * v42 )
  {
    *a2 = v20;
    v21 = hHandle;
    *(_DWORD *)*a2 = *v20 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v22 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v23 = v22;
  if ( v22 )
  {
    v41 = 0;
    v25 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v41,
            (char *)Name,
            (unsigned __int64)v22);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v31 = v41;
      v23[1] = v6;
      v21 = 0;
      v23[2] = v31;
      v32 = *((_QWORD *)&v41 + 1);
      v41 = 0u;
      *(_DWORD *)v23 = 1;
      hHandle = 0;
      v23[3] = v32;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      *a2 = v23;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v41);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v33, v34);
      if ( v21 && !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v35, v36);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, (unsigned int)"wil", (const char *)v24, v39);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v27, v28);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v29, v30);
  return v24;
}

```

## disassembly

```asm
0x1800043ec  mov     [rsp-8+arg_10], rbx
0x1800043f1  push    rbp
0x1800043f2  push    rsi
0x1800043f3  push    rdi
0x1800043f4  push    r14
0x1800043f6  push    r15
0x1800043f8  lea     rbp, [rsp-170h]
0x180004400  sub     rsp, 270h
0x180004407  mov     rax, cs:__security_cookie
0x18000440e  xor     rax, rsp
0x180004411  mov     [rbp+190h+var_30], rax
0x180004418  and     qword ptr [rdx], 0
0x18000441c  mov     r15, rdx
0x18000441f  mov     rbx, rcx
0x180004422  call    cs:__imp_GetCurrentProcessId
0x180004429  nop     dword ptr [rax+rax+00h]
0x18000442e  mov     r14d, 78h ; 'x'
0x180004434  mov     [rsp+290h+var_268], rbx
0x180004439  mov     r9d, eax
0x18000443c  mov     [rsp+290h+var_270], r14d; int
0x180004441  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004448  mov     edx, 104h; unsigned __int64
0x18000444d  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180004452  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004457  and     [rsp+290h+hHandle], 0
0x18000445d  lea     rdx, [rsp+290h+Name]; lpName
0x180004462  mov     r9d, 1F0001h; dwDesiredAccess
0x180004468  xor     r8d, r8d; dwFlags
0x18000446b  xor     ecx, ecx; lpMutexAttributes
0x18000446d  call    cs:__imp_CreateMutexExW
0x180004474  nop     dword ptr [rax+rax+00h]
0x180004479  mov     rdx, rax
0x18000447c  lea     rcx, [rsp+290h+hHandle]
0x180004481  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004486  mov     rbx, [rsp+290h+hHandle]
0x18000448b  test    rbx, rbx
0x18000448e  jnz     short loc_18000449A
0x180004490  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004495  jmp     loc_180004737
0x18000449a  xor     r8d, r8d; bAlertable
0x18000449d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800044a0  mov     rcx, rbx; hHandle
0x1800044a3  call    cs:__imp_WaitForSingleObjectEx
0x1800044aa  nop     dword ptr [rax+rax+00h]
0x1800044af  cmp     eax, 102h
0x1800044b4  jz      short loc_1800044C6
0x1800044b6  test    eax, 0FFFFFF7Fh
0x1800044bb  jnz     loc_180004770
0x1800044c1  mov     rsi, rbx
0x1800044c4  jmp     short loc_1800044C8
0x1800044c6  xor     esi, esi
0x1800044c8  and     [rsp+290h+var_248], 0
0x1800044ce  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x1800044d3  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x1800044d8  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800044dd  mov     edi, eax
0x1800044df  test    eax, eax
0x1800044e1  jns     loc_180004572
0x1800044e7  mov     rcx, [rbp+198h]; this
0x1800044ee  lea     r8, aWil; "wil"
0x1800044f5  mov     r9d, eax; char *
0x1800044f8  mov     edx, 64h ; 'd'; void *
0x1800044fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004502  mov     rcx, [rbp+198h]; this
0x180004509  lea     r8, aWil; "wil"
0x180004510  mov     r9d, edi; char *
0x180004513  mov     edx, 6Dh ; 'm'; void *
0x180004518  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000451d  mov     rcx, [rbp+198h]; this
0x180004524  lea     r8, aWil; "wil"
0x18000452b  mov     r9d, edi; char *
0x18000452e  mov     edx, 12Bh; void *
0x180004533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004538  test    rsi, rsi
0x18000453b  jz      short loc_180004554
0x18000453d  mov     rcx, rsi; hMutex
0x180004540  call    cs:__imp_ReleaseMutex
0x180004547  nop     dword ptr [rax+rax+00h]
0x18000454c  test    eax, eax
0x18000454e  jz      loc_180004782
0x180004554  mov     rcx, rbx; hObject
0x180004557  call    cs:__imp_CloseHandle
0x18000455e  nop     dword ptr [rax+rax+00h]
0x180004563  test    eax, eax
0x180004565  jz      loc_180004794
0x18000456b  mov     eax, edi
0x18000456d  jmp     loc_180004737
0x180004572  mov     rax, [rsp+290h+var_248]
0x180004577  lea     rcx, ds:0[rax*4]
0x18000457f  test    rcx, rcx
0x180004582  jz      short loc_18000459A
0x180004584  mov     [r15], rcx
0x180004587  mov     ecx, [rcx]
0x180004589  mov     rax, [r15]
0x18000458c  inc     ecx
0x18000458e  mov     rbx, [rsp+290h+hHandle]
0x180004593  mov     [rax], ecx
0x180004595  jmp     loc_180004701
0x18000459a  and     qword ptr [r15], 0
0x18000459e  mov     rdx, r14; dwBytes
0x1800045a1  mov     ecx, 8; dwFlags
0x1800045a6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800045ab  mov     rdi, rax
0x1800045ae  test    rax, rax
0x1800045b1  jnz     short loc_1800045D6
0x1800045b3  mov     rcx, [rbp+198h]; this
0x1800045ba  lea     r8, aWil; "wil"
0x1800045c1  mov     r14d, 8007000Eh
0x1800045c7  mov     edx, 148h; void *
0x1800045cc  mov     r9d, r14d; char *
0x1800045cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045d4  jmp     short loc_180004641
0x1800045d6  xorps   xmm0, xmm0
0x1800045d9  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800045de  mov     r8, rdi; void *
0x1800045e1  lea     rcx, [rsp+290h+var_258]; this
0x1800045e6  movdqu  [rsp+290h+var_258], xmm0
0x1800045ec  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800045f1  mov     r14d, eax
0x1800045f4  test    eax, eax
0x1800045f6  jns     loc_18000469C
0x1800045fc  mov     rcx, [rbp+198h]; this
0x180004603  lea     r8, aWil; "wil"
0x18000460a  mov     r9d, eax; char *
0x18000460d  mov     edx, 14Bh; void *
0x180004612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004617  lea     rcx, [rsp+290h+var_258]; this
0x18000461c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004621  call    cs:__imp_GetProcessHeap
0x180004628  nop     dword ptr [rax+rax+00h]
0x18000462d  mov     r8, rdi; lpMem
0x180004630  xor     edx, edx; dwFlags
0x180004632  mov     rcx, rax; hHeap
0x180004635  call    cs:__imp_HeapFree
0x18000463c  nop     dword ptr [rax+rax+00h]
0x180004641  mov     rcx, [rbp+198h]; this
0x180004648  lea     r8, aWil; "wil"
0x18000464f  mov     r9d, r14d; char *
0x180004652  mov     edx, 134h; void *
0x180004657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000465c  test    rsi, rsi
0x18000465f  jz      short loc_180004678
0x180004661  mov     rcx, rsi; hMutex
0x180004664  call    cs:__imp_ReleaseMutex
0x18000466b  nop     dword ptr [rax+rax+00h]
0x180004670  test    eax, eax
0x180004672  jz      loc_1800047A6
0x180004678  test    rbx, rbx
0x18000467b  jz      short loc_180004694
0x18000467d  mov     rcx, rbx; hObject
0x180004680  call    cs:__imp_CloseHandle
0x180004687  nop     dword ptr [rax+rax+00h]
0x18000468c  test    eax, eax
0x18000468e  jz      loc_1800047B8
0x180004694  mov     eax, r14d
0x180004697  jmp     loc_180004737
0x18000469c  mov     rax, qword ptr [rsp+290h+var_258]
0x1800046a1  lea     rcx, [rdi+22h]; void *
0x1800046a5  mov     [rdi+8], rbx
0x1800046a9  xor     edx, edx; Val
0x1800046ab  xor     ebx, ebx
0x1800046ad  mov     [rdi+10h], rax
0x1800046b1  mov     rax, qword ptr [rsp+290h+var_258+8]
0x1800046b6  and     qword ptr [rsp+290h+var_258], rbx
0x1800046bb  and     qword ptr [rsp+290h+var_258+8], rbx
0x1800046c0  lea     r8d, [rbx+56h]; Size
0x1800046c4  mov     dword ptr [rdi], 1
0x1800046ca  mov     [rsp+290h+hHandle], rbx
0x1800046cf  mov     [rdi+18h], rax
0x1800046d3  call    memset_0
0x1800046d8  mov     word ptr [rdi+20h], 58h ; 'X'
0x1800046de  lea     rcx, [rdi+28h]; void *
0x1800046e2  xor     edx, edx; Val
0x1800046e4  mov     dword ptr [rdi+24h], 1
0x1800046eb  lea     r8d, [rbx+50h]; Size
0x1800046ef  call    memset_0
0x1800046f4  lea     rcx, [rsp+290h+var_258]; this
0x1800046f9  mov     [r15], rdi
0x1800046fc  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004701  test    rsi, rsi
0x180004704  jz      short loc_18000471D
0x180004706  mov     rcx, rsi; hMutex
0x180004709  call    cs:__imp_ReleaseMutex
0x180004710  nop     dword ptr [rax+rax+00h]
0x180004715  test    eax, eax
0x180004717  jz      loc_1800047CA
0x18000471d  test    rbx, rbx
0x180004720  jz      short loc_180004735
0x180004722  mov     rcx, rbx; hObject
0x180004725  call    cs:__imp_CloseHandle
0x18000472c  nop     dword ptr [rax+rax+00h]
0x180004731  test    eax, eax
0x180004733  jz      short loc_18000475E
0x180004735  xor     eax, eax
0x180004737  mov     rcx, [rbp+190h+var_30]
0x18000473e  xor     rcx, rsp; StackCookie
0x180004741  call    __security_check_cookie
0x180004746  mov     rbx, [rsp+290h+arg_10]
0x18000474e  add     rsp, 270h
0x180004755  pop     r15
0x180004757  pop     r14
0x180004759  pop     rdi
0x18000475a  pop     rsi
0x18000475b  pop     rbp
0x18000475c  retn
0x18000475e  mov     rcx, [rbp+198h]; this
0x180004765  mov     edx, 9DDh; void *
0x18000476a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004770  mov     rcx, [rbp+198h]; this
0x180004777  mov     edx, 0C37h; void *
0x18000477c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004782  mov     rcx, [rbp+198h]; this
0x180004789  mov     edx, 9E7h; void *
0x18000478e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004794  mov     rcx, [rbp+198h]; this
0x18000479b  mov     edx, 9DDh; void *
0x1800047a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047a6  mov     rcx, [rbp+198h]; this
0x1800047ad  mov     edx, 9E7h; void *
0x1800047b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047b8  mov     rcx, [rbp+198h]; this
0x1800047bf  mov     edx, 9DDh; void *
0x1800047c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800047ca  mov     rcx, [rbp+198h]; this
0x1800047d1  mov     edx, 9E7h; void *
0x1800047d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
