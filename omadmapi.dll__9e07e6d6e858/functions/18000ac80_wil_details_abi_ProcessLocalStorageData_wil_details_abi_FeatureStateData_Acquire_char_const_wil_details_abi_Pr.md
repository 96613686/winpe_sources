# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000ac80`
- end: `0x18000b080`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000bd0c`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180006140`
- `0x180009c44`
- `0x18000a548`
- `0x18000ac80`
- `0x18000b528`
- `0x18000bf64`
- `0x18000ce9c`
- `0x1800100a8`
- `0x180011b98`
- `0x180013468`
- `0x180013cf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aeb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aeb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000acb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000acb9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000acfd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000acfd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000af6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000af6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000adc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000afb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000adc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000afb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000addb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000addb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afce`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v36[0];
  *((_QWORD *)v22 + 3) = v36[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x18000ac80  mov     [rsp-8+arg_10], rbx
0x18000ac85  push    rbp
0x18000ac86  push    rsi
0x18000ac87  push    rdi
0x18000ac88  push    r14
0x18000ac8a  push    r15
0x18000ac8c  lea     rbp, [rsp-160h]
0x18000ac94  sub     rsp, 260h
0x18000ac9b  mov     rax, cs:__security_cookie
0x18000aca2  xor     rax, rsp
0x18000aca5  mov     [rbp+180h+var_30], rax
0x18000acac  mov     r15, rdx
0x18000acaf  mov     qword ptr [rdx], 0
0x18000acb6  mov     rbx, rcx
0x18000acb9  call    cs:__imp_GetCurrentProcessId
0x18000acc0  nop     dword ptr [rax+rax+00h]
0x18000acc5  mov     r14d, 130h
0x18000accb  mov     [rsp+280h+var_258], rbx
0x18000acd0  mov     r9d, eax
0x18000acd3  mov     [rsp+280h+var_260], r14d; int
0x18000acd8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000acdf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ace4  lea     edx, [r14-2Ch]; unsigned __int64
0x18000ace8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000aced  mov     r9d, 1F0001h; dwDesiredAccess
0x18000acf3  lea     rdx, [rsp+280h+Name]; lpName
0x18000acf8  xor     r8d, r8d; dwFlags
0x18000acfb  xor     ecx, ecx; lpMutexAttributes
0x18000acfd  call    cs:__imp_CreateMutexExW
0x18000ad04  nop     dword ptr [rax+rax+00h]
0x18000ad09  mov     rbx, rax
0x18000ad0c  test    rax, rax
0x18000ad0f  jnz     short loc_18000AD1B
0x18000ad11  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ad16  jmp     loc_18000AFE0
0x18000ad1b  xor     r8d, r8d; bAlertable
0x18000ad1e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ad21  mov     rcx, rbx; hHandle
0x18000ad24  call    cs:__imp_WaitForSingleObjectEx
0x18000ad2b  nop     dword ptr [rax+rax+00h]
0x18000ad30  cmp     eax, 102h
0x18000ad35  jz      short loc_18000AD47
0x18000ad37  test    eax, 0FFFFFF7Fh
0x18000ad3c  jnz     loc_18000B02B
0x18000ad42  mov     rdi, rbx
0x18000ad45  jmp     short loc_18000AD49
0x18000ad47  xor     edi, edi
0x18000ad49  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000ad4e  mov     [rsp+280h+var_250], 0
0x18000ad57  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ad5c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000ad61  mov     esi, eax
0x18000ad63  test    eax, eax
0x18000ad65  jns     loc_18000ADF6
0x18000ad6b  mov     rcx, [rbp+188h]; this
0x18000ad72  lea     r8, aWil; "wil"
0x18000ad79  mov     r9d, eax; char *
0x18000ad7c  mov     edx, 66h ; 'f'; void *
0x18000ad81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad86  mov     rcx, [rbp+188h]; this
0x18000ad8d  lea     r8, aWil; "wil"
0x18000ad94  mov     r9d, esi; char *
0x18000ad97  mov     edx, 6Fh ; 'o'; void *
0x18000ad9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ada1  mov     rcx, [rbp+188h]; this
0x18000ada8  lea     r8, aWil; "wil"
0x18000adaf  mov     r9d, esi; char *
0x18000adb2  mov     edx, 12Eh; void *
0x18000adb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adbc  test    rdi, rdi
0x18000adbf  jz      short loc_18000ADD8
0x18000adc1  mov     rcx, rdi; hMutex
0x18000adc4  call    cs:__imp_ReleaseMutex
0x18000adcb  nop     dword ptr [rax+rax+00h]
0x18000add0  test    eax, eax
0x18000add2  jz      loc_18000B038
0x18000add8  mov     rcx, rbx; hObject
0x18000addb  call    cs:__imp_CloseHandle
0x18000ade2  nop     dword ptr [rax+rax+00h]
0x18000ade7  test    eax, eax
0x18000ade9  jz      loc_18000B04A
0x18000adef  mov     eax, esi
0x18000adf1  jmp     loc_18000AFE0
0x18000adf6  mov     rax, [rsp+280h+var_250]
0x18000adfb  lea     rcx, ds:0[rax*4]
0x18000ae03  test    rcx, rcx
0x18000ae06  jz      short loc_18000AE16
0x18000ae08  mov     [r15], rcx
0x18000ae0b  mov     eax, [rcx]
0x18000ae0d  inc     eax
0x18000ae0f  mov     [rcx], eax
0x18000ae11  jmp     loc_18000AFAA
0x18000ae16  mov     rdx, r14; dwBytes
0x18000ae19  mov     qword ptr [r15], 0
0x18000ae20  mov     ecx, 8; dwFlags
0x18000ae25  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ae2a  mov     r14, rax
0x18000ae2d  test    rax, rax
0x18000ae30  jnz     short loc_18000AE54
0x18000ae32  mov     rcx, [rbp+188h]; this
0x18000ae39  lea     r8, aWil; "wil"
0x18000ae40  mov     esi, 8007000Eh
0x18000ae45  mov     edx, 14Bh; void *
0x18000ae4a  mov     r9d, esi; char *
0x18000ae4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae52  jmp     short loc_18000AEBE
0x18000ae54  xorps   xmm0, xmm0
0x18000ae57  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000ae5c  mov     r8, r14; void *
0x18000ae5f  lea     rcx, [rsp+280h+var_250]; this
0x18000ae64  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000ae6a  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000ae6f  mov     esi, eax
0x18000ae71  test    eax, eax
0x18000ae73  jns     loc_18000AF11
0x18000ae79  mov     rcx, [rbp+188h]; this
0x18000ae80  lea     r8, aWil; "wil"
0x18000ae87  mov     r9d, eax; char *
0x18000ae8a  mov     edx, 14Eh; void *
0x18000ae8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae94  lea     rcx, [rsp+280h+var_250]; this
0x18000ae99  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ae9e  call    cs:__imp_GetProcessHeap
0x18000aea5  nop     dword ptr [rax+rax+00h]
0x18000aeaa  mov     r8, r14; lpMem
0x18000aead  xor     edx, edx; dwFlags
0x18000aeaf  mov     rcx, rax; hHeap
0x18000aeb2  call    cs:__imp_HeapFree
0x18000aeb9  nop     dword ptr [rax+rax+00h]
0x18000aebe  mov     rcx, [rbp+188h]; this
0x18000aec5  lea     r8, aWil; "wil"
0x18000aecc  mov     r9d, esi; char *
0x18000aecf  mov     edx, 137h; void *
0x18000aed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aed9  test    rdi, rdi
0x18000aedc  jz      short loc_18000AEF5
0x18000aede  mov     rcx, rdi; hMutex
0x18000aee1  call    cs:__imp_ReleaseMutex
0x18000aee8  nop     dword ptr [rax+rax+00h]
0x18000aeed  test    eax, eax
0x18000aeef  jz      loc_18000B05C
0x18000aef5  mov     rcx, rbx; hObject
0x18000aef8  call    cs:__imp_CloseHandle
0x18000aeff  nop     dword ptr [rax+rax+00h]
0x18000af04  test    eax, eax
0x18000af06  jz      loc_18000B019
0x18000af0c  jmp     loc_18000ADEF
0x18000af11  mov     rax, [rsp+280h+var_250]
0x18000af16  lea     rcx, [r14+28h]; void *
0x18000af1a  mov     [r14+10h], rax
0x18000af1e  xor     edx, edx; Val
0x18000af20  mov     rax, [rsp+280h+var_250+8]
0x18000af25  mov     r8d, 108h; Size
0x18000af2b  mov     [r14+18h], rax
0x18000af2f  mov     dword ptr [r14], 1
0x18000af36  mov     [r14+8], rbx
0x18000af3a  mov     [rsp+280h+var_250], 0
0x18000af43  mov     [rsp+280h+var_250+8], 0
0x18000af4c  call    memset_0
0x18000af51  xor     eax, eax
0x18000af53  lea     rcx, [r14+28h]; this
0x18000af57  mov     [r14+20h], rax
0x18000af5b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000af60  lea     rbx, [r14+0E8h]
0x18000af67  xor     r8d, r8d; Flags
0x18000af6a  mov     rcx, rbx; lpCriticalSection
0x18000af6d  xor     edx, edx; dwSpinCount
0x18000af6f  call    cs:__imp_InitializeCriticalSectionEx
0x18000af76  nop     dword ptr [rax+rax+00h]
0x18000af7b  mov     qword ptr [rbx+28h], 0
0x18000af83  lea     rcx, [rsp+280h+var_250]; this
0x18000af88  mov     qword ptr [rbx+30h], 0
0x18000af90  mov     qword ptr [rbx+38h], 0
0x18000af98  mov     qword ptr [rbx+40h], 0
0x18000afa0  mov     [r15], r14
0x18000afa3  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000afa8  xor     ebx, ebx
0x18000afaa  test    rdi, rdi
0x18000afad  jz      short loc_18000AFC6
0x18000afaf  mov     rcx, rdi; hMutex
0x18000afb2  call    cs:__imp_ReleaseMutex
0x18000afb9  nop     dword ptr [rax+rax+00h]
0x18000afbe  test    eax, eax
0x18000afc0  jz      loc_18000B06E
0x18000afc6  test    rbx, rbx
0x18000afc9  jz      short loc_18000AFDE
0x18000afcb  mov     rcx, rbx; hObject
0x18000afce  call    cs:__imp_CloseHandle
0x18000afd5  nop     dword ptr [rax+rax+00h]
0x18000afda  test    eax, eax
0x18000afdc  jz      short loc_18000B007
0x18000afde  xor     eax, eax
0x18000afe0  mov     rcx, [rbp+180h+var_30]
0x18000afe7  xor     rcx, rsp; StackCookie
0x18000afea  call    __security_check_cookie
0x18000afef  mov     rbx, [rsp+280h+arg_10]
0x18000aff7  add     rsp, 260h
0x18000affe  pop     r15
0x18000b000  pop     r14
0x18000b002  pop     rdi
0x18000b003  pop     rsi
0x18000b004  pop     rbp
0x18000b005  retn
0x18000b007  mov     rcx, [rbp+188h]; this
0x18000b00e  mov     edx, 0A0Bh; void *
0x18000b013  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b019  mov     rcx, [rbp+188h]; this
0x18000b020  mov     edx, 0A0Bh; void *
0x18000b025  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b02b  mov     rcx, [rbp+188h]; this
0x18000b032  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000b038  mov     rcx, [rbp+188h]; this
0x18000b03f  mov     edx, 0A15h; void *
0x18000b044  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b04a  mov     rcx, [rbp+188h]; this
0x18000b051  mov     edx, 0A0Bh; void *
0x18000b056  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b05c  mov     rcx, [rbp+188h]; this
0x18000b063  mov     edx, 0A15h; void *
0x18000b068  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b06e  mov     rcx, [rbp+188h]; this
0x18000b075  mov     edx, 0A15h; void *
0x18000b07a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
