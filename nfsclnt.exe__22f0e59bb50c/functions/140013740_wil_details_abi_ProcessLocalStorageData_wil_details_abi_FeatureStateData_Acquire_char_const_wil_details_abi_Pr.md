# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140013740`
- end: `0x140013b07`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140013de4`

## callees

- `0x140012c8c`
- `0x140013740`
- `0x140013b10`
- `0x140013f74`
- `0x140014898`
- `0x140015488`
- `0x140016720`
- `0x140016bf0`
- `0x140016ef8`
- `0x1400176cc`
- `0x1400176dc`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001395e`
- `KERNEL32!HeapFree` at `0x14001395e`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400139e9`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400139e9`
- `KERNEL32!GetCurrentProcessId` at `0x140013779`
- `KERNEL32!GetCurrentProcessId` at `0x140013779`
- `KERNEL32!GetProcessHeap` at `0x140013950`
- `KERNEL32!GetProcessHeap` at `0x140013950`
- `KERNEL32!ReleaseMutex` at `0x140013859`
- `KERNEL32!ReleaseMutex` at `0x140013980`
- `KERNEL32!ReleaseMutex` at `0x140013a1c`
- `KERNEL32!ReleaseMutex` at `0x140013859`
- `KERNEL32!ReleaseMutex` at `0x140013980`
- `KERNEL32!ReleaseMutex` at `0x140013a1c`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400137d8`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400137d8`
- `KERNEL32!CreateMutexExW` at `0x1400137b7`
- `KERNEL32!CreateMutexExW` at `0x1400137b7`
- `KERNEL32!CloseHandle` at `0x14001386a`
- `KERNEL32!CloseHandle` at `0x14001392a`
- `KERNEL32!CloseHandle` at `0x140013942`
- `KERNEL32!CloseHandle` at `0x140013991`
- `KERNEL32!CloseHandle` at `0x140013a32`
- `KERNEL32!CloseHandle` at `0x14001386a`
- `KERNEL32!CloseHandle` at `0x14001392a`
- `KERNEL32!CloseHandle` at `0x140013942`
- `KERNEL32!CloseHandle` at `0x140013991`
- `KERNEL32!CloseHandle` at `0x140013a32`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
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
0x140013740  mov     [rsp-8+arg_10], rbx
0x140013745  push    rbp
0x140013746  push    rsi
0x140013747  push    rdi
0x140013748  push    r14
0x14001374a  push    r15
0x14001374c  lea     rbp, [rsp-160h]
0x140013754  sub     rsp, 260h
0x14001375b  mov     rax, cs:__security_cookie
0x140013762  xor     rax, rsp
0x140013765  mov     [rbp+180h+var_30], rax
0x14001376c  mov     r15, rdx
0x14001376f  mov     qword ptr [rdx], 0
0x140013776  mov     rbx, rcx
0x140013779  call    cs:__imp_GetCurrentProcessId
0x14001377f  mov     r14d, 130h
0x140013785  mov     [rsp+280h+var_258], rbx
0x14001378a  mov     r9d, eax
0x14001378d  mov     [rsp+280h+var_260], r14d; int
0x140013792  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140013799  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14001379e  lea     edx, [r14-2Ch]; unsigned __int64
0x1400137a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400137a7  mov     r9d, 1F0001h; dwDesiredAccess
0x1400137ad  lea     rdx, [rsp+280h+Name]; lpName
0x1400137b2  xor     r8d, r8d; dwFlags
0x1400137b5  xor     ecx, ecx; lpMutexAttributes
0x1400137b7  call    cs:__imp_CreateMutexExW
0x1400137bd  mov     rbx, rax
0x1400137c0  test    rax, rax
0x1400137c3  jnz     short loc_1400137CF
0x1400137c5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400137ca  jmp     loc_140013A3E
0x1400137cf  xor     r8d, r8d; bAlertable
0x1400137d2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400137d5  mov     rcx, rbx; hHandle
0x1400137d8  call    cs:__imp_WaitForSingleObjectEx
0x1400137de  cmp     eax, 102h
0x1400137e3  jz      short loc_1400137F5
0x1400137e5  test    eax, 0FFFFFF7Fh
0x1400137ea  jnz     loc_140013A88
0x1400137f0  mov     rdi, rbx
0x1400137f3  jmp     short loc_1400137F7
0x1400137f5  xor     edi, edi
0x1400137f7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400137fc  mov     [rsp+280h+hObject], 0
0x140013805  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14001380a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14001380f  mov     esi, eax
0x140013811  test    eax, eax
0x140013813  jns     short loc_14001387F
0x140013815  mov     rcx, [rbp+188h]; this
0x14001381c  mov     r9d, eax; char *
0x14001381f  mov     edx, 66h ; 'f'; void *
0x140013824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013829  mov     rcx, [rbp+188h]; this
0x140013830  mov     r9d, esi; char *
0x140013833  mov     edx, 6Fh ; 'o'; void *
0x140013838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001383d  mov     rcx, [rbp+188h]; this
0x140013844  mov     r9d, esi; char *
0x140013847  mov     edx, 12Eh; void *
0x14001384c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013851  test    rdi, rdi
0x140013854  jz      short loc_140013867
0x140013856  mov     rcx, rdi; hMutex
0x140013859  call    cs:__imp_ReleaseMutex
0x14001385f  test    eax, eax
0x140013861  jz      loc_140013A95
0x140013867  mov     rcx, rbx; hObject
0x14001386a  call    cs:__imp_CloseHandle
0x140013870  test    eax, eax
0x140013872  jz      loc_140013AA7
0x140013878  mov     eax, esi
0x14001387a  jmp     loc_140013A3E
0x14001387f  mov     rax, [rsp+280h+hObject]
0x140013884  lea     rcx, ds:0[rax*4]
0x14001388c  test    rcx, rcx
0x14001388f  jz      short loc_14001389F
0x140013891  mov     [r15], rcx
0x140013894  mov     eax, [rcx]
0x140013896  inc     eax
0x140013898  mov     [rcx], eax
0x14001389a  jmp     loc_140013A14
0x14001389f  mov     rdx, r14; dwBytes
0x1400138a2  mov     qword ptr [r15], 0
0x1400138a9  mov     ecx, 8; dwFlags
0x1400138ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400138b3  mov     r14, rax
0x1400138b6  test    rax, rax
0x1400138b9  jnz     short loc_1400138D9
0x1400138bb  mov     rcx, [rbp+188h]; this
0x1400138c2  mov     esi, 8007000Eh
0x1400138c7  mov     r9d, esi; char *
0x1400138ca  mov     edx, 14Bh; void *
0x1400138cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400138d4  jmp     loc_140013964
0x1400138d9  xorps   xmm0, xmm0
0x1400138dc  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400138e2  test    r14b, 3
0x1400138e6  jnz     loc_140013AB9
0x1400138ec  mov     r9, r14
0x1400138ef  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400138f4  shr     r9, 2; unsigned __int64
0x1400138f8  lea     rcx, [rsp+280h+hObject]; this
0x1400138fd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140013902  mov     esi, eax
0x140013904  test    eax, eax
0x140013906  jns     loc_1400139A4
0x14001390c  mov     rcx, [rbp+188h]; this
0x140013913  mov     r9d, eax; char *
0x140013916  mov     edx, 14Eh; void *
0x14001391b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013920  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140013925  test    rcx, rcx
0x140013928  jz      short loc_140013938
0x14001392a  call    cs:__imp_CloseHandle
0x140013930  test    eax, eax
0x140013932  jz      loc_140013ABF
0x140013938  mov     rcx, [rsp+280h+hObject]; hObject
0x14001393d  test    rcx, rcx
0x140013940  jz      short loc_140013950
0x140013942  call    cs:__imp_CloseHandle
0x140013948  test    eax, eax
0x14001394a  jz      loc_140013AD1
0x140013950  call    cs:__imp_GetProcessHeap
0x140013956  mov     r8, r14; lpMem
0x140013959  xor     edx, edx; dwFlags
0x14001395b  mov     rcx, rax; hHeap
0x14001395e  call    cs:__imp_HeapFree
0x140013964  mov     rcx, [rbp+188h]; this
0x14001396b  mov     r9d, esi; char *
0x14001396e  mov     edx, 137h; void *
0x140013973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013978  test    rdi, rdi
0x14001397b  jz      short loc_14001398E
0x14001397d  mov     rcx, rdi; hMutex
0x140013980  call    cs:__imp_ReleaseMutex
0x140013986  test    eax, eax
0x140013988  jz      loc_140013AE3
0x14001398e  mov     rcx, rbx; hObject
0x140013991  call    cs:__imp_CloseHandle
0x140013997  test    eax, eax
0x140013999  jz      loc_140013A76
0x14001399f  jmp     loc_140013878
0x1400139a4  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400139a9  lea     rcx, [r14+28h]; void *
0x1400139ad  mov     dword ptr [r14], 1
0x1400139b4  xor     edx, edx; Val
0x1400139b6  mov     [r14+8], rbx
0x1400139ba  mov     r8d, 108h; Size
0x1400139c0  movdqu  xmmword ptr [r14+10h], xmm0
0x1400139c6  call    memset_0
0x1400139cb  xor     eax, eax
0x1400139cd  lea     rcx, [r14+28h]; this
0x1400139d1  mov     [r14+20h], rax
0x1400139d5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400139da  lea     rbx, [r14+0E8h]
0x1400139e1  xor     r8d, r8d; Flags
0x1400139e4  mov     rcx, rbx; lpCriticalSection
0x1400139e7  xor     edx, edx; dwSpinCount
0x1400139e9  call    cs:__imp_InitializeCriticalSectionEx
0x1400139ef  mov     qword ptr [rbx+28h], 0
0x1400139f7  mov     qword ptr [rbx+30h], 0
0x1400139ff  mov     qword ptr [rbx+38h], 0
0x140013a07  mov     qword ptr [rbx+40h], 0
0x140013a0f  xor     ebx, ebx
0x140013a11  mov     [r15], r14
0x140013a14  test    rdi, rdi
0x140013a17  jz      short loc_140013A2A
0x140013a19  mov     rcx, rdi; hMutex
0x140013a1c  call    cs:__imp_ReleaseMutex
0x140013a22  test    eax, eax
0x140013a24  jz      loc_140013AF5
0x140013a2a  test    rbx, rbx
0x140013a2d  jz      short loc_140013A3C
0x140013a2f  mov     rcx, rbx; hObject
0x140013a32  call    cs:__imp_CloseHandle
0x140013a38  test    eax, eax
0x140013a3a  jz      short loc_140013A64
0x140013a3c  xor     eax, eax
0x140013a3e  mov     rcx, [rbp+180h+var_30]
0x140013a45  xor     rcx, rsp; StackCookie
0x140013a48  call    __security_check_cookie
0x140013a4d  mov     rbx, [rsp+280h+arg_10]
0x140013a55  add     rsp, 260h
0x140013a5c  pop     r15
0x140013a5e  pop     r14
0x140013a60  pop     rdi
0x140013a61  pop     rsi
0x140013a62  pop     rbp
0x140013a63  retn
0x140013a64  mov     rcx, [rbp+188h]; this
0x140013a6b  mov     edx, 0A0Bh; void *
0x140013a70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013a76  mov     rcx, [rbp+188h]; this
0x140013a7d  mov     edx, 0A0Bh; void *
0x140013a82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013a88  mov     rcx, [rbp+188h]; this
0x140013a8f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140013a95  mov     rcx, [rbp+188h]; this
0x140013a9c  mov     edx, 0A15h; void *
0x140013aa1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013aa7  mov     rcx, [rbp+188h]; this
0x140013aae  mov     edx, 0A0Bh; void *
0x140013ab3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013ab9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140013abf  mov     rcx, [rbp+188h]; this
0x140013ac6  mov     edx, 0A0Bh; void *
0x140013acb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013ad1  mov     rcx, [rbp+188h]; this
0x140013ad8  mov     edx, 0A0Bh; void *
0x140013add  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013ae3  mov     rcx, [rbp+188h]; this
0x140013aea  mov     edx, 0A15h; void *
0x140013aef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013af5  mov     rcx, [rbp+188h]; this
0x140013afc  mov     edx, 0A15h; void *
0x140013b01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
