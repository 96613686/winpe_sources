# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18008bee0`
- end: `0x18008c27e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18008cd5c`

## callees

- `0x1800115f0`
- `0x18001ac40`
- `0x18008bee0`
- `0x18008c284`
- `0x18008c4b0`
- `0x18008caf8`
- `0x18008d5f8`
- `0x18008d8b4`
- `0x18008dc10`
- `0x18008dfcc`
- `0x18008dfdc`
- `0x18008ea60`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18008c101`
- `KERNEL32!HeapFree` at `0x18008c101`
- `KERNEL32!GetProcessHeap` at `0x18008c0f3`
- `KERNEL32!GetProcessHeap` at `0x18008c0f3`
- `KERNEL32!CloseHandle` at `0x18008c00b`
- `KERNEL32!CloseHandle` at `0x18008c0cd`
- `KERNEL32!CloseHandle` at `0x18008c0e5`
- `KERNEL32!CloseHandle` at `0x18008c134`
- `KERNEL32!CloseHandle` at `0x18008c1a9`
- `KERNEL32!CloseHandle` at `0x18008c00b`
- `KERNEL32!CloseHandle` at `0x18008c0cd`
- `KERNEL32!CloseHandle` at `0x18008c0e5`
- `KERNEL32!CloseHandle` at `0x18008c134`
- `KERNEL32!CloseHandle` at `0x18008c1a9`
- `KERNEL32!GetCurrentProcessId` at `0x18008bf19`
- `KERNEL32!GetCurrentProcessId` at `0x18008bf19`
- `KERNEL32!ReleaseMutex` at `0x18008bffa`
- `KERNEL32!ReleaseMutex` at `0x18008c123`
- `KERNEL32!ReleaseMutex` at `0x18008c193`
- `KERNEL32!ReleaseMutex` at `0x18008bffa`
- `KERNEL32!ReleaseMutex` at `0x18008c123`
- `KERNEL32!ReleaseMutex` at `0x18008c193`
- `KERNEL32!WaitForSingleObjectEx` at `0x18008bf79`
- `KERNEL32!WaitForSingleObjectEx` at `0x18008bf79`
- `KERNEL32!CreateMutexExW` at `0x18008bf58`
- `KERNEL32!CreateMutexExW` at `0x18008bf58`

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
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
      memset((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset(v26 + 5, 0, 0x50u);
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
0x18008bee0  mov     [rsp-8+arg_10], rbx
0x18008bee5  push    rbp
0x18008bee6  push    rsi
0x18008bee7  push    rdi
0x18008bee8  push    r14
0x18008beea  push    r15
0x18008beec  lea     rbp, [rsp-160h]
0x18008bef4  sub     rsp, 260h
0x18008befb  mov     rax, cs:__security_cookie
0x18008bf02  xor     rax, rsp
0x18008bf05  mov     [rbp+180h+var_30], rax
0x18008bf0c  mov     r15, rdx
0x18008bf0f  mov     qword ptr [rdx], 0
0x18008bf16  mov     rbx, rcx
0x18008bf19  call    cs:__imp_GetCurrentProcessId
0x18008bf1f  mov     r14d, 78h ; 'x'
0x18008bf25  mov     [rsp+280h+var_258], rbx
0x18008bf2a  mov     r9d, eax
0x18008bf2d  mov     [rsp+280h+var_260], r14d; int
0x18008bf32  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18008bf39  mov     edx, 104h; unsigned __int64
0x18008bf3e  lea     rcx, [rsp+280h+Name]; Buffer
0x18008bf43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008bf48  mov     r9d, 1F0001h; dwDesiredAccess
0x18008bf4e  lea     rdx, [rsp+280h+Name]; lpName
0x18008bf53  xor     r8d, r8d; dwFlags
0x18008bf56  xor     ecx, ecx; lpMutexAttributes
0x18008bf58  call    cs:__imp_CreateMutexExW
0x18008bf5e  mov     rbx, rax
0x18008bf61  test    rax, rax
0x18008bf64  jnz     short loc_18008BF70
0x18008bf66  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008bf6b  jmp     loc_18008C1B5
0x18008bf70  xor     r8d, r8d; bAlertable
0x18008bf73  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008bf76  mov     rcx, rbx; hHandle
0x18008bf79  call    cs:__imp_WaitForSingleObjectEx
0x18008bf7f  cmp     eax, 102h
0x18008bf84  jz      short loc_18008BF96
0x18008bf86  test    eax, 0FFFFFF7Fh
0x18008bf8b  jnz     loc_18008C1ED
0x18008bf91  mov     rdi, rbx
0x18008bf94  jmp     short loc_18008BF98
0x18008bf96  xor     edi, edi
0x18008bf98  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18008bf9d  mov     [rsp+280h+hObject], 0
0x18008bfa6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18008bfab  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18008bfb0  mov     esi, eax
0x18008bfb2  test    eax, eax
0x18008bfb4  jns     short loc_18008C020
0x18008bfb6  mov     rcx, [rbp+188h]; this
0x18008bfbd  mov     r9d, eax; char *
0x18008bfc0  mov     edx, 66h ; 'f'; void *
0x18008bfc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bfca  mov     rcx, [rbp+188h]; this
0x18008bfd1  mov     r9d, esi; char *
0x18008bfd4  mov     edx, 6Fh ; 'o'; void *
0x18008bfd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bfde  mov     rcx, [rbp+188h]; this
0x18008bfe5  mov     r9d, esi; char *
0x18008bfe8  mov     edx, 12Eh; void *
0x18008bfed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bff2  test    rdi, rdi
0x18008bff5  jz      short loc_18008C008
0x18008bff7  mov     rcx, rdi; hMutex
0x18008bffa  call    cs:__imp_ReleaseMutex
0x18008c000  test    eax, eax
0x18008c002  jz      loc_18008C1FA
0x18008c008  mov     rcx, rbx; hObject
0x18008c00b  call    cs:__imp_CloseHandle
0x18008c011  test    eax, eax
0x18008c013  jz      loc_18008C20C
0x18008c019  mov     eax, esi
0x18008c01b  jmp     loc_18008C1B5
0x18008c020  mov     rax, [rsp+280h+hObject]
0x18008c025  lea     rcx, ds:0[rax*4]
0x18008c02d  test    rcx, rcx
0x18008c030  jz      short loc_18008C040
0x18008c032  mov     [r15], rcx
0x18008c035  mov     eax, [rcx]
0x18008c037  inc     eax
0x18008c039  mov     [rcx], eax
0x18008c03b  jmp     loc_18008C18B
0x18008c040  mov     rdx, r14; dwBytes
0x18008c043  mov     qword ptr [r15], 0
0x18008c04a  mov     ecx, 8; dwFlags
0x18008c04f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18008c054  mov     rsi, rax
0x18008c057  test    rax, rax
0x18008c05a  jnz     short loc_18008C07B
0x18008c05c  mov     rcx, [rbp+188h]; this
0x18008c063  mov     r14d, 8007000Eh
0x18008c069  mov     r9d, r14d; char *
0x18008c06c  mov     edx, 14Bh; void *
0x18008c071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c076  jmp     loc_18008C107
0x18008c07b  xorps   xmm0, xmm0
0x18008c07e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18008c084  test    sil, 3
0x18008c088  jnz     loc_18008C21E
0x18008c08e  mov     r9, rsi
0x18008c091  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18008c096  shr     r9, 2; unsigned __int64
0x18008c09a  lea     rcx, [rsp+280h+hObject]; this
0x18008c09f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18008c0a4  mov     r14d, eax
0x18008c0a7  test    eax, eax
0x18008c0a9  jns     loc_18008C147
0x18008c0af  mov     rcx, [rbp+188h]; this
0x18008c0b6  mov     r9d, eax; char *
0x18008c0b9  mov     edx, 14Eh; void *
0x18008c0be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c0c3  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18008c0c8  test    rcx, rcx
0x18008c0cb  jz      short loc_18008C0DB
0x18008c0cd  call    cs:__imp_CloseHandle
0x18008c0d3  test    eax, eax
0x18008c0d5  jz      loc_18008C224
0x18008c0db  mov     rcx, [rsp+280h+hObject]; hObject
0x18008c0e0  test    rcx, rcx
0x18008c0e3  jz      short loc_18008C0F3
0x18008c0e5  call    cs:__imp_CloseHandle
0x18008c0eb  test    eax, eax
0x18008c0ed  jz      loc_18008C236
0x18008c0f3  call    cs:__imp_GetProcessHeap
0x18008c0f9  mov     r8, rsi; lpMem
0x18008c0fc  xor     edx, edx; dwFlags
0x18008c0fe  mov     rcx, rax; hHeap
0x18008c101  call    cs:__imp_HeapFree
0x18008c107  mov     rcx, [rbp+188h]; this
0x18008c10e  mov     r9d, r14d; char *
0x18008c111  mov     edx, 137h; void *
0x18008c116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c11b  test    rdi, rdi
0x18008c11e  jz      short loc_18008C131
0x18008c120  mov     rcx, rdi; hMutex
0x18008c123  call    cs:__imp_ReleaseMutex
0x18008c129  test    eax, eax
0x18008c12b  jz      loc_18008C248
0x18008c131  mov     rcx, rbx; hObject
0x18008c134  call    cs:__imp_CloseHandle
0x18008c13a  test    eax, eax
0x18008c13c  jz      loc_18008C25A
0x18008c142  mov     eax, r14d
0x18008c145  jmp     short loc_18008C1B5
0x18008c147  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18008c14c  xor     edx, edx; Val
0x18008c14e  mov     dword ptr [rsi], 1
0x18008c154  lea     rcx, [rsi+22h]; void *
0x18008c158  mov     [rsi+8], rbx
0x18008c15c  movdqu  xmmword ptr [rsi+10h], xmm0
0x18008c161  lea     r8d, [rdx+56h]; Size
0x18008c165  call    memset
0x18008c16a  xor     edx, edx; Val
0x18008c16c  mov     word ptr [rsi+20h], 58h ; 'X'
0x18008c172  lea     rcx, [rsi+28h]; void *
0x18008c176  mov     dword ptr [rsi+24h], 1
0x18008c17d  lea     r8d, [rdx+50h]; Size
0x18008c181  call    memset
0x18008c186  xor     ebx, ebx
0x18008c188  mov     [r15], rsi
0x18008c18b  test    rdi, rdi
0x18008c18e  jz      short loc_18008C1A1
0x18008c190  mov     rcx, rdi; hMutex
0x18008c193  call    cs:__imp_ReleaseMutex
0x18008c199  test    eax, eax
0x18008c19b  jz      loc_18008C26C
0x18008c1a1  test    rbx, rbx
0x18008c1a4  jz      short loc_18008C1B3
0x18008c1a6  mov     rcx, rbx; hObject
0x18008c1a9  call    cs:__imp_CloseHandle
0x18008c1af  test    eax, eax
0x18008c1b1  jz      short loc_18008C1DB
0x18008c1b3  xor     eax, eax
0x18008c1b5  mov     rcx, [rbp+180h+var_30]
0x18008c1bc  xor     rcx, rsp; StackCookie
0x18008c1bf  call    __security_check_cookie
0x18008c1c4  mov     rbx, [rsp+280h+arg_10]
0x18008c1cc  add     rsp, 260h
0x18008c1d3  pop     r15
0x18008c1d5  pop     r14
0x18008c1d7  pop     rdi
0x18008c1d8  pop     rsi
0x18008c1d9  pop     rbp
0x18008c1da  retn
0x18008c1db  mov     rcx, [rbp+188h]; this
0x18008c1e2  mov     edx, 0A0Bh; void *
0x18008c1e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c1ed  mov     rcx, [rbp+188h]; this
0x18008c1f4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18008c1fa  mov     rcx, [rbp+188h]; this
0x18008c201  mov     edx, 0A15h; void *
0x18008c206  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c20c  mov     rcx, [rbp+188h]; this
0x18008c213  mov     edx, 0A0Bh; void *
0x18008c218  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c21e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18008c224  mov     rcx, [rbp+188h]; this
0x18008c22b  mov     edx, 0A0Bh; void *
0x18008c230  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c236  mov     rcx, [rbp+188h]; this
0x18008c23d  mov     edx, 0A0Bh; void *
0x18008c242  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c248  mov     rcx, [rbp+188h]; this
0x18008c24f  mov     edx, 0A15h; void *
0x18008c254  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c25a  mov     rcx, [rbp+188h]; this
0x18008c261  mov     edx, 0A0Bh; void *
0x18008c266  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008c26c  mov     rcx, [rbp+188h]; this
0x18008c273  mov     edx, 0A15h; void *
0x18008c278  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
