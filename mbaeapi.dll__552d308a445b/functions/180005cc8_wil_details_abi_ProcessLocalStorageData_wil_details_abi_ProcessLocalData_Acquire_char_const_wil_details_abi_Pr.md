# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005cc8`
- end: `0x180006095`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007570`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180005cc8`
- `0x180006498`
- `0x1800069d8`
- `0x180007308`
- `0x180007cf8`
- `0x180009474`
- `0x180009ffc`
- `0x18000a47c`
- `0x18000ad4c`
- `0x18000ad5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005df7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005fa5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005df7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005fa5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d40`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005d61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005d61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005efe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005efe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fbb`

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
  bool v9; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x180005cc8  mov     [rsp-8+arg_10], rbx
0x180005ccd  push    rbp
0x180005cce  push    rsi
0x180005ccf  push    rdi
0x180005cd0  push    r14
0x180005cd2  push    r15
0x180005cd4  lea     rbp, [rsp-160h]
0x180005cdc  sub     rsp, 260h
0x180005ce3  mov     rax, cs:__security_cookie
0x180005cea  xor     rax, rsp
0x180005ced  mov     [rbp+180h+var_30], rax
0x180005cf4  mov     r15, rdx
0x180005cf7  mov     qword ptr [rdx], 0
0x180005cfe  mov     rbx, rcx
0x180005d01  call    cs:__imp_GetCurrentProcessId
0x180005d07  mov     r14d, 78h ; 'x'
0x180005d0d  mov     [rsp+280h+var_258], rbx
0x180005d12  mov     r9d, eax
0x180005d15  mov     [rsp+280h+var_260], r14d; int
0x180005d1a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005d21  mov     edx, 104h; unsigned __int64
0x180005d26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005d2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005d30  mov     r9d, 1F0001h; dwDesiredAccess
0x180005d36  lea     rdx, [rsp+280h+Name]; lpName
0x180005d3b  xor     r8d, r8d; dwFlags
0x180005d3e  xor     ecx, ecx; lpMutexAttributes
0x180005d40  call    cs:__imp_CreateMutexExW
0x180005d46  mov     rbx, rax
0x180005d49  test    rax, rax
0x180005d4c  jnz     short loc_180005D58
0x180005d4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005d53  jmp     loc_180005FC7
0x180005d58  xor     r8d, r8d; bAlertable
0x180005d5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005d5e  mov     rcx, rbx; hHandle
0x180005d61  call    cs:__imp_WaitForSingleObjectEx
0x180005d67  cmp     eax, 102h
0x180005d6c  jz      short loc_180005D7E
0x180005d6e  test    eax, 0FFFFFF7Fh
0x180005d73  jnz     loc_180005FFF
0x180005d79  mov     rdi, rbx
0x180005d7c  jmp     short loc_180005D80
0x180005d7e  xor     edi, edi
0x180005d80  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005d85  mov     [rsp+280h+hObject], 0
0x180005d8e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005d93  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005d98  mov     esi, eax
0x180005d9a  test    eax, eax
0x180005d9c  jns     short loc_180005E1D
0x180005d9e  mov     rcx, [rbp+188h]; this
0x180005da5  lea     r8, aWil; "wil"
0x180005dac  mov     r9d, eax; char *
0x180005daf  mov     edx, 66h ; 'f'; void *
0x180005db4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005db9  mov     rcx, [rbp+188h]; this
0x180005dc0  lea     r8, aWil; "wil"
0x180005dc7  mov     r9d, esi; char *
0x180005dca  mov     edx, 6Fh ; 'o'; void *
0x180005dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005dd4  mov     rcx, [rbp+188h]; this
0x180005ddb  lea     r8, aWil; "wil"
0x180005de2  mov     r9d, esi; char *
0x180005de5  mov     edx, 12Eh; void *
0x180005dea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005def  test    rdi, rdi
0x180005df2  jz      short loc_180005E05
0x180005df4  mov     rcx, rdi; hMutex
0x180005df7  call    cs:__imp_ReleaseMutex
0x180005dfd  test    eax, eax
0x180005dff  jz      loc_180006011
0x180005e05  mov     rcx, rbx; hObject
0x180005e08  call    cs:__imp_CloseHandle
0x180005e0e  test    eax, eax
0x180005e10  jz      loc_180006023
0x180005e16  mov     eax, esi
0x180005e18  jmp     loc_180005FC7
0x180005e1d  mov     rax, [rsp+280h+hObject]
0x180005e22  lea     rcx, ds:0[rax*4]
0x180005e2a  test    rcx, rcx
0x180005e2d  jz      short loc_180005E3D
0x180005e2f  mov     [r15], rcx
0x180005e32  mov     eax, [rcx]
0x180005e34  inc     eax
0x180005e36  mov     [rcx], eax
0x180005e38  jmp     loc_180005F9D
0x180005e3d  mov     rdx, r14; dwBytes
0x180005e40  mov     qword ptr [r15], 0
0x180005e47  mov     ecx, 8; dwFlags
0x180005e4c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005e51  mov     rsi, rax
0x180005e54  test    rax, rax
0x180005e57  jnz     short loc_180005E7F
0x180005e59  mov     rcx, [rbp+188h]; this
0x180005e60  lea     r8, aWil; "wil"
0x180005e67  mov     r14d, 8007000Eh
0x180005e6d  mov     edx, 14Bh; void *
0x180005e72  mov     r9d, r14d; char *
0x180005e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e7a  jmp     loc_180005F12
0x180005e7f  xorps   xmm0, xmm0
0x180005e82  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005e88  test    sil, 3
0x180005e8c  jnz     loc_180006035
0x180005e92  mov     r9, rsi
0x180005e95  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005e9a  shr     r9, 2; unsigned __int64
0x180005e9e  lea     rcx, [rsp+280h+hObject]; this
0x180005ea3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005ea8  mov     r14d, eax
0x180005eab  test    eax, eax
0x180005ead  jns     loc_180005F59
0x180005eb3  mov     rcx, [rbp+188h]; this
0x180005eba  lea     r8, aWil; "wil"
0x180005ec1  mov     r9d, eax; char *
0x180005ec4  mov     edx, 14Eh; void *
0x180005ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ece  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005ed3  test    rcx, rcx
0x180005ed6  jz      short loc_180005EE6
0x180005ed8  call    cs:__imp_CloseHandle
0x180005ede  test    eax, eax
0x180005ee0  jz      loc_18000603B
0x180005ee6  mov     rcx, [rsp+280h+hObject]; hObject
0x180005eeb  test    rcx, rcx
0x180005eee  jz      short loc_180005EFE
0x180005ef0  call    cs:__imp_CloseHandle
0x180005ef6  test    eax, eax
0x180005ef8  jz      loc_18000604D
0x180005efe  call    cs:__imp_GetProcessHeap
0x180005f04  mov     r8, rsi; lpMem
0x180005f07  xor     edx, edx; dwFlags
0x180005f09  mov     rcx, rax; hHeap
0x180005f0c  call    cs:__imp_HeapFree
0x180005f12  mov     rcx, [rbp+188h]; this
0x180005f19  lea     r8, aWil; "wil"
0x180005f20  mov     r9d, r14d; char *
0x180005f23  mov     edx, 137h; void *
0x180005f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f2d  test    rdi, rdi
0x180005f30  jz      short loc_180005F43
0x180005f32  mov     rcx, rdi; hMutex
0x180005f35  call    cs:__imp_ReleaseMutex
0x180005f3b  test    eax, eax
0x180005f3d  jz      loc_18000605F
0x180005f43  mov     rcx, rbx; hObject
0x180005f46  call    cs:__imp_CloseHandle
0x180005f4c  test    eax, eax
0x180005f4e  jz      loc_180006071
0x180005f54  mov     eax, r14d
0x180005f57  jmp     short loc_180005FC7
0x180005f59  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005f5e  xor     edx, edx; Val
0x180005f60  mov     dword ptr [rsi], 1
0x180005f66  lea     rcx, [rsi+22h]; void *
0x180005f6a  mov     [rsi+8], rbx
0x180005f6e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005f73  lea     r8d, [rdx+56h]; Size
0x180005f77  call    memset_0
0x180005f7c  xor     edx, edx; Val
0x180005f7e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005f84  lea     rcx, [rsi+28h]; void *
0x180005f88  mov     dword ptr [rsi+24h], 1
0x180005f8f  lea     r8d, [rdx+50h]; Size
0x180005f93  call    memset_0
0x180005f98  xor     ebx, ebx
0x180005f9a  mov     [r15], rsi
0x180005f9d  test    rdi, rdi
0x180005fa0  jz      short loc_180005FB3
0x180005fa2  mov     rcx, rdi; hMutex
0x180005fa5  call    cs:__imp_ReleaseMutex
0x180005fab  test    eax, eax
0x180005fad  jz      loc_180006083
0x180005fb3  test    rbx, rbx
0x180005fb6  jz      short loc_180005FC5
0x180005fb8  mov     rcx, rbx; hObject
0x180005fbb  call    cs:__imp_CloseHandle
0x180005fc1  test    eax, eax
0x180005fc3  jz      short loc_180005FED
0x180005fc5  xor     eax, eax
0x180005fc7  mov     rcx, [rbp+180h+var_30]
0x180005fce  xor     rcx, rsp; StackCookie
0x180005fd1  call    __security_check_cookie
0x180005fd6  mov     rbx, [rsp+280h+arg_10]
0x180005fde  add     rsp, 260h
0x180005fe5  pop     r15
0x180005fe7  pop     r14
0x180005fe9  pop     rdi
0x180005fea  pop     rsi
0x180005feb  pop     rbp
0x180005fec  retn
0x180005fed  mov     rcx, [rbp+188h]; this
0x180005ff4  mov     edx, 0A0Bh; void *
0x180005ff9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005fff  mov     rcx, [rbp+188h]; this
0x180006006  mov     edx, 0E01h; void *
0x18000600b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006011  mov     rcx, [rbp+188h]; this
0x180006018  mov     edx, 0A15h; void *
0x18000601d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006023  mov     rcx, [rbp+188h]; this
0x18000602a  mov     edx, 0A0Bh; void *
0x18000602f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006035  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000603b  mov     rcx, [rbp+188h]; this
0x180006042  mov     edx, 0A0Bh; void *
0x180006047  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000604d  mov     rcx, [rbp+188h]; this
0x180006054  mov     edx, 0A0Bh; void *
0x180006059  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000605f  mov     rcx, [rbp+188h]; this
0x180006066  mov     edx, 0A15h; void *
0x18000606b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006071  mov     rcx, [rbp+188h]; this
0x180006078  mov     edx, 0A0Bh; void *
0x18000607d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006083  mov     rcx, [rbp+188h]; this
0x18000608a  mov     edx, 0A15h; void *
0x18000608f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
