# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005480`
- end: `0x180005858`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180006634`

## callees

- `0x1800051f0`
- `0x180005480`
- `0x180005860`
- `0x180005bb8`
- `0x1800062e8`
- `0x180006eac`
- `0x180007674`
- `0x180007ea4`
- `0x18000809c`
- `0x18000863c`
- `0x18000864c`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800056c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000575b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800056c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000575b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800054f8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800054f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005519`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005519`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000569b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000569b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000568d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000568d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800054b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800055c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005771`

## string_xrefs

- `0x1800057aa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800057c3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800057dc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800057f5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005814`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000582d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005846`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return v22;
}

```

## disassembly

```asm
0x180005480  mov     [rsp-8+arg_10], rbx
0x180005485  push    rbp
0x180005486  push    rsi
0x180005487  push    rdi
0x180005488  push    r14
0x18000548a  push    r15
0x18000548c  lea     rbp, [rsp-160h]
0x180005494  sub     rsp, 260h
0x18000549b  mov     rax, cs:__security_cookie
0x1800054a2  xor     rax, rsp
0x1800054a5  mov     [rbp+180h+var_30], rax
0x1800054ac  mov     r15, rdx
0x1800054af  mov     qword ptr [rdx], 0
0x1800054b6  mov     rbx, rcx
0x1800054b9  call    cs:__imp_GetCurrentProcessId
0x1800054bf  mov     r14d, 78h ; 'x'
0x1800054c5  mov     [rsp+280h+var_258], rbx
0x1800054ca  mov     r9d, eax
0x1800054cd  mov     [rsp+280h+var_260], r14d; int
0x1800054d2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800054d9  mov     edx, 104h; unsigned __int64
0x1800054de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800054e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800054e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800054ee  lea     rdx, [rsp+280h+Name]; lpName
0x1800054f3  xor     r8d, r8d; dwFlags
0x1800054f6  xor     ecx, ecx; lpMutexAttributes
0x1800054f8  call    cs:__imp_CreateMutexExW
0x1800054fe  mov     rbx, rax
0x180005501  test    rax, rax
0x180005504  jnz     short loc_180005510
0x180005506  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000550b  jmp     loc_18000577D
0x180005510  xor     r8d, r8d; bAlertable
0x180005513  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005516  mov     rcx, rbx; hHandle
0x180005519  call    cs:__imp_WaitForSingleObjectEx
0x18000551f  cmp     eax, 102h
0x180005524  jz      short loc_180005536
0x180005526  test    eax, 0FFFFFF7Fh
0x18000552b  jnz     loc_1800057BC
0x180005531  mov     rdi, rbx
0x180005534  jmp     short loc_180005538
0x180005536  xor     edi, edi
0x180005538  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000553d  mov     [rsp+280h+var_250], 0
0x180005546  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000554b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005550  mov     esi, eax
0x180005552  test    eax, eax
0x180005554  jns     short loc_1800055D5
0x180005556  mov     rcx, [rbp+188h]; this
0x18000555d  lea     r8, aWil; "wil"
0x180005564  mov     r9d, eax; char *
0x180005567  mov     edx, 66h ; 'f'; void *
0x18000556c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005571  mov     rcx, [rbp+188h]; this
0x180005578  lea     r8, aWil; "wil"
0x18000557f  mov     r9d, esi; char *
0x180005582  mov     edx, 6Fh ; 'o'; void *
0x180005587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000558c  mov     rcx, [rbp+188h]; this
0x180005593  lea     r8, aWil; "wil"
0x18000559a  mov     r9d, esi; char *
0x18000559d  mov     edx, 12Eh; void *
0x1800055a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055a7  test    rdi, rdi
0x1800055aa  jz      short loc_1800055BD
0x1800055ac  mov     rcx, rdi; hMutex
0x1800055af  call    cs:__imp_ReleaseMutex
0x1800055b5  test    eax, eax
0x1800055b7  jz      loc_1800057D5
0x1800055bd  mov     rcx, rbx; hObject
0x1800055c0  call    cs:__imp_CloseHandle
0x1800055c6  test    eax, eax
0x1800055c8  jz      loc_1800057EE
0x1800055ce  mov     eax, esi
0x1800055d0  jmp     loc_18000577D
0x1800055d5  mov     rax, [rsp+280h+var_250]
0x1800055da  lea     rcx, ds:0[rax*4]
0x1800055e2  test    rcx, rcx
0x1800055e5  jz      short loc_1800055F5
0x1800055e7  mov     [r15], rcx
0x1800055ea  mov     eax, [rcx]
0x1800055ec  inc     eax
0x1800055ee  mov     [rcx], eax
0x1800055f0  jmp     loc_180005753
0x1800055f5  mov     rdx, r14; dwBytes
0x1800055f8  mov     qword ptr [r15], 0
0x1800055ff  mov     ecx, 8; dwFlags
0x180005604  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005609  mov     rsi, rax
0x18000560c  test    rax, rax
0x18000560f  jnz     short loc_180005634
0x180005611  mov     rcx, [rbp+188h]; this
0x180005618  lea     r8, aWil; "wil"
0x18000561f  mov     r14d, 8007000Eh
0x180005625  mov     edx, 14Bh; void *
0x18000562a  mov     r9d, r14d; char *
0x18000562d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005632  jmp     short loc_1800056A1
0x180005634  xorps   xmm0, xmm0
0x180005637  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000563d  test    sil, 3
0x180005641  jnz     loc_180005807
0x180005647  mov     r9, rsi
0x18000564a  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000564f  shr     r9, 2; unsigned __int64
0x180005653  lea     rcx, [rsp+280h+var_250]; this
0x180005658  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000565d  mov     r14d, eax
0x180005660  test    eax, eax
0x180005662  jns     loc_1800056EB
0x180005668  mov     rcx, [rbp+188h]; this
0x18000566f  lea     r8, aWil; "wil"
0x180005676  mov     r9d, eax; char *
0x180005679  mov     edx, 14Eh; void *
0x18000567e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005683  lea     rcx, [rsp+280h+var_250]; this
0x180005688  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000568d  call    cs:__imp_GetProcessHeap
0x180005693  mov     r8, rsi; lpMem
0x180005696  xor     edx, edx; dwFlags
0x180005698  mov     rcx, rax; hHeap
0x18000569b  call    cs:__imp_HeapFree
0x1800056a1  mov     rcx, [rbp+188h]; this
0x1800056a8  lea     r8, aWil; "wil"
0x1800056af  mov     r9d, r14d; char *
0x1800056b2  mov     edx, 137h; void *
0x1800056b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056bc  test    rdi, rdi
0x1800056bf  jz      short loc_1800056D2
0x1800056c1  mov     rcx, rdi; hMutex
0x1800056c4  call    cs:__imp_ReleaseMutex
0x1800056ca  test    eax, eax
0x1800056cc  jz      loc_18000580D
0x1800056d2  mov     rcx, rbx; hObject
0x1800056d5  call    cs:__imp_CloseHandle
0x1800056db  test    eax, eax
0x1800056dd  jz      loc_180005826
0x1800056e3  mov     eax, r14d
0x1800056e6  jmp     loc_18000577D
0x1800056eb  mov     rax, [rsp+280h+var_250]
0x1800056f0  lea     rcx, [rsi+22h]; void *
0x1800056f4  xor     edx, edx; Val
0x1800056f6  mov     [rsi+10h], rax
0x1800056fa  mov     rax, [rsp+280h+var_250+8]
0x1800056ff  mov     dword ptr [rsi], 1
0x180005705  mov     [rsi+8], rbx
0x180005709  lea     r8d, [rdx+56h]; Size
0x18000570d  mov     [rsp+280h+var_250], 0
0x180005716  mov     [rsi+18h], rax
0x18000571a  mov     [rsp+280h+var_250+8], 0
0x180005723  call    memset_0
0x180005728  xor     edx, edx; Val
0x18000572a  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005730  lea     rcx, [rsi+28h]; void *
0x180005734  mov     dword ptr [rsi+24h], 1
0x18000573b  lea     r8d, [rdx+50h]; Size
0x18000573f  call    memset_0
0x180005744  lea     rcx, [rsp+280h+var_250]; this
0x180005749  mov     [r15], rsi
0x18000574c  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005751  xor     ebx, ebx
0x180005753  test    rdi, rdi
0x180005756  jz      short loc_180005769
0x180005758  mov     rcx, rdi; hMutex
0x18000575b  call    cs:__imp_ReleaseMutex
0x180005761  test    eax, eax
0x180005763  jz      loc_18000583F
0x180005769  test    rbx, rbx
0x18000576c  jz      short loc_18000577B
0x18000576e  mov     rcx, rbx; hObject
0x180005771  call    cs:__imp_CloseHandle
0x180005777  test    eax, eax
0x180005779  jz      short loc_1800057A3
0x18000577b  xor     eax, eax
0x18000577d  mov     rcx, [rbp+180h+var_30]
0x180005784  xor     rcx, rsp; StackCookie
0x180005787  call    __security_check_cookie
0x18000578c  mov     rbx, [rsp+280h+arg_10]
0x180005794  add     rsp, 260h
0x18000579b  pop     r15
0x18000579d  pop     r14
0x18000579f  pop     rdi
0x1800057a0  pop     rsi
0x1800057a1  pop     rbp
0x1800057a2  retn
0x1800057a3  mov     rcx, [rbp+188h]; this
0x1800057aa  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800057b1  mov     edx, 0A0Bh; void *
0x1800057b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057bc  mov     rcx, [rbp+188h]; this
0x1800057c3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800057ca  mov     edx, 0E01h; void *
0x1800057cf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800057d5  mov     rcx, [rbp+188h]; this
0x1800057dc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800057e3  mov     edx, 0A15h; void *
0x1800057e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057ee  mov     rcx, [rbp+188h]; this
0x1800057f5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800057fc  mov     edx, 0A0Bh; void *
0x180005801  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005807  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000580d  mov     rcx, [rbp+188h]; this
0x180005814  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000581b  mov     edx, 0A15h; void *
0x180005820  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005826  mov     rcx, [rbp+188h]; this
0x18000582d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005834  mov     edx, 0A0Bh; void *
0x180005839  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000583f  mov     rcx, [rbp+188h]; this
0x180005846  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000584d  mov     edx, 0A15h; void *
0x180005852  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
