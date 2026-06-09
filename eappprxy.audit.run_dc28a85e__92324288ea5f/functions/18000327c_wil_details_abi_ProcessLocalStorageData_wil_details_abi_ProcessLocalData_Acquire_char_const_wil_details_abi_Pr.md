# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000327c`
- end: `0x180003541`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180003d8c`

## callees

- `0x180001780`
- `0x18000327c`
- `0x180003564`
- `0x180003b10`
- `0x1800045a0`
- `0x180004c94`
- `0x1800054d0`
- `0x180005714`
- `0x180005d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000342f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003472`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000342f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003472`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800032f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800032f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003325`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800032b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800032b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000344d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000348e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000344d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000348e`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  hObject = Mutex;
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
  v37 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37);
  if ( 4 * v37 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_21;
  }
  v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v25 = v23;
  if ( v23 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)v23, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x18000327c  mov     [rsp-8+arg_10], rbx
0x180003281  mov     [rsp-8+arg_18], rsi
0x180003286  push    rbp
0x180003287  push    rdi
0x180003288  push    r14
0x18000328a  lea     rbp, [rsp-160h]
0x180003292  sub     rsp, 260h
0x180003299  mov     rax, cs:__security_cookie
0x1800032a0  xor     rax, rsp
0x1800032a3  mov     [rbp+170h+var_20], rax
0x1800032aa  mov     r14, rdx
0x1800032ad  mov     qword ptr [rdx], 0
0x1800032b4  mov     rbx, rcx
0x1800032b7  call    cs:__imp_GetCurrentProcessId
0x1800032be  nop     dword ptr [rax+rax+00h]
0x1800032c3  mov     [rsp+270h+var_248], rbx
0x1800032c8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800032cf  mov     r9d, eax
0x1800032d2  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800032da  mov     edx, 104h; unsigned __int64
0x1800032df  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800032e4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800032e9  mov     r9d, 1F0001h; dwDesiredAccess
0x1800032ef  lea     rdx, [rsp+270h+Name]; lpName
0x1800032f4  xor     r8d, r8d; dwFlags
0x1800032f7  xor     ecx, ecx; lpMutexAttributes
0x1800032f9  call    cs:__imp_CreateMutexExW
0x180003300  nop     dword ptr [rax+rax+00h]
0x180003305  mov     [rsp+270h+hObject], rax
0x18000330a  mov     rbx, rax
0x18000330d  test    rax, rax
0x180003310  jnz     short loc_18000331C
0x180003312  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003317  jmp     loc_1800034A0
0x18000331c  xor     r8d, r8d; bAlertable
0x18000331f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003322  mov     rcx, rbx; hHandle
0x180003325  call    cs:__imp_WaitForSingleObjectEx
0x18000332c  nop     dword ptr [rax+rax+00h]
0x180003331  cmp     eax, 102h
0x180003336  jz      short loc_180003348
0x180003338  test    eax, 0FFFFFF7Fh
0x18000333d  jnz     loc_1800034DA
0x180003343  mov     rdi, rbx
0x180003346  jmp     short loc_18000334A
0x180003348  xor     edi, edi
0x18000334a  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000334f  mov     [rsp+270h+var_238], 0
0x180003358  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000335d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180003362  mov     esi, eax
0x180003364  test    eax, eax
0x180003366  jns     short loc_1800033DE
0x180003368  mov     rcx, [rbp+178h]; this
0x18000336f  mov     r9d, eax; char *
0x180003372  mov     edx, 66h ; 'f'; void *
0x180003377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000337c  mov     rcx, [rbp+178h]; this
0x180003383  mov     r9d, esi; char *
0x180003386  mov     edx, 6Fh ; 'o'; void *
0x18000338b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003390  mov     rcx, [rbp+178h]; this
0x180003397  mov     r9d, esi; char *
0x18000339a  mov     edx, 12Eh; void *
0x18000339f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033a4  test    rdi, rdi
0x1800033a7  jz      short loc_1800033C0
0x1800033a9  mov     rcx, rdi; hMutex
0x1800033ac  call    cs:__imp_ReleaseMutex
0x1800033b3  nop     dword ptr [rax+rax+00h]
0x1800033b8  test    eax, eax
0x1800033ba  jz      loc_1800034E7
0x1800033c0  mov     rcx, rbx; hObject
0x1800033c3  call    cs:__imp_CloseHandle
0x1800033ca  nop     dword ptr [rax+rax+00h]
0x1800033cf  test    eax, eax
0x1800033d1  jz      loc_1800034F9
0x1800033d7  mov     eax, esi
0x1800033d9  jmp     loc_1800034A0
0x1800033de  mov     rax, [rsp+270h+var_238]
0x1800033e3  lea     rcx, ds:0[rax*4]
0x1800033eb  test    rcx, rcx
0x1800033ee  jz      short loc_1800033FB
0x1800033f0  mov     [r14], rcx
0x1800033f3  mov     eax, [rcx]
0x1800033f5  inc     eax
0x1800033f7  mov     [rcx], eax
0x1800033f9  jmp     short loc_18000346A
0x1800033fb  mov     r8, r14
0x1800033fe  lea     rdx, [rsp+270h+hObject]
0x180003403  lea     rcx, [rsp+270h+Name]
0x180003408  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000340d  mov     ebx, eax
0x18000340f  test    eax, eax
0x180003411  jns     short loc_180003465
0x180003413  mov     rcx, [rbp+178h]; this
0x18000341a  mov     r9d, eax; char *
0x18000341d  mov     edx, 137h; void *
0x180003422  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003427  test    rdi, rdi
0x18000342a  jz      short loc_180003443
0x18000342c  mov     rcx, rdi; hMutex
0x18000342f  call    cs:__imp_ReleaseMutex
0x180003436  nop     dword ptr [rax+rax+00h]
0x18000343b  test    eax, eax
0x18000343d  jz      loc_18000350B
0x180003443  mov     rcx, [rsp+270h+hObject]; hObject
0x180003448  test    rcx, rcx
0x18000344b  jz      short loc_180003461
0x18000344d  call    cs:__imp_CloseHandle
0x180003454  nop     dword ptr [rax+rax+00h]
0x180003459  test    eax, eax
0x18000345b  jz      loc_18000351D
0x180003461  mov     eax, ebx
0x180003463  jmp     short loc_1800034A0
0x180003465  mov     rbx, [rsp+270h+hObject]
0x18000346a  test    rdi, rdi
0x18000346d  jz      short loc_180003486
0x18000346f  mov     rcx, rdi; hMutex
0x180003472  call    cs:__imp_ReleaseMutex
0x180003479  nop     dword ptr [rax+rax+00h]
0x18000347e  test    eax, eax
0x180003480  jz      loc_18000352F
0x180003486  test    rbx, rbx
0x180003489  jz      short loc_18000349E
0x18000348b  mov     rcx, rbx; hObject
0x18000348e  call    cs:__imp_CloseHandle
0x180003495  nop     dword ptr [rax+rax+00h]
0x18000349a  test    eax, eax
0x18000349c  jz      short loc_1800034C8
0x18000349e  xor     eax, eax
0x1800034a0  mov     rcx, [rbp+170h+var_20]
0x1800034a7  xor     rcx, rsp; StackCookie
0x1800034aa  call    __security_check_cookie
0x1800034af  lea     r11, [rsp+270h+var_10]
0x1800034b7  mov     rbx, [r11+30h]
0x1800034bb  mov     rsi, [r11+38h]
0x1800034bf  mov     rsp, r11
0x1800034c2  pop     r14
0x1800034c4  pop     rdi
0x1800034c5  pop     rbp
0x1800034c6  retn
0x1800034c8  mov     rcx, [rbp+178h]; this
0x1800034cf  mov     edx, 0A0Bh; void *
0x1800034d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034da  mov     rcx, [rbp+178h]; this
0x1800034e1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800034e7  mov     rcx, [rbp+178h]; this
0x1800034ee  mov     edx, 0A15h; void *
0x1800034f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034f9  mov     rcx, [rbp+178h]; this
0x180003500  mov     edx, 0A0Bh; void *
0x180003505  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000350b  mov     rcx, [rbp+178h]; this
0x180003512  mov     edx, 0A15h; void *
0x180003517  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000351d  mov     rcx, [rbp+178h]; this
0x180003524  mov     edx, 0A0Bh; void *
0x180003529  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000352f  mov     rcx, [rbp+178h]; this
0x180003536  mov     edx, 0A15h; void *
0x18000353b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
