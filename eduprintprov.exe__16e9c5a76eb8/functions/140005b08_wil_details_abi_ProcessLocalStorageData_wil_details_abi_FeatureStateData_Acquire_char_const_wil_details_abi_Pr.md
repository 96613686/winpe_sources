# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140005b08`
- end: `0x140005ef9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140006930`

## callees

- `0x140002600`
- `0x140003168`
- `0x140004a98`
- `0x140005b08`
- `0x140006434`
- `0x140006ac0`
- `0x1400073e8`
- `0x1400083f8`
- `0x140009724`
- `0x14000a30c`
- `0x14000a6cc`
- `0x14000af58`
- `0x14000af68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140005ba0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140005ba0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140005ddb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140005ddb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005c36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005d72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005e0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005c36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005d72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005e0e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140005b7f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140005b7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005b41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005b41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005d83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005e24`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x140005b08  mov     [rsp-8+arg_10], rbx
0x140005b0d  push    rbp
0x140005b0e  push    rsi
0x140005b0f  push    rdi
0x140005b10  push    r14
0x140005b12  push    r15
0x140005b14  lea     rbp, [rsp-160h]
0x140005b1c  sub     rsp, 260h
0x140005b23  mov     rax, cs:__security_cookie
0x140005b2a  xor     rax, rsp
0x140005b2d  mov     [rbp+180h+var_30], rax
0x140005b34  mov     r15, rdx
0x140005b37  mov     qword ptr [rdx], 0
0x140005b3e  mov     rbx, rcx
0x140005b41  call    cs:__imp_GetCurrentProcessId
0x140005b47  mov     r14d, 130h
0x140005b4d  mov     [rsp+280h+var_258], rbx
0x140005b52  mov     r9d, eax
0x140005b55  mov     [rsp+280h+var_260], r14d; int
0x140005b5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005b61  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005b66  lea     edx, [r14-2Ch]; unsigned __int64
0x140005b6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005b6f  mov     r9d, 1F0001h; dwDesiredAccess
0x140005b75  lea     rdx, [rsp+280h+Name]; lpName
0x140005b7a  xor     r8d, r8d; dwFlags
0x140005b7d  xor     ecx, ecx; lpMutexAttributes
0x140005b7f  call    cs:__imp_CreateMutexExW
0x140005b85  mov     rbx, rax
0x140005b88  test    rax, rax
0x140005b8b  jnz     short loc_140005B97
0x140005b8d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005b92  jmp     loc_140005E30
0x140005b97  xor     r8d, r8d; bAlertable
0x140005b9a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005b9d  mov     rcx, rbx; hHandle
0x140005ba0  call    cs:__imp_WaitForSingleObjectEx
0x140005ba6  cmp     eax, 102h
0x140005bab  jz      short loc_140005BBD
0x140005bad  test    eax, 0FFFFFF7Fh
0x140005bb2  jnz     loc_140005E7A
0x140005bb8  mov     rdi, rbx
0x140005bbb  jmp     short loc_140005BBF
0x140005bbd  xor     edi, edi
0x140005bbf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140005bc4  mov     [rsp+280h+hObject], 0
0x140005bcd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005bd2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140005bd7  mov     esi, eax
0x140005bd9  test    eax, eax
0x140005bdb  jns     short loc_140005C5C
0x140005bdd  mov     rcx, [rbp+188h]; this
0x140005be4  lea     r8, aWil; "wil"
0x140005beb  mov     r9d, eax; char *
0x140005bee  mov     edx, 66h ; 'f'; void *
0x140005bf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005bf8  mov     rcx, [rbp+188h]; this
0x140005bff  lea     r8, aWil; "wil"
0x140005c06  mov     r9d, esi; char *
0x140005c09  mov     edx, 6Fh ; 'o'; void *
0x140005c0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005c13  mov     rcx, [rbp+188h]; this
0x140005c1a  lea     r8, aWil; "wil"
0x140005c21  mov     r9d, esi; char *
0x140005c24  mov     edx, 12Eh; void *
0x140005c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005c2e  test    rdi, rdi
0x140005c31  jz      short loc_140005C44
0x140005c33  mov     rcx, rdi; hMutex
0x140005c36  call    cs:__imp_ReleaseMutex
0x140005c3c  test    eax, eax
0x140005c3e  jz      loc_140005E87
0x140005c44  mov     rcx, rbx; hObject
0x140005c47  call    cs:__imp_CloseHandle
0x140005c4d  test    eax, eax
0x140005c4f  jz      loc_140005E99
0x140005c55  mov     eax, esi
0x140005c57  jmp     loc_140005E30
0x140005c5c  mov     rax, [rsp+280h+hObject]
0x140005c61  lea     rcx, ds:0[rax*4]
0x140005c69  test    rcx, rcx
0x140005c6c  jz      short loc_140005C7C
0x140005c6e  mov     [r15], rcx
0x140005c71  mov     eax, [rcx]
0x140005c73  inc     eax
0x140005c75  mov     [rcx], eax
0x140005c77  jmp     loc_140005E06
0x140005c7c  mov     rdx, r14; dwBytes
0x140005c7f  mov     qword ptr [r15], 0
0x140005c86  mov     ecx, 8; dwFlags
0x140005c8b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005c90  mov     r14, rax
0x140005c93  test    rax, rax
0x140005c96  jnz     short loc_140005CBD
0x140005c98  mov     rcx, [rbp+188h]; this
0x140005c9f  lea     r8, aWil; "wil"
0x140005ca6  mov     esi, 8007000Eh
0x140005cab  mov     edx, 14Bh; void *
0x140005cb0  mov     r9d, esi; char *
0x140005cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005cb8  jmp     loc_140005D4F
0x140005cbd  xorps   xmm0, xmm0
0x140005cc0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140005cc6  test    r14b, 3
0x140005cca  jnz     loc_140005EAB
0x140005cd0  mov     r9, r14
0x140005cd3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140005cd8  shr     r9, 2; unsigned __int64
0x140005cdc  lea     rcx, [rsp+280h+hObject]; this
0x140005ce1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140005ce6  mov     esi, eax
0x140005ce8  test    eax, eax
0x140005cea  jns     loc_140005D96
0x140005cf0  mov     rcx, [rbp+188h]; this
0x140005cf7  lea     r8, aWil; "wil"
0x140005cfe  mov     r9d, eax; char *
0x140005d01  mov     edx, 14Eh; void *
0x140005d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005d0b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140005d10  test    rcx, rcx
0x140005d13  jz      short loc_140005D23
0x140005d15  call    cs:__imp_CloseHandle
0x140005d1b  test    eax, eax
0x140005d1d  jz      loc_140005EB1
0x140005d23  mov     rcx, [rsp+280h+hObject]; hObject
0x140005d28  test    rcx, rcx
0x140005d2b  jz      short loc_140005D3B
0x140005d2d  call    cs:__imp_CloseHandle
0x140005d33  test    eax, eax
0x140005d35  jz      loc_140005EC3
0x140005d3b  call    cs:__imp_GetProcessHeap
0x140005d41  mov     r8, r14; lpMem
0x140005d44  xor     edx, edx; dwFlags
0x140005d46  mov     rcx, rax; hHeap
0x140005d49  call    cs:__imp_HeapFree
0x140005d4f  mov     rcx, [rbp+188h]; this
0x140005d56  lea     r8, aWil; "wil"
0x140005d5d  mov     r9d, esi; char *
0x140005d60  mov     edx, 137h; void *
0x140005d65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005d6a  test    rdi, rdi
0x140005d6d  jz      short loc_140005D80
0x140005d6f  mov     rcx, rdi; hMutex
0x140005d72  call    cs:__imp_ReleaseMutex
0x140005d78  test    eax, eax
0x140005d7a  jz      loc_140005ED5
0x140005d80  mov     rcx, rbx; hObject
0x140005d83  call    cs:__imp_CloseHandle
0x140005d89  test    eax, eax
0x140005d8b  jz      loc_140005E68
0x140005d91  jmp     loc_140005C55
0x140005d96  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140005d9b  lea     rcx, [r14+28h]; void *
0x140005d9f  mov     dword ptr [r14], 1
0x140005da6  xor     edx, edx; Val
0x140005da8  mov     [r14+8], rbx
0x140005dac  mov     r8d, 108h; Size
0x140005db2  movdqu  xmmword ptr [r14+10h], xmm0
0x140005db8  call    memset_0
0x140005dbd  xor     eax, eax
0x140005dbf  lea     rcx, [r14+28h]; this
0x140005dc3  mov     [r14+20h], rax
0x140005dc7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005dcc  lea     rbx, [r14+0E8h]
0x140005dd3  xor     r8d, r8d; Flags
0x140005dd6  mov     rcx, rbx; lpCriticalSection
0x140005dd9  xor     edx, edx; dwSpinCount
0x140005ddb  call    cs:__imp_InitializeCriticalSectionEx
0x140005de1  mov     qword ptr [rbx+28h], 0
0x140005de9  mov     qword ptr [rbx+30h], 0
0x140005df1  mov     qword ptr [rbx+38h], 0
0x140005df9  mov     qword ptr [rbx+40h], 0
0x140005e01  xor     ebx, ebx
0x140005e03  mov     [r15], r14
0x140005e06  test    rdi, rdi
0x140005e09  jz      short loc_140005E1C
0x140005e0b  mov     rcx, rdi; hMutex
0x140005e0e  call    cs:__imp_ReleaseMutex
0x140005e14  test    eax, eax
0x140005e16  jz      loc_140005EE7
0x140005e1c  test    rbx, rbx
0x140005e1f  jz      short loc_140005E2E
0x140005e21  mov     rcx, rbx; hObject
0x140005e24  call    cs:__imp_CloseHandle
0x140005e2a  test    eax, eax
0x140005e2c  jz      short loc_140005E56
0x140005e2e  xor     eax, eax
0x140005e30  mov     rcx, [rbp+180h+var_30]
0x140005e37  xor     rcx, rsp; StackCookie
0x140005e3a  call    __security_check_cookie
0x140005e3f  mov     rbx, [rsp+280h+arg_10]
0x140005e47  add     rsp, 260h
0x140005e4e  pop     r15
0x140005e50  pop     r14
0x140005e52  pop     rdi
0x140005e53  pop     rsi
0x140005e54  pop     rbp
0x140005e55  retn
0x140005e56  mov     rcx, [rbp+188h]; this
0x140005e5d  mov     edx, 0A0Bh; void *
0x140005e62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005e68  mov     rcx, [rbp+188h]; this
0x140005e6f  mov     edx, 0A0Bh; void *
0x140005e74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005e7a  mov     rcx, [rbp+188h]; this
0x140005e81  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140005e87  mov     rcx, [rbp+188h]; this
0x140005e8e  mov     edx, 0A15h; void *
0x140005e93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005e99  mov     rcx, [rbp+188h]; this
0x140005ea0  mov     edx, 0A0Bh; void *
0x140005ea5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005eab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005eb1  mov     rcx, [rbp+188h]; this
0x140005eb8  mov     edx, 0A0Bh; void *
0x140005ebd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005ec3  mov     rcx, [rbp+188h]; this
0x140005eca  mov     edx, 0A0Bh; void *
0x140005ecf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005ed5  mov     rcx, [rbp+188h]; this
0x140005edc  mov     edx, 0A15h; void *
0x140005ee1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005ee7  mov     rcx, [rbp+188h]; this
0x140005eee  mov     edx, 0A15h; void *
0x140005ef3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
