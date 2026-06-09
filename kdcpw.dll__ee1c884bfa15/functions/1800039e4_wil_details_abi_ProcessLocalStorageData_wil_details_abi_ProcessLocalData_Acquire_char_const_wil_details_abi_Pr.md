# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800039e4`
- end: `0x180003d82`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800054bc`

## callees

- `0x180001630`
- `0x180001f88`
- `0x1800039e4`
- `0x180004158`
- `0x1800047b8`
- `0x180005258`
- `0x1800061a8`
- `0x180007bd4`
- `0x18000809c`
- `0x1800085f8`
- `0x180008eac`
- `0x180008ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003a5c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003a5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003a7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003afe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003afe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cad`

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
0x1800039e4  mov     [rsp-8+arg_10], rbx
0x1800039e9  push    rbp
0x1800039ea  push    rsi
0x1800039eb  push    rdi
0x1800039ec  push    r14
0x1800039ee  push    r15
0x1800039f0  lea     rbp, [rsp-160h]
0x1800039f8  sub     rsp, 260h
0x1800039ff  mov     rax, cs:__security_cookie
0x180003a06  xor     rax, rsp
0x180003a09  mov     [rbp+180h+var_30], rax
0x180003a10  mov     r15, rdx
0x180003a13  mov     qword ptr [rdx], 0
0x180003a1a  mov     rbx, rcx
0x180003a1d  call    cs:__imp_GetCurrentProcessId
0x180003a23  mov     r14d, 78h ; 'x'
0x180003a29  mov     [rsp+280h+var_258], rbx
0x180003a2e  mov     r9d, eax
0x180003a31  mov     [rsp+280h+var_260], r14d; int
0x180003a36  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003a3d  mov     edx, 104h; unsigned __int64
0x180003a42  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003a47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003a4c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003a52  lea     rdx, [rsp+280h+Name]; lpName
0x180003a57  xor     r8d, r8d; dwFlags
0x180003a5a  xor     ecx, ecx; lpMutexAttributes
0x180003a5c  call    cs:__imp_CreateMutexExW
0x180003a62  mov     rbx, rax
0x180003a65  test    rax, rax
0x180003a68  jnz     short loc_180003A74
0x180003a6a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a6f  jmp     loc_180003CB9
0x180003a74  xor     r8d, r8d; bAlertable
0x180003a77  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003a7a  mov     rcx, rbx; hHandle
0x180003a7d  call    cs:__imp_WaitForSingleObjectEx
0x180003a83  cmp     eax, 102h
0x180003a88  jz      short loc_180003A9A
0x180003a8a  test    eax, 0FFFFFF7Fh
0x180003a8f  jnz     loc_180003CF1
0x180003a95  mov     rdi, rbx
0x180003a98  jmp     short loc_180003A9C
0x180003a9a  xor     edi, edi
0x180003a9c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003aa1  mov     [rsp+280h+hObject], 0
0x180003aaa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003aaf  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ab4  mov     esi, eax
0x180003ab6  test    eax, eax
0x180003ab8  jns     short loc_180003B24
0x180003aba  mov     rcx, [rbp+188h]; this
0x180003ac1  mov     r9d, eax; char *
0x180003ac4  mov     edx, 66h ; 'f'; void *
0x180003ac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ace  mov     rcx, [rbp+188h]; this
0x180003ad5  mov     r9d, esi; char *
0x180003ad8  mov     edx, 6Fh ; 'o'; void *
0x180003add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ae2  mov     rcx, [rbp+188h]; this
0x180003ae9  mov     r9d, esi; char *
0x180003aec  mov     edx, 12Eh; void *
0x180003af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003af6  test    rdi, rdi
0x180003af9  jz      short loc_180003B0C
0x180003afb  mov     rcx, rdi; hMutex
0x180003afe  call    cs:__imp_ReleaseMutex
0x180003b04  test    eax, eax
0x180003b06  jz      loc_180003CFE
0x180003b0c  mov     rcx, rbx; hObject
0x180003b0f  call    cs:__imp_CloseHandle
0x180003b15  test    eax, eax
0x180003b17  jz      loc_180003D10
0x180003b1d  mov     eax, esi
0x180003b1f  jmp     loc_180003CB9
0x180003b24  mov     rax, [rsp+280h+hObject]
0x180003b29  lea     rcx, ds:0[rax*4]
0x180003b31  test    rcx, rcx
0x180003b34  jz      short loc_180003B44
0x180003b36  mov     [r15], rcx
0x180003b39  mov     eax, [rcx]
0x180003b3b  inc     eax
0x180003b3d  mov     [rcx], eax
0x180003b3f  jmp     loc_180003C8F
0x180003b44  mov     rdx, r14; dwBytes
0x180003b47  mov     qword ptr [r15], 0
0x180003b4e  mov     ecx, 8; dwFlags
0x180003b53  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003b58  mov     rsi, rax
0x180003b5b  test    rax, rax
0x180003b5e  jnz     short loc_180003B7F
0x180003b60  mov     rcx, [rbp+188h]; this
0x180003b67  mov     r14d, 8007000Eh
0x180003b6d  mov     r9d, r14d; char *
0x180003b70  mov     edx, 14Bh; void *
0x180003b75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b7a  jmp     loc_180003C0B
0x180003b7f  xorps   xmm0, xmm0
0x180003b82  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003b88  test    sil, 3
0x180003b8c  jnz     loc_180003D22
0x180003b92  mov     r9, rsi
0x180003b95  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003b9a  shr     r9, 2; unsigned __int64
0x180003b9e  lea     rcx, [rsp+280h+hObject]; this
0x180003ba3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003ba8  mov     r14d, eax
0x180003bab  test    eax, eax
0x180003bad  jns     loc_180003C4B
0x180003bb3  mov     rcx, [rbp+188h]; this
0x180003bba  mov     r9d, eax; char *
0x180003bbd  mov     edx, 14Eh; void *
0x180003bc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bc7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003bcc  test    rcx, rcx
0x180003bcf  jz      short loc_180003BDF
0x180003bd1  call    cs:__imp_CloseHandle
0x180003bd7  test    eax, eax
0x180003bd9  jz      loc_180003D28
0x180003bdf  mov     rcx, [rsp+280h+hObject]; hObject
0x180003be4  test    rcx, rcx
0x180003be7  jz      short loc_180003BF7
0x180003be9  call    cs:__imp_CloseHandle
0x180003bef  test    eax, eax
0x180003bf1  jz      loc_180003D3A
0x180003bf7  call    cs:__imp_GetProcessHeap
0x180003bfd  mov     r8, rsi; lpMem
0x180003c00  xor     edx, edx; dwFlags
0x180003c02  mov     rcx, rax; hHeap
0x180003c05  call    cs:__imp_HeapFree
0x180003c0b  mov     rcx, [rbp+188h]; this
0x180003c12  mov     r9d, r14d; char *
0x180003c15  mov     edx, 137h; void *
0x180003c1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c1f  test    rdi, rdi
0x180003c22  jz      short loc_180003C35
0x180003c24  mov     rcx, rdi; hMutex
0x180003c27  call    cs:__imp_ReleaseMutex
0x180003c2d  test    eax, eax
0x180003c2f  jz      loc_180003D4C
0x180003c35  mov     rcx, rbx; hObject
0x180003c38  call    cs:__imp_CloseHandle
0x180003c3e  test    eax, eax
0x180003c40  jz      loc_180003D5E
0x180003c46  mov     eax, r14d
0x180003c49  jmp     short loc_180003CB9
0x180003c4b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003c50  xor     edx, edx; Val
0x180003c52  mov     dword ptr [rsi], 1
0x180003c58  lea     rcx, [rsi+22h]; void *
0x180003c5c  mov     [rsi+8], rbx
0x180003c60  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003c65  lea     r8d, [rdx+56h]; Size
0x180003c69  call    memset_0
0x180003c6e  xor     edx, edx; Val
0x180003c70  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003c76  lea     rcx, [rsi+28h]; void *
0x180003c7a  mov     dword ptr [rsi+24h], 1
0x180003c81  lea     r8d, [rdx+50h]; Size
0x180003c85  call    memset_0
0x180003c8a  xor     ebx, ebx
0x180003c8c  mov     [r15], rsi
0x180003c8f  test    rdi, rdi
0x180003c92  jz      short loc_180003CA5
0x180003c94  mov     rcx, rdi; hMutex
0x180003c97  call    cs:__imp_ReleaseMutex
0x180003c9d  test    eax, eax
0x180003c9f  jz      loc_180003D70
0x180003ca5  test    rbx, rbx
0x180003ca8  jz      short loc_180003CB7
0x180003caa  mov     rcx, rbx; hObject
0x180003cad  call    cs:__imp_CloseHandle
0x180003cb3  test    eax, eax
0x180003cb5  jz      short loc_180003CDF
0x180003cb7  xor     eax, eax
0x180003cb9  mov     rcx, [rbp+180h+var_30]
0x180003cc0  xor     rcx, rsp; StackCookie
0x180003cc3  call    __security_check_cookie
0x180003cc8  mov     rbx, [rsp+280h+arg_10]
0x180003cd0  add     rsp, 260h
0x180003cd7  pop     r15
0x180003cd9  pop     r14
0x180003cdb  pop     rdi
0x180003cdc  pop     rsi
0x180003cdd  pop     rbp
0x180003cde  retn
0x180003cdf  mov     rcx, [rbp+188h]; this
0x180003ce6  mov     edx, 0A0Bh; void *
0x180003ceb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cf1  mov     rcx, [rbp+188h]; this
0x180003cf8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003cfe  mov     rcx, [rbp+188h]; this
0x180003d05  mov     edx, 0A15h; void *
0x180003d0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d10  mov     rcx, [rbp+188h]; this
0x180003d17  mov     edx, 0A0Bh; void *
0x180003d1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d22  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003d28  mov     rcx, [rbp+188h]; this
0x180003d2f  mov     edx, 0A0Bh; void *
0x180003d34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d3a  mov     rcx, [rbp+188h]; this
0x180003d41  mov     edx, 0A0Bh; void *
0x180003d46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d4c  mov     rcx, [rbp+188h]; this
0x180003d53  mov     edx, 0A15h; void *
0x180003d58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d5e  mov     rcx, [rbp+188h]; this
0x180003d65  mov     edx, 0A0Bh; void *
0x180003d6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d70  mov     rcx, [rbp+188h]; this
0x180003d77  mov     edx, 0A15h; void *
0x180003d7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
