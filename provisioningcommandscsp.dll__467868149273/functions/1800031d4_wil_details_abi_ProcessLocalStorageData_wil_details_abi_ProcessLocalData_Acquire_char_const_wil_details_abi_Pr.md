# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800031d4`
- end: `0x1800034b9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180003dd4`

## callees

- `0x1800031d4`
- `0x180003584`
- `0x180003b50`
- `0x1800045a8`
- `0x180004ee4`
- `0x1800056ec`
- `0x1800057dc`
- `0x180005cf8`
- `0x18000ccc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000331d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000331d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800033ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000327d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000327d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003251`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003251`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000320f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000320f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003406`

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
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
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
  v33 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v33, (bool *)v11);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * v33);
  if ( 4 * v33 )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_21;
  }
  v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v20, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v22, v23);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x1800031d4  mov     [rsp-8+arg_10], rbx
0x1800031d9  mov     [rsp-8+arg_18], rsi
0x1800031de  push    rbp
0x1800031df  push    rdi
0x1800031e0  push    r14
0x1800031e2  lea     rbp, [rsp-160h]
0x1800031ea  sub     rsp, 260h
0x1800031f1  mov     rax, cs:__security_cookie
0x1800031f8  xor     rax, rsp
0x1800031fb  mov     [rbp+170h+var_20], rax
0x180003202  mov     r14, rdx
0x180003205  mov     qword ptr [rdx], 0
0x18000320c  mov     rbx, rcx
0x18000320f  call    cs:__imp_GetCurrentProcessId
0x180003216  nop     dword ptr [rax+rax+00h]
0x18000321b  mov     [rsp+270h+var_248], rbx
0x180003220  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003227  mov     r9d, eax
0x18000322a  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003232  mov     edx, 104h; unsigned __int64
0x180003237  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000323c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003241  mov     r9d, 1F0001h; dwDesiredAccess
0x180003247  lea     rdx, [rsp+270h+Name]; lpName
0x18000324c  xor     r8d, r8d; dwFlags
0x18000324f  xor     ecx, ecx; lpMutexAttributes
0x180003251  call    cs:__imp_CreateMutexExW
0x180003258  nop     dword ptr [rax+rax+00h]
0x18000325d  mov     [rsp+270h+hObject], rax
0x180003262  mov     rbx, rax
0x180003265  test    rax, rax
0x180003268  jnz     short loc_180003274
0x18000326a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000326f  jmp     loc_180003418
0x180003274  xor     r8d, r8d; bAlertable
0x180003277  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000327a  mov     rcx, rbx; hHandle
0x18000327d  call    cs:__imp_WaitForSingleObjectEx
0x180003284  nop     dword ptr [rax+rax+00h]
0x180003289  cmp     eax, 102h
0x18000328e  jz      short loc_1800032A0
0x180003290  test    eax, 0FFFFFF7Fh
0x180003295  jnz     loc_180003452
0x18000329b  mov     rdi, rbx
0x18000329e  jmp     short loc_1800032A2
0x1800032a0  xor     edi, edi
0x1800032a2  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x1800032a7  mov     [rsp+270h+var_238], 0
0x1800032b0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800032b5  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800032ba  mov     esi, eax
0x1800032bc  test    eax, eax
0x1800032be  jns     loc_18000334F
0x1800032c4  mov     rcx, [rbp+178h]; this
0x1800032cb  lea     r8, aWil; "wil"
0x1800032d2  mov     r9d, eax; char *
0x1800032d5  mov     edx, 66h ; 'f'; void *
0x1800032da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032df  mov     rcx, [rbp+178h]; this
0x1800032e6  lea     r8, aWil; "wil"
0x1800032ed  mov     r9d, esi; char *
0x1800032f0  mov     edx, 6Fh ; 'o'; void *
0x1800032f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800032fa  mov     rcx, [rbp+178h]; this
0x180003301  lea     r8, aWil; "wil"
0x180003308  mov     r9d, esi; char *
0x18000330b  mov     edx, 12Eh; void *
0x180003310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003315  test    rdi, rdi
0x180003318  jz      short loc_180003331
0x18000331a  mov     rcx, rdi; hMutex
0x18000331d  call    cs:__imp_ReleaseMutex
0x180003324  nop     dword ptr [rax+rax+00h]
0x180003329  test    eax, eax
0x18000332b  jz      loc_18000345F
0x180003331  mov     rcx, rbx; hObject
0x180003334  call    cs:__imp_CloseHandle
0x18000333b  nop     dword ptr [rax+rax+00h]
0x180003340  test    eax, eax
0x180003342  jz      loc_180003471
0x180003348  mov     eax, esi
0x18000334a  jmp     loc_180003418
0x18000334f  mov     rax, [rsp+270h+var_238]
0x180003354  lea     rcx, ds:0[rax*4]
0x18000335c  test    rcx, rcx
0x18000335f  jz      short loc_18000336C
0x180003361  mov     [r14], rcx
0x180003364  mov     eax, [rcx]
0x180003366  inc     eax
0x180003368  mov     [rcx], eax
0x18000336a  jmp     short loc_1800033E2
0x18000336c  mov     r8, r14
0x18000336f  lea     rdx, [rsp+270h+hObject]
0x180003374  lea     rcx, [rsp+270h+Name]
0x180003379  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000337e  mov     ebx, eax
0x180003380  test    eax, eax
0x180003382  jns     short loc_1800033DD
0x180003384  mov     rcx, [rbp+178h]; this
0x18000338b  lea     r8, aWil; "wil"
0x180003392  mov     r9d, eax; char *
0x180003395  mov     edx, 137h; void *
0x18000339a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000339f  test    rdi, rdi
0x1800033a2  jz      short loc_1800033BB
0x1800033a4  mov     rcx, rdi; hMutex
0x1800033a7  call    cs:__imp_ReleaseMutex
0x1800033ae  nop     dword ptr [rax+rax+00h]
0x1800033b3  test    eax, eax
0x1800033b5  jz      loc_180003483
0x1800033bb  mov     rcx, [rsp+270h+hObject]; hObject
0x1800033c0  test    rcx, rcx
0x1800033c3  jz      short loc_1800033D9
0x1800033c5  call    cs:__imp_CloseHandle
0x1800033cc  nop     dword ptr [rax+rax+00h]
0x1800033d1  test    eax, eax
0x1800033d3  jz      loc_180003495
0x1800033d9  mov     eax, ebx
0x1800033db  jmp     short loc_180003418
0x1800033dd  mov     rbx, [rsp+270h+hObject]
0x1800033e2  test    rdi, rdi
0x1800033e5  jz      short loc_1800033FE
0x1800033e7  mov     rcx, rdi; hMutex
0x1800033ea  call    cs:__imp_ReleaseMutex
0x1800033f1  nop     dword ptr [rax+rax+00h]
0x1800033f6  test    eax, eax
0x1800033f8  jz      loc_1800034A7
0x1800033fe  test    rbx, rbx
0x180003401  jz      short loc_180003416
0x180003403  mov     rcx, rbx; hObject
0x180003406  call    cs:__imp_CloseHandle
0x18000340d  nop     dword ptr [rax+rax+00h]
0x180003412  test    eax, eax
0x180003414  jz      short loc_180003440
0x180003416  xor     eax, eax
0x180003418  mov     rcx, [rbp+170h+var_20]
0x18000341f  xor     rcx, rsp; StackCookie
0x180003422  call    __security_check_cookie
0x180003427  lea     r11, [rsp+270h+var_10]
0x18000342f  mov     rbx, [r11+30h]
0x180003433  mov     rsi, [r11+38h]
0x180003437  mov     rsp, r11
0x18000343a  pop     r14
0x18000343c  pop     rdi
0x18000343d  pop     rbp
0x18000343e  retn
0x180003440  mov     rcx, [rbp+178h]; this
0x180003447  mov     edx, 0A0Bh; void *
0x18000344c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003452  mov     rcx, [rbp+178h]; this
0x180003459  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000345f  mov     rcx, [rbp+178h]; this
0x180003466  mov     edx, 0A15h; void *
0x18000346b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003471  mov     rcx, [rbp+178h]; this
0x180003478  mov     edx, 0A0Bh; void *
0x18000347d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003483  mov     rcx, [rbp+178h]; this
0x18000348a  mov     edx, 0A15h; void *
0x18000348f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003495  mov     rcx, [rbp+178h]; this
0x18000349c  mov     edx, 0A0Bh; void *
0x1800034a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800034a7  mov     rcx, [rbp+178h]; this
0x1800034ae  mov     edx, 0A15h; void *
0x1800034b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
