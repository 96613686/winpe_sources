# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400039d8`
- end: `0x140003da0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400051a0`

## callees

- `0x140001570`
- `0x1400020d0`
- `0x1400039d8`
- `0x1400041a0`
- `0x140004614`
- `0x140004f38`
- `0x140005838`
- `0x140006ce4`
- `0x14000784c`
- `0x140007bac`
- `0x1400083ac`
- `0x1400083bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003a50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003a50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003a71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003a71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003b07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003cb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003b07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003cb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003b18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003be8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003b18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003be8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ccb`

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
0x1400039d8  mov     [rsp-8+arg_10], rbx
0x1400039dd  push    rbp
0x1400039de  push    rsi
0x1400039df  push    rdi
0x1400039e0  push    r14
0x1400039e2  push    r15
0x1400039e4  lea     rbp, [rsp-160h]
0x1400039ec  sub     rsp, 260h
0x1400039f3  mov     rax, cs:__security_cookie
0x1400039fa  xor     rax, rsp
0x1400039fd  mov     [rbp+180h+var_30], rax
0x140003a04  mov     r15, rdx
0x140003a07  mov     qword ptr [rdx], 0
0x140003a0e  mov     rbx, rcx
0x140003a11  call    cs:__imp_GetCurrentProcessId
0x140003a17  mov     r14d, 78h ; 'x'
0x140003a1d  mov     [rsp+280h+var_258], rbx
0x140003a22  mov     r9d, eax
0x140003a25  mov     [rsp+280h+var_260], r14d; int
0x140003a2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003a31  mov     edx, 104h; unsigned __int64
0x140003a36  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003a3b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003a40  mov     r9d, 1F0001h; dwDesiredAccess
0x140003a46  lea     rdx, [rsp+280h+Name]; lpName
0x140003a4b  xor     r8d, r8d; dwFlags
0x140003a4e  xor     ecx, ecx; lpMutexAttributes
0x140003a50  call    cs:__imp_CreateMutexExW
0x140003a56  mov     rbx, rax
0x140003a59  test    rax, rax
0x140003a5c  jnz     short loc_140003A68
0x140003a5e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003a63  jmp     loc_140003CD7
0x140003a68  xor     r8d, r8d; bAlertable
0x140003a6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003a6e  mov     rcx, rbx; hHandle
0x140003a71  call    cs:__imp_WaitForSingleObjectEx
0x140003a77  cmp     eax, 102h
0x140003a7c  jz      short loc_140003A8E
0x140003a7e  test    eax, 0FFFFFF7Fh
0x140003a83  jnz     loc_140003D0F
0x140003a89  mov     rdi, rbx
0x140003a8c  jmp     short loc_140003A90
0x140003a8e  xor     edi, edi
0x140003a90  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003a95  mov     [rsp+280h+hObject], 0
0x140003a9e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003aa3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003aa8  mov     esi, eax
0x140003aaa  test    eax, eax
0x140003aac  jns     short loc_140003B2D
0x140003aae  mov     rcx, [rbp+188h]; this
0x140003ab5  lea     r8, aWil; "wil"
0x140003abc  mov     r9d, eax; char *
0x140003abf  mov     edx, 66h ; 'f'; void *
0x140003ac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ac9  mov     rcx, [rbp+188h]; this
0x140003ad0  lea     r8, aWil; "wil"
0x140003ad7  mov     r9d, esi; char *
0x140003ada  mov     edx, 6Fh ; 'o'; void *
0x140003adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ae4  mov     rcx, [rbp+188h]; this
0x140003aeb  lea     r8, aWil; "wil"
0x140003af2  mov     r9d, esi; char *
0x140003af5  mov     edx, 12Eh; void *
0x140003afa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003aff  test    rdi, rdi
0x140003b02  jz      short loc_140003B15
0x140003b04  mov     rcx, rdi; hMutex
0x140003b07  call    cs:__imp_ReleaseMutex
0x140003b0d  test    eax, eax
0x140003b0f  jz      loc_140003D1C
0x140003b15  mov     rcx, rbx; hObject
0x140003b18  call    cs:__imp_CloseHandle
0x140003b1e  test    eax, eax
0x140003b20  jz      loc_140003D2E
0x140003b26  mov     eax, esi
0x140003b28  jmp     loc_140003CD7
0x140003b2d  mov     rax, [rsp+280h+hObject]
0x140003b32  lea     rcx, ds:0[rax*4]
0x140003b3a  test    rcx, rcx
0x140003b3d  jz      short loc_140003B4D
0x140003b3f  mov     [r15], rcx
0x140003b42  mov     eax, [rcx]
0x140003b44  inc     eax
0x140003b46  mov     [rcx], eax
0x140003b48  jmp     loc_140003CAD
0x140003b4d  mov     rdx, r14; dwBytes
0x140003b50  mov     qword ptr [r15], 0
0x140003b57  mov     ecx, 8; dwFlags
0x140003b5c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003b61  mov     rsi, rax
0x140003b64  test    rax, rax
0x140003b67  jnz     short loc_140003B8F
0x140003b69  mov     rcx, [rbp+188h]; this
0x140003b70  lea     r8, aWil; "wil"
0x140003b77  mov     r14d, 8007000Eh
0x140003b7d  mov     edx, 14Bh; void *
0x140003b82  mov     r9d, r14d; char *
0x140003b85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b8a  jmp     loc_140003C22
0x140003b8f  xorps   xmm0, xmm0
0x140003b92  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003b98  test    sil, 3
0x140003b9c  jnz     loc_140003D40
0x140003ba2  mov     r9, rsi
0x140003ba5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003baa  shr     r9, 2; unsigned __int64
0x140003bae  lea     rcx, [rsp+280h+hObject]; this
0x140003bb3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003bb8  mov     r14d, eax
0x140003bbb  test    eax, eax
0x140003bbd  jns     loc_140003C69
0x140003bc3  mov     rcx, [rbp+188h]; this
0x140003bca  lea     r8, aWil; "wil"
0x140003bd1  mov     r9d, eax; char *
0x140003bd4  mov     edx, 14Eh; void *
0x140003bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003bde  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003be3  test    rcx, rcx
0x140003be6  jz      short loc_140003BF6
0x140003be8  call    cs:__imp_CloseHandle
0x140003bee  test    eax, eax
0x140003bf0  jz      loc_140003D46
0x140003bf6  mov     rcx, [rsp+280h+hObject]; hObject
0x140003bfb  test    rcx, rcx
0x140003bfe  jz      short loc_140003C0E
0x140003c00  call    cs:__imp_CloseHandle
0x140003c06  test    eax, eax
0x140003c08  jz      loc_140003D58
0x140003c0e  call    cs:__imp_GetProcessHeap
0x140003c14  mov     r8, rsi; lpMem
0x140003c17  xor     edx, edx; dwFlags
0x140003c19  mov     rcx, rax; hHeap
0x140003c1c  call    cs:__imp_HeapFree
0x140003c22  mov     rcx, [rbp+188h]; this
0x140003c29  lea     r8, aWil; "wil"
0x140003c30  mov     r9d, r14d; char *
0x140003c33  mov     edx, 137h; void *
0x140003c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c3d  test    rdi, rdi
0x140003c40  jz      short loc_140003C53
0x140003c42  mov     rcx, rdi; hMutex
0x140003c45  call    cs:__imp_ReleaseMutex
0x140003c4b  test    eax, eax
0x140003c4d  jz      loc_140003D6A
0x140003c53  mov     rcx, rbx; hObject
0x140003c56  call    cs:__imp_CloseHandle
0x140003c5c  test    eax, eax
0x140003c5e  jz      loc_140003D7C
0x140003c64  mov     eax, r14d
0x140003c67  jmp     short loc_140003CD7
0x140003c69  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003c6e  xor     edx, edx; Val
0x140003c70  mov     dword ptr [rsi], 1
0x140003c76  lea     rcx, [rsi+22h]; void *
0x140003c7a  mov     [rsi+8], rbx
0x140003c7e  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003c83  lea     r8d, [rdx+56h]; Size
0x140003c87  call    memset_0
0x140003c8c  xor     edx, edx; Val
0x140003c8e  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003c94  lea     rcx, [rsi+28h]; void *
0x140003c98  mov     dword ptr [rsi+24h], 1
0x140003c9f  lea     r8d, [rdx+50h]; Size
0x140003ca3  call    memset_0
0x140003ca8  xor     ebx, ebx
0x140003caa  mov     [r15], rsi
0x140003cad  test    rdi, rdi
0x140003cb0  jz      short loc_140003CC3
0x140003cb2  mov     rcx, rdi; hMutex
0x140003cb5  call    cs:__imp_ReleaseMutex
0x140003cbb  test    eax, eax
0x140003cbd  jz      loc_140003D8E
0x140003cc3  test    rbx, rbx
0x140003cc6  jz      short loc_140003CD5
0x140003cc8  mov     rcx, rbx; hObject
0x140003ccb  call    cs:__imp_CloseHandle
0x140003cd1  test    eax, eax
0x140003cd3  jz      short loc_140003CFD
0x140003cd5  xor     eax, eax
0x140003cd7  mov     rcx, [rbp+180h+var_30]
0x140003cde  xor     rcx, rsp; StackCookie
0x140003ce1  call    __security_check_cookie
0x140003ce6  mov     rbx, [rsp+280h+arg_10]
0x140003cee  add     rsp, 260h
0x140003cf5  pop     r15
0x140003cf7  pop     r14
0x140003cf9  pop     rdi
0x140003cfa  pop     rsi
0x140003cfb  pop     rbp
0x140003cfc  retn
0x140003cfd  mov     rcx, [rbp+188h]; this
0x140003d04  mov     edx, 0A0Bh; void *
0x140003d09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d0f  mov     rcx, [rbp+188h]; this
0x140003d16  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003d1c  mov     rcx, [rbp+188h]; this
0x140003d23  mov     edx, 0A15h; void *
0x140003d28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d2e  mov     rcx, [rbp+188h]; this
0x140003d35  mov     edx, 0A0Bh; void *
0x140003d3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d40  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003d46  mov     rcx, [rbp+188h]; this
0x140003d4d  mov     edx, 0A0Bh; void *
0x140003d52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d58  mov     rcx, [rbp+188h]; this
0x140003d5f  mov     edx, 0A0Bh; void *
0x140003d64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d6a  mov     rcx, [rbp+188h]; this
0x140003d71  mov     edx, 0A15h; void *
0x140003d76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d7c  mov     rcx, [rbp+188h]; this
0x140003d83  mov     edx, 0A0Bh; void *
0x140003d88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d8e  mov     rcx, [rbp+188h]; this
0x140003d95  mov     edx, 0A15h; void *
0x140003d9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
