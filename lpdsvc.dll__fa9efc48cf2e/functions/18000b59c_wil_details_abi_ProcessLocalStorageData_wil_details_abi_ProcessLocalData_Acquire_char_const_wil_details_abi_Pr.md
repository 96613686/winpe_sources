# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b59c`
- end: `0x18000b93a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000c45c`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x18000b59c`
- `0x18000b940`
- `0x18000bb70`
- `0x18000c1f8`
- `0x18000ccc8`
- `0x18000cf84`
- `0x18000d2e0`
- `0x18000d36c`
- `0x18000d71c`
- `0x18000d72c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000b5d5`
- `KERNEL32!GetCurrentProcessId` at `0x18000b5d5`
- `KERNEL32!CloseHandle` at `0x18000b6c7`
- `KERNEL32!CloseHandle` at `0x18000b789`
- `KERNEL32!CloseHandle` at `0x18000b7a1`
- `KERNEL32!CloseHandle` at `0x18000b7f0`
- `KERNEL32!CloseHandle` at `0x18000b865`
- `KERNEL32!CloseHandle` at `0x18000b6c7`
- `KERNEL32!CloseHandle` at `0x18000b789`
- `KERNEL32!CloseHandle` at `0x18000b7a1`
- `KERNEL32!CloseHandle` at `0x18000b7f0`
- `KERNEL32!CloseHandle` at `0x18000b865`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b614`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b614`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b635`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b635`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b6b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b7df`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b84f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b6b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b7df`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b84f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7bd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
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
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x18000b59c  mov     [rsp-8+arg_10], rbx
0x18000b5a1  push    rbp
0x18000b5a2  push    rsi
0x18000b5a3  push    rdi
0x18000b5a4  push    r14
0x18000b5a6  push    r15
0x18000b5a8  lea     rbp, [rsp-160h]
0x18000b5b0  sub     rsp, 260h
0x18000b5b7  mov     rax, cs:__security_cookie
0x18000b5be  xor     rax, rsp
0x18000b5c1  mov     [rbp+180h+var_30], rax
0x18000b5c8  mov     r15, rdx
0x18000b5cb  mov     qword ptr [rdx], 0
0x18000b5d2  mov     rbx, rcx
0x18000b5d5  call    cs:__imp_GetCurrentProcessId
0x18000b5db  mov     r14d, 78h ; 'x'
0x18000b5e1  mov     [rsp+280h+var_258], rbx
0x18000b5e6  mov     r9d, eax
0x18000b5e9  mov     [rsp+280h+var_260], r14d; int
0x18000b5ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b5f5  mov     edx, 104h; unsigned __int64
0x18000b5fa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b5ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b604  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b60a  lea     rdx, [rsp+280h+Name]; lpName
0x18000b60f  xor     r8d, r8d; dwFlags
0x18000b612  xor     ecx, ecx; lpMutexAttributes
0x18000b614  call    cs:__imp_CreateMutexExW
0x18000b61a  mov     rbx, rax
0x18000b61d  test    rax, rax
0x18000b620  jnz     short loc_18000B62C
0x18000b622  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b627  jmp     loc_18000B871
0x18000b62c  xor     r8d, r8d; bAlertable
0x18000b62f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b632  mov     rcx, rbx; hHandle
0x18000b635  call    cs:__imp_WaitForSingleObjectEx
0x18000b63b  cmp     eax, 102h
0x18000b640  jz      short loc_18000B652
0x18000b642  test    eax, 0FFFFFF7Fh
0x18000b647  jnz     loc_18000B8A9
0x18000b64d  mov     rdi, rbx
0x18000b650  jmp     short loc_18000B654
0x18000b652  xor     edi, edi
0x18000b654  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000b659  mov     [rsp+280h+hObject], 0
0x18000b662  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b667  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b66c  mov     esi, eax
0x18000b66e  test    eax, eax
0x18000b670  jns     short loc_18000B6DC
0x18000b672  mov     rcx, [rbp+188h]; this
0x18000b679  mov     r9d, eax; char *
0x18000b67c  mov     edx, 66h ; 'f'; void *
0x18000b681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b686  mov     rcx, [rbp+188h]; this
0x18000b68d  mov     r9d, esi; char *
0x18000b690  mov     edx, 6Fh ; 'o'; void *
0x18000b695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b69a  mov     rcx, [rbp+188h]; this
0x18000b6a1  mov     r9d, esi; char *
0x18000b6a4  mov     edx, 12Eh; void *
0x18000b6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6ae  test    rdi, rdi
0x18000b6b1  jz      short loc_18000B6C4
0x18000b6b3  mov     rcx, rdi; hMutex
0x18000b6b6  call    cs:__imp_ReleaseMutex
0x18000b6bc  test    eax, eax
0x18000b6be  jz      loc_18000B8B6
0x18000b6c4  mov     rcx, rbx; hObject
0x18000b6c7  call    cs:__imp_CloseHandle
0x18000b6cd  test    eax, eax
0x18000b6cf  jz      loc_18000B8C8
0x18000b6d5  mov     eax, esi
0x18000b6d7  jmp     loc_18000B871
0x18000b6dc  mov     rax, [rsp+280h+hObject]
0x18000b6e1  lea     rcx, ds:0[rax*4]
0x18000b6e9  test    rcx, rcx
0x18000b6ec  jz      short loc_18000B6FC
0x18000b6ee  mov     [r15], rcx
0x18000b6f1  mov     eax, [rcx]
0x18000b6f3  inc     eax
0x18000b6f5  mov     [rcx], eax
0x18000b6f7  jmp     loc_18000B847
0x18000b6fc  mov     rdx, r14; dwBytes
0x18000b6ff  mov     qword ptr [r15], 0
0x18000b706  mov     ecx, 8; dwFlags
0x18000b70b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b710  mov     rsi, rax
0x18000b713  test    rax, rax
0x18000b716  jnz     short loc_18000B737
0x18000b718  mov     rcx, [rbp+188h]; this
0x18000b71f  mov     r14d, 8007000Eh
0x18000b725  mov     r9d, r14d; char *
0x18000b728  mov     edx, 14Bh; void *
0x18000b72d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b732  jmp     loc_18000B7C3
0x18000b737  xorps   xmm0, xmm0
0x18000b73a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000b740  test    sil, 3
0x18000b744  jnz     loc_18000B8DA
0x18000b74a  mov     r9, rsi
0x18000b74d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000b752  shr     r9, 2; unsigned __int64
0x18000b756  lea     rcx, [rsp+280h+hObject]; this
0x18000b75b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000b760  mov     r14d, eax
0x18000b763  test    eax, eax
0x18000b765  jns     loc_18000B803
0x18000b76b  mov     rcx, [rbp+188h]; this
0x18000b772  mov     r9d, eax; char *
0x18000b775  mov     edx, 14Eh; void *
0x18000b77a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b77f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000b784  test    rcx, rcx
0x18000b787  jz      short loc_18000B797
0x18000b789  call    cs:__imp_CloseHandle
0x18000b78f  test    eax, eax
0x18000b791  jz      loc_18000B8E0
0x18000b797  mov     rcx, [rsp+280h+hObject]; hObject
0x18000b79c  test    rcx, rcx
0x18000b79f  jz      short loc_18000B7AF
0x18000b7a1  call    cs:__imp_CloseHandle
0x18000b7a7  test    eax, eax
0x18000b7a9  jz      loc_18000B8F2
0x18000b7af  call    cs:__imp_GetProcessHeap
0x18000b7b5  mov     r8, rsi; lpMem
0x18000b7b8  xor     edx, edx; dwFlags
0x18000b7ba  mov     rcx, rax; hHeap
0x18000b7bd  call    cs:__imp_HeapFree
0x18000b7c3  mov     rcx, [rbp+188h]; this
0x18000b7ca  mov     r9d, r14d; char *
0x18000b7cd  mov     edx, 137h; void *
0x18000b7d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7d7  test    rdi, rdi
0x18000b7da  jz      short loc_18000B7ED
0x18000b7dc  mov     rcx, rdi; hMutex
0x18000b7df  call    cs:__imp_ReleaseMutex
0x18000b7e5  test    eax, eax
0x18000b7e7  jz      loc_18000B904
0x18000b7ed  mov     rcx, rbx; hObject
0x18000b7f0  call    cs:__imp_CloseHandle
0x18000b7f6  test    eax, eax
0x18000b7f8  jz      loc_18000B916
0x18000b7fe  mov     eax, r14d
0x18000b801  jmp     short loc_18000B871
0x18000b803  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000b808  xor     edx, edx; Val
0x18000b80a  mov     dword ptr [rsi], 1
0x18000b810  lea     rcx, [rsi+22h]; void *
0x18000b814  mov     [rsi+8], rbx
0x18000b818  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000b81d  lea     r8d, [rdx+56h]; Size
0x18000b821  call    memset_0
0x18000b826  xor     edx, edx; Val
0x18000b828  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000b82e  lea     rcx, [rsi+28h]; void *
0x18000b832  mov     dword ptr [rsi+24h], 1
0x18000b839  lea     r8d, [rdx+50h]; Size
0x18000b83d  call    memset_0
0x18000b842  xor     ebx, ebx
0x18000b844  mov     [r15], rsi
0x18000b847  test    rdi, rdi
0x18000b84a  jz      short loc_18000B85D
0x18000b84c  mov     rcx, rdi; hMutex
0x18000b84f  call    cs:__imp_ReleaseMutex
0x18000b855  test    eax, eax
0x18000b857  jz      loc_18000B928
0x18000b85d  test    rbx, rbx
0x18000b860  jz      short loc_18000B86F
0x18000b862  mov     rcx, rbx; hObject
0x18000b865  call    cs:__imp_CloseHandle
0x18000b86b  test    eax, eax
0x18000b86d  jz      short loc_18000B897
0x18000b86f  xor     eax, eax
0x18000b871  mov     rcx, [rbp+180h+var_30]
0x18000b878  xor     rcx, rsp; StackCookie
0x18000b87b  call    __security_check_cookie
0x18000b880  mov     rbx, [rsp+280h+arg_10]
0x18000b888  add     rsp, 260h
0x18000b88f  pop     r15
0x18000b891  pop     r14
0x18000b893  pop     rdi
0x18000b894  pop     rsi
0x18000b895  pop     rbp
0x18000b896  retn
0x18000b897  mov     rcx, [rbp+188h]; this
0x18000b89e  mov     edx, 0A0Bh; void *
0x18000b8a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b8a9  mov     rcx, [rbp+188h]; this
0x18000b8b0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000b8b6  mov     rcx, [rbp+188h]; this
0x18000b8bd  mov     edx, 0A15h; void *
0x18000b8c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b8c8  mov     rcx, [rbp+188h]; this
0x18000b8cf  mov     edx, 0A0Bh; void *
0x18000b8d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b8da  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b8e0  mov     rcx, [rbp+188h]; this
0x18000b8e7  mov     edx, 0A0Bh; void *
0x18000b8ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b8f2  mov     rcx, [rbp+188h]; this
0x18000b8f9  mov     edx, 0A0Bh; void *
0x18000b8fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b904  mov     rcx, [rbp+188h]; this
0x18000b90b  mov     edx, 0A15h; void *
0x18000b910  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b916  mov     rcx, [rbp+188h]; this
0x18000b91d  mov     edx, 0A0Bh; void *
0x18000b922  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b928  mov     rcx, [rbp+188h]; this
0x18000b92f  mov     edx, 0A15h; void *
0x18000b934  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
