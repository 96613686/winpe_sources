# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003828`
- end: `0x180003bf0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000628c`

## callees

- `0x180003828`
- `0x180004bb4`
- `0x180005654`
- `0x180006014`
- `0x1800075e4`
- `0x1800099f8`
- `0x180009ff4`
- `0x18000a47c`
- `0x18000b3f4`
- `0x18000b404`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180003957`
- `KERNEL32!ReleaseMutex` at `0x180003a95`
- `KERNEL32!ReleaseMutex` at `0x180003b05`
- `KERNEL32!ReleaseMutex` at `0x180003957`
- `KERNEL32!ReleaseMutex` at `0x180003a95`
- `KERNEL32!ReleaseMutex` at `0x180003b05`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800038c1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800038c1`
- `KERNEL32!CloseHandle` at `0x180003968`
- `KERNEL32!CloseHandle` at `0x180003a38`
- `KERNEL32!CloseHandle` at `0x180003a50`
- `KERNEL32!CloseHandle` at `0x180003aa6`
- `KERNEL32!CloseHandle` at `0x180003b1b`
- `KERNEL32!CloseHandle` at `0x180003968`
- `KERNEL32!CloseHandle` at `0x180003a38`
- `KERNEL32!CloseHandle` at `0x180003a50`
- `KERNEL32!CloseHandle` at `0x180003aa6`
- `KERNEL32!CloseHandle` at `0x180003b1b`
- `KERNEL32!CreateMutexExW` at `0x1800038a0`
- `KERNEL32!CreateMutexExW` at `0x1800038a0`
- `KERNEL32!GetCurrentProcessId` at `0x180003861`
- `KERNEL32!GetCurrentProcessId` at `0x180003861`
- `KERNEL32!GetProcessHeap` at `0x180003a5e`
- `KERNEL32!GetProcessHeap` at `0x180003a5e`
- `KERNEL32!HeapFree` at `0x180003a6c`
- `KERNEL32!HeapFree` at `0x180003a6c`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180003828  mov     [rsp-8+arg_10], rbx
0x18000382d  push    rbp
0x18000382e  push    rsi
0x18000382f  push    rdi
0x180003830  push    r14
0x180003832  push    r15
0x180003834  lea     rbp, [rsp-160h]
0x18000383c  sub     rsp, 260h
0x180003843  mov     rax, cs:__security_cookie
0x18000384a  xor     rax, rsp
0x18000384d  mov     [rbp+180h+var_30], rax
0x180003854  mov     r15, rdx
0x180003857  mov     qword ptr [rdx], 0
0x18000385e  mov     rbx, rcx
0x180003861  call    cs:__imp_GetCurrentProcessId
0x180003867  mov     r14d, 78h ; 'x'
0x18000386d  mov     [rsp+280h+var_258], rbx
0x180003872  mov     r9d, eax
0x180003875  mov     [rsp+280h+var_260], r14d; int
0x18000387a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003881  mov     edx, 104h; unsigned __int64
0x180003886  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000388b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003890  mov     r9d, 1F0001h; dwDesiredAccess
0x180003896  lea     rdx, [rsp+280h+Name]; lpName
0x18000389b  xor     r8d, r8d; dwFlags
0x18000389e  xor     ecx, ecx; lpMutexAttributes
0x1800038a0  call    cs:__imp_CreateMutexExW
0x1800038a6  mov     rbx, rax
0x1800038a9  test    rax, rax
0x1800038ac  jnz     short loc_1800038B8
0x1800038ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800038b3  jmp     loc_180003B27
0x1800038b8  xor     r8d, r8d; bAlertable
0x1800038bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800038be  mov     rcx, rbx; hHandle
0x1800038c1  call    cs:__imp_WaitForSingleObjectEx
0x1800038c7  cmp     eax, 102h
0x1800038cc  jz      short loc_1800038DE
0x1800038ce  test    eax, 0FFFFFF7Fh
0x1800038d3  jnz     loc_180003B5F
0x1800038d9  mov     rdi, rbx
0x1800038dc  jmp     short loc_1800038E0
0x1800038de  xor     edi, edi
0x1800038e0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800038e5  mov     [rsp+280h+hObject], 0
0x1800038ee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800038f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800038f8  mov     esi, eax
0x1800038fa  test    eax, eax
0x1800038fc  jns     short loc_18000397D
0x1800038fe  mov     rcx, [rbp+188h]; this
0x180003905  lea     r8, aWil; "wil"
0x18000390c  mov     r9d, eax; char *
0x18000390f  mov     edx, 66h ; 'f'; void *
0x180003914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003919  mov     rcx, [rbp+188h]; this
0x180003920  lea     r8, aWil; "wil"
0x180003927  mov     r9d, esi; char *
0x18000392a  mov     edx, 6Fh ; 'o'; void *
0x18000392f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003934  mov     rcx, [rbp+188h]; this
0x18000393b  lea     r8, aWil; "wil"
0x180003942  mov     r9d, esi; char *
0x180003945  mov     edx, 12Eh; void *
0x18000394a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000394f  test    rdi, rdi
0x180003952  jz      short loc_180003965
0x180003954  mov     rcx, rdi; hMutex
0x180003957  call    cs:__imp_ReleaseMutex
0x18000395d  test    eax, eax
0x18000395f  jz      loc_180003B6C
0x180003965  mov     rcx, rbx; hObject
0x180003968  call    cs:__imp_CloseHandle
0x18000396e  test    eax, eax
0x180003970  jz      loc_180003B7E
0x180003976  mov     eax, esi
0x180003978  jmp     loc_180003B27
0x18000397d  mov     rax, [rsp+280h+hObject]
0x180003982  lea     rcx, ds:0[rax*4]
0x18000398a  test    rcx, rcx
0x18000398d  jz      short loc_18000399D
0x18000398f  mov     [r15], rcx
0x180003992  mov     eax, [rcx]
0x180003994  inc     eax
0x180003996  mov     [rcx], eax
0x180003998  jmp     loc_180003AFD
0x18000399d  mov     rdx, r14; dwBytes
0x1800039a0  mov     qword ptr [r15], 0
0x1800039a7  mov     ecx, 8; dwFlags
0x1800039ac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800039b1  mov     rsi, rax
0x1800039b4  test    rax, rax
0x1800039b7  jnz     short loc_1800039DF
0x1800039b9  mov     rcx, [rbp+188h]; this
0x1800039c0  lea     r8, aWil; "wil"
0x1800039c7  mov     r14d, 8007000Eh
0x1800039cd  mov     edx, 14Bh; void *
0x1800039d2  mov     r9d, r14d; char *
0x1800039d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039da  jmp     loc_180003A72
0x1800039df  xorps   xmm0, xmm0
0x1800039e2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800039e8  test    sil, 3
0x1800039ec  jnz     loc_180003B90
0x1800039f2  mov     r9, rsi
0x1800039f5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800039fa  shr     r9, 2; unsigned __int64
0x1800039fe  lea     rcx, [rsp+280h+hObject]; this
0x180003a03  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003a08  mov     r14d, eax
0x180003a0b  test    eax, eax
0x180003a0d  jns     loc_180003AB9
0x180003a13  mov     rcx, [rbp+188h]; this
0x180003a1a  lea     r8, aWil; "wil"
0x180003a21  mov     r9d, eax; char *
0x180003a24  mov     edx, 14Eh; void *
0x180003a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a2e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003a33  test    rcx, rcx
0x180003a36  jz      short loc_180003A46
0x180003a38  call    cs:__imp_CloseHandle
0x180003a3e  test    eax, eax
0x180003a40  jz      loc_180003B96
0x180003a46  mov     rcx, [rsp+280h+hObject]; hObject
0x180003a4b  test    rcx, rcx
0x180003a4e  jz      short loc_180003A5E
0x180003a50  call    cs:__imp_CloseHandle
0x180003a56  test    eax, eax
0x180003a58  jz      loc_180003BA8
0x180003a5e  call    cs:__imp_GetProcessHeap
0x180003a64  mov     r8, rsi; lpMem
0x180003a67  xor     edx, edx; dwFlags
0x180003a69  mov     rcx, rax; hHeap
0x180003a6c  call    cs:__imp_HeapFree
0x180003a72  mov     rcx, [rbp+188h]; this
0x180003a79  lea     r8, aWil; "wil"
0x180003a80  mov     r9d, r14d; char *
0x180003a83  mov     edx, 137h; void *
0x180003a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a8d  test    rdi, rdi
0x180003a90  jz      short loc_180003AA3
0x180003a92  mov     rcx, rdi; hMutex
0x180003a95  call    cs:__imp_ReleaseMutex
0x180003a9b  test    eax, eax
0x180003a9d  jz      loc_180003BBA
0x180003aa3  mov     rcx, rbx; hObject
0x180003aa6  call    cs:__imp_CloseHandle
0x180003aac  test    eax, eax
0x180003aae  jz      loc_180003BCC
0x180003ab4  mov     eax, r14d
0x180003ab7  jmp     short loc_180003B27
0x180003ab9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003abe  xor     edx, edx; Val
0x180003ac0  mov     dword ptr [rsi], 1
0x180003ac6  lea     rcx, [rsi+22h]; void *
0x180003aca  mov     [rsi+8], rbx
0x180003ace  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003ad3  lea     r8d, [rdx+56h]; Size
0x180003ad7  call    memset_0
0x180003adc  xor     edx, edx; Val
0x180003ade  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003ae4  lea     rcx, [rsi+28h]; void *
0x180003ae8  mov     dword ptr [rsi+24h], 1
0x180003aef  lea     r8d, [rdx+50h]; Size
0x180003af3  call    memset_0
0x180003af8  xor     ebx, ebx
0x180003afa  mov     [r15], rsi
0x180003afd  test    rdi, rdi
0x180003b00  jz      short loc_180003B13
0x180003b02  mov     rcx, rdi; hMutex
0x180003b05  call    cs:__imp_ReleaseMutex
0x180003b0b  test    eax, eax
0x180003b0d  jz      loc_180003BDE
0x180003b13  test    rbx, rbx
0x180003b16  jz      short loc_180003B25
0x180003b18  mov     rcx, rbx; hObject
0x180003b1b  call    cs:__imp_CloseHandle
0x180003b21  test    eax, eax
0x180003b23  jz      short loc_180003B4D
0x180003b25  xor     eax, eax
0x180003b27  mov     rcx, [rbp+180h+var_30]
0x180003b2e  xor     rcx, rsp; StackCookie
0x180003b31  call    __security_check_cookie
0x180003b36  mov     rbx, [rsp+280h+arg_10]
0x180003b3e  add     rsp, 260h
0x180003b45  pop     r15
0x180003b47  pop     r14
0x180003b49  pop     rdi
0x180003b4a  pop     rsi
0x180003b4b  pop     rbp
0x180003b4c  retn
0x180003b4d  mov     rcx, [rbp+188h]; this
0x180003b54  mov     edx, 0A0Bh; void *
0x180003b59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b5f  mov     rcx, [rbp+188h]; this
0x180003b66  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003b6c  mov     rcx, [rbp+188h]; this
0x180003b73  mov     edx, 0A15h; void *
0x180003b78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b7e  mov     rcx, [rbp+188h]; this
0x180003b85  mov     edx, 0A0Bh; void *
0x180003b8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b96  mov     rcx, [rbp+188h]; this
0x180003b9d  mov     edx, 0A0Bh; void *
0x180003ba2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ba8  mov     rcx, [rbp+188h]; this
0x180003baf  mov     edx, 0A0Bh; void *
0x180003bb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bba  mov     rcx, [rbp+188h]; this
0x180003bc1  mov     edx, 0A15h; void *
0x180003bc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bcc  mov     rcx, [rbp+188h]; this
0x180003bd3  mov     edx, 0A0Bh; void *
0x180003bd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bde  mov     rcx, [rbp+188h]; this
0x180003be5  mov     edx, 0A15h; void *
0x180003bea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
