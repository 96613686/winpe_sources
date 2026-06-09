# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003f18`
- end: `0x1800042df`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800045b4`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x1800032d0`
- `0x180003f18`
- `0x1800042e8`
- `0x180004808`
- `0x180005138`
- `0x180006538`
- `0x180007ac4`
- `0x180007f8c`
- `0x1800083c0`
- `0x180008c7c`
- `0x180008c8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003f51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003f51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004128`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f8f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f8f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800041c1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800041c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003fb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003fb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004031`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004158`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004031`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004158`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004102`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000411a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000420a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004102`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000411a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000420a`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180003f18  mov     [rsp-8+arg_10], rbx
0x180003f1d  push    rbp
0x180003f1e  push    rsi
0x180003f1f  push    rdi
0x180003f20  push    r14
0x180003f22  push    r15
0x180003f24  lea     rbp, [rsp-160h]
0x180003f2c  sub     rsp, 260h
0x180003f33  mov     rax, cs:__security_cookie
0x180003f3a  xor     rax, rsp
0x180003f3d  mov     [rbp+180h+var_30], rax
0x180003f44  mov     r15, rdx
0x180003f47  mov     qword ptr [rdx], 0
0x180003f4e  mov     rbx, rcx
0x180003f51  call    cs:__imp_GetCurrentProcessId
0x180003f57  mov     r14d, 130h
0x180003f5d  mov     [rsp+280h+var_258], rbx
0x180003f62  mov     r9d, eax
0x180003f65  mov     [rsp+280h+var_260], r14d; int
0x180003f6a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003f71  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f76  lea     edx, [r14-2Ch]; unsigned __int64
0x180003f7a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f7f  mov     r9d, 1F0001h; dwDesiredAccess
0x180003f85  lea     rdx, [rsp+280h+Name]; lpName
0x180003f8a  xor     r8d, r8d; dwFlags
0x180003f8d  xor     ecx, ecx; lpMutexAttributes
0x180003f8f  call    cs:__imp_CreateMutexExW
0x180003f95  mov     rbx, rax
0x180003f98  test    rax, rax
0x180003f9b  jnz     short loc_180003FA7
0x180003f9d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003fa2  jmp     loc_180004216
0x180003fa7  xor     r8d, r8d; bAlertable
0x180003faa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003fad  mov     rcx, rbx; hHandle
0x180003fb0  call    cs:__imp_WaitForSingleObjectEx
0x180003fb6  cmp     eax, 102h
0x180003fbb  jz      short loc_180003FCD
0x180003fbd  test    eax, 0FFFFFF7Fh
0x180003fc2  jnz     loc_180004260
0x180003fc8  mov     rdi, rbx
0x180003fcb  jmp     short loc_180003FCF
0x180003fcd  xor     edi, edi
0x180003fcf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003fd4  mov     [rsp+280h+hObject], 0
0x180003fdd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003fe2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003fe7  mov     esi, eax
0x180003fe9  test    eax, eax
0x180003feb  jns     short loc_180004057
0x180003fed  mov     rcx, [rbp+188h]; this
0x180003ff4  mov     r9d, eax; char *
0x180003ff7  mov     edx, 66h ; 'f'; void *
0x180003ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004001  mov     rcx, [rbp+188h]; this
0x180004008  mov     r9d, esi; char *
0x18000400b  mov     edx, 6Fh ; 'o'; void *
0x180004010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004015  mov     rcx, [rbp+188h]; this
0x18000401c  mov     r9d, esi; char *
0x18000401f  mov     edx, 12Eh; void *
0x180004024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004029  test    rdi, rdi
0x18000402c  jz      short loc_18000403F
0x18000402e  mov     rcx, rdi; hMutex
0x180004031  call    cs:__imp_ReleaseMutex
0x180004037  test    eax, eax
0x180004039  jz      loc_18000426D
0x18000403f  mov     rcx, rbx; hObject
0x180004042  call    cs:__imp_CloseHandle
0x180004048  test    eax, eax
0x18000404a  jz      loc_18000427F
0x180004050  mov     eax, esi
0x180004052  jmp     loc_180004216
0x180004057  mov     rax, [rsp+280h+hObject]
0x18000405c  lea     rcx, ds:0[rax*4]
0x180004064  test    rcx, rcx
0x180004067  jz      short loc_180004077
0x180004069  mov     [r15], rcx
0x18000406c  mov     eax, [rcx]
0x18000406e  inc     eax
0x180004070  mov     [rcx], eax
0x180004072  jmp     loc_1800041EC
0x180004077  mov     rdx, r14; dwBytes
0x18000407a  mov     qword ptr [r15], 0
0x180004081  mov     ecx, 8; dwFlags
0x180004086  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000408b  mov     r14, rax
0x18000408e  test    rax, rax
0x180004091  jnz     short loc_1800040B1
0x180004093  mov     rcx, [rbp+188h]; this
0x18000409a  mov     esi, 8007000Eh
0x18000409f  mov     r9d, esi; char *
0x1800040a2  mov     edx, 14Bh; void *
0x1800040a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ac  jmp     loc_18000413C
0x1800040b1  xorps   xmm0, xmm0
0x1800040b4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800040ba  test    r14b, 3
0x1800040be  jnz     loc_180004291
0x1800040c4  mov     r9, r14
0x1800040c7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800040cc  shr     r9, 2; unsigned __int64
0x1800040d0  lea     rcx, [rsp+280h+hObject]; this
0x1800040d5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800040da  mov     esi, eax
0x1800040dc  test    eax, eax
0x1800040de  jns     loc_18000417C
0x1800040e4  mov     rcx, [rbp+188h]; this
0x1800040eb  mov     r9d, eax; char *
0x1800040ee  mov     edx, 14Eh; void *
0x1800040f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040f8  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800040fd  test    rcx, rcx
0x180004100  jz      short loc_180004110
0x180004102  call    cs:__imp_CloseHandle
0x180004108  test    eax, eax
0x18000410a  jz      loc_180004297
0x180004110  mov     rcx, [rsp+280h+hObject]; hObject
0x180004115  test    rcx, rcx
0x180004118  jz      short loc_180004128
0x18000411a  call    cs:__imp_CloseHandle
0x180004120  test    eax, eax
0x180004122  jz      loc_1800042A9
0x180004128  call    cs:__imp_GetProcessHeap
0x18000412e  mov     r8, r14; lpMem
0x180004131  xor     edx, edx; dwFlags
0x180004133  mov     rcx, rax; hHeap
0x180004136  call    cs:__imp_HeapFree
0x18000413c  mov     rcx, [rbp+188h]; this
0x180004143  mov     r9d, esi; char *
0x180004146  mov     edx, 137h; void *
0x18000414b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004150  test    rdi, rdi
0x180004153  jz      short loc_180004166
0x180004155  mov     rcx, rdi; hMutex
0x180004158  call    cs:__imp_ReleaseMutex
0x18000415e  test    eax, eax
0x180004160  jz      loc_1800042BB
0x180004166  mov     rcx, rbx; hObject
0x180004169  call    cs:__imp_CloseHandle
0x18000416f  test    eax, eax
0x180004171  jz      loc_18000424E
0x180004177  jmp     loc_180004050
0x18000417c  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004181  lea     rcx, [r14+28h]; void *
0x180004185  mov     dword ptr [r14], 1
0x18000418c  xor     edx, edx; Val
0x18000418e  mov     [r14+8], rbx
0x180004192  mov     r8d, 108h; Size
0x180004198  movdqu  xmmword ptr [r14+10h], xmm0
0x18000419e  call    memset_0
0x1800041a3  xor     eax, eax
0x1800041a5  lea     rcx, [r14+28h]; this
0x1800041a9  mov     [r14+20h], rax
0x1800041ad  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800041b2  lea     rbx, [r14+0E8h]
0x1800041b9  xor     r8d, r8d; Flags
0x1800041bc  mov     rcx, rbx; lpCriticalSection
0x1800041bf  xor     edx, edx; dwSpinCount
0x1800041c1  call    cs:__imp_InitializeCriticalSectionEx
0x1800041c7  mov     qword ptr [rbx+28h], 0
0x1800041cf  mov     qword ptr [rbx+30h], 0
0x1800041d7  mov     qword ptr [rbx+38h], 0
0x1800041df  mov     qword ptr [rbx+40h], 0
0x1800041e7  xor     ebx, ebx
0x1800041e9  mov     [r15], r14
0x1800041ec  test    rdi, rdi
0x1800041ef  jz      short loc_180004202
0x1800041f1  mov     rcx, rdi; hMutex
0x1800041f4  call    cs:__imp_ReleaseMutex
0x1800041fa  test    eax, eax
0x1800041fc  jz      loc_1800042CD
0x180004202  test    rbx, rbx
0x180004205  jz      short loc_180004214
0x180004207  mov     rcx, rbx; hObject
0x18000420a  call    cs:__imp_CloseHandle
0x180004210  test    eax, eax
0x180004212  jz      short loc_18000423C
0x180004214  xor     eax, eax
0x180004216  mov     rcx, [rbp+180h+var_30]
0x18000421d  xor     rcx, rsp; StackCookie
0x180004220  call    __security_check_cookie
0x180004225  mov     rbx, [rsp+280h+arg_10]
0x18000422d  add     rsp, 260h
0x180004234  pop     r15
0x180004236  pop     r14
0x180004238  pop     rdi
0x180004239  pop     rsi
0x18000423a  pop     rbp
0x18000423b  retn
0x18000423c  mov     rcx, [rbp+188h]; this
0x180004243  mov     edx, 0A0Bh; void *
0x180004248  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000424e  mov     rcx, [rbp+188h]; this
0x180004255  mov     edx, 0A0Bh; void *
0x18000425a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004260  mov     rcx, [rbp+188h]; this
0x180004267  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000426d  mov     rcx, [rbp+188h]; this
0x180004274  mov     edx, 0A15h; void *
0x180004279  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000427f  mov     rcx, [rbp+188h]; this
0x180004286  mov     edx, 0A0Bh; void *
0x18000428b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004291  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004297  mov     rcx, [rbp+188h]; this
0x18000429e  mov     edx, 0A0Bh; void *
0x1800042a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042a9  mov     rcx, [rbp+188h]; this
0x1800042b0  mov     edx, 0A0Bh; void *
0x1800042b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042bb  mov     rcx, [rbp+188h]; this
0x1800042c2  mov     edx, 0A15h; void *
0x1800042c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042cd  mov     rcx, [rbp+188h]; this
0x1800042d4  mov     edx, 0A15h; void *
0x1800042d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
