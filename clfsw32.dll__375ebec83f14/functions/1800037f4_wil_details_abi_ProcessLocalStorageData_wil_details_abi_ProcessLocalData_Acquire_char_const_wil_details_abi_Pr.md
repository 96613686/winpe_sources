# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800037f4`
- end: `0x180003b99`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004ef0`

## callees

- `0x180003588`
- `0x1800037f4`
- `0x180003f78`
- `0x180004318`
- `0x180004c70`
- `0x180005910`
- `0x180006ca8`
- `0x1800071bc`
- `0x180007608`
- `0x180007e10`
- `0x180014dce`
- `0x180014e00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000382d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000382d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003920`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003acb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003920`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003acb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003899`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003899`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003872`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003872`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned __int64 v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v42[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42[0]);
  if ( 4 * v42[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v42 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v42, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v42[0];
  v34 = v42[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v42[0] = 0;
  *((_QWORD *)v25 + 3) = v34;
  v42[1] = 0;
  memset_0((char *)v25 + 34, 0, 0x56u);
  *((_WORD *)v25 + 16) = 88;
  v25[9] = 1;
  memset_0(v25 + 10, 0, 0x50u);
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x1800037f4  mov     [rsp-8+arg_10], rbx
0x1800037f9  push    rbp
0x1800037fa  push    rsi
0x1800037fb  push    rdi
0x1800037fc  push    r14
0x1800037fe  push    r15
0x180003800  lea     rbp, [rsp-160h]
0x180003808  sub     rsp, 260h
0x18000380f  mov     rax, cs:__security_cookie
0x180003816  xor     rax, rsp
0x180003819  mov     [rbp+180h+var_30], rax
0x180003820  mov     r15, rdx
0x180003823  mov     qword ptr [rdx], 0
0x18000382a  mov     rbx, rcx
0x18000382d  call    cs:__imp_GetCurrentProcessId
0x180003834  nop     dword ptr [rax+rax+00h]
0x180003839  mov     r14d, 78h ; 'x'
0x18000383f  mov     [rsp+280h+var_258], rbx
0x180003844  mov     r9d, eax
0x180003847  mov     [rsp+280h+var_260], r14d; int
0x18000384c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003853  mov     edx, 104h; unsigned __int64
0x180003858  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000385d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003862  mov     r9d, 1F0001h; dwDesiredAccess
0x180003868  lea     rdx, [rsp+280h+Name]; lpName
0x18000386d  xor     r8d, r8d; dwFlags
0x180003870  xor     ecx, ecx; lpMutexAttributes
0x180003872  call    cs:__imp_CreateMutexExW
0x180003879  nop     dword ptr [rax+rax+00h]
0x18000387e  mov     rbx, rax
0x180003881  test    rax, rax
0x180003884  jnz     short loc_180003890
0x180003886  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000388b  jmp     loc_180003AF9
0x180003890  xor     r8d, r8d; bAlertable
0x180003893  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003896  mov     rcx, rbx; hHandle
0x180003899  call    cs:__imp_WaitForSingleObjectEx
0x1800038a0  nop     dword ptr [rax+rax+00h]
0x1800038a5  cmp     eax, 102h
0x1800038aa  jz      short loc_1800038BC
0x1800038ac  test    eax, 0FFFFFF7Fh
0x1800038b1  jnz     loc_180003B44
0x1800038b7  mov     rdi, rbx
0x1800038ba  jmp     short loc_1800038BE
0x1800038bc  xor     edi, edi
0x1800038be  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800038c3  mov     [rsp+280h+var_250], 0
0x1800038cc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800038d1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800038d6  mov     esi, eax
0x1800038d8  test    eax, eax
0x1800038da  jns     short loc_180003952
0x1800038dc  mov     rcx, [rbp+188h]; this
0x1800038e3  mov     r9d, eax; char *
0x1800038e6  mov     edx, 66h ; 'f'; void *
0x1800038eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038f0  mov     rcx, [rbp+188h]; this
0x1800038f7  mov     r9d, esi; char *
0x1800038fa  mov     edx, 6Fh ; 'o'; void *
0x1800038ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003904  mov     rcx, [rbp+188h]; this
0x18000390b  mov     r9d, esi; char *
0x18000390e  mov     edx, 12Eh; void *
0x180003913  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003918  test    rdi, rdi
0x18000391b  jz      short loc_180003934
0x18000391d  mov     rcx, rdi; hMutex
0x180003920  call    cs:__imp_ReleaseMutex
0x180003927  nop     dword ptr [rax+rax+00h]
0x18000392c  test    eax, eax
0x18000392e  jz      loc_180003B51
0x180003934  mov     rcx, rbx; hObject
0x180003937  call    cs:__imp_CloseHandle
0x18000393e  nop     dword ptr [rax+rax+00h]
0x180003943  test    eax, eax
0x180003945  jz      loc_180003B63
0x18000394b  mov     eax, esi
0x18000394d  jmp     loc_180003AF9
0x180003952  mov     rax, [rsp+280h+var_250]
0x180003957  lea     rcx, ds:0[rax*4]
0x18000395f  test    rcx, rcx
0x180003962  jz      short loc_180003972
0x180003964  mov     [r15], rcx
0x180003967  mov     eax, [rcx]
0x180003969  inc     eax
0x18000396b  mov     [rcx], eax
0x18000396d  jmp     loc_180003AC3
0x180003972  mov     rdx, r14; dwBytes
0x180003975  mov     qword ptr [r15], 0
0x18000397c  mov     ecx, 8; dwFlags
0x180003981  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003986  mov     r14, rax
0x180003989  test    rax, rax
0x18000398c  jnz     short loc_1800039A9
0x18000398e  mov     rcx, [rbp+188h]; this
0x180003995  mov     esi, 8007000Eh
0x18000399a  mov     r9d, esi; char *
0x18000399d  mov     edx, 14Bh; void *
0x1800039a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039a7  jmp     short loc_180003A0C
0x1800039a9  xorps   xmm0, xmm0
0x1800039ac  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800039b1  mov     r8, r14; void *
0x1800039b4  lea     rcx, [rsp+280h+var_250]; this
0x1800039b9  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800039bf  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x1800039c4  mov     esi, eax
0x1800039c6  test    eax, eax
0x1800039c8  jns     loc_180003A58
0x1800039ce  mov     rcx, [rbp+188h]; this
0x1800039d5  mov     r9d, eax; char *
0x1800039d8  mov     edx, 14Eh; void *
0x1800039dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039e2  lea     rcx, [rsp+280h+var_250]; this
0x1800039e7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800039ec  call    cs:__imp_GetProcessHeap
0x1800039f3  nop     dword ptr [rax+rax+00h]
0x1800039f8  mov     r8, r14; lpMem
0x1800039fb  xor     edx, edx; dwFlags
0x1800039fd  mov     rcx, rax; hHeap
0x180003a00  call    cs:__imp_HeapFree
0x180003a07  nop     dword ptr [rax+rax+00h]
0x180003a0c  mov     rcx, [rbp+188h]; this
0x180003a13  mov     r9d, esi; char *
0x180003a16  mov     edx, 137h; void *
0x180003a1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a20  test    rdi, rdi
0x180003a23  jz      short loc_180003A3C
0x180003a25  mov     rcx, rdi; hMutex
0x180003a28  call    cs:__imp_ReleaseMutex
0x180003a2f  nop     dword ptr [rax+rax+00h]
0x180003a34  test    eax, eax
0x180003a36  jz      loc_180003B75
0x180003a3c  mov     rcx, rbx; hObject
0x180003a3f  call    cs:__imp_CloseHandle
0x180003a46  nop     dword ptr [rax+rax+00h]
0x180003a4b  test    eax, eax
0x180003a4d  jz      loc_180003B32
0x180003a53  jmp     loc_18000394B
0x180003a58  mov     rax, [rsp+280h+var_250]
0x180003a5d  lea     rcx, [r14+22h]; void *
0x180003a61  xor     edx, edx; Val
0x180003a63  mov     [r14+10h], rax
0x180003a67  mov     rax, [rsp+280h+var_250+8]
0x180003a6c  mov     dword ptr [r14], 1
0x180003a73  mov     [r14+8], rbx
0x180003a77  lea     r8d, [rdx+56h]; Size
0x180003a7b  mov     [rsp+280h+var_250], 0
0x180003a84  mov     [r14+18h], rax
0x180003a88  mov     [rsp+280h+var_250+8], 0
0x180003a91  call    memset_0
0x180003a96  xor     edx, edx; Val
0x180003a98  mov     word ptr [r14+20h], 58h ; 'X'
0x180003a9f  lea     rcx, [r14+28h]; void *
0x180003aa3  mov     dword ptr [r14+24h], 1
0x180003aab  lea     r8d, [rdx+50h]; Size
0x180003aaf  call    memset_0
0x180003ab4  lea     rcx, [rsp+280h+var_250]; this
0x180003ab9  mov     [r15], r14
0x180003abc  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003ac1  xor     ebx, ebx
0x180003ac3  test    rdi, rdi
0x180003ac6  jz      short loc_180003ADF
0x180003ac8  mov     rcx, rdi; hMutex
0x180003acb  call    cs:__imp_ReleaseMutex
0x180003ad2  nop     dword ptr [rax+rax+00h]
0x180003ad7  test    eax, eax
0x180003ad9  jz      loc_180003B87
0x180003adf  test    rbx, rbx
0x180003ae2  jz      short loc_180003AF7
0x180003ae4  mov     rcx, rbx; hObject
0x180003ae7  call    cs:__imp_CloseHandle
0x180003aee  nop     dword ptr [rax+rax+00h]
0x180003af3  test    eax, eax
0x180003af5  jz      short loc_180003B20
0x180003af7  xor     eax, eax
0x180003af9  mov     rcx, [rbp+180h+var_30]
0x180003b00  xor     rcx, rsp; StackCookie
0x180003b03  call    __security_check_cookie
0x180003b08  mov     rbx, [rsp+280h+arg_10]
0x180003b10  add     rsp, 260h
0x180003b17  pop     r15
0x180003b19  pop     r14
0x180003b1b  pop     rdi
0x180003b1c  pop     rsi
0x180003b1d  pop     rbp
0x180003b1e  retn
0x180003b20  mov     rcx, [rbp+188h]; this
0x180003b27  mov     edx, 0A0Bh; void *
0x180003b2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b32  mov     rcx, [rbp+188h]; this
0x180003b39  mov     edx, 0A0Bh; void *
0x180003b3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b44  mov     rcx, [rbp+188h]; this
0x180003b4b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003b51  mov     rcx, [rbp+188h]; this
0x180003b58  mov     edx, 0A15h; void *
0x180003b5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b63  mov     rcx, [rbp+188h]; this
0x180003b6a  mov     edx, 0A0Bh; void *
0x180003b6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b75  mov     rcx, [rbp+188h]; this
0x180003b7c  mov     edx, 0A15h; void *
0x180003b81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b87  mov     rcx, [rbp+188h]; this
0x180003b8e  mov     edx, 0A15h; void *
0x180003b93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
