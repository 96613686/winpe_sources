# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004bb0`
- end: `0x180004f8f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `991`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005bcc`

## callees

- `0x180004988`
- `0x180004bb0`
- `0x180004fbc`
- `0x18000526c`
- `0x180005870`
- `0x1800064c4`
- `0x180006974`
- `0x180007268`
- `0x18000734c`
- `0x180007834`
- `0x18003586a`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004be9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004be9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c55`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004c2e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004c2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004eb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004de3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ed1`

## string_xrefs

- `0x180004f35`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  _DWORD *v20; // rax
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned __int64 v28; // rax
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v36, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v34);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_23;
  }
  *a2 = 0;
  v20 = wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v22 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v20);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v35);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v36[0];
  v28 = v36[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v36[0] = 0;
  *((_QWORD *)v21 + 3) = v28;
  v36[1] = 0;
  memset_0((char *)v21 + 34, 0, 0x56u);
  *((_WORD *)v21 + 16) = 88;
  v21[9] = 1;
  memset_0(v21 + 10, 0, 0x50u);
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x180004bb0  mov     [rsp-8+arg_10], rbx
0x180004bb5  push    rbp
0x180004bb6  push    rsi
0x180004bb7  push    rdi
0x180004bb8  push    r14
0x180004bba  push    r15
0x180004bbc  lea     rbp, [rsp-160h]
0x180004bc4  sub     rsp, 260h
0x180004bcb  mov     rax, cs:__security_cookie
0x180004bd2  xor     rax, rsp
0x180004bd5  mov     [rbp+180h+var_30], rax
0x180004bdc  mov     r15, rdx
0x180004bdf  mov     qword ptr [rdx], 0
0x180004be6  mov     rbx, rcx
0x180004be9  call    cs:__imp_GetCurrentProcessId
0x180004bf0  nop     dword ptr [rax+rax+00h]
0x180004bf5  mov     r14d, 78h ; 'x'
0x180004bfb  mov     [rsp+280h+var_258], rbx
0x180004c00  mov     r9d, eax
0x180004c03  mov     [rsp+280h+var_260], r14d; int
0x180004c08  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004c0f  mov     edx, 104h; unsigned __int64
0x180004c14  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004c19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004c1e  mov     r9d, 1F0001h; dwDesiredAccess
0x180004c24  lea     rdx, [rsp+280h+Name]; lpName
0x180004c29  xor     r8d, r8d; dwFlags
0x180004c2c  xor     ecx, ecx; lpMutexAttributes
0x180004c2e  call    cs:__imp_CreateMutexExW
0x180004c35  nop     dword ptr [rax+rax+00h]
0x180004c3a  mov     rbx, rax
0x180004c3d  test    rax, rax
0x180004c40  jnz     short loc_180004C4C
0x180004c42  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004c47  jmp     loc_180004EE3
0x180004c4c  xor     r8d, r8d; bAlertable
0x180004c4f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004c52  mov     rcx, rbx; hHandle
0x180004c55  call    cs:__imp_WaitForSingleObjectEx
0x180004c5c  nop     dword ptr [rax+rax+00h]
0x180004c61  cmp     eax, 102h
0x180004c66  jz      short loc_180004C78
0x180004c68  test    eax, 0FFFFFF7Fh
0x180004c6d  jnz     loc_180004F2E
0x180004c73  mov     rdi, rbx
0x180004c76  jmp     short loc_180004C7A
0x180004c78  xor     edi, edi
0x180004c7a  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180004c7f  mov     [rsp+280h+var_250], 0
0x180004c88  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004c8d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004c92  mov     esi, eax
0x180004c94  test    eax, eax
0x180004c96  jns     loc_180004D27
0x180004c9c  mov     rcx, [rbp+188h]; this
0x180004ca3  lea     r8, aWil; "wil"
0x180004caa  mov     r9d, eax; char *
0x180004cad  mov     edx, 66h ; 'f'; void *
0x180004cb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cb7  mov     rcx, [rbp+188h]; this
0x180004cbe  lea     r8, aWil; "wil"
0x180004cc5  mov     r9d, esi; char *
0x180004cc8  mov     edx, 6Fh ; 'o'; void *
0x180004ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cd2  mov     rcx, [rbp+188h]; this
0x180004cd9  lea     r8, aWil; "wil"
0x180004ce0  mov     r9d, esi; char *
0x180004ce3  mov     edx, 12Eh; void *
0x180004ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ced  test    rdi, rdi
0x180004cf0  jz      short loc_180004D09
0x180004cf2  mov     rcx, rdi; hMutex
0x180004cf5  call    cs:__imp_ReleaseMutex
0x180004cfc  nop     dword ptr [rax+rax+00h]
0x180004d01  test    eax, eax
0x180004d03  jz      loc_180004F47
0x180004d09  mov     rcx, rbx; hObject
0x180004d0c  call    cs:__imp_CloseHandle
0x180004d13  nop     dword ptr [rax+rax+00h]
0x180004d18  test    eax, eax
0x180004d1a  jz      loc_180004F59
0x180004d20  mov     eax, esi
0x180004d22  jmp     loc_180004EE3
0x180004d27  mov     rax, [rsp+280h+var_250]
0x180004d2c  lea     rcx, ds:0[rax*4]
0x180004d34  test    rcx, rcx
0x180004d37  jz      short loc_180004D47
0x180004d39  mov     [r15], rcx
0x180004d3c  mov     eax, [rcx]
0x180004d3e  inc     eax
0x180004d40  mov     [rcx], eax
0x180004d42  jmp     loc_180004EAD
0x180004d47  mov     rdx, r14; dwBytes
0x180004d4a  mov     qword ptr [r15], 0
0x180004d51  mov     ecx, 8; dwFlags
0x180004d56  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d5b  mov     r14, rax
0x180004d5e  test    rax, rax
0x180004d61  jnz     short loc_180004D85
0x180004d63  mov     rcx, [rbp+188h]; this
0x180004d6a  lea     r8, aWil; "wil"
0x180004d71  mov     esi, 8007000Eh
0x180004d76  mov     edx, 14Bh; void *
0x180004d7b  mov     r9d, esi; char *
0x180004d7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d83  jmp     short loc_180004DEF
0x180004d85  xorps   xmm0, xmm0
0x180004d88  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004d8d  mov     r8, r14; void *
0x180004d90  lea     rcx, [rsp+280h+var_250]; this
0x180004d95  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180004d9b  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180004da0  mov     esi, eax
0x180004da2  test    eax, eax
0x180004da4  jns     loc_180004E42
0x180004daa  mov     rcx, [rbp+188h]; this
0x180004db1  lea     r8, aWil; "wil"
0x180004db8  mov     r9d, eax; char *
0x180004dbb  mov     edx, 14Eh; void *
0x180004dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dc5  lea     rcx, [rsp+280h+var_250]; this
0x180004dca  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004dcf  call    cs:__imp_GetProcessHeap
0x180004dd6  nop     dword ptr [rax+rax+00h]
0x180004ddb  mov     r8, r14; lpMem
0x180004dde  xor     edx, edx; dwFlags
0x180004de0  mov     rcx, rax; hHeap
0x180004de3  call    cs:__imp_HeapFree
0x180004dea  nop     dword ptr [rax+rax+00h]
0x180004def  mov     rcx, [rbp+188h]; this
0x180004df6  lea     r8, aWil; "wil"
0x180004dfd  mov     r9d, esi; char *
0x180004e00  mov     edx, 137h; void *
0x180004e05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e0a  test    rdi, rdi
0x180004e0d  jz      short loc_180004E26
0x180004e0f  mov     rcx, rdi; hMutex
0x180004e12  call    cs:__imp_ReleaseMutex
0x180004e19  nop     dword ptr [rax+rax+00h]
0x180004e1e  test    eax, eax
0x180004e20  jz      loc_180004F6B
0x180004e26  mov     rcx, rbx; hObject
0x180004e29  call    cs:__imp_CloseHandle
0x180004e30  nop     dword ptr [rax+rax+00h]
0x180004e35  test    eax, eax
0x180004e37  jz      loc_180004F1C
0x180004e3d  jmp     loc_180004D20
0x180004e42  mov     rax, [rsp+280h+var_250]
0x180004e47  lea     rcx, [r14+22h]; void *
0x180004e4b  xor     edx, edx; Val
0x180004e4d  mov     [r14+10h], rax
0x180004e51  mov     rax, [rsp+280h+var_250+8]
0x180004e56  mov     dword ptr [r14], 1
0x180004e5d  mov     [r14+8], rbx
0x180004e61  lea     r8d, [rdx+56h]; Size
0x180004e65  mov     [rsp+280h+var_250], 0
0x180004e6e  mov     [r14+18h], rax
0x180004e72  mov     [rsp+280h+var_250+8], 0
0x180004e7b  call    memset_0
0x180004e80  xor     edx, edx; Val
0x180004e82  mov     word ptr [r14+20h], 58h ; 'X'
0x180004e89  lea     rcx, [r14+28h]; void *
0x180004e8d  mov     dword ptr [r14+24h], 1
0x180004e95  lea     r8d, [rdx+50h]; Size
0x180004e99  call    memset_0
0x180004e9e  lea     rcx, [rsp+280h+var_250]; this
0x180004ea3  mov     [r15], r14
0x180004ea6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004eab  xor     ebx, ebx
0x180004ead  test    rdi, rdi
0x180004eb0  jz      short loc_180004EC9
0x180004eb2  mov     rcx, rdi; hMutex
0x180004eb5  call    cs:__imp_ReleaseMutex
0x180004ebc  nop     dword ptr [rax+rax+00h]
0x180004ec1  test    eax, eax
0x180004ec3  jz      loc_180004F7D
0x180004ec9  test    rbx, rbx
0x180004ecc  jz      short loc_180004EE1
0x180004ece  mov     rcx, rbx; hObject
0x180004ed1  call    cs:__imp_CloseHandle
0x180004ed8  nop     dword ptr [rax+rax+00h]
0x180004edd  test    eax, eax
0x180004edf  jz      short loc_180004F0A
0x180004ee1  xor     eax, eax
0x180004ee3  mov     rcx, [rbp+180h+var_30]
0x180004eea  xor     rcx, rsp; StackCookie
0x180004eed  call    __security_check_cookie
0x180004ef2  mov     rbx, [rsp+280h+arg_10]
0x180004efa  add     rsp, 260h
0x180004f01  pop     r15
0x180004f03  pop     r14
0x180004f05  pop     rdi
0x180004f06  pop     rsi
0x180004f07  pop     rbp
0x180004f08  retn
0x180004f0a  mov     rcx, [rbp+188h]; this
0x180004f11  mov     edx, 0A0Bh; void *
0x180004f16  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f1c  mov     rcx, [rbp+188h]; this
0x180004f23  mov     edx, 0A0Bh; void *
0x180004f28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f2e  mov     rcx, [rbp+188h]; this
0x180004f35  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f3c  mov     edx, 0E01h; void *
0x180004f41  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004f47  mov     rcx, [rbp+188h]; this
0x180004f4e  mov     edx, 0A15h; void *
0x180004f53  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f59  mov     rcx, [rbp+188h]; this
0x180004f60  mov     edx, 0A0Bh; void *
0x180004f65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f6b  mov     rcx, [rbp+188h]; this
0x180004f72  mov     edx, 0A15h; void *
0x180004f77  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f7d  mov     rcx, [rbp+188h]; this
0x180004f84  mov     edx, 0A15h; void *
0x180004f89  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
