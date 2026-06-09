# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000db78`
- end: `0x18000df69`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000e264`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18000cca4`
- `0x18000db78`
- `0x18000df70`
- `0x18000e4c0`
- `0x18000f378`
- `0x1800100d8`
- `0x180011ce4`
- `0x18001286c`
- `0x180012d7c`
- `0x1800136f8`
- `0x180013708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000de4b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000de4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000dca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000dde2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000de7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000dca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000dde2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000de7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dc10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dc10`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000dbef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000dbef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ddb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ddb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dbb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dbb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de94`

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
0x18000db78  mov     [rsp-8+arg_10], rbx
0x18000db7d  push    rbp
0x18000db7e  push    rsi
0x18000db7f  push    rdi
0x18000db80  push    r14
0x18000db82  push    r15
0x18000db84  lea     rbp, [rsp-160h]
0x18000db8c  sub     rsp, 260h
0x18000db93  mov     rax, cs:__security_cookie
0x18000db9a  xor     rax, rsp
0x18000db9d  mov     [rbp+180h+var_30], rax
0x18000dba4  mov     r15, rdx
0x18000dba7  mov     qword ptr [rdx], 0
0x18000dbae  mov     rbx, rcx
0x18000dbb1  call    cs:__imp_GetCurrentProcessId
0x18000dbb7  mov     r14d, 130h
0x18000dbbd  mov     [rsp+280h+var_258], rbx
0x18000dbc2  mov     r9d, eax
0x18000dbc5  mov     [rsp+280h+var_260], r14d; int
0x18000dbca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000dbd1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dbd6  lea     edx, [r14-2Ch]; unsigned __int64
0x18000dbda  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dbdf  mov     r9d, 1F0001h; dwDesiredAccess
0x18000dbe5  lea     rdx, [rsp+280h+Name]; lpName
0x18000dbea  xor     r8d, r8d; dwFlags
0x18000dbed  xor     ecx, ecx; lpMutexAttributes
0x18000dbef  call    cs:__imp_CreateMutexExW
0x18000dbf5  mov     rbx, rax
0x18000dbf8  test    rax, rax
0x18000dbfb  jnz     short loc_18000DC07
0x18000dbfd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000dc02  jmp     loc_18000DEA0
0x18000dc07  xor     r8d, r8d; bAlertable
0x18000dc0a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dc0d  mov     rcx, rbx; hHandle
0x18000dc10  call    cs:__imp_WaitForSingleObjectEx
0x18000dc16  cmp     eax, 102h
0x18000dc1b  jz      short loc_18000DC2D
0x18000dc1d  test    eax, 0FFFFFF7Fh
0x18000dc22  jnz     loc_18000DEEA
0x18000dc28  mov     rdi, rbx
0x18000dc2b  jmp     short loc_18000DC2F
0x18000dc2d  xor     edi, edi
0x18000dc2f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000dc34  mov     [rsp+280h+hObject], 0
0x18000dc3d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000dc42  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000dc47  mov     esi, eax
0x18000dc49  test    eax, eax
0x18000dc4b  jns     short loc_18000DCCC
0x18000dc4d  mov     rcx, [rbp+188h]; this
0x18000dc54  lea     r8, aWil; "wil"
0x18000dc5b  mov     r9d, eax; char *
0x18000dc5e  mov     edx, 66h ; 'f'; void *
0x18000dc63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc68  mov     rcx, [rbp+188h]; this
0x18000dc6f  lea     r8, aWil; "wil"
0x18000dc76  mov     r9d, esi; char *
0x18000dc79  mov     edx, 6Fh ; 'o'; void *
0x18000dc7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc83  mov     rcx, [rbp+188h]; this
0x18000dc8a  lea     r8, aWil; "wil"
0x18000dc91  mov     r9d, esi; char *
0x18000dc94  mov     edx, 12Eh; void *
0x18000dc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc9e  test    rdi, rdi
0x18000dca1  jz      short loc_18000DCB4
0x18000dca3  mov     rcx, rdi; hMutex
0x18000dca6  call    cs:__imp_ReleaseMutex
0x18000dcac  test    eax, eax
0x18000dcae  jz      loc_18000DEF7
0x18000dcb4  mov     rcx, rbx; hObject
0x18000dcb7  call    cs:__imp_CloseHandle
0x18000dcbd  test    eax, eax
0x18000dcbf  jz      loc_18000DF09
0x18000dcc5  mov     eax, esi
0x18000dcc7  jmp     loc_18000DEA0
0x18000dccc  mov     rax, [rsp+280h+hObject]
0x18000dcd1  lea     rcx, ds:0[rax*4]
0x18000dcd9  test    rcx, rcx
0x18000dcdc  jz      short loc_18000DCEC
0x18000dcde  mov     [r15], rcx
0x18000dce1  mov     eax, [rcx]
0x18000dce3  inc     eax
0x18000dce5  mov     [rcx], eax
0x18000dce7  jmp     loc_18000DE76
0x18000dcec  mov     rdx, r14; dwBytes
0x18000dcef  mov     qword ptr [r15], 0
0x18000dcf6  mov     ecx, 8; dwFlags
0x18000dcfb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000dd00  mov     r14, rax
0x18000dd03  test    rax, rax
0x18000dd06  jnz     short loc_18000DD2D
0x18000dd08  mov     rcx, [rbp+188h]; this
0x18000dd0f  lea     r8, aWil; "wil"
0x18000dd16  mov     esi, 8007000Eh
0x18000dd1b  mov     edx, 14Bh; void *
0x18000dd20  mov     r9d, esi; char *
0x18000dd23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd28  jmp     loc_18000DDBF
0x18000dd2d  xorps   xmm0, xmm0
0x18000dd30  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000dd36  test    r14b, 3
0x18000dd3a  jnz     loc_18000DF1B
0x18000dd40  mov     r9, r14
0x18000dd43  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000dd48  shr     r9, 2; unsigned __int64
0x18000dd4c  lea     rcx, [rsp+280h+hObject]; this
0x18000dd51  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000dd56  mov     esi, eax
0x18000dd58  test    eax, eax
0x18000dd5a  jns     loc_18000DE06
0x18000dd60  mov     rcx, [rbp+188h]; this
0x18000dd67  lea     r8, aWil; "wil"
0x18000dd6e  mov     r9d, eax; char *
0x18000dd71  mov     edx, 14Eh; void *
0x18000dd76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd7b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000dd80  test    rcx, rcx
0x18000dd83  jz      short loc_18000DD93
0x18000dd85  call    cs:__imp_CloseHandle
0x18000dd8b  test    eax, eax
0x18000dd8d  jz      loc_18000DF21
0x18000dd93  mov     rcx, [rsp+280h+hObject]; hObject
0x18000dd98  test    rcx, rcx
0x18000dd9b  jz      short loc_18000DDAB
0x18000dd9d  call    cs:__imp_CloseHandle
0x18000dda3  test    eax, eax
0x18000dda5  jz      loc_18000DF33
0x18000ddab  call    cs:__imp_GetProcessHeap
0x18000ddb1  mov     r8, r14; lpMem
0x18000ddb4  xor     edx, edx; dwFlags
0x18000ddb6  mov     rcx, rax; hHeap
0x18000ddb9  call    cs:__imp_HeapFree
0x18000ddbf  mov     rcx, [rbp+188h]; this
0x18000ddc6  lea     r8, aWil; "wil"
0x18000ddcd  mov     r9d, esi; char *
0x18000ddd0  mov     edx, 137h; void *
0x18000ddd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddda  test    rdi, rdi
0x18000dddd  jz      short loc_18000DDF0
0x18000dddf  mov     rcx, rdi; hMutex
0x18000dde2  call    cs:__imp_ReleaseMutex
0x18000dde8  test    eax, eax
0x18000ddea  jz      loc_18000DF45
0x18000ddf0  mov     rcx, rbx; hObject
0x18000ddf3  call    cs:__imp_CloseHandle
0x18000ddf9  test    eax, eax
0x18000ddfb  jz      loc_18000DED8
0x18000de01  jmp     loc_18000DCC5
0x18000de06  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000de0b  lea     rcx, [r14+28h]; void *
0x18000de0f  mov     dword ptr [r14], 1
0x18000de16  xor     edx, edx; Val
0x18000de18  mov     [r14+8], rbx
0x18000de1c  mov     r8d, 108h; Size
0x18000de22  movdqu  xmmword ptr [r14+10h], xmm0
0x18000de28  call    memset_0
0x18000de2d  xor     eax, eax
0x18000de2f  lea     rcx, [r14+28h]; this
0x18000de33  mov     [r14+20h], rax
0x18000de37  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000de3c  lea     rbx, [r14+0E8h]
0x18000de43  xor     r8d, r8d; Flags
0x18000de46  mov     rcx, rbx; lpCriticalSection
0x18000de49  xor     edx, edx; dwSpinCount
0x18000de4b  call    cs:__imp_InitializeCriticalSectionEx
0x18000de51  mov     qword ptr [rbx+28h], 0
0x18000de59  mov     qword ptr [rbx+30h], 0
0x18000de61  mov     qword ptr [rbx+38h], 0
0x18000de69  mov     qword ptr [rbx+40h], 0
0x18000de71  xor     ebx, ebx
0x18000de73  mov     [r15], r14
0x18000de76  test    rdi, rdi
0x18000de79  jz      short loc_18000DE8C
0x18000de7b  mov     rcx, rdi; hMutex
0x18000de7e  call    cs:__imp_ReleaseMutex
0x18000de84  test    eax, eax
0x18000de86  jz      loc_18000DF57
0x18000de8c  test    rbx, rbx
0x18000de8f  jz      short loc_18000DE9E
0x18000de91  mov     rcx, rbx; hObject
0x18000de94  call    cs:__imp_CloseHandle
0x18000de9a  test    eax, eax
0x18000de9c  jz      short loc_18000DEC6
0x18000de9e  xor     eax, eax
0x18000dea0  mov     rcx, [rbp+180h+var_30]
0x18000dea7  xor     rcx, rsp; StackCookie
0x18000deaa  call    __security_check_cookie
0x18000deaf  mov     rbx, [rsp+280h+arg_10]
0x18000deb7  add     rsp, 260h
0x18000debe  pop     r15
0x18000dec0  pop     r14
0x18000dec2  pop     rdi
0x18000dec3  pop     rsi
0x18000dec4  pop     rbp
0x18000dec5  retn
0x18000dec6  mov     rcx, [rbp+188h]; this
0x18000decd  mov     edx, 0A0Bh; void *
0x18000ded2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ded8  mov     rcx, [rbp+188h]; this
0x18000dedf  mov     edx, 0A0Bh; void *
0x18000dee4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000deea  mov     rcx, [rbp+188h]; this
0x18000def1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000def7  mov     rcx, [rbp+188h]; this
0x18000defe  mov     edx, 0A15h; void *
0x18000df03  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000df09  mov     rcx, [rbp+188h]; this
0x18000df10  mov     edx, 0A0Bh; void *
0x18000df15  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000df1b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000df21  mov     rcx, [rbp+188h]; this
0x18000df28  mov     edx, 0A0Bh; void *
0x18000df2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000df33  mov     rcx, [rbp+188h]; this
0x18000df3a  mov     edx, 0A0Bh; void *
0x18000df3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000df45  mov     rcx, [rbp+188h]; this
0x18000df4c  mov     edx, 0A15h; void *
0x18000df51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000df57  mov     rcx, [rbp+188h]; this
0x18000df5e  mov     edx, 0A15h; void *
0x18000df63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
