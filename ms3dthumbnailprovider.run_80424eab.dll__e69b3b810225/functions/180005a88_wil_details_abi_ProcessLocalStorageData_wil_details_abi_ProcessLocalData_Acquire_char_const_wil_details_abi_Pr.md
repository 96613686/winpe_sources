# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005a88`
- end: `0x180005e26`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006c4c`

## callees

- `0x180001ef0`
- `0x180002954`
- `0x180005a88`
- `0x180005e80`
- `0x1800062d0`
- `0x180006918`
- `0x180007b60`
- `0x180008384`
- `0x180009468`
- `0x18000952c`
- `0x1800099a8`
- `0x1800099b8`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180005ba2`
- `KERNEL32!ReleaseMutex` at `0x180005ccb`
- `KERNEL32!ReleaseMutex` at `0x180005d3b`
- `KERNEL32!ReleaseMutex` at `0x180005ba2`
- `KERNEL32!ReleaseMutex` at `0x180005ccb`
- `KERNEL32!ReleaseMutex` at `0x180005d3b`
- `KERNEL32!HeapFree` at `0x180005ca9`
- `KERNEL32!HeapFree` at `0x180005ca9`
- `KERNEL32!CloseHandle` at `0x180005bb3`
- `KERNEL32!CloseHandle` at `0x180005c75`
- `KERNEL32!CloseHandle` at `0x180005c8d`
- `KERNEL32!CloseHandle` at `0x180005cdc`
- `KERNEL32!CloseHandle` at `0x180005d51`
- `KERNEL32!CloseHandle` at `0x180005bb3`
- `KERNEL32!CloseHandle` at `0x180005c75`
- `KERNEL32!CloseHandle` at `0x180005c8d`
- `KERNEL32!CloseHandle` at `0x180005cdc`
- `KERNEL32!CloseHandle` at `0x180005d51`
- `KERNEL32!CreateMutexExW` at `0x180005b00`
- `KERNEL32!CreateMutexExW` at `0x180005b00`
- `KERNEL32!GetProcessHeap` at `0x180005c9b`
- `KERNEL32!GetProcessHeap` at `0x180005c9b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180005b21`
- `KERNEL32!WaitForSingleObjectEx` at `0x180005b21`
- `KERNEL32!GetCurrentProcessId` at `0x180005ac1`
- `KERNEL32!GetCurrentProcessId` at `0x180005ac1`

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
0x180005a88  mov     [rsp-8+arg_10], rbx
0x180005a8d  push    rbp
0x180005a8e  push    rsi
0x180005a8f  push    rdi
0x180005a90  push    r14
0x180005a92  push    r15
0x180005a94  lea     rbp, [rsp-160h]
0x180005a9c  sub     rsp, 260h
0x180005aa3  mov     rax, cs:__security_cookie
0x180005aaa  xor     rax, rsp
0x180005aad  mov     [rbp+180h+var_30], rax
0x180005ab4  mov     r15, rdx
0x180005ab7  mov     qword ptr [rdx], 0
0x180005abe  mov     rbx, rcx
0x180005ac1  call    cs:__imp_GetCurrentProcessId
0x180005ac7  mov     r14d, 78h ; 'x'
0x180005acd  mov     [rsp+280h+var_258], rbx
0x180005ad2  mov     r9d, eax
0x180005ad5  mov     [rsp+280h+var_260], r14d; int
0x180005ada  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005ae1  mov     edx, 104h; unsigned __int64
0x180005ae6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005aeb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005af0  mov     r9d, 1F0001h; dwDesiredAccess
0x180005af6  lea     rdx, [rsp+280h+Name]; lpName
0x180005afb  xor     r8d, r8d; dwFlags
0x180005afe  xor     ecx, ecx; lpMutexAttributes
0x180005b00  call    cs:__imp_CreateMutexExW
0x180005b06  mov     rbx, rax
0x180005b09  test    rax, rax
0x180005b0c  jnz     short loc_180005B18
0x180005b0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b13  jmp     loc_180005D5D
0x180005b18  xor     r8d, r8d; bAlertable
0x180005b1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005b1e  mov     rcx, rbx; hHandle
0x180005b21  call    cs:__imp_WaitForSingleObjectEx
0x180005b27  cmp     eax, 102h
0x180005b2c  jz      short loc_180005B3E
0x180005b2e  test    eax, 0FFFFFF7Fh
0x180005b33  jnz     loc_180005D95
0x180005b39  mov     rdi, rbx
0x180005b3c  jmp     short loc_180005B40
0x180005b3e  xor     edi, edi
0x180005b40  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005b45  mov     [rsp+280h+hObject], 0
0x180005b4e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005b53  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005b58  mov     esi, eax
0x180005b5a  test    eax, eax
0x180005b5c  jns     short loc_180005BC8
0x180005b5e  mov     rcx, [rbp+188h]; this
0x180005b65  mov     r9d, eax; char *
0x180005b68  mov     edx, 66h ; 'f'; void *
0x180005b6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b72  mov     rcx, [rbp+188h]; this
0x180005b79  mov     r9d, esi; char *
0x180005b7c  mov     edx, 6Fh ; 'o'; void *
0x180005b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b86  mov     rcx, [rbp+188h]; this
0x180005b8d  mov     r9d, esi; char *
0x180005b90  mov     edx, 12Eh; void *
0x180005b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b9a  test    rdi, rdi
0x180005b9d  jz      short loc_180005BB0
0x180005b9f  mov     rcx, rdi; hMutex
0x180005ba2  call    cs:__imp_ReleaseMutex
0x180005ba8  test    eax, eax
0x180005baa  jz      loc_180005DA2
0x180005bb0  mov     rcx, rbx; hObject
0x180005bb3  call    cs:__imp_CloseHandle
0x180005bb9  test    eax, eax
0x180005bbb  jz      loc_180005DB4
0x180005bc1  mov     eax, esi
0x180005bc3  jmp     loc_180005D5D
0x180005bc8  mov     rax, [rsp+280h+hObject]
0x180005bcd  lea     rcx, ds:0[rax*4]
0x180005bd5  test    rcx, rcx
0x180005bd8  jz      short loc_180005BE8
0x180005bda  mov     [r15], rcx
0x180005bdd  mov     eax, [rcx]
0x180005bdf  inc     eax
0x180005be1  mov     [rcx], eax
0x180005be3  jmp     loc_180005D33
0x180005be8  mov     rdx, r14; dwBytes
0x180005beb  mov     qword ptr [r15], 0
0x180005bf2  mov     ecx, 8; dwFlags
0x180005bf7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005bfc  mov     rsi, rax
0x180005bff  test    rax, rax
0x180005c02  jnz     short loc_180005C23
0x180005c04  mov     rcx, [rbp+188h]; this
0x180005c0b  mov     r14d, 8007000Eh
0x180005c11  mov     r9d, r14d; char *
0x180005c14  mov     edx, 14Bh; void *
0x180005c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c1e  jmp     loc_180005CAF
0x180005c23  xorps   xmm0, xmm0
0x180005c26  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005c2c  test    sil, 3
0x180005c30  jnz     loc_180005DC6
0x180005c36  mov     r9, rsi
0x180005c39  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005c3e  shr     r9, 2; unsigned __int64
0x180005c42  lea     rcx, [rsp+280h+hObject]; this
0x180005c47  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005c4c  mov     r14d, eax
0x180005c4f  test    eax, eax
0x180005c51  jns     loc_180005CEF
0x180005c57  mov     rcx, [rbp+188h]; this
0x180005c5e  mov     r9d, eax; char *
0x180005c61  mov     edx, 14Eh; void *
0x180005c66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c6b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005c70  test    rcx, rcx
0x180005c73  jz      short loc_180005C83
0x180005c75  call    cs:__imp_CloseHandle
0x180005c7b  test    eax, eax
0x180005c7d  jz      loc_180005DCC
0x180005c83  mov     rcx, [rsp+280h+hObject]; hObject
0x180005c88  test    rcx, rcx
0x180005c8b  jz      short loc_180005C9B
0x180005c8d  call    cs:__imp_CloseHandle
0x180005c93  test    eax, eax
0x180005c95  jz      loc_180005DDE
0x180005c9b  call    cs:__imp_GetProcessHeap
0x180005ca1  mov     r8, rsi; lpMem
0x180005ca4  xor     edx, edx; dwFlags
0x180005ca6  mov     rcx, rax; hHeap
0x180005ca9  call    cs:__imp_HeapFree
0x180005caf  mov     rcx, [rbp+188h]; this
0x180005cb6  mov     r9d, r14d; char *
0x180005cb9  mov     edx, 137h; void *
0x180005cbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cc3  test    rdi, rdi
0x180005cc6  jz      short loc_180005CD9
0x180005cc8  mov     rcx, rdi; hMutex
0x180005ccb  call    cs:__imp_ReleaseMutex
0x180005cd1  test    eax, eax
0x180005cd3  jz      loc_180005DF0
0x180005cd9  mov     rcx, rbx; hObject
0x180005cdc  call    cs:__imp_CloseHandle
0x180005ce2  test    eax, eax
0x180005ce4  jz      loc_180005E02
0x180005cea  mov     eax, r14d
0x180005ced  jmp     short loc_180005D5D
0x180005cef  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005cf4  xor     edx, edx; Val
0x180005cf6  mov     dword ptr [rsi], 1
0x180005cfc  lea     rcx, [rsi+22h]; void *
0x180005d00  mov     [rsi+8], rbx
0x180005d04  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005d09  lea     r8d, [rdx+56h]; Size
0x180005d0d  call    memset_0
0x180005d12  xor     edx, edx; Val
0x180005d14  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005d1a  lea     rcx, [rsi+28h]; void *
0x180005d1e  mov     dword ptr [rsi+24h], 1
0x180005d25  lea     r8d, [rdx+50h]; Size
0x180005d29  call    memset_0
0x180005d2e  xor     ebx, ebx
0x180005d30  mov     [r15], rsi
0x180005d33  test    rdi, rdi
0x180005d36  jz      short loc_180005D49
0x180005d38  mov     rcx, rdi; hMutex
0x180005d3b  call    cs:__imp_ReleaseMutex
0x180005d41  test    eax, eax
0x180005d43  jz      loc_180005E14
0x180005d49  test    rbx, rbx
0x180005d4c  jz      short loc_180005D5B
0x180005d4e  mov     rcx, rbx; hObject
0x180005d51  call    cs:__imp_CloseHandle
0x180005d57  test    eax, eax
0x180005d59  jz      short loc_180005D83
0x180005d5b  xor     eax, eax
0x180005d5d  mov     rcx, [rbp+180h+var_30]
0x180005d64  xor     rcx, rsp; StackCookie
0x180005d67  call    __security_check_cookie
0x180005d6c  mov     rbx, [rsp+280h+arg_10]
0x180005d74  add     rsp, 260h
0x180005d7b  pop     r15
0x180005d7d  pop     r14
0x180005d7f  pop     rdi
0x180005d80  pop     rsi
0x180005d81  pop     rbp
0x180005d82  retn
0x180005d83  mov     rcx, [rbp+188h]; this
0x180005d8a  mov     edx, 0A0Bh; void *
0x180005d8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d95  mov     rcx, [rbp+188h]; this
0x180005d9c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005da2  mov     rcx, [rbp+188h]; this
0x180005da9  mov     edx, 0A15h; void *
0x180005dae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005db4  mov     rcx, [rbp+188h]; this
0x180005dbb  mov     edx, 0A0Bh; void *
0x180005dc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005dc6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005dcc  mov     rcx, [rbp+188h]; this
0x180005dd3  mov     edx, 0A0Bh; void *
0x180005dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005dde  mov     rcx, [rbp+188h]; this
0x180005de5  mov     edx, 0A0Bh; void *
0x180005dea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005df0  mov     rcx, [rbp+188h]; this
0x180005df7  mov     edx, 0A15h; void *
0x180005dfc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e02  mov     rcx, [rbp+188h]; this
0x180005e09  mov     edx, 0A0Bh; void *
0x180005e0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e14  mov     rcx, [rbp+188h]; this
0x180005e1b  mov     edx, 0A15h; void *
0x180005e20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
