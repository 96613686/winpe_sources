# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008fc8`
- end: `0x180009366`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180009d28`

## callees

- `0x180008fc8`
- `0x18000936c`
- `0x180009580`
- `0x180009bf0`
- `0x18000a4fc`
- `0x18000ab30`
- `0x18000ae28`
- `0x18000aeb4`
- `0x18000b204`
- `0x18000b214`
- `0x18000c392`
- `0x18000c3c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800090e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000920b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000927b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800090e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000920b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000927b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009040`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009040`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009061`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000921c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000921c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009291`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009001`

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
  __int64 v25; // r8
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
0x180008fc8  mov     [rsp-8+arg_10], rbx
0x180008fcd  push    rbp
0x180008fce  push    rsi
0x180008fcf  push    rdi
0x180008fd0  push    r14
0x180008fd2  push    r15
0x180008fd4  lea     rbp, [rsp-160h]
0x180008fdc  sub     rsp, 260h
0x180008fe3  mov     rax, cs:__security_cookie
0x180008fea  xor     rax, rsp
0x180008fed  mov     [rbp+180h+var_30], rax
0x180008ff4  mov     r15, rdx
0x180008ff7  mov     qword ptr [rdx], 0
0x180008ffe  mov     rbx, rcx
0x180009001  call    cs:__imp_GetCurrentProcessId
0x180009007  mov     r14d, 78h ; 'x'
0x18000900d  mov     [rsp+280h+var_258], rbx
0x180009012  mov     r9d, eax
0x180009015  mov     [rsp+280h+var_260], r14d; int
0x18000901a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009021  mov     edx, 104h; unsigned __int64
0x180009026  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000902b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009030  mov     r9d, 1F0001h; dwDesiredAccess
0x180009036  lea     rdx, [rsp+280h+Name]; lpName
0x18000903b  xor     r8d, r8d; dwFlags
0x18000903e  xor     ecx, ecx; lpMutexAttributes
0x180009040  call    cs:__imp_CreateMutexExW
0x180009046  mov     rbx, rax
0x180009049  test    rax, rax
0x18000904c  jnz     short loc_180009058
0x18000904e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009053  jmp     loc_18000929D
0x180009058  xor     r8d, r8d; bAlertable
0x18000905b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000905e  mov     rcx, rbx; hHandle
0x180009061  call    cs:__imp_WaitForSingleObjectEx
0x180009067  cmp     eax, 102h
0x18000906c  jz      short loc_18000907E
0x18000906e  test    eax, 0FFFFFF7Fh
0x180009073  jnz     loc_1800092D5
0x180009079  mov     rdi, rbx
0x18000907c  jmp     short loc_180009080
0x18000907e  xor     edi, edi
0x180009080  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009085  mov     [rsp+280h+hObject], 0
0x18000908e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009093  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009098  mov     esi, eax
0x18000909a  test    eax, eax
0x18000909c  jns     short loc_180009108
0x18000909e  mov     rcx, [rbp+188h]; this
0x1800090a5  mov     r9d, eax; char *
0x1800090a8  mov     edx, 66h ; 'f'; void *
0x1800090ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090b2  mov     rcx, [rbp+188h]; this
0x1800090b9  mov     r9d, esi; char *
0x1800090bc  mov     edx, 6Fh ; 'o'; void *
0x1800090c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090c6  mov     rcx, [rbp+188h]; this
0x1800090cd  mov     r9d, esi; char *
0x1800090d0  mov     edx, 12Eh; void *
0x1800090d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090da  test    rdi, rdi
0x1800090dd  jz      short loc_1800090F0
0x1800090df  mov     rcx, rdi; hMutex
0x1800090e2  call    cs:__imp_ReleaseMutex
0x1800090e8  test    eax, eax
0x1800090ea  jz      loc_1800092E2
0x1800090f0  mov     rcx, rbx; hObject
0x1800090f3  call    cs:__imp_CloseHandle
0x1800090f9  test    eax, eax
0x1800090fb  jz      loc_1800092F4
0x180009101  mov     eax, esi
0x180009103  jmp     loc_18000929D
0x180009108  mov     rax, [rsp+280h+hObject]
0x18000910d  lea     rcx, ds:0[rax*4]
0x180009115  test    rcx, rcx
0x180009118  jz      short loc_180009128
0x18000911a  mov     [r15], rcx
0x18000911d  mov     eax, [rcx]
0x18000911f  inc     eax
0x180009121  mov     [rcx], eax
0x180009123  jmp     loc_180009273
0x180009128  mov     rdx, r14; dwBytes
0x18000912b  mov     qword ptr [r15], 0
0x180009132  mov     ecx, 8; dwFlags
0x180009137  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000913c  mov     rsi, rax
0x18000913f  test    rax, rax
0x180009142  jnz     short loc_180009163
0x180009144  mov     rcx, [rbp+188h]; this
0x18000914b  mov     r14d, 8007000Eh
0x180009151  mov     r9d, r14d; char *
0x180009154  mov     edx, 14Bh; void *
0x180009159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000915e  jmp     loc_1800091EF
0x180009163  xorps   xmm0, xmm0
0x180009166  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000916c  test    sil, 3
0x180009170  jnz     loc_180009306
0x180009176  mov     r9, rsi
0x180009179  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000917e  shr     r9, 2; unsigned __int64
0x180009182  lea     rcx, [rsp+280h+hObject]; this
0x180009187  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000918c  mov     r14d, eax
0x18000918f  test    eax, eax
0x180009191  jns     loc_18000922F
0x180009197  mov     rcx, [rbp+188h]; this
0x18000919e  mov     r9d, eax; char *
0x1800091a1  mov     edx, 14Eh; void *
0x1800091a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091ab  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800091b0  test    rcx, rcx
0x1800091b3  jz      short loc_1800091C3
0x1800091b5  call    cs:__imp_CloseHandle
0x1800091bb  test    eax, eax
0x1800091bd  jz      loc_18000930C
0x1800091c3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800091c8  test    rcx, rcx
0x1800091cb  jz      short loc_1800091DB
0x1800091cd  call    cs:__imp_CloseHandle
0x1800091d3  test    eax, eax
0x1800091d5  jz      loc_18000931E
0x1800091db  call    cs:__imp_GetProcessHeap
0x1800091e1  mov     r8, rsi; lpMem
0x1800091e4  xor     edx, edx; dwFlags
0x1800091e6  mov     rcx, rax; hHeap
0x1800091e9  call    cs:__imp_HeapFree
0x1800091ef  mov     rcx, [rbp+188h]; this
0x1800091f6  mov     r9d, r14d; char *
0x1800091f9  mov     edx, 137h; void *
0x1800091fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009203  test    rdi, rdi
0x180009206  jz      short loc_180009219
0x180009208  mov     rcx, rdi; hMutex
0x18000920b  call    cs:__imp_ReleaseMutex
0x180009211  test    eax, eax
0x180009213  jz      loc_180009330
0x180009219  mov     rcx, rbx; hObject
0x18000921c  call    cs:__imp_CloseHandle
0x180009222  test    eax, eax
0x180009224  jz      loc_180009342
0x18000922a  mov     eax, r14d
0x18000922d  jmp     short loc_18000929D
0x18000922f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180009234  xor     edx, edx; Val
0x180009236  mov     dword ptr [rsi], 1
0x18000923c  lea     rcx, [rsi+22h]; void *
0x180009240  mov     [rsi+8], rbx
0x180009244  movdqu  xmmword ptr [rsi+10h], xmm0
0x180009249  lea     r8d, [rdx+56h]; Size
0x18000924d  call    memset_0
0x180009252  xor     edx, edx; Val
0x180009254  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000925a  lea     rcx, [rsi+28h]; void *
0x18000925e  mov     dword ptr [rsi+24h], 1
0x180009265  lea     r8d, [rdx+50h]; Size
0x180009269  call    memset_0
0x18000926e  xor     ebx, ebx
0x180009270  mov     [r15], rsi
0x180009273  test    rdi, rdi
0x180009276  jz      short loc_180009289
0x180009278  mov     rcx, rdi; hMutex
0x18000927b  call    cs:__imp_ReleaseMutex
0x180009281  test    eax, eax
0x180009283  jz      loc_180009354
0x180009289  test    rbx, rbx
0x18000928c  jz      short loc_18000929B
0x18000928e  mov     rcx, rbx; hObject
0x180009291  call    cs:__imp_CloseHandle
0x180009297  test    eax, eax
0x180009299  jz      short loc_1800092C3
0x18000929b  xor     eax, eax
0x18000929d  mov     rcx, [rbp+180h+var_30]
0x1800092a4  xor     rcx, rsp; StackCookie
0x1800092a7  call    __security_check_cookie
0x1800092ac  mov     rbx, [rsp+280h+arg_10]
0x1800092b4  add     rsp, 260h
0x1800092bb  pop     r15
0x1800092bd  pop     r14
0x1800092bf  pop     rdi
0x1800092c0  pop     rsi
0x1800092c1  pop     rbp
0x1800092c2  retn
0x1800092c3  mov     rcx, [rbp+188h]; this
0x1800092ca  mov     edx, 0A0Bh; void *
0x1800092cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092d5  mov     rcx, [rbp+188h]; this
0x1800092dc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800092e2  mov     rcx, [rbp+188h]; this
0x1800092e9  mov     edx, 0A15h; void *
0x1800092ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092f4  mov     rcx, [rbp+188h]; this
0x1800092fb  mov     edx, 0A0Bh; void *
0x180009300  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009306  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000930c  mov     rcx, [rbp+188h]; this
0x180009313  mov     edx, 0A0Bh; void *
0x180009318  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000931e  mov     rcx, [rbp+188h]; this
0x180009325  mov     edx, 0A0Bh; void *
0x18000932a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009330  mov     rcx, [rbp+188h]; this
0x180009337  mov     edx, 0A15h; void *
0x18000933c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009342  mov     rcx, [rbp+188h]; this
0x180009349  mov     edx, 0A0Bh; void *
0x18000934e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009354  mov     rcx, [rbp+188h]; this
0x18000935b  mov     edx, 0A15h; void *
0x180009360  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
