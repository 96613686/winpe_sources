# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140003da8`
- end: `0x140004199`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140004484`

## callees

- `0x140001570`
- `0x1400020d0`
- `0x14000302c`
- `0x140003da8`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003e1f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003e1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003e40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003e40`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003ed6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004012`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400040ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003ed6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004012`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400040ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000407b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000407b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003fe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003fe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003fdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003de1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003de1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040c4`

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
0x140003da8  mov     [rsp-8+arg_10], rbx
0x140003dad  push    rbp
0x140003dae  push    rsi
0x140003daf  push    rdi
0x140003db0  push    r14
0x140003db2  push    r15
0x140003db4  lea     rbp, [rsp-160h]
0x140003dbc  sub     rsp, 260h
0x140003dc3  mov     rax, cs:__security_cookie
0x140003dca  xor     rax, rsp
0x140003dcd  mov     [rbp+180h+var_30], rax
0x140003dd4  mov     r15, rdx
0x140003dd7  mov     qword ptr [rdx], 0
0x140003dde  mov     rbx, rcx
0x140003de1  call    cs:__imp_GetCurrentProcessId
0x140003de7  mov     r14d, 130h
0x140003ded  mov     [rsp+280h+var_258], rbx
0x140003df2  mov     r9d, eax
0x140003df5  mov     [rsp+280h+var_260], r14d; int
0x140003dfa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003e01  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003e06  lea     edx, [r14-2Ch]; unsigned __int64
0x140003e0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003e0f  mov     r9d, 1F0001h; dwDesiredAccess
0x140003e15  lea     rdx, [rsp+280h+Name]; lpName
0x140003e1a  xor     r8d, r8d; dwFlags
0x140003e1d  xor     ecx, ecx; lpMutexAttributes
0x140003e1f  call    cs:__imp_CreateMutexExW
0x140003e25  mov     rbx, rax
0x140003e28  test    rax, rax
0x140003e2b  jnz     short loc_140003E37
0x140003e2d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003e32  jmp     loc_1400040D0
0x140003e37  xor     r8d, r8d; bAlertable
0x140003e3a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003e3d  mov     rcx, rbx; hHandle
0x140003e40  call    cs:__imp_WaitForSingleObjectEx
0x140003e46  cmp     eax, 102h
0x140003e4b  jz      short loc_140003E5D
0x140003e4d  test    eax, 0FFFFFF7Fh
0x140003e52  jnz     loc_14000411A
0x140003e58  mov     rdi, rbx
0x140003e5b  jmp     short loc_140003E5F
0x140003e5d  xor     edi, edi
0x140003e5f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003e64  mov     [rsp+280h+hObject], 0
0x140003e6d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003e72  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003e77  mov     esi, eax
0x140003e79  test    eax, eax
0x140003e7b  jns     short loc_140003EFC
0x140003e7d  mov     rcx, [rbp+188h]; this
0x140003e84  lea     r8, aWil; "wil"
0x140003e8b  mov     r9d, eax; char *
0x140003e8e  mov     edx, 66h ; 'f'; void *
0x140003e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e98  mov     rcx, [rbp+188h]; this
0x140003e9f  lea     r8, aWil; "wil"
0x140003ea6  mov     r9d, esi; char *
0x140003ea9  mov     edx, 6Fh ; 'o'; void *
0x140003eae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003eb3  mov     rcx, [rbp+188h]; this
0x140003eba  lea     r8, aWil; "wil"
0x140003ec1  mov     r9d, esi; char *
0x140003ec4  mov     edx, 12Eh; void *
0x140003ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ece  test    rdi, rdi
0x140003ed1  jz      short loc_140003EE4
0x140003ed3  mov     rcx, rdi; hMutex
0x140003ed6  call    cs:__imp_ReleaseMutex
0x140003edc  test    eax, eax
0x140003ede  jz      loc_140004127
0x140003ee4  mov     rcx, rbx; hObject
0x140003ee7  call    cs:__imp_CloseHandle
0x140003eed  test    eax, eax
0x140003eef  jz      loc_140004139
0x140003ef5  mov     eax, esi
0x140003ef7  jmp     loc_1400040D0
0x140003efc  mov     rax, [rsp+280h+hObject]
0x140003f01  lea     rcx, ds:0[rax*4]
0x140003f09  test    rcx, rcx
0x140003f0c  jz      short loc_140003F1C
0x140003f0e  mov     [r15], rcx
0x140003f11  mov     eax, [rcx]
0x140003f13  inc     eax
0x140003f15  mov     [rcx], eax
0x140003f17  jmp     loc_1400040A6
0x140003f1c  mov     rdx, r14; dwBytes
0x140003f1f  mov     qword ptr [r15], 0
0x140003f26  mov     ecx, 8; dwFlags
0x140003f2b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003f30  mov     r14, rax
0x140003f33  test    rax, rax
0x140003f36  jnz     short loc_140003F5D
0x140003f38  mov     rcx, [rbp+188h]; this
0x140003f3f  lea     r8, aWil; "wil"
0x140003f46  mov     esi, 8007000Eh
0x140003f4b  mov     edx, 14Bh; void *
0x140003f50  mov     r9d, esi; char *
0x140003f53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f58  jmp     loc_140003FEF
0x140003f5d  xorps   xmm0, xmm0
0x140003f60  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003f66  test    r14b, 3
0x140003f6a  jnz     loc_14000414B
0x140003f70  mov     r9, r14
0x140003f73  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003f78  shr     r9, 2; unsigned __int64
0x140003f7c  lea     rcx, [rsp+280h+hObject]; this
0x140003f81  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003f86  mov     esi, eax
0x140003f88  test    eax, eax
0x140003f8a  jns     loc_140004036
0x140003f90  mov     rcx, [rbp+188h]; this
0x140003f97  lea     r8, aWil; "wil"
0x140003f9e  mov     r9d, eax; char *
0x140003fa1  mov     edx, 14Eh; void *
0x140003fa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003fab  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003fb0  test    rcx, rcx
0x140003fb3  jz      short loc_140003FC3
0x140003fb5  call    cs:__imp_CloseHandle
0x140003fbb  test    eax, eax
0x140003fbd  jz      loc_140004151
0x140003fc3  mov     rcx, [rsp+280h+hObject]; hObject
0x140003fc8  test    rcx, rcx
0x140003fcb  jz      short loc_140003FDB
0x140003fcd  call    cs:__imp_CloseHandle
0x140003fd3  test    eax, eax
0x140003fd5  jz      loc_140004163
0x140003fdb  call    cs:__imp_GetProcessHeap
0x140003fe1  mov     r8, r14; lpMem
0x140003fe4  xor     edx, edx; dwFlags
0x140003fe6  mov     rcx, rax; hHeap
0x140003fe9  call    cs:__imp_HeapFree
0x140003fef  mov     rcx, [rbp+188h]; this
0x140003ff6  lea     r8, aWil; "wil"
0x140003ffd  mov     r9d, esi; char *
0x140004000  mov     edx, 137h; void *
0x140004005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000400a  test    rdi, rdi
0x14000400d  jz      short loc_140004020
0x14000400f  mov     rcx, rdi; hMutex
0x140004012  call    cs:__imp_ReleaseMutex
0x140004018  test    eax, eax
0x14000401a  jz      loc_140004175
0x140004020  mov     rcx, rbx; hObject
0x140004023  call    cs:__imp_CloseHandle
0x140004029  test    eax, eax
0x14000402b  jz      loc_140004108
0x140004031  jmp     loc_140003EF5
0x140004036  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000403b  lea     rcx, [r14+28h]; void *
0x14000403f  mov     dword ptr [r14], 1
0x140004046  xor     edx, edx; Val
0x140004048  mov     [r14+8], rbx
0x14000404c  mov     r8d, 108h; Size
0x140004052  movdqu  xmmword ptr [r14+10h], xmm0
0x140004058  call    memset_0
0x14000405d  xor     eax, eax
0x14000405f  lea     rcx, [r14+28h]; this
0x140004063  mov     [r14+20h], rax
0x140004067  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000406c  lea     rbx, [r14+0E8h]
0x140004073  xor     r8d, r8d; Flags
0x140004076  mov     rcx, rbx; lpCriticalSection
0x140004079  xor     edx, edx; dwSpinCount
0x14000407b  call    cs:__imp_InitializeCriticalSectionEx
0x140004081  mov     qword ptr [rbx+28h], 0
0x140004089  mov     qword ptr [rbx+30h], 0
0x140004091  mov     qword ptr [rbx+38h], 0
0x140004099  mov     qword ptr [rbx+40h], 0
0x1400040a1  xor     ebx, ebx
0x1400040a3  mov     [r15], r14
0x1400040a6  test    rdi, rdi
0x1400040a9  jz      short loc_1400040BC
0x1400040ab  mov     rcx, rdi; hMutex
0x1400040ae  call    cs:__imp_ReleaseMutex
0x1400040b4  test    eax, eax
0x1400040b6  jz      loc_140004187
0x1400040bc  test    rbx, rbx
0x1400040bf  jz      short loc_1400040CE
0x1400040c1  mov     rcx, rbx; hObject
0x1400040c4  call    cs:__imp_CloseHandle
0x1400040ca  test    eax, eax
0x1400040cc  jz      short loc_1400040F6
0x1400040ce  xor     eax, eax
0x1400040d0  mov     rcx, [rbp+180h+var_30]
0x1400040d7  xor     rcx, rsp; StackCookie
0x1400040da  call    __security_check_cookie
0x1400040df  mov     rbx, [rsp+280h+arg_10]
0x1400040e7  add     rsp, 260h
0x1400040ee  pop     r15
0x1400040f0  pop     r14
0x1400040f2  pop     rdi
0x1400040f3  pop     rsi
0x1400040f4  pop     rbp
0x1400040f5  retn
0x1400040f6  mov     rcx, [rbp+188h]; this
0x1400040fd  mov     edx, 0A0Bh; void *
0x140004102  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004108  mov     rcx, [rbp+188h]; this
0x14000410f  mov     edx, 0A0Bh; void *
0x140004114  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000411a  mov     rcx, [rbp+188h]; this
0x140004121  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004127  mov     rcx, [rbp+188h]; this
0x14000412e  mov     edx, 0A15h; void *
0x140004133  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004139  mov     rcx, [rbp+188h]; this
0x140004140  mov     edx, 0A0Bh; void *
0x140004145  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000414b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004151  mov     rcx, [rbp+188h]; this
0x140004158  mov     edx, 0A0Bh; void *
0x14000415d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004163  mov     rcx, [rbp+188h]; this
0x14000416a  mov     edx, 0A0Bh; void *
0x14000416f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004175  mov     rcx, [rbp+188h]; this
0x14000417c  mov     edx, 0A15h; void *
0x140004181  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004187  mov     rcx, [rbp+188h]; this
0x14000418e  mov     edx, 0A15h; void *
0x140004193  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
