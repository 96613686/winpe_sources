# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140005738`
- end: `0x140005b00`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400076f4`

## callees

- `0x140002600`
- `0x140003168`
- `0x140005738`
- `0x140006434`
- `0x140006ac0`
- `0x1400073e8`
- `0x1400083f8`
- `0x140009724`
- `0x14000a30c`
- `0x14000a6cc`
- `0x14000af58`
- `0x14000af68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400057d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400057d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005867`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400059a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005a15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005867`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400059a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005a15`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400057b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400057b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000596e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000596e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000597c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000597c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400059b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005a2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400059b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005a2b`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
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
0x140005738  mov     [rsp-8+arg_10], rbx
0x14000573d  push    rbp
0x14000573e  push    rsi
0x14000573f  push    rdi
0x140005740  push    r14
0x140005742  push    r15
0x140005744  lea     rbp, [rsp-160h]
0x14000574c  sub     rsp, 260h
0x140005753  mov     rax, cs:__security_cookie
0x14000575a  xor     rax, rsp
0x14000575d  mov     [rbp+180h+var_30], rax
0x140005764  mov     r15, rdx
0x140005767  mov     qword ptr [rdx], 0
0x14000576e  mov     rbx, rcx
0x140005771  call    cs:__imp_GetCurrentProcessId
0x140005777  mov     r14d, 78h ; 'x'
0x14000577d  mov     [rsp+280h+var_258], rbx
0x140005782  mov     r9d, eax
0x140005785  mov     [rsp+280h+var_260], r14d; int
0x14000578a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005791  mov     edx, 104h; unsigned __int64
0x140005796  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000579b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400057a0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400057a6  lea     rdx, [rsp+280h+Name]; lpName
0x1400057ab  xor     r8d, r8d; dwFlags
0x1400057ae  xor     ecx, ecx; lpMutexAttributes
0x1400057b0  call    cs:__imp_CreateMutexExW
0x1400057b6  mov     rbx, rax
0x1400057b9  test    rax, rax
0x1400057bc  jnz     short loc_1400057C8
0x1400057be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400057c3  jmp     loc_140005A37
0x1400057c8  xor     r8d, r8d; bAlertable
0x1400057cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400057ce  mov     rcx, rbx; hHandle
0x1400057d1  call    cs:__imp_WaitForSingleObjectEx
0x1400057d7  cmp     eax, 102h
0x1400057dc  jz      short loc_1400057EE
0x1400057de  test    eax, 0FFFFFF7Fh
0x1400057e3  jnz     loc_140005A6F
0x1400057e9  mov     rdi, rbx
0x1400057ec  jmp     short loc_1400057F0
0x1400057ee  xor     edi, edi
0x1400057f0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400057f5  mov     [rsp+280h+hObject], 0
0x1400057fe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005803  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140005808  mov     esi, eax
0x14000580a  test    eax, eax
0x14000580c  jns     short loc_14000588D
0x14000580e  mov     rcx, [rbp+188h]; this
0x140005815  lea     r8, aWil; "wil"
0x14000581c  mov     r9d, eax; char *
0x14000581f  mov     edx, 66h ; 'f'; void *
0x140005824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005829  mov     rcx, [rbp+188h]; this
0x140005830  lea     r8, aWil; "wil"
0x140005837  mov     r9d, esi; char *
0x14000583a  mov     edx, 6Fh ; 'o'; void *
0x14000583f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005844  mov     rcx, [rbp+188h]; this
0x14000584b  lea     r8, aWil; "wil"
0x140005852  mov     r9d, esi; char *
0x140005855  mov     edx, 12Eh; void *
0x14000585a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000585f  test    rdi, rdi
0x140005862  jz      short loc_140005875
0x140005864  mov     rcx, rdi; hMutex
0x140005867  call    cs:__imp_ReleaseMutex
0x14000586d  test    eax, eax
0x14000586f  jz      loc_140005A7C
0x140005875  mov     rcx, rbx; hObject
0x140005878  call    cs:__imp_CloseHandle
0x14000587e  test    eax, eax
0x140005880  jz      loc_140005A8E
0x140005886  mov     eax, esi
0x140005888  jmp     loc_140005A37
0x14000588d  mov     rax, [rsp+280h+hObject]
0x140005892  lea     rcx, ds:0[rax*4]
0x14000589a  test    rcx, rcx
0x14000589d  jz      short loc_1400058AD
0x14000589f  mov     [r15], rcx
0x1400058a2  mov     eax, [rcx]
0x1400058a4  inc     eax
0x1400058a6  mov     [rcx], eax
0x1400058a8  jmp     loc_140005A0D
0x1400058ad  mov     rdx, r14; dwBytes
0x1400058b0  mov     qword ptr [r15], 0
0x1400058b7  mov     ecx, 8; dwFlags
0x1400058bc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400058c1  mov     rsi, rax
0x1400058c4  test    rax, rax
0x1400058c7  jnz     short loc_1400058EF
0x1400058c9  mov     rcx, [rbp+188h]; this
0x1400058d0  lea     r8, aWil; "wil"
0x1400058d7  mov     r14d, 8007000Eh
0x1400058dd  mov     edx, 14Bh; void *
0x1400058e2  mov     r9d, r14d; char *
0x1400058e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058ea  jmp     loc_140005982
0x1400058ef  xorps   xmm0, xmm0
0x1400058f2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400058f8  test    sil, 3
0x1400058fc  jnz     loc_140005AA0
0x140005902  mov     r9, rsi
0x140005905  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000590a  shr     r9, 2; unsigned __int64
0x14000590e  lea     rcx, [rsp+280h+hObject]; this
0x140005913  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140005918  mov     r14d, eax
0x14000591b  test    eax, eax
0x14000591d  jns     loc_1400059C9
0x140005923  mov     rcx, [rbp+188h]; this
0x14000592a  lea     r8, aWil; "wil"
0x140005931  mov     r9d, eax; char *
0x140005934  mov     edx, 14Eh; void *
0x140005939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000593e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140005943  test    rcx, rcx
0x140005946  jz      short loc_140005956
0x140005948  call    cs:__imp_CloseHandle
0x14000594e  test    eax, eax
0x140005950  jz      loc_140005AA6
0x140005956  mov     rcx, [rsp+280h+hObject]; hObject
0x14000595b  test    rcx, rcx
0x14000595e  jz      short loc_14000596E
0x140005960  call    cs:__imp_CloseHandle
0x140005966  test    eax, eax
0x140005968  jz      loc_140005AB8
0x14000596e  call    cs:__imp_GetProcessHeap
0x140005974  mov     r8, rsi; lpMem
0x140005977  xor     edx, edx; dwFlags
0x140005979  mov     rcx, rax; hHeap
0x14000597c  call    cs:__imp_HeapFree
0x140005982  mov     rcx, [rbp+188h]; this
0x140005989  lea     r8, aWil; "wil"
0x140005990  mov     r9d, r14d; char *
0x140005993  mov     edx, 137h; void *
0x140005998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000599d  test    rdi, rdi
0x1400059a0  jz      short loc_1400059B3
0x1400059a2  mov     rcx, rdi; hMutex
0x1400059a5  call    cs:__imp_ReleaseMutex
0x1400059ab  test    eax, eax
0x1400059ad  jz      loc_140005ACA
0x1400059b3  mov     rcx, rbx; hObject
0x1400059b6  call    cs:__imp_CloseHandle
0x1400059bc  test    eax, eax
0x1400059be  jz      loc_140005ADC
0x1400059c4  mov     eax, r14d
0x1400059c7  jmp     short loc_140005A37
0x1400059c9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400059ce  xor     edx, edx; Val
0x1400059d0  mov     dword ptr [rsi], 1
0x1400059d6  lea     rcx, [rsi+22h]; void *
0x1400059da  mov     [rsi+8], rbx
0x1400059de  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400059e3  lea     r8d, [rdx+56h]; Size
0x1400059e7  call    memset_0
0x1400059ec  xor     edx, edx; Val
0x1400059ee  mov     word ptr [rsi+20h], 58h ; 'X'
0x1400059f4  lea     rcx, [rsi+28h]; void *
0x1400059f8  mov     dword ptr [rsi+24h], 1
0x1400059ff  lea     r8d, [rdx+50h]; Size
0x140005a03  call    memset_0
0x140005a08  xor     ebx, ebx
0x140005a0a  mov     [r15], rsi
0x140005a0d  test    rdi, rdi
0x140005a10  jz      short loc_140005A23
0x140005a12  mov     rcx, rdi; hMutex
0x140005a15  call    cs:__imp_ReleaseMutex
0x140005a1b  test    eax, eax
0x140005a1d  jz      loc_140005AEE
0x140005a23  test    rbx, rbx
0x140005a26  jz      short loc_140005A35
0x140005a28  mov     rcx, rbx; hObject
0x140005a2b  call    cs:__imp_CloseHandle
0x140005a31  test    eax, eax
0x140005a33  jz      short loc_140005A5D
0x140005a35  xor     eax, eax
0x140005a37  mov     rcx, [rbp+180h+var_30]
0x140005a3e  xor     rcx, rsp; StackCookie
0x140005a41  call    __security_check_cookie
0x140005a46  mov     rbx, [rsp+280h+arg_10]
0x140005a4e  add     rsp, 260h
0x140005a55  pop     r15
0x140005a57  pop     r14
0x140005a59  pop     rdi
0x140005a5a  pop     rsi
0x140005a5b  pop     rbp
0x140005a5c  retn
0x140005a5d  mov     rcx, [rbp+188h]; this
0x140005a64  mov     edx, 0A0Bh; void *
0x140005a69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a6f  mov     rcx, [rbp+188h]; this
0x140005a76  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140005a7c  mov     rcx, [rbp+188h]; this
0x140005a83  mov     edx, 0A15h; void *
0x140005a88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005a8e  mov     rcx, [rbp+188h]; this
0x140005a95  mov     edx, 0A0Bh; void *
0x140005a9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005aa0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005aa6  mov     rcx, [rbp+188h]; this
0x140005aad  mov     edx, 0A0Bh; void *
0x140005ab2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005ab8  mov     rcx, [rbp+188h]; this
0x140005abf  mov     edx, 0A0Bh; void *
0x140005ac4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005aca  mov     rcx, [rbp+188h]; this
0x140005ad1  mov     edx, 0A15h; void *
0x140005ad6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005adc  mov     rcx, [rbp+188h]; this
0x140005ae3  mov     edx, 0A0Bh; void *
0x140005ae8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005aee  mov     rcx, [rbp+188h]; this
0x140005af5  mov     edx, 0A15h; void *
0x140005afa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
