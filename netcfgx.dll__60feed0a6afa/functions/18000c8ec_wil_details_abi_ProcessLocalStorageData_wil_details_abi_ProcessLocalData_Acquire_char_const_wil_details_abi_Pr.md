# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c8ec`
- end: `0x18000cc8c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000d824`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x180007b3c`
- `0x18000c8ec`
- `0x18000cc94`
- `0x18000ced0`
- `0x18000d518`
- `0x18000e8cc`
- `0x18000ef34`
- `0x18000ff0c`
- `0x180010398`
- `0x1800103a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ca06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cb3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cbaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ca06`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cb3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000cbaf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c964`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c964`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c985`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ca17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cada`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ca17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cada`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c925`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = *(_OWORD *)hObject;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      *a2 = v26;
      v6 = 0;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v46);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x18000c8ec  mov     [rsp-8+arg_10], rbx
0x18000c8f1  push    rbp
0x18000c8f2  push    rsi
0x18000c8f3  push    rdi
0x18000c8f4  push    r14
0x18000c8f6  push    r15
0x18000c8f8  lea     rbp, [rsp-160h]
0x18000c900  sub     rsp, 260h
0x18000c907  mov     rax, cs:__security_cookie
0x18000c90e  xor     rax, rsp
0x18000c911  mov     [rbp+180h+var_30], rax
0x18000c918  mov     r15, rdx
0x18000c91b  mov     rbx, rcx
0x18000c91e  mov     qword ptr [rdx], 0
0x18000c925  call    cs:__imp_GetCurrentProcessId
0x18000c92b  mov     r9d, eax
0x18000c92e  mov     [rsp+280h+var_258], rbx
0x18000c933  mov     r14d, 78h ; 'x'
0x18000c939  mov     [rsp+280h+var_260], r14d; int
0x18000c93e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c945  mov     edx, 104h; unsigned __int64
0x18000c94a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c94f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c954  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c95a  xor     r8d, r8d; dwFlags
0x18000c95d  lea     rdx, [rsp+280h+Name]; lpName
0x18000c962  xor     ecx, ecx; lpMutexAttributes
0x18000c964  call    cs:__imp_CreateMutexExW
0x18000c96a  mov     rbx, rax
0x18000c96d  test    rax, rax
0x18000c970  jnz     short loc_18000C97C
0x18000c972  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c977  jmp     loc_18000CBD1
0x18000c97c  xor     r8d, r8d; bAlertable
0x18000c97f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c982  mov     rcx, rbx; hHandle
0x18000c985  call    cs:__imp_WaitForSingleObjectEx
0x18000c98b  cmp     eax, 102h
0x18000c990  jz      short loc_18000C9A2
0x18000c992  test    eax, 0FFFFFF7Fh
0x18000c997  jnz     loc_18000CC09
0x18000c99d  mov     rdi, rbx
0x18000c9a0  jmp     short loc_18000C9A4
0x18000c9a2  xor     edi, edi
0x18000c9a4  mov     [rsp+280h+hObject], 0
0x18000c9ad  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000c9b2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c9b7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000c9bc  mov     esi, eax
0x18000c9be  test    eax, eax
0x18000c9c0  jns     short loc_18000CA2C
0x18000c9c2  mov     rcx, [rbp+188h]; this
0x18000c9c9  mov     r9d, eax; char *
0x18000c9cc  mov     edx, 66h ; 'f'; void *
0x18000c9d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9d6  mov     rcx, [rbp+188h]; this
0x18000c9dd  mov     r9d, esi; char *
0x18000c9e0  mov     edx, 6Fh ; 'o'; void *
0x18000c9e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9ea  mov     rcx, [rbp+188h]; this
0x18000c9f1  mov     r9d, esi; char *
0x18000c9f4  mov     edx, 12Eh; void *
0x18000c9f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9fe  test    rdi, rdi
0x18000ca01  jz      short loc_18000CA14
0x18000ca03  mov     rcx, rdi; hMutex
0x18000ca06  call    cs:__imp_ReleaseMutex
0x18000ca0c  test    eax, eax
0x18000ca0e  jz      loc_18000CC16
0x18000ca14  mov     rcx, rbx; hObject
0x18000ca17  call    cs:__imp_CloseHandle
0x18000ca1d  test    eax, eax
0x18000ca1f  jz      loc_18000CC28
0x18000ca25  mov     eax, esi
0x18000ca27  jmp     loc_18000CBD1
0x18000ca2c  mov     rax, [rsp+280h+hObject]
0x18000ca31  lea     rcx, ds:0[rax*4]
0x18000ca39  test    rcx, rcx
0x18000ca3c  jz      short loc_18000CA4C
0x18000ca3e  mov     [r15], rcx
0x18000ca41  mov     eax, [rcx]
0x18000ca43  inc     eax
0x18000ca45  mov     [rcx], eax
0x18000ca47  jmp     loc_18000CBA7
0x18000ca4c  mov     qword ptr [r15], 0
0x18000ca53  mov     rdx, r14; dwBytes
0x18000ca56  mov     ecx, 8; dwFlags
0x18000ca5b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ca60  mov     rsi, rax
0x18000ca63  test    rax, rax
0x18000ca66  jnz     short loc_18000CA88
0x18000ca68  mov     rcx, [rbp+188h]; this
0x18000ca6f  mov     r14d, 8007000Eh
0x18000ca75  mov     r9d, r14d; char *
0x18000ca78  mov     edx, 14Bh; void *
0x18000ca7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca82  nop
0x18000ca83  jmp     loc_18000CB23
0x18000ca88  xorps   xmm0, xmm0
0x18000ca8b  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000ca91  test    sil, 3
0x18000ca95  jnz     loc_18000CC3A
0x18000ca9b  mov     r9, rsi
0x18000ca9e  shr     r9, 2; unsigned __int64
0x18000caa2  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000caa7  lea     rcx, [rsp+280h+hObject]; this
0x18000caac  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000cab1  mov     r14d, eax
0x18000cab4  test    eax, eax
0x18000cab6  jns     loc_18000CB63
0x18000cabc  mov     rcx, [rbp+188h]; this
0x18000cac3  mov     r9d, eax; char *
0x18000cac6  mov     edx, 14Eh; void *
0x18000cacb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cad0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000cad5  test    rcx, rcx
0x18000cad8  jz      short loc_18000CAEF
0x18000cada  call    cs:__imp_CloseHandle
0x18000cae0  mov     rcx, [rbp+188h]; this
0x18000cae7  test    eax, eax
0x18000cae9  jz      loc_18000CC40
0x18000caef  mov     rcx, [rsp+280h+hObject]; hObject
0x18000caf4  test    rcx, rcx
0x18000caf7  jz      short loc_18000CB0E
0x18000caf9  call    cs:__imp_CloseHandle
0x18000caff  mov     rcx, [rbp+188h]; this
0x18000cb06  test    eax, eax
0x18000cb08  jz      loc_18000CC4B
0x18000cb0e  call    cs:__imp_GetProcessHeap
0x18000cb14  mov     rcx, rax; hHeap
0x18000cb17  mov     r8, rsi; lpMem
0x18000cb1a  xor     edx, edx; dwFlags
0x18000cb1c  call    cs:__imp_HeapFree
0x18000cb22  nop
0x18000cb23  mov     rcx, [rbp+188h]; this
0x18000cb2a  mov     r9d, r14d; char *
0x18000cb2d  mov     edx, 137h; void *
0x18000cb32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb37  test    rdi, rdi
0x18000cb3a  jz      short loc_18000CB4D
0x18000cb3c  mov     rcx, rdi; hMutex
0x18000cb3f  call    cs:__imp_ReleaseMutex
0x18000cb45  test    eax, eax
0x18000cb47  jz      loc_18000CC56
0x18000cb4d  mov     rcx, rbx; hObject
0x18000cb50  call    cs:__imp_CloseHandle
0x18000cb56  test    eax, eax
0x18000cb58  jz      loc_18000CC68
0x18000cb5e  mov     eax, r14d
0x18000cb61  jmp     short loc_18000CBD1
0x18000cb63  mov     dword ptr [rsi], 1
0x18000cb69  mov     [rsi+8], rbx
0x18000cb6d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000cb72  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000cb77  lea     rcx, [rsi+22h]; void *
0x18000cb7b  xor     edx, edx; Val
0x18000cb7d  lea     r8d, [rdx+56h]; Size
0x18000cb81  call    memset_0
0x18000cb86  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000cb8c  mov     dword ptr [rsi+24h], 1
0x18000cb93  lea     rcx, [rsi+28h]; void *
0x18000cb97  xor     edx, edx; Val
0x18000cb99  lea     r8d, [rdx+50h]; Size
0x18000cb9d  call    memset_0
0x18000cba2  mov     [r15], rsi
0x18000cba5  xor     ebx, ebx
0x18000cba7  test    rdi, rdi
0x18000cbaa  jz      short loc_18000CBBD
0x18000cbac  mov     rcx, rdi; hMutex
0x18000cbaf  call    cs:__imp_ReleaseMutex
0x18000cbb5  test    eax, eax
0x18000cbb7  jz      loc_18000CC7A
0x18000cbbd  test    rbx, rbx
0x18000cbc0  jz      short loc_18000CBCF
0x18000cbc2  mov     rcx, rbx; hObject
0x18000cbc5  call    cs:__imp_CloseHandle
0x18000cbcb  test    eax, eax
0x18000cbcd  jz      short loc_18000CBF7
0x18000cbcf  xor     eax, eax
0x18000cbd1  mov     rcx, [rbp+180h+var_30]
0x18000cbd8  xor     rcx, rsp; StackCookie
0x18000cbdb  call    __security_check_cookie
0x18000cbe0  mov     rbx, [rsp+280h+arg_10]
0x18000cbe8  add     rsp, 260h
0x18000cbef  pop     r15
0x18000cbf1  pop     r14
0x18000cbf3  pop     rdi
0x18000cbf4  pop     rsi
0x18000cbf5  pop     rbp
0x18000cbf6  retn
0x18000cbf7  mov     rcx, [rbp+188h]; this
0x18000cbfe  mov     edx, 0A0Bh; void *
0x18000cc03  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc09  mov     rcx, [rbp+188h]; this
0x18000cc10  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000cc16  mov     rcx, [rbp+188h]; this
0x18000cc1d  mov     edx, 0A15h; void *
0x18000cc22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc28  mov     rcx, [rbp+188h]; this
0x18000cc2f  mov     edx, 0A0Bh; void *
0x18000cc34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc3a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cc40  mov     edx, 0A0Bh; void *
0x18000cc45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc4b  mov     edx, 0A0Bh; void *
0x18000cc50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc56  mov     rcx, [rbp+188h]; this
0x18000cc5d  mov     edx, 0A15h; void *
0x18000cc62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc68  mov     rcx, [rbp+188h]; this
0x18000cc6f  mov     edx, 0A0Bh; void *
0x18000cc74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cc7a  mov     rcx, [rbp+188h]; this
0x18000cc81  mov     edx, 0A15h; void *
0x18000cc86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
