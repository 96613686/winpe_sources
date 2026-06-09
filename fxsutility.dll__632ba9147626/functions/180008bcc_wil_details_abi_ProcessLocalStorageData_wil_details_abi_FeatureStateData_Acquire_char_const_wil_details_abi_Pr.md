# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008bcc`
- end: `0x180008f93`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009314`

## callees

- `0x180005168`
- `0x180007fa0`
- `0x180008bcc`
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

- `KERNEL32!CloseHandle` at `0x180008cf6`
- `KERNEL32!CloseHandle` at `0x180008db6`
- `KERNEL32!CloseHandle` at `0x180008dce`
- `KERNEL32!CloseHandle` at `0x180008e1d`
- `KERNEL32!CloseHandle` at `0x180008ebe`
- `KERNEL32!CloseHandle` at `0x180008cf6`
- `KERNEL32!CloseHandle` at `0x180008db6`
- `KERNEL32!CloseHandle` at `0x180008dce`
- `KERNEL32!CloseHandle` at `0x180008e1d`
- `KERNEL32!CloseHandle` at `0x180008ebe`
- `KERNEL32!GetCurrentProcessId` at `0x180008c05`
- `KERNEL32!GetCurrentProcessId` at `0x180008c05`
- `KERNEL32!HeapFree` at `0x180008dea`
- `KERNEL32!HeapFree` at `0x180008dea`
- `KERNEL32!GetProcessHeap` at `0x180008ddc`
- `KERNEL32!GetProcessHeap` at `0x180008ddc`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180008e75`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180008e75`
- `KERNEL32!ReleaseMutex` at `0x180008ce5`
- `KERNEL32!ReleaseMutex` at `0x180008e0c`
- `KERNEL32!ReleaseMutex` at `0x180008ea8`
- `KERNEL32!ReleaseMutex` at `0x180008ce5`
- `KERNEL32!ReleaseMutex` at `0x180008e0c`
- `KERNEL32!ReleaseMutex` at `0x180008ea8`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008c64`
- `KERNEL32!WaitForSingleObjectEx` at `0x180008c64`
- `KERNEL32!CreateMutexExW` at `0x180008c43`
- `KERNEL32!CreateMutexExW` at `0x180008c43`

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
0x180008bcc  mov     [rsp-8+arg_10], rbx
0x180008bd1  push    rbp
0x180008bd2  push    rsi
0x180008bd3  push    rdi
0x180008bd4  push    r14
0x180008bd6  push    r15
0x180008bd8  lea     rbp, [rsp-160h]
0x180008be0  sub     rsp, 260h
0x180008be7  mov     rax, cs:__security_cookie
0x180008bee  xor     rax, rsp
0x180008bf1  mov     [rbp+180h+var_30], rax
0x180008bf8  mov     r15, rdx
0x180008bfb  mov     qword ptr [rdx], 0
0x180008c02  mov     rbx, rcx
0x180008c05  call    cs:__imp_GetCurrentProcessId
0x180008c0b  mov     r14d, 130h
0x180008c11  mov     [rsp+280h+var_258], rbx
0x180008c16  mov     r9d, eax
0x180008c19  mov     [rsp+280h+var_260], r14d; int
0x180008c1e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008c25  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008c2a  lea     edx, [r14-2Ch]; unsigned __int64
0x180008c2e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008c33  mov     r9d, 1F0001h; dwDesiredAccess
0x180008c39  lea     rdx, [rsp+280h+Name]; lpName
0x180008c3e  xor     r8d, r8d; dwFlags
0x180008c41  xor     ecx, ecx; lpMutexAttributes
0x180008c43  call    cs:__imp_CreateMutexExW
0x180008c49  mov     rbx, rax
0x180008c4c  test    rax, rax
0x180008c4f  jnz     short loc_180008C5B
0x180008c51  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008c56  jmp     loc_180008ECA
0x180008c5b  xor     r8d, r8d; bAlertable
0x180008c5e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008c61  mov     rcx, rbx; hHandle
0x180008c64  call    cs:__imp_WaitForSingleObjectEx
0x180008c6a  cmp     eax, 102h
0x180008c6f  jz      short loc_180008C81
0x180008c71  test    eax, 0FFFFFF7Fh
0x180008c76  jnz     loc_180008F14
0x180008c7c  mov     rdi, rbx
0x180008c7f  jmp     short loc_180008C83
0x180008c81  xor     edi, edi
0x180008c83  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008c88  mov     [rsp+280h+hObject], 0
0x180008c91  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008c96  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008c9b  mov     esi, eax
0x180008c9d  test    eax, eax
0x180008c9f  jns     short loc_180008D0B
0x180008ca1  mov     rcx, [rbp+188h]; this
0x180008ca8  mov     r9d, eax; char *
0x180008cab  mov     edx, 66h ; 'f'; void *
0x180008cb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cb5  mov     rcx, [rbp+188h]; this
0x180008cbc  mov     r9d, esi; char *
0x180008cbf  mov     edx, 6Fh ; 'o'; void *
0x180008cc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cc9  mov     rcx, [rbp+188h]; this
0x180008cd0  mov     r9d, esi; char *
0x180008cd3  mov     edx, 12Eh; void *
0x180008cd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cdd  test    rdi, rdi
0x180008ce0  jz      short loc_180008CF3
0x180008ce2  mov     rcx, rdi; hMutex
0x180008ce5  call    cs:__imp_ReleaseMutex
0x180008ceb  test    eax, eax
0x180008ced  jz      loc_180008F21
0x180008cf3  mov     rcx, rbx; hObject
0x180008cf6  call    cs:__imp_CloseHandle
0x180008cfc  test    eax, eax
0x180008cfe  jz      loc_180008F33
0x180008d04  mov     eax, esi
0x180008d06  jmp     loc_180008ECA
0x180008d0b  mov     rax, [rsp+280h+hObject]
0x180008d10  lea     rcx, ds:0[rax*4]
0x180008d18  test    rcx, rcx
0x180008d1b  jz      short loc_180008D2B
0x180008d1d  mov     [r15], rcx
0x180008d20  mov     eax, [rcx]
0x180008d22  inc     eax
0x180008d24  mov     [rcx], eax
0x180008d26  jmp     loc_180008EA0
0x180008d2b  mov     rdx, r14; dwBytes
0x180008d2e  mov     qword ptr [r15], 0
0x180008d35  mov     ecx, 8; dwFlags
0x180008d3a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008d3f  mov     r14, rax
0x180008d42  test    rax, rax
0x180008d45  jnz     short loc_180008D65
0x180008d47  mov     rcx, [rbp+188h]; this
0x180008d4e  mov     esi, 8007000Eh
0x180008d53  mov     r9d, esi; char *
0x180008d56  mov     edx, 14Bh; void *
0x180008d5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d60  jmp     loc_180008DF0
0x180008d65  xorps   xmm0, xmm0
0x180008d68  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008d6e  test    r14b, 3
0x180008d72  jnz     loc_180008F45
0x180008d78  mov     r9, r14
0x180008d7b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008d80  shr     r9, 2; unsigned __int64
0x180008d84  lea     rcx, [rsp+280h+hObject]; this
0x180008d89  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008d8e  mov     esi, eax
0x180008d90  test    eax, eax
0x180008d92  jns     loc_180008E30
0x180008d98  mov     rcx, [rbp+188h]; this
0x180008d9f  mov     r9d, eax; char *
0x180008da2  mov     edx, 14Eh; void *
0x180008da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dac  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008db1  test    rcx, rcx
0x180008db4  jz      short loc_180008DC4
0x180008db6  call    cs:__imp_CloseHandle
0x180008dbc  test    eax, eax
0x180008dbe  jz      loc_180008F4B
0x180008dc4  mov     rcx, [rsp+280h+hObject]; hObject
0x180008dc9  test    rcx, rcx
0x180008dcc  jz      short loc_180008DDC
0x180008dce  call    cs:__imp_CloseHandle
0x180008dd4  test    eax, eax
0x180008dd6  jz      loc_180008F5D
0x180008ddc  call    cs:__imp_GetProcessHeap
0x180008de2  mov     r8, r14; lpMem
0x180008de5  xor     edx, edx; dwFlags
0x180008de7  mov     rcx, rax; hHeap
0x180008dea  call    cs:__imp_HeapFree
0x180008df0  mov     rcx, [rbp+188h]; this
0x180008df7  mov     r9d, esi; char *
0x180008dfa  mov     edx, 137h; void *
0x180008dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e04  test    rdi, rdi
0x180008e07  jz      short loc_180008E1A
0x180008e09  mov     rcx, rdi; hMutex
0x180008e0c  call    cs:__imp_ReleaseMutex
0x180008e12  test    eax, eax
0x180008e14  jz      loc_180008F6F
0x180008e1a  mov     rcx, rbx; hObject
0x180008e1d  call    cs:__imp_CloseHandle
0x180008e23  test    eax, eax
0x180008e25  jz      loc_180008F02
0x180008e2b  jmp     loc_180008D04
0x180008e30  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008e35  lea     rcx, [r14+28h]; void *
0x180008e39  mov     dword ptr [r14], 1
0x180008e40  xor     edx, edx; Val
0x180008e42  mov     [r14+8], rbx
0x180008e46  mov     r8d, 108h; Size
0x180008e4c  movdqu  xmmword ptr [r14+10h], xmm0
0x180008e52  call    memset_0
0x180008e57  xor     eax, eax
0x180008e59  lea     rcx, [r14+28h]; this
0x180008e5d  mov     [r14+20h], rax
0x180008e61  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008e66  lea     rbx, [r14+0E8h]
0x180008e6d  xor     r8d, r8d; Flags
0x180008e70  mov     rcx, rbx; lpCriticalSection
0x180008e73  xor     edx, edx; dwSpinCount
0x180008e75  call    cs:__imp_InitializeCriticalSectionEx
0x180008e7b  mov     qword ptr [rbx+28h], 0
0x180008e83  mov     qword ptr [rbx+30h], 0
0x180008e8b  mov     qword ptr [rbx+38h], 0
0x180008e93  mov     qword ptr [rbx+40h], 0
0x180008e9b  xor     ebx, ebx
0x180008e9d  mov     [r15], r14
0x180008ea0  test    rdi, rdi
0x180008ea3  jz      short loc_180008EB6
0x180008ea5  mov     rcx, rdi; hMutex
0x180008ea8  call    cs:__imp_ReleaseMutex
0x180008eae  test    eax, eax
0x180008eb0  jz      loc_180008F81
0x180008eb6  test    rbx, rbx
0x180008eb9  jz      short loc_180008EC8
0x180008ebb  mov     rcx, rbx; hObject
0x180008ebe  call    cs:__imp_CloseHandle
0x180008ec4  test    eax, eax
0x180008ec6  jz      short loc_180008EF0
0x180008ec8  xor     eax, eax
0x180008eca  mov     rcx, [rbp+180h+var_30]
0x180008ed1  xor     rcx, rsp; StackCookie
0x180008ed4  call    __security_check_cookie
0x180008ed9  mov     rbx, [rsp+280h+arg_10]
0x180008ee1  add     rsp, 260h
0x180008ee8  pop     r15
0x180008eea  pop     r14
0x180008eec  pop     rdi
0x180008eed  pop     rsi
0x180008eee  pop     rbp
0x180008eef  retn
0x180008ef0  mov     rcx, [rbp+188h]; this
0x180008ef7  mov     edx, 0A0Bh; void *
0x180008efc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f02  mov     rcx, [rbp+188h]; this
0x180008f09  mov     edx, 0A0Bh; void *
0x180008f0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f14  mov     rcx, [rbp+188h]; this
0x180008f1b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008f21  mov     rcx, [rbp+188h]; this
0x180008f28  mov     edx, 0A15h; void *
0x180008f2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f33  mov     rcx, [rbp+188h]; this
0x180008f3a  mov     edx, 0A0Bh; void *
0x180008f3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f45  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008f4b  mov     rcx, [rbp+188h]; this
0x180008f52  mov     edx, 0A0Bh; void *
0x180008f57  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f5d  mov     rcx, [rbp+188h]; this
0x180008f64  mov     edx, 0A0Bh; void *
0x180008f69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f6f  mov     rcx, [rbp+188h]; this
0x180008f76  mov     edx, 0A15h; void *
0x180008f7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f81  mov     rcx, [rbp+188h]; this
0x180008f88  mov     edx, 0A15h; void *
0x180008f8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
