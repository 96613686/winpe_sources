# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180002f5c`
- end: `0x180003221`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180003a6c`

## callees

- `0x180001660`
- `0x180002f5c`
- `0x180003244`
- `0x1800037f0`
- `0x180004210`
- `0x180004914`
- `0x180005114`
- `0x1800051cc`
- `0x1800055e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003005`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003005`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002fd9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002fd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000308c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000310f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003152`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000308c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000310f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003152`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000312d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000316e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000312d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000316e`

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
0x180002f5c  mov     [rsp-8+arg_10], rbx
0x180002f61  mov     [rsp-8+arg_18], rsi
0x180002f66  push    rbp
0x180002f67  push    rdi
0x180002f68  push    r14
0x180002f6a  lea     rbp, [rsp-160h]
0x180002f72  sub     rsp, 260h
0x180002f79  mov     rax, cs:__security_cookie
0x180002f80  xor     rax, rsp
0x180002f83  mov     [rbp+170h+var_20], rax
0x180002f8a  mov     r14, rdx
0x180002f8d  mov     qword ptr [rdx], 0
0x180002f94  mov     rbx, rcx
0x180002f97  call    cs:__imp_GetCurrentProcessId
0x180002f9e  nop     dword ptr [rax+rax+00h]
0x180002fa3  mov     [rsp+270h+var_248], rbx
0x180002fa8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180002faf  mov     r9d, eax
0x180002fb2  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180002fba  mov     edx, 104h; unsigned __int64
0x180002fbf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180002fc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002fc9  mov     r9d, 1F0001h; dwDesiredAccess
0x180002fcf  lea     rdx, [rsp+270h+Name]; lpName
0x180002fd4  xor     r8d, r8d; dwFlags
0x180002fd7  xor     ecx, ecx; lpMutexAttributes
0x180002fd9  call    cs:__imp_CreateMutexExW
0x180002fe0  nop     dword ptr [rax+rax+00h]
0x180002fe5  mov     [rsp+270h+hObject], rax
0x180002fea  mov     rbx, rax
0x180002fed  test    rax, rax
0x180002ff0  jnz     short loc_180002FFC
0x180002ff2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002ff7  jmp     loc_180003180
0x180002ffc  xor     r8d, r8d; bAlertable
0x180002fff  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003002  mov     rcx, rbx; hHandle
0x180003005  call    cs:__imp_WaitForSingleObjectEx
0x18000300c  nop     dword ptr [rax+rax+00h]
0x180003011  cmp     eax, 102h
0x180003016  jz      short loc_180003028
0x180003018  test    eax, 0FFFFFF7Fh
0x18000301d  jnz     loc_1800031BA
0x180003023  mov     rdi, rbx
0x180003026  jmp     short loc_18000302A
0x180003028  xor     edi, edi
0x18000302a  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000302f  mov     [rsp+270h+var_238], 0
0x180003038  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000303d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003042  mov     esi, eax
0x180003044  test    eax, eax
0x180003046  jns     short loc_1800030BE
0x180003048  mov     rcx, [rbp+178h]; this
0x18000304f  mov     r9d, eax; char *
0x180003052  mov     edx, 66h ; 'f'; void *
0x180003057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000305c  mov     rcx, [rbp+178h]; this
0x180003063  mov     r9d, esi; char *
0x180003066  mov     edx, 6Fh ; 'o'; void *
0x18000306b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003070  mov     rcx, [rbp+178h]; this
0x180003077  mov     r9d, esi; char *
0x18000307a  mov     edx, 12Eh; void *
0x18000307f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003084  test    rdi, rdi
0x180003087  jz      short loc_1800030A0
0x180003089  mov     rcx, rdi; hMutex
0x18000308c  call    cs:__imp_ReleaseMutex
0x180003093  nop     dword ptr [rax+rax+00h]
0x180003098  test    eax, eax
0x18000309a  jz      loc_1800031C7
0x1800030a0  mov     rcx, rbx; hObject
0x1800030a3  call    cs:__imp_CloseHandle
0x1800030aa  nop     dword ptr [rax+rax+00h]
0x1800030af  test    eax, eax
0x1800030b1  jz      loc_1800031D9
0x1800030b7  mov     eax, esi
0x1800030b9  jmp     loc_180003180
0x1800030be  mov     rax, [rsp+270h+var_238]
0x1800030c3  lea     rcx, ds:0[rax*4]
0x1800030cb  test    rcx, rcx
0x1800030ce  jz      short loc_1800030DB
0x1800030d0  mov     [r14], rcx
0x1800030d3  mov     eax, [rcx]
0x1800030d5  inc     eax
0x1800030d7  mov     [rcx], eax
0x1800030d9  jmp     short loc_18000314A
0x1800030db  mov     r8, r14
0x1800030de  lea     rdx, [rsp+270h+hObject]
0x1800030e3  lea     rcx, [rsp+270h+Name]
0x1800030e8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800030ed  mov     ebx, eax
0x1800030ef  test    eax, eax
0x1800030f1  jns     short loc_180003145
0x1800030f3  mov     rcx, [rbp+178h]; this
0x1800030fa  mov     r9d, eax; char *
0x1800030fd  mov     edx, 137h; void *
0x180003102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003107  test    rdi, rdi
0x18000310a  jz      short loc_180003123
0x18000310c  mov     rcx, rdi; hMutex
0x18000310f  call    cs:__imp_ReleaseMutex
0x180003116  nop     dword ptr [rax+rax+00h]
0x18000311b  test    eax, eax
0x18000311d  jz      loc_1800031EB
0x180003123  mov     rcx, [rsp+270h+hObject]; hObject
0x180003128  test    rcx, rcx
0x18000312b  jz      short loc_180003141
0x18000312d  call    cs:__imp_CloseHandle
0x180003134  nop     dword ptr [rax+rax+00h]
0x180003139  test    eax, eax
0x18000313b  jz      loc_1800031FD
0x180003141  mov     eax, ebx
0x180003143  jmp     short loc_180003180
0x180003145  mov     rbx, [rsp+270h+hObject]
0x18000314a  test    rdi, rdi
0x18000314d  jz      short loc_180003166
0x18000314f  mov     rcx, rdi; hMutex
0x180003152  call    cs:__imp_ReleaseMutex
0x180003159  nop     dword ptr [rax+rax+00h]
0x18000315e  test    eax, eax
0x180003160  jz      loc_18000320F
0x180003166  test    rbx, rbx
0x180003169  jz      short loc_18000317E
0x18000316b  mov     rcx, rbx; hObject
0x18000316e  call    cs:__imp_CloseHandle
0x180003175  nop     dword ptr [rax+rax+00h]
0x18000317a  test    eax, eax
0x18000317c  jz      short loc_1800031A8
0x18000317e  xor     eax, eax
0x180003180  mov     rcx, [rbp+170h+var_20]
0x180003187  xor     rcx, rsp; StackCookie
0x18000318a  call    __security_check_cookie
0x18000318f  lea     r11, [rsp+270h+var_10]
0x180003197  mov     rbx, [r11+30h]
0x18000319b  mov     rsi, [r11+38h]
0x18000319f  mov     rsp, r11
0x1800031a2  pop     r14
0x1800031a4  pop     rdi
0x1800031a5  pop     rbp
0x1800031a6  retn
0x1800031a8  mov     rcx, [rbp+178h]; this
0x1800031af  mov     edx, 0A0Bh; void *
0x1800031b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031ba  mov     rcx, [rbp+178h]; this
0x1800031c1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800031c7  mov     rcx, [rbp+178h]; this
0x1800031ce  mov     edx, 0A15h; void *
0x1800031d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031d9  mov     rcx, [rbp+178h]; this
0x1800031e0  mov     edx, 0A0Bh; void *
0x1800031e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031eb  mov     rcx, [rbp+178h]; this
0x1800031f2  mov     edx, 0A15h; void *
0x1800031f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031fd  mov     rcx, [rbp+178h]; this
0x180003204  mov     edx, 0A0Bh; void *
0x180003209  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000320f  mov     rcx, [rbp+178h]; this
0x180003216  mov     edx, 0A15h; void *
0x18000321b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
