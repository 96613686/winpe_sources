# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140007738`
- end: `0x140007b29`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400083cc`

## callees

- `0x1400022a0`
- `0x140002d4c`
- `0x140005c9c`
- `0x140007738`
- `0x140007f28`
- `0x14000855c`
- `0x140009674`
- `0x14000a910`
- `0x14000c8d4`
- `0x14000dad4`
- `0x14000de70`
- `0x1400100dc`
- `0x1400100ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400077af`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400077af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400077d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400077d0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140007a0b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140007a0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007866`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400079a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007866`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400079a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007a3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000796b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000796b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007979`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000795d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400079b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000795d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400079b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a54`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
0x140007738  mov     [rsp-8+arg_10], rbx
0x14000773d  push    rbp
0x14000773e  push    rsi
0x14000773f  push    rdi
0x140007740  push    r14
0x140007742  push    r15
0x140007744  lea     rbp, [rsp-160h]
0x14000774c  sub     rsp, 260h
0x140007753  mov     rax, cs:__security_cookie
0x14000775a  xor     rax, rsp
0x14000775d  mov     [rbp+180h+var_30], rax
0x140007764  mov     r15, rdx
0x140007767  mov     qword ptr [rdx], 0
0x14000776e  mov     rbx, rcx
0x140007771  call    cs:__imp_GetCurrentProcessId
0x140007777  mov     r14d, 130h
0x14000777d  mov     [rsp+280h+var_258], rbx
0x140007782  mov     r9d, eax
0x140007785  mov     [rsp+280h+var_260], r14d; int
0x14000778a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007791  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007796  lea     edx, [r14-2Ch]; unsigned __int64
0x14000779a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000779f  mov     r9d, 1F0001h; dwDesiredAccess
0x1400077a5  lea     rdx, [rsp+280h+Name]; lpName
0x1400077aa  xor     r8d, r8d; dwFlags
0x1400077ad  xor     ecx, ecx; lpMutexAttributes
0x1400077af  call    cs:__imp_CreateMutexExW
0x1400077b5  mov     rbx, rax
0x1400077b8  test    rax, rax
0x1400077bb  jnz     short loc_1400077C7
0x1400077bd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400077c2  jmp     loc_140007A60
0x1400077c7  xor     r8d, r8d; bAlertable
0x1400077ca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400077cd  mov     rcx, rbx; hHandle
0x1400077d0  call    cs:__imp_WaitForSingleObjectEx
0x1400077d6  cmp     eax, 102h
0x1400077db  jz      short loc_1400077ED
0x1400077dd  test    eax, 0FFFFFF7Fh
0x1400077e2  jnz     loc_140007AAA
0x1400077e8  mov     rdi, rbx
0x1400077eb  jmp     short loc_1400077EF
0x1400077ed  xor     edi, edi
0x1400077ef  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400077f4  mov     [rsp+280h+hObject], 0
0x1400077fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007802  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140007807  mov     esi, eax
0x140007809  test    eax, eax
0x14000780b  jns     short loc_14000788C
0x14000780d  mov     rcx, [rbp+188h]; this
0x140007814  lea     r8, aWil; "wil"
0x14000781b  mov     r9d, eax; char *
0x14000781e  mov     edx, 66h ; 'f'; void *
0x140007823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007828  mov     rcx, [rbp+188h]; this
0x14000782f  lea     r8, aWil; "wil"
0x140007836  mov     r9d, esi; char *
0x140007839  mov     edx, 6Fh ; 'o'; void *
0x14000783e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007843  mov     rcx, [rbp+188h]; this
0x14000784a  lea     r8, aWil; "wil"
0x140007851  mov     r9d, esi; char *
0x140007854  mov     edx, 12Eh; void *
0x140007859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000785e  test    rdi, rdi
0x140007861  jz      short loc_140007874
0x140007863  mov     rcx, rdi; hMutex
0x140007866  call    cs:__imp_ReleaseMutex
0x14000786c  test    eax, eax
0x14000786e  jz      loc_140007AB7
0x140007874  mov     rcx, rbx; hObject
0x140007877  call    cs:__imp_CloseHandle
0x14000787d  test    eax, eax
0x14000787f  jz      loc_140007AC9
0x140007885  mov     eax, esi
0x140007887  jmp     loc_140007A60
0x14000788c  mov     rax, [rsp+280h+hObject]
0x140007891  lea     rcx, ds:0[rax*4]
0x140007899  test    rcx, rcx
0x14000789c  jz      short loc_1400078AC
0x14000789e  mov     [r15], rcx
0x1400078a1  mov     eax, [rcx]
0x1400078a3  inc     eax
0x1400078a5  mov     [rcx], eax
0x1400078a7  jmp     loc_140007A36
0x1400078ac  mov     rdx, r14; dwBytes
0x1400078af  mov     qword ptr [r15], 0
0x1400078b6  mov     ecx, 8; dwFlags
0x1400078bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400078c0  mov     r14, rax
0x1400078c3  test    rax, rax
0x1400078c6  jnz     short loc_1400078ED
0x1400078c8  mov     rcx, [rbp+188h]; this
0x1400078cf  lea     r8, aWil; "wil"
0x1400078d6  mov     esi, 8007000Eh
0x1400078db  mov     edx, 14Bh; void *
0x1400078e0  mov     r9d, esi; char *
0x1400078e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400078e8  jmp     loc_14000797F
0x1400078ed  xorps   xmm0, xmm0
0x1400078f0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400078f6  test    r14b, 3
0x1400078fa  jnz     loc_140007ADB
0x140007900  mov     r9, r14
0x140007903  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140007908  shr     r9, 2; unsigned __int64
0x14000790c  lea     rcx, [rsp+280h+hObject]; this
0x140007911  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140007916  mov     esi, eax
0x140007918  test    eax, eax
0x14000791a  jns     loc_1400079C6
0x140007920  mov     rcx, [rbp+188h]; this
0x140007927  lea     r8, aWil; "wil"
0x14000792e  mov     r9d, eax; char *
0x140007931  mov     edx, 14Eh; void *
0x140007936  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000793b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140007940  test    rcx, rcx
0x140007943  jz      short loc_140007953
0x140007945  call    cs:__imp_CloseHandle
0x14000794b  test    eax, eax
0x14000794d  jz      loc_140007AE1
0x140007953  mov     rcx, [rsp+280h+hObject]; hObject
0x140007958  test    rcx, rcx
0x14000795b  jz      short loc_14000796B
0x14000795d  call    cs:__imp_CloseHandle
0x140007963  test    eax, eax
0x140007965  jz      loc_140007AF3
0x14000796b  call    cs:__imp_GetProcessHeap
0x140007971  mov     r8, r14; lpMem
0x140007974  xor     edx, edx; dwFlags
0x140007976  mov     rcx, rax; hHeap
0x140007979  call    cs:__imp_HeapFree
0x14000797f  mov     rcx, [rbp+188h]; this
0x140007986  lea     r8, aWil; "wil"
0x14000798d  mov     r9d, esi; char *
0x140007990  mov     edx, 137h; void *
0x140007995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000799a  test    rdi, rdi
0x14000799d  jz      short loc_1400079B0
0x14000799f  mov     rcx, rdi; hMutex
0x1400079a2  call    cs:__imp_ReleaseMutex
0x1400079a8  test    eax, eax
0x1400079aa  jz      loc_140007B05
0x1400079b0  mov     rcx, rbx; hObject
0x1400079b3  call    cs:__imp_CloseHandle
0x1400079b9  test    eax, eax
0x1400079bb  jz      loc_140007A98
0x1400079c1  jmp     loc_140007885
0x1400079c6  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400079cb  lea     rcx, [r14+28h]; void *
0x1400079cf  mov     dword ptr [r14], 1
0x1400079d6  xor     edx, edx; Val
0x1400079d8  mov     [r14+8], rbx
0x1400079dc  mov     r8d, 108h; Size
0x1400079e2  movdqu  xmmword ptr [r14+10h], xmm0
0x1400079e8  call    memset_0
0x1400079ed  xor     eax, eax
0x1400079ef  lea     rcx, [r14+28h]; this
0x1400079f3  mov     [r14+20h], rax
0x1400079f7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400079fc  lea     rbx, [r14+0E8h]
0x140007a03  xor     r8d, r8d; Flags
0x140007a06  mov     rcx, rbx; lpCriticalSection
0x140007a09  xor     edx, edx; dwSpinCount
0x140007a0b  call    cs:__imp_InitializeCriticalSectionEx
0x140007a11  mov     qword ptr [rbx+28h], 0
0x140007a19  mov     qword ptr [rbx+30h], 0
0x140007a21  mov     qword ptr [rbx+38h], 0
0x140007a29  mov     qword ptr [rbx+40h], 0
0x140007a31  xor     ebx, ebx
0x140007a33  mov     [r15], r14
0x140007a36  test    rdi, rdi
0x140007a39  jz      short loc_140007A4C
0x140007a3b  mov     rcx, rdi; hMutex
0x140007a3e  call    cs:__imp_ReleaseMutex
0x140007a44  test    eax, eax
0x140007a46  jz      loc_140007B17
0x140007a4c  test    rbx, rbx
0x140007a4f  jz      short loc_140007A5E
0x140007a51  mov     rcx, rbx; hObject
0x140007a54  call    cs:__imp_CloseHandle
0x140007a5a  test    eax, eax
0x140007a5c  jz      short loc_140007A86
0x140007a5e  xor     eax, eax
0x140007a60  mov     rcx, [rbp+180h+var_30]
0x140007a67  xor     rcx, rsp; StackCookie
0x140007a6a  call    __security_check_cookie
0x140007a6f  mov     rbx, [rsp+280h+arg_10]
0x140007a77  add     rsp, 260h
0x140007a7e  pop     r15
0x140007a80  pop     r14
0x140007a82  pop     rdi
0x140007a83  pop     rsi
0x140007a84  pop     rbp
0x140007a85  retn
0x140007a86  mov     rcx, [rbp+188h]; this
0x140007a8d  mov     edx, 0A0Bh; void *
0x140007a92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007a98  mov     rcx, [rbp+188h]; this
0x140007a9f  mov     edx, 0A0Bh; void *
0x140007aa4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007aaa  mov     rcx, [rbp+188h]; this
0x140007ab1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140007ab7  mov     rcx, [rbp+188h]; this
0x140007abe  mov     edx, 0A15h; void *
0x140007ac3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007ac9  mov     rcx, [rbp+188h]; this
0x140007ad0  mov     edx, 0A0Bh; void *
0x140007ad5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007adb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140007ae1  mov     rcx, [rbp+188h]; this
0x140007ae8  mov     edx, 0A0Bh; void *
0x140007aed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007af3  mov     rcx, [rbp+188h]; this
0x140007afa  mov     edx, 0A0Bh; void *
0x140007aff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007b05  mov     rcx, [rbp+188h]; this
0x140007b0c  mov     edx, 0A15h; void *
0x140007b11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007b17  mov     rcx, [rbp+188h]; this
0x140007b1e  mov     edx, 0A15h; void *
0x140007b23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
