# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14001339c`
- end: `0x14001373a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140014afc`

## callees

- `0x14001339c`
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

- `KERNEL32!HeapFree` at `0x1400135bd`
- `KERNEL32!HeapFree` at `0x1400135bd`
- `KERNEL32!GetCurrentProcessId` at `0x1400133d5`
- `KERNEL32!GetCurrentProcessId` at `0x1400133d5`
- `KERNEL32!GetProcessHeap` at `0x1400135af`
- `KERNEL32!GetProcessHeap` at `0x1400135af`
- `KERNEL32!ReleaseMutex` at `0x1400134b6`
- `KERNEL32!ReleaseMutex` at `0x1400135df`
- `KERNEL32!ReleaseMutex` at `0x14001364f`
- `KERNEL32!ReleaseMutex` at `0x1400134b6`
- `KERNEL32!ReleaseMutex` at `0x1400135df`
- `KERNEL32!ReleaseMutex` at `0x14001364f`
- `KERNEL32!WaitForSingleObjectEx` at `0x140013435`
- `KERNEL32!WaitForSingleObjectEx` at `0x140013435`
- `KERNEL32!CreateMutexExW` at `0x140013414`
- `KERNEL32!CreateMutexExW` at `0x140013414`
- `KERNEL32!CloseHandle` at `0x1400134c7`
- `KERNEL32!CloseHandle` at `0x140013589`
- `KERNEL32!CloseHandle` at `0x1400135a1`
- `KERNEL32!CloseHandle` at `0x1400135f0`
- `KERNEL32!CloseHandle` at `0x140013665`
- `KERNEL32!CloseHandle` at `0x1400134c7`
- `KERNEL32!CloseHandle` at `0x140013589`
- `KERNEL32!CloseHandle` at `0x1400135a1`
- `KERNEL32!CloseHandle` at `0x1400135f0`
- `KERNEL32!CloseHandle` at `0x140013665`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x14001339c  mov     [rsp-8+arg_10], rbx
0x1400133a1  push    rbp
0x1400133a2  push    rsi
0x1400133a3  push    rdi
0x1400133a4  push    r14
0x1400133a6  push    r15
0x1400133a8  lea     rbp, [rsp-160h]
0x1400133b0  sub     rsp, 260h
0x1400133b7  mov     rax, cs:__security_cookie
0x1400133be  xor     rax, rsp
0x1400133c1  mov     [rbp+180h+var_30], rax
0x1400133c8  mov     r15, rdx
0x1400133cb  mov     qword ptr [rdx], 0
0x1400133d2  mov     rbx, rcx
0x1400133d5  call    cs:__imp_GetCurrentProcessId
0x1400133db  mov     r14d, 78h ; 'x'
0x1400133e1  mov     [rsp+280h+var_258], rbx
0x1400133e6  mov     r9d, eax
0x1400133e9  mov     [rsp+280h+var_260], r14d; int
0x1400133ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400133f5  mov     edx, 104h; unsigned __int64
0x1400133fa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400133ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013404  mov     r9d, 1F0001h; dwDesiredAccess
0x14001340a  lea     rdx, [rsp+280h+Name]; lpName
0x14001340f  xor     r8d, r8d; dwFlags
0x140013412  xor     ecx, ecx; lpMutexAttributes
0x140013414  call    cs:__imp_CreateMutexExW
0x14001341a  mov     rbx, rax
0x14001341d  test    rax, rax
0x140013420  jnz     short loc_14001342C
0x140013422  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140013427  jmp     loc_140013671
0x14001342c  xor     r8d, r8d; bAlertable
0x14001342f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140013432  mov     rcx, rbx; hHandle
0x140013435  call    cs:__imp_WaitForSingleObjectEx
0x14001343b  cmp     eax, 102h
0x140013440  jz      short loc_140013452
0x140013442  test    eax, 0FFFFFF7Fh
0x140013447  jnz     loc_1400136A9
0x14001344d  mov     rdi, rbx
0x140013450  jmp     short loc_140013454
0x140013452  xor     edi, edi
0x140013454  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140013459  mov     [rsp+280h+hObject], 0
0x140013462  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140013467  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14001346c  mov     esi, eax
0x14001346e  test    eax, eax
0x140013470  jns     short loc_1400134DC
0x140013472  mov     rcx, [rbp+188h]; this
0x140013479  mov     r9d, eax; char *
0x14001347c  mov     edx, 66h ; 'f'; void *
0x140013481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013486  mov     rcx, [rbp+188h]; this
0x14001348d  mov     r9d, esi; char *
0x140013490  mov     edx, 6Fh ; 'o'; void *
0x140013495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001349a  mov     rcx, [rbp+188h]; this
0x1400134a1  mov     r9d, esi; char *
0x1400134a4  mov     edx, 12Eh; void *
0x1400134a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400134ae  test    rdi, rdi
0x1400134b1  jz      short loc_1400134C4
0x1400134b3  mov     rcx, rdi; hMutex
0x1400134b6  call    cs:__imp_ReleaseMutex
0x1400134bc  test    eax, eax
0x1400134be  jz      loc_1400136B6
0x1400134c4  mov     rcx, rbx; hObject
0x1400134c7  call    cs:__imp_CloseHandle
0x1400134cd  test    eax, eax
0x1400134cf  jz      loc_1400136C8
0x1400134d5  mov     eax, esi
0x1400134d7  jmp     loc_140013671
0x1400134dc  mov     rax, [rsp+280h+hObject]
0x1400134e1  lea     rcx, ds:0[rax*4]
0x1400134e9  test    rcx, rcx
0x1400134ec  jz      short loc_1400134FC
0x1400134ee  mov     [r15], rcx
0x1400134f1  mov     eax, [rcx]
0x1400134f3  inc     eax
0x1400134f5  mov     [rcx], eax
0x1400134f7  jmp     loc_140013647
0x1400134fc  mov     rdx, r14; dwBytes
0x1400134ff  mov     qword ptr [r15], 0
0x140013506  mov     ecx, 8; dwFlags
0x14001350b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140013510  mov     rsi, rax
0x140013513  test    rax, rax
0x140013516  jnz     short loc_140013537
0x140013518  mov     rcx, [rbp+188h]; this
0x14001351f  mov     r14d, 8007000Eh
0x140013525  mov     r9d, r14d; char *
0x140013528  mov     edx, 14Bh; void *
0x14001352d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013532  jmp     loc_1400135C3
0x140013537  xorps   xmm0, xmm0
0x14001353a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140013540  test    sil, 3
0x140013544  jnz     loc_1400136DA
0x14001354a  mov     r9, rsi
0x14001354d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140013552  shr     r9, 2; unsigned __int64
0x140013556  lea     rcx, [rsp+280h+hObject]; this
0x14001355b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140013560  mov     r14d, eax
0x140013563  test    eax, eax
0x140013565  jns     loc_140013603
0x14001356b  mov     rcx, [rbp+188h]; this
0x140013572  mov     r9d, eax; char *
0x140013575  mov     edx, 14Eh; void *
0x14001357a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001357f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140013584  test    rcx, rcx
0x140013587  jz      short loc_140013597
0x140013589  call    cs:__imp_CloseHandle
0x14001358f  test    eax, eax
0x140013591  jz      loc_1400136E0
0x140013597  mov     rcx, [rsp+280h+hObject]; hObject
0x14001359c  test    rcx, rcx
0x14001359f  jz      short loc_1400135AF
0x1400135a1  call    cs:__imp_CloseHandle
0x1400135a7  test    eax, eax
0x1400135a9  jz      loc_1400136F2
0x1400135af  call    cs:__imp_GetProcessHeap
0x1400135b5  mov     r8, rsi; lpMem
0x1400135b8  xor     edx, edx; dwFlags
0x1400135ba  mov     rcx, rax; hHeap
0x1400135bd  call    cs:__imp_HeapFree
0x1400135c3  mov     rcx, [rbp+188h]; this
0x1400135ca  mov     r9d, r14d; char *
0x1400135cd  mov     edx, 137h; void *
0x1400135d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400135d7  test    rdi, rdi
0x1400135da  jz      short loc_1400135ED
0x1400135dc  mov     rcx, rdi; hMutex
0x1400135df  call    cs:__imp_ReleaseMutex
0x1400135e5  test    eax, eax
0x1400135e7  jz      loc_140013704
0x1400135ed  mov     rcx, rbx; hObject
0x1400135f0  call    cs:__imp_CloseHandle
0x1400135f6  test    eax, eax
0x1400135f8  jz      loc_140013716
0x1400135fe  mov     eax, r14d
0x140013601  jmp     short loc_140013671
0x140013603  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140013608  xor     edx, edx; Val
0x14001360a  mov     dword ptr [rsi], 1
0x140013610  lea     rcx, [rsi+22h]; void *
0x140013614  mov     [rsi+8], rbx
0x140013618  movdqu  xmmword ptr [rsi+10h], xmm0
0x14001361d  lea     r8d, [rdx+56h]; Size
0x140013621  call    memset_0
0x140013626  xor     edx, edx; Val
0x140013628  mov     word ptr [rsi+20h], 58h ; 'X'
0x14001362e  lea     rcx, [rsi+28h]; void *
0x140013632  mov     dword ptr [rsi+24h], 1
0x140013639  lea     r8d, [rdx+50h]; Size
0x14001363d  call    memset_0
0x140013642  xor     ebx, ebx
0x140013644  mov     [r15], rsi
0x140013647  test    rdi, rdi
0x14001364a  jz      short loc_14001365D
0x14001364c  mov     rcx, rdi; hMutex
0x14001364f  call    cs:__imp_ReleaseMutex
0x140013655  test    eax, eax
0x140013657  jz      loc_140013728
0x14001365d  test    rbx, rbx
0x140013660  jz      short loc_14001366F
0x140013662  mov     rcx, rbx; hObject
0x140013665  call    cs:__imp_CloseHandle
0x14001366b  test    eax, eax
0x14001366d  jz      short loc_140013697
0x14001366f  xor     eax, eax
0x140013671  mov     rcx, [rbp+180h+var_30]
0x140013678  xor     rcx, rsp; StackCookie
0x14001367b  call    __security_check_cookie
0x140013680  mov     rbx, [rsp+280h+arg_10]
0x140013688  add     rsp, 260h
0x14001368f  pop     r15
0x140013691  pop     r14
0x140013693  pop     rdi
0x140013694  pop     rsi
0x140013695  pop     rbp
0x140013696  retn
0x140013697  mov     rcx, [rbp+188h]; this
0x14001369e  mov     edx, 0A0Bh; void *
0x1400136a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136a9  mov     rcx, [rbp+188h]; this
0x1400136b0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400136b6  mov     rcx, [rbp+188h]; this
0x1400136bd  mov     edx, 0A15h; void *
0x1400136c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136c8  mov     rcx, [rbp+188h]; this
0x1400136cf  mov     edx, 0A0Bh; void *
0x1400136d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136da  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400136e0  mov     rcx, [rbp+188h]; this
0x1400136e7  mov     edx, 0A0Bh; void *
0x1400136ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400136f2  mov     rcx, [rbp+188h]; this
0x1400136f9  mov     edx, 0A0Bh; void *
0x1400136fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013704  mov     rcx, [rbp+188h]; this
0x14001370b  mov     edx, 0A15h; void *
0x140013710  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013716  mov     rcx, [rbp+188h]; this
0x14001371d  mov     edx, 0A0Bh; void *
0x140013722  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013728  mov     rcx, [rbp+188h]; this
0x14001372f  mov     edx, 0A15h; void *
0x140013734  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
