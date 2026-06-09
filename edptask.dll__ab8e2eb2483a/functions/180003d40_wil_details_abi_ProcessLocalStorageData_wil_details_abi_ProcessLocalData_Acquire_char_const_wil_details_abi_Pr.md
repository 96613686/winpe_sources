# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003d40`
- end: `0x180004108`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004bf0`

## callees

- `0x180002c00`
- `0x180003d40`
- `0x180004110`
- `0x1800043f4`
- `0x180004988`
- `0x180005468`
- `0x1800056c4`
- `0x1800061ac`
- `0x180006790`
- `0x1800067a0`
- `0x1800133e2`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003dd9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003dd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000401d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000401d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003db8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003db8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004033`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004033`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f76`

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
0x180003d40  mov     [rsp-8+arg_10], rbx
0x180003d45  push    rbp
0x180003d46  push    rsi
0x180003d47  push    rdi
0x180003d48  push    r14
0x180003d4a  push    r15
0x180003d4c  lea     rbp, [rsp-160h]
0x180003d54  sub     rsp, 260h
0x180003d5b  mov     rax, cs:__security_cookie
0x180003d62  xor     rax, rsp
0x180003d65  mov     [rbp+180h+var_30], rax
0x180003d6c  mov     r15, rdx
0x180003d6f  mov     qword ptr [rdx], 0
0x180003d76  mov     rbx, rcx
0x180003d79  call    cs:__imp_GetCurrentProcessId
0x180003d7f  mov     r14d, 78h ; 'x'
0x180003d85  mov     [rsp+280h+var_258], rbx
0x180003d8a  mov     r9d, eax
0x180003d8d  mov     [rsp+280h+var_260], r14d; int
0x180003d92  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d99  mov     edx, 104h; unsigned __int64
0x180003d9e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003da3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003da8  mov     r9d, 1F0001h; dwDesiredAccess
0x180003dae  lea     rdx, [rsp+280h+Name]; lpName
0x180003db3  xor     r8d, r8d; dwFlags
0x180003db6  xor     ecx, ecx; lpMutexAttributes
0x180003db8  call    cs:__imp_CreateMutexExW
0x180003dbe  mov     rbx, rax
0x180003dc1  test    rax, rax
0x180003dc4  jnz     short loc_180003DD0
0x180003dc6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003dcb  jmp     loc_18000403F
0x180003dd0  xor     r8d, r8d; bAlertable
0x180003dd3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003dd6  mov     rcx, rbx; hHandle
0x180003dd9  call    cs:__imp_WaitForSingleObjectEx
0x180003ddf  cmp     eax, 102h
0x180003de4  jz      short loc_180003DF6
0x180003de6  test    eax, 0FFFFFF7Fh
0x180003deb  jnz     loc_180004077
0x180003df1  mov     rdi, rbx
0x180003df4  jmp     short loc_180003DF8
0x180003df6  xor     edi, edi
0x180003df8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003dfd  mov     [rsp+280h+hObject], 0
0x180003e06  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e0b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003e10  mov     esi, eax
0x180003e12  test    eax, eax
0x180003e14  jns     short loc_180003E95
0x180003e16  mov     rcx, [rbp+188h]; this
0x180003e1d  lea     r8, aWil; "wil"
0x180003e24  mov     r9d, eax; char *
0x180003e27  mov     edx, 66h ; 'f'; void *
0x180003e2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e31  mov     rcx, [rbp+188h]; this
0x180003e38  lea     r8, aWil; "wil"
0x180003e3f  mov     r9d, esi; char *
0x180003e42  mov     edx, 6Fh ; 'o'; void *
0x180003e47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e4c  mov     rcx, [rbp+188h]; this
0x180003e53  lea     r8, aWil; "wil"
0x180003e5a  mov     r9d, esi; char *
0x180003e5d  mov     edx, 12Eh; void *
0x180003e62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e67  test    rdi, rdi
0x180003e6a  jz      short loc_180003E7D
0x180003e6c  mov     rcx, rdi; hMutex
0x180003e6f  call    cs:__imp_ReleaseMutex
0x180003e75  test    eax, eax
0x180003e77  jz      loc_180004084
0x180003e7d  mov     rcx, rbx; hObject
0x180003e80  call    cs:__imp_CloseHandle
0x180003e86  test    eax, eax
0x180003e88  jz      loc_180004096
0x180003e8e  mov     eax, esi
0x180003e90  jmp     loc_18000403F
0x180003e95  mov     rax, [rsp+280h+hObject]
0x180003e9a  lea     rcx, ds:0[rax*4]
0x180003ea2  test    rcx, rcx
0x180003ea5  jz      short loc_180003EB5
0x180003ea7  mov     [r15], rcx
0x180003eaa  mov     eax, [rcx]
0x180003eac  inc     eax
0x180003eae  mov     [rcx], eax
0x180003eb0  jmp     loc_180004015
0x180003eb5  mov     rdx, r14; dwBytes
0x180003eb8  mov     qword ptr [r15], 0
0x180003ebf  mov     ecx, 8; dwFlags
0x180003ec4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003ec9  mov     rsi, rax
0x180003ecc  test    rax, rax
0x180003ecf  jnz     short loc_180003EF7
0x180003ed1  mov     rcx, [rbp+188h]; this
0x180003ed8  lea     r8, aWil; "wil"
0x180003edf  mov     r14d, 8007000Eh
0x180003ee5  mov     edx, 14Bh; void *
0x180003eea  mov     r9d, r14d; char *
0x180003eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ef2  jmp     loc_180003F8A
0x180003ef7  xorps   xmm0, xmm0
0x180003efa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003f00  test    sil, 3
0x180003f04  jnz     loc_1800040A8
0x180003f0a  mov     r9, rsi
0x180003f0d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003f12  shr     r9, 2; unsigned __int64
0x180003f16  lea     rcx, [rsp+280h+hObject]; this
0x180003f1b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003f20  mov     r14d, eax
0x180003f23  test    eax, eax
0x180003f25  jns     loc_180003FD1
0x180003f2b  mov     rcx, [rbp+188h]; this
0x180003f32  lea     r8, aWil; "wil"
0x180003f39  mov     r9d, eax; char *
0x180003f3c  mov     edx, 14Eh; void *
0x180003f41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f46  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003f4b  test    rcx, rcx
0x180003f4e  jz      short loc_180003F5E
0x180003f50  call    cs:__imp_CloseHandle
0x180003f56  test    eax, eax
0x180003f58  jz      loc_1800040AE
0x180003f5e  mov     rcx, [rsp+280h+hObject]; hObject
0x180003f63  test    rcx, rcx
0x180003f66  jz      short loc_180003F76
0x180003f68  call    cs:__imp_CloseHandle
0x180003f6e  test    eax, eax
0x180003f70  jz      loc_1800040C0
0x180003f76  call    cs:__imp_GetProcessHeap
0x180003f7c  mov     r8, rsi; lpMem
0x180003f7f  xor     edx, edx; dwFlags
0x180003f81  mov     rcx, rax; hHeap
0x180003f84  call    cs:__imp_HeapFree
0x180003f8a  mov     rcx, [rbp+188h]; this
0x180003f91  lea     r8, aWil; "wil"
0x180003f98  mov     r9d, r14d; char *
0x180003f9b  mov     edx, 137h; void *
0x180003fa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fa5  test    rdi, rdi
0x180003fa8  jz      short loc_180003FBB
0x180003faa  mov     rcx, rdi; hMutex
0x180003fad  call    cs:__imp_ReleaseMutex
0x180003fb3  test    eax, eax
0x180003fb5  jz      loc_1800040D2
0x180003fbb  mov     rcx, rbx; hObject
0x180003fbe  call    cs:__imp_CloseHandle
0x180003fc4  test    eax, eax
0x180003fc6  jz      loc_1800040E4
0x180003fcc  mov     eax, r14d
0x180003fcf  jmp     short loc_18000403F
0x180003fd1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003fd6  xor     edx, edx; Val
0x180003fd8  mov     dword ptr [rsi], 1
0x180003fde  lea     rcx, [rsi+22h]; void *
0x180003fe2  mov     [rsi+8], rbx
0x180003fe6  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003feb  lea     r8d, [rdx+56h]; Size
0x180003fef  call    memset_0
0x180003ff4  xor     edx, edx; Val
0x180003ff6  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003ffc  lea     rcx, [rsi+28h]; void *
0x180004000  mov     dword ptr [rsi+24h], 1
0x180004007  lea     r8d, [rdx+50h]; Size
0x18000400b  call    memset_0
0x180004010  xor     ebx, ebx
0x180004012  mov     [r15], rsi
0x180004015  test    rdi, rdi
0x180004018  jz      short loc_18000402B
0x18000401a  mov     rcx, rdi; hMutex
0x18000401d  call    cs:__imp_ReleaseMutex
0x180004023  test    eax, eax
0x180004025  jz      loc_1800040F6
0x18000402b  test    rbx, rbx
0x18000402e  jz      short loc_18000403D
0x180004030  mov     rcx, rbx; hObject
0x180004033  call    cs:__imp_CloseHandle
0x180004039  test    eax, eax
0x18000403b  jz      short loc_180004065
0x18000403d  xor     eax, eax
0x18000403f  mov     rcx, [rbp+180h+var_30]
0x180004046  xor     rcx, rsp; StackCookie
0x180004049  call    __security_check_cookie
0x18000404e  mov     rbx, [rsp+280h+arg_10]
0x180004056  add     rsp, 260h
0x18000405d  pop     r15
0x18000405f  pop     r14
0x180004061  pop     rdi
0x180004062  pop     rsi
0x180004063  pop     rbp
0x180004064  retn
0x180004065  mov     rcx, [rbp+188h]; this
0x18000406c  mov     edx, 0A0Bh; void *
0x180004071  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004077  mov     rcx, [rbp+188h]; this
0x18000407e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004084  mov     rcx, [rbp+188h]; this
0x18000408b  mov     edx, 0A15h; void *
0x180004090  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004096  mov     rcx, [rbp+188h]; this
0x18000409d  mov     edx, 0A0Bh; void *
0x1800040a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800040ae  mov     rcx, [rbp+188h]; this
0x1800040b5  mov     edx, 0A0Bh; void *
0x1800040ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040c0  mov     rcx, [rbp+188h]; this
0x1800040c7  mov     edx, 0A0Bh; void *
0x1800040cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040d2  mov     rcx, [rbp+188h]; this
0x1800040d9  mov     edx, 0A15h; void *
0x1800040de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040e4  mov     rcx, [rbp+188h]; this
0x1800040eb  mov     edx, 0A0Bh; void *
0x1800040f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040f6  mov     rcx, [rbp+188h]; this
0x1800040fd  mov     edx, 0A15h; void *
0x180004102  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
