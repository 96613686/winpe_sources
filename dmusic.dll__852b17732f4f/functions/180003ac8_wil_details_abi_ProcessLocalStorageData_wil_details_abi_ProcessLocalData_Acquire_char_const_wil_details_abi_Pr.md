# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003ac8`
- end: `0x180003e90`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005370`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x180003ac8`
- `0x180004290`
- `0x1800047d8`
- `0x180005108`
- `0x18000603c`
- `0x180007684`
- `0x18000818c`
- `0x1800085ec`
- `0x180008ebc`
- `0x180008ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b40`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b61`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003da5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dbb`

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
0x180003ac8  mov     [rsp-8+arg_10], rbx
0x180003acd  push    rbp
0x180003ace  push    rsi
0x180003acf  push    rdi
0x180003ad0  push    r14
0x180003ad2  push    r15
0x180003ad4  lea     rbp, [rsp-160h]
0x180003adc  sub     rsp, 260h
0x180003ae3  mov     rax, cs:__security_cookie
0x180003aea  xor     rax, rsp
0x180003aed  mov     [rbp+180h+var_30], rax
0x180003af4  mov     r15, rdx
0x180003af7  mov     qword ptr [rdx], 0
0x180003afe  mov     rbx, rcx
0x180003b01  call    cs:__imp_GetCurrentProcessId
0x180003b07  mov     r14d, 78h ; 'x'
0x180003b0d  mov     [rsp+280h+var_258], rbx
0x180003b12  mov     r9d, eax
0x180003b15  mov     [rsp+280h+var_260], r14d; int
0x180003b1a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003b21  mov     edx, 104h; unsigned __int64
0x180003b26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b30  mov     r9d, 1F0001h; dwDesiredAccess
0x180003b36  lea     rdx, [rsp+280h+Name]; lpName
0x180003b3b  xor     r8d, r8d; dwFlags
0x180003b3e  xor     ecx, ecx; lpMutexAttributes
0x180003b40  call    cs:__imp_CreateMutexExW
0x180003b46  mov     rbx, rax
0x180003b49  test    rax, rax
0x180003b4c  jnz     short loc_180003B58
0x180003b4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b53  jmp     loc_180003DC7
0x180003b58  xor     r8d, r8d; bAlertable
0x180003b5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b5e  mov     rcx, rbx; hHandle
0x180003b61  call    cs:__imp_WaitForSingleObjectEx
0x180003b67  cmp     eax, 102h
0x180003b6c  jz      short loc_180003B7E
0x180003b6e  test    eax, 0FFFFFF7Fh
0x180003b73  jnz     loc_180003DFF
0x180003b79  mov     rdi, rbx
0x180003b7c  jmp     short loc_180003B80
0x180003b7e  xor     edi, edi
0x180003b80  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003b85  mov     [rsp+280h+hObject], 0
0x180003b8e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b93  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003b98  mov     esi, eax
0x180003b9a  test    eax, eax
0x180003b9c  jns     short loc_180003C1D
0x180003b9e  mov     rcx, [rbp+188h]; this
0x180003ba5  lea     r8, aWil; "wil"
0x180003bac  mov     r9d, eax; char *
0x180003baf  mov     edx, 66h ; 'f'; void *
0x180003bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bb9  mov     rcx, [rbp+188h]; this
0x180003bc0  lea     r8, aWil; "wil"
0x180003bc7  mov     r9d, esi; char *
0x180003bca  mov     edx, 6Fh ; 'o'; void *
0x180003bcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bd4  mov     rcx, [rbp+188h]; this
0x180003bdb  lea     r8, aWil; "wil"
0x180003be2  mov     r9d, esi; char *
0x180003be5  mov     edx, 12Eh; void *
0x180003bea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bef  test    rdi, rdi
0x180003bf2  jz      short loc_180003C05
0x180003bf4  mov     rcx, rdi; hMutex
0x180003bf7  call    cs:__imp_ReleaseMutex
0x180003bfd  test    eax, eax
0x180003bff  jz      loc_180003E0C
0x180003c05  mov     rcx, rbx; hObject
0x180003c08  call    cs:__imp_CloseHandle
0x180003c0e  test    eax, eax
0x180003c10  jz      loc_180003E1E
0x180003c16  mov     eax, esi
0x180003c18  jmp     loc_180003DC7
0x180003c1d  mov     rax, [rsp+280h+hObject]
0x180003c22  lea     rcx, ds:0[rax*4]
0x180003c2a  test    rcx, rcx
0x180003c2d  jz      short loc_180003C3D
0x180003c2f  mov     [r15], rcx
0x180003c32  mov     eax, [rcx]
0x180003c34  inc     eax
0x180003c36  mov     [rcx], eax
0x180003c38  jmp     loc_180003D9D
0x180003c3d  mov     rdx, r14; dwBytes
0x180003c40  mov     qword ptr [r15], 0
0x180003c47  mov     ecx, 8; dwFlags
0x180003c4c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c51  mov     rsi, rax
0x180003c54  test    rax, rax
0x180003c57  jnz     short loc_180003C7F
0x180003c59  mov     rcx, [rbp+188h]; this
0x180003c60  lea     r8, aWil; "wil"
0x180003c67  mov     r14d, 8007000Eh
0x180003c6d  mov     edx, 14Bh; void *
0x180003c72  mov     r9d, r14d; char *
0x180003c75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c7a  jmp     loc_180003D12
0x180003c7f  xorps   xmm0, xmm0
0x180003c82  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003c88  test    sil, 3
0x180003c8c  jnz     loc_180003E30
0x180003c92  mov     r9, rsi
0x180003c95  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003c9a  shr     r9, 2; unsigned __int64
0x180003c9e  lea     rcx, [rsp+280h+hObject]; this
0x180003ca3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003ca8  mov     r14d, eax
0x180003cab  test    eax, eax
0x180003cad  jns     loc_180003D59
0x180003cb3  mov     rcx, [rbp+188h]; this
0x180003cba  lea     r8, aWil; "wil"
0x180003cc1  mov     r9d, eax; char *
0x180003cc4  mov     edx, 14Eh; void *
0x180003cc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cce  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003cd3  test    rcx, rcx
0x180003cd6  jz      short loc_180003CE6
0x180003cd8  call    cs:__imp_CloseHandle
0x180003cde  test    eax, eax
0x180003ce0  jz      loc_180003E36
0x180003ce6  mov     rcx, [rsp+280h+hObject]; hObject
0x180003ceb  test    rcx, rcx
0x180003cee  jz      short loc_180003CFE
0x180003cf0  call    cs:__imp_CloseHandle
0x180003cf6  test    eax, eax
0x180003cf8  jz      loc_180003E48
0x180003cfe  call    cs:__imp_GetProcessHeap
0x180003d04  mov     r8, rsi; lpMem
0x180003d07  xor     edx, edx; dwFlags
0x180003d09  mov     rcx, rax; hHeap
0x180003d0c  call    cs:__imp_HeapFree
0x180003d12  mov     rcx, [rbp+188h]; this
0x180003d19  lea     r8, aWil; "wil"
0x180003d20  mov     r9d, r14d; char *
0x180003d23  mov     edx, 137h; void *
0x180003d28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d2d  test    rdi, rdi
0x180003d30  jz      short loc_180003D43
0x180003d32  mov     rcx, rdi; hMutex
0x180003d35  call    cs:__imp_ReleaseMutex
0x180003d3b  test    eax, eax
0x180003d3d  jz      loc_180003E5A
0x180003d43  mov     rcx, rbx; hObject
0x180003d46  call    cs:__imp_CloseHandle
0x180003d4c  test    eax, eax
0x180003d4e  jz      loc_180003E6C
0x180003d54  mov     eax, r14d
0x180003d57  jmp     short loc_180003DC7
0x180003d59  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003d5e  xor     edx, edx; Val
0x180003d60  mov     dword ptr [rsi], 1
0x180003d66  lea     rcx, [rsi+22h]; void *
0x180003d6a  mov     [rsi+8], rbx
0x180003d6e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003d73  lea     r8d, [rdx+56h]; Size
0x180003d77  call    memset_0
0x180003d7c  xor     edx, edx; Val
0x180003d7e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003d84  lea     rcx, [rsi+28h]; void *
0x180003d88  mov     dword ptr [rsi+24h], 1
0x180003d8f  lea     r8d, [rdx+50h]; Size
0x180003d93  call    memset_0
0x180003d98  xor     ebx, ebx
0x180003d9a  mov     [r15], rsi
0x180003d9d  test    rdi, rdi
0x180003da0  jz      short loc_180003DB3
0x180003da2  mov     rcx, rdi; hMutex
0x180003da5  call    cs:__imp_ReleaseMutex
0x180003dab  test    eax, eax
0x180003dad  jz      loc_180003E7E
0x180003db3  test    rbx, rbx
0x180003db6  jz      short loc_180003DC5
0x180003db8  mov     rcx, rbx; hObject
0x180003dbb  call    cs:__imp_CloseHandle
0x180003dc1  test    eax, eax
0x180003dc3  jz      short loc_180003DED
0x180003dc5  xor     eax, eax
0x180003dc7  mov     rcx, [rbp+180h+var_30]
0x180003dce  xor     rcx, rsp; StackCookie
0x180003dd1  call    __security_check_cookie
0x180003dd6  mov     rbx, [rsp+280h+arg_10]
0x180003dde  add     rsp, 260h
0x180003de5  pop     r15
0x180003de7  pop     r14
0x180003de9  pop     rdi
0x180003dea  pop     rsi
0x180003deb  pop     rbp
0x180003dec  retn
0x180003ded  mov     rcx, [rbp+188h]; this
0x180003df4  mov     edx, 0A0Bh; void *
0x180003df9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dff  mov     rcx, [rbp+188h]; this
0x180003e06  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003e0c  mov     rcx, [rbp+188h]; this
0x180003e13  mov     edx, 0A15h; void *
0x180003e18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e1e  mov     rcx, [rbp+188h]; this
0x180003e25  mov     edx, 0A0Bh; void *
0x180003e2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e30  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e36  mov     rcx, [rbp+188h]; this
0x180003e3d  mov     edx, 0A0Bh; void *
0x180003e42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e48  mov     rcx, [rbp+188h]; this
0x180003e4f  mov     edx, 0A0Bh; void *
0x180003e54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e5a  mov     rcx, [rbp+188h]; this
0x180003e61  mov     edx, 0A15h; void *
0x180003e66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e6c  mov     rcx, [rbp+188h]; this
0x180003e73  mov     edx, 0A0Bh; void *
0x180003e78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e7e  mov     rcx, [rbp+188h]; this
0x180003e85  mov     edx, 0A15h; void *
0x180003e8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
