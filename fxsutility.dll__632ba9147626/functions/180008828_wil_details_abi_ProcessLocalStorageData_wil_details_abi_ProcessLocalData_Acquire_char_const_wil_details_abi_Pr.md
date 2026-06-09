# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008828`
- end: `0x180008bc6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180009f70`

## callees

- `0x180005168`
- `0x180008828`
- `0x180009044`
- `0x1800094a4`
- `0x180009d08`
- `0x18000a908`
- `0x18000bbd4`
- `0x18000c70c`
- `0x18000cedc`
- `0x18000ceec`
- `0x180015cbe`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180008953`
- `KERNEL32!CloseHandle` at `0x180008a15`
- `KERNEL32!CloseHandle` at `0x180008a2d`
- `KERNEL32!CloseHandle` at `0x180008a7c`
- `KERNEL32!CloseHandle` at `0x180008af1`
- `KERNEL32!CloseHandle` at `0x180008953`
- `KERNEL32!CloseHandle` at `0x180008a15`
- `KERNEL32!CloseHandle` at `0x180008a2d`
- `KERNEL32!CloseHandle` at `0x180008a7c`
- `KERNEL32!CloseHandle` at `0x180008af1`
- `KERNEL32!GetCurrentProcessId` at `0x180008861`
- `KERNEL32!GetCurrentProcessId` at `0x180008861`
- `KERNEL32!HeapFree` at `0x180008a49`
- `KERNEL32!HeapFree` at `0x180008a49`
- `KERNEL32!GetProcessHeap` at `0x180008a3b`
- `KERNEL32!GetProcessHeap` at `0x180008a3b`
- `KERNEL32!ReleaseMutex` at `0x180008942`
- `KERNEL32!ReleaseMutex` at `0x180008a6b`
- `KERNEL32!ReleaseMutex` at `0x180008adb`
- `KERNEL32!ReleaseMutex` at `0x180008942`
- `KERNEL32!ReleaseMutex` at `0x180008a6b`
- `KERNEL32!ReleaseMutex` at `0x180008adb`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800088c1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800088c1`
- `KERNEL32!CreateMutexExW` at `0x1800088a0`
- `KERNEL32!CreateMutexExW` at `0x1800088a0`

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
0x180008828  mov     [rsp-8+arg_10], rbx
0x18000882d  push    rbp
0x18000882e  push    rsi
0x18000882f  push    rdi
0x180008830  push    r14
0x180008832  push    r15
0x180008834  lea     rbp, [rsp-160h]
0x18000883c  sub     rsp, 260h
0x180008843  mov     rax, cs:__security_cookie
0x18000884a  xor     rax, rsp
0x18000884d  mov     [rbp+180h+var_30], rax
0x180008854  mov     r15, rdx
0x180008857  mov     qword ptr [rdx], 0
0x18000885e  mov     rbx, rcx
0x180008861  call    cs:__imp_GetCurrentProcessId
0x180008867  mov     r14d, 78h ; 'x'
0x18000886d  mov     [rsp+280h+var_258], rbx
0x180008872  mov     r9d, eax
0x180008875  mov     [rsp+280h+var_260], r14d; int
0x18000887a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008881  mov     edx, 104h; unsigned __int64
0x180008886  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000888b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008890  mov     r9d, 1F0001h; dwDesiredAccess
0x180008896  lea     rdx, [rsp+280h+Name]; lpName
0x18000889b  xor     r8d, r8d; dwFlags
0x18000889e  xor     ecx, ecx; lpMutexAttributes
0x1800088a0  call    cs:__imp_CreateMutexExW
0x1800088a6  mov     rbx, rax
0x1800088a9  test    rax, rax
0x1800088ac  jnz     short loc_1800088B8
0x1800088ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800088b3  jmp     loc_180008AFD
0x1800088b8  xor     r8d, r8d; bAlertable
0x1800088bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800088be  mov     rcx, rbx; hHandle
0x1800088c1  call    cs:__imp_WaitForSingleObjectEx
0x1800088c7  cmp     eax, 102h
0x1800088cc  jz      short loc_1800088DE
0x1800088ce  test    eax, 0FFFFFF7Fh
0x1800088d3  jnz     loc_180008B35
0x1800088d9  mov     rdi, rbx
0x1800088dc  jmp     short loc_1800088E0
0x1800088de  xor     edi, edi
0x1800088e0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800088e5  mov     [rsp+280h+hObject], 0
0x1800088ee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800088f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800088f8  mov     esi, eax
0x1800088fa  test    eax, eax
0x1800088fc  jns     short loc_180008968
0x1800088fe  mov     rcx, [rbp+188h]; this
0x180008905  mov     r9d, eax; char *
0x180008908  mov     edx, 66h ; 'f'; void *
0x18000890d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008912  mov     rcx, [rbp+188h]; this
0x180008919  mov     r9d, esi; char *
0x18000891c  mov     edx, 6Fh ; 'o'; void *
0x180008921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008926  mov     rcx, [rbp+188h]; this
0x18000892d  mov     r9d, esi; char *
0x180008930  mov     edx, 12Eh; void *
0x180008935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000893a  test    rdi, rdi
0x18000893d  jz      short loc_180008950
0x18000893f  mov     rcx, rdi; hMutex
0x180008942  call    cs:__imp_ReleaseMutex
0x180008948  test    eax, eax
0x18000894a  jz      loc_180008B42
0x180008950  mov     rcx, rbx; hObject
0x180008953  call    cs:__imp_CloseHandle
0x180008959  test    eax, eax
0x18000895b  jz      loc_180008B54
0x180008961  mov     eax, esi
0x180008963  jmp     loc_180008AFD
0x180008968  mov     rax, [rsp+280h+hObject]
0x18000896d  lea     rcx, ds:0[rax*4]
0x180008975  test    rcx, rcx
0x180008978  jz      short loc_180008988
0x18000897a  mov     [r15], rcx
0x18000897d  mov     eax, [rcx]
0x18000897f  inc     eax
0x180008981  mov     [rcx], eax
0x180008983  jmp     loc_180008AD3
0x180008988  mov     rdx, r14; dwBytes
0x18000898b  mov     qword ptr [r15], 0
0x180008992  mov     ecx, 8; dwFlags
0x180008997  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000899c  mov     rsi, rax
0x18000899f  test    rax, rax
0x1800089a2  jnz     short loc_1800089C3
0x1800089a4  mov     rcx, [rbp+188h]; this
0x1800089ab  mov     r14d, 8007000Eh
0x1800089b1  mov     r9d, r14d; char *
0x1800089b4  mov     edx, 14Bh; void *
0x1800089b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089be  jmp     loc_180008A4F
0x1800089c3  xorps   xmm0, xmm0
0x1800089c6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800089cc  test    sil, 3
0x1800089d0  jnz     loc_180008B66
0x1800089d6  mov     r9, rsi
0x1800089d9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800089de  shr     r9, 2; unsigned __int64
0x1800089e2  lea     rcx, [rsp+280h+hObject]; this
0x1800089e7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800089ec  mov     r14d, eax
0x1800089ef  test    eax, eax
0x1800089f1  jns     loc_180008A8F
0x1800089f7  mov     rcx, [rbp+188h]; this
0x1800089fe  mov     r9d, eax; char *
0x180008a01  mov     edx, 14Eh; void *
0x180008a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a0b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008a10  test    rcx, rcx
0x180008a13  jz      short loc_180008A23
0x180008a15  call    cs:__imp_CloseHandle
0x180008a1b  test    eax, eax
0x180008a1d  jz      loc_180008B6C
0x180008a23  mov     rcx, [rsp+280h+hObject]; hObject
0x180008a28  test    rcx, rcx
0x180008a2b  jz      short loc_180008A3B
0x180008a2d  call    cs:__imp_CloseHandle
0x180008a33  test    eax, eax
0x180008a35  jz      loc_180008B7E
0x180008a3b  call    cs:__imp_GetProcessHeap
0x180008a41  mov     r8, rsi; lpMem
0x180008a44  xor     edx, edx; dwFlags
0x180008a46  mov     rcx, rax; hHeap
0x180008a49  call    cs:__imp_HeapFree
0x180008a4f  mov     rcx, [rbp+188h]; this
0x180008a56  mov     r9d, r14d; char *
0x180008a59  mov     edx, 137h; void *
0x180008a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a63  test    rdi, rdi
0x180008a66  jz      short loc_180008A79
0x180008a68  mov     rcx, rdi; hMutex
0x180008a6b  call    cs:__imp_ReleaseMutex
0x180008a71  test    eax, eax
0x180008a73  jz      loc_180008B90
0x180008a79  mov     rcx, rbx; hObject
0x180008a7c  call    cs:__imp_CloseHandle
0x180008a82  test    eax, eax
0x180008a84  jz      loc_180008BA2
0x180008a8a  mov     eax, r14d
0x180008a8d  jmp     short loc_180008AFD
0x180008a8f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008a94  xor     edx, edx; Val
0x180008a96  mov     dword ptr [rsi], 1
0x180008a9c  lea     rcx, [rsi+22h]; void *
0x180008aa0  mov     [rsi+8], rbx
0x180008aa4  movdqu  xmmword ptr [rsi+10h], xmm0
0x180008aa9  lea     r8d, [rdx+56h]; Size
0x180008aad  call    memset_0
0x180008ab2  xor     edx, edx; Val
0x180008ab4  mov     word ptr [rsi+20h], 58h ; 'X'
0x180008aba  lea     rcx, [rsi+28h]; void *
0x180008abe  mov     dword ptr [rsi+24h], 1
0x180008ac5  lea     r8d, [rdx+50h]; Size
0x180008ac9  call    memset_0
0x180008ace  xor     ebx, ebx
0x180008ad0  mov     [r15], rsi
0x180008ad3  test    rdi, rdi
0x180008ad6  jz      short loc_180008AE9
0x180008ad8  mov     rcx, rdi; hMutex
0x180008adb  call    cs:__imp_ReleaseMutex
0x180008ae1  test    eax, eax
0x180008ae3  jz      loc_180008BB4
0x180008ae9  test    rbx, rbx
0x180008aec  jz      short loc_180008AFB
0x180008aee  mov     rcx, rbx; hObject
0x180008af1  call    cs:__imp_CloseHandle
0x180008af7  test    eax, eax
0x180008af9  jz      short loc_180008B23
0x180008afb  xor     eax, eax
0x180008afd  mov     rcx, [rbp+180h+var_30]
0x180008b04  xor     rcx, rsp; StackCookie
0x180008b07  call    __security_check_cookie
0x180008b0c  mov     rbx, [rsp+280h+arg_10]
0x180008b14  add     rsp, 260h
0x180008b1b  pop     r15
0x180008b1d  pop     r14
0x180008b1f  pop     rdi
0x180008b20  pop     rsi
0x180008b21  pop     rbp
0x180008b22  retn
0x180008b23  mov     rcx, [rbp+188h]; this
0x180008b2a  mov     edx, 0A0Bh; void *
0x180008b2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b35  mov     rcx, [rbp+188h]; this
0x180008b3c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008b42  mov     rcx, [rbp+188h]; this
0x180008b49  mov     edx, 0A15h; void *
0x180008b4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b54  mov     rcx, [rbp+188h]; this
0x180008b5b  mov     edx, 0A0Bh; void *
0x180008b60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b66  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008b6c  mov     rcx, [rbp+188h]; this
0x180008b73  mov     edx, 0A0Bh; void *
0x180008b78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b7e  mov     rcx, [rbp+188h]; this
0x180008b85  mov     edx, 0A0Bh; void *
0x180008b8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b90  mov     rcx, [rbp+188h]; this
0x180008b97  mov     edx, 0A15h; void *
0x180008b9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ba2  mov     rcx, [rbp+188h]; this
0x180008ba9  mov     edx, 0A0Bh; void *
0x180008bae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008bb4  mov     rcx, [rbp+188h]; this
0x180008bbb  mov     edx, 0A15h; void *
0x180008bc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
