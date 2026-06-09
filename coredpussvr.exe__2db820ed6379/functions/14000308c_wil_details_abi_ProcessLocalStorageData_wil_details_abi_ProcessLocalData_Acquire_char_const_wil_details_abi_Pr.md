# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000308c`
- end: `0x140003351`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140003b9c`

## callees

- `0x140001500`
- `0x14000308c`
- `0x140003374`
- `0x140003920`
- `0x140004340`
- `0x140004a34`
- `0x140005220`
- `0x1400052dc`
- `0x1400056e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003109`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003109`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003135`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003135`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400031bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000323f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003282`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400031bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000323f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400030c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400030c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400031d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000325d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000329e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400031d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000325d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000329e`

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
0x14000308c  mov     [rsp-8+arg_10], rbx
0x140003091  mov     [rsp-8+arg_18], rsi
0x140003096  push    rbp
0x140003097  push    rdi
0x140003098  push    r14
0x14000309a  lea     rbp, [rsp-160h]
0x1400030a2  sub     rsp, 260h
0x1400030a9  mov     rax, cs:__security_cookie
0x1400030b0  xor     rax, rsp
0x1400030b3  mov     [rbp+170h+var_20], rax
0x1400030ba  mov     r14, rdx
0x1400030bd  mov     qword ptr [rdx], 0
0x1400030c4  mov     rbx, rcx
0x1400030c7  call    cs:__imp_GetCurrentProcessId
0x1400030ce  nop     dword ptr [rax+rax+00h]
0x1400030d3  mov     [rsp+270h+var_248], rbx
0x1400030d8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400030df  mov     r9d, eax
0x1400030e2  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400030ea  mov     edx, 104h; unsigned __int64
0x1400030ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400030f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400030f9  mov     r9d, 1F0001h; dwDesiredAccess
0x1400030ff  lea     rdx, [rsp+270h+Name]; lpName
0x140003104  xor     r8d, r8d; dwFlags
0x140003107  xor     ecx, ecx; lpMutexAttributes
0x140003109  call    cs:__imp_CreateMutexExW
0x140003110  nop     dword ptr [rax+rax+00h]
0x140003115  mov     [rsp+270h+hObject], rax
0x14000311a  mov     rbx, rax
0x14000311d  test    rax, rax
0x140003120  jnz     short loc_14000312C
0x140003122  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003127  jmp     loc_1400032B0
0x14000312c  xor     r8d, r8d; bAlertable
0x14000312f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003132  mov     rcx, rbx; hHandle
0x140003135  call    cs:__imp_WaitForSingleObjectEx
0x14000313c  nop     dword ptr [rax+rax+00h]
0x140003141  cmp     eax, 102h
0x140003146  jz      short loc_140003158
0x140003148  test    eax, 0FFFFFF7Fh
0x14000314d  jnz     loc_1400032EA
0x140003153  mov     rdi, rbx
0x140003156  jmp     short loc_14000315A
0x140003158  xor     edi, edi
0x14000315a  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x14000315f  mov     [rsp+270h+var_238], 0
0x140003168  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000316d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003172  mov     esi, eax
0x140003174  test    eax, eax
0x140003176  jns     short loc_1400031EE
0x140003178  mov     rcx, [rbp+178h]; this
0x14000317f  mov     r9d, eax; char *
0x140003182  mov     edx, 66h ; 'f'; void *
0x140003187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000318c  mov     rcx, [rbp+178h]; this
0x140003193  mov     r9d, esi; char *
0x140003196  mov     edx, 6Fh ; 'o'; void *
0x14000319b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031a0  mov     rcx, [rbp+178h]; this
0x1400031a7  mov     r9d, esi; char *
0x1400031aa  mov     edx, 12Eh; void *
0x1400031af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400031b4  test    rdi, rdi
0x1400031b7  jz      short loc_1400031D0
0x1400031b9  mov     rcx, rdi; hMutex
0x1400031bc  call    cs:__imp_ReleaseMutex
0x1400031c3  nop     dword ptr [rax+rax+00h]
0x1400031c8  test    eax, eax
0x1400031ca  jz      loc_1400032F7
0x1400031d0  mov     rcx, rbx; hObject
0x1400031d3  call    cs:__imp_CloseHandle
0x1400031da  nop     dword ptr [rax+rax+00h]
0x1400031df  test    eax, eax
0x1400031e1  jz      loc_140003309
0x1400031e7  mov     eax, esi
0x1400031e9  jmp     loc_1400032B0
0x1400031ee  mov     rax, [rsp+270h+var_238]
0x1400031f3  lea     rcx, ds:0[rax*4]
0x1400031fb  test    rcx, rcx
0x1400031fe  jz      short loc_14000320B
0x140003200  mov     [r14], rcx
0x140003203  mov     eax, [rcx]
0x140003205  inc     eax
0x140003207  mov     [rcx], eax
0x140003209  jmp     short loc_14000327A
0x14000320b  mov     r8, r14
0x14000320e  lea     rdx, [rsp+270h+hObject]
0x140003213  lea     rcx, [rsp+270h+Name]
0x140003218  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000321d  mov     ebx, eax
0x14000321f  test    eax, eax
0x140003221  jns     short loc_140003275
0x140003223  mov     rcx, [rbp+178h]; this
0x14000322a  mov     r9d, eax; char *
0x14000322d  mov     edx, 137h; void *
0x140003232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003237  test    rdi, rdi
0x14000323a  jz      short loc_140003253
0x14000323c  mov     rcx, rdi; hMutex
0x14000323f  call    cs:__imp_ReleaseMutex
0x140003246  nop     dword ptr [rax+rax+00h]
0x14000324b  test    eax, eax
0x14000324d  jz      loc_14000331B
0x140003253  mov     rcx, [rsp+270h+hObject]; hObject
0x140003258  test    rcx, rcx
0x14000325b  jz      short loc_140003271
0x14000325d  call    cs:__imp_CloseHandle
0x140003264  nop     dword ptr [rax+rax+00h]
0x140003269  test    eax, eax
0x14000326b  jz      loc_14000332D
0x140003271  mov     eax, ebx
0x140003273  jmp     short loc_1400032B0
0x140003275  mov     rbx, [rsp+270h+hObject]
0x14000327a  test    rdi, rdi
0x14000327d  jz      short loc_140003296
0x14000327f  mov     rcx, rdi; hMutex
0x140003282  call    cs:__imp_ReleaseMutex
0x140003289  nop     dword ptr [rax+rax+00h]
0x14000328e  test    eax, eax
0x140003290  jz      loc_14000333F
0x140003296  test    rbx, rbx
0x140003299  jz      short loc_1400032AE
0x14000329b  mov     rcx, rbx; hObject
0x14000329e  call    cs:__imp_CloseHandle
0x1400032a5  nop     dword ptr [rax+rax+00h]
0x1400032aa  test    eax, eax
0x1400032ac  jz      short loc_1400032D8
0x1400032ae  xor     eax, eax
0x1400032b0  mov     rcx, [rbp+170h+var_20]
0x1400032b7  xor     rcx, rsp; StackCookie
0x1400032ba  call    __security_check_cookie
0x1400032bf  lea     r11, [rsp+270h+var_10]
0x1400032c7  mov     rbx, [r11+30h]
0x1400032cb  mov     rsi, [r11+38h]
0x1400032cf  mov     rsp, r11
0x1400032d2  pop     r14
0x1400032d4  pop     rdi
0x1400032d5  pop     rbp
0x1400032d6  retn
0x1400032d8  mov     rcx, [rbp+178h]; this
0x1400032df  mov     edx, 0A0Bh; void *
0x1400032e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400032ea  mov     rcx, [rbp+178h]; this
0x1400032f1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400032f7  mov     rcx, [rbp+178h]; this
0x1400032fe  mov     edx, 0A15h; void *
0x140003303  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003309  mov     rcx, [rbp+178h]; this
0x140003310  mov     edx, 0A0Bh; void *
0x140003315  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000331b  mov     rcx, [rbp+178h]; this
0x140003322  mov     edx, 0A15h; void *
0x140003327  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000332d  mov     rcx, [rbp+178h]; this
0x140003334  mov     edx, 0A0Bh; void *
0x140003339  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000333f  mov     rcx, [rbp+178h]; this
0x140003346  mov     edx, 0A15h; void *
0x14000334b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
