# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009a10`
- end: `0x180009cd5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000a4c0`

## callees

- `0x180009a10`
- `0x180009cdc`
- `0x18000a378`
- `0x18000ac68`
- `0x18000b624`
- `0x18000b93c`
- `0x18000b9d0`
- `0x18000bd6c`
- `0x18000d1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009b40`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009b40`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c06`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009a8d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009a8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009ab9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009be1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009be1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a4b`

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
0x180009a10  mov     [rsp-8+arg_10], rbx
0x180009a15  mov     [rsp-8+arg_18], rsi
0x180009a1a  push    rbp
0x180009a1b  push    rdi
0x180009a1c  push    r14
0x180009a1e  lea     rbp, [rsp-160h]
0x180009a26  sub     rsp, 260h
0x180009a2d  mov     rax, cs:__security_cookie
0x180009a34  xor     rax, rsp
0x180009a37  mov     [rbp+170h+var_20], rax
0x180009a3e  mov     r14, rdx
0x180009a41  mov     qword ptr [rdx], 0
0x180009a48  mov     rbx, rcx
0x180009a4b  call    cs:__imp_GetCurrentProcessId
0x180009a52  nop     dword ptr [rax+rax+00h]
0x180009a57  mov     [rsp+270h+var_248], rbx
0x180009a5c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009a63  mov     r9d, eax
0x180009a66  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009a6e  mov     edx, 104h; unsigned __int64
0x180009a73  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009a78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009a7d  mov     r9d, 1F0001h; dwDesiredAccess
0x180009a83  lea     rdx, [rsp+270h+Name]; lpName
0x180009a88  xor     r8d, r8d; dwFlags
0x180009a8b  xor     ecx, ecx; lpMutexAttributes
0x180009a8d  call    cs:__imp_CreateMutexExW
0x180009a94  nop     dword ptr [rax+rax+00h]
0x180009a99  mov     [rsp+270h+hObject], rax
0x180009a9e  mov     rbx, rax
0x180009aa1  test    rax, rax
0x180009aa4  jnz     short loc_180009AB0
0x180009aa6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009aab  jmp     loc_180009C34
0x180009ab0  xor     r8d, r8d; bAlertable
0x180009ab3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009ab6  mov     rcx, rbx; hHandle
0x180009ab9  call    cs:__imp_WaitForSingleObjectEx
0x180009ac0  nop     dword ptr [rax+rax+00h]
0x180009ac5  cmp     eax, 102h
0x180009aca  jz      short loc_180009ADC
0x180009acc  test    eax, 0FFFFFF7Fh
0x180009ad1  jnz     loc_180009C6E
0x180009ad7  mov     rdi, rbx
0x180009ada  jmp     short loc_180009ADE
0x180009adc  xor     edi, edi
0x180009ade  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180009ae3  mov     [rsp+270h+var_238], 0
0x180009aec  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009af1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009af6  mov     esi, eax
0x180009af8  test    eax, eax
0x180009afa  jns     short loc_180009B72
0x180009afc  mov     rcx, [rbp+178h]; this
0x180009b03  mov     r9d, eax; char *
0x180009b06  mov     edx, 66h ; 'f'; void *
0x180009b0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b10  mov     rcx, [rbp+178h]; this
0x180009b17  mov     r9d, esi; char *
0x180009b1a  mov     edx, 6Fh ; 'o'; void *
0x180009b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b24  mov     rcx, [rbp+178h]; this
0x180009b2b  mov     r9d, esi; char *
0x180009b2e  mov     edx, 12Eh; void *
0x180009b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b38  test    rdi, rdi
0x180009b3b  jz      short loc_180009B54
0x180009b3d  mov     rcx, rdi; hMutex
0x180009b40  call    cs:__imp_ReleaseMutex
0x180009b47  nop     dword ptr [rax+rax+00h]
0x180009b4c  test    eax, eax
0x180009b4e  jz      loc_180009C7B
0x180009b54  mov     rcx, rbx; hObject
0x180009b57  call    cs:__imp_CloseHandle
0x180009b5e  nop     dword ptr [rax+rax+00h]
0x180009b63  test    eax, eax
0x180009b65  jz      loc_180009C8D
0x180009b6b  mov     eax, esi
0x180009b6d  jmp     loc_180009C34
0x180009b72  mov     rax, [rsp+270h+var_238]
0x180009b77  lea     rcx, ds:0[rax*4]
0x180009b7f  test    rcx, rcx
0x180009b82  jz      short loc_180009B8F
0x180009b84  mov     [r14], rcx
0x180009b87  mov     eax, [rcx]
0x180009b89  inc     eax
0x180009b8b  mov     [rcx], eax
0x180009b8d  jmp     short loc_180009BFE
0x180009b8f  mov     r8, r14
0x180009b92  lea     rdx, [rsp+270h+hObject]
0x180009b97  lea     rcx, [rsp+270h+Name]
0x180009b9c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009ba1  mov     ebx, eax
0x180009ba3  test    eax, eax
0x180009ba5  jns     short loc_180009BF9
0x180009ba7  mov     rcx, [rbp+178h]; this
0x180009bae  mov     r9d, eax; char *
0x180009bb1  mov     edx, 137h; void *
0x180009bb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bbb  test    rdi, rdi
0x180009bbe  jz      short loc_180009BD7
0x180009bc0  mov     rcx, rdi; hMutex
0x180009bc3  call    cs:__imp_ReleaseMutex
0x180009bca  nop     dword ptr [rax+rax+00h]
0x180009bcf  test    eax, eax
0x180009bd1  jz      loc_180009C9F
0x180009bd7  mov     rcx, [rsp+270h+hObject]; hObject
0x180009bdc  test    rcx, rcx
0x180009bdf  jz      short loc_180009BF5
0x180009be1  call    cs:__imp_CloseHandle
0x180009be8  nop     dword ptr [rax+rax+00h]
0x180009bed  test    eax, eax
0x180009bef  jz      loc_180009CB1
0x180009bf5  mov     eax, ebx
0x180009bf7  jmp     short loc_180009C34
0x180009bf9  mov     rbx, [rsp+270h+hObject]
0x180009bfe  test    rdi, rdi
0x180009c01  jz      short loc_180009C1A
0x180009c03  mov     rcx, rdi; hMutex
0x180009c06  call    cs:__imp_ReleaseMutex
0x180009c0d  nop     dword ptr [rax+rax+00h]
0x180009c12  test    eax, eax
0x180009c14  jz      loc_180009CC3
0x180009c1a  test    rbx, rbx
0x180009c1d  jz      short loc_180009C32
0x180009c1f  mov     rcx, rbx; hObject
0x180009c22  call    cs:__imp_CloseHandle
0x180009c29  nop     dword ptr [rax+rax+00h]
0x180009c2e  test    eax, eax
0x180009c30  jz      short loc_180009C5C
0x180009c32  xor     eax, eax
0x180009c34  mov     rcx, [rbp+170h+var_20]
0x180009c3b  xor     rcx, rsp; StackCookie
0x180009c3e  call    __security_check_cookie
0x180009c43  lea     r11, [rsp+270h+var_10]
0x180009c4b  mov     rbx, [r11+30h]
0x180009c4f  mov     rsi, [r11+38h]
0x180009c53  mov     rsp, r11
0x180009c56  pop     r14
0x180009c58  pop     rdi
0x180009c59  pop     rbp
0x180009c5a  retn
0x180009c5c  mov     rcx, [rbp+178h]; this
0x180009c63  mov     edx, 0A0Bh; void *
0x180009c68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c6e  mov     rcx, [rbp+178h]; this
0x180009c75  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009c7b  mov     rcx, [rbp+178h]; this
0x180009c82  mov     edx, 0A15h; void *
0x180009c87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c8d  mov     rcx, [rbp+178h]; this
0x180009c94  mov     edx, 0A0Bh; void *
0x180009c99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c9f  mov     rcx, [rbp+178h]; this
0x180009ca6  mov     edx, 0A15h; void *
0x180009cab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cb1  mov     rcx, [rbp+178h]; this
0x180009cb8  mov     edx, 0A0Bh; void *
0x180009cbd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cc3  mov     rcx, [rbp+178h]; this
0x180009cca  mov     edx, 0A15h; void *
0x180009ccf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
