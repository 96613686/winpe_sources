# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000eb58`
- end: `0x14000eef6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140010380`

## callees

- `0x140002f60`
- `0x140003b28`
- `0x14000eb58`
- `0x14000f2cc`
- `0x14000f7e8`
- `0x140010118`
- `0x140010df8`
- `0x140012554`
- `0x140013048`
- `0x1400134cc`
- `0x140013d7c`
- `0x140013d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ec72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ed9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ee0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ec72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ed9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ee0b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000ebd0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000ebd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ebf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ebf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ed79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ed79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ed6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ed6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000eb91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000eb91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ec83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ed45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ed5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000edac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ee21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ec83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ed45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ed5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000edac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ee21`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
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
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x14000eb58  mov     [rsp-8+arg_10], rbx
0x14000eb5d  push    rbp
0x14000eb5e  push    rsi
0x14000eb5f  push    rdi
0x14000eb60  push    r14
0x14000eb62  push    r15
0x14000eb64  lea     rbp, [rsp-160h]
0x14000eb6c  sub     rsp, 260h
0x14000eb73  mov     rax, cs:__security_cookie
0x14000eb7a  xor     rax, rsp
0x14000eb7d  mov     [rbp+180h+var_30], rax
0x14000eb84  mov     r15, rdx
0x14000eb87  mov     qword ptr [rdx], 0
0x14000eb8e  mov     rbx, rcx
0x14000eb91  call    cs:__imp_GetCurrentProcessId
0x14000eb97  mov     r14d, 78h ; 'x'
0x14000eb9d  mov     [rsp+280h+var_258], rbx
0x14000eba2  mov     r9d, eax
0x14000eba5  mov     [rsp+280h+var_260], r14d; int
0x14000ebaa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000ebb1  mov     edx, 104h; unsigned __int64
0x14000ebb6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ebbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ebc0  mov     r9d, 1F0001h; dwDesiredAccess
0x14000ebc6  lea     rdx, [rsp+280h+Name]; lpName
0x14000ebcb  xor     r8d, r8d; dwFlags
0x14000ebce  xor     ecx, ecx; lpMutexAttributes
0x14000ebd0  call    cs:__imp_CreateMutexExW
0x14000ebd6  mov     rbx, rax
0x14000ebd9  test    rax, rax
0x14000ebdc  jnz     short loc_14000EBE8
0x14000ebde  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000ebe3  jmp     loc_14000EE2D
0x14000ebe8  xor     r8d, r8d; bAlertable
0x14000ebeb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000ebee  mov     rcx, rbx; hHandle
0x14000ebf1  call    cs:__imp_WaitForSingleObjectEx
0x14000ebf7  cmp     eax, 102h
0x14000ebfc  jz      short loc_14000EC0E
0x14000ebfe  test    eax, 0FFFFFF7Fh
0x14000ec03  jnz     loc_14000EE65
0x14000ec09  mov     rdi, rbx
0x14000ec0c  jmp     short loc_14000EC10
0x14000ec0e  xor     edi, edi
0x14000ec10  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000ec15  mov     [rsp+280h+hObject], 0
0x14000ec1e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ec23  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000ec28  mov     esi, eax
0x14000ec2a  test    eax, eax
0x14000ec2c  jns     short loc_14000EC98
0x14000ec2e  mov     rcx, [rbp+188h]; this
0x14000ec35  mov     r9d, eax; char *
0x14000ec38  mov     edx, 66h ; 'f'; void *
0x14000ec3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ec42  mov     rcx, [rbp+188h]; this
0x14000ec49  mov     r9d, esi; char *
0x14000ec4c  mov     edx, 6Fh ; 'o'; void *
0x14000ec51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ec56  mov     rcx, [rbp+188h]; this
0x14000ec5d  mov     r9d, esi; char *
0x14000ec60  mov     edx, 12Eh; void *
0x14000ec65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ec6a  test    rdi, rdi
0x14000ec6d  jz      short loc_14000EC80
0x14000ec6f  mov     rcx, rdi; hMutex
0x14000ec72  call    cs:__imp_ReleaseMutex
0x14000ec78  test    eax, eax
0x14000ec7a  jz      loc_14000EE72
0x14000ec80  mov     rcx, rbx; hObject
0x14000ec83  call    cs:__imp_CloseHandle
0x14000ec89  test    eax, eax
0x14000ec8b  jz      loc_14000EE84
0x14000ec91  mov     eax, esi
0x14000ec93  jmp     loc_14000EE2D
0x14000ec98  mov     rax, [rsp+280h+hObject]
0x14000ec9d  lea     rcx, ds:0[rax*4]
0x14000eca5  test    rcx, rcx
0x14000eca8  jz      short loc_14000ECB8
0x14000ecaa  mov     [r15], rcx
0x14000ecad  mov     eax, [rcx]
0x14000ecaf  inc     eax
0x14000ecb1  mov     [rcx], eax
0x14000ecb3  jmp     loc_14000EE03
0x14000ecb8  mov     rdx, r14; dwBytes
0x14000ecbb  mov     qword ptr [r15], 0
0x14000ecc2  mov     ecx, 8; dwFlags
0x14000ecc7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000eccc  mov     rsi, rax
0x14000eccf  test    rax, rax
0x14000ecd2  jnz     short loc_14000ECF3
0x14000ecd4  mov     rcx, [rbp+188h]; this
0x14000ecdb  mov     r14d, 8007000Eh
0x14000ece1  mov     r9d, r14d; char *
0x14000ece4  mov     edx, 14Bh; void *
0x14000ece9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ecee  jmp     loc_14000ED7F
0x14000ecf3  xorps   xmm0, xmm0
0x14000ecf6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000ecfc  test    sil, 3
0x14000ed00  jnz     loc_14000EE96
0x14000ed06  mov     r9, rsi
0x14000ed09  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000ed0e  shr     r9, 2; unsigned __int64
0x14000ed12  lea     rcx, [rsp+280h+hObject]; this
0x14000ed17  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000ed1c  mov     r14d, eax
0x14000ed1f  test    eax, eax
0x14000ed21  jns     loc_14000EDBF
0x14000ed27  mov     rcx, [rbp+188h]; this
0x14000ed2e  mov     r9d, eax; char *
0x14000ed31  mov     edx, 14Eh; void *
0x14000ed36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ed3b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000ed40  test    rcx, rcx
0x14000ed43  jz      short loc_14000ED53
0x14000ed45  call    cs:__imp_CloseHandle
0x14000ed4b  test    eax, eax
0x14000ed4d  jz      loc_14000EE9C
0x14000ed53  mov     rcx, [rsp+280h+hObject]; hObject
0x14000ed58  test    rcx, rcx
0x14000ed5b  jz      short loc_14000ED6B
0x14000ed5d  call    cs:__imp_CloseHandle
0x14000ed63  test    eax, eax
0x14000ed65  jz      loc_14000EEAE
0x14000ed6b  call    cs:__imp_GetProcessHeap
0x14000ed71  mov     r8, rsi; lpMem
0x14000ed74  xor     edx, edx; dwFlags
0x14000ed76  mov     rcx, rax; hHeap
0x14000ed79  call    cs:__imp_HeapFree
0x14000ed7f  mov     rcx, [rbp+188h]; this
0x14000ed86  mov     r9d, r14d; char *
0x14000ed89  mov     edx, 137h; void *
0x14000ed8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ed93  test    rdi, rdi
0x14000ed96  jz      short loc_14000EDA9
0x14000ed98  mov     rcx, rdi; hMutex
0x14000ed9b  call    cs:__imp_ReleaseMutex
0x14000eda1  test    eax, eax
0x14000eda3  jz      loc_14000EEC0
0x14000eda9  mov     rcx, rbx; hObject
0x14000edac  call    cs:__imp_CloseHandle
0x14000edb2  test    eax, eax
0x14000edb4  jz      loc_14000EED2
0x14000edba  mov     eax, r14d
0x14000edbd  jmp     short loc_14000EE2D
0x14000edbf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000edc4  xor     edx, edx; Val
0x14000edc6  mov     dword ptr [rsi], 1
0x14000edcc  lea     rcx, [rsi+22h]; void *
0x14000edd0  mov     [rsi+8], rbx
0x14000edd4  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000edd9  lea     r8d, [rdx+56h]; Size
0x14000eddd  call    memset_0
0x14000ede2  xor     edx, edx; Val
0x14000ede4  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000edea  lea     rcx, [rsi+28h]; void *
0x14000edee  mov     dword ptr [rsi+24h], 1
0x14000edf5  lea     r8d, [rdx+50h]; Size
0x14000edf9  call    memset_0
0x14000edfe  xor     ebx, ebx
0x14000ee00  mov     [r15], rsi
0x14000ee03  test    rdi, rdi
0x14000ee06  jz      short loc_14000EE19
0x14000ee08  mov     rcx, rdi; hMutex
0x14000ee0b  call    cs:__imp_ReleaseMutex
0x14000ee11  test    eax, eax
0x14000ee13  jz      loc_14000EEE4
0x14000ee19  test    rbx, rbx
0x14000ee1c  jz      short loc_14000EE2B
0x14000ee1e  mov     rcx, rbx; hObject
0x14000ee21  call    cs:__imp_CloseHandle
0x14000ee27  test    eax, eax
0x14000ee29  jz      short loc_14000EE53
0x14000ee2b  xor     eax, eax
0x14000ee2d  mov     rcx, [rbp+180h+var_30]
0x14000ee34  xor     rcx, rsp; StackCookie
0x14000ee37  call    __security_check_cookie
0x14000ee3c  mov     rbx, [rsp+280h+arg_10]
0x14000ee44  add     rsp, 260h
0x14000ee4b  pop     r15
0x14000ee4d  pop     r14
0x14000ee4f  pop     rdi
0x14000ee50  pop     rsi
0x14000ee51  pop     rbp
0x14000ee52  retn
0x14000ee53  mov     rcx, [rbp+188h]; this
0x14000ee5a  mov     edx, 0A0Bh; void *
0x14000ee5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ee65  mov     rcx, [rbp+188h]; this
0x14000ee6c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000ee72  mov     rcx, [rbp+188h]; this
0x14000ee79  mov     edx, 0A15h; void *
0x14000ee7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ee84  mov     rcx, [rbp+188h]; this
0x14000ee8b  mov     edx, 0A0Bh; void *
0x14000ee90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ee96  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ee9c  mov     rcx, [rbp+188h]; this
0x14000eea3  mov     edx, 0A0Bh; void *
0x14000eea8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000eeae  mov     rcx, [rbp+188h]; this
0x14000eeb5  mov     edx, 0A0Bh; void *
0x14000eeba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000eec0  mov     rcx, [rbp+188h]; this
0x14000eec7  mov     edx, 0A15h; void *
0x14000eecc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000eed2  mov     rcx, [rbp+188h]; this
0x14000eed9  mov     edx, 0A0Bh; void *
0x14000eede  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000eee4  mov     rcx, [rbp+188h]; this
0x14000eeeb  mov     edx, 0A15h; void *
0x14000eef0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
