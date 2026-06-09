# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004b38`
- end: `0x180004f00`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005b64`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x180004b38`
- `0x180004f08`
- `0x1800051f4`
- `0x180005858`
- `0x1800063d8`
- `0x1800067c4`
- `0x180007228`
- `0x18000730c`
- `0x180007798`
- `0x1800077a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004bb0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004bb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004bd1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004bd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004b71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e2b`

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
0x180004b38  mov     [rsp-8+arg_10], rbx
0x180004b3d  push    rbp
0x180004b3e  push    rsi
0x180004b3f  push    rdi
0x180004b40  push    r14
0x180004b42  push    r15
0x180004b44  lea     rbp, [rsp-160h]
0x180004b4c  sub     rsp, 260h
0x180004b53  mov     rax, cs:__security_cookie
0x180004b5a  xor     rax, rsp
0x180004b5d  mov     [rbp+180h+var_30], rax
0x180004b64  mov     r15, rdx
0x180004b67  mov     qword ptr [rdx], 0
0x180004b6e  mov     rbx, rcx
0x180004b71  call    cs:__imp_GetCurrentProcessId
0x180004b77  mov     r14d, 78h ; 'x'
0x180004b7d  mov     [rsp+280h+var_258], rbx
0x180004b82  mov     r9d, eax
0x180004b85  mov     [rsp+280h+var_260], r14d; int
0x180004b8a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004b91  mov     edx, 104h; unsigned __int64
0x180004b96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004b9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ba0  mov     r9d, 1F0001h; dwDesiredAccess
0x180004ba6  lea     rdx, [rsp+280h+Name]; lpName
0x180004bab  xor     r8d, r8d; dwFlags
0x180004bae  xor     ecx, ecx; lpMutexAttributes
0x180004bb0  call    cs:__imp_CreateMutexExW
0x180004bb6  mov     rbx, rax
0x180004bb9  test    rax, rax
0x180004bbc  jnz     short loc_180004BC8
0x180004bbe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004bc3  jmp     loc_180004E37
0x180004bc8  xor     r8d, r8d; bAlertable
0x180004bcb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004bce  mov     rcx, rbx; hHandle
0x180004bd1  call    cs:__imp_WaitForSingleObjectEx
0x180004bd7  cmp     eax, 102h
0x180004bdc  jz      short loc_180004BEE
0x180004bde  test    eax, 0FFFFFF7Fh
0x180004be3  jnz     loc_180004E6F
0x180004be9  mov     rdi, rbx
0x180004bec  jmp     short loc_180004BF0
0x180004bee  xor     edi, edi
0x180004bf0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004bf5  mov     [rsp+280h+hObject], 0
0x180004bfe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004c03  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004c08  mov     esi, eax
0x180004c0a  test    eax, eax
0x180004c0c  jns     short loc_180004C8D
0x180004c0e  mov     rcx, [rbp+188h]; this
0x180004c15  lea     r8, aWil; "wil"
0x180004c1c  mov     r9d, eax; char *
0x180004c1f  mov     edx, 66h ; 'f'; void *
0x180004c24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c29  mov     rcx, [rbp+188h]; this
0x180004c30  lea     r8, aWil; "wil"
0x180004c37  mov     r9d, esi; char *
0x180004c3a  mov     edx, 6Fh ; 'o'; void *
0x180004c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c44  mov     rcx, [rbp+188h]; this
0x180004c4b  lea     r8, aWil; "wil"
0x180004c52  mov     r9d, esi; char *
0x180004c55  mov     edx, 12Eh; void *
0x180004c5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c5f  test    rdi, rdi
0x180004c62  jz      short loc_180004C75
0x180004c64  mov     rcx, rdi; hMutex
0x180004c67  call    cs:__imp_ReleaseMutex
0x180004c6d  test    eax, eax
0x180004c6f  jz      loc_180004E7C
0x180004c75  mov     rcx, rbx; hObject
0x180004c78  call    cs:__imp_CloseHandle
0x180004c7e  test    eax, eax
0x180004c80  jz      loc_180004E8E
0x180004c86  mov     eax, esi
0x180004c88  jmp     loc_180004E37
0x180004c8d  mov     rax, [rsp+280h+hObject]
0x180004c92  lea     rcx, ds:0[rax*4]
0x180004c9a  test    rcx, rcx
0x180004c9d  jz      short loc_180004CAD
0x180004c9f  mov     [r15], rcx
0x180004ca2  mov     eax, [rcx]
0x180004ca4  inc     eax
0x180004ca6  mov     [rcx], eax
0x180004ca8  jmp     loc_180004E0D
0x180004cad  mov     rdx, r14; dwBytes
0x180004cb0  mov     qword ptr [r15], 0
0x180004cb7  mov     ecx, 8; dwFlags
0x180004cbc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004cc1  mov     rsi, rax
0x180004cc4  test    rax, rax
0x180004cc7  jnz     short loc_180004CEF
0x180004cc9  mov     rcx, [rbp+188h]; this
0x180004cd0  lea     r8, aWil; "wil"
0x180004cd7  mov     r14d, 8007000Eh
0x180004cdd  mov     edx, 14Bh; void *
0x180004ce2  mov     r9d, r14d; char *
0x180004ce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cea  jmp     loc_180004D82
0x180004cef  xorps   xmm0, xmm0
0x180004cf2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004cf8  test    sil, 3
0x180004cfc  jnz     loc_180004EA0
0x180004d02  mov     r9, rsi
0x180004d05  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004d0a  shr     r9, 2; unsigned __int64
0x180004d0e  lea     rcx, [rsp+280h+hObject]; this
0x180004d13  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004d18  mov     r14d, eax
0x180004d1b  test    eax, eax
0x180004d1d  jns     loc_180004DC9
0x180004d23  mov     rcx, [rbp+188h]; this
0x180004d2a  lea     r8, aWil; "wil"
0x180004d31  mov     r9d, eax; char *
0x180004d34  mov     edx, 14Eh; void *
0x180004d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d3e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004d43  test    rcx, rcx
0x180004d46  jz      short loc_180004D56
0x180004d48  call    cs:__imp_CloseHandle
0x180004d4e  test    eax, eax
0x180004d50  jz      loc_180004EA6
0x180004d56  mov     rcx, [rsp+280h+hObject]; hObject
0x180004d5b  test    rcx, rcx
0x180004d5e  jz      short loc_180004D6E
0x180004d60  call    cs:__imp_CloseHandle
0x180004d66  test    eax, eax
0x180004d68  jz      loc_180004EB8
0x180004d6e  call    cs:__imp_GetProcessHeap
0x180004d74  mov     r8, rsi; lpMem
0x180004d77  xor     edx, edx; dwFlags
0x180004d79  mov     rcx, rax; hHeap
0x180004d7c  call    cs:__imp_HeapFree
0x180004d82  mov     rcx, [rbp+188h]; this
0x180004d89  lea     r8, aWil; "wil"
0x180004d90  mov     r9d, r14d; char *
0x180004d93  mov     edx, 137h; void *
0x180004d98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d9d  test    rdi, rdi
0x180004da0  jz      short loc_180004DB3
0x180004da2  mov     rcx, rdi; hMutex
0x180004da5  call    cs:__imp_ReleaseMutex
0x180004dab  test    eax, eax
0x180004dad  jz      loc_180004ECA
0x180004db3  mov     rcx, rbx; hObject
0x180004db6  call    cs:__imp_CloseHandle
0x180004dbc  test    eax, eax
0x180004dbe  jz      loc_180004EDC
0x180004dc4  mov     eax, r14d
0x180004dc7  jmp     short loc_180004E37
0x180004dc9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004dce  xor     edx, edx; Val
0x180004dd0  mov     dword ptr [rsi], 1
0x180004dd6  lea     rcx, [rsi+22h]; void *
0x180004dda  mov     [rsi+8], rbx
0x180004dde  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004de3  lea     r8d, [rdx+56h]; Size
0x180004de7  call    memset_0
0x180004dec  xor     edx, edx; Val
0x180004dee  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004df4  lea     rcx, [rsi+28h]; void *
0x180004df8  mov     dword ptr [rsi+24h], 1
0x180004dff  lea     r8d, [rdx+50h]; Size
0x180004e03  call    memset_0
0x180004e08  xor     ebx, ebx
0x180004e0a  mov     [r15], rsi
0x180004e0d  test    rdi, rdi
0x180004e10  jz      short loc_180004E23
0x180004e12  mov     rcx, rdi; hMutex
0x180004e15  call    cs:__imp_ReleaseMutex
0x180004e1b  test    eax, eax
0x180004e1d  jz      loc_180004EEE
0x180004e23  test    rbx, rbx
0x180004e26  jz      short loc_180004E35
0x180004e28  mov     rcx, rbx; hObject
0x180004e2b  call    cs:__imp_CloseHandle
0x180004e31  test    eax, eax
0x180004e33  jz      short loc_180004E5D
0x180004e35  xor     eax, eax
0x180004e37  mov     rcx, [rbp+180h+var_30]
0x180004e3e  xor     rcx, rsp; StackCookie
0x180004e41  call    __security_check_cookie
0x180004e46  mov     rbx, [rsp+280h+arg_10]
0x180004e4e  add     rsp, 260h
0x180004e55  pop     r15
0x180004e57  pop     r14
0x180004e59  pop     rdi
0x180004e5a  pop     rsi
0x180004e5b  pop     rbp
0x180004e5c  retn
0x180004e5d  mov     rcx, [rbp+188h]; this
0x180004e64  mov     edx, 0A0Bh; void *
0x180004e69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004e6f  mov     rcx, [rbp+188h]; this
0x180004e76  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004e7c  mov     rcx, [rbp+188h]; this
0x180004e83  mov     edx, 0A15h; void *
0x180004e88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004e8e  mov     rcx, [rbp+188h]; this
0x180004e95  mov     edx, 0A0Bh; void *
0x180004e9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ea0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004ea6  mov     rcx, [rbp+188h]; this
0x180004ead  mov     edx, 0A0Bh; void *
0x180004eb2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004eb8  mov     rcx, [rbp+188h]; this
0x180004ebf  mov     edx, 0A0Bh; void *
0x180004ec4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004eca  mov     rcx, [rbp+188h]; this
0x180004ed1  mov     edx, 0A15h; void *
0x180004ed6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004edc  mov     rcx, [rbp+188h]; this
0x180004ee3  mov     edx, 0A0Bh; void *
0x180004ee8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004eee  mov     rcx, [rbp+188h]; this
0x180004ef5  mov     edx, 0A15h; void *
0x180004efa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
