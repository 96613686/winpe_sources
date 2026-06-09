# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180002e48`
- end: `0x180003210`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003d10`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180002e48`
- `0x180003218`
- `0x180003460`
- `0x180003aa8`
- `0x180004588`
- `0x1800049f4`
- `0x180005380`
- `0x18000545c`
- `0x18000581c`
- `0x18000582c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002ee1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002ee1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002ec0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002ec0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002f77`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800030b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003125`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002f77`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800030b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003125`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000308c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000308c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000307e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000307e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003070`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000313b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003070`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000313b`

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
0x180002e48  mov     [rsp-8+arg_10], rbx
0x180002e4d  push    rbp
0x180002e4e  push    rsi
0x180002e4f  push    rdi
0x180002e50  push    r14
0x180002e52  push    r15
0x180002e54  lea     rbp, [rsp-160h]
0x180002e5c  sub     rsp, 260h
0x180002e63  mov     rax, cs:__security_cookie
0x180002e6a  xor     rax, rsp
0x180002e6d  mov     [rbp+180h+var_30], rax
0x180002e74  mov     r15, rdx
0x180002e77  mov     qword ptr [rdx], 0
0x180002e7e  mov     rbx, rcx
0x180002e81  call    cs:__imp_GetCurrentProcessId
0x180002e87  mov     r14d, 78h ; 'x'
0x180002e8d  mov     [rsp+280h+var_258], rbx
0x180002e92  mov     r9d, eax
0x180002e95  mov     [rsp+280h+var_260], r14d; int
0x180002e9a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180002ea1  mov     edx, 104h; unsigned __int64
0x180002ea6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180002eab  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180002eb0  mov     r9d, 1F0001h; dwDesiredAccess
0x180002eb6  lea     rdx, [rsp+280h+Name]; lpName
0x180002ebb  xor     r8d, r8d; dwFlags
0x180002ebe  xor     ecx, ecx; lpMutexAttributes
0x180002ec0  call    cs:__imp_CreateMutexExW
0x180002ec6  mov     rbx, rax
0x180002ec9  test    rax, rax
0x180002ecc  jnz     short loc_180002ED8
0x180002ece  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002ed3  jmp     loc_180003147
0x180002ed8  xor     r8d, r8d; bAlertable
0x180002edb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002ede  mov     rcx, rbx; hHandle
0x180002ee1  call    cs:__imp_WaitForSingleObjectEx
0x180002ee7  cmp     eax, 102h
0x180002eec  jz      short loc_180002EFE
0x180002eee  test    eax, 0FFFFFF7Fh
0x180002ef3  jnz     loc_18000317F
0x180002ef9  mov     rdi, rbx
0x180002efc  jmp     short loc_180002F00
0x180002efe  xor     edi, edi
0x180002f00  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180002f05  mov     [rsp+280h+hObject], 0
0x180002f0e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180002f13  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180002f18  mov     esi, eax
0x180002f1a  test    eax, eax
0x180002f1c  jns     short loc_180002F9D
0x180002f1e  mov     rcx, [rbp+188h]; this
0x180002f25  lea     r8, aWil; "wil"
0x180002f2c  mov     r9d, eax; char *
0x180002f2f  mov     edx, 66h ; 'f'; void *
0x180002f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f39  mov     rcx, [rbp+188h]; this
0x180002f40  lea     r8, aWil; "wil"
0x180002f47  mov     r9d, esi; char *
0x180002f4a  mov     edx, 6Fh ; 'o'; void *
0x180002f4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f54  mov     rcx, [rbp+188h]; this
0x180002f5b  lea     r8, aWil; "wil"
0x180002f62  mov     r9d, esi; char *
0x180002f65  mov     edx, 12Eh; void *
0x180002f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f6f  test    rdi, rdi
0x180002f72  jz      short loc_180002F85
0x180002f74  mov     rcx, rdi; hMutex
0x180002f77  call    cs:__imp_ReleaseMutex
0x180002f7d  test    eax, eax
0x180002f7f  jz      loc_18000318C
0x180002f85  mov     rcx, rbx; hObject
0x180002f88  call    cs:__imp_CloseHandle
0x180002f8e  test    eax, eax
0x180002f90  jz      loc_18000319E
0x180002f96  mov     eax, esi
0x180002f98  jmp     loc_180003147
0x180002f9d  mov     rax, [rsp+280h+hObject]
0x180002fa2  lea     rcx, ds:0[rax*4]
0x180002faa  test    rcx, rcx
0x180002fad  jz      short loc_180002FBD
0x180002faf  mov     [r15], rcx
0x180002fb2  mov     eax, [rcx]
0x180002fb4  inc     eax
0x180002fb6  mov     [rcx], eax
0x180002fb8  jmp     loc_18000311D
0x180002fbd  mov     rdx, r14; dwBytes
0x180002fc0  mov     qword ptr [r15], 0
0x180002fc7  mov     ecx, 8; dwFlags
0x180002fcc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180002fd1  mov     rsi, rax
0x180002fd4  test    rax, rax
0x180002fd7  jnz     short loc_180002FFF
0x180002fd9  mov     rcx, [rbp+188h]; this
0x180002fe0  lea     r8, aWil; "wil"
0x180002fe7  mov     r14d, 8007000Eh
0x180002fed  mov     edx, 14Bh; void *
0x180002ff2  mov     r9d, r14d; char *
0x180002ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ffa  jmp     loc_180003092
0x180002fff  xorps   xmm0, xmm0
0x180003002  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003008  test    sil, 3
0x18000300c  jnz     loc_1800031B0
0x180003012  mov     r9, rsi
0x180003015  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000301a  shr     r9, 2; unsigned __int64
0x18000301e  lea     rcx, [rsp+280h+hObject]; this
0x180003023  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180003028  mov     r14d, eax
0x18000302b  test    eax, eax
0x18000302d  jns     loc_1800030D9
0x180003033  mov     rcx, [rbp+188h]; this
0x18000303a  lea     r8, aWil; "wil"
0x180003041  mov     r9d, eax; char *
0x180003044  mov     edx, 14Eh; void *
0x180003049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000304e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003053  test    rcx, rcx
0x180003056  jz      short loc_180003066
0x180003058  call    cs:__imp_CloseHandle
0x18000305e  test    eax, eax
0x180003060  jz      loc_1800031B6
0x180003066  mov     rcx, [rsp+280h+hObject]; hObject
0x18000306b  test    rcx, rcx
0x18000306e  jz      short loc_18000307E
0x180003070  call    cs:__imp_CloseHandle
0x180003076  test    eax, eax
0x180003078  jz      loc_1800031C8
0x18000307e  call    cs:__imp_GetProcessHeap
0x180003084  mov     r8, rsi; lpMem
0x180003087  xor     edx, edx; dwFlags
0x180003089  mov     rcx, rax; hHeap
0x18000308c  call    cs:__imp_HeapFree
0x180003092  mov     rcx, [rbp+188h]; this
0x180003099  lea     r8, aWil; "wil"
0x1800030a0  mov     r9d, r14d; char *
0x1800030a3  mov     edx, 137h; void *
0x1800030a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800030ad  test    rdi, rdi
0x1800030b0  jz      short loc_1800030C3
0x1800030b2  mov     rcx, rdi; hMutex
0x1800030b5  call    cs:__imp_ReleaseMutex
0x1800030bb  test    eax, eax
0x1800030bd  jz      loc_1800031DA
0x1800030c3  mov     rcx, rbx; hObject
0x1800030c6  call    cs:__imp_CloseHandle
0x1800030cc  test    eax, eax
0x1800030ce  jz      loc_1800031EC
0x1800030d4  mov     eax, r14d
0x1800030d7  jmp     short loc_180003147
0x1800030d9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800030de  xor     edx, edx; Val
0x1800030e0  mov     dword ptr [rsi], 1
0x1800030e6  lea     rcx, [rsi+22h]; void *
0x1800030ea  mov     [rsi+8], rbx
0x1800030ee  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800030f3  lea     r8d, [rdx+56h]; Size
0x1800030f7  call    memset_0
0x1800030fc  xor     edx, edx; Val
0x1800030fe  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003104  lea     rcx, [rsi+28h]; void *
0x180003108  mov     dword ptr [rsi+24h], 1
0x18000310f  lea     r8d, [rdx+50h]; Size
0x180003113  call    memset_0
0x180003118  xor     ebx, ebx
0x18000311a  mov     [r15], rsi
0x18000311d  test    rdi, rdi
0x180003120  jz      short loc_180003133
0x180003122  mov     rcx, rdi; hMutex
0x180003125  call    cs:__imp_ReleaseMutex
0x18000312b  test    eax, eax
0x18000312d  jz      loc_1800031FE
0x180003133  test    rbx, rbx
0x180003136  jz      short loc_180003145
0x180003138  mov     rcx, rbx; hObject
0x18000313b  call    cs:__imp_CloseHandle
0x180003141  test    eax, eax
0x180003143  jz      short loc_18000316D
0x180003145  xor     eax, eax
0x180003147  mov     rcx, [rbp+180h+var_30]
0x18000314e  xor     rcx, rsp; StackCookie
0x180003151  call    __security_check_cookie
0x180003156  mov     rbx, [rsp+280h+arg_10]
0x18000315e  add     rsp, 260h
0x180003165  pop     r15
0x180003167  pop     r14
0x180003169  pop     rdi
0x18000316a  pop     rsi
0x18000316b  pop     rbp
0x18000316c  retn
0x18000316d  mov     rcx, [rbp+188h]; this
0x180003174  mov     edx, 0A0Bh; void *
0x180003179  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000317f  mov     rcx, [rbp+188h]; this
0x180003186  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000318c  mov     rcx, [rbp+188h]; this
0x180003193  mov     edx, 0A15h; void *
0x180003198  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000319e  mov     rcx, [rbp+188h]; this
0x1800031a5  mov     edx, 0A0Bh; void *
0x1800031aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800031b6  mov     rcx, [rbp+188h]; this
0x1800031bd  mov     edx, 0A0Bh; void *
0x1800031c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031c8  mov     rcx, [rbp+188h]; this
0x1800031cf  mov     edx, 0A0Bh; void *
0x1800031d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031da  mov     rcx, [rbp+188h]; this
0x1800031e1  mov     edx, 0A15h; void *
0x1800031e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031ec  mov     rcx, [rbp+188h]; this
0x1800031f3  mov     edx, 0A0Bh; void *
0x1800031f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031fe  mov     rcx, [rbp+188h]; this
0x180003205  mov     edx, 0A15h; void *
0x18000320a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
