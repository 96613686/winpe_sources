# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800060c8`
- end: `0x180006490`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006f90`

## callees

- `0x180001500`
- `0x1800060c8`
- `0x180006498`
- `0x1800066e0`
- `0x180006d28`
- `0x180007828`
- `0x180007b04`
- `0x180008490`
- `0x18000857c`
- `0x18000893c`
- `0x18000894c`
- `0x18000b8b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006140`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006140`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006161`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006161`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800063a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800063a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000630c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000630c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063bb`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x1800060c8  mov     [rsp-8+arg_10], rbx
0x1800060cd  push    rbp
0x1800060ce  push    rsi
0x1800060cf  push    rdi
0x1800060d0  push    r14
0x1800060d2  push    r15
0x1800060d4  lea     rbp, [rsp-160h]
0x1800060dc  sub     rsp, 260h
0x1800060e3  mov     rax, cs:__security_cookie
0x1800060ea  xor     rax, rsp
0x1800060ed  mov     [rbp+180h+var_30], rax
0x1800060f4  mov     r15, rdx
0x1800060f7  mov     qword ptr [rdx], 0
0x1800060fe  mov     rbx, rcx
0x180006101  call    cs:__imp_GetCurrentProcessId
0x180006107  mov     r14d, 78h ; 'x'
0x18000610d  mov     [rsp+280h+var_258], rbx
0x180006112  mov     r9d, eax
0x180006115  mov     [rsp+280h+var_260], r14d; int
0x18000611a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006121  mov     edx, 104h; unsigned __int64
0x180006126  lea     rcx, [rsp+280h+Name]; Buffer
0x18000612b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006130  mov     r9d, 1F0001h; dwDesiredAccess
0x180006136  lea     rdx, [rsp+280h+Name]; lpName
0x18000613b  xor     r8d, r8d; dwFlags
0x18000613e  xor     ecx, ecx; lpMutexAttributes
0x180006140  call    cs:__imp_CreateMutexExW
0x180006146  mov     rbx, rax
0x180006149  test    rax, rax
0x18000614c  jnz     short loc_180006158
0x18000614e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006153  jmp     loc_1800063C7
0x180006158  xor     r8d, r8d; bAlertable
0x18000615b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000615e  mov     rcx, rbx; hHandle
0x180006161  call    cs:__imp_WaitForSingleObjectEx
0x180006167  cmp     eax, 102h
0x18000616c  jz      short loc_18000617E
0x18000616e  test    eax, 0FFFFFF7Fh
0x180006173  jnz     loc_1800063FF
0x180006179  mov     rdi, rbx
0x18000617c  jmp     short loc_180006180
0x18000617e  xor     edi, edi
0x180006180  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006185  mov     [rsp+280h+hObject], 0
0x18000618e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006193  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006198  mov     esi, eax
0x18000619a  test    eax, eax
0x18000619c  jns     short loc_18000621D
0x18000619e  mov     rcx, [rbp+188h]; this
0x1800061a5  lea     r8, aWil; "wil"
0x1800061ac  mov     r9d, eax; char *
0x1800061af  mov     edx, 66h ; 'f'; void *
0x1800061b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061b9  mov     rcx, [rbp+188h]; this
0x1800061c0  lea     r8, aWil; "wil"
0x1800061c7  mov     r9d, esi; char *
0x1800061ca  mov     edx, 6Fh ; 'o'; void *
0x1800061cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061d4  mov     rcx, [rbp+188h]; this
0x1800061db  lea     r8, aWil; "wil"
0x1800061e2  mov     r9d, esi; char *
0x1800061e5  mov     edx, 12Eh; void *
0x1800061ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061ef  test    rdi, rdi
0x1800061f2  jz      short loc_180006205
0x1800061f4  mov     rcx, rdi; hMutex
0x1800061f7  call    cs:__imp_ReleaseMutex
0x1800061fd  test    eax, eax
0x1800061ff  jz      loc_18000640C
0x180006205  mov     rcx, rbx; hObject
0x180006208  call    cs:__imp_CloseHandle
0x18000620e  test    eax, eax
0x180006210  jz      loc_18000641E
0x180006216  mov     eax, esi
0x180006218  jmp     loc_1800063C7
0x18000621d  mov     rax, [rsp+280h+hObject]
0x180006222  lea     rcx, ds:0[rax*4]
0x18000622a  test    rcx, rcx
0x18000622d  jz      short loc_18000623D
0x18000622f  mov     [r15], rcx
0x180006232  mov     eax, [rcx]
0x180006234  inc     eax
0x180006236  mov     [rcx], eax
0x180006238  jmp     loc_18000639D
0x18000623d  mov     rdx, r14; dwBytes
0x180006240  mov     qword ptr [r15], 0
0x180006247  mov     ecx, 8; dwFlags
0x18000624c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006251  mov     rsi, rax
0x180006254  test    rax, rax
0x180006257  jnz     short loc_18000627F
0x180006259  mov     rcx, [rbp+188h]; this
0x180006260  lea     r8, aWil; "wil"
0x180006267  mov     r14d, 8007000Eh
0x18000626d  mov     edx, 14Bh; void *
0x180006272  mov     r9d, r14d; char *
0x180006275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000627a  jmp     loc_180006312
0x18000627f  xorps   xmm0, xmm0
0x180006282  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006288  test    sil, 3
0x18000628c  jnz     loc_180006430
0x180006292  mov     r9, rsi
0x180006295  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000629a  shr     r9, 2; unsigned __int64
0x18000629e  lea     rcx, [rsp+280h+hObject]; this
0x1800062a3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800062a8  mov     r14d, eax
0x1800062ab  test    eax, eax
0x1800062ad  jns     loc_180006359
0x1800062b3  mov     rcx, [rbp+188h]; this
0x1800062ba  lea     r8, aWil; "wil"
0x1800062c1  mov     r9d, eax; char *
0x1800062c4  mov     edx, 14Eh; void *
0x1800062c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062ce  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800062d3  test    rcx, rcx
0x1800062d6  jz      short loc_1800062E6
0x1800062d8  call    cs:__imp_CloseHandle
0x1800062de  test    eax, eax
0x1800062e0  jz      loc_180006436
0x1800062e6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800062eb  test    rcx, rcx
0x1800062ee  jz      short loc_1800062FE
0x1800062f0  call    cs:__imp_CloseHandle
0x1800062f6  test    eax, eax
0x1800062f8  jz      loc_180006448
0x1800062fe  call    cs:__imp_GetProcessHeap
0x180006304  mov     r8, rsi; lpMem
0x180006307  xor     edx, edx; dwFlags
0x180006309  mov     rcx, rax; hHeap
0x18000630c  call    cs:__imp_HeapFree
0x180006312  mov     rcx, [rbp+188h]; this
0x180006319  lea     r8, aWil; "wil"
0x180006320  mov     r9d, r14d; char *
0x180006323  mov     edx, 137h; void *
0x180006328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000632d  test    rdi, rdi
0x180006330  jz      short loc_180006343
0x180006332  mov     rcx, rdi; hMutex
0x180006335  call    cs:__imp_ReleaseMutex
0x18000633b  test    eax, eax
0x18000633d  jz      loc_18000645A
0x180006343  mov     rcx, rbx; hObject
0x180006346  call    cs:__imp_CloseHandle
0x18000634c  test    eax, eax
0x18000634e  jz      loc_18000646C
0x180006354  mov     eax, r14d
0x180006357  jmp     short loc_1800063C7
0x180006359  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000635e  xor     edx, edx; Val
0x180006360  mov     dword ptr [rsi], 1
0x180006366  lea     rcx, [rsi+22h]; void *
0x18000636a  mov     [rsi+8], rbx
0x18000636e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006373  lea     r8d, [rdx+56h]; Size
0x180006377  call    memset
0x18000637c  xor     edx, edx; Val
0x18000637e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006384  lea     rcx, [rsi+28h]; void *
0x180006388  mov     dword ptr [rsi+24h], 1
0x18000638f  lea     r8d, [rdx+50h]; Size
0x180006393  call    memset
0x180006398  xor     ebx, ebx
0x18000639a  mov     [r15], rsi
0x18000639d  test    rdi, rdi
0x1800063a0  jz      short loc_1800063B3
0x1800063a2  mov     rcx, rdi; hMutex
0x1800063a5  call    cs:__imp_ReleaseMutex
0x1800063ab  test    eax, eax
0x1800063ad  jz      loc_18000647E
0x1800063b3  test    rbx, rbx
0x1800063b6  jz      short loc_1800063C5
0x1800063b8  mov     rcx, rbx; hObject
0x1800063bb  call    cs:__imp_CloseHandle
0x1800063c1  test    eax, eax
0x1800063c3  jz      short loc_1800063ED
0x1800063c5  xor     eax, eax
0x1800063c7  mov     rcx, [rbp+180h+var_30]
0x1800063ce  xor     rcx, rsp; StackCookie
0x1800063d1  call    __security_check_cookie
0x1800063d6  mov     rbx, [rsp+280h+arg_10]
0x1800063de  add     rsp, 260h
0x1800063e5  pop     r15
0x1800063e7  pop     r14
0x1800063e9  pop     rdi
0x1800063ea  pop     rsi
0x1800063eb  pop     rbp
0x1800063ec  retn
0x1800063ed  mov     rcx, [rbp+188h]; this
0x1800063f4  mov     edx, 0A0Bh; void *
0x1800063f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063ff  mov     rcx, [rbp+188h]; this
0x180006406  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000640c  mov     rcx, [rbp+188h]; this
0x180006413  mov     edx, 0A15h; void *
0x180006418  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000641e  mov     rcx, [rbp+188h]; this
0x180006425  mov     edx, 0A0Bh; void *
0x18000642a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006430  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006436  mov     rcx, [rbp+188h]; this
0x18000643d  mov     edx, 0A0Bh; void *
0x180006442  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006448  mov     rcx, [rbp+188h]; this
0x18000644f  mov     edx, 0A0Bh; void *
0x180006454  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000645a  mov     rcx, [rbp+188h]; this
0x180006461  mov     edx, 0A15h; void *
0x180006466  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000646c  mov     rcx, [rbp+188h]; this
0x180006473  mov     edx, 0A0Bh; void *
0x180006478  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000647e  mov     rcx, [rbp+188h]; this
0x180006485  mov     edx, 0A15h; void *
0x18000648a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
