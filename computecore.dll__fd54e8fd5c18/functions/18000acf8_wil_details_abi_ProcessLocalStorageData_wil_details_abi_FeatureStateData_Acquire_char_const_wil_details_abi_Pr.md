# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000acf8`
- end: `0x18000b0f5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18000b6d8`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009bac`
- `0x18000a488`
- `0x18000acf8`
- `0x18000b2a8`
- `0x18000b948`
- `0x18000c690`
- `0x18000d668`
- `0x18000f1b4`
- `0x18000fcc8`
- `0x180010198`
- `0x1800115b4`
- `0x1800115c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000afbb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000afbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ae26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000af39`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aff8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ae26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000af39`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aff8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ad6f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ad6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b00e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b00e`

## string_xrefs

- `0x18000b047`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b060`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b079`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b092`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b0ab`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b0ca`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000b0e3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x18000acf8  mov     [rsp-8+arg_10], rbx
0x18000acfd  push    rbp
0x18000acfe  push    rsi
0x18000acff  push    rdi
0x18000ad00  push    r14
0x18000ad02  push    r15
0x18000ad04  lea     rbp, [rsp-160h]
0x18000ad0c  sub     rsp, 260h
0x18000ad13  mov     rax, cs:__security_cookie
0x18000ad1a  xor     rax, rsp
0x18000ad1d  mov     [rbp+180h+var_30], rax
0x18000ad24  mov     r15, rdx
0x18000ad27  mov     qword ptr [rdx], 0
0x18000ad2e  mov     rbx, rcx
0x18000ad31  call    cs:__imp_GetCurrentProcessId
0x18000ad37  mov     r14d, 130h
0x18000ad3d  mov     [rsp+280h+var_258], rbx
0x18000ad42  mov     r9d, eax
0x18000ad45  mov     [rsp+280h+var_260], r14d; int
0x18000ad4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ad51  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ad56  lea     edx, [r14-2Ch]; unsigned __int64
0x18000ad5a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ad5f  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ad65  lea     rdx, [rsp+280h+Name]; lpName
0x18000ad6a  xor     r8d, r8d; dwFlags
0x18000ad6d  xor     ecx, ecx; lpMutexAttributes
0x18000ad6f  call    cs:__imp_CreateMutexExW
0x18000ad75  mov     rbx, rax
0x18000ad78  test    rax, rax
0x18000ad7b  jnz     short loc_18000AD87
0x18000ad7d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ad82  jmp     loc_18000B01A
0x18000ad87  xor     r8d, r8d; bAlertable
0x18000ad8a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ad8d  mov     rcx, rbx; hHandle
0x18000ad90  call    cs:__imp_WaitForSingleObjectEx
0x18000ad96  cmp     eax, 102h
0x18000ad9b  jz      short loc_18000ADAD
0x18000ad9d  test    eax, 0FFFFFF7Fh
0x18000ada2  jnz     loc_18000B072
0x18000ada8  mov     rdi, rbx
0x18000adab  jmp     short loc_18000ADAF
0x18000adad  xor     edi, edi
0x18000adaf  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000adb4  mov     [rsp+280h+var_250], 0
0x18000adbd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000adc2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000adc7  mov     esi, eax
0x18000adc9  test    eax, eax
0x18000adcb  jns     short loc_18000AE4C
0x18000adcd  mov     rcx, [rbp+188h]; this
0x18000add4  lea     r8, aWil; "wil"
0x18000addb  mov     r9d, eax; char *
0x18000adde  mov     edx, 66h ; 'f'; void *
0x18000ade3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ade8  mov     rcx, [rbp+188h]; this
0x18000adef  lea     r8, aWil; "wil"
0x18000adf6  mov     r9d, esi; char *
0x18000adf9  mov     edx, 6Fh ; 'o'; void *
0x18000adfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae03  mov     rcx, [rbp+188h]; this
0x18000ae0a  lea     r8, aWil; "wil"
0x18000ae11  mov     r9d, esi; char *
0x18000ae14  mov     edx, 12Eh; void *
0x18000ae19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae1e  test    rdi, rdi
0x18000ae21  jz      short loc_18000AE34
0x18000ae23  mov     rcx, rdi; hMutex
0x18000ae26  call    cs:__imp_ReleaseMutex
0x18000ae2c  test    eax, eax
0x18000ae2e  jz      loc_18000B08B
0x18000ae34  mov     rcx, rbx; hObject
0x18000ae37  call    cs:__imp_CloseHandle
0x18000ae3d  test    eax, eax
0x18000ae3f  jz      loc_18000B0A4
0x18000ae45  mov     eax, esi
0x18000ae47  jmp     loc_18000B01A
0x18000ae4c  mov     rax, [rsp+280h+var_250]
0x18000ae51  lea     rcx, ds:0[rax*4]
0x18000ae59  test    rcx, rcx
0x18000ae5c  jz      short loc_18000AE6C
0x18000ae5e  mov     [r15], rcx
0x18000ae61  mov     eax, [rcx]
0x18000ae63  inc     eax
0x18000ae65  mov     [rcx], eax
0x18000ae67  jmp     loc_18000AFF0
0x18000ae6c  mov     rdx, r14; dwBytes
0x18000ae6f  mov     qword ptr [r15], 0
0x18000ae76  mov     ecx, 8; dwFlags
0x18000ae7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ae80  mov     r14, rax
0x18000ae83  test    rax, rax
0x18000ae86  jnz     short loc_18000AEAA
0x18000ae88  mov     rcx, [rbp+188h]; this
0x18000ae8f  lea     r8, aWil; "wil"
0x18000ae96  mov     esi, 8007000Eh
0x18000ae9b  mov     edx, 14Bh; void *
0x18000aea0  mov     r9d, esi; char *
0x18000aea3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aea8  jmp     short loc_18000AF16
0x18000aeaa  xorps   xmm0, xmm0
0x18000aead  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000aeb3  test    r14b, 3
0x18000aeb7  jnz     loc_18000B0BD
0x18000aebd  mov     r9, r14
0x18000aec0  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000aec5  shr     r9, 2; unsigned __int64
0x18000aec9  lea     rcx, [rsp+280h+var_250]; this
0x18000aece  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000aed3  mov     esi, eax
0x18000aed5  test    eax, eax
0x18000aed7  jns     loc_18000AF5D
0x18000aedd  mov     rcx, [rbp+188h]; this
0x18000aee4  lea     r8, aWil; "wil"
0x18000aeeb  mov     r9d, eax; char *
0x18000aeee  mov     edx, 14Eh; void *
0x18000aef3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aef8  lea     rcx, [rsp+280h+var_250]; this
0x18000aefd  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000af02  call    cs:__imp_GetProcessHeap
0x18000af08  mov     r8, r14; lpMem
0x18000af0b  xor     edx, edx; dwFlags
0x18000af0d  mov     rcx, rax; hHeap
0x18000af10  call    cs:__imp_HeapFree
0x18000af16  mov     rcx, [rbp+188h]; this
0x18000af1d  lea     r8, aWil; "wil"
0x18000af24  mov     r9d, esi; char *
0x18000af27  mov     edx, 137h; void *
0x18000af2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af31  test    rdi, rdi
0x18000af34  jz      short loc_18000AF47
0x18000af36  mov     rcx, rdi; hMutex
0x18000af39  call    cs:__imp_ReleaseMutex
0x18000af3f  test    eax, eax
0x18000af41  jz      loc_18000B0C3
0x18000af47  mov     rcx, rbx; hObject
0x18000af4a  call    cs:__imp_CloseHandle
0x18000af50  test    eax, eax
0x18000af52  jz      loc_18000B059
0x18000af58  jmp     loc_18000AE45
0x18000af5d  mov     rax, [rsp+280h+var_250]
0x18000af62  lea     rcx, [r14+28h]; void *
0x18000af66  mov     [r14+10h], rax
0x18000af6a  xor     edx, edx; Val
0x18000af6c  mov     rax, [rsp+280h+var_250+8]
0x18000af71  mov     r8d, 108h; Size
0x18000af77  mov     [r14+18h], rax
0x18000af7b  mov     dword ptr [r14], 1
0x18000af82  mov     [r14+8], rbx
0x18000af86  mov     [rsp+280h+var_250], 0
0x18000af8f  mov     [rsp+280h+var_250+8], 0
0x18000af98  call    memset_0
0x18000af9d  xor     eax, eax
0x18000af9f  lea     rcx, [r14+28h]; this
0x18000afa3  mov     [r14+20h], rax
0x18000afa7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000afac  lea     rbx, [r14+0E8h]
0x18000afb3  xor     r8d, r8d; Flags
0x18000afb6  mov     rcx, rbx; lpCriticalSection
0x18000afb9  xor     edx, edx; dwSpinCount
0x18000afbb  call    cs:__imp_InitializeCriticalSectionEx
0x18000afc1  mov     qword ptr [rbx+28h], 0
0x18000afc9  lea     rcx, [rsp+280h+var_250]; this
0x18000afce  mov     qword ptr [rbx+30h], 0
0x18000afd6  mov     qword ptr [rbx+38h], 0
0x18000afde  mov     qword ptr [rbx+40h], 0
0x18000afe6  mov     [r15], r14
0x18000afe9  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000afee  xor     ebx, ebx
0x18000aff0  test    rdi, rdi
0x18000aff3  jz      short loc_18000B006
0x18000aff5  mov     rcx, rdi; hMutex
0x18000aff8  call    cs:__imp_ReleaseMutex
0x18000affe  test    eax, eax
0x18000b000  jz      loc_18000B0DC
0x18000b006  test    rbx, rbx
0x18000b009  jz      short loc_18000B018
0x18000b00b  mov     rcx, rbx; hObject
0x18000b00e  call    cs:__imp_CloseHandle
0x18000b014  test    eax, eax
0x18000b016  jz      short loc_18000B040
0x18000b018  xor     eax, eax
0x18000b01a  mov     rcx, [rbp+180h+var_30]
0x18000b021  xor     rcx, rsp; StackCookie
0x18000b024  call    __security_check_cookie
0x18000b029  mov     rbx, [rsp+280h+arg_10]
0x18000b031  add     rsp, 260h
0x18000b038  pop     r15
0x18000b03a  pop     r14
0x18000b03c  pop     rdi
0x18000b03d  pop     rsi
0x18000b03e  pop     rbp
0x18000b03f  retn
0x18000b040  mov     rcx, [rbp+188h]; this
0x18000b047  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b04e  mov     edx, 0A0Bh; void *
0x18000b053  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b059  mov     rcx, [rbp+188h]; this
0x18000b060  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b067  mov     edx, 0A0Bh; void *
0x18000b06c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b072  mov     rcx, [rbp+188h]; this
0x18000b079  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b080  mov     edx, 0E01h; void *
0x18000b085  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000b08b  mov     rcx, [rbp+188h]; this
0x18000b092  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b099  mov     edx, 0A15h; void *
0x18000b09e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0a4  mov     rcx, [rbp+188h]; this
0x18000b0ab  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b0b2  mov     edx, 0A0Bh; void *
0x18000b0b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0bd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b0c3  mov     rcx, [rbp+188h]; this
0x18000b0ca  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b0d1  mov     edx, 0A15h; void *
0x18000b0d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0dc  mov     rcx, [rbp+188h]; this
0x18000b0e3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b0ea  mov     edx, 0A15h; void *
0x18000b0ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
